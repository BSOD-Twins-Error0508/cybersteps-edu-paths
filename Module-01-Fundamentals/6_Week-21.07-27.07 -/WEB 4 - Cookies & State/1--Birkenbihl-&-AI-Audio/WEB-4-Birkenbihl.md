Welcome! In this session, we'll explore how websites remember you and your preferences. Willkommen! In dieser Lektion werden wir erkunden, wie Webseiten sich an dich und deine Einstellungen erinnern.

The Stateless Web and the Need for State. Das zustandslose Web und der Bedarf nach Zustand.

You've learned that HTTP, Hypertext Transfer Protocol, is the foundation of data communication for the World Wide Web. Du hast gelernt, dass HTTP, Hypertext Transfer Protocol, die Grundlage der Datenkommunikation für das World Wide Web ist.

One of its core characteristics is that it's a stateless protocol. Eine seiner Kerneigenschaften ist, dass es ein zustandsloses Protokoll ist.

This means each request from a client, your browser, to a server is treated as an independent transaction. Das bedeutet, dass jede Anfrage von einem Client, deinem Browser, an einen Server als unabhängige Transaktion behandelt wird.

The server doesn't inherently remember anything about previous requests from the same client. Der Server erinnert sich grundsätzlich nicht an vorherige Anfragen vom selben Client.

This is where the concept of state management comes in. Hier kommt das Konzept der Zustandsverwaltung ins Spiel.

Web applications often need to remember information about users and their interactions across multiple requests or visits. Webanwendungen müssen sich oft Informationen über Benutzer und ihre Interaktionen über mehrere Anfragen oder Besuche hinweg merken.

This memory is what we refer to as state. Dieses Gedächtnis ist das, was wir als Zustand bezeichnen.

Without it, every time you clicked a link or loaded a new page on a site, it would be like visiting for the very first time. Ohne diesen würde es jedes Mal, wenn du auf einen Link klickst oder eine neue Seite auf einer Website lädst, so sein, als würdest du sie zum allerersten Mal besuchen.

Common scenarios requiring state management include: User Authentication, keeping a user logged in across different pages. Häufige Szenarien, die Zustandsverwaltung erfordern, umfassen: Benutzerauthentifizierung, einen Benutzer über verschiedene Seiten hinweg eingeloggt zu halten.

Shopping Carts, remembering items a user intends to purchase. Warenkörbe, sich an Artikel zu erinnern, die ein Benutzer kaufen möchte.

User Preferences, storing settings like language, theme, or personalized content. Benutzereinstellungen, Speichern von Einstellungen wie Sprache, Design oder personalisierte Inhalte.

Tracking User Behavior, understanding how users navigate a site, though this has privacy implications. Verfolgung des Benutzerverhaltens, Verstehen, wie Benutzer auf einer Seite navigieren, obwohl dies Auswirkungen auf die Privatsphäre hat.

Think about it. Which websites don't need to manage state? Denk darüber nach. Welche Webseiten müssen keinen Zustand verwalten?

Introducing Cookies: The Web's Memory. Einführung von Cookies: Das Gedächtnis des Webs.

Cookies are one of the most common mechanisms for maintaining state on the web. Cookies sind einer der häufigsten Mechanismen zur Aufrechterhaltung des Zustands im Web.

A cookie is a small piece of data that a server sends to a user's web browser. Ein Cookie ist ein kleines Datenstück, das ein Server an den Webbrowser eines Benutzers sendet.

The browser then stores this data and sends it back to the same server with subsequent requests. Der Browser speichert dann diese Daten und sendet sie bei nachfolgenden Anfragen an denselben Server zurück.

This allows the server to remember information associated with that browser. Dies ermöglicht es dem Server, sich an Informationen zu erinnern, die mit diesem Browser verbunden sind.

Think of cookies like a cloakroom ticket. Stell dir Cookies wie eine Garderobenmarke vor.

When you hand over your coat, information, you get a ticket, cookie. Wenn du deinen Mantel, Informationen, abgibst, bekommst du eine Marke, Cookie.

The next time you visit the cloakroom, server, you present your ticket, and they can retrieve your specific coat. Das nächste Mal, wenn du die Garderobe, Server, besuchst, zeigst du deine Marke vor, und sie können deinen spezifischen Mantel abrufen.

How Cookies Work: A Two-Way Conversation. Wie Cookies funktionieren: Eine wechselseitige Konversation.

The process of using cookies involves a few steps. Der Prozess der Verwendung von Cookies umfasst einige Schritte.

Initial Request: Your browser makes a request to a web server, for example, visiting a website for the first time. Erste Anfrage: Dein Browser stellt eine Anfrage an einen Webserver, zum Beispiel beim ersten Besuch einer Webseite.

Server Response with Set-Cookie Header: If the server wants to store a cookie on your browser, it includes a Set-Cookie header in its HTTP response. Serverantwort mit Set-Cookie-Header: Wenn der Server ein Cookie auf deinem Browser speichern möchte, fügt er einen Set-Cookie-Header in seine HTTP-Antwort ein.

This header contains the name and value of the cookie, along with other attributes that control its behavior. Dieser Header enthält den Namen und Wert des Cookies zusammen mit anderen Attributen, die sein Verhalten steuern.

Example Set-Cookie header: Set-Cookie: userID equals 12345; Expires equals Wed, 21 Oct 2025 07:28:00 GMT. Beispiel Set-Cookie-Header: Set-Cookie: userID gleich 12345; Expires gleich Wed, 21 Oct 2025 07:28:00 GMT.

Browser Stores the Cookie: Your browser receives the response and stores the cookie, associating it with the website's domain. Browser speichert das Cookie: Dein Browser empfängt die Antwort und speichert das Cookie, wobei er es mit der Domain der Webseite verknüpft.

Subsequent Requests with Cookie Header: For every subsequent request your browser makes to the same server, or a server within the cookie's specified domain and path, it includes a Cookie header containing the names and values of all relevant stored cookies. Nachfolgende Anfragen mit Cookie-Header: Bei jeder nachfolgenden Anfrage, die dein Browser an denselben Server oder einen Server innerhalb der angegebenen Domain und des Pfads des Cookies stellt, fügt er einen Cookie-Header hinzu, der die Namen und Werte aller relevanten gespeicherten Cookies enthält.

Example Cookie header: Cookie: userID equals 12345. Beispiel Cookie-Header: Cookie: userID gleich 12345.

Server Reads the Cookie: The server receives the request, reads the Cookie header, and can use the information, for example, userID equals 12345, to identify the user, retrieve their session, load their preferences, and so on. Server liest das Cookie: Der Server empfängt die Anfrage, liest den Cookie-Header und kann die Informationen, zum Beispiel userID gleich 12345, verwenden, um den Benutzer zu identifizieren, seine Sitzung abzurufen, seine Einstellungen zu laden und so weiter.

This back-and-forth allows the server to link multiple requests from the same browser, effectively creating a session or remembering past interactions. Dieser Austausch ermöglicht es dem Server, mehrere Anfragen vom selben Browser zu verknüpfen, wodurch effektiv eine Sitzung erstellt oder vergangene Interaktionen erinnert werden.

Dissecting a Cookie: Attributes and Their Meanings. Einen Cookie sezieren: Attribute und ihre Bedeutungen.

Besides a name and value, cookies can have several attributes that define their behavior and lifecycle. Neben einem Namen und Wert können Cookies mehrere Attribute haben, die ihr Verhalten und ihren Lebenszyklus definieren.

Expires equals date or Max-Age equals seconds: Expires specifies a date and time when the cookie will expire. Expires gleich Datum oder Max-Age gleich Sekunden: Expires gibt ein Datum und eine Uhrzeit an, wann das Cookie abläuft.

After this date, the browser will delete the cookie. Nach diesem Datum wird der Browser das Cookie löschen.

Max-Age specifies the lifetime of the cookie in seconds from the time it's set. Max-Age gibt die Lebensdauer des Cookies in Sekunden ab dem Zeitpunkt seiner Erstellung an.

If both Expires and Max-Age are set, Max-Age takes precedence. Wenn sowohl Expires als auch Max-Age gesetzt sind, hat Max-Age Vorrang.

If neither is set, the cookie is a session cookie and will be deleted when the browser session ends, that is, when the browser is closed. Wenn keines gesetzt ist, ist das Cookie ein Sitzungs-Cookie und wird gelöscht, wenn die Browser-Sitzung endet, das heißt, wenn der Browser geschlossen wird.

Domain equals domain-name: Specifies the domain for which the cookie is valid. Domain gleich Domain-Name: Gibt die Domain an, für die das Cookie gültig ist.

If set, the cookie will be sent to that domain and its subdomains. Wenn gesetzt, wird das Cookie an diese Domain und ihre Subdomains gesendet.

For example, if Domain equals example.com, the cookie would be sent to www.example.com and api.example.com. Zum Beispiel, wenn Domain gleich example.com ist, würde das Cookie an www.example.com und api.example.com gesendet werden.

If not set, it defaults to the host of the document that set the cookie, but not its subdomains. Wenn nicht gesetzt, ist standardmäßig der Host des Dokuments, das das Cookie gesetzt hat, aber nicht seine Subdomains, zuständig.

Path equals path: Specifies the URL path for which the cookie is valid. Path gleich Pfad: Gibt den URL-Pfad an, für den das Cookie gültig ist.

If set to forward slash, the cookie is valid for all paths within the domain. Wenn auf Schrägstrich gesetzt, ist das Cookie für alle Pfade innerhalb der Domain gültig.

If set to forward slash profile forward slash, it's only valid for requests to forward slash profile forward slash and its subdirectories. Wenn auf Schrägstrich profile Schrägstrich gesetzt, ist es nur für Anfragen an Schrägstrich profile Schrägstrich und seine Unterverzeichnisse gültig.

Secure: If this attribute is present, the cookie will only be transmitted over encrypted HTTPS connections. Secure: Wenn dieses Attribut vorhanden ist, wird das Cookie nur über verschlüsselte HTTPS-Verbindungen übertragen.

It will not be sent over unencrypted HTTP. Es wird nicht über unverschlüsseltes HTTP gesendet.

This is crucial for protecting sensitive information in cookies. Dies ist entscheidend zum Schutz sensibler Informationen in Cookies.

HttpOnly: If this attribute is present, the cookie cannot be accessed by client-side JavaScript, for example, using document.cookie. HttpOnly: Wenn dieses Attribut vorhanden ist, kann das Cookie nicht von clientseitigem JavaScript, zum Beispiel mit document.cookie, aufgerufen werden.

This is an important security measure that helps mitigate Cross-Site Scripting, XSS, attacks, where an attacker might try to steal cookies using malicious scripts. Dies ist eine wichtige Sicherheitsmaßnahme, die hilft, Cross-Site Scripting, XSS, Angriffe zu mindern, bei denen ein Angreifer versuchen könnte, Cookies mit bösartigen Skripten zu stehlen.

SameSite equals Strict, Lax, or None: This attribute helps protect against Cross-Site Request Forgery, CSRF, attacks. SameSite gleich Strict, Lax oder None: Dieses Attribut hilft, vor Cross-Site Request Forgery, CSRF, Angriffen zu schützen.

It controls whether a cookie is sent with requests initiated from third-party websites. Es kontrolliert, ob ein Cookie mit Anfragen gesendet wird, die von Drittanbieter-Webseiten initiiert werden.

Strict: The cookie will only be sent with requests originating from the same site that set the cookie. Strict: Das Cookie wird nur mit Anfragen gesendet, die von derselben Seite stammen, die das Cookie gesetzt hat.

Lax: The cookie is sent with same-site requests and with top-level navigations, for example, clicking a link to the target site from an external site. Lax: Das Cookie wird mit Same-Site-Anfragen und mit Top-Level-Navigationen gesendet, zum Beispiel beim Klicken auf einen Link zur Zielseite von einer externen Seite.

This is the default in many modern browsers. Dies ist die Standardeinstellung in vielen modernen Browsern.

None: The cookie will be sent with all requests, both same-site and cross-site. None: Das Cookie wird mit allen Anfragen gesendet, sowohl Same-Site als auch Cross-Site.

If SameSite equals None is used, the Secure attribute must also be set, that is, the cookie must be sent over HTTPS. Wenn SameSite gleich None verwendet wird, muss auch das Secure-Attribut gesetzt werden, das heißt, das Cookie muss über HTTPS gesendet werden.

Managing Cookies: Session versus Persistent. Verwaltung von Cookies: Sitzungs- versus dauerhafte Cookies.

Based on their lifespan, cookies can be broadly categorized into two types. Basierend auf ihrer Lebensdauer können Cookies grob in zwei Typen kategorisiert werden.

Session Cookies: These cookies do not have an Expires or Max-Age attribute. Sitzungs-Cookies: Diese Cookies haben kein Expires- oder Max-Age-Attribut.

They are temporary and are stored in the browser's memory only for the duration of the current browsing session. Sie sind temporär und werden nur für die Dauer der aktuellen Browser-Sitzung im Speicher des Browsers gespeichert.

When the user closes their browser, session cookies are automatically deleted. Wenn der Benutzer seinen Browser schließt, werden Sitzungs-Cookies automatisch gelöscht.

Often used for things like temporarily storing shopping cart contents or maintaining a logged-in state for the current visit. Oft verwendet für Dinge wie das vorübergehende Speichern von Warenkorbinhalten oder das Aufrechterhalten eines eingeloggten Zustands für den aktuellen Besuch.

Persistent Cookies: These cookies have an Expires or Max-Age attribute set to some point in the future. Dauerhafte Cookies: Diese Cookies haben ein Expires- oder Max-Age-Attribut, das auf einen Zeitpunkt in der Zukunft gesetzt ist.

They are stored on the user's hard drive and survive browser restarts. Sie werden auf der Festplatte des Benutzers gespeichert und überleben Browser-Neustarts.

They remain valid until their expiration date is reached or they are manually deleted by the user. Sie bleiben gültig, bis ihr Ablaufdatum erreicht ist oder sie vom Benutzer manuell gelöscht werden.

Used for remembering user preferences, login details, for example, Remember Me functionality, or tracking user behavior across multiple sessions. Verwendet zum Erinnern von Benutzereinstellungen, Login-Details, zum Beispiel Angemeldet bleiben-Funktion, oder zum Verfolgen des Benutzerverhaltens über mehrere Sitzungen hinweg.

Think about it. When might a website choose to use a session cookie over a persistent cookie, and vice-versa? What are the trade-offs? Denk darüber nach. Wann könnte eine Webseite sich dafür entscheiden, ein Sitzungs-Cookie anstelle eines dauerhaften Cookies zu verwenden, und umgekehrt? Was sind die Kompromisse?

Peeking into the Cookie Jar: Using Browser Developer Tools. Einen Blick in die Cookie-Dose werfen: Verwendung von Browser-Entwicklertools.

Modern web browsers provide developer tools that allow you to inspect cookies stored for a particular website. Moderne Webbrowser bieten Entwicklertools, die es dir ermöglichen, Cookies zu inspizieren, die für eine bestimmte Webseite gespeichert sind.

This is incredibly useful for understanding how a site uses cookies and for debugging web applications. Dies ist unglaublich nützlich zum Verstehen, wie eine Seite Cookies verwendet, und zum Debuggen von Webanwendungen.

Try it yourself. Probiere es selbst aus.

Open your web browser, for example, Chrome or Firefox. Öffne deinen Webbrowser, zum Beispiel Chrome oder Firefox.

Visit a few different websites, for example, a news site, an e-commerce site, a social media site. Besuche einige verschiedene Webseiten, zum Beispiel eine Nachrichtenseite, eine E-Commerce-Seite, eine Social-Media-Seite.

Open the browser's developer tools: Usually by right-clicking on the page and selecting Inspect or Inspect Element. Öffne die Entwicklertools des Browsers: Normalerweise durch Rechtsklick auf die Seite und Auswahl von Untersuchen oder Element untersuchen.

Alternatively, press F12, Windows or Linux, or Command plus Option plus I, Mac. Alternativ drücke F12, Windows oder Linux, oder Command plus Option plus I, Mac.

Find the Application tab, in Chrome, or Storage tab, in Firefox. Finde den Anwendung-Tab, in Chrome, oder Speicher-Tab, in Firefox.

In the left-hand panel, look for Cookies under the Storage or Application section. Expand it to see the cookies associated with the current domain. Im linken Panel suche nach Cookies unter dem Speicher- oder Anwendungsbereich. Erweitere es, um die Cookies zu sehen, die mit der aktuellen Domain verbunden sind.

Click on a domain to see the list of cookies. Klicke auf eine Domain, um die Liste der Cookies zu sehen.

You'll see their names, values, domain, path, expiration dates, and other attributes like HttpOnly, Secure, and SameSite. Du siehst ihre Namen, Werte, Domain, Pfad, Ablaufdaten und andere Attribute wie HttpOnly, Secure und SameSite.

Also, explore the Network tab in the developer tools. Erkunde auch den Netzwerk-Tab in den Entwicklertools.

When you load a page or interact with it, look at the HTTP requests and responses. Wenn du eine Seite lädst oder mit ihr interagierst, schaue dir die HTTP-Anfragen und -Antworten an.

You can often find Set-Cookie headers in responses from the server and Cookie headers in requests sent by your browser. Du kannst oft Set-Cookie-Header in Antworten vom Server und Cookie-Header in Anfragen finden, die von deinem Browser gesendet werden.

Observe the different types of information stored in cookies. Do you see any session IDs? Any user preferences? Beobachte die verschiedenen Arten von Informationen, die in Cookies gespeichert sind. Siehst du Sitzungs-IDs? Irgendwelche Benutzereinstellungen?

Cookies and Security: A Double-Edged Sword. Cookies und Sicherheit: Ein zweischneidiges Schwert.

While cookies are essential for modern web functionality, they also introduce potential security risks if not handled carefully. Während Cookies für moderne Webfunktionalität unerlässlich sind, führen sie auch potenzielle Sicherheitsrisiken ein, wenn sie nicht sorgfältig behandelt werden.

Session Hijacking: If an attacker manages to steal a user's session cookie, which often contains a session ID, they can potentially impersonate that user and gain unauthorized access to their account. Sitzungs-Hijacking: Wenn ein Angreifer es schafft, das Sitzungs-Cookie eines Benutzers zu stehlen, das oft eine Sitzungs-ID enthält, kann er möglicherweise diesen Benutzer imitieren und unbefugten Zugriff auf sein Konto erlangen.

This is why Secure and HttpOnly attributes are important. Deshalb sind Secure- und HttpOnly-Attribute wichtig.

Cross-Site Scripting, XSS: If a website is vulnerable to XSS, an attacker might inject malicious JavaScript code that steals cookies. Cross-Site Scripting, XSS: Wenn eine Webseite anfällig für XSS ist, könnte ein Angreifer bösartigen JavaScript-Code einschleusen, der Cookies stiehlt.

If a cookie is not HttpOnly, JavaScript can access it. Wenn ein Cookie nicht HttpOnly ist, kann JavaScript darauf zugreifen.

The stolen cookie, especially a session cookie, can then be used for session hijacking. Das gestohlene Cookie, besonders ein Sitzungs-Cookie, kann dann für Sitzungs-Hijacking verwendet werden.

Cross-Site Request Forgery, CSRF: In a CSRF attack, an attacker tricks a logged-in user into unknowingly submitting a malicious request to a website where they are authenticated. Cross-Site Request Forgery, CSRF: Bei einem CSRF-Angriff bringt ein Angreifer einen eingeloggten Benutzer dazu, unwissentlich eine bösartige Anfrage an eine Webseite zu senden, bei der er authentifiziert ist.

Cookies are sent automatically with requests to their originating domain, so the malicious request would appear legitimate. Cookies werden automatisch mit Anfragen an ihre ursprüngliche Domain gesendet, sodass die bösartige Anfrage legitim erscheinen würde.

The SameSite attribute is a key defense against CSRF. Das SameSite-Attribut ist eine Schlüsselverteidigung gegen CSRF.

Tracking: Cookies, especially third-party cookies, set by a domain different from the one the user is currently visiting, often from ads or tracking scripts, can be used to track users' browsing habits across multiple websites. Verfolgung: Cookies, besonders Drittanbieter-Cookies, die von einer Domain gesetzt werden, die sich von der unterscheidet, die der Benutzer gerade besucht, oft von Werbung oder Tracking-Skripten, können verwendet werden, um die Surfgewohnheiten der Benutzer über mehrere Webseiten hinweg zu verfolgen.

This raises privacy concerns and has led to browsers implementing stricter controls over third-party cookies. Dies wirft Datenschutzbedenken auf und hat dazu geführt, dass Browser strengere Kontrollen über Drittanbieter-Cookies implementieren.

Developers must be mindful of these risks and implement cookies securely, using attributes like HttpOnly, Secure, and SameSite appropriately. Entwickler müssen sich dieser Risiken bewusst sein und Cookies sicher implementieren, indem sie Attribute wie HttpOnly, Secure und SameSite angemessen verwenden.

Beyond Cookies: Server-Side Sessions. Jenseits von Cookies: Serverseitige Sitzungen.

While cookies are great for storing small amounts of data or identifiers on the client-side, storing large amounts of sensitive information directly in cookies is generally not recommended. Während Cookies großartig zum Speichern kleiner Datenmengen oder Identifikatoren auf der Client-Seite sind, wird das Speichern großer Mengen sensibler Informationen direkt in Cookies generell nicht empfohlen.

An alternative and often complementary approach is server-side sessions. Ein alternativer und oft ergänzender Ansatz sind serverseitige Sitzungen.

Here's the basic idea. Hier ist die grundlegende Idee.

When a user starts a session, for example, logs in, the server creates a unique session ID. Wenn ein Benutzer eine Sitzung startet, zum Beispiel sich einloggt, erstellt der Server eine einzigartige Sitzungs-ID.

The server stores the actual session data, for example, user details, shopping cart contents, on the server itself, associated with this unique session ID. Der Server speichert die tatsächlichen Sitzungsdaten, zum Beispiel Benutzerdetails, Warenkorbinhalte, auf dem Server selbst, verknüpft mit dieser einzigartigen Sitzungs-ID.

This data can be stored in memory, a database, or a dedicated session store. Diese Daten können im Speicher, einer Datenbank oder einem dedizierten Sitzungsspeicher gespeichert werden.

The server sends only the session ID back to the client, typically stored in a cookie, a session cookie is perfect for this. Der Server sendet nur die Sitzungs-ID an den Client zurück, typischerweise in einem Cookie gespeichert, ein Sitzungs-Cookie ist perfekt dafür.

On subsequent requests, the client sends the session ID cookie back to the server. Bei nachfolgenden Anfragen sendet der Client das Sitzungs-ID-Cookie zurück an den Server.

The server uses this ID to look up the corresponding session data stored on its side. Der Server verwendet diese ID, um die entsprechenden Sitzungsdaten nachzuschlagen, die auf seiner Seite gespeichert sind.

Advantages of server-side sessions: Security: Sensitive data is kept on the server, not transmitted back and forth or stored on the client's machine, beyond the session ID. Vorteile serverseitiger Sitzungen: Sicherheit: Sensible Daten werden auf dem Server aufbewahrt, nicht hin und her übertragen oder auf der Maschine des Clients gespeichert, über die Sitzungs-ID hinaus.

This reduces the risk if a cookie is compromised. Dies reduziert das Risiko, wenn ein Cookie kompromittiert wird.

Data Capacity: Servers can store much more session data than what can be practically stored in cookies, which have size limits. Datenkapazität: Server können viel mehr Sitzungsdaten speichern, als praktisch in Cookies gespeichert werden kann, die Größenbeschränkungen haben.

Often, cookies and server-side sessions work together. Oft arbeiten Cookies und serverseitige Sitzungen zusammen.

The cookie on the client acts as the key, the session ID, to unlock the data stored on the server. Das Cookie auf dem Client fungiert als Schlüssel, die Sitzungs-ID, um die auf dem Server gespeicherten Daten freizuschalten.

This concludes your pre-class preparation on cookies and state. Dies schließt deine Vorbereitung vor dem Unterricht zu Cookies und Zustand ab.

Take some time to digest this information, and come prepared with any questions for our live session! Nimm dir etwas Zeit, diese Informationen zu verdauen, und komm mit Fragen vorbereitet zu unserer Live-Sitzung!

The slides for the live session can be viewed here. Die Folien für die Live-Sitzung können hier angesehen werden.

Try not to peek before class, spoilers inside! Versuche nicht vor dem Unterricht zu spicken, Spoiler drin!