Welcome! Before our live session on the Transmission Control Protocol, also known as TCP, please go through this material. Willkommen! Bevor unsere Live-Sitzung zum Transmission Control Protocol, auch bekannt als TCP, beginnt, gehen Sie bitte dieses Material durch.

We'll be diving into one of the most fundamental protocols that powers the internet. Wir werden uns mit einem der grundlegendsten Protokolle beschäftigen, die das Internet antreiben.

Understanding TCP is crucial for comprehending how reliable communication happens online, which is vital in cybersecurity for analyzing network traffic and understanding application behavior. Das Verständnis von TCP ist entscheidend, um zu begreifen, wie zuverlässige Kommunikation online stattfindet, was in der Cybersicherheit für die Analyse von Netzwerkverkehr und das Verstehen von Anwendungsverhalten unerlässlich ist.

Recall the 5 layer network model we discussed. Erinnern Sie sich an das 5-Schichten-Netzwerkmodell, das wir besprochen haben.

Sandwiched between the Network Layer, handling IP addresses and routing, and the Application Layer, like HTTP or DNS, lies the Transport Layer. Eingebettet zwischen der Netzwerkschicht, die IP-Adressen und Routing verwaltet, und der Anwendungsschicht, wie HTTP oder DNS, liegt die Transportschicht.

The primary role of the Transport Layer is to provide logical communication between applications running on different hosts. Die Hauptaufgabe der Transportschicht besteht darin, logische Kommunikation zwischen Anwendungen bereitzustellen, die auf verschiedenen Hosts laufen.

While the Network Layer gets packets from one host to another, the Transport Layer gets the data to the correct application on that host. Während die Netzwerkschicht Pakete von einem Host zum anderen befördert, bringt die Transportschicht die Daten zur richtigen Anwendung auf diesem Host.

It acts like a mail sorting room within the destination computer, ensuring the data meant for your web browser doesn't end up delivered to your email client. Sie funktioniert wie eine Postsortieranlage innerhalb des Zielcomputers und stellt sicher, dass Daten für Ihren Webbrowser nicht beim E-Mail-Client landen.

The two most common Transport Layer protocols are TCP and UDP, User Datagram Protocol. Die beiden gängigsten Transportschicht-Protokolle sind TCP und UDP, User Datagram Protocol.

Today, we focus on TCP. Heute konzentrieren wir uns auf TCP.

TCP stands for Transmission Control Protocol. TCP steht für Transmission Control Protocol.

It's defined in RFC 793 and updated by many others. Es ist in RFC 793 definiert und wurde durch viele weitere aktualisiert.

Think of TCP as the reliable, careful postal service of the internet. Stellen Sie sich TCP als den zuverlässigen, sorgfältigen Postdienst des Internets vor.

Its main goal is to ensure that data sent from one application arrives reliably, in order, and error checked at the application on the receiving end. Sein Hauptziel besteht darin, sicherzustellen, dass Daten, die von einer Anwendung gesendet werden, zuverlässig, in der richtigen Reihenfolge und fehlergeprüft bei der Anwendung am empfangenden Ende ankommen.

TCP is connection oriented. TCP ist verbindungsorientiert.

This means before any actual application data is exchanged, the two communicating devices, for example your computer and a web server, establish a connection through a process called a handshake. Das bedeutet, bevor tatsächliche Anwendungsdaten ausgetauscht werden, stellen die beiden kommunizierenden Geräte, zum Beispiel Ihr Computer und ein Webserver, eine Verbindung durch einen Prozess namens Handshake her.

This ensures both sides are ready to communicate and agree on some initial parameters. Dies stellt sicher, dass beide Seiten bereit sind zu kommunizieren und sich auf einige Anfangsparameter einigen.

Once the data transfer is complete, the connection is formally closed. Sobald die Datenübertragung abgeschlossen ist, wird die Verbindung formal geschlossen.

TCP provides several features that make it suitable for applications requiring high reliability. TCP bietet mehrere Funktionen, die es für Anwendungen geeignet machen, die hohe Zuverlässigkeit erfordern.

Connection oriented: As mentioned, TCP establishes a dedicated connection using a three way handshake before data transfer begins. Verbindungsorientiert: Wie erwähnt, stellt TCP eine dedizierte Verbindung mittels eines Drei-Wege-Handshakes her, bevor die Datenübertragung beginnt.

Step 1, SYN: The client wanting to connect sends a TCP segment with the SYN, Synchronize, flag set. Schritt 1, SYN: Der Client, der sich verbinden möchte, sendet ein TCP-Segment mit gesetztem SYN, Synchronize, Flag.

This segment includes an initial sequence number, ISN. Dieses Segment enthält eine anfängliche Sequenznummer, ISN.

Step 2, SYN ACK: The server responds with a TCP segment where both the SYN and ACK, Acknowledgment, flags are set. Schritt 2, SYN ACK: Der Server antwortet mit einem TCP-Segment, bei dem sowohl die SYN- als auch die ACK, Acknowledgment, Flags gesetzt sind.

It acknowledges the client's ISN and proposes its own ISN. Er bestätigt die ISN des Clients und schlägt seine eigene ISN vor.

Step 3, ACK: The client sends back a segment with the ACK flag set, acknowledging the server's ISN. Schritt 3, ACK: Der Client sendet ein Segment mit gesetztem ACK-Flag zurück und bestätigt die ISN des Servers.

At this point, the connection is established, and data transfer can begin. An diesem Punkt ist die Verbindung hergestellt und die Datenübertragung kann beginnen.

Reliable Delivery: TCP guarantees that data sent will arrive. Zuverlässige Zustellung: TCP garantiert, dass gesendete Daten ankommen.

It achieves this using sequence numbers: Each byte of data sent is assigned a sequence number. Dies erreicht es durch Sequenznummern: Jedem gesendeten Datenbyte wird eine Sequenznummer zugewiesen.

Acknowledgments, ACKs: When the receiver gets data, it sends back an acknowledgment indicating the next sequence number it expects. Bestätigungen, ACKs: Wenn der Empfänger Daten erhält, sendet er eine Bestätigung zurück, die die nächste erwartete Sequenznummer angibt.

If the sender doesn't receive an ACK within a certain time, it assumes the data was lost and retransmits it. Wenn der Sender innerhalb einer bestimmten Zeit kein ACK erhält, nimmt er an, dass die Daten verloren gingen, und überträgt sie erneut.

Ordered Data Transfer: IP packets can take different routes and arrive out of order. Geordnete Datenübertragung: IP-Pakete können verschiedene Routen nehmen und in falscher Reihenfolge ankommen.

TCP uses the sequence numbers to reassemble the data segments in the correct order before passing them up to the application layer. TCP verwendet die Sequenznummern, um die Datensegmente in der richtigen Reihenfolge wieder zusammenzusetzen, bevor sie an die Anwendungsschicht weitergegeben werden.

Flow Control: The receiver has a limited amount of buffer space. Flusskontrolle: Der Empfänger hat eine begrenzte Menge an Pufferspeicher.

TCP uses a sliding window mechanism. TCP verwendet einen Sliding-Window-Mechanismus.

The receiver advertises its available buffer space, the window size, in the TCP header. Der Empfänger gibt seinen verfügbaren Pufferspeicher, die Fenstergröße, im TCP-Header bekannt.

The sender agrees not to send more data than the receiver can handle, preventing the receiver from being overwhelmed. Der Sender verpflichtet sich, nicht mehr Daten zu senden, als der Empfänger verarbeiten kann, und verhindert so eine Überlastung des Empfängers.

Congestion Control: TCP tries to prevent overwhelming the network itself, not just the receiver. Staukontrolle: TCP versucht zu verhindern, dass das Netzwerk selbst überlastet wird, nicht nur der Empfänger.

It uses algorithms to slow down its transmission rate if it detects signs of network congestion, like lost packets. Es verwendet Algorithmen, um seine Übertragungsrate zu verlangsamen, wenn es Anzeichen von Netzwerküberlastung wie verlorene Pakete erkennt.

This is crucial for the overall stability of the internet. Dies ist entscheidend für die allgemeine Stabilität des Internets.

How does TCP know which application, for example web browser, email client, game, on the destination host should receive the data? Wie weiß TCP, welche Anwendung, zum Beispiel Webbrowser, E-Mail-Client, Spiel, auf dem Ziel-Host die Daten empfangen soll?

It uses port numbers. Es verwendet Portnummern.

Imagine an apartment building, the host computer, with many apartments, applications. Stellen Sie sich ein Wohnhaus vor, den Host-Computer, mit vielen Wohnungen, den Anwendungen.

The IP address gets you to the building, but the port number gets you to the specific apartment. Die IP-Adresse bringt Sie zum Gebäude, aber die Portnummer bringt Sie zur spezifischen Wohnung.

Port numbers are 16 bit unsigned integers, 0 to 65535. Portnummern sind 16-Bit-Ganzzahlen ohne Vorzeichen, 0 bis 65535.

The combination of an IP address and a port number uniquely identifies a specific process on a specific host. This combination is often called a socket. Die Kombination aus IP-Adresse und Portnummer identifiziert eindeutig einen bestimmten Prozess auf einem bestimmten Host. Diese Kombination wird oft als Socket bezeichnet.

Well Known Ports, 0 to 1023: Reserved for standard, universally known services, for example HTTP on port 80, HTTPS on port 443, SSH on port 22, FTP on port 21. Bekannte Ports, 0 bis 1023: Reserviert für standardmäßige, allgemein bekannte Dienste, zum Beispiel HTTP auf Port 80, HTTPS auf Port 443, SSH auf Port 22, FTP auf Port 21.

On Unix like systems, binding to these ports usually requires administrative privileges. Auf Unix-ähnlichen Systemen erfordert das Binden an diese Ports normalerweise administrative Rechte.

Registered Ports, 1024 to 49151: Used by specific applications and services registered with IANA, Internet Assigned Numbers Authority. Registrierte Ports, 1024 bis 49151: Werden von spezifischen Anwendungen und Diensten verwendet, die bei der IANA, Internet Assigned Numbers Authority, registriert sind.

Dynamic, Private, Ephemeral Ports, 49152 to 65535: Used by client applications as their source port when initiating connections. Dynamische, private, flüchtige Ports, 49152 bis 65535: Werden von Client-Anwendungen als ihr Quellport beim Initiieren von Verbindungen verwendet.

These are typically assigned randomly by the operating system. Diese werden normalerweise zufällig vom Betriebssystem zugewiesen.

Like other protocols, TCP adds its own header to the data it receives from the application layer. Wie andere Protokolle fügt TCP seinen eigenen Header zu den Daten hinzu, die es von der Anwendungsschicht erhält.

This header contains crucial control information. Dieser Header enthält wichtige Steuerungsinformationen.

Here are some key fields: Source Port, 16 bits: Identifies the application port number on the sending host. Hier sind einige wichtige Felder: Quellport, 16 Bit: Identifiziert die Anwendungsportnummer auf dem sendenden Host.

Destination Port, 16 bits: Identifies the application port number on the receiving host. Zielport, 16 Bit: Identifiziert die Anwendungsportnummer auf dem empfangenden Host.

Sequence Number, 32 bits: Used for ordering data and reliability. It identifies the sequence number of the first byte of data in this segment. Sequenznummer, 32 Bit: Wird für die Datenordnung und Zuverlässigkeit verwendet. Sie identifiziert die Sequenznummer des ersten Datenbytes in diesem Segment.

Acknowledgment Number, 32 bits: Used for reliability. If the ACK flag is set, this field contains the sequence number of the next byte the sender of the ACK expects to receive. Bestätigungsnummer, 32 Bit: Wird für die Zuverlässigkeit verwendet. Wenn das ACK-Flag gesetzt ist, enthält dieses Feld die Sequenznummer des nächsten Bytes, das der Absender des ACK zu empfangen erwartet.

Flags, for example SYN, ACK, FIN, RST, PSH, URG: These are single bits used for control purposes. Flags, zum Beispiel SYN, ACK, FIN, RST, PSH, URG: Dies sind einzelne Bits, die für Steuerungszwecke verwendet werden.

SYN: Synchronize sequence numbers, used in handshake. SYN: Sequenznummern synchronisieren, wird beim Handshake verwendet.

ACK: Acknowledgment field is valid. ACK: Bestätigungsfeld ist gültig.

FIN: Finish, sender has no more data to send, used in connection termination. FIN: Fertig, Absender hat keine weiteren Daten zu senden, wird beim Verbindungsabbau verwendet.

RST: Reset the connection, abruptly closes the connection, often due to errors. RST: Verbindung zurücksetzen, schließt die Verbindung abrupt, oft aufgrund von Fehlern.

PSH: Push, tells the receiver to pass the data to the application immediately. PSH: Push, weist den Empfänger an, die Daten sofort an die Anwendung weiterzugeben.

URG: Urgent pointer field is valid, rarely used. URG: Dringendes Zeigerfeld ist gültig, wird selten verwendet.

Window Size, 16 bits: Used for flow control. Specifies the number of bytes the sender of this segment is willing to receive. Fenstergröße, 16 Bit: Wird für die Flusskontrolle verwendet. Gibt die Anzahl der Bytes an, die der Absender dieses Segments bereit ist zu empfangen.

Checksum, 16 bits: Used for error detection. Calculated over the TCP header, TCP data, and parts of the IP header. Prüfsumme, 16 Bit: Wird zur Fehlererkennung verwendet. Wird über den TCP-Header, TCP-Daten und Teile des IP-Headers berechnet.

If the checksum doesn't match upon arrival, the segment is discarded. Wenn die Prüfsumme bei der Ankunft nicht übereinstimmt, wird das Segment verworfen.

Establishment: The three way handshake, SYN, SYN ACK, ACK. Aufbau: Der Drei-Wege-Handshake, SYN, SYN ACK, ACK.

Data Transfer: Segments containing application data are exchanged, with sequence numbers and ACKs ensuring reliability and order. Datenübertragung: Segmente mit Anwendungsdaten werden ausgetauscht, wobei Sequenznummern und ACKs Zuverlässigkeit und Reihenfolge gewährleisten.

Flow and congestion control mechanisms operate during this phase. Fluss- und Staukontrollmechanismen sind während dieser Phase aktiv.

Termination: When an application is finished sending data, it initiates connection closing. Beendigung: Wenn eine Anwendung mit dem Senden von Daten fertig ist, leitet sie das Schließen der Verbindung ein.

This typically involves a four way handshake: Side A sends a FIN segment. Dies beinhaltet typischerweise einen Vier-Wege-Handshake: Seite A sendet ein FIN-Segment.

Side B sends an ACK for Side A's FIN. Seite B sendet ein ACK für das FIN von Seite A.

Side B, when ready to close its side, sends its own FIN segment. Seite B sendet, wenn sie bereit ist ihre Seite zu schließen, ihr eigenes FIN-Segment.

Side A sends an ACK for Side B's FIN. Seite A sendet ein ACK für das FIN von Seite B.

The connection is now closed. A connection can also be abruptly closed using the RST flag. Die Verbindung ist jetzt geschlossen. Eine Verbindung kann auch abrupt mit dem RST-Flag geschlossen werden.

Why is the reliability provided by TCP absolutely essential for web browsing, HTTP or HTTPS, or transferring files, FTP or SFTP, but perhaps less critical, or even detrimental, for applications like live video streaming or online gaming? Warum ist die von TCP bereitgestellte Zuverlässigkeit absolut unverzichtbar für Webbrowsing, HTTP oder HTTPS, oder Dateiübertragung, FTP oder SFTP, aber vielleicht weniger kritisch oder sogar nachteilig für Anwendungen wie Live-Video-Streaming oder Online-Gaming?

What trade offs are being made? Welche Kompromisse werden eingegangen?