# Kategorisierung DHCP (Dynamic Host Configuration Protocol)

## Übersichtstabelle

|**Kategorie**|**Details**|
|---|---|
|**Verwendete Tools**|• **Systemeinstellungen/Einstellungen**: Netzwerkkonfiguration prüfen (macOS: Systemeinstellungen → Netzwerk; Windows: Einstellungen → Netzwerk und Internet → Eigenschaften)<br>• **ipconfig**: DHCP-Informationen anzeigen (Windows: `ipconfig /all`, `ipconfig /release`, `ipconfig /renew`)<br>• **ifconfig**: Netzwerkschnittstellen anzeigen (macOS; Windows: `ipconfig`)<br>• **DHCP-Server-Software**: Windows Server DHCP, ISC DHCP Server, Dnsmasq<br>• **Router-Webinterface**: DHCP-Server-Einstellungen (Browser: z.B. 192.168.1.1)<br>• **Wireshark**: DHCP-Paketanalyse (DORA-Prozess beobachten)<br>• **netsh**: DHCP-Konfiguration (Windows: `netsh interface ip show config`)<br>• **PowerShell**: `Get-NetIPConfiguration`, `Get-DhcpServerv4Lease`<br>• **dhcpcd**: DHCP-Client-Daemon (Linux/macOS)<br>• **Event Viewer/Ereignisanzeige**: DHCP-Ereignisse protokollieren (Windows)<br>• **Terminal**: `sudo ipconfig set en0 DHCP` (macOS DHCP neu starten)<br>• **Network Troubleshooter**: Windows-Netzwerkproblembehandlung|
|**Technische Fachbegriffe**|• **DHCP** (Dynamic Host Configuration Protocol): Protokoll zur automatischen IP-Konfiguration<br>• **DHCP Server**: Server, der IP-Adressen vergibt<br>• **DHCP Client**: Gerät, das IP-Adresse anfordert<br>• **DORA Process**: Discover, Offer, Request, Acknowledge (4-Stufen-Handshake)<br>• **DHCPDISCOVER**: Entdeckungsnachricht des Clients (Broadcast)<br>• **DHCPOFFER**: Angebotsnachricht des Servers<br>• **DHCPREQUEST**: Anfragenachricht des Clients<br>• **DHCPACK**: Bestätigungsnachricht des Servers (Acknowledge)<br>• **DHCPNAK**: Negative Bestätigung (Negative Acknowledge)<br>• **IP Lease**: IP-Adress-Leasing/Mietvertrag<br>• **Lease Duration/Time**: Leasingdauer/Mietdauer<br>• **Lease Renewal**: Mietverlängerung/Erneuerung<br>• **IP Address Pool**: Pool verfügbarer IP-Adressen<br>• **Scope**: DHCP-Bereich/Adressbereich<br>• **Reservation**: Reservierung (feste IP für bestimmte MAC)<br>• **Broadcast**: Rundsendung an alle Geräte (255.255.255.255)<br>• **Unicast**: Direktsendung an ein bestimmtes Gerät<br>• **MAC Address**: Hardware-Adresse der Netzwerkkarte<br>• **APIPA** (Automatic Private IP Addressing): Automatische private IP-Vergabe<br>• **Link-Local Address**: Lokale Verbindungsadresse (169.254.x.x)<br>• **Default Gateway**: Standard-Gateway (Router-Adresse)<br>• **DNS Server**: Domain Name System Server<br>• **Subnet Mask**: Subnetzmaske<br>• **DHCP Options**: Zusätzliche Konfigurationsparameter<br>• **Relay Agent**: DHCP-Relay/Weiterleitungsagent<br>• **IP Conflict**: IP-Adresskonflikt (zwei Geräte, eine IP)<br>• **Static IP**: Statische/feste IP-Adresse<br>• **Dynamic IP**: Dynamische IP-Adresse|
|**Wichtige Vokabeln**|• **Automatische Konfiguration**: Selbstständige Einrichtung ohne manuelle Eingabe<br>• **Zuweisung**: Vergabe von IP-Adressen<br>• **Eindeutige Adresse**: Nur einmal im Netzwerk verwendbar<br>• **Manuelle Konfiguration**: Händisches Eintragen von Netzwerkeinstellungen<br>• **Fehleranfällig**: Hohes Risiko für menschliche Fehler<br>• **Mühsam**: Zeitaufwendig und arbeitsintensiv<br>• **Leasing**: Zeitlich begrenzte Vergabe<br>• **Zurückgeben**: IP-Adresse wieder freigeben<br>• **Pool**: Vorrat/Sammlung verfügbarer Adressen<br>• **Flüchtige Geräte**: Temporäre/wechselnde Geräte<br>• **Zentrales Management**: Verwaltung von einem Punkt aus<br>• **Broadcast-Nachricht**: Rundsendebenachrichtigung<br>• **Quell-IP**: Absender-IP-Adresse<br>• **Ziel-IP**: Empfänger-IP-Adresse<br>• **Vorgeschlagene IP**: Angebotene IP-Adresse<br>• **Angebot annehmen**: Zusage für IP-Adresse<br>• **Angebot ablehnen**: Absage für IP-Adresse<br>• **Mietvertrag abschließen**: Lease finalisieren<br>• **Ablaufen**: Zeitlich auslaufen/verfallen<br>• **Erneuern**: Verlängern der Leasingdauer<br>• **Reservierter Bereich**: Für spezielle Zwecke vorgesehener IP-Bereich<br>• **Eingeschränkte Konnektivität**: Limitierte Verbindungsfähigkeit<br>• **Selbst zugewiesene IP**: Automatisch vergebene Fallback-IP<br>• **Mobilität**: Beweglichkeit zwischen Netzwerken<br>• **Skalierbarkeit**: Anpassungsfähigkeit an wachsende Gerätezahl<br>• **Effizienz**: Optimale Ressourcennutzung|

---

## 80/20-Zusammenfassung: Die wichtigsten 20% zum Verständnis von 80% von DHCP

### **Was ist DHCP? Der automatische Netzwerk-Bibliothekar**

**DHCP (Dynamic Host Configuration Protocol)** ist ein **Netzwerkprotokoll**, das Geräten **automatisch** IP-Adressen und andere Netzwerkeinstellungen zuweist.

**Analogie**:

- **Ohne DHCP**: Wie eine Bibliothek ohne Bibliothekar – jeder sucht sich selbst einen Platz → Chaos, Doppelbelegungen
- **Mit DHCP**: Freundlicher Bibliothekar weist jedem einen eindeutigen Platz zu → Ordnung, keine Konflikte

**Kernfunktion**: Automatische Vergabe von:

- ✅ IP-Adresse
- ✅ Subnetzmaske
- ✅ Standard-Gateway (Router)
- ✅ DNS-Server-Adressen
- ✅ Weitere Netzwerkparameter

### **Warum ist DHCP so wichtig? Die 5 Hauptvorteile**

|Vorteil|Ohne DHCP|Mit DHCP|
|---|---|---|
|**Automatisierung**|❌ Jedes Gerät manuell konfigurieren|✅ Automatische Konfiguration|
|**Genauigkeit**|❌ Hohe Fehlerrate (Tippfehler, Konflikte)|✅ Keine IP-Konflikte|
|**Effizienz**|❌ Verschwendete IP-Adressen|✅ IP-Recycling durch Leasing|
|**Zentrales Management**|❌ Jedes Gerät einzeln ändern|✅ Änderungen zentral verteilen|
|**Skalierbarkeit**|❌ Unmöglich bei vielen Geräten|✅ Tausende Geräte problemlos|

**Beispiel**:

- **Ohne DHCP**: 1000 neue Mitarbeiter → IT muss 1000 Computer einzeln konfigurieren (Tage!)
- **Mit DHCP**: 1000 neue Mitarbeiter → Einstecken und sofort online (Sekunden!)

### **Netzwerk-Grundkonzepte (kurze Wiederholung)**

**IP-Adresse**: Eindeutige "Straßenadresse" im Netzwerk (z.B. 192.168.1.100)

**Subnetzmaske**: Trennt Netzwerk- und Host-Teil (z.B. 255.255.255.0)

**Standard-Gateway**: Router-Adresse zum Verlassen des lokalen Netzes (z.B. 192.168.1.1)

**DNS-Server**: Übersetzt Namen → IP-Adressen (z.B. google.com → 172.217.160.142)

### **Netzwerkkonfiguration prüfen (Windows 11)**

**Methode 1: Einstellungen (GUI)**

1. **Einstellungen** öffnen (Windows + I)
2. **Netzwerk und Internet** → **Eigenschaften**
3. Suche **IP-Zuweisung**: "Automatisch (DHCP)" bedeutet DHCP aktiv!
4. Anzeige: IP-Adresse, Subnetzmaske, Gateway, DNS-Server

**Methode 2: Kommandozeile**

```cmd
ipconfig /all
```

Suche nach:

- **DHCP aktiviert**: Ja/Nein
- **DHCP-Server**: IP-Adresse des DHCP-Servers
- **Lease erhalten**: Zeitstempel der IP-Vergabe
- **Lease läuft ab**: Ablaufzeitpunkt

### **Der DORA-Prozess: Wie DHCP funktioniert**

**DORA** = **D**iscover, **O**ffer, **R**equest, **A**cknowledge (4-Stufen-Handshake)

#### **Schritt 1: DISCOVER (Entdecken) 📡**

```
Neues Gerät startet im Netzwerk:
"Hallo? Gibt es hier einen DHCP-Server?"

Client sendet DHCPDISCOVER-Broadcast:
Quell-IP:  0.0.0.0      (hat noch keine IP!)
Ziel-IP:   255.255.255.255 (Broadcast an alle)
```

**Bedeutung**: Client sucht nach DHCP-Server im lokalen Netzwerk

#### **Schritt 2: OFFER (Angebot) 📬**

```
DHCP-Server antwortet:
"Ja, ich bin da! Hier ist ein Angebot für dich:"

Server sendet DHCPOFFER (Unicast oder Broadcast):
- Angebotene IP: 192.168.1.100
- Subnetzmaske: 255.255.255.0
- Gateway: 192.168.1.1
- DNS-Server: 8.8.8.8, 8.8.4.4
- Leasingdauer: 24 Stunden
```

**Hinweis**: Mehrere DHCP-Server können antworten → Client wählt (meist das erste Angebot)

#### **Schritt 3: REQUEST (Anfrage) 🙋**

```
Client wählt ein Angebot:
"Ich möchte die IP 192.168.1.100 von Server 192.168.1.1!"

Client sendet DHCPREQUEST-Broadcast:
- Informiert gewählten Server: "Ich nehme dein Angebot an"
- Informiert andere Server: "Eure Angebote lehne ich ab"
```

**Wichtig**: Broadcast, damit alle Server Bescheid wissen!

#### **Schritt 4: ACKNOWLEDGE (Bestätigung) ✅**

```
Server finalisiert Leasing:
"Bestätigt! Die IP gehört dir für 24 Stunden."

Server sendet DHCPACK (Unicast):
- Bestätigt alle Parameter
- Client konfiguriert Netzwerkschnittstelle
- Client ist nun online! 🎉
```

**Alternative**: **DHCPNAK** (Negative Acknowledge) = Ablehnung → Client muss neu starten

### **Visueller DORA-Ablauf**

```
┌────────────┐                           ┌─────────────┐
│   Client   │                           │ DHCP Server │
│ (Dein PC)  │                           │  (Router)   │
└────────────┘                           └─────────────┘
      │                                          │
      │  1. DHCPDISCOVER (Broadcast)            │
      │ ──────────────────────────────────────> │
      │  "Wer kann mir eine IP geben?"          │
      │                                          │
      │  2. DHCPOFFER (Unicast/Broadcast)       │
      │ <────────────────────────────────────── │
      │  "Hier: 192.168.1.100, 24h Lease"       │
      │                                          │
      │  3. DHCPREQUEST (Broadcast)             │
      │ ──────────────────────────────────────> │
      │  "Ich nehme 192.168.1.100 an!"          │
      │                                          │
      │  4. DHCPACK (Unicast)                   │
      │ <────────────────────────────────────── │
      │  "Bestätigt! Viel Spaß!"                │
      │                                          │
      ▼                                          ▼
[Client konfiguriert IP und ist online]
```

**Zeitaufwand**: Der gesamte DORA-Prozess dauert nur **wenige Sekunden**!

### **IP-Leasing: Zeitlich begrenzte Vergabe**

**Warum nicht dauerhaft?**

- ✅ **Effiziente Ressourcennutzung**: Verlassene Geräte geben IPs frei
- ✅ **Flexibilität**: Geräte können zwischen Netzwerken wechseln
- ✅ **Dynamische Anpassung**: Parameter-Änderungen werden verteilt

**Leasingdauer**:

- **Heimnetzwerk**: Typisch 24 Stunden
- **Firmennetzwerk**: Oft 8 Stunden (Arbeitstag)
- **Öffentliches WLAN**: 1-2 Stunden

**Lease-Erneuerung**:

```
Lease-Zeitstrahl (24 Stunden):

0h ────────────── 12h ────────────── 24h
│                  │                   │
IP vergeben        Erneuerung         Ablauf
                   versuchen          (falls keine
                   (50% erreicht)     Erneuerung)
```

**Automatische Erneuerung**:

- Bei **50%** der Leasingdauer: Client sendet **DHCPREQUEST** direkt an Server
- Bei **87,5%** der Leasingdauer: Falls keine Antwort, erneuter Versuch (Broadcast)
- Bei **100%**: Falls keine Antwort → DORA-Prozess neu starten

**Ergebnis**: Client merkt davon nichts – nahtlose Erneuerung im Hintergrund!

### **Wichtige DHCP-Informationen (DHCP Options)**

**Standardparameter**:

- **IP-Adresse**: Eindeutige Adresse im Netzwerk
- **Subnetzmaske**: Netzwerkgrenzen definieren
- **Standard-Gateway**: Router-IP
- **DNS-Server**: Namensauflösung
- **Leasingdauer**: Gültigkeitszeitraum

**Zusätzliche Optionen** (optional):

- **Domänenname**: z.B. "firma.local"
- **NTP-Server**: Zeitsynchronisation
- **TFTP-Server**: Network Boot
- **WINS-Server**: Windows-Namensauflösung (veraltet)
- **Und viele mehr** (über 100 definierte DHCP-Optionen!)

### **DHCP-Rollen**

**DHCP-Server**:

- Verwaltet Pool von IP-Adressen
- Beantwortet Client-Anfragen
- Führt Leasing-Datenbank
- **Typisch**: Router, dedizierter Server, Windows Server

**DHCP-Client**:

- Fordert IP-Konfiguration an
- Erneuert Leasing automatisch
- **Fast jedes Gerät**: Computer, Smartphones, Drucker, Smart-TVs, IoT-Geräte

### **Praktische DHCP-Befehle (Windows 11)**

**IP-Adresse freigeben** (Lease zurückgeben):

```cmd
ipconfig /release
```

→ Client gibt IP-Adresse auf

**Neue IP-Adresse anfordern**:

```cmd
ipconfig /renew
```

→ DORA-Prozess wird gestartet

**DHCP-Informationen anzeigen**:

```cmd
ipconfig /all
```

→ Zeigt DHCP-Server, Lease-Zeiten, etc.

**Kombination** (Netzwerk neu starten):

```cmd
ipconfig /release && ipconfig /renew
```

### **Was passiert ohne DHCP-Server? APIPA**

**Szenario**: Gerät auf DHCP konfiguriert, aber kein DHCP-Server erreichbar

**Lösung**: **APIPA (Automatic Private IP Addressing)** = **Link-Local Addressing**

```
DHCP-Anfrage sendet...
Keine Antwort...
Timeout...

→ Betriebssystem vergibt selbst eine IP:
   169.254.x.x (z.B. 169.254.123.45)
   Subnetzmaske: 255.255.0.0
```

**APIPA-Eigenschaften**:

- ✅ Kommunikation mit anderen APIPA-Geräten im **selben lokalen Segment** möglich
- ❌ **Kein** Gateway (kein Internet-Zugriff)
- ❌ **Keine** DNS-Server
- ❌ **Keine** Kommunikation mit anderen Netzwerken

**Fehlermeldungen**:

- Windows: "Eingeschränkte Konnektivität"
- macOS: "Selbst zugewiesene IP-Adresse"
- Typisches Zeichen: IP beginnt mit **169.254.x.x**

**Problemlösung**:

1. DHCP-Server prüfen (läuft er?)
2. Netzwerkverbindung prüfen (Kabel, WLAN)
3. `ipconfig /renew` ausführen

### **DHCP-Reservierungen: Feste IPs für spezielle Geräte**

**Problem**: Manche Geräte brauchen immer dieselbe IP (z.B. Drucker, Server)

**Lösung**: **DHCP-Reservation** (Statisches Leasing)

```
DHCP-Server-Konfiguration:
"Wenn Gerät mit MAC-Adresse AA:BB:CC:DD:EE:FF
 eine IP anfragt, gib immer 192.168.1.50"
```

**Vorteile**:

- ✅ Gerät behält immer dieselbe IP
- ✅ Trotzdem DHCP-Management (zentrale Verwaltung)
- ✅ Keine manuelle Konfiguration am Gerät nötig

**Typische Anwendung**:

- Netzwerkdrucker (damit alle die feste IP kennen)
- Server (für DNS-Einträge)
- Netzwerk-Kameras
- Gaming-Konsolen (Port-Forwarding)

### **DHCP-Relay-Agent: DHCP über Netzwerkgrenzen**

**Problem**: DHCP-DISCOVER ist Broadcast → erreicht nur lokales Netzwerk

**Szenario**: Firma mit mehreren VLANs, ein zentraler DHCP-Server

**Lösung**: **DHCP-Relay-Agent** (auch: IP Helper)

```
Client (VLAN 10)  →  Router (Relay)  →  DHCP-Server (VLAN 1)
                     wandelt Broadcast
                     in Unicast um
```

**Funktion**:

- Router empfängt DHCP-Broadcast
- Leitet als **Unicast** an DHCP-Server weiter
- Server antwortet → Router leitet zurück an Client

**Ergebnis**: Ein DHCP-Server kann **mehrere Netzwerke** bedienen!

### **DHCP-Sicherheit: Potenzielle Risiken**

⚠️ **Rogue DHCP Server** (Schurken-DHCP-Server):

- Angreifer setzt eigenen DHCP-Server auf
- Verteilt falsche Gateway/DNS-Adressen
- **Resultat**: Man-in-the-Middle-Angriff, Traffic-Umleitung

⚠️ **DHCP Starvation Attack**:

- Angreifer fordert alle verfügbaren IPs an
- Pool erschöpft → legitime Clients bekommen keine IP
- **Resultat**: Denial of Service (DoS)

⚠️ **DHCP Spoofing**:

- Angreifer gibt sich als DHCP-Server aus
- Antwortet schneller als legitimer Server

**Schutzmaßnahmen**:

- ✅ **DHCP Snooping** (Switch-Feature): Nur autorisierte DHCP-Server erlauben
- ✅ **Port Security**: MAC-Adressen limitieren
- ✅ **802.1X**: Netzwerk-Authentifizierung

### **Kernbotschaft**

**DHCP** ist das **unsichtbare Helferlein**, das moderne Netzwerke überhaupt erst praktikabel macht:

**Ohne DHCP**:

- ❌ Jedes Gerät manuell konfigurieren
- ❌ IP-Konflikte häufig
- ❌ Änderungen = enormer Aufwand
- ❌ Nicht skalierbar

**Mit DHCP**:

- ✅ Plug-and-Play: Einstecken und loslegen
- ✅ Keine Konflikte
- ✅ Zentrale Verwaltung
- ✅ Tausende Geräte problemlos

**Der DORA-Prozess** (Discover → Offer → Request → Acknowledge) passiert **blitzschnell** und **automatisch** – du merkst gar nicht, dass er läuft!

**Analogie finale**: DHCP ist wie ein **selbstbedienender Parkplatz-Automat** – du fährst rein, bekommst automatisch einen freien Platz zugewiesen, nutzt ihn für eine gewisse Zeit, und wenn du gehst, wird er für andere wieder frei. Kein Chaos, keine Doppelbelegungen, maximale Effizienz! 🚗🅿️📶