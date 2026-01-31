# Python Lektion 7: Funktionen

## Kategorisierung der Themen

|Kategorie|Begriff|Bedeutung|
|---|---|---|
|**Verwendete Tools**|Python Interpreter|Zum interaktiven Testen von Funktionen|
||VS Code|Editor zum Schreiben von Python-Skripten mit Funktionen|
||`print()` Funktion|Ausgabe von Werten (selbst eine eingebaute Funktion)|
||`def` Keyword|Schlüsselwort zum Definieren eigener Funktionen|
||`return` Statement|Gibt Wert aus Funktion zurück|
|**Technische Fachbegriffe**|Function (Funktion)|Wiederverwendbarer, benannter Code-Block für spezifische Aufgabe|
||Function Definition (Funktionsdefinition)|Erstellen einer Funktion mit `def`|
||Function Call (Funktionsaufruf)|Ausführen einer Funktion durch Nennen ihres Namens|
||Parameter|Platzhalter-Variable in Funktionsdefinition (z.B. `def func(parameter):`)|
||Argument|Tatsächlicher Wert, der beim Aufruf übergeben wird (z.B. `func(5)`)|
||Return Value (Rückgabewert)|Wert, den Funktion mit `return` zurückgibt|
||Docstring|Dokumentations-String in dreifachen Anführungszeichen nach Funktionskopf|
||Code Block (Code-Block)|Eingerückter Code innerhalb der Funktion|
||Modularity (Modularität)|Aufteilung von Code in wiederverwendbare Einheiten|
||Reusability (Wiederverwendbarkeit)|Mehrfache Nutzung desselben Codes ohne Wiederholung|
||Abstraction (Abstraktion)|Nutzung von Funktionen ohne Kenntnis ihrer internen Arbeitsweise|
||DRY Principle|"Don't Repeat Yourself" - Vermeidung von Code-Wiederholungen|
||Scope (Gültigkeitsbereich)|Bereich, in dem Variable zugänglich ist|
||Local Scope (Lokaler Bereich)|Variablen innerhalb der Funktion (nur dort zugänglich)|
||Global Scope (Globaler Bereich)|Variablen außerhalb von Funktionen (überall zugänglich)|
||Function Header (Funktionskopf)|Erste Zeile mit `def`, Name, Parametern und `:`|
||Function Body (Funktionskörper)|Eingerückter Code, der ausgeführt wird|
||`None`|Spezieller Wert, den Funktionen ohne `return` zurückgeben|
|**Wichtige Vokabeln**|`def`|Keyword zum Starten einer Funktionsdefinition|
||`return`|Gibt Wert zurück und beendet Funktion|
||Function Name (Funktionsname)|Beschreibender Name in snake_case (z.B. `berechne_summe`)|
||Parentheses `()`|Runde Klammern für Parameter bei Definition und Argumente bei Aufruf|
||Colon `:`|Doppelpunkt am Ende des Funktionskopfes (Pflicht!)|
||Indentation (Einrückung)|4 Leerzeichen für Code innerhalb der Funktion|
||Triple Quotes `"""`|Dreifache Anführungszeichen für Docstrings|
||Calling (Aufrufen)|Ausführen einer Funktion mit `funktionsname()`|
||Passing Arguments (Argumente übergeben)|Werte beim Funktionsaufruf mitgeben|
||Zero Parameters|Funktion ohne Parameter: `def func():`|
||Multiple Parameters|Mehrere Parameter durch Kommas getrennt: `def func(a, b, c):`|
||Unreachable Code|Code nach `return` wird nie ausgeführt|
||snake_case|Namenskonvention für Funktionen: `meine_funktion`|

---

## Zusammenfassung nach dem 80/20-Prinzip

### Die 20% Kernwissen, die 80% der praktischen Anwendung abdecken:

---

## **TEIL 1: WAS SIND FUNKTIONEN?**

### **1. Das Problem ohne Funktionen**

**Ohne Funktion (repetitiv):**

```python
# Fläche Rechteck 1
laenge = 10
breite = 5
flaeche = laenge * breite
print("Fläche:", flaeche)

# Fläche Rechteck 2
laenge2 = 7
breite2 = 3
flaeche2 = laenge2 * breite2
print("Fläche:", flaeche2)

# Fläche Rechteck 3
laenge3 = 12
breite3 = 8
flaeche3 = laenge3 * breite3
print("Fläche:", flaeche3)
```

**Mit Funktion (elegant):**

```python
def berechne_flaeche(laenge, breite):
    flaeche = laenge * breite
    return flaeche

# Mehrfache Nutzung
print("Fläche:", berechne_flaeche(10, 5))
print("Fläche:", berechne_flaeche(7, 3))
print("Fläche:", berechne_flaeche(12, 8))
```

**Funktion = Wiederverwendbarer Code-Baustein**

---

## **TEIL 2: FUNKTIONEN DEFINIEREN**

### **2. Grundstruktur einer Funktion**

```python
def funktionsname(parameter1, parameter2):
    """Optionaler Docstring: Erklärt, was die Funktion macht."""
    # Code-Block (eingerückt!)
    # ... Anweisungen ...
    return ergebnis  # Optional: gibt Wert zurück
```

**Komponenten:**

1. **`def`** = Keyword zum Starten
2. **`funktionsname`** = Beschreibender Name in snake_case
3. **`(parameter1, parameter2)`** = Eingaben (können 0 oder mehr sein)
4. **`:`** = Doppelpunkt (Pflicht!)
5. **`"""Docstring"""`** = Dokumentation (optional, aber empfohlen)
6. **Eingerückter Code** = Was die Funktion tut
7. **`return`** = Gibt Wert zurück (optional)

---

### **3. Einfache Funktion ohne Parameter**

```python
def begruessung():
    """Gibt eine einfache Begrüßung aus."""
    print("Hallo, willkommen!")

# Funktion aufrufen
begruessung()
# Output: Hallo, willkommen!
```

**Wichtig:**

- Definition allein führt Code NICHT aus
- Erst der Aufruf `begruessung()` führt Code aus

---

### **4. Funktion mit Parametern**

```python
def begruessung_mit_name(name):
    """Begrüßt eine Person mit ihrem Namen."""
    print(f"Hallo, {name}!")

# Funktion mit Argument aufrufen
begruessung_mit_name("Alice")   # Output: Hallo, Alice!
begruessung_mit_name("Bob")     # Output: Hallo, Bob!
```

---

### **5. Funktion mit mehreren Parametern**

```python
def addiere(zahl1, zahl2):
    """Addiert zwei Zahlen."""
    summe = zahl1 + zahl2
    return summe

ergebnis = addiere(5, 3)
print(ergebnis)  # Output: 8

# Oder direkt ausgeben
print(addiere(10, 20))  # Output: 30
```

---

## **TEIL 3: PARAMETER VS. ARGUMENTE**

### **6. Der Unterschied**

```python
def multipliziere(x, y):  # x und y = PARAMETER (Platzhalter)
    return x * y

resultat = multipliziere(4, 7)  # 4 und 7 = ARGUMENTE (tatsächliche Werte)
```

**Merkregel:**

- **Parameter** = Platzhalter bei **Definition** (`def`)
- **Argumente** = Werte beim **Aufruf**

---

## **TEIL 4: DAS `return`-STATEMENT**

### **7. Funktion mit Rückgabewert**

```python
def quadrat(zahl):
    """Berechnet das Quadrat einer Zahl."""
    ergebnis = zahl ** 2
    return ergebnis

# Rückgabewert in Variable speichern
resultat = quadrat(5)
print(resultat)  # Output: 25

# Oder direkt verwenden
print(quadrat(3) + quadrat(4))  # Output: 9 + 16 = 25
```

---

### **8. `return` beendet Funktion sofort**

```python
def pruefe_zahl(zahl):
    """Prüft, ob Zahl positiv, negativ oder null ist."""
    if zahl > 0:
        return "Positiv"
    elif zahl < 0:
        return "Negativ"
    else:
        return "Null"
    print("Diese Zeile wird nie erreicht!")  # Unreachable Code

print(pruefe_zahl(5))    # Output: Positiv
print(pruefe_zahl(-3))   # Output: Negativ
print(pruefe_zahl(0))    # Output: Null
```

**Wichtig:** Code nach `return` wird nie ausgeführt!

---

### **9. Funktion ohne `return` gibt `None` zurück**

```python
def sage_hallo(name):
    """Gibt Begrüßung aus, gibt aber nichts zurück."""
    print(f"Hallo, {name}!")
    # Kein return Statement

resultat = sage_hallo("Max")
print(resultat)

# Output:
# Hallo, Max!
# None
```

---

### **10. Verschiedene Rückgabetypen**

```python
# Integer zurückgeben
def gib_alter():
    return 25

# String zurückgeben
def gib_name():
    return "Alice"

# Boolean zurückgeben
def ist_gerade(zahl):
    return zahl % 2 == 0

# Liste zurückgeben
def gib_zahlen():
    return [1, 2, 3, 4, 5]

print(gib_alter())        # Output: 25
print(gib_name())         # Output: Alice
print(ist_gerade(10))     # Output: True
print(gib_zahlen())       # Output: [1, 2, 3, 4, 5]
```

---

## **TEIL 5: WARUM FUNKTIONEN? (DIE 4 VORTEILE)**

### **11. Organisation**

```python
# Ohne Funktionen (unübersichtlich)
# ... 100 Zeilen Code für Aufgabe 1 ...
# ... 150 Zeilen Code für Aufgabe 2 ...
# ... 80 Zeilen Code für Aufgabe 3 ...

# Mit Funktionen (übersichtlich)
def aufgabe1():
    # ... Code ...
    pass

def aufgabe2():
    # ... Code ...
    pass

def aufgabe3():
    # ... Code ...
    pass

# Hauptprogramm
aufgabe1()
aufgabe2()
aufgabe3()
```

---

### **12. Wiederverwendbarkeit (DRY-Prinzip)**

**DRY = "Don't Repeat Yourself"**

```python
# Ohne Funktion: 3x derselbe Code
passwort1 = "geheim123"
if len(passwort1) >= 8 and any(c.isdigit() for c in passwort1):
    print("Passwort 1 ist stark")

passwort2 = "test"
if len(passwort2) >= 8 and any(c.isdigit() for c in passwort2):
    print("Passwort 2 ist stark")

# Mit Funktion: Einmal schreiben, mehrfach nutzen
def ist_passwort_stark(passwort):
    """Prüft, ob Passwort mind. 8 Zeichen und eine Ziffer hat."""
    return len(passwort) >= 8 and any(c.isdigit() for c in passwort)

if ist_passwort_stark("geheim123"):
    print("Passwort 1 ist stark")

if ist_passwort_stark("test"):
    print("Passwort 2 ist stark")
```

---

### **13. Wartbarkeit**

```python
# Änderung nötig? Nur an EINER Stelle!
def berechne_steuer(betrag):
    """Berechnet Steuer auf Betrag."""
    steuersatz = 0.19  # Änderung hier wirkt sich überall aus
    return betrag * steuersatz

print(berechne_steuer(100))
print(berechne_steuer(250))
print(berechne_steuer(500))
```

---

### **14. Abstraktion**

```python
# Man muss nicht wissen, WIE es funktioniert
# Man muss nur wissen, WAS es tut

def verschluessel_passwort(passwort):
    """Verschlüsselt ein Passwort (komplexe Logik intern)."""
    # Komplexer Verschlüsselungs-Algorithmus hier...
    # 50 Zeilen Code...
    return verschluesselt

# Nutzer muss nur wissen: Gibt verschlüsseltes Passwort zurück
sicheres_pw = verschluessel_passwort("meinPasswort123")
```

---

## **TEIL 6: SCOPE (GÜLTIGKEITSBEREICH)**

### **15. Lokaler vs. Globaler Scope**

```python
# Globale Variable (außerhalb von Funktionen)
globale_variable = "Ich bin global"

def meine_funktion():
    # Lokale Variable (innerhalb der Funktion)
    lokale_variable = "Ich bin lokal"
    
    print(lokale_variable)    # ✅ Funktioniert
    print(globale_variable)   # ✅ Funktioniert (global lesbar)

meine_funktion()

print(globale_variable)       # ✅ Funktioniert
# print(lokale_variable)      # ❌ NameError! Nicht zugänglich hier
```

**Regel:**

- **Lokale Variablen** = nur innerhalb der Funktion sichtbar
- **Globale Variablen** = überall sichtbar (aber Änderung in Funktion erfordert `global`)

---

### **16. Parameter sind lokal**

```python
def addiere(a, b):
    # a und b existieren nur innerhalb dieser Funktion
    summe = a + b  # summe ist auch lokal
    return summe

resultat = addiere(5, 3)
# print(a)      # ❌ Fehler! a existiert hier nicht
# print(b)      # ❌ Fehler! b existiert hier nicht
# print(summe)  # ❌ Fehler! summe existiert hier nicht
print(resultat)  # ✅ Funktioniert
```

---

## **PRAKTISCHE BEISPIELE**

### **17. Beispiel 1: Temperaturkonverter**

```python
def celsius_zu_fahrenheit(celsius):
    """Konvertiert Celsius in Fahrenheit."""
    fahrenheit = (celsius * 9/5) + 32
    return fahrenheit

print(f"0°C = {celsius_zu_fahrenheit(0)}°F")
print(f"25°C = {celsius_zu_fahrenheit(25)}°F")
print(f"100°C = {celsius_zu_fahrenheit(100)}°F")

# Output:
# 0°C = 32.0°F
# 25°C = 77.0°F
# 100°C = 212.0°F
```

---

### **18. Beispiel 2: Gerade oder ungerade**

```python
def ist_gerade(zahl):
    """Prüft, ob Zahl gerade ist."""
    if zahl % 2 == 0:
        return True
    else:
        return False

# Oder kürzer:
def ist_gerade(zahl):
    """Prüft, ob Zahl gerade ist."""
    return zahl % 2 == 0

print(ist_gerade(10))  # Output: True
print(ist_gerade(7))   # Output: False
```

---

### **19. Beispiel 3: Maximum von drei Zahlen**

```python
def max_von_drei(a, b, c):
    """Gibt die größte von drei Zahlen zurück."""
    if a >= b and a >= c:
        return a
    elif b >= a and b >= c:
        return b
    else:
        return c

print(max_von_drei(5, 10, 3))   # Output: 10
print(max_von_drei(15, 8, 12))  # Output: 15
```

---

### **20. Beispiel 4: Liste verarbeiten**

```python
def liste_verdoppeln(zahlen):
    """Verdoppelt alle Zahlen in einer Liste."""
    verdoppelt = []
    for zahl in zahlen:
        verdoppelt.append(zahl * 2)
    return verdoppelt

original = [1, 2, 3, 4, 5]
ergebnis = liste_verdoppeln(original)

print(f"Original: {original}")
print(f"Verdoppelt: {ergebnis}")

# Output:
# Original: [1, 2, 3, 4, 5]
# Verdoppelt: [2, 4, 6, 8, 10]
```

---

## **SCHNELLREFERENZ**

### **Funktions-Cheatsheet:**

```python
# Einfache Funktion
def sage_hallo():
    print("Hallo!")

sage_hallo()

# Mit Parameter
def gruesse(name):
    print(f"Hallo, {name}!")

gruesse("Max")

# Mit Rückgabewert
def addiere(a, b):
    return a + b

summe = addiere(5, 3)

# Mit mehreren Parametern und Rückgabewert
def berechne_flaeche(laenge, breite):
    """Berechnet Rechteckfläche."""
    return laenge * breite

flaeche = berechne_flaeche(10, 5)

# Mit Docstring
def beispiel_funktion(param):
    """
    Beschreibung der Funktion.
    
    Parameter:
        param: Beschreibung des Parameters
    
    Rückgabe:
        Beschreibung des Rückgabewerts
    """
    return param * 2
```

---

## **HÄUFIGE FEHLER UND LÖSUNGEN**

❌ **Fehler 1: Funktion definiert, aber nicht aufgerufen**

```python
def sage_hallo():
    print("Hallo!")

# Nichts passiert, weil Funktion nicht aufgerufen wurde
```

✅ **Lösung:** Funktion aufrufen

```python
def sage_hallo():
    print("Hallo!")

sage_hallo()  # Jetzt wird "Hallo!" ausgegeben
```

---

❌ **Fehler 2: Vergessene Klammern beim Aufruf**

```python
def berechne_summe(a, b):
    return a + b

print(berechne_summe)  # Gibt Funktionsobjekt aus, nicht das Ergebnis
```

✅ **Lösung:** Klammern hinzufügen

```python
print(berechne_summe(5, 3))  # Output: 8
```

---

❌ **Fehler 3: Falsche Anzahl an Argumenten**

```python
def addiere(a, b):
    return a + b

# addiere(5)         # TypeError! Fehlt ein Argument
# addiere(5, 3, 7)   # TypeError! Zu viele Argumente
```

✅ **Lösung:** Korrekte Anzahl übergeben

```python
addiere(5, 3)  # ✅ Funktioniert
```

---

❌ **Fehler 4: Rückgabewert nicht gespeichert/verwendet**

```python
def multipliziere(a, b):
    return a * b

multipliziere(5, 3)  # Ergebnis geht verloren
```

✅ **Lösung:** Rückgabewert speichern oder nutzen

```python
resultat = multipliziere(5, 3)
print(resultat)  # Output: 15
```

---

❌ **Fehler 5: Lokale Variable außerhalb nutzen**

```python
def berechne():
    summe = 10 + 5
    return summe

berechne()
# print(summe)  # NameError! summe existiert nur in Funktion
```

✅ **Lösung:** Rückgabewert verwenden

```python
resultat = berechne()
print(resultat)  # Output: 15
```

---

## **ÜBUNGSAUFGABEN**

**Aufgabe 1:** Schreibe eine Funktion `berechne_quadrat(zahl)`, die das Quadrat einer Zahl zurückgibt.

**Aufgabe 2:** Schreibe eine Funktion `ist_volljährig(alter)`, die `True` zurückgibt, wenn `alter >= 18`, sonst `False`.

**Aufgabe 3:** Schreibe eine Funktion `summiere_liste(zahlen)`, die die Summe aller Zahlen in einer Liste zurückgibt.

**Aufgabe 4:** Schreibe eine Funktion `umdrehen(text)`, die einen String rückwärts zurückgibt.

---

### **Merksätze:**

🎯 **Definition ≠ Ausführung! Erst Aufruf mit `()` führt Code aus**  
🎯 **Parameter = Platzhalter bei Definition, Argumente = Werte beim Aufruf**  
🎯 **`return` gibt Wert zurück UND beendet Funktion sofort**  
🎯 **Ohne `return` gibt Funktion `None` zurück**  
🎯 **Lokale Variablen = nur in Funktion, globale = überall sichtbar**  
🎯 **Funktionen = Wiederverwendbar, wartbar, organisiert (DRY-Prinzip!)**