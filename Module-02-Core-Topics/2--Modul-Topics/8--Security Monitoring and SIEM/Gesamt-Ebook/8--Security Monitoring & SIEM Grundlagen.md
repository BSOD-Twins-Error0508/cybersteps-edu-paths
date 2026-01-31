## 1. Security Monitoring & SIEM

### Was ist Security Monitoring?

Security Monitoring ist der kontinuierliche Prozess des Sammelns und Analysierens von Informationen, um Sicherheitsvorfälle zu erkennen, zu untersuchen und darauf zu reagieren.

**Die Grundidee:** Stell dir eine große Stadt vor. Um sie sicher zu halten, überwachen Behörden Verkehrskameras, hören Notrufe ab und analysieren Kriminalitätsmuster. Genauso funktioniert Security Monitoring für IT-Infrastrukturen.

### Logs - Digitale Fußspuren

Logs sind digitale Brotkrümel, die jede Aktion in einem System hinterlässt. Sie bieten einen Prüfpfad und helfen, Vorfälle zu rekonstruieren.

**Haupttypen von Logs:**

- **Betriebssystem-Logs:** Windows Event Logs (Application, Security, System) oder Linux Logs in `/var/log`
- **Anwendungs-Logs:** Von Webservern, Datenbanken und Geschäftsanwendungen
- **Netzwerkgeräte-Logs:** Von Routern, Firewalls und IDS/IPS-Systemen

**Das Problem:** Eine Organisation mit tausenden Geräten erzeugt enorme Datenmengen. Die manuelle Überprüfung ist unmöglich.

### SIEM - Der zentrale Sicherheits-Hub

**SIEM = Security Information and Event Management**

Ein SIEM-System ist das zentrale Nervensystem der Sicherheitsoperationen. Es sammelt Daten aus verschiedenen Quellen, zentralisiert und analysiert sie.

**Kernfunktionen:**

1. **Log-Sammlung:** Über Agents, Syslog, APIs oder Dateiüberwachung
2. **Normalisierung:** Verschiedene Log-Formate werden in ein einheitliches Format umgewandelt
3. **Korrelation:** Identifiziert Beziehungen und Muster aus verschiedenen Quellen
4. **Alarmierung:** Benachrichtigt Analysten bei verdächtigen Ereignissen
5. **Reporting & Dashboards:** Visualisierung und Compliance-Berichte

**Beispiel-Korrelation:** Ein fehlgeschlagener Login, gefolgt von einem erfolgreichen Login aus einem anderen Land innerhalb kurzer Zeit, löst einen Alarm aus.

### Splunk - Die führende SIEM-Plattform

**Warum Splunk?**

- **SPL (Search Processing Language):** Flexible Abfragesprache für komplexe Analysen
- **Echtzeit-Überwachung:** Sofortige Sichtbarkeit auf Ereignisse
- **Skalierbar:** Von kleinen Unternehmen bis zu Petabytes an Daten
- **Anpassbare Dashboards:** Intuitive Visualisierung der Sicherheitslage

---

## 2. SIEM-Abfragen & Ermittlungsmethodik

### Die Sprache des SIEM

Jedes SIEM hat eine eigene Abfragesprache (Splunk = SPL, Microsoft Sentinel = KQL). **Aber:** Die Ermittlungsmethodik bleibt gleich!

**Abfrage-Komponenten:**

- **Felder:** Schlüssel-Wert-Paare (z.B. `user=admin`, `src_ip=192.168.1.100`)
- **Operatoren:** Logische Aussagen zum Filtern (`AND`, `OR`, `NOT`)
- **Befehle:** Verkettung mit Pipe-Zeichen `|` für Datenverarbeitung

### Die Ermittlungsmethodik

**1. Hypothese formulieren** Jede Untersuchung beginnt mit einer Frage oder Theorie.

**2. Breit anfangen** Starte mit einer weiten Suche, um die Landschaft zu verstehen, dann zoome hinein.

**3. Auf Findings pivotieren** Ein Fund (z.B. verdächtige IP) wird zum Angelpunkt für neue Fragen über alle Datenquellen.

**4. Timeline aufbauen** Rekonstruiere die Ereignisabfolge mit Zeitstempeln für eine präzise Erzählung.

**Praxis-Beispiel:** Ein Service-Account `svc_database` hat sich interaktiv von einer Marketing-Workstation angemeldet. Normalerweise erfolgen nur nicht-interaktive Logins vom Datenbankserver.

- **Hypothese:** Kompromittiertes Konto
- **Erste Abfrage:** Alle Aktivitäten von `svc_database` anzeigen
- **Pivot:** Workstation-IP für weitere verdächtige Aktivitäten untersuchen

---

## 3. Network Security Monitoring (NSM)

### Was ist NSM?

Network Security Monitoring sammelt, analysiert und reagiert auf Netzwerkdaten, um Bedrohungen zu erkennen und zu untersuchen. Es ist das Kamerasystem für Computernetzwerke.

**Assume-Breach-Mentalität:** Keine Verteidigung ist perfekt. Es ist nicht die Frage _ob_, sondern _wann_ ein Angreifer eindringt. NSM ermöglicht Erkennung und Reaktion.

### Die NSM Visibility Triad

**1. Full Packet Capture (PCAP)**

- **Was:** Bit-für-Bit-Aufzeichnung jedes Pakets
- **Vorteil:** Ultimative Grundwahrheit, vollständige Details
- **Nachteil:** Enorme Datenmenge, verschlüsselter Traffic ist unlesbar

**2. Network Flow Data**

- **Was:** Metadaten über Konversationen (wer, wann, wie lange)
- **Felder:** Quell-/Ziel-IP, Ports, Protokoll, Bytes, TCP-Flags
- **Vorteil:** Leichtgewichtig, Überblick über gesamten Traffic
- **Nachteil:** Keine Payload-Details

**3. Transaction Logs (Zeek)**

- **Was:** Strukturierte, hochrangige Beschreibungen von Netzwerkaktivitäten
- **Vorteil:** Perfekte Balance zwischen Detail und Übersicht
- **Beispiel:** DNS-Log zeigt sofort, welcher Client welche Domain abgefragt hat

### Wie sie zusammenarbeiten

**Szenario:** IDS-Alarm auf `192.168.1.100`

1. **Flow Data:** Zeigt große Verbindung zu verdächtiger externer IP
2. **Zeek Logs:** SSL-Log zeigt verdächtiges Zertifikat, DNS-Log zeigt Abfrage zu bösartiger Domain
3. **PCAP:** Bestätigt verdächtige Zertifikatdetails im TLS-Handshake

### Wichtige NSM-Tools

**Intrusion Detection Systems (IDS)**

- **Signaturbasiert:** Kennt bekannte Angriffe (wie Verbrecherfotos)
- **Anomaliebasiert:** Lernt normales Verhalten, alarmiert bei Abweichungen
- **Tools:** Snort, Suricata

**Zeek (früher Bro)** Erstellt umfassende Transaction Logs für proaktive Bedrohungsjagd. Philosophie: Daten geben, um Bedrohungen zu jagen, statt nur auf Signaturen zu warten.

**Wireshark** Essentielles Tool für tiefgehende, manuelle Paketanalyse.

---

## 4. Endpoint Security Monitoring

### Was ist ein Endpoint?

Jedes Gerät am Ende einer Netzwerkverbindung: Laptops, Server, Smartphones, IoT-Geräte. Für Angreifer sind Endpoints das Ziel - hier können sie Daten stehlen und Malware installieren.

### Warum Standard-Logs nicht reichen

**Limitierungen:**

- Keine Befehlszeilen-Protokollierung
- Kein Prozesskontext für Netzwerkverbindungen
- Kein automatisches File-Hashing
- Zu viel irrelevantes Rauschen

### Die Lösung: Spezialisierte Tools

**Sysmon - Die ultimative Datenquelle**

Ein kostenloses Tool von Microsoft, das hochwertige Logs über sicherheitsrelevante Ereignisse generiert.

**Wichtige Events:**

- **Event ID 1:** Prozesserstellung (Hash, Befehlszeile, Elternprozess)
- **Event ID 3:** Netzwerkverbindungen (verknüpft mit Prozess)
- **Event ID 11:** Dateierstellung (Malware-Dropper)
- **Event ID 22:** DNS-Abfragen (Command & Control)

**Wazuh - Open-Source Security Platform**

Kombiniert HIDS, EDR und SIEM-Funktionen.

**Architektur:**

- **Agent:** Auf Endpoints installiert, sammelt Daten
- **Manager:** Zentraler Server, analysiert und korreliert Daten
- **Dashboard:** Web-Interface für Visualisierung

**Features:** File Integrity Monitoring, Schwachstellenerkennung, Sicherheitskonfigurationsbewertung

**osquery - Der Endpoint als Datenbank**

Behandelt das Betriebssystem als SQL-Datenbank. Ermöglicht Echtzeit-Abfragen über den aktuellen Zustand.

**Beispiel-Abfragen:**

```sql
SELECT * FROM users WHERE username='admin'
SELECT * FROM listening_ports WHERE address='0.0.0.0'
SELECT * FROM processes WHERE on_disk=0
```

**Unterschied:** Logs zeigen die Vergangenheit, osquery zeigt den aktuellen Zustand.

---

## 5. Best Practices & Zusammenfassung

### Kernprinzipien

1. **Defense in Depth:** Mehrere Schutzschichten kombinieren
2. **Assume Breach:** Fokus auf Erkennung und Reaktion
3. **Kontinuierliche Überwachung:** 24/7-Sichtbarkeit ist essentiell
4. **Korrelation:** Einzelne Events sind weniger wichtig als Muster

### Die Security Monitoring Pipeline

```
Datenquellen (Logs, Netzwerk, Endpoints)
    ↓
Sammlung & Normalisierung (SIEM)
    ↓
Korrelation & Analyse
    ↓
Alarmierung & Dashboards
    ↓
Incident Response
```

### Wichtige Takeaways

- **SIEM:** Zentralisiert alle Sicherheitsdaten für Korrelation und Alarmierung
- **NSM:** Drei Datentypen (PCAP, Flow, Zeek) ergänzen sich perfekt
- **Endpoint Monitoring:** Sysmon + Wazuh + osquery decken alle Aspekte ab
- **Methodik:** Hypothese → Breit starten → Pivotieren → Timeline aufbauen

### Erfolgreiche Ermittlung

Eine gute Sicherheitsuntersuchung folgt immer der gleichen Logik, unabhängig vom Tool:

1. Verstehe, was normal ist
2. Erkenne Anomalien
3. Verfolge Indikatoren über alle Systeme
4. Baue eine evidenzbasierte Geschichte auf

---

**Viel Erfolg bei deiner Ausbildung!** 🛡️