Welcome! Before our live session on Python Modules, please go through this material. Understanding these concepts will help you get the most out of our class. Willkommen! Vor unserer Live-Sitzung über Python-Module gehe bitte dieses Material durch. Das Verständnis dieser Konzepte wird dir helfen, das Beste aus unserem Unterricht herauszuholen.

What are Modules? Was sind Module?

Imagine you're building a large project, like a house. You wouldn't build every single component from scratch right there on the site, would you? You'd likely use pre-fabricated parts like doors, windows, and maybe even entire wall sections. These pre-made components save time, ensure consistency, and are built by specialists. Stell dir vor, du baust ein großes Projekt, wie ein Haus. Du würdest nicht jede einzelne Komponente von Grund auf direkt vor Ort bauen, oder? Du würdest wahrscheinlich vorgefertigte Teile wie Türen, Fenster und vielleicht sogar ganze Wandabschnitte verwenden. Diese vorgefertigten Komponenten sparen Zeit, gewährleisten Konsistenz und werden von Spezialisten gebaut.

In Python, modules are like those pre-fabricated parts. They are simply Python files, dot py files, containing Python definitions and statements, like functions, classes, and variables. Modules allow you to logically organize your Python code. Grouping related code into a module makes the code easier to understand, use, and maintain. It also allows you to reuse code across different projects without copying and pasting. In Python sind Module wie diese vorgefertigten Teile. Sie sind einfach Python-Dateien, Punkt-py-Dateien, die Python-Definitionen und Anweisungen enthalten, wie Funktionen, Klassen und Variablen. Module ermöglichen es dir, deinen Python-Code logisch zu organisieren. Das Gruppieren von zusammenhängendem Code in ein Modul macht den Code einfacher zu verstehen, zu verwenden und zu warten. Es ermöglicht dir auch, Code über verschiedene Projekte hinweg wiederzuverwenden, ohne zu kopieren und einzufügen.

Why Use Modules? Warum Module verwenden?

Organization: Instead of writing one enormous script, you can break down your project into smaller, manageable modules, each handling a specific part of the task. Organisation: Anstatt ein einziges riesiges Skript zu schreiben, kannst du dein Projekt in kleinere, handhabbare Module aufteilen, von denen jedes einen bestimmten Teil der Aufgabe übernimmt.

Reusability: Write a function or class once in a module, and you can use it in many different scripts or projects just by importing the module. This follows the DRY principle: Don't Repeat Yourself. Wiederverwendbarkeit: Schreibe eine Funktion oder Klasse einmal in einem Modul, und du kannst sie in vielen verschiedenen Skripten oder Projekten verwenden, indem du einfach das Modul importierst. Das folgt dem DRY-Prinzip: Don't Repeat Yourself, wiederhole dich nicht.

Collaboration: Different team members can work on different modules simultaneously. Zusammenarbeit: Verschiedene Teammitglieder können gleichzeitig an verschiedenen Modulen arbeiten.

Namespace Management: Modules help prevent naming conflicts. A function named calculate in module_a.py won't clash with a function named calculate in module_b.py because you'll access them as module_a.calculate() and module_b.calculate(). Namespace-Verwaltung: Module helfen, Namenskonflikte zu vermeiden. Eine Funktion namens calculate in module_a.py wird nicht mit einer Funktion namens calculate in module_b.py kollidieren, weil du auf sie als module_a.calculate() und module_b.calculate() zugreifst.

Using Existing Code: Python comes with a vast Standard Library, a collection of built-in modules providing tools for common tasks, like math operations, file input/output, networking, randomness, et cetera. You don't have to write these yourself! There are also countless third-party modules created by the community for almost any task imaginable. Vorhandenen Code verwenden: Python kommt mit einer umfangreichen Standardbibliothek, einer Sammlung von eingebauten Modulen, die Werkzeuge für häufige Aufgaben bereitstellen, wie mathematische Operationen, Dateieingabe/-ausgabe, Netzwerke, Zufälligkeit und so weiter. Du musst diese nicht selbst schreiben! Es gibt auch unzählige Module von Drittanbietern, die von der Community für fast jede vorstellbare Aufgabe erstellt wurden.

How to Use Modules: The import Statement Wie man Module verwendet: Die import-Anweisung

To use the code defined in a module within your current Python script, you need to import it. The simplest way is using the import keyword followed by the module name, the filename without the dot py extension. Um den in einem Modul definierten Code in deinem aktuellen Python-Skript zu verwenden, musst du es importieren. Der einfachste Weg ist die Verwendung des import-Schlüsselworts, gefolgt vom Modulnamen, dem Dateinamen ohne die Punkt-py-Erweiterung.

import module_name. import module_name.

Once imported, you can access the functions, variables, or classes defined inside that module using dot notation: module_name.item_name. Sobald importiert, kannst du auf die Funktionen, Variablen oder Klassen zugreifen, die in diesem Modul definiert sind, indem du die Punkt-Notation verwendest: module_name.item_name.

Example: Using the math module Beispiel: Verwendung des math-Moduls

Python's standard library includes a module named math that provides various mathematical functions and constants. Pythons Standardbibliothek enthält ein Modul namens math, das verschiedene mathematische Funktionen und Konstanten bereitstellt.

Import the entire math module: import math. Das gesamte math-Modul importieren: import math.

Use the sqrt function from the math module: number equals 16. square_root equals math.sqrt(number). print(f"The square root of {number} is {square_root}"). Die sqrt-Funktion aus dem math-Modul verwenden: number gleich 16. square_root gleich math.sqrt(number). print(f"Die Quadratwurzel von {number} ist {square_root}").

Use the pi constant from the math module: radius equals 5. area equals math.pi times (radius to the power of 2). print(f"The area of a circle with radius {radius} is {area}"). Die pi-Konstante aus dem math-Modul verwenden: radius gleich 5. area gleich math.pi mal (radius hoch 2). print(f"Die Fläche eines Kreises mit Radius {radius} ist {area}").

Output: The square root of 16 is 4.0. The area of a circle with radius 5 is 78.53981633974483. Ausgabe: Die Quadratwurzel von 16 ist 4.0. Die Fläche eines Kreises mit Radius 5 ist 78.53981633974483.

Try it yourself Probiere es selbst aus

Open Visual Studio Code, create a new Python file, for example try_math.py, type or paste the code above, and run it. See the output for yourself. Öffne Visual Studio Code, erstelle eine neue Python-Datei, zum Beispiel try_math.py, tippe oder füge den obigen Code ein und führe ihn aus. Sieh dir die Ausgabe selbst an.

Importing Specific Items: from dot dot dot import dot dot dot Spezifische Elemente importieren: from Punkt Punkt Punkt import Punkt Punkt Punkt

Sometimes, you only need one or two specific items from a module, or you might find typing the module name repeatedly cumbersome. In such cases, you can use the from dot dot dot import dot dot dot statement. Manchmal brauchst du nur ein oder zwei spezifische Elemente aus einem Modul, oder du findest das wiederholte Tippen des Modulnamens umständlich. In solchen Fällen kannst du die from Punkt Punkt Punkt import Punkt Punkt Punkt Anweisung verwenden.

from module_name import item_name1, item_name2. from module_name import item_name1, item_name2.

When you use from dot dot dot import dot dot dot, the imported items are added directly to your script's namespace, so you can use them without the module_name dot prefix. Wenn du from Punkt Punkt Punkt import Punkt Punkt Punkt verwendest, werden die importierten Elemente direkt zum Namespace deines Skripts hinzugefügt, sodass du sie ohne das module_name Punkt Präfix verwenden kannst.

Example: Using from dot dot dot import dot dot dot with random Beispiel: Verwendung von from Punkt Punkt Punkt import Punkt Punkt Punkt mit random

The random module provides functions for generating random numbers. Das random-Modul stellt Funktionen zur Generierung von Zufallszahlen bereit.

Import only the randint function from the random module: from random import randint. Importiere nur die randint-Funktion aus dem random-Modul: from random import randint.

Now we can use randint directly without the 'random dot' prefix: random_number equals randint(1, 10). Generates a random integer between 1 and 10, inclusive. print(f"A random integer between 1 and 10: {random_number}"). Jetzt können wir randint direkt ohne das 'random Punkt' Präfix verwenden: random_number gleich randint(1, 10). Erzeugt eine zufällige Ganzzahl zwischen 1 und 10, einschließlich. print(f"Eine zufällige Ganzzahl zwischen 1 und 10: {random_number}").

If we try to use another function from random, like choice, it won't work because we didn't import it directly. The following line would cause an error: print(random.choice(['a', 'b', 'c'])). Wenn wir versuchen, eine andere Funktion aus random zu verwenden, wie choice, wird es nicht funktionieren, weil wir sie nicht direkt importiert haben. Die folgende Zeile würde einen Fehler verursachen: print(random.choice(['a', 'b', 'c'])).

Caution: While convenient, using from dot dot dot import dot dot dot extensively can sometimes make it harder to tell where a specific function or variable came from, especially if different modules have items with the same name. Importing the whole module, import module_name, is often clearer for larger scripts. Vorsicht: Obwohl bequem, kann die extensive Verwendung von from Punkt Punkt Punkt import Punkt Punkt Punkt es manchmal schwieriger machen zu erkennen, woher eine bestimmte Funktion oder Variable kommt, besonders wenn verschiedene Module Elemente mit demselben Namen haben. Das Importieren des gesamten Moduls, import module_name, ist oft klarer für größere Skripte.

You can also import everything from a module using asterisk, like from math import asterisk. However, this is generally discouraged because it pollutes your script's namespace with all the names from the module, potentially overwriting your own variables or functions without you realizing it, and making the code harder to read and debug. Du kannst auch alles aus einem Modul mit Sternchen importieren, wie from math import Sternchen. Dies wird jedoch generell nicht empfohlen, weil es den Namespace deines Skripts mit allen Namen aus dem Modul verschmutzt, möglicherweise deine eigenen Variablen oder Funktionen überschreibt, ohne dass du es merkst, und den Code schwerer lesbar und debugbar macht.

The Python Standard Library Die Python-Standardbibliothek

Python comes batteries included, meaning it has a rich standard library full of useful modules. You don't need to install anything extra to use them; you just import them. We've already seen math and random. Here are a few others you might encounter: Python kommt mit Batterien inklusive, was bedeutet, dass es eine reichhaltige Standardbibliothek voller nützlicher Module hat. Du musst nichts extra installieren, um sie zu verwenden; du importierst sie einfach. Wir haben bereits math und random gesehen. Hier sind ein paar andere, denen du begegnen könntest:

os: Provides functions for interacting with the operating system, like working with files and directories, getting environment variables. os: Stellt Funktionen für die Interaktion mit dem Betriebssystem bereit, wie das Arbeiten mit Dateien und Verzeichnissen, das Abrufen von Umgebungsvariablen.

sys: Access to system-specific parameters and functions, like command-line arguments. sys: Zugriff auf systemspezifische Parameter und Funktionen, wie Kommandozeilenargumente.

datetime: For working with dates and times. datetime: Für die Arbeit mit Daten und Zeiten.

json: For working with JSON data. json: Für die Arbeit mit JSON-Daten.

re: For working with regular expressions. re: Für die Arbeit mit regulären Ausdrücken.

You can explore the full list and documentation here, no need to memorize it now, just be aware it exists: https://docs.python.org/3/library/ Du kannst die vollständige Liste und Dokumentation hier erkunden, keine Notwendigkeit, es jetzt auswendig zu lernen, sei dir nur bewusst, dass es existiert: https://docs.python.org/3/library/

Try it yourself Probiere es selbst aus

Let's try the datetime module to get the current date and time. Lass uns das datetime-Modul ausprobieren, um das aktuelle Datum und die aktuelle Uhrzeit zu erhalten.

Create a new Python file in Visual Studio Code, for example try_datetime.py. Erstelle eine neue Python-Datei in Visual Studio Code, zum Beispiel try_datetime.py.

Type or paste the following code: Tippe oder füge den folgenden Code ein:

Import the datetime module: import datetime. Importiere das datetime-Modul: import datetime.

Get the current date and time: now equals datetime.datetime.now(). Das aktuelle Datum und die aktuelle Uhrzeit abrufen: now gleich datetime.datetime.now().

Print it out: print("The current date and time is:"). print(now). Gib es aus: print("Das aktuelle Datum und die aktuelle Uhrzeit ist:"). print(now).

You can also format it: formatted_time equals now.strftime("%Y-%m-%d %H:%M:%S"). print("Formatted time:"). print(formatted_time). Du kannst es auch formatieren: formatted_time gleich now.strftime("%Y-%m-%d %H:%M:%S"). print("Formatierte Zeit:"). print(formatted_time).

Run the file. Observe how the datetime module provides the datetime object, which has methods like now() to get the current time and strftime() to format it as a string. Führe die Datei aus. Beobachte, wie das datetime-Modul das datetime-Objekt bereitstellt, das Methoden wie now() hat, um die aktuelle Zeit zu erhalten, und strftime(), um sie als String zu formatieren.

Think about it Denke darüber nach

Why is it beneficial that Python includes a standard library? How does this compare to having to find and install basic tools for every project? Warum ist es vorteilhaft, dass Python eine Standardbibliothek enthält? Wie vergleicht sich das damit, grundlegende Werkzeuge für jedes Projekt finden und installieren zu müssen?

Summary Zusammenfassung

Modules are Python files, dot py, containing reusable code, like functions, classes, variables. Module sind Python-Dateien, Punkt py, die wiederverwendbaren Code enthalten, wie Funktionen, Klassen, Variablen.

They help organize code, promote reusability, and prevent naming conflicts. Sie helfen, Code zu organisieren, fördern Wiederverwendbarkeit und verhindern Namenskonflikte.

Use import module_name to bring a module's code into your script. Verwende import module_name, um den Code eines Moduls in dein Skript zu bringen.

Access items within an imported module using dot notation: module_name.item_name. Greife auf Elemente innerhalb eines importierten Moduls mit Punkt-Notation zu: module_name.item_name.

Use from module_name import item_name to import specific items directly into your namespace. Use with caution. Verwende from module_name import item_name, um spezifische Elemente direkt in deinen Namespace zu importieren. Verwende mit Vorsicht.

Python has a vast Standard Library of built-in modules for common tasks. Python hat eine umfangreiche Standardbibliothek von eingebauten Modulen für häufige Aufgaben.

That's it for the pre-class preparation! Spend some time reviewing these concepts and try the examples. We'll build upon this foundation in our live session. Das war's für die Vorbereitung vor dem Unterricht! Verbringe etwas Zeit damit, diese Konzepte zu wiederholen und probiere die Beispiele aus. Wir werden auf diesem Fundament in unserer Live-Sitzung aufbauen.