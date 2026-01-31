Welcome to the second lesson in Technical Foundations! In the previous lesson, you became familiar with the terminal, the command-line interface that is a fundamental tool for many tasks in IT and cybersecurity. Now, we'll focus on another essential tool: the text editor, and the related skill of using keyboard shortcuts effectively. Willkommen zur zweiten Lektion in Technical Foundations! In der vorherigen Lektion bist du mit dem Terminal vertraut geworden, der Kommandozeilen-Schnittstelle, die ein fundamentales Werkzeug für viele Aufgaben in IT und Cybersicherheit ist. Jetzt werden wir uns auf ein anderes wesentliches Werkzeug konzentrieren: den Texteditor und die damit verbundene Fähigkeit, Tastaturkürzel effektiv zu verwenden.

Whether you're writing code, configuring systems, analyzing logs, or documenting findings, you'll constantly be working with text files. Using the right editor and knowing how to use it, and your computer in general, efficiently can dramatically speed up your workflow and reduce frustration. Ob du Code schreibst, Systeme konfigurierst, Logs analysierst oder Ergebnisse dokumentierst, du wirst ständig mit Textdateien arbeiten. Den richtigen Editor zu verwenden und zu wissen, wie man ihn benutzt, und deinen Computer im Allgemeinen, effizient kann deinen Arbeitsablauf dramatisch beschleunigen und Frustration reduzieren.

What is a Text Editor? Was ist ein Texteditor?

At its core, a text editor is a program used for editing plain text files. What's plain text? It's text without any fancy formatting like different fonts, colors, sizes, or embedded images. Think of files ending in dot txt, dot py for Python code, dot sh for shell scripts, dot conf for configuration files, dot log for log files, dot xml, dot css, dot js, et cetera. These files contain only character data. Im Kern ist ein Texteditor ein Programm, das zum Bearbeiten von Nur-Text-Dateien verwendet wird. Was ist Nur-Text? Es ist Text ohne jegliche ausgefallene Formatierung wie verschiedene Schriftarten, Farben, Größen oder eingebettete Bilder. Denke an Dateien, die mit Punkt txt enden, Punkt py für Python-Code, Punkt sh für Shell-Skripte, Punkt conf für Konfigurationsdateien, Punkt log für Logdateien, Punkt xml, Punkt css, Punkt js und so weiter. Diese Dateien enthalten nur Zeichendaten.

This is fundamentally different from word processors like Microsoft Word or Google Docs, which create rich text documents. These documents embed complex formatting information alongside the text. Trying to open a dot docx file in a plain text editor will show you a jumble of unreadable characters because the editor doesn't understand the formatting codes. Conversely, saving code or configuration files using a word processor often adds hidden formatting that can break the code or configuration. Das ist grundlegend anders als Textverarbeitungsprogramme wie Microsoft Word oder Google Docs, die Rich-Text-Dokumente erstellen. Diese Dokumente betten komplexe Formatierungsinformationen neben dem Text ein. Der Versuch, eine Punkt-docx-Datei in einem Nur-Text-Editor zu öffnen, zeigt dir ein Durcheinander unlesbarer Zeichen, weil der Editor die Formatierungscodes nicht versteht. Umgekehrt fügt das Speichern von Code- oder Konfigurationsdateien mit einem Textverarbeitungsprogramm oft versteckte Formatierung hinzu, die den Code oder die Konfiguration zerstören kann.

Key takeaway: For coding, configuration, and most cybersecurity tasks involving text files, always use a plain text editor. Wichtigste Erkenntnis: Für Programmierung, Konfiguration und die meisten Cybersicherheitsaufgaben, die Textdateien betreffen, verwende immer einen Nur-Text-Editor.

Types of Text Editors Arten von Texteditoren

Text editors come in various forms, broadly categorized as: Texteditoren gibt es in verschiedenen Formen, grob kategorisiert als:

Command-Line Interface, CLI, Editors: These editors run directly within your terminal window. You interact with them using keyboard commands, not a mouse. They are essential when working on remote servers or systems without a graphical user interface, GUI. Kommandozeilen-Schnittstelle, CLI, Editoren: Diese Editoren laufen direkt in deinem Terminal-Fenster. Du interagierst mit ihnen über Tastaturbefehle, nicht mit einer Maus. Sie sind wesentlich beim Arbeiten auf entfernten Servern oder Systemen ohne grafische Benutzeroberfläche, GUI.

Nano: A simple, beginner-friendly CLI editor. It displays helpful commands at the bottom of the screen. Often available by default on Linux and macOS. Nano: Ein einfacher, anfängerfreundlicher CLI-Editor. Er zeigt hilfreiche Befehle am unteren Bildschirmrand an. Oft standardmäßig auf Linux und macOS verfügbar.

Vim or Vi: A very powerful but notoriously complex modal editor. It has different modes, for example insert mode for typing, normal mode for commands. Vim has a steep learning curve but is incredibly efficient once mastered. It's a favorite among many experienced developers and system administrators. Available on almost every Unix-like system. Vim oder Vi: Ein sehr mächtiger, aber notorisch komplexer modaler Editor. Er hat verschiedene Modi, zum Beispiel Einfügemodus zum Tippen, Normalmodus für Befehle. Vim hat eine steile Lernkurve, ist aber unglaublich effizient, wenn man es gemeistert hat. Er ist ein Favorit unter vielen erfahrenen Entwicklern und Systemadministratoren. Verfügbar auf fast jedem Unix-ähnlichen System.

Emacs: Another extremely powerful and extensible CLI and GUI editor. Often described as an operating system in itself due to its vast capabilities. Like Vim, it has a significant learning curve. Emacs: Ein weiterer extrem mächtiger und erweiterbarer CLI- und GUI-Editor. Oft als Betriebssystem an sich beschrieben wegen seiner umfangreichen Fähigkeiten. Wie Vim hat es eine erhebliche Lernkurve.

Graphical User Interface, GUI, Editors: These are standalone applications with familiar graphical elements like menus, buttons, and mouse support. Grafische Benutzeroberfläche, GUI, Editoren: Das sind eigenständige Anwendungen mit vertrauten grafischen Elementen wie Menüs, Schaltflächen und Mausunterstützung.

Simple Editors: Such as TextEdit on macOS when set to plain text mode or Notepad on Windows. Good for quick, basic edits, but lack features for complex tasks. Einfache Editoren: Wie TextEdit auf macOS, wenn auf Nur-Text-Modus eingestellt, oder Notepad auf Windows. Gut für schnelle, grundlegende Bearbeitungen, fehlen aber Funktionen für komplexe Aufgaben.

Code Editors: These are sophisticated GUI editors designed specifically for programming and development, but they are excellent for general text editing too. They offer features well beyond simple editors. Code-Editoren: Das sind ausgeklügelte GUI-Editoren, die speziell für Programmierung und Entwicklung entwickelt wurden, aber sie sind auch ausgezeichnet für allgemeine Textbearbeitung. Sie bieten Funktionen weit über einfache Editoren hinaus.

Sublime Text Sublime Text

This is a very popular, sophisticated, and highly regarded commercial text editor known for its speed, attractive interface, and powerful features. While it requires a license for continued use, it offers an unlimited free evaluation period. It runs on Windows, macOS, and Linux. Das ist ein sehr beliebter, ausgeklügelter und hoch angesehener kommerzieller Texteditor, bekannt für seine Geschwindigkeit, attraktive Oberfläche und leistungsstarke Funktionen. Obwohl es eine Lizenz für fortgesetzte Nutzung erfordert, bietet es eine unbegrenzte kostenlose Evaluierungsperiode. Es läuft auf Windows, macOS und Linux.

It provides features like: Es bietet Funktionen wie:

Syntax Highlighting: Displays code elements like keywords, variables, strings in different colors for readability across many languages. Syntax-Hervorhebung: Zeigt Code-Elemente wie Schlüsselwörter, Variablen, Strings in verschiedenen Farben zur Lesbarkeit über viele Sprachen hinweg.

Command Palette: A quick way to access most commands and settings using the keyboard. Befehlspalette: Ein schneller Weg, auf die meisten Befehle und Einstellungen über die Tastatur zuzugreifen.

Multi-Cursor or Multi-Select: Allows editing multiple places in the file simultaneously. Multi-Cursor oder Multi-Select: Ermöglicht das gleichzeitige Bearbeiten mehrerer Stellen in der Datei.

Package Control: An integrated package manager allowing easy installation of extensions, packages, for added functionality and language support. Package Control: Ein integrierter Paketmanager, der einfache Installation von Erweiterungen, Paketen, für zusätzliche Funktionalität und Sprachunterstützung ermöglicht.

Project Management: Organize multiple files within a project folder. Projektverwaltung: Organisiere mehrere Dateien innerhalb eines Projektordners.

High Customizability: Themes, color schemes, key bindings, and settings can be extensively modified. Hohe Anpassbarkeit: Themes, Farbschemata, Tastenbelegungen und Einstellungen können umfassend modifiziert werden.

This, Sublime Text, will be the primary editor we focus on in this program. Das, Sublime Text, wird der primäre Editor sein, auf den wir uns in diesem Programm konzentrieren.

Try it yourself Probiere es selbst aus

Open your terminal. You learned this in TF1. Öffne dein Terminal. Du hast das in TF1 gelernt.

Type nano testfile.txt and press Enter. Tippe nano testfile.txt und drücke Enter.

Type a few lines of text. Tippe ein paar Textzeilen.

Notice the commands at the bottom, for example caret X Exit. The caret symbol usually means the Ctrl key. On macOS, for nano specifically in the macOS terminal, it's usually Ctrl. Try pressing Ctrl plus X. Beachte die Befehle am unteren Rand, zum Beispiel Zirkumflex X Beenden. Das Zirkumflex-Symbol bedeutet normalerweise die Ctrl-Taste. Auf macOS, speziell für nano im macOS-Terminal, ist es normalerweise Ctrl. Probiere Ctrl plus X zu drücken.

It will ask if you want to save. Press Y for Yes. Es wird fragen, ob du speichern möchtest. Drücke Y für Ja.

It will confirm the filename. Press Enter. Es wird den Dateinamen bestätigen. Drücke Enter.

You're back at the command prompt. Type ls to see testfile.txt. Type cat testfile.txt to see its contents. Du bist zurück an der Kommandozeilen-Eingabeaufforderung. Tippe ls, um testfile.txt zu sehen. Tippe cat testfile.txt, um ihren Inhalt zu sehen.

Type rm testfile.txt to delete the file. Tippe rm testfile.txt, um die Datei zu löschen.

This gave you a taste of a CLI editor. While powerful editors like Vim are valuable, we'll focus on the graphical Sublime Text for most of our work due to its user-friendliness and rich features suitable for learning. Das gab dir einen Vorgeschmack auf einen CLI-Editor. Während mächtige Editoren wie Vim wertvoll sind, werden wir uns für die meiste unserer Arbeit auf das grafische Sublime Text konzentrieren wegen seiner Benutzerfreundlichkeit und reichen Funktionen, die zum Lernen geeignet sind.

Why Efficiency Matters: The Power of Shortcuts Warum Effizienz wichtig ist: Die Kraft der Tastenkombinationen

Imagine writing an essay by carving letters into stone versus typing on a keyboard. Both achieve the goal, but the speed and effort involved are vastly different. The same applies to editing text and using your computer in general. Stell dir vor, einen Aufsatz zu schreiben, indem du Buchstaben in Stein meißelst, versus auf einer Tastatur zu tippen. Beide erreichen das Ziel, aber die Geschwindigkeit und der Aufwand sind sehr unterschiedlich. Dasselbe gilt für das Bearbeiten von Text und die allgemeine Verwendung deines Computers.

Manually performing actions like selecting text with the mouse, right-clicking to copy, moving the cursor, right-clicking again to paste, or navigating menus is slow. Keyboard shortcuts allow you to perform these common actions instantly without taking your hands off the keyboard. Das manuelle Ausführen von Aktionen wie Text mit der Maus auswählen, Rechtsklick zum Kopieren, Cursor bewegen, nochmal Rechtsklick zum Einfügen oder durch Menüs navigieren ist langsam. Tastaturkürzel ermöglichen es dir, diese häufigen Aktionen sofort auszuführen, ohne deine Hände von der Tastatur zu nehmen.

Learning fundamental shortcuts is crucial for productivity in any technical field. Even saving a few seconds per action adds up significantly over hours, days, and weeks. Importantly, many shortcuts are standardized: Das Erlernen grundlegender Tastenkombinationen ist entscheidend für Produktivität in jedem technischen Bereich. Selbst das Sparen weniger Sekunden pro Aktion summiert sich erheblich über Stunden, Tage und Wochen. Wichtig ist, dass viele Tastenkombinationen standardisiert sind:

Within the Operating System: Many shortcuts work consistently across different applications on your Mac, for example Copy/Paste. Innerhalb des Betriebssystems: Viele Tastenkombinationen funktionieren konsistent über verschiedene Anwendungen auf deinem Mac, zum Beispiel Kopieren/Einfügen.

Within Applications: Specific applications like Sublime Text have their own powerful shortcuts for specialized tasks. Innerhalb von Anwendungen: Spezifische Anwendungen wie Sublime Text haben ihre eigenen mächtigen Tastenkombinationen für spezialisierte Aufgaben.

Mastering shortcuts in your primary tools, like your OS, text editor, browser, terminal, is a key part of becoming technically proficient. Die Beherrschung von Tastenkombinationen in deinen Hauptwerkzeugen, wie deinem OS, Texteditor, Browser, Terminal, ist ein Schlüsselteil beim technisch versiert werden.

Common Shortcut Categories: Häufige Tastenkombinations-Kategorien:

Navigation: Moving the cursor or focus, character by character, word by word, line by line, start/end of file, between applications, between tabs. Navigation: Bewegen des Cursors oder Fokus, Zeichen für Zeichen, Wort für Wort, Zeile für Zeile, Anfang/Ende der Datei, zwischen Anwendungen, zwischen Tabs.

Selection: Highlighting text, often by combining navigation shortcuts with the Shift key. Auswahl: Text hervorheben, oft durch Kombinieren von Navigations-Tastenkombinationen mit der Shift-Taste.

Editing: Cut, Copy, Paste, Undo, Redo, Indent, Outdent. Bearbeiten: Ausschneiden, Kopieren, Einfügen, Rückgängig, Wiederherstellen, Einrücken, Ausrücken.

File Operations: Save, Save As, Open, New File, Close File/Window/Tab. Dateioperationen: Speichern, Speichern unter, Öffnen, Neue Datei, Datei/Fenster/Tab schließen.

Searching: Find, Find and Replace. Suchen: Finden, Finden und Ersetzen.

Application/Window Management: Switching apps, closing apps, opening search. Anwendungs-/Fensterverwaltung: Apps wechseln, Apps schließen, Suche öffnen.

Common macOS Shortcuts to Explore Häufige macOS-Tastenkombinationen zum Erkunden

Before the class, try experimenting with these common shortcuts in different applications, like a simple text file, your browser, or Finder, to see how they work. Don't worry about memorizing them all now; the goal is to get familiar with the concept and see their utility. Vor dem Unterricht probiere, mit diesen häufigen Tastenkombinationen in verschiedenen Anwendungen zu experimentieren, wie einer einfachen Textdatei, deinem Browser oder Finder, um zu sehen, wie sie funktionieren. Mach dir keine Sorgen, sie jetzt alle auswendig zu lernen; das Ziel ist, mit dem Konzept vertraut zu werden und ihren Nutzen zu sehen.

Cmd plus C: Copy selected text or item. Cmd plus C: Ausgewählten Text oder Element kopieren.

Cmd plus X: Cut selected text or item. Cmd plus X: Ausgewählten Text oder Element ausschneiden.

Cmd plus V: Paste copied or cut text or item. Cmd plus V: Kopierten oder ausgeschnittenen Text oder Element einfügen.

Cmd plus Z: Undo the last action. Cmd plus Z: Letzte Aktion rückgängig machen.

Cmd plus Shift plus Z: Redo the last undone action. Cmd plus Shift plus Z: Letzte rückgängig gemachte Aktion wiederherstellen.

Cmd plus A: Select All, for example all text in a document, all files in a folder. Cmd plus A: Alles auswählen, zum Beispiel allen Text in einem Dokument, alle Dateien in einem Ordner.

Cmd plus F: Find, opens a search bar in most apps. Cmd plus F: Finden, öffnet eine Suchleiste in den meisten Apps.

Cmd plus S: Save the current file. Cmd plus S: Aktuelle Datei speichern.

Cmd plus P: Print. Cmd plus P: Drucken.

Cmd plus Q: Quit the current application. Cmd plus Q: Aktuelle Anwendung beenden.

Cmd plus W: Close the current window or tab. Cmd plus W: Aktuelles Fenster oder Tab schließen.

Cmd plus T: Open a new tab in apps that support tabs, like browsers or Sublime Text. Cmd plus T: Neuen Tab öffnen in Apps, die Tabs unterstützen, wie Browser oder Sublime Text.

Cmd plus Tab: Switch to the next most recently used application among your open applications. Hold Cmd and keep pressing Tab to cycle through. Cmd plus Tab: Zur nächsten zuletzt verwendeten Anwendung unter deinen geöffneten Anwendungen wechseln. Halte Cmd und drücke weiter Tab, um durchzuschalten.

Cmd plus Space: Open Spotlight search, useful for quickly launching apps or finding files. Cmd plus Leertaste: Spotlight-Suche öffnen, nützlich zum schnellen Starten von Apps oder Finden von Dateien.

Option plus Left/Right Arrow: Move the text cursor one word left or right. Option plus Linke/Rechte Pfeiltaste: Textcursor ein Wort nach links oder rechts bewegen.

Cmd plus Left/Right Arrow: Move the text cursor to the beginning or end of the current line. Cmd plus Linke/Rechte Pfeiltaste: Textcursor zum Anfang oder Ende der aktuellen Zeile bewegen.

Shift plus Arrow Keys, or Shift plus Option/Cmd plus Arrow Keys: Select text while moving the cursor. Shift plus Pfeiltasten, oder Shift plus Option/Cmd plus Pfeiltasten: Text auswählen während der Cursor bewegt wird.

Cmd plus Shift plus 3: Take a screenshot of the entire screen, saved to Desktop. Cmd plus Shift plus 3: Screenshot des gesamten Bildschirms machen, gespeichert auf dem Desktop.

Cmd plus Shift plus 4: Take a screenshot of a selected area, cursor turns into crosshairs, click and drag. Cmd plus Shift plus 4: Screenshot eines ausgewählten Bereichs machen, Cursor wird zu Fadenkreuz, klicken und ziehen.

Checkout more Mac shortcuts. Schaue dir mehr Mac-Tastenkombinationen an.

Think about it Denke darüber nach

When might you have to use a CLI editor like Nano or Vim instead of a GUI editor like Sublime Text? Wann könntest du einen CLI-Editor wie Nano oder Vim anstelle eines GUI-Editors wie Sublime Text verwenden müssen?

Beyond speed, what other benefits might come from learning keyboard shortcuts? Über Geschwindigkeit hinaus, welche anderen Vorteile könnten sich aus dem Erlernen von Tastaturkürzeln ergeben?

Research Task: Open the built-in TextEdit application on your Mac, Applications, TextEdit. Go to Format, Make Plain Text. Now, compare this to what you see on the Sublime Text website or in descriptions/reviews online. Identify at least one specific feature that Sublime Text offers for editing text or code that TextEdit in plain text mode does not have. Be ready to share what you found. Recherche-Aufgabe: Öffne die eingebaute TextEdit-Anwendung auf deinem Mac, Anwendungen, TextEdit. Gehe zu Format, Als reinen Text darstellen. Vergleiche dies jetzt mit dem, was du auf der Sublime Text-Website oder in Beschreibungen/Rezensionen online siehst. Identifiziere mindestens eine spezifische Funktion, die Sublime Text zum Bearbeiten von Text oder Code bietet, die TextEdit im Nur-Text-Modus nicht hat. Sei bereit zu teilen, was du gefunden hast.

Setup Einrichtung

For this course, we will standardize on Sublime Text as our primary editor. Please ensure the latest version is installed on your Mac before the live session. Für diesen Kurs werden wir Sublime Text als unseren primären Editor standardisieren. Bitte stelle sicher, dass die neueste Version auf deinem Mac vor der Live-Sitzung installiert ist.

Check if Sublime Text is installed: Open your Applications folder. You can use Finder. Look for Sublime Text. If it's there, double-click to launch it and make sure it opens without errors. If it opens, you're all set! Prüfen, ob Sublime Text installiert ist: Öffne deinen Anwendungsordner. Du kannst Finder verwenden. Suche nach Sublime Text. Wenn es da ist, doppelklicke, um es zu starten und stelle sicher, dass es ohne Fehler öffnet. Wenn es öffnet, bist du fertig!

Install Sublime Text if necessary: Sublime Text installieren, falls nötig:

Go to the official Sublime Text download page: https://www.sublimetext.com/download Gehe zur offiziellen Sublime Text Download-Seite: https://www.sublimetext.com/download

Click the download link for macOS. This will download a dot dmg, Disk Image, file. Klicke auf den Download-Link für macOS. Das wird eine Punkt-dmg-, Disk-Image-, Datei herunterladen.

Open your Downloads folder and find the downloaded dot dmg file, for example Sublime Text Build xxxx dot dmg. Öffne deinen Downloads-Ordner und finde die heruntergeladene Punkt-dmg-Datei, zum Beispiel Sublime Text Build xxxx Punkt dmg.

Double-click the dot dmg file. A new window will open showing the Sublime Text application icon and usually a shortcut to the Applications folder. Doppelklicke auf die Punkt-dmg-Datei. Ein neues Fenster öffnet sich und zeigt das Sublime Text Anwendungssymbol und normalerweise eine Verknüpfung zum Anwendungsordner.

Drag the Sublime Text application icon into the Applications folder icon within that window. Ziehe das Sublime Text Anwendungssymbol in das Anwendungsordner-Symbol innerhalb dieses Fensters.

Close the disk image window. You can also eject the Sublime Text disk image from Finder, like ejecting a USB drive. Schließe das Disk-Image-Fenster. Du kannst auch das Sublime Text Disk-Image vom Finder auswerfen, wie das Auswerfen eines USB-Laufwerks.

Optional but recommended: Launch Sublime Text from your Applications folder. You might get a security warning since you downloaded it from the internet; click Open. Once open, right-click the Sublime Text icon in your Dock and choose Options, Keep in Dock for easy access. Optional aber empfohlen: Starte Sublime Text von deinem Anwendungsordner. Du könntest eine Sicherheitswarnung bekommen, da du es aus dem Internet heruntergeladen hast; klicke auf Öffnen. Einmal geöffnet, rechtsklicke auf das Sublime Text Symbol in deinem Dock und wähle Optionen, Im Dock behalten für einfachen Zugriff.

Launch Sublime Text: Open Sublime Text to familiarize yourself briefly with its interface. Don't worry about understanding everything yet; we'll cover the essentials in the lesson. You might see a popup mentioning it's an evaluation version; you can simply close this. Sublime Text starten: Öffne Sublime Text, um dich kurz mit seiner Oberfläche vertraut zu machen. Mach dir keine Sorgen, noch nicht alles zu verstehen; wir werden die Grundlagen in der Lektion behandeln. Du könntest ein Popup sehen, das erwähnt, dass es eine Evaluierungsversion ist; du kannst das einfach schließen.

That's it for preparation! We'll dive into using Sublime Text and mastering essential shortcuts during our live session. Be ready to practice! Das war's für die Vorbereitung! Wir werden in die Verwendung von Sublime Text eintauchen und wesentliche Tastenkombinationen während unserer Live-Sitzung meistern. Sei bereit zu üben!