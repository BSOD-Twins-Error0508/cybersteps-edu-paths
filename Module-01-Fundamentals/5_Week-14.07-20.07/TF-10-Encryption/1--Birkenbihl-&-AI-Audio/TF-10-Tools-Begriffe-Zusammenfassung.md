# Verschlüsselung (Encryption) - Kategorisierung und Zusammenfassung

## Kategorisierung der Themen

|**Kategorie**|**Begriff**|**Bedeutung**|
|---|---|---|
|**Verwendete Tools**|BitLocker (Windows 11)|Windows-Tool für vollständige Festplattenverschlüsselung (Full-Disk Encryption)|
||VPN-Software|Programme zur Erstellung verschlüsselter Tunnel für Internetverkehr|
||Password Manager|Anwendungen zur verschlüsselten Speicherung von Passwörtern (z.B. KeePass, Bitwarden)|
||OpenSSL|Kommandozeilen-Tool für Verschlüsselung und Zertifikatsverwaltung|
||GPG/PGP|Tools für asymmetrische Verschlüsselung von E-Mails und Dateien|
||Webbrowser (Chrome, Edge, Firefox)|Zeigen HTTPS-Verschlüsselung durch Vorhängeschloss-Symbol an|
||HashCalc / certutil (Windows 11)|Tools zur Berechnung von Hash-Werten von Dateien|
|**Technische Fachbegriffe**|Plaintext (Klartext)|Original-Text oder Daten in lesbarer Form vor der Verschlüsselung|
||Ciphertext (Geheimtext)|Verschlüsselter, unlesbarer Text nach der Verschlüsselung|
||Algorithm/Cipher (Algorithmus)|Mathematische Methode zum Ver- und Entschlüsseln von Daten|
||Key (Schlüssel)|Geheime Information, die der Algorithmus zur Ver-/Entschlüsselung verwendet|
||Encryption (Verschlüsselung)|Umwandlung von Klartext in Geheimtext|
||Decryption (Entschlüsselung)|Rückumwandlung von Geheimtext in Klartext|
||Confidentiality (Vertraulichkeit)|Sicherstellung, dass Informationen nur für Berechtigte zugänglich sind|
||Symmetric Encryption|Verschlüsselung mit einem einzigen geheimen Schlüssel für beide Richtungen|
||Asymmetric Encryption|Verschlüsselung mit Schlüsselpaar (öffentlich + privat)|
||Public Key (Öffentlicher Schlüssel)|Schlüssel, der frei geteilt werden kann zum Verschlüsseln von Nachrichten|
||Private Key (Privater Schlüssel)|Geheimer Schlüssel zum Entschlüsseln von Nachrichten, muss geheim bleiben|
||Hybrid Encryption|Kombination aus symmetrischer und asymmetrischer Verschlüsselung|
||Key Distribution Problem|Herausforderung, symmetrische Schlüssel sicher zu teilen|
||Hashing|Einweg-Funktion zur Erstellung eines Fingerabdrucks von Daten|
||Hash Value/Digest|Feste Länge an Zeichen als Ergebnis einer Hash-Funktion|
||Avalanche Effect|Kleine Änderung im Input führt zu komplett anderem Hash-Wert|
||Data at Rest|Gespeicherte Daten auf Festplatten, USB-Sticks etc.|
||Data in Transit|Daten, die über Netzwerke übertragen werden|
||Authenticity (Authentizität)|Bestätigung der Echtheit einer Nachricht oder Identität|
||Integrity (Integrität)|Sicherstellung, dass Daten nicht verändert wurden|
||Digital Signature|Digitale Signatur zur Bestätigung von Absender und Unverändertheit|
||Full-Disk Encryption|Vollständige Verschlüsselung aller Daten auf einem Speichermedium|
||AES (Advanced Encryption Standard)|Moderner, starker symmetrischer Verschlüsselungsalgorithmus|
||RSA|Weit verbreiteter asymmetrischer Verschlüsselungsalgorithmus|
||ECC (Elliptic Curve Cryptography)|Moderne asymmetrische Verschlüsselung mit kürzeren Schlüsseln|
||DES/3DES|Ältere, heute unsichere symmetrische Algorithmen|
||SHA-256/SHA-3|Starke Hash-Funktionen der SHA-Familie|
||MD5|Alte, nicht mehr sichere Hash-Funktion|
||Salting|Hinzufügen zufälliger Daten zu Passwörtern vor dem Hashen|
|**Wichtige Vokabeln**|Scramble (Verschlüsseln/Verwürfeln)|Daten unleserlich machen|
||Unscramble (Entschlüsseln)|Daten wieder lesbar machen|
||Secret code (Geheimer Code)|Methode zur Geheimhaltung von Nachrichten|
||Tamper-proof (Fälschungssicher)|Kann nicht unbemerkt verändert werden|
||One-way (Einweg)|Prozess, der nicht umkehrbar ist (bei Hashing)|
||Two-way (Zweiweg)|Prozess, der umkehrbar ist (bei Verschlüsselung)|
||Fingerprint (Fingerabdruck)|Eindeutige Kennung für Daten (Hash-Wert)|
||Mailbox analogy (Briefkasten-Analogie)|Veranschaulichung asymmetrischer Verschlüsselung|
||Padlock icon (Vorhängeschloss-Symbol)|Browser-Symbol für sichere HTTPS-Verbindung|
||Tunnel (Tunnel)|Verschlüsselter Kommunikationskanal (bei VPN)|
||Master password (Master-Passwort)|Haupt-Passwort zum Entsperren eines Password Managers|
||Intercept (Abfangen)|Unbefugtes Mitlesen von Daten während der Übertragung|
||Caesar Cipher|Einfache historische Verschlüsselungsmethode durch Buchstabenverschiebung|
||Shift (Verschiebung)|Anzahl der Stellen, um die Buchstaben verschoben werden|
||Vault (Tresor)|Verschlüsselter Speicherort für sensible Daten|
||Download verification|Überprüfung der Echtheit heruntergeladener Dateien|

---

## Hinweis zu macOS vs. Windows 11

Das Dokument erwähnt **FileVault** (macOS) für Full-Disk Encryption. Für **Windows 11** verwenden Sie stattdessen:

- **BitLocker**: Windows-eigene Festplattenverschlüsselung
- Aktivierung: Einstellungen → Datenschutz & Sicherheit → Geräteverschlüsselung (oder Systemsteuerung → BitLocker-Laufwerkverschlüsselung)

---

## 80/20 Zusammenfassung (Die wichtigsten 20%)

### Was ist Verschlüsselung?

**Verschlüsselung (Encryption)** ist eine Methode, um lesbare Informationen in unlesbaren Code zu verwandeln, sodass nur autorisierte Personen sie lesen können.

**Der Grundprozess**:

```
Klartext (Plaintext) 
    → [Algorithmus + Schlüssel] → 
        Geheimtext (Ciphertext) 
            → [Algorithmus + Schlüssel] → 
                Klartext (Plaintext)
```

**Hauptziel**: **Vertraulichkeit (Confidentiality)** – Informationen vor unbefugtem Zugriff schützen

---

### Die 4 Grundbegriffe (80% des Verständnisses)

|Begriff|Bedeutung|Beispiel|
|---|---|---|
|**Plaintext**|Lesbare Original-Nachricht|"Mein Passwort ist cat123"|
|**Ciphertext**|Verschlüsselte Nachricht|"aGv#7!kLp"|
|**Algorithm**|Verschlüsselungsmethode|AES, RSA|
|**Key**|Geheimer Schlüssel|Wie ein Passwort für die Ver-/Entschlüsselung|

**Merksatz**: Ohne den richtigen **Schlüssel** ist der **Geheimtext** wertlos, selbst wenn man den **Algorithmus** kennt.

---

### Die 2 Haupttypen der Verschlüsselung

#### 1. Symmetrische Verschlüsselung (Ein Schlüssel für alles)

**Konzept**: Sender und Empfänger nutzen denselben geheimen Schlüssel

**Analogie**: Tagebuch mit einem Schloss – nur wer den identischen Schlüssel hat, kann es öffnen

**Prozess**:

```
1. Alice und Bob einigen sich auf geheimen Schlüssel
2. Alice verschlüsselt Nachricht mit Schlüssel → Ciphertext
3. Alice sendet Ciphertext an Bob
4. Bob entschlüsselt mit demselben Schlüssel → Plaintext
```

**Beispiele**:

- **AES** (Advanced Encryption Standard) – moderner Standard
- DES/3DES (veraltet, unsicher)

**Vorteile** ✅:

- **Sehr schnell** – ideal für große Datenmengen
- Einfache Implementierung

**Nachteile** ❌:

- **Key Distribution Problem**: Wie teilt man den Schlüssel sicher?
- Viele Kommunikationspartner = viele verschiedene Schlüssel nötig

**Anwendungen**:

- Festplattenverschlüsselung (BitLocker)
- Wi-Fi-Verschlüsselung (WPA2/WPA3)
- Verschlüsselung großer Dateien

---

#### 2. Asymmetrische Verschlüsselung (Zwei Schlüssel: öffentlich + privat)

**Konzept**: Jede Person hat ein Schlüsselpaar

**Die zwei Schlüssel**:

- **Public Key (Öffentlicher Schlüssel)**: Kann frei geteilt werden
- **Private Key (Privater Schlüssel)**: Muss absolut geheim bleiben

**Briefkasten-Analogie**:

- Jeder kann einen Brief in Ihren Briefkasten werfen (= mit Public Key verschlüsseln)
- Nur Sie haben den Schlüssel zum Öffnen (= mit Private Key entschlüsseln)

**Prozess**:

```
1. Bob veröffentlicht seinen Public Key
2. Alice verschlüsselt Nachricht mit Bobs Public Key
3. Alice sendet Ciphertext an Bob
4. Nur Bob kann mit seinem Private Key entschlüsseln
```

**Mathematische Beziehung**:

- Public Key + Nachricht = Ciphertext
- Nur passender Private Key kann Ciphertext entschlüsseln
- Private Key kann NICHT aus Public Key berechnet werden

**Beispiele**:

- **RSA** (Rivest-Shamir-Adleman)
- **ECC** (Elliptic Curve Cryptography)

**Vorteile** ✅:

- Löst das Key Distribution Problem
- Ermöglicht digitale Signaturen
- Keine vorherige Geheimkommunikation nötig

**Nachteile** ❌:

- **Langsam** – rechenintensiv, nicht für große Datenmengen geeignet

**Anwendungen**:

- HTTPS-Verbindungen (initialer Handshake)
- E-Mail-Verschlüsselung (PGP/GPG)
- Digitale Signaturen
- SSH-Verbindungen

---

### Hybride Verschlüsselung: Das Beste aus beiden Welten

**Problem**:

- Symmetrisch = schnell, aber Schlüsselaustausch unsicher
- Asymmetrisch = sicherer Schlüsselaustausch, aber langsam

**Lösung – Hybrid-Ansatz** (so funktioniert HTTPS):

```
Schritt 1: Asymmetrische Verschlüsselung
├─ Verwende Public/Private Keys
└─ Übertrage sicher einen temporären symmetrischen Schlüssel

Schritt 2: Symmetrische Verschlüsselung
├─ Nutze den ausgetauschten symmetrischen Schlüssel
└─ Verschlüssele alle weiteren Daten (schnell!)
```

**Reales Beispiel – Online-Shopping**:

1. Browser kontaktiert Amazon
2. **Asymmetrisch**: Browser und Server einigen sich auf Session-Key
3. **Symmetrisch**: Alle Daten (Login, Kreditkarte) werden mit Session-Key verschlüsselt
4. Session endet → neuer Session-Key beim nächsten Besuch

**Vorteil**: Sicherheit von Asymmetrisch + Geschwindigkeit von Symmetrisch

---

### Hashing: Der Einweg-Cousin der Verschlüsselung

**Wichtig**: Hashing ≠ Verschlüsselung!

**Hauptunterschiede**:

|Eigenschaft|Verschlüsselung|Hashing|
|---|---|---|
|Richtung|Zweiweg (hin + zurück)|Einweg (nur hin)|
|Hauptziel|Vertraulichkeit|Integrität|
|Umkehrbar?|Ja (mit Schlüssel)|Nein (mathematisch unmöglich)|
|Output-Länge|Variable Länge|Feste Länge|

**Was ist ein Hash?**

- Input (beliebige Größe) → Hash-Funktion → Hash-Wert (feste Länge)
- Beispiel: "Hallo Welt" → SHA-256 → "3d38e1..." (immer 64 Zeichen)

**Eigenschaften von Hashes**:

1. **Deterministisch**: Gleicher Input = immer gleicher Hash
2. **Einweg**: Hash → Original ist unmöglich
3. **Feste Länge**: 1 Byte oder 1 GB Input → immer gleiche Hash-Länge
4. **Avalanche Effect**: 1 Bit Änderung → komplett anderer Hash

**Hash-Funktionen**:

- ❌ **MD5** (128 Bit) – veraltet, unsicher
- ⚠️ **SHA-1** (160 Bit) – unsicher, nicht mehr verwenden
- ✅ **SHA-256** (256 Bit) – sicher, weit verbreitet
- ✅ **SHA-3** – neuester Standard

**Praktische Anwendungen**:

**1. Datei-Integrität prüfen**:

```
Software-Download:
├─ Website bietet SHA-256 Hash: "a3f4b2..."
├─ Sie laden Datei herunter
├─ Berechnen Hash selbst: "a3f4b2..."
└─ Hashes identisch? → Datei unverändert ✓
```

**2. Passwort-Speicherung**:

```
Registrierung:
├─ Sie: Passwort "cat123" eingeben
├─ Server: Hash berechnen → "8d969eef..." speichern
└─ Originales Passwort wird gelöscht

Login:
├─ Sie: Passwort "cat123" eingeben
├─ Server: Hash berechnen → "8d969eef..."
├─ Server: Vergleich mit gespeichertem Hash
└─ Hashes identisch? → Login erfolgreich
```

**Salting** (wichtige Zusatztechnik):

- Problem: Gleiche Passwörter = gleiche Hashes
- Lösung: Zufällige Daten (Salt) vor dem Hashen hinzufügen
- Beispiel: "cat123" + "randomSalt123" → Hash

---

### Die 5 wichtigsten Anwendungsfälle

#### 1. HTTPS – Sichere Websites

**Symbol**: 🔒 Vorhängeschloss + `https://`

**Ablauf**:

1. Browser kontaktiert Website
2. **Asymmetrisch**: Austausch eines Session-Keys
3. **Symmetrisch**: Verschlüsselung aller Daten mit Session-Key
4. Ihre Login-Daten, Kreditkarten etc. sind geschützt

**Schutz vor**: Abhören im Netzwerk, Man-in-the-Middle-Angriffen

---

#### 2. Festplattenverschlüsselung (BitLocker für Windows 11)

**Was es tut**: Verschlüsselt ALLE Daten auf der Festplatte

**Typ**: Symmetrische Verschlüsselung (AES)

**Szenario**:

- Laptop wird gestohlen
- Dieb kann physisch auf Festplatte zugreifen
- Ohne Passwort/Schlüssel → alle Daten unlesbar

**Aktivierung Windows 11**:

```
Einstellungen → Datenschutz & Sicherheit → Geräteverschlüsselung
oder
Systemsteuerung → BitLocker-Laufwerkverschlüsselung
```

---

#### 3. VPN (Virtual Private Network)

**Was es tut**: Erstellt verschlüsselten Tunnel für Internetverkehr

**Ablauf**:

```
Ihr Gerät → [Verschlüsselter Tunnel] → VPN-Server → Internet
```

**Typ**: Hybrid (asymmetrisch für Setup, symmetrisch für Daten)

**Schutz vor**:

- Abhören in öffentlichen WLANs (Café, Flughafen)
- ISP-Überwachung
- Geo-Blocking

---

#### 4. Verschlüsselte E-Mails (PGP/GPG)

**Typ**: Hybrid-Verschlüsselung

**Ablauf**:

1. E-Mail wird mit symmetrischem Schlüssel verschlüsselt (schnell)
2. Symmetrischer Schlüssel wird mit Empfänger-Public-Key verschlüsselt
3. Empfänger entschlüsselt Schlüssel mit Private Key
4. Empfänger entschlüsselt E-Mail mit symmetrischem Schlüssel

---

#### 5. Password Manager

**Was es tut**: Speichert alle Passwörter in verschlüsseltem Tresor

**Typ**: Symmetrische Verschlüsselung (AES)

**Prinzip**:

- Sie merken sich: 1 Master-Passwort
- Password Manager merkt sich: alle anderen Passwörter (verschlüsselt)

**Beispiele**:

- Bitwarden (Open Source)
- KeePass (Windows 11)
- 1Password
- LastPass

---

### Verschlüsselung vs. Hashing – Die kritischen Unterschiede

|Kriterium|Verschlüsselung|Hashing|
|---|---|---|
|**Zweck**|Vertraulichkeit|Integrität|
|**Umkehrbar?**|Ja (mit Schlüssel)|Nein|
|**Braucht Schlüssel?**|Ja|Nein|
|**Output-Länge**|Variabel|Fix|
|**Use Case**|Geheimnisse schützen|Änderungen erkennen|
|**Beispiel**|Login-Daten übertragen|Passwort speichern|

**Einfache Regel**:

- Müssen Daten wieder lesbar sein? → **Verschlüsselung**
- Müssen Daten nur vergleichbar sein? → **Hashing**

---

### Sicherheitsprinzipien – Was Verschlüsselung bietet

|Prinzip|Bedeutung|Technik|
|---|---|---|
|**Confidentiality**|Nur Berechtigte können lesen|Verschlüsselung|
|**Integrity**|Daten wurden nicht verändert|Hashing|
|**Authenticity**|Absender ist echt|Digitale Signaturen|
|**Non-Repudiation**|Absender kann nicht leugnen|Digitale Signaturen|

**CIA-Triad in Cybersecurity**:

- **C**onfidentiality (Vertraulichkeit)
- **I**ntegrity (Integrität)
- **A**vailability (Verfügbarkeit)

Verschlüsselung adressiert hauptsächlich **C** und hilft bei **I**.

---

### Merksätze für die Praxis

1. **Symmetrisch** = Ein Schlüssel für beide (schnell, Schlüsselaustausch problematisch)
2. **Asymmetrisch** = Zwei Schlüssel, Public + Private (langsam, sicherer Austausch)
3. **Hybrid** = Asymmetrisch für Schlüsselaustausch, dann symmetrisch für Daten
4. **Hashing ≠ Verschlüsselung** = Einweg vs. Zweiweg
5. **Private Key** = Absolut geheim halten, wie Ihre PIN
6. **Public Key** = Frei teilen, wie Ihre Postadresse
7. **HTTPS** = Ihre Verbindung ist verschlüsselt (Vorhängeschloss-Symbol)
8. **Gleicher Hash** = Gleicher Input (nützlich für Integrität)
9. **AES** = Moderner symmetrischer Standard
10. **RSA/ECC** = Moderne asymmetrische Standards

---

### Praktische Windows 11 Befehle

**Hash einer Datei berechnen** (PowerShell):

```powershell
Get-FileHash -Path "C:\Users\Download\file.exe" -Algorithm SHA256
```

**BitLocker Status prüfen**:

```powershell
manage-bde -status
```

**BitLocker aktivieren**:

```powershell
manage-bde -on C:
```

---

### Häufige Missverständnisse

❌ **Falsch**: "Hashing ist eine Art Verschlüsselung" ✅ **Richtig**: Hashing ist einweg, Verschlüsselung ist zweiweg

❌ **Falsch**: "Asymmetrische Verschlüsselung ist immer besser" ✅ **Richtig**: Jede hat ihre Anwendung (asymmetrisch für Keys, symmetrisch für Daten)

❌ **Falsch**: "Wenn ich den Algorithmus geheim halte, ist es sicherer" ✅ **Richtig**: Sicherheit liegt im Schlüssel, nicht im geheimen Algorithmus (Kerckhoffs-Prinzip)

❌ **Falsch**: "MD5-Hashes sind okay für Passwörter" ✅ **Richtig**: MD5 ist gebrochen, verwenden Sie SHA-256 oder besser bcrypt/Argon2

❌ **Falsch**: "VPN macht mich komplett anonym" ✅ **Richtig**: VPN verschlüsselt Verkehr, aber der VPN-Provider kann Aktivität sehen