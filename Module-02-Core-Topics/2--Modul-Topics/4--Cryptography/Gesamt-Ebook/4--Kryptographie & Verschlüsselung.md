## 1. Die Grundprinzipien: CIA-Triade + Non-Repudiation

Die Ziele der Kryptographie lassen sich in vier Kategorien einteilen:

### **Confidentiality (Vertraulichkeit)**

Daten geheim halten vor unbefugten Personen. Erreicht durch **Verschlüsselung**.

### **Integrity (Integrität)**

Sicherstellen, dass Daten nicht verändert wurden. Erreicht durch **Hashing**.

### **Availability (Verfügbarkeit)**

Daten müssen zugänglich sein, wenn sie gebraucht werden.

### **Non-Repudiation (Nichtabstreitbarkeit)**

Beweis, dass eine bestimmte Person eine Aktion durchgeführt hat. Erreicht durch **digitale Signaturen**.

---

## 2. Symmetrische Verschlüsselung

### Das Konzept

**Symmetrische Verschlüsselung** nutzt einen **einzigen geheimen Schlüssel** sowohl zum Ver- als auch zum Entschlüsseln. Es ist schnell und effizient – perfekt für große Datenmengen.

### XOR: Die einfachste Verschlüsselung

Die XOR-Operation (exklusives ODER) ist das Herzstück einfacher Verschlüsselung:

- Gleiche Eingaben → Ausgabe = 0
- Verschiedene Eingaben → Ausgabe = 1

**Die Magie von XOR:**

- `Klartext XOR Schlüssel = Geheimtext`
- `Geheimtext XOR Schlüssel = Klartext`

Derselbe Schlüssel ver- und entschlüsselt – perfekte Symmetrie!

### Moderne Lösungen

**Stream Ciphers:** Verschlüsseln Daten Bit für Bit mit einem kontinuierlichen Schlüsselstrom. Ideal für Echtzeitkommunikation wie Videoanrufe.

**Block Ciphers:** Verschlüsseln Daten in festen Blöcken. **AES (Advanced Encryption Standard)** ist der bekannteste Block-Cipher und verschlüsselt in Blöcken von 16 Bytes durch viele komplexe mathematische Runden.

### Das große Problem: Schlüsselverteilung

**Wie teilt man den geheimen Schlüssel sicher?** Wenn ein Angreifer den Schlüssel abfängt, ist die gesamte Verschlüsselung wertlos. Dies nennt man das **Key Distribution Problem**.

---

## 3. Hashing: Der digitale Fingerabdruck

### Was ist ein Hash?

Ein **Hash** ist eine Einbahnstraßen-Funktion, die aus beliebig langen Daten eine Zeichenkette fester Länge erzeugt.

**Eigenschaften:**

- **Einbahnstraße:** Aus dem Hash kann man die Originaldaten nicht zurückrechnen
- **Konsistent:** Gleiche Eingabe = gleicher Hash
- **Lawinen-Effekt:** Kleinste Änderung → komplett anderer Hash

### Anwendung: Passwort-Sicherheit

Systeme speichern nie Klartext-Passwörter, sondern nur deren Hash. Beim Login wird das eingegebene Passwort gehasht und mit dem gespeicherten Hash verglichen.

### Das Problem: Rainbow Tables

Angreifer können Millionen häufiger Passwörter vorher hashen und in **Rainbow Tables** speichern. Bei einem Datendiebstahl suchen sie einfach die gestohlenen Hashes in ihrer Tabelle.

### Die Lösung: Salting

Ein **Salt** ist eine zufällige Zeichenkette, die vor dem Hashing zum Passwort hinzugefügt wird:

- Benutzer 1: `password123` + Salt `aJd837` → Hash A
- Benutzer 2: `password123` + Salt `xyz123` → Hash B

Gleiche Passwörter haben nun völlig unterschiedliche Hashes. Rainbow Tables werden nutzlos!

### Hash-Algorithmen

- ❌ **MD5, SHA-1:** Veraltet und unsicher (Kollisionen möglich)
- ✅ **SHA-256, SHA-3:** Modern und sicher

---

## 4. Asymmetrische Verschlüsselung

### Das Konzept

**Asymmetrische Verschlüsselung** löst das Schlüsselverteilungsproblem durch ein Schlüsselpaar:

- **Public Key (Öffentlicher Schlüssel):** Kann frei geteilt werden, verschlüsselt Daten
- **Private Key (Privater Schlüssel):** Bleibt geheim, entschlüsselt Daten

**Kernprinzip:** Mit dem Public Key verschlüsselte Daten können **nur** mit dem zugehörigen Private Key entschlüsselt werden.

### Die Briefkasten-Analogie

1. Bob verteilt offene Vorhängeschlösser (Public Key) an alle
2. Alice legt eine Nachricht in Bobs Briefkasten und schließt sein Schloss
3. Nur Bob hat den passenden Schlüssel (Private Key) zum Öffnen

Selbst wenn jemand das Schloss stiehlt, kann er damit nur verschließen, nicht öffnen!

### Ablauf für Vertraulichkeit

1. Bob generiert sein Schlüsselpaar
2. Bob sendet seinen **Public Key** an Alice (kann abgehört werden!)
3. Alice verschlüsselt ihre Nachricht mit Bobs Public Key
4. Alice sendet den verschlüsselten Text an Bob
5. Bob entschlüsselt mit seinem **Private Key**

---

## 5. Digitale Signaturen

### Das umgekehrte Prinzip

Während der Public Key für **Vertraulichkeit** sorgt, ermöglicht der Private Key **Authentizität und Integrität**.

### So funktioniert's

1. **Hashing:** Alice erstellt einen Hash ihrer Nachricht
2. **Signieren:** Alice verschlüsselt den Hash mit ihrem **Private Key** (= digitale Signatur)
3. **Versenden:** Nachricht + Signatur gehen an Bob
4. **Verifizieren:** Bob entschlüsselt die Signatur mit Alices **Public Key** → Hash A
5. **Vergleichen:** Bob erstellt selbst einen Hash der Nachricht → Hash B
6. **Validierung:** Hash A = Hash B? → Signatur gültig!

### Was wird bewiesen?

- **Authentizität:** Nur Alice konnte die Signatur erstellen
- **Integrität:** Die Nachricht wurde nicht verändert
- **Non-Repudiation:** Alice kann nicht abstreiten, die Nachricht gesendet zu haben

---

## 6. Diffie-Hellman-Schlüsselaustausch

### Das Problem

Asymmetrische Verschlüsselung ist rechenintensiv und langsam. Für große Datenmengen unpraktisch.

### Die Lösung

**Hybrides System:** Asymmetrische Verschlüsselung zum sicheren Austausch eines temporären Schlüssels, dann schnelle symmetrische Verschlüsselung für die eigentliche Kommunikation.

### Die Farbmischungs-Analogie

1. **Gemeinsame Farbe:** Alice und Bob einigen sich öffentlich auf Gelb
2. **Geheime Farben:** Alice wählt heimlich Rot, Bob heimlich Blau
3. **Erste Mischung:**
    - Alice mischt Gelb + Rot = Orange
    - Bob mischt Gelb + Blau = Hellblau
4. **Öffentlicher Austausch:** Sie tauschen Orange und Hellblau aus
5. **Finales Geheimnis:**
    - Alice nimmt Bobs Hellblau + ihr Rot = Braunlila
    - Bob nimmt Alices Orange + sein Blau = Braunlila

Beide haben dieselbe Endfarbe! Ein Lauscher, der nur Gelb, Orange und Hellblau sah, kann die Endfarbe nicht "entmischen".

### Die Mathematik dahinter

Basiert auf **modularer Arithmetik** (Uhrzeit-Arithmetik):

1. Alice und Bob einigen sich öffentlich auf Zahlen `p` (große Primzahl) und `g` (Generator)
2. Alice wählt geheimes `a`, Bob wählt geheimes `b`
3. Alice berechnet `A = g^a mod p`, Bob berechnet `B = g^b mod p`
4. Sie tauschen `A` und `B` öffentlich aus
5. Alice berechnet `s = B^a mod p`, Bob berechnet `s = A^b mod p`

Beide erhalten denselben geheimen Schlüssel `s`!

**Warum es funktioniert:** `(g^b)^a = g^(b×a) = g^(a×b) = (g^a)^b`

---

## 7. Digitale Zertifikate & Vertrauen

### Das Problem: Man-in-the-Middle

Wie weiß man, mit wem man wirklich einen Diffie-Hellman-Austausch durchführt?

**MITM-Angriff:** Ein Angreifer positioniert sich zwischen Ihnen und der Bank:

- Führt einen Schlüsselaustausch mit Ihnen durch
- Führt einen separaten Austausch mit der Bank durch
- Entschlüsselt Ihre Nachrichten, liest sie, verschlüsselt sie neu

Sie denken, Sie reden mit der Bank – in Wahrheit kontrolliert der Angreifer alles!

### Die Lösung: Digitale Zertifikate

Ein **digitales Zertifikat** ist wie ein Pass für eine Website. Es verbindet kryptografisch eine Identität (z.B. `google.com`) mit einem Public Key.

**Standard:** X.509-Zertifikate

### Certificate Authorities (CAs)

**Vertrauenskette:**

1. **Root CA:** Hochvertrauenswürdige Zertifizierungsstellen (z.B. Let's Encrypt, DigiCert), deren Zertifikate in Ihrem Browser vorinstalliert sind
2. **Intermediate CA:** Von der Root CA signiert
3. **Server-Zertifikat:** Von der Intermediate CA signiert (z.B. für `www.google.com`)

Ihr Browser prüft die gesamte Kette. Wenn alles gültig ist: 🔒 Schloss-Symbol erscheint!

### Was steht im Zertifikat?

- **Subject:** Wem gehört es (z.B. `www.google.com`)
- **Issuer:** Wer hat es ausgestellt (CA)
- **Public Key:** Der öffentliche Schlüssel des Inhabers
- **Gültigkeitszeitraum:** "Nicht vor" und "Nicht nach" Datum
- **Seriennummer:** Eindeutige Kennung
- **Digitale Signatur:** Hash des Zertifikats, verschlüsselt mit dem Private Key der CA

---

## 8. TLS (Transport Layer Security)

### Das Hybrid-System

**TLS** kombiniert asymmetrische und symmetrische Verschlüsselung:

- **Asymmetrisch:** Für den Handshake – Authentifizierung und Schlüsselaushandlung
- **Symmetrisch:** Für die eigentliche Datenübertragung (schnell!)

### Die drei Garantien von TLS

1. **Authentifizierung:** Server-Zertifikat beweist Identität
2. **Vertraulichkeit:** Alle Daten sind verschlüsselt
3. **Integrität:** Daten können nicht unbemerkt verändert werden

### Der TLS-Handshake (vereinfacht)

1. **ClientHello:** "Hallo Server, ich unterstütze diese TLS-Versionen und Algorithmen"
2. **ServerHello:** "Perfekt, lass uns diese Version und Algorithmen nutzen. Hier ist mein Zertifikat"
3. **Verifikation & Schlüsselaustausch:**
    - Client prüft Zertifikat (Gültigkeit, Domain, CA-Signatur)
    - Beide führen Diffie-Hellman durch
    - Temporärer **symmetrischer Session Key** wird erstellt
4. **Finished:** Beide senden verschlüsselte "Fertig"-Nachricht

Ab jetzt: Alle Daten werden mit dem schnellen Session Key verschlüsselt!

---

## 9. Kryptographische Angriffe

### Die Angreifer-Denkweise

Moderne Verschlüsselungsalgorithmen direkt zu "knacken" ist extrem schwierig. Angreifer suchen nach **schwächeren Gliedern:**

- Veraltete Protokolle
- Fehlerhafte Implementierungen
- Menschliche Fehler

### Man-in-the-Middle (MITM)

Der Angreifer positioniert sich zwischen zwei Parteien und kontrolliert die gesamte Kommunikation.

**Angriffsvektoren:**

- **Unsicheres öffentliches WLAN:** Gefälschter Hotspot "Free_Airport_WiFi"
- **ARP Spoofing:** Angreifer gibt sich als Gateway im lokalen Netzwerk aus
- **DNS Spoofing:** Gefälschte DNS-Antworten leiten auf bösartige Server um

### Downgrade-Angriff

Statt starke Verschlüsselung zu knacken, **zwingt** der Angreifer beide Parteien zu schwächerer, angreifbarer Verschlüsselung.

**SSL Stripping:**

1. Sie wollen auf `https://mybank.com`
2. MITM-Angreifer fängt Anfrage ab
3. Angreifer verbindet sich per `https://` mit der Bank
4. Angreifer sendet Ihnen eine `http://`-Version (unverschlüsselt!)
5. Sie sehen kein Schloss-Symbol, tippen aber trotzdem Ihr Passwort ein
6. Angreifer liest alles im Klartext mit

**Besonders gefährlich:** Öffentliche WLANs!

### Hash-Kollisionen & Birthday Attack

Eine **Kollision** entsteht, wenn zwei unterschiedliche Eingaben denselben Hash erzeugen.

**Birthday Attack:** Basiert auf dem Geburtstags-Paradoxon – in einer Gruppe von nur 23 Personen liegt die Wahrscheinlichkeit bei über 50%, dass zwei denselben Geburtstag haben.

Statistisch ist es viel einfacher, **irgendeine** Kollision zu finden, als eine Kollision zu einem **spezifischen** Hash zu finden.

**Reales Beispiel: Flame-Malware (2012)**

Die Flame-Malware nutzte eine MD5-Kollision, um ein gefälschtes Microsoft-Zertifikat zu erstellen:

1. Angreifer fanden altes Microsoft-Zertifikat mit MD5
2. Erstellten bösartiges Zertifikat mit **identischem MD5-Hash**
3. Microsoft signierte unwissentlich das legitime Zertifikat
4. Signatur galt auch für das bösartige Zertifikat
5. Flame verbreitete sich als "echtes" Windows-Update

### Replay-Angriff

Der Angreifer zeichnet gültige Daten auf und sendet sie später erneut, um eine Aktion zu wiederholen.

**Beispiel: Keyless Car Theft**

Frühe Funkschlüssel-Systeme:

1. Angreifer zeichnet Signal beim Drücken des "Aufschließen"-Knopfes auf
2. Angreifer kommt später zurück und "replayed" das Signal
3. Auto öffnet sich

**Moderne Abwehr:**

- **Rolling Codes:** Jeder Knopfdruck sendet einen neuen Code
- **Timestamps:** Alte Nachrichten werden abgelehnt
- **Nonces:** Einmalig verwendete Zufallszahlen
- **Session IDs:** Eindeutige Token nach Login

---

## 10. Wichtigste Erkenntnisse

### Verschlüsselung

✅ **Symmetrisch:** Ein Schlüssel, schnell, Problem = Schlüsselverteilung

✅ **Asymmetrisch:** Schlüsselpaar, löst Verteilungsproblem, langsam

✅ **Hybrid (TLS):** Best of both worlds – asymmetrisch für Handshake, symmetrisch für Daten

### Sicherheitsmechanismen

✅ **Hashing + Salting:** Schützt Passwörter vor Rainbow Tables

✅ **Digitale Signaturen:** Beweisen Authentizität, Integrität, Non-Repudiation

✅ **Zertifikate:** Schaffen Vertrauen, verhindern MITM-Angriffe

✅ **Diffie-Hellman:** Ermöglicht sicheren Schlüsselaustausch über unsichere Kanäle

### Angriffe

✅ **MITM:** Angreifer positioniert sich zwischen Kommunikationspartnern

✅ **Downgrade:** Erzwingt schwächere Verschlüsselung (SSL Stripping)

✅ **Hash-Kollisionen:** Zwei Eingaben, gleicher Hash (MD5/SHA-1 unsicher!)

✅ **Replay:** Aufgezeichnete Daten werden erneut gesendet

---

## 11. Handlungsempfehlungen

🔐 **Nutzen Sie ausschließlich moderne Algorithmen:** AES, SHA-256/SHA-3, RSA-2048+

🔐 **Immer HTTPS verwenden** – nie Passwörter über HTTP eingeben

🔐 **Prüfen Sie das Schloss-Symbol** im Browser – Zertifikat anschauen!

🔐 **Vorsicht bei öffentlichem WLAN** – nutzen Sie VPN für sensible Daten

🔐 **Achten Sie auf Downgrade-Warnungen** – wenn plötzlich kein HTTPS mehr da ist

🔐 **Verwenden Sie gesalzene Hashes** beim Passwort-Speichern (bcrypt, Argon2)

🔐 **Multi-Faktor-Authentifizierung** als zusätzliche Sicherheitsschicht

---

**Ende des E-Books**

_Verschlüsselt bleiben, sicher bleiben!_