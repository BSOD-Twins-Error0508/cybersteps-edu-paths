# Python Lektion 4: Bedingungen und Entscheidungen

## Kategorisierung der Themen

|Kategorie|Begriff|Bedeutung|
|---|---|---|
|**Verwendete Tools**|Python Interpreter|Interaktive Umgebung zum Testen von Bedingungen|
||VS Code|Code-Editor zum Schreiben und Ausführen von Python-Skripten mit `.py` Dateien|
||`print()` Funktion|Ausgabe von Werten und Ergebnissen zur Überprüfung von Bedingungen|
|**Technische Fachbegriffe**|Condition (Bedingung)|Ausdruck, der zu `True` oder `False` ausgewertet wird|
||Boolean Value (Boolescher Wert)|Wahrheitswert: entweder `True` oder `False`|
||Comparison Operator (Vergleichsoperator)|Operatoren zum Vergleichen von Werten (`==`, `!=`, `>`, `<`, `>=`, `<=`)|
||Logical Operator (Logischer Operator)|Operatoren zum Kombinieren von Bedingungen (`and`, `or`, `not`)|
||Assignment Operator (Zuweisungsoperator)|Das `=` Zeichen zum Zuweisen von Werten (`x = 5`)|
||Equality Operator (Gleichheitsoperator)|Das `==` Zeichen zum Vergleichen von Werten (`x == 5`)|
||Indentation (Einrückung)|Pflichteinrückung in Python (4 Leerzeichen) zur Definition von Code-Blöcken|
||Code Block (Code-Block)|Zusammengehörige Zeilen, die durch Einrückung gruppiert sind|
||Control Flow (Kontrollfluss)|Steuerung, welcher Code basierend auf Bedingungen ausgeführt wird|
||Case-sensitive (Groß-/Kleinschreibung beachten)|`True`/`False` müssen großgeschrieben werden, nicht `true`/`false`|
||Expression (Ausdruck)|Code, der zu einem Wert ausgewertet wird (z.B. `5 > 3` → `True`)|
||Dynamic Execution (Dynamische Ausführung)|Code reagiert unterschiedlich basierend auf Bedingungen|
|**Wichtige Vokabeln**|`if` Statement|Führt Code aus, wenn Bedingung `True` ist|
||`else` Statement|Führt Code aus, wenn vorherige `if`-Bedingung `False` ist|
||`elif` Statement|"else if" – prüft zusätzliche Bedingung, wenn vorherige `False` war|
||`==` (Equal to)|Gleich (z.B. `5 == 5` → `True`)|
||`!=` (Not equal to)|Ungleich (z.B. `5 != 6` → `True`)|
||`>` (Greater than)|Größer als (z.B. `10 > 5` → `True`)|
||`<` (Less than)|Kleiner als (z.B. `3 < 8` → `True`)|
||`>=` (Greater than or equal)|Größer oder gleich (z.B. `7 >= 7` → `True`)|
||`<=` (Less than or equal)|Kleiner oder gleich (z.B. `4 <= 3` → `False`)|
||`and`|UND – beide Bedingungen müssen `True` sein|
||`or`|ODER – mindestens eine Bedingung muss `True` sein|
||`not`|NICHT – kehrt Wahrheitswert um (`not True` → `False`)|
||Colon `:`|Doppelpunkt am Ende jeder Bedingungszeile (Pflicht!)|
||Catch-all|`else`-Block, der ausgeführt wird, wenn keine Bedingung zutrifft|

---

## Zusammenfassung nach dem 80/20-Prinzip

### Die 20% Kernwissen, die 80% der praktischen Anwendung abdecken:

**1. Was sind Bedingungen?**

- **Bedingungen = Fragen, die das Programm stellt**
- Antwort ist immer `True` (wahr) oder `False` (falsch)
- **Zweck:** Code reagiert unterschiedlich auf verschiedene Situationen
- Beispiel: Ist der Benutzer über 18? → Ja/Nein → Zugang gewähren/verweigern

**2. Boolean-Werte: Die Basis**

- Nur zwei mögliche Werte: `True` und `False`
- **Wichtig:** Großschreibung beachten! `true` funktioniert NICHT

```python
ist_erwachsen = True
ist_kind = False
print(type(ist_erwachsen))  # <class 'bool'>
```

**3. Vergleichsoperatoren: Fragen stellen**

|Operator|Bedeutung|Beispiel|Ergebnis|
|---|---|---|---|
|`==`|Gleich|`5 == 5`|`True`|
|`!=`|Ungleich|`5 != 6`|`True`|
|`>`|Größer als|`10 > 5`|`True`|
|`<`|Kleiner als|`3 < 8`|`True`|
|`>=`|Größer oder gleich|`7 >= 7`|`True`|
|`<=`|Kleiner oder gleich|`4 <= 3`|`False`|

**⚠️ Häufigster Fehler:**

- `=` ist ZUWEISUNG → `x = 5` (speichert 5 in x)
- `==` ist VERGLEICH → `x == 5` (prüft ob x gleich 5 ist)

**4. Das `if`-Statement: Einfache Entscheidung**

**Struktur:**

```python
if bedingung:
    # Code wird NUR ausgeführt wenn bedingung True ist
    # MUSS eingerückt sein (4 Leerzeichen)
    print("Bedingung ist wahr!")
```

**Praktisches Beispiel:**

```python
temperatur = 32
if temperatur > 30:
    print("Es ist heiß!")  # Wird ausgeführt
print("Schönen Tag!")      # Wird IMMER ausgeführt (nicht eingerückt)
```

**5. Das `else`-Statement: Die Alternative**

**Struktur:**

```python
if bedingung:
    # Code wenn True
else:
    # Code wenn False
```

**Praktisches Beispiel:**

```python
alter = 17
if alter >= 18:
    print("Zugang erlaubt")
else:
    print("Zugang verweigert")  # Dies wird ausgeführt
```

**6. Das `elif`-Statement: Mehrere Möglichkeiten**

**Struktur:**

```python
if bedingung1:
    # Code wenn bedingung1 True
elif bedingung2:
    # Code wenn bedingung1 False ABER bedingung2 True
elif bedingung3:
    # Code wenn bedingung1 und bedingung2 False ABER bedingung3 True
else:
    # Code wenn ALLE Bedingungen False
```

**Praktisches Beispiel (Notensystem):**

```python
punkte = 75

if punkte >= 90:
    print("Note: Sehr gut")
elif punkte >= 80:
    print("Note: Gut")
elif punkte >= 70:
    print("Note: Befriedigend")  # Dies wird ausgeführt
elif punkte >= 60:
    print("Note: Ausreichend")
else:
    print("Note: Mangelhaft")
```

**Wichtig:** Python prüft von oben nach unten und stoppt beim ersten `True`!

**7. Logische Operatoren: Bedingungen kombinieren**

**`and` – UND (BEIDE müssen True sein):**

```python
alter = 25
hat_ticket = True

if alter >= 18 and hat_ticket:
    print("Eintritt erlaubt")  # Beide Bedingungen sind True → wird ausgeführt
```

**`or` – ODER (MINDESTENS EINE muss True sein):**

```python
ist_wochenende = False
hat_urlaub = True

if ist_wochenende or hat_urlaub:
    print("Frei!")  # Eine Bedingung ist True → wird ausgeführt
```

**`not` – NICHT (kehrt um):**

```python
regnet = False

if not regnet:
    print("Kein Regenschirm nötig")  # not False = True → wird ausgeführt
```

**Wahrheitstabelle für `and` und `or`:**

```
True and True   = True
True and False  = False
False and False = False

True or True    = True
True or False   = True
False or False  = False
```

**8. Wichtige Syntax-Regeln (Häufige Fehler vermeiden!)**

✅ **Richtig:**

```python
if alter >= 18:
    print("Erwachsen")
```

❌ **Falsch (fehlt Doppelpunkt):**

```python
if alter >= 18
    print("Erwachsen")
```

❌ **Falsch (fehlende Einrückung):**

```python
if alter >= 18:
print("Erwachsen")
```

❌ **Falsch (falsche Groß-/Kleinschreibung):**

```python
if alter >= 18:
    print(true)  # Muss True sein!
```

**9. Praxisbeispiel: Komplette Entscheidungslogik**

```python
# Eintrittskontrolle für Club
alter = 22
hat_ausweis = True
ist_gast = False

if alter >= 21 and hat_ausweis:
    print("Willkommen!")
elif ist_gast:
    print("Gäste müssen zum Empfang")
else:
    print("Kein Eintritt möglich")
```

**Schritt-für-Schritt-Logik:**

1. Prüfe: `alter >= 21` → `True` UND `hat_ausweis` → `True` = `True and True` = `True`
2. Erste Bedingung ist `True` → "Willkommen!" wird ausgegeben
3. Alle weiteren Bedingungen (`elif`, `else`) werden übersprungen

**10. Schnelltest: Verstehst du es?**

**Aufgabe:** Was gibt dieser Code aus?

```python
x = 10
y = 5

if x > y:
    print("A")
elif x < y:
    print("B")
else:
    print("C")
```

**Antwort:** `A` (weil 10 > 5 ist `True`)

---

**Aufgabe:** Was gibt dieser Code aus?

```python
ist_sonnig = True
temperatur = 20

if ist_sonnig and temperatur > 25:
    print("Perfekter Strandtag!")
elif ist_sonnig:
    print("Schöner Tag für Spaziergang")
else:
    print("Vielleicht lieber drinnen bleiben")
```

**Antwort:** `Schöner Tag für Spaziergang`  
(Erste Bedingung `False` weil 20 nicht > 25, zweite Bedingung `True` weil `ist_sonnig` = `True`)

---

### Merksätze:

🎯 **`=` speichert, `==` vergleicht**  
🎯 **Einrückung ist Pflicht, nicht optional!**  
🎯 **`and` = beide müssen stimmen, `or` = eins reicht**  
🎯 **Vergiss nie den Doppelpunkt `:` am Ende der Bedingungszeile!**  
🎯 **Python prüft Bedingungen von oben nach unten und stoppt beim ersten `True`**