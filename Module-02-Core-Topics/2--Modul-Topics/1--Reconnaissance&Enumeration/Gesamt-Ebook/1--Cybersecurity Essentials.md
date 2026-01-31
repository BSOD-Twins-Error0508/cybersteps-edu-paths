## Modul 2: Kern-Themen der Cybersicherheit

### 1. Bedrohungsakteure - Wer sind die Gegner?

Ein Bedrohungsakteur ist eine Person oder Gruppe, die bösartige Handlungen gegen digitale Geräte, Systeme oder Netzwerke ausführt.

**Die Haupttypen:**

**Cyberkriminelle**

- Motivation: Finanzieller Gewinn
- Methoden: Ransomware, Phishing, Botnets
- Anspruch: Von niedrig (fertige Tools) bis sehr hoch (eigene Malware)

**Nationalstaaten (APTs)**

- Motivation: Spionage, Sabotage
- Methoden: Langfristiger Zugang zu Zielnetzwerken
- Anspruch: Sehr hoch, umfangreiche Ressourcen

**Hacktivisten**

- Motivation: Politische oder soziale Ziele
- Methoden: Website-Defacing, Doxing, DoS-Angriffe
- Anspruch: Niedrig bis mittel

**Interne Bedrohungen**

- Böswillige Insider: Absichtlicher Datendiebstahl oder Sabotage
- Fahrlässige Insider: Versehentliche Sicherheitsverletzungen durch Unachtsamkeit

**Script Kiddies**

- Unerfahrene Hacker mit fertigen Tools
- Motivation: Neugier, Bekanntheit
- Anspruch: Niedrig, aber dennoch gefährlich

---

### 2. Die CIA-Triade - Grundpfeiler der Sicherheit

Die drei Kernprinzipien zum Schutz von Informationen:

**Vertraulichkeit (Confidentiality)**

- **Ziel:** Unbefugte Offenlegung sensibler Informationen verhindern
- **Bedrohungen:** Datenlecks, Abhören, unbefugter Zugriff
- **Schutzmaßnahmen:**
    - Verschlüsselung
    - Zugriffskontrollen (Passwörter, Biometrie)
    - Datenklassifikation
    - Physische Sicherheit

**Integrität (Integrity)**

- **Ziel:** Genauigkeit und Vertrauenswürdigkeit der Daten bewahren
- **Bedrohungen:** Unbefugte Änderungen, Datenkorruption
- **Schutzmaßnahmen:**
    - Hashing (Änderungen werden erkennbar)
    - Digitale Signaturen
    - Versionskontrolle
    - Eingabevalidierung
    - Audit-Trails

**Verfügbarkeit (Availability)**

- **Ziel:** Systeme sind nutzbar, wenn sie gebraucht werden
- **Bedrohungen:** Systemausfälle, DDoS-Angriffe, Ransomware
- **Schutzmaßnahmen:**
    - Redundanz (RAID, Backup-Server)
    - Regelmäßige Backups
    - DDoS-Schutz
    - Systemüberwachung
    - Patch-Management

**Merke:** Die Verbesserung eines Aspekts kann einen anderen negativ beeinflussen. Sehr strenge Vertraulichkeitsmaßnahmen können die Verfügbarkeit einschränken.

---

### 3. MITRE ATT&CK Framework

Ein globales Wissenssystem über Taktiken und Techniken von Angreifern.

**Struktur:**

**Taktiken** = Das "Warum" (taktische Ziele)

- Reconnaissance: Informationen sammeln
- Initial Access: Einstieg ins Netzwerk
- Execution: Bösartigen Code ausführen
- Persistence: Zugang aufrechterhalten
- Privilege Escalation: Höhere Berechtigungen erlangen
- Defense Evasion: Erkennung vermeiden
- Credential Access: Passwörter stehlen
- Discovery: Umgebung erkunden
- Lateral Movement: Durch das Netzwerk bewegen
- Collection: Interessante Daten sammeln
- Command and Control (C2): Mit kompromittierten Systemen kommunizieren
- Exfiltration: Daten stehlen
- Impact: Systeme stören oder zerstören

**Techniken** = Das "Wie" Beispiel für Initial Access:

- Phishing
- Exploit Public-Facing Application
- External Remote Services

**Sub-Techniken** = Noch spezifischer Beispiel für Phishing:

- Spearphishing Attachment
- Spearphishing Link
- Spearphishing via Service

**Nutzen:** Einheitliche Sprache für Angriffsbeschreibungen, bessere Verteidigung, gezieltes Threat Hunting

---

### 4. Bedrohungsvektoren - Wie Angriffe erfolgen

**Nachrichtenbasierte Vektoren**

- **E-Mails und SMS:** Schädliche Links, Malware-Anhänge, Social Engineering
- **Warnsignale:** Unerwartete Absender, Dringlichkeit, Rechtschreibfehler, verdächtige Links

**Dateibasierte Vektoren**

- **Ausführbare Dateien:** .exe, .dmg, .app - können Malware enthalten
- **Dokumente mit Makros:** Word, Excel können schädliche Makros enthalten
- **PDF-Dateien:** Können Skripte mit Schwachstellen nutzen
- **Browser-Erweiterungen:** Manche spionieren oder stehlen Daten
- **ZIP/RAR-Archive:** Malware zwischen legitimen Dateien versteckt

**Software-Schwachstellen**

- **Ungepatche Systeme:** Bekannte Schwachstellen werden ausgenutzt
- **Zero-Day-Schwachstellen:** Noch keine Patches verfügbar
- **Lösung:** Regelmäßige Updates sind entscheidend!

**Physische Vektoren**

- **USB-Sticks:** Aus Neugier eingesteckt, enthalten oft Malware
- **Modifizierte Hardware:** Kompromittiert in der Lieferkette

---

### 5. Wichtige Plattformen und Tools

**TryHackMe**

- Gamifizierte Lernplattform für Cybersecurity
- Virtuelle "Räume" für praktische Übungen
- Sicheres, legales Lernumfeld
- Überbrückt Theorie und Praxis

**Kali Linux**

- Spezialisiertes Linux für Penetrationstests
- Hunderte vorinstallierte Security-Tools
- Kategorien: Netzwerkscans, Schwachstellenanalyse, Passwortknacken, Web-Tests
- Open Source und anpassbar
- **Wichtig:** Nur mit Erlaubnis verwenden!

**Metasploit Framework**

- Tool für Exploit-Entwicklung und -Tests
- **Exploits:** Code, der Schwachstellen ausnutzt
- **Payloads:** Code, der nach erfolgreicher Kompromittierung läuft
- **Module:** Verschiedene Funktionen (Scanning, Exploitation)
- **MSFConsole:** Hauptschnittstelle
- Standardisiert den Exploitation-Prozess

---

### 6. Passive Reconnaissance - Information ohne Spuren

**Was ist passive Reconnaissance?** Informationen sammeln, ohne das Ziel direkt zu kontaktieren. Das Ziel merkt nichts davon.

**Zu sammelnde Informationen:**

**Organisatorisch:**

- Unternehmensgröße, Standorte, Branche
- Schlüsselpersonal (für Social Engineering)
- Geschäftsbeziehungen
- Aktuelle Nachrichten

**Technisch:**

- Domains und Subdomains
- IP-Adressbereiche
- Verwendete Technologien
- E-Mail-Formate
- Sicherheitsmaßnahmen

**Wichtige Techniken:**

**Google Dorking** Erweiterte Suchoperatoren:

- `site:example.com` - Nur diese Website
- `filetype:pdf` - Nur PDF-Dateien
- `inurl:admin` - URLs mit "admin"
- `intitle:"index of"` - Verzeichnislisten

**WHOIS-Lookup** Zeigt Domain-Registrierungsinformationen:

- Inhaber, Kontakte
- Registrar, Name-Server
- Registrierungsdaten
- (Oft durch Privacy-Services geschützt)

**DNS-Enumeration**

- A Records: IP-Adressen
- MX Records: Mail-Server
- NS Records: Name-Server
- TXT Records: Verifikation, SPF

**Website-Analyse**

- `robots.txt`: Zeigt versteckte Bereiche
- `sitemap.xml`: Struktur der Website
- HTML-Quellcode: Kommentare, versteckte Felder
- Technologie-Erkennung: Wappalyzer, BuiltWith

**Social Media & öffentliche Aufzeichnungen**

- LinkedIn: Mitarbeiter, Technologien
- Stellenanzeigen: Verwendete Systeme und Software
- GitHub: Möglicherweise geleakte Credentials
- Unternehmensberichte

**Spezialisierte Tools**

- **Shodan:** Suchmaschine für internetverbundene Geräte
- **Wayback Machine:** Historische Website-Versionen

**Ethik:** Nur öffentlich verfügbare Informationen nutzen. Terms of Service beachten.

---

### 7. Active Reconnaissance - Direktes Sondieren

**Was ist active Reconnaissance?** Direktes Interagieren mit den Systemen des Ziels. Höheres Risiko der Entdeckung!

**Kernziele:**

- Live Hosts identifizieren
- Offene Ports finden
- Services und Versionen erkennen
- Betriebssystem bestimmen
- Netzwerk kartieren

**Unterschied zu passiv:**

- Direkte Interaktion mit Zielsystemen
- Höheres Entdeckungsrisiko
- Kann geloggt werden
- Detailliertere Informationen
- **Immer Erlaubnis erforderlich!**

**Host Discovery (Ping Sweep)**

- ICMP Echo Requests an IP-Bereiche
- Reagierende Hosts sind "live"
- Firewall kann ICMP blockieren
- Alternative: TCP/UDP-Pakete

```bash
# Einzelner Host
ping -c 4 google.com

# Nmap Ping Sweep
nmap -sn 192.168.1.0/24
```

**Port Scanning mit Nmap**

**TCP SYN Scan (-sS)** - "Half-Open Scan"

- Standard für privilegierte Nutzer
- Sendet SYN, wartet auf SYN/ACK
- Schickt RST vor Verbindungsaufbau
- Relativ unauffällig

**TCP Connect Scan (-sT)**

- Vollständiger Handshake
- Weniger unauffällig
- Wird häufiger geloggt

**UDP Scan (-sU)**

- Langsamer als TCP
- Wichtig für DNS, DHCP, SNMP
- Offene Ports antworten oft nicht

**Stealth Scans (-sF, -sN, -sX)**

- FIN, Null, Xmas Scans
- Noch unauffälliger
- Funktionieren meist nur bei Nicht-Windows-Systemen

```bash
# Basis-Scan
sudo nmap -sS scanme.nmap.org

# Mit Version Detection
sudo nmap -sS -sV scanme.nmap.org

# Mit OS Detection
sudo nmap -sS -sV -O scanme.nmap.org
```

**Service Enumeration**

- `-sV` Option für Versionserkennung
- Banner Grabbing zeigt Software-Version
- Wichtig für Schwachstellensuche

**OS Fingerprinting**

- `-O` Option
- Analysiert TCP/UDP/ICMP-Antworten
- Vergleich mit Fingerprint-Datenbank

**Traceroute**

- Zeigt Netzwerkpfad zum Ziel
- Identifiziert Router und Firewalls
- `traceroute` (Linux/Mac) oder `tracert` (Windows)

**Ethische Grenzen:**

- Nie ohne ausdrückliche, schriftliche Erlaubnis scannen!
- IP-Adresse ist sichtbar
- Kann IDS/IPS auslösen
- Wird oft geloggt
- Rechtliche Konsequenzen bei unbefugtem Scannen

---

### 8. Service Enumeration - Details sammeln

Nach dem Port-Scan: Detaillierte Informationen über Services sammeln.

**Web-Server (HTTP/HTTPS)**

**Directory Brute-Forcing mit Gobuster** Findet versteckte Verzeichnisse wie `/admin`, `/backups`, `/dev`

```bash
# Installation
sudo apt install gobuster -y

# Basis-Scan
gobuster dir -u http://example.com -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
```

**SMB Enumeration (Port 445)**

- Windows File Sharing
- Kann exponieren:
    - Geteilte Ordner
    - Benutzernamen
    - Systeminfos
- Oft mit Fehlkonfigurationen

**SNMP Enumeration (UDP Port 161)**

- Netzwerkgeräte-Management
- Standard Community Strings: `public` (read) / `private` (write)
- Oft unsicher konfiguriert

```bash
# Installation
sudo apt install snmp -y

# SNMP Walk
snmpwalk -v2c -c public demo.pysnmp.com
```

**FTP Enumeration (Port 21)**

- Dateiübertragungsprotokoll
- **Kritische Schwäche:** Anonymer Zugang
- Username: `anonymous`, beliebiges/kein Passwort
- Kann sensible Dateien exponieren

**Ziel:** Von Port-Liste zu umsetzbarer Intelligence

---

## Zusammenfassung - Die wichtigsten Punkte

1. **Bedrohungsakteure** kennen und ihre Motivationen verstehen
2. **CIA-Triade** als Sicherheitsgrundlage: Vertraulichkeit, Integrität, Verfügbarkeit
3. **MITRE ATT&CK** für einheitliche Angriffsbeschreibung nutzen
4. **Bedrohungsvektoren** verstehen: Nachrichten, Dateien, Software, Physisch
5. **Passive Reconnaissance** für unauffällige Informationsbeschaffung
6. **Active Reconnaissance** mit Nmap für detaillierte System-Analyse
7. **Service Enumeration** für tiefgehende Schwachstellensuche
8. **Immer ethisch handeln:** Nur mit Erlaubnis testen!

---

## Praktische Übungen

### Setup

1. TryHackMe-Account erstellen auf tryhackme.com
2. Kali Linux als VM installieren
3. Metasploit Framework erkunden auf metasploit.com

### Erste Schritte

1. Passive Recon üben: WHOIS-Lookup, Google Dorking
2. `scanme.nmap.org` mit verschiedenen Nmap-Scans testen
3. TryHackMe-Räume absolvieren

### Wichtig

- Alle Übungen nur in legalen, dafür vorgesehenen Umgebungen
- Nie echte Systeme ohne Erlaubnis scannen
- Bei TryHackMe oder eigenen VMs üben

---

_Erstellt für mobile Wiederholung unterwegs_ _Fokus auf die 20% die 80% des Verständnisses bringen_