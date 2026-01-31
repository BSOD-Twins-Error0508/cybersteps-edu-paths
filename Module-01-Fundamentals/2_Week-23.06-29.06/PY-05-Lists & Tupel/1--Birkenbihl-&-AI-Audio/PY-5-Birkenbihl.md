Welcome to the world of Python lists! Before our live session, please go through this material to get familiar with the basics. Willkommen in der Welt der Python-Listen! Vor unserer Live-Sitzung gehe bitte dieses Material durch, um dich mit den Grundlagen vertraut zu machen.

What is a List? Was ist eine Liste?

Here's an example: myList equals ["hey", 123, 456, "there!"]. Hier ist ein Beispiel: myList gleich ["hey", 123, 456, "there!"].

In Python, a list is a way to store multiple items in a single variable. Think of it like a shopping list where you can write down several items you need to buy. Instead of having separate variables for each item, like item1 equals "milk", item2 equals "eggs", item3 equals "bread", you can group them together. In Python ist eine Liste eine Möglichkeit, mehrere Elemente in einer einzigen Variable zu speichern. Denke daran wie an eine Einkaufsliste, auf der du mehrere Artikel aufschreiben kannst, die du kaufen musst. Anstatt separate Variablen für jedes Element zu haben, wie item1 gleich "Milch", item2 gleich "Eier", item3 gleich "Brot", kannst du sie zusammen gruppieren.

Lists are: Ordered. The items in a list have a specific position, and that order stays the same unless you change it. Listen sind: Geordnet. Die Elemente in einer Liste haben eine bestimmte Position, und diese Reihenfolge bleibt gleich, es sei denn, du änderst sie.

Mutable. You can change the contents of a list after it's created, add items, remove items, or change existing items. Veränderbar. Du kannst den Inhalt einer Liste nach ihrer Erstellung ändern, Elemente hinzufügen, Elemente entfernen oder bestehende Elemente ändern.

Allow Duplicates. A list can contain the same item multiple times. Erlauben Duplikate. Eine Liste kann dasselbe Element mehrfach enthalten.

Creating a List Eine Liste erstellen

You create a list by placing items inside square brackets, separated by commas. Du erstellst eine Liste, indem du Elemente in eckige Klammern setzt, getrennt durch Kommas.

An empty list: empty_list equals empty brackets. print(empty_list). Eine leere Liste: empty_list gleich leere Klammern. print(empty_list).

A list of numbers, integers: primes equals [2, 3, 5, 7, 11]. print(primes). Eine Liste von Zahlen, ganzen Zahlen: primes gleich [2, 3, 5, 7, 11]. print(primes).

A list of strings: fruits equals ["apple", "banana", "cherry"]. print(fruits). Eine Liste von Strings: fruits gleich ["apple", "banana", "cherry"]. print(fruits).

A list with mixed data types, though often you'll keep types consistent: mixed_list equals ["hello", 100, True, 3.14]. print(mixed_list). Eine Liste mit gemischten Datentypen, obwohl du oft die Typen konsistent hältst: mixed_list gleich ["hello", 100, True, 3.14]. print(mixed_list).

Try it yourself Probiere es selbst aus

Create a list named planets containing the names of the first three planets from the sun as strings: "Mercury", "Venus", "Earth". Erstelle eine Liste namens planets, die die Namen der ersten drei Planeten von der Sonne als Strings enthält: "Mercury", "Venus", "Earth".

Print the planets list. Drucke die planets-Liste.

Create a list named scores containing three integer scores: 10, 25, and 15. Erstelle eine Liste namens scores, die drei ganzzahlige Punktzahlen enthält: 10, 25 und 15.

Print the scores list. Drucke die scores-Liste.

Tuples, Immutable Lists Tupel, unveränderbare Listen

In Python, a tuple is very similar to a list. It can store multiple items in a single variable, items can be of mixed types, and their order matters. The key difference is that tuples cannot be changed after they are created. This means you can't add, remove, or modify elements in a tuple. In Python ist ein Tupel einer Liste sehr ähnlich. Es kann mehrere Elemente in einer einzigen Variable speichern, Elemente können von gemischten Typen sein, und ihre Reihenfolge ist wichtig. Der Hauptunterschied ist, dass Tupel nach ihrer Erstellung nicht geändert werden können. Das bedeutet, du kannst keine Elemente in einem Tupel hinzufügen, entfernen oder ändern.

You create a tuple by placing items inside parentheses instead of square brackets. Du erstellst ein Tupel, indem du Elemente in runde Klammern setzt anstatt in eckige Klammern.

A simple tuple: coordinates equals (10.0, 20.0). print(coordinates). Ein einfaches Tupel: coordinates gleich (10.0, 20.0). print(coordinates).

A tuple with mixed data types: person equals ("Alice", 30, "Engineer"). print(person). Ein Tupel mit gemischten Datentypen: person gleich ("Alice", 30, "Engineer"). print(person).

A tuple with one item needs a comma! single_item equals ("hello",). print(single_item). Ein Tupel mit einem Element braucht ein Komma! single_item gleich ("hello",). print(single_item).

If you try to modify a tuple, Python will raise an error: numbers equals (1, 2, 3). This will cause an error: numbers[1] equals 5. Wenn du versuchst, ein Tupel zu ändern, wird Python einen Fehler auslösen: numbers gleich (1, 2, 3). Das wird einen Fehler verursachen: numbers[1] gleich 5.

Tuples are often used for data that should not change, like fixed coordinates, dates, or return values from functions that naturally come as groups. Tupel werden oft für Daten verwendet, die sich nicht ändern sollten, wie feste Koordinaten, Daten oder Rückgabewerte von Funktionen, die natürlich als Gruppen kommen.

You can still access items in a tuple using the same indexing as with lists: person equals ("Alice", 30, "Engineer"). print(person[0]) outputs Alice. print(person[-1]) outputs Engineer. Du kannst immer noch auf Elemente in einem Tupel zugreifen, indem du dieselbe Indizierung wie bei Listen verwendest: person gleich ("Alice", 30, "Engineer"). print(person[0]) gibt Alice aus. print(person[-1]) gibt Engineer aus.

Valid Operations Gültige Operationen

Even though tuples are immutable, you can still perform some operations: colors equals ("red", "green", "blue"). Obwohl Tupel unveränderbar sind, kannst du trotzdem einige Operationen durchführen: colors gleich ("red", "green", "blue").

Access items by index: print(colors[0]) outputs red. Greife auf Elemente über den Index zu: print(colors[0]) gibt red aus.

Check if an item exists: print("green" in colors) outputs True. Prüfe, ob ein Element existiert: print("green" in colors) gibt True aus.

Find length: print(len(colors)) outputs 3. Finde die Länge: print(len(colors)) gibt 3 aus.

Count occurrences: print(colors.count("red")) outputs 1. Zähle Vorkommen: print(colors.count("red")) gibt 1 aus.

Find index of an item: print(colors.index("blue")) outputs 2. Finde den Index eines Elements: print(colors.index("blue")) gibt 2 aus.

Concatenate tuples: new_colors equals colors plus ("yellow",). print(new_colors). Verkette Tupel: new_colors gleich colors plus ("yellow",). print(new_colors).

Iterating Over Tuples Über Tupel iterieren

You can loop through a tuple just like a list: animals equals ("cat", "dog", "bird"). for a in animals, colon, print(a). Du kannst durch ein Tupel durchlaufen, genau wie durch eine Liste: animals gleich ("cat", "dog", "bird"). for a in animals, Doppelpunkt, print(a).

Immutability in Practice Unveränderbarkeit in der Praxis

Tuples cannot be changed directly, but if a tuple contains a mutable object, like a list, that object can be modified. Tupel können nicht direkt geändert werden, aber wenn ein Tupel ein veränderbares Objekt enthält, wie eine Liste, kann dieses Objekt verändert werden.

Example: data equals (1, [2, 3], 4). data[1].append(5). print(data) outputs (1, [2, 3, 5], 4). Beispiel: data gleich (1, [2, 3], 4). data[1].append(5). print(data) gibt (1, [2, 3, 5], 4) aus.

Here, the tuple itself didn't change. It still has three elements. But one of those elements, the list, was modified internally. Hier hat sich das Tupel selbst nicht geändert. Es hat immer noch drei Elemente. Aber eines dieser Elemente, die Liste, wurde intern verändert.

Tuple Unpacking Tupel-Entpacken

Tuples can be unpacked into separate variables in a single step. This is one of the most powerful and convenient uses of tuples. Tupel können in separate Variablen in einem einzigen Schritt entpackt werden. Das ist eine der mächtigsten und praktischsten Verwendungen von Tupeln.

Example: person equals ("Alice", 30, "Engineer"). name, age, job equals person. print(name) outputs Alice. print(age) outputs 30. print(job) outputs Engineer. Beispiel: person gleich ("Alice", 30, "Engineer"). name, age, job gleich person. print(name) gibt Alice aus. print(age) gibt 30 aus. print(job) gibt Engineer aus.

You can even swap values easily using tuple unpacking: x, y equals 10, 20. x, y equals y, x. print(x, y) outputs 20 10. Du kannst sogar Werte leicht austauschen, indem du Tupel-Entpacken verwendest: x, y gleich 10, 20. x, y gleich y, x. print(x, y) gibt 20 10 aus.

Tuple Operations and Methods Tupel-Operationen und Methoden

Tuples support a small set of methods compared to lists, since they are immutable. Commonly used methods include: count(value) returns how many times a value appears in the tuple. index(value) returns the index of the first occurrence of the value. Tupel unterstützen eine kleine Menge von Methoden im Vergleich zu Listen, da sie unveränderbar sind. Häufig verwendete Methoden umfassen: count(value) gibt zurück, wie oft ein Wert im Tupel vorkommt. index(value) gibt den Index des ersten Vorkommens des Wertes zurück.

Most list methods like append(), remove(), or sort() are not available for tuples. Die meisten Listen-Methoden wie append(), remove() oder sort() sind für Tupel nicht verfügbar.

Common Use Cases for Tuples Häufige Anwendungsfälle für Tupel

Tuples are used when: Data should not change, for example days of the week, fixed coordinates. Tupel werden verwendet, wenn: Daten sich nicht ändern sollten, zum Beispiel Wochentage, feste Koordinaten.

You want a sequence to be hashable and used as a dictionary key. Du möchtest, dass eine Sequenz hashbar ist und als Dictionary-Schlüssel verwendet werden kann.

You need to return multiple values from a function. Du musst mehrere Werte von einer Funktion zurückgeben.

You want to unpack multiple values conveniently. Du möchtest mehrere Werte bequem entpacken.

Example: def get_position(), colon, return (100, 200). x, y equals get_position(). print(x, y). Beispiel: def get_position(), Doppelpunkt, return (100, 200). x, y gleich get_position(). print(x, y).

List versus Tuple Liste versus Tupel

Syntax: List uses square brackets. Tuple uses parentheses. Syntax: Liste verwendet eckige Klammern. Tupel verwendet runde Klammern.

Mutability: List is mutable, can be changed. Tuple is immutable, cannot be changed. Veränderbarkeit: Liste ist veränderbar, kann geändert werden. Tupel ist unveränderbar, kann nicht geändert werden.

Methods: List has many methods like append, remove, sort, et cetera. Tuple has few methods, count and index. Methoden: Liste hat viele Methoden wie append, remove, sort und so weiter. Tupel hat wenige Methoden, count und index.

Performance: List is slightly slower. Tuple is slightly faster. Performance: Liste ist etwas langsamer. Tupel ist etwas schneller.

Use Case: List for data that changes. Tuple for data that should remain constant. Anwendungsfall: Liste für Daten, die sich ändern. Tupel für Daten, die konstant bleiben sollten.

Think about it Denke darüber nach

How are tuples similar to lists? How are they different? Why might you want to use a tuple instead of a list in your own code? Wie sind Tupel ähnlich zu Listen? Wie unterscheiden sie sich? Warum könntest du ein Tupel anstelle einer Liste in deinem eigenen Code verwenden wollen?

Accessing Items: Indexing Auf Elemente zugreifen: Indizierung

Each item in a list has a position, called an index. Python uses zero-based indexing, which means the first item is at index 0, the second item is at index 1, and so on. Jedes Element in einer Liste hat eine Position, genannt Index. Python verwendet nullbasierte Indizierung, was bedeutet, dass das erste Element bei Index 0 ist, das zweite Element bei Index 1, und so weiter.

To access an item, you use the list name followed by the index in square brackets. Um auf ein Element zuzugreifen, verwendest du den Listennamen gefolgt vom Index in eckigen Klammern.

Example: fruits equals ["apple", "banana", "cherry"]. Access the first item, index 0: first_fruit equals fruits[0]. print(first_fruit) outputs apple. Beispiel: fruits gleich ["apple", "banana", "cherry"]. Greife auf das erste Element zu, Index 0: first_fruit gleich fruits[0]. print(first_fruit) gibt apple aus.

Access the third item, index 2: third_fruit equals fruits[2]. print(third_fruit) outputs cherry. Greife auf das dritte Element zu, Index 2: third_fruit gleich fruits[2]. print(third_fruit) gibt cherry aus.

Trying to access an index that doesn't exist will cause an IndexError. This will cause an error because index 3 doesn't exist. Indices are 0, 1, 2: print(fruits[3]). Der Versuch, auf einen Index zuzugreifen, der nicht existiert, verursacht einen IndexError. Das wird einen Fehler verursachen, weil Index 3 nicht existiert. Indizes sind 0, 1, 2: print(fruits[3]).

You can also use negative indices. Index minus 1 refers to the last item, minus 2 refers to the second-to-last item, and so on. Du kannst auch negative Indizes verwenden. Index minus 1 bezieht sich auf das letzte Element, minus 2 bezieht sich auf das vorletzte Element, und so weiter.

Example: fruits equals ["apple", "banana", "cherry"]. Access the last item: last_fruit equals fruits[-1]. print(last_fruit) outputs cherry. Beispiel: fruits gleich ["apple", "banana", "cherry"]. Greife auf das letzte Element zu: last_fruit gleich fruits[-1]. print(last_fruit) gibt cherry aus.

Access the second-to-last item: second_last_fruit equals fruits[-2]. print(second_last_fruit) outputs banana. Greife auf das vorletzte Element zu: second_last_fruit gleich fruits[-2]. print(second_last_fruit) gibt banana aus.

Think about it Denke darüber nach

Consider the list letters equals ["a", "b", "c", "d", "e"]. What is the index of the item "a"? Betrachte die Liste letters gleich ["a", "b", "c", "d", "e"]. Was ist der Index des Elements "a"?

What is the index of the item "e"? Was ist der Index des Elements "e"?

How would you access the item "c" using a positive index? Wie würdest du auf das Element "c" mit einem positiven Index zugreifen?

How would you access the item "d" using a negative index? Wie würdest du auf das Element "d" mit einem negativen Index zugreifen?

Try it yourself Probiere es selbst aus

Using the planets list you created earlier, ["Mercury", "Venus", "Earth"]: Print the planet at index 1. Verwende die planets-Liste, die du früher erstellt hast, ["Mercury", "Venus", "Earth"]: Drucke den Planeten bei Index 1.

Print the last planet using a negative index. Drucke den letzten Planeten mit einem negativen Index.

Modifying List Items Listen-Elemente ändern

Because lists are mutable, you can change their contents. To change an item, you access it using its index and assign a new value. Weil Listen veränderbar sind, kannst du ihren Inhalt ändern. Um ein Element zu ändern, greifst du darauf über seinen Index zu und weist einen neuen Wert zu.

Example: colors equals ["red", "green", "blue"]. print(colors) outputs ['red', 'green', 'blue']. Beispiel: colors gleich ["red", "green", "blue"]. print(colors) gibt ['red', 'green', 'blue'] aus.

Change the item at index 1: colors[1] equals "yellow". print(colors) outputs ['red', 'yellow', 'blue']. Ändere das Element bei Index 1: colors[1] gleich "yellow". print(colors) gibt ['red', 'yellow', 'blue'] aus.

Try it yourself Probiere es selbst aus

Create a list numbers equals [1, 2, 30, 4, 5]. Erstelle eine Liste numbers gleich [1, 2, 30, 4, 5].

Change the item at index 2 to be 3. Ändere das Element bei Index 2 zu 3.

Print the updated numbers list. Drucke die aktualisierte numbers-Liste.

Getting the Length of a List Die Länge einer Liste ermitteln

You can find out how many items are in a list using the built-in len() function. Du kannst herausfinden, wie viele Elemente in einer Liste sind, indem du die eingebaute len()-Funktion verwendest.

Example: fruits equals ["apple", "banana", "cherry"]. num_fruits equals len(fruits). print(num_fruits) outputs 3. Beispiel: fruits gleich ["apple", "banana", "cherry"]. num_fruits gleich len(fruits). print(num_fruits) gibt 3 aus.

empty_list equals empty brackets. num_items equals len(empty_list). print(num_items) outputs 0. empty_list gleich leere Klammern. num_items gleich len(empty_list). print(num_items) gibt 0 aus.

Think about it Denke darüber nach

If a list has a length of 5, what is the index of the first item? What is the index of the last item? Wenn eine Liste eine Länge von 5 hat, was ist der Index des ersten Elements? Was ist der Index des letzten Elements?

Adding Items to a List: append() Elemente zu einer Liste hinzufügen: append()

One of the most common list operations is adding a new item to the end of the list. You can do this using the append() method. A method is like a function that belongs to an object, in this case the list. You call it using a dot after the list variable. Eine der häufigsten Listenoperationen ist das Hinzufügen eines neuen Elements am Ende der Liste. Du kannst dies mit der append()-Methode tun. Eine Methode ist wie eine Funktion, die zu einem Objekt gehört, in diesem Fall zur Liste. Du rufst sie mit einem Punkt nach der Listenvariable auf.

Example: fruits equals ["apple", "banana"]. print(fruits) outputs ['apple', 'banana']. Beispiel: fruits gleich ["apple", "banana"]. print(fruits) gibt ['apple', 'banana'] aus.

Add "cherry" to the end: fruits.append("cherry"). print(fruits) outputs ['apple', 'banana', 'cherry']. Füge "cherry" am Ende hinzu: fruits.append("cherry"). print(fruits) gibt ['apple', 'banana', 'cherry'] aus.

Add another fruit: fruits.append("orange"). print(fruits) outputs ['apple', 'banana', 'cherry', 'orange']. Füge eine weitere Frucht hinzu: fruits.append("orange"). print(fruits) gibt ['apple', 'banana', 'cherry', 'orange'] aus.

Notice that append() modifies the original list directly. It's mutable! Beachte, dass append() die ursprüngliche Liste direkt ändert. Sie ist veränderbar!

Try it yourself Probiere es selbst aus

Start with the list tasks equals ["email boss", "buy groceries"]. Beginne mit der Liste tasks gleich ["email boss", "buy groceries"].

Append the task "call plumber" to the list. Füge die Aufgabe "call plumber" zur Liste hinzu.

Print the tasks list. Drucke die tasks-Liste.

Print the length of the updated tasks list. Drucke die Länge der aktualisierten tasks-Liste.

That's it for the pre-class preparation! We'll dive deeper into lists, explore more ways to modify them, like inserting items at specific positions and removing items, and see how they interact with loops in our live session. Das war's für die Vorbereitung vor dem Unterricht! Wir werden tiefer in Listen eintauchen, mehr Wege erkunden, sie zu ändern, wie das Einfügen von Elementen an bestimmten Positionen und das Entfernen von Elementen, und sehen, wie sie mit Schleifen in unserer Live-Sitzung interagieren.