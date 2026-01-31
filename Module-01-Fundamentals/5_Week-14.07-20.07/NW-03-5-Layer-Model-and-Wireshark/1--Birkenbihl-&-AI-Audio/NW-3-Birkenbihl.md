Welcome! Before our next session, let's explore how network communication is structured and introduce a powerful tool for observing it. Willkommen! Vor unserer nächsten Sitzung wollen wir erkunden, wie Netzwerkkommunikation strukturiert ist und ein mächtiges Werkzeug zu ihrer Beobachtung vorstellen.

This preparation should take about 45 minutes. Diese Vorbereitung sollte etwa 45 Minuten dauern.

The Need for Structure: Network Models. Die Notwendigkeit für Struktur: Netzwerkmodelle.

Why do we need models to describe computer networks? Warum brauchen wir Modelle, um Computernetzwerke zu beschreiben?

Sending data seems simple, like sending an email or loading a webpage. Das Senden von Daten erscheint einfach, wie das Versenden einer E-Mail oder das Laden einer Webseite.

However, beneath the surface, countless complex interactions occur across different hardware and software components, potentially spanning the globe. Doch unter der Oberfläche finden zahllose komplexe Interaktionen über verschiedene Hardware- und Softwarekomponenten hinweg statt, die sich möglicherweise über den ganzen Globus erstrecken.

Without a standardized structure, we would face several challenges. Ohne eine standardisierte Struktur würden wir mehreren Herausforderungen gegenüberstehen.

First, complexity. Managing the entire process from application click to data arriving across the world would be incredibly difficult. Erstens, Komplexität. Die Verwaltung des gesamten Prozesses vom Klick in der Anwendung bis zur Ankunft der Daten auf der anderen Seite der Welt wäre unglaublich schwierig.

How would your browser know how to talk to a specific web server through potentially dozens of intermediate devices? Wie würde Ihr Browser wissen, wie er mit einem bestimmten Webserver durch potenziell Dutzende von Zwischengeräten kommunizieren soll?

Second, interoperability. How could a Mac computer reliably communicate with a Linux server if they didn't agree on common rules? Zweitens, Interoperabilität. Wie könnte ein Mac-Computer zuverlässig mit einem Linux-Server kommunizieren, wenn sie sich nicht auf gemeinsame Regeln einigen würden?

Different vendors and technologies need a shared framework to ensure their products can work together. Verschiedene Anbieter und Technologien benötigen ein gemeinsames Framework, um sicherzustellen, dass ihre Produkte zusammenarbeiten können.

Third, development and innovation. If every application developer had to reinvent the entire process of network transmission, innovation would slow dramatically. Drittens, Entwicklung und Innovation. Wenn jeder Anwendungsentwickler den gesamten Prozess der Netzwerkübertragung neu erfinden müsste, würde sich die Innovation dramatisch verlangsamen.

Models allow developers to focus on their specific layer, for example building a better web browser, without worrying about the underlying details of fiber optic transmission. Modelle ermöglichen es Entwicklern, sich auf ihre spezifische Schicht zu konzentrieren, zum Beispiel den Bau eines besseren Webbrowsers, ohne sich um die zugrunde liegenden Details der Glasfaserübertragung sorgen zu müssen.

Fourth, troubleshooting. When something goes wrong, for example a website won't load, a layered model helps isolate the problem. Viertens, Fehlerbehebung. Wenn etwas schief geht, zum Beispiel eine Webseite nicht lädt, hilft ein geschichtetes Modell, das Problem zu isolieren.

Is it an issue with the physical cable? The IP address? The application itself? Ist es ein Problem mit dem physischen Kabel? Der IP-Adresse? Der Anwendung selbst?

Network models, like blueprints for communication, solve these problems by dividing the complex task of networking into smaller, manageable layers. Netzwerkmodelle, wie Baupläne für Kommunikation, lösen diese Probleme, indem sie die komplexe Aufgabe des Networking in kleinere, handhabbare Schichten aufteilen.

Each layer has specific responsibilities and interacts only with the layers directly above and below it. Jede Schicht hat spezifische Verantwortlichkeiten und interagiert nur mit den Schichten direkt über und unter ihr.

This modular approach brings order, promotes standardization, and simplifies both development and troubleshooting. Dieser modulare Ansatz bringt Ordnung, fördert Standardisierung und vereinfacht sowohl Entwicklung als auch Fehlerbehebung.

While several models exist, the two most referenced are the OSI Model and the TCP/IP Model. Während mehrere Modelle existieren, sind die beiden am häufigsten referenzierten das OSI-Modell und das TCP/IP-Modell.

OSI, or Open Systems Interconnection Model, is a 7-layer conceptual model published by the International Organization for Standardization, or ISO. OSI, oder Open Systems Interconnection Model, ist ein 7-Schichten-Konzeptmodell, das von der International Organization for Standardization, oder ISO, veröffentlicht wurde.

It's very detailed and excellent for understanding the theory of networking, but not always directly implemented in its full 7-layer form. Es ist sehr detailliert und hervorragend zum Verständnis der Theorie des Networking geeignet, wird aber nicht immer direkt in seiner vollständigen 7-Schichten-Form implementiert.

TCP/IP Model is a more practical model that closely reflects the actual implementation of the internet protocols, TCP and IP. Das TCP/IP-Modell ist ein praktischeres Modell, das die tatsächliche Implementierung der Internetprotokolle TCP und IP genau widerspiegelt.

It's often described with 4 or 5 layers. We will focus on a common 5-Layer TCP/IP Model as it provides a good balance of detail and practical relevance for cybersecurity work. Es wird oft mit 4 oder 5 Schichten beschrieben. Wir werden uns auf ein gängiges 5-Schichten-TCP/IP-Modell konzentrieren, da es ein gutes Gleichgewicht zwischen Detail und praktischer Relevanz für Cybersicherheitsarbeit bietet.

The 5-Layer TCP/IP Model. Das 5-Schichten-TCP/IP-Modell.

This model provides a practical framework for understanding how data travels from an application on one computer to an application on another computer across a network. Dieses Modell bietet ein praktisches Framework zum Verständnis, wie Daten von einer Anwendung auf einem Computer zu einer Anwendung auf einem anderen Computer über ein Netzwerk reisen.

Let's use the analogy of sending a physical letter or package. Lassen Sie uns die Analogie des Versendens eines physischen Briefes oder Pakets verwenden.

Layer 1: Application Layer. Schicht 1: Anwendungsschicht.

Purpose: Provides the interface for software to use network services. This is where user-facing protocols operate. Zweck: Bietet die Schnittstelle für Software, um Netzwerkdienste zu nutzen. Hier operieren benutzerseitige Protokolle.

Analogy for physical mail: This is like writing the actual letter or preparing the contents of the package. Analogie für physische Post: Dies ist wie das Schreiben des eigentlichen Briefes oder die Vorbereitung des Inhalts des Pakets.

You decide what information to send, the email message, the request for a webpage, and its purpose, personal letter, business order. Sie entscheiden, welche Informationen Sie senden, die E-Mail-Nachricht, die Anfrage nach einer Webseite und ihren Zweck, persönlicher Brief, Geschäftsbestellung.

The application formats this data. Die Anwendung formatiert diese Daten.

Examples: HTTP or HTTPS for browsing, SMTP for email, DNS for address lookup. Beispiele: HTTP oder HTTPS zum Browsen, SMTP für E-Mail, DNS für Adresssuche.

Data Unit: Often simply called "Data" or "Message". Dateneinheit: Oft einfach "Daten" oder "Nachricht" genannt.

Layer 2: Transport Layer. Schicht 2: Transportschicht.

Purpose: Responsible for process-to-process communication, getting data to the correct application on the destination host, and managing the quality of the connection, reliability, flow control. Zweck: Verantwortlich für Prozess-zu-Prozess-Kommunikation, das Übermitteln von Daten an die richtige Anwendung auf dem Zielhost und die Verwaltung der Verbindungsqualität, Zuverlässigkeit, Flusskontrolle.

Analogy for physical mail: This is like choosing the shipping service and preparing the package for the specific recipient within the destination building. Analogie für physische Post: Dies ist wie die Wahl des Versanddienstes und die Vorbereitung des Pakets für den spezifischen Empfänger innerhalb des Zielgebäudes.

You decide if you need tracking and delivery confirmation, like TCP, using registered mail, or if standard, faster, but less guaranteed delivery is okay, like UDP, using a standard postcard. Sie entscheiden, ob Sie Sendungsverfolgung und Zustellbestätigung benötigen, wie TCP, mit Einschreiben, oder ob Standard, schneller, aber weniger garantierte Zustellung in Ordnung ist, wie UDP, mit einer Standard-Postkarte.

You also specify the department or person, the port number, within the destination address, ensuring it reaches the correct end-point inside the building or computer. Sie geben auch die Abteilung oder Person, die Portnummer, innerhalb der Zieladresse an, um sicherzustellen, dass es den richtigen Endpunkt innerhalb des Gebäudes oder Computers erreicht.

Key Protocols: TCP, Transmission Control Protocol, UDP, User Datagram Protocol. Hauptprotokolle: TCP, Transmission Control Protocol, UDP, User Datagram Protocol.

Data Unit: Segment for TCP or Datagram for UDP. Dateneinheit: Segment für TCP oder Datagramm für UDP.

Layer 3: Network Layer, or Internet Layer. Schicht 3: Netzwerkschicht oder Internetschicht.

Purpose: Responsible for logical addressing, IP addresses, and routing data packets across different networks, internetworking. Zweck: Verantwortlich für logische Adressierung, IP-Adressen und das Routing von Datenpaketen über verschiedene Netzwerke, Internetworking.

It finds the best path from the source computer to the destination computer. Sie findet den besten Pfad vom Quellcomputer zum Zielcomputer.

Analogy for physical mail: This is like writing the full destination address, street, city, zip code, like the IP address, and the return address on the envelope or package. Analogie für physische Post: Dies ist wie das Schreiben der vollständigen Zieladresse, Straße, Stadt, Postleitzahl, wie die IP-Adresse, und der Rücksendeadresse auf dem Umschlag oder Paket.

The postal service uses this global address to figure out the route across cities and countries to get the package to the correct destination city or town. Der Postdienst verwendet diese globale Adresse, um die Route über Städte und Länder zu ermitteln, um das Paket in die richtige Zielstadt oder den richtigen Zielort zu bringen.

Key Protocols: IP, Internet Protocol, ICMP, Internet Control Message Protocol. Hauptprotokolle: IP, Internet Protocol, ICMP, Internet Control Message Protocol.

Data Unit: Packet. Dateneinheit: Paket.

Layer 4: Data Link Layer. Schicht 4: Sicherungsschicht.

Purpose: Responsible for transferring data between devices on the same local network segment, like your home Wi-Fi or an office Ethernet network. Zweck: Verantwortlich für die Übertragung von Daten zwischen Geräten im selben lokalen Netzwerksegment, wie Ihrem Heim-Wi-Fi oder einem Büro-Ethernet-Netzwerk.

It uses physical addresses, MAC addresses, and manages access to the shared physical medium. Sie verwendet physische Adressen, MAC-Adressen, und verwaltet den Zugriff auf das gemeinsam genutzte physische Medium.

Analogy for physical mail: This is the local mail carrier delivering the package on their specific route. Analogie für physische Post: Dies ist der lokale Postbote, der das Paket auf seiner spezifischen Route zustellt.

They use the specific house number, like the MAC address, to deliver the package to the correct physical building on that street segment or local network. Sie verwenden die spezifische Hausnummer, wie die MAC-Adresse, um das Paket an das richtige physische Gebäude in diesem Straßensegment oder lokalen Netzwerk zuzustellen.

This layer handles the rules for accessing the local road, for example Ethernet or Wi-Fi rules. Diese Schicht behandelt die Regeln für den Zugriff auf die lokale Straße, zum Beispiel Ethernet- oder Wi-Fi-Regeln.

Key Protocols: Ethernet, Wi-Fi 802.11, ARP, Address Resolution Protocol. Hauptprotokolle: Ethernet, Wi-Fi 802.11, ARP, Address Resolution Protocol.

Data Unit: Frame. Dateneinheit: Frame.

Layer 5: Physical Layer. Schicht 5: Physische Schicht.

Purpose: Responsible for the actual transmission and reception of raw bits, zeros and ones, over the physical medium, cables, radio waves. Zweck: Verantwortlich für die tatsächliche Übertragung und den Empfang von rohen Bits, Nullen und Einsen, über das physische Medium, Kabel, Radiowellen.

It defines the physical characteristics of the connection. Sie definiert die physischen Eigenschaften der Verbindung.

Analogy for physical mail: This represents the physical infrastructure used for transport, the actual roads, mail trucks, airplanes, mailbags, the paper of the letter, and the physical act of moving the mail from one point to the next. Analogie für physische Post: Dies repräsentiert die physische Infrastruktur, die für den Transport verwendet wird, die tatsächlichen Straßen, Postwagen, Flugzeuge, Postsäcke, das Papier des Briefes und den physischen Akt, die Post von einem Punkt zum nächsten zu bewegen.

Examples: Ethernet cables, Wi-Fi radio waves, fiber optic cables, connectors, voltage levels. Beispiele: Ethernet-Kabel, Wi-Fi-Radiowellen, Glasfaserkabel, Steckverbinder, Spannungspegel.

Data Unit: Bits. Dateneinheit: Bits.

Encapsulation and Decapsulation. Verkapselung und Entkapselung.

A crucial concept is encapsulation. Ein entscheidendes Konzept ist die Verkapselung.

Using our mail analogy: you write the letter, application data, put it in a service envelope specifying the department or port, transport header. Mit unserer Post-Analogie: Sie schreiben den Brief, Anwendungsdaten, legen ihn in einen Dienstumschlag, der die Abteilung oder den Port angibt, Transport-Header.

You put that envelope into a larger one with the full street, city, zip address, network header. Sie legen diesen Umschlag in einen größeren mit der vollständigen Straßen-, Stadt-, Postleitzahladresse, Netzwerk-Header.

And finally, the local mail carrier puts this into their mailbag marked for the specific house number on their route, data link header or trailer. Und schließlich legt der lokale Postbote dies in seinen Postsack, der für die spezifische Hausnummer auf seiner Route markiert ist, Sicherungsschicht-Header oder -Trailer.

Each step adds necessary information for that stage of the journey. Jeder Schritt fügt notwendige Informationen für diese Phase der Reise hinzu.

On the receiving end, decapsulation occurs. Auf der Empfangsseite findet Entkapselung statt.

The local carrier delivers the mailbag, data link, the building's mailroom opens it and finds the envelope with the full address, network. Der lokale Postbote liefert den Postsack, Sicherungsschicht, die Poststelle des Gebäudes öffnet ihn und findet den Umschlag mit der vollständigen Adresse, Netzwerkschicht.

They route it internally based on the service envelope, transport, and finally, the recipient opens the letter, application. Sie leiten es intern weiter basierend auf dem Dienstumschlag, Transportschicht, und schließlich öffnet der Empfänger den Brief, Anwendungsschicht.

Each layer processes and removes its own information before passing the contents up. Jede Schicht verarbeitet und entfernt ihre eigenen Informationen, bevor sie den Inhalt nach oben weitergibt.

Think about it. Denken Sie darüber nach.

How does the layered approach help in troubleshooting? Wie hilft der geschichtete Ansatz bei der Fehlerbehebung?

If a letter never arrives, was the address wrong, network layer? Wenn ein Brief nie ankommt, war die Adresse falsch, Netzwerkschicht?

Did the local carrier lose it, data link layer? Hat der lokale Postbote ihn verloren, Sicherungsschicht?

Was the road blocked, physical layer? War die Straße blockiert, physische Schicht?

Or did you forget to put it in the mailbox, application or transport layer? Oder haben Sie vergessen, ihn in den Briefkasten zu legen, Anwendungs- oder Transportschicht?

Introduction to Wireshark. Einführung in Wireshark.

How can we actually see this layered communication happening? Wie können wir diese geschichtete Kommunikation tatsächlich sehen?

We use a network protocol analyzer, commonly called a "packet sniffer". Wir verwenden einen Netzwerkprotokoll-Analysator, allgemein als "Packet Sniffer" bezeichnet.

The most popular and powerful free tool for this is Wireshark. Das beliebteste und mächtigste kostenlose Werkzeug hierfür ist Wireshark.

Wireshark captures the network traffic arriving at or leaving your computer's network interface. Wireshark erfasst den Netzwerkverkehr, der an der Netzwerkschnittstelle Ihres Computers ankommt oder diese verlässt.

It then decodes this traffic, displaying the details of each packet and sorting the information according to the protocol layers, like our 5-layer model. Es dekodiert dann diesen Verkehr, zeigt die Details jedes Pakets an und sortiert die Informationen gemäß den Protokollschichten, wie unser 5-Schichten-Modell.

Think of it as having special glasses that let you see all the envelopes, addresses, and delivery instructions for every piece of data mail passing by. Stellen Sie es sich vor wie eine Spezialbrille, die es Ihnen ermöglicht, alle Umschläge, Adressen und Zustellanweisungen für jedes Stück Datenpost zu sehen, das vorbeikommt.

This allows you to see the headers added at each layer, Ethernet, IP, TCP or UDP, and so on. Dies ermöglicht es Ihnen, die Header zu sehen, die auf jeder Schicht hinzugefügt werden, Ethernet, IP, TCP oder UDP und so weiter.

You can analyze protocol behavior, for example watch the TCP handshake. Sie können Protokollverhalten analysieren, zum Beispiel den TCP-Handshake beobachten.

You can troubleshoot network problems, why can't I reach this website? Sie können Netzwerkprobleme beheben, warum kann ich diese Webseite nicht erreichen?

You can learn how network protocols work in detail. Sie können im Detail lernen, wie Netzwerkprotokolle funktionieren.

And you can identify potentially malicious activity. Und Sie können potenziell bösartige Aktivitäten identifizieren.

In cybersecurity, Wireshark is an indispensable tool for understanding network communications, analyzing malware traffic, investigating incidents, and testing network security. In der Cybersicherheit ist Wireshark ein unverzichtbares Werkzeug zum Verständnis von Netzwerkkommunikation, zur Analyse von Malware-Verkehr, zur Untersuchung von Vorfällen und zum Testen der Netzwerksicherheit.

Try it yourself. Probieren Sie es selbst aus.

Think about sending an email with a large attachment. Denken Sie an das Versenden einer E-Mail mit einem großen Anhang.

Using the mail analogy, how does encapsulation work? Mit der Post-Analogie, wie funktioniert Verkapselung?

Which layer might be responsible for breaking the large attachment data into smaller, numbered packages to ensure they all arrive and can be reassembled correctly? Welche Schicht könnte dafür verantwortlich sein, die großen Anhangdaten in kleinere, nummerierte Pakete aufzuteilen, um sicherzustellen, dass sie alle ankommen und korrekt wieder zusammengesetzt werden können?

Hint: Think about reliability. Hinweis: Denken Sie an Zuverlässigkeit.

Setup: Installing Wireshark on macOS. Einrichtung: Installation von Wireshark auf macOS.

Before our live session, please install Wireshark. Vor unserer Live-Sitzung installieren Sie bitte Wireshark.

Step 1: Download. Go to the official Wireshark download page: https://www.wireshark.org/download.html Schritt 1: Herunterladen. Gehen Sie zur offiziellen Wireshark-Download-Seite: https://www.wireshark.org/download.html

Step 2: Select Installer. Find the macOS Arm .dmg installer. Schritt 2: Installer auswählen. Finden Sie den macOS Arm .dmg Installer.

Step 3: Install. Open the downloaded .dmg file. Drag the Wireshark icon into your Applications folder. Schritt 3: Installieren. Öffnen Sie die heruntergeladene .dmg-Datei. Ziehen Sie das Wireshark-Symbol in Ihren Anwendungsordner.

Step 4: Install ChmodBPF for capture permissions. Schritt 4: Installieren Sie ChmodBPF für Erfassungsberechtigungen.

The .dmg file also contains a package named "Install ChmodBPF.pkg". Die .dmg-Datei enthält auch ein Paket namens "Install ChmodBPF.pkg".

Double-click this package and follow the installation prompts. Doppelklicken Sie auf dieses Paket und folgen Sie den Installationsanweisungen.

This component is necessary for Wireshark to capture live network traffic without requiring you to run Wireshark as the root user, which is generally discouraged for security reasons. Diese Komponente ist notwendig, damit Wireshark Live-Netzwerkverkehr erfassen kann, ohne dass Sie Wireshark als Root-Benutzer ausführen müssen, was aus Sicherheitsgründen generell nicht empfohlen wird.

You will likely need to enter your administrator password during this installation. Sie werden wahrscheinlich Ihr Administratorpasswort während dieser Installation eingeben müssen.

Step 5: Allow System Extension if prompted. Schritt 5: Systemerweiterung erlauben, wenn dazu aufgefordert.

macOS might ask for permission to allow the system extension related to ChmodBPF or Wireshark's capture components. macOS könnte um Erlaubnis bitten, die Systemerweiterung im Zusammenhang mit ChmodBPF oder Wiresharks Erfassungskomponenten zuzulassen.

Go to System Settings, Privacy and Security, and allow it if prompted. Gehen Sie zu Systemeinstellungen, Datenschutz und Sicherheit, und erlauben Sie es, wenn dazu aufgefordert.

You might need to restart your Mac after allowing the extension. Sie müssen möglicherweise Ihren Mac neu starten, nachdem Sie die Erweiterung erlaubt haben.

Step 6: Run Wireshark. Launch Wireshark from your Applications folder. Schritt 6: Wireshark ausführen. Starten Sie Wireshark aus Ihrem Anwendungsordner.

It might perform an initial setup or ask for permissions again on the first run. Es könnte eine anfängliche Einrichtung durchführen oder beim ersten Start erneut nach Berechtigungen fragen.

You don't need to use Wireshark extensively yet, just ensure it's installed and launches without errors. Sie müssen Wireshark noch nicht ausgiebig verwenden, stellen Sie nur sicher, dass es installiert ist und ohne Fehler startet.

We will explore its interface together in the live session. Wir werden seine Benutzeroberfläche gemeinsam in der Live-Sitzung erkunden.

That's it for the pre-class preparation. Das war's für die Vorbereitung vor dem Unterricht.

Make sure you have Wireshark installed, and reflect on the purpose of the 5-layer model using the physical mail analogy. Stellen Sie sicher, dass Sie Wireshark installiert haben, und denken Sie über den Zweck des 5-Schichten-Modells anhand der physischen Post-Analogie nach.

See you in the session! Wir sehen uns in der Sitzung!

The slides for the live session can be viewed here. Try not to peek before class, spoilers inside! Die Folien für die Live-Sitzung können hier angesehen werden. Versuchen Sie nicht, vor dem Unterricht zu spähen, Spoiler enthalten!