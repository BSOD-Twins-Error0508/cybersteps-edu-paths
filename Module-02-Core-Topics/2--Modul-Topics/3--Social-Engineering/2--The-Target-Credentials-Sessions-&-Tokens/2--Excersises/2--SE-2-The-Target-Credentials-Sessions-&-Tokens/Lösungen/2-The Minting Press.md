# 🚀 KOMPLETTE ANLEITUNG: FLASK JWT API MIT POWER SHELL TESTS

## 📋 FINALES FLASK SCRIPT (app.py)

```python
from flask import Flask, request, jsonify
import jwt
import datetime
from functools import wraps

app = Flask(__name__)
app.config['SECRET_KEY'] = 'dein_super_geheimer_schluessel_hier_123'

# Demo Credentials
VALID_USERNAME = "admin"
VALID_PASSWORD = "password123"

# Token Required Decorator
def token_required(f):
    @wraps(f)
    def decorated(*args, **kwargs):
        token = None
        
        # Header Extraction
        if 'Authorization' in request.headers:
            auth_header = request.headers['Authorization']
            if auth_header.startswith('Bearer '):
                token = auth_header.split(' ')[1]
        
        if not token:
            return jsonify({"error": "Token fehlt. Bitte zuerst einloggen."}), 401
        
        try:
            # Token Validation
            data = jwt.decode(token, app.config['SECRET_KEY'], algorithms=['HS256'])
            current_user = data['username']
        except jwt.ExpiredSignatureError:
            return jsonify({"error": "Token abgelaufen. Bitte neu einloggen."}), 401
        except jwt.InvalidTokenError:
            return jsonify({"error": "Ungültiges Token."}), 401
        
        return f(current_user, *args, **kwargs)
    
    return decorated

# Routes
@app.route('/')
def home():
    return jsonify({
        "message": "Willkommen zur JWT Demo API!",
        "endpoints": {
            "login": "POST /login mit JSON {username, password}",
            "protected": "GET /protected mit Authorization: Bearer <token>"
        }
    })

@app.route('/login', methods=['POST'])
def login():
    auth_data = request.get_json()
    
    if not auth_data:
        return jsonify({"error": "JSON Body mit username und password erforderlich"}), 400
    
    username = auth_data.get('username')
    password = auth_data.get('password')
    
    # Credentials validieren
    if username != VALID_USERNAME or password != VALID_PASSWORD:
        return jsonify({"error": "Ungültige Anmeldedaten"}), 401
    
    try:
        # Token erstellen
        payload = {
            'username': username,
            'exp': datetime.datetime.utcnow() + datetime.timedelta(minutes=5)
        }
        
        token = jwt.encode(payload, app.config['SECRET_KEY'], algorithm='HS256')
        
        return jsonify({
            "message": "Login erfolgreich",
            "token": token,
            "expires_in": "5 minutes"
        })
        
    except Exception as e:
        return jsonify({"error": "Server Fehler beim Token erstellen"}), 500

@app.route('/protected')
@token_required
def protected(current_user):
    return jsonify({
        "message": f"Willkommen {current_user}, Sie haben Zugang zum geschützten Bereich!",
        "user": current_user,
        "timestamp": datetime.datetime.utcnow().isoformat()
    })

# Error Handler
@app.errorhandler(404)
def not_found(error):
    return jsonify({"error": "Endpoint nicht gefunden"}), 404

@app.errorhandler(500)
def internal_error(error):
    return jsonify({"error": "Interner Server Fehler"}), 500

if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0', port=5000)
```

## 🔧 SETUP ANLEITUNG

### Schritt 1: Virtual Environment Setup
```powershell
# In PowerShell als Administrator öffnen
# Zum Projektverzeichnis navigieren
cd E:\Work-Area\Maximal-3-Dinge-Heute-2025-09-25\Cybersteps\SE-2-EX-2

# Virtual Environment erstellen
python -m venv jwt_env

# Environment aktivieren
jwt_env\Scripts\Activate.ps1

# Required Packages installieren
pip install flask pyjwt
```

### Schritt 2: Flask Server starten
```powershell
# In EINEM PowerShell Fenster (Server-Fenster)
cd E:\Work-Area\Maximal-3-Dinge-Heute-2025-09-25\Cybersteps\SE-2-EX-2
jwt_env\Scripts\Activate.ps1
python app.py
```

**Erwartete Ausgabe:**
```
 * Serving Flask app 'app'
 * Debug mode: on
WARNING: This is a development server. Do not use it in a production deployment.
 * Running on all addresses (0.0.0.0)
 * Running on http://127.0.0.1:5000
 * Running on http://[::1]:5000
```

## 🧪 VOLLSTÄNDIGE POWER SHELL TEST SUITE

### PowerShell Test Script (tests.ps1)
```powershell
# tests.ps1 - Komplette Test Suite für JWT API
Write-Host "🎯 FLASK JWT API TEST SUITE" -ForegroundColor Green
Write-Host "==========================================" -ForegroundColor Yellow

# Test 1: Home Route
Write-Host "`n1️⃣  TEST: Home Route (Öffentlich)" -ForegroundColor Cyan
try {
    $response = Invoke-RestMethod -Uri "http://localhost:5000/" -Method GET
    Write-Host "✅ ERFOLG: $($response.message)" -ForegroundColor Green
    Write-Host "   Endpoints: $($response.endpoints | ConvertTo-Json -Compress)"
} catch {
    Write-Host "❌ FEHLER: $($_.Exception.Message)" -ForegroundColor Red
}

# Test 2: Login mit falschen Credentials
Write-Host "`n2️⃣  TEST: Login mit falschen Credentials" -ForegroundColor Cyan
try {
    $body = @{
        username = "falscher_user"
        password = "falsches_passwort"
    } | ConvertTo-Json
    
    $response = Invoke-RestMethod -Uri "http://localhost:5000/login" -Method POST -Body $body -ContentType "application/json"
    Write-Host "❌ UNERWARTET: Login hat trotz falscher Daten funktioniert" -ForegroundColor Red
} catch {
    Write-Host "✅ ERFOLG: Login korrekt abgelehnt mit: $($_.ErrorDetails.Message)" -ForegroundColor Green
}

# Test 3: Login mit richtigen Credentials
Write-Host "`n3️⃣  TEST: Login mit richtigen Credentials" -ForegroundColor Cyan
try {
    $body = @{
        username = "admin"
        password = "password123"
    } | ConvertTo-Json
    
    $response = Invoke-RestMethod -Uri "http://localhost:5000/login" -Method POST -Body $body -ContentType "application/json"
    $global:token = $response.token
    Write-Host "✅ ERFOLG: $($response.message)" -ForegroundColor Green
    Write-Host "   Token: $($global:token)" -ForegroundColor Gray
    Write-Host "   Läuft ab in: $($response.expires_in)" -ForegroundColor Gray
} catch {
    Write-Host "❌ FEHLER: $($_.Exception.Message)" -ForegroundColor Red
}

# Test 4: Geschützte Route OHNE Token
Write-Host "`n4️⃣  TEST: Geschützte Route ohne Token" -ForegroundColor Cyan
try {
    $response = Invoke-RestMethod -Uri "http://localhost:5000/protected" -Method GET
    Write-Host "❌ UNERWARTET: Zugriff ohne Token funktioniert" -ForegroundColor Red
} catch {
    Write-Host "✅ ERFOLG: Zugriff korrekt verweigert mit Status: $($_.Exception.Response.StatusCode.value__)" -ForegroundColor Green
}

# Test 5: Geschützte Route MIT Token
Write-Host "`n5️⃣  TEST: Geschützte Route mit Token" -ForegroundColor Cyan
if ($global:token) {
    try {
        $headers = @{
            "Authorization" = "Bearer $global:token"
        }
        $response = Invoke-RestMethod -Uri "http://localhost:5000/protected" -Method GET -Headers $headers
        Write-Host "✅ ERFOLG: $($response.message)" -ForegroundColor Green
        Write-Host "   User: $($response.user)" -ForegroundColor Gray
        Write-Host "   Zeit: $($response.timestamp)" -ForegroundColor Gray
    } catch {
        Write-Host "❌ FEHLER: $($_.Exception.Message)" -ForegroundColor Red
    }
} else {
    Write-Host "⚠️  WARNUNG: Kein Token verfügbar - Test 3 muss zuerst erfolgreich sein" -ForegroundColor Yellow
}

# Test 6: Token Decoding Test (Optional)
Write-Host "`n6️⃣  TEST: Token Inhalt analysieren" -ForegroundColor Cyan
if ($global:token) {
    try {
        # Token in seine Bestandteile zerlegen
        $tokenParts = $global:token.Split('.')
        $header = [System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String($tokenParts[0]))
        $payload = [System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String($tokenParts[1]))
        
        Write-Host "🔐 Token Analyse:" -ForegroundColor Magenta
        Write-Host "   Header: $header" -ForegroundColor Gray
        Write-Host "   Payload: $payload" -ForegroundColor Gray
        Write-Host "   Signatur: [Verschlüsselt mit Secret Key]" -ForegroundColor Gray
    } catch {
        Write-Host "⚠️  Hinweis: Token konnte nicht analysiert werden" -ForegroundColor Yellow
    }
}

Write-Host "`n🎉 TEST SUITE ABGESCHLOSSEN" -ForegroundColor Green
Write-Host "==========================================" -ForegroundColor Yellow
```

### Einfache Manuelle Tests
```powershell
# Einfache Test-Befehle zum Kopieren & Einfügen:

# 1. Home Route testen
curl http://localhost:5000/

# 2. Login mit falschen Daten
$body = '{"username":"wrong","password":"wrong"}'
Invoke-RestMethod -Uri "http://localhost:5000/login" -Method POST -Body $body -ContentType "application/json"

# 3. Erfolgreicher Login
$body = '{"username":"admin","password":"password123"}'
$response = Invoke-RestMethod -Uri "http://localhost:5000/login" -Method POST -Body $body -ContentType "application/json"
$token = $response.token

# 4. Geschützte Route ohne Token testen
try { Invoke-RestMethod -Uri "http://localhost:5000/protected" -Method GET } catch { $_.Exception.Message }

# 5. Geschützte Route mit Token
Invoke-RestMethod -Uri "http://localhost:5000/protected" -Method GET -Headers @{ "Authorization" = "Bearer $token" }

# 6. Token ablaufen lassen und neu testen (nach 5 Minuten)
Start-Sleep -Seconds 300  # 5 Minuten warten
try { 
    Invoke-RestMethod -Uri "http://localhost:5000/protected" -Method GET -Headers @{ "Authorization" = "Bearer $token" }
} catch { 
    Write-Host "Token abgelaufen: $($_.Exception.Message)" 
}
```

## 🎯 ERWARTETE TEST ERGEBNISSE

### ✅ Erfolgreicher Testlauf sollte zeigen:
```
🎯 FLASK JWT API TEST SUITE
==========================================

1️⃣  TEST: Home Route (Öffentlich)
✅ ERFOLG: Willkommen zur JWT Demo API!

2️⃣  TEST: Login mit falschen Credentials  
✅ ERFOLG: Login korrekt abgelehnt mit: {"error": "Ungültige Anmeldedaten"}

3️⃣  TEST: Login mit richtigen Credentials
✅ ERFOLG: Login erfolgreich
   Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
   Läuft ab in: 5 minutes

4️⃣  TEST: Geschützte Route ohne Token
✅ ERFOLG: Zugriff korrekt verweigert mit Status: 401

5️⃣  TEST: Geschützte Route mit Token
✅ ERFOLG: Willkommen admin, Sie haben Zugang zum geschützten Bereich!

6️⃣  TEST: Token Inhalt analysieren
🔐 Token Analyse:
   Header: {"alg":"HS256","typ":"JWT"}
   Payload: {"username":"admin","exp":1759168707}

🎉 TEST SUITE ABGESCHLOSSEN
==========================================
```

## 🔄 AUTOMATISIERTER TEST DURCHLAUF

### Komplette Test-Datei erstellen (run_tests.ps1):
```powershell
# run_tests.ps1 - Automatischer Testlauf
param(
    [string]$BaseUrl = "http://localhost:5000"
)

function Test-Endpoint {
    param($Name, $Url, $Method = "GET", $Body = $null, $Headers = @{})
    
    Write-Host "Testing: $Name" -ForegroundColor Cyan
    try {
        if ($Body) {
            $response = Invoke-RestMethod -Uri $Url -Method $Method -Body $Body -ContentType "application/json" -Headers $Headers
        } else {
            $response = Invoke-RestMethod -Uri $Url -Method $Method -Headers $Headers
        }
        Write-Host "  ✅ SUCCESS" -ForegroundColor Green
        return $response
    } catch {
        Write-Host "  ❌ FAILED: $($_.Exception.Message)" -ForegroundColor Red
        return $null
    }
}

# Haupt-Testlauf
Write-Host "🚀 STARTING AUTOMATED JWT API TESTS" -ForegroundColor Magenta

# 1. Home
Test-Endpoint -Name "Home Route" -Url "$BaseUrl/"

# 2. Failed Login
$badLoginBody = '{"username":"wrong","password":"wrong"}'
Test-Endpoint -Name "Failed Login" -Url "$BaseUrl/login" -Method "POST" -Body $badLoginBody

# 3. Successful Login
$goodLoginBody = '{"username":"admin","password":"password123"}'
$loginResponse = Test-Endpoint -Name "Successful Login" -Url "$BaseUrl/login" -Method "POST" -Body $goodLoginBody

if ($loginResponse -and $loginResponse.token) {
    $token = $loginResponse.token
    Write-Host "  🔐 Token received: $($token.Substring(0, 20))..." -ForegroundColor Gray
    
    # 4. Protected without token (should fail)
    Test-Endpoint -Name "Protected without token" -Url "$BaseUrl/protected"
    
    # 5. Protected with token (should succeed)
    $headers = @{"Authorization" = "Bearer $token"}
    Test-Endpoint -Name "Protected with token" -Url "$BaseUrl/protected" -Headers $headers
} else {
    Write-Host "  ⚠️  Cannot proceed - no token received" -ForegroundColor Yellow
}

Write-Host "`n🎯 ALL TESTS COMPLETED" -ForegroundColor Magenta
```

## 📝 FEHLERBEHEBUNG

### Häufige Probleme und Lösungen:

**Problem: "Port 5000 already in use"**
```powershell
# Anderen Prozess auf Port 5000 finden
netstat -ano | findstr :5000

# Prozess beenden (PID von oben verwenden)
taskkill /PID [PID] /F

# Oder mit anderem Port starten
python app.py --port 5001
```

**Problem: "ModuleNotFoundError: No module named 'flask'"**
```powershell
# Virtual Environment sicher aktivieren
jwt_env\Scripts\Activate.ps1
pip install flask pyjwt
```

**Problem: PowerShell Execution Policy**
```powershell
# Execution Policy für aktuelle Session ändern
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

# Oder Script direkt ausführen
powershell -ExecutionPolicy Bypass -File .\tests.ps1
```

## 🎉 ZUSAMMENFASSUNG

Du hast jetzt:
- ✅ **Voll funktionsfähige Flask JWT API**
- ✅ **Komplette PowerShell Test Suite**
- ✅ **Automatisierte Test Scripts**
- ✅ **Detaillierte Fehlerbehebung**

**Nächste Schritte:**
1. Flask Server in einem Fenster starten
2. Tests in einem zweiten Fenster ausführen
3. Bei Erfolg: Weitere Features hinzufügen

**Viel Erfolg beim Testen! 🚀**