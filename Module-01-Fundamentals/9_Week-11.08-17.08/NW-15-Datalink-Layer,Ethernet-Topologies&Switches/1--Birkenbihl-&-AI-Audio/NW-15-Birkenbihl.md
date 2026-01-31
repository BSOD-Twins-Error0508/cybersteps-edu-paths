Welcome! This preparation material introduces you to the data link layer, a fundamental part of how devices communicate within a local network. Herzlich willkommen! Dieses Vorbereitungsmaterial führt Sie in die Datenübertragungsschicht ein, einen grundlegenden Teil der Kommunikation von Geräten in einem lokalen Netzwerk.

We will cover key concepts such as Ethernet, MAC addresses, network topologies, and how devices like hubs and switches manage local traffic. Wir werden Schlüsselkonzepte wie Ethernet, MAC-Adressen, Netzwerktopologien und die Verwaltung des lokalen Datenverkehrs durch Geräte wie Hubs und Switches behandeln.

The data link layer, layer 2. Die Datenverbindungsschicht, Schicht 2.

Imagine you have several computers in a room and you want them to communicate directly with each other. Stellen Sie sich vor, Sie haben mehrere Computer in einem Raum und möchten, dass diese direkt miteinander kommunizieren.

How do they reliably send messages over the physical cables, or WiFi signals, that connect them? Wie senden sie zuverlässig Nachrichten über die physikalischen Kabel, oder WiFi-Signale, die sie verbinden?

This is where the data link layer comes in. Hier kommt die Datenverbindungsschicht ins Spiel.

In the 5 layer network model we have discussed, the data link layer sits directly above the physical layer, layer 1, and below the network layer, layer 3. In dem 5-Schichten-Netzwerkmodell, das wir besprochen haben, befindet sich die Datenverbindungsschicht direkt über der physikalischen Schicht, Schicht 1, und unter der Netzwerkschicht, Schicht 3.

Physical layer, layer 1. It deals with the raw transmission of bits, ones and zeros, over a physical medium like cables or radio waves. Physikalische Schicht, Schicht 1. Sie befasst sich mit der reinen Übertragung von Bits, Einsen und Nullen, über ein physikalisches Medium wie Kabel oder Funkwellen.

It knows nothing about which device the bits are intended for. Sie weiß nichts darüber, für welches Gerät die Bits bestimmt sind.

Data link layer, layer 2. It takes the raw bits from the physical layer and organizes them into structured units called frames. Datenverbindungsschicht, Schicht 2. Sie nimmt die rohen Bits von der physikalischen Schicht und organisiert sie in strukturierte Einheiten, die Frames genannt werden.

Its primary job is to manage communication between devices on the same local network segment. Ihre Hauptaufgabe besteht darin, die Kommunikation zwischen den Geräten im selben lokalen Netzwerksegment zu verwalten.

Think of it as managing the local neighborhood traffic. Man kann sich das so vorstellen, dass sie den lokalen Nachbarschaftsverkehr verwaltet.

Network layer, layer 3. It manages the routing of data between different networks. Netzwerkschicht, Schicht 3. Sie verwaltet die Weiterleitung von Daten zwischen verschiedenen Netzen.

This is where IP addresses live, managing traffic between different neighborhoods or cities. Hier befinden sich die IP-Adressen, die den Verkehr zwischen verschiedenen Stadtteilen oder Städten verwalten.

Key responsibilities of the data link layer. Schlüsselzuständigkeiten der Datenverbindungsschicht.

Framing. Grouping the bits received from the physical layer into frames. Framing. Gruppierung der von der physikalischen Schicht empfangenen Bits in Frames.

Frames have specific structures often including a header with addressing information and a trailer, sometimes for error checking. Frames haben spezifische Strukturen, die oft einen Header mit Adressierungsinformationen und einen Trailer enthalten, manchmal zur Fehlerprüfung.

Physical addressing. Identifying devices on the local network using unique hardware addresses called MAC addresses. Physikalische Adressierung. Identifizierung von Geräten im lokalen Netz anhand eindeutiger Hardware-Adressen, die MAC-Adressen genannt werden.

Error detection. Detecting errors that occurred during transmission over the physical medium, although correction is often handled by higher layers. Fehlererkennung. Erkennung von Fehlern, die bei der Übertragung über das physikalische Medium aufgetreten sind, obwohl die Korrektur oft von höheren Schichten übernommen wird.

A common method is using a Frame Check Sequence, or FCS, field in the frame trailer. Eine gängige Methode ist die Verwendung eines Frame Check Sequence, oder FCS, Feldes im Frame-Trailer.

Flow control. Managing the rate of data transmission to prevent a fast sender from overwhelming a slow receiver on the same network. Flusskontrolle. Verwaltung der Datenübertragungsrate, um zu verhindern, dass ein schneller Sender einen langsamen Empfänger im selben Netz überfordert.

Media Access Control, or MAC. Determining which device is allowed to transmit data on a shared medium at any given time, to avoid collisions, multiple devices transmitting simultaneously and corrupting the data. Media Access Control, oder MAC. Festlegung, welches Gerät zu einem bestimmten Zeitpunkt Daten auf einem gemeinsam genutzten Medium übertragen darf, um Kollisionen zu verhindern, mehrere Geräte, die gleichzeitig übertragen und die Daten verstümmeln.

Ethernet. Ethernet.

Ethernet is by far the most widely used data link layer technology for wired local area networks, or LANs, today. Ethernet ist die heute bei weitem am häufigsten verwendete Datenverbindungsschicht-Technologie für kabelgebundene lokale Netzwerke, oder LANs.

It was developed in the 1970s and has evolved significantly since. Sie wurde in den 1970er Jahren entwickelt und hat sich seither erheblich weiterentwickelt.

Think of Ethernet as a set of rules and standards that define how devices format data into frames and how they should behave when connected to a shared network cable. Stellen Sie sich Ethernet als eine Reihe von Regeln und Standards vor, die festlegen, wie Geräte Daten in Frames formatieren und wie sie sich verhalten sollen, wenn sie an ein gemeinsames Netzwerkkabel angeschlossen sind.

Early Ethernet used a shared coaxial cable, like old cable TV, where devices had to wait to see if the line was busy before transmitting, a method called CSMA slash CD, Carrier Sense Multiple Access with Collision Detection. Das frühe Ethernet verwendete ein gemeinsam genutztes Koaxialkabel, wie das alte Kabelfernsehen, bei dem die Geräte vor der Übertragung abwarten mussten, ob die Leitung belegt war, eine Methode namens CSMA Slash CD, Carrier Sense Multiple Access with Collision Detection.

Modern Ethernet almost always uses twisted pair cables, like the ones connecting your computer to a wall jack or router, and switches. Modernes Ethernet verwendet fast immer Twisted-Pair-Kabel, wie die, die Ihren Computer mit einer Steckdose oder einem Router verbinden, und Switches.

Switches are intelligent devices that learn which device is connected to which port, so multiple devices can communicate simultaneously without collisions, mostly. Switches sind intelligente Geräte, die lernen, welches Gerät an welchen Anschluss angeschlossen ist, so dass mehrere Geräte gleichzeitig ohne Kollisionen kommunizieren können, meistens.

This makes modern Ethernet far more efficient than its older versions. Dadurch ist das moderne Ethernet viel effizienter als seine älteren Versionen.

An Ethernet frame typically contains destination MAC address, the hardware address of the receiver on the local network. Ein Ethernet-Frame enthält in der Regel Ziel-MAC-Adresse, die Hardware-Adresse des Empfängers im lokalen Netz.

Source MAC address, the hardware address of the sender on the local network. Quell-MAC-Adresse, die Hardware-Adresse des Senders im lokalen Netz.

EtherType, indicating which network layer protocol the data belongs to, for example, IPv4 or IPv6. EtherType, gibt an, zu welchem Netzwerkschichtprotokoll die Daten gehören, zum Beispiel IPv4 oder IPv6.

Payload, the actual data being transmitted, for example, an IP packet. Payload, die eigentlichen Daten, die übertragen werden, zum Beispiel ein IP-Paket.

Frame Check Sequence, or FCS, for error detection. Frame Check Sequence, oder FCS, zur Fehlererkennung.

Hubs, switches, and managing traffic. Hubs, Switches und die Verwaltung des Datenverkehrs.

When you connect multiple devices on a wired Ethernet network, typically in a star topology, you use a central connection device. Wenn Sie mehrere Geräte in einem kabelgebundenen Ethernet-Netzwerk verbinden, in der Regel in einer Sterntopologie, verwenden Sie ein zentrales Verbindungsgerät.

Historically, this was often a hub, but modern networks almost exclusively use switches. In der Vergangenheit war dies oft ein Hub, aber moderne Netzwerke verwenden fast ausschließlich Switches.

Understanding the difference is key to understanding modern network performance. Das Verständnis des Unterschieds ist der Schlüssel zum Verständnis der modernen Netzwerkleistung.

Hubs, layer 1 device. Hubs, Schicht 1 Gerät.

Function. A hub is a simple device that operates at the physical layer, layer 1. Funktion. Ein Hub ist ein einfaches Gerät, das auf der physikalischen Schicht, Schicht 1, arbeitet.

It essentially acts as a multiport repeater. Er fungiert im Wesentlichen als Multiport-Repeater.

When an electrical signal, bits, comes in on one port, the hub regenerates that signal and broadcasts it out to all other ports, regardless of the intended destination. Wenn ein elektrisches Signal, Bits, an einem Anschluss eingeht, regeneriert der Hub dieses Signal und sendet es an alle anderen Anschlüsse, unabhängig vom beabsichtigten Ziel.

Intelligence. Hubs have no real intelligence. Intelligenz. Hubs haben keine wirkliche Intelligenz.

They do not look at MAC addresses or frames. They simply repeat electrical signals. Sie schauen nicht auf MAC-Adressen oder Frames. Sie wiederholen lediglich elektrische Signale.

Collision domain. Because all ports receive all traffic, all devices connected to a hub are in the same collision domain. Kollisionsbereich. Da alle Ports den gesamten Verkehr empfangen, befinden sich alle an einen Hub angeschlossenen Geräte im selben Kollisionsbereich.

This means if two devices try to transmit at exactly the same time, their signals collide on the network, corrupting the data. Das heißt, wenn zwei Geräte versuchen, genau zur gleichen Zeit zu übertragen, kollidieren ihre Signale im Netz, wodurch die Daten verfälscht werden.

Devices must use mechanisms like CSMA slash CD to listen before transmitting and to detect and recover from collisions. Die Geräte müssen Mechanismen wie CSMA Slash CD verwenden, um vor der Übertragung zuzuhören und Kollisionen zu erkennen und zu beheben.

Collisions significantly reduce network efficiency, especially as more devices are added. Kollisionen verringern die Effizienz des Netzes erheblich, vor allem, wenn mehr Geräte hinzukommen.

Duplex mode. Hubs operate in half duplex mode. Duplex-Modus. Hubs arbeiten im Halbduplex-Modus.

A device connected to a hub can either send or receive at any given time, but not both simultaneously, like a walkie talkie. Ein Gerät, das an einen Hub angeschlossen ist, kann zu einem bestimmten Zeitpunkt entweder senden oder empfangen, aber nicht beides gleichzeitig, wie ein Walkie-Talkie.

Relevance. Hubs are largely obsolete and rarely used in modern networks due to their inefficiency. Bedeutung. Hubs sind weitgehend veraltet und werden in modernen Netzwerken aufgrund ihrer Ineffizienz kaum noch verwendet.

Switches, layer 2 device. Switches, Schicht 2 Gerät.

Function. A switch is a more intelligent device that operates primarily at the data link layer, layer 2. Funktion. Ein Switch ist ein intelligenteres Gerät, das hauptsächlich auf der Datenübertragungsschicht, Schicht 2, arbeitet.

It receives incoming frames and examines the destination MAC address in the frame's header. Er empfängt eingehende Frames und prüft die Ziel-MAC-Adresse im Header des Frames.

Intelligence. Switches build and maintain a MAC address table, also called a CAM table. Intelligenz. Switches erstellen und pflegen eine MAC-Adresstabelle, auch CAM-Tabelle genannt.

This table maps the MAC addresses of connected devices to the specific switch port they are connected to. Diese Tabelle ordnet die MAC-Adressen der angeschlossenen Geräte dem jeweiligen Switch-Port zu, an dem sie angeschlossen sind.

When a frame arrives, the switch looks up the destination MAC address in its table and forwards the frame only to the appropriate port. Wenn ein Frame ankommt, sucht der Switch in seiner Tabelle nach der Ziel-MAC-Adresse und leitet den Frame nur an den entsprechenden Port weiter.

If the destination MAC is unknown or is a broadcast address, FF colon FF colon FF colon FF colon FF colon FF, the switch forwards the frame to all ports except the one it arrived on. Ist die Ziel-MAC unbekannt oder eine Broadcast-Adresse, FF Doppelpunkt FF Doppelpunkt FF Doppelpunkt FF Doppelpunkt FF Doppelpunkt FF, leitet der Switch den Frame an alle Ports außer dem, an dem er angekommen ist.

Collision domain. Each port on a switch represents its own collision domain. Kollisionsdomäne. Jeder Port eines Switches stellt eine eigene Kollisionsdomäne dar.

Because the switch intelligently forwards frames only where they need to go, devices connected to different ports do not interfere with each other's transmissions. Da der Switch Frames auf intelligente Weise nur dorthin weiterleitet, wo sie hingehören, stören sich Geräte, die an verschiedene Ports angeschlossen sind, nicht gegenseitig bei ihren Übertragungen.

This eliminates collisions between ports and greatly increases network efficiency compared to hubs. Dadurch werden Kollisionen zwischen den Ports vermieden und die Effizienz des Netzwerks im Vergleich zu Hubs erheblich gesteigert.

Duplex mode. Switches typically operate in full duplex mode. Duplex-Modus. Switches arbeiten normalerweise im Vollduplex-Modus.

A device connected to a switch port can send and receive data simultaneously without interfering with each other, like a telephone conversation. Ein Gerät, das an einen Switch-Port angeschlossen ist, kann gleichzeitig Daten senden und empfangen, ohne sich gegenseitig zu stören, wie bei einem Telefongespräch.

This effectively doubles the potential bandwidth of the connection, for example, a 100 megabits per second connection becomes 100 megabits per second sending plus 100 megabits per second receiving. Dadurch verdoppelt sich die potenzielle Bandbreite der Verbindung, zum Beispiel wird eine 100 Megabit pro Sekunde Verbindung zu 100 Megabit pro Sekunde Senden plus 100 Megabit pro Sekunde Empfangen.

Broadcast domain. While switches create separate collision domains, all ports on a basic switch belong to the same broadcast domain by default. Broadcast-Domäne. Während Switches getrennte Kollisionsdomänen schaffen, gehören alle Ports eines Basis-Switches standardmäßig zur gleichen Broadcast-Domäne.

This means if a device sends a broadcast frame, intended for all devices on the local network with MAC address FF colon FF colon FF colon FF colon FF colon FF, the switch forwards it to all other ports. Das heißt, wenn ein Gerät einen Broadcast-Frame sendet, für alle Geräte im lokalen Netz bestimmt mit MAC-Adresse FF Doppelpunkt FF Doppelpunkt FF Doppelpunkt FF Doppelpunkt FF Doppelpunkt FF, leitet der Switch ihn an alle anderen Ports weiter.

Routers, layer 3 devices, are typically used to separate broadcast domains. Router, Schicht 3 Geräte, werden in der Regel zur Trennung von Broadcast-Domänen verwendet.

We will discuss VLANs later, which allow switches to segment broadcast domains. Wir werden später auf VLANs eingehen, die es Switches ermöglichen, Broadcast-Domänen zu segmentieren.

Think about it. Denken Sie darüber nach.

Why was the invention of the network switch such a significant improvement over the hub for Ethernet performance? Warum war die Erfindung des Netzwerk-Switches für die Ethernet-Leistung eine so bedeutende Verbesserung gegenüber dem Hub?

MAC addresses. MAC-Adressen.

Every network interface card, or NIC, the hardware that connects a device to a network, wired or WiFi, has a unique identifier burned in by the manufacturer. Jede Netzwerkkarte, oder NIC, die Hardware, die ein Gerät mit einem Netzwerk verbindet, kabelgebunden oder WiFi, hat eine eindeutige, vom Hersteller eingebrannte Kennung.

This is called the MAC address, or Media Access Control address. Diese wird als MAC-Adresse, oder Media Access Control Adresse, bezeichnet.

It is sometimes also referred to as the physical address or hardware address. Manchmal wird sie auch als physikalische Adresse oder Hardware-Adresse bezeichnet.

Format. A MAC address is a 48 bit number, typically represented as 12 hexadecimal digits grouped in pairs, for example, 00 colon 1A colon 2B colon 3C colon 4D colon 5E, or 00 dash 1A dash 2B dash 3C dash 4D dash 5E. Format. Eine MAC-Adresse ist eine 48-Bit-Zahl, die normalerweise als 12 paarweise gruppierte Hexadezimalziffern dargestellt wird, zum Beispiel 00 Doppelpunkt 1A Doppelpunkt 2B Doppelpunkt 3C Doppelpunkt 4D Doppelpunkt 5E, oder 00 Bindestrich 1A Bindestrich 2B Bindestrich 3C Bindestrich 4D Bindestrich 5E.

Uniqueness. MAC addresses are intended to be globally unique. Einzigartigkeit. MAC-Adressen sollen weltweit eindeutig sein.

The first half, the first 6 hex digits, for example 00 colon 1A colon 2B, is the Organizationally Unique Identifier, or OUI, assigned to a specific manufacturer. Die erste Hälfte, die ersten 6 Hex-Ziffern, zum Beispiel 00 Doppelpunkt 1A Doppelpunkt 2B, ist der Organizationally Unique Identifier, oder OUI, der einem bestimmten Hersteller zugewiesen wird.

The manufacturer then assigns a unique value for the second half, the last 6 hex digits, for example 3C colon 4D colon 5E, to each NIC they produce. Der Hersteller weist dann jeder von ihm produzierten NIC einen eindeutigen Wert für die zweite Hälfte, die letzten 6 Hexadezimalziffern, zum Beispiel 3C Doppelpunkt 4D Doppelpunkt 5E, zu.

Purpose. MAC addresses are used for addressing frames within the same local network. Zweck. MAC-Adressen werden für die Adressierung von Frames innerhalb desselben lokalen Netzes verwendet.

When your computer wants to send data to another device on your home WiFi or wired LAN segment, it uses the destination device's MAC address. Wenn Ihr Computer Daten an ein anderes Gerät in Ihrem heimischen WiFi oder kabelgebundenen LAN-Segment senden möchte, verwendet er die MAC-Adresse des Zielgeräts.

Switches use MAC addresses to forward frames to the correct port. Switches verwenden MAC-Adressen, um Frames an den richtigen Port weiterzuleiten.

Routers use MAC addresses to forward packets to the next device on the local network segment. Router verwenden MAC-Adressen, um Pakete an das nächste Gerät im lokalen Netzwerksegment weiterzuleiten.

They are essential for layer 2 communication. Sie sind für die Schicht 2 Kommunikation unerlässlich.

Think about it. Denk mal drüber nach.

If MAC addresses are unique identifiers for devices, why do we also need IP addresses, layer 3? Wenn MAC-Adressen eindeutige Identifikatoren für Geräte sind, warum brauchen wir dann auch IP-Adressen, Schicht 3?

What different roles do they play in network communication? Welche unterschiedlichen Rollen spielen sie in der Netzwerkkommunikation?

Try it yourself. Versuchen Sie es selbst.

Find the MAC address for your Mac's WiFi or Ethernet adapter. Finden Sie die MAC-Adresse für den WiFi oder Ethernet-Adapter Ihres Macs.

Open System Preferences. Öffnen Sie Systemeinstellungen.

Click on Network in the sidebar. Klicken Sie in der Seitenleiste auf Netzwerk.

Select your active network interface, for example, WiFi or Ethernet. Wählen Sie Ihre aktive Netzwerkschnittstelle aus, zum Beispiel WiFi oder Ethernet.

Click on the Details button. Klicken Sie auf die Schaltfläche Details.

Look for the Hardware tab or section. Your MAC address should be listed there, it might be labeled MAC address or hardware address. Suchen Sie nach der Registerkarte oder dem Abschnitt Hardware. Ihre MAC-Adresse sollte dort aufgelistet sein, sie könnte mit MAC-Adresse oder Hardware-Adresse beschriftet sein.

Alternatively, you can use Terminal. Open the Terminal application, you can find it using Spotlight search. Alternativ können Sie auch das Terminal verwenden. Öffnen Sie die Anwendung Terminal, Sie können sie mit der Spotlight-Suche finden.

Type the command ifconfig en0, for WiFi, usually en0 or en1, or ifconfig enX, where X is the number of your Ethernet adapter if you have one connected, and press Enter. Geben Sie den Befehl ifconfig en0 ein, für WiFi, normalerweise en0 oder en1, oder ifconfig enX, wobei X die Nummer Ihres Ethernet-Adapters ist, falls Sie einen angeschlossen haben, und drücken Sie Enter.

Look for the line that starts with ether. The sequence of letters and numbers after ether is your MAC address. Suchen Sie nach der Zeile, die mit ether beginnt. Die Folge von Buchstaben und Zahlen nach ether ist Ihre MAC-Adresse.

Network topologies. Netzwerktopologien.

Network topology refers to the arrangement or layout of the connections, links, and nodes, devices like computers, switches, routers, in a network. Netzwerktopologie bezieht sich auf die Anordnung oder das Layout der Verbindungen, Links, und Knoten, Geräte wie Computer, Switches, Router, in einem Netzwerk.

It describes how devices are physically or logically interconnected. Sie beschreibt, wie Geräte physikalisch oder logisch miteinander verbunden sind.

Here are some common topologies. Hier sind einige gängige Topologien.

Bus topology. Bus-Topologie.

Layout. All devices share a single communication line or cable, the bus. Layout. Alle Geräte teilen sich eine einzige Kommunikationsleitung oder ein Kabel, den Bus.

How it works. Data sent by one device travels along the bus, and all other devices see it, but only the intended recipient accepts it. Wie es funktioniert. Daten, die von einem Gerät gesendet werden, wandern entlang des Busses, und alle anderen Geräte sehen sie, aber nur der beabsichtigte Empfänger nimmt sie an.

Terminators are needed at each end of the bus. Devices typically used CSMA slash CD to manage access. Terminatoren werden an jedem Ende des Busses benötigt. Geräte verwendeten typischerweise CSMA Slash CD, um den Zugriff zu verwalten.

Pros. Simple, inexpensive for small networks. Vorteile. Einfach, kostengünstig für kleine Netzwerke.

Cons. If the main cable fails, the entire network goes down. Collisions are frequent. Difficult to troubleshoot. Largely obsolete now. Nachteile. Wenn das Hauptkabel ausfällt, fällt das gesamte Netzwerk aus. Kollisionen sind häufig. Schwierig zu beheben. Weitgehend veraltet jetzt.

Ring topology. Ring-Topologie.

Layout. Devices are connected in a circular loop. Data travels in one direction around the ring. Layout. Geräte sind in einer kreisförmigen Schleife verbunden. Daten wandern in eine Richtung um den Ring.

How it works. Each device receives data from one neighbor and passes it to the next. Wie es funktioniert. Jedes Gerät empfängt Daten von einem Nachbarn und gibt sie an den nächsten weiter.

A token passing mechanism is often used to control who can transmit, avoiding collisions. Ein Token-Passing-Mechanismus wird oft verwendet, um zu kontrollieren, wer übertragen kann, um Kollisionen zu vermeiden.

Pros. Orderly transmission. Vorteile. Geordnete Übertragung.

Cons. Failure of one device or cable segment can break the ring, though dual ring setups add redundancy. Nachteile. Ausfall eines Geräts oder Kabelsegments kann den Ring unterbrechen, obwohl Dual-Ring-Setups Redundanz hinzufügen.

Adding or removing devices disrupts the network. Less common now. Hinzufügen oder Entfernen von Geräten stört das Netzwerk. Weniger verbreitet jetzt.

Star topology. Stern-Topologie.

Layout. All devices connect to a central device, historically a hub, but now almost always a switch. Layout. Alle Geräte verbinden sich mit einem zentralen Gerät, historisch ein Hub, aber jetzt fast immer ein Switch.

How it works. With a switch, devices send data to the central switch, which then forwards it only to the intended destination device based on MAC address. Wie es funktioniert. Mit einem Switch senden Geräte Daten an den zentralen Switch, der sie dann nur an das beabsichtigte Zielgerät basierend auf der MAC-Adresse weiterleitet.

Pros. Easy to install and manage. Failure of one cable or device doesn't affect others, unless the central switch fails. Vorteile. Einfach zu installieren und zu verwalten. Ausfall eines Kabels oder Geräts betrifft andere nicht, es sei denn, der zentrale Switch fällt aus.

Easy to add or remove devices. Efficient communication with switches, separate collision domains, full duplex. Einfach Geräte hinzuzufügen oder zu entfernen. Effiziente Kommunikation mit Switches, getrennte Kollisionsdomänen, Vollduplex.

Most common topology for modern LANs. Häufigste Topologie für moderne LANs.

Cons. If the central switch fails, the entire network segment connected to it goes down. Nachteile. Wenn der zentrale Switch ausfällt, fällt das gesamte Netzwerksegment aus, das damit verbunden ist.

Can require more cabling than bus or ring. Kann mehr Verkabelung erfordern als Bus oder Ring.

Mesh topology. Mesh-Topologie.

Layout. Devices are interconnected with many redundant paths. Layout. Geräte sind mit vielen redundanten Pfaden miteinander verbunden.

In a full mesh, every device connects directly to every other device. In einem vollständigen Mesh verbindet sich jedes Gerät direkt mit jedem anderen Gerät.

In a partial mesh, only some devices have multiple connections. In einem teilweisen Mesh haben nur einige Geräte mehrere Verbindungen.

How it works. Data can take multiple paths, providing high fault tolerance. Wie es funktioniert. Daten können mehrere Pfade nehmen, was eine hohe Fehlertoleranz bietet.

Often used with routers at layer 3 to manage paths. Oft mit Routern auf Schicht 3 verwendet, um Pfade zu verwalten.

Pros. Highly reliable and redundant. If one link fails, data can be rerouted. Vorteile. Hochzuverlässig und redundant. Wenn ein Link ausfällt, können Daten umgeleitet werden.

Cons. Very expensive due to extensive cabling and complex configuration. Nachteile. Sehr teuer aufgrund umfangreicher Verkabelung und komplexer Konfiguration.

Primarily used for critical backbone networks, like parts of the internet, or specific high availability needs, not typical LANs. Hauptsächlich für kritische Backbone-Netzwerke verwendet, wie Teile des Internets, oder spezifische Hochverfügbarkeitsanforderungen, nicht typische LANs.

Hybrid topology. Hybrid-Topologie.

Layout. A combination of two or more different topologies. Layout. Eine Kombination aus zwei oder mehr verschiedenen Topologien.

For example, connecting several star topology networks, each centered around a switch, together via a backbone link. Zum Beispiel, mehrere Stern-Topologie-Netzwerke verbinden, jedes um einen Switch zentriert, zusammen über einen Backbone-Link.

How it works. Depends on the specific combination. Wie es funktioniert. Hängt von der spezifischen Kombination ab.

Pros. Flexible, scalable. Can leverage the strengths of different topologies. Vorteile. Flexibel, skalierbar. Kann die Stärken verschiedener Topologien nutzen.

Cons. Can be complex to manage and troubleshoot. Nachteile. Kann komplex zu verwalten und zu beheben sein.

Think about it. Denken Sie darüber nach.

Consider your home network, computers, phones, smart devices connected to your WiFi router. Betrachten Sie Ihr Heimnetzwerk, Computer, Telefone, intelligente Geräte, die mit Ihrem WiFi-Router verbunden sind.

Which topology does it most closely resemble? Why? Welcher Topologie ähnelt es am meisten? Warum?

Hint: Think about how devices connect to the central router or access point. Hinweis: Denken Sie darüber nach, wie Geräte sich mit dem zentralen Router oder Access Point verbinden.

That covers the basics for our pre class preparation! We'll build on these concepts in the live session. Das deckt die Grundlagen für unsere Vorbereitung vor dem Unterricht ab! Wir werden auf diesen Konzepten in der Live-Sitzung aufbauen.

The slides for the live session can be viewed here. Try not to peek before class, spoilers inside! Die Folien für die Live-Sitzung können hier eingesehen werden. Versuchen Sie, nicht vor dem Unterricht zu schauen, Spoiler im Inneren!

Microsoft Sysinternals Suite. Microsoft Sysinternals Suite.

The Sysinternals Troubleshooting Utilities have been rolled up into a single suite of tools. Die Sysinternals Troubleshooting Utilities wurden in eine einzige Suite von Tools zusammengefasst.

This file contains the individual troubleshooting tools and help files. Diese Datei enthält die einzelnen Troubleshooting-Tools und Hilfedateien.

For exercises please download Microsoft Sysinternals Suite, ARM64 version, into your Windows virtual machine. Für Übungen laden Sie bitte die Microsoft Sysinternals Suite, ARM64-Version, in Ihre Windows virtuelle Maschine herunter.