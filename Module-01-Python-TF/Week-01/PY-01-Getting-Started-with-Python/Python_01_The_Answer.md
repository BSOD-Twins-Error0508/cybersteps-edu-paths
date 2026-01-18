# 🐍 The Answer (Einfache Berechnung)

**Kurs:** TF1 - Python Grundlagen | **Datum:** 18.01.2026

---

## Aufgabe

**Ziel:** Berechnung von `6 * 7` und Ausgabe mit formatiertem Text.

**Anforderungen:**
- Berechne: `6 * 7`
- Ausgabe: `The answer is: 42`
- Verwende: `print()` Funktion

---

## Lösung

```python
answer = 6 * 7
print(f"The answer is: {answer}")
```

**Alternative Lösungen:**
```python
# Mit Komma-Separator
answer = 6 * 7
print("The answer is:", answer)

# Direkte Berechnung
print(f"The answer is: {6 * 7}")
```

---

## Tests

| Input | Erwartet | Ergebnis | ✓ |
|-------|----------|----------|---|
| (keine) | `The answer is: 42` | `The answer is: 42` | ✅ |

---

## Notizen

- **Konzept:** Variablenzuweisung und f-Strings
- **f-String:** `f"Text {variable}"` fügt Variablenwert ein
- **Alternative:** `print("Text", var)` fügt automatisch Leerzeichen ein
- **Tipp:** f-Strings sind die modernste Methode (Python 3.6+)
