## Kategorisierung: Endpoint Security

|**Kategorie**|**Bedeutung**|
|---|---|
|**Verwendete Tools**||
|Sysmon (System Monitor)|Kostenloses Microsoft-Tool zur Generierung hochqualitativer Sicherheitslogs auf Windows-Systemen|
|Wazuh|Umfassende Open-Source-Sicherheitsplattform, die HIDS, EDR und SIEM kombiniert|
|Wazuh Agent|Kleines Programm auf Endpunkten zur Sammlung von Systemdaten, Logs und Prozessinformationen|
|Wazuh Manager|Zentraler Server zur Sammlung, Analyse und Korrelation von Daten aller Agents|
|Wazuh Indexer & Dashboard|Speicher- und Visualisierungsoberfläche für Daten und Alarme|
|osquery|Facebook-Tool, das Betriebssysteme als relationale Datenbank behandelt und SQL-ähnliche Abfragen ermöglicht|
|Event Viewer|Windows-Tool zur Anzeige von System-, Sicherheits- und Anwendungsereignissen|
|Wireshark|Tool zur Paketanalyse (aus vorherigen Lektionen)|
|PowerShell|Windows-Befehlszeilen-Schnittstelle für Systemadministration|
|SwiftOnSecurity Config|Beliebte Sysmon-Konfigurationsdatei zum Herausfiltern von Rauschen|
|**Technische Fachbegriffe**||
|Endpoint|Jedes Gerät am Ende einer Netzwerkverbindung (Laptop, Server, IoT-Gerät)|
|EDR (Endpoint Detection and Response)|Technologie zur Erkennung und Reaktion auf Bedrohungen auf Endpunkten|
|HIDS (Host-based Intrusion Detection System)|Intrusion-Detection-System, das auf einzelnen Hosts läuft|
|Event ID 1 (Process Creation)|Sysmon-Ereignis, das jeden Prozessstart mit Hash, Befehlszeile und Elternprozess protokolliert|
|Event ID 3 (Network Connection)|Sysmon-Ereignis für TCP/UDP-Verbindungen mit Prozesszuordnung|
|Event ID 11 (File Creation)|Sysmon-Ereignis zur Protokollierung von Dateierstellungen|
|Event ID 22 (DNS Query)|Sysmon-Ereignis für DNS-Abfragen von Prozessen|
|Command Line Logging|Protokollierung der vollständigen Befehlszeile eines ausgeführten Prozesses|
|File Hash (SHA-256)|Kryptographischer Fingerabdruck einer Datei zur eindeutigen Identifikation|
|File Integrity Monitoring (FIM)|Überwachung von Dateiänderungen zur Erkennung unbefugter Modifikationen|
|Fileless Malware|Malware, die keine Datei auf der Festplatte hinterlässt und nur im Speicher existiert|
|Parent Process|Elternprozess, der einen anderen Prozess gestartet hat|
|IoT (Internet of Things)|Intelligente, vernetzte Geräte wie Smart-TVs, Drucker, Kameras|
|Manager-Agent Model|Architektur mit zentralem Server (Manager) und verteilten Clients (Agents)|
|**Wichtige Vokabeln**||
|Default Logs|Standard-Systemprotokolle, die primär für Fehlerbehebung, nicht für Sicherheit entwickelt wurden|
|Process Context|Kontextinformationen über den Prozess, der eine Aktion ausgeführt hat|
|Malware Dropper|Schadprogramm, das andere Malware herunterlädt oder installiert|
|Command and Control (C2)|Kommunikationskanal zwischen Malware und Angreifer-Server|
|High-Fidelity Logs|Hochqualitative, detailreiche Protokolle|
|Threat Hunting|Proaktive Suche nach Bedrohungen in der Infrastruktur|
|Indicator of Compromise (IoC)|Hinweis auf eine erfolgte Kompromittierung|
|State-based Querying|Abfragen zum aktuellen Systemzustand (Gegensatz zu historischen Logs)|
|Log-based Analysis|Analyse vergangener Ereignisse anhand von Protokollen|
|SQL-like Query|SQL-ähnliche Datenbankabfrage|
|Security Configuration Assessment|Bewertung der Sicherheitskonfiguration eines Systems|
|Vulnerability Detection|Erkennung von Schwachstellen im System|
|Ruleset|Regelwerk zur Erkennung bekannter Angriffsmuster|
|Event Correlation|Verknüpfung mehrier Ereignisse zur Mustererkennung|
|Actionable Alert|Umsetzbarer Alarm mit konkreten Handlungsempfehlungen|
|Ground Truth|Definitiver, unwiderlegbarer Beweis für ein Ereignis|
|svchost.exe|Legitimer Windows-Systemprozess, der häufig von Malware imitiert wird|

**Kernkonzept**: Logs (Vergangenheit: Was passierte?) + State Queries (Gegenwart: Was ist jetzt?) = Vollständige Endpoint-Sichtbarkeit

**Hauptproblem**: Standard-Logs fehlen: Befehlszeilen, Prozesskontext, Datei-Hashes → Lösung: Sysmon + Wazuh + osquery