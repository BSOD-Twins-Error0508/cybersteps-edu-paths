Welcome to the world of JavaScript! In this pre class preparation, we'll lay the groundwork for understanding what JavaScript is, how it works in web browsers, and its basic syntax. Willkommen in der Welt von JavaScript! In dieser Vorbereitung vor dem Unterricht legen wir die Grundlage für das Verständnis, was JavaScript ist, wie es in Webbrowsern funktioniert und seine grundlegende Syntax.

This will prepare you for our live session where we'll dive deeper into making web pages interactive. Dies wird Sie auf unsere Live-Sitzung vorbereiten, in der wir tiefer eintauchen werden, um Webseiten interaktiv zu gestalten.

What is JavaScript? Was ist JavaScript?

JavaScript is a powerful and versatile programming language primarily known as the scripting language for web pages. JavaScript ist eine leistungsstarke und vielseitige Programmiersprache, die hauptsächlich als Skriptsprache für Webseiten bekannt ist.

But it's also used in many non browser environments. Aber sie wird auch in vielen Nicht-Browser-Umgebungen verwendet.

For our purposes, we'll focus on its role in web development. Für unsere Zwecke konzentrieren wir uns auf ihre Rolle in der Webentwicklung.

Think of a website as a house. Stellen Sie sich eine Website als ein Haus vor.

HTML, HyperText Markup Language, is the structure of the house, the walls, roof, doors, and windows. HTML, HyperText Markup Language, ist die Struktur des Hauses, die Wände, das Dach, die Türen und die Fenster.

It defines the content and its organization. Es definiert den Inhalt und seine Organisation.

CSS, Cascading Style Sheets, is the interior and exterior design, the paint colors, furniture style, and landscaping. CSS, Cascading Style Sheets, ist das Innen- und Außendesign, die Farben, der Möbelstil und die Landschaftsgestaltung.

It controls the presentation and appearance of the HTML content. Es steuert die Präsentation und das Erscheinungsbild des HTML-Inhalts.

JavaScript, or JS, makes the house interactive and dynamic. JavaScript, oder JS, macht das Haus interaktiv und dynamisch.

It's like the electrical wiring, plumbing, and appliances that allow you to turn on lights, open automated doors, or have a security system that reacts to movement. Es ist wie die elektrische Verkabelung, die Sanitäranlagen und die Geräte, die es Ihnen ermöglichen, Lichter einzuschalten, automatische Türen zu öffnen oder ein Sicherheitssystem zu haben, das auf Bewegung reagiert.

JavaScript allows you to implement complex features on web pages. JavaScript ermöglicht es Ihnen, komplexe Funktionen auf Webseiten zu implementieren.

Every time you see a dynamic map, an animated graphic, a live content update, or an interactive form, JavaScript is likely involved. Jedes Mal, wenn Sie eine dynamische Karte, eine animierte Grafik, ein Live-Content-Update oder ein interaktives Formular sehen, ist wahrscheinlich JavaScript beteiligt.

It runs directly in the user's web browser, client side, which means it can respond quickly to user actions without needing to constantly communicate with a web server. Es läuft direkt im Webbrowser des Benutzers, Client-seitig, was bedeutet, dass es schnell auf Benutzeraktionen reagieren kann, ohne ständig mit einem Webserver kommunizieren zu müssen.

Basic syntax. Grundlegende Syntax.

Like any language, JavaScript has its own grammar and rules, which we call syntax. Wie jede Sprache hat JavaScript seine eigene Grammatik und Regeln, die wir Syntax nennen.

Here are some fundamental aspects. Hier sind einige grundlegende Aspekte.

Statements. Anweisungen.

A JavaScript program is a sequence of statements. Ein JavaScript-Programm ist eine Folge von Anweisungen.

Each statement is an instruction for the computer to perform an action. Jede Anweisung ist eine Instruktion für den Computer, eine Aktion auszuführen.

Statements in JavaScript are typically ended with a semicolon, although it's sometimes optional due to a feature called Automatic Semicolon Insertion, or ASI. Anweisungen in JavaScript enden normalerweise mit einem Semikolon, obwohl es manchmal optional ist aufgrund einer Funktion namens Automatic Semicolon Insertion, oder ASI.

However, it's good practice to include semicolons to avoid ambiguity. Es ist jedoch eine gute Praxis, Semikolons einzufügen, um Unklarheiten zu vermeiden.

Comments. Kommentare.

Comments are notes that you can add to your code. Kommentare sind Notizen, die Sie Ihrem Code hinzufügen können.

They are ignored by the JavaScript engine but are invaluable for explaining what your code does, both for yourself and for others who might read it. Sie werden von der JavaScript-Engine ignoriert, sind aber unschätzbar wertvoll, um zu erklären, was Ihr Code tut, sowohl für Sie selbst als auch für andere, die ihn lesen könnten.

There are two types of comments. Es gibt zwei Arten von Kommentaren.

Single line comments start with two slashes. Everything after two slashes on that line is a comment. Einzeilige Kommentare beginnen mit zwei Schrägstrichen. Alles nach zwei Schrägstrichen auf dieser Zeile ist ein Kommentar.

Multi line comments start with slash asterisk and end with asterisk slash. Everything between them is a comment. Mehrzeilige Kommentare beginnen mit Schrägstrich Sternchen und enden mit Sternchen Schrägstrich. Alles dazwischen ist ein Kommentar.

Case sensitivity. Groß- und Kleinschreibung.

JavaScript is case sensitive. JavaScript unterscheidet zwischen Groß- und Kleinschreibung.

This means that myVariable, MyVariable, and myvariable would be treated as three distinct variables. Das bedeutet, dass myVariable, MyVariable und myvariable als drei unterschiedliche Variablen behandelt würden.

Always pay close attention to capitalization. Achten Sie immer genau auf die Großschreibung.

Where does JavaScript code go? Wo kommt JavaScript-Code hin?

You can include JavaScript in your HTML documents in a few ways. Sie können JavaScript auf verschiedene Arten in Ihre HTML-Dokumente einbinden.

You'll use Visual Studio Code, or VS Code, which you're already familiar with from Python, to create and edit your HTML files and JavaScript files. Sie werden Visual Studio Code, oder VS Code, verwenden, mit dem Sie bereits von Python vertraut sind, um Ihre HTML-Dateien und JavaScript-Dateien zu erstellen und zu bearbeiten.

Typically, you'll create a project folder, open it in VS Code, and then add your files there. Normalerweise erstellen Sie einen Projektordner, öffnen ihn in VS Code und fügen dann Ihre Dateien dort hinzu.

To see your work, you'll open the HTML file directly in your web browser. Um Ihre Arbeit zu sehen, öffnen Sie die HTML-Datei direkt in Ihrem Webbrowser.

Internal JavaScript, within script tags. Internes JavaScript, innerhalb von Script-Tags.

You can embed JavaScript code directly within your HTML file using script tags. Sie können JavaScript-Code direkt in Ihrer HTML-Datei mit Script-Tags einbetten.

Typically, these are placed just before the closing body tag so that the HTML structure is loaded before the script tries to interact with it. Normalerweise werden diese direkt vor dem schließenden Body-Tag platziert, damit die HTML-Struktur geladen wird, bevor das Skript versucht, damit zu interagieren.

External JavaScript, linking to JavaScript files. Externes JavaScript, Verknüpfung mit JavaScript-Dateien.

This is the most common and recommended method for larger scripts. Dies ist die gebräuchlichste und empfohlene Methode für größere Skripte.

You write your JavaScript code in a separate file with a JavaScript extension, for example, myscript.js, and then link to it from your HTML file using the script tag with the src attribute. Sie schreiben Ihren JavaScript-Code in eine separate Datei mit einer JavaScript-Erweiterung, zum Beispiel myscript.js, und verknüpfen sie dann von Ihrer HTML-Datei aus mit dem Script-Tag mit dem src-Attribut.

Using external files helps keep your HTML cleaner, makes your JavaScript reusable across multiple pages, and improves site performance through browser caching. Die Verwendung externer Dateien hilft, Ihr HTML sauberer zu halten, macht Ihr JavaScript über mehrere Seiten hinweg wiederverwendbar und verbessert die Site-Performance durch Browser-Caching.

Inline JavaScript, in HTML attributes, use sparingly. Inline JavaScript, in HTML-Attributen, sparsam verwenden.

JavaScript can also be placed directly within HTML attributes, like onclick or onmouseover. JavaScript kann auch direkt in HTML-Attributen platziert werden, wie onclick oder onmouseover.

This is generally discouraged for anything more than very simple actions because it mixes structure, HTML, with behavior, JavaScript, too closely, making the code harder to maintain. Dies wird im Allgemeinen für mehr als sehr einfache Aktionen nicht empfohlen, weil es Struktur, HTML, mit Verhalten, JavaScript, zu eng vermischt, was den Code schwerer wartbar macht.

Think about it. Denken Sie darüber nach.

Why is it generally better to place your script tags at the end of the body section rather than in the head? Warum ist es im Allgemeinen besser, Ihre Script-Tags am Ende des Body-Abschnitts zu platzieren als im Head?

What are the advantages of using external JavaScript files over internal scripts? Was sind die Vorteile der Verwendung externer JavaScript-Dateien gegenüber internen Skripten?

Variables. Variablen.

Variables are containers for storing data values. Variablen sind Container zum Speichern von Datenwerten.

Think of them as named storage locations. Denken Sie an sie als benannte Speicherorte.

In JavaScript, you can declare variables using var, let, or const. In JavaScript können Sie Variablen mit var, let oder const deklarieren.

let declares a block scoped local variable, optionally initializing it to a value. let deklariert eine blockbezogene lokale Variable und initialisiert sie optional mit einem Wert.

Block scoped means the variable is only accessible within the block of code, for example, inside an if statement or a for loop, where it's defined. Blockbezogen bedeutet, dass die Variable nur innerhalb des Codeblocks zugänglich ist, zum Beispiel innerhalb einer if-Anweisung oder einer for-Schleife, wo sie definiert ist.

This is the preferred way to declare variables that might be reassigned. Dies ist die bevorzugte Art, Variablen zu deklarieren, die möglicherweise neu zugewiesen werden.

const declares a block scoped local variable, but its value cannot be reassigned after it's initialized. const deklariert eine blockbezogene lokale Variable, aber ihr Wert kann nach der Initialisierung nicht neu zugewiesen werden.

It's short for constant. Use const for values that you know shouldn't change. Es ist die Abkürzung für Konstante. Verwenden Sie const für Werte, von denen Sie wissen, dass sie sich nicht ändern sollten.

var, this was the original way to declare variables in JavaScript. var, dies war die ursprüngliche Art, Variablen in JavaScript zu deklarieren.

It has function scope or global scope, and has some quirks, like hoisting, that can lead to confusion. Es hat Funktions- oder globalen Gültigkeitsbereich und hat einige Eigenheiten, wie Hoisting, die zu Verwirrung führen können.

While you'll see it in older code, modern JavaScript development generally favors let and const. Während Sie es in älterem Code sehen werden, bevorzugt die moderne JavaScript-Entwicklung im Allgemeinen let und const.

Naming conventions. Namenskonventionen.

Variable names can contain letters, digits, underscores, and dollar signs. Variablennamen können Buchstaben, Ziffern, Unterstriche und Dollarzeichen enthalten.

They must begin with a letter, underscore, or dollar sign. They cannot start with a number. Sie müssen mit einem Buchstaben, Unterstrich oder Dollarzeichen beginnen. Sie können nicht mit einer Zahl beginnen.

Names are case sensitive, for example, user and User are different. Namen unterscheiden zwischen Groß- und Kleinschreibung, zum Beispiel sind user und User unterschiedlich.

It's common practice to use camelCase for variable names, for example, firstName, userProfileData. Es ist übliche Praxis, camelCase für Variablennamen zu verwenden, zum Beispiel firstName, userProfileData.

Avoid using reserved keywords, like let, const, function, if, and so on, as variable names. Vermeiden Sie die Verwendung reservierter Schlüsselwörter wie let, const, function, if und so weiter als Variablennamen.

Data types. Datentypen.

JavaScript variables can hold various types of data. JavaScript-Variablen können verschiedene Arten von Daten enthalten.

JavaScript is a dynamically typed language, meaning you don't have to explicitly declare the type of a variable. JavaScript ist eine dynamisch typisierte Sprache, was bedeutet, dass Sie den Typ einer Variablen nicht explizit deklarieren müssen.

The type is determined automatically at runtime. Der Typ wird automatisch zur Laufzeit bestimmt.

Here are the basic, primitive, data types. Hier sind die grundlegenden, primitiven Datentypen.

String represents textual data. Strings are enclosed in single quotes, double quotes, or backticks. String repräsentiert Textdaten. Strings sind in einfache Anführungszeichen, doppelte Anführungszeichen oder Backticks eingeschlossen.

Number represents numeric data, including integers and floating point numbers. Number repräsentiert numerische Daten, einschließlich ganzer Zahlen und Gleitkommazahlen.

Boolean represents a logical entity and can have two values, true or false. Boolean repräsentiert eine logische Entität und kann zwei Werte haben, wahr oder falsch.

Null represents the intentional absence of any object value. It's a special value that means no value or empty. Null repräsentiert die beabsichtigte Abwesenheit eines Objektwerts. Es ist ein spezieller Wert, der keinen Wert oder leer bedeutet.

Undefined represents a variable that has been declared but not yet assigned a value. Undefined repräsentiert eine Variable, die deklariert, aber noch nicht mit einem Wert versehen wurde.

There's also a complex data type called Object, which we'll explore in more detail later. Es gibt auch einen komplexen Datentyp namens Object, den wir später genauer untersuchen werden.

Arrays and functions are also types of objects in JavaScript. Arrays und Funktionen sind auch Arten von Objekten in JavaScript.

You can check the type of a variable using the typeof operator. Sie können den Typ einer Variablen mit dem typeof-Operator überprüfen.

Try it yourself. Probieren Sie es selbst aus.

Open your web browser's developer console. Öffnen Sie die Entwicklerkonsole Ihres Webbrowsers.

Declare a variable using let and assign it your favorite color as a string. Deklarieren Sie eine Variable mit let und weisen Sie ihr Ihre Lieblingsfarbe als String zu.

Declare another variable using const and assign it the current year as a number. Deklarieren Sie eine weitere Variable mit const und weisen Sie ihr das aktuelle Jahr als Zahl zu.

Use console.log to print both variables and their types using the typeof operator. Verwenden Sie console.log, um beide Variablen und ihre Typen mit dem typeof-Operator auszugeben.

Basic operators. Grundlegende Operatoren.

Operators are special symbols used to perform operations on operands, values and variables. Operatoren sind spezielle Symbole, die verwendet werden, um Operationen auf Operanden, Werten und Variablen durchzuführen.

Arithmetic operators. Arithmetische Operatoren.

Plus for addition, minus for subtraction, asterisk for multiplication, slash for division, percent for modulus, remainder of a division, asterisk asterisk for exponentiation. Plus für Addition, Minus für Subtraktion, Sternchen für Multiplikation, Schrägstrich für Division, Prozent für Modulus, Rest einer Division, Sternchen Sternchen für Potenzierung.

Assignment operators. Zuweisungsoperatoren.

Equals for assignment, plus equals for addition assignment, x plus equals y is x equals x plus y, minus equals for subtraction assignment, asterisk equals for multiplication assignment, slash equals for division assignment. Gleich für Zuweisung, Plus Gleich für Additionszuweisung, x plus gleich y ist x gleich x plus y, Minus Gleich für Subtraktionszuweisung, Sternchen Gleich für Multiplikationszuweisung, Schrägstrich Gleich für Divisionszuweisung.

Comparison operators. Vergleichsoperatoren.

These operators compare two values and return a boolean, true or false. Diese Operatoren vergleichen zwei Werte und geben einen booleschen Wert zurück, wahr oder falsch.

Double equals, equal to, loose equality, performs type coercion. Doppeltes Gleichheitszeichen, gleich, lose Gleichheit, führt Typumwandlung durch.

Triple equals, strictly equal to, checks value and type, no type coercion. Dreifaches Gleichheitszeichen, streng gleich, überprüft Wert und Typ, keine Typumwandlung.

Exclamation mark equals, not equal to, loose inequality. Ausrufezeichen Gleich, nicht gleich, lose Ungleichheit.

Exclamation mark double equals, strictly not equal to, checks value and type. Ausrufezeichen Doppeltes Gleichheitszeichen, streng nicht gleich, überprüft Wert und Typ.

Greater than, less than, greater than or equal to, less than or equal to. Größer als, kleiner als, größer oder gleich, kleiner oder gleich.

It is strongly recommended to use strict equality, triple equals, and strict inequality, exclamation mark double equals, to avoid unexpected behavior due to type coercion. Es wird dringend empfohlen, strikte Gleichheit, dreifaches Gleichheitszeichen, und strikte Ungleichheit, Ausrufezeichen Doppeltes Gleichheitszeichen, zu verwenden, um unerwartetes Verhalten aufgrund von Typumwandlung zu vermeiden.

Logical operators. Logische Operatoren.

Used to combine or invert boolean values. Verwendet, um boolesche Werte zu kombinieren oder umzukehren.

Ampersand ampersand, logical AND, true if both operands are true. Ampersand Ampersand, logisches UND, wahr wenn beide Operanden wahr sind.

Pipe pipe, logical OR, true if at least one operand is true. Pipe Pipe, logisches ODER, wahr wenn mindestens ein Operand wahr ist.

Exclamation mark, logical NOT, inverts the boolean value. Ausrufezeichen, logisches NICHT, kehrt den booleschen Wert um.

Think about it. Denken Sie darüber nach.

What would be the result of 0 double equals false? What about 0 triple equals false? Why? Was wäre das Ergebnis von 0 doppeltes Gleichheitszeichen falsch? Was ist mit 0 dreifaches Gleichheitszeichen falsch? Warum?

Consider let a equals 5, let b equals string 10, console.log a plus b. What do you expect the output to be and why? Betrachten Sie let a gleich 5, let b gleich String 10, console.log a plus b. Was erwarten Sie als Ausgabe und warum?

Interacting with the browser. Interaktion mit dem Browser.

JavaScript's primary playground in web development is a modern web browser like Google Chrome or Mozilla Firefox. Ensure yours is up to date. JavaScripts primärer Spielplatz in der Webentwicklung ist ein moderner Webbrowser wie Google Chrome oder Mozilla Firefox. Stellen Sie sicher, dass Ihrer auf dem neuesten Stand ist.

These browsers come with built in Developer Tools, or DevTools, that are essential for web development. Diese Browser kommen mit eingebauten Entwicklertools, oder DevTools, die für die Webentwicklung unerlässlich sind.

How to open Developer Tools, or DevTools. Wie man Entwicklertools, oder DevTools, öffnet.

Chrome, right click anywhere on a webpage and select Inspect, or press Command plus Option plus I on Mac. Chrome, Rechtsklick irgendwo auf einer Webseite und wählen Sie Inspizieren, oder drücken Sie Befehl plus Option plus I auf Mac.

Firefox, right click anywhere on a webpage and select Inspect Element, or press Command plus Option plus I on Mac. Firefox, Rechtsklick irgendwo auf einer Webseite und wählen Sie Element untersuchen, oder drücken Sie Befehl plus Option plus I auf Mac.

Once DevTools is open, look for the Console tab. This is where console.log messages appear and where you can type and execute JavaScript code directly. Sobald DevTools geöffnet ist, suchen Sie nach dem Konsolen-Tab. Hier erscheinen console.log-Nachrichten und hier können Sie JavaScript-Code direkt eingeben und ausführen.

console.log console.log

The console.log method writes a message to the browser's developer console. Die console.log-Methode schreibt eine Nachricht in die Entwicklerkonsole des Browsers.

It's incredibly useful for debugging your code, checking variable values, and understanding the flow of execution. Es ist unglaublich nützlich zum Debuggen Ihres Codes, Überprüfen von Variablenwerten und Verstehen des Ausführungsflusses.

alert alert

The alert method displays a simple dialog box with a message and an OK button. Die alert-Methode zeigt ein einfaches Dialogfeld mit einer Nachricht und einer OK-Schaltfläche an.

It's modal, meaning it blocks further interaction with the page until the user dismisses it. Es ist modal, was bedeutet, dass es weitere Interaktionen mit der Seite blockiert, bis der Benutzer es schließt.

While alert can be useful for quick tests, it's generally not recommended for user interaction in modern web applications because it can be disruptive. Während alert für schnelle Tests nützlich sein kann, wird es im Allgemeinen nicht für Benutzerinteraktion in modernen Webanwendungen empfohlen, weil es störend sein kann.

A glimpse into DOM manipulation. Ein Einblick in DOM-Manipulation.

The Document Object Model, or DOM, is a programming interface for HTML documents. Das Document Object Model, oder DOM, ist eine Programmierschnittstelle für HTML-Dokumente.

It represents the page so that programs can change the document structure, style, and content. Es repräsentiert die Seite, sodass Programme die Dokumentstruktur, den Stil und den Inhalt ändern können.

JavaScript can interact with the DOM to dynamically update what the user sees. JavaScript kann mit dem DOM interagieren, um dynamisch zu aktualisieren, was der Benutzer sieht.

We will explore DOM manipulation in much more detail in our live session and subsequent lessons. Wir werden DOM-Manipulation in unserer Live-Sitzung und in nachfolgenden Lektionen viel detaillierter erkunden.

Try it yourself. Probieren Sie es selbst aus.

Create a new HTML file named test.html on your computer using VS Code. Erstellen Sie eine neue HTML-Datei mit dem Namen test.html auf Ihrem Computer mit VS Code.

Add the basic HTML structure. Fügen Sie die grundlegende HTML-Struktur hinzu.

Save the file and open it in your web browser. Speichern Sie die Datei und öffnen Sie sie in Ihrem Webbrowser.

Observe the alert box. Beobachten Sie das Warnfeld.

Open the developer console, for example, right click, Inspect, then Console tab. Öffnen Sie die Entwicklerkonsole, zum Beispiel Rechtsklick, Inspizieren, dann Konsolen-Tab.

Do you see the message Hello from the internal script? Sehen Sie die Nachricht Hallo vom internen Skript?

In the console, type 2 plus 2 and press Enter. What happens? Geben Sie in der Konsole 2 plus 2 ein und drücken Sie Enter. Was passiert?

Type let myName equals Your Name, replace Your Name with your actual name, and press Enter. Geben Sie let myName gleich Ihr Name ein, ersetzen Sie Ihr Name durch Ihren tatsächlichen Namen, und drücken Sie Enter.

Then type console.log myName and press Enter. Dann geben Sie console.log myName ein und drücken Sie Enter.

This concludes your pre class preparation for JavaScript. Dies schließt Ihre Vorbereitung vor dem Unterricht für JavaScript ab.

By understanding these core concepts, you'll be well equipped for our interactive session. Durch das Verständnis dieser Kernkonzepte sind Sie gut für unsere interaktive Sitzung ausgerüstet.

Get ready to bring your web pages to life! Machen Sie sich bereit, Ihre Webseiten zum Leben zu erwecken!

The slides for the live session can be viewed here. Try not to peek before class, spoilers inside! Die Folien für die Live-Sitzung können hier eingesehen werden. Versuchen Sie, nicht vor dem Unterricht zu schauen, Spoiler im Inneren!