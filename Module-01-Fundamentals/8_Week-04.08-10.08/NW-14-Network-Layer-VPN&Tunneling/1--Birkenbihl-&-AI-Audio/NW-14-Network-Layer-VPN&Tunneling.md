Herzlich willkommen! Dieses Vorbereitungsmaterial ist Ihr Ausgangspunkt für unsere bevorstehende Sitzung über virtuelle private Netzwerke (VPNs) und Tunneling. Wir werden die wichtigsten Konzepte gemeinsam erforschen, damit Sie gut auf die Lektion vorbereitet sind. Während Sie die Erklärungen durchgehen, finden Sie die Abschnitte "Versuchen Sie es selbst" und "Denken Sie darüber nach", um Ihr Verständnis zu vertiefen.

## Was ist ein virtuelles privates Netzwerk (VPN)?

Stellen Sie sich vor, Sie verschicken ein wertvolles Paket über das öffentliche Postsystem. Sie würden nicht wollen, dass irgendjemand den Inhalt sehen oder daran herumfummeln kann. Ein VPN funktioniert wie ein sicherer, privater Kurierdienst für Ihre Internetdaten. Anstatt dass Ihre Daten offen über das Internet übertragen werden, schafft ein VPN einen sicheren, verschlüsselten "Tunnel" zwischen Ihrem Gerät (Computer, Smartphone) und einem VPN-Server. Dieser Server leitet Ihre Daten dann an ihr endgültiges Ziel im Internet weiter.

![[Pasted image 20250930051354.png]]

**Kernvorteile der Verwendung eines VPN:**

- **Vertraulichkeit:** VPNs verschlüsseln Ihren Internetverkehr. Die Verschlüsselung verschlüsselt Ihre Daten und macht sie unlesbar für jeden, der sie abfangen könnte, wie z. B. Hacker in einem öffentlichen Wi-Fi-Netzwerk oder sogar Ihr Internetdienstanbieter (ISP).
- **Integrität:** VPNs können dazu beitragen, dass die von Ihnen gesendeten und empfangenen Daten während der Übertragung nicht verfälscht werden.
- **Authentifizierung:** VPNs stellen sicher, dass Sie sich mit dem richtigen Server verbinden, und können auch vom Netzwerk verwendet werden, um Ihre Identität zu überprüfen, bevor der Zugang gewährt wird.
- **Anonymität (bis zu einem gewissen Grad) & Datenschutz:** Da Ihr Datenverkehr scheinbar von einem VPN-Server kommt, wird Ihre tatsächliche IP-Adresse verschleiert. Dies kann dazu beitragen, dass Ihre Online-Aktivitäten nicht direkt zu Ihnen zurückverfolgt werden können, was Ihre Privatsphäre stärkt.
- **Zugang:** Mit VPNs können Sie auf Ressourcen in einem privaten Netzwerk zugreifen, als ob Sie sich dort befänden (z. B. von zu Hause aus auf die internen Server Ihres Unternehmens zugreifen). Sie können auch verwendet werden, um geografische Beschränkungen für Inhalte zu umgehen (obwohl dies oft ein sekundärer Vorteil gegenüber den Sicherheitsaspekten ist, auf die wir uns konzentrieren).

### Denken Sie darüber nach

- Haben Sie schon einmal ein VPN benutzt? Wenn ja, was war der Hauptgrund dafür?
- Warum sollte ein Unternehmen wollen, dass seine Mitarbeiter ein VPN verwenden, wenn sie aus der Ferne arbeiten?

## How Does a VPN Work?

![[Pasted image 20250930051416.png]]

Das Verständnis der komplizierten Details der VPN-Technologie kann komplex sein, aber der grundlegende Prozess ist einfach:

1. **Initiation:** Sie starten die VPN-Client-Software auf Ihrem Gerät. Dieser Client enthält die Daten des VPN-Servers, mit dem Sie sich verbinden möchten.
2. **Authentifizierung:** Ihr VPN-Client stellt eine Verbindung mit dem VPN-Server her. Bei diesem Schritt wird in der Regel Ihre Identität verifiziert (z. B. mit einem Benutzernamen und einem Passwort oder einem digitalen Zertifikat). Der Server authentifiziert sich ebenfalls gegenüber Ihrem Client.
3. **Tunnelaufbau:** Sobald die Authentifizierung erfolgreich war, bauen der VPN-Client und der Server einen verschlüsselten Tunnel auf. Alle Daten, die zwischen Ihrem Gerät und dem VPN-Server übertragen werden, sind nun verschlüsselt.
4. **Daten-Routing:**
    - Wenn Sie auf das Internet zugreifen, wird Ihr Datenverkehr zunächst durch diesen verschlüsselten Tunnel an den VPN-Server gesendet.
    - Der VPN-Server entschlüsselt Ihren Datenverkehr.
    - Der VPN-Server leitet Ihren Datenverkehr dann an das gewünschte Ziel im Internet weiter (z. B. eine Website, einen Online-Dienst).
    - Die Antworten des Ziels werden an den VPN-Server zurückgesendet.
    - Der VPN-Server verschlüsselt diese Antworten und sendet sie durch den sicheren Tunnel zurück an Ihr Gerät.
    - Ihr VPN-Client entschlüsselt die Daten, so dass Sie sie sehen können.

Im Wesentlichen fungiert der VPN-Server als sicherer Vermittler für Ihre Internetverbindung.

## Schlüsselkonzepte in VPNs

Mehrere Kerntechnologien und -konzepte machen VPNs möglich:

### Tunneling

Unter Tunneling versteht man die Kapselung eines Netzwerkprotokolls in einem anderen. Stellen Sie sich vor, Sie stecken einen kleineren Umschlag (Ihr ursprüngliches Datenpaket) in einen größeren, sichereren Umschlag (das Tunneling-Protokoll). Das äußere Protokoll verbirgt das innere Protokoll und seine Daten effektiv.

Im Zusammenhang mit einem VPN wird der Internetverkehr Ihres Geräts (z. B. HTTP-Anfragen, E-Mail-Daten) in die Pakete des VPN-Protokolls eingekapselt. Diese eingekapselten Daten werden dann durch den "Tunnel" an den VPN-Server gesendet. Der VPN-Server "entpackt" die ursprünglichen Daten und sendet sie an ihr Ziel.

### Verschlüsselung

Bei der Verschlüsselung werden die Daten in ein kodiertes Format umgewandelt, das nur mit einem bestimmten Schlüssel entschlüsselt werden kann. Dadurch wird die "Privatsphäre" in einem virtuellen privaten Netzwerk gewährleistet. Wenn eine unbefugte Partei Ihren VPN-Verkehr abfängt, sieht sie nur verschlüsselte, unverständliche Daten, es sei denn, sie hat den Entschlüsselungsschlüssel (was sie nicht sollte!).

VPNs verwenden verschiedene Verschlüsselungsalgorithmen und -protokolle, um den Datentunnel zu sichern. Die Stärke der Verschlüsselung ist ein entscheidender Faktor dafür, wie sicher ein VPN ist.

### Authentifizierung

Unter Authentifizierung versteht man die Überprüfung der Identität eines Benutzers, eines Geräts oder eines Servers. In VPNs erfolgt die Authentifizierung auf verschiedene Weise:

- **Benutzerauthentifizierung:** Sie weisen Ihre Identität gegenüber dem VPN-Server nach (z. B. Benutzername/Passwort, Zertifikat, Multi-Faktor-Authentifizierung).
- **Server-Authentifizierung:** Ihr VPN-Client verifiziert, dass er sich mit einem legitimen VPN-Server verbindet und nicht mit einem Betrüger.

Eine starke Authentifizierung ist entscheidend, um den unbefugten Zugriff auf das VPN und das damit geschützte Netzwerk zu verhindern.

## VPN Protocols

Es gibt mehrere Protokolle, die zum Aufbau und zur Sicherung von VPN-Tunneln verwendet werden. Sie müssen diese nicht im Detail kennen, aber es ist gut, sich ihrer Existenz bewusst zu sein, da Sie auf diese Begriffe stoßen könnten:

- **IPsec (Internet Protocol Security):** Eine vielseitige und robuste Reihe von Protokollen, die sowohl für den Fernzugriff als auch für Standort-VPNs verwendet werden können. Es arbeitet auf der Netzwerkebene.
- **SSL/TLS (Secure Sockets Layer/Transport Layer Security):** Diese Protokolle sind weithin für die Absicherung des Webverkehrs (HTTPS) bekannt. Viele moderne Fernzugriffs-VPNs (oft als SSL-VPNs bezeichnet) nutzen TLS, um sichere Tunnel zu erstellen, normalerweise über einen Webbrowser oder eine spezielle Client-Anwendung.
- **OpenVPN:** Eine beliebte Open-Source-VPN-Anwendung und ein Protokoll, das TLS für die Sicherheit verwendet. Es ist bekannt für seine Flexibilität und hohe Sicherheit.
- **WireGuard:** Ein neueres, modernes VPN-Protokoll, das für seine Einfachheit, hohe Geschwindigkeit und hohe Sicherheit bekannt ist.
- **PPTP (Point-to-Point Tunneling Protocol):** Ein älteres Protokoll mit bekannten Sicherheitslücken. Wird im Allgemeinen nicht mehr zur Verwendung empfohlen.
- L2TP (Layer 2 Tunneling Protocol):** Dieses Protokoll bietet selbst keine Verschlüsselung, wird aber oft mit IPsec (L2TP/IPsec) gekoppelt, um sowohl Tunneling als auch Sicherheit zu bieten.

### Versuchen Sie es selbst

- Besuchen Sie die Website eines kommerziellen VPN-Anbieters (z.B. ProtonVPN, Mullvad, NordVPN - nur zu Recherchezwecken, Sie müssen sich nicht anmelden oder etwas installieren). Suchen Sie nach Informationen darüber, welche VPN-Protokolle sie unterstützen oder standardmäßig verwenden. Erklären sie, warum sie bestimmte Protokolle wählen?

## Arten von VPNs

VPNs können je nach Anwendungsfall in verschiedene Kategorien eingeteilt werden:

### Remote Access VPN (Client-to-Site)

Dies ist der häufigste Typ für Einzelanwender und Mitarbeiter. Er ermöglicht es dem Gerät eines Benutzers, eine sichere Verbindung zu einem entfernten Netzwerk herzustellen, in der Regel dem internen Netzwerk eines Unternehmens oder einem VPN-Dienst eines Drittanbieters.

- **Beispiel:** Ein Angestellter, der von zu Hause aus arbeitet, verwendet einen VPN-Client, um sich mit dem Netzwerk seines Unternehmens zu verbinden und sicher auf interne Dateien und Anwendungen zuzugreifen.
- **Beispiel:** Ein Reisender nutzt einen VPN-Dienst auf seinem Laptop in einem öffentlichen Wi-Fi-Hotspot, um seine Surfaktivitäten zu verschlüsseln und seine Daten zu schützen.

### Site-to-Site VPN

![[Pasted image 20250930051520.png]]

Diese Art von VPN verbindet zwei oder mehr getrennte Netzwerke und schafft so ein sicheres, virtuelles Wide Area Network (WAN) über das Internet.

- **Beispiel:** Ein Unternehmen mit mehreren Zweigstellen verwendet Site-to-Site-VPNs, um das Netzwerk jeder Zweigstelle sicher mit dem Netzwerk des Hauptsitzes zu verbinden. Dies ermöglicht eine nahtlose und sichere Kommunikation und einen Datenaustausch zwischen den Niederlassungen, als ob sie sich im selben lokalen Netz befänden.


## Tunneling als umfassenderes Konzept

![[Pasted image 20250930051542.png]]

VPNs sind zwar eine der Hauptanwendungen von Tunneling, aber das Konzept selbst wird auch in verschiedenen anderen Netzwerkszenarien verwendet. Denken Sie daran, dass es beim Tunneln im Wesentlichen darum geht, ein Protokoll oder eine Datenlast in ein anderes zu kapseln.

**Warum einkapseln?**

- **Sicherheit:** Wie bei VPNs, um den Datenverkehr über ein nicht vertrauenswürdiges Netzwerk zu verschlüsseln.
- **Interoperabilität:** Um ein Protokoll über ein Netzwerk zu übertragen, das es von Haus aus nicht unterstützt (z. B. Übertragung von IPv6-Datenverkehr über ein IPv4-Netzwerk).
- **Netzpolitik/Routing:** Um den Datenverkehr in bestimmte Richtungen zu leiten oder bestimmte Netzbeschränkungen zu umgehen.

**Andere Beispiele für Tunneling (über VPNs hinaus):**

- **GRE (Generic Routing Encapsulation):** Ein einfaches, von Cisco entwickeltes Tunneling-Protokoll, das eine Vielzahl von Protokollen der Netzwerkebene in virtuelle Punkt-zu-Punkt-Verbindungen über ein IP-Netzwerk einkapseln kann. Es enthält standardmäßig keine Verschlüsselung, kann aber mit IPsec gekoppelt werden.
- **SSH-Tunneling (Portweiterleitung):** Das Secure Shell (SSH)-Protokoll, das üblicherweise für die sichere Fernanmeldung und Befehlsausführung verwendet wird, kann ebenfalls sichere Tunnel erstellen. Damit können Netzwerk-Ports weitergeleitet werden, so dass Sie sicher auf Dienste auf einem entfernten Computer oder Netzwerk zugreifen können, als ob sie lokal wären. So können Sie zum Beispiel sicher auf eine Datenbank zugreifen, die auf einem entfernten Server läuft, indem Sie den entsprechenden Port auf Ihren lokalen Rechner tunneln.
- **IPv6 in IPv4-Tunneln:** Da das Internet von IPv4 auf IPv6 umgestellt wird, werden Tunnelmechanismen (wie 6to4, Teredo, ISATAP) verwendet, um IPv6-Pakete über Teile des Internets zu übertragen, die nur IPv4 unterstützen.

### Denken Sie darüber nach

- Nehmen wir das Beispiel SSH-Tunneling. Wenn Sie eine Anwendung auf einem entfernten Server haben, die aus Sicherheitsgründen nur auf Verbindungen von "localhost" (dem Server selbst) wartet, wie könnten Sie dann mit SSH-Tunneling von Ihrem eigenen Computer aus sicher auf diese Anwendung zugreifen?

Dieses vorbereitende Material hat Sie mit den Grundgedanken von VPNs und dem breiteren Konzept des Netzwerk-Tunnelings vertraut gemacht und Sie auf die kommende Lektion vorbereitet.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Networking-14-VPN-Tunneling-ur3ldjzd2wjn2vj?mode=doc](https://gamma.app/docs/Networking-14-VPN-Tunneling-ur3ldjzd2wjn2vj?mode=doc)

Try not to peek before class - spoilers inside!

</aside>