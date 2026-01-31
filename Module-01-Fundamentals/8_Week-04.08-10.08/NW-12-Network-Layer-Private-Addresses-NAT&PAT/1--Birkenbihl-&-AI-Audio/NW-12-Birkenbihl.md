Welcome to your preparation for our upcoming session on private IP addresses, Network Address Translation (NAT), and Port Address Translation (PAT). Willkommen zu Ihrer Vorbereitung auf unsere kommende Sitzung über private IP-Adressen, Network Address Translation (NAT) und Port Address Translation (PAT).

Understanding these concepts is important to grasp how most networks, from your home network to large enterprise environments, connect to the Internet and manage their internal addressing. Das Verständnis dieser Konzepte ist wichtig, um zu begreifen, wie die meisten Netzwerke, von Ihrem Heimnetzwerk bis hin zu großen Unternehmensumgebungen, sich mit dem Internet verbinden und ihre interne Adressierung verwalten.

A brief recap: IP addresses. Eine kurze Zusammenfassung: IP-Adressen.

From previous lessons, you know that an IP address, or Internet Protocol address, is a unique numerical identifier assigned to each device connected to a computer network that uses the Internet Protocol for communication. Aus den vorangegangenen Lektionen wissen Sie, dass eine IP-Adresse, oder Internet-Protokoll-Adresse, eine eindeutige numerische Kennzeichnung ist, die jedem Gerät zugewiesen wird, das an ein Computernetzwerk angeschlossen ist, welches das Internet-Protokoll für die Kommunikation verwendet.

Think of this like a postal address for your computer on the Internet. Stellen Sie sich dies wie eine Postadresse für Ihren Computer im Internet vor.

These addresses allow devices to find each other and exchange information. Diese Adressen ermöglichen es den Geräten, einander zu finden und Informationen auszutauschen.

We have primarily dealt with IPv4 addresses, which are 32-bit numbers typically expressed in a dot-decimal format, for example, 192.168.1.1. Wir haben uns hauptsächlich mit IPv4-Adressen befasst, bei denen es sich um 32-Bit-Zahlen handelt, die in der Regel in einem Punkt-Dezimal-Format ausgedrückt werden, zum Beispiel 192.168.1.1.

A key insight is that a device's IP address must be globally unique for it to be directly reachable on the public Internet. Eine wichtige Erkenntnis ist, dass die IP-Adresse eines Geräts weltweit eindeutig sein muss, damit es im öffentlichen Internet direkt erreichbar ist.

No two devices on the public Internet can have the same public IP address at the same time. Keine zwei Geräte im öffentlichen Internet können gleichzeitig die gleiche öffentliche IP-Adresse haben.

The challenge: running out of numbers. Die Herausforderung: Die Zahlen gehen zur Neige.

The IPv4 addressing system, with its 32-bit addresses, provides approximately 2 to the power of 32, or about 4.3 billion, unique addresses. Das IPv4-Adressierungssystem mit seinen 32-Bit-Adressen bietet etwa 2 hoch 32, oder ungefähr 4,3 Milliarden, eindeutige Adressen.

While this seemed like a huge number in the early days of the Internet, the explosive growth of Internet-connected devices, computers, smartphones, servers, IoT devices, and so on, has led to a situation known as IPv4 address exhaustion. Während dies in den Anfängen des Internets wie eine riesige Zahl erschien, hat das explosive Wachstum der mit dem Internet verbundenen Geräte, Computer, Smartphones, Server, IoT-Geräte und so weiter, zu einer Situation geführt, die als IPv4-Adressenerschöpfung bekannt ist.

Simply put, we have run out of freely available unique public IPv4 addresses to assign to every new device. Einfach ausgedrückt: Wir haben keine frei verfügbaren, eindeutigen öffentlichen IPv4-Adressen mehr, die wir jedem neuen Gerät zuweisen könnten.

While IPv6, with its much larger 128-bit address space, is the long-term solution, the transition is happening gradually. IPv6 mit seinem viel größeren 128-Bit-Adressraum ist zwar die langfristige Lösung, aber der Übergang erfolgt schrittweise.

In the meantime, clever techniques have been required to make the most of existing IPv4 addresses. In der Zwischenzeit waren clevere Techniken erforderlich, um die vorhandenen IPv4-Adressen optimal zu nutzen.

This is where private IP addresses and NAT come in. An dieser Stelle kommen private IP-Adressen und NAT ins Spiel.

Private IP addresses: your network's internal space. Private IP-Adressen: Der interne Raum Ihres Netzwerks.

To reduce the need for unique public IPv4 addresses and to allow organizations to build internal networks without needing globally unique IPs for every device, the concept of private IP addresses was introduced. Um den Bedarf an eindeutigen öffentlichen IPv4-Adressen zu verringern und Unternehmen die Möglichkeit zu geben, interne Netze aufzubauen, ohne für jedes Gerät weltweit eindeutige IPs zu benötigen, wurde das Konzept der privaten IP-Adressen eingeführt.

Certain ranges of IPv4 addresses were reserved for use in private networks. Bestimmte Bereiche von IPv4-Adressen wurden für die Verwendung in privaten Netzen reserviert.

These addresses are not routable on the public Internet. Diese Adressen sind im öffentlichen Internet nicht routbar.

This means that Internet routers are configured to directly discard any traffic originating from or destined for these private IP addresses. Das bedeutet, dass Internet-Router so konfiguriert sind, dass sie jeglichen Datenverkehr, der von diesen privaten IP-Adressen ausgeht oder an sie gerichtet ist, direkt verwerfen.

The Internet Engineering Task Force, or IETF, defined these ranges in RFC 1918. Die Internet Engineering Task Force, oder IETF, hat diese Bereiche in RFC 1918 festgelegt.

10.0.0.0 to 10.255.255.255. This is a slash 8 block, meaning the first 8 bits are fixed for the network portion. It can also be written as 10.0.0.0 slash 8. This range provides over 16 million addresses. 10.0.0.0 bis 10.255.255.255. Dies ist ein Slash-8-Block, das heißt, die ersten 8 Bits sind für den Netzwerkteil festgelegt. Er kann auch als 10.0.0.0 Slash 8 geschrieben werden. Dieser Bereich bietet über 16 Millionen Adressen.

172.16.0.0 to 172.31.255.255. A slash 12 block, or 172.16.0.0 slash 12. This range provides over 1 million addresses. 172.16.0.0 bis 172.31.255.255. Ein Slash-12-Block, oder 172.16.0.0 Slash 12. Dieser Bereich bietet über 1 Million Adressen.

192.168.0.0 to 192.168.255.255. A slash 16 block, or 192.168.0.0 slash 16. This range provides over 65,000 addresses. 192.168.0.0 bis 192.168.255.255. Ein Slash-16-Block, oder 192.168.0.0 Slash 16. Dieser Bereich bietet über 65.000 Adressen.

Key characteristics of private IP addresses. Schlüsselmerkmale von privaten IP-Adressen.

Not globally unique. The same private IP address, for example 192.168.1.100, can be used by countless devices on different private networks around the world simultaneously. Nicht weltweit eindeutig. Dieselbe private IP-Adresse, zum Beispiel 192.168.1.100, kann von zahllosen Geräten in verschiedenen privaten Netzen auf der ganzen Welt gleichzeitig verwendet werden.

Your laptop could have this IP address on your home network, and another user's printer could have exactly the same IP address on their office network. Ihr Laptop könnte diese IP-Adresse in Ihrem Heimnetzwerk haben, und der Drucker eines anderen Nutzers könnte genau dieselbe IP-Adresse in dessen Büronetzwerk haben.

This is fine because these networks are isolated from each other with respect to these private IPs. Das ist in Ordnung, da diese Netze in Bezug auf diese privaten IPs voneinander isoliert sind.

Not routable on the public Internet. Routers on the Internet backbone do not forward packets that have a private IP address as source or destination. Nicht im öffentlichen Internet routingfähig. Router im Internet-Backbone leiten keine Pakete weiter, die eine private IP-Adresse als Quelle oder Ziel haben.

Free to use. Anyone can use these address ranges within their private network without needing permission or registration from an Internet authority. Freie Nutzung. Jeder kann diese Adressbereiche innerhalb seines privaten Netzes nutzen, ohne eine Genehmigung oder Registrierung von einer Internetbehörde zu benötigen.

Enhanced security, indirectly. Since devices with private IPs are not directly reachable from the Internet, an additional layer of protection is created. Erhöhte Sicherheit, indirekt. Da Geräte mit privaten IPs nicht direkt aus dem Internet erreichbar sind, wird eine zusätzliche Schutzebene geschaffen.

An external attacker cannot directly attack a device using its private IP address from outside the local network. Ein externer Angreifer kann ein Gerät, das seine private IP-Adresse verwendet, nicht direkt von außerhalb des lokalen Netzes angreifen.

Private IP addresses are used in your home WiFi network, in corporate LANs, or Local Area Networks, and in many other scenarios where devices need to communicate locally but don't all need a unique public IP address. Private IP-Adressen werden in Ihrem WiFi-Heimnetzwerk, in LANs von Unternehmen, oder Local Area Networks, und in vielen anderen Szenarien verwendet, in denen Geräte lokal kommunizieren müssen, aber nicht alle eine eindeutige öffentliche IP-Adresse benötigen.

Try it yourself. Versuchen Sie es selbst.

Check your IP address. On your Mac, go to System Preferences. Prüfen Sie Ihre IP-Adresse. Gehen Sie auf Ihrem Mac zu Systemeinstellungen.

Click on Network in the sidebar. Klicken Sie in der Seitenleiste auf Netzwerk.

Select your active network connection, for example, WiFi or Ethernet. Wählen Sie Ihre aktive Netzwerkverbindung aus, zum Beispiel WiFi oder Ethernet.

Click on the Details button. Klicken Sie auf die Schaltfläche Details.

Look for the IP address listed. Suchen Sie nach der aufgelisteten IP-Adresse.

Does this IP address fall within one of the private RFC 1918 ranges mentioned above? For most home and office networks, it will. Fällt diese IP-Adresse in einen der oben erwähnten privaten RFC 1918-Bereiche? Bei den meisten Heim- und Büronetzwerken ist dies der Fall.

Identify your router's LAN IP. In the same network details on your Mac, look for the Router address. Identifizieren Sie die LAN-IP Ihres Routers. Suchen Sie in den gleichen Netzwerkdetails auf Ihrem Mac nach der Router-Adresse.

This is your router's private IP address on your local network. Dies ist die private IP-Adresse Ihres Routers in Ihrem lokalen Netzwerk.

It acts as a gateway for your devices to reach other networks, including the Internet. Er fungiert als Gateway für Ihre Geräte, um andere Netzwerke, einschließlich des Internets, zu erreichen.

This address is also typically in a private IP range, often something like 192.168.1.1 or 10.0.0.1. Diese Adresse liegt normalerweise auch in einem privaten IP-Bereich, oft so etwas wie 192.168.1.1 oder 10.0.0.1.

The gateway: Network Address Translation, or NAT. Das Gateway: Netzwerk-Adressübersetzung, oder NAT.

So, if devices on your local network have private IP addresses that are not allowed on the Internet, how can they access websites, send emails, or stream videos? Wenn also Geräte in Ihrem lokalen Netzwerk über private IP-Adressen verfügen, die nicht für das Internet zugelassen sind, wie können sie dann auf Websites zugreifen, E-Mails senden oder Videos streamen?

This is where Network Address Translation, or NAT, comes in. An dieser Stelle kommt Network Address Translation, oder NAT, ins Spiel.

NAT is a process typically performed by your router, or a dedicated firewall, that allows multiple devices on a private network to share a single public IP address to connect to the Internet. NAT ist ein Prozess, der in der Regel von Ihrem Router, oder einer speziellen Firewall, durchgeführt wird und der es mehreren Geräten in einem privaten Netzwerk ermöglicht, eine einzige öffentliche IP-Adresse zu nutzen, um eine Verbindung mit dem Internet herzustellen.

The router sits at the boundary between your private network and the public Internet. Der Router befindet sich an der Grenze zwischen Ihrem privaten Netz und dem öffentlichen Internet.

It has at least two IP addresses. Er verfügt über mindestens zwei IP-Adressen.

A private IP address on the local network, for example 192.168.1.1, which serves as the default gateway for your devices. Eine private IP-Adresse im lokalen Netz, zum Beispiel 192.168.1.1, die als Standard-Gateway für Ihre Geräte dient.

A public IP address assigned by your Internet Service Provider, or ISP, which is globally unique and can be routed over the Internet. Eine öffentliche IP-Adresse, die von Ihrem Internet Service Provider, oder ISP, zugewiesen wird, die weltweit eindeutig ist und über das Internet geroutet werden kann.

How NAT works, a simplified view. Wie NAT funktioniert, eine vereinfachte Darstellung.

Outbound traffic, your computer to the Internet. Ausgehender Verkehr, Ihr Computer zum Internet.

Your computer, for example with private IP 192.168.1.100, wants to send a request to a web server on the Internet, for example www.google.com with public IP 142.250.180.196. Ihr Computer, zum Beispiel mit der privaten IP 192.168.1.100, möchte eine Anfrage an einen Webserver im Internet senden, zum Beispiel www.google.com mit der öffentlichen IP 142.250.180.196.

The packet leaves your computer with source IP 192.168.1.100, which is private, and destination IP 142.250.180.196, which is public. Das Paket verlässt Ihren Computer mit Quell-IP 192.168.1.100, die privat ist, und Ziel-IP 142.250.180.196, die öffentlich ist.

The packet reaches your router. The router performs NAT. Das Paket erreicht Ihren Router. Der Router führt NAT durch.

It changes the source IP address from your computer's private IP, 192.168.1.100, to the router's public IP address, for example 80.100.20.30. Er ändert die Quell-IP-Adresse von der privaten IP Ihres Computers, 192.168.1.100, in die öffentliche IP-Adresse des Routers, zum Beispiel 80.100.20.30.

It stores this translation, private IP plus original source port, to public IP plus new source port, in a special table, the NAT table. Er speichert diese Umwandlung, private IP plus ursprünglicher Quellport, zu öffentlicher IP plus neuer Quellport, in einer speziellen Tabelle, der NAT-Tabelle.

The modified packet, now with a public source IP, is sent out onto the Internet. Das geänderte Paket, jetzt mit einer öffentlichen Quell-IP, wird ins Internet gesendet.

Inbound traffic, Internet back to your computer. Eingehender Verkehr, Internet zurück zu Ihrem Computer.

The web server, 142.250.180.196, sends a response. This response is addressed to your router's public IP address, 80.100.20.30, because that was the source IP address the server saw. Der Webserver, 142.250.180.196, sendet eine Antwort. Diese Antwort ist an die öffentliche IP-Adresse Ihres Routers, 80.100.20.30, adressiert, da dies die Quell-IP-Adresse war, die der Server sah.

The packet arrives at your router with source IP 142.250.180.196, which is public, and destination IP 80.100.20.30, your router's public IP. Das Paket kommt bei Ihrem Router an mit Quell-IP 142.250.180.196, die öffentlich ist, und Ziel-IP 80.100.20.30, die öffentliche IP Ihres Routers.

The router consults its NAT table. It looks up the entry associated with the incoming packet, based on the port numbers, which we will discuss next. Der Router konsultiert seine NAT-Tabelle. Er sucht den Eintrag, der mit dem eingehenden Paket verbunden ist, basierend auf den Portnummern, die wir als nächstes besprechen werden.

It finds the original private IP address, 192.168.1.100, from which this communication originated. Er findet die ursprüngliche private IP-Adresse, 192.168.1.100, von der diese Kommunikation ausging.

It changes the destination IP address of the packet from its own public IP, 80.100.20.30, back to your computer's private IP, 192.168.1.100. Er ändert die Ziel-IP-Adresse des Pakets von seiner eigenen öffentlichen IP, 80.100.20.30, zurück zur privaten IP Ihres Computers, 192.168.1.100.

The packet is then forwarded to your computer on the local network. Das Paket wird dann an Ihren Computer im lokalen Netz weitergeleitet.

So, your router acts as a proxy, making all traffic originating from your private network appear to come from its single public IP address. Ihr Router fungiert also als Proxy, der den gesamten von Ihrem privaten Netz ausgehenden Datenverkehr so aussehen lässt, als stamme er von seiner einzigen öffentlichen IP-Adresse.

Handling multiple devices: Port Address Translation, or PAT. Umgang mit mehreren Geräten: Port Address Translation, oder PAT.

A common question arises. If multiple devices on your private network, for example your laptop, your phone, a smart TV, all use NAT to share the same public IP address, how can the router know which device an incoming response packet is intended for? Es stellt sich eine häufige Frage. Wenn mehrere Geräte in Ihrem privaten Netzwerk, zum Beispiel Ihr Laptop, Ihr Telefon, ein Smart-TV, alle NAT verwenden, um sich dieselbe öffentliche IP-Adresse zu teilen, wie kann der Router dann wissen, für welches Gerät ein eingehendes Antwortpaket bestimmt ist?

This is where Port Address Translation, or PAT, also known as NAT Overload, comes in. Hier kommt Port Address Translation, oder PAT, auch bekannt als NAT Overload, ins Spiel.

PAT is the most common type of NAT. PAT ist die häufigste Art von NAT.

When your computer sends an outbound packet, it has not only a source IP address but also a source port number. Wenn Ihr Computer ein ausgehendes Paket sendet, hat es nicht nur eine Quell-IP-Adresse, sondern auch eine Quellportnummer.

For example, when your browser makes a web request, it might use a random source port like 51000. Wenn Ihr Browser zum Beispiel eine Web-Anfrage stellt, könnte er einen zufälligen Quell-Port wie 51000 verwenden.

The destination port is typically 80, for HTTP, or 443, for HTTPS. Der Zielport ist normalerweise 80, für HTTP, oder 443, für HTTPS.

PAT takes advantage of these port numbers. PAT macht sich diese Portnummern zunutze.

When the router translates the private source IP to its public IP, it often also translates the source port number. Wenn der Router die private Quell-IP in seine öffentliche IP übersetzt, übersetzt er oft auch die Quell-Portnummer.

This ensures that each active session from an internal device maps to a unique combination of the router's public IP address plus a unique source port number in the NAT table. Dadurch wird sichergestellt, dass jede aktive Sitzung von einem internen Gerät in der NAT-Tabelle einer eindeutigen Kombination aus der öffentlichen IP-Adresse des Routers plus einer eindeutigen Quellportnummer zugeordnet wird.

An example. Ein Beispiel.

Your laptop, 192.168.1.100, source port 51000, sends a request. The router might map this to public IP, source port 34001. Ihr Laptop, 192.168.1.100, Quellport 51000, sendet eine Anfrage. Der Router könnte diese auf öffentliche IP, Quellport 34001 abbilden.

Your phone, 192.168.1.101, source port 52000, sends a request simultaneously. The router might map this to public IP, source port 34002. Ihr Telefon, 192.168.1.101, Quellport 52000, sendet gleichzeitig eine Anfrage. Der Router könnte diese auf öffentliche IP, Quellport 34002 abbilden.

When a response comes back to the router's public IP address, the router looks at the destination port number in the incoming packet. Wenn eine Antwort an die öffentliche IP-Adresse des Routers zurückkommt, sieht sich der Router die Ziel-Portnummer im eingehenden Paket an.

That was the source port number it assigned and recorded. Das war die Quell-Portnummer, die er zugewiesen und aufgezeichnet hat.

Using that port number, it can uniquely determine which internal device the packet is intended for. Anhand dieser Portnummer kann er eindeutig feststellen, für welches interne Gerät das Paket bestimmt ist.

It then translates the destination IP address back to the correct private IP address and the destination port back to the internal device's original source port. Anschließend wird die Ziel-IP-Adresse in die korrekte private IP-Adresse und der Ziel-Port in den ursprünglichen Quell-Port des internen Geräts zurückübersetzt.

By using different source port numbers on the public side for different internal sessions, a single public IP address can be shared by many private IP devices, effectively overloading the single public IP address. Durch die Verwendung unterschiedlicher Quellportnummern auf der öffentlichen Seite für verschiedene interne Sitzungen kann eine einzige öffentliche IP-Adresse von vielen privaten IP-Geräten gemeinsam genutzt werden, wodurch die einzelne öffentliche IP-Adresse effektiv überlastet wird.

This is why your entire household can browse the Internet simultaneously while using only a single public IP address provided to you by your ISP. Aus diesem Grund kann Ihr gesamter Haushalt gleichzeitig im Internet surfen und dabei nur eine einzige öffentliche IP-Adresse verwenden, die Ihnen von Ihrem ISP zur Verfügung gestellt wird.

Think about it. Denken Sie darüber nach.

Scalability. How does PAT improve the scalability of IPv4 usage compared to a simple NAT that only changes IP addresses? Skalierbarkeit. Wie verbessert PAT die Skalierbarkeit der IPv4-Nutzung im Vergleich zu einem einfachen NAT, das nur die IP-Adressen ändert?

Security implications. If someone on the Internet tries to send an unsolicited packet to your router's public IP address, how would NAT slash PAT typically handle it if there is no entry for that traffic in the NAT table? Auswirkungen auf die Sicherheit. Wenn jemand im Internet versucht, ein unerwünschtes Paket an die öffentliche IP-Adresse Ihres Routers zu senden, wie würde NAT Slash PAT normalerweise damit umgehen, wenn in der NAT-Tabelle kein Eintrag für diesen Datenverkehr vorhanden ist?

Hint: This is an important reason why NAT is often considered a basic form of firewall. Hinweis: Dies ist ein wichtiger Grund, warum NAT oft als eine grundlegende Form der Firewall betrachtet wird.

Limitations. Can you think of applications or services that might have trouble functioning correctly through NAT? Einschränkungen. Fallen Ihnen Anwendungen oder Dienste ein, die Probleme haben könnten, durch NAT korrekt zu funktionieren?

Think about applications that require incoming connections to be initiated from the Internet, or protocols that embed IP address information in their data payload. Denken Sie an Anwendungen, die erfordern, dass eingehende Verbindungen aus dem Internet initiiert werden, oder an Protokolle, die IP-Adressinformationen in ihre Daten-Nutzlast einbetten.

This material should give you a solid foundation on private IP addresses, NAT, and PAT. Dieses Material sollte Ihnen eine solide Grundlage über private IP-Adressen, NAT und PAT vermitteln.

In our next live session, we will delve deeper into these concepts, explore different types of NAT, and discuss their implications. In unserer nächsten Live-Sitzung werden wir diese Konzepte vertiefen, verschiedene Arten von NAT untersuchen und ihre Auswirkungen diskutieren.

The slides for the live session can be viewed here. Try not to peek before class, spoilers inside! Die Folien für die Live-Sitzung können hier eingesehen werden. Versuchen Sie, nicht vor dem Unterricht zu schauen, Spoiler im Inneren!