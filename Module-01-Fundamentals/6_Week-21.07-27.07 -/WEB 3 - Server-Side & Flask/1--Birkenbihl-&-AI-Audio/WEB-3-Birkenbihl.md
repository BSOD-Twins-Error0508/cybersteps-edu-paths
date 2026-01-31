Welcome to the world of server-side web development! Willkommen in der Welt der serverseitigen Webentwicklung!

So far, you've learned about what happens in a web browser, the client-side, using HTML, CSS, and JavaScript. Bisher hast du gelernt, was in einem Webbrowser passiert, der Client-Seite, mit HTML, CSS und JavaScript.

Now, we'll explore what happens on the server, the powerful machine that responds to your browser's requests and makes the web dynamic and interactive. Jetzt werden wir erkunden, was auf dem Server passiert, der leistungsstarken Maschine, die auf die Anfragen deines Browsers antwortet und das Web dynamisch und interaktiv macht.

In this lesson, we'll focus on Flask, a popular Python framework for building web applications. In dieser Lektion konzentrieren wir uns auf Flask, ein beliebtes Python-Framework zum Erstellen von Webanwendungen.

Client-Side versus Server-Side Client-Seite versus Server-Seite

Think of a restaurant. The client-side is like the dining area and the menu you see. Denke an ein Restaurant. Die Client-Seite ist wie der Essbereich und die Speisekarte, die du siehst.

It's what you, the customer or user, interact with directly. Das ist das, womit du, der Kunde oder Benutzer, direkt interagierst.

Your web browser renders HTML, the structure of the menu, CSS, how the menu looks, and JavaScript, any interactive elements on the menu, like a button to show daily specials. Dein Webbrowser rendert HTML, die Struktur der Speisekarte, CSS, wie die Speisekarte aussieht, und JavaScript, alle interaktiven Elemente auf der Speisekarte, wie einen Button, um Tagesgerichte anzuzeigen.

The server-side is like the kitchen of the restaurant. Die Server-Seite ist wie die Küche des Restaurants.

It's hidden from you, but it's where all the important work happens. Sie ist vor dir verborgen, aber dort passiert die ganze wichtige Arbeit.

Receiving Orders, Requests: The kitchen receives an order from a waiter, your browser sending an HTTP request. Empfangen von Bestellungen, Anfragen: Die Küche erhält eine Bestellung von einem Kellner, dein Browser sendet eine HTTP-Anfrage.

Preparing Food, Processing Logic: Chefs, server-side code, use ingredients, data, and recipes, algorithms, to prepare your meal. Essen zubereiten, Verarbeitungslogik: Köche, serverseitiger Code, verwenden Zutaten, Daten, und Rezepte, Algorithmen, um deine Mahlzeit zuzubereiten.

This could involve looking up information in a database, like checking if an item is in stock, performing calculations, or making decisions based on your order. Dies könnte das Nachschlagen von Informationen in einer Datenbank beinhalten, wie die Überprüfung, ob ein Artikel vorrätig ist, Berechnungen durchzuführen oder Entscheidungen basierend auf deiner Bestellung zu treffen.

Sending Out the Meal, Responses: Once the meal is ready, it's sent back to your table, the server sends an HTTP response, often containing HTML, back to your browser. Versenden der Mahlzeit, Antworten: Sobald die Mahlzeit fertig ist, wird sie zu deinem Tisch zurückgeschickt, der Server sendet eine HTTP-Antwort, oft HTML enthaltend, zurück an deinen Browser.

Key Differences Hauptunterschiede

Execution Location: Client-side code, HTML, CSS, JavaScript, runs in the user's web browser. Server-side code, for example Python with Flask, runs on a web server. Ausführungsort: Client-seitiger Code, HTML, CSS, JavaScript, läuft im Webbrowser des Benutzers. Server-seitiger Code, zum Beispiel Python mit Flask, läuft auf einem Webserver.

Access to Resources: Server-side code can access resources that client-side code cannot, such as databases, file systems on the server, and other server-side services. Zugriff auf Ressourcen: Server-seitiger Code kann auf Ressourcen zugreifen, auf die client-seitiger Code nicht zugreifen kann, wie Datenbanken, Dateisysteme auf dem Server und andere serverseitige Dienste.

This is crucial for security and data management. Das ist entscheidend für Sicherheit und Datenverwaltung.

Dynamic Content Generation: While JavaScript can manipulate a page after it's loaded, server-side code is often responsible for generating the initial HTML content dynamically, tailoring it to the specific user or request. Dynamische Inhaltsgenerierung: Während JavaScript eine Seite manipulieren kann, nachdem sie geladen wurde, ist serverseitiger Code oft dafür verantwortlich, den anfänglichen HTML-Inhalt dynamisch zu generieren und ihn auf den spezifischen Benutzer oder die Anfrage zuzuschneiden.

For example, showing your username after you log in, or displaying search results. Zum Beispiel, deinen Benutzernamen anzuzeigen, nachdem du dich angemeldet hast, oder Suchergebnisse anzuzeigen.

Think about it Denke darüber nach

What are some tasks that must happen on a server and cannot be done securely or efficiently in a user's browser? Welche Aufgaben müssen auf einem Server ausgeführt werden und können nicht sicher oder effizient im Browser eines Benutzers erledigt werden?

What is a Web Framework? Was ist ein Web-Framework?

Imagine building a complex application like a social media site or an online store from scratch using only basic Python. Stell dir vor, du baust eine komplexe Anwendung wie eine Social-Media-Seite oder einen Online-Shop von Grund auf nur mit grundlegendem Python.

You'd have to handle raw HTTP requests, manage URLs, structure your code in a maintainable way, connect to databases, ensure security, and much more. Du müsstest rohe HTTP-Anfragen verarbeiten, URLs verwalten, deinen Code auf wartbare Weise strukturieren, dich mit Datenbanken verbinden, Sicherheit gewährleisten und vieles mehr.

It would be a monumental task! Es wäre eine monumentale Aufgabe!

A web framework is a collection of tools, libraries, and conventions that simplifies the process of building web applications. Ein Web-Framework ist eine Sammlung von Werkzeugen, Bibliotheken und Konventionen, die den Prozess der Erstellung von Webanwendungen vereinfacht.

It provides a structured way to develop web apps, handling many of an application's common, repetitive tasks, allowing developers to focus on the unique features of their application. Es bietet einen strukturierten Weg, Web-Apps zu entwickeln, viele der häufigen, sich wiederholenden Aufgaben einer Anwendung zu handhaben und ermöglicht es Entwicklern, sich auf die einzigartigen Funktionen ihrer Anwendung zu konzentrieren.

Why use a web framework? Warum ein Web-Framework verwenden?

Productivity: Frameworks provide ready-made components for common tasks, like routing URLs or handling forms, speeding up development. Produktivität: Frameworks bieten vorgefertigte Komponenten für gängige Aufgaben, wie das Routen von URLs oder das Verarbeiten von Formularen, was die Entwicklung beschleunigt.

Organization: They enforce a certain structure, making code more organized and easier for teams to work on. Organisation: Sie erzwingen eine bestimmte Struktur, wodurch der Code organisierter wird und Teams leichter damit arbeiten können.

Best Practices: Good frameworks often incorporate best practices for security, performance, and scalability. Best Practices: Gute Frameworks integrieren oft Best Practices für Sicherheit, Leistung und Skalierbarkeit.

Community and Ecosystem: Popular frameworks have large communities, meaning plenty of documentation, tutorials, and third-party packages. Community und Ökosystem: Beliebte Frameworks haben große Communities, was viel Dokumentation, Tutorials und Drittanbieter-Pakete bedeutet.

Introduction to Flask Einführung in Flask

Flask is a micro web framework written in Python. Flask ist ein Mikro-Web-Framework, das in Python geschrieben ist.

The term micro doesn't mean it's less powerful or can only build small applications. Der Begriff Mikro bedeutet nicht, dass es weniger leistungsfähig ist oder nur kleine Anwendungen erstellen kann.

Instead, it means Flask aims to keep its core simple and extensible. Stattdessen bedeutet es, dass Flask darauf abzielt, seinen Kern einfach und erweiterbar zu halten.

It provides the basics for web development, like routing requests, but doesn't make many decisions for you about things like database layers or template engines, though it has excellent defaults and makes them easy to add. Es bietet die Grundlagen für Webentwicklung, wie das Routen von Anfragen, trifft aber nicht viele Entscheidungen für dich über Dinge wie Datenbankschichten oder Template-Engines, obwohl es ausgezeichnete Standards hat und sie einfach hinzuzufügen macht.

Key Characteristics of Flask Hauptmerkmale von Flask

Lightweight: It has a small, easy-to-understand core. Leichtgewichtig: Es hat einen kleinen, leicht verständlichen Kern.

Flexible: You can choose your own tools and libraries for tasks like database interaction or form validation. Flexibel: Du kannst deine eigenen Werkzeuge und Bibliotheken für Aufgaben wie Datenbankinteraktion oder Formularvalidierung wählen.

Extensible: Flask can be extended with numerous Flask extensions that add functionality, for example for database integration, user authentication, etc. Erweiterbar: Flask kann mit zahlreichen Flask-Erweiterungen erweitert werden, die Funktionalität hinzufügen, zum Beispiel für Datenbankintegration, Benutzerauthentifizierung usw.

Pythonic: Flask feels natural to Python developers. Pythonisch: Flask fühlt sich für Python-Entwickler natürlich an.

Install Flask Flask installieren

Open your terminal or command prompt. Öffne dein Terminal oder die Eingabeaufforderung.

Install Flask using pip, Python's package installer. Type the following command and press Enter: pip install Flask Installiere Flask mit pip, Pythons Paketinstaller. Gib den folgenden Befehl ein und drücke Enter: pip install Flask

Or if you have multiple Python versions or use python3 command: pip3 install Flask Oder wenn du mehrere Python-Versionen hast oder den python3-Befehl verwendest: pip3 install Flask

To verify Flask is installed, you can try to import it in a Python interpreter. Um zu überprüfen, ob Flask installiert ist, kannst du versuchen, es in einem Python-Interpreter zu importieren.

Type python or python3 in your terminal to start the interpreter. Gib python oder python3 in dein Terminal ein, um den Interpreter zu starten.

Then type import flask and press Enter. Dann gib import flask ein und drücke Enter.

If no errors appear, Flask is installed correctly. You can type exit() to leave the Python interpreter. Wenn keine Fehler erscheinen, ist Flask korrekt installiert. Du kannst exit() eingeben, um den Python-Interpreter zu verlassen.

Basic Flask Concepts Grundlegende Flask-Konzepte

Let's look at the fundamental building blocks of a Flask application. Schauen wir uns die grundlegenden Bausteine einer Flask-Anwendung an.

Routing Routing

When your browser sends a request to a URL, for example http://example.com/about, the web server needs to know which piece of code should handle that request. Wenn dein Browser eine Anfrage an eine URL sendet, zum Beispiel http://example.com/about, muss der Webserver wissen, welches Code-Stück diese Anfrage verarbeiten soll.

Routing is the mechanism that maps URLs to specific Python functions in your Flask application. Routing ist der Mechanismus, der URLs auf bestimmte Python-Funktionen in deiner Flask-Anwendung abbildet.

In Flask, you define routes using the @app.route() decorator above a function. In Flask definierst du Routen mit dem @app.route()-Dekorator über einer Funktion.

from flask import Flask from flask import Flask

Create a Flask application instance: app = Flask(**name**) Erstelle eine Flask-Anwendungsinstanz: app = Flask(**name**)

Define a route for the homepage URL, slash: @app.route('/') Definiere eine Route für die Homepage-URL, Schrägstrich: @app.route('/')

def home(): return "Hello, this is the homepage!" def home(): return "Hallo, das ist die Homepage!"

Define a route for slash about: @app.route('/about') Definiere eine Route für Schrägstrich about: @app.route('/about')

def about_page(): return "This is the about page." def about_page(): return "Das ist die About-Seite."

In this example, app = Flask(**name**) creates an instance of the Flask application. In diesem Beispiel erstellt app = Flask(**name**) eine Instanz der Flask-Anwendung.

**name** is a special Python variable that gets the name of the current module. Flask uses this to locate resources. **name** ist eine spezielle Python-Variable, die den Namen des aktuellen Moduls erhält. Flask verwendet dies, um Ressourcen zu lokalisieren.

@app.route('/') tells Flask that if someone visits the root URL of your site, for example http://127.0.0.1:5000/, the home() function should be executed. @app.route('/') sagt Flask, dass wenn jemand die Root-URL deiner Seite besucht, zum Beispiel http://127.0.0.1:5000/, die home()-Funktion ausgeführt werden soll.

@app.route('/about') tells Flask that visiting slash about should execute the about_page() function. @app.route('/about') sagt Flask, dass der Besuch von Schrägstrich about die about_page()-Funktion ausführen soll.

View Functions View-Funktionen

The functions associated with routes, like home() and about_page() above, are called view functions. Die mit Routen verbundenen Funktionen, wie home() und about_page() oben, werden View-Funktionen genannt.

Their job is to receive and process the incoming request, though in these simple examples they don't do much processing. Ihre Aufgabe ist es, die eingehende Anfrage zu empfangen und zu verarbeiten, obwohl sie in diesen einfachen Beispielen nicht viel Verarbeitung durchführen.

And to return a response that will be sent back to the client's browser. This response is typically HTML, but it can also be plain text, JSON, or other formats. Und eine Antwort zurückzugeben, die an den Browser des Clients zurückgeschickt wird. Diese Antwort ist typischerweise HTML, kann aber auch einfacher Text, JSON oder andere Formate sein.

For now, our view functions are just returning simple strings. These strings will be displayed directly in the browser. Vorerst geben unsere View-Funktionen nur einfache Strings zurück. Diese Strings werden direkt im Browser angezeigt.

Running a Flask Application Eine Flask-Anwendung ausführen

To actually run your Flask application and see it in action, you need to add a bit more code to your Python file. Um deine Flask-Anwendung tatsächlich auszuführen und in Aktion zu sehen, musst du etwas mehr Code zu deiner Python-Datei hinzufügen.

This code typically checks if the script is being run directly, as opposed to being imported into another script, and then starts a development web server. Dieser Code überprüft typischerweise, ob das Skript direkt ausgeführt wird, im Gegensatz dazu, in ein anderes Skript importiert zu werden, und startet dann einen Entwicklungs-Webserver.

from flask import Flask from flask import Flask

app = Flask(**name**) app = Flask(**name**)

@app.route('/') def home(): return "Hello, World! This is Flask." @app.route('/') def home(): return "Hallo, Welt! Das ist Flask."

@app.route('/profile/<username>') def profile(username): return f"Hello, {username}! This is your profile page." @app.route('/profile/<username>') def profile(username): return f"Hallo, {username}! Das ist deine Profilseite."

This is the part that runs the app: if **name** == '**main**': Das ist der Teil, der die App ausführt: if **name** == '**main**':

host='0.0.0.0' makes the server accessible from other devices on your network host='0.0.0.0' macht den Server von anderen Geräten in deinem Netzwerk aus zugänglich

port=5000 is the default port Flask uses port=5000 ist der Standardport, den Flask verwendet

debug=True enables debug mode, which is very helpful during development debug=True aktiviert den Debug-Modus, der während der Entwicklung sehr hilfreich ist

app.run(host='0.0.0.0', port=5000, debug=True) app.run(host='0.0.0.0', port=5000, debug=True)

Explanation Erklärung

if **name** == '**main**': This is a standard Python construct. The code inside this block will only run when you execute the script directly, for example python my_app.py. if **name** == '**main**': Das ist ein Standard-Python-Konstrukt. Der Code in diesem Block wird nur ausgeführt, wenn du das Skript direkt ausführst, zum Beispiel python my_app.py.

app.run(host='0.0.0.0', port=5000, debug=True): This line starts Flask's built-in development server. app.run(host='0.0.0.0', port=5000, debug=True): Diese Zeile startet Flasks eingebauten Entwicklungsserver.

host='0.0.0.0': This makes the server accessible from any IP address on your machine, including from other devices on your local network if your firewall allows it. host='0.0.0.0': Dies macht den Server von jeder IP-Adresse auf deinem Computer aus zugänglich, einschließlich von anderen Geräten in deinem lokalen Netzwerk, wenn deine Firewall es erlaubt.

For local development, 127.0.0.1, localhost, is also common. Für lokale Entwicklung ist 127.0.0.1, localhost, auch üblich.

port=5000: This specifies the port number the server will listen on. You'd access your app at http://127.0.0.1:5000/ or http://localhost:5000/. port=5000: Dies spezifiziert die Portnummer, auf der der Server hört. Du würdest auf deine App unter http://127.0.0.1:5000/ oder http://localhost:5000/ zugreifen.

debug=True: This is very important during development. It does two things. debug=True: Das ist während der Entwicklung sehr wichtig. Es macht zwei Dinge.

Activates the debugger: If an error occurs in your code, Flask will show you a detailed traceback in your browser, making it easier to find and fix issues. Aktiviert den Debugger: Wenn ein Fehler in deinem Code auftritt, zeigt dir Flask einen detaillierten Traceback in deinem Browser, was es einfacher macht, Probleme zu finden und zu beheben.

Activates the reloader: Whenever you save changes to your Python code, the server will automatically restart, so you don't have to stop and start it manually to see your changes. Aktiviert den Reloader: Wann immer du Änderungen an deinem Python-Code speicherst, wird der Server automatisch neu starten, sodass du ihn nicht manuell stoppen und starten musst, um deine Änderungen zu sehen.

Caution: Never run a Flask application with debug=True in a production environment, as it can pose security risks. Vorsicht: Führe niemals eine Flask-Anwendung mit debug=True in einer Produktionsumgebung aus, da dies Sicherheitsrisiken mit sich bringen kann.

Try it yourself Probiere es selbst aus

Create a new folder for your Flask project, for example my_flask_app. Erstelle einen neuen Ordner für dein Flask-Projekt, zum Beispiel my_flask_app.

Inside this folder, create a Python file named app.py. Erstelle in diesem Ordner eine Python-Datei mit dem Namen app.py.

Copy the complete Flask application code, including the app.run part, from the Running a Flask Application section above into your app.py. Kopiere den vollständigen Flask-Anwendungscode, einschließlich des app.run-Teils, aus dem Abschnitt Eine Flask-Anwendung ausführen oben in deine app.py.

Open your terminal or command prompt, navigate to your project folder, my_flask_app. Öffne dein Terminal oder die Eingabeaufforderung, navigiere zu deinem Projektordner, my_flask_app.

Run the command python app.py. Führe den Befehl python app.py aus.

You should see output indicating the server is running, something like: Running on http://127.0.0.1:5000/, Press CTRL+C to quit, Restarting with stat, Debugger is active!, Debugger PIN: ... Du solltest eine Ausgabe sehen, die anzeigt, dass der Server läuft, etwa so: Running on http://127.0.0.1:5000/, Press CTRL+C to quit, Restarting with stat, Debugger is active!, Debugger PIN: ...

Open your web browser and go to http://127.0.0.1:5000/. You should see Hello, World! This is Flask. Öffne deinen Webbrowser und gehe zu http://127.0.0.1:5000/. Du solltest Hallo, Welt! Das ist Flask sehen.

Now try visiting http://127.0.0.1:5000/profile/YourName, replace YourName with your actual name. You should see a personalized greeting! Versuche jetzt http://127.0.0.1:5000/profile/YourName zu besuchen, ersetze YourName durch deinen tatsächlichen Namen. Du solltest eine personalisierte Begrüßung sehen!

Think about it Denke darüber nach

How might you design routes for a simple blog that needs to show a homepage listing all blog posts. Wie würdest du Routen für einen einfachen Blog entwerfen, der eine Homepage mit allen Blogposts zeigen muss.

A page to display a single blog post, identified by a unique ID, for example slash post slash 123. Eine Seite, um einen einzelnen Blogpost anzuzeigen, identifiziert durch eine eindeutige ID, zum Beispiel Schrägstrich post Schrägstrich 123.

A page where a user could create a new blog post, for example slash create-post. Eine Seite, wo ein Benutzer einen neuen Blogpost erstellen kann, zum Beispiel Schrägstrich create-post.

The Request-Response Cycle with Flask Der Request-Response-Zyklus mit Flask

Let's revisit the request-response cycle, now with Flask in the picture. Betrachten wir den Request-Response-Zyklus erneut, jetzt mit Flask im Bild.

User Action: You type http://127.0.0.1:5000/profile/Alice into your browser and press Enter. Benutzeraktion: Du gibst http://127.0.0.1:5000/profile/Alice in deinen Browser ein und drückst Enter.

HTTP Request: Your browser creates an HTTP GET request and sends it to the server at IP address 127.0.0.1 on port 5000. The request path is slash profile slash Alice. HTTP-Anfrage: Dein Browser erstellt eine HTTP-GET-Anfrage und sendet sie an den Server unter der IP-Adresse 127.0.0.1 auf Port 5000. Der Anfragepfad ist Schrägstrich profile Schrägstrich Alice.

Flask Receives Request: Your running Flask application, via Werkzeug, receives this HTTP request. Flask empfängt Anfrage: Deine laufende Flask-Anwendung empfängt über Werkzeug diese HTTP-Anfrage.

Routing: Flask looks at its routing rules. It finds the rule @app.route('/profile/<username>') which matches the path slash profile slash Alice. Routing: Flask schaut sich seine Routing-Regeln an. Es findet die Regel @app.route('/profile/<username>'), die dem Pfad Schrägstrich profile Schrägstrich Alice entspricht.

It also extracts the username part, Alice, from the URL. Es extrahiert auch den username-Teil, Alice, aus der URL.

View Function Called: Flask calls the associated view function, profile(), and passes the extracted username, Alice, as an argument to it: profile(username="Alice"). View-Funktion aufgerufen: Flask ruft die zugehörige View-Funktion, profile(), auf und übergibt den extrahierten Benutzernamen, Alice, als Argument an sie: profile(username="Alice").

View Function Processes: The profile function executes: return f"Hello, Alice! This is your profile page." It generates a string. View-Funktion verarbeitet: Die profile-Funktion führt aus: return f"Hallo, Alice! Das ist deine Profilseite." Sie generiert einen String.

HTTP Response Generated: Flask takes this string, wraps it in an HTTP response, setting appropriate headers like Content-Type: text/html, and prepares to send it back. HTTP-Antwort generiert: Flask nimmt diesen String, verpackt ihn in eine HTTP-Antwort, setzt entsprechende Header wie Content-Type: text/html und bereitet sich darauf vor, ihn zurückzuschicken.

Response Sent: Flask sends the HTTP response back to your browser. Antwort gesendet: Flask sendet die HTTP-Antwort zurück an deinen Browser.

Browser Renders: Your browser receives the response, sees it's HTML, or in this case text that it will render as HTML, and displays Hello, Alice! This is your profile page. Browser rendert: Dein Browser empfängt die Antwort, sieht dass es HTML ist, oder in diesem Fall Text, den er als HTML rendern wird, und zeigt Hallo, Alice! Das ist deine Profilseite an.

This cycle is fundamental to how web applications work. Dieser Zyklus ist grundlegend dafür, wie Webanwendungen funktionieren.

Dynamic Content with Templates Dynamischer Inhalt mit Templates

So far, our view functions have returned simple strings. Bisher haben unsere View-Funktionen einfache Strings zurückgegeben.

In real web applications, you'll want to return rich HTML pages. In echten Webanwendungen möchtest du reichhaltige HTML-Seiten zurückgeben.

Manually creating complex HTML strings in Python code can be messy and difficult to manage. Das manuelle Erstellen komplexer HTML-Strings in Python-Code kann unordentlich und schwierig zu verwalten sein.

This is where templating engines come in. Flask uses Jinja2 by default. Hier kommen Template-Engines ins Spiel. Flask verwendet standardmäßig Jinja2.

A template is essentially an HTML file with special placeholders for dynamic data. Ein Template ist im Wesentlichen eine HTML-Datei mit speziellen Platzhaltern für dynamische Daten.

Your Flask view function can load a template, fill in the placeholders with data, and then render it to produce the final HTML to send to the browser. Deine Flask-View-Funktion kann ein Template laden, die Platzhalter mit Daten füllen und es dann rendern, um das endgültige HTML zu produzieren, das an den Browser gesendet wird.

For example, you might have a template profile_template.html: Zum Beispiel könntest du ein Template profile_template.html haben:

<!DOCTYPE html> <html> <head> <title>User Profile</title> </head> <body> <h1>Hello, {{ user_name_in_template }}!</h1> <p>This is your profile page.</p> </body> </html> <!DOCTYPE html> <html> <head> <title>Benutzerprofil</title> </head> <body> <h1>Hallo, {{ user_name_in_template }}!</h1> <p>Das ist deine Profilseite.</p> </body> </html>

And your Flask view function would look something like this, this requires a bit more setup, like creating a templates folder, which we'll cover in class: Und deine Flask-View-Funktion würde etwa so aussehen, das erfordert etwas mehr Einrichtung, wie das Erstellen eines templates-Ordners, was wir im Unterricht behandeln werden:

from flask import Flask, render_template from flask import Flask, render_template

app = Flask(**name**) app = Flask(**name**)

@app.route('/user/<name>') def user_profile(name): @app.route('/user/<name>') def user_profile(name):

Instead of returning a string, we render a template Anstatt einen String zurückzugeben, rendern wir ein Template

We pass the name from the URL to the template as user_name_in_template Wir übergeben den Namen aus der URL an das Template als user_name_in_template

return render_template('profile_template.html', user_name_in_template=name) return render_template('profile_template.html', user_name_in_template=name)

if **name** == '**main**': app.run(debug=True) if **name** == '**main**': app.run(debug=True)

When someone visits slash user slash Bob, Flask would use profile_template.html, replace {{ user_name_in_template }} with Bob, and send the resulting HTML to the browser. Wenn jemand Schrägstrich user Schrägstrich Bob besucht, würde Flask profile_template.html verwenden, {{ user_name_in_template }} durch Bob ersetzen und das resultierende HTML an den Browser senden.

This makes it much easier to separate your application's logic, Python code, from its presentation, HTML. Das macht es viel einfacher, die Logik deiner Anwendung, Python-Code, von ihrer Präsentation, HTML, zu trennen.

We'll dive deeper into templates during the live session. Wir werden während der Live-Sitzung tiefer in Templates eintauchen.

That's it for the pre-class preparation! Das war's mit der Vorbereitung vor dem Unterricht!

By understanding these core concepts of server-side development and Flask, you'll be well-prepared for our hands-on session where we'll build more interesting web applications. Durch das Verstehen dieser Kernkonzepte der serverseitigen Entwicklung und Flask wirst du gut vorbereitet sein für unsere praktische Sitzung, wo wir interessantere Webanwendungen erstellen werden.

The slides for the live session can be viewed here. Try not to peek before class, spoilers inside! Die Folien für die Live-Sitzung können hier angesehen werden. Versuche nicht vor dem Unterricht zu spickeln, Spoiler drin!