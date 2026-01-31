Ich erstelle eine übersichtliche Kategorisierung der Themen aus dem Dokument über SIEM-Abfragen:

## Kategorisierung: SIEM und digitale Ermittlung

|**Kategorie**|**Bedeutung**|
|---|---|
|**Verwendete Tools**||
|SIEM (Security Information and Event Management)|System zur Sammlung, Aggregation und Analyse von Sicherheitsprotokollen aus dem gesamten Netzwerk|
|SPL (Search Processing Language)|Abfragesprache von Splunk für die Datenanalyse|
|Kusto Query Language (KQL)|Abfragesprache von Microsoft Sentinel für Sicherheitsabfragen|
|Splunk|SIEM-Plattform mit eigener Abfragesprache (SPL)|
|Microsoft Sentinel|Cloud-basierte SIEM-Lösung von Microsoft|
|**Technische Fachbegriffe**||
|Indexierung|Prozess, bei dem Daten durchsuchbar gemacht werden|
|Felder (Fields)|Schlüssel-Wert-Paare, die Kontext in Protokolleinträgen liefern|
|Operatoren|Logische Anweisungen zum Filtern von Daten|
|Befehle (Commands)|Anweisungen, die dem SIEM sagen, was mit den Daten zu tun ist|
|Pipe-Zeichen (\|)|Verkettungszeichen, das die Ausgabe eines Befehls als Eingabe für den nächsten weitergibt|
|IoC (Indicator of Compromise)|Hinweis auf eine Sicherheitskompromittierung (z.B. verdächtige IP-Adresse)|
|Pivot Point|Angelpunkt - ein Fund, der als Ausgangspunkt für weitere Untersuchungen dient|
|Timestamp|Zeitstempel zur Rekonstruktion der Ereignisabfolge|
|Non-interactive login|Nicht-interaktive Anmeldung (automatischer Prozess ohne Benutzerinteraktion)|
|Interactive login|Interaktive Anmeldung (manuelle Anmeldung durch Benutzer)|
|Service Account|Dienstkonto für automatisierte Prozesse ohne menschliche Interaktion|
|**Wichtige Vokabeln**||
|Ermittlungsmethodik|Systematischer Ansatz zur Untersuchung von Sicherheitsvorfällen|
|Hypothese|Anfängliche Theorie oder Frage, die eine Untersuchung leitet|
|Abfrage (Query)|Frage, die an die Daten gestellt wird, um Informationen zu filtern|
|Datenverarbeitungs-Pipeline|Verkettung von Befehlen zur schrittweisen Datenverarbeitung|
|Protokolleintrag (Log Entry)|Einzelner Eintrag in einer Logdatei|
|Protokollquelle (Log Source)|Ursprung der Protokolldaten (z.B. Server, Firewall)|
|Zeitstempelfeld|Feld, das den Zeitpunkt eines Ereignisses dokumentiert|
|Evidenzbasierte Erzählung|Durch Beweise gestützte Rekonstruktion eines Vorfalls|
|Weitwinkelobjektiv-Ansatz|Breite, unspezifische Anfangsabfrage, die später verfeinert wird|
|Hineinzoomen|Verfeinerung der Abfrage für spezifischere Ergebnisse|

**Kernmethodik**: Start Broad → Pivot on Findings → Build Timeline → Reconstruct Story