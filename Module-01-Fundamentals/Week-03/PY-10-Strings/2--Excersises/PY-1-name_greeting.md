# 🐍 Name Greeting - Begrüßung formatieren

**Kurs:** Fachinformatiker Ausbildung | **Datum:** 19.01.2026

---

## Aufgabe

**Ziel:** Lese Vor- und Nachname ein, bereinige und formatiere sie, gib Begrüßung aus.

**Anforderungen:**
- Input: Vorname + Nachname (mit Prompts)
- Verarbeitung: `.strip()` + `.title()`
- Output: `"Hello, [Vorname] [Nachname]!"`

---

## Lösung

```python
# Namen einlesen
first_name = input("Enter first name: ")
last_name = input("Enter last name: ")

# Bereinigen und formatieren
first_name = first_name.strip().title()
last_name = last_name.strip().title()

# Ausgabe
print(f"Hello, {first_name} {last_name}!")
```

**Einzeiler-Alternative:**
```python
print(f"Hello, {input('Enter first name: ').strip().title()} {input('Enter last name: ').strip().title()}!")
```

---

## Tests

| Input | Output | ✓ |
|-------|--------|---|
| `alice   ` / `sMitH` | `Hello, Alice Smith!` | ✅ |
| `bOB` / ` jones` | `Hello, Bob Jones!` | ✅ |
| `  JANE  ` / `DOE` | `Hello, Jane Doe!` | ✅ |

---

## Notizen

- **`.strip()`:** Entfernt Leerzeichen am Anfang/Ende
- **`.title()`:** Erster Buchstabe groß, Rest klein → `"jOHN"` → `"John"`
- **f-String:** `f"Text {variable}"` für formatierte Ausgabe
