Welcome! This preparation material is your starting point for our upcoming session on virtual private networks, VPNs, and tunneling. We will explore the key concepts together so that you are well prepared for the lesson. As you go through the explanations, you will find the try it yourself and think about it sections to deepen your understanding. Willkommen! Dieses Vorbereitungsmaterial ist Ihr Ausgangspunkt für unsere bevorstehende Sitzung über virtuelle private Netzwerke, VPNs und Tunneling. Wir werden die wichtigsten Konzepte gemeinsam erforschen, damit Sie gut auf die Lektion vorbereitet sind. Während Sie die Erklärungen durchgehen, finden Sie die Abschnitte „Versuchen Sie es selbst" und „Denken Sie darüber nach", um Ihr Verständnis zu vertiefen.

What is a virtual private network, VPN? Was ist ein virtuelles privates Netzwerk, VPN?

Imagine you are sending a valuable package via the public postal system. You would not want anyone to see or tamper with the contents. A VPN works like a secure, private courier service for your internet data. Instead of your data being transmitted openly over the internet, a VPN creates a secure, encrypted tunnel between your device, computer or smartphone, and a VPN server. This server then forwards your data to its final destination on the internet. Stellen Sie sich vor, Sie verschicken ein wertvolles Paket über das öffentliche Postsystem. Sie möchten nicht, dass irgendjemand den Inhalt sehen oder daran herumfummeln kann. Ein VPN funktioniert wie ein sicherer, privater Kurierdienst für Ihre Internetdaten. Anstatt dass Ihre Daten offen über das Internet übertragen werden, schafft ein VPN einen sicheren, verschlüsselten Tunnel zwischen Ihrem Gerät, Computer oder Smartphone, und einem VPN-Server. Dieser Server leitet Ihre Daten dann an ihr endgültiges Ziel im Internet weiter.

Core benefits of using a VPN. Confidentiality. VPNs encrypt your internet traffic. Encryption scrambles your data, making it unreadable to anyone who might intercept it, such as hackers on a public Wi-Fi network or even your internet service provider, ISP. Kernvorteile der Verwendung eines VPN. Vertraulichkeit. VPNs verschlüsseln Ihren Internetverkehr. Die Verschlüsselung verschlüsselt Ihre Daten und macht sie unlesbar für jeden, der sie abfangen könnte, wie zum Beispiel Hacker in einem öffentlichen WLAN-Netzwerk oder sogar Ihr Internetdienstanbieter, ISP.

Integrity. VPNs can help ensure that the data you send and receive is not tampered with during transmission. Integrität. VPNs können dazu beitragen, dass die von Ihnen gesendeten und empfangenen Daten während der Übertragung nicht verfälscht werden.

Authentication. VPNs ensure that you are connecting to the correct server and can also be used by the network to verify your identity before granting access. Authentifizierung. VPNs stellen sicher, dass Sie sich mit dem richtigen Server verbinden, und können auch vom Netzwerk verwendet werden, um Ihre Identität zu überprüfen, bevor der Zugang gewährt wird.

Anonymity to a certain extent and privacy. Since your traffic appears to come from a VPN server, your actual IP address is obscured. This can help prevent your online activities from being traced directly back to you, strengthening your privacy. Anonymität bis zu einem gewissen Grad und Datenschutz. Da Ihr Datenverkehr scheinbar von einem VPN-Server kommt, wird Ihre tatsächliche IP-Adresse verschleiert. Dies kann dazu beitragen, dass Ihre Online-Aktivitäten nicht direkt zu Ihnen zurückverfolgt werden können, was Ihre Privatsphäre stärkt.

Access. VPNs allow you to access resources on a private network as if you were there, for example, accessing your company's internal servers from home. They can also be used to bypass geographic restrictions on content, although this is often a secondary benefit compared to the security aspects we are focusing on. Zugang. Mit VPNs können Sie auf Ressourcen in einem privaten Netzwerk zugreifen, als ob Sie sich dort befänden, zum Beispiel von zu Hause aus auf die internen Server Ihres Unternehmens zugreifen. Sie können auch verwendet werden, um geografische Beschränkungen für Inhalte zu umgehen, obwohl dies oft ein sekundärer Vorteil gegenüber den Sicherheitsaspekten ist, auf die wir uns konzentrieren.

Think about it. Have you ever used a VPN? If so, what was the main reason for it? Denken Sie darüber nach. Haben Sie schon einmal ein VPN benutzt? Wenn ja, was war der Hauptgrund dafür?

Why would a company want its employees to use a VPN when working remotely? Warum sollte ein Unternehmen wollen, dass seine Mitarbeiter ein VPN verwenden, wenn sie aus der Ferne arbeiten?

How does a VPN work? Wie funktioniert ein VPN?

Understanding the intricate details of VPN technology can be complex, but the basic process is simple. Das Verständnis der komplizierten Details der VPN-Technologie kann komplex sein, aber der grundlegende Prozess ist einfach.

Initiation. You start the VPN client software on your device. This client contains the data of the VPN server you want to connect to. Initiierung. Sie starten die VPN-Client-Software auf Ihrem Gerät. Dieser Client enthält die Daten des VPN-Servers, mit dem Sie sich verbinden möchten.

Authentication. Your VPN client establishes a connection to the VPN server. This step typically verifies your identity, for example with a username and password or a digital certificate. The server also authenticates itself to your client. Authentifizierung. Ihr VPN-Client stellt eine Verbindung mit dem VPN-Server her. Bei diesem Schritt wird in der Regel Ihre Identität verifiziert, zum Beispiel mit einem Benutzernamen und einem Passwort oder einem digitalen Zertifikat. Der Server authentifiziert sich ebenfalls gegenüber Ihrem Client.

Tunnel establishment. Once authentication is successful, the VPN client and server establish an encrypted tunnel. All data transmitted between your device and the VPN server is now encrypted. Tunnelaufbau. Sobald die Authentifizierung erfolgreich war, bauen der VPN-Client und der Server einen verschlüsselten Tunnel auf. Alle Daten, die zwischen Ihrem Gerät und dem VPN-Server übertragen werden, sind nun verschlüsselt.

Data routing. When you access the internet, your traffic is first sent through this encrypted tunnel to the VPN server. Daten-Routing. Wenn Sie auf das Internet zugreifen, wird Ihr Datenverkehr zunächst durch diesen verschlüsselten Tunnel an den VPN-Server gesendet.

The VPN server decrypts your traffic. Der VPN-Server entschlüsselt Ihren Datenverkehr.

The VPN server then forwards your traffic to the desired destination on the internet, for example a website or an online service. Der VPN-Server leitet Ihren Datenverkehr dann an das gewünschte Ziel im Internet weiter, zum Beispiel eine Website oder einen Online-Dienst.

The responses from the destination are sent back to the VPN server. Die Antworten des Ziels werden an den VPN-Server zurückgesendet.

The VPN server encrypts these responses and sends them back through the secure tunnel to your device. Der VPN-Server verschlüsselt diese Antworten und sendet sie durch den sicheren Tunnel zurück an Ihr Gerät.

Your VPN client decrypts the data so you can see it. Ihr VPN-Client entschlüsselt die Daten, sodass Sie sie sehen können.

Essentially, the VPN server acts as a secure intermediary for your internet connection. Im Wesentlichen fungiert der VPN-Server als sicherer Vermittler für Ihre Internetverbindung.

Key concepts in VPNs. Several core technologies and concepts make VPNs possible. Schlüsselkonzepte in VPNs. Mehrere Kerntechnologien und Konzepte machen VPNs möglich.

Tunneling. Tunneling refers to the encapsulation of one network protocol within another. Imagine putting a smaller envelope, your original data packet, inside a larger, more secure envelope, the tunneling protocol. The outer protocol effectively hides the inner protocol and its data. Tunneling. Unter Tunneling versteht man die Kapselung eines Netzwerkprotokolls in einem anderen. Stellen Sie sich vor, Sie stecken einen kleineren Umschlag, Ihr ursprüngliches Datenpaket, in einen größeren, sichereren Umschlag, das Tunneling-Protokoll. Das äußere Protokoll verbirgt das innere Protokoll und seine Daten effektiv.

In the context of a VPN, your device's internet traffic, such as HTTP requests or email data, is encapsulated in the VPN protocol's packets. This encapsulated data is then sent through the tunnel to the VPN server. The VPN server unpacks the original data and sends it to its destination. Im Zusammenhang mit einem VPN wird der Internetverkehr Ihres Geräts, wie zum Beispiel HTTP-Anfragen oder E-Mail-Daten, in die Pakete des VPN-Protokolls eingekapselt. Diese eingekapselten Daten werden dann durch den Tunnel an den VPN-Server gesendet. Der VPN-Server entpackt die ursprünglichen Daten und sendet sie an ihr Ziel.

Encryption. Encryption converts data into an encoded format that can only be decrypted with a specific key. This ensures the privacy in a virtual private network. If an unauthorized party intercepts your VPN traffic, they only see encrypted, incomprehensible data unless they have the decryption key, which they should not have. Verschlüsselung. Bei der Verschlüsselung werden die Daten in ein kodiertes Format umgewandelt, das nur mit einem bestimmten Schlüssel entschlüsselt werden kann. Dadurch wird die Privatsphäre in einem virtuellen privaten Netzwerk gewährleistet. Wenn eine unbefugte Partei Ihren VPN-Verkehr abfängt, sieht sie nur verschlüsselte, unverständliche Daten, es sei denn, sie hat den Entschlüsselungsschlüssel, was sie nicht haben sollte.

VPNs use various encryption algorithms and protocols to secure the data tunnel. The strength of the encryption is a crucial factor in how secure a VPN is. VPNs verwenden verschiedene Verschlüsselungsalgorithmen und Protokolle, um den Datentunnel zu sichern. Die Stärke der Verschlüsselung ist ein entscheidender Faktor dafür, wie sicher ein VPN ist.

Authentication. Authentication refers to verifying the identity of a user, a device, or a server. In VPNs, authentication occurs in various ways. Authentifizierung. Unter Authentifizierung versteht man die Überprüfung der Identität eines Benutzers, eines Geräts oder eines Servers. In VPNs erfolgt die Authentifizierung auf verschiedene Weise.

User authentication. You prove your identity to the VPN server, for example username and password, certificate, multi-factor authentication. Benutzerauthentifizierung. Sie weisen Ihre Identität gegenüber dem VPN-Server nach, zum Beispiel Benutzername und Passwort, Zertifikat, Multi-Faktor-Authentifizierung.

Server authentication. Your VPN client verifies that it is connecting to a legitimate VPN server and not an impostor. Server-Authentifizierung. Ihr VPN-Client verifiziert, dass er sich mit einem legitimen VPN-Server verbindet und nicht mit einem Betrüger.

Strong authentication is crucial to prevent unauthorized access to the VPN and the network it protects. Eine starke Authentifizierung ist entscheidend, um den unbefugten Zugriff auf das VPN und das damit geschützte Netzwerk zu verhindern.

VPN protocols. There are several protocols used to establish and secure VPN tunnels. You do not need to know these in detail, but it is good to be aware of their existence as you might encounter these terms. VPN-Protokolle. Es gibt mehrere Protokolle, die zum Aufbau und zur Sicherung von VPN-Tunneln verwendet werden. Sie müssen diese nicht im Detail kennen, aber es ist gut, sich ihrer Existenz bewusst zu sein, da Sie auf diese Begriffe stoßen könnten.

IPsec, Internet Protocol Security. A versatile and robust set of protocols that can be used for both remote access and site-to-site VPNs. It operates at the network layer. IPsec, Internet Protocol Security. Eine vielseitige und robuste Reihe von Protokollen, die sowohl für den Fernzugriff als auch für Standort-VPNs verwendet werden können. Es arbeitet auf der Netzwerkebene.

SSL and TLS, Secure Sockets Layer and Transport Layer Security. These protocols are widely known for securing web traffic, HTTPS. Many modern remote access VPNs, often referred to as SSL VPNs, use TLS to create secure tunnels, usually via a web browser or dedicated client application. SSL und TLS, Secure Sockets Layer und Transport Layer Security. Diese Protokolle sind weithin für die Absicherung des Webverkehrs, HTTPS, bekannt. Viele moderne Fernzugriffs-VPNs, oft als SSL-VPNs bezeichnet, nutzen TLS, um sichere Tunnel zu erstellen, normalerweise über einen Webbrowser oder eine spezielle Client-Anwendung.

OpenVPN. A popular open source VPN application and protocol that uses TLS for security. It is known for its flexibility and high security. OpenVPN. Eine beliebte Open-Source-VPN-Anwendung und ein Protokoll, das TLS für die Sicherheit verwendet. Es ist bekannt für seine Flexibilität und hohe Sicherheit.

WireGuard. A newer, modern VPN protocol known for its simplicity, high speed, and high security. WireGuard. Ein neueres, modernes VPN-Protokoll, das für seine Einfachheit, hohe Geschwindigkeit und hohe Sicherheit bekannt ist.

PPTP, Point-to-Point Tunneling Protocol. An older protocol with known security vulnerabilities. Generally no longer recommended for use. PPTP, Point-to-Point Tunneling Protocol. Ein älteres Protokoll mit bekannten Sicherheitslücken. Wird im Allgemeinen nicht mehr zur Verwendung empfohlen.

L2TP, Layer 2 Tunneling Protocol. This protocol does not provide encryption itself but is often coupled with IPsec, L2TP and IPsec, to provide both tunneling and security. L2TP, Layer 2 Tunneling Protocol. Dieses Protokoll bietet selbst keine Verschlüsselung, wird aber oft mit IPsec, L2TP und IPsec, gekoppelt, um sowohl Tunneling als auch Sicherheit zu bieten.

Try it yourself. Visit the website of a commercial VPN provider, for example ProtonVPN, Mullvad, NordVPN, for research purposes only. You do not need to sign up or install anything. Look for information about which VPN protocols they support or use by default. Do they explain why they choose certain protocols? Versuchen Sie es selbst. Besuchen Sie die Website eines kommerziellen VPN-Anbieters, zum Beispiel ProtonVPN, Mullvad, NordVPN, nur zu Recherchezwecken. Sie müssen sich nicht anmelden oder etwas installieren. Suchen Sie nach Informationen darüber, welche VPN-Protokolle sie unterstützen oder standardmäßig verwenden. Erklären sie, warum sie bestimmte Protokolle wählen?

Types of VPNs. VPNs can be categorized into different types depending on the use case. Arten von VPNs. VPNs können je nach Anwendungsfall in verschiedene Kategorien eingeteilt werden.

Remote access VPN, client-to-site. This is the most common type for individual users and employees. It allows a user's device to establish a secure connection to a remote network, typically a company's internal network or a third-party VPN service. Remote-Access-VPN, Client-to-Site. Dies ist der häufigste Typ für Einzelanwender und Mitarbeiter. Er ermöglicht es dem Gerät eines Benutzers, eine sichere Verbindung zu einem entfernten Netzwerk herzustellen, in der Regel dem internen Netzwerk eines Unternehmens oder einem VPN-Dienst eines Drittanbieters.

Example. An employee working from home uses a VPN client to connect to their company's network and securely access internal files and applications. Beispiel. Ein Angestellter, der von zu Hause aus arbeitet, verwendet einen VPN-Client, um sich mit dem Netzwerk seines Unternehmens zu verbinden und sicher auf interne Dateien und Anwendungen zuzugreifen.

Example. A traveler uses a VPN service on their laptop in a public Wi-Fi hotspot to encrypt their browsing activities and protect their data. Beispiel. Ein Reisender nutzt einen VPN-Dienst auf seinem Laptop in einem öffentlichen WLAN-Hotspot, um seine Surfaktivitäten zu verschlüsseln und seine Daten zu schützen.

Site-to-site VPN. This type of VPN connects two or more separate networks, creating a secure, virtual wide area network, WAN, over the internet. Site-to-Site-VPN. Diese Art von VPN verbindet zwei oder mehr getrennte Netzwerke und schafft so ein sicheres, virtuelles Wide-Area-Network, WAN, über das Internet.

Example. A company with multiple branches uses site-to-site VPNs to securely connect each branch's network to the headquarters network. This enables seamless and secure communication and data exchange between the branches as if they were on the same local network. Beispiel. Ein Unternehmen mit mehreren Zweigstellen verwendet Site-to-Site-VPNs, um das Netzwerk jeder Zweigstelle sicher mit dem Netzwerk des Hauptsitzes zu verbinden. Dies ermöglicht eine nahtlose und sichere Kommunikation und einen Datenaustausch zwischen den Niederlassungen, als ob sie sich im selben lokalen Netzwerk befänden.

Tunneling as a broader concept. While VPNs are one of the main applications of tunneling, the concept itself is used in various other networking scenarios. Remember that tunneling essentially involves encapsulating one protocol or data payload within another. Tunneling als umfassenderes Konzept. VPNs sind zwar eine der Hauptanwendungen von Tunneling, aber das Konzept selbst wird auch in verschiedenen anderen Netzwerkszenarien verwendet. Denken Sie daran, dass es beim Tunneling im Wesentlichen darum geht, ein Protokoll oder eine Datenlast in ein anderes zu kapseln.

Why encapsulate? Security. As with VPNs, to encrypt traffic over an untrusted network. Warum einkapseln? Sicherheit. Wie bei VPNs, um den Datenverkehr über ein nicht vertrauenswürdiges Netzwerk zu verschlüsseln.

Interoperability. To transmit a protocol over a network that does not natively support it, for example transmitting IPv6 traffic over an IPv4 network. Interoperabilität. Um ein Protokoll über ein Netzwerk zu übertragen, das es von Haus aus nicht unterstützt, zum Beispiel Übertragung von IPv6-Datenverkehr über ein IPv4-Netzwerk.

Network policy and routing. To route traffic in specific directions or bypass certain network restrictions. Netzpolitik und Routing. Um den Datenverkehr in bestimmte Richtungen zu leiten oder bestimmte Netzwerkbeschränkungen zu umgehen.

Other examples of tunneling beyond VPNs. GRE, Generic Routing Encapsulation. A simple tunneling protocol developed by Cisco that can encapsulate a variety of network layer protocols into virtual point-to-point connections over an IP network. It does not include encryption by default but can be coupled with IPsec. Andere Beispiele für Tunneling über VPNs hinaus. GRE, Generic Routing Encapsulation. Ein einfaches, von Cisco entwickeltes Tunneling-Protokoll, das eine Vielzahl von Protokollen der Netzwerkebene in virtuelle Punkt-zu-Punkt-Verbindungen über ein IP-Netzwerk einkapseln kann. Es enthält standardmäßig keine Verschlüsselung, kann aber mit IPsec gekoppelt werden.

SSH tunneling, port forwarding. The Secure Shell, SSH, protocol, commonly used for secure remote login and command execution, can also create secure tunnels. This allows network ports to be forwarded, enabling you to securely access services on a remote computer or network as if they were local. For example, you can securely access a database running on a remote server by tunneling the appropriate port to your local machine. SSH-Tunneling, Portweiterleitung. Das Secure-Shell, SSH, Protokoll, das üblicherweise für die sichere Fernanmeldung und Befehlsausführung verwendet wird, kann ebenfalls sichere Tunnel erstellen. Damit können Netzwerk-Ports weitergeleitet werden, sodass Sie sicher auf Dienste auf einem entfernten Computer oder Netzwerk zugreifen können, als ob sie lokal wären. So können Sie zum Beispiel sicher auf eine Datenbank zugreifen, die auf einem entfernten Server läuft, indem Sie den entsprechenden Port auf Ihren lokalen Rechner tunneln.

IPv6 in IPv4 tunnels. As the internet transitions from IPv4 to IPv6, tunneling mechanisms, such as 6to4, Teredo, ISATAP, are used to transmit IPv6 packets over parts of the internet that only support IPv4. IPv6 in IPv4-Tunneln. Da das Internet von IPv4 auf IPv6 umgestellt wird, werden Tunnelmechanismen, wie 6to4, Teredo, ISATAP, verwendet, um IPv6-Pakete über Teile des Internets zu übertragen, die nur IPv4 unterstützen.

Think about it. Let us take the SSH tunneling example. If you have an application on a remote server that, for security reasons, only accepts connections from localhost, the server itself, how could you use SSH tunneling to securely access this application from your own computer? Denken Sie darüber nach. Nehmen wir das Beispiel SSH-Tunneling. Wenn Sie eine Anwendung auf einem entfernten Server haben, die aus Sicherheitsgründen nur Verbindungen von localhost, dem Server selbst, akzeptiert, wie könnten Sie dann mit SSH-Tunneling von Ihrem eigenen Computer aus sicher auf diese Anwendung zugreifen?

This preparatory material has familiarized you with the basic ideas of VPNs and the broader concept of network tunneling, preparing you for the upcoming lesson. Dieses vorbereitende Material hat Sie mit den Grundgedanken von VPNs und dem breiteren Konzept des Netzwerk-Tunnelings vertraut gemacht und Sie auf die kommende Lektion vorbereitet.

The slides for the live session can be viewed here. Try not to peek before class, spoilers inside. Die Folien für die Live-Sitzung können hier angesehen werden. Versuchen Sie nicht, vor dem Unterricht zu spähen, Spoiler innen.