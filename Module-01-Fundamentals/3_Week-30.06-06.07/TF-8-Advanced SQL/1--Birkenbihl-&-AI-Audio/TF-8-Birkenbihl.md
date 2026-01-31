Welcome back to SQL! In the previous lesson, we learned the basics of retrieving data from a single table using SELECT, filtering with WHERE, sorting with ORDER BY, and limiting results with LIMIT. Willkommen zurück zu SQL! In der vorherigen Lektion haben wir die Grundlagen des Abrufens von Daten aus einer einzelnen Tabelle mit SELECT gelernt, das Filtern mit WHERE, das Sortieren mit ORDER BY und das Begrenzen von Ergebnissen mit LIMIT.

That's a great start, but most real-world databases organize information across multiple tables. Das ist ein großartiger Anfang, aber die meisten realen Datenbanken organisieren Informationen über mehrere Tabellen hinweg.

Why? It avoids redundancy, like storing a customer's full address with every single order they make, and keeps data consistent. Warum? Es vermeidet Redundanz, wie das Speichern der vollständigen Adresse eines Kunden bei jeder einzelnen Bestellung, die er aufgibt, und hält die Daten konsistent.

This lesson focuses on how to work with data from multiple tables simultaneously and how to perform calculations and summaries directly within your SQL queries. Diese Lektion konzentriert sich darauf, wie man gleichzeitig mit Daten aus mehreren Tabellen arbeitet und wie man Berechnungen und Zusammenfassungen direkt in SQL-Abfragen durchführt.

We'll cover techniques essential for extracting more complex and meaningful information. Wir werden Techniken behandeln, die für das Extrahieren komplexerer und aussagekräftigerer Informationen wesentlich sind.

Combining Tables with JOINs. Tabellen mit JOINs kombinieren.

The core idea behind relational databases is the relation, how different pieces of data connect. Die Kernidee hinter relationalen Datenbanken ist die Beziehung, wie verschiedene Datenstücke miteinander verbunden sind.

SQL provides JOIN clauses to combine rows from two or more tables based on a related column between them. SQL bietet JOIN-Klauseln, um Zeilen aus zwei oder mehr Tabellen basierend auf einer verwandten Spalte zwischen ihnen zu kombinieren.

This lets you pull together a complete picture from scattered information. Dies ermöglicht es dir, ein vollständiges Bild aus verstreuten Informationen zusammenzustellen.

INNER JOIN. INNER JOIN.

The most fundamental join is the INNER JOIN. Der grundlegendste Join ist der INNER JOIN.

It returns only the rows where there is a match in both tables based on the specified join condition. Er gibt nur die Zeilen zurück, bei denen es eine Übereinstimmung in beiden Tabellen basierend auf der angegebenen Join-Bedingung gibt.

If a row in one table doesn't have a corresponding match in the other, it's left out of the result. Wenn eine Zeile in einer Tabelle keine entsprechende Übereinstimmung in der anderen hat, wird sie aus dem Ergebnis ausgeschlossen.

Think of it like the overlapping area in a Venn diagram. Denk daran wie an den überlappenden Bereich in einem Venn-Diagramm.

Syntax: SELECT table one dot column name, table two dot column name FROM table one INNER JOIN table two ON table one dot common column equals table two dot common column. Syntax: SELECT Tabelle eins Punkt Spaltenname, Tabelle zwei Punkt Spaltenname FROM Tabelle eins INNER JOIN Tabelle zwei ON Tabelle eins Punkt gemeinsame Spalte gleich Tabelle zwei Punkt gemeinsame Spalte.

FROM table one: The first table, sometimes called the left table. FROM Tabelle eins: Die erste Tabelle, manchmal die linke Tabelle genannt.

INNER JOIN table two: The second table, the right table, you want to connect. INNER JOIN Tabelle zwei: Die zweite Tabelle, die rechte Tabelle, die du verbinden möchtest.

ON table one dot common column equals table two dot common column: The join condition. ON Tabelle eins Punkt gemeinsame Spalte gleich Tabelle zwei Punkt gemeinsame Spalte: Die Join-Bedingung.

This tells the database how to link the tables. Dies sagt der Datenbank, wie sie die Tabellen verknüpfen soll.

It compares the values in common column from both tables and combines rows where these values are equal. Sie vergleicht die Werte in der gemeinsamen Spalte aus beiden Tabellen und kombiniert Zeilen, bei denen diese Werte gleich sind.

Often, this common column is an ID field, like user underscore id. Oft ist diese gemeinsame Spalte ein ID-Feld, wie user Unterstrich id.

Example: Imagine we have Employees and Departments tables. Beispiel: Stell dir vor, wir haben Mitarbeiter- und Abteilungstabellen.

Employees table: employee underscore id one hundred one, name Alice, dept underscore id ten. Mitarbeitertabelle: Mitarbeiter Unterstrich id einhunderteins, Name Alice, Abteilung Unterstrich id zehn.

Employee underscore id one hundred two, name Bob, dept underscore id twenty. Mitarbeiter Unterstrich id einhundertzwei, Name Bob, Abteilung Unterstrich id zwanzig.

Employee underscore id one hundred three, name Charlie, dept underscore id ten. Mitarbeiter Unterstrich id einhundertdrei, Name Charlie, Abteilung Unterstrich id zehn.

Employee underscore id one hundred four, name David, dept underscore id NULL. Mitarbeiter Unterstrich id einhundertvier, Name David, Abteilung Unterstrich id NULL.

Departments table: dept underscore id ten, dept underscore name Engineering, location Building A. Abteilungstabelle: Abteilung Unterstrich id zehn, Abteilung Unterstrich Name Engineering, Standort Gebäude A.

Dept underscore id twenty, dept underscore name Sales, location Building B. Abteilung Unterstrich id zwanzig, Abteilung Unterstrich Name Vertrieb, Standort Gebäude B.

Dept underscore id thirty, dept underscore name Marketing, location Building C. Abteilung Unterstrich id dreißig, Abteilung Unterstrich Name Marketing, Standort Gebäude C.

To list employees alongside their department names: SELECT Employees dot name, Departments dot dept underscore name FROM Employees INNER JOIN Departments ON Employees dot dept underscore id equals Departments dot dept underscore id. Um Mitarbeiter zusammen mit ihren Abteilungsnamen aufzulisten: SELECT Mitarbeiter Punkt Name, Abteilungen Punkt Abteilung Unterstrich Name FROM Mitarbeiter INNER JOIN Abteilungen ON Mitarbeiter Punkt Abteilung Unterstrich id gleich Abteilungen Punkt Abteilung Unterstrich id.

Result: name Alice, dept underscore name Engineering. Name Bob, dept underscore name Sales. Name Charlie, dept underscore name Engineering. Ergebnis: Name Alice, Abteilung Unterstrich Name Engineering. Name Bob, Abteilung Unterstrich Name Vertrieb. Name Charlie, Abteilung Unterstrich Name Engineering.

Notice: David is missing because his dept underscore id is NULL, which doesn't match any dept underscore id in Departments. Beachte: David fehlt, weil seine Abteilung Unterstrich id NULL ist, was keiner Abteilung Unterstrich id in Abteilungen entspricht.

The Marketing department is missing because no employee in the Employees table has dept underscore id thirty. Die Marketing-Abteilung fehlt, weil kein Mitarbeiter in der Mitarbeitertabelle die Abteilung Unterstrich id dreißig hat.

OUTER JOINs, LEFT, RIGHT, FULL. OUTER JOINs, LEFT, RIGHT, FULL.

Sometimes you want to keep all rows from one table, even if they don't have a match in the other. Manchmal möchtest du alle Zeilen aus einer Tabelle behalten, auch wenn sie keine Übereinstimmung in der anderen haben.

OUTER JOINs are used for this. OUTER JOINs werden dafür verwendet.

LEFT JOIN or LEFT OUTER JOIN: Returns all rows from the left table, FROM table, and the matched rows from the right table, LEFT JOIN table. LEFT JOIN oder LEFT OUTER JOIN: Gibt alle Zeilen aus der linken Tabelle zurück, FROM Tabelle, und die übereinstimmenden Zeilen aus der rechten Tabelle, LEFT JOIN Tabelle.

If there's no match in the right table, the columns selected from the right table will have NULL values for that row. Wenn es keine Übereinstimmung in der rechten Tabelle gibt, haben die ausgewählten Spalten aus der rechten Tabelle NULL-Werte für diese Zeile.

RIGHT JOIN or RIGHT OUTER JOIN: Returns all rows from the right table and the matched rows from the left table. RIGHT JOIN oder RIGHT OUTER JOIN: Gibt alle Zeilen aus der rechten Tabelle und die übereinstimmenden Zeilen aus der linken Tabelle zurück.

If there's no match in the left table, its columns will be NULL. Wenn es keine Übereinstimmung in der linken Tabelle gibt, werden ihre Spalten NULL sein.

Often, you can rewrite a RIGHT JOIN as a LEFT JOIN by swapping the table order, which many find more intuitive. Oft kann man einen RIGHT JOIN als LEFT JOIN umschreiben, indem man die Tabellenreihenfolge vertauscht, was viele intuitiver finden.

FULL OUTER JOIN: Returns all rows when there is a match in either the left or right table. FULL OUTER JOIN: Gibt alle Zeilen zurück, wenn es eine Übereinstimmung in der linken oder rechten Tabelle gibt.

If a row from one table doesn't have a match in the other, the columns from the non-matching table will be NULL. Wenn eine Zeile aus einer Tabelle keine Übereinstimmung in der anderen hat, werden die Spalten aus der nicht übereinstimmenden Tabelle NULL sein.

Not all database systems support FULL OUTER JOIN. Nicht alle Datenbanksysteme unterstützen FULL OUTER JOIN.

LEFT JOIN Example using Employees and Departments. LEFT JOIN Beispiel mit Mitarbeitern und Abteilungen.

Find all employees and their department names, including employees without an assigned department. Finde alle Mitarbeiter und ihre Abteilungsnamen, einschließlich Mitarbeiter ohne zugewiesene Abteilung.

SELECT Employees dot name, Departments dot dept underscore name FROM Employees LEFT JOIN Departments ON Employees dot dept underscore id equals Departments dot dept underscore id. SELECT Mitarbeiter Punkt Name, Abteilungen Punkt Abteilung Unterstrich Name FROM Mitarbeiter LEFT JOIN Abteilungen ON Mitarbeiter Punkt Abteilung Unterstrich id gleich Abteilungen Punkt Abteilung Unterstrich id.

Result: name Alice, dept underscore name Engineering. Name Bob, dept underscore name Sales. Name Charlie, dept underscore name Engineering. Name David, dept underscore name NULL. Ergebnis: Name Alice, Abteilung Unterstrich Name Engineering. Name Bob, Abteilung Unterstrich Name Vertrieb. Name Charlie, Abteilung Unterstrich Name Engineering. Name David, Abteilung Unterstrich Name NULL.

Notice: David is now included, with NULL for dept underscore name because his dept underscore id didn't match any department. Beachte: David ist jetzt enthalten, mit NULL für Abteilung Unterstrich Name, weil seine Abteilung Unterstrich id mit keiner Abteilung übereinstimmte.

Think about it. Denk darüber nach.

Using the Employees and Departments tables: How would you write a query to show all departments and the names of employees in them, including departments that currently have no employees listed? Mit den Mitarbeiter- und Abteilungstabellen: Wie würdest du eine Abfrage schreiben, um alle Abteilungen und die Namen der Mitarbeiter darin zu zeigen, einschließlich Abteilungen, die derzeit keine Mitarbeiter aufgelistet haben?

Hint: Which table should be the left table if using LEFT JOIN, or consider RIGHT JOIN? Hinweis: Welche Tabelle sollte die linke Tabelle sein, wenn LEFT JOIN verwendet wird, oder erwäge RIGHT JOIN?

What practical scenario might lead you to prefer a LEFT JOIN over an INNER JOIN when analyzing employee data? Welches praktische Szenario könnte dich dazu bringen, einen LEFT JOIN einem INNER JOIN vorzuziehen, wenn du Mitarbeiterdaten analysierst?

A Short Note on NULLs. Eine kurze Anmerkung zu NULLs.

As seen above, NULL represents a missing or unknown value. Wie oben gesehen, repräsentiert NULL einen fehlenden oder unbekannten Wert.

It's crucial to remember NULL is not zero, not an empty string, and not a space. Es ist entscheidend zu bedenken, dass NULL nicht null ist, keine leere Zeichenkette und kein Leerzeichen.

It's the absence of information. Es ist die Abwesenheit von Information.

Comparisons: Comparing anything to NULL using standard operators, equals, not equals, less than, greater than, results in UNKNOWN, which usually acts like FALSE in filtering with WHERE. Vergleiche: Alles mit NULL zu vergleichen unter Verwendung von Standardoperatoren, gleich, ungleich, kleiner als, größer als, ergibt UNKNOWN, was normalerweise wie FALSE beim Filtern mit WHERE wirkt.

Even NULL equals NULL is not considered true. Selbst NULL gleich NULL wird nicht als wahr betrachtet.

Checking for NULL: To find rows where a value is missing, use IS NULL. Auf NULL prüfen: Um Zeilen zu finden, bei denen ein Wert fehlt, verwende IS NULL.

To find rows where a value is present, use IS NOT NULL. Um Zeilen zu finden, bei denen ein Wert vorhanden ist, verwende IS NOT NULL.

Example: Find employees not assigned to a department. Beispiel: Finde Mitarbeiter, die keiner Abteilung zugewiesen sind.

SELECT name FROM Employees WHERE dept underscore id IS NULL. SELECT Name FROM Mitarbeiter WHERE Abteilung Unterstrich id IS NULL.

Result: name David. Ergebnis: Name David.

Think about it. Denk darüber nach.

Why is it important that NULL equals NULL evaluates to UNKNOWN, effectively false? Warum ist es wichtig, dass NULL gleich NULL zu UNKNOWN ausgewertet wird, effektiv falsch?

How might database operations behave unexpectedly if NULL was treated as equal to other NULLs in standard comparisons? Wie könnten sich Datenbankoperationen unerwartet verhalten, wenn NULL in Standardvergleichen als gleich zu anderen NULLs behandelt würde?

Queries with Expressions. Abfragen mit Ausdrücken.

You can perform calculations and manipulate data directly within your SELECT statement. Du kannst Berechnungen durchführen und Daten direkt in deiner SELECT-Anweisung manipulieren.

This is useful for creating derived information on the fly. Dies ist nützlich, um abgeleitete Informationen spontan zu erstellen.

Arithmetic: Use plus, minus, asterisk, slash. Arithmetik: Verwende Plus, Minus, Sternchen, Schrägstrich.

Be mindful of integer division versus floating-point division, for example, five divided by two might be two in some SQL dialects, while five divided by two point zero would be two point five. Sei dir der Ganzzahldivision gegenüber Fließkommadivision bewusst, zum Beispiel könnte fünf geteilt durch zwei in einigen SQL-Dialekten zwei sein, während fünf geteilt durch zwei Punkt null zwei Punkt fünf wäre.

String Concatenation: Often two vertical bars or plus, depends on the SQL dialect, or functions like CONCAT. Zeichenkettenverkettung: Oft zwei vertikale Balken oder Plus, abhängig vom SQL-Dialekt, oder Funktionen wie CONCAT.

Aliases using AS: Give your calculated columns meaningful names using AS. Aliase mit AS: Gib deinen berechneten Spalten aussagekräftige Namen mit AS.

Example: Suppose a Products table has item underscore name and price. Beispiel: Angenommen, eine Produktetabelle hat Artikel Unterstrich Name und Preis.

Show the price including a nineteen percent tax. Zeige den Preis einschließlich neunzehn Prozent Steuer.

SELECT item underscore name, price, price times one point one nine AS price underscore incl underscore tax FROM Products. SELECT Artikel Unterstrich Name, Preis, Preis mal eins Punkt eins neun AS Preis Unterstrich inkl Unterstrich Steuer FROM Produkte.

The result will have three columns: item underscore name, price, and the calculated price underscore incl underscore tax. Das Ergebnis wird drei Spalten haben: Artikel Unterstrich Name, Preis und den berechneten Preis Unterstrich inkl Unterstrich Steuer.

Try it yourself. Probiere es selbst aus.

Given a LogEvents table with event underscore id, start underscore timestamp, and end underscore timestamp, write a query to show the event underscore id and the duration of the event in seconds. Angenommen, eine LogEvents-Tabelle mit Ereignis Unterstrich id, Start Unterstrich Zeitstempel und Ende Unterstrich Zeitstempel, schreibe eine Abfrage, um die Ereignis Unterstrich id und die Dauer des Ereignisses in Sekunden zu zeigen.

Assume your SQL dialect allows subtracting timestamps to get an interval, and you might need a function to extract seconds from that interval. Nimm an, dein SQL-Dialekt erlaubt das Subtrahieren von Zeitstempeln, um ein Intervall zu erhalten, und du benötigst möglicherweise eine Funktion, um Sekunden aus diesem Intervall zu extrahieren.

The exact function varies, for example, TIMESTAMPDIFF with SECOND, start underscore timestamp, end underscore timestamp in MySQL, or direct subtraction might yield an interval type in PostgreSQL. Die genaue Funktion variiert, zum Beispiel TIMESTAMPDIFF mit SECOND, Start Unterstrich Zeitstempel, Ende Unterstrich Zeitstempel in MySQL, oder direkte Subtraktion könnte einen Intervalltyp in PostgreSQL ergeben.

Name the duration column duration underscore seconds. Benenne die Dauerspalte Dauer Unterstrich Sekunden.

Focus on the structure, don't worry about the exact time function name. Konzentriere dich auf die Struktur, mach dir keine Sorgen über den genauen Namen der Zeitfunktion.

Queries with Aggregates. Abfragen mit Aggregaten.

Aggregate functions perform calculations across a set of rows, returning a single summary value. Aggregatfunktionen führen Berechnungen über eine Menge von Zeilen durch und geben einen einzelnen Zusammenfassungswert zurück.

Common Aggregate Functions. Häufige Aggregatfunktionen.

COUNT with column: Counts rows where column is not NULL. COUNT mit Spalte: Zählt Zeilen, bei denen die Spalte nicht NULL ist.

COUNT with asterisk: Counts the total number of rows selected. COUNT mit Sternchen: Zählt die Gesamtzahl der ausgewählten Zeilen.

SUM with column: Sums the values in column, ignores NULLs. SUM mit Spalte: Summiert die Werte in der Spalte, ignoriert NULLs.

AVG with column: Calculates the average of values in column, ignores NULLs. AVG mit Spalte: Berechnet den Durchschnitt der Werte in der Spalte, ignoriert NULLs.

MIN with column: Finds the minimum value in column. MIN mit Spalte: Findet den Minimalwert in der Spalte.

MAX with column: Finds the maximum value in column. MAX mit Spalte: Findet den Maximalwert in der Spalte.

Example: Find the total number of employees and the highest employee underscore id. Beispiel: Finde die Gesamtzahl der Mitarbeiter und die höchste Mitarbeiter Unterstrich id.

SELECT COUNT with asterisk AS total underscore employees, MAX with employee underscore id AS highest underscore id FROM Employees. SELECT COUNT mit Sternchen AS Gesamt Unterstrich Mitarbeiter, MAX mit Mitarbeiter Unterstrich id AS höchste Unterstrich id FROM Mitarbeiter.

Result: total underscore employees four, highest underscore id one hundred four. Ergebnis: Gesamt Unterstrich Mitarbeiter vier, höchste Unterstrich id einhundertvier.

Grouping Aggregates with GROUP BY. Aggregieren gruppieren mit GROUP BY.

Aggregates become much more powerful when combined with GROUP BY. Aggregate werden viel mächtiger, wenn sie mit GROUP BY kombiniert werden.

This clause groups rows that share the same value in specified columns, and then applies the aggregate function or functions to each group separately. Diese Klausel gruppiert Zeilen, die denselben Wert in angegebenen Spalten haben, und wendet dann die Aggregatfunktion oder Funktionen auf jede Gruppe separat an.

Syntax: SELECT column to group by, AGGREGATE underscore FUNCTION with column to aggregate AS alias FROM table name WHERE, optional, filter rows before grouping, GROUP BY column to group by, HAVING, optional, filter groups after aggregation, ORDER BY, optional, sort the final grouped results. Syntax: SELECT Spalte zum Gruppieren, AGGREGATE Unterstrich FUNCTION mit Spalte zum Aggregieren AS Alias FROM Tabellenname WHERE, optional, filtere Zeilen vor dem Gruppieren, GROUP BY Spalte zum Gruppieren, HAVING, optional, filtere Gruppen nach der Aggregation, ORDER BY, optional, sortiere die finalen gruppierten Ergebnisse.

Key Rule: Any column in the SELECT list that is not an aggregate function must be included in the GROUP BY clause. Schlüsselregel: Jede Spalte in der SELECT-Liste, die keine Aggregatfunktion ist, muss in der GROUP BY-Klausel enthalten sein.

Example: Count the number of employees in each department. Beispiel: Zähle die Anzahl der Mitarbeiter in jeder Abteilung.

SELECT dept underscore id, COUNT with asterisk AS num underscore employees FROM Employees WHERE dept underscore id IS NOT NULL, exclude David before grouping, GROUP BY dept underscore id. SELECT Abteilung Unterstrich id, COUNT mit Sternchen AS Anzahl Unterstrich Mitarbeiter FROM Mitarbeiter WHERE Abteilung Unterstrich id IS NOT NULL, schließe David vor dem Gruppieren aus, GROUP BY Abteilung Unterstrich id.

Result: dept underscore id ten, num underscore employees two. Dept underscore id twenty, num underscore employees one. Ergebnis: Abteilung Unterstrich id zehn, Anzahl Unterstrich Mitarbeiter zwei. Abteilung Unterstrich id zwanzig, Anzahl Unterstrich Mitarbeiter eins.

How it works: FROM Employees: Selects the table. Wie es funktioniert: FROM Mitarbeiter: Wählt die Tabelle aus.

WHERE dept underscore id IS NOT NULL: Filters out the row for David. WHERE Abteilung Unterstrich id IS NOT NULL: Filtert die Zeile für David heraus.

GROUP BY dept underscore id: Groups the remaining rows based on their dept underscore id, one group for ten, one for twenty. GROUP BY Abteilung Unterstrich id: Gruppiert die verbleibenden Zeilen basierend auf ihrer Abteilung Unterstrich id, eine Gruppe für zehn, eine für zwanzig.

SELECT dept underscore id, COUNT with asterisk: For each group, selects the dept underscore id and counts the rows within that group. SELECT Abteilung Unterstrich id, COUNT mit Sternchen: Wählt für jede Gruppe die Abteilung Unterstrich id aus und zählt die Zeilen innerhalb dieser Gruppe.

Think about it. Denk darüber nach.

What would the result of the previous query be if we removed the WHERE dept underscore id IS NOT NULL clause? Was wäre das Ergebnis der vorherigen Abfrage, wenn wir die WHERE Abteilung Unterstrich id IS NOT NULL Klausel entfernen würden?

Would NULL form its own group? The behavior might vary slightly between SQL databases, but often NULLs are grouped together. Würde NULL eine eigene Gruppe bilden? Das Verhalten kann zwischen SQL-Datenbanken leicht variieren, aber oft werden NULLs zusammen gruppiert.

How could you modify the query to show the department name instead of the dept underscore id, along with the employee count? Wie könntest du die Abfrage ändern, um den Abteilungsnamen anstelle der Abteilung Unterstrich id zusammen mit der Mitarbeiterzahl anzuzeigen?

Hint: You'll need a JOIN. Hinweis: Du wirst einen JOIN benötigen.

Order of Execution of a Query. Ausführungsreihenfolge einer Abfrage.

While you write SQL in a specific sequence, SELECT, FROM, WHERE, GROUP BY, HAVING, ORDER BY, the database logically processes it in a different order. Während du SQL in einer bestimmten Reihenfolge schreibst, SELECT, FROM, WHERE, GROUP BY, HAVING, ORDER BY, verarbeitet die Datenbank es logisch in einer anderen Reihenfolge.

Understanding this helps troubleshoot and write correct queries. Dies zu verstehen hilft bei der Fehlerbehebung und beim Schreiben korrekter Abfragen.

Logical Processing Order, Simplified. Logische Verarbeitungsreihenfolge, vereinfacht.

FROM slash JOIN: Determines the source tables and how they are combined. FROM Schrägstrich JOIN: Bestimmt die Quelltabellen und wie sie kombiniert werden.

WHERE: Filters individual rows based on conditions. WHERE: Filtert einzelne Zeilen basierend auf Bedingungen.

GROUP BY: Groups the filtered rows based on common values. GROUP BY: Gruppiert die gefilterten Zeilen basierend auf gemeinsamen Werten.

HAVING: Filters the groups themselves based on conditions, often involving aggregate functions. HAVING: Filtert die Gruppen selbst basierend auf Bedingungen, oft mit Aggregatfunktionen.

SELECT: Determines the final columns and calculates expressions slash aggregates for the remaining rows slash groups. SELECT: Bestimmt die finalen Spalten und berechnet Ausdrücke Schrägstrich Aggregate für die verbleibenden Zeilen Schrägstrich Gruppen.

DISTINCT: Removes duplicate rows from the result, if specified. DISTINCT: Entfernt doppelte Zeilen aus dem Ergebnis, falls angegeben.

ORDER BY: Sorts the final result set. ORDER BY: Sortiert die finale Ergebnismenge.

LIMIT slash OFFSET: Selects a subset of the sorted rows. LIMIT Schrägstrich OFFSET: Wählt eine Teilmenge der sortierten Zeilen aus.

Key takeaway: WHERE filters before grouping, HAVING filters after grouping. Wichtigste Erkenntnis: WHERE filtert vor dem Gruppieren, HAVING filtert nach dem Gruppieren.

You can't use an aggregate function, like COUNT with asterisk, in the WHERE clause because aggregation hasn't happened yet. Du kannst keine Aggregatfunktion, wie COUNT mit Sternchen, in der WHERE-Klausel verwenden, weil die Aggregation noch nicht stattgefunden hat.

You can use aggregates in the HAVING clause. Du kannst Aggregate in der HAVING-Klausel verwenden.

This pre-class material covers joining tables, handling missing data with NULL, calculating values within queries, and summarizing data using aggregates and grouping. Dieses Material vor dem Unterricht behandelt das Verknüpfen von Tabellen, den Umgang mit fehlenden Daten mit NULL, das Berechnen von Werten innerhalb von Abfragen und das Zusammenfassen von Daten mit Aggregaten und Gruppierung.

These are powerful tools for data analysis using SQL. Dies sind mächtige Werkzeuge für die Datenanalyse mit SQL.

Review these concepts to prepare for the hands-on session. Überprüfe diese Konzepte, um dich auf die praktische Sitzung vorzubereiten.

The slides for the live session can be viewed at a specific link. Die Folien für die Live-Sitzung können unter einem bestimmten Link angesehen werden.

Try not to peek before class, spoilers inside! Versuche nicht vor dem Unterricht zu spähen, Spoiler drinnen!