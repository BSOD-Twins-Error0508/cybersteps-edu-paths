## Einführung

GRC steht für Governance, Risk und Compliance – das strategische Rückgrat der Cybersecurity. Während du bisher die technischen Aspekte gelernt hast (wie Schwachstellen finden, Netzwerke verteidigen), zeigt dir GRC das "Warum" und "Wofür".

---

## Teil 1: Was ist GRC?

### Governance (Führung)

**Definition:** Wie eine Organisation gesteuert und kontrolliert wird.

**Kernfragen:**

- Wer ist für Cybersecurity verantwortlich?
- Was sind unsere Sicherheitsziele?
- Wie treffen wir Sicherheitsentscheidungen?
- Wie messen wir Erfolg?

**Beispiel:** "Alle neue Software muss vor Einsatz ein Sicherheitsreview durchlaufen."

### Risk Management (Risikomanagement)

**Definition:** Risiken identifizieren, bewerten und priorisieren.

**Der Prozess:**

1. **Risiken identifizieren** - Was kann schiefgehen?
2. **Risiken analysieren** - Wie wahrscheinlich? Welche Auswirkung?
3. **Risiken behandeln** - Vier Optionen:
    - **Mindern:** Sicherheitsmaßnahmen implementieren
    - **Übertragen:** Risiko verschieben (z.B. Versicherung)
    - **Vermeiden:** Riskante Aktivität stoppen
    - **Akzeptieren:** Mit dem Risiko leben

**Beispiel:** SQL-Injection-Schwachstelle → Patch installieren (mindern)

### Compliance (Regelkonformität)

**Definition:** Gesetze, Vorschriften und Standards einhalten.

**Warum wichtig:**

- Vermeidung von Strafen
- Schutz der Reputation
- Vertrauen bei Kunden

---

## Teil 2: Sicherheits-Frameworks

### NIST Cybersecurity Framework (CSF)

Das weltweit beliebteste Framework mit **6 Funktionen:**

1. **GOVERN** - Strategie und Verantwortlichkeit festlegen
2. **IDENTIFY** - Assets und Risiken verstehen
3. **PROTECT** - Schutzmaßnahmen implementieren
4. **DETECT** - Angriffe erkennen
5. **RESPOND** - Auf Vorfälle reagieren
6. **RECOVER** - Normalbetrieb wiederherstellen

**Merksatz:** "Gutes Identifizieren Professioneller Dienste Rettet Rechtzeitig"

### ISO/IEC 27001

- Internationaler Standard für Informationssicherheit
- Organisationen können zertifiziert werden
- Erfordert ein Information Security Management System (ISMS)

### BSI IT-Grundschutz

- Deutscher Standard vom Bundesamt für Sicherheit
- Sehr detailliert mit Katalogen für typische IT-Komponenten
- De-facto-Standard für Behörden und Unternehmen in Deutschland

---

## Teil 3: Risikomanagement im Detail

### Was ist ein Risiko?

**Formel:** Risiko = Asset + Bedrohung + Schwachstelle

**Komponenten:**

- **Asset:** Etwas Wertvolles (Daten, Systeme, Reputation)
- **Schwachstelle:** Sicherheitslücke (ungepatchter Server, ungeschulter Mitarbeiter)
- **Bedrohung:** Potenzielle Gefahr (Hacker, Feuer, Unfall)

### Risikoanalyse-Methoden

#### 1. Qualitative Analyse (am häufigsten)

Verwendet Bewertungen wie **Hoch, Mittel, Niedrig**

**Risiko-Matrix:**

```
                AUSWIRKUNG
           Gering  Mittel   Hoch
W   Hoch     M       H       K
A Mittel     N       M       H
H Gering     N       N       M

N=Niedrig, M=Mittel, H=Hoch, K=Kritisch
```

#### 2. Quantitative Analyse

Rechnet mit konkreten Geldwerten:

- **SLE** (Single Loss Expectancy) = Verlust pro Vorfall
- **ARO** (Annualized Rate of Occurrence) = Häufigkeit pro Jahr
- **ALE** (Annualized Loss Expectancy) = SLE × ARO

**Beispiel:**

- SLE: 100.000€ pro Datenleck
- ARO: 0,2 (alle 5 Jahre)
- ALE: 20.000€ pro Jahr
- → Investition von 15.000€ in Schutzmaßnahme ist gerechtfertigt

### NIST Risk Management Framework (RMF)

**7 Schritte für formelles Risikomanagement:**

1. **PREPARE** - Organisation vorbereiten
2. **CATEGORIZE** - System nach Auswirkung einstufen
3. **SELECT** - Sicherheitsmaßnahmen auswählen
4. **IMPLEMENT** - Maßnahmen umsetzen
5. **ASSESS** - Wirksamkeit prüfen
6. **AUTHORIZE** - Freigabe erteilen
7. **MONITOR** - Kontinuierlich überwachen

### Third-Party Risk Management (TPRM)

**Problem:** Deine Sicherheit ist nur so stark wie der schwächste Partner.

**Beispiele für Drittparteien:**

- Cloud-Anbieter (AWS, Azure)
- Zahlungsdienstleister
- Marketing-Firmen mit Kundendaten

**Prozess:**

- Due Diligence vor Vertragsabschluss
- Sicherheitsanforderungen im Vertrag
- Kontinuierliche Überwachung

---

## Teil 4: Compliance und Regulierung

### GDPR (Datenschutz-Grundverordnung)

**Kern-Infos:**

- EU-Verordnung seit 2018
- Schützt personenbezogene Daten von EU-Bürgern
- Gilt weltweit für alle, die EU-Daten verarbeiten

**Wichtige Begriffe:**

- **Personenbezogene Daten:** Alle Infos, die eine Person identifizieren (Name, E-Mail, IP-Adresse)
- **Betroffene Person:** Die Person, deren Daten verarbeitet werden
- **Verantwortlicher:** Bestimmt Zweck und Mittel der Verarbeitung
- **Auftragsverarbeiter:** Verarbeitet Daten im Auftrag

**Artikel 32 - Datensicherheit:** Fordert angemessene technische Maßnahmen:

- Verschlüsselung und Pseudonymisierung
- Vertraulichkeit, Integrität, Verfügbarkeit
- Wiederherstellungsfähigkeit
- Regelmäßige Tests

**Strafen:** Bis zu 20 Mio. € oder 4% des weltweiten Jahresumsatzes

### PCI-DSS (Payment Card Industry Standard)

**Kern-Infos:**

- Kein Gesetz, sondern Standard der Kreditkartenbranche
- Pflicht für alle, die Kreditkartendaten verarbeiten
- Sehr präzise und technische Vorgaben

**6 Ziele und 12 Anforderungen:**

**Ziel 1: Sicheres Netzwerk**

1. Firewall konfigurieren
2. Keine Standardpasswörter verwenden

**Ziel 2: Karteninhaberdaten schützen** 3. Gespeicherte Daten schützen 4. Übertragung verschlüsseln

**Ziel 3: Schwachstellen-Management** 5. Malware-Schutz 6. Sichere Systeme entwickeln

**Ziel 4: Zugriffskontrolle** 7. Zugriff nach "Need-to-know" 8. Authentifizierung 9. Physischer Zugangsschutz

**Ziel 5: Monitoring** 10. Zugriffe protokollieren 11. Regelmäßig testen

**Ziel 6: Sicherheitsrichtlinie** 12. Security Policy pflegen

**Wichtige Regel (Req 3.4):** Kreditkartennummern müssen verschlüsselt, gehasht oder abgeschnitten gespeichert werden (z.B. ************1234)

---

## Teil 5: Governance und Policy-Hierarchie

### Die Policy-Hierarchie

Ein Management-Beschluss wird durch 4 Ebenen konkretisiert:

#### 1. Policy (Richtlinie)

- **Zweck:** Definiert das WARUM
- **Beispiel:** "Firmendaten auf Mobilgeräten müssen geschützt werden"
- **Eigenschaften:** Verpflichtend, high-level

#### 2. Standard

- **Zweck:** Definiert das WAS
- **Beispiel:** "Alle Firmen-Smartphones benötigen mindestens 6-stellige PIN und Remote-Wipe"
- **Eigenschaften:** Verpflichtend, messbar

#### 3. Procedure (Verfahrensanweisung)

- **Zweck:** Erklärt das WIE
- **Beispiel:** "1. Öffne Einstellungen. 2. Tippe auf Face ID & Code. 3. Wähle 'Code aktivieren'..."
- **Eigenschaften:** Schritt-für-Schritt-Anleitung

#### 4. Guideline (Empfehlung)

- **Zweck:** Zusätzliche Best Practices
- **Beispiel:** "Es wird empfohlen, einen alphanumerischen Code statt nur Zahlen zu verwenden"
- **Eigenschaften:** Nicht verpflichtend

**Eselsbrücke:** Policy → Standard → Procedure → Guideline = PSPG = "Please Stop Playing Games"

---

## Teil 6: NIST CSF im Detail

### Die 6 Funktionen - vertieft

#### GOVERN (GV)

**Kernfrage:** "Wer ist verantwortlich und was sind die Regeln?"

**Aktivitäten:**

- Cybersecurity-Strategie festlegen
- Rollen und Verantwortlichkeiten definieren
- Policies erstellen
- Risiko-Governance

#### IDENTIFY (ID)

**Kernfrage:** "Was habe ich und wo sind meine Probleme?"

**Aktivitäten:**

- Asset-Inventar erstellen
- Risikoanalyse durchführen
- Geschäftsumfeld verstehen

#### PROTECT (PR)

**Kernfrage:** "Wie verhindere ich erfolgreiche Angriffe?"

**Aktivitäten:**

- Zugriffskontrollen
- Datenverschlüsselung
- Schutztechnologien (Firewall, Antivirus)
- Mitarbeiterschulungen

#### DETECT (DE)

**Kernfrage:** "Wie erkenne ich Angriffe?"

**Aktivitäten:**

- Log-Sammlung
- Anomalie-Erkennung
- SIEM-Monitoring
- Kontinuierliche Überwachung

#### RESPOND (RS)

**Kernfrage:** "Was tue ich bei einem Angriff?"

**Aktivitäiten:**

- Incident Response Plan
- Kommunikation
- Analyse des Vorfalls
- Eindämmung
- Verbesserungen

#### RECOVER (RC)

**Kernfrage:** "Wie stellen wir den Betrieb wieder her?"

**Aktivitäten:**

- Recovery-Planung
- Disaster Recovery
- Backups wiederherstellen
- Kommunikation an Stakeholder

---

## Praxis-Beispiel: Alles zusammen

**Szenario:** E-Commerce-Website mit SQL-Injection-Schwachstelle

### 1. Risiko-Assessment

- **Asset:** Kundendatenbank mit E-Mails
- **Schwachstelle:** SQL-Injection
- **Bedrohung:** Externer Hacker
- **Auswirkung:** Hoch (GDPR-Strafe, Reputationsverlust)
- **Wahrscheinlichkeit:** Hoch (bekannte, leicht auffindbare Schwachstelle)
- **Gesamt-Risiko:** KRITISCH

### 2. NIST CSF Mapping

- **IDENTIFY:** Schwachstelle durch Scan gefunden
- **PROTECT:** Patch anwenden, Input-Validierung
- **DETECT:** WAF-Logs auf SQL-Injection-Versuche überwachen
- **RESPOND:** Incident Response Plan aktivieren falls Exploitation
- **RECOVER:** Backup-Strategie für Datenbank

### 3. Governance/Policy

- **Policy:** "Alle Web-Anwendungen müssen gegen OWASP Top 10 geschützt sein"
- **Standard:** "Quartalsmäßige Vulnerability Scans, kritische Patches innerhalb 48h"
- **Procedure:** "Patch-Prozess: 1. Backup erstellen, 2. Test-Umgebung, 3. Produktion..."

### 4. Compliance

- **GDPR Art. 32:** Technische Maßnahmen zum Datenschutz (Patch = Maßnahme)
- **Dokumentation:** Nachweis der Risikobehandlung für Audits

---

## Wichtige Merksätze

**GRC-Dreieck:**

- **Governance** = Die Regeln
- **Risk** = Die Prioritäten
- **Compliance** = Der Nachweis

**Risiko-Formel:**

> Risiko entsteht nur, wenn Asset, Bedrohung UND Schwachstelle zusammentreffen

**4 R's der Risikobehandlung:**

- **R**educe (Mindern)
- **t**Ransfer (Übertragen)
- **R**eject (Vermeiden)
- **R**etain (Akzeptieren)

**Policy-Kette:**

> Policy (Warum) → Standard (Was) → Procedure (Wie) → Guideline (Empfehlung)

---

## Checkliste für GRC-Verständnis

✓ Kannst du die drei Komponenten von GRC erklären? ✓ Kennst du die 6 NIST CSF Funktionen auswendig? ✓ Verstehst du den Unterschied zwischen qualitativ und quantitativ? ✓ Kennst du die 4 Arten der Risikobehandlung? ✓ Kannst du GDPR und PCI-DSS unterscheiden? ✓ Verstehst du die Policy-Hierarchie? ✓ Weißt du, was Third-Party Risk ist?

---

## Abschluss

GRC bildet das Fundament jeder professionellen Cybersecurity-Arbeit. Technisches Know-how allein reicht nicht – du musst verstehen:

- **Warum** Sicherheitsmaßnahmen nötig sind (Risk)
- **Was** rechtlich gefordert ist (Compliance)
- **Wie** alles organisiert wird (Governance)

Die Frameworks wie NIST CSF und Standards wie GDPR/PCI-DSS geben dir die Struktur, um aus technischen Einzelaktionen ein kohärentes, geschäftsorientiertes Sicherheitsprogramm zu machen.

**Nächste Schritte:**

- NIST CSF 2.0 Dokument durchblättern
- GDPR Enforcement Tracker ansehen
- PCI-DSS Quick Reference Guide lesen

---

_Viel Erfolg bei deiner Ausbildung!_