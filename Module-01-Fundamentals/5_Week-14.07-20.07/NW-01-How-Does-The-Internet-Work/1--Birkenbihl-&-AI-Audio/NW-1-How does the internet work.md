Welcome to the fascinating world of computer networks! Willkommen in der faszinierenden Welt der Computernetzwerke!

Ever wondered what really happens when you type a website address like www.google.com into your browser and hit Enter? Hast du dich jemals gefragt, was wirklich passiert, wenn du eine Webadresse wie www.google.com in deinen Browser eingibst und Enter drückst?

In milliseconds, a complex sequence of events unfolds. In Millisekunden entfaltet sich eine komplexe Abfolge von Ereignissen.

Your computer sends a DNS query to find the server's IP address. Dein Computer sendet eine DNS-Anfrage, um die IP-Adresse des Servers zu finden.

Your browser initiates a TCP connection to that server, typically on port 443 for secure HTTPS. Dein Browser stellt eine TCP-Verbindung zu diesem Server her, typischerweise über Port 443 für sicheres HTTPS.

It sends an HTTP request asking for the webpage content. Er sendet eine HTTP-Anfrage und bittet um den Inhalt der Webseite.

This request travels as packets of data across your local network, through your router, across your ISP's network. Diese Anfrage reist als Datenpakete durch dein lokales Netzwerk, durch deinen Router und durch das Netzwerk deines Internetanbieters.

It hops between massive core routers on the internet backbone, potentially passing through firewalls, until it reaches Google's server. Sie springt zwischen riesigen Kernroutern im Internet-Backbone hin und her, passiert möglicherweise Firewalls, bis sie Googles Server erreicht.

The server processes the request and sends back the webpage content, again broken into packets. Der Server verarbeitet die Anfrage und sendet den Inhalt der Webseite zurück, wieder aufgeteilt in Pakete.

These packets retrace a path back to your computer. Diese Pakete finden ihren Weg zurück zu deinem Computer.

Your browser reassembles these packets and renders the page you see. Dein Browser setzt diese Pakete wieder zusammen und zeigt die Seite an, die du siehst.

Sounds complicated? Klingt kompliziert?

Don't worry! Keine Sorge!

We'll break down all these concepts, like DNS, TCP/IP, HTTP, packets, routers, IPs, and many more throughout our learning about computer networks. Wir werden all diese Konzepte wie DNS, TCP/IP, HTTP, Pakete, Router, IPs und viele mehr im Laufe unseres Lernens über Computernetzwerke erklären.

For now, let's start with the absolute basics. Für den Moment beginnen wir mit den absoluten Grundlagen.

Before our first live session, this preparation will introduce you to some fundamental ideas and terms. Vor unserer ersten Live-Sitzung wird diese Vorbereitung dich mit einigen grundlegenden Ideen und Begriffen vertraut machen.

We'll cover everything step by step, assuming no prior knowledge. Wir werden alles Schritt für Schritt behandeln und setzen kein Vorwissen voraus.

What is a Network? Was ist ein Netzwerk?

At its simplest, a network is just two or more computers connected together so they can share resources or information. Ganz einfach ausgedrückt ist ein Netzwerk nur zwei oder mehr Computer, die miteinander verbunden sind, damit sie Ressourcen oder Informationen teilen können.

Think about your home network. Denke an dein Heimnetzwerk.

You might have a laptop, a phone, and maybe a smart TV all connected to your Wi-Fi. Du hast vielleicht einen Laptop, ein Handy und vielleicht einen Smart-TV, die alle mit deinem WLAN verbunden sind.

That's a small network! Das ist ein kleines Netzwerk!

They can communicate with each other and often share one connection to the outside world. Sie können miteinander kommunizieren und teilen sich oft eine Verbindung zur Außenwelt.

What is the Internet? Was ist das Internet?

The Internet is essentially a massive network of networks. Das Internet ist im Wesentlichen ein riesiges Netzwerk aus Netzwerken.

It connects billions of computers, phones, servers, and other devices globally. Es verbindet Milliarden von Computern, Handys, Servern und anderen Geräten weltweit.

It's not a single entity but a vast, interconnected web allowing devices on different networks, from your home network to large corporate or university networks, to communicate with each other. Es ist keine einzelne Einheit, sondern ein riesiges, miteinander verbundenes Netz, das es Geräten in verschiedenen Netzwerken ermöglicht, von deinem Heimnetzwerk bis zu großen Firmen- oder Universitätsnetzwerken, miteinander zu kommunizieren.

Think of it like the global postal system. Stell es dir wie das globale Postsystem vor.

You have local post offices, your home network, connected by regional hubs, larger networks, all part of a worldwide system that lets you send a letter, data, from your house to almost anywhere else in the world. Du hast lokale Postämter, dein Heimnetzwerk, verbunden durch regionale Knotenpunkte, größere Netzwerke, alles Teil eines weltweiten Systems, das es dir ermöglicht, einen Brief, also Daten, von deinem Haus fast überall anders auf der Welt hinzuschicken.

Clients and Servers. Clients und Server.

Much of the internet works on a client-server model. Ein Großteil des Internets funktioniert nach dem Client-Server-Modell.

Client: A device or program that requests information or services. Client: Ein Gerät oder Programm, das Informationen oder Dienste anfordert.

When you browse a website, your web browser, like Chrome or Firefox, acts as a client. Wenn du eine Webseite besuchst, fungiert dein Webbrowser, wie Chrome oder Firefox, als Client.

It requests the webpage from a server. Er fordert die Webseite von einem Server an.

Server: A powerful computer or program that provides information or services to clients. Server: Ein leistungsstarker Computer oder ein Programm, das Informationen oder Dienste für Clients bereitstellt.

The computer hosting the website you want to visit is a server. Der Computer, der die Webseite hostet, die du besuchen möchtest, ist ein Server.

It listens for requests and sends back the requested data, like the webpage. Er wartet auf Anfragen und sendet die angeforderten Daten zurück, wie zum Beispiel die Webseite.

This isn't limited to websites. Das ist nicht auf Webseiten beschränkt.

Email, online games, streaming services, many internet applications use this model. E-Mail, Online-Spiele, Streaming-Dienste, viele Internetanwendungen nutzen dieses Modell.

Your email app is a client requesting emails from an email server. Deine E-Mail-App ist ein Client, der E-Mails von einem E-Mail-Server anfordert.

Think about it. Denk mal darüber nach.

Can you think of other examples of client-server interactions you use every day, besides web browsing and email? Kannst du dir andere Beispiele für Client-Server-Interaktionen vorstellen, die du jeden Tag nutzt, außer Websurfen und E-Mail?

Addresses on the Internet: IP Addresses. Adressen im Internet: IP-Adressen.

Just like every house needs a unique address for mail delivery, every device connected directly to the internet needs a unique identifier. Genau wie jedes Haus eine eindeutige Adresse für die Postzustellung braucht, benötigt jedes Gerät, das direkt mit dem Internet verbunden ist, eine eindeutige Kennung.

This is called an IP address, which stands for Internet Protocol address. Das nennt man eine IP-Adresse, was für Internet-Protokoll-Adresse steht.

An IP address is a series of numbers that identifies a specific device on a specific network. Eine IP-Adresse ist eine Zahlenreihe, die ein bestimmtes Gerät in einem bestimmten Netzwerk identifiziert.

It serves two main functions. Sie erfüllt zwei Hauptfunktionen.

First, identification: It uniquely identifies the device, like your name. Erstens, Identifikation: Sie identifiziert das Gerät eindeutig, wie dein Name.

Second, location: It helps locate the device within the vast internet, like your street address. Zweitens, Standort: Sie hilft dabei, das Gerät im riesigen Internet zu lokalisieren, wie deine Straßenadresse.

A common format you might see is something like 172.217.160.142. Ein gängiges Format, das du sehen könntest, ist zum Beispiel 172.217.160.142.

This is an IPv4 address. Das ist eine IPv4-Adresse.

When you type a website name like www.google.com into your browser, systems behind the scenes translate that name into the server's IP address so your request can be sent to the right place. Wenn du einen Webseiten-Namen wie www.google.com in deinen Browser eingibst, übersetzen Systeme im Hintergrund diesen Namen in die IP-Adresse des Servers, damit deine Anfrage an die richtige Stelle gesendet werden kann.

We'll learn more about this translation process, called DNS, later. Wir werden später mehr über diesen Übersetzungsprozess lernen, der DNS genannt wird.

Guiding the Traffic: Routers. Den Verkehr leiten: Router.

So, how does your request find its way from your computer, the client, to the correct server, possibly halfway across the world, and how does the response get back? Wie findet also deine Anfrage ihren Weg von deinem Computer, dem Client, zum richtigen Server, möglicherweise auf der anderen Seite der Welt, und wie kommt die Antwort zurück?

This is where routers come in. Hier kommen Router ins Spiel.

A router is a networking device that directs data traffic between different networks. Ein Router ist ein Netzwerkgerät, das den Datenverkehr zwischen verschiedenen Netzwerken lenkt.

Think of it as a traffic controller or a smart post office for the internet. Stell ihn dir als Verkehrsregler oder als intelligentes Postamt für das Internet vor.

Home Router: You likely have a router at home, often combined with your Wi-Fi access point. Heimrouter: Du hast wahrscheinlich einen Router zu Hause, oft kombiniert mit deinem WLAN-Zugangspunkt.

Its job is to connect all the devices on your home network to each other and, crucially, to connect your entire home network to the internet via your Internet Service Provider. Seine Aufgabe ist es, alle Geräte in deinem Heimnetzwerk miteinander zu verbinden und, ganz wichtig, dein gesamtes Heimnetzwerk über deinen Internetanbieter mit dem Internet zu verbinden.

Core Routers: The internet itself relies on many large, powerful routers. Kernrouter: Das Internet selbst stützt sich auf viele große, leistungsstarke Router.

When you send a request, it hops from router to router, each one figuring out the best next step to get your data closer to its destination IP address. Wenn du eine Anfrage sendest, springt sie von Router zu Router, wobei jeder den besten nächsten Schritt ermittelt, um deine Daten näher an ihre Ziel-IP-Adresse zu bringen.

Connecting to the Big Network: ISPs. Verbindung zum großen Netzwerk: Internetanbieter.

How does your home network actually connect to the massive global internet? Wie verbindet sich dein Heimnetzwerk eigentlich mit dem riesigen globalen Internet?

Through an Internet Service Provider, or ISP. Über einen Internetanbieter, auch ISP genannt.

An ISP is a company, like Comcast, Deutsche Telekom, Vodafone, and so on, that provides individuals and organizations access to the internet. Ein ISP ist ein Unternehmen, wie Comcast, Deutsche Telekom, Vodafone und so weiter, das Privatpersonen und Organisationen Zugang zum Internet bietet.

They manage large networks and the infrastructure, cables, routers, and so on, that link your home or business to the rest of the online world. Sie verwalten große Netzwerke und die Infrastruktur, Kabel, Router und so weiter, die dein Zuhause oder Geschäft mit dem Rest der Online-Welt verbinden.

You pay them for your internet connection. Du bezahlst sie für deine Internetverbindung.

They are your gateway to the internet. Sie sind dein Tor zum Internet.

Basic Network Commands in the Terminal. Grundlegende Netzwerkbefehle im Terminal.

Let's try two fundamental commands you can run in your computer's terminal, which is the Terminal app on macOS. Lass uns zwei grundlegende Befehle ausprobieren, die du im Terminal deines Computers ausführen kannst, das ist die Terminal-App auf macOS.

These help check basic network connectivity and view your own network configuration. Diese helfen dabei, die grundlegende Netzwerkverbindung zu überprüfen und deine eigene Netzwerkkonfiguration anzuzeigen.

Try it yourself: Ping. Probiere es selbst: Ping.

The ping command sends a small packet of data to a target host, identified by name or IP address, and waits for a reply. Der Ping-Befehl sendet ein kleines Datenpaket an einen Zielhost, identifiziert durch Namen oder IP-Adresse, und wartet auf eine Antwort.

It's a basic way to check if another computer is reachable over the network and how long it takes for the signal to travel there and back, which is called latency. Es ist eine grundlegende Methode, um zu überprüfen, ob ein anderer Computer über das Netzwerk erreichbar ist und wie lange das Signal für den Hin- und Rückweg braucht, was man Latenz nennt.

Open the Terminal app on your Mac. Öffne die Terminal-App auf deinem Mac.

You can find it using Spotlight search by pressing Command and Space, then type Terminal. Du findest sie über die Spotlight-Suche, indem du Befehlstaste und Leertaste drückst und dann Terminal eingibst.

Type the following command and press Enter: ping www.google.com. Gib den folgenden Befehl ein und drücke Enter: ping www.google.com.

You should see lines appearing, showing replies received from Google's server, along with the time it took in milliseconds. Du solltest Zeilen erscheinen sehen, die Antworten von Googles Server zeigen, zusammen mit der Zeit, die es in Millisekunden gedauert hat.

This means your computer can reach Google! Das bedeutet, dein Computer kann Google erreichen!

Press Control and C to stop the ping command. Drücke Steuerung und C, um den Ping-Befehl zu stoppen.

Try it yourself: Check Your IP Configuration. Probiere es selbst: Überprüfe deine IP-Konfiguration.

You can view the network configuration of your own computer, including its local IP address assigned by your home router. Du kannst die Netzwerkkonfiguration deines eigenen Computers ansehen, einschließlich der lokalen IP-Adresse, die von deinem Heimrouter zugewiesen wurde.

In the Terminal app, type the following command and press Enter: ifconfig. Gib in der Terminal-App den folgenden Befehl ein und drücke Enter: ifconfig.

This command prints out a lot of information about your network interfaces, like Wi-Fi, Ethernet, and so on. Dieser Befehl gibt viele Informationen über deine Netzwerkschnittstellen aus, wie WLAN, Ethernet und so weiter.

Look for an active interface, often en0 or en1 for Wi-Fi. Suche nach einer aktiven Schnittstelle, oft en0 oder en1 für WLAN.

Within its details, find the line starting with inet followed by an address like 192.168.1.x or 10.0.0.x. In den Details findest du die Zeile, die mit inet beginnt, gefolgt von einer Adresse wie 192.168.1.x oder 10.0.0.x.

This is your computer's local IP address on your home network. Das ist die lokale IP-Adresse deines Computers in deinem Heimnetzwerk.

It's different from the public IP address your whole network uses to talk to the internet, which you might find by searching "what is my IP address" in a browser. Sie unterscheidet sich von der öffentlichen IP-Adresse, die dein gesamtes Netzwerk nutzt, um mit dem Internet zu kommunizieren, die du findest, indem du im Browser nach "what is my IP address" suchst.

We'll explore the difference between public and private IPs later. Wir werden den Unterschied zwischen öffentlichen und privaten IPs später erkunden.

That's it for the pre-class reading and activities! Das war's für die Vorlektüre und Aktivitäten vor der Stunde!

We've touched upon the complexity of web browsing, defined core terms like network, internet, client/server, IP address, router, and ISP, and even tried basic commands like ping and ifconfig. Wir haben die Komplexität des Websurfens angesprochen, Kernbegriffe wie Netzwerk, Internet, Client/Server, IP-Adresse, Router und ISP definiert und sogar grundlegende Befehle wie ping und ifconfig ausprobiert.

Take some time to digest these concepts. Nimm dir etwas Zeit, um diese Konzepte zu verdauen.

We'll build upon them significantly in our live session. Wir werden in unserer Live-Sitzung erheblich darauf aufbauen.

The slides for the live session can be viewed here. Die Folien für die Live-Sitzung können hier angesehen werden.

Try not to peek before class, spoilers inside! Versuche nicht vor der Stunde zu spicken, es gibt Spoiler!