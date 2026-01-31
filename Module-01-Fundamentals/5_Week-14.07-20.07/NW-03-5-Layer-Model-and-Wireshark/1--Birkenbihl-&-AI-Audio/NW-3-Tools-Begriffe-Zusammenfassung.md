# Kategorisierung: Netzwerkmodelle und Wireshark

## Übersicht der verwendeten Elemente

|Kategorie|Begriffe/Tools|
|---|---|
|**Verwendete Tools (Windows 11)**|Wireshark, Npcap (Windows-Paketerfassungstreiber), Windows PowerShell, Kommandozeile (cmd), Netzwerk- und Freigabecenter, Geräte-Manager, Taskmanager (Netzwerkaktivität), Ressourcenmonitor|
|**Technische Fachbegriffe**|OSI-Modell (7 Schichten), TCP/IP-Modell (5 Schichten), Application Layer, Transport Layer, Network Layer, Data Link Layer, Physical Layer, Encapsulation (Verkapselung), Decapsulation (Entkapselung), Packet Sniffer, Protocol Analyzer, TCP (Transmission Control Protocol), UDP (User Datagram Protocol), IP (Internet Protocol), HTTP/HTTPS, SMTP, DNS, Ethernet, Wi-Fi (802.11), MAC-Adresse, IP-Adresse, Port-Nummer, Segment, Datagram, Packet (Paket), Frame (Rahmen), Bits, Header, Trailer, Three-Way Handshake, ICMP, ARP, Routing, Interoperability|
|**Wichtige Vokabeln**|Netzwerkschicht, Protokoll, Datenübertragung, Netzwerkverkehr, Paketerfassung, Schnittstelle (Interface), Logische Adressierung, Physische Adressierung, Zuverlässigkeit, Fehlerbehebung (Troubleshooting), Modularität, Standardisierung, End-to-End-Kommunikation, Process-to-Process-Kommunikation, Lokales Netzwerk, Router, Switch|

## Bedeutungen

|Begriff|Bedeutung|
|---|---|
|**Verwendete Tools (Windows 11)**||
|Wireshark|Kostenloses, leistungsstarkes Netzwerkanalyse-Tool zur Erfassung und Untersuchung von Netzwerkverkehr in Echtzeit|
|Npcap|Windows-Treiber zur Paketerfassung (ersetzt WinPcap), notwendig für Wireshark unter Windows – wird bei der Wireshark-Installation mitinstalliert|
|Windows PowerShell|Erweiterte Kommandozeile für Netzwerkbefehle wie `Test-NetConnection`, `Get-NetAdapter`, `ipconfig`|
|Kommandozeile (cmd)|Klassische Windows-Eingabeaufforderung für Netzwerkbefehle wie `ping`, `tracert`, `netstat`, `ipconfig`|
|Netzwerk- und Freigabecenter|Windows-Systemsteuerungsbereich zur Verwaltung von Netzwerkverbindungen und -einstellungen|
|Geräte-Manager|Windows-Tool zur Verwaltung von Hardware, einschließlich Netzwerkadaptern|
|Taskmanager (Netzwerkaktivität)|Zeigt aktuelle Netzwerkauslastung nach Prozessen an (Strg+Shift+Esc → Registerkarte "Leistung")|
|Ressourcenmonitor|Detaillierte Ansicht der Netzwerkaktivität einzelner Prozesse und Verbindungen|
|**Technische Fachbegriffe**||
|OSI-Modell|7-Schichten-Referenzmodell der ISO zur theoretischen Beschreibung von Netzwerkkommunikation|
|TCP/IP-Modell|Praktisches 4- oder 5-Schichten-Modell, das die tatsächliche Implementierung des Internets beschreibt|
|Application Layer (Anwendungsschicht)|Oberste Schicht – Schnittstelle für Anwendungen (z.B. Webbrowser, E-Mail) zu Netzwerkdiensten|
|Transport Layer (Transportschicht)|Schicht 4 – Process-to-Process-Kommunikation, Zuverlässigkeit, Flusskontrolle (TCP/UDP)|
|Network Layer (Netzwerkschicht)|Schicht 3 – Logische Adressierung (IP), Routing zwischen verschiedenen Netzwerken|
|Data Link Layer (Sicherungsschicht)|Schicht 2 – Datenübertragung im lokalen Netzwerksegment, physische Adressierung (MAC)|
|Physical Layer (Bitübertragungsschicht)|Schicht 1 – Übertragung roher Bits über physische Medien (Kabel, Funk)|
|Encapsulation (Verkapselung)|Prozess des Hinzufügens von Schicht-spezifischen Headern beim Senden von Daten (von oben nach unten)|
|Decapsulation (Entkapselung)|Prozess des Entfernens von Schicht-spezifischen Headern beim Empfangen von Daten (von unten nach oben)|
|Packet Sniffer|Tool zum Abfangen und Analysieren von Netzwerkpaketen|
|Protocol Analyzer|Anderer Name für Packet Sniffer – analysiert Protokolle in erfassten Daten|
|TCP (Transmission Control Protocol)|Verbindungsorientiertes, zuverlässiges Transportprotokoll mit Fehlerkorrektur und Bestätigung|
|UDP (User Datagram Protocol)|Verbindungsloses, schnelles Transportprotokoll ohne Garantie für Zustellung|
|IP (Internet Protocol)|Protokoll für logische Adressierung und Routing auf Netzwerkschicht|
|HTTP/HTTPS|Protokolle für Webbrowser-Kommunikation (HTTPS ist verschlüsselt)|
|SMTP|Simple Mail Transfer Protocol – zum Versenden von E-Mails|
|DNS|Domain Name System – übersetzt Domainnamen in IP-Adressen|
|Ethernet|Kabelgebundene Netzwerktechnologie der Data Link Layer|
|Wi-Fi (802.11)|Drahtlose Netzwerktechnologie der Data Link Layer|
|MAC-Adresse|Media Access Control – eindeutige physische Hardware-Adresse einer Netzwerkkarte (z.B. 00:1A:2B:3C:4D:5E)|
|IP-Adresse|Logische Netzwerkadresse zur Identifikation von Geräten im Netzwerk (z.B. 192.168.1.1)|
|Port-Nummer|Nummer zur Identifikation spezifischer Anwendungen/Dienste auf einem Gerät (z.B. Port 80 für HTTP)|
|Segment|Dateneinheit auf der Transportschicht (TCP)|
|Datagram|Dateneinheit auf der Transportschicht (UDP)|
|Packet (Paket)|Dateneinheit auf der Netzwerkschicht (IP)|
|Frame (Rahmen)|Dateneinheit auf der Data Link Layer (Ethernet/Wi-Fi)|
|Bits|Kleinste Dateneinheit (0 oder 1) auf der Physical Layer|
|Header|Steuerdaten am Anfang einer Dateneinheit mit schichtspezifischen Informationen|
|Trailer|Steuerdaten am Ende einer Dateneinheit (z.B. Prüfsumme bei Ethernet)|
|Three-Way Handshake|Dreistufiger TCP-Verbindungsaufbau (SYN, SYN-ACK, ACK)|
|ICMP|Internet Control Message Protocol – für Diagnose (z.B. ping)|
|ARP|Address Resolution Protocol – übersetzt IP-Adressen in MAC-Adressen|
|Routing|Prozess der Wegfindung für Datenpakete durch verschiedene Netzwerke|
|Interoperability|Fähigkeit verschiedener Systeme, zusammenzuarbeiten|
|**Wichtige Vokabeln**||
|Netzwerkschicht|Eine Ebene im Netzwerkmodell mit spezifischen Aufgaben|
|Protokoll|Regelwerk für Kommunikation zwischen Systemen|
|Datenübertragung|Transport von Informationen über ein Netzwerk|
|Netzwerkverkehr|Gesamtheit aller Daten, die über ein Netzwerk fließen|
|Paketerfassung|Das Abfangen von Datenpaketen zur Analyse|
|Schnittstelle (Interface)|Verbindungspunkt zwischen System und Netzwerk (z.B. Netzwerkkarte)|
|Logische Adressierung|Adressierung auf Netzwerkebene (IP-Adressen) – kann sich ändern|
|Physische Adressierung|Hardware-basierte Adressierung (MAC-Adressen) – fest zugeordnet|
|Zuverlässigkeit|Garantie, dass Daten vollständig und korrekt ankommen|
|Fehlerbehebung (Troubleshooting)|Systematisches Identifizieren und Lösen von Problemen|
|Modularität|Aufteilung in unabhängige, austauschbare Module|
|Standardisierung|Einheitliche Regeln für Interoperabilität|
|End-to-End-Kommunikation|Verbindung zwischen zwei Endpunkten über mehrere Netzwerke|
|Process-to-Process-Kommunikation|Direkte Verbindung zwischen Anwendungen auf verschiedenen Geräten|
|Lokales Netzwerk|Netzwerk in einem begrenzten geografischen Bereich (z.B. Heimnetzwerk)|
|Router|Gerät zum Verbinden verschiedener Netzwerke und Weiterleiten von Paketen|
|Switch|Gerät zum Verbinden von Geräten in einem lokalen Netzwerk|

---

## 80/20 Zusammenfassung: Netzwerkmodelle und Wireshark

### Warum brauchen wir Netzwerkmodelle?

Netzwerkkommunikation ist komplex – von einem Klick im Browser bis zur Datenübertragung über den Globus laufen unzählige Prozesse ab. Ohne strukturierte Modelle wäre dies kaum zu bewältigen.

**Vorteile strukturierter Modelle:**

- **Komplexitätsreduzierung**: Aufteilung in überschaubare Schichten
- **Interoperabilität**: Mac, Windows, Linux können problemlos kommunizieren
- **Innovation**: Entwickler können sich auf eine Schicht konzentrieren, ohne alle Details kennen zu müssen
- **Fehlerbehebung**: Systematisches Eingrenzen von Problemen nach Schichten

**Die zwei Hauptmodelle:**

1. **OSI-Modell**: 7 Schichten, theoretisch, sehr detailliert
2. **TCP/IP-Modell**: 4-5 Schichten, praktisch, entspricht der Internet-Realität

Wir konzentrieren uns auf das **5-Schichten TCP/IP-Modell** als praktische Balance.

### Das 5-Schichten TCP/IP-Modell (mit Briefpost-Analogie)

#### **1. Application Layer (Anwendungsschicht)**

**Aufgabe**: Schnittstelle für Software zu Netzwerkdiensten

**Analogie**: Sie schreiben den Brief oder bereiten den Paketinhalt vor – das eigentliche "WAS" wird gesendet

**Beispiele**:

- HTTP/HTTPS (Websites)
- SMTP (E-Mail versenden)
- DNS (Namensauflösung)

**Dateneinheit**: Message/Data

---

#### **2. Transport Layer (Transportschicht)**

**Aufgabe**: Process-to-Process-Kommunikation, Zuverlässigkeit, Flusskontrolle

**Analogie**: Wahl des Versanddienstes und Angabe der Abteilung/Person im Zielgebäude

- Einschreiben mit Sendungsverfolgung = **TCP** (zuverlässig, langsamer)
- Normale Postkarte = **UDP** (schnell, keine Garantie)

**Wichtige Protokolle**:

- **TCP**: Verbindungsorientiert, zuverlässig, Fehlerkorrektur (für E-Mail, Websites, Dateiübertragung)
- **UDP**: Verbindungslos, schnell, keine Garantie (für Streaming, Online-Gaming, VoIP)

**Port-Nummern**: Wie Abteilungsnummern – identifizieren die richtige Anwendung (Port 80 = HTTP, Port 443 = HTTPS)

**Dateneinheit**: Segment (TCP) / Datagram (UDP)

---

#### **3. Network Layer (Netzwerkschicht/Internet Layer)**

**Aufgabe**: Logische Adressierung (IP-Adressen), Routing zwischen Netzwerken

**Analogie**: Vollständige Zieladresse (Straße, Stadt, PLZ) und Absenderadresse auf dem Umschlag

**Wichtige Protokolle**:

- **IP** (Internet Protocol): Adressierung und Weiterleitung
- **ICMP**: Diagnose (z.B. `ping`-Befehl)

**Dateneinheit**: Packet (Paket)

---

#### **4. Data Link Layer (Sicherungsschicht)**

**Aufgabe**: Übertragung zwischen Geräten im **gleichen** lokalen Netzwerk, physische Adressierung (MAC)

**Analogie**: Lokaler Postbote liefert zur spezifischen Hausnummer in seiner Route

**Wichtige Technologien**:

- **Ethernet**: Kabelgebundene LANs
- **Wi-Fi (802.11)**: Drahtlose LANs
- **ARP**: Übersetzt IP-Adressen in MAC-Adressen

**MAC-Adresse**: Eindeutige Hardware-Adresse (z.B. 00:1A:2B:3C:4D:5E)

**Dateneinheit**: Frame (Rahmen)

---

#### **5. Physical Layer (Bitübertragungsschicht)**

**Aufgabe**: Übertragung roher Bits (0 und 1) über physische Medien

**Analogie**: Straßen, Postautos, Flugzeuge, Papier – die physische Infrastruktur

**Beispiele**:

- Ethernet-Kabel (Kupfer)
- Glasfaserkabel
- Wi-Fi-Funkwellen
- Stecker, Spannungspegel

**Dateneinheit**: Bits (0 und 1)

---

### Encapsulation (Verkapselung) und Decapsulation (Entkapselung)

**Beim Senden (Encapsulation – von oben nach unten):**

```
[Application] Daten erstellen
     ↓
[Transport] + Transport-Header (Port, TCP/UDP-Info)
     ↓
[Network] + IP-Header (Quell- und Ziel-IP)
     ↓
[Data Link] + Ethernet-Header + Trailer (Quell- und Ziel-MAC)
     ↓
[Physical] Umwandlung in Bits zur Übertragung
```

**Mail-Analogie**: Brief schreiben → in Serviceumschlag mit Abteilung → in Adressumschlag mit voller Adresse → in Postbeutel mit Hausnummer

**Beim Empfangen (Decapsulation – von unten nach oben):** Jede Schicht entfernt ihre eigenen Header/Trailer und reicht die Daten an die nächsthöhere Schicht weiter.

---

### Wireshark: Netzwerkverkehr sichtbar machen

**Was ist Wireshark?** Ein kostenloser **Network Protocol Analyzer** (Packet Sniffer), der Netzwerkverkehr erfasst und nach Protokollschichten dekodiert anzeigt.

**Metapher**: Spezialbrille, die alle "Briefumschläge" und deren Beschriftungen sichtbar macht

**Anwendungsfälle:**

- Alle Schicht-Header sichtbar machen (Ethernet, IP, TCP/UDP)
- Protokollverhalten analysieren (z.B. TCP Three-Way Handshake beobachten)
- Netzwerkprobleme diagnostizieren
- Malware-Traffic untersuchen
- Sicherheitsanalysen durchführen

**In Cybersecurity unverzichtbar für:**

- Incident Response
- Malware-Analyse
- Netzwerksicherheitstests
- Forensik

---

### Wireshark Installation unter Windows 11

**Schritt-für-Schritt:**

1. **Download**: [https://www.wireshark.org/download.html](https://www.wireshark.org/download.html)
2. **Windows Installer wählen**: `.exe`-Datei für Windows herunterladen
3. **Installation starten**: Installer ausführen
4. **Npcap installieren**:
    - Während der Wireshark-Installation wird **Npcap** (Paketerfassungstreiber für Windows) automatisch angeboten
    - **Wichtig**: Npcap-Option aktivieren – ohne diesen Treiber kann Wireshark keinen Traffic erfassen
    - Alternative: Separate Installation von [npcap.com](https://npcap.com/)
5. **Installation abschließen**: Standardeinstellungen sind meist ausreichend
6. **Wireshark starten**:
    - Programm im Startmenü finden
    - Administrator-Rechte können für manche Netzwerk-Interfaces erforderlich sein
7. **Netzwerk-Interface auswählen**:
    - Beim Start zeigt Wireshark verfügbare Schnittstellen (Ethernet, Wi-Fi)
    - Doppelklick auf Interface startet Paketerfassung

**Erste Schritte:**

- Öffnen Sie Wireshark
- Wählen Sie Ihr aktives Netzwerk-Interface (z.B. Wi-Fi oder Ethernet)
- Klicken Sie auf den blauen Hai (Start Capture) oder Doppelklick auf Interface
- Beobachten Sie, wie Pakete in Echtzeit erfasst werden
- Stoppen Sie die Erfassung mit dem roten Quadrat

---

### Praktisches Beispiel: E-Mail mit großem Anhang

**Szenario**: Sie versenden eine E-Mail mit 5 MB Foto-Anhang

**Wie funktioniert die Verkapselung?**

1. **Application Layer**: E-Mail-Client (Outlook, Thunderbird) erstellt Nachricht mit SMTP-Format
2. **Transport Layer**:
    - **TCP** wird verwendet (E-Mail braucht Zuverlässigkeit)
    - Große Datei wird in viele kleine **Segmente** (ca. 1.500 Bytes) aufgeteilt
    - Jedes Segment erhält Sequenznummer für korrekte Zusammensetzung
    - Port-Nummern: Quellport (zufällig) → Zielport 25 (SMTP)
3. **Network Layer**: Jedes Segment wird in IP-Pakete verpackt mit:
    - Ihrer IP-Adresse (Absender)
    - Server-IP-Adresse (Empfänger)
4. **Data Link Layer**: Pakete werden in Ethernet-/Wi-Fi-Frames verpackt mit:
    - MAC-Adresse Ihrer Netzwerkkarte
    - MAC-Adresse des Routers
5. **Physical Layer**: Frames werden in elektrische Signale (Kabel) oder Funkwellen (Wi-Fi) umgewandelt

**Beim Empfänger**: Kompletter Rückwärtsprozess (Decapsulation), TCP setzt alle Segmente in korrekter Reihenfolge zusammen

---

### Fehlerbehebung mit dem Schichtenmodell

**Problem**: Website lädt nicht

**Systematisches Troubleshooting nach Schichten:**

1. **Physical Layer**: Ist das Kabel eingesteckt? Wi-Fi aktiviert? Netzwerkadapter funktioniert?
2. **Data Link Layer**: Haben Sie eine gültige lokale Verbindung? Switch/Router erreichbar?
3. **Network Layer**: Haben Sie eine IP-Adresse? Funktioniert DNS? (`ping 8.8.8.8`, `ipconfig /all`)
4. **Transport Layer**: Sind die richtigen Ports offen? Firewall blockiert?
5. **Application Layer**: Browser-Cache? Falsche URL? Server-Fehler?

**Windows-Diagnosetools:**

```powershell
ipconfig /all              # IP-Konfiguration anzeigen
ping google.com            # Netzwerkkonnektivität testen
tracert google.com         # Route zum Ziel verfolgen
netstat -an                # Aktive Verbindungen anzeigen
Test-NetConnection google.com -Port 443  # Port-Test (PowerShell)
```

---

### Kernpunkte

✅ **5-Schichten-Modell**: Application → Transport → Network → Data Link → Physical ✅ **TCP vs. UDP**: TCP = zuverlässig + langsamer, UDP = schnell + keine Garantie ✅ **IP-Adressen**: Logische Adressierung für globales Routing (Netzwerkschicht) ✅ **MAC-Adressen**: Physische Adressierung für lokale Netzwerke (Data Link Layer) ✅ **Port-Nummern**: Identifizieren spezifische Anwendungen (Transportschicht) ✅ **Encapsulation**: Jede Schicht fügt Header hinzu (oben nach unten) ✅ **Wireshark**: Macht alle Schichten und Header sichtbar – essentielles Tool für Cybersecurity ✅ **Npcap**: Windows-Treiber für Paketerfassung – muss installiert sein