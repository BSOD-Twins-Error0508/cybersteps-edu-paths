Welcome! In programming, we often need to repeat a block of code multiple times. Instead of writing the same code over and over again, we use loops. Loops allow us to execute a statement or a group of statements multiple times efficiently. Python provides two primary types of loops: for loops and while loops. We'll also look at ways to control the flow within loops using break and continue. Willkommen! In der Programmierung müssen wir oft einen Codeblock mehrmals wiederholen. Anstatt denselben Code immer wieder zu schreiben, verwenden wir Schleifen. Schleifen ermöglichen es uns, eine Anweisung oder eine Gruppe von Anweisungen mehrmals effizient auszuführen. Python bietet zwei Haupttypen von Schleifen: for-Schleifen und while-Schleifen. Wir werden uns auch Möglichkeiten ansehen, den Ablauf innerhalb von Schleifen mit break und continue zu steuern.

Why Use Loops? Warum Schleifen verwenden?

Imagine you need to print the numbers from 1 to 5. You could write: print(1), print(2), print(3), print(4), print(5). Stell dir vor, du musst die Zahlen von 1 bis 5 ausgeben. Du könntest schreiben: print(1), print(2), print(3), print(4), print(5).

This works, but what if you needed to print numbers from 1 to 100? Or 1 to 1,000,000? Writing a print statement for each number would be incredibly tedious and error-prone. Loops solve this problem by allowing you to specify the action, printing a number, and the range or condition for repetition. Das funktioniert, aber was ist, wenn du Zahlen von 1 bis 100 ausgeben müsstest? Oder von 1 bis 1.000.000? Eine Print-Anweisung für jede Zahl zu schreiben wäre unglaublich mühsam und fehleranfällig. Schleifen lösen dieses Problem, indem sie dir erlauben, die Aktion, das Ausgeben einer Zahl, und den Bereich oder die Bedingung für die Wiederholung festzulegen.

The for Loop Die for-Schleife

The for loop in Python is used for iterating over a sequence, like a list, tuple, dictionary, set, or string, or other iterable object. With the for loop, we can execute a set of statements, once for each item in a sequence. Die for-Schleife in Python wird verwendet, um über eine Sequenz zu iterieren, wie eine Liste, ein Tupel, ein Dictionary, eine Menge oder einen String, oder ein anderes iterierbares Objekt. Mit der for-Schleife können wir eine Reihe von Anweisungen ausführen, einmal für jedes Element in einer Sequenz.

Syntax: for variable in sequence, colon, code block to execute for each item. Indentation matters here! statement1, statement2, and so on. Syntax: for Variable in Sequenz, Doppelpunkt, Codeblock, der für jedes Element ausgeführt wird. Einrückung ist hier wichtig! Anweisung1, Anweisung2, und so weiter.

Variable: In each iteration, this variable takes the value of the next item in the sequence. Variable: In jeder Iteration nimmt diese Variable den Wert des nächsten Elements in der Sequenz an.

Sequence: This is the collection of items you want to loop through, for example a list. Sequenz: Dies ist die Sammlung von Elementen, durch die du durchlaufen möchtest, zum Beispiel eine Liste.

The code block inside the loop, indented, is executed for each item. Der Codeblock innerhalb der Schleife, eingerückt, wird für jedes Element ausgeführt.

Example: Looping Through a List Beispiel: Durch eine Liste durchlaufen

fruits equals ["apple", "banana", "cherry"]. print("Available fruits:"). for fruit in fruits, colon, print(f"- {fruit}"). print("Loop finished!"). fruits gleich ["apple", "banana", "cherry"]. print("Verfügbare Früchte:"). for fruit in fruits, Doppelpunkt, print(f"- {fruit}"). print("Schleife beendet!").

Output: Available fruits: dash apple, dash banana, dash cherry, Loop finished! Ausgabe: Verfügbare Früchte: Strich apple, Strich banana, Strich cherry, Schleife beendet!

In this example, the for loop goes through the fruits list. In the first iteration, fruit is "apple", and dash apple is printed. In the second, fruit is "banana", and dash banana is printed. In the third, fruit is "cherry", and dash cherry is printed. After the last item, the loop ends, and "Loop finished!" is printed. In diesem Beispiel geht die for-Schleife durch die fruits-Liste. In der ersten Iteration ist fruit "apple", und Strich apple wird ausgegeben. In der zweiten ist fruit "banana", und Strich banana wird ausgegeben. In der dritten ist fruit "cherry", und Strich cherry wird ausgegeben. Nach dem letzten Element endet die Schleife, und "Schleife beendet!" wird ausgegeben.

The range() Function Die range()-Funktion

Often, you want to loop a specific number of times, or loop through a sequence of numbers. The range() function is perfect for this. It generates a sequence of numbers. Oft möchtest du eine bestimmte Anzahl von Malen durchlaufen oder durch eine Sequenz von Zahlen iterieren. Die range()-Funktion ist dafür perfekt. Sie erzeugt eine Sequenz von Zahlen.

range(stop): Generates numbers from 0 up to, but not including, stop. range(5) generates 0, 1, 2, 3, 4. range(stop): Erzeugt Zahlen von 0 bis, aber nicht einschließlich, stop. range(5) erzeugt 0, 1, 2, 3, 4.

range(start, stop): Generates numbers from start up to, but not including, stop. range(2, 6) generates 2, 3, 4, 5. range(start, stop): Erzeugt Zahlen von start bis, aber nicht einschließlich, stop. range(2, 6) erzeugt 2, 3, 4, 5.

range(start, stop, step): Generates numbers from start up to, but not including, stop, incrementing by step. range(1, 10, 2) generates 1, 3, 5, 7, 9. range(start, stop, step): Erzeugt Zahlen von start bis, aber nicht einschließlich, stop, mit Erhöhung um step. range(1, 10, 2) erzeugt 1, 3, 5, 7, 9.

Example: Using range() Beispiel: Verwendung von range()

Print numbers 0 to 4: print("Numbers 0 to 4:"). for i in range(5), colon, print(i). Zahlen 0 bis 4 ausgeben: print("Zahlen 0 bis 4:"). for i in range(5), Doppelpunkt, print(i).

Print numbers 3 to 6: print("Numbers 3 to 6:"). for number in range(3, 7), colon, print(number). Zahlen 3 bis 6 ausgeben: print("Zahlen 3 bis 6:"). for number in range(3, 7), Doppelpunkt, print(number).

Print even numbers from 2 to 10: print("Even numbers 2 to 10:"). for even_num in range(2, 11, 2), colon, print(even_num). Gerade Zahlen von 2 bis 10 ausgeben: print("Gerade Zahlen 2 bis 10:"). for even_num in range(2, 11, 2), Doppelpunkt, print(even_num).

Output: Numbers 0 to 4: 0, 1, 2, 3, 4. Numbers 3 to 6: 3, 4, 5, 6. Even numbers 2 to 10: 2, 4, 6, 8, 10. Ausgabe: Zahlen 0 bis 4: 0, 1, 2, 3, 4. Zahlen 3 bis 6: 3, 4, 5, 6. Gerade Zahlen 2 bis 10: 2, 4, 6, 8, 10.

Try it yourself Probiere es selbst aus

Write a for loop that prints the squares, number times number, of numbers from 1 to 5. Schreibe eine for-Schleife, die die Quadrate, Zahl mal Zahl, der Zahlen von 1 bis 5 ausgibt.

Create a list of your favorite cybersecurity tools as strings. Write a for loop to print each tool name. Erstelle eine Liste deiner bevorzugten Cybersicherheitswerkzeuge als Strings. Schreibe eine for-Schleife, um jeden Werkzeugnamen auszugeben.

The while Loop Die while-Schleife

The while loop executes a set of statements as long as a specified condition is True. It's useful when you don't know beforehand how many times you need to loop, but you know the condition under which the loop should continue. Die while-Schleife führt eine Reihe von Anweisungen aus, solange eine bestimmte Bedingung Wahr ist. Sie ist nützlich, wenn du nicht im Voraus weißt, wie oft du durchlaufen musst, aber die Bedingung kennst, unter der die Schleife fortgesetzt werden soll.

Syntax: while condition, colon, code block to execute as long as condition is True. Indentation matters! statement1, statement2, and so on. Often, you need to update variables used in the condition to eventually make it False and exit the loop. Syntax: while Bedingung, Doppelpunkt, Codeblock, der ausgeführt wird, solange Bedingung Wahr ist. Einrückung ist wichtig! Anweisung1, Anweisung2, und so weiter. Oft musst du Variablen aktualisieren, die in der Bedingung verwendet werden, um sie schließlich Falsch zu machen und die Schleife zu beenden.

Condition: A boolean expression that evaluates to True or False. The loop continues as long as this is True. Bedingung: Ein boolescher Ausdruck, der zu Wahr oder Falsch ausgewertet wird. Die Schleife läuft weiter, solange dies Wahr ist.

The code block inside the loop is executed repeatedly. Crucially, something inside the loop should eventually make the condition become False, otherwise you'll create an infinite loop. Der Codeblock innerhalb der Schleife wird wiederholt ausgeführt. Entscheidend ist, dass etwas innerhalb der Schleife die Bedingung schließlich Falsch machen sollte, sonst erzeugst du eine Endlosschleife.

Example: Counting with while Beispiel: Zählen mit while

count equals 0. print("Counting up to 3:"). while count less than 3, colon, print(f"Count is: {count}"). count equals count plus 1. Increment count, crucial to avoid infinite loop! print("Loop finished!"). count gleich 0. print("Bis 3 zählen:"). while count kleiner als 3, Doppelpunkt, print(f"Zähler ist: {count}"). count gleich count plus 1. Erhöhe count, entscheidend, um Endlosschleife zu vermeiden! print("Schleife beendet!").

Output: Counting up to 3: Count is: 0, Count is: 1, Count is: 2, Loop finished! Ausgabe: Bis 3 zählen: Zähler ist: 0, Zähler ist: 1, Zähler ist: 2, Schleife beendet!

Here, the loop continues as long as count is less than 3. Inside the loop, we print the current value of count and then increment it, count equals count plus 1. When count becomes 3, the condition count less than 3 becomes False, and the loop terminates. Hier läuft die Schleife weiter, solange count kleiner als 3 ist. Innerhalb der Schleife geben wir den aktuellen Wert von count aus und erhöhen ihn dann, count gleich count plus 1. Wenn count 3 wird, wird die Bedingung count kleiner als 3 Falsch, und die Schleife endet.

Think about it Denke darüber nach

When might you prefer a while loop over a for loop? Consider scenarios like waiting for user input or processing data until a specific marker is found. Wann könntest du eine while-Schleife einer for-Schleife vorziehen? Betrachte Szenarien wie das Warten auf Benutzereingaben oder das Verarbeiten von Daten, bis ein bestimmter Marker gefunden wird.

Controlling Loop Flow: break and continue Schleifenablauf steuern: break und continue

Sometimes you need more control over how a loop executes. Python provides two statements for this: break and continue. Manchmal brauchst du mehr Kontrolle darüber, wie eine Schleife ausgeführt wird. Python bietet zwei Anweisungen dafür: break und continue.

The break Statement Die break-Anweisung

The break statement immediately terminates the current loop, the innermost loop if nested. Execution resumes at the first statement after the loop. Die break-Anweisung beendet sofort die aktuelle Schleife, die innerste Schleife, wenn verschachtelt. Die Ausführung wird mit der ersten Anweisung nach der Schleife fortgesetzt.

Example: Using break Beispiel: Verwendung von break

Let's find the first number divisible by 3 in a sequence. Lass uns die erste Zahl finden, die durch 3 teilbar ist, in einer Sequenz.

numbers equals [1, 2, 4, 3, 5, 6]. print("Searching for the first number divisible by 3..."). for num in numbers, colon, print(f"Checking {num}..."). numbers gleich [1, 2, 4, 3, 5, 6]. print("Suche nach der ersten Zahl, die durch 3 teilbar ist..."). for num in numbers, Doppelpunkt, print(f"Prüfe {num}...").

if num modulo 3 double equals 0, colon. The modulo operator gives the remainder of a division. print(f"Found it! {num} is divisible by 3."). break. Exit the loop immediately. print("Loop finished or broken."). if num modulo 3 doppelgleich 0, Doppelpunkt. Der Modulo-Operator gibt den Rest einer Division. print(f"Gefunden! {num} ist durch 3 teilbar."). break. Verlasse die Schleife sofort. print("Schleife beendet oder abgebrochen.").

Output: Searching for the first number divisible by 3... Checking 1... Checking 2... Checking 4... Checking 3... Found it! 3 is divisible by 3. Loop finished or broken. Ausgabe: Suche nach der ersten Zahl, die durch 3 teilbar ist... Prüfe 1... Prüfe 2... Prüfe 4... Prüfe 3... Gefunden! 3 ist durch 3 teilbar. Schleife beendet oder abgebrochen.

Notice that once num becomes 3, the if condition is met, the message is printed, and break is executed. The loop stops immediately, and the numbers 5 and 6 are never checked. Beachte, dass sobald num zu 3 wird, die if-Bedingung erfüllt ist, die Nachricht ausgegeben wird und break ausgeführt wird. Die Schleife stoppt sofort, und die Zahlen 5 und 6 werden nie überprüft.

The continue Statement Die continue-Anweisung

The continue statement skips the rest of the code inside the current iteration of the loop and proceeds to the next iteration. Die continue-Anweisung überspringt den Rest des Codes innerhalb der aktuellen Iteration der Schleife und fährt mit der nächsten Iteration fort.

Example: Using continue Beispiel: Verwendung von continue

Let's print only the even numbers from a list. Lass uns nur die geraden Zahlen aus einer Liste ausgeben.

numbers equals [1, 2, 3, 4, 5, 6]. print("Printing even numbers:"). for num in numbers, colon, if num modulo 2 not equal 0, colon. If the number is odd, not divisible by 2. continue. Skip the rest of this iteration and go to the next number. numbers gleich [1, 2, 3, 4, 5, 6]. print("Gerade Zahlen ausgeben:"). for num in numbers, Doppelpunkt, if num modulo 2 ungleich 0, Doppelpunkt. Wenn die Zahl ungerade ist, nicht durch 2 teilbar. continue. Überspringe den Rest dieser Iteration und gehe zur nächsten Zahl.

This print statement is only reached if the number is even. print(num). print("Loop finished."). Diese Print-Anweisung wird nur erreicht, wenn die Zahl gerade ist. print(num). print("Schleife beendet.").

Output: Printing even numbers: 2, 4, 6, Loop finished. Ausgabe: Gerade Zahlen ausgeben: 2, 4, 6, Schleife beendet.

When num is 1, 3, or 5, the if condition num modulo 2 not equal 0 is True. The continue statement is executed, skipping the print(num) line for that iteration. The loop then moves to the next number. When num is 2, 4, or 6, the if condition is False, continue is skipped, and print(num) is executed. Wenn num 1, 3 oder 5 ist, ist die if-Bedingung num modulo 2 ungleich 0 Wahr. Die continue-Anweisung wird ausgeführt, wodurch die print(num)-Zeile für diese Iteration übersprungen wird. Die Schleife geht dann zur nächsten Zahl. Wenn num 2, 4 oder 6 ist, ist die if-Bedingung Falsch, continue wird übersprungen, und print(num) wird ausgeführt.

Try it yourself Probiere es selbst aus

Write a while loop that asks the user for input until they type "quit". Schreibe eine while-Schleife, die den Benutzer um Eingabe bittet, bis er "quit" eingibt.

Write a for loop using range(1, 11) that prints numbers, but skips printing the number 5 using continue. Schreibe eine for-Schleife mit range(1, 11), die Zahlen ausgibt, aber das Ausgeben der Zahl 5 mit continue überspringt.

Summary Zusammenfassung

Loops automate repetitive tasks. Schleifen automatisieren sich wiederholende Aufgaben.

for loops iterate over sequences, like lists, strings, range(), et cetera. Use when you know how many times to iterate or want to process each item in a collection. for-Schleifen iterieren über Sequenzen, wie Listen, Strings, range() und so weiter. Verwende sie, wenn du weißt, wie oft du iterieren musst oder jedes Element in einer Sammlung verarbeiten möchtest.

while loops repeat as long as a condition is True. Use when the number of iterations is unknown beforehand. Be careful to avoid infinite loops! while-Schleifen wiederholen sich, solange eine Bedingung Wahr ist. Verwende sie, wenn die Anzahl der Iterationen im Voraus unbekannt ist. Sei vorsichtig, um Endlosschleifen zu vermeiden!

range(start, stop, step) generates sequences of numbers, often used with for loops. range(start, stop, step) erzeugt Sequenzen von Zahlen, die oft mit for-Schleifen verwendet werden.

break exits the current loop entirely. break verlässt die aktuelle Schleife vollständig.

continue skips the current iteration and moves to the next one. continue überspringt die aktuelle Iteration und geht zur nächsten.

Understanding loops is fundamental to writing effective Python code, especially in cybersecurity tasks like processing log files, scanning networks, or automating analyses. Make sure you're comfortable with these concepts before the class session! Das Verständnis von Schleifen ist grundlegend für das Schreiben effektiven Python-Codes, besonders bei Cybersicherheitsaufgaben wie dem Verarbeiten von Logdateien, dem Scannen von Netzwerken oder dem Automatisieren von Analysen. Stelle sicher, dass du mit diesen Konzepten vertraut bist, bevor die Unterrichtsstunde beginnt!