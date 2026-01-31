# Kategorisierung: Erweiterte Wireshark-Funktionen

## Übersicht der verwendeten Elemente

|Kategorie|Begriffe/Tools|
|---|---|
|**Verwendete Tools (Windows 11)**|Wireshark, Display Filter Bar, Find Packet (Strg+F), Follow Stream, Statistics Menu, Endpoints Tool, Conversations Tool, Protocol Hierarchy, IO Graphs, Export Objects, Sample Captures (.pcap/.pcapng-Dateien), Wireshark Wiki|
|**Technische Fachbegriffe**|Display Filter, Capture Filter, Logical Operators (AND, OR, NOT), Comparison Operators, Protocol Stream, Stream Reassembly, Packet Details Pane, Hex Value Search, String Search, Endpoints, Conversations, Protocol Hierarchy, IO Graph, Object Export, HTTP Objects, SMB Objects, Malware Traffic Analysis, Packet Length (frame.len), TCP Flags, DNS Response Code, HTTP Request Method, Source/Destination Port, Network Bottleneck, Bandwidth Hog, Exfiltration|
|**Wichtige Vokabeln**|Netzwerkerfassung, Datenverkehrsanalyse, Filterausdruck, Paketsuche, Datenströme, Statistik, Traffic-Übersicht, Dateiextraktion, Netzwerkleistung, Protokollverteilung, Verkehrsspitzen, Zeitverlauf, Kommunikationspaare, Netzwerksegment, Payload, Syntaxprüfung, Fallunterscheidung (Case-Sensitive)|

## Bedeutungen

|Begriff|Bedeutung|
|---|---|
|**Verwendete Tools (Windows 11)**||
|Wireshark|Hauptwerkzeug zur Netzwerkpaketanalyse (gleiche Bedienung wie unter macOS)|
|Display Filter Bar|Eingabefeld oben in Wireshark zur Filterung angezeigter Pakete (grün = gültige Syntax, rot = ungültig)|
|Find Packet (Strg+F)|Suchfunktion in Wireshark (unter Windows: Strg+F statt Cmd+F) zum Finden spezifischer Daten in Paketen|
|Follow Stream|Funktion zur Rekonstruktion vollständiger Kommunikationsdatenströme aus einzelnen Paketen (Rechtsklick → Follow → TCP/UDP/HTTP Stream)|
|Statistics Menu|Menüpunkt mit statistischen Analysewerkzeugen für Netzwerkverkehr-Übersichten|
|Endpoints Tool|Statistik-Tool, das alle eindeutigen kommunizierenden Geräte und deren Datenvolumen auflistet|
|Conversations Tool|Statistik-Tool, das Kommunikation zwischen Gerätepaaren mit Details zu Paket-/Byte-Anzahl zeigt|
|Protocol Hierarchy|Hierarchische Darstellung der Protokollverteilung im Capture nach Schichten|
|IO Graphs|Visualisierung von Verkehrsraten (Pakete/Sekunde, Bytes/Sekunde) über Zeit|
|Export Objects|Funktion zum Extrahieren von Dateien aus Netzwerkverkehr (z.B. Bilder, HTML, Downloads)|
|Sample Captures|Vorgefertigte .pcap/.pcapng-Dateien zum Üben und Lernen verschiedener Protokolle|
|Wireshark Wiki|Online-Dokumentation mit Beispiel-Captures unter wiki.wireshark.org/SampleCaptures|
|**Technische Fachbegriffe**||
|Display Filter|Filter, der bereits erfasste Pakete aus- oder einblendet, ohne die Erfassung zu beeinflussen|
|Capture Filter|Filter, der VOR der Erfassung festlegt, welche Pakete gespeichert werden (in diesem Dokument nicht behandelt)|
|Logical Operators (AND, OR, NOT)|Logische Operatoren zum Kombinieren von Filterbedingungen: `&&` (und), `|
|Comparison Operators|Vergleichsoperatoren: `==` (gleich), `!=` (ungleich), `>` (größer), `<` (kleiner), `>=`, `<=`|
|Protocol Stream|Zusammenhängender Datenstrom eines Protokolls zwischen zwei Endpunkten|
|Stream Reassembly|Prozess des Zusammensetzens fragmentierter Pakete zu vollständigen Datenströmen|
|Packet Details Pane|Mittlerer Bereich in Wireshark, der Paketinhalte nach Protokollschichten aufschlüsselt|
|Hex Value Search|Suche nach rohen Byte-Werten in hexadezimaler Darstellung|
|String Search|Textsuche in den Rohdaten der Pakete|
|Endpoints|Eindeutige Kommunikations-Endpunkte (Geräte mit MAC/IP/Port)|
|Conversations|Kommunikation zwischen zwei spezifischen Endpunkten|
|Protocol Hierarchy|Baumstruktur der verwendeten Protokolle mit prozentualer Verteilung|
|IO Graph|Eingabe/Ausgabe-Diagramm zur Visualisierung von Netzwerkaktivität über Zeit|
|Object Export|Extrahieren von in Paketen enthaltenen Dateien (Bilder, Dokumente, etc.)|
|HTTP Objects|Über HTTP übertragene Dateien (HTML, Bilder, Scripts, Downloads)|
|SMB Objects|Über SMB (Server Message Block) übertragene Dateien in Windows-Netzwerken|
|Malware Traffic Analysis|Analyse von Netzwerkverkehr zur Identifikation schädlicher Kommunikation|
|Packet Length (frame.len)|Größe eines Pakets in Bytes (filterbares Feld in Wireshark)|
|TCP Flags|Steuerflags in TCP-Headern (SYN, ACK, RST, FIN, etc.)|
|DNS Response Code|Rückgabecode von DNS-Antworten (0 = Erfolg, andere = Fehler)|
|HTTP Request Method|HTTP-Anfragemethode (GET, POST, PUT, DELETE, etc.)|
|Source/Destination Port|Quell- und Zielport für Transport-Layer-Protokolle|
|Network Bottleneck|Engpass im Netzwerk, der Geschwindigkeit begrenzt|
|Bandwidth Hog|Anwendung oder Gerät, das übermäßig viel Bandbreite verbraucht|
|Exfiltration|Unerlaubtes Abfließen von Daten aus einem Netzwerk|
|**Wichtige Vokabeln**||
|Netzwerkerfassung|Capture – das Aufzeichnen von Netzwerkpaketen|
|Datenverkehrsanalyse|Untersuchung von Netzwerkaktivität zur Fehlersuche oder Sicherheitsanalyse|
|Filterausdruck|Bedingung zur Eingrenzung angezeigter Pakete|
|Paketsuche|Funktion zum Finden spezifischer Inhalte in erfassten Paketen|
|Datenströme|Zusammenhängende Kommunikation zwischen Anwendungen|
|Statistik|Quantitative Zusammenfassung von Netzwerkverkehr|
|Traffic-Übersicht|Hochrangige Ansicht der Netzwerkaktivität|
|Dateiextraktion|Herausziehen von Dateien aus Netzwerkpaketen|
|Netzwerkleistung|Geschwindigkeit und Effizienz der Datenübertragung|
|Protokollverteilung|Anteil verschiedener Protokolle am Gesamtverkehr|
|Verkehrsspitzen|Zeitpunkte mit besonders hoher Netzwerkaktivität|
|Zeitverlauf|Entwicklung von Metriken über die Zeit|
|Kommunikationspaare|Zwei Endpunkte, die miteinander kommunizieren|
|Netzwerksegment|Abgegrenzter Teil eines Netzwerks|
|Payload|Nutzdaten – eigentlicher Inhalt eines Pakets (ohne Header)|
|Syntaxprüfung|Überprüfung der Gültigkeit eines Filterausdrucks|
|Fallunterscheidung (Case-Sensitive)|Unterscheidung zwischen Groß- und Kleinschreibung bei Suchen|

---

## 80/20 Zusammenfassung: Erweiterte Wireshark-Funktionen

### Das Problem: Zu viele Daten

Netzwerk-Captures können schnell riesig werden. Einfache Filter (`ip.addr == ...`, `tcp.port == ...`) reichen oft nicht aus. Sie benötigen fortgeschrittene Werkzeuge, um:

- Verkehr präzise zu filtern
- Vollständige Konversationen zu rekonstruieren
- Statistische Übersichten zu erhalten
- Dateien direkt zu extrahieren

**Metapher**: Upgrade von einer Lupe zu einem kompletten Analysekit.

---

## 1. Erweiterte Display-Filter

### Logische Operatoren kombinieren Bedingungen

**UND-Verknüpfung (`&&` oder `and`):** Beide Bedingungen müssen erfüllt sein.

```
ip.src == 192.168.1.50 && tcp.dstport == 80
```

Zeigt nur Pakete, die VON 192.168.1.50 kommen UND an Port 80 gehen.

**ODER-Verknüpfung (`||` oder `or`):** Mindestens eine Bedingung muss erfüllt sein.

```
udp.port == 53 || tcp.port == 53
```

Zeigt DNS-Verkehr über UDP ODER TCP (Port 53).

**NICHT-Verknüpfung (`!` oder `not`):** Schließt Pakete aus. Nutzen Sie Klammern `()` für Klarheit.

```
ip.addr == 192.168.1.1 && !(tcp.port == 22)
```

Zeigt Verkehr mit 192.168.1.1, aber OHNE SSH (Port 22).

### Vergleichsoperatoren für präzise Filterung

|Operator|Bedeutung|Beispiel|
|---|---|---|
|`==`|Gleich|`tcp.port == 443`|
|`!=`|Ungleich|`dns.flags.rcode != 0` (DNS-Fehler)|
|`>`|Größer als|`frame.len > 1000` (große Pakete)|
|`<`|Kleiner als|`frame.len < 100` (kleine Pakete)|
|`>=`|Größer/gleich|`tcp.window_size >= 65535`|
|`<=`|Kleiner/gleich|`ip.ttl <= 10`|

### Spezifische Felder filtern

**HTTP-Beispiele:**

```
http.request.method == "POST"          # Nur POST-Anfragen
http.response.code == 404              # "Not Found"-Fehler
http.host contains "google"            # Hosts mit "google"
```

**TCP-Beispiele:**

```
tcp.flags.reset == 1                   # TCP-Reset-Pakete
tcp.flags.syn == 1 && tcp.flags.ack == 0  # SYN-Pakete (Verbindungsanfragen)
tcp.analysis.retransmission            # Wiederholte Übertragungen
```

**DNS-Beispiele:**

```
dns.qry.name contains ".com"           # Alle .com-Domains
dns.flags.rcode != 0                   # DNS-Fehlerantworten
```

**Tipp**: Rechtsklick auf ein Feld in der Packet Details Pane → "Apply as Filter" → "Selected" lernt Ihnen die Syntax!

---

## 2. Pakete finden: Find Packet (Strg+F)

**Zugriff**: `Edit > Find Packet...` oder **Strg+F** (Windows) / Cmd+F (Mac)

**Suchoptionen:**

1. **Display Filter**: Sucht nach Paketen, die einem Filterausdruck entsprechen
2. **Hex Value**: Sucht nach rohen Byte-Werten (z.B. `48 65 6C 6C 6F` für "Hello")
3. **String**: Textsuche in Paketdaten
    - **Case-sensitive**: Groß-/Kleinschreibung beachten
    - **Case-insensitive**: Groß-/Kleinschreibung ignorieren

**Praktische Anwendungen:**

```
String-Suche: "password"     # Unverschlüsselte Passwörter finden
String-Suche: "GET"          # HTTP-Anfragen finden
String-Suche: "google"       # Verkehr zu Google-Diensten
Hex-Suche: 89 50 4E 47      # PNG-Bilddateien (PNG-Signatur)
```

---

## 3. Follow Stream: Konversationen rekonstruieren

**Problem**: Anwendungsdaten sind oft über viele kleine Pakete verteilt. Einzeln betrachtet ergeben sie wenig Sinn.

**Lösung**: Wireshark rekonstruiert vollständige Datenströme.

### Verwendung

**Schritt-für-Schritt:**

1. Rechtsklick auf ein Paket einer Konversation
2. `Follow > [Protocol] Stream` auswählen
3. Neues Fenster zeigt rekonstruierte Daten

**Verfügbare Stream-Typen:**

- **TCP Stream**: Vollständige TCP-Verbindung
- **UDP Stream**: UDP-Datagramme derselben Konversation
- **HTTP Stream**: HTTP-Anfrage und -Antwort zusammen
- **TLS/SSL Stream**: Verschlüsselte Daten (nur wenn Sie den Schlüssel haben)

### Darstellung im Stream-Fenster

**Farbcodierung:**

- **Rot**: Daten vom Client zum Server
- **Blau**: Daten vom Server zum Client

**Anzeigeoptionen:**

- **ASCII**: Textdarstellung
- **Hex Dump**: Hexadezimal + ASCII
- **C Arrays**: Für Programmierung
- **Raw**: Rohdaten

### Praktisches Beispiel

**HTTP-Verkehr analysieren:**

1. Filter: `http`
2. Rechtsklick auf GET-Request
3. Follow → HTTP Stream
4. Sie sehen:

```
GET /index.html HTTP/1.1
Host: example.com
User-Agent: Mozilla/5.0...

HTTP/1.1 200 OK
Content-Type: text/html
...
<html>...</html>
```

**Nutzen:**

- Vollständige E-Mail-Nachrichten lesen
- Dateiübertragungen verfolgen
- API-Kommunikation verstehen
- Malware-Befehle analysieren

---

## 4. Statistics: Verkehr zusammenfassen

**Zugriff**: `Statistics`-Menü in Wireshark

### 4.1 Endpoints (`Statistics > Endpoints`)

**Zeigt**: Alle eindeutigen Geräte/Ports, die kommuniziert haben

**Registerkarten:**

- **Ethernet**: MAC-Adressen
- **IPv4/IPv6**: IP-Adressen mit Paket-/Byte-Anzahl
- **TCP/UDP**: Port-Nummern und Verbindungen

**Beantwortet**: _WER_ hat kommuniziert?

**Praktisch für:**

- Identifikation unbekannter Geräte im Netzwerk
- Finden von "Bandwidth Hogs" (sortiert nach Bytes)
- Erkennen ungewöhnlicher Ports

### 4.2 Conversations (`Statistics > Conversations`)

**Zeigt**: Kommunikation zwischen Gerätepaaren

**Spalten:**

- Address A ↔ Address B
- Packets A→B / B→A
- Bytes A→B / B→A
- Duration (Dauer)

**Beantwortet**: _WER sprach mit WEM, und wie viel?_

**Praktisch für:**

- Identifikation der aktivsten Verbindungen
- Erkennen ungewöhnlicher Kommunikationsmuster
- Aufspüren von Datenexfiltration

### 4.3 Protocol Hierarchy (`Statistics > Protocol Hierarchy`)

**Zeigt**: Baumstruktur aller Protokolle mit prozentualer Verteilung

**Beispiel:**

```
Frame                          100%
  Ethernet                     100%
    IPv4                       95%
      TCP                      80%
        HTTP                   40%
        TLS                    30%
        SSH                    10%
      UDP                      15%
        DNS                    10%
        QUIC                   5%
    IPv6                       5%
```

**Beantwortet**: _WELCHE_ Art von Verkehr liegt vor?

**Praktisch für:**

- Schneller Überblick über Netzwerkaktivität
- Erkennen unerwarteter Protokolle
- Baseline-Vergleiche (Normal vs. Angriff)

### 4.4 IO Graphs (`Statistics > IO Graphs`)

**Zeigt**: Verkehrsraten über Zeit als Diagramm

**Metriken:**

- Packets/sec (Pakete pro Sekunde)
- Bytes/sec (Bytes pro Sekunde)
- Bits/sec (Bits pro Sekunde)

**Features:**

- Mehrere Graphen gleichzeitig (verschiedene Filter in verschiedenen Farben)
- Zoom in Zeitbereiche
- Identifikation von Verkehrsspitzen

**Beantwortet**: _WANN_ traten Verkehrsspitzen auf?

**Praktisch für:**

- Erkennen von DDoS-Mustern
- Identifikation von Leistungsproblemen
- Korrelation mit Ereignissen

---

## 5. Export Objects: Dateien extrahieren

**Problem**: Dateien werden oft über HTTP, SMB oder andere Protokolle übertragen. Wie extrahiert man sie?

**Lösung**: `File > Export Objects > [Protocol]`

### HTTP Objects exportieren

**Schritt-für-Schritt:**

1. `File > Export Objects > HTTP...`
2. Fenster listet alle erkannten Objekte auf:
    - **Hostname**: Server, von dem heruntergeladen wurde
    - **Content Type**: MIME-Typ (image/jpeg, text/html, application/pdf)
    - **Bytes**: Dateigröße
    - **Filename**: Dateiname (falls vorhanden)
3. Objekt auswählen → "Save As..." → Speicherort wählen

**Was kann exportiert werden:**

- Bilder (JPEG, PNG, GIF)
- HTML-Seiten
- JavaScript-Dateien
- CSS-Stylesheets
- PDF-Dokumente
- EXE-Dateien (Vorsicht: Malware!)

### Andere Protokolle

**Verfügbare Export-Optionen:**

- **SMB/SMB2**: Windows-Dateifreigaben
- **DICOM**: Medizinische Bilder
- **IMF**: E-Mail-Nachrichten
- **TFTP**: Trivial File Transfer Protocol

### Sicherheitsanwendungen

**Malware-Analyse:**

- Extrahieren von schädlichen Payloads
- Untersuchung heruntergeladener Exploits
- Identifikation von Command-and-Control-Kommunikation

**Forensik:**

- Wiederherstellung exfiltrierter Daten
- Nachweis von Datendiebstahl
- Beweissicherung

**WICHTIG**: Exportierte Dateien können schädlich sein! Nur in isolierten/virtuellen Umgebungen öffnen.

---

## 6. Übungsmaterial: Sample Captures

**Quelle**: [https://wiki.wireshark.org/SampleCaptures](https://wiki.wireshark.org/SampleCaptures)

**Was ist das?** Sammlung vorgefertigter `.pcap`/`.pcapng`-Dateien zu verschiedenen Protokollen und Szenarien.

**Kategorien:**

- **Grundlegende Protokolle**: HTTP, DNS, DHCP, ARP, ICMP
- **Verschlüsselung**: TLS/SSL, IPsec, VPN
- **Spezialprotokolle**: VoIP (SIP, RTP), industrielle Protokolle
- **Netzwerkprobleme**: Fragmentierung, Retransmissions
- **Sicherheit**: Malware-Traffic, Angriffsmuster

**Empfohlene Starter-Captures:**

1. `http.cap` – Einfacher HTTP-Verkehr
2. `dns.pcap` – DNS-Anfragen und -Antworten
3. `arp-storm.pcap` – ARP-Probleme
4. Von **malware-traffic-analysis.net**: Echte Malware-Kommunikation (fortgeschritten)

**Wie nutzen:**

1. Capture herunterladen
2. In Wireshark öffnen (`File > Open`)
3. Verschiedene Filter ausprobieren
4. Streams folgen
5. Statistiken analysieren
6. Objekte exportieren

---

## Troubleshooting-Szenario: Langsames Netzwerk

**Ausgangslage**: Benutzer berichten langsame Performance.

**Schritt 1: Capture erstellen**

- Wireshark auf betroffenem Gerät oder Netzwerksegment starten
- 2-5 Minuten Verkehr erfassen

**Schritt 2: Protocol Hierarchy prüfen** `Statistics > Protocol Hierarchy`

- Unerwartete Protokolle?
- Übermäßiger Broadcast-Verkehr?
- Ungewöhnliche Verteilung?

**Schritt 3: Conversations analysieren** `Statistics > Conversations`

- Nach "Bytes" sortieren
- Top-Kommunikationspaare identifizieren
- Gibt es Bandwidth Hogs?

**Schritt 4: IO Graph visualisieren** `Statistics > IO Graphs`

- Verkehrsspitzen identifizieren
- Zeitkorrelation mit Beschwerden

**Schritt 5: Spezifischen Verkehr filtern**

```
ip.addr == [verdächtiges_gerät] && frame.len > 1000
```

- Große Pakete analysieren
- Streams folgen zur Ursachenermittlung

**Schritt 6: TCP-Probleme suchen**

```
tcp.analysis.flags
tcp.analysis.retransmission
tcp.analysis.lost_segment
```

- Wiederholte Übertragungen = Paketverlust?
- Hohe RTT (Round-Trip Time) = Latenz?

---

## Praktische Filter-Beispiele für Windows 11

**Typische Windows-Protokolle filtern:**

```
# SMB-Dateifreigabenverkehr
smb || smb2

# NetBIOS-Namensauflösung
nbns

# Windows Update
http.request.uri contains "windowsupdate"

# DHCP-Aktivität
bootp || dhcp

# LLMNR (Link-Local Multicast Name Resolution)
llmnr

# Kerberos-Authentifizierung
kerberos

# LDAP-Verzeichnisdienst
ldap
```

**Sicherheitsrelevante Filter:**

```
# Unverschlüsselte Credentials
http.authorization

# Fehlgeschlagene Verbindungen
tcp.flags.reset == 1

# Port-Scans erkennen (viele SYN, keine Antworten)
tcp.flags.syn == 1 && tcp.flags.ack == 0

# DNS-Tunnel erkennen (ungewöhnlich große Anfragen)
dns && frame.len > 512

# Außergewöhnlich viele Verbindungen zu einer IP
ip.addr == [verdächtige_IP]
```

---

## Kernpunkte

✅ **Logische Operatoren**: `&&` (und), `||` (oder), `!` (nicht) kombinieren Filter ✅ **Vergleichsoperatoren**: `>`, `<`, `==`, `!=` für präzise Bedingungen ✅ **Find Packet (Strg+F)**: Sucht Strings, Hex-Werte oder Filter-Ausdrücke ✅ **Follow Stream**: Rekonstruiert vollständige Konversationen aus Paketen ✅ **Endpoints**: Zeigt WER kommuniziert hat (nach Datenvolumen sortierbar) ✅ **Conversations**: Zeigt WER mit WEM kommuniziert hat (inkl. Richtung) ✅ **Protocol Hierarchy**: Zeigt WELCHE Protokolle vorhanden sind (prozentual) ✅ **IO Graphs**: Zeigt WANN Verkehrsspitzen auftraten (zeitliche Visualisierung) ✅ **Export Objects**: Extrahiert Dateien aus HTTP, SMB und anderen Protokollen ✅ **Sample Captures**: Üben mit echten Beispieldateien von wiki.wireshark.org

**Workflow für Analyse:**

1. **Übersicht**: Statistics → Protocol Hierarchy
2. **Auffälligkeiten**: Statistics → Conversations (nach Bytes sortieren)
3. **Zeitanalyse**: Statistics → IO Graphs
4. **Details**: Erweiterte Filter anwenden
5. **Vertiefung**: Follow Stream für spezifische Verbindungen
6. **Extraktion**: Export Objects bei Dateiübertragungen