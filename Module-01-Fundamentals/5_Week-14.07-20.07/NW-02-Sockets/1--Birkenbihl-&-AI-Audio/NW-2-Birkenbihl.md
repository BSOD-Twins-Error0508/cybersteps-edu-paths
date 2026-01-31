Welcome! Before our live session on socket programming, let's get familiar with the basics. This preparation should take about 45 minutes. We'll learn how programs on different computers talk to each other over a network. Willkommen! Bevor wir mit unserer Live-Session zur Socket-Programmierung beginnen, machen wir uns mit den Grundlagen vertraut. Diese Vorbereitung sollte etwa 45 Minuten dauern. Wir werden lernen, wie Programme auf verschiedenen Computern über ein Netzwerk miteinander kommunizieren.

What is a Network Socket? Was ist ein Netzwerk-Socket?

Imagine the internet is like a huge city connecting many buildings, which are computers. Each building has a unique street address, called an IP address, for example 192.168.1.10 or 8.8.8.8. This address makes sure information gets sent to the right computer. Stell dir das Internet wie eine riesige Stadt vor, die viele Gebäude verbindet, wobei die Gebäude Computer sind. Jedes Gebäude hat eine eindeutige Straßenadresse, die IP-Adresse genannt wird, zum Beispiel 192.168.1.10 oder 8.8.8.8. Diese Adresse stellt sicher, dass Informationen an den richtigen Computer gesendet werden.

But what if that computer is running many different programs at once, like a web browser, a game, and email? How does the information reach the correct program? That's where sockets and ports come in. Aber was ist, wenn dieser Computer viele verschiedene Programme gleichzeitig ausführt, wie einen Webbrowser, ein Spiel und E-Mail? Wie erreicht die Information das richtige Programm? Hier kommen Sockets und Ports ins Spiel.

A network socket is like a specific communication endpoint for an application on a computer. Think of it as the program's personal doorway for sending and receiving network messages. To make this doorway unique, it uses the computer's IP address plus a special number called a port. Ein Netzwerk-Socket ist wie ein spezifischer Kommunikationsendpunkt für eine Anwendung auf einem Computer. Stell es dir als die persönliche Tür des Programms vor, um Netzwerknachrichten zu senden und zu empfangen. Um diese Tür einzigartig zu machen, verwendet sie die IP-Adresse des Computers plus eine spezielle Nummer, die Port genannt wird.

Ports: The Application's Doorbell. Ports: Die Türklingel der Anwendung.

A port number is a number between 0 and 65535. If the IP address tells you which building, which is the computer, to go to, the port number tells you which apartment or office, which is the application, inside that building you need. Eine Portnummer ist eine Zahl zwischen 0 und 65535. Wenn die IP-Adresse dir sagt, zu welchem Gebäude, also welchem Computer, du gehen sollst, sagt dir die Portnummer, welche Wohnung oder welches Büro, also welche Anwendung, in diesem Gebäude du brauchst.

When data arrives at a computer, identified by its IP address, the operating system looks at the port number attached to that data. It then directs the data to the specific application that is listening on that port. Wenn Daten an einem Computer ankommen, der durch seine IP-Adresse identifiziert wird, schaut das Betriebssystem auf die Portnummer, die an diese Daten angehängt ist. Es leitet die Daten dann an die spezifische Anwendung weiter, die auf diesem Port lauscht.

Well-Known Ports, 0 to 1023: These are usually reserved for common, standard services. For example, web servers often use port 80 for HTTP or 443 for secure HTTPS. You usually don't need special permissions to connect to these ports, but setting up a server on these ports might require administrator rights. Bekannte Ports, 0 bis 1023: Diese sind normalerweise für gängige Standarddienste reserviert. Zum Beispiel verwenden Webserver oft Port 80 für HTTP oder 443 für sicheres HTTPS. Du brauchst normalerweise keine speziellen Berechtigungen, um dich mit diesen Ports zu verbinden, aber das Einrichten eines Servers auf diesen Ports könnte Administratorrechte erfordern.

Other Ports, 1024 to 65535: These are available for general use by other applications, like games, databases, or custom programs you write. Andere Ports, 1024 bis 65535: Diese sind für die allgemeine Nutzung durch andere Anwendungen verfügbar, wie Spiele, Datenbanken oder benutzerdefinierte Programme, die du schreibst.

So, a socket is really the combination of an IP address plus Port number. This pair uniquely identifies one side of a network communication link. Also ist ein Socket wirklich die Kombination aus einer IP-Adresse plus Portnummer. Dieses Paar identifiziert eindeutig eine Seite einer Netzwerkkommunikationsverbindung.

The Client-Server Model. Das Client-Server-Modell.

A very common way programs communicate over a network is the client-server model. Eine sehr verbreitete Art, wie Programme über ein Netzwerk kommunizieren, ist das Client-Server-Modell.

Server: A program that runs on a computer, listens on a specific IP address and port number, and waits for other programs to contact it. It provides some kind of service, for example, hosting a website or managing a game. Like a shop waiting for customers at its specific address and door number. Server: Ein Programm, das auf einem Computer läuft, auf einer bestimmten IP-Adresse und Portnummer lauscht und darauf wartet, dass andere Programme es kontaktieren. Es bietet eine Art Dienst an, zum Beispiel das Hosten einer Website oder die Verwaltung eines Spiels. Wie ein Geschäft, das an seiner bestimmten Adresse und Türnummer auf Kunden wartet.

Client: A program that starts the conversation by connecting to a server. The client needs to know the server's IP address and the specific port number the server is listening on. Like a customer going to the shop's address and ringing the correct doorbell, which is the port. Client: Ein Programm, das das Gespräch beginnt, indem es sich mit einem Server verbindet. Der Client muss die IP-Adresse des Servers und die spezifische Portnummer kennen, auf der der Server lauscht. Wie ein Kunde, der zur Adresse des Geschäfts geht und an der richtigen Türklingel, dem Port, klingelt.

When you visit google dot com, your browser, the client, connects to one of Google's computers using its IP address on port 443, the standard port for secure websites. Google's web server, the server, is listening on that IP and port, receives the request, and sends the webpage data back to your browser. Wenn du google punkt com besuchst, verbindet sich dein Browser, der Client, mit einem von Googles Computern über dessen IP-Adresse auf Port 443, dem Standardport für sichere Websites. Googles Webserver, der Server, lauscht auf dieser IP und diesem Port, empfängt die Anfrage und sendet die Webseiten-Daten zurück an deinen Browser.

Sockets in Python. Sockets in Python.

Python has a built-in socket library that lets us create clients and servers. Let's look at how to set up a simple server first, and then how a client connects to it. Python hat eine eingebaute Socket-Bibliothek, die es uns ermöglicht, Clients und Server zu erstellen. Schauen wir uns zuerst an, wie man einen einfachen Server einrichtet, und dann, wie sich ein Client damit verbindet.

Python Server Example. Python-Server-Beispiel.

This server listens on port 9999 for one connection, receives a message, and then stops. Dieser Server lauscht auf Port 9999 auf eine Verbindung, empfängt eine Nachricht und stoppt dann.

Try it yourself: Server. Probiere es selbst aus: Server.

In Visual Studio Code, create a new Python file, for example, server dot py. Erstelle in Visual Studio Code eine neue Python-Datei, zum Beispiel server punkt py.

Paste this code: import socket, print "Server: Starting...", try: create a socket, server underscore socket equals socket dot socket, print "Server: Socket created.", address to listen on, 0.0.0.0 means all available interfaces, and port, server underscore address equals "0.0.0.0", 9999. Füge diesen Code ein: import socket, print "Server: Starting...", try: erstelle einen Socket, server underscore socket gleich socket punkt socket, print "Server: Socket created.", Adresse zum Lauschen, 0.0.0.0 bedeutet alle verfügbaren Schnittstellen, und Port, server underscore address gleich "0.0.0.0", 9999.

Print "Server: Binding to" server underscore address 0 ":" server underscore address 1, attach the socket to the address and port, server underscore socket dot bind server underscore address. Print "Server: Binding to" server underscore address 0 ":" server underscore address 1, hänge den Socket an die Adresse und den Port an, server underscore socket punkt bind server underscore address.

Start listening for incoming connections, allow 1 waiting connection, server underscore socket dot listen 1, print "Server: Listening on port" server underscore address 1. Beginne auf eingehende Verbindungen zu lauschen, erlaube 1 wartende Verbindung, server underscore socket punkt listen 1, print "Server: Listening on port" server underscore address 1.

Wait for a client to connect, this stops the program until connection, client underscore connection, client underscore address equals server underscore socket dot accept, print "Server: Connection accepted from" client underscore address 0 ":" client underscore address 1. Warte darauf, dass sich ein Client verbindet, dies stoppt das Programm bis zur Verbindung, client underscore connection, client underscore address gleich server underscore socket punkt accept, print "Server: Connection accepted from" client underscore address 0 ":" client underscore address 1.

Receive data, up to 1024 bytes, data underscore received equals client underscore connection dot recv 1024, decode the bytes back into a string, message equals data underscore received dot decode 'utf-8', print "Server: Received:" message. Empfange Daten, bis zu 1024 Bytes, data underscore received gleich client underscore connection punkt recv 1024, dekodiere die Bytes zurück in einen String, message gleich data underscore received punkt decode 'utf-8', print "Server: Received:" message.

Close the connection with the client, client underscore connection dot close, print "Server: Client connection closed." Schließe die Verbindung mit dem Client, client underscore connection punkt close, print "Server: Client connection closed."

Close the server's listening socket, server underscore socket dot close, print "Server: Server socket closed." Schließe den lauschenden Socket des Servers, server underscore socket punkt close, print "Server: Server socket closed."

Except socket dot error as err: print "Server: Socket error:" err, except Exception as e: print "Server: An error occurred:" e. Except socket punkt error as err: print "Server: Socket error:" err, except Exception as e: print "Server: An error occurred:" e.

Save the file. You'll run this first. Speichere die Datei. Du wirst diese zuerst ausführen.

Python Client Example. Python-Client-Beispiel.

This client tries to connect to a server running on the same machine, 127.0.0.1, also known as localhost, on port 9999. It expects the server from the example above to be running. Dieser Client versucht, sich mit einem Server zu verbinden, der auf derselben Maschine läuft, 127.0.0.1, auch bekannt als localhost, auf Port 9999. Er erwartet, dass der Server aus dem obigen Beispiel läuft.

Try it yourself: Client. Probiere es selbst aus: Client.

Open Visual Studio Code. Create another new Python file, for example, client dot py. Öffne Visual Studio Code. Erstelle eine weitere neue Python-Datei, zum Beispiel client punkt py.

Paste this code: import socket, print "Client: Starting...", try: create a socket, client underscore socket equals socket dot socket, print "Client: Socket created." Füge diesen Code ein: import socket, print "Client: Starting...", try: erstelle einen Socket, client underscore socket gleich socket punkt socket, print "Client: Socket created."

Server address, localhost means this computer, and port, server underscore address equals "127.0.0.1", 9999. Server-Adresse, localhost bedeutet dieser Computer, und Port, server underscore address gleich "127.0.0.1", 9999.

Print "Client: Connecting to" server underscore address 0 ":" server underscore address 1, connect to the server, client underscore socket dot connect server underscore address, print "Client: Connected!" Print "Client: Connecting to" server underscore address 0 ":" server underscore address 1, verbinde dich mit dem Server, client underscore socket punkt connect server underscore address, print "Client: Connected!"

Send a message, must be encoded to bytes, message equals "Hi server!", client underscore socket dot sendall message dot encode 'utf-8', print "Client: Sent:" message. Sende eine Nachricht, muss in Bytes kodiert werden, message gleich "Hi server!", client underscore socket punkt sendall message punkt encode 'utf-8', print "Client: Sent:" message.

Close the socket, client underscore socket dot close, print "Client: Socket closed." Schließe den Socket, client underscore socket punkt close, print "Client: Socket closed."

Except socket dot error as err: print "Client: Failed to connect or send. Is server running? Error:" err, except Exception as e: print "Client: An error occurred:" e. Except socket punkt error as err: print "Client: Failed to connect or send. Is server running? Error:" err, except Exception as e: print "Client: An error occurred:" e.

Save the file. You'll run this after starting the server. Speichere die Datei. Du wirst diese nach dem Starten des Servers ausführen.

Running the Client and Server. Ausführen von Client und Server.

Open two separate terminals in Visual Studio Code. Öffne zwei separate Terminals in Visual Studio Code.

In the first terminal, run the server: python server dot py. It should print messages and stop at "Listening on port 9999...". Im ersten Terminal führe den Server aus: python server punkt py. Er sollte Nachrichten ausgeben und bei "Listening on port 9999..." stoppen.

In the second terminal, run the client: python client dot py. The client should print its messages, including "Connected!" and "Sent: 'Hi server!'". Im zweiten Terminal führe den Client aus: python client punkt py. Der Client sollte seine Nachrichten ausgeben, einschließlich "Connected!" und "Sent: 'Hi server!'".

The server should then print that it accepted a connection, received the message, and closed. Both scripts should finish. Der Server sollte dann ausgeben, dass er eine Verbindung akzeptiert, die Nachricht empfangen und geschlossen hat. Beide Skripte sollten beendet sein.

What to Observe: Was zu beobachten ist:

The server uses bind to claim a port and listen to wait for clients. Der Server verwendet bind, um einen Port zu beanspruchen, und listen, um auf Clients zu warten.

Accept waits for a client and gives back a new socket just for talking to that specific client. Accept wartet auf einen Client und gibt einen neuen Socket zurück, nur um mit diesem bestimmten Client zu sprechen.

The client uses connect to reach out to the server's IP and port. Der Client verwendet connect, um die IP und den Port des Servers zu erreichen.

Sendall sends data as bytes, recv receives data as bytes. We use dot encode 'utf-8' and dot decode 'utf-8' to convert between strings and bytes. Sendall sendet Daten als Bytes, recv empfängt Daten als Bytes. Wir verwenden punkt encode 'utf-8' und punkt decode 'utf-8', um zwischen Strings und Bytes zu konvertieren.

Sockets should be closed. Sockets sollten geschlossen werden.

Using try...except helps handle network errors gracefully. Die Verwendung von try...except hilft, Netzwerkfehler elegant zu behandeln.

Summary. Zusammenfassung.

Sockets are communication endpoints defined by an IP address and a port number. They allow specific applications on networked computers to talk to each other. Sockets sind Kommunikationsendpunkte, die durch eine IP-Adresse und eine Portnummer definiert sind. Sie ermöglichen es spezifischen Anwendungen auf vernetzten Computern, miteinander zu kommunizieren.

The client-server model is common: servers bind and listen on a port, while clients connect to them. Python's socket module provides the functions needed to build these network programs. Das Client-Server-Modell ist verbreitet: Server binden und lauschen auf einem Port, während Clients sich mit ihnen verbinden. Pythons Socket-Modul stellt die Funktionen bereit, die benötigt werden, um diese Netzwerkprogramme zu erstellen.

The slides for the live session can be viewed here: https://gamma.app/docs/Networking-2-Sockets-lco1tb9z8litcyu?mode=doc. Try not to peek before class, spoilers inside! Die Folien für die Live-Session können hier angesehen werden: https://gamma.app/docs/Networking-2-Sockets-lco1tb9z8litcyu?mode=doc. Versuche nicht vor dem Unterricht zu spicken, es sind Spoiler drin!