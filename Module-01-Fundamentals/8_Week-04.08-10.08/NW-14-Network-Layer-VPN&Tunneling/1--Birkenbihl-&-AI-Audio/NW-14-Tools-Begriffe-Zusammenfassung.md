# Kategorisierung VPN (Virtual Private Network) & Tunneling

## Übersichtstabelle

|**Kategorie**|**Details**|
|---|---|
|**Verwendete Tools**|• **VPN-Client-Software**: OpenVPN, WireGuard, ProtonVPN, NordVPN, Mullvad (Windows & macOS)<br>• **Windows VPN**: Integrierte VPN-Funktion (Einstellungen → Netzwerk und Internet → VPN)<br>• **macOS VPN**: Systemeinstellungen → Netzwerk → VPN (macOS; Windows: siehe oben)<br>• **OpenVPN Client**: Open-Source VPN-Client (beide Systeme)<br>• **WireGuard**: Moderner VPN-Client (beide Systeme)<br>• **Cisco AnyConnect**: Enterprise VPN-Lösung<br>• **FortiClient**: VPN-Client für FortiGate<br>• **Pulse Secure**: VPN-Client für Unternehmen<br>• **SSH**: Secure Shell für SSH-Tunneling (Terminal/PuTTY)<br>• **PuTTY**: SSH-Client mit Tunneling-Funktion (Windows)<br>• **Wireshark**: Paketanalyse für verschlüsselten VPN-Verkehr<br>• **traceroute/tracert**: VPN-Route nachverfolgen<br>• **ping**: VPN-Verbindung testen<br>• **Browser-Extensions**: VPN-Browser-Add-ons (Vorsicht: begrenzte Funktionalität)<br>• **Router-VPN**: VPN direkt auf Router (DD-WRT, OpenWrt)<br>• **IPsec-Tools**: racoon, strongSwan, Libreswan|
|**Technische Fachbegriffe**|• **VPN** (Virtual Private Network): Virtuelles privates Netzwerk<br>• **Tunneling**: Kapselung eines Protokolls in einem anderen<br>• **Encapsulation**: Einhüllung/Kapselung von Datenpaketen<br>• **Encryption**: Verschlüsselung von Daten<br>• **Decryption**: Entschlüsselung von Daten<br>• **VPN Server**: Server-Seite der VPN-Verbindung<br>• **VPN Client**: Client-Software auf dem Endgerät<br>• **VPN Tunnel**: Verschlüsselter virtueller Kanal<br>• **Authentication**: Authentifizierung/Identitätsprüfung<br>• **Confidentiality**: Vertraulichkeit der Daten<br>• **Integrity**: Datenintegrität (Schutz vor Manipulation)<br>• **Anonymity**: Anonymität (Verschleierung der Identität)<br>• **IP Masking**: IP-Adress-Verschleierung<br>• **IPsec** (Internet Protocol Security): Protokoll-Suite für VPN<br>• **SSL/TLS VPN**: VPN basierend auf SSL/TLS-Protokollen<br>• **OpenVPN**: Open-Source VPN-Protokoll und -Anwendung<br>• **WireGuard**: Modernes, schnelles VPN-Protokoll<br>• **PPTP** (Point-to-Point Tunneling Protocol): Veraltetes VPN-Protokoll<br>• **L2TP** (Layer 2 Tunneling Protocol): Tunneling ohne Verschlüsselung<br>• **L2TP/IPsec**: Kombination aus L2TP und IPsec<br>• **Remote Access VPN**: Client-to-Site VPN (Einzelnutzer → Netzwerk)<br>• **Site-to-Site VPN**: Netzwerk-zu-Netzwerk-Verbindung<br>• **Split Tunneling**: Geteilter Tunnel (nur bestimmter Traffic über VPN)<br>• **Full Tunneling**: Gesamter Traffic über VPN<br>• **Kill Switch**: Notabschaltung bei VPN-Ausfall<br>• **GRE** (Generic Routing Encapsulation): Tunneling-Protokoll ohne Verschlüsselung<br>• **SSH Tunneling**: Port-Weiterleitung über SSH<br>• **Port Forwarding**: Portweiterleitung<br>• **6to4, Teredo, ISATAP**: IPv6-über-IPv4-Tunnelmechanismen<br>• **Certificate**: Digitales Zertifikat für Authentifizierung<br>• **Multi-Factor Authentication (MFA)**: Mehrfaktor-Authentifizierung<br>• **Endpoint**: Endpunkt der VPN-Verbindung<br>• **Gateway**: VPN-Gateway (Eintrittspunkt ins Netzwerk)<br>• **Encryption Algorithm**: Verschlüsselungsalgorithmus (AES, ChaCha20)<br>• **Key Exchange**: Schlüsselaustausch-Mechanismus|
|**Wichtige Vokabeln**|• **Sicherer Tunnel**: Verschlüsselter Kommunikationskanal<br>• **Verschlüsselter Verkehr**: Codierter Datenverkehr<br>• **Abfangen**: Unbefugtes Mitlesen von Daten<br>• **Hacker**: Angreifer in unsicheren Netzwerken<br>• **Öffentliches WLAN**: Unsicheres öffentliches Netzwerk<br>• **ISP** (Internet Service Provider): Internetanbieter<br>• **Verfälschung**: Manipulation von Daten<br>• **Identitätsprüfung**: Verifizierung der Benutzeridentität<br>• **Verschleierung**: Verbergen der tatsächlichen IP<br>• **Zurückverfolgung**: Nachverfolgung von Online-Aktivitäten<br>• **Privatsphäre**: Schutz persönlicher Daten<br>• **Geografische Beschränkungen**: Regionale Zugriffssperren<br>• **Fernzugriff**: Remote-Zugang zu Netzwerken<br>• **Internes Netzwerk**: Privates Unternehmensnetzwerk<br>• **Vermittler**: Zwischenstation (VPN-Server)<br>• **Kapselung**: Umhüllung von Datenpaketen<br>• **Äußeres Protokoll**: Umhüllendes Protokoll (Tunnel)<br>• **Inneres Protokoll**: Eingekapseltes Originalprotokoll<br>• **Entpacken**: Entfernung der Kapselung<br>• **Kodiertes Format**: Verschlüsselter Zustand<br>• **Entschlüsselungsschlüssel**: Schlüssel zum Decodieren<br>• **Unverständliche Daten**: Nicht lesbare verschlüsselte Daten<br>• **Unbefugter Zugriff**: Zugriff ohne Berechtigung<br>• **Betrüger**: Gefälschter/falscher Server<br>• **Sicherheitslücke**: Schwachstelle im Protokoll<br>• **Zweigstelle**: Filiale/Nebenstelle<br>• **Hauptsitz**: Zentrale/Firmensitz<br>• **Nahtlose Kommunikation**: Reibungslose Verbindung<br>• **Wide Area Network (WAN)**: Großflächiges Netzwerk<br>• **Nicht vertrauenswürdiges Netzwerk**: Unsicheres Netzwerk<br>• **Interoperabilität**: Zusammenarbeit verschiedener Systeme<br>• **Netzpolitik**: Netzwerkrichtlinien<br>• **Punkt-zu-Punkt-Verbindung**: Direkte Verbindung zweier Punkte<br>• **Localhost**: Lokaler Computer (127.0.0.1)|

---

## 80/20-Zusammenfassung: Die wichtigsten 20% zum Verständnis von 80% von VPN & Tunneling

### **Was ist ein VPN? Der sichere Kurierdienst für deine Daten**

**VPN (Virtual Private Network)** = **Virtuelles Privates Netzwerk**

**Analogie**:

- **Ohne VPN**: Deine Daten reisen wie eine **offene Postkarte** durchs Internet – jeder kann mitlesen
- **Mit VPN**: Deine Daten reisen in einem **verschlossenen, gepanzerten Kuvert** – niemand kann den Inhalt sehen

**Kernidee**: VPN schafft einen **verschlüsselten Tunnel** zwischen deinem Gerät und einem VPN-Server

```
Dein Gerät  →→→  [Verschlüsselter Tunnel]  →→→  VPN-Server  →→→  Internet
            🔒 Niemand kann mitlesen 🔒
```

### **Die 5 Kernvorteile von VPN**

|Vorteil|Bedeutung|Beispiel|
|---|---|---|
|**1. Vertraulichkeit** 🔐|Verschlüsselung macht Daten unlesbar|Hacker im Café-WLAN sehen nur "Datensalat"|
|**2. Integrität** ✅|Schutz vor Datenmanipulation|Niemand kann deine Anfragen verändern|
|**3. Authentifizierung** 🔑|Überprüfung der Identität|Du verbindest dich mit dem echten Server|
|**4. Anonymität** 🕵️|Verschleierung deiner IP-Adresse|Websites sehen VPN-Server-IP, nicht deine|
|**5. Zugang** 🌐|Zugriff auf entfernte Netzwerke|Vom Homeoffice ins Firmennetzwerk|

### **Wie funktioniert ein VPN? Der 4-Schritte-Prozess**

#### **Schritt 1: Initiation (Start) 🚀**

```
Du startest VPN-Client auf deinem Gerät
Client kennt VPN-Server-Adresse
```

#### **Schritt 2: Authentication (Authentifizierung) 🔑**

```
Client ↔ Server: Wer bist du?
- Benutzername/Passwort
- Digitales Zertifikat
- Multi-Faktor-Authentifizierung (MFA)

Beide Seiten verifizieren sich gegenseitig
```

#### **Schritt 3: Tunnel Establishment (Tunnelaufbau) 🛡️**

```
Verschlüsselter Tunnel wird aufgebaut:

┌──────────────────────────────────────┐
│   Dein Gerät  ←→  VPN-Server         │
│   🔒 AES-256 Verschlüsselung 🔒      │
└──────────────────────────────────────┘

Alle Daten jetzt verschlüsselt!
```

#### **Schritt 4: Data Routing (Datenweiterleitung) 📡**

```
AUSGEHEND:
1. Dein Browser: "Ich will google.com"
2. VPN-Client: verschlüsselt → sendet an VPN-Server
3. VPN-Server: entschlüsselt → sendet an Google
4. Google denkt: "Anfrage kommt vom VPN-Server"

EINGEHEND:
1. Google: sendet Antwort an VPN-Server
2. VPN-Server: verschlüsselt → sendet an deinen Client
3. VPN-Client: entschlüsselt → zeigt Webseite

Du siehst die Webseite, aber niemand konnte mitlesen!
```

**Visuell**:

```
┌─────────────┐         ┌─────────────┐         ┌─────────────┐
│  Dein PC    │ 🔒══════│ VPN-Server  │═════════│   Google    │
│ (verschl.)  │ Tunnel  │ (sichtbar)  │ Normal  │ (denkt: VPN │
│             │         │             │         │ ist Client) │
└─────────────┘         └─────────────┘         └─────────────┘
```

### **Schlüsselkonzepte: Die drei Säulen von VPN**

#### **1. Tunneling (Kapselung) 📦**

**Was ist das?** Ein Protokoll wird in ein anderes "verpackt"

**Analogie**:

```
Kleinerer Umschlag (deine Daten)
      ↓
Steckst du in größeren, sichereren Umschlag (VPN-Protokoll)
      ↓
Äußerer Umschlag verbirgt den inneren
```

**Technisch**:

```
[HTTP-Anfrage] → Original-Datenpaket
      ↓ Einkapseln
[VPN-Header [HTTP-Anfrage]] → Verschlüsseltes VPN-Paket
      ↓ Durch Tunnel senden
      ↓ Am VPN-Server: Entpacken
[HTTP-Anfrage] → Originalpaket wird weitergeleitet
```

#### **2. Encryption (Verschlüsselung) 🔐**

**Was ist das?** Umwandlung von lesbaren Daten in unlesbaren Code

**Beispiel**:

```
VORHER (Klartext):
"Mein Passwort ist: geheim123"

NACHHER (verschlüsselt mit AES-256):
"a7k3!x9#mQ@pL5vR$nZ8wY2tF6..."

Nur mit Schlüssel wieder lesbar!
```

**Gängige Algorithmen**:

- **AES-256**: Industriestandard, sehr sicher
- **ChaCha20**: Modern, schnell auf mobilen Geräten

#### **3. Authentication (Authentifizierung) 🎫**

**Zwei Richtungen**:

**A) Benutzer → Server** (Du beweist, wer du bist):

- Benutzername/Passwort
- Digitales Zertifikat
- MFA (SMS-Code, Authenticator-App)

**B) Server → Client** (Server beweist, er ist echt):

- Digitales Zertifikat vom Server
- Verhindert Man-in-the-Middle-Angriffe

### **VPN-Protokolle: Die verschiedenen "Sprachen"**

|Protokoll|Sicherheit|Geschwindigkeit|Verwendung|Empfehlung|
|---|---|---|---|---|
|**WireGuard**|⭐⭐⭐⭐⭐|⚡⚡⚡⚡⚡|Modern, einfach|✅ **Sehr empfohlen**|
|**OpenVPN**|⭐⭐⭐⭐⭐|⚡⚡⚡|Flexibel, bewährt|✅ **Empfohlen**|
|**IPsec**|⭐⭐⭐⭐|⚡⚡⚡|Enterprise, robust|✅ Gut|
|**SSL/TLS VPN**|⭐⭐⭐⭐|⚡⚡⚡|Browser-basiert|✅ Gut|
|**L2TP/IPsec**|⭐⭐⭐|⚡⚡|Verbreitet|⚠️ OK|
|**PPTP**|⭐|⚡⚡⚡⚡|Veraltet|❌ **NICHT verwenden!**|

**Faustregel**: WireGuard oder OpenVPN wählen!

### **VPN-Typen: Remote Access vs. Site-to-Site**

#### **Remote Access VPN (Client-to-Site) 🏠→🏢**

**Was ist das?** Einzelnes Gerät verbindet sich mit einem Netzwerk

**Verwendung**:

```
┌──────────────┐         ┌──────────────────┐
│ Mitarbeiter  │ 🔒══════│ Firmennetzwerk   │
│ (Homeoffice) │  VPN    │ (Interne Server) │
└──────────────┘         └──────────────────┘
```

**Typische Szenarien**:

- 💼 Homeoffice-Zugriff auf Firmen-Intranet
- ✈️ Sicheres Surfen in öffentlichen WLANs (Flughafen, Café)
- 🎭 Umgehung geografischer Sperren (sekundär)

**Beispiel**:

```
Du sitzt im Café:
- Ohne VPN: Café-WLAN → Internet (unsicher!)
- Mit VPN: Café-WLAN → VPN-Server → Internet (sicher!)
```

#### **Site-to-Site VPN (Network-to-Network) 🏢↔🏢**

**Was ist das?** Zwei komplette Netzwerke werden verbunden

**Verwendung**:

```
┌──────────────┐         ┌──────────────────┐
│ Hauptsitz    │ 🔒══════│ Zweigstelle      │
│ (Berlin)     │  VPN    │ (München)        │
└──────────────┘         └──────────────────┘
```

**Vorteil**:

- Alle Geräte in beiden Netzwerken können miteinander kommunizieren
- Als wären sie im **selben lokalen Netzwerk**!

**Beispiel**:

```
Firma mit 3 Standorten:
Berlin (Hauptsitz) ←VPN→ München (Filiale)
        ↓ VPN
    Hamburg (Filiale)

Ergebnis: Alle Standorte = Ein virtuelles Netzwerk
```

### **Praktische VPN-Nutzung (Windows 11)**

#### **Methode 1: Integrierte Windows-VPN-Funktion**

1. **Einstellungen** öffnen (Windows + I)
2. **Netzwerk und Internet** → **VPN**
3. **VPN hinzufügen**
4. Eingabe:
    - VPN-Anbieter: Windows (integriert)
    - Verbindungsname: z.B. "Firma VPN"
    - Serveradresse: vpn.firma.de
    - VPN-Typ: Automatisch (oder spezifisch wählen)
    - Anmeldeinformationen: Benutzername/Passwort
5. **Verbinden**

#### **Methode 2: Dedizierte VPN-Client-Software**

**Beispiel: OpenVPN**

1. OpenVPN Client installieren (openvpn.net)
2. Konfigurationsdatei (.ovpn) vom VPN-Anbieter erhalten
3. Konfigurationsdatei importieren
4. Verbinden klicken
5. Authentifizierung eingeben

**Beispiel: WireGuard**

1. WireGuard installieren (wireguard.com)
2. Konfigurationsdatei importieren oder QR-Code scannen
3. Tunnel aktivieren

#### **VPN-Status überprüfen**

**IP-Adresse vor/nach VPN prüfen**:

```powershell
# Vor VPN:
Invoke-RestMethod -Uri "https://api.ipify.org"
# → Zeigt deine echte IP

# VPN aktivieren

# Nach VPN:
Invoke-RestMethod -Uri "https://api.ipify.org"
# → Zeigt VPN-Server-IP (anders!)
```

**Oder Browser**: https://www.whatismyip.com

### **Tunneling: Breiter als nur VPN**

**Tunneling-Konzept** = Kapselung eines Protokolls in einem anderen

**Warum?**

- ✅ **Sicherheit**: Verschlüsselung über unsichere Netze
- ✅ **Interoperabilität**: IPv6 über IPv4-Netz transportieren
- ✅ **Routing**: Traffic gezielt umleiten

#### **Weitere Tunneling-Beispiele**

**1. SSH Tunneling (Port Forwarding) 🔧**

```
Problem: Datenbank auf Server nur von "localhost" erreichbar

Lösung: SSH-Tunnel
ssh -L 3306:localhost:3306 user@remote-server

Jetzt: localhost:3306 auf deinem PC → Datenbank auf Server!
```

**Verwendung**:

- Sicherer Zugriff auf Remote-Datenbanken
- Umgehung von Firewalls (Vorsicht: Richtlinien beachten!)
- Verschlüsselung unsicherer Protokolle

**2. GRE (Generic Routing Encapsulation) 📦**

```
Tunnelt beliebige Protokolle über IP
ABER: Keine Verschlüsselung!
→ Oft kombiniert mit IPsec
```

**3. IPv6-über-IPv4-Tunnel 🌐**

```
Mechanismen: 6to4, Teredo, ISATAP
Problem: IPv6-Paket muss über IPv4-Netzwerk
Lösung: IPv6-Paket in IPv4-Paket verpacken
```

### **Split Tunneling vs. Full Tunneling**

**Full Tunneling** (Standard):

```
ALLER Traffic → VPN-Server → Internet

Vorteil: Maximale Sicherheit
Nachteil: Langsamer (alles geht über VPN)
```

**Split Tunneling**:

```
Firmen-Traffic → VPN-Server → Firmennetzwerk
Normal-Traffic → Direkt ins Internet (kein VPN)

Vorteil: Schneller für Netflix, YouTube etc.
Nachteil: Firmen-Daten besser geschützt als privater Traffic
```

**Konfigurieren** (je nach VPN-Client):

- OpenVPN: Routing-Einstellungen
- Windows VPN: Häkchen "Für Remoteverbindungen verwenden"

### **Wichtige VPN-Features**

**Kill Switch** (Notabschaltung):

```
Falls VPN-Verbindung abbricht:
→ Internetverbindung wird KOMPLETT gekappt
→ Verhindert "Datenleck" (keine unverschlüsselten Pakete)
```

**DNS Leak Protection**:

```
Problem: DNS-Anfragen könnten außerhalb des VPN laufen
Lösung: Alle DNS-Anfragen durch VPN-Tunnel zwingen
```

**Multi-Hop/Double VPN**:

```
Dein Gerät → VPN-Server 1 → VPN-Server 2 → Internet
Extra-Sicherheitsschicht (aber langsamer)
```

### **VPN-Sicherheit: Was zu beachten ist**

✅ **Gute VPN-Anbieter**:

- **No-Logs-Policy** (keine Aktivitätsprotokolle)
- **Starke Verschlüsselung** (AES-256, WireGuard)
- **Kill Switch**
- **DNS Leak Protection**
- **Sitz in datenschutzfreundlichem Land**

⚠️ **Vorsicht bei**:

- **Kostenlosen VPNs** (verkaufen oft deine Daten!)
- **VPNs mit schlechter Reputation**
- **Browser-VPN-Extensions** (oft nur Proxys, keine echte Verschlüsselung)

❌ **VPN schützt NICHT vor**:

- Viren/Malware (brauchst Antivirus)
- Phishing (brauchst gesunden Menschenverstand)
- Kompromittierten Geräten (brauchst Updates, Patches)

### **Typische VPN-Anwendungsfälle**

**1. Homeoffice** 💼:

```
Firma → VPN-Server aufsetzen
Mitarbeiter → VPN-Client installieren
Ergebnis: Sicherer Zugriff auf Intranet, Dateiserver, Datenbanken
```

**2. Öffentliches WLAN** ☕:

```
Café-WLAN → unsicher (Man-in-the-Middle möglich)
VPN aktivieren → alle Daten verschlüsselt
Hacker sehen nur: "Verschlüsselter Datensalat"
```

**3. Reisen** ✈️:

```
In Land X: Bestimmte Websites gesperrt
VPN → Server in Land Y
Websites denken: Anfrage kommt aus Land Y
Zugriff möglich (Rechtslage beachten!)
```

**4. Datenschutz** 🕵️:

```
ISP trackt deine Aktivitäten
Mit VPN: ISP sieht nur "Verbindung zu VPN-Server"
ISP weiß NICHT, welche Websites du besuchst
```

### **Kernbotschaft**

**VPN** schafft einen **verschlüsselten Tunnel** durchs Internet, der:

- 🔒 Deine Daten **schützt** (Verschlüsselung)
- 🕵️ Deine Identität **verschleiert** (IP-Maskierung)
- 🌐 Dir **Zugang** zu entfernten Netzwerken gibt

**Tunneling** ist das zugrunde liegende Konzept: **Ein Protokoll in ein anderes kapseln**

**Analogie finale**: VPN ist wie ein **gepanzerter Unterwasser-Tunnel** zwischen zwei Inseln:

- Niemand sieht, wer durchfährt (Anonymität)
- Niemand kann den Inhalt der Fahrzeuge sehen (Verschlüsselung)
- Sicher vor Angriffen von außen (Integrität)

**Wichtig**: VPN ist **kein Allheilmittel**, aber ein **mächtiges Werkzeug** für Sicherheit und Privatsphäre im Internet! 🛡️🔐🌐