In our previous session, we captured our first network packets with Wireshark and learned how basic display filters help us start making sense of the traffic. In unserer vorherigen Sitzung haben wir unsere ersten Netzwerkpakete mit Wireshark aufgezeichnet und gelernt, wie grundlegende Anzeigefilter uns helfen, den Datenverkehr zu verstehen.

We saw the raw data, but now we need better tools to analyze it effectively. Wir haben die Rohdaten gesehen, aber jetzt brauchen wir bessere Werkzeuge, um sie effektiv zu analysieren.

Network captures can quickly grow to immense sizes. Netzwerkaufzeichnungen können schnell immens groß werden.

To find the information that matters, we need to move beyond simple filters. Um die wichtigen Informationen zu finden, müssen wir über einfache Filter hinausgehen.

This session introduces more advanced Wireshark features that let you precisely filter traffic, reconstruct full conversations from individual packets, get high-level statistical summaries of network activity, and even extract files directly from network traffic. Diese Sitzung führt fortgeschrittenere Wireshark-Funktionen ein, die es dir ermöglichen, Datenverkehr präzise zu filtern, vollständige Konversationen aus einzelnen Paketen zu rekonstruieren, statistische Zusammenfassungen auf hoher Ebene der Netzwerkaktivität zu erhalten und sogar Dateien direkt aus dem Netzwerkverkehr zu extrahieren.

Think of it as upgrading from a magnifying glass to a full analysis toolkit. Stell es dir vor wie ein Upgrade von einer Lupe zu einem vollständigen Analyse-Toolkit.

Refining Your View: Advanced Display Filters and Finding Packets. Deine Ansicht verfeinern: Erweiterte Anzeigefilter und Pakete finden.

Simple filters are often just the starting point. Einfache Filter sind oft nur der Ausgangspunkt.

Combining Conditions: Use logical operators. Bedingungen kombinieren: Verwende logische Operatoren.

And matches packets meeting both conditions. Und findet Pakete, die beide Bedingungen erfüllen.

Or matches packets meeting either condition. Oder findet Pakete, die eine der beiden Bedingungen erfüllen.

Not excludes packets matching a condition. Nicht schließt Pakete aus, die eine Bedingung erfüllen.

Use parentheses for clarity, especially with not. Verwende Klammern zur Klarheit, besonders bei nicht.

Using Comparisons: Go beyond simple equality with operators like not equal, greater than, less than, greater than or equal to, less than or equal to. Vergleiche verwenden: Gehe über einfache Gleichheit hinaus mit Operatoren wie ungleich, größer als, kleiner als, größer oder gleich, kleiner oder gleich.

Example: frame length greater than 1000 shows packets larger than 1000 bytes. Beispiel: Frame-Länge größer als 1000 zeigt Pakete, die größer als 1000 Bytes sind.

TCP flags reset equals 1 finds TCP Reset packets. TCP-Flags Reset gleich 1 findet TCP-Reset-Pakete.

Filtering on Specific Fields: Target any dissected field identified by Wireshark. Filtern nach spezifischen Feldern: Ziele auf jedes von Wireshark identifizierte analysierte Feld ab.

Use the right-click, Apply as Filter option in the Packet Details pane to easily learn the syntax for a field you're interested in. Verwende die Rechtsklick-Option „Als Filter anwenden" im Paketdetails-Bereich, um die Syntax für ein Feld, das dich interessiert, einfach zu lernen.

Finding Specific Packets: Sometimes filtering isn't enough, or you want to quickly jump to a specific piece of data. Spezifische Pakete finden: Manchmal reicht Filtern nicht aus, oder du möchtest schnell zu einem bestimmten Datenelement springen.

Use the Find Packet feature. Verwende die Funktion „Paket finden".

This lets you search through the currently displayed packets for a specific display filter expression, a hex value searching the raw byte data, or a string searching the raw byte data, case-sensitive or insensitive. Dies ermöglicht es dir, durch die aktuell angezeigten Pakete nach einem bestimmten Anzeigefilter-Ausdruck, einem Hex-Wert in den rohen Byte-Daten oder einer Zeichenfolge in den rohen Byte-Daten zu suchen, groß- und kleinschreibungssensitiv oder nicht.

This is excellent for finding specific usernames, error messages, filenames, or other text data within packets. Dies ist hervorragend geeignet, um spezifische Benutzernamen, Fehlermeldungen, Dateinamen oder andere Textdaten innerhalb von Paketen zu finden.

Try it yourself. Probiere es selbst aus.

Open Wireshark. Öffne Wireshark.

Type a combined filter into the display filter bar, like IP address equals 8.8.8.8 or IP address equals 1.1.1.1. Gib einen kombinierten Filter in die Anzeigefilterleiste ein, wie IP-Adresse gleich 8.8.8.8 oder IP-Adresse gleich 1.1.1.1.

Notice the bar stays green if the syntax is correct. Beachte, dass die Leiste grün bleibt, wenn die Syntax korrekt ist.

Load a capture file if you have one, or capture some traffic. Lade eine Aufzeichnungsdatei, falls du eine hast, oder zeichne etwas Datenverkehr auf.

Use Command F to search for a string you expect might be in the traffic, for example google if you visited google.com, or GET for HTTP traffic. Verwende Befehlstaste F, um nach einer Zeichenfolge zu suchen, die du im Datenverkehr erwartest, zum Beispiel google, wenn du google.com besucht hast, oder GET für HTTP-Verkehr.

Reconstructing Conversations: Following Protocol Streams. Konversationen rekonstruieren: Protokoll-Streams folgen.

Network applications communicate via streams of data, often broken into many small packets. Netzwerkanwendungen kommunizieren über Datenströme, die oft in viele kleine Pakete aufgeteilt sind.

Trying to read a web page or understand a file transfer by looking at individual packets is impractical. Zu versuchen, eine Webseite zu lesen oder einen Dateitransfer zu verstehen, indem man einzelne Pakete betrachtet, ist unpraktisch.

Wireshark's Follow Stream feature reconstructs the application-level data for specific conversations. Wiresharks „Follow Stream"-Funktion rekonstruiert die Daten auf Anwendungsebene für bestimmte Konversationen.

How to access it: Right-click a packet belonging to a TCP, UDP, HTTP, or TLS/SSL conversation, then Follow, then Protocol Stream. So greifst du darauf zu: Rechtsklicke auf ein Paket, das zu einer TCP-, UDP-, HTTP- oder TLS/SSL-Konversation gehört, dann Follow, dann Protokoll-Stream.

This opens a new window showing the reassembled data flow, such as the complete HTTP requests and responses between a client and server. Dies öffnet ein neues Fenster, das den wieder zusammengesetzten Datenfluss zeigt, wie zum Beispiel die vollständigen HTTP-Anfragen und -Antworten zwischen einem Client und einem Server.

It's essential for understanding what was actually communicated at the application layer. Es ist wesentlich, um zu verstehen, was tatsächlich auf der Anwendungsebene kommuniziert wurde.

Summarizing Traffic: Wireshark Statistics. Datenverkehr zusammenfassen: Wireshark-Statistiken.

Before diving into individual packets, or after filtering down the traffic, get a high-level overview using the Statistics menu. Bevor du in einzelne Pakete eintauchst oder nachdem du den Datenverkehr gefiltert hast, verschaffe dir einen Überblick auf hoher Ebene mit dem Statistik-Menü.

Endpoints lists all unique devices, MAC addresses, IP addresses, TCP/UDP ports, involved and their traffic volume. Endpunkte listet alle eindeutigen Geräte, MAC-Adressen, IP-Adressen, TCP/UDP-Ports auf, die beteiligt sind, und deren Verkehrsvolumen.

This answers: Who was communicating? Das beantwortet: Wer kommunizierte?

Conversations shows communication between pairs of endpoints, with details like packet/byte counts per direction and duration. Konversationen zeigt die Kommunikation zwischen Endpunkt-Paaren mit Details wie Paket- und Byte-Anzahl pro Richtung und Dauer.

This answers: Who talked to whom, and how much? Das beantwortet: Wer sprach mit wem und wie viel?

Protocol Hierarchy displays the distribution of different protocols in the capture, organized by layers, showing packet and byte percentages. Protokoll-Hierarchie zeigt die Verteilung verschiedener Protokolle in der Aufzeichnung, organisiert nach Schichten, und zeigt Paket- und Byte-Prozentsätze.

This answers: What kind of traffic is present? Is anything unusual? Das beantwortet: Welche Art von Verkehr ist vorhanden? Ist etwas ungewöhnlich?

IO Graphs visualizes traffic rates, packets per second, bytes per second, over time. IO-Graphen visualisieren Verkehrsraten, Pakete pro Sekunde, Bytes pro Sekunde, über die Zeit.

You can graph overall traffic or apply display filters to focus on specific types. Du kannst den gesamten Verkehr grafisch darstellen oder Anzeigefilter anwenden, um dich auf bestimmte Typen zu konzentrieren.

This answers: When did traffic peaks occur? Das beantwortet: Wann traten Verkehrsspitzen auf?

Think about it. Denk mal darüber nach.

You are investigating slow network performance. Du untersuchst langsame Netzwerk-Performance.

Which two statistical tools would likely be most useful initially to identify potential bottlenecks or bandwidth hogs? Welche zwei statistischen Werkzeuge wären wahrscheinlich anfangs am nützlichsten, um potenzielle Engpässe oder Bandbreitenfresser zu identifizieren?

Why? Warum?

Extracting Information: Exporting Objects. Informationen extrahieren: Objekte exportieren.

Sometimes, files are transferred directly within the network traffic, for example images on a webpage, files downloaded via HTTP, files transferred over SMB. Manchmal werden Dateien direkt im Netzwerkverkehr übertragen, zum Beispiel Bilder auf einer Webseite, Dateien, die über HTTP heruntergeladen wurden, Dateien, die über SMB übertragen wurden.

Wireshark can often identify and extract these objects. Wireshark kann diese Objekte oft identifizieren und extrahieren.

Example: HTTP Objects. For unencrypted HTTP traffic, go to File, Export Objects, HTTP. Beispiel: HTTP-Objekte. Für unverschlüsselten HTTP-Verkehr gehe zu Datei, Objekte exportieren, HTTP.

A window lists detected objects, images, HTML files, scripts, et cetera. Ein Fenster listet erkannte Objekte auf, Bilder, HTML-Dateien, Skripte und so weiter.

Select objects and click Save As to extract them. Wähle Objekte aus und klicke auf „Speichern unter", um sie zu extrahieren.

This is invaluable for security analysis, extracting malware payloads or exfiltrated data, or simply understanding what files were transferred. Dies ist von unschätzbarem Wert für Sicherheitsanalysen, zum Extrahieren von Malware-Payloads oder exfiltrierten Daten oder einfach um zu verstehen, welche Dateien übertragen wurden.

Similar options exist for other protocols like SMB under the File, Export Objects menu. Ähnliche Optionen existieren für andere Protokolle wie SMB unter dem Menü Datei, Objekte exportieren.

Finding Practice Files: Sample Captures. Übungsdateien finden: Beispiel-Aufzeichnungen.

The best way to master Wireshark is to practice on diverse traffic. Der beste Weg, Wireshark zu meistern, ist es, mit vielfältigem Datenverkehr zu üben.

While you can capture your own traffic, exploring pre-made capture files exposes you to protocols and scenarios you might not encounter locally. Während du deinen eigenen Datenverkehr aufzeichnen kannst, bringen dich vorgefertigte Aufzeichnungsdateien mit Protokollen und Szenarien in Kontakt, denen du lokal möglicherweise nicht begegnest.

The Wireshark Wiki maintains a page dedicated to Sample Captures. Das Wireshark-Wiki pflegt eine Seite, die sich Sample Captures widmet.

This page contains a large collection of pcap or pcapng files demonstrating various protocols, from common ones like DNS, DHCP, HTTP, SMB to more obscure or specialized ones, network problems, and even security-related traffic captures like malware communication. Diese Seite enthält eine große Sammlung von pcap- oder pcapng-Dateien, die verschiedene Protokolle demonstrieren, von gängigen wie DNS, DHCP, HTTP, SMB bis zu obskureren oder spezialisierten, Netzwerkprobleme und sogar sicherheitsbezogene Verkehrsaufzeichnungen wie Malware-Kommunikation.

Recommendation: Visit this page. Empfehlung: Besuche diese Seite.

Find a capture file related to a protocol you're curious about, perhaps HTTP, DNS, or ARP, or a scenario like a basic web browse. Finde eine Aufzeichnungsdatei, die mit einem Protokoll zu tun hat, das dich interessiert, vielleicht HTTP, DNS oder ARP, oder ein Szenario wie einfaches Web-Browsing.

Download it and open it in Wireshark. Lade sie herunter und öffne sie in Wireshark.

Try applying the filtering, stream following, and statistical techniques discussed here. Versuche, die hier besprochenen Filter-, Stream-Following- und statistischen Techniken anzuwenden.

Try it yourself. Probiere es selbst aus.

Go to the Sample Captures wiki page linked above. Gehe zur oben verlinkten Sample-Captures-Wiki-Seite.

Browse the sections. Durchsuche die Abschnitte.

Download one or two captures that look interesting, for example http.cap, dns.pcap, or one from the malware-traffic-analysis.net section if you're feeling adventurous. Lade eine oder zwei Aufzeichnungen herunter, die interessant aussehen, zum Beispiel http.cap, dns.pcap oder eine aus dem Bereich malware-traffic-analysis.net, wenn du abenteuerlustig bist.

Open them in Wireshark and just explore! Öffne sie in Wireshark und erkunde einfach!

The slides for the live session can be viewed here. Die Folien für die Live-Sitzung können hier angesehen werden.

Try not to peek before class, spoilers inside! Versuche nicht vor der Stunde zu spicken, es gibt Spoiler!