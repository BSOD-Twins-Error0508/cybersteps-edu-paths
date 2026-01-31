Welcome! Before our live session on Databases and SQL, please go through this material. Willkommen! Bitte arbeite dieses Material durch, bevor wir uns zur Live-Sitzung über Datenbanken und SQL treffen.

We'll explore how data is organized and accessed efficiently, a fundamental skill in many tech roles, including cybersecurity. Wir werden erforschen, wie Daten effizient organisiert und abgerufen werden, eine grundlegende Fähigkeit in vielen technischen Berufen, einschließlich Cybersicherheit.

What is Data? Was sind Daten?

In the context of computers, data is essentially information. Im Kontext von Computern sind Daten im Wesentlichen Informationen.

This could be anything: text, numbers, dates, images. Das kann alles sein: Text, Zahlen, Daten, Bilder.

Think about your contacts list. It contains names, text, phone numbers, numbers, maybe text, and maybe birthdays, dates. Denk an deine Kontaktliste. Sie enthält Namen, Text, Telefonnummern, Zahlen, vielleicht Text, und vielleicht Geburtstage, Daten.

A shopping website stores information about products, names, descriptions, prices, customers, names, addresses, and orders, product IDs, quantities, dates. Eine Shopping-Website speichert Informationen über Produkte, Namen, Beschreibungen, Preise, Kunden, Namen, Adressen, und Bestellungen, Produkt-IDs, Mengen, Daten.

All of this is data. All dies sind Daten.

Why Organize Data? Warum Daten organisieren?

Imagine trying to find a specific friend's phone number if all your contacts were just scribbled randomly on pieces of paper scattered around your room. Stell dir vor, du versuchst die Telefonnummer eines bestimmten Freundes zu finden, wenn alle deine Kontakte einfach zufällig auf Papierstücke gekritzelt wären, die in deinem Zimmer verstreut liegen.

It would be slow and frustrating! Das wäre langsam und frustrierend!

Computers face a similar challenge when dealing with large amounts of data. Computer stehen vor einer ähnlichen Herausforderung, wenn sie mit großen Datenmengen umgehen.

We need ways to store data reliably so it doesn't get lost. Wir brauchen Wege, Daten zuverlässig zu speichern, damit sie nicht verloren gehen.

Organize data logically so it makes sense. Daten logisch zu organisieren, damit sie Sinn ergeben.

Retrieve specific pieces of data quickly and easily. Bestimmte Datenstücke schnell und einfach abzurufen.

Update data when things change, like a friend's phone number. Daten zu aktualisieren, wenn sich Dinge ändern, wie die Telefonnummer eines Freundes.

Manage access to data, who can see or change what. Den Zugriff auf Daten zu verwalten, wer was sehen oder ändern kann.

This is where databases come in. Hier kommen Datenbanken ins Spiel.

What is a Database? Was ist eine Datenbank?

A database is an organized collection of data, stored electronically, designed for efficient storage, retrieval, and management. Eine Datenbank ist eine organisierte Sammlung von Daten, elektronisch gespeichert, konzipiert für effiziente Speicherung, Abruf und Verwaltung.

Think of it as a highly organized digital filing cabinet. Denk daran wie an einen hochorganisierten digitalen Aktenschrank.

Instead of random pieces of paper, a database uses structures to keep things tidy. Anstelle von zufälligen Papierstücken verwendet eine Datenbank Strukturen, um die Dinge ordentlich zu halten.

A very common structure, especially in what we call relational databases, is the table. Eine sehr häufige Struktur, besonders in dem, was wir relationale Datenbanken nennen, ist die Tabelle.

Relational Databases and Tables. Relationale Datenbanken und Tabellen.

A relational database organizes data into one or more tables. Eine relationale Datenbank organisiert Daten in eine oder mehrere Tabellen.

Table: A collection of related data entries organized in rows and columns. Tabelle: Eine Sammlung verwandter Dateneinträge, organisiert in Zeilen und Spalten.

Think of a spreadsheet. Denk an eine Tabellenkalkulation.

For example, we could have a Customers table. Zum Beispiel könnten wir eine Kunden-Tabelle haben.

Column or Field: Represents a specific type of information within a table. Spalte oder Feld: Repräsentiert eine bestimmte Art von Information innerhalb einer Tabelle.

Each column has a name and holds a particular data type, like text, number, date. Jede Spalte hat einen Namen und enthält einen bestimmten Datentyp, wie Text, Zahl, Datum.

In our Customers table, columns might be FirstName, LastName, Email, SignupDate. In unserer Kunden-Tabelle könnten Spalten sein: Vorname, Nachname, E-Mail, Anmeldedatum.

Note: We often add a unique identifier column, like CustomerID. Hinweis: Wir fügen oft eine eindeutige Identifikationsspalte hinzu, wie Kunden-ID.

Row or Record: Represents a single entry or item in the table. Zeile oder Datensatz: Repräsentiert einen einzelnen Eintrag oder ein Element in der Tabelle.

Each row contains the specific values for each column for that particular entry. Jede Zeile enthält die spezifischen Werte für jede Spalte für diesen bestimmten Eintrag.

A row in the Customers table would represent one specific customer. Eine Zeile in der Kunden-Tabelle würde einen bestimmten Kunden repräsentieren.

Here's a simplified example of a Customers table. Hier ist ein vereinfachtes Beispiel einer Kunden-Tabelle.

CustomerID one, FirstName Alice, LastName Smith, Email alice dot s at email dot com, SignupDate two thousand twenty-three, January fifteenth. Kunden-ID eins, Vorname Alice, Nachname Smith, E-Mail alice punkt s at email punkt com, Anmeldedatum zweitausenddreiundzwanzig, fünfzehnter Januar.

CustomerID two, FirstName Bob, LastName Jones, Email b dot jones at domain dot org, SignupDate two thousand twenty-three, February tenth. Kunden-ID zwei, Vorname Bob, Nachname Jones, E-Mail b punkt jones at domain punkt org, Anmeldedatum zweitausenddreiundzwanzig, zehnter Februar.

CustomerID three, FirstName Charlie, LastName Brown, Email charlie at mailservice dot net, SignupDate two thousand twenty-three, January fifteenth. Kunden-ID drei, Vorname Charlie, Nachname Brown, E-Mail charlie at mailservice punkt net, Anmeldedatum zweitausenddreiundzwanzig, fünfzehnter Januar.

Key Concepts. Schlüsselkonzepte.

Structured Data: Data organized in a predefined format, like tables with rows and columns. Strukturierte Daten: Daten, die in einem vordefinierten Format organisiert sind, wie Tabellen mit Zeilen und Spalten.

Relational databases primarily deal with structured data. Relationale Datenbanken befassen sich hauptsächlich mit strukturierten Daten.

Primary Key: A column or set of columns whose value uniquely identifies each row in a table. Primärschlüssel: Eine Spalte oder eine Gruppe von Spalten, deren Wert jede Zeile in einer Tabelle eindeutig identifiziert.

In the example above, CustomerID is likely the primary key because each customer has a unique ID. Im obigen Beispiel ist Kunden-ID wahrscheinlich der Primärschlüssel, weil jeder Kunde eine eindeutige ID hat.

No two rows can have the same CustomerID. Keine zwei Zeilen können dieselbe Kunden-ID haben.

Relational: The relational part comes from the ability to link or relate data between different tables. Relational: Der relationale Teil kommt von der Fähigkeit, Daten zwischen verschiedenen Tabellen zu verknüpfen oder in Beziehung zu setzen.

For instance, we might have another table called Orders with a CustomerID column. Zum Beispiel könnten wir eine weitere Tabelle namens Bestellungen haben mit einer Kunden-ID-Spalte.

We could use this CustomerID to link an order back to the specific customer in the Customers table who placed it. Wir könnten diese Kunden-ID verwenden, um eine Bestellung mit dem spezifischen Kunden in der Kunden-Tabelle zu verknüpfen, der sie aufgegeben hat.

Think about it. Denk darüber nach.

What other tables might a simple online store need besides Customers and Orders? Welche anderen Tabellen könnte ein einfacher Online-Shop außer Kunden und Bestellungen benötigen?

What columns might those tables have? Welche Spalten könnten diese Tabellen haben?

Why is it useful to have separate tables instead of putting all information, customer details, order details, product details, into one giant table? Warum ist es nützlich, separate Tabellen zu haben, anstatt alle Informationen, Kundendetails, Bestelldetails, Produktdetails, in eine riesige Tabelle zu packen?

What is SQL? Was ist SQL?

Okay, we have this organized data in tables within a database. Okay, wir haben diese organisierten Daten in Tabellen innerhalb einer Datenbank.

How do we actually interact with it? Wie interagieren wir eigentlich damit?

How do we ask the database questions like, Show me all customers who signed up in January? or, Add a new customer? Wie stellen wir der Datenbank Fragen wie: Zeige mir alle Kunden, die sich im Januar angemeldet haben? oder: Füge einen neuen Kunden hinzu?

We use a special language called SQL, Structured Query Language, often pronounced sequel or S Q L. Wir verwenden eine spezielle Sprache namens SQL, Structured Query Language, oft ausgesprochen als Sequel oder S Q L.

SQL is the standard language for managing and manipulating data in relational databases. SQL ist die Standardsprache für die Verwaltung und Manipulation von Daten in relationalen Datenbanken.

It allows you to query data: Retrieve specific information, for example, SELECT. Sie ermöglicht dir, Daten abzufragen: Spezifische Informationen abrufen, zum Beispiel SELECT.

Insert data: Add new rows, for example, INSERT INTO. Daten einfügen: Neue Zeilen hinzufügen, zum Beispiel INSERT INTO.

Update data: Modify existing rows, for example, UPDATE. Daten aktualisieren: Bestehende Zeilen ändern, zum Beispiel UPDATE.

Delete data: Remove rows, for example, DELETE FROM. Daten löschen: Zeilen entfernen, zum Beispiel DELETE FROM.

Manage the database structure: Create tables, define columns, etcetera, for example, CREATE TABLE. Die Datenbankstruktur verwalten: Tabellen erstellen, Spalten definieren, et cetera, zum Beispiel CREATE TABLE.

Basic SQL Queries: SELECT. Grundlegende SQL-Abfragen: SELECT.

The most common SQL command is SELECT. Der häufigste SQL-Befehl ist SELECT.

It's used to retrieve data. Er wird verwendet, um Daten abzurufen.

Its basic structure looks like this: SELECT column one, column two, and so on, FROM TableName, WHERE condition. Seine grundlegende Struktur sieht so aus: SELECT Spalte eins, Spalte zwei, und so weiter, FROM Tabellenname, WHERE Bedingung.

SELECT: Specifies the columns you want to retrieve. SELECT: Gibt die Spalten an, die du abrufen möchtest.

Using asterisk means all columns. Die Verwendung von Sternchen bedeutet alle Spalten.

FROM: Specifies the table you want to retrieve the data from. FROM: Gibt die Tabelle an, aus der du die Daten abrufen möchtest.

WHERE: Optional, filters the rows based on a specific condition. WHERE: Optional, filtert die Zeilen basierend auf einer bestimmten Bedingung.

Only rows that meet the condition are returned. Nur Zeilen, die die Bedingung erfüllen, werden zurückgegeben.

Examples using our Customers table. Beispiele mit unserer Kunden-Tabelle.

Get all information for all customers: SELECT asterisk FROM Customers. Alle Informationen für alle Kunden abrufen: SELECT Sternchen FROM Kunden.

Get only the first name and email of all customers: SELECT FirstName, Email FROM Customers. Nur den Vornamen und die E-Mail aller Kunden abrufen: SELECT Vorname, E-Mail FROM Kunden.

Get all information for the customer with CustomerID two: SELECT asterisk FROM Customers WHERE CustomerID equals two. Alle Informationen für den Kunden mit Kunden-ID zwei abrufen: SELECT Sternchen FROM Kunden WHERE Kunden-ID gleich zwei.

Note: Text values in WHERE clauses usually need single quotes, like WHERE FirstName equals quote Alice quote. Hinweis: Textwerte in WHERE-Klauseln benötigen normalerweise einfache Anführungszeichen, wie WHERE Vorname gleich Anführungszeichen Alice Anführungszeichen.

Get the email addresses of customers who signed up on two thousand twenty-three, January fifteenth: SELECT Email FROM Customers WHERE SignupDate equals quote two thousand twenty-three, January fifteenth quote. Die E-Mail-Adressen von Kunden abrufen, die sich am fünfzehnten Januar zweitausenddreiundzwanzig angemeldet haben: SELECT E-Mail FROM Kunden WHERE Anmeldedatum gleich Anführungszeichen zweitausenddreiundzwanzig, fünfzehnter Januar Anführungszeichen.

Try it yourself. Probiere es selbst aus.

Look at the example Customers table again. Schau dir die Beispiel-Kunden-Tabelle noch einmal an.

Write down, on paper or a text file, the SQL queries you would use to get the LastName and Email for all customers. Schreib auf, auf Papier oder in eine Textdatei, die SQL-Abfragen, die du verwenden würdest, um den Nachnamen und die E-Mail für alle Kunden abzurufen.

Get all columns for the customer whose FirstName is Charlie. Alle Spalten für den Kunden abrufen, dessen Vorname Charlie ist.

Get the FirstName of the customer with CustomerID one. Den Vornamen des Kunden mit Kunden-ID eins abrufen.

Don't worry about running these yet, just practice thinking in SQL terms. Mach dir keine Sorgen, diese noch auszuführen, übe einfach, in SQL-Begriffen zu denken.

Setup: DB Browser for SQLite. Einrichtung: DB Browser für SQLite.

Before the hands-on section, please install DB Browser for SQLite. Vor dem praktischen Abschnitt installiere bitte DB Browser für SQLite.

This tool lets you work with simple databases stored in a single file. Dieses Werkzeug ermöglicht es dir, mit einfachen Datenbanken zu arbeiten, die in einer einzigen Datei gespeichert sind.

Installation Steps for mac O S. Installationsschritte für mac O S.

Download: Go to https colon slash slash sqlitebrowser dot org slash dl slash and download the latest stable dot dmg file for mac O S. Download: Gehe zu https Doppelpunkt Schrägstrich Schrägstrich sqlitebrowser punkt org Schrägstrich dl Schrägstrich und lade die neueste stabile Punkt-dmg-Datei für mac O S herunter.

Install: Open the downloaded dot dmg file and drag the DB Browser for SQLite icon into your Applications folder. Installieren: Öffne die heruntergeladene Punkt-dmg-Datei und ziehe das DB Browser für SQLite-Symbol in deinen Anwendungsordner.

Verify: Open the application from your Applications folder to ensure it launches correctly. Überprüfen: Öffne die Anwendung aus deinem Anwendungsordner, um sicherzustellen, dass sie korrekt startet.

You might need to approve opening an app downloaded from the internet the first time. Du musst möglicherweise das Öffnen einer aus dem Internet heruntergeladenen App beim ersten Mal genehmigen.

Hands-On: Your First Database Interaction. Praktische Übung: Deine erste Datenbankinteraktion.

Now that you have DB Browser for SQLite installed, let's use it to create and query a simple database. Jetzt, da du DB Browser für SQLite installiert hast, lass uns damit eine einfache Datenbank erstellen und abfragen.

Launch DB Browser for SQLite: Open the application from your Applications folder. Starte DB Browser für SQLite: Öffne die Anwendung aus deinem Anwendungsordner.

Create a New Database: Click the New Database button. Eine neue Datenbank erstellen: Klicke auf die Schaltfläche Neue Datenbank.

Choose a location, like your Desktop or Documents. Wähle einen Speicherort, wie deinen Desktop oder Dokumente.

Enter a file name, for example, my underscore first underscore db dot sqlite, and click Save. Gib einen Dateinamen ein, zum Beispiel my Unterstrich first Unterstrich db Punkt sqlite, und klicke auf Speichern.

Create a Table: An Edit table definition window will pop up. Eine Tabelle erstellen: Ein Fenster zum Bearbeiten der Tabellendefinition wird erscheinen.

Table name: Friends. Tabellenname: Freunde.

Click Add field three times. Klicke dreimal auf Feld hinzufügen.

Configure the fields: Field one: Name: FriendID, Type: INTEGER, check PK, Primary Key. Konfiguriere die Felder: Feld eins: Name: Freund-ID, Typ: INTEGER, markiere PK, Primärschlüssel.

Field two: Name: Name, Type: TEXT. Feld zwei: Name: Name, Typ: TEXT.

Field three: Name: Hobby, Type: TEXT. Feld drei: Name: Hobby, Typ: TEXT.

Click OK. Klicke auf OK.

Add Some Data: Go to the Browse Data tab. Einige Daten hinzufügen: Gehe zum Tab Daten durchsuchen.

Ensure Table shows Friends. Stelle sicher, dass Tabelle Freunde anzeigt.

Click New Record. Klicke auf Neuer Datensatz.

Enter data for a few friends, double-click cells: Name: Alex, Hobby: Gaming. Gib Daten für ein paar Freunde ein, doppelklicke auf Zellen: Name: Alex, Hobby: Gaming.

Name: Bea, Hobby: Reading. Name: Bea, Hobby: Lesen.

Name: Chris, Hobby: Gaming. Name: Chris, Hobby: Gaming.

Click Write Changes to save the data. Klicke auf Änderungen speichern, um die Daten zu sichern.

Query Your Data with SQL: Go to the Execute SQL tab. Frage deine Daten mit SQL ab: Gehe zum Tab SQL ausführen.

Type this query in the top editor: SELECT asterisk FROM Friends. Gib diese Abfrage im oberen Editor ein: SELECT Sternchen FROM Freunde.

Click the Execute button, blue triangle. Klicke auf die Schaltfläche Ausführen, blaues Dreieck.

See the results below. Sieh die Ergebnisse unten.

Try Another Query: Replace the query with: SELECT Name FROM Friends WHERE Hobby equals quote Gaming quote. Probiere eine weitere Abfrage: Ersetze die Abfrage durch: SELECT Name FROM Freunde WHERE Hobby gleich Anführungszeichen Gaming Anführungszeichen.

Click Execute. Klicke auf Ausführen.

You should see the names Alex and Chris. Du solltest die Namen Alex und Chris sehen.

Congratulations! You've created a database, defined a table, added data, and used SQL to query it. Glückwunsch! Du hast eine Datenbank erstellt, eine Tabelle definiert, Daten hinzugefügt und SQL verwendet, um sie abzufragen.

Keep the my underscore first underscore db dot sqlite file handy. Behalte die Datei my Unterstrich first Unterstrich db Punkt sqlite griffbereit.

That's it for the pre-class preparation. Das war's für die Vorbereitung vor dem Unterricht.

Make sure you've read through the concepts, installed DB Browser for SQLite, and completed the hands-on exercise. Stelle sicher, dass du die Konzepte durchgelesen hast, DB Browser für SQLite installiert hast und die praktische Übung abgeschlossen hast.

See you in class! Wir sehen uns im Unterricht!

The slides for the live session can be viewed at a specific link. Die Folien für die Live-Sitzung können unter einem bestimmten Link angesehen werden.

Try not to peek before class, spoilers inside! Versuche nicht vor dem Unterricht zu spähen, Spoiler drinnen!