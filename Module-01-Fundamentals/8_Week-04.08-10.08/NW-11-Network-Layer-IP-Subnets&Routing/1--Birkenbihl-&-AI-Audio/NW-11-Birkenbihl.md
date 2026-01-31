Welcome to your preparation for our session on the Network Layer! Willkommen zu Ihrer Vorbereitung auf unsere Sitzung über die Netzwerkschicht!

This layer is crucial for how data is transported across the internet and within local networks. Diese Schicht ist entscheidend dafür, wie Daten über das Internet und innerhalb lokaler Netzwerke transportiert werden.

Understanding its functions, particularly IP addressing and routing, is fundamental to cybersecurity. Das Verständnis ihrer Funktionen, insbesondere IP-Adressierung und Routing, ist für die Cybersicherheit von grundlegender Bedeutung.

Take your time to go through these materials, as they form the foundation for our live course. Nehmen Sie sich die Zeit, diese Materialien durchzugehen, da sie die Grundlage für unseren Live-Kurs bilden.

The Network Layer: The Internet's Postal Service. Die Netzwerkschicht: Der Postdienst des Internets.

In our layered model of networking, you may remember the five layer model, the Network Layer sits at Layer 3. In unserem Schichtenmodell der Vernetzung, Sie erinnern sich vielleicht an das Fünf-Schichten-Modell, befindet sich die Netzwerkschicht auf Schicht 3.

Its primary job is to handle the addressing and routing of data packets across different networks. Ihre Hauptaufgabe besteht darin, die Adressierung und Weiterleitung von Datenpaketen über verschiedene Netzwerke hinweg zu regeln.

Think of the Network Layer like the part of the postal service that figures out which city and which street a letter needs to go to, even if it's thousands of kilometers away. Stellen Sie sich die Netzwerkschicht wie den Teil des Postdienstes vor, der herausfindet, in welche Stadt und an welche Straße ein Brief geschickt werden muss, auch wenn er Tausende von Kilometern entfernt ist.

Key responsibilities of the Network Layer include: Logical Addressing. Zu den wichtigsten Aufgaben der Netzwerkschicht gehören: Logische Adressierung.

Assigning unique addresses to devices so they can be identified across networks. Die Zuweisung eindeutiger Adressen an Geräte, damit diese netzwerkübergreifend identifiziert werden können.

The most common form of this address is the IP address. Die gebräuchlichste Form dieser Adresse ist die IP-Adresse.

Routing: Determining the best path for data packets to travel from a source device to a destination device. Routing: Bestimmung des besten Pfads für Datenpakete, die von einem Quellgerät zu einem Zielgerät gelangen sollen.

This requires specialized devices called routers. Dazu sind spezielle Geräte erforderlich, so genannte Router.

Packet Forwarding, or Packet Switching: The actual process of sending packets from one router to the next along the determined path. Paketweiterleitung oder Paketvermittlung: Der eigentliche Prozess des Sendens von Paketen von einem Router zum nächsten entlang des festgelegten Pfads.

The Network Layer provides services to the Transport Layer above it, which ensures data arrives correctly and in order, and uses services from the Data Link Layer below, which handles communication between devices on the same local network. Die Netzwerkschicht stellt Dienste für die darüber liegende Transportschicht bereit, die sicherstellt, dass die Daten korrekt und in der richtigen Reihenfolge ankommen, und nutzt die Dienste der darunter liegenden Datenverbindungsschicht, die die Kommunikation zwischen Geräten im gleichen lokalen Netzwerk abwickelt.

Internet Protocol, IP: The Workhorse. Internetprotokoll, IP: Das Arbeitspferd.

The Internet Protocol, IP, is the primary protocol at the Network Layer. Das Internetprotokoll, IP, ist das wichtigste Protokoll auf der Netzwerkschicht.

It's the set of rules that governs how data is sent from one computer to another across the internet. Es ist das Regelwerk, das regelt, wie Daten von einem Computer zu einem anderen über das Internet gesendet werden.

Key features of IP: Connectionless. Wichtige Merkmale von IP: Verbindungslos.

IP does not establish a connection before sending data. IP baut vor dem Senden von Daten keine Verbindung auf.

Each packet, a small chunk of your data, is treated independently. Jedes Paket, ein kleiner Teil Ihrer Daten, wird unabhängig behandelt.

Imagine mailing each page of a long letter in a separate envelope, each with the full destination address. Stellen Sie sich vor, Sie verschicken jede Seite eines langen Briefes in einem separaten Umschlag, jeweils mit der vollständigen Zieladresse.

Best Effort Delivery: IP tries its best to deliver packets, but there's no guarantee of delivery. Best-Effort-Zustellung: IP versucht sein Bestes, um Pakete zuzustellen, aber es gibt keine Garantie für die Zustellung.

Packets can be lost, duplicated, or arrive out of order. Pakete können verloren gehen, dupliziert werden oder nicht in der richtigen Reihenfolge ankommen.

Typically, higher layer protocols, like TCP on the Transport Layer, handle these issues and ensure reliable communication. In der Regel sind es Protokolle auf höherer Ebene, wie TCP auf der Transportschicht, die diese Probleme lösen und eine zuverlässige Kommunikation gewährleisten.

IP Addressing: Who's Who on the Network. IP-Adressierung: Wer ist wer im Netzwerk.

It is very useful for testing network software without actually sending packets onto the network. Sie ist sehr nützlich, um Netzwerksoftware zu testen, ohne tatsächlich Pakete in das Netzwerk zu senden.

Public versus private IP addresses. Öffentliche gegen private IP-Adressen.

An IP address is a unique numerical label assigned to each device, computer, phone, server, etcetera, participating in a computer network that uses the Internet Protocol for communication. Eine IP-Adresse ist eine eindeutige numerische Kennzeichnung, die jedem Gerät, Computer, Telefon, Server und so weiter, zugewiesen wird, das an einem Computernetzwerk teilnimmt, das das Internetprotokoll für die Kommunikation verwendet.

It serves two main functions: it identifies the host, or more precisely, its network interface, and provides its location in the network. Sie hat zwei Hauptfunktionen: Sie identifiziert den Host, oder genauer gesagt, seine Netzwerkschnittstelle, und gibt seinen Standort im Netzwerk an.

IPv4 Addresses: For many years, IPv4, IP Version 4, has been the standard. IPv4-Adressen: Seit vielen Jahren ist IPv4, IP Version 4, der Standard.

An IPv4 address is a 32 bit number. Eine IPv4-Adresse ist eine 32-Bit-Zahl.

To make it easier for humans to read and write, it's typically expressed in dotted decimal notation, for example, 192.168.1.100. Damit sie für Menschen leichter zu lesen und zu schreiben ist, wird sie normalerweise in gepunkteter Dezimalschreibweise ausgedrückt, zum Beispiel 192.168.1.100.

Each of the four numbers, octets, can range from 0 to 255. Jede der vier Zahlen, Oktette, kann von 0 bis 255 reichen.

Subnetting: Dividing Networks. Subnetting: Aufteilung von Netzwerken.

An IP address isn't just one long number, it's divided into two important parts. Eine IP-Adresse besteht nicht nur aus einer einzigen langen Zahl, sondern ist in zwei wichtige Teile unterteilt.

The process of this subdivision is called subnetting. Der Prozess dieser Unterteilung wird Subnetting genannt.

A subnet, or subnetwork, is a logical subdivision of an IP network. Ein Subnetz oder Subnetzwerk ist eine logische Unterteilung eines IP-Netzwerks.

Imagine a large company with many departments, sales, marketing, engineering. Stellen Sie sich ein großes Unternehmen mit vielen Abteilungen vor, Vertrieb, Marketing, Technik.

Instead of having all computers on one big network, each department could have its own subnet. Anstatt alle Computer in einem großen Netzwerk zu haben, könnte jede Abteilung ihr eigenes Subnetz haben.

Why subnet? Organization: Keeps networks organized and manageable. Warum ein Subnetz? Organisation: Hält die Netzwerke übersichtlich und verwaltbar.

Security: Can isolate parts of a network. Sicherheit: Kann Teile eines Netzwerks isolieren.

If one subnet is compromised, others can remain secure. Wenn ein Subnetz kompromittiert wird, können andere sicher bleiben.

Performance: Reduces overall network traffic by limiting broadcast traffic to smaller domains. Leistung: Reduziert den gesamten Netzwerkverkehr, indem der Broadcast-Verkehr auf kleinere Domänen beschränkt wird.

Address Management: Allows more efficient use of a limited block of IP addresses. Adressverwaltung: Ermöglicht eine effizientere Nutzung eines begrenzten Blocks von IP-Adressen.

Subnet Masks and Network slash Host Portions. Subnetzmasken und Netzwerk-Schrägstrich-Hostabschnitte.

A subnet mask tells a computer which part of an IP address is the network portion and which part is the host portion. Eine Subnetzmaske teilt einem Computer mit, welcher Teil einer IP-Adresse der Netzwerkteil und welcher Teil der Hostteil ist.

Like an IP address, it's a 32 bit number, often given in dotted decimal notation, for example, 255.255.255.0. Wie eine IP-Adresse ist sie eine 32-Bit-Zahl, die oft in punktierter Dezimalschreibweise angegeben wird, zum Beispiel 255.255.255.0.

The network portion identifies the specific network the device belongs to. Der Netzwerkteil identifiziert das spezifische Netzwerk, zu dem das Gerät gehört.

The 255, or binary ones, in the mask mask out this part. Die 255, oder binären Einsen, in der Maske maskieren diesen Teil aus.

The host portion identifies the specific device within that network. Der Host-Teil identifiziert das spezifische Gerät innerhalb dieses Netzwerks.

The 0, or binary zeros, in the mask identify this part. Die 0, oder binären Nullen, in der Maske identifizieren diesen Teil.

Example: Your IP is 192.168.1.100 and your subnet mask is 255.255.255.0. Beispiel: Ihre IP lautet 192.168.1.100 und Ihre Subnetzmaske 255.255.255.0.

The 255.255.255 part of the mask means 192.168.1 is the network portion. Der Teil 255.255.255 der Maske bedeutet, dass 192.168.1 der Netzteil ist.

The .0 part of the mask means .100 is the host portion. Der Teil .0 der Maske bedeutet, dass .100 der Host-Teil ist.

Another way to represent subnet masks is CIDR notation, Classless Inter Domain Routing. Eine andere Möglichkeit, Subnetzmasken darzustellen, ist die CIDR-Notation, Classless Inter-Domain Routing.

This is a slash followed by the number of bits in the network portion. Dies ist ein Schrägstrich, gefolgt von der Anzahl der Bits im Netzwerkteil.

For example, 255.255.255.0 is equivalent to slash 24, because the first 24 bits, 3 octets times 8 bits per octet, are for the network. Zum Beispiel ist 255.255.255.0 gleichbedeutend mit Schrägstrich 24, weil die ersten 24 Bits, 3 Oktette mal 8 Bits pro Oktett, für das Netzwerk sind.

So 192.168.1.100 slash 24 defines both the IP and the subnet. Also 192.168.1.100 Schrägstrich 24 definiert sowohl die IP als auch das Subnetz.

Special IPv4 Addresses. Spezielle IPv4-Adressen.

Now that we understand subnetting, we can define some special addresses that exist in every subnet. Jetzt, wo wir das Subnetting verstehen, können wir einige spezielle Adressen definieren, die in jedem Subnetz existieren.

Network Address: An IP address where all host bits are zero, for example, 192.168.1.0 for a typical home network with a slash 24 mask. Netzwerkadresse: Eine IP-Adresse, bei der alle Host-Bits Null sind, zum Beispiel 192.168.1.0 für ein typisches Heimnetzwerk mit einer Schrägstrich-24-Maske.

This address represents the network itself, not a specific device. Diese Adresse repräsentiert das Netzwerk selbst, nicht ein bestimmtes Gerät.

Broadcast Address: An IP address where all host bits are one, for example, 192.168.1.255 for a slash 24 network. Broadcast-Adresse: Eine IP-Adresse, bei der alle Host-Bits eins sind, zum Beispiel 192.168.1.255 für ein Schrägstrich-24-Netzwerk.

Packets sent to this address are delivered to all devices on that specific network. Pakete, die an diese Adresse gesendet werden, werden an alle Geräte in diesem spezifischen Netzwerk zugestellt.

Loopback Address: 127.0.0.1 is a special address that devices can use to send packets to themselves. Loopback-Adresse: 127.0.0.1 ist eine spezielle Adresse, die Geräte verwenden können, um Pakete an sich selbst zu senden.

Public IP Addresses: These are globally unique addresses assigned to devices that connect directly to the internet. Öffentliche IP-Adressen: Dies sind weltweit eindeutige Adressen, die Geräten zugewiesen werden, die direkt mit dem Internet verbunden sind.

For example, your home router has a public IP address assigned by your Internet Service Provider, ISP. Zum Beispiel hat Ihr Heimrouter eine öffentliche IP-Adresse, die von Ihrem Internetdienstanbieter, ISP, zugewiesen wurde.

Private IP Addresses: Since there's a limited number of IPv4 addresses available, certain ranges are reserved for use within private networks, like at home or in offices. Private IP-Adressen: Da nur eine begrenzte Anzahl von IPv4-Adressen zur Verfügung steht, sind bestimmte Bereiche für die Verwendung in privaten Netzwerken, wie zu Hause oder in Büros, reserviert.

These addresses are not routable on the public internet. Diese Adressen sind im öffentlichen Internet nicht routbar.

Common private IP address ranges include 10.0.0.0 slash 8, 172.16.0.0 slash 12, and 192.168.0.0 slash 16. Zu den üblichen privaten IP-Adressbereichen gehören 10.0.0.0 Schrägstrich 8, 172.16.0.0 Schrägstrich 12 und 192.168.0.0 Schrägstrich 16.

Devices on these private networks use these addresses for internal communication. Die Geräte in diesen privaten Netzwerken verwenden diese Adressen für die interne Kommunikation.

To access the internet, a process called Network Address Translation, NAT, is typically used by the router, allowing multiple devices to share a single public IP address. Für den Zugriff auf das Internet wird in der Regel ein Verfahren namens Network Address Translation, NAT, vom Router verwendet, das es mehreren Geräten ermöglicht, eine einzige öffentliche IP-Adresse zu nutzen.

We will explore private IP addresses and NAT in more detail in the next lesson. Wir werden uns in der nächsten Lektion ausführlicher mit privaten IP-Adressen und NAT beschäftigen.

Think about it: Your computer has the IP address 10.0.1.50 with a subnet mask of 255.255.0.0. Denken Sie darüber nach: Ihr Computer hat die IP-Adresse 10.0.1.50 mit einer Subnetzmaske von 255.255.0.0.

What is its network address? What is the broadcast address for this subnet? Wie lautet seine Netzwerkadresse? Wie lautet die Broadcast-Adresse für dieses Subnetz?

Why might a large university campus want to divide its network into many subnets? Warum sollte ein großer Universitätscampus sein Netzwerk in viele Subnetze aufteilen wollen?

Try it yourself: Find your network configuration. Versuchen Sie es selbst: Finden Sie Ihre Netzwerkkonfiguration.

On macOS: Open Terminal, you can find it via Spotlight search. Unter macOS: Öffnen Sie Terminal, Sie können es über die Spotlight-Suche finden.

Type ifconfig en0, for Wi-Fi, en0 is usually your Wi-Fi interface, for wired Ethernet, it might be en1 or another number, look for an active interface with an inet address. Geben Sie ifconfig en0 ein, bei Wi-Fi ist en0 normalerweise Ihre Wi-Fi-Schnittstelle, bei kabelgebundenem Ethernet könnte es en1 oder eine andere Nummer sein, suchen Sie nach einer aktiven Schnittstelle mit einer inet-Adresse.

Alternatively, on newer macOS: ip address show en0 or simply ip a will show all interfaces. Alternativ kann unter neuerem macOS: ip address show en0 oder einfach ip a alle Schnittstellen anzeigen.

Identify your IPv4 address, often labeled inet, your subnet mask, netmask, and your default gateway. Identifizieren Sie Ihre IPv4-Adresse, oft mit inet beschriftet, Ihre Subnetzmaske, netmask, und Ihr Standard-Gateway.

On macOS, you can type netstat minus nr pipe grep default into Terminal, the address next to default is your gateway. Unter macOS können Sie netstat minus nr Pipe grep default in das Terminal eingeben, die Adresse neben default ist Ihr Gateway.

Ping yourself: In Terminal, type ping 127.0.0.1. Pingen Sie sich selbst an: Geben Sie im Terminal ping 127.0.0.1 ein.

You should see replies. Sie sollten Antworten sehen.

This confirms your computer's network stack is working. Dies bestätigt, dass der Netzwerkstack Ihres Computers funktioniert.

Press Control plus C to stop. Drücken Sie Control plus C zum Beenden.

Ping your gateway: Ping the default gateway IP address you found. Pingen Sie Ihr Gateway an: Pingen Sie die IP-Adresse des Standard-Gateways an, die Sie gefunden haben.

This tests the connection to your local router. Damit testen Sie die Verbindung zu Ihrem lokalen Router.

IPv6: The Next Generation. IPv6: Die nächste Generation.

IPv4 has been incredibly successful, but it has one major limitation: there aren't enough unique IPv4 addresses for all the devices now connecting to the internet, phones, smart devices, etcetera. IPv4 war unglaublich erfolgreich, aber es hat eine große Einschränkung: Es gibt nicht genügend eindeutige IPv4-Adressen für alle Geräte, die jetzt eine Verbindung zum Internet herstellen, Telefone, intelligente Geräte und so weiter.

This is called IPv4 address exhaustion. Dies wird als Erschöpfung der IPv4-Adressen bezeichnet.

IPv6, IP Version 6, is the successor, designed to solve this problem and provide other improvements. IPv6, IP Version 6, ist der Nachfolger, der dieses Problem lösen und weitere Verbesserungen bieten soll.

Key features of IPv6: Vastly larger address space. Die wichtigsten Merkmale von IPv6: Extrem größerer Adressraum.

IPv6 addresses are 128 bits long, compared to 32 bits for IPv4. IPv6-Adressen sind 128 Bit lang, im Vergleich zu 32 Bit bei IPv4.

This provides an astronomical number of unique addresses, approximately 3.4 times 10 to the power of 38, meaning we won't run out anytime soon. Damit steht eine astronomische Anzahl eindeutiger Adressen zur Verfügung, etwa 3,4 mal 10 hoch 38, was bedeutet, dass diese in absehbarer Zeit wohl nicht ausgehen werden.

Format: IPv6 addresses are written as eight groups of four hexadecimal digits, separated by colons. Format: IPv6-Adressen werden als acht Gruppen von vier hexadezimalen Ziffern geschrieben, die durch Doppelpunkte getrennt sind.

Example: 2001 colon 0db8 colon 85a3 colon 0000 colon 0000 colon 8a2e colon 0370 colon 7334. Beispiel: 2001 Doppelpunkt 0db8 Doppelpunkt 85a3 Doppelpunkt 0000 Doppelpunkt 0000 Doppelpunkt 8a2e Doppelpunkt 0370 Doppelpunkt 7334.

Abbreviation Rules: Leading zeros in each group can be omitted, 0db8 is equivalent to db8. Abkürzungsregeln: Führende Nullen in jeder Gruppe können weggelassen werden, 0db8 ist gleichbedeutend mit db8.

A sequence of consecutive groups of zeros can be replaced with a double colon. Eine Folge von aufeinanderfolgenden Gruppen von Nullen kann durch einen Doppelpunkt ersetzt werden.

For example, 2001 colon 0db8 colon 0000 colon 0000 colon 1234 colon 0000 colon 0000 colon 5678 can be written as 2001 colon db8 colon colon 1234 colon 0 colon 0 colon 5678. Zum Beispiel kann 2001 Doppelpunkt 0db8 Doppelpunkt 0000 Doppelpunkt 0000 Doppelpunkt 1234 Doppelpunkt 0000 Doppelpunkt 0000 Doppelpunkt 5678 als 2001 Doppelpunkt db8 Doppelpunkt Doppelpunkt 1234 Doppelpunkt 0 Doppelpunkt 0 Doppelpunkt 5678 geschrieben werden.

The double colon may only be used once in an address to avoid ambiguity. Der Doppelpunkt darf nur einmal in einer Adresse verwendet werden, um Mehrdeutigkeiten zu vermeiden.

The example 2001 colon 0db8 colon 85a3 colon 0000 colon 0000 colon 8a2e colon 0370 colon 7334 could be 2001 colon db8 colon 85a3 colon colon 8a2e colon 370 colon 7334. Das Beispiel 2001 Doppelpunkt 0db8 Doppelpunkt 85a3 Doppelpunkt 0000 Doppelpunkt 0000 Doppelpunkt 8a2e Doppelpunkt 0370 Doppelpunkt 7334 könnte 2001 Doppelpunkt db8 Doppelpunkt 85a3 Doppelpunkt Doppelpunkt 8a2e Doppelpunkt 370 Doppelpunkt 7334 sein.

Simplified Header: The IPv6 packet header is simpler than IPv4's, which can lead to more efficient processing by routers. Vereinfachter Header: Der IPv6-Paketkopf ist einfacher als der von IPv4, was zu einer effizienteren Verarbeitung durch Router führen kann.

No NAT, typically: With so many addresses, Network Address Translation, NAT, is typically not necessary, allowing for true end to end connectivity. Kein NAT, in der Regel: Bei so vielen Adressen ist Network Address Translation, NAT, in der Regel nicht erforderlich, was eine echte Ende-zu-Ende-Konnektivität ermöglicht.

Built in Security, mandatory IPSec support: While IPSec, Internet Protocol Security, exists for IPv4, its support is mandatory for IPv6, which can make securing communication easier, though actual usage varies. Eingebaute Sicherheit, obligatorische IPSec-Unterstützung: IPSec, Internet Protocol Security, gibt es zwar schon für IPv4, aber seine Unterstützung ist bei IPv6 obligatorisch, was die Sicherheit der Kommunikation erleichtern kann, die tatsächliche Nutzung ist jedoch unterschiedlich.

Many networks today run IPv4 and IPv6 simultaneously, this is called dual stack. In vielen Netzwerken werden heute IPv4 und IPv6 gleichzeitig betrieben, dies wird als Dual-Stack bezeichnet.

Try it yourself: Check if your computer has an IPv6 address. Versuchen Sie es selbst: Prüfen Sie, ob Ihr Computer eine IPv6-Adresse hat.

On macOS, look in the output of ifconfig en0, or your active interface, for an address labeled inet6. Unter macOS suchen Sie in der Ausgabe von ifconfig en0, oder Ihrer aktiven Schnittstelle, nach einer Adresse mit der Bezeichnung inet6.

It will be a long hexadecimal string. Es handelt sich um eine lange hexadezimale Zeichenfolge.

Try pinging an IPv6 address. Versuchen Sie, eine IPv6-Adresse anzupingen.

For example, Google's public DNS server has an IPv6 address: ping6 2001 colon 4860 colon 4860 colon colon 8888. Der öffentliche DNS-Server von Google hat zum Beispiel eine IPv6-Adresse: ping6 2001 Doppelpunkt 4860 Doppelpunkt 4860 Doppelpunkt Doppelpunkt 8888.

On macOS, use ping6. Unter macOS verwenden Sie ping6.

Routing: Finding the Best Path. Routing: Den besten Pfad finden.

Routing is the process of selecting paths in a network along which to send data packets from a source to a destination. Unter Routing versteht man den Prozess der Auswahl von Pfaden in einem Netzwerk, auf denen Datenpakete von einer Quelle zu einem Ziel gelangen.

Devices called routers are responsible for this. Hierfür sind Geräte namens Router zuständig.

Routers operate at the Network Layer and maintain routing tables. Router arbeiten auf der Netzwerkschicht und führen Routing-Tabellen.

Routing Tables: A routing table is like a map for a router. Routing-Tabellen: Eine Routing-Tabelle ist wie eine Karte für einen Router.

It contains information about: Destination Network, the network the packet is trying to reach. Sie enthält Informationen über: Zielnetzwerk, das Netzwerk, das das Paket zu erreichen versucht.

Next Hop: The IP address of the next router on the path to the destination network. Nächster Hop: Die IP-Adresse des nächsten Routers auf dem Weg zum Zielnetzwerk.

Interface: The physical network interface, for example, Ethernet port, the router should use to send the packet to the next hop. Schnittstelle: Die physische Netzwerkschnittstelle, zum Beispiel Ethernet-Port, die der Router verwenden soll, um das Paket an den nächsten Hop zu senden.

Metric: A measure of the cost of a route, for example, number of hops, speed of connection. Metrik: Ein Maß für die Kosten einer Route, zum Beispiel die Anzahl der Sprünge, die Geschwindigkeit der Verbindung.

Routers try to choose the path with the lowest metric. Router versuchen, den Weg mit der niedrigsten Metrik zu wählen.

When a router receives a packet, it examines the destination IP address in the packet's header. Wenn ein Router ein Paket empfängt, prüft er die Ziel-IP-Adresse im Header des Pakets.

It then consults its routing table to find the best match for that destination network, and forwards the packet to the appropriate next hop, or directly to the destination if it's on a connected network. Dann konsultiert er seine Routing-Tabelle, um die beste Übereinstimmung für dieses Zielnetzwerk zu finden, und leitet das Paket an den entsprechenden nächsten Hop oder direkt an das Ziel weiter, wenn es sich in einem verbundenen Netzwerk befindet.

Types of Routing, brief overview: Static Routing. Arten von Routing, kurzer Überblick: Statisches Routing.

Network administrators manually configure routes in the routing table. Netzwerkadministratoren konfigurieren Routen manuell in der Routing-Tabelle.

This is simple for small networks, but doesn't scale well and can't automatically adapt to network changes. Dies ist für kleine Netzwerke einfach, lässt sich aber nicht gut skalieren und kann sich nicht automatisch an Netzwerkänderungen anpassen.

Dynamic Routing: Routers use special routing protocols, like OSPF, EIGRP, BGP, RIP, to communicate with each other and automatically learn about available routes and changes in network topology. Dynamisches Routing: Router verwenden spezielle Routing-Protokolle, wie OSPF, EIGRP, BGP, RIP, um miteinander zu kommunizieren und automatisch von verfügbaren Routen und Änderungen der Netztopologie zu erfahren.

This is more complex, but much more scalable and robust. Dies ist komplexer, aber viel skalierbarer und robuster.

Default Gateway: Most end devices, like your computer, are not routers themselves and don't have extensive routing tables. Standard-Gateway: Die meisten Endgeräte, wie Ihr Computer, sind selbst keine Router und verfügen nicht über umfangreiche Routing-Tabellen.

They usually only know about their local network. Sie kennen in der Regel nur ihr lokales Netzwerk.

When a device wants to send a packet to a destination outside its local network, it sends the packet to its default gateway. Wenn ein Gerät ein Paket an ein Ziel außerhalb seines lokalen Netzwerks senden möchte, sendet es das Paket an sein Standard-Gateway.

The default gateway is a router on the local network that knows how to forward packets to other networks, including the internet. Das Standard-Gateway ist ein Router im lokalen Netzwerk, der weiß, wie man Pakete an andere Netzwerke, einschließlich des Internets, weiterleitet.

Try it yourself: View your routing table. Versuchen Sie es selbst: Zeigen Sie Ihre Routing-Tabelle an.

On macOS: Open Terminal and type netstat minus nr. Unter macOS: Öffnen Sie Terminal und geben Sie netstat minus nr ein.

Look for the default route, this is your default gateway. Suchen Sie nach der Standard-Route, dies ist Ihr Standard-Gateway.

You'll also see routes to directly connected networks. Sie werden auch Routen zu direkt verbundenen Netzwerken sehen.

Think about it: If your computer's default gateway fails, can you still access websites on the internet? Denken Sie darüber nach: Wenn das Standard-Gateway Ihres Computers ausgefallen ist, können Sie dann noch auf Websites im Internet zugreifen?

Can you still print on a printer on your local network? Können Sie noch auf einem Drucker in Ihrem lokalen Netzwerk drucken?

Why is dynamic routing preferable for large networks like the internet, despite its complexity? Warum ist dynamisches Routing trotz seiner Komplexität für große Netzwerke wie das Internet vorzuziehen?

This preparation material covers the fundamental concepts of the Network Layer. Dieses Vorbereitungsmaterial deckt die grundlegenden Konzepte der Netzwerkschicht ab.

Don't worry if not everything is clear yet, we will review and expand on these topics in our live session with practical demonstrations. Machen Sie sich keine Sorgen, wenn noch nicht alles klar ist, wir werden diese Themen in unserer Live-Sitzung mit praktischen Demonstrationen überprüfen und erweitern.

The goal is to familiarize you with the terminology and basic ideas. Das Ziel ist es, Sie mit der Terminologie und den grundlegenden Ideen vertraut zu machen.

Setup: Installing Cisco Packet Tracer. Einrichtung: Installation von Cisco Packet Tracer.

For the upcoming lessons and exercises, we will be using Cisco Packet Tracer, a powerful network simulation tool that allows you to build, configure, and troubleshoot virtual networks. Für die kommenden Lektionen und Übungen werden wir Cisco Packet Tracer verwenden, ein leistungsstarkes Netzwerksimulationstool, mit dem Sie virtuelle Netzwerke aufbauen, konfigurieren und Fehler beheben können.

Please install it before our live session. Bitte installieren Sie es vor unserer Live-Sitzung.

Installing Cisco Packet Tracer: Account Creation. Installation von Cisco Packet Tracer: Kontoerstellung.

Go to the Cisco Networking Academy website: www.netacad.com. Rufen Sie die Website der Cisco Networking Academy auf: www.netacad.com.

You'll need to create a free account. Sie müssen ein kostenloses Konto erstellen.

Look for options like Packet Tracer or Courses and then Packet Tracer, which typically leads to a signup or login page. Suchen Sie nach Optionen wie Packet Tracer oder Kurse und dann Packet Tracer, was normalerweise zu einer Anmelde- oder Login-Seite führt.

Often, an Introduction to Packet Tracer course is offered, which grants access. Oft wird ein Introduction to Packet Tracer-Kurs angeboten, der den Zugang ermöglicht.

Sign up for an account. Melden Sie sich für ein Konto an.

This might involve enrolling in a short introductory course, which you don't necessarily have to complete fully, but it gives you access to the download. Dies kann bedeuten, dass Sie sich für einen kurzen Einführungskurs anmelden, den Sie nicht unbedingt vollständig abschließen müssen, der Ihnen aber Zugang zum Download verschafft.

Download: Once logged into your NetAcad account, navigate to the Packet Tracer download area. Download: Sobald Sie in Ihrem NetAcad-Konto eingeloggt sind, navigieren Sie zum Download-Bereich für Packet Tracer.

This is usually found under Resources, Download Packet Tracer. Diesen finden Sie normalerweise unter Ressourcen, Packet Tracer herunterladen.

Download the latest version of Cisco Packet Tracer for macOS. Laden Sie die neueste Version von Cisco Packet Tracer für macOS herunter.

Installation: Open the downloaded .dmg file. Installation: Öffnen Sie die heruntergeladene .dmg-Datei.

Follow the on screen instructions to install Packet Tracer. Folgen Sie den Anweisungen auf dem Bildschirm, um Packet Tracer zu installieren.

Typically, you'll need to drag the Packet Tracer application into your Applications folder. In der Regel müssen Sie die Packet Tracer-Anwendung in Ihren Anwendungsordner ziehen.

First Launch and Login: Launch Packet Tracer from your Applications folder. Erster Start und Anmeldung: Starten Sie Packet Tracer aus Ihrem Anwendungsordner.

The first time you launch Packet Tracer, and occasionally after that, you will be prompted to log in with your Cisco Networking Academy, NetAcad, credentials that you created in step 1. Wenn Sie Packet Tracer zum ersten Mal starten, und gelegentlich danach, werden Sie aufgefordert, sich mit Ihren Cisco Networking Academy, NetAcad, Zugangsdaten anzumelden, die Sie in Schritt 1 erstellt haben.

This is required for full functionality. Dies ist für die volle Funktionalität erforderlich.

If given a choice between Networking Academy and Skills For All, choose Skills For All. Wenn Sie die Wahl zwischen Networking Academy und Skills For All haben, wählen Sie Skills For All.

Make sure Packet Tracer is installed and you can successfully log in before class. Vergewissern Sie sich, dass Packet Tracer installiert ist und Sie sich vor dem Kurs erfolgreich anmelden können.

This will save valuable time during the session. Dadurch sparen Sie wertvolle Zeit während der Sitzung.

If you encounter any issues, please search online for solutions on the topic Cisco Packet Tracer Installation macOS or contact our support. Sollten Sie auf Probleme stoßen, suchen Sie bitte online nach Lösungen zum Thema Cisco Packet Tracer Installation macOS oder wenden Sie sich an unseren Support.

Also, Cisco Packet Tracer's default fonts are quite small, especially in the computer's CLI. Außerdem sind die Standard-Schriftarten von Cisco Packet Tracer ziemlich klein, vor allem in der CLI der Computer.

It is recommended to increase the font via the top menu: Cisco Packet Tracer, Preferences, Font, CLI Change to 18, and don't forget to click Apply at the bottom of the page. Es wird empfohlen, die Schriftart über das obere Menü zu vergrößern: Cisco Packet Tracer, Preferences, Font, CLI Change to 18, und vergessen Sie nicht, unten auf der Seite auf Apply zu klicken.

The slides for the live session can be viewed here. Die Folien für die Live-Sitzung können hier angesehen werden.

Try not to peek before class, spoilers inside! Versuchen Sie nicht vor dem Unterricht zu spickeln, Spoiler drinnen!