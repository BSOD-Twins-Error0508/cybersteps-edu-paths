Welcome to your second Python lesson! In the first lesson, you got Python running and executed some basic commands using the interactive interpreter. Now, we'll dive into one of the most fundamental concepts in programming: variables and data types. Understanding these is crucial for writing any useful program. Willkommen zu deiner zweiten Python-Lektion! In der ersten Lektion hast du Python zum Laufen gebracht und einige grundlegende Befehle mit dem interaktiven Interpreter ausgeführt. Jetzt werden wir uns in eines der fundamentalsten Konzepte der Programmierung vertiefen: Variablen und Datentypen. Das Verständnis dieser Konzepte ist entscheidend, um jedes nützliche Programm zu schreiben.

What is a Variable? Was ist eine Variable?

Think of a variable as a labeled box where you can store information, or data. You give the box a name, the variable name, and you put something inside it, the value. You can then refer to the box by its name to see what's inside or even change what's inside. Stelle dir eine Variable als beschriftete Box vor, in der du Informationen oder Daten speichern kannst. Du gibst der Box einen Namen, den Variablennamen, und legst etwas hinein, den Wert. Du kannst dann über den Namen auf die Box verweisen, um zu sehen, was darin ist, oder sogar ändern, was darin ist.

In Python, you create a variable by choosing a name and using the equals sign, known as the assignment operator, to give it a value. You do this directly in the Python interpreter, the three greater-than signs prompt. In Python erstellst du eine Variable, indem du einen Namen wählst und das Gleichheitszeichen verwendest, das als Zuweisungsoperator bekannt ist, um ihr einen Wert zu geben. Du machst das direkt im Python-Interpreter bei der Eingabeaufforderung mit den drei Größer-als-Zeichen.

Here are some examples: message equals "Hello, Cybersecurity!", student_count equals 120, pi_approx equals 3.14, is_online equals True. Hier sind einige Beispiele: message gleich "Hallo, Cybersicherheit!", student_count gleich 120, pi_approx gleich 3,14, is_online gleich Wahr.

In this example: message is a variable storing text. student_count is a variable storing a whole number. pi_approx is a variable storing a number with a decimal point. is_online is a variable storing a true or false value. In diesem Beispiel: message ist eine Variable, die Text speichert. student_count ist eine Variable, die eine ganze Zahl speichert. pi_approx ist eine Variable, die eine Zahl mit Dezimalpunkt speichert. is_online ist eine Variable, die einen Wahr- oder Falsch-Wert speichert.

Once you've assigned a value to a variable, you can use the variable name in place of the value. For example, typing the variable name itself into the interpreter will usually show its value, or you can use the print function. Sobald du einer Variable einen Wert zugewiesen hast, kannst du den Variablennamen anstelle des Wertes verwenden. Zum Beispiel zeigt das Eintippen des Variablennamens selbst in den Interpreter normalerweise seinen Wert an, oder du kannst die Print-Funktion verwenden.

In the interpreter, after defining message and student_count, you can type print(message) and the output will be: Hello, Cybersecurity! Typing the variable name often shows its value too: student_count would output 120. Im Interpreter kannst du nach der Definition von message und student_count print(message) eingeben und die Ausgabe wird sein: Hallo, Cybersicherheit! Das Eintippen des Variablennamens zeigt oft auch seinen Wert: student_count würde 120 ausgeben.

Variable Naming Rules Regeln für Variablennamen

Choosing good variable names makes your code much easier to read and understand. Python has some rules and conventions. Die Wahl guter Variablennamen macht deinen Code viel leichter lesbar und verständlich. Python hat einige Regeln und Konventionen.

Rule one: Must start with a letter or underscore. my_var and _internal are valid, but 1var is not. Regel eins: Muss mit einem Buchstaben oder Unterstrich beginnen. my_var und _internal sind gültig, aber 1var ist es nicht.

Rule two: Can only contain letters, numbers, and underscores. user_id_1 is valid, but user-id or user id are not. Regel zwei: Kann nur Buchstaben, Zahlen und Unterstriche enthalten. user_id_1 ist gültig, aber user-id oder user id sind es nicht.

Rule three: Case-sensitive. myVariable is different from myvariable. Regel drei: Groß- und Kleinschreibung wird unterschieden. myVariable ist verschieden von myvariable.

Rule four: Cannot be a Python keyword. You can't name a variable if, else, for, while, class, et cetera. These words have special meanings in Python. Regel vier: Kann kein Python-Schlüsselwort sein. Du kannst keine Variable if, else, for, while, class und so weiter nennen. Diese Wörter haben besondere Bedeutungen in Python.

Convention: Use snake_case for variable names, all lowercase words separated by underscores. This is the standard practice in the Python community and makes code readable. Examples: user_name, ip_address, file_path. Konvention: Verwende snake_case für Variablennamen, alle Kleinbuchstaben, getrennt durch Unterstriche. Das ist die Standardpraxis in der Python-Community und macht den Code lesbar. Beispiele: user_name, ip_address, file_path.

Try it yourself Probiere es selbst aus

Open your terminal application. Öffne deine Terminal-Anwendung.

Start the Python interpreter by typing python3, or just python depending on your system, and pressing Enter. You should see the three greater-than signs prompt. Starte den Python-Interpreter, indem du python3 oder einfach python eintippst, je nach deinem System, und Enter drückst. Du solltest die Eingabeaufforderung mit den drei Größer-als-Zeichen sehen.

At the prompt, create a variable named my_name and assign your name, as text enclosed in quotes, to it. Press Enter. An der Eingabeaufforderung erstelle eine Variable namens my_name und weise ihr deinen Namen zu, als Text in Anführungszeichen. Drücke Enter.

For example: my_name equals "Your Name Here". Zum Beispiel: my_name gleich "Dein Name Hier".

Create a variable named my_age and assign your age, as a whole number, to it. Press Enter. Erstelle eine Variable namens my_age und weise ihr dein Alter zu, als ganze Zahl. Drücke Enter.

For example: my_age equals 30. Use your actual age. Zum Beispiel: my_age gleich 30. Verwende dein tatsächliches Alter.

Use the print function to display the values of both variables. Type each line and press Enter. Verwende die Print-Funktion, um die Werte beider Variablen anzuzeigen. Tippe jede Zeile und drücke Enter.

Type print(my_name) and then print(my_age). Tippe print(my_name) und dann print(my_age).

Observe the output printed by the interpreter. Beobachte die Ausgabe, die vom Interpreter ausgegeben wird.

Data Types: What Kind of Data? Datentypen: Welche Art von Daten?

The something you put inside the variable's box has a specific type. Python needs to know the type of data to understand how to work with it. For example, you can do math with numbers, but not directly with text. Python figures out the type automatically when you assign a value. Das Etwas, das du in die Box der Variable legst, hat einen bestimmten Typ. Python muss den Datentyp kennen, um zu verstehen, wie damit gearbeitet werden soll. Zum Beispiel kannst du mit Zahlen rechnen, aber nicht direkt mit Text. Python ermittelt den Typ automatisch, wenn du einen Wert zuweist.

Here are the fundamental data types we'll start with: Hier sind die grundlegenden Datentypen, mit denen wir beginnen:

Integer, abbreviated as int: Whole numbers, positive or negative, without decimals. Examples: 10, minus 5, 0, 12345. Integer, abgekürzt als int: Ganze Zahlen, positiv oder negativ, ohne Dezimalstellen. Beispiele: 10, minus 5, 0, 12345.

Float: Numbers with a decimal point or numbers written in exponential notation. Examples: 3.14, 0.5, 2.0, 1.5e3, which means 1.5 times 10 to the power of 3, equals 1500.0. Float: Zahlen mit Dezimalpunkt oder Zahlen in exponentieller Schreibweise. Beispiele: 3,14, 0,5, 2,0, 1,5e3, was 1,5 mal 10 hoch 3 bedeutet, gleich 1500,0.

String, abbreviated as str: Sequences of characters, or text. You define strings using single quotes or double quotes. Examples: "Hello", 'Cybersecurity', "123", a space is also a character. String, abgekürzt als str: Zeichenfolgen oder Text. Du definierst Strings mit einfachen oder doppelten Anführungszeichen. Beispiele: "Hallo", 'Cybersicherheit', "123", ein Leerzeichen ist auch ein Zeichen.

Boolean, abbreviated as bool: Represents truth values. Can only be True or False. Note the capital letters. Booleans are essential for making decisions in code. Examples: True, False. Boolean, abgekürzt als bool: Stellt Wahrheitswerte dar. Kann nur Wahr oder Falsch sein. Beachte die Großbuchstaben. Booleans sind wesentlich für Entscheidungen im Code. Beispiele: Wahr, Falsch.

Checking the Type Überprüfung des Typs

You can use the built-in type function to find out the data type of a variable or a value directly in the interpreter. Du kannst die eingebaute Type-Funktion verwenden, um den Datentyp einer Variable oder eines Wertes direkt im Interpreter herauszufinden.

First, define some variables in the interpreter: message equals "File not found", error_code equals 404, severity equals 3.5, is_critical equals False. Definiere zuerst einige Variablen im Interpreter: message gleich "Datei nicht gefunden", error_code gleich 404, severity gleich 3,5, is_critical gleich Falsch.

Now check their types and the types of literal values: type(message) outputs: class 'str'. type(error_code) outputs: class 'int'. type(severity) outputs: class 'float'. type(is_critical) outputs: class 'bool'. type(99) outputs: class 'int'. type("Alert!") outputs: class 'str'. Überprüfe jetzt ihre Typen und die Typen von Literalwerten: type(message) gibt aus: Klasse 'str'. type(error_code) gibt aus: Klasse 'int'. type(severity) gibt aus: Klasse 'float'. type(is_critical) gibt aus: Klasse 'bool'. type(99) gibt aus: Klasse 'int'. type("Alert!") gibt aus: Klasse 'str'.

Just type each type command at the prompt and press Enter to see the result immediately. Tippe einfach jeden Type-Befehl an der Eingabeaufforderung und drücke Enter, um das Ergebnis sofort zu sehen.

Try it yourself Probiere es selbst aus

In the same Python interpreter session, or start a new one if you closed it, define the following variables by typing each line and pressing Enter: In derselben Python-Interpreter-Sitzung, oder starte eine neue, wenn du sie geschlossen hast, definiere die folgenden Variablen, indem du jede Zeile eintippst und Enter drückst:

score equals 1500, player_name equals "Hero", game_over equals False, time_elapsed equals 123.5. score gleich 1500, player_name gleich "Held", game_over gleich Falsch, time_elapsed gleich 123,5.

Now, check the type of each variable using the type function. Type each line and press Enter: type(score), type(player_name), type(game_over), type(time_elapsed). Überprüfe jetzt den Typ jeder Variable mit der Type-Funktion. Tippe jede Zeile und drücke Enter: type(score), type(player_name), type(game_over), type(time_elapsed).

Observe the output for each command. Does it match what you expected based on the definitions? Beobachte die Ausgabe für jeden Befehl. Entspricht sie dem, was du basierend auf den Definitionen erwartet hast?

Basic Operations Grundlegende Operationen

The type of a variable determines what operations you can perform with it. You can try these directly in the interpreter. Der Typ einer Variable bestimmt, welche Operationen du damit durchführen kannst. Du kannst diese direkt im Interpreter ausprobieren.

For numbers, int and float, you can perform standard arithmetic operations: Addition with the plus sign, Subtraction with the minus sign, Multiplication with the asterisk, Division with the forward slash, which always results in a float. Für Zahlen, int und float, kannst du standardmäßige arithmetische Operationen durchführen: Addition mit dem Plus-Zeichen, Subtraktion mit dem Minus-Zeichen, Multiplikation mit dem Sternchen, Division mit dem Schrägstrich, was immer zu einem Float führt.

Floor Division with two forward slashes divides and rounds down to the nearest whole number. The result type depends on the operands. Floor Division mit zwei Schrägstrichen teilt und rundet zur nächsten ganzen Zahl ab. Der Ergebnistyp hängt von den Operanden ab.

Modulo, the remainder operation, uses the percent sign. Exponentiation uses two asterisks. Modulo, die Restoperation, verwendet das Prozentzeichen. Potenzierung verwendet zwei Sternchen.

Here are some examples: x equals 10, y equals 3.0. x plus y outputs 13.0. x minus y outputs 7.0. x times y outputs 30.0. x divided by y outputs 3.3333333333333335. x floor divided by y outputs 3.0. x modulo y outputs 1.0. x to the power of 2 outputs 100. Hier sind einige Beispiele: x gleich 10, y gleich 3,0. x plus y ergibt 13,0. x minus y ergibt 7,0. x mal y ergibt 30,0. x geteilt durch y ergibt 3,3333333333333335. x ganzzahlig geteilt durch y ergibt 3,0. x modulo y ergibt 1,0. x hoch 2 ergibt 100.

For Strings, str, you can use: Concatenation, joining strings, with the plus sign. Repetition with the asterisk, combined with an integer. Für Strings, str, kannst du verwenden: Konkatenation, das Verbinden von Strings, mit dem Plus-Zeichen. Wiederholung mit dem Sternchen, kombiniert mit einer ganzen Zahl.

Here are some examples: first_name equals "Ada", last_name equals "Lovelace". full_name equals first_name plus a space plus last_name. Add a space in between! print(full_name) outputs: Ada Lovelace. Hier sind einige Beispiele: first_name gleich "Ada", last_name gleich "Lovelace". full_name gleich first_name plus ein Leerzeichen plus last_name. Füge ein Leerzeichen dazwischen ein! print(full_name) gibt aus: Ada Lovelace.

separator equals minus sign times 10. This repeats the minus sign ten times. print(separator) outputs: ten minus signs in a row. separator gleich Minus-Zeichen mal 10. Das wiederholt das Minus-Zeichen zehnmal. print(separator) gibt aus: zehn Minus-Zeichen hintereinander.

Important: You generally cannot mix types in operations without explicitly converting them. For example, typing 10 plus "5" into the interpreter will cause a TypeError because Python doesn't know whether you want to do math or join text. Try it! Wichtig: Du kannst im Allgemeinen keine Typen in Operationen mischen, ohne sie explizit zu konvertieren. Zum Beispiel verursacht das Eintippen von 10 plus "5" in den Interpreter einen TypeError, weil Python nicht weiß, ob du rechnen oder Text verbinden möchtest. Probiere es aus!

10 plus "5" will produce a TypeError as shown in the text above. 10 plus "5" wird einen TypeError erzeugen, wie im Text oben gezeigt.

Think about it Denke darüber nach

Why is 10 divided by 2 a float, 5.0, and not an int, 5, in Python? Hint: Think about consistency. Warum ist 10 geteilt durch 2 ein Float, 5,0, und nicht ein int, 5, in Python? Hinweis: Denke an Konsistenz.

What do you think 10 floor divided by 3.0 results in? What about 10.0 floor divided by 3? Try them out in the interpreter! Was denkst du, ergibt 10 ganzzahlig geteilt durch 3,0? Was ist mit 10,0 ganzzahlig geteilt durch 3? Probiere sie im Interpreter aus!

If you have a variable count equals 5, how could you create the string "Count: 5" using the variable and string concatenation? This will actually cause a TypeError. We'll see how to fix this soon! Wenn du eine Variable count gleich 5 hast, wie könntest du den String "Zähler: 5" mit der Variable und String-Konkatenation erstellen? Das wird tatsächlich einen TypeError verursachen. Wir werden bald sehen, wie man das behebt!

Dynamic Typing Dynamische Typisierung

One characteristic of Python is dynamic typing. This means you don't have to declare the type of a variable when you create it, and you can even change the type of data a variable holds later on. Eine Eigenschaft von Python ist die dynamische Typisierung. Das bedeutet, du musst den Typ einer Variable nicht deklarieren, wenn du sie erstellst, und du kannst sogar den Typ der Daten, die eine Variable enthält, später ändern.

Try this in the interpreter: Type these lines sequentially: my_variable equals 100. type(my_variable) outputs: class 'int'. Probiere dies im Interpreter: Tippe diese Zeilen nacheinander: my_variable gleich 100. type(my_variable) gibt aus: Klasse 'int'.

my_variable equals "Now I'm a string". type(my_variable) outputs: class 'str'. my_variable gleich "Jetzt bin ich ein String". type(my_variable) gibt aus: Klasse 'str'.

my_variable equals True. type(my_variable) outputs: class 'bool'. my_variable gleich Wahr. type(my_variable) gibt aus: Klasse 'bool'.

While flexible, this means you need to be mindful of what type of data your variable currently holds, especially before performing operations on it. Obwohl flexibel, bedeutet das, dass du achtsam sein musst, welchen Datentyp deine Variable gerade enthält, besonders bevor du Operationen damit durchführst.

That covers the basics of variables and fundamental data types! Spend some time experimenting with these concepts in the Python interpreter. Create different variables, check their types, and try some basic operations. This will prepare you well for our live session where we'll build upon this foundation. To exit the interpreter, you can type exit() or press Control plus D. Das deckt die Grundlagen von Variablen und grundlegenden Datentypen ab! Verbringe etwas Zeit damit, mit diesen Konzepten im Python-Interpreter zu experimentieren. Erstelle verschiedene Variablen, überprüfe ihre Typen und probiere einige grundlegende Operationen aus. Das wird dich gut auf unsere Live-Sitzung vorbereiten, in der wir auf diesem Fundament aufbauen werden. Um den Interpreter zu verlassen, kannst du exit() eintippen oder Control plus D drücken.

The slides for the live session can be viewed at the provided link. Try not to peek before class, spoilers inside! Die Folien für die Live-Sitzung können unter dem angegebenen Link angesehen werden. Versuche nicht vor dem Unterricht zu spicken, Spoiler darin!

Variables: Labeled Boxes Variablen: Beschriftete Boxen

Store data, or values. Use names, or identifiers, to refer to data. Assignment: variable_name equals value. Naming Rules and snake_case Convention, as recommended by PEP 8! Speichere Daten oder Werte. Verwende Namen oder Bezeichner, um auf Daten zu verweisen. Zuweisung: variable_name gleich Wert. Namensregeln und snake_case-Konvention, wie von PEP 8 empfohlen!

PEP 8, the Style Guide for Python Code, can be found at peps.python.org, Python Enhancement Proposals. PEP 8, der Styleguide für Python-Code, kann unter peps.python.org gefunden werden, Python Enhancement Proposals.

Basic Data Types Grundlegende Datentypen

int: Whole numbers, for example 10, minus 3, 0. float: Numbers with decimals, for example 3.14, minus 0.5, 2.0. str: Text or sequences of characters, for example "Hello", 'Cyber'. bool: Truth values, True or False. Use type() to check! int: Ganze Zahlen, zum Beispiel 10, minus 3, 0. float: Zahlen mit Dezimalstellen, zum Beispiel 3,14, minus 0,5, 2,0. str: Text oder Zeichenfolgen, zum Beispiel "Hallo", 'Cyber'. bool: Wahrheitswerte, Wahr oder Falsch. Verwende type(), um zu überprüfen!

Numeric Operations Numerische Operationen

Plus: Addition. Minus: Subtraction. Asterisk: Multiplication. Forward slash: Float division. Double forward slash: Floor division. Percent: Modulo. Double asterisk: Exponent. Plus: Addition. Minus: Subtraktion. Sternchen: Multiplikation. Schrägstrich: Float-Division. Doppelter Schrägstrich: Floor-Division. Prozent: Modulo. Doppeltes Sternchen: Exponent.

String Operations String-Operationen

Plus, concatenation: Joins strings together. Example: "Hello" plus " World" results in "Hello World". Plus, Konkatenation: Verbindet Strings miteinander. Beispiel: "Hallo" plus " Welt" ergibt "Hallo Welt".

Asterisk, repetition: Repeats a string. Example: "Python " times 3 results in "Python Python Python ". Sternchen, Wiederholung: Wiederholt einen String. Beispiel: "Python " mal 3 ergibt "Python Python Python ".

TypeError: Mixing Incompatible Types TypeError: Mischen inkompatibler Typen

Python often doesn't know how to combine different types automatically. Example: 5 plus " apples" leads to a TypeError. Need to convert types explicitly. Python weiß oft nicht, wie verschiedene Typen automatisch kombiniert werden sollen. Beispiel: 5 plus " Äpfel" führt zu einem TypeError. Typen müssen explizit konvertiert werden.

Incompatible Types: 5 plus " apples". TypeError: Can't add int and str. Solution: str(5) plus " apples". Inkompatible Typen: 5 plus " Äpfel". TypeError: Kann int und str nicht addieren. Lösung: str(5) plus " Äpfel".

What happens if you run value equals "100" and then print(value divided by 2)? Why? You get a TypeError. value is a string, "100", and you cannot perform mathematical division directly on a string. You would need to convert value to a number first, for example int(value). Was passiert, wenn du value gleich "100" ausführst und dann print(value geteilt durch 2)? Warum? Du bekommst einen TypeError. value ist ein String, "100", und du kannst keine mathematische Division direkt auf einem String durchführen. Du müsstest value zuerst in eine Zahl konvertieren, zum Beispiel int(value).

Here's the correct approach: value equals "100". print(int(value) divided by 2) outputs 50.0. Hier ist der richtige Ansatz: value gleich "100". print(int(value) geteilt durch 2) gibt 50,0 aus.

f-string f-string

Example: name equals "Alice", age equals 30. f-string example: print(f"Hello, {name}! You are {age} years old.") outputs: Hello, Alice! You are 30 years old. Beispiel: name gleich "Alice", age gleich 30. f-string-Beispiel: print(f"Hallo, {name}! Du bist {age} Jahre alt.") gibt aus: Hallo, Alice! Du bist 30 Jahre alt.

Benefits of f-strings: More readable than other string formatting methods. Can include expressions: f"Result: {2 times 3}". Format specifiers available: f"Pi: {3.14159:.2f}". Vorteile von f-strings: Lesbarer als andere String-Formatierungsmethoden. Kann Ausdrücke enthalten: f"Ergebnis: {2 mal 3}". Formatangaben verfügbar: f"Pi: {3,14159:.2f}".

Using isinstance() for Type Checking Verwendung von isinstance() zur Typüberprüfung

What is isinstance()? A built-in function that checks if an object is an instance of a specified class or type. Was ist isinstance()? Eine eingebaute Funktion, die prüft, ob ein Objekt eine Instanz einer bestimmten Klasse oder eines bestimmten Typs ist.

Syntax: isinstance(object, classinfo). Returns True if object is an instance of classinfo. Returns False otherwise. Syntax: isinstance(Objekt, Klasseninfo). Gibt Wahr zurück, wenn Objekt eine Instanz von Klasseninfo ist. Gibt Falsch zurück, wenn nicht.

Examples: x equals 5. print(isinstance(x, int)) outputs True. print(isinstance(x, float)) outputs False. name equals "Python". print(isinstance(name, str)) outputs True. Beispiele: x gleich 5. print(isinstance(x, int)) gibt Wahr aus. print(isinstance(x, float)) gibt Falsch aus. name gleich "Python". print(isinstance(name, str)) gibt Wahr aus.

Unlike type(), isinstance() also handles inheritance, making it more flexible for class hierarchies. Im Gegensatz zu type() behandelt isinstance() auch Vererbung, was es flexibler für Klassenhierarchien macht.

Summary Zusammenfassung

Variables store data using names. Core types: int, float, str, bool. type() checks the data type. Operators work based on type: plus, minus, forward slash, double forward slash, et cetera. Variablen speichern Daten unter Verwendung von Namen. Kerntypen: int, float, str, bool. type() überprüft den Datentyp. Operatoren funktionieren basierend auf dem Typ: plus, minus, Schrägstrich, doppelter Schrägstrich und so weiter.

TypeError happens when mixing incompatible types. Use int(), float(), str() to convert types. Follow snake_case naming convention, as recommended by PEP 8. TypeError tritt auf, wenn inkompatible Typen gemischt werden. Verwende int(), float(), str(), um Typen zu konvertieren. Folge der snake_case-Namenskonvention, wie von PEP 8 empfohlen.