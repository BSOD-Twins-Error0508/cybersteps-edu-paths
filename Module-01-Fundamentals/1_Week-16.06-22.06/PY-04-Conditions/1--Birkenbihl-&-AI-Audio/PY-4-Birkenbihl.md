Welcome to the world of decision-making in Python! So far, our scripts have run line by line, from top to bottom. But what if we want our program to do different things based on certain situations? That's where conditions come in. They allow our code to react dynamically to different inputs or states. Willkommen in der Welt der Entscheidungsfindung in Python! Bisher sind unsere Skripte Zeile für Zeile von oben nach unten gelaufen. Aber was ist, wenn wir wollen, dass unser Programm verschiedene Dinge tut, basierend auf bestimmten Situationen? Hier kommen Bedingungen ins Spiel. Sie ermöglichen es unserem Code, dynamisch auf verschiedene Eingaben oder Zustände zu reagieren.

What are Conditions? Was sind Bedingungen?

Here's an example: if days_learning_python greater than 0, print "Keep going!", else print "It's never too late to start". Hier ist ein Beispiel: wenn days_learning_python größer als 0, drucke "Mach weiter!", sonst drucke "Es ist nie zu spät, anzufangen".

In programming, conditions are statements that evaluate to either true or false. Think of them like questions the program asks itself. Based on the answer, true or false, the program decides which block of code to execute next. This ability to make decisions is fundamental to creating useful and interactive programs. In der Programmierung sind Bedingungen Anweisungen, die entweder zu wahr oder falsch ausgewertet werden. Denke an sie wie Fragen, die das Programm sich selbst stellt. Basierend auf der Antwort, wahr oder falsch, entscheidet das Programm, welchen Codeblock es als nächstes ausführt. Diese Fähigkeit, Entscheidungen zu treffen, ist grundlegend für die Erstellung nützlicher und interaktiver Programme.

Boolean Values: The Heart of Conditions Boolean-Werte: Das Herz der Bedingungen

At the core of every condition is a simple concept: Boolean values. A Boolean value can only be one of two things: True or False. Im Kern jeder Bedingung liegt ein einfaches Konzept: Boolean-Werte. Ein Boolean-Wert kann nur eines von zwei Dingen sein: Wahr oder Falsch.

Notice the capitalization. Python is case-sensitive, so True and False must start with a capital letter. These values represent the answers to the questions our conditions ask. Beachte die Großschreibung. Python unterscheidet zwischen Groß- und Kleinschreibung, also müssen Wahr und Falsch mit einem Großbuchstaben beginnen. Diese Werte repräsentieren die Antworten auf die Fragen, die unsere Bedingungen stellen.

Asking Questions: Comparison Operators Fragen stellen: Vergleichsoperatoren

How do we form these questions in Python? We use comparison operators. These operators compare two values and produce a Boolean result, True or False. Here are the most common ones: Wie formulieren wir diese Fragen in Python? Wir verwenden Vergleichsoperatoren. Diese Operatoren vergleichen zwei Werte und erzeugen ein Boolean-Ergebnis, Wahr oder Falsch. Hier sind die häufigsten:

Double equals: Equal to. Example: 5 double equals 5 results in True. Doppeltes Gleichheitszeichen: Gleich. Beispiel: 5 doppelgleich 5 ergibt Wahr.

Exclamation mark equals: Not equal to. Example: 5 not equal 6 results in True. Ausrufezeichen gleich: Ungleich. Beispiel: 5 ungleich 6 ergibt Wahr.

Greater than sign: Greater than. Example: 10 greater than 5 results in True. Größer-als-Zeichen: Größer als. Beispiel: 10 größer als 5 ergibt Wahr.

Less than sign: Less than. Example: 3 less than 8 results in True. Kleiner-als-Zeichen: Kleiner als. Beispiel: 3 kleiner als 8 ergibt Wahr.

Greater than or equals: Greater than or equal to. Example: 7 greater than or equal to 7 results in True. Größer-gleich: Größer als oder gleich. Beispiel: 7 größer oder gleich 7 ergibt Wahr.

Less than or equals: Less than or equal to. Example: 4 less than or equal to 3 results in False. Kleiner-gleich: Kleiner als oder gleich. Beispiel: 4 kleiner oder gleich 3 ergibt Falsch.

Important: Don't confuse the assignment operator, single equals, with the equality comparison operator, double equals. Wichtig: Verwechsle nicht den Zuweisungsoperator, einfaches Gleichheitszeichen, mit dem Gleichheitsvergleichsoperator, doppeltes Gleichheitszeichen.

x equals 5 assigns the value 5 to the variable x. x double equals 5 checks if the value of x is equal to 5 and results in True or False. x gleich 5 weist der Variable x den Wert 5 zu. x doppelgleich 5 prüft, ob der Wert von x gleich 5 ist und ergibt Wahr oder Falsch.

Try it yourself Probiere es selbst aus

Open your Python interpreter, or create a simple dot py file in Visual Studio Code and run it, and try out these comparisons. Use the print function to see the results: Öffne deinen Python-Interpreter oder erstelle eine einfache Punkt-py-Datei in Visual Studio Code und führe sie aus, und probiere diese Vergleiche aus. Verwende die Print-Funktion, um die Ergebnisse zu sehen:

print(10 double equals 10), print("hello" double equals "world"), print(5 greater than 2), age equals 25, print(age greater than or equal to 18), print(age not equal 25). print(10 doppelgleich 10), print("hallo" doppelgleich "welt"), print(5 größer als 2), age gleich 25, print(age größer oder gleich 18), print(age ungleich 25).

Making Decisions: The if Statement Entscheidungen treffen: Die if-Anweisung

The simplest way to use a condition is with an if statement. Its structure is: if condition, colon, then the code to execute if the condition is True. This block must be indented. Der einfachste Weg, eine Bedingung zu verwenden, ist mit einer if-Anweisung. Ihre Struktur ist: if Bedingung, Doppelpunkt, dann der Code, der ausgeführt wird, wenn die Bedingung Wahr ist. Dieser Block muss eingerückt sein.

For example: print("The condition was true!"). Code here runs regardless, as it's not indented under the if. print("This line runs anyway."). Zum Beispiel: print("Die Bedingung war wahr!"). Code hier wird unabhängig davon ausgeführt, da er nicht unter dem if eingerückt ist. print("Diese Zeile wird sowieso ausgeführt.").

The if keyword starts the statement. The condition is an expression that evaluates to True or False, for example age greater than 18, or name double equals "Alice". Das if-Schlüsselwort startet die Anweisung. Die Bedingung ist ein Ausdruck, der zu Wahr oder Falsch ausgewertet wird, zum Beispiel age größer als 18, oder name doppelgleich "Alice".

The colon marks the end of the condition. The indented block is the code that runs only if the condition is True. Indentation is crucial in Python; it defines code blocks. Usually, this is four spaces. Der Doppelpunkt markiert das Ende der Bedingung. Der eingerückte Block ist der Code, der nur ausgeführt wird, wenn die Bedingung Wahr ist. Einrückung ist entscheidend in Python; sie definiert Codeblöcke. Normalerweise sind das vier Leerzeichen.

Example: temperature equals 32. if temperature greater than 30, colon, print("It's a hot day!"). print("Have a nice day!"). Beispiel: temperature gleich 32. if temperature größer als 30, Doppelpunkt, print("Es ist ein heißer Tag!"). print("Hab einen schönen Tag!").

In this example, because temperature, 32, is greater than 30, the message "It's a hot day!" will be printed. "Have a nice day!" will always be printed because it's not indented under the if. In diesem Beispiel wird, weil temperature, 32, größer als 30 ist, die Nachricht "Es ist ein heißer Tag!" gedruckt. "Hab einen schönen Tag!" wird immer gedruckt, weil es nicht unter dem if eingerückt ist.

Think about it Denke darüber nach

What would happen in the example above if temperature was set to 25? Which lines would be printed? Was würde in dem Beispiel oben passieren, wenn temperature auf 25 gesetzt wäre? Welche Zeilen würden gedruckt?

Handling the Otherwise: The else Statement Das "Andernfalls" behandeln: Die else-Anweisung

What if you want to do something specific when the if condition is not met? That's what else is for. It provides an alternative block of code. Was ist, wenn du etwas Bestimmtes tun willst, wenn die if-Bedingung nicht erfüllt ist? Dafür ist else da. Es bietet einen alternativen Codeblock.

The structure is: if condition, colon, code runs if condition is True, print("Condition is True."), else, colon, code runs if condition is False, print("Condition is False."). Die Struktur ist: if Bedingung, Doppelpunkt, Code wird ausgeführt, wenn Bedingung Wahr ist, print("Bedingung ist Wahr."), else, Doppelpunkt, Code wird ausgeführt, wenn Bedingung Falsch ist, print("Bedingung ist Falsch.").

Example: user_age equals 17. if user_age greater than or equal to 18, colon, print("Access granted."), else, colon, print("Access denied. You must be 18 or older."). Beispiel: user_age gleich 17. if user_age größer oder gleich 18, Doppelpunkt, print("Zugang gewährt."), else, Doppelpunkt, print("Zugang verweigert. Du musst 18 oder älter sein.").

Here, since user_age, 17, is not greater than or equal to 18, the condition is False, and the code under else is executed. Hier ist, da user_age, 17, nicht größer oder gleich 18 ist, die Bedingung Falsch, und der Code unter else wird ausgeführt.

Checking Multiple Conditions: The elif Statement Mehrere Bedingungen prüfen: Die elif-Anweisung

Sometimes you have more than two possibilities. You can use elif, short for "else if", to check additional conditions only if the preceding if and elif conditions were False. Manchmal hast du mehr als zwei Möglichkeiten. Du kannst elif verwenden, kurz für "else if", um zusätzliche Bedingungen zu prüfen, nur wenn die vorangehenden if- und elif-Bedingungen Falsch waren.

Example: score equals 75. if score greater than or equal to 90, colon, print("Grade: A"). elif score greater than or equal to 80, colon, print("Grade: B"). elif score greater than or equal to 70, colon, print("Grade: C"). else, colon, print("Grade: D"). Beispiel: score gleich 75. if score größer oder gleich 90, Doppelpunkt, print("Note: A"). elif score größer oder gleich 80, Doppelpunkt, print("Note: B"). elif score größer oder gleich 70, Doppelpunkt, print("Note: C"). else, Doppelpunkt, print("Note: D").

Python checks the conditions in order: Is score greater than or equal to 90? No, 75 is not greater than or equal to 90. Python prüft die Bedingungen der Reihe nach: Ist score größer oder gleich 90? Nein, 75 ist nicht größer oder gleich 90.

Is score greater than or equal to 80? No, 75 is not greater than or equal to 80. Ist score größer oder gleich 80? Nein, 75 ist nicht größer oder gleich 80.

Is score greater than or equal to 70? Yes, 75 is greater than or equal to 70. Print "Grade: C" and stop checking. Ist score größer oder gleich 70? Ja, 75 ist größer oder gleich 70. Drucke "Note: C" und höre auf zu prüfen.

The else block is skipped because a previous elif was True. Der else-Block wird übersprungen, weil ein vorheriges elif Wahr war.

You can have multiple elif statements, but only one else at the very end, which acts as a catch-all if none of the if or elif conditions are met. Du kannst mehrere elif-Anweisungen haben, aber nur ein else ganz am Ende, das als Auffangnetz dient, wenn keine der if- oder elif-Bedingungen erfüllt ist.

Try it yourself Probiere es selbst aus

Modify the grading example above. What happens if the score is 95? What if it's 60? Predict the output, then run the code to check. Modifiziere das Noten-Beispiel oben. Was passiert, wenn der score 95 ist? Was ist, wenn er 60 ist? Sage die Ausgabe vorher, dann führe den Code aus, um es zu überprüfen.

Combining Conditions: Logical Operators Bedingungen kombinieren: Logische Operatoren

Often, you need to check if multiple conditions are true, or if at least one of several conditions is true. Logical operators help combine Boolean values. Oft musst du prüfen, ob mehrere Bedingungen wahr sind, oder ob mindestens eine von mehreren Bedingungen wahr ist. Logische Operatoren helfen, Boolean-Werte zu kombinieren.

The and operator returns True only if both conditions on its left and right are True. Der and-Operator gibt Wahr nur zurück, wenn beide Bedingungen links und rechts davon Wahr sind.

Example: age equals 25, has_ticket equals True. if age greater than or equal to 18 and has_ticket double equals True, colon, print("Allowed entry."). This will print. Beispiel: age gleich 25, has_ticket gleich Wahr. if age größer oder gleich 18 and has_ticket doppelgleich Wahr, Doppelpunkt, print("Einlass erlaubt."). Dies wird gedruckt.

The or operator returns True if at least one of the conditions on its left or right is True. Der or-Operator gibt Wahr zurück, wenn mindestens eine der Bedingungen links oder rechts davon Wahr ist.

Example: is_weekend equals False, has_holiday equals True. if is_weekend or has_holiday, colon, print("Enjoy your day off!"). This will print. Beispiel: is_weekend gleich Falsch, has_holiday gleich Wahr. if is_weekend or has_holiday, Doppelpunkt, print("Genieße deinen freien Tag!"). Dies wird gedruckt.

The not operator reverses the Boolean value. not True becomes False, and not False becomes True. Der not-Operator kehrt den Boolean-Wert um. not Wahr wird Falsch, und not Falsch wird Wahr.

Example: is_raining equals False. if not is_raining, colon, print("No need for an umbrella."). This will print. Beispiel: is_raining gleich Falsch. if not is_raining, Doppelpunkt, print("Kein Bedarf für einen Regenschirm."). Dies wird gedruckt.

Think about it Denke darüber nach

Consider this code: credits equals 15, gpa equals 3.0. if credits greater than or equal to 12 and gpa greater than or equal to 2.0, colon, print("Good standing."), else, colon, print("Needs review."). Betrachte diesen Code: credits gleich 15, gpa gleich 3,0. if credits größer oder gleich 12 and gpa größer oder gleich 2,0, Doppelpunkt, print("Guter Stand."), else, Doppelpunkt, print("Braucht Überprüfung.").

Then: if credits less than 12 or gpa less than 2.0, colon, print("Needs review."), else, colon, print("Good standing."). Dann: if credits kleiner als 12 or gpa kleiner als 2,0, Doppelpunkt, print("Braucht Überprüfung."), else, Doppelpunkt, print("Guter Stand.").

Do these two if/else blocks achieve the same outcome? Why or why not? Hint: Think about the relationship between and and or when conditions are negated. Erreichen diese beiden if/else-Blöcke das gleiche Ergebnis? Warum oder warum nicht? Hinweis: Denke über die Beziehung zwischen and und or nach, wenn Bedingungen negiert werden.

That's the basics of conditions in Python! By understanding if, elif, else, comparison operators, and logical operators, you can start writing programs that make intelligent decisions. Das sind die Grundlagen von Bedingungen in Python! Durch das Verständnis von if, elif, else, Vergleichsoperatoren und logischen Operatoren kannst du beginnen, Programme zu schreiben, die intelligente Entscheidungen treffen.