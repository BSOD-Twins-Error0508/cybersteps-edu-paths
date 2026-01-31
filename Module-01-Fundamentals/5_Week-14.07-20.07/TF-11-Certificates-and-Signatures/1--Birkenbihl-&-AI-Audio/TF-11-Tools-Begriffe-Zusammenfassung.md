# Kategorisierung: Digitale Signaturen und Zertifikate

## Übersicht der verwendeten Elemente

|Kategorie|Begriffe/Tools|
|---|---|
|**Verwendete Tools**|Web-Browser (Chrome, Firefox, Edge), HTTPS-Websites, Verschlüsselungssoftware, Certificate Viewer (in Browsern integriert), Hash-Funktionen (SHA-256), PKI-Software|
|**Technische Fachbegriffe**|Digitale Signatur, Digitales Zertifikat, Certificate Authority (CA), Public Key Infrastructure (PKI), Hash/Message Digest, Asymmetrische Kryptographie, Root CA, Intermediate CA, X.509-Standard, Certificate Revocation List (CRL), Online Certificate Status Protocol (OCSP), Chain of Trust, Self-Signed Certificate|
|**Wichtige Vokabeln**|Authentizität, Integrität, Nichtabstreitbarkeit (Non-Repudiation), Privater Schlüssel, Öffentlicher Schlüssel, Verschlüsselung, Entschlüsselung, Verifikation, Trust Store, Gültigkeitszeitraum, Kollisionsresistenz|

## Bedeutungen

|Begriff|Bedeutung|
|---|---|
|**Verwendete Tools**||
|Web-Browser|Programme zum Anzeigen von Websites, die integrierte Funktionen zur Überprüfung von Zertifikaten haben (z.B. Edge, Chrome, Firefox)|
|HTTPS-Websites|Sichere Websites, die Verschlüsselung und Zertifikate verwenden (erkennbar am Schloss-Symbol)|
|Certificate Viewer|In Browsern eingebautes Werkzeug zum Anzeigen von Website-Zertifikaten (über Schloss-Symbol in Adressleiste)|
|Hash-Funktionen (SHA-256)|Mathematische Verfahren zur Erstellung eindeutiger "Fingerabdrücke" von Daten|
|PKI-Software|Programme zur Verwaltung von Zertifikaten und Schlüsseln|
|**Technische Fachbegriffe**||
|Digitale Signatur|Kryptographischer Mechanismus zum Nachweis von Echtheit, Unversehrtheit und Urheberschaft digitaler Daten|
|Digitales Zertifikat|Elektronisches Dokument, das einen öffentlichen Schlüssel einer bestimmten Identität (Person, Organisation, Website) zuordnet|
|Certificate Authority (CA)|Vertrauenswürdige Organisation, die digitale Zertifikate ausstellt und deren Echtheit bestätigt|
|Public Key Infrastructure (PKI)|Gesamtsystem aus Technologien, Regeln und Verfahren zur Verwaltung digitaler Zertifikate und Signaturen|
|Hash/Message Digest|Eindeutiger, fester "Fingerabdruck" einer Datei oder Nachricht, der durch eine Hash-Funktion erzeugt wird|
|Asymmetrische Kryptographie|Verschlüsselungsverfahren mit zwei Schlüsseln: einem privaten (geheim) und einem öffentlichen (für alle zugänglich)|
|Root CA|Oberste Zertifizierungsstelle, deren Zertifikat bereits in Betriebssystemen und Browsern vorinstalliert ist|
|Intermediate CA|Zwischenstelle, die von einer Root CA autorisiert wurde, Zertifikate auszustellen|
|X.509-Standard|Internationaler Standard für das Format digitaler Zertifikate|
|Certificate Revocation List (CRL)|Liste ungültig gemachter Zertifikate|
|OCSP|Online-Dienst zur Echtzeit-Überprüfung des Zertifikatstatus|
|Chain of Trust|Vertrauenskette von einem Website-Zertifikat über Intermediate CAs bis zur Root CA|
|Self-Signed Certificate|Selbst signiertes Zertifikat (nicht von externer CA bestätigt)|
|**Wichtige Vokabeln**||
|Authentizität|Echtheit – Bestätigung, dass der Absender wirklich ist, wer er vorgibt zu sein|
|Integrität|Unversehrtheit – Garantie, dass Daten nicht verändert wurden|
|Nichtabstreitbarkeit (Non-Repudiation)|Der Absender kann nicht leugnen, eine Nachricht gesendet zu haben|
|Privater Schlüssel|Geheimer Schlüssel, der nur dem Besitzer bekannt ist und zum Signieren/Entschlüsseln verwendet wird|
|Öffentlicher Schlüssel|Frei verfügbarer Schlüssel zum Verifizieren von Signaturen und Verschlüsseln von Nachrichten|
|Verschlüsselung|Umwandlung von Daten in unlesbares Format|
|Entschlüsselung|Rückumwandlung verschlüsselter Daten in lesbares Format|
|Verifikation|Überprüfung der Echtheit und Gültigkeit|
|Trust Store|Speicher für vertrauenswürdige Root-CA-Zertifikate im System|
|Gültigkeitszeitraum|Zeitraum, in dem ein Zertifikat gültig ist (von-bis Datum)|
|Kollisionsresistenz|Eigenschaft, dass zwei verschiedene Eingaben praktisch nie denselben Hash erzeugen|

---

## 80/20 Zusammenfassung: Das Wichtigste zu Digitalen Signaturen und Zertifikaten

### Kernproblem

Im Internet muss man zwei zentrale Fragen beantworten können:

1. Ist diese Nachricht/Datei wirklich von der angegebenen Person/Organisation?
2. Wurde sie unterwegs verändert?

### Die Lösung: Digitale Signaturen

**Funktionsweise in 3 Schritten:**

1. **Hash erstellen**: Sender erzeugt einen "Fingerabdruck" (Hash) der Nachricht mit einer Hash-Funktion wie SHA-256
2. **Mit privatem Schlüssel verschlüsseln**: Dieser Hash wird mit dem privaten Schlüssel verschlüsselt → das ist die digitale Signatur
3. **Verifizierung**: Empfänger entschlüsselt die Signatur mit dem öffentlichen Schlüssel des Senders und vergleicht den erhaltenen Hash mit einem selbst berechneten Hash der empfangenen Nachricht

**Was wird garantiert:**

- **Authentizität**: Nur der Besitzer des privaten Schlüssels konnte die Signatur erstellen
- **Integrität**: Jede Änderung an der Nachricht führt zu einem anderen Hash
- **Nichtabstreitbarkeit**: Der Sender kann nicht bestreiten, die Nachricht signiert zu haben

### Das zweite Problem: Vertrauen in öffentliche Schlüssel

**Problem**: Woher weiß man, dass ein öffentlicher Schlüssel wirklich der richtigen Person gehört?

**Lösung**: Digitale Zertifikate – elektronische "Ausweise" die aussagen: "Dieser öffentliche Schlüssel gehört zu dieser Person/Organisation"

**Ein Zertifikat enthält:**

- Identitätsinformationen (z.B. Domain-Name wie www.google.com)
- Den öffentlichen Schlüssel
- Digitale Signatur einer vertrauenswürdigen Zertifizierungsstelle (CA)
- Gültigkeitszeitraum

### Certificate Authorities (CAs): Die Vertrauensinstanzen

**Aufgaben:**

- Identität von Antragstellern überprüfen
- Zertifikate ausstellen und mit eigenem privaten Schlüssel signieren
- Kompromittierte Zertifikate widerrufen

**Chain of Trust (Vertrauenskette):**

1. Windows 11 (wie Mac OS) hat vorinstallierte Root-CA-Zertifikate
2. Root CAs signieren Intermediate CAs
3. Intermediate CAs signieren Website-Zertifikate
4. Browser prüft die gesamte Kette zurück bis zur vertrauenswürdigen Root CA

### Public Key Infrastructure (PKI)

Das Gesamtsystem aus Technologien, Richtlinien und Verfahren, das digitale Signaturen und Zertifikate ermöglicht. Es ist das "Ökosystem" hinter sicheren Online-Transaktionen.

### Praktische Anwendung in Windows 11

**So sehen Sie ein Zertifikat:**

1. Besuchen Sie eine HTTPS-Website in Edge, Chrome oder Firefox
2. Klicken Sie auf das Schloss-Symbol in der Adressleiste
3. Wählen Sie "Zertifikat anzeigen" oder "Verbindung ist sicher"
4. Dort sehen Sie alle Zertifikatsinformationen und die Vertrauenskette

**Warum ist das wichtig?**

- Jede sichere Website (Online-Banking, E-Mail, E-Commerce) nutzt diese Technologie
- Softwaredownloads werden oft digital signiert, um Manipulation zu verhindern
- E-Mail-Verschlüsselung und -Signierung basiert auf diesen Prinzipien

**Kritischer Punkt**: Wenn der private Schlüssel einer CA kompromittiert wird, könnten Angreifer gefälschte Zertifikate erstellen und sich als beliebige Websites ausgeben – deshalb ist die Sicherheit von Root CAs entscheidend für das gesamte Internet-Vertrauen.