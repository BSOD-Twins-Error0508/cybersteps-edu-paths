Welcome to the pre-class preparation for our upcoming session on APIs and Authentication! Willkommen zur Vorbereitung für unsere kommende Sitzung über APIs und Authentifizierung!

This material will provide you with the foundational knowledge needed to understand how different software systems communicate and how we ensure those communications are secure and authorized. Dieses Material wird dir das grundlegende Wissen vermitteln, das du brauchst, um zu verstehen, wie verschiedene Softwaresysteme kommunizieren und wie wir sicherstellen, dass diese Kommunikation sicher und autorisiert ist.

What is an API? Was ist eine API?

API stands for Application Programming Interface. API steht für Application Programming Interface, also Anwendungsprogrammierschnittstelle.

At its core, an API is a set of rules and protocols that allows one software application to interact with another. Im Kern ist eine API eine Reihe von Regeln und Protokollen, die es einer Softwareanwendung ermöglichen, mit einer anderen zu interagieren.

Think of it as a contract between two pieces of software: one offers services, the API provider, and the other consumes those services, the API client. Stell dir das als einen Vertrag zwischen zwei Softwarekomponenten vor: Eine bietet Dienste an, der API-Anbieter, und die andere nutzt diese Dienste, der API-Client.

Imagine you're at a restaurant. Stell dir vor, du bist in einem Restaurant.

You, the client, want food. Du, der Kunde, möchtest Essen.

The kitchen, the provider, can prepare it. Die Küche, der Anbieter, kann es zubereiten.

You don't go into the kitchen yourself and start cooking. Du gehst nicht selbst in die Küche und fängst an zu kochen.

Instead, you interact with a waiter, the API. Stattdessen interagierst du mit einem Kellner, der API.

The waiter takes your order, a request, communicates it to the kitchen, and then brings your food back, a response. Der Kellner nimmt deine Bestellung auf, eine Anfrage, übermittelt sie an die Küche und bringt dann dein Essen zurück, eine Antwort.

The menu acts as a guide to what you can order and what to expect, similar to how API documentation tells developers what services are available and how to use them. Die Speisekarte dient als Leitfaden dafür, was du bestellen kannst und was du erwarten darfst, ähnlich wie API-Dokumentation Entwicklern mitteilt, welche Dienste verfügbar sind und wie man sie nutzt.

In the context of web development, we often deal with Web APIs. Im Kontext der Webentwicklung haben wir es oft mit Web-APIs zu tun.

These APIs are accessed over the web using the HTTP protocol. Auf diese APIs wird über das Web mithilfe des HTTP-Protokolls zugegriffen.

They allow different web services, mobile apps, or even other servers to communicate and exchange data. Sie ermöglichen es verschiedenen Webdiensten, mobilen Apps oder sogar anderen Servern, zu kommunizieren und Daten auszutauschen.

For example, when a weather app on your phone shows you the current temperature, it's likely fetching that data from a weather service's API. Wenn zum Beispiel eine Wetter-App auf deinem Handy dir die aktuelle Temperatur anzeigt, holt sie diese Daten wahrscheinlich von der API eines Wetterdienstes.

When you log in to a website using your Google account, that's also an API in action, Google's authentication API. Wenn du dich auf einer Webseite mit deinem Google-Konto anmeldest, ist das auch eine API in Aktion, Googles Authentifizierungs-API.

Why are APIs important? Warum sind APIs wichtig?

APIs are crucial for modern software development for several reasons. APIs sind aus mehreren Gründen entscheidend für die moderne Softwareentwicklung.

Modularity: APIs allow complex applications to be broken down into smaller, independent services. Modularität: APIs ermöglichen es, komplexe Anwendungen in kleinere, unabhängige Dienste aufzuteilen.

Each service can be developed, deployed, and scaled independently. Jeder Dienst kann unabhängig entwickelt, bereitgestellt und skaliert werden.

Reusability: Once an API is created, its functionality can be reused by multiple applications. Wiederverwendbarkeit: Sobald eine API erstellt wurde, kann ihre Funktionalität von mehreren Anwendungen wiederverwendet werden.

For instance, a payment processing API can be used by many different e-commerce websites. Zum Beispiel kann eine Zahlungsabwicklungs-API von vielen verschiedenen E-Commerce-Webseiten genutzt werden.

Integration: APIs enable different systems, built with different technologies, to connect and share data. Integration: APIs ermöglichen es verschiedenen Systemen, die mit unterschiedlichen Technologien erstellt wurden, sich zu verbinden und Daten auszutauschen.

This is vital for creating rich, interconnected experiences. Das ist entscheidend für die Schaffung reichhaltiger, vernetzter Erfahrungen.

Abstraction: APIs hide the underlying complexity of a system. Abstraktion: APIs verbergen die zugrunde liegende Komplexität eines Systems.

A client application doesn't need to know how the provider's service is implemented; it only needs to know how to interact with the API. Eine Client-Anwendung muss nicht wissen, wie der Dienst des Anbieters implementiert ist, sie muss nur wissen, wie man mit der API interagiert.

Innovation: By exposing data and functionality through APIs, companies can allow third-party developers to build new and innovative applications on top of their platforms. Innovation: Indem Unternehmen Daten und Funktionalität durch APIs zugänglich machen, können sie Drittentwicklern ermöglichen, neue und innovative Anwendungen auf ihren Plattformen aufzubauen.

Common API Architectural Styles: REST. Gängige API-Architekturstile: REST.

While there are several ways to design APIs, one of the most prevalent styles for web APIs is REST, Representational State Transfer. Obwohl es mehrere Möglichkeiten gibt, APIs zu entwerfen, ist einer der am weitesten verbreiteten Stile für Web-APIs REST, Representational State Transfer.

REST is an architectural style, not a strict protocol, that uses standard HTTP methods to perform operations on resources. REST ist ein Architekturstil, kein striktes Protokoll, der Standard-HTTP-Methoden verwendet, um Operationen auf Ressourcen auszuführen.

Key principles of REST: Resources. Grundprinzipien von REST: Ressourcen.

Everything in a REST API is considered a resource. Alles in einer REST-API wird als Ressource betrachtet.

A resource could be a user, a product, an order, or any other piece of information. Eine Ressource kann ein Benutzer, ein Produkt, eine Bestellung oder jede andere Information sein.

Resources are identified by URLs, Uniform Resource Locators, like https://api.example.com/users/123 or https://api.example.com/products. Ressourcen werden durch URLs identifiziert, Uniform Resource Locators, wie https://api.example.com/users/123 oder https://api.example.com/products.

HTTP Methods: RESTful APIs use standard HTTP methods to perform actions on these resources. HTTP-Methoden: RESTful APIs verwenden Standard-HTTP-Methoden, um Aktionen auf diesen Ressourcen auszuführen.

GET: Retrieve a resource, for example, get user details. GET: Eine Ressource abrufen, zum Beispiel Benutzerdetails erhalten.

POST: Create a new resource, for example, create a new user. POST: Eine neue Ressource erstellen, zum Beispiel einen neuen Benutzer anlegen.

PUT: Update an existing resource entirely, for example, update all details of a user. PUT: Eine bestehende Ressource vollständig aktualisieren, zum Beispiel alle Details eines Benutzers aktualisieren.

PATCH: Partially update an existing resource, for example, update only the email address of a user. PATCH: Eine bestehende Ressource teilweise aktualisieren, zum Beispiel nur die E-Mail-Adresse eines Benutzers aktualisieren.

DELETE: Remove a resource, for example, delete a user. DELETE: Eine Ressource entfernen, zum Beispiel einen Benutzer löschen.

Statelessness: Each request from a client to a server must contain all the information needed to understand and process the request. Zustandslosigkeit: Jede Anfrage von einem Client an einen Server muss alle Informationen enthalten, die benötigt werden, um die Anfrage zu verstehen und zu verarbeiten.

The server does not store any client context between requests. Der Server speichert keinen Client-Kontext zwischen den Anfragen.

If state is needed, like a user's session, it's managed on the client side and sent with each relevant request. Wenn ein Zustand benötigt wird, wie die Sitzung eines Benutzers, wird er auf der Client-Seite verwaltet und mit jeder relevanten Anfrage gesendet.

Client-Server Architecture: The client, which consumes the API, and the server, which provides the API, are separate. Client-Server-Architektur: Der Client, der die API nutzt, und der Server, der die API bereitstellt, sind getrennt.

This separation allows them to evolve independently. Diese Trennung ermöglicht es ihnen, sich unabhängig voneinander weiterzuentwickeln.

Uniform Interface: REST APIs have a consistent way of interacting, regardless of the specific resource. Einheitliche Schnittstelle: REST-APIs haben eine konsistente Art der Interaktion, unabhängig von der spezifischen Ressource.

This usually involves using standard HTTP methods, URIs to identify resources, and a standard media type, like JSON, for exchanging data. Das beinhaltet normalerweise die Verwendung von Standard-HTTP-Methoden, URIs zur Identifizierung von Ressourcen und einem Standardmedientyp wie JSON für den Datenaustausch.

API Requests and Responses. API-Anfragen und Antworten.

When a client communicates with a web API, it sends an HTTP request, and the server replies with an HTTP response. Wenn ein Client mit einer Web-API kommuniziert, sendet er eine HTTP-Anfrage, und der Server antwortet mit einer HTTP-Antwort.

You've encountered these in the HTTP lesson, but let's recap in the API context. Du bist diesen bereits in der HTTP-Lektion begegnet, aber lass uns das im API-Kontext noch einmal zusammenfassen.

Request: URL, or Endpoint, specifies the resource the client wants to interact with, for example, /users or /products/789. Anfrage: URL oder Endpunkt gibt die Ressource an, mit der der Client interagieren möchte, zum Beispiel /users oder /products/789.

Method: The HTTP verb, GET, POST, PUT, DELETE, etc., indicating the desired action. Methode: Das HTTP-Verb, GET, POST, PUT, DELETE usw., das die gewünschte Aktion angibt.

Headers: Additional information sent with the request, such as the content type of the data being sent, Content-Type: application/json, authentication information, Authorization: Bearer token, or caching directives. Header: Zusätzliche Informationen, die mit der Anfrage gesendet werden, wie der Inhaltstyp der gesendeten Daten, Content-Type: application/json, Authentifizierungsinformationen, Authorization: Bearer Token, oder Caching-Anweisungen.

Body, or Payload: Data sent to the server, typically for POST, PUT, or PATCH requests. Body oder Payload: Daten, die an den Server gesendet werden, typischerweise für POST-, PUT- oder PATCH-Anfragen.

This is often in JSON format. Dies ist oft im JSON-Format.

GET and DELETE requests usually don't have a body. GET- und DELETE-Anfragen haben normalerweise keinen Body.

Response: Status Code: A three-digit number indicating the outcome of the request, for example, 200 OK, 201 Created, 400 Bad Request, 401 Unauthorized, 404 Not Found, 500 Internal Server Error. Antwort: Statuscode: Eine dreistellige Zahl, die das Ergebnis der Anfrage anzeigt, zum Beispiel 200 OK, 201 Created, 400 Bad Request, 401 Unauthorized, 404 Not Found, 500 Internal Server Error.

Headers: Additional information sent with the response, such as the content type of the data being returned, Content-Type: application/json, caching information, or rate limiting details. Header: Zusätzliche Informationen, die mit der Antwort gesendet werden, wie der Inhaltstyp der zurückgegebenen Daten, Content-Type: application/json, Caching-Informationen oder Ratenbegrenzungsdetails.

Body, or Payload: The data returned by the server, often in JSON format. Body oder Payload: Die vom Server zurückgegebenen Daten, oft im JSON-Format.

For example, a GET request to /users/123 might return a JSON object with the user's details. Zum Beispiel könnte eine GET-Anfrage an /users/123 ein JSON-Objekt mit den Benutzerdetails zurückgeben.

Data Formats in APIs: JSON. Datenformate in APIs: JSON.

APIs need a standard way to structure the data they exchange. APIs benötigen eine Standardmethode, um die Daten zu strukturieren, die sie austauschen.

While XML, eXtensible Markup Language, was historically common, JSON, JavaScript Object Notation, is now the de facto standard for most web APIs. Während XML, eXtensible Markup Language, historisch gesehen üblich war, ist JSON, JavaScript Object Notation, jetzt der De-facto-Standard für die meisten Web-APIs.

JSON is a lightweight, human-readable data interchange format. JSON ist ein leichtgewichtiges, menschenlesbares Datenaustauschformat.

It's easy for humans to read and write, and easy for machines to parse and generate. Es ist leicht für Menschen zu lesen und zu schreiben und leicht für Maschinen zu verarbeiten und zu generieren.

It represents data as key-value pairs, like Python dictionaries, and ordered lists, like Python lists. Es repräsentiert Daten als Schlüssel-Wert-Paare, wie Python-Dictionaries, und geordnete Listen, wie Python-Listen.

Example of JSON data representing a user: id: 123, username: cyber_student, email: student@example.com, isActive: true, roles: student, editor. Beispiel für JSON-Daten, die einen Benutzer repräsentieren: id: 123, username: cyber_student, email: student@example.com, isActive: true, roles: student, editor.

Think about it: Why do you think JSON has become more popular than XML for web APIs? Denk darüber nach: Warum glaubst du, ist JSON beliebter geworden als XML für Web-APIs?

Consider factors like readability, verbosity, and ease of use with JavaScript. Berücksichtige Faktoren wie Lesbarkeit, Ausführlichkeit und einfache Nutzung mit JavaScript.

Introduction to Authentication and Authorization. Einführung in Authentifizierung und Autorisierung.

When an API exposes data or functionality, it's often crucial to control who can access it and what they can do. Wenn eine API Daten oder Funktionalität zugänglich macht, ist es oft entscheidend zu kontrollieren, wer darauf zugreifen kann und was sie tun können.

This is where authentication and authorization come in. Hier kommen Authentifizierung und Autorisierung ins Spiel.

What is Authentication? Was ist Authentifizierung?

Authentication is the process of verifying the identity of a user, application, or device. Authentifizierung ist der Prozess der Überprüfung der Identität eines Benutzers, einer Anwendung oder eines Geräts.

It answers the question: Who are you? Sie beantwortet die Frage: Wer bist du?

Before an API grants access to its resources, it needs to be sure that the requester is who they claim to be. Bevor eine API Zugriff auf ihre Ressourcen gewährt, muss sie sicher sein, dass der Anfragende derjenige ist, der er vorgibt zu sein.

Think of it like showing your ID card to a security guard before entering a building. Stell dir das so vor, als würdest du einem Sicherheitsbeamten deinen Ausweis zeigen, bevor du ein Gebäude betrittst.

The guard checks your ID to confirm you are a legitimate person allowed to request entry. Der Wachmann überprüft deinen Ausweis, um zu bestätigen, dass du eine legitime Person bist, die Einlass beantragen darf.

Why is Authentication needed for APIs? Warum wird Authentifizierung für APIs benötigt?

Protecting Sensitive Data: APIs often handle personal, financial, or confidential information. Schutz sensibler Daten: APIs verarbeiten oft persönliche, finanzielle oder vertrauliche Informationen.

Authentication ensures that only legitimate users can access this data. Authentifizierung stellt sicher, dass nur legitime Benutzer auf diese Daten zugreifen können.

Controlling Access to Functionality: Some API operations, like creating or deleting data, should only be performed by authenticated and authorized users. Kontrolle des Zugriffs auf Funktionalität: Einige API-Operationen, wie das Erstellen oder Löschen von Daten, sollten nur von authentifizierten und autorisierten Benutzern durchgeführt werden.

Tracking Usage: Authentication allows API providers to track who is using their API, which can be important for billing, rate limiting, preventing abuse, and analytics. Verfolgung der Nutzung: Authentifizierung ermöglicht es API-Anbietern zu verfolgen, wer ihre API nutzt, was wichtig sein kann für Abrechnung, Ratenbegrenzung, Missbrauchsverhinderung und Analysen.

Personalization: Once a user is authenticated, the API can provide a personalized experience or data specific to that user. Personalisierung: Sobald ein Benutzer authentifiziert ist, kann die API eine personalisierte Erfahrung oder benutzerspezifische Daten bereitstellen.

Common API Authentication Methods. Gängige API-Authentifizierungsmethoden.

There are various methods to authenticate requests to an API. Es gibt verschiedene Methoden, um Anfragen an eine API zu authentifizieren.

Here are a few common ones. Hier sind einige gängige.

API Keys: How it works: The client is issued a unique string, the API key. API-Schlüssel: So funktioniert es: Der Client erhält eine eindeutige Zeichenfolge, den API-Schlüssel.

The client includes this key in its requests, often in an HTTP header like X-API-Key or as a query parameter. Der Client fügt diesen Schlüssel in seine Anfragen ein, oft in einem HTTP-Header wie X-API-Key oder als Query-Parameter.

The server validates the key to authenticate the request. Der Server validiert den Schlüssel, um die Anfrage zu authentifizieren.

Pros: Simple to implement and use. Vorteile: Einfach zu implementieren und zu nutzen.

Cons: Keys are often long-lived. Nachteile: Schlüssel sind oft langlebig.

If a key is compromised, it can be used by an attacker until revoked. Wenn ein Schlüssel kompromittiert wird, kann er von einem Angreifer bis zum Widerruf genutzt werden.

They don't inherently identify a specific user but rather a specific client application. Sie identifizieren nicht grundsätzlich einen bestimmten Benutzer, sondern vielmehr eine bestimmte Client-Anwendung.

HTTP Basic Authentication: How it works: The client sends a username and password in the Authorization HTTP header. HTTP Basic Authentication: So funktioniert es: Der Client sendet einen Benutzernamen und ein Passwort im Authorization-HTTP-Header.

The value is the word Basic followed by a space and a base64-encoded string of username:password. Der Wert ist das Wort Basic gefolgt von einem Leerzeichen und einer base64-kodierten Zeichenfolge von username:password.

Pros: Simple, widely supported. Vorteile: Einfach, weit verbreitet unterstützt.

Cons: Sends credentials with every request. Nachteile: Sendet Anmeldedaten mit jeder Anfrage.

Must be used over HTTPS to prevent credentials from being intercepted as base64 is easily decoded. Muss über HTTPS verwendet werden, um zu verhindern, dass Anmeldedaten abgefangen werden, da base64 leicht dekodiert werden kann.

Not ideal for browser-based clients as it often triggers a native browser login popup. Nicht ideal für browserbasierte Clients, da es oft ein natives Browser-Login-Popup auslöst.

Bearer Tokens, for example, OAuth 2.0, JWT: How it works: The client first obtains a token, the bearer token, from an authentication server after successfully authenticating, for example, with a username/password, or through a third-party provider like Google. Bearer Tokens, zum Beispiel OAuth 2.0, JWT: So funktioniert es: Der Client erhält zunächst ein Token, das Bearer Token, von einem Authentifizierungsserver, nachdem er sich erfolgreich authentifiziert hat, zum Beispiel mit Benutzername/Passwort oder über einen Drittanbieter wie Google.

The client then includes this token in the Authorization header of its API requests, prefixed with Bearer. Der Client fügt dann dieses Token in den Authorization-Header seiner API-Anfragen ein, mit dem Präfix Bearer.

Example: Authorization: Bearer your_token_here. Beispiel: Authorization: Bearer your_token_here.

OAuth 2.0 is an authorization framework that enables third-party applications to obtain limited access to an HTTP service, either on behalf of a resource owner or by allowing the third-party application to obtain access on its own behalf. OAuth 2.0 ist ein Autorisierungsframework, das es Drittanwendungen ermöglicht, begrenzten Zugriff auf einen HTTP-Dienst zu erhalten, entweder im Namen eines Ressourcenbesitzers oder indem die Drittanwendung selbst Zugriff erhält.

It often involves tokens. Es beinhaltet oft Tokens.

JWT, JSON Web Token, is a compact, URL-safe means of representing claims to be transferred between two parties. JWT, JSON Web Token, ist ein kompaktes, URL-sicheres Mittel zur Darstellung von Ansprüchen, die zwischen zwei Parteien übertragen werden.

JWTs are often used as bearer tokens. JWTs werden oft als Bearer Tokens verwendet.

They are digitally signed, and can be encrypted, and contain claims, pieces of information, about the user and the token itself, for example, expiration time. Sie sind digital signiert, können verschlüsselt werden und enthalten Claims, Informationsstücke, über den Benutzer und das Token selbst, zum Beispiel Ablaufzeit.

Pros: More secure than Basic Auth as credentials aren't sent with every request. Vorteile: Sicherer als Basic Auth, da Anmeldedaten nicht mit jeder Anfrage gesendet werden.

Tokens can be short-lived and have specific scopes, or permissions. Tokens können kurzlebig sein und spezifische Bereiche oder Berechtigungen haben.

JWTs are self-contained and can carry user information, reducing the need for database lookups on the server. JWTs sind in sich geschlossen und können Benutzerinformationen enthalten, was die Notwendigkeit von Datenbankabfragen auf dem Server reduziert.

Cons: More complex to implement initially. Nachteile: Anfangs komplexer zu implementieren.

Token management, storage, expiry, revocation, needs careful handling. Token-Verwaltung, Speicherung, Ablauf, Widerruf, erfordert sorgfältige Handhabung.

Try it yourself: Open your browser's developer tools, usually by pressing F12 or right-clicking and selecting Inspect. Probiere es selbst aus: Öffne die Entwicklertools deines Browsers, normalerweise durch Drücken von F12 oder Rechtsklick und Auswahl von Untersuchen.

Go to the Network tab. Gehe zum Netzwerk-Tab.

Now, visit a website you log into, like a social media site or a news site with a login. Besuche jetzt eine Webseite, auf der du dich anmeldest, wie eine Social-Media-Seite oder eine Nachrichtenseite mit Login.

Perform a login. Führe eine Anmeldung durch.

Observe the network requests. Beobachte die Netzwerkanfragen.

Can you identify any requests that seem related to authentication? Kannst du Anfragen identifizieren, die mit Authentifizierung zusammenhängen?

Look at their headers. Schau dir ihre Header an.

Do you see an Authorization header? Siehst du einen Authorization-Header?

What kind of value does it have, if any? Welche Art von Wert hat er, falls vorhanden?

Don't share any sensitive details you find, just observe the pattern. Teile keine sensiblen Details, die du findest, beobachte nur das Muster.

What is Authorization? Was ist Autorisierung?

Authorization comes after authentication. Autorisierung kommt nach der Authentifizierung.

Once a user's identity is confirmed, authentication, authorization determines what that user is allowed to do. Sobald die Identität eines Benutzers bestätigt ist, Authentifizierung, bestimmt die Autorisierung, was dieser Benutzer tun darf.

It answers the question: What are you allowed to do? Sie beantwortet die Frage: Was darfst du tun?

For example, on a blogging platform: Any visitor, even unauthenticated, might be authorized to read blog posts. Zum Beispiel auf einer Blogging-Plattform: Jeder Besucher, selbst unauthentifiziert, könnte autorisiert sein, Blogbeiträge zu lesen.

An authenticated user, for example Alice, might be authorized to create new posts and edit or delete her own posts. Ein authentifizierter Benutzer, zum Beispiel Alice, könnte autorisiert sein, neue Beiträge zu erstellen und ihre eigenen Beiträge zu bearbeiten oder zu löschen.

An authenticated administrator, for example AdminBob, might be authorized to edit or delete any post on the platform. Ein authentifizierter Administrator, zum Beispiel AdminBob, könnte autorisiert sein, jeden Beitrag auf der Plattform zu bearbeiten oder zu löschen.

Authentication confirms you are Alice. Authentifizierung bestätigt, dass du Alice bist.

Authorization checks if Alice has permission to delete a specific post. Autorisierung prüft, ob Alice die Berechtigung hat, einen bestimmten Beitrag zu löschen.

Authentication versus Authorization. Authentifizierung versus Autorisierung.

Feature: Authentication. Purpose: Verifies identity, Who are you? Authorization. Purpose: Grants/denies permissions, What can you do? Merkmal: Authentifizierung. Zweck: Überprüft Identität, Wer bist du? Autorisierung. Zweck: Gewährt/verweigert Berechtigungen, Was kannst du tun?

Process: Authentication confirms credentials, for example password, token, key. Authorization checks access control rules against the identity. Prozess: Authentifizierung bestätigt Anmeldedaten, zum Beispiel Passwort, Token, Schlüssel. Autorisierung prüft Zugriffskontrollregeln gegen die Identität.

Timing: Authentication happens first. Authorization happens after successful authentication. Zeitpunkt: Authentifizierung geschieht zuerst. Autorisierung geschieht nach erfolgreicher Authentifizierung.

Outcome: Authentication, identity is known or unknown. Authorization, access is granted or denied to a specific resource/action. Ergebnis: Authentifizierung, Identität ist bekannt oder unbekannt. Autorisierung, Zugriff wird gewährt oder verweigert für eine spezifische Ressource/Aktion.

Analogy: Authentication, showing your ID to enter a building. Authorization, checking your ticket type to see if you can enter the VIP area. Analogie: Authentifizierung, deinen Ausweis zeigen, um ein Gebäude zu betreten. Autorisierung, deinen Tickettyp prüfen, um zu sehen, ob du den VIP-Bereich betreten kannst.

Understanding both concepts is vital for building secure APIs. Das Verständnis beider Konzepte ist entscheidend für den Aufbau sicherer APIs.

An API might authenticate a user correctly but still be vulnerable if it doesn't properly authorize their actions. Eine API könnte einen Benutzer korrekt authentifizieren, aber dennoch anfällig sein, wenn sie seine Aktionen nicht ordnungsgemäß autorisiert.

This pre-class material should give you a solid starting point. Dieses Vorbereitungsmaterial sollte dir einen soliden Ausgangspunkt geben.

In our live session, we'll dive deeper into these topics, explore practical examples, and discuss how to implement and secure APIs. In unserer Live-Sitzung werden wir tiefer in diese Themen eintauchen, praktische Beispiele erkunden und diskutieren, wie man APIs implementiert und sichert.

The slides for the live session can be viewed here. Die Folien für die Live-Sitzung können hier angesehen werden.

Try not to peek before class, spoilers inside! Versuche nicht, vor dem Unterricht zu schauen, es sind Spoiler drin!