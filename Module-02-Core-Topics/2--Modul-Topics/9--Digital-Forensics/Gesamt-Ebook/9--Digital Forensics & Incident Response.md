## Kapitel 1: Grundlagen DFIR

### Was ist DFIR?

**DFIR** steht für Digital Forensics and Incident Response - ein Bereich der Cybersicherheit, der sich mit der Identifizierung, Untersuchung und Behebung von Cyberangriffen befasst.

**Zwei Disziplinen:**

**Incident Response (IR)** - Die Notaufnahme der Cybersicherheit

- Ziel: Sicherheitsvorfall in Echtzeit bewältigen
- Fokus: Angriff stoppen, Schaden begrenzen, schnell wiederherstellen
- Unter Zeitdruck

**Digital Forensics (DF)** - Die Tatortuntersuchung

- Ziel: Vollständige Geschichte des Angriffs aufdecken
- Fokus: Beweise sammeln, bewahren und methodisch analysieren
- Für Berichte, Versicherungen, Gerichtsverfahren
- Methodisch und gründlich, nicht unter Zeitdruck

**Analogie:** Bei einem brennenden Haus sind die Incident Responder die Feuerwehrleute. Die Digital Forensic Investigators kommen danach und untersuchen, wie das Feuer begann.

---

### Der PICERL-Lebenszyklus

**1. Preparation (Vorbereitung)**

- Richtige Tools bereithalten
- Personal schulen
- Klaren Aktionsplan haben

**2. Identification (Identifizierung)**

- Echter Vorfall oder Fehlalarm?
- Schwere bestimmen
- Betroffene Systeme identifizieren

**3. Containment (Eindämmung)**

- Die Blutung stoppen
- Computer isolieren
- Dienste temporär deaktivieren

**4. Eradication (Beseitigung)**

- Bedrohung entfernen
- Malware löschen
- Kompromittierte Accounts deaktivieren
- Schwachstellen patchen

**5. Recovery (Wiederherstellung)**

- Systeme sicher wiederherstellen
- Daten aus sauberen Backups
- Umgebung überwachen

**6. Lessons Learned**

- Post-Incident Review
- Was lief gut? Was nicht?
- Für nächstes Mal verbessern

---

### Kernprinzipien der Forensik

#### Chain of Custody (Beweismittelkette)

Detailliertes Protokoll über den gesamten Lebenszyklus eines Beweisstücks:

- Wer hat es gehandhabt?
- Wann wurde es gehandhabt?
- Wo wurde es gelagert?
- Warum wurde es gehandhabt?

**Wichtig:** Jede Übertragung dokumentieren! Ein Bruch macht Beweise unbrauchbar.

#### Order of Volatility (Reihenfolge der Flüchtigkeit)

Von **am flüchtigsten** zu **am wenigsten flüchtig:**

1. **CPU-Register, Cache** - extrem flüchtig
2. **RAM (Arbeitsspeicher)** - verloren beim Ausschalten
3. **Temporäre Dateisysteme** - gelöscht beim Neustart
4. **Festplatten (HDD/SSD)** - nicht flüchtig
5. **Remote-Logs (SIEM)** - zentral gespeichert
6. **Backups und Archive** - am wenigsten flüchtig

**Regel:** Immer mit den flüchtigsten Beweisen beginnen!

#### Evidence Integrity (Beweisintegrität)

**Hashing zum Beweis der Unversehrtheit:**

1. Hash des Originals berechnen (z.B. SHA-256)
2. Forensisches Image erstellen
3. Hash der Kopie berechnen
4. Hashes vergleichen → identisch = perfekte Kopie

**Alle Analysen nur am verifizierten Image durchführen, nie am Original!**

---

## Kapitel 2: Windows Forensik

### Warum Windows?

Die große Mehrheit der Unternehmens- und Regierungsnetzwerke läuft auf Windows. Von Arbeitsplätzen bis zu Active Directory Servern - Windows ist das Hauptziel von Angreifern.

### Forensische Artefakt-Kategorien

#### 1. Filesystem-Artefakte

- Erstellte, geänderte, gelöschte Dateien
- Zugriffszeitpunkte
- **Master File Table (MFT)** - Datenbank aller Dateien
- **USN Journal** - verfolgt Dateiänderungen

#### 2. Programmausführungs-Artefakte

Beweis, dass ein Programm ausgeführt wurde:

- **Prefetch-Dateien** - Windows erstellt diese zum schnelleren Laden
- **Shimcache, Amcache** - Kompatibilitätsinformationen

#### 3. Benutzeraktivitäts-Artefakte

- **LNK-Dateien** (Verknüpfungen)
- **Shellbags** - Ordneransichtspräferenzen
- **Browserverlauf**

#### 4. System-Artefakte

- **Windows Registry** - riesige Datenbank von Einstellungen
- **Windows Event Logs** - Anmeldungen, Abstürze, etc.

#### 5. Volatile Memory-Artefakte

Im RAM, verloren beim Herunterfahren:

- Laufende Prozesse
- Aktive Netzwerkverbindungen
- Kommandozeilenverlauf
- Verschlüsselungsschlüssel

---

### Praktisches Beispiel: Prefetch-Dateien

**Fundort:** `C:\Windows\Prefetch`

**Was sie zeigen:** Dass ein Programm ausgeführt wurde

**Beispiel:** `MSPAINT.EXE-[hash].pf`

- Beweis: mspaint.exe wurde ausgeführt
- Zeitstempel: Wann es zuletzt lief

**Tool:** Eric Zimmerman's PECmd.exe

```
PECmd.exe -d C:\Windows\Prefetch --csv .
```

Ergebnis: CSV mit ExecutableName, RunCount, LastRun

---

## Kapitel 3: Disk Forensik

### Die erste Regel: Preserve the Evidence

**Do No Harm!**

Jede Aktion (selbst Computer hochfahren) kann Dateien verändern.

**Lösung: Write Blocker**

- Hardware oder Software
- Erlaubt Lesen, verhindert Schreiben

**Forensisches Image erstellen:**

- Bit-für-Bit identische Kopie der gesamten Festplatte
- Inklusive aller leeren Bereiche und gelöschten Dateien
- Arbeiten nur am Image, nie am Original

**Formate:** Raw DD, EnCase

---

### Von physisch zu logisch

**Disk (physische Hardware)** ↓ **Partition (logischer Abschnitt)** ↓ **File System (Organisationsregeln)** ↓ **Volume (z.B. C:-Laufwerk)**

### Partitionierungsschemas

**MBR (Master Boot Record)**

- Alt, limitiert (max. 2 TB)
- Partitionstabelle am Anfang der Disk

**GPT (GUID Partition Table)**

- Modern, robust
- Unterstützt große Disks
- **Backup der Partitionstabelle am Ende** - wichtig für Forensik!

---

### NTFS - Das Herz von Windows

#### Master File Table (MFT)

Datenbank **jeder** Datei und jedes Verzeichnisses.

**Jeder MFT-Eintrag enthält:**

**Standard Information:**

- Created (Erstellung)
- Modified (Änderung)
- Accessed (Zugriff)

**File Name:**

- Name der Datei
- **Zweiter Satz der gleichen Zeitstempel!**

**Warum zwei Sätze?** Diskrepanzen können auf **Timestomping** hinweisen - Angreifer ändern Zeitstempel mit Tools. File Name Zeitstempel sind schwerer zu ändern!

#### Weitere wichtige NTFS-Artefakte

**$LogFile**

- Journal aller Dateisystemänderungen
- Zeigt aktuelle Aktivität

**$UsnJrnl (Update Sequence Number Journal)**

- Protokoll aller Änderungen an Dateien
- Was wurde hinzugefügt, gelöscht, geändert

---

### Die Wahrheit über gelöschte Dateien

**Wichtigstes Konzept:** Beim Löschen werden Daten **nicht sofort gelöscht**!

Das Dateisystem markiert nur:

- MFT-Eintrag als "inaktiv"
- Belegte Cluster als "unallocated space"

Die eigentlichen Daten (1en und 0en) bleiben auf der Disk, bis sie überschrieben werden.

#### Data Carving

Technik zum Wiederherstellen gelöschter Dateien:

1. Unallocated Space scannen
2. Nach bekannten File Headers suchen (z.B. JPEG beginnt mit `FF D8 FF`)
3. Daten bis zum Footer extrahieren
4. Datei rekonstruieren - ohne Metadaten!

**Tool:** Autopsy

---

## Kapitel 4: Memory Forensics

### Was ist Memory Forensics?

Analyse des **flüchtigen Speichers (RAM)** - das temporäre Arbeitsgedächtnis des Computers.

**RAM enthält:**

- Laufende Programme
- Offene Dateien
- Netzwerkverbindungen
- Benutzeraktionen
- Passwörter und Schlüssel

**Problem:** Inhalt wird gelöscht, sobald Strom weg ist!

---

### Warum so wichtig?

**Fileless Malware:** Moderne Angreifer laufen oft nur im RAM, schreiben nichts auf die Festplatte.

→ Disk Forensics findet nichts → Memory Forensics ist essentiell!

### Was Memory Forensics aufdeckt

1. **Was lief auf dem System?**
    
    - Liste laufender Prozesse
    - Getarnte Malware (z.B. fake svchost.exe)
    - Wer startete das Programm, wann?
2. **Mit wem kommunizierte das System?**
    
    - Netzwerkverbindungen
    - Command & Control Server
    - Datenexfiltration
3. **Was tat der Angreifer?**
    
    - Ausgeführte Befehle
    - PowerShell-Verlauf
    - Direktes Log der Aktivität
4. **Welche Geheimnisse wurden gestohlen?**
    
    - Passwörter
    - Benutzernamen
    - Kryptografische Schlüssel
5. **Wie funktioniert die Malware?**
    
    - Code-Injection
    - Hooks ins OS
    - Verstecktechniken

---

### Der Prozess

#### 1. Acquisition (Erfassung)

Bit-für-Bit Kopie des gesamten RAM in eine Datei = **Memory Dump**

**Herausforderung:** Acquisition-Tool verändert selbst den RAM (Observer-Effekt) → Tools sind extrem leichtgewichtig

**Tools:** FTK Imager, Redline

#### 2. Analysis (Analyse)

**Tool: Volatility 3**

Open-Source Framework mit Plugins für spezifische Artefakte.

**Wichtig:** Volatility muss das OS kennen (Windows 7 ≠ Windows 10) → Volatility 3 erkennt OS automatisch (Symbol Tables)

---

### Volatility 3 - Grundlagen

**Installation:**

1. Von GitHub herunterladen (Source Code ZIP)
2. In Arbeitsverzeichnis entpacken
3. `vol.py` ist das Hauptskript

**Basis-Befehl:**

```bash
python3 vol.py -f memory_dump.vmem windows.info.Info
```

**Wichtige Plugins:**

- `windows.pslist.PsList` - Laufende Prozesse
- `windows.netscan.NetScan` - Netzwerkverbindungen
- `windows.cmdline.CmdLine` - Kommandozeilenargumente
- `windows.filescan.FileScan` - Dateien im Memory

**Beispiel-Workflow:**

```bash
# 1. System-Info
python3 vol.py -f dump.vmem windows.info.Info

# 2. Prozesse auflisten
python3 vol.py -f dump.vmem windows.pslist.PsList

# 3. Netzwerkverbindungen
python3 vol.py -f dump.vmem windows.netscan.NetScan
```

---

## Kapitel 5: Network Forensics

### Was ist Network Forensics?

Erfassen, Aufzeichnen und Analysieren von **Netzwerkverkehr** (Daten in Bewegung).

**Ziele:**

- Angreifer identifizieren
- Umfang des Vorfalls bestimmen
- Angriffsmethodik verstehen
- Gestohlene Daten finden

---

### Die Herausforderungen

1. **Volumen**
    
    - Terabytes pro Tag
    - Nadel im Heuhaufen
2. **Flüchtigkeit**
    
    - Nicht erfasst = für immer verloren
    - Keine Zeitreise möglich
3. **Verschlüsselung**
    
    - HTTPS, SSH, VPNs verschlüsselt
    - Nur Metadaten sichtbar (wer mit wem)
    - Inhalt ohne Schlüssel nicht lesbar
4. **Verschleierung**
    
    - Non-Standard Ports
    - Tunneling
    - Versteckte Encodierung

---

### Quellen für Netzwerkbeweise

#### 1. Full Packet Capture (PCAP)

**Goldstandard!**

Speichert jedes Bit:

- Header (Quell/Ziel-IP, Ports)
- Payload (eigentliche Daten)

**Stärke:** Detailliertester Beweis **Schwäche:** Riesiger Speicherbedarf

#### 2. NetFlow / IPFIX

Nur Metadaten:

- Wer sprach mit wem?
- Wann, wie lange?
- Wie viele Daten?

**Five-Tuple:**

- Source IP
- Destination IP
- Source Port
- Destination Port
- Protocol

**Analogie:** Telefonrechnung (Nummer, Dauer, Zeit) - aber kein Gesprächsinhalt

**Stärke:** Wenig Ressourcen, Überblick **Schwäche:** Keine Details

#### 3. Device Logs

- **Firewall Logs** - Erlaubter/blockierter Traffic
- **IDS/IPS Logs** - Erkannte Angriffsmuster
- **Proxy Logs** - Besuchte Websites
- **DNS Logs** - Domain-Lookups (zeigt C2-Server)

---

### Die wichtigsten Tools

#### Wireshark

GUI-Tool für PCAP-Analyse

**Hauptfunktionen:**

- Protokoll-Dissektoren (tausende Protokolle)
- Display Filter
- **Follow TCP Stream** - rekonstruiert ganze Gespräche

**Interface:**

1. Packet List - Zusammenfassung
2. Packet Details - Header-Details
3. Packet Bytes - Rohdaten (Hex)

#### Tshark

Kommandozeilen-Wireshark

Perfekt für:

- Automatisierung
- Skripte
- Große Datenmengen

**Beispiel:**

```bash
tshark -r file.pcap -Y "http.request" -T fields -e http.host
```

→ Extrahiert alle HTTP-Hostnamen

---

### Der Untersuchungsprozess

1. **Acquisition**
    
    - Network TAP oder SPAN Port
    - Traffic erfassen
2. **Analysis**
    
    - Wireshark/Tshark
    - Anomalien suchen
    - IOCs (Indicators of Compromise) finden
3. **Correlation** (am wichtigsten!)
    
    - Netzwerkdaten mit anderen Quellen verbinden:
        - Windows Event Logs
        - Memory Analysis
        - Disk Forensics
    - Vollständige Timeline erstellen

---

### Diamond Model

Framework zur Strukturierung:

```
        Adversary (Angreifer)
             /  \
            /    \
Capability       Infrastructure
(Tools/Techniken)  (C2-Server/Domains)
            \    /
             \  /
           Victim (Opfer)
```

**Ziel:** Alle vier Elemente identifizieren und verknüpfen für Gesamtbild.

---

## Quick Reference: Die wichtigsten Tools

### Windows Forensics

- **Eric Zimmerman Tools** - Artefakt-Parsing
- **Autopsy** - Disk Forensics Platform

### Memory Forensics

- **Volatility 3** - RAM-Analyse
- **FTK Imager** - Memory Acquisition

### Network Forensics

- **Wireshark** - PCAP-Analyse (GUI)
- **Tshark** - PCAP-Analyse (CLI)

---

## Die wichtigsten Merksätze

1. **Preserve the Evidence** - Nie am Original arbeiten!
    
2. **Order of Volatility** - Flüchtigstes zuerst!
    
3. **Chain of Custody** - Alles dokumentieren!
    
4. **Hash Everything** - Integrität beweisen!
    
5. **Gelöschte Dateien sind nicht weg** - Data Carving möglich!
    
6. **RAM ist Gold** - Moderne Malware lebt im Memory!
    
7. **Korrelation ist King** - Verschiedene Quellen verbinden!
    
8. **Verschlüsselung ist eine Hürde** - Aber Metadaten helfen!
    

---

## Typischer Incident-Response-Workflow

1. **Vorbereitung**
    
    - Tools bereit
    - Team trainiert
    - Plan vorhanden
2. **Erste Maßnahmen**
    
    - Memory Dump erfassen (flüchtigste Daten!)
    - System isolieren (nicht ausschalten!)
    - Logs sichern
3. **Forensische Analyse**
    
    - Forensisches Disk-Image
    - Memory-Analyse (Volatility)
    - Network-Logs analysieren
    - Timeline erstellen
4. **Findings korrelieren**
    
    - Disk + Memory + Network = Vollbild
    - Angriffskette rekonstruieren
5. **Reporting**
    
    - Was passierte?
    - Wann passierte es?
    - Wie kam Angreifer rein?
    - Was wurde kompromittiert?
    - Empfehlungen
6. **Lessons Learned**
    
    - Prozesse verbessern
    - Defenses stärken

---

## Abschluss

DFIR ist die Detektivarbeit der Cybersecurity. Mit den richtigen Methoden, Tools und Prinzipien können digitale Spuren aufgedeckt werden, die Angreifer hinterlassen.

**Erfolgsformel:**

- Methodisch arbeiten
- Beweise schützen
- Verschiedene Quellen korrelieren
- Kontinuierlich lernen

Die Angreifer werden kreativer - wir müssen es auch sein!

---

_Ende des E-Books_