Welcome to the world of file handling in Python! So far, most of the data you've worked with, like variables, disappears when your script finishes running. Files allow you to store data persistently, meaning it stays saved even after your program closes, and you can read data created by other programs or stored previously. This is essential for many real-world applications, from saving user preferences to processing large datasets or logs. Willkommen in der Welt der Dateiverarbeitung in Python! Bisher verschwinden die meisten Daten, mit denen du gearbeitet hast, wie Variablen, wenn dein Skript die Ausführung beendet. Dateien ermöglichen es dir, Daten persistent zu speichern, was bedeutet, dass sie gespeichert bleiben, auch nachdem dein Programm geschlossen wurde, und du kannst Daten lesen, die von anderen Programmen erstellt oder zuvor gespeichert wurden. Das ist wesentlich für viele reale Anwendungen, vom Speichern von Benutzereinstellungen bis zur Verarbeitung großer Datensätze oder Logs.

What are Files? Was sind Dateien?

At its core, a file is just a named location on your computer's storage, like a hard drive or SSD, where data is stored. You interact with files constantly: text documents, images, music, program code, they are all files. Python provides built-in ways to interact with these files programmatically. Im Kern ist eine Datei einfach ein benannter Ort auf dem Speicher deines Computers, wie einer Festplatte oder SSD, wo Daten gespeichert werden. Du interagierst ständig mit Dateien: Textdokumente, Bilder, Musik, Programmcode, sie sind alle Dateien. Python bietet eingebaute Möglichkeiten, programmatisch mit diesen Dateien zu interagieren.

Opening Files Dateien öffnen

Before you can read from or write to a file in Python, you need to open it. This establishes a connection between your script and the file on the disk. The primary tool for this is the built-in open() function. Bevor du aus einer Datei in Python lesen oder in sie schreiben kannst, musst du sie öffnen. Das stellt eine Verbindung zwischen deinem Skript und der Datei auf der Festplatte her. Das Hauptwerkzeug dafür ist die eingebaute open()-Funktion.

The open() function typically takes two arguments: Die open()-Funktion nimmt typischerweise zwei Argumente:

File Path: A string specifying the location and name of the file, for example "my_document.txt" or "/Users/yourname/Documents/report.txt". Dateipfad: Ein String, der den Ort und Namen der Datei angibt, zum Beispiel "my_document.txt" oder "/Users/yourname/Documents/report.txt".

Mode: A string indicating how you want to interact with the file, read, write, append, et cetera. Modus: Ein String, der angibt, wie du mit der Datei interagieren möchtest, lesen, schreiben, anhängen und so weiter.

Example: Opening a file named "hello.txt" in read mode: file_object equals open("hello.txt", "r"). Do something with the file. file_object.close(). Don't forget to close it! Beispiel: Eine Datei namens "hello.txt" im Lesemodus öffnen: file_object gleich open("hello.txt", "r"). Mache etwas mit der Datei. file_object.close(). Vergiss nicht, sie zu schließen!

File Modes Dateimodi

The mode tells Python what you intend to do with the file. Here are the most common modes: Der Modus teilt Python mit, was du mit der Datei vorhast. Hier sind die häufigsten Modi:

'r', Read Mode: Default. Opens the file for reading. If the file doesn't exist, it raises a FileNotFoundError. The file pointer is placed at the beginning of the file. 'r', Lesemodus: Standard. Öffnet die Datei zum Lesen. Wenn die Datei nicht existiert, löst es einen FileNotFoundError aus. Der Dateizeiger wird am Anfang der Datei platziert.

'w', Write Mode: Opens the file for writing. Crucially, if the file already exists, its contents are deleted! If the file doesn't exist, it creates a new one. 'w', Schreibmodus: Öffnet die Datei zum Schreiben. Entscheidend: Wenn die Datei bereits existiert, wird ihr Inhalt gelöscht! Wenn die Datei nicht existiert, erstellt es eine neue.

'a', Append Mode: Opens the file for appending. Any data written to the file is automatically added to the end. If the file doesn't exist, it creates a new one. 'a', Anhängemodus: Öffnet die Datei zum Anhängen. Alle Daten, die in die Datei geschrieben werden, werden automatisch am Ende hinzugefügt. Wenn die Datei nicht existiert, erstellt es eine neue.

'b', Binary Mode: This is added to other modes, for example 'rb', 'wb'. It tells Python to handle the file as raw bytes rather than text, useful for images, executables, et cetera. We'll mostly focus on text files for now. 'b', Binärmodus: Dies wird zu anderen Modi hinzugefügt, zum Beispiel 'rb', 'wb'. Es teilt Python mit, die Datei als rohe Bytes anstatt als Text zu behandeln, nützlich für Bilder, ausführbare Dateien und so weiter. Wir werden uns vorerst hauptsächlich auf Textdateien konzentrieren.

'+', Update Mode: This can be added to other modes, for example 'r+', 'w+', 'a+', to allow both reading and writing. '+', Aktualisierungsmodus: Dies kann zu anderen Modi hinzugefügt werden, zum Beispiel 'r+', 'w+', 'a+', um sowohl Lesen als auch Schreiben zu ermöglichen.

Think about it Denke darüber nach

What do you think might happen if you try to open a file in 'r' mode, but the file doesn't actually exist on your computer? What about if you open an existing file in 'w' mode? Was denkst du, könnte passieren, wenn du versuchst, eine Datei im 'r'-Modus zu öffnen, aber die Datei tatsächlich nicht auf deinem Computer existiert? Was ist, wenn du eine existierende Datei im 'w'-Modus öffnest?

Reading from Files Aus Dateien lesen

Once a file is opened in read mode, 'r' or 'r+', you can read its contents using several methods: Sobald eine Datei im Lesemodus, 'r' oder 'r+', geöffnet ist, kannst du ihren Inhalt mit mehreren Methoden lesen:

read(): Reads the entire content of the file and returns it as a single string. Be careful with very large files, as this loads everything into memory. read(): Liest den gesamten Inhalt der Datei und gibt ihn als einzelnen String zurück. Sei vorsichtig bei sehr großen Dateien, da dies alles in den Speicher lädt.

readline(): Reads a single line from the file, including the newline character backslash n at the end. Each time you call it, it reads the next line. readline(): Liest eine einzelne Zeile aus der Datei, einschließlich des Zeilenumbruchzeichens Backslash n am Ende. Jedes Mal, wenn du es aufrufst, liest es die nächste Zeile.

readlines(): Reads all lines from the file and returns them as a list of strings, where each string is a line including its newline character. readlines(): Liest alle Zeilen aus der Datei und gibt sie als Liste von Strings zurück, wobei jeder String eine Zeile einschließlich ihres Zeilenumbruchzeichens ist.

Assume "example.txt" contains: Line 1, Line 2, Line 3. Angenommen "example.txt" enthält: Zeile 1, Zeile 2, Zeile 3.

Using read(): file equals open("example.txt", "r"). content equals file.read(). print("Using read()"). print(content). file.close(). Verwendung von read(): file gleich open("example.txt", "r"). content gleich file.read(). print("Verwendung von read()"). print(content). file.close().

Using readline(): file equals open("example.txt", "r"). print("Using readline()"). line1 equals file.readline(). print(f"Line 1: {line1.strip()}"). dot strip() removes leading/trailing whitespace like backslash n. line2 equals file.readline(). print(f"Line 2: {line2.strip()}"). file.close(). Verwendung von readline(): file gleich open("example.txt", "r"). print("Verwendung von readline()"). line1 gleich file.readline(). print(f"Zeile 1: {line1.strip()}"). Punkt strip() entfernt führende/nachfolgende Leerzeichen wie Backslash n. line2 gleich file.readline(). print(f"Zeile 2: {line2.strip()}"). file.close().

Using readlines(): file equals open("example.txt", "r"). lines equals file.readlines(). print("Using readlines()"). print(lines). Output: ['Line 1 backslash n', 'Line 2 backslash n', 'Line 3']. for i, line in enumerate(lines), colon, print(f"Line {i+1}: {line.strip()}"). file.close(). Verwendung von readlines(): file gleich open("example.txt", "r"). lines gleich file.readlines(). print("Verwendung von readlines()"). print(lines). Ausgabe: ['Zeile 1 Backslash n', 'Zeile 2 Backslash n', 'Zeile 3']. for i, line in enumerate(lines), Doppelpunkt, print(f"Zeile {i+1}: {line.strip()}"). file.close().

Writing to Files In Dateien schreiben

To write data, open the file in write, 'w', or append, 'a', mode. Um Daten zu schreiben, öffne die Datei im Schreibmodus, 'w', oder Anhängemodus, 'a'.

write(string): Writes the given string to the file. It does not automatically add a newline character. You need to include backslash n if you want lines separated. write(string): Schreibt den gegebenen String in die Datei. Es fügt nicht automatisch ein Zeilenumbruchzeichen hinzu. Du musst Backslash n einschließen, wenn du Zeilen getrennt haben möchtest.

writelines(list_of_strings): Writes each string from the list to the file. Like write(), it does not add newlines automatically. writelines(list_of_strings): Schreibt jeden String aus der Liste in die Datei. Wie write() fügt es nicht automatisch Zeilenumbrüche hinzu.

Writing using write(): file equals open("output.txt", "w"). Opens or creates output.txt and clears it. file.write("Hello there! backslash n"). Add backslash n for a new line. file.write("This is the second line."). file.close(). Content is saved when closed. Schreiben mit write(): file gleich open("output.txt", "w"). Öffnet oder erstellt output.txt und löscht sie. file.write("Hallo dort! Backslash n"). Füge Backslash n für eine neue Zeile hinzu. file.write("Das ist die zweite Zeile."). file.close(). Inhalt wird beim Schließen gespeichert.

Appending using writelines(): lines_to_add equals ["backslash n Third line.", "backslash n Fourth line."]. Need backslash n here too. file equals open("output.txt", "a"). Open in append mode. file.writelines(lines_to_add). file.close(). Anhängen mit writelines(): lines_to_add gleich ["Backslash n Dritte Zeile.", "Backslash n Vierte Zeile."]. Brauche Backslash n auch hier. file gleich open("output.txt", "a"). Im Anhängemodus öffnen. file.writelines(lines_to_add). file.close().

Try it yourself Probiere es selbst aus

Create a new Python file, for example file_practice.py. Erstelle eine neue Python-Datei, zum Beispiel file_practice.py.

Write code to create a new text file named my_notes.txt. Schreibe Code, um eine neue Textdatei namens my_notes.txt zu erstellen.

Write three lines of text into my_notes.txt. Make sure each line appears on a new line in the actual file. Schreibe drei Textzeilen in my_notes.txt. Stelle sicher, dass jede Zeile in einer neuen Zeile in der tatsächlichen Datei erscheint.

Close the file. Schließe die Datei.

Now, write code to open my_notes.txt again, read its entire content, and print it to the console. Schreibe jetzt Code, um my_notes.txt erneut zu öffnen, ihren gesamten Inhalt zu lesen und ihn auf der Konsole auszugeben.

Close the file. Schließe die Datei.

Run your Python script and then check if my_notes.txt was created and contains the text you wrote. Führe dein Python-Skript aus und überprüfe dann, ob my_notes.txt erstellt wurde und den Text enthält, den du geschrieben hast.

Closing Files: The Importance of close() Dateien schließen: Die Wichtigkeit von close()

When you're finished with a file, it's crucial to close it using the file_object.close() method. Why? Wenn du mit einer Datei fertig bist, ist es entscheidend, sie mit der file_object.close()-Methode zu schließen. Warum?

Flushing the Buffer: When you write to a file, the changes might not be saved to the disk immediately. Python often buffers the output, holds it in memory temporarily, for efficiency. Closing the file ensures that all buffered data is written, or flushed, to the disk. If your program crashes before closing, you might lose data. Buffer leeren: Wenn du in eine Datei schreibst, werden die Änderungen möglicherweise nicht sofort auf der Festplatte gespeichert. Python puffert die Ausgabe oft, hält sie vorübergehend im Speicher, für Effizienz. Das Schließen der Datei stellt sicher, dass alle gepufferten Daten auf die Festplatte geschrieben oder geleert werden. Wenn dein Programm vor dem Schließen abstürzt, könntest du Daten verlieren.

Releasing Resources: Operating systems limit the number of files a program can have open simultaneously. Closing files releases these resources. Leaving many files open unnecessarily can cause problems. Ressourcen freigeben: Betriebssysteme begrenzen die Anzahl der Dateien, die ein Programm gleichzeitig geöffnet haben kann. Das Schließen von Dateien gibt diese Ressourcen frei. Viele Dateien unnötig offen zu lassen, kann Probleme verursachen.

The with Statement: The Preferred Way Die with-Anweisung: Der bevorzugte Weg

Forgetting to close a file is a common mistake. Python provides a cleaner, safer way to handle files using the with statement. It automatically takes care of closing the file, even if errors occur within the block. Das Vergessen, eine Datei zu schließen, ist ein häufiger Fehler. Python bietet einen saubereren, sichereren Weg, Dateien mit der with-Anweisung zu handhaben. Sie kümmert sich automatisch um das Schließen der Datei, selbst wenn Fehler innerhalb des Blocks auftreten.

Using 'with' for reading: try, colon, with open("example.txt", "r") as file, colon, content equals file.read(). print("Reading with 'with'"). print(content). File is automatically closed here, even if errors happened inside the 'with' block. except FileNotFoundError, colon, print("Error: example.txt not found!"). Verwendung von 'with' zum Lesen: try, Doppelpunkt, with open("example.txt", "r") as file, Doppelpunkt, content gleich file.read(). print("Lesen mit 'with'"). print(content). Datei wird hier automatisch geschlossen, selbst wenn Fehler innerhalb des 'with'-Blocks aufgetreten sind. except FileNotFoundError, Doppelpunkt, print("Fehler: example.txt nicht gefunden!").

Using 'with' for writing: lines_to_write equals ["First line backslash n", "Second line backslash n"]. try, colon, with open("new_output.txt", "w") as file, colon, file.writelines(lines_to_write). Maybe some error happens here? File will still be closed. File is automatically closed here. print("Successfully wrote to new_output.txt"). except IOError, colon. A more general error for input/output problems. print("Error: Could not write to file."). Verwendung von 'with' zum Schreiben: lines_to_write gleich ["Erste Zeile Backslash n", "Zweite Zeile Backslash n"]. try, Doppelpunkt, with open("new_output.txt", "w") as file, Doppelpunkt, file.writelines(lines_to_write). Vielleicht passiert hier ein Fehler? Datei wird trotzdem geschlossen. Datei wird hier automatisch geschlossen. print("Erfolgreich in new_output.txt geschrieben"). except IOError, Doppelpunkt. Ein allgemeinerer Fehler für Eingabe/Ausgabe-Probleme. print("Fehler: Konnte nicht in Datei schreiben.").

Using with is strongly recommended for file operations in Python. It makes your code more readable and robust. Die Verwendung von with wird stark für Dateioperationen in Python empfohlen. Es macht deinen Code lesbarer und robuster.

Think about it Denke darüber nach

Why is using the with statement generally safer than manually calling open() and close()? What kind of problems does it help prevent? Warum ist die Verwendung der with-Anweisung generell sicherer als das manuelle Aufrufen von open() und close()? Welche Art von Problemen hilft sie zu verhindern?

File Paths Dateipfade

When you specify a filename like "my_notes.txt", Python looks for or creates the file in the current working directory. This is usually the directory where you ran your Python script from. Wenn du einen Dateinamen wie "my_notes.txt" angibst, sucht Python nach der Datei oder erstellt sie im aktuellen Arbeitsverzeichnis. Das ist normalerweise das Verzeichnis, von dem aus du dein Python-Skript ausgeführt hast.

You can also use: Du kannst auch verwenden:

Relative Paths: Paths relative to the current directory, for example "data/input.csv", "../scripts/config.txt". Relative Pfade: Pfade relativ zum aktuellen Verzeichnis, zum Beispiel "data/input.csv", "../scripts/config.txt".

Absolute Paths: Full paths starting from the root directory, for example "/Users/yourname/Documents/project/data.txt" on macOS/Linux or "C colon backslash backslash Users backslash backslash yourname backslash backslash Documents backslash backslash project backslash backslash data.txt" on Windows. Note the double backslashes needed in Windows strings, or use raw strings like r"C colon backslash Users backslash yourname dot dot dot". Absolute Pfade: Vollständige Pfade, die vom Wurzelverzeichnis beginnen, zum Beispiel "/Users/yourname/Documents/project/data.txt" auf macOS/Linux oder "C Doppelpunkt Backslash Backslash Users Backslash Backslash yourname Backslash Backslash Documents Backslash Backslash project Backslash Backslash data.txt" auf Windows. Beachte die doppelten Backslashes, die in Windows-Strings benötigt werden, oder verwende Raw-Strings wie r"C Doppelpunkt Backslash Users Backslash yourname Punkt Punkt Punkt".

Using relative paths often makes your code more portable, as it doesn't depend on specific user directory structures. The os module, which you might have seen in the Modules lesson preview or will see soon, has helpful functions for working with paths, like os.path.join() to create paths correctly across different operating systems. Die Verwendung relativer Pfade macht deinen Code oft portabler, da er nicht von spezifischen Benutzerverzeichnisstrukturen abhängt. Das os-Modul, das du möglicherweise in der Vorschau der Module-Lektion gesehen hast oder bald sehen wirst, hat hilfreiche Funktionen für die Arbeit mit Pfaden, wie os.path.join(), um Pfade korrekt über verschiedene Betriebssysteme hinweg zu erstellen.

That covers the basics of file handling! You're now ready to read data from files and save your program's results persistently. Das deckt die Grundlagen der Dateiverarbeitung ab! Du bist jetzt bereit, Daten aus Dateien zu lesen und die Ergebnisse deines Programms persistent zu speichern.

The slides for the live session can be viewed here. Try not to peek before class, spoilers inside! Die Folien für die Live-Sitzung können hier angesehen werden. Versuche nicht vor dem Unterricht zu spicken, Spoiler darin!