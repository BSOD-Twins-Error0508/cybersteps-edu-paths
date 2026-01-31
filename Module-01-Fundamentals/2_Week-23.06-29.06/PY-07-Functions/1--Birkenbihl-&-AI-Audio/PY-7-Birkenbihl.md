Welcome to the world of functions in Python! Functions are a fundamental concept in programming that allows you to write more organized, reusable, and efficient code. Think of them as named blocks of code that perform a specific task. Instead of writing the same sequence of steps multiple times, you can define it once as a function and then call that function whenever you need it. Willkommen in der Welt der Funktionen in Python! Funktionen sind ein fundamentales Konzept in der Programmierung, das es dir ermöglicht, organisierten, wiederverwendbaren und effizienten Code zu schreiben. Denke an sie als benannte Codeblöcke, die eine bestimmte Aufgabe ausführen. Anstatt dieselbe Abfolge von Schritten mehrmals zu schreiben, kannst du sie einmal als Funktion definieren und diese Funktion dann aufrufen, wann immer du sie brauchst.

What is a Function? Was ist eine Funktion?

At its core, a function is a block of organized, reusable code that is used to perform a single, related action. Functions provide better modularity for your application and a high degree of code reusing. Im Kern ist eine Funktion ein Block aus organisiertem, wiederverwendbarem Code, der verwendet wird, um eine einzelne, zusammenhängende Aktion auszuführen. Funktionen bieten bessere Modularität für deine Anwendung und einen hohen Grad an Code-Wiederverwendung.

Imagine you're writing a script, and you find yourself calculating the area of a rectangle in several different places. Each time, you write: length equals 10, width equals 5, area equals length times width, print("The area is:", area). Stell dir vor, du schreibst ein Skript und findest dich dabei, wie du die Fläche eines Rechtecks an mehreren verschiedenen Stellen berechnest. Jedes Mal schreibst du: length gleich 10, width gleich 5, area gleich length mal width, print("Die Fläche ist:", area).

Some other code. Then length2 equals 7, width2 equals 3, area2 equals length2 times width2, print("The area is:", area2). Etwas anderer Code. Dann length2 gleich 7, width2 gleich 3, area2 gleich length2 mal width2, print("Die Fläche ist:", area2).

This works, but it's repetitive. If you needed to change how the area is calculated or displayed, you'd have to find and modify every instance. A function solves this. Das funktioniert, aber es ist sich wiederholend. Wenn du ändern müsstest, wie die Fläche berechnet oder angezeigt wird, müsstest du jede Instanz finden und ändern. Eine Funktion löst dieses Problem.

Defining a Function Eine Funktion definieren

You can define your own functions using the def keyword. Here's the basic syntax: Du kannst deine eigenen Funktionen mit dem def-Schlüsselwort definieren. Hier ist die grundlegende Syntax:

def function_name(parameters), colon. Optional docstring explaining what the function does. Code block, indented. Statements performing the task. return value. Optional: returns a value from the function. def function_name(parameters), Doppelpunkt. Optionaler Docstring, der erklärt, was die Funktion tut. Codeblock, eingerückt. Anweisungen, die die Aufgabe ausführen. return value. Optional: gibt einen Wert von der Funktion zurück.

Let's break this down: Lass uns das aufschlüsseln:

The def keyword: This signals the start of a function definition. Das def-Schlüsselwort: Dies signalisiert den Beginn einer Funktionsdefinition.

function_name: This is the name you give your function. Choose descriptive names. Like variable names, use snake_case: lowercase words separated by underscores. function_name: Dies ist der Name, den du deiner Funktion gibst. Wähle beschreibende Namen. Wie bei Variablennamen verwende snake_case: Kleinbuchstaben, getrennt durch Unterstriche.

parameters in parentheses: These are inputs the function accepts. A function can have zero or more parameters, separated by commas. These act like variables inside the function. If there are no parameters, you still need the empty parentheses. parameters in Klammern: Dies sind Eingaben, die die Funktion akzeptiert. Eine Funktion kann null oder mehr Parameter haben, getrennt durch Kommas. Diese verhalten sich wie Variablen innerhalb der Funktion. Wenn es keine Parameter gibt, brauchst du trotzdem die leeren Klammern.

Colon: Marks the end of the function header. Doppelpunkt: Markiert das Ende des Funktionskopfes.

Docstring, optional but recommended: A string literal enclosed in triple quotes right after the header. It explains the function's purpose, parameters, and what it returns. Good practice for documentation! Docstring, optional aber empfohlen: Ein String-Literal in dreifachen Anführungszeichen direkt nach dem Kopf. Es erklärt den Zweck der Funktion, Parameter und was sie zurückgibt. Gute Praxis für Dokumentation!

Indented Code Block: The actual code that performs the function's task. This block must be indented, usually 4 spaces. Eingerückter Codeblock: Der tatsächliche Code, der die Aufgabe der Funktion ausführt. Dieser Block muss eingerückt sein, normalerweise 4 Leerzeichen.

return statement, optional: Used to send a result back from the function to the place where it was called. If omitted, the function implicitly returns a special value None. return-Anweisung, optional: Wird verwendet, um ein Ergebnis von der Funktion zurück zu der Stelle zu senden, wo sie aufgerufen wurde. Wenn weggelassen, gibt die Funktion implizit einen speziellen Wert None zurück.

Example: A Simple Greeting Function Beispiel: Eine einfache Begrüßungsfunktion

def greet(), colon. Prints a simple greeting. print("Hello there!"). def greet(), Doppelpunkt. Gibt eine einfache Begrüßung aus. print("Hallo dort!").

Example: Calculating Rectangle Area Beispiel: Rechteckfläche berechnen

def calculate_rectangle_area(length, width), colon. Calculates the area of a rectangle. area equals length times width. return area. def calculate_rectangle_area(length, width), Doppelpunkt. Berechnet die Fläche eines Rechtecks. area gleich length mal width. return area.

Calling a Function Eine Funktion aufrufen

Defining a function doesn't execute its code. It just creates the function. To run the code inside a function, you need to call it. You call a function by using its name followed by parentheses. If the function expects parameters, or inputs, you provide values, called arguments, inside the parentheses. Eine Funktion zu definieren führt ihren Code nicht aus. Es erstellt nur die Funktion. Um den Code innerhalb einer Funktion auszuführen, musst du sie aufrufen. Du rufst eine Funktion auf, indem du ihren Namen gefolgt von Klammern verwendest. Wenn die Funktion Parameter oder Eingaben erwartet, stellst du Werte bereit, genannt Argumente, innerhalb der Klammern.

Calling the greet function, no arguments needed: greet(). Die greet-Funktion aufrufen, keine Argumente benötigt: greet().

Calling the calculate_rectangle_area function with arguments: rect_length equals 10, rect_width equals 5, result_area equals calculate_rectangle_area(rect_length, rect_width). Arguments are 10 and 5. print("The calculated area is:", result_area). Die calculate_rectangle_area-Funktion mit Argumenten aufrufen: rect_length gleich 10, rect_width gleich 5, result_area gleich calculate_rectangle_area(rect_length, rect_width). Argumente sind 10 und 5. print("Die berechnete Fläche ist:", result_area).

You can also pass literal values as arguments: another_area equals calculate_rectangle_area(7, 3). print("Another area:", another_area). Du kannst auch literale Werte als Argumente übergeben: another_area gleich calculate_rectangle_area(7, 3). print("Eine andere Fläche:", another_area).

Output of the above code: Hello there! The calculated area is: 50. Another area: 21. Ausgabe des obigen Codes: Hallo dort! Die berechnete Fläche ist: 50. Eine andere Fläche: 21.

Notice how calculate_rectangle_area returns a value, which we store in variables, result_area and another_area, and then print. The greet function doesn't return anything explicitly, it returns None, it just performs an action, printing. Beachte, wie calculate_rectangle_area einen Wert zurückgibt, den wir in Variablen speichern, result_area und another_area, und dann ausgeben. Die greet-Funktion gibt nichts explizit zurück, sie gibt None zurück, sie führt nur eine Aktion aus, das Ausgeben.

Try it yourself Probiere es selbst aus

Define a function called say_goodbye that takes one parameter name and prints "Goodbye, [name]!". Then, call this function with your own name as the argument. Definiere eine Funktion namens say_goodbye, die einen Parameter name nimmt und "Auf Wiedersehen, [name]!" ausgibt. Rufe dann diese Funktion mit deinem eigenen Namen als Argument auf.

Parameters versus Arguments Parameter versus Argumente

These terms are often used interchangeably, but there's a subtle difference: Diese Begriffe werden oft austauschbar verwendet, aber es gibt einen subtilen Unterschied:

Parameters: Variables listed inside the parentheses in the function definition. They are placeholders for the inputs. For example, length and width in def calculate_rectangle_area(length, width). Parameter: Variablen, die innerhalb der Klammern in der Funktionsdefinition aufgelistet sind. Sie sind Platzhalter für die Eingaben. Zum Beispiel length und width in def calculate_rectangle_area(length, width).

Arguments: The actual values passed to the function when it is called. For example, 10 and 5 in calculate_rectangle_area(10, 5). Argumente: Die tatsächlichen Werte, die an die Funktion übergeben werden, wenn sie aufgerufen wird. Zum Beispiel 10 und 5 in calculate_rectangle_area(10, 5).

The return Statement Die return-Anweisung

The return statement does two things: Immediately exits the function. No code after return in the function block will be executed. Sends a value back to the caller. Die return-Anweisung macht zwei Dinge: Verlässt sofort die Funktion. Kein Code nach return im Funktionsblock wird ausgeführt. Sendet einen Wert zurück an den Aufrufer.

A function can return any type of value: numbers, strings, lists, booleans, even None. Eine Funktion kann jeden Typ von Wert zurückgeben: Zahlen, Strings, Listen, Booleans, sogar None.

def add_numbers(x, y), colon. Adds two numbers and returns the sum. total equals x plus y. return total. print("This line will never be printed."). Code after return is unreachable. def add_numbers(x, y), Doppelpunkt. Addiert zwei Zahlen und gibt die Summe zurück. total gleich x plus y. return total. print("Diese Zeile wird nie ausgegeben."). Code nach return ist unerreichbar.

sum_result equals add_numbers(5, 3). print(sum_result). Output: 8. sum_result gleich add_numbers(5, 3). print(sum_result). Ausgabe: 8.

def check_even(number), colon. Checks if a number is even. if number modulo 2 double equals 0, colon, return True. Return boolean True if even. else, colon, return False. Return boolean False if odd. def check_even(number), Doppelpunkt. Prüft, ob eine Zahl gerade ist. if number modulo 2 doppelgleich 0, Doppelpunkt, return True. Gibt Boolean True zurück, wenn gerade. else, Doppelpunkt, return False. Gibt Boolean False zurück, wenn ungerade.

is_10_even equals check_even(10). print(is_10_even). Output: True. is_7_even equals check_even(7). print(is_7_even). Output: False. is_10_even gleich check_even(10). print(is_10_even). Ausgabe: True. is_7_even gleich check_even(7). print(is_7_even). Ausgabe: False.

If a function doesn't have a return statement, or just has return with no value, it automatically returns None. Wenn eine Funktion keine return-Anweisung hat, oder nur return ohne Wert hat, gibt sie automatisch None zurück.

def simple_print(message), colon. Prints a message but doesn't return anything explicitly. print(message). def simple_print(message), Doppelpunkt. Gibt eine Nachricht aus, gibt aber nichts explizit zurück. print(message).

result equals simple_print("Hello again"). print(result). result gleich simple_print("Hallo nochmal"). print(result).

Output: Hello again. None. Ausgabe: Hallo nochmal. None.

Why Use Functions? Warum Funktionen verwenden?

Organization: Break down complex problems into smaller, manageable pieces. A program made of well-defined functions is easier to read and understand. Organisation: Zerlege komplexe Probleme in kleinere, handhabbare Teile. Ein Programm, das aus gut definierten Funktionen besteht, ist leichter zu lesen und zu verstehen.

Reusability, DRY Principle: DRY stands for "Don't Repeat Yourself". Write code once and reuse it multiple times by calling the function. This saves time and reduces errors. Wiederverwendbarkeit, DRY-Prinzip: DRY steht für "Don't Repeat Yourself", wiederhole dich nicht. Schreibe Code einmal und verwende ihn mehrmals wieder, indem du die Funktion aufrufst. Das spart Zeit und reduziert Fehler.

Maintainability: If you need to update or fix logic, you only need to change it in one place, the function definition. Wartbarkeit: Wenn du Logik aktualisieren oder korrigieren musst, musst du sie nur an einer Stelle ändern, der Funktionsdefinition.

Abstraction: You can use a function without needing to know the details of how it works internally. You just need to know its name, what inputs it needs, parameters, and what output it gives, return value. Abstraktion: Du kannst eine Funktion verwenden, ohne die Details zu kennen, wie sie intern funktioniert. Du musst nur ihren Namen kennen, welche Eingaben sie braucht, Parameter, und welche Ausgabe sie gibt, Rückgabewert.

Think about it Denke darüber nach

Consider the programs you've written so far, using conditions, lists, loops. Can you identify parts of your code that were repeated? How could you rewrite those parts using functions to make the code shorter and cleaner? Betrachte die Programme, die du bisher geschrieben hast, mit Bedingungen, Listen, Schleifen. Kannst du Teile deines Codes identifizieren, die wiederholt wurden? Wie könntest du diese Teile mit Funktionen umschreiben, um den Code kürzer und sauberer zu machen?

Scope: Where Variables Live Scope: Wo Variablen leben

An important concept related to functions is scope. Scope refers to the region of your code where a variable can be accessed. Ein wichtiges Konzept im Zusammenhang mit Funktionen ist Scope. Scope bezieht sich auf den Bereich deines Codes, wo auf eine Variable zugegriffen werden kann.

Local Scope: Variables defined inside a function, including its parameters, are local to that function. They can only be accessed from within that function. They are created when the function is called and destroyed when the function finishes. Lokaler Scope: Variablen, die innerhalb einer Funktion definiert sind, einschließlich ihrer Parameter, sind lokal zu dieser Funktion. Auf sie kann nur von innerhalb dieser Funktion zugegriffen werden. Sie werden erstellt, wenn die Funktion aufgerufen wird, und zerstört, wenn die Funktion endet.

Global Scope: Variables defined outside of any function have global scope. They can be accessed from anywhere in your script, including inside functions. Though modifying global variables from within functions requires special care and is often discouraged. Globaler Scope: Variablen, die außerhalb jeder Funktion definiert sind, haben globalen Scope. Auf sie kann von überall in deinem Skript zugegriffen werden, einschließlich innerhalb von Funktionen. Obwohl das Ändern globaler Variablen von innerhalb von Funktionen besondere Vorsicht erfordert und oft nicht empfohlen wird.

global_variable equals "I am global". def my_function(), colon, local_variable equals "I am local". print(local_variable). Works: Accessing local variable inside the function. print(global_variable). Works: Accessing global variable inside the function. global_variable gleich "Ich bin global". def my_function(), Doppelpunkt, local_variable gleich "Ich bin lokal". print(local_variable). Funktioniert: Zugriff auf lokale Variable innerhalb der Funktion. print(global_variable). Funktioniert: Zugriff auf globale Variable innerhalb der Funktion.

my_function(). print(global_variable). Works: Accessing global variable outside the function. print(local_variable). This would cause an error! Cannot access local_variable here. my_function(). print(global_variable). Funktioniert: Zugriff auf globale Variable außerhalb der Funktion. print(local_variable). Das würde einen Fehler verursachen! Kann nicht auf local_variable hier zugreifen.

Understanding scope helps prevent naming conflicts and unexpected behavior in your programs. For now, focus on the fact that variables created inside a function generally stay inside that function. Das Verständnis von Scope hilft, Namenskonflikte und unerwartetes Verhalten in deinen Programmen zu verhindern. Konzentriere dich vorerst auf die Tatsache, dass Variablen, die innerhalb einer Funktion erstellt werden, im Allgemeinen innerhalb dieser Funktion bleiben.

That's the basics of defining and using functions in Python! Prepare any questions you have for the live session. Das sind die Grundlagen des Definierens und Verwendens von Funktionen in Python! Bereite alle Fragen vor, die du für die Live-Sitzung hast.