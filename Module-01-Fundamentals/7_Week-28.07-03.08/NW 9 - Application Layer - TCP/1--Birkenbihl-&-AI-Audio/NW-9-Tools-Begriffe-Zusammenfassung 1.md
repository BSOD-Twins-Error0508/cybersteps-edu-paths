# Kategorisierung TCP (Transmission Control Protocol)

## Übersichtstabelle

|**Kategorie**|**Details**|
|---|---|
|**Verwendete Tools**|• **Wireshark**: Netzwerkanalyse-Tool zum Mitschneiden und Analysieren von TCP-Paketen (Windows & macOS)<br>• **tcpdump**: Kommandozeilen-Paket-Analyzer (macOS vorinstalliert; Windows: WinDump oder über WSL)<br>• **netstat**: Zeigt aktive TCP-Verbindungen an (beide Systeme: `netstat -an`)<br>• **telnet**: Zum Testen von TCP-Verbindungen zu bestimmten Ports (Windows: aktivierbar über Features; macOS vorinstalliert)<br>• **nmap**: Port-Scanner zum Überprüfen offener TCP-Ports (Installation erforderlich auf beiden Systemen)<br>• **iperf/iperf3**: TCP-Bandbreiten- und Performance-Tests<br>• **Resource Monitor/Activity Monitor**: Netzwerkverbindungen überwachen (Windows: Ressourcenmonitor; macOS: Aktivitätsanzeige)<br>• **PowerShell/Terminal**: `Test-NetConnection` (Windows), `nc` (macOS) für TCP-Tests|
|**Technische Fachbegriffe**|• **TCP** (Transmission Control Protocol): Verbindungsorientiertes Transport-Protokoll<br>• **Transport Layer**: Transportschicht (Schicht 4 im OSI-Modell)<br>• **Connection-Oriented**: Verbindungsorientiert (erfordert Verbindungsaufbau)<br>• **Three-Way Handshake**: Drei-Wege-Handshake zum Verbindungsaufbau<br>• **SYN** (Synchronize): Synchronisierungs-Flag zum Verbindungsstart<br>• **ACK** (Acknowledgment): Bestätigungs-Flag für empfangene Daten<br>• **FIN** (Finish): Beendigungs-Flag zum Verbindungsabbau<br>• **RST** (Reset): Zurücksetzen der Verbindung (abrupter Abbruch)<br>• **PSH** (Push): Sofortige Datenweitergabe an Anwendung<br>• **URG** (Urgent): Dringlichkeits-Flag für prioritäre Daten<br>• **Sequence Number**: Sequenznummer zur Datensortierung<br>• **ISN** (Initial Sequence Number): Anfangs-Sequenznummer<br>• **Port Number**: Port-Nummer zur Anwendungsidentifikation (0-65535)<br>• **Socket**: Kombination aus IP-Adresse und Port-Nummer<br>• **Well-Known Ports**: Standard-Ports (0-1023) für bekannte Dienste<br>• **Registered Ports**: Registrierte Ports (1024-49151)<br>• **Ephemeral Ports**: Dynamische/temporäre Ports (49152-65535)<br>• **Sliding Window**: Fenster-Mechanismus für Flusskontrolle<br>• **Window Size**: Fenstergröße (verfügbarer Pufferspeicher)<br>• **Flow Control**: Flusskontrolle (verhindert Empfänger-Überlastung)<br>• **Congestion Control**: Staukontrolle (verhindert Netzwerk-Überlastung)<br>• **Retransmission**: Neuübertragung verlorener Pakete<br>• **Checksum**: Prüfsumme zur Fehlererkennung<br>• **TCP Header**: TCP-Kopfzeile mit Steuerungsinformationen<br>• **Four-Way Handshake**: Vier-Wege-Handshake zum Verbindungsabbau<br>• **RFC 793**: Technische Spezifikation des TCP-Protokolls<br>• **Buffer**: Pufferspeicher für empfangene Daten<br>• **Segment**: TCP-Dateneinheit|
|**Wichtige Vokabeln**|• **Zuverlässige Zustellung**: Garantierte Datenübertragung ohne Verlust<br>• **Geordnete Übertragung**: Daten kommen in der richtigen Reihenfolge an<br>• **Fehlerprüfung**: Erkennung beschädigter Daten<br>• **Verbindungsaufbau**: Etablierung einer Kommunikationsverbindung<br>• **Verbindungsabbau**: Beendigung einer bestehenden Verbindung<br>• **Handshake**: "Händedruck" - Abstimmungsverfahren zwischen Sender und Empfänger<br>• **Logische Kommunikation**: Virtuelle Verbindung zwischen Anwendungen<br>• **Sortierraum-Analogie**: TCP als "Postsortierraum" im Computer<br>• **Wohnhaus-Analogie**: IP = Gebäude, Port = Wohnungsnummer<br>• **Zuverlässiger Postdienst**: TCP-Metapher für garantierte Zustellung<br>• **Bestätigung**: Empfangsquittierung für erhaltene Daten<br>• **Timeout**: Zeitüberschreitung vor Neuübertragung<br>• **Paketverlust**: Nicht angekommene Datenpakete<br>• **Netzwerkstau**: Überlastung des Netzwerks<br>• **Überlastung**: Zu viele Daten für verfügbare Kapazität<br>• **Administratorrechte**: Erhöhte Berechtigungen (für Ports 0-1023)<br>• **IANA** (Internet Assigned Numbers Authority): Organisation für Port-Registrierung<br>• **Routing**: Wegewahl von Paketen durch das Netzwerk<br>• **Out-of-Order**: Nicht in der richtigen Reihenfolge<br>• **Reassemblierung**: Zusammensetzen von Datensegmenten<br>• **Abrupter Abbruch**: Sofortiges Beenden ohne ordentlichen Abbau|

---

## 80/20-Zusammenfassung: Die wichtigsten 20% zum Verständnis von 80% von TCP

### **Was ist TCP? Der zuverlässige Postdienst des Internets**

**TCP (Transmission Control Protocol)** ist ein **verbindungsorientiertes Protokoll** auf der **Transportschicht** (Schicht 4), das **zuverlässige, geordnete und fehlergeprüfte** Datenübertragung zwischen Anwendungen garantiert.

**Analogie**: TCP ist wie ein sorgfältiger Postdienst mit Einschreiben und Empfangsbestätigung – jedes Paket kommt garantiert an, in der richtigen Reihenfolge und ohne Beschädigung.

### **Die Rolle der Transportschicht**

Die Transportschicht sitzt zwischen:

- **Netzwerkschicht** (IP-Adressen, Routing zwischen Hosts)
- **Anwendungsschicht** (HTTP, DNS, E-Mail)

**Aufgabe**: Daten zur **richtigen Anwendung** auf dem Zielhost leiten – wie ein Postsortierraum im Computer.

**Die zwei Hauptprotokolle**:

- **TCP**: Zuverlässig, langsamer (z.B. Webseiten, E-Mail, Dateiübertragung)
- **UDP**: Schnell, unzuverlässig (z.B. Live-Streaming, Gaming)

### **Die 5 Schlüssel-Eigenschaften von TCP**

#### **1. Verbindungsorientiert (Connection-Oriented)**

Vor Datenaustausch wird eine **Verbindung etabliert** durch den **Three-Way Handshake**:

```
Client                          Server
  |                               |
  |-------- SYN (seq=x) -------->|  (1. Schritt: "Kann ich verbinden?")
  |                               |
  |<----- SYN-ACK (seq=y) -------|  (2. Schritt: "Ja, bereit!")
  |        (ack=x+1)              |
  |                               |
  |-------- ACK (ack=y+1) ------>|  (3. Schritt: "Bestätigt, los geht's!")
  |                               |
  [Verbindung etabliert - Daten können fließen]
```

**Merke**: SYN → SYN-ACK → ACK = "Hallo → Hallo zurück → Los geht's!"

#### **2. Zuverlässige Zustellung (Reliable Delivery)**

TCP **garantiert** Datenankommen durch:

- **Sequenznummern**: Jedes Byte erhält eine Nummer
- **Acknowledgments (ACKs)**: Empfänger bestätigt erhaltene Daten
- **Retransmission**: Keine Bestätigung = automatische Neuübertragung

**Beispiel**:

```
Sender: "Hier sind Bytes 1-100"
Empfänger: "ACK - erwarte jetzt Byte 101"
[Kein ACK nach Timeout?] → Sender sendet erneut
```

#### **3. Geordnete Übertragung (Ordered Data Transfer)**

IP-Pakete können unterschiedliche Routen nehmen und durcheinander ankommen. TCP **sortiert** sie durch Sequenznummern in die richtige Reihenfolge, bevor sie an die Anwendung weitergegeben werden.

#### **4. Flusskontrolle (Flow Control)**

**Problem**: Empfänger hat begrenzten Pufferspeicher

**Lösung**: **Sliding Window** - Empfänger teilt mit, wie viel Platz er noch hat (Window Size im Header), Sender passt sich an.

**Verhindert**: Empfänger-Überlastung

#### **5. Staukontrolle (Congestion Control)**

**Problem**: Netzwerk selbst kann überlastet werden

**Lösung**: TCP erkennt Stauzeichen (verlorene Pakete) und **drosselt automatisch** die Übertragungsrate.

**Verhindert**: Netzwerk-Kollaps

### **Ports: Die Wohnungsnummern im Computer-Gebäude**

**Port-Nummern** (0-65535) identifizieren **spezifische Anwendungen** auf einem Host.

**Analogie**:

- **IP-Adresse** = Adresse des Wohnhauses
- **Port-Nummer** = Wohnungsnummer im Haus

|Port-Bereich|Name|Verwendung|Beispiele|
|---|---|---|---|
|**0-1023**|Well-Known Ports|Standard-Dienste|HTTP (80), HTTPS (443), SSH (22), FTP (21)|
|**1024-49151**|Registered Ports|Registrierte Anwendungen|MySQL (3306), PostgreSQL (5432)|
|**49152-65535**|Ephemeral Ports|Client-Quellports|Zufällig vom OS zugewiesen|

**Socket** = IP-Adresse + Port-Nummer (eindeutige Identifikation eines Prozesses)

### **Der TCP-Header: Steuerungszentrale**

Die wichtigsten Felder im TCP-Header:

|Feld|Größe|Funktion|
|---|---|---|
|**Source Port**|16 Bit|Absender-Anwendung|
|**Destination Port**|16 Bit|Empfänger-Anwendung|
|**Sequence Number**|32 Bit|Byte-Nummer des ersten Daten-Bytes|
|**Acknowledgment Number**|32 Bit|Nächstes erwartetes Byte|
|**Flags**|Bits|SYN, ACK, FIN, RST, PSH, URG|
|**Window Size**|16 Bit|Verfügbarer Pufferspeicher|
|**Checksum**|16 Bit|Fehlerprüfung|

**Die wichtigsten Flags**:

- **SYN**: Verbindung starten
- **ACK**: Daten bestätigen
- **FIN**: Verbindung beenden (ordentlich)
- **RST**: Verbindung zurücksetzen (abrupt)

### **TCP-Verbindungs-Lebenszyklus**

**1. Aufbau**: Three-Way Handshake (SYN → SYN-ACK → ACK)

**2. Datenübertragung**:

- Segmente mit Sequenznummern
- ACKs für Bestätigungen
- Fluss- und Staukontrolle aktiv

**3. Abbau**: Four-Way Handshake

```
Seite A: FIN →
Seite B: ← ACK
Seite B: FIN →
Seite A: ← ACK
[Verbindung geschlossen]
```

### **TCP vs. UDP: Wann welches Protokoll?**

**TCP verwenden für**:

- ✅ Webseiten (HTTP/HTTPS)
- ✅ E-Mail (SMTP, IMAP)
- ✅ Dateiübertragung (FTP, SFTP)
- ✅ Alles, wo **Zuverlässigkeit wichtiger als Geschwindigkeit** ist

**UDP verwenden für**:

- ✅ Live-Video/Audio-Streaming
- ✅ Online-Gaming
- ✅ DNS-Anfragen
- ✅ Alles, wo **Geschwindigkeit wichtiger als einzelne Paketverluste** ist

**Warum?** TCP's Zuverlässigkeitsmechanismen (Neuübertragungen, Bestätigungen) verursachen **Verzögerungen**. Bei Live-Streams ist ein verlorenes Frame weniger schlimm als Verzögerung – der Stream läuft einfach weiter.

### **Praktischer Test (Windows 11)**

**Aktive TCP-Verbindungen anzeigen**:

```powershell
netstat -an | findstr "ESTABLISHED"
```

**TCP-Port-Test mit PowerShell**:

```powershell
Test-NetConnection google.com -Port 443
```

**TCP-Verbindung manuell testen**:

```powershell
telnet google.com 80
```

(Telnet muss über "Windows-Features" aktiviert werden)

### **Kernbotschaft**

TCP ist das **Rückgrat zuverlässiger Internet-Kommunikation**. Durch seinen **Three-Way Handshake**, **Sequenznummern**, **ACKs**, **Fluss- und Staukontrolle** garantiert es:

✅ **Zuverlässigkeit** - Keine Datenverluste ✅ **Reihenfolge** - Richtige Sortierung ✅ **Fehlerprüfung** - Beschädigte Daten werden erkannt

Der Preis: **Overhead und Latenz** durch Verbindungsaufbau und Bestätigungen.

**Trade-off verstehen**: TCP = Qualität vor Geschwindigkeit | UDP = Geschwindigkeit vor Qualität

TCP ist essenziell für Cybersecurity-Analysen, da das Verständnis von TCP-Headern, Flags und Verbindungszuständen die Grundlage für Netzwerkverkehrsanalyse und Angriffserkennung bildet! 🔒🌐