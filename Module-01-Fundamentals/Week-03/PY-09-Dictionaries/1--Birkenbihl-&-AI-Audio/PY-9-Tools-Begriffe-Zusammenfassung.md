# Python Lektion 9: Dictionaries (Wörterbücher)

## Kategorisierung der Themen

|Kategorie|Begriff|Bedeutung|
|---|---|---|
|**Verwendete Tools**|Python Interpreter|Zum interaktiven Testen von Dictionaries|
||VS Code|Editor zum Schreiben von Python-Skripten mit Dictionaries|
||`print()` Funktion|Ausgabe von Dictionaries und deren Inhalten|
||`dict()` Constructor|Alternative Methode zur Dictionary-Erstellung|
||Square Brackets `[]`|Zugriff auf Werte über Keys|
|**Technische Fachbegriffe**|Dictionary (Wörterbuch)|Datenstruktur zur Speicherung von Schlüssel-Wert-Paaren|
||Key-Value Pair (Schlüssel-Wert-Paar)|Grundeinheit eines Dictionaries: Key → Value|
||Key (Schlüssel)|Eindeutiger Identifier zum Auffinden von Daten|
||Value (Wert)|Daten, die mit einem Key verknüpft sind|
||Immutable (Unveränderlich)|Eigenschaft von Keys: können nicht geändert werden (str, int, tuple)|
||Mutable (Veränderlich)|Values können jeden Typ haben (auch Listen, andere Dicts)|
||Unordered (Ungeordnet)|Keine feste Reihenfolge (ab Python 3.7: Einfüge-Reihenfolge erhalten)|
||KeyError|Fehler beim Zugriff auf nicht existierenden Key|
||View Object|Dynamische Ansicht auf Keys/Values/Items eines Dictionaries|
||Insertion Order (Einfüge-Reihenfolge)|Reihenfolge, in der Elemente hinzugefügt wurden (seit Python 3.7)|
||Lookup (Nachschlagen)|Suche nach Wert anhand des Keys|
||Overwrite (Überschreiben)|Ersetzen eines existierenden Werts durch neuen Wert|
||Default Value (Standardwert)|Rückgabewert, wenn Key nicht existiert (bei `.get()`)|
|**Wichtige Vokabeln**|`{}` Curly Braces|Geschweifte Klammern zum Erstellen von Dictionaries|
||`dict()`|Funktion/Constructor zur Dictionary-Erstellung|
||`[key]`|Syntax zum Zugriff auf Wert über Key|
||`.get(key)`|Sichere Methode zum Abrufen von Werten (kein KeyError)|
||`.get(key, default)`|`.get()` mit Standardwert, wenn Key nicht existiert|
||`del dict[key]`|Entfernt Key-Value-Paar aus Dictionary|
||`.pop(key)`|Entfernt Key-Value-Paar und gibt Wert zurück|
||`.popitem()`|Entfernt letztes eingefügtes Paar und gibt es als Tuple zurück|
||`.keys()`|Gibt alle Keys als View-Objekt zurück|
||`.values()`|Gibt alle Values als View-Objekt zurück|
||`.items()`|Gibt alle Key-Value-Paare als Tuples zurück|
||`in` Operator|Prüft, ob Key im Dictionary existiert|
||`not in` Operator|Prüft, ob Key NICHT im Dictionary existiert|
||Colon `:`|Trennt Key von Value: `"name": "Alice"`|
||Comma `,`|Trennt Key-Value-Paare voneinander|
||Empty Dictionary|Leeres Dictionary: `{}` oder `dict()`|

---

## Zusammenfassung nach dem 80/20-Prinzip

### Die 20% Kernwissen, die 80% der praktischen Anwendung abdecken:

---

## **TEIL 1: WAS SIND DICTIONARIES?**

### **1. Konzept: Dictionary = Reales Wörterbuch**

**Reales Wörterbuch:**

- Wort → Definition
- "Hund" → "Vierbeiniges Haustier"

**Python Dictionary:**

- Key (Schlüssel) → Value (Wert)
- "name" → "Alice"

```python
# Dictionary = Sammlung von Key-Value-Paaren
person = {
    "name": "Alice",
    "alter": 30,
    "beruf": "Ingenieur"
}
```

**Hauptunterschiede zu Listen:**

|Eigenschaft|Liste|Dictionary|
|---|---|---|
|**Zugriff**|Über Index (Zahl)|Über Key (beliebig)|
|**Reihenfolge**|Wichtig (Index-basiert)|Unwichtig (Key-basiert)|
|**Duplikate**|Erlaubt|Keys müssen eindeutig sein|
|**Verwendung**|Geordnete Sammlung|Zuordnungen/Mappings|

---

### **2. Struktur: Key-Value-Pairs**

```python
dictionary = {
    key1: value1,
    key2: value2,
    key3: value3
}
```

**Wichtige Regeln:**

✅ **Keys müssen unveränderlich (immutable) sein:**

- String: `"name"`
- Integer: `42`
- Float: `3.14`
- Tuple: `(1, 2, 3)`

❌ **Keys dürfen NICHT veränderlich (mutable) sein:**

- Liste: `[1, 2, 3]` ❌
- Dictionary: `{"a": 1}` ❌

✅ **Values können ALLES sein:**

- String, Integer, Float, Boolean
- Liste, Tuple, Dictionary
- Jeder Python-Datentyp

---

## **TEIL 2: DICTIONARIES ERSTELLEN**

### **3. Methode 1: Geschweifte Klammern `{}`**

```python
# Leeres Dictionary
leer = {}

# Dictionary mit Werten
noten = {
    "Alice": 85,
    "Bob": 92,
    "Charlie": 78
}

# Dictionary mit gemischten Typen
benutzer = {
    "username": "max123",
    "level": 5,
    "hobbies": ["Lesen", "Sport"],
    "aktiv": True
}

print(noten)
# Output: {'Alice': 85, 'Bob': 92, 'Charlie': 78}
```

---

### **4. Methode 2: `dict()` Constructor**

```python
# Mit Keyword-Argumenten
einstellungen = dict(theme="dark", font_size=12, notifications=True)
print(einstellungen)
# Output: {'theme': 'dark', 'font_size': 12, 'notifications': True}

# Von Liste mit Tupeln (selten verwendet)
paare = [("name", "Alice"), ("alter", 30)]
person = dict(paare)
print(person)
# Output: {'name': 'Alice', 'alter': 30}
```

---

## **TEIL 3: AUF WERTE ZUGREIFEN**

### **5. Zugriff mit Square Brackets `[]`**

```python
noten = {"Alice": 85, "Bob": 92, "Charlie": 78}

# Wert abrufen
alices_note = noten["Alice"]
print(alices_note)  # Output: 85

bobs_note = noten["Bob"]
print(bobs_note)    # Output: 92
```

**⚠️ Gefahr: KeyError**

```python
# ❌ Key existiert nicht
davids_note = noten["David"]
# KeyError: 'David'
```

---

### **6. Sicherer Zugriff mit `.get()`**

**Syntax:**

- `.get(key)` → Gibt `None` zurück, wenn Key nicht existiert
- `.get(key, default)` → Gibt `default` zurück, wenn Key nicht existiert

```python
noten = {"Alice": 85, "Bob": 92, "Charlie": 78}

# Key existiert
alices_note = noten.get("Alice")
print(alices_note)  # Output: 85

# Key existiert NICHT (gibt None zurück)
davids_note = noten.get("David")
print(davids_note)  # Output: None

# Mit Standardwert
davids_note_default = noten.get("David", "Nicht gefunden")
print(davids_note_default)  # Output: Nicht gefunden
```

**Wann `.get()` verwenden?** ✅ Wenn unsicher, ob Key existiert ✅ Wenn KeyError vermieden werden soll ✅ Wenn Standardwert sinnvoll ist

---

## **TEIL 4: ELEMENTE HINZUFÜGEN UND ÄNDERN**

### **7. Hinzufügen und Aktualisieren**

```python
noten = {"Alice": 85, "Bob": 92}
print(f"Vorher: {noten}")

# Neues Element HINZUFÜGEN
noten["David"] = 88
print(f"Nach Hinzufügen: {noten}")

# Existierendes Element AKTUALISIEREN
noten["Bob"] = 95
print(f"Nach Aktualisieren: {noten}")

# Output:
# Vorher: {'Alice': 85, 'Bob': 92}
# Nach Hinzufügen: {'Alice': 85, 'Bob': 92, 'David': 88}
# Nach Aktualisieren: {'Alice': 85, 'Bob': 95, 'David': 88}
```

**Regel:**

- **Key existiert** → Wert wird **überschrieben**
- **Key existiert nicht** → Neues Paar wird **hinzugefügt**

---

## **TEIL 5: ELEMENTE ENTFERNEN**

### **8. Methode 1: `del` Keyword**

```python
einstellungen = {"theme": "dark", "font_size": 12, "auto_save": True}
print(f"Vorher: {einstellungen}")

del einstellungen["auto_save"]
print(f"Nachher: {einstellungen}")

# Output:
# Vorher: {'theme': 'dark', 'font_size': 12, 'auto_save': True}
# Nachher: {'theme': 'dark', 'font_size': 12}

# ❌ Key existiert nicht
# del einstellungen["language"]  # KeyError!
```

**Verwendung:** Wenn nur Löschen wichtig ist, nicht der Wert

---

### **9. Methode 2: `.pop(key)` – Entfernen und Wert zurückgeben**

```python
einstellungen = {"theme": "dark", "font_size": 12, "auto_save": True}

# Element entfernen und Wert erhalten
entfernter_wert = einstellungen.pop("font_size")
print(f"Entfernter Wert: {entfernter_wert}")  # Output: 12
print(f"Dictionary: {einstellungen}")

# Mit Standardwert (Key existiert nicht)
sprache = einstellungen.pop("language", "English")
print(f"Sprache: {sprache}")  # Output: English

# ❌ Ohne Standardwert bei nicht existierendem Key
# wert = einstellungen.pop("language")  # KeyError!
```

**Verwendung:** Wenn der entfernte Wert gebraucht wird

---

### **10. Methode 3: `.popitem()` – Letztes Element entfernen**

```python
einstellungen = {"theme": "dark", "font_size": 12, "auto_save": True}

# Entfernt letztes eingefügtes Paar
letztes = einstellungen.popitem()
print(f"Entfernt: {letztes}")    # Output: ('auto_save', True)
print(f"Dictionary: {einstellungen}")

# ❌ Bei leerem Dictionary
# leeres = {}
# leeres.popitem()  # KeyError!
```

**Verwendung:** Selten – wenn letztes Element entfernt werden soll

---

## **TEIL 6: KEYS PRÜFEN**

### **11. Mit `in` und `not in` Operator**

```python
noten = {"Alice": 85, "Bob": 92, "Charlie": 78}

# Prüfen, ob Key existiert
if "Alice" in noten:
    print("Alice ist im Dictionary")
else:
    print("Alice ist nicht im Dictionary")

# Prüfen, ob Key NICHT existiert
if "David" not in noten:
    print("David ist nicht im Dictionary")
else:
    print("David ist im Dictionary")

# Praktischer Einsatz: Sicherer Zugriff
name = "David"
if name in noten:
    print(f"{name}: {noten[name]}")
else:
    print(f"{name} nicht gefunden")
```

**Best Practice:** Vor Zugriff mit `[]` immer prüfen, ob Key existiert

---

## **TEIL 7: WICHTIGE DICTIONARY-METHODEN**

### **12. `.keys()` – Alle Keys abrufen**

```python
einstellungen = {"theme": "dark", "font_size": 12, "auto_save": True}

# Keys als View-Objekt
keys = einstellungen.keys()
print(keys)  # Output: dict_keys(['theme', 'font_size', 'auto_save'])

# In Liste umwandeln
keys_liste = list(keys)
print(keys_liste)  # Output: ['theme', 'font_size', 'auto_save']

# Über Keys iterieren
for key in einstellungen.keys():
    print(key)
# Output:
# theme
# font_size
# auto_save
```

---

### **13. `.values()` – Alle Values abrufen**

```python
einstellungen = {"theme": "dark", "font_size": 12, "auto_save": True}

# Values als View-Objekt
values = einstellungen.values()
print(values)  # Output: dict_values(['dark', 12, True])

# In Liste umwandeln
values_liste = list(values)
print(values_liste)  # Output: ['dark', 12, True]

# Über Values iterieren
for value in einstellungen.values():
    print(value)
# Output:
# dark
# 12
# True
```

---

### **14. `.items()` – Alle Key-Value-Paare abrufen**

```python
einstellungen = {"theme": "dark", "font_size": 12, "auto_save": True}

# Items als View-Objekt (Tuples)
items = einstellungen.items()
print(items)
# Output: dict_items([('theme', 'dark'), ('font_size', 12), ('auto_save', True)])

# In Liste umwandeln
items_liste = list(items)
print(items_liste)
# Output: [('theme', 'dark'), ('font_size', 12), ('auto_save', True)]

# Über Items iterieren (sehr häufig verwendet!)
for key, value in einstellungen.items():
    print(f"Key: {key}, Value: {value}")
# Output:
# Key: theme, Value: dark
# Key: font_size, Value: 12
# Key: auto_save, Value: True
```

**💡 Tipp:** `.items()` mit Schleife ist die häufigste Verwendung!

---

## **TEIL 8: PRAKTISCHE BEISPIELE**

### **15. Beispiel 1: Kontaktliste**

```python
kontakte = {
    "Alice": "555-1234",
    "Bob": "555-5678",
    "Charlie": "555-9012"
}

# Kontakt suchen
name = "Alice"
if name in kontakte:
    print(f"{name}: {kontakte[name]}")
else:
    print(f"{name} nicht gefunden")

# Neuen Kontakt hinzufügen
kontakte["Diana"] = "555-3456"

# Kontakt aktualisieren
kontakte["Bob"] = "555-0000"

# Alle Kontakte ausgeben
print("\nAlle Kontakte:")
for name, nummer in kontakte.items():
    print(f"{name}: {nummer}")
```

---

### **16. Beispiel 2: Wortfrequenz zählen**

```python
text = "hallo welt hallo python welt hallo"
woerter = text.split()

# Leeres Dictionary für Zählung
frequenz = {}

# Zählen
for wort in woerter:
    if wort in frequenz:
        frequenz[wort] += 1
    else:
        frequenz[wort] = 1

print(frequenz)
# Output: {'hallo': 3, 'welt': 2, 'python': 1}

# Alternative mit .get()
frequenz2 = {}
for wort in woerter:
    frequenz2[wort] = frequenz2.get(wort, 0) + 1

print(frequenz2)
# Output: {'hallo': 3, 'welt': 2, 'python': 1}
```

---

### **17. Beispiel 3: Nested Dictionaries (Verschachtelt)**

```python
# Dictionary von Dictionaries
studenten = {
    "Alice": {
        "alter": 20,
        "noten": [85, 90, 88],
        "aktiv": True
    },
    "Bob": {
        "alter": 22,
        "noten": [92, 87, 95],
        "aktiv": False
    }
}

# Zugriff auf verschachtelte Werte
print(studenten["Alice"]["alter"])      # Output: 20
print(studenten["Alice"]["noten"][0])   # Output: 85

# Über verschachtelte Struktur iterieren
for name, daten in studenten.items():
    print(f"\n{name}:")
    print(f"  Alter: {daten['alter']}")
    print(f"  Durchschnitt: {sum(daten['noten']) / len(daten['noten'])}")
    print(f"  Aktiv: {daten['aktiv']}")
```

---

## **SCHNELLREFERENZ**

### **Dictionary-Cheatsheet:**

```python
# Erstellen
d = {}
d = {"key": "value"}
d = dict(key="value")

# Zugriff
wert = d["key"]         # KeyError wenn nicht vorhanden
wert = d.get("key")     # None wenn nicht vorhanden
wert = d.get("key", "default")  # "default" wenn nicht vorhanden

# Hinzufügen/Ändern
d["neuer_key"] = "wert"
d["alter_key"] = "neuer_wert"

# Entfernen
del d["key"]
wert = d.pop("key")
letztes = d.popitem()

# Prüfen
if "key" in d:
    print("vorhanden")

# Methoden
keys = d.keys()
values = d.values()
items = d.items()

# Iteration
for key in d:
    print(key, d[key])

for key, value in d.items():
    print(key, value)
```

---

## **HÄUFIGE FEHLER UND LÖSUNGEN**

### **18. Fehler 1: KeyError bei Zugriff**

```python
# ❌ Problem
noten = {"Alice": 85}
print(noten["Bob"])  # KeyError!
```

**✅ Lösungen:**

```python
# Lösung 1: Vorher prüfen
if "Bob" in noten:
    print(noten["Bob"])

# Lösung 2: .get() verwenden
print(noten.get("Bob", "Nicht gefunden"))
```

---

### **19. Fehler 2: Liste als Key verwenden**

```python
# ❌ Problem
d = {[1, 2]: "wert"}  # TypeError: unhashable type: 'list'
```

**✅ Lösung:** Tuple statt Liste verwenden

```python
d = {(1, 2): "wert"}  # ✅ Funktioniert
```

---

### **20. Fehler 3: Verschachtelte Werte falsch zugreifen**

```python
person = {"name": "Alice", "adresse": {"stadt": "Berlin"}}

# ❌ Falsch
# stadt = person["stadt"]  # KeyError!

# ✅ Richtig
stadt = person["adresse"]["stadt"]
print(stadt)  # Output: Berlin
```

---

## **VERGLEICH: LISTE VS. DICTIONARY**

### **21. Wann was verwenden?**

|Situation|Verwende|Beispiel|
|---|---|---|
|Reihenfolge wichtig|Liste|Highscores, Warteschlange|
|Schneller Zugriff per Name|Dictionary|Kontakte, Einstellungen|
|Duplikate erlaubt|Liste|Messwerte, Logs|
|Eindeutige Identifier|Dictionary|Benutzer-IDs, Produkt-Codes|
|Iteration über Position|Liste|`liste[0]`, `liste[1]`|
|Zuordnung/Mapping|Dictionary|Land → Hauptstadt|

**Beispiel:**

```python
# Liste: Reihenfolge wichtig
highscores = [1000, 950, 900, 850, 800]
print(f"1. Platz: {highscores[0]}")

# Dictionary: Zuordnung wichtig
hauptstaedte = {
    "Deutschland": "Berlin",
    "Frankreich": "Paris",
    "Italien": "Rom"
}
print(f"Hauptstadt von Deutschland: {hauptstaedte['Deutschland']}")
```

---

## **ÜBUNGSAUFGABEN**

**Aufgabe 1:** Erstelle ein Dictionary `buch` mit Keys: "titel", "autor", "jahr", "seiten". Gib alle Keys und Values aus.

**Aufgabe 2:** Schreibe ein Programm, das Benutzernamen und Passwörter speichert. Prüfe bei Login, ob Benutzername existiert und Passwort stimmt.

**Aufgabe 3:** Zähle, wie oft jeder Buchstabe in einem String vorkommt (case-insensitive).

**Aufgabe 4:** Erstelle ein verschachteltes Dictionary für 3 Produkte mit Name, Preis, und Lagerbestand. Berechne Gesamtwert aller Produkte.

---

### **Merksätze:**

🎯 **Dictionary = Key → Value (wie echtes Wörterbuch)**  
🎯 **Keys müssen unveränderlich sein (str, int, tuple), Values können alles sein**  
🎯 **Zugriff: `dict["key"]` → KeyError möglich, `dict.get("key")` → sicher**  
🎯 **`dict["key"] = value` → Hinzufügen ODER Überschreiben**  
🎯 **`.items()` mit Schleife = häufigste Verwendung: `for k, v in dict.items()`**  
🎯 **`in` Operator prüft, ob Key existiert: `if "key" in dict:`**  
🎯 **Liste = Position wichtig, Dictionary = Identifier wichtig**