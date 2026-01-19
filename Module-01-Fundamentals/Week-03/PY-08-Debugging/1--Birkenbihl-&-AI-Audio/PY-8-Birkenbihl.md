Welcome! Before our live session on debugging, please go through this material. It introduces the concept of bugs in programming and the basic techniques we use to find and fix them. Willkommen! Vor unserer Live-Sitzung über Debugging gehe bitte dieses Material durch. Es führt in das Konzept von Bugs in der Programmierung ein und die grundlegenden Techniken, die wir verwenden, um sie zu finden und zu beheben.

What is a Bug? Was ist ein Bug?

Computer bugs used to be actual bugs! Computer-Bugs waren früher tatsächliche Insekten!

In programming, a bug is simply an error or flaw in your code that causes it to produce an incorrect or unexpected result, or to behave in unintended ways. Bugs can range from simple typos to complex logical errors. The process of finding and fixing these bugs is called debugging. In der Programmierung ist ein Bug einfach ein Fehler oder Mangel in deinem Code, der dazu führt, dass er ein falsches oder unerwartetes Ergebnis produziert oder sich auf unbeabsichtigte Weise verhält. Bugs können von einfachen Tippfehlern bis zu komplexen logischen Fehlern reichen. Der Prozess, diese Bugs zu finden und zu beheben, wird Debugging genannt.

Think of writing code like giving instructions to a computer. If your instructions are unclear, ambiguous, or just plain wrong, the computer won't do what you want it to do. Denke beim Schreiben von Code daran, dass du einem Computer Anweisungen gibst. Wenn deine Anweisungen unklar, mehrdeutig oder einfach falsch sind, wird der Computer nicht tun, was du von ihm willst.

Common Types of Bugs Häufige Arten von Bugs

There are three main categories of bugs you'll encounter: Es gibt drei Hauptkategorien von Bugs, denen du begegnen wirst:

Syntax Errors: These are like grammatical errors in your code. Python has strict rules about how code must be written, its syntax. If you break these rules, Python won't even be able to run your code. These are often the easiest to find because Python will usually tell you exactly where the error occurred. Syntax-Fehler: Diese sind wie grammatikalische Fehler in deinem Code. Python hat strenge Regeln darüber, wie Code geschrieben werden muss, seine Syntax. Wenn du diese Regeln brichst, wird Python nicht einmal in der Lage sein, deinen Code auszuführen. Diese sind oft am einfachsten zu finden, weil Python dir normalerweise genau sagt, wo der Fehler aufgetreten ist.

Example: Forgetting a colon at the end of an if statement or a for loop definition, misspelling a keyword like whlie instead of while, or having mismatched parentheses. Beispiel: Einen Doppelpunkt am Ende einer if-Anweisung oder einer for-Schleifen-Definition vergessen, ein Schlüsselwort falsch schreiben wie whlie anstatt while, oder nicht zusammenpassende Klammern haben.

Runtime Errors: These errors occur while your program is running. The syntax might be correct, but something unexpected happens during execution. The program starts running but crashes partway through. Laufzeitfehler: Diese Fehler treten auf, während dein Programm läuft. Die Syntax mag korrekt sein, aber etwas Unerwartetes passiert während der Ausführung. Das Programm beginnt zu laufen, stürzt aber auf halbem Weg ab.

Example: Trying to divide a number by zero, trying to access an item in a list using an index that doesn't exist, for example accessing my_list[10] when the list only has 5 items, or trying to use a variable that hasn't been defined yet. Python will usually report a Traceback when a runtime error occurs, giving clues about where the problem happened. Beispiel: Versuchen, eine Zahl durch Null zu teilen, versuchen, auf ein Element in einer Liste mit einem Index zuzugreifen, der nicht existiert, zum Beispiel auf my_list[10] zugreifen, wenn die Liste nur 5 Elemente hat, oder versuchen, eine Variable zu verwenden, die noch nicht definiert wurde. Python wird normalerweise einen Traceback melden, wenn ein Laufzeitfehler auftritt, der Hinweise darauf gibt, wo das Problem aufgetreten ist.

Logic Errors: These are often the trickiest bugs. The code runs without crashing, no syntax or runtime errors, but it doesn't do what you intended it to do. The result is incorrect or unexpected. The computer is doing exactly what you told it to do, but what you told it to do was wrong. Logikfehler: Diese sind oft die kniffligsten Bugs. Der Code läuft ohne abzustürzen, keine Syntax- oder Laufzeitfehler, aber er tut nicht, was du beabsichtigt hast. Das Ergebnis ist falsch oder unerwartet. Der Computer tut genau das, was du ihm gesagt hast, aber was du ihm gesagt hast zu tun, war falsch.

Example: You want to calculate the average of a list of numbers, but you accidentally divide by the wrong count. You write a condition for an if statement that doesn't quite capture the logic you needed. You use greater than when you meant to use greater than or equal to. Beispiel: Du willst den Durchschnitt einer Liste von Zahlen berechnen, aber du teilst versehentlich durch die falsche Anzahl. Du schreibst eine Bedingung für eine if-Anweisung, die die Logik, die du brauchtest, nicht ganz erfasst. Du verwendest größer als, wenn du größer oder gleich meintest.

Think about it Denke darüber nach

Consider the following code snippet which aims to print numbers from 0 to 4: count equals 0, while count greater than 5, colon, print(count), count equals count plus 1. Betrachte den folgenden Code-Ausschnitt, der darauf abzielt, Zahlen von 0 bis 4 auszugeben: count gleich 0, while count größer als 5, Doppelpunkt, print(count), count gleich count plus 1.

What type of error is this: Syntax, Runtime, or Logic? Why won't it work as intended? Welche Art von Fehler ist das: Syntax, Laufzeit oder Logik? Warum wird es nicht wie beabsichtigt funktionieren?

The Debugging Process Der Debugging-Prozess

Debugging isn't just randomly changing code until it works. It's a systematic process: Debugging bedeutet nicht, einfach Code zufällig zu ändern, bis er funktioniert. Es ist ein systematischer Prozess:

Understand the Problem: Reproduce the bug consistently. Know what the expected output or behavior is and what the actual, incorrect, output or behavior is. Das Problem verstehen: Reproduziere den Bug konsistent. Wisse, was die erwartete Ausgabe oder das Verhalten ist und was die tatsächliche, falsche, Ausgabe oder das Verhalten ist.

Find the Source, Isolate the Bug: Narrow down where in the code the error is occurring. This is often the hardest part. Die Quelle finden, den Bug isolieren: Grenze ein, wo im Code der Fehler auftritt. Das ist oft der schwierigste Teil.

Fix the Bug: Correct the code. Den Bug beheben: Korrigiere den Code.

Test the Fix: Run the code again, including tests for edge cases, to ensure the bug is gone and you haven't introduced new ones. Die Behebung testen: Führe den Code erneut aus, einschließlich Tests für Grenzfälle, um sicherzustellen, dass der Bug verschwunden ist und du keine neuen eingeführt hast.

Basic Debugging Technique: Print Statements Grundlegende Debugging-Technik: Print-Anweisungen

One of the simplest yet most effective debugging techniques is using print() statements. You can insert print() calls at various points in your code to check the values of variables or see which parts of your code are being executed. Eine der einfachsten und dennoch effektivsten Debugging-Techniken ist die Verwendung von print()-Anweisungen. Du kannst print()-Aufrufe an verschiedenen Stellen in deinem Code einfügen, um die Werte von Variablen zu überprüfen oder zu sehen, welche Teile deines Codes ausgeführt werden.

Example: Imagine a loop isn't behaving as expected. Beispiel: Stell dir vor, eine Schleife verhält sich nicht wie erwartet.

Original code, buggy: numbers equals [1, 2, 3, 4, 5], total equals 10. Start with an incorrect initial total. for num in numbers, colon, total equals total plus num. Expected total is 1 plus 2 plus 3 plus 4 plus 5 equals 15, but we started total at 10. Ursprünglicher Code, fehlerhaft: numbers gleich [1, 2, 3, 4, 5], total gleich 10. Beginne mit einem falschen Anfangswert für total. for num in numbers, Doppelpunkt, total gleich total plus num. Erwartetes total ist 1 plus 2 plus 3 plus 4 plus 5 gleich 15, aber wir haben total bei 10 gestartet.

print(f"Final total: {total}"). Output: Final total: 25. Incorrect! print(f"Finales total: {total}"). Ausgabe: Finales total: 25. Falsch!

Debugging with print: numbers equals [1, 2, 3, 4, 5], total equals 10. Start with an incorrect initial total. print(f"Starting total: {total}"). Check initial value. Debugging mit print: numbers gleich [1, 2, 3, 4, 5], total gleich 10. Beginne mit einem falschen Anfangswert für total. print(f"Start-total: {total}"). Überprüfe Anfangswert.

for num in numbers, colon, print(f"Current number: {num}"). Check number being processed. total equals total plus num. print(f"Total after adding {num}: {total}"). Check total in each iteration. for num in numbers, Doppelpunkt, print(f"Aktuelle Zahl: {num}"). Überprüfe die verarbeitete Zahl. total gleich total plus num. print(f"Total nach Hinzufügen von {num}: {total}"). Überprüfe total in jeder Iteration.

print(f"Final total: {total}"). print(f"Finales total: {total}").

By adding print statements, you can trace the execution flow and see exactly where the total variable's value goes wrong. In this case, you'd see it started at 10 instead of 0. Once you find the bug, you remove the debug print statements. Durch Hinzufügen von print-Anweisungen kannst du den Ausführungsablauf verfolgen und genau sehen, wo der Wert der total-Variable falsch wird. In diesem Fall würdest du sehen, dass sie bei 10 statt bei 0 gestartet ist. Sobald du den Bug gefunden hast, entfernst du die Debug-print-Anweisungen.

Try it yourself Probiere es selbst aus

Take the buggy code from the "Think about it" section earlier. Add print statements inside and outside the loop to understand why it's not executing. What do you observe? Nimm den fehlerhaften Code aus dem "Denke darüber nach"-Abschnitt von vorhin. Füge print-Anweisungen innerhalb und außerhalb der Schleife hinzu, um zu verstehen, warum sie nicht ausgeführt wird. Was beobachtest du?

Introduction to IDE Debuggers, Visual Studio Code Einführung in IDE-Debugger, Visual Studio Code

While print statements are useful, Integrated Development Environments, or IDEs, like Visual Studio Code have built-in debugging tools that are much more powerful. They allow you to: Während print-Anweisungen nützlich sind, haben Integrierte Entwicklungsumgebungen, oder IDEs, wie Visual Studio Code eingebaute Debugging-Werkzeuge, die viel leistungsfähiger sind. Sie ermöglichen es dir:

Set Breakpoints: Mark lines in your code where you want the execution to pause. Haltepunkte setzen: Markiere Zeilen in deinem Code, wo die Ausführung pausieren soll.

Step Through Code: Execute your code line by line, Step Over, step into functions, Step Into, or step out of functions, Step Out. Durch Code durchgehen: Führe deinen Code Zeile für Zeile aus, Step Over, in Funktionen hinein, Step Into, oder aus Funktionen heraus, Step Out.

Inspect Variables: Examine the values of variables at any point while the code is paused. Variablen untersuchen: Untersuche die Werte von Variablen an jedem Punkt, während der Code pausiert ist.

Watch Expressions: Monitor specific variables or expressions as the code executes. Ausdrücke beobachten: Überwache bestimmte Variablen oder Ausdrücke, während der Code ausgeführt wird.

View the Call Stack: See the sequence of function calls that led to the current point in the code. Den Call Stack ansehen: Sieh die Sequenz von Funktionsaufrufen, die zum aktuellen Punkt im Code geführt haben.

Using a debugger lets you observe your program's state in detail without cluttering your code with temporary print statements. Die Verwendung eines Debuggers ermöglicht es dir, den Zustand deines Programms im Detail zu beobachten, ohne deinen Code mit temporären print-Anweisungen zu überladen.

Setup Einrichtung

Visual Studio Code: Ensure you have Visual Studio Code installed and the Python extension is enabled. You should already have this from previous lessons. Visual Studio Code: Stelle sicher, dass du Visual Studio Code installiert hast und die Python-Erweiterung aktiviert ist. Du solltest das bereits aus vorherigen Lektionen haben.

Basic Python File: Create a simple Python file, for example debugger_test.py, with the following code: Grundlegende Python-Datei: Erstelle eine einfache Python-Datei, zum Beispiel debugger_test.py, mit folgendem Code:

def add_numbers(a, b), colon, result equals a plus b, return result. def add_numbers(a, b), Doppelpunkt, result gleich a plus b, return result.

x equals 5, y equals 10, sum_result equals add_numbers(x, y). x gleich 5, y gleich 10, sum_result gleich add_numbers(x, y).

print(f"The sum of {x} and {y} is: {sum_result}"). print(f"Die Summe von {x} und {y} ist: {sum_result}").

if sum_result greater than 10, colon, print("The result is greater than 10."), else, colon, print("The result is not greater than 10."). if sum_result größer als 10, Doppelpunkt, print("Das Ergebnis ist größer als 10."), else, Doppelpunkt, print("Das Ergebnis ist nicht größer als 10.").

print("Finished!"). print("Fertig!").

Practice Setting a Breakpoint: Übe das Setzen eines Haltepunkts:

Open debugger_test.py in Visual Studio Code. Öffne debugger_test.py in Visual Studio Code.

Click in the gutter, the space to the left of the line numbers, next to the line result equals a plus b inside the add_numbers function. A red dot should appear. This is a breakpoint. Klicke in den Rand, den Bereich links von den Zeilennummern, neben der Zeile result gleich a plus b innerhalb der add_numbers-Funktion. Ein roter Punkt sollte erscheinen. Das ist ein Haltepunkt.

Click in the gutter next to the line print(f"The sum of {x} and {y} is: {sum_result}"). Add another breakpoint here. Klicke in den Rand neben der Zeile print(f"Die Summe von {x} und {y} ist: {sum_result}"). Füge hier einen weiteren Haltepunkt hinzu.

Run with Debugger: Mit Debugger ausführen:

Go to the "Run and Debug" view in Visual Studio Code. It usually looks like a play button with a bug icon on the left sidebar. Gehe zur "Run and Debug"-Ansicht in Visual Studio Code. Sie sieht normalerweise wie ein Play-Button mit einem Bug-Symbol in der linken Seitenleiste aus.

Click the "Run and Debug" button. It might ask you to select a configuration, choose "Python File". Klicke auf den "Run and Debug"-Button. Es könnte dich bitten, eine Konfiguration auszuwählen, wähle "Python File".

Observe that the execution pauses at the first breakpoint inside the add_numbers function. Beobachte, dass die Ausführung am ersten Haltepunkt innerhalb der add_numbers-Funktion pausiert.

Explore the Debug view: Look at the "Variables" panel to see the values of a and b. Use the controls at the top: Continue, Step Over, Step Into, Step Out, to control execution. Press "Continue", the play icon, to run until the next breakpoint. Press "Continue" again to finish execution. Erkunde die Debug-Ansicht: Schaue dir das "Variables"-Panel an, um die Werte von a und b zu sehen. Verwende die Steuerelemente oben: Continue, Step Over, Step Into, Step Out, um die Ausführung zu steuern. Drücke "Continue", das Play-Symbol, um bis zum nächsten Haltepunkt zu laufen. Drücke "Continue" erneut, um die Ausführung abzuschließen.

Familiarize yourself with setting breakpoints and stepping through this simple script. We will explore the debugger in more detail during the live session. Mache dich vertraut mit dem Setzen von Haltepunkten und dem Durchgehen dieses einfachen Skripts. Wir werden den Debugger während der Live-Sitzung detaillierter erkunden.