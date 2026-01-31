Welcome! In previous lessons, you learned about lists, which are ordered sequences of items. Now, we'll explore another fundamental Python data structure: dictionaries. Dictionaries are incredibly useful for storing and retrieving data based on a unique identifier, much like looking up a word in a real dictionary or finding a phone number in a contact list. Willkommen! In vorherigen Lektionen hast du über Listen gelernt, die geordnete Sequenzen von Elementen sind. Jetzt werden wir eine weitere fundamentale Python-Datenstruktur erkunden: Dictionaries. Dictionaries sind unglaublich nützlich zum Speichern und Abrufen von Daten basierend auf einem eindeutigen Bezeichner, ähnlich wie das Nachschlagen eines Wortes in einem echten Wörterbuch oder das Finden einer Telefonnummer in einer Kontaktliste.

What is a Dictionary? Was ist ein Dictionary?

Here's an example: myDict equals {"hey": "there", "abc": 123, 456: ["word", -0.5]}. Hier ist ein Beispiel: myDict gleich {"hey": "there", "abc": 123, 456: ["word", -0.5]}.

Think about a real-world dictionary. You look up a word, the key, to find its definition, the value. Python dictionaries work similarly. They store data as key-value pairs. Denke an ein echtes Wörterbuch. Du schlägst ein Wort nach, den Schlüssel, um seine Definition zu finden, den Wert. Python-Dictionaries funktionieren ähnlich. Sie speichern Daten als Schlüssel-Wert-Paare.

Key: A unique identifier used to look up data. Keys must be immutable types, meaning they cannot be changed after creation. Common immutable types include strings, numbers like integers and floats, and tuples if they contain only immutable elements. You cannot use lists or other dictionaries as keys. Schlüssel: Ein eindeutiger Bezeichner, der verwendet wird, um Daten nachzuschlagen. Schlüssel müssen unveränderbare Typen sein, das heißt, sie können nach der Erstellung nicht geändert werden. Häufige unveränderbare Typen umfassen Strings, Zahlen wie Integers und Floats, und Tupel, wenn sie nur unveränderbare Elemente enthalten. Du kannst keine Listen oder andere Dictionaries als Schlüssel verwenden.

Value: The data associated with a key. Values can be of any data type: strings, numbers, lists, other dictionaries, et cetera. Wert: Die Daten, die mit einem Schlüssel verbunden sind. Werte können von jedem Datentyp sein: Strings, Zahlen, Listen, andere Dictionaries und so weiter.

Unlike lists, dictionaries are unordered, or more accurately, insertion order is preserved in recent Python versions, but you shouldn't rely on this for accessing elements like you do with list indices. You access values using their specific keys, not by their position or index number. Im Gegensatz zu Listen sind Dictionaries ungeordnet, oder genauer gesagt, die Einfügereihenfolge wird in neueren Python-Versionen beibehalten, aber du solltest dich nicht darauf verlassen, um auf Elemente zuzugreifen, wie du es mit Listen-Indizes tust. Du greifst auf Werte über ihre spezifischen Schlüssel zu, nicht über ihre Position oder Indexnummer.

Creating Dictionaries Dictionaries erstellen

You can create dictionaries in a couple of ways: Du kannst Dictionaries auf ein paar Arten erstellen:

Using Curly Braces: This is the most common way. Verwendung von geschweiften Klammern: Das ist der häufigste Weg.

An empty dictionary: empty_dict equals empty braces. Ein leeres Dictionary: empty_dict gleich leere geschweifte Klammern.

A dictionary of student grades: student_grades equals {"Alice": 85, "Bob": 92, "Charlie": 78}. Ein Dictionary von Schülernoten: student_grades gleich {"Alice": 85, "Bob": 92, "Charlie": 78}.

A dictionary describing a user profile: user_profile equals {"username": "coder123", "level": 5, "interests": ["Python", "Cybersecurity"], "is_active": True}. Ein Dictionary, das ein Benutzerprofil beschreibt: user_profile gleich {"username": "coder123", "level": 5, "interests": ["Python", "Cybersecurity"], "is_active": True}.

print(student_grades). print(user_profile). print(student_grades). print(user_profile).

Using the dict() constructor: This can be useful for creating dictionaries from other sequences or keyword arguments. Verwendung des dict()-Konstruktors: Das kann nützlich sein, um Dictionaries aus anderen Sequenzen oder Schlüsselwort-Argumenten zu erstellen.

From keyword arguments: settings equals dict(theme="dark", font_size=12, notifications_enabled=True). print(settings). Aus Schlüsselwort-Argumenten: settings gleich dict(theme="dark", font_size=12, notifications_enabled=True). print(settings).

From a list of key-value tuples, less common: pairs equals [('item', 'laptop'), ('quantity', 1)]. inventory_item equals dict(pairs). print(inventory_item). Aus einer Liste von Schlüssel-Wert-Tupeln, weniger üblich: pairs gleich [('item', 'laptop'), ('quantity', 1)]. inventory_item gleich dict(pairs). print(inventory_item).

Try it yourself Probiere es selbst aus

Create an empty dictionary called my_contacts. Erstelle ein leeres Dictionary namens my_contacts.

Create a dictionary called book_details containing the keys "title" as a string, "author" as a string, and "pages" as an integer with appropriate values. Print the book_details dictionary. Erstelle ein Dictionary namens book_details, das die Schlüssel "title" als String, "author" als String und "pages" als Integer mit passenden Werten enthält. Drucke das book_details-Dictionary.

Accessing Values Auf Werte zugreifen

To get the value associated with a specific key, you use square brackets with the key inside: Um den Wert zu erhalten, der mit einem bestimmten Schlüssel verbunden ist, verwendest du eckige Klammern mit dem Schlüssel darin:

student_grades equals {"Alice": 85, "Bob": 92, "Charlie": 78}. student_grades gleich {"Alice": 85, "Bob": 92, "Charlie": 78}.

alices_grade equals student_grades["Alice"]. print(f"Alice's grade is: {alices_grade}"). Output: Alice's grade is: 85. alices_grade gleich student_grades["Alice"]. print(f"Alices Note ist: {alices_grade}"). Ausgabe: Alices Note ist: 85.

bobs_grade equals student_grades["Bob"]. print(f"Bob's grade is: {bobs_grade}"). Output: Bob's grade is: 92. bobs_grade gleich student_grades["Bob"]. print(f"Bobs Note ist: {bobs_grade}"). Ausgabe: Bobs Note ist: 92.

What if the key doesn't exist? Was ist, wenn der Schlüssel nicht existiert?

If you try to access a key that isn't in the dictionary using square brackets, Python will raise a KeyError. Wenn du versuchst, auf einen Schlüssel zuzugreifen, der nicht im Dictionary ist, mit eckigen Klammern, wird Python einen KeyError auslösen.

This will cause an error! davids_grade equals student_grades["David"]. Raises KeyError: 'David'. Das wird einen Fehler verursachen! davids_grade gleich student_grades["David"]. Löst KeyError aus: 'David'.

Safer Access with dot get() Sicherer Zugriff mit Punkt get()

To avoid errors, you can use the dot get() method. It returns the value for the key if it exists, or None by default if it doesn't. You can also provide a default value to return instead of None. Um Fehler zu vermeiden, kannst du die Punkt get()-Methode verwenden. Sie gibt den Wert für den Schlüssel zurück, wenn er existiert, oder None standardmäßig, wenn nicht. Du kannst auch einen Standardwert angeben, der anstelle von None zurückgegeben wird.

student_grades equals {"Alice": 85, "Bob": 92, "Charlie": 78}. student_grades gleich {"Alice": 85, "Bob": 92, "Charlie": 78}.

Get Alice's grade, exists: alices_grade equals student_grades.get("Alice"). print(f"Alice's grade (using get): {alices_grade}"). Output: Alice's grade (using get): 85. Alices Note abrufen, existiert: alices_grade gleich student_grades.get("Alice"). print(f"Alices Note (mit get): {alices_grade}"). Ausgabe: Alices Note (mit get): 85.

Try to get David's grade, doesn't exist: davids_grade equals student_grades.get("David"). print(f"David's grade (using get): {davids_grade}"). Output: David's grade (using get): None. Versuche Davids Note abzurufen, existiert nicht: davids_grade gleich student_grades.get("David"). print(f"Davids Note (mit get): {davids_grade}"). Ausgabe: Davids Note (mit get): None.

Try to get David's grade with a default value: davids_grade_default equals student_grades.get("David", "Not found"). print(f"David's grade (with default): {davids_grade_default}"). Output: David's grade (with default): Not found. Versuche Davids Note mit einem Standardwert abzurufen: davids_grade_default gleich student_grades.get("David", "Not found"). print(f"Davids Note (mit Standard): {davids_grade_default}"). Ausgabe: Davids Note (mit Standard): Not found.

Try it yourself Probiere es selbst aus

Using the book_details dictionary you created earlier, print the value associated with the "author" key. Verwende das book_details-Dictionary, das du früher erstellt hast, und drucke den Wert, der mit dem "author"-Schlüssel verbunden ist.

Try to access the value for a key named "genre" using square brackets. Observe the error. Versuche auf den Wert für einen Schlüssel namens "genre" mit eckigen Klammern zuzugreifen. Beobachte den Fehler.

Now, access the value for "genre" using the dot get() method. Print the result. Greife jetzt auf den Wert für "genre" mit der Punkt get()-Methode zu. Drucke das Ergebnis.

Access the value for "genre" using dot get(), but provide a default value of "Unknown". Print the result. Greife auf den Wert für "genre" mit Punkt get() zu, aber stelle einen Standardwert von "Unknown" bereit. Drucke das Ergebnis.

Adding and Updating Items Elemente hinzufügen und aktualisieren

Adding a new key-value pair or updating the value of an existing key is done using the square bracket assignment syntax: Das Hinzufügen eines neuen Schlüssel-Wert-Paares oder das Aktualisieren des Wertes eines vorhandenen Schlüssels erfolgt mit der eckigen Klammer-Zuweisungssyntax:

student_grades equals {"Alice": 85, "Bob": 92}. print(f"Original grades: {student_grades}"). student_grades gleich {"Alice": 85, "Bob": 92}. print(f"Original-Noten: {student_grades}").

Add a new student: student_grades["David"] equals 88. print(f"After adding David: {student_grades}"). Einen neuen Schüler hinzufügen: student_grades["David"] gleich 88. print(f"Nach Hinzufügen von David: {student_grades}").

Update Bob's grade: student_grades["Bob"] equals 95. print(f"After updating Bob: {student_grades}"). Bobs Note aktualisieren: student_grades["Bob"] gleich 95. print(f"Nach Aktualisierung von Bob: {student_grades}").

If the key already exists, its value is overwritten. If the key doesn't exist, the new key-value pair is added. Wenn der Schlüssel bereits existiert, wird sein Wert überschrieben. Wenn der Schlüssel nicht existiert, wird das neue Schlüssel-Wert-Paar hinzugefügt.

Try it yourself Probiere es selbst aus

Add a new key-value pair "published_year": 1997 to your book_details dictionary. Füge ein neues Schlüssel-Wert-Paar "published_year": 1997 zu deinem book_details-Dictionary hinzu.

Update the "pages" value in book_details to a new number. Aktualisiere den "pages"-Wert in book_details auf eine neue Zahl.

Print the final book_details dictionary. Drucke das finale book_details-Dictionary.

Removing Items Elemente entfernen

There are several ways to remove items from a dictionary: Es gibt mehrere Möglichkeiten, Elemente aus einem Dictionary zu entfernen:

The del keyword: Removes the item with the specified key. Raises a KeyError if the key doesn't exist. Das del-Schlüsselwort: Entfernt das Element mit dem angegebenen Schlüssel. Löst einen KeyError aus, wenn der Schlüssel nicht existiert.

settings equals {"theme": "dark", "font_size": 12, "auto_save": True}. print(f"Settings before del: {settings}"). del settings["auto_save"]. print(f"Settings after del: {settings}"). del settings["nonexistent_key"] would cause KeyError. settings gleich {"theme": "dark", "font_size": 12, "auto_save": True}. print(f"Einstellungen vor del: {settings}"). del settings["auto_save"]. print(f"Einstellungen nach del: {settings}"). del settings["nonexistent_key"] würde KeyError verursachen.

The dot pop(key) method: Removes the item with the specified key and returns its value. Raises a KeyError if the key doesn't exist, unless you provide a default return value. Die Punkt pop(key)-Methode: Entfernt das Element mit dem angegebenen Schlüssel und gibt seinen Wert zurück. Löst einen KeyError aus, wenn der Schlüssel nicht existiert, es sei denn, du stellst einen Standard-Rückgabewert bereit.

settings equals {"theme": "dark", "font_size": 12, "auto_save": True}. print(f"Settings before pop: {settings}"). removed_value equals settings.pop("font_size"). print(f"Settings after pop: {settings}"). print(f"Removed value: {removed_value}"). settings gleich {"theme": "dark", "font_size": 12, "auto_save": True}. print(f"Einstellungen vor pop: {settings}"). removed_value gleich settings.pop("font_size"). print(f"Einstellungen nach pop: {settings}"). print(f"Entfernter Wert: {removed_value}").

Pop a non-existent key with a default value: removed_default equals settings.pop("language", "English"). print(f"Removed non-existent key (with default): {removed_default}"). removed_error equals settings.pop("language") would cause KeyError. Einen nicht existierenden Schlüssel mit einem Standardwert poppen: removed_default gleich settings.pop("language", "English"). print(f"Nicht existierenden Schlüssel entfernt (mit Standard): {removed_default}"). removed_error gleich settings.pop("language") würde KeyError verursachen.

The dot popitem() method: Removes and returns the last inserted key-value pair as a tuple. In older Python versions before 3.7, it removed an arbitrary pair. Raises a KeyError if the dictionary is empty. Die Punkt popitem()-Methode: Entfernt und gibt das zuletzt eingefügte Schlüssel-Wert-Paar als Tupel zurück. In älteren Python-Versionen vor 3.7 entfernte es ein beliebiges Paar. Löst einen KeyError aus, wenn das Dictionary leer ist.

settings equals {"theme": "dark", "font_size": 12, "auto_save": True}. print(f"Settings before popitem: {settings}"). last_item equals settings.popitem(). print(f"Settings after popitem: {settings}"). print(f"Removed item: {last_item}"). Output might be ('auto_save', True). settings gleich {"theme": "dark", "font_size": 12, "auto_save": True}. print(f"Einstellungen vor popitem: {settings}"). last_item gleich settings.popitem(). print(f"Einstellungen nach popitem: {settings}"). print(f"Entferntes Element: {last_item}"). Ausgabe könnte ('auto_save', True) sein.

Try it yourself Probiere es selbst aus

Create a dictionary user_prefs equals {"theme": "dark", "fontSize": 12, "notifications": True}. Erstelle ein Dictionary user_prefs gleich {"theme": "dark", "fontSize": 12, "notifications": True}.

Remove the "fontSize" item using del. Entferne das "fontSize"-Element mit del.

Remove the "notifications" item using dot pop() and print the removed value. Entferne das "notifications"-Element mit Punkt pop() und drucke den entfernten Wert.

Print the final user_prefs dictionary. Drucke das finale user_prefs-Dictionary.

Checking for Keys Nach Schlüsseln suchen

You can easily check if a key exists in a dictionary using the in operator: Du kannst leicht überprüfen, ob ein Schlüssel in einem Dictionary existiert, indem du den in-Operator verwendest:

student_grades equals {"Alice": 85, "Bob": 92, "Charlie": 78}. student_grades gleich {"Alice": 85, "Bob": 92, "Charlie": 78}.

if "Alice" in student_grades, colon, print("Alice is in the dictionary."), else, colon, print("Alice is not in the dictionary."). if "Alice" in student_grades, Doppelpunkt, print("Alice ist im Dictionary."), else, Doppelpunkt, print("Alice ist nicht im Dictionary.").

if "David" not in student_grades, colon, print("David is not in the dictionary."), else, colon, print("David is in the dictionary."). if "David" not in student_grades, Doppelpunkt, print("David ist nicht im Dictionary."), else, Doppelpunkt, print("David ist im Dictionary.").

Useful Dictionary Methods Nützliche Dictionary-Methoden

Dictionaries have several built-in methods to work with their contents: Dictionaries haben mehrere eingebaute Methoden, um mit ihrem Inhalt zu arbeiten:

Dot keys(): Returns a view object containing all the keys in the dictionary. Punkt keys(): Gibt ein View-Objekt zurück, das alle Schlüssel im Dictionary enthält.

Dot values(): Returns a view object containing all the values in the dictionary. Punkt values(): Gibt ein View-Objekt zurück, das alle Werte im Dictionary enthält.

Dot items(): Returns a view object containing all the key-value pairs as tuples, key comma value. Punkt items(): Gibt ein View-Objekt zurück, das alle Schlüssel-Wert-Paare als Tupel enthält, Schlüssel Komma Wert.

View objects are dynamic, they reflect changes made to the dictionary. You can easily convert them to lists if needed. View-Objekte sind dynamisch, sie spiegeln Änderungen wider, die am Dictionary vorgenommen wurden. Du kannst sie bei Bedarf leicht in Listen konvertieren.

settings equals {"theme": "dark", "font_size": 12, "auto_save": True}. settings gleich {"theme": "dark", "font_size": 12, "auto_save": True}.

keys equals settings.keys(). values equals settings.values(). items equals settings.items(). keys gleich settings.keys(). values gleich settings.values(). items gleich settings.items().

print(f"Keys: {keys}"). Output: Keys: dict_keys(['theme', 'font_size', 'auto_save']). print(f"Schlüssel: {keys}"). Ausgabe: Schlüssel: dict_keys(['theme', 'font_size', 'auto_save']).

print(f"Values: {values}"). Output: Values: dict_values(['dark', 12, True]). print(f"Werte: {values}"). Ausgabe: Werte: dict_values(['dark', 12, True]).

print(f"Items: {items}"). Output: Items: dict_items([('theme', 'dark'), ('font_size', 12), ('auto_save', True)]). print(f"Elemente: {items}"). Ausgabe: Elemente: dict_items([('theme', 'dark'), ('font_size', 12), ('auto_save', True)]).

Convert to lists: key_list equals list(keys). value_list equals list(values). item_list equals list(items). In Listen konvertieren: key_list gleich list(keys). value_list gleich list(values). item_list gleich list(items).

print(f"Key list: {key_list}"). Output: Key list: ['theme', 'font_size', 'auto_save']. print(f"Schlüsselliste: {key_list}"). Ausgabe: Schlüsselliste: ['theme', 'font_size', 'auto_save'].

print(f"Value list: {value_list}"). Output: Value list: ['dark', 12, True]. print(f"Werteliste: {value_list}"). Ausgabe: Werteliste: ['dark', 12, True].

print(f"Item list: {item_list}"). Output: Item list: [('theme', 'dark'), ('font_size', 12), ('auto_save', True)]. print(f"Elementliste: {item_list}"). Ausgabe: Elementliste: [('theme', 'dark'), ('font_size', 12), ('auto_save', True)].

You often use these methods in loops, which we'll cover more in class. print("Iterating through items:"). for key, value in settings.items(), colon, print(f" Key: {key}, Value: {value}"). Du verwendest diese Methoden oft in Schleifen, was wir mehr im Unterricht behandeln werden. print("Durch Elemente iterieren:"). for key, value in settings.items(), Doppelpunkt, print(f" Schlüssel: {key}, Wert: {value}").

Think about it Denke darüber nach

When would using a dictionary be more advantageous than using a list? Think about scenarios where you need to look up information quickly based on a specific identifier rather than its position. Wann wäre die Verwendung eines Dictionarys vorteilhafter als die Verwendung einer Liste? Denke an Szenarien, in denen du Informationen schnell basierend auf einem bestimmten Bezeichner nachschlagen musst, anstatt auf seiner Position.

That's the basics of Python dictionaries! Spend some time experimenting with the examples above in Visual Studio Code. Having a good grasp of these concepts will prepare you well for the live session where we'll dive deeper and see how dictionaries are used in practice. Das sind die Grundlagen von Python-Dictionaries! Verbringe etwas Zeit damit, mit den obigen Beispielen in Visual Studio Code zu experimentieren. Ein gutes Verständnis dieser Konzepte wird dich gut auf die Live-Sitzung vorbereiten, in der wir tiefer eintauchen und sehen werden, wie Dictionaries in der Praxis verwendet werden.