Welcome! Before our live session on the Hypertext Transfer Protocol, HTTP, please go through this material. We'll explore how your browser requests web pages and how web servers respond. Understanding HTTP is fundamental to understanding how the web works. Willkommen! Bevor wir mit unserer Live-Session zum Hypertext Transfer Protocol, HTTP, beginnen, gehe bitte dieses Material durch. Wir werden erforschen, wie dein Browser Webseiten anfordert und wie Webserver antworten. HTTP zu verstehen ist grundlegend, um zu verstehen, wie das Web funktioniert.

What is the Application Layer? Was ist die Anwendungsschicht?

In our 5-layer network model, Physical, Datalink, Network, Transport, Application, the Application Layer is at the top. It's the layer where network applications, the software you interact with directly, create and interpret data. Think of web browsers, email clients, or file transfer programs. In unserem 5-Schichten-Netzwerkmodell, Physical, Datalink, Network, Transport, Application, ist die Anwendungsschicht ganz oben. Es ist die Schicht, in der Netzwerkanwendungen, die Software, mit der du direkt interagierst, Daten erstellen und interpretieren. Denke an Webbrowser, E-Mail-Clients oder Dateiübertragungsprogramme.

These applications need rules, or protocols, to communicate effectively across the network. HTTP is one of the most important application layer protocols. It's the foundation of the World Wide Web. Diese Anwendungen brauchen Regeln oder Protokolle, um effektiv über das Netzwerk zu kommunizieren. HTTP ist eines der wichtigsten Protokolle der Anwendungsschicht. Es ist die Grundlage des World Wide Web.

Introducing HTTP: The Language of the Web. Einführung in HTTP: Die Sprache des Web.

HTTP stands for Hypertext Transfer Protocol. At its core, it's a set of rules that defines how web clients, like your browser, request information from web servers, and how those servers respond. It's a text-based protocol, meaning the messages exchanged are human-readable text, although often quite structured. HTTP steht für Hypertext Transfer Protocol. Im Kern ist es eine Reihe von Regeln, die festlegen, wie Web-Clients, wie dein Browser, Informationen von Webservern anfordern und wie diese Server antworten. Es ist ein textbasiertes Protokoll, was bedeutet, dass die ausgetauschten Nachrichten menschenlesbarer Text sind, obwohl oft ziemlich strukturiert.

Key characteristics of HTTP: Hauptmerkmale von HTTP:

Client-Server Model: HTTP operates based on a request-response cycle between a client and a server. Client-Server-Modell: HTTP arbeitet auf Basis eines Anfrage-Antwort-Zyklus zwischen einem Client und einem Server.

Client: The entity initiating the request. Usually, this is your web browser, Chrome, Firefox, Safari, Edge, but it can also be other software like command-line tools, curl, or scripts. Client: Die Einheit, die die Anfrage initiiert. Normalerweise ist dies dein Webbrowser, Chrome, Firefox, Safari, Edge, aber es kann auch andere Software sein wie Kommandozeilen-Tools, curl, oder Skripte.

Server: The entity hosting the resource, like a web page, image, or data, and responding to the client's request. Examples include Apache, Nginx, or Microsoft IIS web server software running on powerful computers somewhere on the internet. Server: Die Einheit, die die Ressource hostet, wie eine Webseite, ein Bild oder Daten, und auf die Anfrage des Clients antwortet. Beispiele sind Apache, Nginx oder Microsoft IIS Webserver-Software, die auf leistungsstarken Computern irgendwo im Internet läuft.

Resources and URLs: HTTP is used to access resources on the web. A resource is anything that can be identified by a Uniform Resource Locator, URL. This could be an HTML document, a CSS stylesheet, a JavaScript file, an image, a video, or data from an API. Ressourcen und URLs: HTTP wird verwendet, um auf Ressourcen im Web zuzugreifen. Eine Ressource ist alles, was durch einen Uniform Resource Locator, URL, identifiziert werden kann. Dies könnte ein HTML-Dokument, ein CSS-Stylesheet, eine JavaScript-Datei, ein Bild, ein Video oder Daten von einer API sein.

A URL typically looks like this: http://www.example.com/path/to/resource?query=value#fragment Eine URL sieht typischerweise so aus: http://www.example.com/path/to/resource?query=value#fragment

http:// is the scheme, which is the protocol. https:// indicates HTTP secured with encryption, more on this later. http:// ist das Schema, also das Protokoll. https:// zeigt HTTP gesichert mit Verschlüsselung an, mehr dazu später.

www.example.com is the host or domain name, which resolves to an IP address via DNS, Domain Name System. www.example.com ist der Host oder Domainname, der über DNS, Domain Name System, zu einer IP-Adresse aufgelöst wird.

/path/to/resource is the path specifying the location of the resource on the server. /path/to/resource ist der Pfad, der den Speicherort der Ressource auf dem Server angibt.

?query=value is an optional query string used to pass parameters to the server. ?query=value ist ein optionaler Query-String, der verwendet wird, um Parameter an den Server zu übergeben.

#fragment is an optional fragment identifier, processed by the client, the browser, to navigate within the resource, for example, jump to a section of a page. #fragment ist ein optionaler Fragment-Identifikator, der vom Client, dem Browser, verarbeitet wird, um innerhalb der Ressource zu navigieren, zum Beispiel zu einem Abschnitt einer Seite zu springen.

Statelessness: This is a crucial concept. Each HTTP request from a client to a server is treated independently. The server does not store any information about previous requests from the same client by default. Zustandslosigkeit: Dies ist ein entscheidendes Konzept. Jede HTTP-Anfrage von einem Client an einen Server wird unabhängig behandelt. Der Server speichert standardmäßig keine Informationen über vorherige Anfragen desselben Clients.

If state, like knowing who is logged in, is needed, it's usually managed using other mechanisms like cookies or session data, which are built on top of HTTP. Wenn ein Zustand, wie zu wissen, wer eingeloggt ist, benötigt wird, wird er normalerweise über andere Mechanismen wie Cookies oder Session-Daten verwaltet, die auf HTTP aufbauen.

The HTTP Request-Response Cycle. Der HTTP-Anfrage-Antwort-Zyklus.

Client Sends Request: Your browser, the client, wants to fetch http://www.example.com/index.html. It constructs an HTTP request message and sends it to the server located at www.example.com, using the IP address obtained via DNS, over the transport layer, usually TCP on port 80 for HTTP, or port 443 for HTTPS. Client sendet Anfrage: Dein Browser, der Client, möchte http://www.example.com/index.html abrufen. Er erstellt eine HTTP-Anfrage-Nachricht und sendet sie an den Server bei www.example.com, unter Verwendung der über DNS erhaltenen IP-Adresse, über die Transportschicht, normalerweise TCP auf Port 80 für HTTP oder Port 443 für HTTPS.

Server Processes Request: The web server receives the request, identifies the requested resource, /index.html, processes any parameters, and determines the appropriate action. Server verarbeitet Anfrage: Der Webserver empfängt die Anfrage, identifiziert die angeforderte Ressource, /index.html, verarbeitet alle Parameter und bestimmt die geeignete Aktion.

Server Sends Response: The server constructs an HTTP response message, including the requested resource, if found and accessible, or an error message, and sends it back to the client. Server sendet Antwort: Der Server erstellt eine HTTP-Antwort-Nachricht, einschließlich der angeforderten Ressource, falls gefunden und zugänglich, oder einer Fehlermeldung, und sendet sie zurück an den Client.

Client Receives Response: Your browser receives the response, interprets it, for example, renders the HTML, and displays the result. If the HTML page references other resources, images, CSS, JavaScript, the browser will initiate separate HTTP requests for each of those. Client empfängt Antwort: Dein Browser empfängt die Antwort, interpretiert sie, zum Beispiel rendert er das HTML, und zeigt das Ergebnis an. Wenn die HTML-Seite auf andere Ressourcen verweist, Bilder, CSS, JavaScript, wird der Browser separate HTTP-Anfragen für jede dieser Ressourcen starten.

Anatomy of an HTTP Message. Anatomie einer HTTP-Nachricht.

Both requests and responses have a similar structure: Sowohl Anfragen als auch Antworten haben eine ähnliche Struktur:

Start Line: Request Line contains the HTTP Method, the Request Target, usually the path from the URL, and the HTTP Version. Example: GET /index.html HTTP/1.1 Startzeile: Die Anfragezeile enthält die HTTP-Methode, das Anfrageziel, normalerweise den Pfad aus der URL, und die HTTP-Version. Beispiel: GET /index.html HTTP/1.1

Status Line contains the HTTP Version, a Status Code, and a Reason Phrase. Example: HTTP/1.1 200 OK Die Statuszeile enthält die HTTP-Version, einen Statuscode und eine Begründungsphrase. Beispiel: HTTP/1.1 200 OK

Headers: Zero or more lines providing metadata about the request or response. Each header is a name-value pair, separated by a colon. Header: Null oder mehr Zeilen, die Metadaten über die Anfrage oder Antwort liefern. Jeder Header ist ein Name-Wert-Paar, getrennt durch einen Doppelpunkt.

Examples: Host: www.example.com, required in HTTP/1.1 requests. Beispiele: Host: www.example.com, erforderlich in HTTP/1.1-Anfragen.

User-Agent: Mozilla/5.0, identifies the client software. User-Agent: Mozilla/5.0, identifiziert die Client-Software.

Accept: text/html, tells the server what kind of content the client prefers. Accept: text/html, teilt dem Server mit, welche Art von Inhalt der Client bevorzugt.

Content-Type: text/html; charset=UTF-8, in a response, tells the client the type of the content in the body. Content-Type: text/html; charset=UTF-8, in einer Antwort, teilt dem Client den Typ des Inhalts im Body mit.

Content-Length: 1234, specifies the size of the message body in bytes. Content-Length: 1234, gibt die Größe des Nachrichtenkörpers in Bytes an.

Empty Line: A single blank line, CRLF, Carriage Return Line Feed, separates the headers from the message body. Leerzeile: Eine einzelne Leerzeile, CRLF, Carriage Return Line Feed, trennt die Header vom Nachrichtenkörper.

Message Body, Optional: Contains the actual data being transferred. In a request, like a POST request, this might be form data or JSON data. In a response, this is often the HTML content, image data, etc. GET requests typically don't have a body. Nachrichtenkörper, Optional: Enthält die tatsächlich übertragenen Daten. In einer Anfrage, wie einer POST-Anfrage, könnten dies Formulardaten oder JSON-Daten sein. In einer Antwort ist dies oft der HTML-Inhalt, Bilddaten usw. GET-Anfragen haben normalerweise keinen Body.

HTTP Methods, or Verbs. HTTP-Methoden oder Verben.

The HTTP method indicates the desired action to be performed on the resource. Common methods include: Die HTTP-Methode gibt die gewünschte Aktion an, die auf der Ressource ausgeführt werden soll. Häufige Methoden sind:

GET: Requests a representation of the specified resource. This is the most common method, used when you click a link or type a URL in your browser. GET requests should only retrieve data and have no other effect. They are idempotent and safe. GET: Fordert eine Darstellung der angegebenen Ressource an. Dies ist die häufigste Methode, die verwendet wird, wenn du auf einen Link klickst oder eine URL in deinem Browser eingibst. GET-Anfragen sollten nur Daten abrufen und keine andere Wirkung haben. Sie sind idempotent und sicher.

POST: Submits data to be processed to the specified resource, for example, submitting a web form, uploading a file, sending JSON data to an API. POST requests often result in a change in state on the server. POST: Übermittelt Daten zur Verarbeitung an die angegebene Ressource, zum Beispiel das Absenden eines Webformulars, das Hochladen einer Datei, das Senden von JSON-Daten an eine API. POST-Anfragen führen oft zu einer Zustandsänderung auf dem Server.

PUT: Replaces the current representation of the target resource with the request payload. PUT: Ersetzt die aktuelle Darstellung der Zielressource durch die Anfrage-Nutzlast.

DELETE: Deletes the specified resource. DELETE: Löscht die angegebene Ressource.

HEAD: Similar to GET, but asks for the response headers only, without the message body. Useful for checking if a resource exists or getting its metadata without downloading it. HEAD: Ähnlich wie GET, aber fragt nur nach den Antwort-Headern, ohne den Nachrichtenkörper. Nützlich, um zu prüfen, ob eine Ressource existiert oder ihre Metadaten zu erhalten, ohne sie herunterzuladen.

OPTIONS: Requests information about the communication options available for the target resource, for example, which methods are supported. OPTIONS: Fordert Informationen über die verfügbaren Kommunikationsoptionen für die Zielressource an, zum Beispiel welche Methoden unterstützt werden.

PATCH: Applies partial modifications to a resource. PATCH: Wendet teilweise Änderungen auf eine Ressource an.

HTTP Status Codes. HTTP-Statuscodes.

The status code in the response indicates the outcome of the request. They are grouped into categories: Der Statuscode in der Antwort zeigt das Ergebnis der Anfrage an. Sie sind in Kategorien gruppiert:

1xx, Informational: Request received, continuing process. Rarely seen by users. 1xx, Informational: Anfrage empfangen, Prozess wird fortgesetzt. Von Benutzern selten gesehen.

2xx, Successful: The action was successfully received, understood, and accepted. 2xx, Successful: Die Aktion wurde erfolgreich empfangen, verstanden und akzeptiert.

200 OK: Standard success response. 200 OK: Standard-Erfolgsantwort.

201 Created: The request has been fulfilled and resulted in a new resource being created. 201 Created: Die Anfrage wurde erfüllt und führte zur Erstellung einer neuen Ressource.

204 No Content: The server successfully processed the request but is not returning any content. 204 No Content: Der Server hat die Anfrage erfolgreich verarbeitet, gibt aber keinen Inhalt zurück.

3xx, Redirection: Further action needs to be taken by the client to complete the request. 3xx, Redirection: Weitere Aktionen müssen vom Client ausgeführt werden, um die Anfrage abzuschließen.

301 Moved Permanently: The requested resource has been permanently moved to a new URL, given in the Location header. 301 Moved Permanently: Die angeforderte Ressource wurde dauerhaft zu einer neuen URL verschoben, die im Location-Header angegeben ist.

302 Found, or 307 Temporary Redirect: The resource is temporarily at a different URL. 302 Found oder 307 Temporary Redirect: Die Ressource befindet sich vorübergehend unter einer anderen URL.

4xx, Client Error: The request contains bad syntax or cannot be fulfilled. 4xx, Client Error: Die Anfrage enthält fehlerhafte Syntax oder kann nicht erfüllt werden.

400 Bad Request: The server could not understand the request due to invalid syntax. 400 Bad Request: Der Server konnte die Anfrage aufgrund ungültiger Syntax nicht verstehen.

401 Unauthorized: Authentication is required and has failed or has not yet been provided. 401 Unauthorized: Authentifizierung ist erforderlich und ist fehlgeschlagen oder wurde noch nicht bereitgestellt.

403 Forbidden: The server understood the request, but refuses to authorize it. You don't have permission. 403 Forbidden: Der Server hat die Anfrage verstanden, weigert sich aber, sie zu autorisieren. Du hast keine Berechtigung.

404 Not Found: The server cannot find the requested resource. This is one of the most famous codes! 404 Not Found: Der Server kann die angeforderte Ressource nicht finden. Dies ist einer der bekanntesten Codes!

5xx, Server Error: The server failed to fulfill an apparently valid request. 5xx, Server Error: Der Server konnte eine scheinbar gültige Anfrage nicht erfüllen.

500 Internal Server Error: A generic error message, given when an unexpected condition was encountered. 500 Internal Server Error: Eine allgemeine Fehlermeldung, die ausgegeben wird, wenn eine unerwartete Bedingung aufgetreten ist.

503 Service Unavailable: The server is not ready to handle the request, for example, down for maintenance or overloaded. 503 Service Unavailable: Der Server ist nicht bereit, die Anfrage zu bearbeiten, zum Beispiel wegen Wartung oder Überlastung.

Think about it. Denk darüber nach.

Why is it useful to have different methods like GET and POST? Why not just use GET for everything and put data in the URL? Warum ist es nützlich, verschiedene Methoden wie GET und POST zu haben? Warum nicht einfach GET für alles verwenden und Daten in die URL einfügen?

Try it yourself. Probiere es selbst aus.

Most modern web browsers have built-in Developer Tools that let you inspect network traffic. Die meisten modernen Webbrowser haben eingebaute Entwickler-Tools, mit denen du den Netzwerkverkehr untersuchen kannst.

Open your web browser, Chrome or Firefox recommended. Right-click anywhere on a web page, like google.com, and select Inspect or Inspect Element. Öffne deinen Webbrowser, Chrome oder Firefox empfohlen. Klicke mit der rechten Maustaste irgendwo auf einer Webseite, wie google.com, und wähle Inspect oder Inspect Element.

Find and click on the Network tab in the developer tools panel. Make sure recording is enabled, usually a red or grey circle icon. You might need to refresh the page, Command plus R or F5. Finde und klicke auf den Network-Tab im Entwickler-Tools-Panel. Stelle sicher, dass die Aufnahme aktiviert ist, normalerweise ein rotes oder graues Kreissymbol. Du musst möglicherweise die Seite aktualisieren, Command plus R oder F5.

You'll see a list of requests made by the browser to load the page. Click on the first request, usually the main HTML document. Du wirst eine Liste von Anfragen sehen, die der Browser zum Laden der Seite gestellt hat. Klicke auf die erste Anfrage, normalerweise das Haupt-HTML-Dokument.

Look at the Headers section for that request. Can you identify the Request Method, for example, GET? The Status Code, for example, 200? The User-Agent header? The Content-Type header in the response headers? Schau dir den Headers-Bereich für diese Anfrage an. Kannst du die Request Method identifizieren, zum Beispiel GET? Den Status Code, zum Beispiel 200? Den User-Agent-Header? Den Content-Type-Header in den Antwort-Headern?

Don't worry about understanding everything you see yet. The goal is just to get familiar with where to find this information. Mach dir keine Sorgen, wenn du noch nicht alles verstehst, was du siehst. Das Ziel ist nur, dich damit vertraut zu machen, wo du diese Informationen findest.

HTTP vs. HTTPS. HTTP vs. HTTPS.

You've likely seen https:// in URLs more often than http://. HTTPS stands for HTTP Secure. It's essentially the standard HTTP protocol layered on top of an encryption layer, usually TLS, Transport Layer Security, or its predecessor SSL, Secure Sockets Layer. Du hast wahrscheinlich https:// in URLs öfter gesehen als http://. HTTPS steht für HTTP Secure. Es ist im Wesentlichen das Standard-HTTP-Protokoll, das auf einer Verschlüsselungsschicht aufgebaut ist, normalerweise TLS, Transport Layer Security, oder seinem Vorgänger SSL, Secure Sockets Layer.

HTTP: Transmits data in plain text. Anyone intercepting the traffic, for example, on the same Wi-Fi network, can read it. HTTP: Überträgt Daten im Klartext. Jeder, der den Datenverkehr abfängt, zum Beispiel im selben WLAN-Netzwerk, kann ihn lesen.

HTTPS: Encrypts the data exchanged between the client and server. This provides: HTTPS: Verschlüsselt die zwischen Client und Server ausgetauschten Daten. Dies bietet:

Confidentiality: Protects against eavesdropping. Vertraulichkeit: Schützt vor Abhören.

Integrity: Ensures the data hasn't been tampered with during transit. Integrität: Stellt sicher, dass die Daten während der Übertragung nicht manipuliert wurden.

Authentication: Often involves verifying the server's identity using digital certificates, helping prevent man-in-the-middle attacks. Authentifizierung: Beinhaltet oft die Überprüfung der Identität des Servers mithilfe digitaler Zertifikate und hilft, Man-in-the-Middle-Angriffe zu verhindern.

For security reasons, especially when sensitive data like passwords or credit card numbers are involved, HTTPS is essential and is now standard practice for almost all websites. Aus Sicherheitsgründen, besonders wenn sensible Daten wie Passwörter oder Kreditkartennummern beteiligt sind, ist HTTPS unerlässlich und ist jetzt Standardpraxis für fast alle Websites.

We'll delve deeper into encryption and certificates in later modules. For now, understand that HTTPS is HTTP with a crucial security layer added via the Transport Layer. Wir werden in späteren Modulen tiefer in Verschlüsselung und Zertifikate eintauchen. Verstehe vorerst, dass HTTPS HTTP mit einer entscheidenden Sicherheitsschicht ist, die über die Transportschicht hinzugefügt wird.

That concludes the pre-class reading on HTTP basics. We'll explore these concepts further with live demonstrations in our session! Damit schließen wir die Vorab-Lektüre zu den HTTP-Grundlagen ab. Wir werden diese Konzepte in unserer Session mit Live-Demonstrationen weiter erforschen!

The slides for the live session can be viewed here: https://gamma.app/docs/Networking-5-Application-Layer-HTTP-07k96b3eps4k76r?mode=doc. Try not to peek before class, spoilers inside! Die Folien für die Live-Session können hier angesehen werden: https://gamma.app/docs/Networking-5-Application-Layer-HTTP-07k96b3eps4k76r?mode=doc. Versuche nicht vor dem Unterricht zu spicken, es sind Spoiler drin!