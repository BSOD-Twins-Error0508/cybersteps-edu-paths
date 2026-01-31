# Kategorisierung der Zahlensystem-Themen

## Verwendete Tools, Technische Fachbegriffe und Wichtige Vokabeln

|Begriff|Bedeutung|
|---|---|
|**Verwendete Tools (macOS → Windows)**||
|Calculator (Programmer Mode)|Taschenrechner im Programmierer-Modus für Zahlenkonvertierung (Windows: `Rechner-App` → Menü → `Programmierer`)|
|`Cmd + Space` → "Calculator"|Taschenrechner öffnen (Windows: `Windows-Taste` → "Rechner" eingeben)|
|`Shift + Cmd + 3` (Calculator)|Programmierer-Ansicht (Windows Rechner: Menü-Icon → `Programmierer` auswählen)|
|Online Converter|Web-basierte Konvertierungstools (z.B. "binary to hex converter")|
|Python Shell|Programmiersprache für Konvertierungen (`bin()`, `hex()`, `int(x, base)`) - identisch auf Windows|
|Wireshark|Netzwerk-Analyse-Tool, zeigt Daten in Hex (verfügbar für Windows)|
|**Zahlensysteme (Numeral Systems)**||
|Numeral System / Number System|Zahlensystem - Art der Darstellung von Zahlen|
|Base / Radix|Basis eines Zahlensystems (z.B. Base-10, Base-2, Base-16)|
|Place Value|Stellenwert - Wert einer Ziffer abhängig von ihrer Position|
|Decimal (Base-10)|Dezimalsystem - System mit 10 Ziffern (0-9), das wir täglich nutzen|
|Binary (Base-2)|Binärsystem - System mit 2 Ziffern (0 und 1), von Computern verwendet|
|Hexadecimal (Base-16)|Hexadezimalsystem - System mit 16 Symbolen (0-9, A-F)|
|**Binäre Konzepte**||
|Bit|Binary Digit - kleinste Dateneinheit (0 oder 1)|
|Byte|8 Bits zusammen - Standard-Dateneinheit|
|Nibble|4 Bits - halbes Byte, entspricht genau einer Hex-Ziffer|
|MSB (Most Significant Bit)|Höchstwertiges Bit - linkestes Bit mit größtem Stellenwert|
|LSB (Least Significant Bit)|Niedrigstwertiges Bit - rechtestes Bit mit kleinstem Stellenwert|
|Transistor|Elektronisches Bauteil mit 2 Zuständen (ON/OFF = 1/0) - Grundlage von Computern|
|**Hexadezimal-Notation**||
|Hex Digit|Hexadezimal-Ziffer (0-9, A-F)|
|`0x` Prefix|Präfix zur Kennzeichnung von Hexadezimalzahlen (z.B. `0xFACE`, `0xFF`)|
|`#` Prefix|Präfix für Hex-Farben im Web (z.B. `#FF0000` = Rot)|
|A-F|Hexadezimal-Buchstaben für Dezimalwerte 10-15|
|**Bitweise Operationen (Bitwise Operations)**||
|Bitwise Operation|Operation direkt auf Bit-Ebene|
|AND (`&`)|UND-Verknüpfung - Ergebnis ist 1 nur wenn beide Bits 1 sind|
|OR (`\|`)|ODER-Verknüpfung - Ergebnis ist 1 wenn mindestens ein Bit 1 ist|
|XOR (`^`)|Exklusiv-ODER - Ergebnis ist 1 wenn Bits unterschiedlich sind|
|NOT (`~`)|NICHT-Verknüpfung - invertiert alle Bits (0↔1)|
|Left Shift (`<<`)|Linksverschiebung - verschiebt Bits nach links (multipliziert mit 2)|
|Right Shift (`>>`)|Rechtsverschiebung - verschiebt Bits nach rechts (dividiert durch 2)|
|Masking|Maskierung - Prüfen spezifischer Bits mit AND-Operation|
|Bit Toggling|Bit umschalten - Ändern eines Bits mit XOR|
|Unary Operator|Einstelliger Operator - wirkt auf einen Operanden (z.B. NOT)|
|Binary Operator|Zweistelliger Operator - wirkt auf zwei Operanden (z.B. AND, OR, XOR)|
|**Negative Zahlen**||
|Two's Complement|Zweierkomplement - Standardmethode zur Darstellung negativer Zahlen|
|One's Complement|Einerkomplement - invertierte Bits (Zwischenschritt für Two's Complement)|
|Sign Bit|Vorzeichenbit - MSB zeigt Vorzeichen (0=positiv, 1=negativ in Two's Complement)|
|Signed / Unsigned|Mit/ohne Vorzeichen - bestimmt, ob negative Zahlen möglich sind|
|**Konvertierungsmethoden**||
|Manual Conversion|Manuelle Konvertierung - Rechnung von Hand zur Umwandlung zwischen Systemen|
|Powers of 2|Zweierpotenzen - 1, 2, 4, 8, 16, 32, 64, 128, 256, 512, 1024...|
|Powers of 16|Sechzehnerpotenzen - 1, 16, 256, 4096...|
|Grouping (Binary to Hex)|Gruppierung - 4er-Gruppen von Binärziffern für Hex-Konvertierung|
|Remainder Method|Rest-Methode - Division mit Rest für Dezimal→Binär/Hex Konvertierung|
|**Anwendungsbereiche**||
|Memory Dump|Speicherabbild - Rohdaten aus dem Arbeitsspeicher (meist in Hex angezeigt)|
|Packet Analysis|Paketanalyse - Untersuchen von Netzwerkdaten (in Hex)|
|MAC Address|Hardware-Adresse in Hex-Format (z.B. `AA:BB:CC:DD:EE:FF`)|
|IPv6 Address|IPv6-Adresse nutzt Hexadezimal (z.B. `2001:0db8::1`)|
|Machine Code|Maschinencode - Prozessor-Anweisungen in Binär/Hex|
|Color Code|Farbcode im Web - Hex-RGB-Werte (z.B. `#FF0000`)|
|Permission Flags|Berechtigungs-Flags - Zugriffskontrolle mit Bits (z.B. `rwx` = `111`)|
|Encryption|Verschlüsselung - oft mit XOR-Operationen|
|Error Checking|Fehlerprüfung - XOR für Checksummen|
|**Speichereinheiten**||
|Kilobyte vs Kibibyte|KB (1000 Bytes, Dezimal) vs KiB (1024 Bytes, Binär) - Verwirrung durch Base-10 vs Base-2|
|Binary Prefix|Binäres Präfix - KiB, MiB, GiB (basierend auf 1024)|
|Decimal Prefix|Dezimales Präfix - KB, MB, GB (basierend auf 1000)|

---

## Windows 11: Rechner im Programmierer-Modus nutzen

|Funktion|Anleitung|
|---|---|
|**Rechner öffnen**|`Windows-Taste` drücken → "Rechner" eingeben → Enter|
|**Programmierer-Modus aktivieren**|Im Rechner: Hamburger-Menü (☰) oben links → `Programmierer` auswählen|
|**Zahlensystem wechseln**|Linke Seite: Buttons für `HEX`, `DEC`, `OCT`, `BIN` anklicken|
|**Dezimal → Binär**|Im `DEC`-Modus Zahl eingeben → auf `BIN` klicken|
|**Binär → Hexadezimal**|Im `BIN`-Modus Zahl eingeben → auf `HEX` klicken|
|**Hexadezimal → Dezimal**|Im `HEX`-Modus Zahl eingeben (A-F verfügbar) → auf `DEC` klicken|
|**Bitweise Operationen**|Im Programmierer-Modus verfügbar: `AND`, `OR`, `XOR`, `NOT`, `<<`, `>>`|
|**Bit-Anzeige**|Zeigt Binärdarstellung mit anklickbaren Bits (zum Umschalten)|
|**QWORD/DWORD/WORD/BYTE**|Schaltet zwischen Bit-Breiten um (64/32/16/8 Bit)|

**Python-Alternative (Windows PowerShell oder CMD):**

```python
# Python starten: "python" in CMD/PowerShell eingeben
bin(42)        # Dezimal → Binär: '0b101010'
hex(42)        # Dezimal → Hex: '0x2a'
int('101010', 2)   # Binär → Dezimal: 42
int('2a', 16)      # Hex → Dezimal: 42
int('0xFACE', 16)  # Hex mit 0x → Dezimal: 64206
```

---

## 80/20 Zusammenfassung: Die wichtigsten 20% für 80% Verständnis

### Die 3 Zahlensysteme, die du kennen musst

#### 1. **Dezimal (Base-10) - Unser Alltags-System**

- **Ziffern:** 0-9 (10 verschiedene)
- **Stellenwerte:** Zehnerpotenzen (1, 10, 100, 1000...)
- **Beispiel:** `254` = 2×100 + 5×10 + 4×1
- **Verwendung:** Menschliche Kommunikation

#### 2. **Binär (Base-2) - Die Sprache der Computer**

- **Ziffern:** 0 und 1 (nur 2!)
- **Stellenwerte:** Zweierpotenzen (1, 2, 4, 8, 16, 32, 64, 128...)
- **Beispiel:** `11111110` = 128+64+32+16+8+4+2 = 254
- **Warum Binär?** Transistoren haben nur 2 Zustände: AN (1) oder AUS (0)
- **1 Byte = 8 Bits** (z.B. `11111111` = 255 dezimal)

#### 3. **Hexadezimal (Base-16) - Programmier-Kurzschrift**

- **Symbole:** 0-9 und A-F (16 verschiedene)
    - A=10, B=11, C=12, D=13, E=14, F=15
- **Stellenwerte:** Sechzehnerpotenzen (1, 16, 256...)
- **Beispiel:** `FE` = 15×16 + 14×1 = 254
- **Schreibweise:** Mit `0x` Präfix → `0xFE`

### Der Hex-Binär-Trick: Die goldene Regel

**1 Hex-Ziffer = genau 4 Binär-Bits**

|Hex|Binär|Dezimal|
|---|---|---|
|0|0000|0|
|1|0001|1|
|2|0010|2|
|...|...|...|
|9|1001|9|
|A|1010|10|
|B|1011|11|
|C|1100|12|
|D|1101|13|
|E|1110|14|
|F|1111|15|

**Beispiel-Konvertierung:**

- Binär: `11111110`
- Gruppiere: `1111 1110`
- Konvertiere: `F E`
- Hex: `0xFE`

**Daher:** Hex ist perfekt zum Lesen von Binärdaten!

### Wichtigste Zweierpotenzen auswendig lernen

```
2⁰ = 1       2⁴ = 16      2⁸ = 256
2¹ = 2       2⁵ = 32      2⁹ = 512
2² = 4       2⁶ = 64      2¹⁰ = 1024
2³ = 8       2⁷ = 128
```

**Merkhilfe:** Jede Verdopplung ist die nächste Potenz!

### Konvertierung: Die Schnellmethoden

#### **Binär → Dezimal** (Addition)

```
10110 = ?
Position: 4 3 2 1 0
Wert:    16+0+4+2+0 = 22
```

#### **Dezimal → Binär** (Division durch 2)

```
42 ÷ 2 = 21 Rest 0  ↓
21 ÷ 2 = 10 Rest 1  ↓
10 ÷ 2 = 5  Rest 0  ↓
5  ÷ 2 = 2  Rest 1  ↓
2  ÷ 2 = 1  Rest 0  ↓
1  ÷ 2 = 0  Rest 1  ↓

Von unten lesen: 101010
```

#### **Hex → Binär** (Ersetze jede Ziffer durch 4 Bits)

```
0xA3 = ?
A = 1010
3 = 0011
→ 10100011
```

#### **Binär → Hex** (Gruppiere 4er-Blöcke)

```
11010111 = ?
Gruppiere: 1101 0111
           D    7
→ 0xD7
```

### Bitweise Operationen: Die Top 4

#### **1. AND (`&`) - Masken erstellen**

```
  1100  (12)
& 1010  (10)
------
  1000  (8)
```

**Regel:** Nur 1, wenn BEIDE 1 sind **Nutzen:** Bestimmte Bits prüfen (z.B. Berechtigungen checken)

#### **2. OR (`|`) - Bits setzen**

```
  1100  (12)
| 1010  (10)
------
  1110  (14)
```

**Regel:** 1, wenn MINDESTENS EINE 1 **Nutzen:** Bestimmte Bits aktivieren (z.B. Berechtigung erteilen)

#### **3. XOR (`^`) - Unterschiede finden**

```
  1100  (12)
^ 1010  (10)
------
  0110  (6)
```

**Regel:** 1, wenn Bits UNTERSCHIEDLICH sind **Nutzen:** Einfache Verschlüsselung, Fehlerprüfung **Besonderheit:**

- `X ^ X = 0` (Zahl mit sich selbst = immer 0)
- `X ^ 0 = X` (Zahl mit 0 = bleibt unverändert)

#### **4. NOT (`~`) - Alles umkehren**

```
~ 1100
------
  0011
```

**Regel:** Jedes Bit wird invertiert (0↔1) **Nutzen:** Bits invertieren

#### **Bonus: Shift-Operationen**

```
1100 << 1 = 11000   (Links: ×2)
1100 >> 1 = 0110    (Rechts: ÷2)
```

### Windows-Rechner: Die 3-Schritte-Anleitung

**Schritt 1:** Windows-Taste → "Rechner" → Enter

**Schritt 2:** Menü (☰) → "Programmierer"

**Schritt 3:** Zahl eingeben → Zwischen `HEX`, `DEC`, `BIN` wechseln

**Beispiel:**

1. Aktiviere `DEC`, tippe `42`
2. Klicke `BIN` → siehst `101010`
3. Klicke `HEX` → siehst `2A`

### Negative Zahlen: Two's Complement (Grundidee)

**Problem:** Wie zeigt man `-5` mit nur 0 und 1?

**Lösung: Two's Complement (8 Bit Beispiel)**

```
+5 = 00000101
Schritt 1: Invertiere (NOT)  → 11111010
Schritt 2: Addiere 1          → 11111011
Ergebnis: -5 = 11111011
```

**Regel:** Linkestes Bit = Vorzeichen (0=positiv, 1=negativ)

### Cybersecurity-Relevanz: Wo begegnet dir das?

1. **Netzwerk-Analyse (Wireshark)**
    
    - MAC-Adressen: `AA:BB:CC:DD:EE:FF` (Hex)
    - IPv6: `2001:0db8::1` (Hex)
    - Paket-Dumps in Hex
2. **Speicher-Forensik**
    
    - RAM-Dumps in Hex angezeigt
    - Adressen: `0x7FFF8A2C` (Hex)
3. **Berechtigungen (Linux/Unix)**
    
    - `rwx` = `111` (Binär) = `7` (Oktal/Dezimal)
    - `chmod 755` nutzt Oktal (Base-8)
4. **Malware-Analyse**
    
    - Maschinencode in Hex
    - Muster-Suche in Binärdateien
5. **Farbcodes (Web)**
    
    - `#FF0000` = Rot (FF=255 Rot, 00 Grün, 00 Blau)

### Übungsaufgaben mit Lösungen

**1. Dezimal 42 → Binär & Hex**

- Binär: `101010` (32+8+2)
- Hex: `0x2A` (2×16 + 10)

**2. Hex `0xFACE` → Binär**

```
F    A    C    E
1111 1010 1100 1110
→ 1111101011001110
```

**3. `1011 & 0101` = ?**

```
  1011
& 0101
------
  0001  = 1 dezimal
```

**4. `00110100 << 2` = ?**

```
00110100 (52 dezimal)
Shift 2 nach links:
11010000 (208 dezimal)
Effekt: ×4 (2²)
```

### Kernbotschaft

**Die 4 wichtigsten Erkenntnisse:**

1. **Computer verstehen nur Binär** - alles andere ist für Menschen
2. **Hex ist Binär-Kurzschrift** - 1 Hex-Ziffer = 4 Bits (auswendig lernen!)
3. **Windows-Rechner ist dein Freund** - Programmierer-Modus für alle Konvertierungen
4. **Bitweise Ops sind mächtig** - AND für Masken, OR zum Setzen, XOR für Crypto/Fehler

**Eselsbrücke:**

- **Binär** = Computer-Sprache (nur 0 und 1)
- **Hex** = Mensch-freundliche Computer-Sprache (kompakter als Binär)
- **Dezimal** = Mensch-Sprache (das, was wir täglich nutzen)

**Praktischer Tipp:** Lerne die Hex-Binär-Tabelle (0-F) auswendig - damit kannst du blitzschnell zwischen Hex und Binär wechseln!