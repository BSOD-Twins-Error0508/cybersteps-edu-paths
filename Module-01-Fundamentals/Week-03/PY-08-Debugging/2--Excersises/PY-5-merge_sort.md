# 🐍 Merge Sort - Divide & Conquer Sortierung

**Kurs:** Fachinformatiker Ausbildung | **Datum:** 19.01.2026

---

## Aufgabe

**Ziel:** Sortiere eine Liste mit dem Merge-Sort-Algorithmus (Divide & Conquer).

**Anforderungen:**
- Funktion: `merge_sort(arr)`
- Rückgabe: Sortierte Liste (aufsteigend)
- Edge Cases: Leere Liste → `[]`

---

## Lösung

```python
def merge_sort(arr):
    # Basisfall: 0 oder 1 Element
    if len(arr) <= 1:          # Fix: <= 1 statt < 1
        return arr             # Fix: arr statt None
    
    # Teilen
    mid = len(arr) // 2        # Fix: ohne + 1
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    
    # Zusammenführen
    merged = []
    i = j = 0
    
    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            merged.append(left[i])   # Fix: left[i] bei <=
            i += 1                   # Fix: i erhöhen
        else:
            merged.append(right[j])  # Fix: right[j] bei >
            j += 1                   # Fix: j erhöhen
    
    # Rest anhängen
    while i < len(left):       # Fix: < statt <=
        merged.append(left[i])
        i += 1
    
    while j < len(right):
        merged.append(right[j])
        j += 1
    
    return merged
```

---

## Tests

| Input | Erwartet | Ergebnis | ✓ |
|-------|----------|----------|---|
| `[3, 1, 4, 1, 5, 9, 2, 6]` | [1, 1, 2, 3, 4, 5, 6, 9] | [1, 1, 2, 3, 4, 5, 6, 9] | ✅ |
| `[]` | [] | [] | ✅ |
| `[5]` | [5] | [5] | ✅ |

---

## Notizen

- **Fehler 1:** Basisfall `< 1` → `<= 1` (auch 1 Element ist fertig)
- **Fehler 2:** `return None` → `return arr` (leere/einzelne Liste zurückgeben)
- **Fehler 3:** `// 2 + 1` → `// 2` (falsche Teilung)
- **Fehler 4:** Vertauschte append-Logik im Merge-Schritt
- **Fehler 5:** `i <= len(left)` → `i < len(left)` (IndexError vermeiden)
- **Komplexität:** O(n log n) Zeit, O(n) Speicher
