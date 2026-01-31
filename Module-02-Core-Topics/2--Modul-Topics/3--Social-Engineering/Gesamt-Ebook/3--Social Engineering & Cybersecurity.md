## 1. Was ist Social Engineering?

**Social Engineering** ist die Kunst der psychologischen Manipulation. Statt komplexe technische Sicherheitssysteme anzugreifen, konzentrieren sich Angreifer auf das schwächste Glied: **den Menschen**.

### Ziele der Angreifer:

- **Zugangsdaten**: Benutzernamen und Passwörter sind der Schlüssel zu allen Systemen
- **Geld**: Betrügerische Überweisungen oder Ransomware-Zahlungen
- **Informationen**: Persönliche Daten, Geschäftsgeheimnisse, Quellcode
- **Störung**: Chaos verursachen und den Ruf schädigen

**Warum Menschen?** Weil es funktioniert! Es ist oft einfacher, eine Person zu täuschen, als eine technische Schwachstelle zu finden.

---

## 2. Psychologische Tricks der Angreifer

Social Engineers nutzen vorhersagbare menschliche Verhaltensweisen:

### **Autorität**

Wir gehorchen Autoritätspersonen. Angreifer geben sich als CEO, IT-Support oder Polizei aus.

### **Dringlichkeit**

"Ihr Konto wird in 24 Stunden gesperrt!" – Zeitdruck verhindert kritisches Denken.

### **Vertrauen**

Angreifer geben sich als Kollegen aus oder nutzen Informationen aus sozialen Medien, um Vertrauen aufzubauen.

### **Sozialer Beweis**

"Alle in Ihrem Team haben ihre Daten bereits aktualisiert" – macht die Anfrage normal erscheinen.

### **Knappheit**

"Nur noch 2 Plätze frei!" – erzeugt Handlungsdruck.

### **Einschüchterung**

Aggressive Sprache und Drohungen zwingen zur Kooperation.

---

## 3. Häufige Angriffstechniken

### **Phishing / Spear Phishing**

E-Mails, die von legitimen Quellen zu stammen scheinen. Spear Phishing ist gezielt auf bestimmte Personen oder Organisationen ausgerichtet.

### **Vishing / Smishing**

Telefonanrufe (Vishing) oder SMS (Smishing) statt E-Mails.

### **Baiting**

Ein Köder wird ausgelegt, z.B. ein USB-Stick mit der Aufschrift "Gehälter" auf einem Parkplatz.

### **Tailgating**

Physisch einer autorisierten Person in einen geschützten Bereich folgen.

---

## 4. Passwörter: Das Hauptziel

Die meisten Angriffe zielen darauf ab, **Ihr Passwort zu stehlen**. Ein Passwort öffnet Türen zu E-Mails, Bankkonten und Unternehmensdaten.

### Wie Passwörter gespeichert werden: Hashing

Seriöse Dienste speichern Passwörter nie im Klartext, sondern als **Hash** – eine Einbahnstraßen-Verschlüsselung.

**Hash-Funktion:**

- Wandelt Passwort in Zeichenkette fester Länge um
- Rückrechnung ist unmöglich
- Gleiche Eingabe = gleiche Ausgabe

**Problem:** Gleiche Passwörter = gleiche Hashes

### Die Lösung: Salting

Ein **Salt** ist ein zufälliger Text, der vor dem Hashing zum Passwort hinzugefügt wird:

- Benutzer 1: `GoBlue!` + Salt `abc789` → Hash A
- Benutzer 2: `GoBlue!` + Salt `xyz123` → Hash B

Auch bei gleichem Passwort sind die Hashes völlig unterschiedlich. Jedes Passwort muss einzeln geknackt werden.

---

## 5. Authentifizierung: Vom Passwort zum Token

### Das grundlegende Problem: Zustandslosigkeit

HTTP ist **zustandslos** – der Server vergisst Sie nach jeder Anfrage. Es braucht einen Mechanismus, um Sie wiederzuerkennen.

### Methode 1: Credentials bei jeder Anfrage (UNSICHER)

**HTTP Basic Authentication:** Benutzername und Passwort werden bei jeder Anfrage mitgeschickt (nur Base64-kodiert, nicht verschlüsselt). **Hochgradig unsicher!**

### Methode 2: Session-basiert (KLASSISCH)

**So funktioniert es:**

1. Sie loggen sich ein
2. Server erstellt eine Session und eine eindeutige **Session-ID**
3. Session-ID wird als **Cookie** in Ihrem Browser gespeichert
4. Bei jeder Anfrage sendet Browser den Cookie mit
5. Server erkennt Sie anhand der Session-ID

**Nachteil:** Server muss alle aktiven Sessions speichern (zustandsbehaftet).

**Gefahr:** Wer Ihre Session-ID stiehlt, kann Ihr Konto übernehmen (**Session Hijacking**).

### Methode 3: Token-basiert (MODERN)

**JSON Web Token (JWT):**

1. Sie loggen sich ein
2. Server erstellt ein Token mit Ihren Daten und einer kryptografischen Signatur
3. Sie speichern das Token und senden es bei jeder Anfrage mit
4. Server prüft nur die Signatur – keine Session-Speicherung nötig

**Vorteil:** Zustandslos, gut skalierbar.

**Gefahr:** Gestohlene Tokens gewähren sofortigen Zugriff bis zum Ablauf.

---

## 6. Multi-Faktor-Authentifizierung (MFA)

MFA schützt Konten durch Kombination mehrerer Faktoren:

- **Etwas, das Sie wissen:** Passwort
- **Etwas, das Sie haben:** Smartphone, Hardware-Key
- **Etwas, das Sie sind:** Fingerabdruck, Gesichtserkennung

### MFA-Methoden und ihre Schwächen

#### SMS & E-Mail-Codes (SCHWACH)

**Angriff:** SIM-Swapping – Angreifer überzeugt Ihren Mobilfunkanbieter, Ihre Nummer auf seine SIM-Karte zu übertragen.

#### Push-Benachrichtigungen

**Angriff:** MFA-Fatigue – Angreifer bombardiert Sie mit Login-Anfragen, bis Sie versehentlich auf "Genehmigen" tippen.

#### TOTP (Authenticator-App)

6-stelliger Code, der alle 30-60 Sekunden wechselt. Besser als SMS, aber nicht immun gegen fortgeschrittene Angriffe.

---

## 7. Der ultimative Angriff: Adversary-in-the-Middle (AiTM)

**AiTM-Phishing** ist die effektivste Methode, um auch TOTP-basierte MFA zu umgehen.

### So funktioniert es:

1. Opfer gibt Zugangsdaten auf Phishing-Seite ein
2. Angreifer leitet Daten in Echtzeit an echte Website weiter
3. Echte Website sendet 2FA-Code an Opfer
4. Opfer gibt Code auf Phishing-Seite ein
5. Angreifer leitet Code weiter
6. Echte Website gibt Session-Cookie heraus
7. Angreifer stiehlt Cookie und übernimmt Konto

**Das Ergebnis:** Angreifer hat vollen Zugriff ohne Passwort oder 2FA.

---

## 8. Die echte Lösung: Phishing-resistente MFA

### FIDO2 / WebAuthn

**Hardware Security Keys** (z.B. YubiKey) oder **Plattform-Authentifikatoren** (Windows Hello, Face/Touch ID) sind die einzige wirklich sichere Lösung.

**Warum es funktioniert:**

Bei der Registrierung wird ein kryptografischer Schlüssel erstellt, der an die **exakte Domain** gebunden ist (z.B. `google.com`).

Wenn ein Angreifer eine Phishing-Seite mit falscher Domain nutzt (z.B. `g00gle-login.com`), erkennt der Sicherheitsschlüssel den Unterschied und **verweigert die Aktivierung**.

**AiTM-Angriff = gestoppt!**

---

## 9. Wichtigste Erkenntnisse

✅ **Social Engineering zielt auf Menschen ab** – technische Sicherheit allein reicht nicht

✅ **Passwörter werden gehashed und gesalted** – nie im Klartext gespeichert

✅ **Sessions und Tokens ersetzen wiederholte Passwort-Eingaben** – beide können gestohlen werden

✅ **Standard-MFA ist nicht genug** – SMS und Push-Benachrichtigungen sind angreifbar

✅ **FIDO2/WebAuthn ist die Zukunft** – phishing-resistent durch Domain-Bindung

---

## 10. Handlungsempfehlungen

🔐 **Nutzen Sie einzigartige, starke Passwörter** für jeden Dienst

🔐 **Aktivieren Sie MFA überall** – bevorzugt FIDO2/Hardware-Keys

🔐 **Seien Sie skeptisch** bei unerwarteten Anfragen, auch von "Autoritäten"

🔐 **Prüfen Sie URLs genau** – Phishing-Seiten haben oft subtile Unterschiede

🔐 **Niemals unter Zeitdruck handeln** – Dringlichkeit ist eine Taktik

🔐 **Schulen Sie sich kontinuierlich** – Angreifer entwickeln ständig neue Methoden

---

**Ende des E-Books**

_Bleiben Sie wachsam, bleiben Sie sicher!_