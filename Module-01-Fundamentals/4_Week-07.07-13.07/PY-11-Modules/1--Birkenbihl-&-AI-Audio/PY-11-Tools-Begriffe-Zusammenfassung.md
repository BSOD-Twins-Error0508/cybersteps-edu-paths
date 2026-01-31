# Python Lektion 11: Module

## Kategorisierung der Themen

|Kategorie|Begriff|Bedeutung|
|---|---|---|
|**Verwendete Tools**|Python Interpreter|Zum Testen von Modul-Imports|
||VS Code|Editor zum Schreiben von Python-Skripten mit Modulen|
||`.py` Dateien|Python-Dateien, die als Module fungieren können|
||Standard Library|Integrierte Sammlung von Python-Modulen|
||Third-party Modules|Externe Module von der Community (nicht im Dokument behandelt)|
|**Technische Fachbegriffe**|Module|Python-Datei mit wiederverwendbarem Code (Funktionen, Klassen, Variablen)|
||Import|Einbinden eines Moduls in den aktuellen Code|
||`import` Statement|Befehl zum Importieren eines Moduls|
||Dot Notation (Punkt-Notation)|Zugriff auf Modul-Inhalte: `modul.funktion()`|
||Namespace|Bereich, in dem Namen (Variablen, Funktionen) definiert sind|
||Namespace Management|Vermeidung von Namenskonflikten durch Module|
||Standard Library|Sammlung eingebauter Python-Module für häufige Aufgaben|
||DRY Principle|"Don't Repeat Yourself" - Wiederverwendbarkeit von Code|
||Pre-fabricated Parts (Vorgefertigte Teile)|Metapher: Module als fertige Bausteine|
||Naming Conflict (Namenskonflikt)|Zwei Funktionen/Variablen mit gleichem Namen|
||Pollute Namespace|Namespace mit vielen Namen überfüllen (bei `from ... import *`)|
||Reusability (Wiederverwendbarkeit)|Code einmal schreiben, mehrfach nutzen|
||Organization (Organisation)|Code in logische Module aufteilen|
||Collaboration (Zusammenarbeit)|Mehrere Entwickler arbeiten an verschiedenen Modulen|
|**Wichtige Vokabeln**|`import module_name`|Importiert gesamtes Modul|
||`from module_name import item`|Importiert spezifisches Element aus Modul|
||`from module_name import *`|Importiert alles aus Modul (NICHT empfohlen!)|
||`module_name.item_name`|Zugriff auf Element im Modul (Dot Notation)|
||`math` Module|Standard-Modul für mathematische Funktionen|
||`random` Module|Standard-Modul für Zufallszahlen|
||`os` Module|Standard-Modul für Betriebssystem-Operationen|
||`sys` Module|Standard-Modul für system-spezifische Parameter|
||`datetime` Module|Standard-Modul für Datum und Zeit|
||`json` Module|Standard-Modul für JSON-Daten|
||`re` Module|Standard-Modul für Regular Expressions|
||`.sqrt()`|Quadratwurzel-Funktion aus `math`|
||`.pi`|Konstante Pi aus `math`|
||`.randint()`|Zufällige Ganzzahl aus `random`|
||`.now()`|Aktuelle Zeit aus `datetime`|
||`.strftime()`|Zeit formatieren aus `datetime`|
||File Extension `.py`|Python-Dateiendung|

---

## Zusammenfassung nach dem 80/20-Prinzip

### Die 20% Kernwissen, die 80% der praktischen Anwendung abdecken:

---

## **TEIL 1: WAS SIND MODULE?**

### **1. Konzept: Module als Bausteine**

**Metapher: Hausbau**

- Ohne Module: Alles von Grund auf selbst bauen
- Mit Modulen: Vorgefertigte Teile verwenden (Türen, Fenster, Wände)

**Python-Modul:**

- Modul = Python-Datei (`.py`) mit wiederverwendbarem Code
- Enthält: Funktionen, Klassen, Variablen
- Zweck: Code organisieren und wiederverwenden

```python
# Beispiel: math_utils.py (ein eigenes Modul)
def addiere(a, b):
    return a + b

def multipliziere(a, b):
    return a * b

PI = 3.14159
```

---

### **2. Warum Module verwenden? (5 Gründe)**

**1. Organisation**

```python
# Statt 1000 Zeilen in einer Datei:
# main.py (50 Zeilen)
# database.py (200 Zeilen)
# network.py (150 Zeilen)
# ui.py (300 Zeilen)
```

**2. Wiederverwendbarkeit (DRY)**

```python
# Einmal schreiben
# math_utils.py
def berechne_flaeche(radius):
    return 3.14 * radius ** 2

# In vielen Projekten nutzen
import math_utils
flaeche = math_utils.berechne_flaeche(5)
```

**3. Zusammenarbeit**

- Person A arbeitet an `database.py`
- Person B arbeitet an `ui.py`
- Keine Konflikte!

**4. Namespace Management (Namenskonflikte vermeiden)**

```python
# modul_a.py
def calculate():
    return 10

# modul_b.py
def calculate():
    return 20

# main.py
import modul_a
import modul_b

print(modul_a.calculate())  # 10
print(modul_b.calculate())  # 20
# Kein Konflikt!
```

**5. Bestehenden Code nutzen**

- Python Standard Library: 200+ Module bereits vorhanden
- Keine Neuentwicklung nötig!

---

## **TEIL 2: MODULE IMPORTIEREN**

### **3. Methode 1: `import module_name`**

**Syntax:**

```python
import module_name
```

**Verwendung mit Dot Notation:**

```python
module_name.funktion()
module_name.variable
```

**Praktisches Beispiel: `math` Modul**

```python
import math

# Quadratwurzel berechnen
zahl = 16
wurzel = math.sqrt(zahl)
print(f"Wurzel von {zahl} = {wurzel}")  # Output: Wurzel von 16 = 4.0

# Pi verwenden
radius = 5
flaeche = math.pi * (radius ** 2)
print(f"Kreisfläche: {flaeche}")  # Output: Kreisfläche: 78.53981633974483

# Weitere nützliche Funktionen
print(math.ceil(4.3))   # Output: 5 (aufrunden)
print(math.floor(4.7))  # Output: 4 (abrunden)
print(math.pow(2, 3))   # Output: 8.0 (2^3)
```

**Vorteile:**

- ✅ Klar erkennbar, woher Funktionen kommen
- ✅ Keine Namenskonflikte
- ✅ Gute Lesbarkeit

---

### **4. Methode 2: `from module_name import item`**

**Syntax:**

```python
from module_name import funktion1, funktion2
```

**Verwendung direkt ohne Modulname:**

```python
funktion1()  # Ohne "module_name." Präfix
```

**Praktisches Beispiel: `random` Modul**

```python
from random import randint, choice

# Direkte Verwendung ohne "random." Präfix
zufallszahl = randint(1, 10)
print(f"Zufallszahl: {zufallszahl}")

auswahl = choice(['Apfel', 'Banane', 'Kirsche'])
print(f"Zufällige Frucht: {auswahl}")

# ❌ Andere Funktionen aus random sind nicht verfügbar
# uniform(1, 10)  # NameError! Nicht importiert
```

**Vorteile:**

- ✅ Kürzerer Code (kein Modulname nötig)
- ✅ Gut für häufig verwendete Funktionen

**Nachteile:**

- ❌ Unklarer, woher Funktion kommt
- ❌ Potenzielle Namenskonflikte

---

### **5. ⚠️ Methode 3: `from module_name import *` (NICHT EMPFOHLEN!)**

**Syntax:**

```python
from math import *
```

**Was passiert:** Alle Funktionen und Variablen aus `math` werden importiert

```python
from math import *

# Alle Funktionen direkt nutzbar
print(sqrt(16))  # 4.0
print(pi)        # 3.141592653589793
print(sin(0))    # 0.0
```

**⚠️ Warum NICHT empfohlen?**

```python
# Eigene Variable
pi = 3.14

# Import überschreibt eigene Variable!
from math import *

print(pi)  # 3.141592653589793 (nicht mehr 3.14!)
```

**Probleme:**

- ❌ Namespace-Verschmutzung
- ❌ Unklare Herkunft von Funktionen
- ❌ Überschreibt versehentlich eigene Variablen
- ❌ Schwer zu debuggen

**Regel:** Verwende `import *` niemals in Produktions-Code!

---

## **TEIL 3: PYTHON STANDARD LIBRARY**

### **6. Die wichtigsten Standard-Module**

**Python = "Batteries Included"** (Batterien inklusive) → Viele nützliche Module bereits eingebaut, keine Installation nötig!

---

### **7. Modul 1: `math` – Mathematische Funktionen**

```python
import math

# Grundlegende Funktionen
print(math.sqrt(25))        # 5.0 (Quadratwurzel)
print(math.pow(2, 3))       # 8.0 (Potenz)
print(math.factorial(5))    # 120 (Fakultät: 5!)

# Runden
print(math.ceil(4.3))       # 5 (aufrunden)
print(math.floor(4.7))      # 4 (abrunden)

# Trigonometrie
print(math.sin(math.pi/2))  # 1.0
print(math.cos(0))          # 1.0

# Konstanten
print(math.pi)              # 3.141592653589793
print(math.e)               # 2.718281828459045
```

**Verwendung:** Wissenschaftliche Berechnungen, Geometrie, Statistik

---

### **8. Modul 2: `random` – Zufallszahlen**

```python
import random

# Zufällige Ganzzahl
wurf = random.randint(1, 6)
print(f"Würfel: {wurf}")

# Zufälliges Element aus Liste
farben = ['rot', 'grün', 'blau', 'gelb']
farbe = random.choice(farben)
print(f"Zufällige Farbe: {farbe}")

# Zufällige Gleitkommazahl
zufall = random.random()  # 0.0 bis 1.0
print(f"Zufallszahl: {zufall}")

# Liste mischen
karten = ['Ass', 'König', 'Dame', 'Bube']
random.shuffle(karten)
print(f"Gemischt: {karten}")

# Mehrere zufällige Elemente
gewinner = random.sample(farben, 2)
print(f"2 Gewinner: {gewinner}")
```

**Verwendung:** Spiele, Simulationen, Stichproben, Tests

---

### **9. Modul 3: `datetime` – Datum und Zeit**

```python
import datetime

# Aktuelles Datum und Zeit
jetzt = datetime.datetime.now()
print(f"Jetzt: {jetzt}")
# Output: 2024-01-15 14:30:45.123456

# Nur Datum
heute = datetime.date.today()
print(f"Heute: {heute}")
# Output: 2024-01-15

# Formatierte Ausgabe
formatiert = jetzt.strftime("%d.%m.%Y %H:%M:%S")
print(f"Formatiert: {formatiert}")
# Output: 15.01.2024 14:30:45

# Bestimmtes Datum erstellen
geburtstag = datetime.date(1990, 5, 15)
print(f"Geburtstag: {geburtstag}")

# Zeitdifferenz berechnen
alter_tage = (heute - geburtstag).days
alter_jahre = alter_tage // 365
print(f"Alter: ca. {alter_jahre} Jahre")
```

**Verwendung:** Zeitstempel, Logs, Terminplanung, Altersberechnung

---

### **10. Modul 4: `os` – Betriebssystem-Interaktion**

```python
import os

# Aktuelles Arbeitsverzeichnis
verzeichnis = os.getcwd()
print(f"Aktuelles Verzeichnis: {verzeichnis}")
# Windows: C:\Users\Username\Documents

# Dateien im Verzeichnis auflisten
dateien = os.listdir('.')
print(f"Dateien: {dateien}")

# Prüfen, ob Datei existiert
if os.path.exists('test.txt'):
    print("Datei existiert")
else:
    print("Datei existiert nicht")

# Verzeichnis erstellen
# os.mkdir('neuer_ordner')

# Pfad zusammenbauen (plattformunabhängig!)
pfad = os.path.join('ordner', 'datei.txt')
print(f"Pfad: {pfad}")
# Windows: ordner\datei.txt
# Linux/Mac: ordner/datei.txt
```

**Verwendung:** Datei-/Ordnerverwaltung, Pfade, Umgebungsvariablen

---

### **11. Modul 5: `sys` – System-Parameter**

```python
import sys

# Python-Version
print(f"Python-Version: {sys.version}")

# Plattform (Betriebssystem)
print(f"Plattform: {sys.platform}")
# Windows: 'win32'
# Linux: 'linux'
# Mac: 'darwin'

# Kommandozeilen-Argumente
# Wenn Skript aufgerufen: python script.py arg1 arg2
print(f"Argumente: {sys.argv}")

# Skript beenden
# sys.exit(0)
```

**Verwendung:** System-Informationen, Kommandozeilen-Tools

---

### **12. Weitere wichtige Module (Kurzübersicht)**

|Modul|Zweck|Beispiel|
|---|---|---|
|`json`|JSON-Daten verarbeiten|`json.loads('{"name": "Alice"}')`|
|`re`|Regular Expressions|`re.search(r'\d+', 'abc123')`|
|`time`|Zeit-Funktionen|`time.sleep(1)` (1 Sekunde warten)|
|`csv`|CSV-Dateien lesen/schreiben|`csv.reader(file)`|
|`pathlib`|Moderne Pfadverwaltung|`Path('datei.txt').exists()`|

**Vollständige Liste:** https://docs.python.org/3/library/

---

## **TEIL 4: PRAKTISCHE BEISPIELE**

### **13. Beispiel 1: Würfelspiel**

```python
import random

def wuerfeln():
    """Würfelt einen 6-seitigen Würfel."""
    return random.randint(1, 6)

# Spiel
print("Würfelspiel!")
spieler1 = wuerfeln()
spieler2 = wuerfeln()

print(f"Spieler 1: {spieler1}")
print(f"Spieler 2: {spieler2}")

if spieler1 > spieler2:
    print("Spieler 1 gewinnt!")
elif spieler2 > spieler1:
    print("Spieler 2 gewinnt!")
else:
    print("Unentschieden!")
```

---

### **14. Beispiel 2: Kreisberechnung**

```python
import math

def berechne_kreis(radius):
    """Berechnet Umfang und Fläche eines Kreises."""
    umfang = 2 * math.pi * radius
    flaeche = math.pi * radius ** 2
    return umfang, flaeche

# Verwendung
r = 5
u, f = berechne_kreis(r)
print(f"Radius: {r}")
print(f"Umfang: {u:.2f}")
print(f"Fläche: {f:.2f}")

# Output:
# Radius: 5
# Umfang: 31.42
# Fläche: 78.54
```

---

### **15. Beispiel 3: Datums-Log**

```python
import datetime

def log_eintrag(nachricht):
    """Erstellt Log-Eintrag mit Zeitstempel."""
    jetzt = datetime.datetime.now()
    zeitstempel = jetzt.strftime("%Y-%m-%d %H:%M:%S")
    return f"[{zeitstempel}] {nachricht}"

# Verwendung
print(log_eintrag("Programm gestartet"))
print(log_eintrag("Benutzer angemeldet"))
print(log_eintrag("Datei gespeichert"))

# Output:
# [2024-01-15 14:30:00] Programm gestartet
# [2024-01-15 14:30:01] Benutzer angemeldet
# [2024-01-15 14:30:02] Datei gespeichert
```

---

## **SCHNELLREFERENZ**

### **Import-Cheatsheet:**

```python
# Ganzes Modul importieren
import math
ergebnis = math.sqrt(16)

# Spezifische Elemente importieren
from random import randint, choice
zahl = randint(1, 10)

# Modul mit Alias
import datetime as dt
jetzt = dt.datetime.now()

# Mehrere Module
import math, random, os
```

### **Wichtige Standard-Module:**

```python
import math      # Mathematik
import random    # Zufallszahlen
import datetime  # Datum/Zeit
import os        # Betriebssystem
import sys       # System-Parameter
import json      # JSON-Daten
import time      # Zeit-Funktionen
```

---

## **HÄUFIGE FEHLER UND LÖSUNGEN**

### **16. Fehler 1: ModuleNotFoundError**

```python
# ❌ Problem
import nicht_existierendes_modul
# ModuleNotFoundError: No module named 'nicht_existierendes_modul'
```

**Ursachen:**

- Modul nicht installiert (bei Third-party)
- Tippfehler im Modulnamen
- Falsche Python-Umgebung

**✅ Lösung:**

```python
# Prüfe Schreibweise
import math  # ✅ Richtig (klein geschrieben)

# Bei Third-party: Installation nötig
# pip install numpy (im Terminal)
```

---

### **17. Fehler 2: Eigenes Modul überschattet Standard-Modul**

```python
# ❌ Problem: Datei heißt "random.py"
# Versuche zu importieren:
import random
# Importiert eigene Datei statt Standard-Modul!
```

**✅ Lösung:** Benenne eigene Dateien NICHT wie Standard-Module

---

### **18. Fehler 3: Dot Notation vergessen**

```python
import math

# ❌ Falsch
# print(sqrt(16))  # NameError: name 'sqrt' is not defined

# ✅ Richtig
print(math.sqrt(16))  # 4.0
```

---

## **VERGLEICH: IMPORT-METHODEN**

### **19. Welche Methode wann?**

|Methode|Wann verwenden|Beispiel|
|---|---|---|
|`import module`|Standard, immer gut|`import math`|
|`from module import item`|1-3 spezifische Items|`from math import sqrt, pi`|
|`from module import *`|**NIEMALS!**|❌|
|`import module as alias`|Lange Modulnamen|`import datetime as dt`|

---

## **EIGENE MODULE ERSTELLEN (VORSCHAU)**

### **20. Einfaches eigenes Modul**

**Datei: `mein_modul.py`**

```python
def begruessung(name):
    """Begrüßt eine Person."""
    return f"Hallo, {name}!"

def addiere(a, b):
    """Addiert zwei Zahlen."""
    return a + b

PI = 3.14159
```

**Datei: `main.py`**

```python
import mein_modul

nachricht = mein_modul.begruessung("Alice")
print(nachricht)  # Output: Hallo, Alice!

summe = mein_modul.addiere(5, 3)
print(summe)  # Output: 8

print(mein_modul.PI)  # Output: 3.14159
```

---

## **ÜBUNGSAUFGABEN**

**Aufgabe 1:** Schreibe ein Programm mit `random`, das 10 zufällige Zahlen zwischen 1 und 100 generiert und ausgibt.

**Aufgabe 2:** Verwende `datetime`, um zu berechnen, wie viele Tage bis zu deinem nächsten Geburtstag sind.

**Aufgabe 3:** Erstelle mit `math` eine Funktion, die den Abstand zwischen zwei Punkten (x1,y1) und (x2,y2) berechnet.

**Aufgabe 4:** Verwende `os`, um alle `.txt` Dateien im aktuellen Verzeichnis aufzulisten.

---

### **Merksätze:**

🎯 **Modul = Python-Datei mit wiederverwendbarem Code**  
🎯 **`import module` → Zugriff mit `module.funktion()`**  
🎯 **`from module import item` → Direkter Zugriff auf `item()`**  
🎯 **`from module import *` → NIEMALS verwenden!**  
🎯 **Standard Library = 200+ Module, keine Installation nötig**  
🎯 **Wichtigste Module: `math`, `random`, `datetime`, `os`, `sys`**  
🎯 **Module = DRY-Prinzip: Code einmal schreiben, mehrfach nutzen**