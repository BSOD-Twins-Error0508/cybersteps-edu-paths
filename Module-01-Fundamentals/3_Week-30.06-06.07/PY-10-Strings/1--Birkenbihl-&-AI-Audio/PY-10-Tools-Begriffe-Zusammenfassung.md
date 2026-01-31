# Python Lektion 10: Strings (Zeichenketten)

## Kategorisierung der Themen

|Kategorie|Begriff|Bedeutung|
|---|---|---|
|**Verwendete Tools**|Python Interpreter|Zum interaktiven Testen von String-Operationen|
||VS Code|Editor zum Schreiben von Python-Skripten mit Strings|
||`print()` Funktion|Ausgabe von Strings und String-Operationen|
||`len()` Funktion|Gibt Länge (Anzahl Zeichen) eines Strings zurück|
||f-Strings|Moderne Methode zur String-Formatierung (ab Python 3.6)|
|**Technische Fachbegriffe**|String (Zeichenkette)|Geordnete Sequenz von Zeichen|
||Character (Zeichen)|Einzelnes Element eines Strings (Buchstabe, Zahl, Symbol, Leerzeichen)|
||Index (Indexierung)|Position eines Zeichens im String (startet bei 0)|
||Zero-based Indexing|Erstes Zeichen hat Index 0, nicht 1|
||Negative Indexing|Zugriff von hinten: `-1` = letztes Zeichen|
||Slicing (Schneiden)|Extrahieren eines Teilstrings aus String|
||Substring (Teilstring)|Teil eines Strings|
||Concatenation (Verkettung)|Strings mit `+` verbinden|
||Repetition (Wiederholung)|String mit `*` vervielfachen|
||Method (Methode)|Funktion, die zu String-Objekt gehört (mit `.` aufgerufen)|
||Immutable (Unveränderlich)|Strings können nicht geändert werden, Methoden geben neue Strings zurück|
||Delimiter (Trennzeichen)|Zeichen zum Aufteilen von Strings (z.B. bei `.split()`)|
||Whitespace (Leerzeichen)|Leerzeichen, Tabs, Zeilenumbrüche|
||Escape Character (Escape-Zeichen)|Backslash `\` für Sonderzeichen (z.B. `\n`, `\t`)|
||String Formatting (String-Formatierung)|Einbetten von Variablen in Strings|
||String Literal|String-Wert direkt im Code (z.B. `"Hallo"`)|
||Multi-line String|String über mehrere Zeilen (mit `"""` oder `'''`)|
||IndexError|Fehler bei Zugriff auf nicht existierenden Index|
||ValueError|Fehler bei `.index()`, wenn Substring nicht gefunden|
|**Wichtige Vokabeln**|`'...'` Single Quotes|Einfache Anführungszeichen für Strings|
||`"..."` Double Quotes|Doppelte Anführungszeichen für Strings|
||`"""..."""` Triple Quotes|Dreifache Anführungszeichen für mehrzeilige Strings|
||`[index]`|Zugriff auf Zeichen an Position|
||`[start:stop:step]`|Slicing-Syntax zum Extrahieren von Teilstrings|
||`+` Operator|Verkettung von Strings|
||`*` Operator|Wiederholung von Strings|
||`.upper()`|Konvertiert zu Großbuchstaben|
||`.lower()`|Konvertiert zu Kleinbuchstaben|
||`.capitalize()`|Erster Buchstabe groß|
||`.title()`|Erster Buchstabe jedes Wortes groß|
||`.find(substring)`|Gibt Index des ersten Vorkommens zurück (-1 wenn nicht gefunden)|
||`.index(substring)`|Wie `.find()`, aber ValueError bei nicht gefunden|
||`.replace(alt, neu)`|Ersetzt Teilstring durch anderen|
||`.split(delimiter)`|Teilt String in Liste auf|
||`.strip()`|Entfernt führende/nachfolgende Leerzeichen|
||`.lstrip()`|Entfernt führende Leerzeichen (links)|
||`.rstrip()`|Entfernt nachfolgende Leerzeichen (rechts)|
||`.startswith(prefix)`|Prüft, ob String mit prefix beginnt|
||`.endswith(suffix)`|Prüft, ob String mit suffix endet|
||`.isdigit()`|Prüft, ob alle Zeichen Ziffern sind|
||`.isalpha()`|Prüft, ob alle Zeichen Buchstaben sind|
||`.isalnum()`|Prüft, ob alle Zeichen alphanumerisch sind|
||`f"..."`|f-String für Formatierung mit Variablen in `{}`|
||`.format()`|Ältere Formatierungsmethode|
||`\n`|Escape-Zeichen für Zeilenumbruch|
||`\t`|Escape-Zeichen für Tab|
||`\\`|Escape-Zeichen für Backslash|
||`\'`|Escape-Zeichen für einfaches Anführungszeichen|
||`\"`|Escape-Zeichen für doppeltes Anführungszeichen|

---

## Zusammenfassung nach dem 80/20-Prinzip

### Die 20% Kernwissen, die 80% der praktischen Anwendung abdecken:

---

## **TEIL 1: WAS SIND STRINGS?**

### **1. Definition: String**

**String = Geordnete Sequenz von Zeichen**

```python
# Verschiedene Arten, Strings zu erstellen
nachricht1 = 'Hallo Welt!'
nachricht2 = "Dies ist auch ein String."
zahl_als_string = "12345"
leer = ""

print(nachricht1)  # Output: Hallo Welt!
```

**Zeichen können sein:**

- Buchstaben: `a-z`, `A-Z`
- Zahlen: `0-9`
- Symbole: `!`, `@`, `#`, `$`, etc.
- Leerzeichen: Leerzeichen, Tabs, Zeilenumbrüche

---

### **2. Single vs. Double vs. Triple Quotes**

```python
# Single Quotes
text1 = 'Hallo'

# Double Quotes
text2 = "Hallo"

# Triple Quotes (mehrzeilig)
text3 = """Dies ist
ein mehrzeiliger
String."""

print(text3)
# Output:
# Dies ist
# ein mehrzeiliger
# String.
```

**Wann welche verwenden?**

- **Single/Double:** Bei kurzen, einzeiligen Strings (austauschbar)
- **Triple:** Bei mehrzeiligen Strings oder Docstrings

---

## **TEIL 2: INDEXIERUNG – EINZELNE ZEICHEN ZUGREIFEN**

### **3. Positiver Index (von vorne)**

```python
text = "Python"
#       012345  (Indizes)

print(text[0])  # Output: P
print(text[1])  # Output: y
print(text[2])  # Output: t
print(text[5])  # Output: n
```

**⚠️ Wichtig:** Python startet bei 0, nicht bei 1!

---

### **4. Negativer Index (von hinten)**

```python
text = "Python"
#       -6-5-4-3-2-1  (negative Indizes)

print(text[-1])  # Output: n (letztes Zeichen)
print(text[-2])  # Output: o (vorletztes Zeichen)
print(text[-6])  # Output: P (erstes Zeichen)
```

**Praktischer Nutzen:** Letztes Zeichen ohne Länge kennen: `text[-1]`

---

### **5. IndexError vermeiden**

```python
text = "Hallo"

# ❌ Fehler
# print(text[10])  # IndexError: string index out of range

# ✅ Sicherer Zugriff
if 10 < len(text):
    print(text[10])
else:
    print("Index existiert nicht")
```

---

## **TEIL 3: SLICING – TEILSTRINGS EXTRAHIEREN**

### **6. Slicing-Syntax: `[start:stop:step]`**

```python
text = "Cybersecurity"
#       0123456789...

# [start:stop] - von start bis stop (exklusiv)
print(text[0:5])    # Output: Cyber
print(text[5:13])   # Output: security

# [:stop] - vom Anfang bis stop
print(text[:5])     # Output: Cyber

# [start:] - von start bis Ende
print(text[5:])     # Output: security

# [:] - kompletter String
print(text[:])      # Output: Cybersecurity
```

**Wichtig:** `stop` ist **exklusiv** (wird nicht mitgenommen)

---

### **7. Slicing mit Step**

```python
text = "Python"

# Jedes zweite Zeichen
print(text[::2])    # Output: Pto

# Jeden dritten Buchstaben
print(text[::3])    # Output: Ph

# String umkehren (negativer Step!)
print(text[::-1])   # Output: nohtyP
```

**Trick:** `[::-1]` kehrt String um!

---

### **8. Praktische Slicing-Beispiele**

```python
email = "benutzer@example.com"

# Alles vor @
benutzername = email[:email.find('@')]
print(benutzername)  # Output: benutzer

# Alles nach @
domain = email[email.find('@')+1:]
print(domain)  # Output: example.com

# Letzte 4 Zeichen
dateiendung = "dokument.txt"
endung = dateiendung[-4:]
print(endung)  # Output: .txt
```

---

## **TEIL 4: STRING-OPERATIONEN**

### **9. Verkettung mit `+` und Wiederholung mit `*`**

```python
# Verkettung (Concatenation)
vorname = "Max"
nachname = "Mustermann"
vollername = vorname + " " + nachname
print(vollername)  # Output: Max Mustermann

# Wiederholung (Repetition)
trennlinie = "-" * 20
print(trennlinie)  # Output: --------------------

gruss = "Hallo! " * 3
print(gruss)  # Output: Hallo! Hallo! Hallo!
```

---

### **10. Länge mit `len()`**

```python
text = "Python"
laenge = len(text)
print(laenge)  # Output: 6

# Praktisch für Validierung
passwort = "geheim123"
if len(passwort) >= 8:
    print("Passwort ist lang genug")
else:
    print("Passwort zu kurz")
```

---

## **TEIL 5: WICHTIGE STRING-METHODEN**

### **11. Groß-/Kleinschreibung ändern**

```python
text = "PyThOn PrOgRaMmInG"

print(text.upper())      # Output: PYTHON PROGRAMMING
print(text.lower())      # Output: python programming
print(text.capitalize()) # Output: Python programming
print(text.title())      # Output: Python Programming
```

**Verwendung:**

- `.upper()` / `.lower()` → Vergleiche (case-insensitive)
- `.title()` → Überschriften formatieren
- `.capitalize()` → Satzanfang

---

### **12. Substrings finden mit `.find()` und `.index()`**

```python
text = "Der schnelle braune Fuchs springt."

# .find() - gibt -1 zurück wenn nicht gefunden
position1 = text.find("Fuchs")
print(position1)  # Output: 20

position2 = text.find("Katze")
print(position2)  # Output: -1

# .index() - ValueError wenn nicht gefunden
position3 = text.index("Fuchs")
print(position3)  # Output: 20

# position4 = text.index("Katze")  # ValueError!
```

**Unterschied:**

- `.find()` → Gibt `-1` zurück (sicherer)
- `.index()` → Wirft ValueError (nur wenn man sicher ist)

---

### **13. Substring ersetzen mit `.replace()`**

```python
text = "Ich mag Katzen."
neuer_text = text.replace("Katzen", "Hunde")
print(neuer_text)  # Output: Ich mag Hunde.

# Original bleibt unverändert (Strings sind immutable!)
print(text)  # Output: Ich mag Katzen.

# Mehrfaches Ersetzen
zahlen = "1-2-3-4-5"
ohne_bindestriche = zahlen.replace("-", "")
print(ohne_bindestriche)  # Output: 12345
```

**Wichtig:** Strings sind **immutable** → Methoden geben neue Strings zurück!

---

### **14. String aufteilen mit `.split()`**

```python
# Split bei Leerzeichen (Standard)
satz = "Dies ist ein Satz"
woerter = satz.split()
print(woerter)  # Output: ['Dies', 'ist', 'ein', 'Satz']

# Split bei spezifischem Trennzeichen
csv_zeile = "Name,Alter,Stadt"
spalten = csv_zeile.split(',')
print(spalten)  # Output: ['Name', 'Alter', 'Stadt']

# Log-Datei parsen
log = "ERROR:2024-01-15:Datei nicht gefunden"
teile = log.split(':')
print(teile)  # Output: ['ERROR', '2024-01-15', 'Datei nicht gefunden']
level = teile[0]
datum = teile[1]
nachricht = teile[2]
```

**Praktisch:** CSV-Dateien, Logs, Pfade parsen

---

### **15. Leerzeichen entfernen mit `.strip()`**

```python
# .strip() - entfernt führende UND nachfolgende Leerzeichen
username = "  admin  \n"
sauber = username.strip()
print(f"'{sauber}'")  # Output: 'admin'

# .lstrip() - nur führende Leerzeichen (links)
text = "  Hallo"
print(f"'{text.lstrip()}'")  # Output: 'Hallo'

# .rstrip() - nur nachfolgende Leerzeichen (rechts)
text2 = "Hallo  "
print(f"'{text2.rstrip()}'")  # Output: 'Hallo'
```

**Verwendung:** Benutzereingaben bereinigen, Datei-Zeilen säubern

---

### **16. String-Inhalte prüfen**

```python
# .startswith() - beginnt mit?
dateiname = "bericht.txt"
print(dateiname.startswith("bericht"))  # Output: True
print(dateiname.startswith("daten"))    # Output: False

# .endswith() - endet mit?
print(dateiname.endswith(".txt"))    # Output: True
print(dateiname.endswith(".pdf"))    # Output: False

# .isdigit() - nur Ziffern?
pin = "1234"
print(pin.isdigit())  # Output: True
pin2 = "12a4"
print(pin2.isdigit())  # Output: False

# .isalpha() - nur Buchstaben?
name = "Alice"
print(name.isalpha())  # Output: True
name2 = "Alice123"
print(name2.isalpha())  # Output: False

# .isalnum() - Buchstaben ODER Zahlen?
benutzername = "User123"
print(benutzername.isalnum())  # Output: True
```

**Praktisch:** Validierung von Eingaben

---

## **TEIL 6: STRING-FORMATIERUNG**

### **17. f-Strings (EMPFOHLEN – ab Python 3.6)**

```python
name = "Alice"
alter = 30

# Variablen einbetten
print(f"Benutzer {name} ist {alter} Jahre alt.")
# Output: Benutzer Alice ist 30 Jahre alt.

# Ausdrücke in {}
print(f"In 5 Jahren ist {name} {alter + 5} Jahre alt.")
# Output: In 5 Jahren ist Alice 35 Jahre alt.

# Formatierung
preis = 19.99
print(f"Preis: {preis:.2f} EUR")
# Output: Preis: 19.99 EUR

# Mehrere Variablen
stadt = "Berlin"
land = "Deutschland"
print(f"{name} lebt in {stadt}, {land}.")
# Output: Alice lebt in Berlin, Deutschland.
```

**Vorteile:** Lesbar, präzise, modern

---

### **18. Ältere Formatierungsmethoden (zum Verständnis)**

```python
name = "Bob"
alter = 25

# .format() Methode
print("Benutzer {} ist {} Jahre alt.".format(name, alter))
# Output: Benutzer Bob ist 25 Jahre alt.

# %-Formatierung (veraltet, aber in altem Code)
print("Benutzer %s ist %d Jahre alt." % (name, alter))
# Output: Benutzer Bob ist 25 Jahre alt.
```

**Empfehlung:** Verwende f-Strings für neuen Code!

---

## **TEIL 7: ESCAPE-ZEICHEN**

### **19. Sonderzeichen mit Backslash `\`**

```python
# \n - Zeilenumbruch
print("Zeile 1\nZeile 2")
# Output:
# Zeile 1
# Zeile 2

# \t - Tab
print("Name:\tAlice")
# Output: Name:    Alice

# \\ - Backslash
print("Pfad: C:\\Benutzer\\Admin")
# Output: Pfad: C:\Benutzer\Admin

# \' - Einfaches Anführungszeichen
print('It\'s a nice day.')
# Output: It's a nice day.

# \" - Doppeltes Anführungszeichen
print("Er sagte \"Hallo\".")
# Output: Er sagte "Hallo".
```

---

### **20. Windows-Pfade korrekt darstellen**

```python
# ❌ Falsch (wird als Escape-Sequenzen interpretiert)
# pfad = "C:\Users\Admin"  # SyntaxError oder falsche Ausgabe

# ✅ Richtig: Doppelte Backslashes
pfad1 = "C:\\Users\\Admin"
print(pfad1)  # Output: C:\Users\Admin

# ✅ Oder: Raw String (r vor String)
pfad2 = r"C:\Users\Admin"
print(pfad2)  # Output: C:\Users\Admin
```

**Windows 11:** Immer `\\` oder `r"..."` für Pfade verwenden!

---

## **PRAKTISCHE BEISPIELE**

### **21. Beispiel 1: E-Mail-Validierung**

```python
def ist_email_gueltig(email):
    """Einfache E-Mail-Validierung."""
    # Bereinigen
    email = email.strip().lower()
    
    # Enthält @?
    if '@' not in email:
        return False
    
    # Mindestens ein Punkt nach @?
    at_position = email.find('@')
    nach_at = email[at_position+1:]
    if '.' not in nach_at:
        return False
    
    return True

print(ist_email_gueltig("user@example.com"))   # True
print(ist_email_gueltig("invalid-email"))      # False
print(ist_email_gueltig("  TEST@SITE.DE  "))  # True
```

---

### **22. Beispiel 2: Passwort-Stärke prüfen**

```python
def pruefe_passwort(passwort):
    """Prüft Passwort-Stärke."""
    if len(passwort) < 8:
        return "Zu kurz (min. 8 Zeichen)"
    
    hat_ziffer = any(char.isdigit() for char in passwort)
    hat_buchstabe = any(char.isalpha() for char in passwort)
    
    if not hat_ziffer:
        return "Keine Ziffer enthalten"
    
    if not hat_buchstabe:
        return "Kein Buchstabe enthalten"
    
    return "Stark"

print(pruefe_passwort("geheim"))      # Zu kurz
print(pruefe_passwort("abcdefgh"))    # Keine Ziffer
print(pruefe_passwort("12345678"))    # Kein Buchstabe
print(pruefe_passwort("geheim123"))   # Stark
```

---

### **23. Beispiel 3: Log-Datei parsen**

```python
log_zeilen = [
    "2024-01-15 10:30:00 INFO Benutzer angemeldet",
    "2024-01-15 10:35:12 ERROR Datei nicht gefunden",
    "2024-01-15 10:40:55 WARNING Speicher fast voll"
]

for zeile in log_zeilen:
    teile = zeile.split(' ', 3)  # Max. 4 Teile
    datum = teile[0]
    zeit = teile[1]
    level = teile[2]
    nachricht = teile[3]
    
    print(f"[{level}] {datum} {zeit}: {nachricht}")

# Output:
# [INFO] 2024-01-15 10:30:00: Benutzer angemeldet
# [ERROR] 2024-01-15 10:35:12: Datei nicht gefunden
# [WARNING] 2024-01-15 10:40:55: Speicher fast voll
```

---

## **SCHNELLREFERENZ**

### **String-Cheatsheet:**

```python
# Erstellen
s = "Hallo"
s = 'Hallo'
s = """Mehrzeilig"""

# Zugriff
s[0]        # Erstes Zeichen
s[-1]       # Letztes Zeichen
s[1:4]      # Slice von Index 1 bis 3
s[::-1]     # String umkehren

# Operationen
s1 + s2     # Verketten
s * 3       # Wiederholen
len(s)      # Länge

# Wichtige Methoden
s.upper()              # GROSSBUCHSTABEN
s.lower()              # kleinbuchstaben
s.strip()              # Leerzeichen entfernen
s.split(',')           # Bei ',' aufteilen
s.replace('alt', 'neu') # Ersetzen
s.find('sub')          # Substring finden
s.startswith('pre')    # Beginnt mit?
s.endswith('suf')      # Endet mit?
s.isdigit()            # Nur Ziffern?

# Formatierung
f"{var}"               # f-String (empfohlen)

# Escape-Zeichen
\n  # Zeilenumbruch
\t  # Tab
\\  # Backslash
```

---

## **HÄUFIGE FEHLER UND LÖSUNGEN**

### **24. Fehler 1: Strings sind immutable**

```python
# ❌ Funktioniert nicht
text = "Hallo"
# text[0] = "h"  # TypeError: 'str' object does not support item assignment

# ✅ Lösung: Neuen String erstellen
text = "h" + text[1:]
print(text)  # Output: hallo
```

---

### **25. Fehler 2: IndexError bei Slicing**

```python
text = "Python"

# ❌ IndexError
# print(text[10])  # IndexError

# ✅ Slicing gibt keinen Fehler
print(text[10:20])  # Output: '' (leerer String)
```

---

### **26. Fehler 3: `.find()` vs. `.index()` verwechseln**

```python
text = "Hallo Welt"

# .find() - sicher
pos1 = text.find("xyz")
print(pos1)  # Output: -1

# .index() - kann crashen
# pos2 = text.index("xyz")  # ValueError!

# ✅ Besser: Erst prüfen
if "xyz" in text:
    pos = text.index("xyz")
else:
    print("Nicht gefunden")
```

---

## **ÜBUNGSAUFGABEN**

**Aufgabe 1:** Schreibe eine Funktion, die einen String umkehrt (ohne `[::-1]`).

**Aufgabe 2:** Zähle, wie oft ein bestimmter Buchstabe in einem String vorkommt.

**Aufgabe 3:** Extrahiere Benutzername und Domain aus E-Mail-Adresse.

**Aufgabe 4:** Formatiere Telefonnummer: `"1234567890"` → `"(123) 456-7890"`

---

### **Merksätze:**

🎯 **String = unveränderlich! Methoden geben neue Strings zurück**  
🎯 **Indexierung: `[0]` = erster, `[-1]` = letzter Buchstabe**  
🎯 **Slicing: `[start:stop:step]`, stop ist exklusiv!**  
🎯 **`[::-1]` kehrt String um (negativer Step)**  
🎯 **f-Strings = beste Formatierung: `f"{variable}"`**  
🎯 **`.strip()` = Leerzeichen entfernen (sehr häufig bei Eingaben!)**  
🎯 **`.split()` = String in Liste aufteilen (Parsing!)**  
🎯 **Windows-Pfade: `"C:\\Users"` oder `r"C:\Users"`**