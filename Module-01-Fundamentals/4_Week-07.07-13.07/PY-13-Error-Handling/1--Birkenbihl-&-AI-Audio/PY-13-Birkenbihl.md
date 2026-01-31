Welcome to the world of Python Error Handling! Sometimes, even the best-written code encounters unexpected situations or outright mistakes. What happens then? Does the program just crash? Often, yes! But Python provides powerful tools to gracefully manage these errors, prevent crashes, and make your programs more robust and user-friendly. This preparation will introduce you to the fundamental concepts of errors and how to start handling them. Willkommen in der Welt der Python-Fehlerbehandlung! Manchmal begegnet selbst der am besten geschriebene Code unerwarteten Situationen oder regelrechten Fehlern. Was passiert dann? Stürzt das Programm einfach ab? Oft ja! Aber Python bietet mächtige Werkzeuge, um diese Fehler elegant zu handhaben, Abstürze zu verhindern und deine Programme robuster und benutzerfreundlicher zu machen. Diese Vorbereitung wird dich in die fundamentalen Konzepte von Fehlern einführen und wie man beginnt, sie zu handhaben.

What Are Errors in Programming? Was sind Fehler in der Programmierung?

Think about following a recipe. If the recipe tells you to add 1 cup of sugar but you don't have any sugar, you've encountered an issue. You can't proceed as instructed. Similarly, if a step says mix vigorously but doesn't specify what to mix, that's a different kind of problem, an ambiguity or mistake in the instructions themselves. Denke an das Befolgen eines Rezepts. Wenn das Rezept dir sagt, du sollst 1 Tasse Zucker hinzufügen, aber du hast keinen Zucker, bist du auf ein Problem gestoßen. Du kannst nicht wie angewiesen fortfahren. Ähnlich, wenn ein Schritt sagt, kräftig mischen, aber nicht angibt, was gemischt werden soll, ist das eine andere Art von Problem, eine Mehrdeutigkeit oder ein Fehler in den Anweisungen selbst.

In programming, errors are similar. They represent situations where the Python interpreter cannot execute the instructions as written, either because the instructions themselves are malformed or because some condition arises during execution that prevents the instruction from completing successfully. In der Programmierung sind Fehler ähnlich. Sie repräsentieren Situationen, in denen der Python-Interpreter die Anweisungen nicht wie geschrieben ausführen kann, entweder weil die Anweisungen selbst fehlerhaft sind oder weil eine Bedingung während der Ausführung auftritt, die verhindert, dass die Anweisung erfolgreich abgeschlossen wird.

There are generally two main categories of errors in Python: Es gibt generell zwei Hauptkategorien von Fehlern in Python:

Syntax Errors: These are mistakes in the structure or grammar of the Python code itself. The interpreter spots these before the program even starts running. It's like trying to read a sentence where words are misspelled or punctuation is missing, you can't understand it. Syntaxfehler: Das sind Fehler in der Struktur oder Grammatik des Python-Codes selbst. Der Interpreter entdeckt diese, bevor das Programm überhaupt zu laufen beginnt. Es ist wie der Versuch, einen Satz zu lesen, in dem Wörter falsch geschrieben sind oder Interpunktion fehlt, du kannst ihn nicht verstehen.

Example: Forgetting a colon at the end of an if statement, misspelling a keyword like whle instead of while, or having unmatched parentheses. Python will refuse to run the code and point out the location of the syntax error. Beispiel: Einen Doppelpunkt am Ende einer if-Anweisung vergessen, ein Schlüsselwort falsch schreiben wie whle anstatt while, oder nicht zusammenpassende Klammern haben. Python wird sich weigern, den Code auszuführen und die Position des Syntaxfehlers anzeigen.

Exceptions, Runtime Errors: These errors occur during the execution of the program, even if the syntax is perfectly correct. They happen when the code encounters an unexpected situation it doesn't know how to handle. It's like the recipe example: the instruction add 1 cup of sugar is grammatically correct, but the error occurs when you try to execute it because you lack the ingredient. Exceptions, Laufzeitfehler: Diese Fehler treten während der Ausführung des Programms auf, selbst wenn die Syntax perfekt korrekt ist. Sie passieren, wenn der Code auf eine unerwartete Situation stößt, mit der er nicht umgehen kann. Es ist wie das Rezept-Beispiel: die Anweisung 1 Tasse Zucker hinzufügen ist grammatikalisch korrekt, aber der Fehler tritt auf, wenn du versuchst, sie auszuführen, weil dir die Zutat fehlt.

Example: Trying to divide a number by zero, ZeroDivisionError, trying to access an item in a list using an index that doesn't exist, IndexError, trying to open a file that isn't there, FileNotFoundError, or trying to add a number to a string, TypeError. Beispiel: Versuchen, eine Zahl durch Null zu teilen, ZeroDivisionError, versuchen, auf ein Element in einer Liste mit einem Index zuzugreifen, der nicht existiert, IndexError, versuchen, eine Datei zu öffnen, die nicht da ist, FileNotFoundError, oder versuchen, eine Zahl zu einem String hinzuzufügen, TypeError.

This lesson focuses on Exceptions, how to anticipate and manage these runtime errors. Diese Lektion konzentriert sich auf Exceptions, wie man diese Laufzeitfehler antizipiert und handhabt.

Try it yourself Probiere es selbst aus

Open your Python interpreter or create a small dot py file and try running these lines, one at a time. Observe the output: Öffne deinen Python-Interpreter oder erstelle eine kleine Punkt-py-Datei und versuche, diese Zeilen nacheinander auszuführen. Beobachte die Ausgabe:

Cause a TypeError: result equals "hello" plus 5. print(result). Einen TypeError verursachen: result gleich "hello" plus 5. print(result).

Cause an IndexError: my_list equals [1, 2, 3]. print(my_list[5]). Einen IndexError verursachen: my_list gleich [1, 2, 3]. print(my_list[5]).

Cause a ZeroDivisionError: result equals 10 divided by 0. print(result). Einen ZeroDivisionError verursachen: result gleich 10 geteilt durch 0. print(result).

You'll see Python stops execution and prints a traceback, showing where the error occurred and what type of exception it was. Du wirst sehen, dass Python die Ausführung stoppt und einen Traceback ausgibt, der zeigt, wo der Fehler aufgetreten ist und welchen Typ von Exception es war.

Why Handle Exceptions? Warum Exceptions handhaben?

When an exception occurs and is not handled, the default behavior is for the program to stop immediately, crash, and print the traceback message. This might be acceptable for a quick script you wrote for yourself, but it's terrible for users of your software! Wenn eine Exception auftritt und nicht behandelt wird, ist das Standardverhalten, dass das Programm sofort stoppt, abstürzt und die Traceback-Nachricht ausgibt. Das mag akzeptabel sein für ein schnelles Skript, das du für dich selbst geschrieben hast, aber es ist schrecklich für Benutzer deiner Software!

Imagine using a web application, filling out a long form, and clicking Submit, only to have the entire application crash because you accidentally typed text into a field expecting a number. That's a frustrating user experience. Stell dir vor, du verwendest eine Webanwendung, füllst ein langes Formular aus und klickst auf Absenden, nur um zu erleben, dass die gesamte Anwendung abstürzt, weil du versehentlich Text in ein Feld eingegeben hast, das eine Zahl erwartet. Das ist eine frustrierende Benutzererfahrung.

Proper exception handling allows you to: Ordnungsgemäße Exception-Behandlung ermöglicht es dir:

Prevent Crashes: Catch errors gracefully instead of letting the program terminate abruptly. Abstürze verhindern: Fehler elegant abfangen, anstatt das Programm abrupt beenden zu lassen.

Provide User Feedback: Inform the user about what went wrong in a helpful way, for example Invalid input: Please enter a number, instead of showing a scary traceback. Benutzerfeedback geben: Den Benutzer auf hilfreiche Weise darüber informieren, was schiefgelaufen ist, zum Beispiel Ungültige Eingabe: Bitte gib eine Zahl ein, anstatt einen beängstigenden Traceback zu zeigen.

Perform Cleanup Actions: Ensure critical resources, like files or network connections, are closed properly, even if an error occurs. Aufräumaktionen durchführen: Sicherstellen, dass kritische Ressourcen, wie Dateien oder Netzwerkverbindungen, ordnungsgemäß geschlossen werden, selbst wenn ein Fehler auftritt.

Allow Recovery: In some cases, you can correct the error condition or try an alternative approach. Wiederherstellung ermöglichen: In einigen Fällen kannst du die Fehlerbedingung korrigieren oder einen alternativen Ansatz versuchen.

Log Errors: Record details about errors to help with debugging and monitoring application health. Fehler protokollieren: Details über Fehler aufzeichnen, um beim Debuggen und Überwachen der Anwendungsgesundheit zu helfen.

Introducing try, except, and finally Einführung in try, except und finally

The core mechanism for handling exceptions in Python involves the try, except, and optionally finally clauses. The basic structure looks like this: Der Kernmechanismus zur Behandlung von Exceptions in Python beinhaltet die try-, except- und optional finally-Klauseln. Die grundlegende Struktur sieht so aus:

try, colon. Code that might potentially raise an exception. Suspicious code goes here. print("Attempting the risky operation..."). try, Doppelpunkt. Code, der potenziell eine Exception auslösen könnte. Verdächtiger Code kommt hierhin. print("Versuche die riskante Operation...").

Example 1: No error. risky_result equals 10 divided by 2. Example 2: Error. risky_result equals 10 divided by 0. This will cause a ZeroDivisionError. print("This line will not be reached if an error occurs above."). Beispiel 1: Kein Fehler. risky_result gleich 10 geteilt durch 2. Beispiel 2: Fehler. risky_result gleich 10 geteilt durch 0. Das wird einen ZeroDivisionError verursachen. print("Diese Zeile wird nicht erreicht, wenn oben ein Fehler auftritt.").

except ZeroDivisionError, colon. Code that runs ONLY if a ZeroDivisionError occurs in the try block. print("Caught the division by zero error!"). except ZeroDivisionError, Doppelpunkt. Code, der NUR läuft, wenn ein ZeroDivisionError im try-Block auftritt. print("Division-durch-Null-Fehler abgefangen!").

except Exception as e, colon. Code that runs if ANY OTHER exception that is a subclass of Exception occurs. print(f"Caught some other error: {e}"). except Exception as e, Doppelpunkt. Code, der läuft, wenn JEDE ANDERE Exception auftritt, die eine Unterklasse von Exception ist. print(f"Einen anderen Fehler abgefangen: {e}").

finally, colon. Code that ALWAYS runs, regardless of whether an exception occurred or was caught. print("This 'finally' block always executes, for cleanup perhaps."). finally, Doppelpunkt. Code, der IMMER läuft, unabhängig davon, ob eine Exception aufgetreten ist oder abgefangen wurde. print("Dieser 'finally'-Block wird immer ausgeführt, vielleicht für Aufräumarbeiten.").

print("Execution continues after the try-except-finally block."). print("Die Ausführung setzt sich nach dem try-except-finally-Block fort.").

How it works: Wie es funktioniert:

Python starts executing the code inside the try block. Python beginnt, den Code innerhalb des try-Blocks auszuführen.

If no exception occurs: The entire try block completes successfully. Any except blocks are skipped. The finally block, if present, is executed. Execution continues with the code after the try except finally structure. Wenn keine Exception auftritt: Der gesamte try-Block wird erfolgreich abgeschlossen. Alle except-Blöcke werden übersprungen. Der finally-Block, falls vorhanden, wird ausgeführt. Die Ausführung setzt sich mit dem Code nach der try-except-finally-Struktur fort.

If an exception occurs inside the try block: Python immediately stops executing the rest of the code within the try block. It looks for an except block whose specified exception type matches the one that occurred. Wenn eine Exception innerhalb des try-Blocks auftritt: Python stoppt sofort die Ausführung des restlichen Codes innerhalb des try-Blocks. Es sucht nach einem except-Block, dessen angegebener Exception-Typ mit dem übereinstimmt, der aufgetreten ist.

If a matching except block is found: The code inside that except block is executed. The finally block, if present, is executed. Execution continues with the code after the try except finally structure. Wenn ein passender except-Block gefunden wird: Der Code innerhalb dieses except-Blocks wird ausgeführt. Der finally-Block, falls vorhanden, wird ausgeführt. Die Ausführung setzt sich mit dem Code nach der try-except-finally-Struktur fort.

If no matching except block is found: The finally block, if present, is still executed. After the finally block, the exception is unhandled, re-raised, and the program crashes unless caught by an outer try except. Wenn kein passender except-Block gefunden wird: Der finally-Block, falls vorhanden, wird trotzdem ausgeführt. Nach dem finally-Block ist die Exception unbehandelt, wird erneut ausgelöst, und das Programm stürzt ab, es sei denn, sie wird von einem äußeren try-except abgefangen.

The finally Clause: Die finally-Klausel:

The key purpose of the finally block is to guarantee that certain code runs, no matter what happens in the try or except blocks. This is crucial for cleanup operations, such as: Der Hauptzweck des finally-Blocks ist zu garantieren, dass bestimmter Code läuft, egal was in den try- oder except-Blöcken passiert. Das ist entscheidend für Aufräumoperationen, wie:

Closing files that were opened. Releasing network connections. Disconnecting from databases. Resetting configurations. Schließen von Dateien, die geöffnet wurden. Freigeben von Netzwerkverbindungen. Trennen von Datenbankverbindungen. Zurücksetzen von Konfigurationen.

Even if an error occurs and is caught, or if an error occurs and isn't caught, or even if the try block finishes successfully, the finally block provides a safe place to ensure these cleanup tasks happen. Selbst wenn ein Fehler auftritt und abgefangen wird, oder wenn ein Fehler auftritt und nicht abgefangen wird, oder selbst wenn der try-Block erfolgreich abgeschlossen wird, bietet der finally-Block einen sicheren Ort, um sicherzustellen, dass diese Aufräumaufgaben passieren.

Common Built-in Exceptions Häufige eingebaute Exceptions

Python has many built-in exceptions for common errors. You've already seen some. Here are a few you'll encounter frequently: Python hat viele eingebaute Exceptions für häufige Fehler. Du hast bereits einige gesehen. Hier sind ein paar, denen du häufig begegnen wirst:

Exception: The base class for almost all built-in exceptions. Catching Exception will catch most errors, but usually, it's better to be more specific. Exception: Die Basisklasse für fast alle eingebauten Exceptions. Exception abzufangen wird die meisten Fehler abfangen, aber normalerweise ist es besser, spezifischer zu sein.

SyntaxError: Error in the code's syntax. Cannot be caught by try except as it happens before execution. SyntaxError: Fehler in der Syntax des Codes. Kann nicht durch try-except abgefangen werden, da es vor der Ausführung passiert.

TypeError: An operation or function is applied to an object of an inappropriate type, for example len(123) or "hello" plus 5. TypeError: Eine Operation oder Funktion wird auf ein Objekt eines unpassenden Typs angewendet, zum Beispiel len(123) oder "hello" plus 5.

ValueError: An operation or function receives an argument that has the right type but an inappropriate value, for example int("abc"). ValueError: Eine Operation oder Funktion erhält ein Argument, das den richtigen Typ hat, aber einen unpassenden Wert, zum Beispiel int("abc").

NameError: A variable or function name is used before it has been assigned a value. NameError: Ein Variablen- oder Funktionsname wird verwendet, bevor ihm ein Wert zugewiesen wurde.

IndexError: A sequence subscript, like list index, is out of range. IndexError: Ein Sequenz-Index, wie ein Listenindex, liegt außerhalb des Bereichs.

KeyError: A dictionary key is not found. KeyError: Ein Dictionary-Schlüssel wird nicht gefunden.

FileNotFoundError: Trying to open a file that does not exist for reading. FileNotFoundError: Versuch, eine Datei zu öffnen, die zum Lesen nicht existiert.

ZeroDivisionError: Trying to divide by zero. ZeroDivisionError: Versuch, durch Null zu teilen.

ImportError: Python cannot find the module you're trying to import. ImportError: Python kann das Modul nicht finden, das du zu importieren versuchst.

AttributeError: Trying to access an attribute or method that doesn't exist on an object, for example mylist.appeend(1), misspelled append. AttributeError: Versuch, auf ein Attribut oder eine Methode zuzugreifen, die auf einem Objekt nicht existiert, zum Beispiel mylist.appeend(1), falsch geschriebenes append.

Try it yourself Probiere es selbst aus

Modify the earlier examples to use try except blocks to catch the specific exceptions and print a user-friendly message instead of crashing. Modifiziere die früheren Beispiele, um try-except-Blöcke zu verwenden, um die spezifischen Exceptions abzufangen und eine benutzerfreundliche Nachricht auszugeben, anstatt abzustürzen.

Example for TypeError: try, colon, result equals "hello" plus 5. print(result). except TypeError, colon, print("Oops! Looks like you tried to combine text and a number in a way Python doesn't like."). finally, colon, print("Cleanup step after TypeError attempt."). print("Program continues running!"). Beispiel für TypeError: try, Doppelpunkt, result gleich "hello" plus 5. print(result). except TypeError, Doppelpunkt, print("Hoppla! Sieht so aus, als hättest du versucht, Text und eine Zahl auf eine Weise zu kombinieren, die Python nicht mag."). finally, Doppelpunkt, print("Aufräumschritt nach TypeError-Versuch."). print("Programm läuft weiter!").

Try this for IndexError and ZeroDivisionError as well. Probiere das auch für IndexError und ZeroDivisionError aus.

Experiment with catching a different exception type than the one that actually occurs, for example except ValueError when a TypeError happens, to see that the error is not caught, but the finally block still runs before the program crashes. Experimentiere mit dem Abfangen eines anderen Exception-Typs als dem, der tatsächlich auftritt, zum Beispiel except ValueError, wenn ein TypeError passiert, um zu sehen, dass der Fehler nicht abgefangen wird, aber der finally-Block trotzdem läuft, bevor das Programm abstürzt.

Also try using a generic except Exception to see that it catches the error, and the finally block runs afterwards. Probiere auch, ein generisches except Exception zu verwenden, um zu sehen, dass es den Fehler abfängt und der finally-Block danach läuft.

Think about it Denke darüber nach

Why is it generally better to catch specific exceptions, like except ValueError, rather than using a generic except or except Exception? What potential problems could arise from catching all possible exceptions without distinguishing them? Warum ist es generell besser, spezifische Exceptions abzufangen, wie except ValueError, anstatt ein generisches except oder except Exception zu verwenden? Welche potenziellen Probleme könnten entstehen, wenn man alle möglichen Exceptions abfängt, ohne sie zu unterscheiden?

Can't We Get By Without Error Handling? Kommen wir nicht ohne Fehlerbehandlung aus?

Python offers two styles to manage potential errors: Python bietet zwei Stile, um potenzielle Fehler zu handhaben:

LBYL, Look Before You Leap: Check conditions before acting. Example: LBYL, Look Before You Leap, Schau, bevor du springst: Überprüfe Bedingungen, bevor du handelst. Beispiel:

if 'key' in my_dict, colon, value equals my_dict['key'], else, colon, value equals 'default'. if 'key' in my_dict, Doppelpunkt, value gleich my_dict['key'], else, Doppelpunkt, value gleich 'default'.

Good when checking is cheap and reliable. Gut, wenn die Überprüfung billig und zuverlässig ist.

EAFP, Easier to Ask Forgiveness than Permission: Try first, handle errors if they happen. Example: EAFP, Easier to Ask Forgiveness than Permission, Es ist einfacher, um Vergebung zu bitten als um Erlaubnis: Probiere zuerst, behandle Fehler, wenn sie passieren. Beispiel:

try, colon, value equals my_dict['key'], except KeyError, colon, value equals 'default'. try, Doppelpunkt, value gleich my_dict['key'], except KeyError, Doppelpunkt, value gleich 'default'.

This is more Pythonic: it's cleaner, and more efficient where failure is rare. Das ist pythonischer: es ist sauberer und effizienter, wenn Fehler selten sind.

Sometimes we must handle exceptions for situations we can't prevent, like import errors, network failures, or file access issues. Manchmal müssen wir Exceptions für Situationen behandeln, die wir nicht verhindern können, wie Import-Fehler, Netzwerkausfälle oder Dateizugriffsprobleme.

Example: try, colon, import non_existent_module, except ImportError, colon, print("Module not found, using alternative solution"). Use alternative implementation or fallback. Beispiel: try, Doppelpunkt, import non_existent_module, except ImportError, Doppelpunkt, print("Modul nicht gefunden, verwende alternative Lösung"). Verwende alternative Implementierung oder Fallback.

Bottom Line: We can't always avoid error handling. Even in simple cases, deciding between LBYL and EAFP shapes how you write robust, readable code. Fazit: Wir können Fehlerbehandlung nicht immer vermeiden. Selbst in einfachen Fällen prägt die Entscheidung zwischen LBYL und EAFP, wie du robusten, lesbaren Code schreibst.

This introduction should give you a good foundation for understanding what exceptions are and why and how we start to handle them using try, except, and finally. In the live lesson, we'll dive deeper into more advanced techniques and best practices. Diese Einführung sollte dir eine gute Grundlage geben, um zu verstehen, was Exceptions sind und warum und wie wir beginnen, sie mit try, except und finally zu behandeln. In der Live-Lektion werden wir tiefer in fortgeschrittenere Techniken und Best Practices eintauchen.

The slides for the live session can be viewed here. Try not to peek before class, spoilers inside! Die Folien für die Live-Sitzung können hier angesehen werden. Versuche nicht vor dem Unterricht zu spicken, Spoiler darin!