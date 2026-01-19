# Fortgeschrittenes SQL - Kategorisierung und Zusammenfassung

## Kategorisierung der Themen

|**Kategorie**|**Begriff**|**Bedeutung**|
|---|---|---|
|**Verwendete Tools**|DB Browser for SQLite|Grafisches Tool zum Ausführen komplexer SQL-Abfragen mit JOIN-Operationen|
||SQL Query Editor|Editor zum Schreiben und Testen von mehrzeiligen SQL-Abfragen|
||Result Viewer|Anzeige-Tool für Abfrageergebnisse mit mehreren verknüpften Tabellen|
||Table Designer|Interface zur Planung und Visualisierung von Tabellenbeziehungen|
|**Technische Fachbegriffe**|JOIN|SQL-Klausel zum Kombinieren von Zeilen aus zwei oder mehr Tabellen|
||INNER JOIN|Join-Typ, der nur übereinstimmende Zeilen aus beiden Tabellen zurückgibt|
||LEFT JOIN (LEFT OUTER JOIN)|Join-Typ, der alle Zeilen der linken Tabelle behält, auch ohne Übereinstimmung|
||RIGHT JOIN (RIGHT OUTER JOIN)|Join-Typ, der alle Zeilen der rechten Tabelle behält, auch ohne Übereinstimmung|
||FULL OUTER JOIN|Join-Typ, der alle Zeilen beider Tabellen behält, unabhängig von Übereinstimmungen|
||Join Condition (ON-Klausel)|Bedingung, die angibt, wie Tabellen verknüpft werden (z.B. ON table1.id = table2.id)|
||Common Column|Gemeinsame Spalte zwischen Tabellen für die Verknüpfung (oft eine ID)|
||NULL|Repräsentiert fehlende oder unbekannte Werte (nicht 0, nicht leerer String)|
||IS NULL / IS NOT NULL|SQL-Operatoren zum Prüfen auf fehlende bzw. vorhandene Werte|
||Aggregate Functions|Funktionen zur Berechnung über mehrere Zeilen (COUNT, SUM, AVG, MIN, MAX)|
||COUNT()|Zählt Anzahl der Zeilen (COUNT(*) = alle Zeilen, COUNT(column) = nicht-NULL Werte)|
||SUM()|Summiert numerische Werte einer Spalte|
||AVG()|Berechnet Durchschnitt der Werte einer Spalte|
||MIN() / MAX()|Findet kleinsten bzw. größten Wert einer Spalte|
||GROUP BY|Gruppiert Zeilen mit gleichen Werten für Aggregat-Berechnungen|
||HAVING|Filtert Gruppen nach Aggregat-Bedingungen (nach GROUP BY)|
||Alias (AS)|Gibt berechneten Spalten oder Tabellen einen alternativen Namen|
||Expression|Berechnungsausdruck in SQL (z.B. price * 1.19)|
||Redundanz|Unnötige Wiederholung von Daten (wird durch mehrere Tabellen vermieden)|
||Venn-Diagramm-Logik|Visuelle Darstellung von JOIN-Operationen (Überschneidungsbereiche)|
||Query Execution Order|Logische Reihenfolge der Abfrageverarbeitung (FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY → LIMIT)|
|**Wichtige Vokabeln**|Left Table (Linke Tabelle)|Die erste Tabelle in der FROM-Klausel bei JOIN-Operationen|
||Right Table (Rechte Tabelle)|Die zweite Tabelle in der JOIN-Klausel|
||Match (Übereinstimmung)|Zeilen mit gleichen Werten in der Join-Spalte|
||Related Column (Verknüpfte Spalte)|Spalte, über die Tabellen verbunden werden|
||Derived Information|Aus bestehenden Daten berechnete neue Informationen|
||Arithmetic Operations|Rechenoperationen (+, -, *, /) in SQL-Abfragen|
||String Concatenation|Verkettung von Textwerten (mit|
||Summary Value|Zusammenfassender Einzelwert aus mehreren Zeilen (z.B. Summe)|
||Grouping|Zusammenfassen von Zeilen mit gemeinsamen Eigenschaften|
||Filter (Filtern)|Einschränken von Ergebnissen nach Bedingungen|
||Before Grouping (Vor Gruppierung)|WHERE filtert einzelne Zeilen vor der Gruppierung|
||After Grouping (Nach Gruppierung)|HAVING filtert Gruppen nach Aggregation|
||Absence of Information|NULL als "Fehlen von Information", nicht als Wert|
||Integer Division|Ganzzahlige Division (z.B. 5/2 = 2 statt 2.5)|
||Floating-Point Division|Division mit Dezimalzahlen (z.B. 5/2.0 = 2.5)|
||Distinct (Eindeutig)|Entfernt Duplikate aus Ergebnissen|

---

## 80/20 Zusammenfassung (Die wichtigsten 20%)

### Kernproblem: Daten über mehrere Tabellen verteilt

**Warum mehrere Tabellen?**

- **Vermeidung von Redundanz**: Kundenadressen nicht bei jeder Bestellung wiederholen
- **Datenkonsistenz**: Änderungen nur an einer Stelle nötig
- **Effizienz**: Weniger Speicherplatz, schnellere Updates

**Lösung**: JOIN-Operationen verbinden Tabellen über gemeinsame Spalten (meist IDs)

---

### JOIN-Operationen: Tabellen verknüpfen

#### 1. INNER JOIN (80% aller Anwendungsfälle)

**Konzept**: Nur Zeilen mit Übereinstimmung in BEIDEN Tabellen

**Grundstruktur**:

```sql
SELECT tabelle1.spalte, tabelle2.spalte
FROM tabelle1
INNER JOIN tabelle2 ON tabelle1.gemeinsame_spalte = tabelle2.gemeinsame_spalte;
```

**Beispiel** (Mitarbeiter + Abteilungen):

```sql
SELECT Employees.name, Departments.dept_name
FROM Employees
INNER JOIN Departments ON Employees.dept_id = Departments.dept_id;
```

**Ergebnis**: Nur Mitarbeiter MIT zugewiesener Abteilung (David mit dept_id=NULL fällt weg)

**Venn-Diagramm**: Die Überschneidungsfläche zweier Kreise

---

#### 2. LEFT JOIN (wichtigste OUTER JOIN-Variante)

**Konzept**: ALLE Zeilen der linken Tabelle + passende Zeilen der rechten Tabelle

**Wann verwenden?**

- "Zeige alle Mitarbeiter, auch die ohne Abteilung"
- "Liste alle Kunden, auch ohne Bestellungen"

**Beispiel**:

```sql
SELECT Employees.name, Departments.dept_name
FROM Employees
LEFT JOIN Departments ON Employees.dept_id = Departments.dept_id;
```

**Ergebnis**: David erscheint jetzt mit dept_name=NULL

**Merksatz**: LEFT JOIN behält die LINKE (FROM) Tabelle vollständig

---

#### 3. RIGHT JOIN & FULL OUTER JOIN (selten verwendet)

- **RIGHT JOIN**: Alle Zeilen der rechten Tabelle (kann meist als LEFT JOIN umgeschrieben werden)
- **FULL OUTER JOIN**: Alle Zeilen beider Tabellen (nicht in allen Datenbanken verfügbar)

---

### NULL-Werte: Die Abwesenheit von Information

**Kritische Eigenschaften**:

- NULL ≠ 0
- NULL ≠ leerer String ""
- NULL ≠ NULL (Vergleich ergibt UNKNOWN/FALSE)

**Richtige Prüfung**:

```sql
WHERE dept_id IS NULL        -- Findet fehlende Werte
WHERE dept_id IS NOT NULL    -- Findet vorhandene Werte
```

**Falsch** (funktioniert NICHT):

```sql
WHERE dept_id = NULL         -- Funktioniert nicht!
```

---

### Berechnungen in Abfragen: Expressions

**Arithmetische Operationen**:

```sql
SELECT 
    item_name,
    price,
    price * 1.19 AS price_incl_tax    -- Berechnung + Alias
FROM Products;
```

**String-Verkettung**:

```sql
SELECT first_name || ' ' || last_name AS full_name
FROM Employees;
```

**AS-Keyword**: Gibt berechneten Spalten lesbare Namen

---

### Aggregatfunktionen: Zusammenfassungen berechnen

#### Die 5 wichtigsten Aggregatfunktionen:

1. **COUNT(*)**: Zählt alle Zeilen
2. **COUNT(spalte)**: Zählt Zeilen mit Nicht-NULL-Werten
3. **SUM(spalte)**: Summiert Werte
4. **AVG(spalte)**: Berechnet Durchschnitt
5. **MIN(spalte) / MAX(spalte)**: Findet kleinsten/größten Wert

**Einfaches Beispiel**:

```sql
SELECT 
    COUNT(*) AS total_employees,
    MAX(employee_id) AS highest_id
FROM Employees;
```

---

### GROUP BY: Aggregation pro Gruppe

**Konzept**: Teile Daten in Gruppen und berechne für jede Gruppe

**Grundstruktur**:

```sql
SELECT spalte_gruppierung, AGGREGAT(spalte) AS alias
FROM tabelle
WHERE /* Filter EINZELNE Zeilen */
GROUP BY spalte_gruppierung
HAVING /* Filter GRUPPEN */
ORDER BY /* Sortierung */;
```

**Beispiel** - Mitarbeiter pro Abteilung:

```sql
SELECT dept_id, COUNT(*) AS num_employees
FROM Employees
WHERE dept_id IS NOT NULL
GROUP BY dept_id;
```

**Ergebnis**:

- dept_id=10: 2 Mitarbeiter
- dept_id=20: 1 Mitarbeiter

**Goldene Regel**: Jede Spalte in SELECT (außer Aggregaten) MUSS in GROUP BY stehen

---

### WHERE vs. HAVING: Der kritische Unterschied

|**WHERE**|**HAVING**|
|---|---|
|Filtert EINZELNE Zeilen|Filtert GRUPPEN|
|VOR Gruppierung|NACH Gruppierung|
|Kann KEINE Aggregatfunktionen verwenden|Kann Aggregatfunktionen verwenden|

**WHERE-Beispiel**:

```sql
WHERE dept_id = 10          -- Filtert Zeilen vor Gruppierung
```

**HAVING-Beispiel**:

```sql
HAVING COUNT(*) > 5         -- Filtert Gruppen nach Aggregation
```

---

### Logische Ausführungsreihenfolge (WICHTIG!)

**Sie schreiben**:

```sql
SELECT ... FROM ... WHERE ... GROUP BY ... HAVING ... ORDER BY ... LIMIT
```

**Datenbank verarbeitet**:

1. **FROM / JOIN** → Tabellen kombinieren
2. **WHERE** → Einzelne Zeilen filtern
3. **GROUP BY** → Zeilen gruppieren
4. **HAVING** → Gruppen filtern
5. **SELECT** → Spalten auswählen & berechnen
6. **DISTINCT** → Duplikate entfernen
7. **ORDER BY** → Sortieren
8. **LIMIT** → Anzahl begrenzen

**Warum wichtig?**: Erklärt, warum Aggregatfunktionen nicht in WHERE erlaubt sind (Aggregation passiert erst später bei GROUP BY)

---

### Praktische Kombinationen

#### JOIN + GROUP BY (häufiges Muster):

```sql
SELECT Departments.dept_name, COUNT(*) AS num_employees
FROM Employees
INNER JOIN Departments ON Employees.dept_id = Departments.dept_id
GROUP BY Departments.dept_name;
```

**Ergebnis**: Anzahl Mitarbeiter pro Abteilungsname (statt nur dept_id)

---

### Merksätze für die Praxis

1. **INNER JOIN** = "Nur Übereinstimmungen" (Schnittmenge)
2. **LEFT JOIN** = "Alle von links, passende von rechts"
3. **NULL prüfen** = Immer IS NULL/IS NOT NULL verwenden
4. **GROUP BY Regel** = Alles in SELECT (außer Aggregate) muss in GROUP BY
5. **WHERE vor HAVING** = WHERE filtert Zeilen, HAVING filtert Gruppen
6. **Ausführungsreihenfolge** = FROM → WHERE → GROUP BY → HAVING → SELECT

---

### Relevanz für Cybersecurity

- **Log-Analyse mit JOINs**: Verknüpfung von User-Logs mit IP-Adressen und Geräte-Informationen
- **Anomalie-Erkennung**: GROUP BY + HAVING für ungewöhnliche Aktivitätsmuster (z.B. "mehr als 100 Login-Versuche")
- **Audit-Trails**: JOIN mehrerer Tabellen zur Rekonstruktion von Ereignisketten
- **Threat Intelligence**: Aggregation von Bedrohungsdaten über verschiedene Quellen
- **Access Control**: LEFT JOIN zur Identifizierung von Nutzern OHNE zugewiesene Berechtigungen (NULL-Werte)