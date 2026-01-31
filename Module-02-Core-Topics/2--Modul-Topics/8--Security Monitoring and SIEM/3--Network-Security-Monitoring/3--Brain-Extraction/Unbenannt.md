## Kategorisierung: Network Security Monitoring (NSM)

|**Kategorie**|**Bedeutung**|
|---|---|
|**Verwendete Tools**||
|Zeek|Mächtiges Netzwerkanalyse-Framework zur Erzeugung strukturierter Transaction Logs für verschiedene Protokolle|
|Wireshark|Werkzeug für manuelle, tiefgehende Paketanalyse zur Untersuchung von PCAP-Dateien|
|Snort|Signaturbasiertes Intrusion Detection/Prevention System|
|Suricata|Signaturbasiertes Intrusion Detection/Prevention System|
|IDS (Intrusion Detection System)|Passives Überwachungswerkzeug zur Erkennung bösartiger Netzwerkmuster|
|IPS (Intrusion Prevention System)|Aktives System, das inline sitzt und bösartige Pakete automatisch blockieren kann|
|**Technische Fachbegriffe**||
|NSM (Network Security Monitoring)|Praxis des Sammelns, Analysierens und Reagierens auf Netzwerkdaten zur Bedrohungserkennung|
|Full Packet Capture (PCAP)|Bit-für-Bit-Aufzeichnung jedes einzelnen Pakets an einem Netzwerkpunkt|
|Network Flow Data|Metadaten über Netzwerkkonversationen (NetFlow, sFlow, IPFIX)|
|Transaction Logs|Strukturierte, hochrangige Beschreibungen spezifischer Netzwerkaktivitäten|
|NSM Visibility Triad|Die drei Hauptdatenquellen: PCAP, Flow Data, Transaction Logs|
|Payload|Anwendungsschichtdaten innerhalb eines Netzwerkpakets|
|C2 (Command-and-Control) Server|Bösartiger Server zur Steuerung kompromittierter Systeme|
|Exfiltration|Unbefugtes Herausschleusen/Stehlen von Daten aus einem Netzwerk|
|Ground Truth|Ultimative, unwiderlegbare Wahrheit über ein Netzwerkereignis|
|Assume Breach Mentality|Sicherheitsprinzip, das davon ausgeht, dass Angreifer irgendwann eindringen werden|
|Zero-Day Attack|Neuer, bisher unbekannter Angriff ohne existierende Signatur|
|False Positive|Fehlalarm - legitime Aktivität wird fälschlicherweise als bösartig erkannt|
|TLS (Transport Layer Security)|Verschlüsselungsprotokoll für sichere Netzwerkkommunikation|
|TCP Flags|Steuerungsinformationen in TCP-Paketen (z.B. SYN, FIN, RST)|
|DDoS (Distributed Denial of Service)|Verteilter Angriff zur Überlastung eines Systems|
|**Wichtige Vokabeln**||
|Signaturbasierte Erkennung|Methode zur Angriffserkennung basierend auf bekannten Mustern/Signaturen|
|Anomaliebasierte Erkennung|Erkennung durch Abweichung vom gelernten "normalen" Netzwerkverhalten|
|Source IP/Destination IP|Quell- und Ziel-IP-Adresse einer Netzwerkverbindung|
|Port|Logischer Verbindungsendpunkt für Netzwerkkommunikation|
|Protokoll|Regelwerk für die Kommunikation (z.B. TCP, UDP)|
|DNS Query|Anfrage zur Auflösung eines Domainnamens in eine IP-Adresse|
|SSL/TLS Certificate|Digitales Zertifikat zur Identifikation und Verschlüsselung|
|Baseline|Referenzbild normaler Netzwerkaktivität|
|Forensische Analyse|Detaillierte Untersuchung zur Rekonstruktion von Ereignissen|
|Inline|Direkt im Datenverkehrspfad positioniert (im Gegensatz zu passiv/parallel)|
|Tab-separated|Durch Tabulatorzeichen getrennte Datenfelder|
|Granular|Sehr detailliert, feinkörnig|
|Lightweight|Ressourcenschonend, mit geringem Speicher-/Rechenbedarf|
|Scalable|Skalierbar für große Datenmengen|
|30,000-foot view|Überblick aus der Vogelperspektive, hochrangige Gesamtsicht|

**Kernkonzept**: PCAP (Details) + Flow Data (Überblick) + Transaction Logs (Balance) = Vollständige NSM-Sichtbarkeit