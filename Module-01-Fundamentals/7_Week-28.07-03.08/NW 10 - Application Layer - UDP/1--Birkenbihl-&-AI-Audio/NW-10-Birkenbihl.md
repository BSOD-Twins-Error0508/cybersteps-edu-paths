Welcome to the world of User Datagram Protocol, UDP, a core protocol of the Internet's transport layer. Willkommen in der Welt des User Datagram Protocol, UDP, einem Kernprotokoll der Transportschicht des Internets.

Unlike its counterpart TCP, which you might have encountered earlier, UDP takes a different approach to data transmission. Im Gegensatz zu seinem Gegenstück TCP, dem Sie vielleicht schon früher begegnet sind, verfolgt UDP einen anderen Ansatz bei der Datenübertragung.

It prioritizes speed and simplicity over reliability and order. Es priorisiert Geschwindigkeit und Einfachheit über Zuverlässigkeit und Reihenfolge.

This preparation material will introduce you to UDP, its characteristics, how it works, and where it's commonly used. Dieses Vorbereitungsmaterial wird Sie in UDP einführen, seine Eigenschaften, wie es funktioniert und wo es häufig verwendet wird.

The Transport Layer: A Quick Recap Die Transportschicht: Eine kurze Zusammenfassung

Before diving into UDP, let's briefly recall the role of the transport layer in the network model, like the TCP/IP model or OSI model. Bevor wir uns in UDP vertiefen, lassen Sie uns kurz die Rolle der Transportschicht im Netzwerkmodell in Erinnerung rufen, wie dem TCP/IP-Modell oder OSI-Modell.

The transport layer is responsible for logical communication between application processes running on different hosts. Die Transportschicht ist verantwortlich für die logische Kommunikation zwischen Anwendungsprozessen, die auf verschiedenen Hosts laufen.

It takes data from applications, segments it if necessary, and passes it to the network layer. Sie nimmt Daten von Anwendungen, segmentiert sie bei Bedarf und gibt sie an die Netzwerkschicht weiter.

On the receiving end, it reassembles the data and delivers it to the correct application. Auf der Empfangsseite setzt sie die Daten wieder zusammen und liefert sie an die richtige Anwendung.

Two main protocols operate at this layer: TCP, Transmission Control Protocol, and UDP, User Datagram Protocol. Zwei Hauptprotokolle arbeiten auf dieser Schicht: TCP, Transmission Control Protocol, und UDP, User Datagram Protocol.

What is UDP? Was ist UDP?

UDP stands for User Datagram Protocol. UDP steht für User Datagram Protocol.

It's a simple, lightweight, and connectionless protocol. Es ist ein einfaches, leichtgewichtiges und verbindungsloses Protokoll.

Think of it as sending a postcard: you write the message, address it, and drop it in the mail. Stellen Sie es sich vor wie das Versenden einer Postkarte: Sie schreiben die Nachricht, adressieren sie und werfen sie in den Briefkasten.

You don't establish a connection with the recipient beforehand, and you don't get a confirmation when they receive it. Sie stellen vorher keine Verbindung zum Empfänger her, und Sie erhalten keine Bestätigung, wenn er sie erhält.

It might get lost, it might arrive out of order if you send multiple postcards, but it's fast and doesn't involve much overhead. Sie könnte verloren gehen, sie könnte in falscher Reihenfolge ankommen, wenn Sie mehrere Postkarten senden, aber es ist schnell und beinhaltet nicht viel Overhead.

Key characteristics of UDP include: Connectionless: UDP does not establish a connection, no handshake, before sending data. Wichtige Merkmale von UDP sind: Verbindungslos: UDP stellt keine Verbindung her, keinen Handshake, bevor Daten gesendet werden.

Each UDP datagram, a unit of data in UDP, is an independent entity, unrelated to any other datagram. Jedes UDP-Datagramm, eine Dateneinheit in UDP, ist eine unabhängige Einheit, die nichts mit anderen Datagrammen zu tun hat.

Unreliable: UDP provides no guarantee that the data will reach its destination. Unzuverlässig: UDP bietet keine Garantie, dass die Daten ihr Ziel erreichen.

There are no acknowledgments, no retransmission of lost packets, and no built-in mechanisms to ensure data integrity beyond an optional checksum. Es gibt keine Bestätigungen, keine erneute Übertragung verlorener Pakete und keine eingebauten Mechanismen zur Gewährleistung der Datenintegrität über eine optionale Prüfsumme hinaus.

If a datagram is lost, it's lost. Wenn ein Datagramm verloren geht, ist es verloren.

Not Ordered: UDP does not ensure that datagrams arrive in the order they were sent. Nicht geordnet: UDP stellt nicht sicher, dass Datagramme in der Reihenfolge ankommen, in der sie gesendet wurden.

If Application A sends datagram 1, then datagram 2, they might arrive as datagram 2, then datagram 1, or one might not arrive at all. Wenn Anwendung A Datagramm 1 sendet, dann Datagramm 2, könnten sie als Datagramm 2 ankommen, dann Datagramm 1, oder eines kommt vielleicht gar nicht an.

Low Overhead: UDP headers are very small, only 8 bytes, which means less protocol-related data is added to your actual data. Geringer Overhead: UDP-Header sind sehr klein, nur 8 Bytes, was bedeutet, dass weniger protokollbezogene Daten zu Ihren tatsächlichen Daten hinzugefügt werden.

This contributes to its speed. Dies trägt zu seiner Geschwindigkeit bei.

Fast: Because there's no connection setup, no acknowledgments, and minimal header information, UDP is generally faster than TCP for transmitting data. Schnell: Weil es keinen Verbindungsaufbau gibt, keine Bestätigungen und minimale Header-Informationen, ist UDP im Allgemeinen schneller als TCP bei der Datenübertragung.

The UDP Header Der UDP-Header

The simplicity of UDP is reflected in its header structure. Die Einfachheit von UDP spiegelt sich in seiner Header-Struktur wider.

A UDP header is only 8 bytes long and consists of four fields. Ein UDP-Header ist nur 8 Bytes lang und besteht aus vier Feldern.

Source Port, 16 bits: Identifies the port number of the sending application process. Quell-Port, 16 Bit: Identifiziert die Portnummer des sendenden Anwendungsprozesses.

This field is optional, and if not used, it should be set to zero. Dieses Feld ist optional, und wenn es nicht verwendet wird, sollte es auf Null gesetzt werden.

It's important for the receiver if it needs to send a reply. Es ist wichtig für den Empfänger, wenn er eine Antwort senden muss.

Destination Port, 16 bits: Identifies the port number of the receiving application process on the destination host. Ziel-Port, 16 Bit: Identifiziert die Portnummer des empfangenden Anwendungsprozesses auf dem Ziel-Host.

This is a crucial field for delivering the data to the correct application. Dies ist ein entscheidendes Feld für die Zustellung der Daten an die richtige Anwendung.

Length, 16 bits: Specifies the length in bytes of the UDP header and the UDP data, payload. Länge, 16 Bit: Gibt die Länge in Bytes des UDP-Headers und der UDP-Daten, der Nutzlast, an.

The minimum length is 8 bytes, the header itself, with no data. Die Mindestlänge beträgt 8 Bytes, der Header selbst, ohne Daten.

Checksum, 16 bits: Used for error detection. Prüfsumme, 16 Bit: Wird zur Fehlererkennung verwendet.

It calculates a checksum value for the UDP header, the UDP data, and parts of the IP header, pseudo-header. Sie berechnet einen Prüfsummenwert für den UDP-Header, die UDP-Daten und Teile des IP-Headers, den Pseudo-Header.

For IPv4, the checksum is optional. Für IPv4 ist die Prüfsumme optional.

If not used, it's set to all zeros. Wenn sie nicht verwendet wird, wird sie auf alle Nullen gesetzt.

For IPv6, the checksum is mandatory. Für IPv6 ist die Prüfsumme obligatorisch.

If the checksum calculation at the receiver doesn't match the checksum value in the header, the datagram is typically discarded silently. Wenn die Prüfsummenberechnung beim Empfänger nicht mit dem Prüfsummenwert im Header übereinstimmt, wird das Datagramm normalerweise stillschweigend verworfen.

This provides a basic level of integrity checking. Dies bietet ein grundlegendes Maß an Integritätsprüfung.

Think About It: Why do you think the UDP checksum is optional for IPv4 but mandatory for IPv6? Denken Sie darüber nach: Warum glauben Sie, ist die UDP-Prüfsumme für IPv4 optional, aber für IPv6 obligatorisch?

What might have changed in the design philosophy or network environment? Was könnte sich in der Designphilosophie oder der Netzwerkumgebung geändert haben?

Ports Reminder Erinnerung an Ports

Both UDP and TCP use port numbers to differentiate between various application processes running on a single host. Sowohl UDP als auch TCP verwenden Portnummern, um zwischen verschiedenen Anwendungsprozessen zu unterscheiden, die auf einem einzelnen Host laufen.

When data arrives at a host, the transport layer uses the destination port number to pass the data to the correct application. Wenn Daten bei einem Host ankommen, verwendet die Transportschicht die Ziel-Portnummer, um die Daten an die richtige Anwendung weiterzugeben.

Well-Known Ports, 0 to 1023: These are reserved for common services and applications, for example, HTTP uses TCP port 80, DNS uses UDP port 53. Bekannte Ports, 0 bis 1023: Diese sind für gängige Dienste und Anwendungen reserviert, zum Beispiel verwendet HTTP TCP-Port 80, DNS verwendet UDP-Port 53.

Registered Ports, 1024 to 49151: These can be registered by software vendors for specific applications. Registrierte Ports, 1024 bis 49151: Diese können von Software-Herstellern für bestimmte Anwendungen registriert werden.

Dynamic, Private, Ephemeral Ports, 49152 to 65535: These are used for temporary or private connections, often assigned dynamically by the client's operating system when initiating a connection. Dynamische, private, flüchtige Ports, 49152 bis 65535: Diese werden für temporäre oder private Verbindungen verwendet, oft dynamisch vom Betriebssystem des Clients zugewiesen, wenn eine Verbindung eingeleitet wird.

When a client wants to communicate with a server, for example, making a DNS query, the client usually uses a dynamic port as its source port and the well-known port of the service, for example, port 53 for DNS, as the destination port. Wenn ein Client mit einem Server kommunizieren möchte, zum Beispiel eine DNS-Abfrage macht, verwendet der Client normalerweise einen dynamischen Port als seinen Quell-Port und den bekannten Port des Dienstes, zum Beispiel Port 53 für DNS, als Ziel-Port.

When is UDP the Right Choice? Wann ist UDP die richtige Wahl?

Given its best-effort delivery, UDP might seem like a poor choice. Angesichts seiner Best-Effort-Zustellung könnte UDP wie eine schlechte Wahl erscheinen.

However, its speed and low overhead make it ideal for certain types of applications. Allerdings machen seine Geschwindigkeit und sein geringer Overhead es ideal für bestimmte Arten von Anwendungen.

Applications Tolerant of Data Loss: If occasional loss of data is acceptable, or if the application has its own mechanisms for handling errors and retransmissions. Anwendungen, die Datenverlust tolerieren: Wenn gelegentlicher Datenverlust akzeptabel ist oder wenn die Anwendung ihre eigenen Mechanismen zur Fehlerbehandlung und erneuten Übertragung hat.

Real-time Applications: Streaming Media: For live video and audio streaming, for example, online gaming, VoIP like Skype or Zoom, receiving data quickly is more important than receiving every single bit. Echtzeit-Anwendungen: Streaming-Medien: Für Live-Video- und Audio-Streaming, zum Beispiel Online-Gaming, VoIP wie Skype oder Zoom, ist es wichtiger, Daten schnell zu empfangen als jedes einzelne Bit zu empfangen.

A lost frame in a video stream or a slight glitch in audio is often preferable to a long delay caused by retransmissions. Ein verlorenes Bild in einem Videostream oder ein leichter Fehler im Audio ist oft einem langen Verzögerung durch erneute Übertragungen vorzuziehen.

Online Gaming: Fast updates are crucial. Online-Gaming: Schnelle Updates sind entscheidend.

Old data is often useless. Alte Daten sind oft nutzlos.

Query-Response Protocols: DNS, Domain Name System: DNS queries are typically small and expect a quick response. Anfrage-Antwort-Protokolle: DNS, Domain Name System: DNS-Abfragen sind normalerweise klein und erwarten eine schnelle Antwort.

If a query is lost, the client can simply resend it. Wenn eine Abfrage verloren geht, kann der Client sie einfach erneut senden.

Using UDP keeps DNS fast. Die Verwendung von UDP hält DNS schnell.

DHCP, Dynamic Host Configuration Protocol: Used for obtaining IP addresses. DHCP, Dynamic Host Configuration Protocol: Wird zum Erhalten von IP-Adressen verwendet.

It operates in a local network where packet loss is generally low. Es arbeitet in einem lokalen Netzwerk, wo Paketverlust im Allgemeinen gering ist.

Multicasting, Broadcasting: UDP supports sending a single datagram to multiple recipients, multicast, or all recipients on a subnet, broadcast, efficiently. Multicasting, Broadcasting: UDP unterstützt das effiziente Senden eines einzelnen Datagramms an mehrere Empfänger, Multicast, oder alle Empfänger in einem Subnetz, Broadcast.

TCP is designed for one-to-one communication. TCP ist für Eins-zu-Eins-Kommunikation ausgelegt.

TFTP, Trivial File Transfer Protocol: A simplified version of FTP that uses UDP. TFTP, Trivial File Transfer Protocol: Eine vereinfachte Version von FTP, die UDP verwendet.

It's often used for booting diskless workstations or transferring firmware to network devices. Es wird oft zum Booten von festplattenlosen Workstations oder zum Übertragen von Firmware auf Netzwerkgeräte verwendet.

SNMP, Simple Network Management Protocol: Used for managing and monitoring network devices. SNMP, Simple Network Management Protocol: Wird zur Verwaltung und Überwachung von Netzwerkgeräten verwendet.

Try It Yourself: Think about the applications you use daily. Probieren Sie es selbst: Denken Sie an die Anwendungen, die Sie täglich verwenden.

Which ones do you think might be using UDP? Welche könnten Ihrer Meinung nach UDP verwenden?

For each, why would UDP be a suitable choice, or not? Warum wäre UDP für jede eine geeignete Wahl oder nicht?

Consider what would happen if some data packets were lost or arrived out of order. Überlegen Sie, was passieren würde, wenn einige Datenpakete verloren gingen oder in falscher Reihenfolge ankämen.

UDP vs. TCP: A Quick Comparison UDP versus TCP: Ein schneller Vergleich

Connection: UDP is Connectionless, TCP is Connection-oriented. Verbindung: UDP ist verbindungslos, TCP ist verbindungsorientiert.

Reliability: UDP is Unreliable, best-effort delivery, TCP is Reliable, guaranteed delivery. Zuverlässigkeit: UDP ist unzuverlässig, Best-Effort-Zustellung, TCP ist zuverlässig, garantierte Zustellung.

Ordering: UDP is Not guaranteed, TCP is Guaranteed in-order delivery. Reihenfolge: UDP ist nicht garantiert, TCP ist garantierte Zustellung in richtiger Reihenfolge.

Overhead: UDP is Low, 8-byte header, TCP is Higher, 20-byte header minimum. Overhead: UDP ist gering, 8-Byte-Header, TCP ist höher, mindestens 20-Byte-Header.

Speed: UDP is Generally faster, TCP is Slower due to connection setup and acknowledgments. Geschwindigkeit: UDP ist im Allgemeinen schneller, TCP ist langsamer aufgrund von Verbindungsaufbau und Bestätigungen.

Flow Control: UDP has No flow control, TCP has Yes. Flusskontrolle: UDP hat keine Flusskontrolle, TCP hat sie.

Congestion Control: UDP has No congestion control, TCP has Yes. Überlastkontrolle: UDP hat keine Überlastkontrolle, TCP hat sie.

Use Cases: UDP is for DNS, DHCP, VoIP, streaming, gaming, TCP is for Web, HTTP/S, email, SMTP, FTP. Anwendungsfälle: UDP ist für DNS, DHCP, VoIP, Streaming, Gaming, TCP ist für Web, HTTP/S, E-Mail, SMTP, FTP.

What Happens to Lost UDP Packets? Was passiert mit verlorenen UDP-Paketen?

Simply put, they are gone. Einfach gesagt, sie sind weg.

UDP itself does not attempt to recover lost packets. UDP selbst versucht nicht, verlorene Pakete wiederherzustellen.

It's up to the application layer to deal with this, if necessary. Es liegt an der Anwendungsschicht, sich damit zu befassen, falls nötig.

For example: A DNS client will typically time out and resend the query if it doesn't receive a response. Zum Beispiel: Ein DNS-Client wird normalerweise eine Zeitüberschreitung haben und die Anfrage erneut senden, wenn er keine Antwort erhält.

A VoIP application might just accept a momentary glitch in the audio. Eine VoIP-Anwendung könnte einfach einen momentanen Fehler im Audio akzeptieren.

It won't try to recover the lost audio packet because, by the time it could be retransmitted, the conversation would have moved on, and the old audio would be irrelevant. Sie wird nicht versuchen, das verlorene Audio-Paket wiederherzustellen, denn zu dem Zeitpunkt, zu dem es erneut übertragen werden könnte, wäre das Gespräch weitergegangen und das alte Audio wäre irrelevant.

This application-level recovery is a common pattern for services built on UDP that require some form of reliability but still want the benefits of UDP's low overhead. Diese Wiederherstellung auf Anwendungsebene ist ein gängiges Muster für Dienste, die auf UDP basieren, die eine Form von Zuverlässigkeit benötigen, aber dennoch die Vorteile des geringen Overheads von UDP nutzen möchten.

Think About It: Consider a video streaming service. Denken Sie darüber nach: Betrachten Sie einen Video-Streaming-Dienst.

If it uses UDP and a packet is lost, what do you see? Wenn er UDP verwendet und ein Paket verloren geht, was sehen Sie?

How might the application try to make this less jarring for the user, even without UDP retransmitting the packet? Wie könnte die Anwendung versuchen, dies für den Benutzer weniger störend zu machen, auch ohne dass UDP das Paket erneut überträgt?

This pre-class material should give you a solid foundation on UDP. Dieses Vorbereitungsmaterial sollte Ihnen eine solide Grundlage zu UDP geben.

We will explore these concepts further, look at UDP in action, and discuss its security implications in the live session. Wir werden diese Konzepte weiter erforschen, UDP in Aktion betrachten und seine Sicherheitsauswirkungen in der Live-Sitzung diskutieren.