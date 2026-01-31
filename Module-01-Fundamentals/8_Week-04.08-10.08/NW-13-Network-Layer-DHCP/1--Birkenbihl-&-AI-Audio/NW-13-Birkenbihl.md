Welcome to your preparation for our upcoming lesson on the Dynamic Host Configuration Protocol, or DHCP. The goal of this material is to familiarize you with the basic concepts of DHCP and to explain why it is essential in modern networks and how it generally works. Please read the information carefully. Willkommen zu Ihrer Vorbereitung auf unsere kommende Lektion über das Dynamic Host Configuration Protocol, oder DHCP. Ziel dieses Materials ist es, Sie mit den grundlegenden Konzepten von DHCP vertraut zu machen und zu erklären, warum es in modernen Netzwerken unerlässlich ist und wie es im Allgemeinen funktioniert. Bitte lesen Sie sich die Informationen sorgfältig durch.

What is DHCP? Was ist DHCP?

Imagine you enter a large library, and instead of a system that assigns you a seat, everyone picks one themselves. Chaos, right? Two people might try to sit on the same chair, or some sections are overcrowded while others are empty. Stellen Sie sich vor, Sie betreten eine große Bibliothek, und statt eines Systems, das Ihnen einen Platz zuweist, sucht sich jeder einen aus. Ein Chaos, nicht wahr? Zwei Personen könnten versuchen, auf demselben Stuhl zu sitzen, oder einige Abteilungen sind überfüllt, während andere leer sind.

In the world of computer networks, every device needs a unique seat, or more precisely, an address to communicate. This address is known as an IP address. In der Welt der Computernetzwerke benötigt jedes Gerät einen eindeutigen Sitzplatz, oder genauer gesagt, eine Adresse, um zu kommunizieren. Diese Adresse ist als IP-Adresse bekannt.

The Dynamic Host Configuration Protocol, or DHCP, is like the friendly librarian for networks. It is a network management protocol used in IP networks, where a DHCP server automatically assigns an IP address and other network configuration parameters to each device in a network so that it can communicate with other IP networks. Das Dynamic Host Configuration Protocol, oder DHCP, ist so etwas wie der freundliche Bibliothekar für Netzwerke. Es ist ein Netzwerkverwaltungsprotokoll, das in IP-Netzwerken verwendet wird, wobei ein DHCP-Server jedem Gerät in einem Netzwerk automatisch eine IP-Adresse und andere Netzwerkkonfigurationsparameter zuweist, damit es mit anderen IP-Netzwerken kommunizieren kann.

Without DHCP, network administrators would have to manually configure every device that joins the network, a tedious and error-prone task, especially in large environments. Ohne DHCP müssten Netzwerkadministratoren jedes Gerät, das dem Netzwerk beitritt, manuell konfigurieren, eine mühsame und fehleranfällige Aufgabe, insbesondere in großen Umgebungen.

Reasons why DHCP is so important: Automation. Manual configuration of IP addresses for each device becomes unnecessary. Gründe, warum DHCP so wichtig ist: Automatisierung. Die manuelle Konfiguration von IP-Adressen für jedes Gerät wird überflüssig.

Accuracy. It reduces the risk of human errors, such as assigning the same IP address to two different devices, known as IP conflict, or entering incorrect subnet masks or gateway addresses. Genauigkeit. Es verringert das Risiko menschlicher Fehler, wie zum Beispiel die Zuweisung derselben IP-Adresse an zwei verschiedene Geräte, bekannt als IP-Konflikt, oder die Eingabe falscher Subnetzmasken oder Gateway-Adressen.

Efficiency. IP addresses are leased for a specific period and can be returned to a pool for reuse when a device leaves the network. This is especially useful for networks with many transient devices, such as a public Wi-Fi hotspot. Effizienz. IP-Adressen werden für einen bestimmten Zeitraum geleast und können zur Wiederverwendung in einen Pool zurückgegeben werden, wenn ein Gerät das Netz verlässt. Dies ist besonders nützlich für Netzwerke mit vielen flüchtigen Geräten, wie zum Beispiel ein öffentlicher Wi-Fi-Hotspot.

Central management. Network parameters such as DNS server addresses and default gateway addresses can be managed and distributed from a central point. Zentrales Management. Netzwerkparameter wie DNS-Serveradressen und Standard-Gateway-Adressen können von einem zentralen Punkt aus verwaltet und verteilt werden.

Overview of important network concepts. Before we delve deeper into DHCP, let us review some basic network concepts. Überblick über die wichtigsten Netzwerk-Konzepte. Bevor wir uns näher mit DHCP beschäftigen, sollten wir einige grundlegende Netzwerkkonzepte wiederholen.

IP address, or Internet Protocol address. A unique numerical identifier assigned to each device connected to a computer network that uses the Internet Protocol for communication. Think of it like a specific street address for a house on the internet. For example, one nine two dot one six eight dot one dot one hundred. IP-Adresse, oder Internet-Protokoll-Adresse. Eine eindeutige numerische Kennzeichnung, die jedem Gerät zugewiesen wird, das an ein Computernetzwerk angeschlossen ist, das das Internet-Protokoll zur Kommunikation verwendet. Stellen Sie sich das vor wie eine bestimmte Straßenadresse für ein Haus im Internet. Zum Beispiel eins neun zwei Punkt eins sechs acht Punkt eins Punkt einhundert.

Subnet mask. Used to divide an IP address into two parts: one part identifies the network, called the network address, the other part identifies the specific device in that network, called the host address. For example, two five five dot two five five dot two five five dot zero. Subnetzmaske. Wird verwendet, um eine IP-Adresse in zwei Teile zu unterteilen: ein Teil identifiziert das Netzwerk, genannt die Netzwerkadresse, der andere Teil identifiziert das spezifische Gerät in diesem Netzwerk, genannt die Hostadresse. Zum Beispiel zwei fünf fünf Punkt zwei fünf fünf Punkt zwei fünf fünf Punkt null.

It helps devices determine whether another IP address is on the same local network or on a remote network. Sie hilft den Geräten festzustellen, ob sich eine andere IP-Adresse im selben lokalen Netz oder in einem entfernten Netz befindet.

Default gateway. A router in a network that serves as an access point to other networks. When your computer wants to send information to a device that is not on its local network, for example a website on the internet, it sends the traffic to the default gateway. The gateway then forwards the traffic to its destination. Standard-Gateway. Ein Router in einem Netzwerk, der als Zugangspunkt zu anderen Netzwerken dient. Wenn Ihr Computer Informationen an ein Gerät senden möchte, das sich nicht in seinem lokalen Netzwerk befindet, zum Beispiel eine Website im Internet, sendet er den Datenverkehr an das Standard-Gateway. Das Gateway leitet den Datenverkehr dann an sein Ziel weiter.

DNS server, or Domain Name System server. Translates human-readable domain names, such as www dot google dot com, into machine-readable IP addresses, such as one seven two dot two one seven dot one six zero dot one four two. Computers use IP addresses to communicate, but humans can remember names more easily. DNS-Server, oder Domain Name System Server. Übersetzt von Menschen lesbare Domänennamen, wie www Punkt google Punkt com, in maschinenlesbare IP-Adressen, wie eins sieben zwei Punkt zwei eins sieben Punkt eins sechs null Punkt eins vier zwei. Computer verwenden IP-Adressen zur Kommunikation, aber Menschen können sich Namen leichter merken.

Try it yourself: Check your Mac's network configuration. You can see these settings on your own Mac. Versuchen Sie es selbst: Prüfen Sie die Netzwerkkonfiguration Ihres Macs. Sie können diese Einstellungen auf Ihrem eigenen Mac sehen.

Open System Preferences. Click on Network in the sidebar. Select your active network connection, for example Wi-Fi or Ethernet. Öffnen Sie Systemeinstellungen. Klicken Sie in der Seitenleiste auf Netzwerk. Wählen Sie Ihre aktive Netzwerkverbindung aus, zum Beispiel Wi-Fi oder Ethernet.

Click on the Details button next to your active connection. In the window that appears, you will see your IP address, the subnet mask, the router, which is the default gateway, and the DNS servers under the DNS tab. Klicken Sie auf die Schaltfläche Details neben Ihrer aktiven Verbindung. In dem daraufhin angezeigten Fenster sehen Sie Ihre IP-Adresse, die Subnetzmaske, den Router, das ist das Standard-Gateway, und die DNS-Server unter der Registerkarte DNS.

Pay attention to whether it says configure IPv4: using DHCP. This means your Mac is acting as a DHCP client. Achten Sie darauf, ob dort steht IPv4 konfigurieren: DHCP verwenden. Das bedeutet, dass Ihr Mac als DHCP-Client fungiert.

How DHCP works: The DORA process. Wie DHCP funktioniert: Der DORA-Prozess.

The process by which a device receives network configuration information from a DHCP server is often referred to by the acronym DORA, which stands for Discover, Offer, Request, and Acknowledge. This is a four-step handshake between the DHCP client, your device, and the DHCP server. Der Prozess, durch den ein Gerät Netzwerkkonfigurationsinformationen von einem DHCP-Server erhält, wird oft mit dem Akronym DORA bezeichnet, das für Discover, Offer, Request und Acknowledge steht. Dies ist ein vierstufiger Handshake zwischen dem DHCP-Client, Ihrem Gerät, und dem DHCP-Server.

Step one: Discover, or DHCPDISCOVER. When a DHCP client device boots up or connects to a network and is configured to automatically receive an IP address, it has no IP information. Schritt eins: Erkennen, oder DHCPDISCOVER. Wenn ein DHCP-Client-Gerät hochfährt oder eine Verbindung zu einem Netzwerk herstellt und so konfiguriert ist, dass es automatisch eine IP-Adresse erhält, hat es keine IP-Informationen.

It sends a DHCPDISCOVER message onto the local network. This message is like the client calling out: Is there a DHCP server out there that can give me an IP address? Es sendet eine DHCPDISCOVER-Nachricht in das lokale Netz. Diese Nachricht ist so, als würde der Client rufen: Gibt es da draußen einen DHCP-Server, der mir eine IP-Adresse geben kann?

Since the client does not yet have an IP address, it uses zero dot zero dot zero dot zero as its source IP address and two five five dot two five five dot two five five dot two five five as the destination IP address, which is the broadcast address. Da der Client noch keine IP-Adresse hat, verwendet er null Punkt null Punkt null Punkt null als seine Quell-IP-Adresse und zwei fünf fünf Punkt zwei fünf fünf Punkt zwei fünf fünf Punkt zwei fünf fünf als Ziel-IP-Adresse, das ist die Broadcast-Adresse.

Step two: Offer, or DHCPOFFER. All DHCP servers on the local network that receive the DHCPDISCOVER message and have available IP addresses can respond. Schritt zwei: Angebot, oder DHCPOFFER. Alle DHCP-Server im lokalen Netz, die die DHCPDISCOVER-Nachricht empfangen und über verfügbare IP-Adressen verfügen, können darauf antworten.

Each interested DHCP server responds with a DHCPOFFER message. This message is sent back to the client via unicast, if possible using the client's MAC address, or via broadcast. Jeder interessierte DHCP-Server antwortet mit einer DHCPOFFER-Nachricht. Diese Nachricht wird per Unicast an den Client zurückgesendet, wenn möglich unter Verwendung der MAC-Adresse des Clients, oder per Broadcast.

The offer contains a proposed IP address, the subnet mask, the default gateway, the DNS server or servers, and the lease duration, which is the time period during which the client can use this IP address. Das Angebot enthält eine vorgeschlagene IP-Adresse, die Subnetzmaske, das Standard-Gateway, den oder die DNS-Server und die Leasedauer, das ist die Zeitspanne, in der der Client diese IP-Adresse nutzen kann.

It is possible for a client to receive offers from multiple DHCP servers. Es ist möglich, dass ein Client Angebote von mehreren DHCP-Servern erhält.

Step three: Request, or DHCPREQUEST. The client reviews the offer or offers. Typically, it accepts the first offer it receives. Schritt drei: Anfrage, oder DHCPREQUEST. Der Client prüft das Angebot oder die Angebote. Normalerweise nimmt er das erste Angebot an, das er erhält.

The client then sends a DHCPREQUEST message back onto the network. This message essentially says: I want to accept the IP address, the offered IP, from server, the server IP. Der Client sendet dann eine DHCPREQUEST-Nachricht an das Netz zurück. Diese Nachricht besagt im Wesentlichen: Ich möchte die IP-Adresse, die angebotene IP, von Server, die Server-IP, annehmen.

Sending this message informs the selected server that its offer has been accepted, and it also informs all other DHCP servers that made offers that their offers have been rejected. This prevents other servers from reserving an IP address that will not be used. Durch das Senden dieser Nachricht wird der ausgewählte Server darüber informiert, dass sein Angebot angenommen wurde, und auch alle anderen DHCP-Server, die Angebote gemacht haben, werden darüber informiert, dass ihre Angebote abgelehnt wurden. Dadurch wird verhindert, dass andere Server eine IP-Adresse reservieren, die nicht genutzt wird.

Step four: Acknowledgment, or DHCPACK, and Negative Acknowledgment, or DHCPNAK. The DHCP server whose offer was accepted completes the lease. Schritt vier: Bestätigung, oder DHCPACK, und Negative Bestätigung, oder DHCPNAK. Der DHCP-Server, dessen Angebot angenommen wurde, schließt den Mietvertrag ab.

It sends a DHCPACK message, which stands for Acknowledge, to the client. This message confirms all configuration parameters, including the IP address, subnet mask, default gateway, DNS servers, and lease duration. Er sendet eine DHCPACK-Nachricht, das steht für Acknowledge, an den Client. Diese Nachricht bestätigt alle Konfigurationsparameter, einschließlich der IP-Adresse, der Subnetzmaske, des Standard-Gateways, der DNS-Server und der Leasingdauer.

Now the client can configure its network interface with the specified IP address and begin communication on the network. Nun kann der Client seine Netzwerkschnittstelle mit der angegebenen IP-Adresse konfigurieren und die Kommunikation im Netzwerk aufnehmen.

If for some reason the offered IP address is no longer available or the server cannot fulfill the request, the server may send a DHCPNAK message, which stands for Negative Acknowledge. In this case, the client would have to restart the DORA process. Wenn die angebotene IP-Adresse aus irgendeinem Grund nicht mehr verfügbar ist oder der Server die Anfrage nicht erfüllen kann, sendet der Server möglicherweise eine DHCPNAK-Nachricht, das steht für Negative Acknowledge. In diesem Fall müsste der Client den DORA-Prozess neu starten.

This DORA process happens very quickly, typically within a few seconds, every time a device connects to a DHCP-enabled network. Dieser DORA-Prozess läuft sehr schnell ab, in der Regel innerhalb weniger Sekunden, jedes Mal, wenn ein Gerät eine Verbindung zu einem DHCP-fähigen Netz herstellt.

Think about it: Lease expiration and renewal. The IP address assigned by a DHCP server is not permanent but is leased for a specific duration. Denken Sie darüber nach: Ablauf und Erneuerung von Leases. Die von einem DHCP-Server zugewiesene IP-Adresse ist nicht dauerhaft, sondern wird für eine bestimmte Dauer geleast.

Why do you think leases are not permanent? What do you think happens when an IP lease expires? Hint: The client does not simply stop working. It attempts to renew the lease, typically when fifty percent of the lease time has elapsed, by sending a DHCPREQUEST directly to the server that granted the lease. Warum, glauben Sie, sind Leases nicht dauerhaft? Was passiert Ihrer Meinung nach, wenn ein IP-Leasing abläuft? Hinweis: Der Client hört nicht einfach auf zu arbeiten. Er versucht, den Lease zu erneuern, in der Regel, wenn fünfzig Prozent der Lease-Zeit verstrichen sind, indem er eine DHCPREQUEST direkt an den Server sendet, der den Lease gewährt hat.

Important information provided by DHCP. A DHCP server can provide a client with a variety of configuration parameters. The most common include: Wichtige von DHCP bereitgestellte Informationen. Ein DHCP-Server kann einen Client mit einer Reihe von Konfigurationsparametern versorgen. Zu den häufigsten gehören:

IP address. A unique address for the client on the network. IP-Adresse. Eine eindeutige Adresse für den Client im Netz.

Subnet mask. Defines the network and host portions of the IP address. Subnetzmaske. Definiert die Netzwerk- und Host-Anteile der IP-Adresse.

Default gateway, or router address. The IP address of the router the client should use to reach external networks. Standard-Gateway, oder Router-Adresse. Die IP-Adresse des Routers, den der Client verwenden soll, um externe Netzwerke zu erreichen.

DNS server address or addresses. IP address or addresses of the DNS servers for domain name resolution. DNS-Server-Adresse oder Adressen. IP-Adresse oder Adressen der DNS-Server für die Auflösung von Domänennamen.

Lease duration. The time period for which the IP address is valid. Leasingdauer. Der Zeitraum, für den die IP-Adresse gültig ist.

Domain name. The domain name the client should use. Domänenname. Der Domänenname, den der Client verwenden soll.

Other options. Such as NTP servers for time synchronization, TFTP servers for network booting, and more, as defined in the DHCP options. Andere Optionen. Wie zum Beispiel NTP-Server für die Zeitsynchronisation, TFTP-Server für das Booten im Netzwerk und weitere, definiert in den DHCP-Optionen.

DHCP server and client roles. DHCP server. This is a specially configured network server, or a device such as a router with DHCP server functionality, that manages a pool of IP addresses and leases them to client devices. It listens for DHCPDISCOVER messages from clients and responds according to the DORA process. DHCP-Server- und Client-Rollen. DHCP-Server. Dies ist ein speziell konfigurierter Netzwerkserver, oder ein Gerät wie ein Router mit DHCP-Server-Funktionalität, der einen Pool von IP-Adressen verwaltet und sie an Client-Geräte vermietet. Er lauscht auf DHCPDISCOVER-Nachrichten von Clients und antwortet gemäß dem DORA-Prozess.

DHCP client. Any network-capable device, such as computers, smartphones, printers, smart TVs, that is configured to automatically obtain its IP address and network settings from a DHCP server. Most operating systems have a built-in DHCP client. DHCP-Client. Jedes netzwerkfähige Gerät, zum Beispiel Computer, Smartphone, Drucker, Smart-TV, das so konfiguriert ist, dass es seine IP-Adresse und Netzwerkeinstellungen automatisch von einem DHCP-Server bezieht. Die meisten Betriebssysteme haben einen integrierten DHCP-Client.

Think about it: No DHCP server? What happens if a device is configured to use DHCP but there is no DHCP server on the network or the server is down? Denken Sie darüber nach: Kein DHCP-Server? Was passiert, wenn ein Gerät für die Verwendung von DHCP konfiguriert ist, es aber keinen DHCP-Server im Netzwerk gibt oder der Server ausgefallen ist?

The device is unable to obtain an IP address through the DORA process. Das Gerät ist nicht in der Lage, über den DORA-Prozess eine IP-Adresse zu erhalten.

Many operating systems then fall back on Automatic Private IP Addressing, or APIPA, or Link-Local Addressing. The device assigns itself an IP address from a special reserved range, for example one six nine dot two five four dot x dot x for IPv4. Viele Betriebssysteme greifen dann auf Automatic Private IP Addressing, oder APIPA, oder Link-Local Addressing zurück. Das Gerät weist sich selbst eine IP-Adresse aus einem speziellen reservierten Bereich zu, zum Beispiel eins sechs neun Punkt zwei fünf vier Punkt x Punkt x für IPv4.

Devices using APIPA can communicate with other APIPA devices on the same local network segment, but they cannot communicate with devices on other networks or on the internet because they do not have a default gateway or valid DNS information. You may see an error message such as limited connectivity or self-assigned IP. Geräte, die APIPA verwenden, können mit anderen APIPA-Geräten im selben lokalen Netzwerksegment kommunizieren, aber sie können nicht mit Geräten in anderen Netzwerken oder im Internet kommunizieren, da sie kein Standard-Gateway oder gültige DNS-Informationen haben. Möglicherweise wird eine Fehlermeldung wie eingeschränkte Konnektivität oder selbst zugewiesene IP angezeigt.

Benefits of using DHCP. We have already discussed some of these, but let us summarize the key benefits once more. Vorteile der Verwendung von DHCP. Einige davon haben wir bereits angesprochen, aber fassen wir die wichtigsten Vorteile noch einmal zusammen.

Simplified administration. Significantly reduces the manual effort and technical knowledge required to connect devices to a network. Vereinfachte Administration. Verringert den manuellen Aufwand und die technischen Kenntnisse, die für den Anschluss von Geräten an ein Netzwerk erforderlich sind, erheblich.

Reduced IP conflicts. Prevents the accidental assignment of the same IP address to multiple devices. Reduzierte IP-Konflikte. Verhindert die versehentliche Zuweisung der gleichen IP-Adresse an mehrere Geräte.

Efficient IP address management. IP addresses are dynamically assigned and reclaimed, ensuring efficient use of a limited IP address pool. Effizientes IP-Adressmanagement. IP-Adressen werden dynamisch zugewiesen und zurückverlangt, was eine effiziente Nutzung eines begrenzten IP-Adresspools gewährleistet.

Central configuration. Enables administrators to manage and update network parameters, such as DNS servers or gateway addresses, from a single location. Changes are automatically propagated to clients when they renew their leases. Zentrale Konfiguration. Ermöglicht Administratoren die Verwaltung und Aktualisierung von Netzwerkparametern, wie DNS-Servern oder Gateway-Adressen, von einem einzigen Standort aus. Die Änderungen werden automatisch an die Clients weitergegeben, wenn diese ihre Mietverträge erneuern.

Mobility and scalability. Easy adaptation to devices moving between networks or to a large number of devices joining or leaving the network, for example guest Wi-Fi. Mobilität und Skalierbarkeit. Einfache Anpassung an Geräte, die zwischen Netzwerken wechseln, oder an eine große Anzahl von Geräten, die dem Netzwerk beitreten oder es verlassen, zum Beispiel Gast-Wi-Fi.

This concludes your preparation for the DHCP course. Understanding these concepts will allow you to get the most out of our interactive session. Write down any questions you have. Dies ist der Abschluss Ihrer Vorbereitung auf den DHCP-Kurs. Wenn Sie diese Konzepte verstehen, können Sie den größten Nutzen aus unserer interaktiven Sitzung ziehen. Notieren Sie sich alle Fragen, die Sie haben.

The slides for the live session can be viewed here. Try not to peek before class, spoilers inside. Die Folien für die Live-Sitzung können hier angesehen werden. Versuchen Sie nicht, vor dem Unterricht zu spicken, Spoiler enthalten.