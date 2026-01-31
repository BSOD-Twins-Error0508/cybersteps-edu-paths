Welcome to your first step into the world of the command line! Before our live session, please work through this material. It will introduce you to the terminal, a fundamental tool in cybersecurity and many other tech fields. Don't worry if it seems unfamiliar; we'll build on these concepts together. Willkommen zu deinem ersten Schritt in die Welt der Kommandozeile! Vor unserer Live-Sitzung arbeite bitte dieses Material durch. Es wird dich in das Terminal einführen, ein fundamentales Werkzeug in Cybersicherheit und vielen anderen Tech-Bereichen. Mach dir keine Sorgen, wenn es ungewohnt erscheint; wir werden auf diesen Konzepten zusammen aufbauen.

What is the Terminal? Was ist das Terminal?

Think about how you usually interact with your computer. You probably click on icons, open windows, drag files, and use menus. This is called a Graphical User Interface, GUI. It's visual and intuitive for many tasks. The Terminal, also known as the Command-Line Interface, CLI, is a different way to interact with your computer. Instead of clicking icons, you type commands as text, and the computer responds with text output. It might look simple or even old-fashioned at first glance, but it's incredibly powerful. Denke darüber nach, wie du normalerweise mit deinem Computer interagierst. Du klickst wahrscheinlich auf Icons, öffnest Fenster, ziehst Dateien und verwendest Menüs. Das nennt man eine grafische Benutzeroberfläche, GUI. Sie ist visuell und intuitiv für viele Aufgaben. Das Terminal, auch bekannt als Kommandozeilen-Schnittstelle, CLI, ist eine andere Art, mit deinem Computer zu interagieren. Anstatt auf Icons zu klicken, tippst du Befehle als Text ein, und der Computer antwortet mit Textausgabe. Es mag auf den ersten Blick einfach oder sogar altmodisch aussehen, aber es ist unglaublich leistungsstark.

GUI: Uses graphics like icons, windows, menus, controlled by mouse clicks and gestures. Examples: macOS Finder, Windows Explorer, web browsers. GUI: Verwendet Grafiken wie Icons, Fenster, Menüs, gesteuert durch Mausklicks und Gesten. Beispiele: macOS Finder, Windows Explorer, Webbrowser.

CLI, Terminal: Uses text commands, controlled by keyboard input. Examples: macOS Terminal app, Windows Command Prompt, Linux shell. CLI, Terminal: Verwendet Textbefehle, gesteuert durch Tastatureingabe. Beispiele: macOS Terminal-App, Windows Eingabeaufforderung, Linux-Shell.

Why Use the Terminal? Warum das Terminal verwenden?

If GUIs are so user-friendly, why bother with the text-based terminal? Wenn GUIs so benutzerfreundlich sind, warum sich mit dem textbasierten Terminal beschäftigen?

Efficiency: For certain tasks, typing a short command can be much faster than clicking through multiple menus and windows. Effizienz: Für bestimmte Aufgaben kann das Eintippen eines kurzen Befehls viel schneller sein als durch mehrere Menüs und Fenster zu klicken.

Automation: You can string commands together into scripts to automate repetitive tasks. Imagine renaming 1000 files with one command! Automatisierung: Du kannst Befehle zu Skripten zusammenfügen, um sich wiederholende Aufgaben zu automatisieren. Stell dir vor, 1000 Dateien mit einem Befehl umzubenennen!

Power and Control: Some tools and settings are only accessible through the terminal, giving you more direct control over the system. This is crucial in cybersecurity for analysis and system interaction. Macht und Kontrolle: Einige Werkzeuge und Einstellungen sind nur über das Terminal zugänglich, was dir direktere Kontrolle über das System gibt. Das ist entscheidend in der Cybersicherheit für Analyse und Systeminteraktion.

Remote Access: When connecting to other computers, like servers, you often only have terminal access. Fernzugriff: Beim Verbinden mit anderen Computern, wie Servern, hast du oft nur Terminal-Zugriff.

Resource Light: CLIs use fewer system resources than GUIs. Ressourcenschonend: CLIs verwenden weniger Systemressourcen als GUIs.

In cybersecurity, you'll constantly use the terminal to run security tools, analyze logs, manage systems, and automate processes. It's an essential skill. In der Cybersicherheit wirst du ständig das Terminal verwenden, um Sicherheitswerkzeuge auszuführen, Logs zu analysieren, Systeme zu verwalten und Prozesse zu automatisieren. Es ist eine wesentliche Fähigkeit.

The Shell Die Shell

When you open the Terminal application, you're interacting with a program called the shell. The shell's job is to: Wenn du die Terminal-Anwendung öffnest, interagierst du mit einem Programm namens Shell. Die Aufgabe der Shell ist:

Read the command you type. Den Befehl zu lesen, den du eintippst.

Interpret what you want to do. Zu interpretieren, was du tun möchtest.

Execute the command, run the program or perform the action. Den Befehl auszuführen, das Programm zu starten oder die Aktion durchzuführen.

Display the output. Die Ausgabe anzuzeigen.

There are different types of shells, like bash, zsh, fish, but they all serve this fundamental purpose. macOS uses zsh by default in recent versions, which is very similar to bash, another common shell. For now, you don't need to worry too much about the specific shell type. Es gibt verschiedene Arten von Shells, wie bash, zsh, fish, aber sie alle dienen diesem grundlegenden Zweck. macOS verwendet standardmäßig zsh in neueren Versionen, was bash, einer anderen häufigen Shell, sehr ähnlich ist. Vorerst musst du dir nicht zu viele Gedanken über den spezifischen Shell-Typ machen.

Your First Commands: Navigating the Filesystem Deine ersten Befehle: Im Dateisystem navigieren

Your computer organizes files and folders, also called directories, in a hierarchical structure, like a tree. The terminal allows you to move around this structure and see what's inside. Dein Computer organisiert Dateien und Ordner, auch Verzeichnisse genannt, in einer hierarchischen Struktur, wie ein Baum. Das Terminal ermöglicht es dir, dich in dieser Struktur zu bewegen und zu sehen, was drin ist.

pwd, Print Working Directory: Shows you exactly where you are currently located in the filesystem hierarchy. Think of it as "You are here" on a map. pwd, Print Working Directory: Zeigt dir genau, wo du dich aktuell in der Dateisystem-Hierarchie befindest. Denke daran wie "Sie sind hier" auf einer Karte.

Try it yourself: Open the Terminal app, see Setup below if you haven't already. Type pwd and press Enter. What path does it show? This is your home directory. Probiere es selbst aus: Öffne die Terminal-App, siehe Einrichtung unten, falls du es noch nicht getan hast. Tippe pwd und drücke Enter. Welchen Pfad zeigt es? Das ist dein Home-Verzeichnis.

ls, List: Lists the files and directories inside your current working directory. ls, List: Listet die Dateien und Verzeichnisse in deinem aktuellen Arbeitsverzeichnis auf.

Try it yourself: Type ls and press Enter. What files and folders do you see? These are the contents of your home directory. Probiere es selbst aus: Tippe ls und drücke Enter. Welche Dateien und Ordner siehst du? Das sind die Inhalte deines Home-Verzeichnisses.

cd, Change Directory: Allows you to move to a different directory. cd, Change Directory: Ermöglicht es dir, zu einem anderen Verzeichnis zu wechseln.

cd directory_name: Moves you into the specified directory, for example cd Documents. cd Verzeichnisname: Bewegt dich in das angegebene Verzeichnis, zum Beispiel cd Documents.

cd dot dot: Moves you up one level in the hierarchy, to the parent directory. cd Punkt Punkt: Bewegt dich eine Ebene nach oben in der Hierarchie, zum übergeordneten Verzeichnis.

cd: Takes you back to your home directory from anywhere. cd: Bringt dich von überall zurück zu deinem Home-Verzeichnis.

cd forward slash: Takes you to the root directory, the very top of the filesystem tree. cd Schrägstrich: Bringt dich zum Root-Verzeichnis, ganz oben im Dateisystembaum.

cd tilde: Also takes you to your home directory. The tilde is a shortcut for home. cd Tilde: Bringt dich auch zu deinem Home-Verzeichnis. Die Tilde ist eine Abkürzung für Home.

Try it yourself: Probiere es selbst aus:

Type ls to see your directories. Pick one, like Documents or Downloads. Tippe ls, um deine Verzeichnisse zu sehen. Wähle eins, wie Documents oder Downloads.

Type cd Documents, replace Documents with your chosen directory, and press Enter. Tippe cd Documents, ersetze Documents mit deinem gewählten Verzeichnis, und drücke Enter.

Type pwd. Notice how the path has changed? Tippe pwd. Bemerkst du, wie sich der Pfad geändert hat?

Type ls. See the contents of this new directory? Tippe ls. Siehst du den Inhalt dieses neuen Verzeichnisses?

Type cd dot dot and press Enter. Tippe cd Punkt Punkt und drücke Enter.

Type pwd. Where are you now? You should be back where you started, your home directory. Tippe pwd. Wo bist du jetzt? Du solltest zurück sein, wo du gestartet bist, deinem Home-Verzeichnis.

Try cd forward slash and then ls. What do you see at the root? Probiere cd Schrägstrich und dann ls. Was siehst du im Root?

Type cd to get back home quickly. Tippe cd, um schnell nach Hause zurückzukommen.

Paths: Absolute versus Relative Pfade: Absolut versus Relativ

When you specify a file or directory for a command like cd, you're using a path. There are two types: Wenn du eine Datei oder ein Verzeichnis für einen Befehl wie cd angibst, verwendest du einen Pfad. Es gibt zwei Typen:

Absolute Path: Specifies the location starting from the root directory, forward slash. It's the complete, unambiguous address. Example: forward slash Users forward slash yourusername forward slash Documents forward slash report.txt. Absoluter Pfad: Gibt den Ort an, beginnend vom Root-Verzeichnis, Schrägstrich. Es ist die vollständige, eindeutige Adresse. Beispiel: Schrägstrich Users Schrägstrich deinbenutzername Schrägstrich Documents Schrägstrich report.txt.

Relative Path: Specifies the location relative to your current working directory, pwd. It's shorter but depends on where you are now. Example: If pwd shows forward slash Users forward slash yourusername, then Documents forward slash report.txt refers to the same file as the absolute path above. dot dot forward slash Pictures would refer to the Pictures directory, which is one level up and then down into Pictures. Relativer Pfad: Gibt den Ort relativ zu deinem aktuellen Arbeitsverzeichnis, pwd, an. Er ist kürzer, hängt aber davon ab, wo du jetzt bist. Beispiel: Wenn pwd Schrägstrich Users Schrägstrich deinbenutzername zeigt, dann bezieht sich Documents Schrägstrich report.txt auf dieselbe Datei wie der absolute Pfad oben. Punkt Punkt Schrägstrich Pictures würde sich auf das Pictures-Verzeichnis beziehen, das eine Ebene nach oben und dann runter in Pictures ist.

Think about it: When might you prefer using an absolute path? When might a relative path be more convenient? Denke darüber nach: Wann könntest du es vorziehen, einen absoluten Pfad zu verwenden? Wann könnte ein relativer Pfad bequemer sein?

Environment Variables Umgebungsvariablen

Environment variables are dynamic named values that can affect the way running processes will behave on a computer. They are part of the environment in which a process runs. Think of them as settings or configurations that programs can read. Umgebungsvariablen sind dynamische benannte Werte, die beeinflussen können, wie laufende Prozesse sich auf einem Computer verhalten. Sie sind Teil der Umgebung, in der ein Prozess läuft. Denke an sie als Einstellungen oder Konfigurationen, die Programme lesen können.

For example, the PATH environment variable tells the shell which directories to search for executable programs. When you type a command like ls, the shell looks for an executable file named ls in the directories listed in your PATH variable. Zum Beispiel teilt die PATH-Umgebungsvariable der Shell mit, in welchen Verzeichnissen nach ausführbaren Programmen gesucht werden soll. Wenn du einen Befehl wie ls eintippst, sucht die Shell nach einer ausführbaren Datei namens ls in den Verzeichnissen, die in deiner PATH-Variable aufgelistet sind.

printenv or env: Displays all environment variables. printenv oder env: Zeigt alle Umgebungsvariablen an.

Try it yourself: Type printenv and press Enter. You'll see a list of variables and their values. Look for one called HOME, your home directory, or USER, your username. Probiere es selbst aus: Tippe printenv und drücke Enter. Du wirst eine Liste von Variablen und ihren Werten sehen. Suche nach einer namens HOME, dein Home-Verzeichnis, oder USER, dein Benutzername.

echo dollar VARIABLE_NAME: Displays the value of a specific environment variable. The dollar sign tells the shell to substitute the variable's name with its value. echo Dollar VARIABLENNAME: Zeigt den Wert einer bestimmten Umgebungsvariable an. Das Dollar-Zeichen sagt der Shell, den Namen der Variable durch ihren Wert zu ersetzen.

Try it yourself: Type echo dollar SHELL and press Enter. This will show you the path to your default shell program. Try echo dollar PATH. Probiere es selbst aus: Tippe echo Dollar SHELL und drücke Enter. Das wird dir den Pfad zu deinem Standard-Shell-Programm zeigen. Probiere echo Dollar PATH.

Setting Variables, Temporary: You can set an environment variable for your current terminal session like this: export MY_VARIABLE equals "hello world". This variable will only exist in that terminal window and will be gone when you close it. Variablen setzen, temporär: Du kannst eine Umgebungsvariable für deine aktuelle Terminal-Sitzung so setzen: export MY_VARIABLE gleich "hello world". Diese Variable wird nur in diesem Terminal-Fenster existieren und verschwindet, wenn du es schließt.

Try it yourself: Probiere es selbst aus:

Type export GREETING equals "Hello from the Terminal" and press Enter. Tippe export GREETING gleich "Hello from the Terminal" und drücke Enter.

Type echo dollar GREETING. You should see "Hello from the Terminal". Tippe echo Dollar GREETING. Du solltest "Hello from the Terminal" sehen.

Open a new Terminal window and type echo dollar GREETING. You'll see nothing, because the variable was only set in the first window. Öffne ein neues Terminal-Fenster und tippe echo Dollar GREETING. Du wirst nichts sehen, weil die Variable nur im ersten Fenster gesetzt wurde.

Persistent Variables: Making environment variables permanent usually involves editing shell configuration files, like dot zshrc for zsh or dot bashrc for bash, which is a more advanced topic we'll cover later. Persistente Variablen: Umgebungsvariablen permanent zu machen, beinhaltet normalerweise das Bearbeiten von Shell-Konfigurationsdateien, wie Punkt zshrc für zsh oder Punkt bashrc für bash, was ein fortgeschritteneres Thema ist, das wir später behandeln werden.

Understanding environment variables is important because they control many aspects of how your system and applications behave, especially in scripting and development. Das Verständnis von Umgebungsvariablen ist wichtig, weil sie viele Aspekte kontrollieren, wie dein System und Anwendungen sich verhalten, besonders beim Skripting und in der Entwicklung.

Getting Help: man pages Hilfe bekommen: man-Seiten

How do you know what commands exist or what they do? Most commands come with a built-in manual page. Wie weißt du, welche Befehle existieren oder was sie tun? Die meisten Befehle kommen mit einer eingebauten Manual-Seite.

man command_name, Manual: Displays the manual page for a command. Example: man ls shows you all about the ls command, including options like ls dash l for a long listing format or ls dash a to show hidden files. man Befehlsname, Manual: Zeigt die Manual-Seite für einen Befehl an. Beispiel: man ls zeigt dir alles über den ls-Befehl, einschließlich Optionen wie ls Strich l für ein langes Auflistungsformat oder ls Strich a, um versteckte Dateien zu zeigen.

Press q to quit the manual page viewer. Use the arrow keys or spacebar to navigate within the man page. Drücke q, um den Manual-Seiten-Betrachter zu verlassen. Verwende die Pfeiltasten oder Leertaste, um innerhalb der man-Seite zu navigieren.

Try it yourself: Type man ls and press Enter. Look for options like l and a. What do they do? Press q to exit. Now try ls dash la in your terminal. See the difference? Probiere es selbst aus: Tippe man ls und drücke Enter. Suche nach Optionen wie l und a. Was machen sie? Drücke q zum Beenden. Probiere jetzt ls Strich la in deinem Terminal. Siehst du den Unterschied?

Setup: Finding and Opening the Terminal on macOS Einrichtung: Das Terminal auf macOS finden und öffnen

The Terminal application is already installed on your Mac. Here's how to find it: Die Terminal-Anwendung ist bereits auf deinem Mac installiert. So findest du sie:

Click the Spotlight icon, the magnifying glass, in the top-right corner of your screen, or press Command plus Spacebar. Klicke auf das Spotlight-Symbol, die Lupe, in der oberen rechten Ecke deines Bildschirms, oder drücke Command plus Leertaste.

Type Terminal in the search bar. Tippe Terminal in die Suchleiste.

Double-click the Terminal application that appears. Doppelklicke auf die Terminal-Anwendung, die erscheint.

A window will open with a text prompt. You're ready to type commands! Ein Fenster öffnet sich mit einer Texteingabeaufforderung. Du bist bereit, Befehle einzutippen!

Optional but Recommended: Drag the Terminal icon from the search results, or find it in Applications, Utilities, to your Dock for easy access later. Optional aber empfohlen: Ziehe das Terminal-Symbol aus den Suchergebnissen, oder finde es in Anwendungen, Dienstprogramme, zu deinem Dock für einfachen Zugriff später.

That's it for the pre-class reading! Experiment with the commands, pwd, ls, cd, man, printenv, echo, to get comfortable navigating your filesystem and understanding basic environment concepts. Don't worry about memorizing everything perfectly yet. The goal is to understand the basic concepts of what the terminal is, why it's useful, and how to perform fundamental navigation and inspection tasks. Das war's für die Vorbereitung vor dem Unterricht! Experimentiere mit den Befehlen, pwd, ls, cd, man, printenv, echo, um dich beim Navigieren in deinem Dateisystem und Verstehen grundlegender Umgebungskonzepte wohlzufühlen. Mach dir keine Sorgen, noch nicht alles perfekt auswendig zu können. Das Ziel ist, die grundlegenden Konzepte zu verstehen, was das Terminal ist, warum es nützlich ist und wie man fundamentale Navigations- und Inspektionsaufgaben durchführt.