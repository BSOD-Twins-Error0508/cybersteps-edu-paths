Herzlich willkommen! Dieses Vorbereitungsmaterial führt Sie in die Datenübertragungsschicht ein, einen grundlegenden Teil der Kommunikation von Geräten in einem lokalen Netzwerk. Wir werden Schlüsselkonzepte wie Ethernet, MAC-Adressen, Netzwerktopologien und die Verwaltung des lokalen Datenverkehrs durch Geräte wie Hubs und Switches behandeln.

## Die Datenverbindungsschicht (Schicht 2)

Stellen Sie sich vor, Sie haben mehrere Computer in einem Raum und möchten, dass diese direkt miteinander kommunizieren. Wie senden sie zuverlässig Nachrichten über die physikalischen Kabel (oder Wi-Fi-Signale), die sie verbinden? Hier kommt die **Datalink-Schicht** ins Spiel.

In dem 5-Schichten-Netzwerkmodell, das wir besprochen haben, befindet sich die Datenverbindungsschicht direkt über der physikalischen Schicht (Schicht 1) und unter der Netzwerkschicht (Schicht 3).

- **Physikalische Schicht (Schicht 1):** Sie befasst sich mit der reinen Übertragung von Bits (Einsen und Nullen) über ein physikalisches Medium (Kabel, Funkwellen). Sie weiß nichts darüber, _für welches_ Gerät die Bits bestimmt sind.
- **Datenverbindungsschicht (Schicht 2):** Nimmt die rohen Bits von der physikalischen Schicht und organisiert sie in strukturierte Einheiten, die **Frames** genannt werden. Ihre Hauptaufgabe besteht darin, die Kommunikation _zwischen den Geräten im selben lokalen Netzwerksegment_ zu verwalten. Man kann sich das so vorstellen, dass sie den lokalen Nachbarschaftsverkehr verwaltet.
- **Netzwerkschicht (Schicht 3):** Sie verwaltet die Weiterleitung von Daten _zwischen verschiedenen Netzen_. Hier befinden sich die IP-Adressen, die den Verkehr zwischen verschiedenen Stadtteilen oder Städten verwalten.

**Schlüsselzuständigkeiten der Datenverbindungsschicht:**

1. **Framing:** Gruppierung der von der physikalischen Schicht empfangenen Bits in Frames. Frames haben spezifische Strukturen, die oft einen Header (mit Adressierungsinformationen) und einen Trailer (manchmal zur Fehlerprüfung) enthalten.
2. **Physikalische Adressierung:** Identifizierung von Geräten im lokalen Netz anhand eindeutiger Hardware-Adressen, die MAC-Adressen genannt werden.
3. **Fehlererkennung:** Erkennung von Fehlern, die bei der Übertragung über das physikalische Medium aufgetreten sind (obwohl die Korrektur oft von höheren Schichten übernommen wird). Eine gängige Methode ist die Verwendung eines Frame Check Sequence (FCS)-Feldes im Frame-Trailer.
4. **Flusskontrolle:** Verwaltung der Datenübertragungsrate, um zu verhindern, dass ein schneller Sender einen langsamen Empfänger im selben Netz überfordert.
5. **Media Access Control (MAC):** Festlegung, welches Gerät zu einem bestimmten Zeitpunkt Daten auf einem gemeinsam genutzten Medium übertragen darf, um Kollisionen (mehrere Geräte, die gleichzeitig übertragen und die Daten verstümmeln) zu verhindern.

## Ethernet

Ethernet ist die heute bei weitem am häufigsten verwendete Datalink Layer-Technologie für kabelgebundene lokale Netzwerke (LANs). Sie wurde in den 1970er Jahren entwickelt und hat sich seither erheblich weiterentwickelt.

Stellen Sie sich Ethernet als eine Reihe von Regeln und Standards vor, die festlegen, wie Geräte Daten in Rahmen formatieren und wie sie sich verhalten sollen, wenn sie an ein gemeinsames Netzwerkkabel angeschlossen sind. Das frühe Ethernet verwendete ein gemeinsam genutztes Koaxialkabel (wie das alte Kabelfernsehen), bei dem die Geräte vor der Übertragung abwarten mussten, ob die Leitung belegt war (eine Methode namens CSMA/CD - Carrier Sense Multiple Access with Collision Detection).

![[Pasted image 20250930060713.png]]

Modernes Ethernet verwendet fast immer Twisted-Pair-Kabel (wie die, die Ihren Computer mit einer Steckdose oder einem Router verbinden) und **Switches**. Switches sind intelligente Geräte, die lernen, welches Gerät an welchen Anschluss angeschlossen ist, so dass mehrere Geräte gleichzeitig ohne Kollisionen kommunizieren können (meistens). Dadurch ist das moderne Ethernet viel effizienter als seine älteren Versionen.

Ein Ethernet-Rahmen enthält in der Regel:

- **Ziel-MAC-Adresse:** Die Hardware-Adresse des Empfängers im lokalen Netz.
- **Quell-MAC-Adresse:** Die Hardware-Adresse des Senders im lokalen Netz.
- **EtherType:** Gibt an, zu welchem Netzwerkschichtprotokoll die Daten gehören (z. B. IPv4, IPv6).
- **Payload:** Die eigentlichen Daten, die übertragen werden (z. B. ein IP-Paket).
- **Frame Check Sequence (FCS):** Zur Fehlererkennung.
![[Pasted image 20250930060721.png]]

## Hubs, Switches und die Verwaltung des Datenverkehrs

Wenn Sie mehrere Geräte in einem kabelgebundenen Ethernet-Netzwerk verbinden (in der Regel in einer Sterntopologie), verwenden Sie ein zentrales Verbindungsgerät. In der Vergangenheit war dies oft ein **Hub**, aber moderne Netzwerke verwenden fast ausschließlich **Switches**. Das Verständnis des Unterschieds ist der Schlüssel zum Verständnis der modernen Netzwerkleistung.

![[Pasted image 20250930060729.png]]

### Hubs (Layer 1 Device)

- **Funktion:** Ein Hub ist ein einfaches Gerät, das auf der **Physikalischen Schicht (Schicht 1)** arbeitet. Er fungiert im Wesentlichen als Multiport-Repeater. Wenn ein elektrisches Signal (Bits) an einem Anschluss eingeht, regeneriert der Hub dieses Signal und sendet es an _alle anderen Anschlüsse_, unabhängig vom beabsichtigten Ziel.
- **Intelligenz:** Hubs haben keine wirkliche Intelligenz. Sie schauen nicht auf MAC-Adressen oder Frames. Sie wiederholen lediglich elektrische Signale.
- **Kollisionsbereich:** Da alle Ports den gesamten Verkehr empfangen, befinden sich alle an einen Hub angeschlossenen Geräte im selben **Kollisionsbereich**. Das heißt, wenn zwei Geräte versuchen, genau zur gleichen Zeit zu übertragen, kollidieren ihre Signale im Netz, wodurch die Daten verfälscht werden. Die Geräte müssen Mechanismen wie CSMA/CD verwenden, um vor der Übertragung zuzuhören und Kollisionen zu erkennen und zu beheben. Kollisionen verringern die Effizienz des Netzes erheblich, vor allem, wenn mehr Geräte hinzukommen.
- **Duplex-Modus:** Hubs arbeiten im **Halbduplex**-Modus. Ein Gerät, das an einen Hub angeschlossen ist, kann zu einem bestimmten Zeitpunkt entweder senden _oder_ empfangen, aber nicht beides gleichzeitig (wie ein Walkie-Talkie).
- **Bedeutung:** Hubs sind weitgehend veraltet und werden in modernen Netzwerken aufgrund ihrer Ineffizienz kaum noch verwendet.

Switches (Schicht-2-Gerät) ###

- **Funktion:** Ein Switch ist ein intelligenteres Gerät, das hauptsächlich auf der **Datenübertragungsschicht (Layer 2)** arbeitet. Er empfängt eingehende Frames und prüft die **Ziel-MAC-Adresse** im Header des Frames.
- **Intelligenz:** Switches erstellen und pflegen eine **MAC-Adresstabelle** (auch CAM-Tabelle genannt). Diese Tabelle ordnet die MAC-Adressen der angeschlossenen Geräte dem jeweiligen Switch-Port zu, an dem sie angeschlossen sind. Wenn ein Frame ankommt, sucht der Switch in seiner Tabelle nach der Ziel-MAC-Adresse und leitet den Frame _nur_ an den entsprechenden Port weiter. Ist die Ziel-MAC unbekannt oder eine Broadcast-Adresse (FF:FF:FF:FF:FF:FF:FF), leitet der Switch den Frame an alle Ports außer dem, an dem er angekommen ist.
- **Kollisionsdomäne:** Jeder Port eines Switches stellt eine eigene **Kollisionsdomäne** dar. Da der Switch Frames auf intelligente Weise nur dorthin weiterleitet, wo sie hingehören, stören sich Geräte, die an verschiedene Ports angeschlossen sind, nicht gegenseitig bei ihren Übertragungen. Dadurch werden Kollisionen zwischen den Ports vermieden und die Effizienz des Netzwerks im Vergleich zu Hubs erheblich gesteigert.
- **Duplex-Modus:** Switches arbeiten normalerweise im **Vollduplex**-Modus. Ein Gerät, das an einen Switch-Port angeschlossen ist, kann gleichzeitig Daten senden und empfangen, ohne sich gegenseitig zu stören (wie bei einem Telefongespräch). Dadurch verdoppelt sich die potenzielle Bandbreite der Verbindung (z. B. wird eine 100-Mbps-Verbindung zu 100 Mbps Senden + 100 Mbps Empfangen).
- **Broadcast-Domäne:** Während Switches getrennte Kollisionsdomänen schaffen, gehören alle Ports eines Basis-Switches standardmäßig zur gleichen **Broadcast-Domäne**. Das heißt, wenn ein Gerät einen Broadcast-Frame sendet (für alle Geräte im lokalen Netz bestimmt, MAC-Adresse FF:FF:FF:FF:FF:FF), leitet der Switch ihn an _alle_ anderen Ports weiter. Router (Layer-3-Geräte) werden in der Regel zur Trennung von Broadcast-Domänen verwendet. (Wir werden später auf VLANs eingehen, die es Switches ermöglichen, Broadcast-Domänen zu segmentieren).

### Denken Sie darüber nach

Warum war die Erfindung des Netzwerk-Switches für die Ethernet-Leistung eine so bedeutende Verbesserung gegenüber dem Hub?
## MAC Addresses

![[Pasted image 20250930060738.png]]

Jede Netzwerkkarte (NIC) - die Hardware, die ein Gerät mit einem Netzwerk (kabelgebunden oder Wi-Fi) verbindet - hat eine eindeutige, vom Hersteller eingebrannte Kennung. Diese wird als **MAC-Adresse (Media Access Control)** bezeichnet. Manchmal wird sie auch als physikalische Adresse oder Hardware-Adresse bezeichnet.

- **Format:** Eine MAC-Adresse ist eine 48-Bit-Zahl, die normalerweise als 12 paarweise gruppierte Hexadezimalziffern dargestellt wird (z. B. "00:1A:2B:3C:4D:5E" oder "00-1A-2B-3C-4D-5E").
- **Einzigartigkeit:** MAC-Adressen sollen weltweit eindeutig sein. Die erste Hälfte (die ersten 6 Hex-Ziffern, z. B. "00:1A:2B") ist der **Organizationally Unique Identifier (OUI)**, der einem bestimmten Hersteller zugewiesen wird. Der Hersteller weist dann jeder von ihm produzierten NIC einen eindeutigen Wert für die zweite Hälfte (die letzten 6 Hexadezimalziffern, z. B. "3C:4D:5E") zu.
- **Zweck:** MAC-Adressen werden für die Adressierung von Frames _innerhalb desselben lokalen Netzes_ verwendet. Wenn Ihr Computer Daten an ein anderes Gerät in Ihrem heimischen Wi-Fi- oder kabelgebundenen LAN-Segment senden möchte, verwendet er die MAC-Adresse des Zielgeräts. Switches verwenden MAC-Adressen, um Frames an den richtigen Port weiterzuleiten. Router verwenden MAC-Adressen, um Pakete an das nächste Gerät im lokalen Netzwerksegment weiterzuleiten. Sie sind für die Layer-2-Kommunikation unerlässlich.

### Denk mal drüber nach

Wenn MAC-Adressen eindeutige Identifikatoren für Geräte sind, warum brauchen wir dann auch IP-Adressen (Schicht 3)? Welche unterschiedlichen Rollen spielen sie in der Netzwerkkommunikation?

### Versuchen Sie es selbst

Finden Sie die MAC-Adresse für den Wi-Fi- oder Ethernet-Adapter Ihres Macs.

1. Öffnen Sie **Systemeinstellungen**.
2. Klicken Sie in der Seitenleiste auf **Netzwerk**.
3. Wählen Sie Ihre aktive Netzwerkschnittstelle aus (z. B. **Wi-Fi** oder **Ethernet**).
4. Klicken Sie auf die Schaltfläche **Details...**.
5. Suchen Sie nach der Registerkarte oder dem Abschnitt **Hardware**. Ihre MAC-Adresse sollte dort aufgelistet sein (sie könnte mit "MAC-Adresse" oder "Hardware-Adresse" beschriftet sein). Alternativ können Sie auch das Terminal verwenden:
6. Öffnen Sie die Anwendung **Terminal** (Sie können sie mit der Spotlight-Suche finden).
7. Geben Sie den Befehl `ifconfig en0` (für Wi-Fi, normalerweise `en0` oder `en1`) oder `ifconfig enX` (wobei X die Nummer Ihres Ethernet-Adapters ist, falls Sie einen angeschlossen haben) ein und drücken Sie Enter.
8. Suchen Sie nach der Zeile, die mit `ether` beginnt. Die Folge von Buchstaben und Zahlen nach `ether` ist Ihre MAC-Adresse.
## Network Topologies

![[Pasted image 20250930060750.png]]

Network topology refers to the arrangement or layout of the connections (links) and nodes (devices like computers, switches, routers) in a network. It describes how devices are physically or logically interconnected. Here are some common topologies:

1. **Bus Topology:**
    - **Layout:** All devices share a single communication line or cable (the "bus").
    - **How it works:** Data sent by one device travels along the bus, and all other devices see it, but only the intended recipient accepts it. Terminators are needed at each end of the bus. Devices typically used CSMA/CD to manage access.
    - **Pros:** Simple, inexpensive for small networks.
    - **Cons:** If the main cable fails, the entire network goes down. Collisions are frequent. Difficult to troubleshoot. (Largely obsolete now).
2. **Ring Topology:**
    - **Layout:** Devices are connected in a circular loop. Data travels in one direction around the ring.
    - **How it works:** Each device receives data from one neighbor and passes it to the next. A "token" passing mechanism is often used to control who can transmit, avoiding collisions.
    - **Pros:** Orderly transmission.
    - **Cons:** Failure of one device or cable segment can break the ring (though dual-ring setups add redundancy). Adding/removing devices disrupts the network. (Less common now).
3. **Star Topology:**
    - **Layout:** All devices connect to a central device – historically a hub, but now almost always a **switch**.
    - **How it works:** With a switch, devices send data to the central switch, which then forwards it only to the intended destination device based on MAC address.
    - **Pros:** Easy to install and manage. Failure of one cable/device doesn't affect others (unless the central switch fails). Easy to add/remove devices. Efficient communication with switches (separate collision domains, full-duplex). Most common topology for modern LANs.
    - **Cons:** If the central switch fails, the entire network segment connected to it goes down. Can require more cabling than bus or ring.
4. **Mesh Topology:**
    - **Layout:** Devices are interconnected with many redundant paths. In a _full mesh_, every device connects directly to every other device. In a _partial mesh_, only some devices have multiple connections.
    - **How it works:** Data can take multiple paths, providing high fault tolerance. Often used with routers at Layer 3 to manage paths.
    - **Pros:** Highly reliable and redundant. If one link fails, data can be rerouted.
    - **Cons:** Very expensive due to extensive cabling and complex configuration. Primarily used for critical backbone networks (like parts of the internet) or specific high-availability needs, not typical LANs.
5. **Hybrid Topology:**
    - **Layout:** A combination of two or more different topologies. For example, connecting several star topology networks (each centered around a switch) together via a backbone link.
    - **How it works:** Depends on the specific combination.
    - **Pros:** Flexible, scalable. Can leverage the strengths of different topologies.
    - **Cons:** Can be complex to manage and troubleshoot.

### Think about it

Consider your home network (computers, phones, smart devices connected to your Wi-Fi router). Which topology does it most closely resemble? Why? (Hint: Think about how devices connect to the central router/access point).

That covers the basics for our pre-class preparation! We'll build on these concepts in the live session.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Networking-15-Datalink-Layer-Fundamentals-9afi33phq39ep2g?mode=doc](https://gamma.app/docs/Networking-15-Datalink-Layer-Fundamentals-9afi33phq39ep2g?mode=doc)

Try not to peek before class - spoilers inside!

</aside>

## Microsoft Sysinternals Suite

The Sysinternals Troubleshooting Utilities have been rolled up into a single Suite of tools. This file contains the individual troubleshooting tools and help files.

For exercises please download Microsoft Sysinternals Suite (ARM64 version!) into your Windows VM: [https://download.sysinternals.com/files/SysinternalsSuite-ARM64.zip](https://download.sysinternals.com/files/SysinternalsSuite-ARM64.zip)