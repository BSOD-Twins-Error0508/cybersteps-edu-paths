# Kategorisierung der Netzwerkprotokolle

## Übersichtstabelle

|**Kategorie**|**Details**|
|---|---|
|**Verwendete Tools**|• **E-Mail-Clients**: Apple Mail, Outlook (Windows: Outlook, Thunderbird, Windows Mail)<br>• **FTP-Clients**: Terminal mit tnftp (Windows: FileZilla, WinSCP, Command Prompt mit `ftp`)<br>• **Remote-Access-Tools**: SSH-Client, Telnet-Client (Windows: PuTTY, OpenSSH, Windows Terminal)<br>• **RDP-Client**: (macOS: Microsoft Remote Desktop; Windows: Remotedesktopverbindung - integriert)<br>• **Homebrew**: Paketmanager für macOS (Windows: Chocolatey, Winget)|
|**Technische Fachbegriffe**|• **SMTP** (Simple Mail Transfer Protocol): Protokoll zum Versenden von E-Mails<br>• **POP3** (Post Office Protocol v3): Protokoll zum Abrufen von E-Mails mit Download<br>• **IMAP** (Internet Message Access Protocol): Protokoll zur serverseitigen E-Mail-Verwaltung<br>• **FTP** (File Transfer Protocol): Protokoll zur Dateiübertragung<br>• **FTPS**: FTP mit TLS/SSL-Verschlüsselung<br>• **SFTP** (SSH File Transfer Protocol): Dateiübertragung über SSH-Tunnel<br>• **Telnet**: Unverschlüsseltes Fernzugriffsprotokoll<br>• **SSH** (Secure Shell): Verschlüsselter Fernzugriff<br>• **RDP** (Remote Desktop Protocol): Grafischer Fernzugriff von Microsoft<br>• **TLS/SSL**: Verschlüsselungsprotokolle<br>• **STARTTLS**: Befehl zur Verschlüsselung einer bestehenden Verbindung<br>• **Active/Passive Mode**: FTP-Verbindungsmodi<br>• **NLA** (Network Level Authentication): Zusätzliche RDP-Sicherheitsebene<br>• **Clear Text**: Unverschlüsselte Datenübertragung<br>• **Public-Key-Cryptography**: Asymmetrische Verschlüsselung<br>• **Port**: Netzwerk-Endpunkt für Dienste|
|**Wichtige Vokabeln**|• **Anwendungsschicht** (Application Layer): Oberste Schicht im Netzwerkmodell<br>• **Push-Protokoll**: Sendet Daten aktiv zum Server<br>• **Pull-Protokoll**: Holt Daten vom Server ab<br>• **Kontrollverbindung** (Control Connection): Befehlskanal bei FTP<br>• **Datenverbindung** (Data Connection): Übertragungskanal bei FTP<br>• **Firewall**: Netzwerksicherheitsbarriere<br>• **Banner Grabbing**: Auslesen von Dienstinformationen<br>• **Port Forwarding**: Weiterleitung von Netzwerkports<br>• **Man-in-the-Middle-Angriff**: Abfangen von Netzwerkkommunikation<br>• **Authentifizierung** (Authentication): Identitätsprüfung<br>• **Verschlüsselung** (Encryption): Datenverschleierung<br>• **Synchronisation**: Abgleich über mehrere Geräte<br>• **Serverseitige Ordner**: Verzeichnisse auf dem Mailserver<br>• **Offline-Zugriff**: Arbeit ohne Internetverbindung<br>• **Multi-Device-Zugriff**: Nutzung auf mehreren Geräten|

---

## 80/20-Zusammenfassung: Die wichtigsten 20% zum Verständnis von 80% des Inhalts

### **E-Mail-Protokolle: Das Drei-Protokoll-System**

E-Mail funktioniert durch die Zusammenarbeit von drei Protokollen:

- **SMTP** (Ports 25/587/465) ist zum **Versenden** da – es "pusht" E-Mails vom Client zum Server und zwischen Servern
- **POP3** (Ports 110/995) **lädt E-Mails herunter** und löscht sie meist vom Server – gut für Offline-Zugriff, aber nicht geräteübergreifend
- **IMAP** (Ports 143/993) **verwaltet E-Mails auf dem Server** – ideal für mehrere Geräte, da alles synchronisiert bleibt

**Merke**: Moderne E-Mail nutzt verschlüsselte Ports (587, 995, 993) statt der alten unverschlüsselten Versionen.

### **Dateiübertragung: FTP und seine sicheren Alternativen**

**FTP** (Port 21) nutzt zwei getrennte Verbindungen – eine für Befehle, eine für Daten. Das Problem: **Alles unverschlüsselt!** Passwörter und Dateien sind im Klartext sichtbar.

**Sichere Alternativen:**

- **FTPS**: FTP mit TLS/SSL-Verschlüsselung
- **SFTP** (Port 22): Läuft über SSH, komplett verschlüsselt – **das ist die bevorzugte Methode**

### **Fernzugriff: Von unsicher zu sicher**

Die Evolution des Fernzugriffs:

1. **Telnet** (Port 23): **Niemals verwenden!** Alles unverschlüsselt – Angreifer können Passwörter direkt mitlesen
2. **SSH** (Port 22): **Die sichere Alternative** – verschlüsselt alles, authentifiziert Server und Clients
3. **RDP** (Port 3389): **Grafischer Fernzugriff** für Windows – modern verschlüsselt, aber sollte nie direkt ins Internet exponiert werden

### **Die goldene Sicherheitsregel**

**Unverschlüsselte Protokolle = Sicherheitsrisiko:**

- Telnet, FTP (Standard), SMTP/POP3/IMAP (auf unverschlüsselten Ports) übertragen **alles im Klartext**
- Verwende immer die verschlüsselten Versionen oder Alternativen (SSH statt Telnet, SFTP statt FTP, verschlüsselte E-Mail-Ports)

### **Praktische Portnummern zum Merken**

|Dienst|Unsicher|Sicher|
|---|---|---|
|SMTP|25|587/465|
|POP3|110|995|
|IMAP|143|993|
|FTP|21|-|
|SFTP|-|22|
|Telnet|23|-|
|SSH|-|22|
|RDP|3389|3389 (mit NLA)|

**Kernbotschaft**: In der Cybersicherheit ist die Wahl des richtigen Protokolls entscheidend. Verschlüsselte Verbindungen schützen vor Abhören und Identitätsdiebstahl.