# Python Lektion 14: Objektorientierte Programmierung (OOP)

## Kategorisierung der Themen

|Kategorie|Begriff|Bedeutung|
|---|---|---|
|**Verwendete Tools**|Python Interpreter|Zum Testen von OOP-Konzepten|
||VS Code|Editor zum Schreiben von Klassen und Objekten|
||`class` Keyword|Schlüsselwort zum Definieren einer Klasse|
||Dot Notation (Punkt-Notation)|Zugriff auf Attribute/Methoden: `objekt.attribut`|
|**Technische Fachbegriffe**|OOP (Object-Oriented Programming)|Objektorientierte Programmierung - Paradigma basierend auf Objekten|
||Procedural Programming|Prozedurale Programmierung - sequenzielle Anweisungen|
||Class (Klasse)|Bauplan/Vorlage für Objekte|
||Object (Objekt)|Konkrete Instanz einer Klasse|
||Instance (Instanz)|Anderer Begriff für Objekt (spezifisches Exemplar einer Klasse)|
||Blueprint (Bauplan)|Metapher für Klasse (z.B. Bauplan für Haus)|
||State (Zustand)|Daten/Eigenschaften eines Objekts|
||Behavior (Verhalten)|Aktionen, die ein Objekt ausführen kann|
||Attribute|Variable, die zu einem Objekt gehört (speichert Zustand)|
||Method (Methode)|Funktion, die zu einem Objekt gehört (definiert Verhalten)|
||Constructor (Konstruktor)|Spezielle Methode `__init__` zum Initialisieren von Objekten|
||`self` Parameter|Referenz auf die aktuelle Instanz innerhalb der Klasse|
||Instance Variable|Variable, die zu spezifischer Instanz gehört (via `self`)|
||Instance Method|Methode, die auf spezifischer Instanz arbeitet (erster Parameter: `self`)|
||Instantiation (Instanziierung)|Prozess des Erstellens eines Objekts aus einer Klasse|
||Encapsulation (Kapselung)|Gruppierung von Daten und Funktionen in Objekt|
||Modularity (Modularität)|Aufteilung in selbständige, wiederverwendbare Einheiten|
||Reusability (Wiederverwendbarkeit)|Mehrfache Nutzung von Klassen-Definitionen|
||Modeling (Modellierung)|Abbildung realer/konzeptioneller Entitäten im Code|
|**Wichtige Vokabeln**|`class ClassName:`|Definiert neue Klasse|
||`__init__(self, ...)`|Konstruktor-Methode zur Initialisierung|
||`self`|Referenz auf aktuelles Objekt (muss erster Parameter sein)|
||`self.attribute`|Instanz-Attribut (Zustand des Objekts)|
||`def method(self):`|Instanz-Methode (Verhalten des Objekts)|
||`object = ClassName(args)`|Erstellt neue Instanz|
||`object.attribute`|Zugriff auf Attribut|
||`object.method()`|Aufruf einer Methode|
||Capital Letter Convention|Klassennamen beginnen mit Großbuchstaben (z.B. `Dog`, `LogEntry`)|
||Instance Attribute|Attribut, das zu spezifischer Instanz gehört|
||Dot Notation|`objekt.attribut` oder `objekt.methode()`|

---

## Zusammenfassung nach dem 80/20-Prinzip

### Die 20% Kernwissen, die 80% der praktischen Anwendung abdecken:

---

## **TEIL 1: WAS IST OOP?**

### **1. Vergleich: Prozedural vs. Objektorientiert**

**Prozedural (bisheriger Stil):**

```python
# Daten und Funktionen getrennt
hund1_name = "Fido"
hund1_rasse = "Golden Retriever"
hund2_name = "Rex"
hund2_rasse = "Schäferhund"

def bellen(name):
    print(f"{name} bellt: Wuff!")

bellen(hund1_name)
bellen(hund2_name)
```

**Probleme:**

- Daten und Funktionen getrennt
- Keine klare Struktur
- Schwer zu skalieren

---

**Objektorientiert:**

```python
class Hund:
    def __init__(self, name, rasse):
        self.name = name
        self.rasse = rasse
    
    def bellen(self):
        print(f"{self.name} bellt: Wuff!")

hund1 = Hund("Fido", "Golden Retriever")
hund2 = Hund("Rex", "Schäferhund")

hund1.bellen()
hund2.bellen()
```

**Vorteile:**

- ✅ Daten und Funktionen zusammen
- ✅ Klare Struktur
- ✅ Wiederverwendbar
- ✅ Modelliert reale Welt

---

### **2. Reale Welt → Objekte**

**Beispiele aus der realen Welt:**

|Real-Welt-Objekt|Zustand (State)|Verhalten (Behavior)|
|---|---|---|
|Auto|Farbe, Marke, Geschwindigkeit|Starten, Beschleunigen, Bremsen|
|Hund|Name, Rasse, Alter|Bellen, Laufen, Fressen|
|Log-Eintrag|Zeitstempel, IP, Nachricht|Parsen, Filtern, Speichern|
|Benutzer-Konto|Username, E-Mail, Passwort|Anmelden, Abmelden, Passwort ändern|

**OOP = Reale Objekte als Code-Objekte modellieren**

---

### **3. Die 4 Hauptvorteile von OOP**

**1. Organisation**

```python
# Alles zusammen in einer Klasse
class Benutzer:
    def __init__(self, name, email):
        self.name = name
        self.email = email
    
    def sende_email(self, nachricht):
        print(f"E-Mail an {self.email}: {nachricht}")
```

**2. Wiederverwendbarkeit**

```python
# Einmal definieren, mehrfach nutzen
benutzer1 = Benutzer("Alice", "alice@example.com")
benutzer2 = Benutzer("Bob", "bob@example.com")
benutzer3 = Benutzer("Charlie", "charlie@example.com")
```

**3. Modularität**

```python
# Jedes Objekt ist eigenständig
benutzer1.sende_email("Hallo!")
benutzer2.sende_email("Willkommen!")
```

**4. Modellierung**

```python
# Natürliche Abbildung komplexer Systeme
class Netzwerkverbindung:
    def __init__(self, quell_ip, ziel_ip):
        self.quell_ip = quell_ip
        self.ziel_ip = ziel_ip
    
    def verbinden(self):
        print(f"Verbinde {self.quell_ip} mit {self.ziel_ip}")
```

---

## **TEIL 2: KLASSEN – DER BAUPLAN**

### **4. Was ist eine Klasse?**

**Klasse = Bauplan für Objekte**

**Metapher:**

- Klasse = Keksausstecher (Bauplan)
- Objekt = Keks (konkretes Exemplar)

```python
# Syntax
class KlassenName:
    def __init__(self, parameter):
        self.attribut = parameter
    
    def methode(self):
        # Code
```

---

### **5. Einfaches Beispiel: Hund-Klasse**

```python
class Hund:
    # Konstruktor: Wird automatisch beim Erstellen aufgerufen
    def __init__(self, name, rasse):
        # Attribute (Zustand)
        self.name = name
        self.rasse = rasse
    
    # Methode (Verhalten)
    def bellen(self):
        print(f"{self.name} sagt Wuff!")
    
    def info(self):
        print(f"{self.name} ist ein {self.rasse}")
```

**Komponenten:**

1. **`class Hund:`** → Klassenname (Großbuchstabe!)
2. **`__init__`** → Konstruktor (Initialisierung)
3. **`self.name`, `self.rasse`** → Attribute (Daten)
4. **`bellen()`, `info()`** → Methoden (Aktionen)

---

### **6. Konventionen für Klassennamen**

```python
# ✅ Richtig: PascalCase (erster Buchstabe groß)
class Hund:
    pass

class BenutzerKonto:
    pass

class LogEintrag:
    pass

# ❌ Falsch
class hund:  # Kleinbuchstabe
    pass

class benutzer_konto:  # snake_case
    pass
```

**Regel:** Klassennamen immer mit Großbuchstaben beginnen!

---

## **TEIL 3: OBJEKTE – KONKRETE EXEMPLARE**

### **7. Objekte erstellen (Instanziierung)**

```python
# Klasse definieren
class Hund:
    def __init__(self, name, rasse):
        self.name = name
        self.rasse = rasse
    
    def bellen(self):
        print(f"{self.name} sagt Wuff!")

# Objekte erstellen (Instanziierung)
hund1 = Hund("Fido", "Golden Retriever")
hund2 = Hund("Rex", "Schäferhund")
hund3 = Hund("Luna", "Labrador")
```

**Was passiert:**

1. Python ruft `__init__` auf
2. Erstellt neues Objekt
3. Weist Argumente zu Attributen zu
4. Gibt Objekt zurück

---

### **8. Jedes Objekt ist unabhängig**

```python
hund1 = Hund("Fido", "Golden Retriever")
hund2 = Hund("Rex", "Schäferhund")

# Änderung an hund1 beeinflusst hund2 nicht
hund1.name = "Buddy"

print(hund1.name)  # Output: Buddy
print(hund2.name)  # Output: Rex (unverändert!)
```

**Wichtig:** Jedes Objekt hat eigene Attribute-Werte

---

## **TEIL 4: ATTRIBUTE – DER ZUSTAND**

### **9. Attribute definieren und zugreifen**

```python
class Auto:
    def __init__(self, marke, farbe, baujahr):
        # Attribute definieren
        self.marke = marke
        self.farbe = farbe
        self.baujahr = baujahr
        self.geschwindigkeit = 0  # Standard-Wert

# Objekt erstellen
auto1 = Auto("BMW", "Blau", 2020)

# Attribute lesen
print(auto1.marke)        # Output: BMW
print(auto1.farbe)        # Output: Blau
print(auto1.baujahr)      # Output: 2020
print(auto1.geschwindigkeit)  # Output: 0

# Attribute ändern
auto1.farbe = "Rot"
auto1.geschwindigkeit = 120

print(auto1.farbe)        # Output: Rot
print(auto1.geschwindigkeit)  # Output: 120
```

---

### **10. Attribute vs. lokale Variablen**

```python
class Beispiel:
    def __init__(self, wert):
        self.attribut = wert  # ✅ Attribut (mit self)
        lokale_variable = 10  # ❌ Nur in __init__ verfügbar
    
    def methode(self):
        print(self.attribut)  # ✅ Funktioniert
        # print(lokale_variable)  # ❌ NameError!

obj = Beispiel(5)
obj.methode()  # Output: 5
```

**Regel:** Verwende `self.` für Attribute, die im ganzen Objekt verfügbar sein sollen

---

## **TEIL 5: METHODEN – DAS VERHALTEN**

### **11. Methoden definieren und aufrufen**

```python
class Kreis:
    def __init__(self, radius):
        self.radius = radius
    
    # Methoden
    def berechne_flaeche(self):
        import math
        return math.pi * self.radius ** 2
    
    def berechne_umfang(self):
        import math
        return 2 * math.pi * self.radius
    
    def info(self):
        print(f"Kreis mit Radius {self.radius}")

# Objekt erstellen
kreis1 = Kreis(5)

# Methoden aufrufen
kreis1.info()  # Output: Kreis mit Radius 5
flaeche = kreis1.berechne_flaeche()
print(f"Fläche: {flaeche:.2f}")  # Output: Fläche: 78.54
umfang = kreis1.berechne_umfang()
print(f"Umfang: {umfang:.2f}")  # Output: Umfang: 31.42
```

---

### **12. Methoden mit Parametern**

```python
class Bankkonto:
    def __init__(self, inhaber, kontostand):
        self.inhaber = inhaber
        self.kontostand = kontostand
    
    def einzahlen(self, betrag):
        self.kontostand += betrag
        print(f"{betrag}€ eingezahlt. Neuer Kontostand: {self.kontostand}€")
    
    def abheben(self, betrag):
        if betrag > self.kontostand:
            print("Nicht genug Guthaben!")
        else:
            self.kontostand -= betrag
            print(f"{betrag}€ abgehoben. Neuer Kontostand: {self.kontostand}€")
    
    def zeige_kontostand(self):
        print(f"Kontostand von {self.inhaber}: {self.kontostand}€")

# Verwendung
konto = Bankkonto("Alice", 1000)
konto.zeige_kontostand()  # Output: Kontostand von Alice: 1000€
konto.einzahlen(500)      # Output: 500€ eingezahlt. Neuer Kontostand: 1500€
konto.abheben(200)        # Output: 200€ abgehoben. Neuer Kontostand: 1300€
```

---

## **TEIL 6: DER `self`-PARAMETER**

### **13. Was ist `self`?**

**`self` = Referenz auf das aktuelle Objekt**

```python
class Beispiel:
    def __init__(self, wert):
        self.wert = wert  # self = aktuelles Objekt
    
    def zeige(self):
        print(f"Wert: {self.wert}")  # Zugriff auf Attribut

obj1 = Beispiel(10)
obj2 = Beispiel(20)

obj1.zeige()  # self ist obj1 → Output: Wert: 10
obj2.zeige()  # self ist obj2 → Output: Wert: 20
```

**Was passiert intern:**

```python
# Du schreibst:
obj1.zeige()

# Python übersetzt zu:
Beispiel.zeige(obj1)  # obj1 wird als self übergeben
```

---

### **14. `self` ist immer erster Parameter**

```python
class Hund:
    def __init__(self, name):  # self = erstes Argument
        self.name = name
    
    def bellen(self):  # self = erstes Argument
        print(f"{self.name} bellt")
    
    def fressen(self, futter):  # self = IMMER zuerst, dann andere
        print(f"{self.name} frisst {futter}")

hund = Hund("Fido")
hund.bellen()           # Kein self nötig beim Aufruf
hund.fressen("Fleisch") # Python fügt self automatisch hinzu
```

**Regel:** `self` muss bei Definition dabei sein, beim Aufruf nicht!

---

### **15. Warum `self` notwendig ist**

```python
class Konto:
    def __init__(self, kontostand):
        self.kontostand = kontostand  # Attribut
    
    def einzahlen(self, betrag):
        # ❌ Ohne self: Greift auf lokale Variable zu
        # kontostand = kontostand + betrag  # Ändert nichts am Objekt!
        
        # ✅ Mit self: Greift auf Attribut zu
        self.kontostand = self.kontostand + betrag  # Ändert Objekt!

konto = Konto(100)
konto.einzahlen(50)
print(konto.kontostand)  # Output: 150
```

---

## **TEIL 7: DER KONSTRUKTOR `__init__`**

### **16. Was macht `__init__`?**

**Konstruktor = Initialisierungs-Methode**

- Wird automatisch beim Erstellen aufgerufen
- Setzt Start-Werte für Attribute

```python
class Person:
    def __init__(self, name, alter):
        print(f"Erstelle Person: {name}")
        self.name = name
        self.alter = alter
        self.ist_erwachsen = alter >= 18  # Berechnetes Attribut

person1 = Person("Alice", 25)
# Output: Erstelle Person: Alice

print(person1.name)          # Output: Alice
print(person1.alter)         # Output: 25
print(person1.ist_erwachsen) # Output: True
```

---

### **17. Standard-Werte im Konstruktor**

```python
class Rechteck:
    def __init__(self, breite=10, hoehe=5):
        self.breite = breite
        self.hoehe = hoehe
    
    def flaeche(self):
        return self.breite * self.hoehe

# Verschiedene Verwendungen
r1 = Rechteck()           # Verwendet Defaults
r2 = Rechteck(20)         # breite=20, hoehe=5 (Default)
r3 = Rechteck(15, 10)     # breite=15, hoehe=10
r4 = Rechteck(hoehe=8)    # breite=10 (Default), hoehe=8

print(r1.flaeche())  # Output: 50
print(r2.flaeche())  # Output: 100
print(r3.flaeche())  # Output: 150
print(r4.flaeche())  # Output: 80
```

---

## **PRAKTISCHE BEISPIELE**

### **18. Beispiel 1: Log-Eintrag (Cybersecurity)**

```python
class LogEintrag:
    def __init__(self, zeitstempel, quell_ip, nachricht, schweregrad="INFO"):
        self.zeitstempel = zeitstempel
        self.quell_ip = quell_ip
        self.nachricht = nachricht
        self.schweregrad = schweregrad
    
    def ist_fehler(self):
        return self.schweregrad in ["ERROR", "CRITICAL"]
    
    def ist_von_ip(self, ip):
        return self.quell_ip == ip
    
    def formatiert(self):
        return f"[{self.zeitstempel}] {self.schweregrad} - {self.quell_ip}: {self.nachricht}"

# Verwendung
log1 = LogEintrag("2024-01-15 10:30:00", "192.168.1.100", "Benutzer angemeldet")
log2 = LogEintrag("2024-01-15 10:31:00", "192.168.1.50", "Datei nicht gefunden", "ERROR")

print(log1.formatiert())
# Output: [2024-01-15 10:30:00] INFO - 192.168.1.100: Benutzer angemeldet

print(log2.formatiert())
# Output: [2024-01-15 10:31:00] ERROR - 192.168.1.50: Datei nicht gefunden

if log2.ist_fehler():
    print("Warnung: Fehler erkannt!")
```

---

### **19. Beispiel 2: Benutzer-Verwaltung**

```python
class Benutzer:
    def __init__(self, username, email, rolle="user"):
        self.username = username
        self.email = email
        self.rolle = rolle
        self.ist_aktiv = True
    
    def deaktivieren(self):
        self.ist_aktiv = False
        print(f"Benutzer {self.username} wurde deaktiviert")
    
    def aktivieren(self):
        self.ist_aktiv = True
        print(f"Benutzer {self.username} wurde aktiviert")
    
    def ist_admin(self):
        return self.rolle == "admin"
    
    def info(self):
        status = "aktiv" if self.ist_aktiv else "inaktiv"
        return f"Benutzer: {self.username} ({self.email}) - Rolle: {self.rolle} - Status: {status}"

# Verwendung
user1 = Benutzer("alice", "alice@example.com", "admin")
user2 = Benutzer("bob", "bob@example.com")

print(user1.info())
# Output: Benutzer: alice (alice@example.com) - Rolle: admin - Status: aktiv

if user1.ist_admin():
    print(f"{user1.username} hat Admin-Rechte")

user2.deaktivieren()
# Output: Benutzer bob wurde deaktiviert
```

---

### **20. Beispiel 3: Einkaufswagen**

```python
class Produkt:
    def __init__(self, name, preis):
        self.name = name
        self.preis = preis

class Einkaufswagen:
    def __init__(self):
        self.produkte = []
    
    def hinzufuegen(self, produkt):
        self.produkte.append(produkt)
        print(f"{produkt.name} hinzugefügt")
    
    def entfernen(self, produkt_name):
        for produkt in self.produkte:
            if produkt.name == produkt_name:
                self.produkte.remove(produkt)
                print(f"{produkt_name} entfernt")
                return
        print(f"{produkt_name} nicht gefunden")
    
    def gesamtpreis(self):
        return sum(p.preis for p in self.produkte)
    
    def anzeigen(self):
        if not self.produkte:
            print("Warenkorb ist leer")
        else:
            print("=== Warenkorb ===")
            for produkt in self.produkte:
                print(f"- {produkt.name}: {produkt.preis:.2f}€")
            print(f"Gesamt: {self.gesamtpreis():.2f}€")

# Verwendung
wagen = Einkaufswagen()

laptop = Produkt("Laptop", 999.99)
maus = Produkt("Maus", 29.99)
tastatur = Produkt("Tastatur", 79.99)

wagen.hinzufuegen(laptop)
wagen.hinzufuegen(maus)
wagen.hinzufuegen(tastatur)

wagen.anzeigen()
# Output:
# === Warenkorb ===
# - Laptop: 999.99€
# - Maus: 29.99€
# - Tastatur: 79.99€
# Gesamt: 1109.97€

wagen.entfernen("Maus")
wagen.anzeigen()
```

---

## **SCHNELLREFERENZ**

### **OOP-Cheatsheet:**

```python
# Klasse definieren
class KlassenName:
    def __init__(self, parameter):
        self.attribut = parameter
    
    def methode(self):
        return self.attribut

# Objekt erstellen
objekt = KlassenName(wert)

# Attribut zugreifen
print(objekt.attribut)
objekt.attribut = neuer_wert

# Methode aufrufen
ergebnis = objekt.methode()

# Mehrere Objekte
obj1 = KlassenName(wert1)
obj2 = KlassenName(wert2)
```

---

## **HÄUFIGE FEHLER UND LÖSUNGEN**

### **21. Fehler 1: `self` vergessen**

```python
# ❌ Falsch
class Hund:
    def __init__(self, name):
        name = name  # Kein self!
    
    def bellen(self):
        print(f"{name} bellt")  # NameError!

# ✅ Richtig
class Hund:
    def __init__(self, name):
        self.name = name  # Mit self!
    
    def bellen(self):
        print(f"{self.name} bellt")
```

---

### **22. Fehler 2: Klassenname klein geschrieben**

```python
# ❌ Falsch (gegen Konvention)
class hund:
    pass

# ✅ Richtig
class Hund:
    pass
```

---

### **23. Fehler 3: `__init__` falsch geschrieben**

```python
# ❌ Falsch
class Hund:
    def _init_(self, name):  # Nur 1 Unterstrich!
        self.name = name

# ❌ Falsch
class Hund:
    def init(self, name):  # Keine Unterstriche!
        self.name = name

# ✅ Richtig
class Hund:
    def __init__(self, name):  # 2 Unterstriche vor UND nach!
        self.name = name
```

---

### **24. Fehler 4: `self` beim Aufruf angeben**

```python
class Hund:
    def bellen(self):
        print("Wuff!")

hund = Hund()

# ❌ Falsch
# hund.bellen(hund)  # TypeError! Zu viele Argumente

# ✅ Richtig
hund.bellen()  # Python fügt self automatisch hinzu
```

---

## **ÜBUNGSAUFGABEN**

**Aufgabe 1:** Erstelle Klasse `Buch` mit Attributen `titel`, `autor`, `seiten`. Methode `info()` gibt Buchdetails aus.

**Aufgabe 2:** Erstelle Klasse `Rechteck` mit `breite`, `hoehe`. Methoden: `flaeche()`, `umfang()`.

**Aufgabe 3:** Erstelle Klasse `Bankkonto` mit `inhaber`, `kontostand`. Methoden: `einzahlen()`, `abheben()`, `zeige_kontostand()`.

**Aufgabe 4:** Erstelle Klasse `Student` mit `name`, `matrikelnummer`, `noten` (Liste). Methoden: `note_hinzufuegen()`, `durchschnitt()`.

---

### **Merksätze:**

🎯 **Klasse = Bauplan, Objekt = konkretes Exemplar**  
🎯 **`__init__` = Konstruktor (automatisch beim Erstellen aufgerufen)**  
🎯 **`self` = Referenz auf aktuelles Objekt (immer erster Parameter!)**  
🎯 **Attribute = Zustand (Daten), Methoden = Verhalten (Aktionen)**  
🎯 **Klassennamen mit Großbuchstaben beginnen (PascalCase)**  
🎯 **`self.attribut` für Attribute, die im ganzen Objekt verfügbar sind**  
🎯 **OOP = Organisation, Wiederverwendbarkeit, Modularität, Modellierung**