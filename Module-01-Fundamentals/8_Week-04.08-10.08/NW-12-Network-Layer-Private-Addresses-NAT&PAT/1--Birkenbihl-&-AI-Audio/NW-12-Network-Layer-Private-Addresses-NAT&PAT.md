Willkommen zu Ihrer Vorbereitung auf unsere kommende Sitzung über private IP-Adressen, Network Address Translation (NAT) und Port Address Translation (PAT). Das Verständnis dieser Konzepte ist wichtig, um zu verstehen, wie die meisten Netzwerke - von Ihrem Heimnetzwerk bis hin zu großen Unternehmensumgebungen - mit dem Internet verbunden sind und ihre interne Adressierung verwalten.

## Eine kurze Zusammenfassung: IP-Adressen

Aus den vorangegangenen Lektionen wissen Sie, dass eine IP-Adresse (Internet-Protokoll-Adresse) eine eindeutige numerische Kennzeichnung ist, die jedem Gerät zugewiesen wird, das an ein Computernetzwerk angeschlossen ist, das das Internet-Protokoll für die Kommunikation verwendet. Stellen Sie sich dies wie eine Postadresse für Ihren Computer im Internet vor. Diese Adressen ermöglichen es den Geräten, einander zu finden und Informationen auszutauschen. Wir haben uns hauptsächlich mit IPv4-Adressen befasst, bei denen es sich um 32-Bit-Zahlen handelt, die in der Regel in einem "Punkt-Dezimal"-Format ausgedrückt werden (z. B. "192.168.1.1").

Eine wichtige Erkenntnis ist, dass die IP-Adresse eines Geräts weltweit eindeutig sein muss, damit es im _öffentlichen Internet_ direkt erreichbar ist. Keine zwei Geräte im öffentlichen Internet können gleichzeitig die gleiche öffentliche IP-Adresse haben.

## Die Herausforderung: Die Zahlen gehen zur Neige

Das IPv4-Adressierungssystem mit seinen 32-Bit-Adressen bietet etwa 232 (etwa 4,3 Milliarden) eindeutige Adressen. Während dies in den Anfängen des Internets wie eine riesige Zahl erschien, hat das explosive Wachstum der mit dem Internet verbundenen Geräte (Computer, Smartphones, Server, IoT-Geräte usw.) zu einer Situation geführt, die als **IPv4-Adressenerschöpfung** bekannt ist. Einfach ausgedrückt: Wir haben keine frei verfügbaren, eindeutigen öffentlichen IPv4-Adressen mehr, die wir jedem neuen Gerät zuweisen könnten.

IPv6 mit seinem viel größeren 128-Bit-Adressraum ist zwar die langfristige Lösung, aber der Übergang erfolgt schrittweise. In der Zwischenzeit waren clevere Techniken erforderlich, um die vorhandenen IPv4-Adressen optimal zu nutzen. An dieser Stelle kommen private IP-Adressen und NAT ins Spiel.

## Private IP-Adressen: Der interne Raum Ihres Netzwerks

Um den Bedarf an eindeutigen öffentlichen IPv4-Adressen zu verringern und Unternehmen die Möglichkeit zu geben, interne Netze aufzubauen, ohne für jedes Gerät weltweit eindeutige IPs zu benötigen, wurde das Konzept der **privaten IP-Adressen** eingeführt.

Bestimmte Bereiche von IPv4-Adressen wurden für die Verwendung in privaten Netzen reserviert. Diese Adressen sind im öffentlichen Internet nicht routbar. Das bedeutet, dass Internet-Router so konfiguriert sind, dass sie jeglichen Datenverkehr, der von diesen privaten IP-Adressen ausgeht oder an sie gerichtet ist, direkt verwerfen.

Die Internet Engineering Task Force (IETF) hat diese Bereiche in RFC 1918 festgelegt:

- **10.0.0.0 bis 10.255.255.255** (Dies ist ein /8-Block, d. h. die ersten 8 Bits sind für den Netzwerkteil festgelegt. Er kann auch als "10.0.0.0/8" geschrieben werden). Dieser Bereich bietet über 16 Millionen Adressen.
- **172.16.0.0 bis 172.31.255.255** (A /12-Block, oder `172.16.0.0/12`). Dieser Bereich bietet über 1 Million Adressen.
- **192.168.0.0 bis 192.168.255.255** (A /16-Block oder "192.168.0.0/16"). Dieser Bereich bietet über 65.000 Adressen.

![[Pasted image 20250929210544.png]]

**Schlüsselmerkmale von privaten IP-Adressen:**

- **Nicht weltweit eindeutig:** Dieselbe private IP-Adresse (z. B. "192.168.1.100") kann von zahllosen Geräten in verschiedenen privaten Netzen auf der ganzen Welt gleichzeitig verwendet werden. Ihr Laptop könnte diese IP-Adresse in Ihrem Heimnetzwerk haben, und der Drucker eines anderen Nutzers könnte genau dieselbe IP-Adresse in dessen Büronetzwerk haben. Das ist in Ordnung, da diese Netze in Bezug auf diese privaten IPs voneinander isoliert sind.
- **Nicht im öffentlichen Internet routingfähig:** Router im Internet-Backbone leiten keine Pakete weiter, die eine private IP-Adresse als Quelle oder Ziel haben.
- **Freie Nutzung:** Jeder kann diese Adressbereiche innerhalb seines privaten Netzes nutzen, ohne eine Genehmigung oder Registrierung von einer Internetbehörde zu benötigen.
- **Erhöhte Sicherheit (indirekt):** Da Geräte mit privaten IPs nicht direkt aus dem Internet erreichbar sind, wird eine zusätzliche Schutzebene geschaffen. Ein externer Angreifer kann ein Gerät, das seine private IP-Adresse verwendet, nicht direkt von außerhalb des lokalen Netzes angreifen.

Private IP-Adressen werden in Ihrem Wi-Fi-Heimnetzwerk, in LANs (Local Area Networks) von Unternehmen und in vielen anderen Szenarien verwendet, in denen Geräte lokal kommunizieren müssen, aber nicht alle eine eindeutige öffentliche IP-Adresse benötigen

### Versuchen Sie es selbst

1. **Prüfen Sie Ihre IP-Adresse:**
    - Gehen Sie auf Ihrem Mac zu **Systemeinstellungen**.
    - Klicken Sie in der Seitenleiste auf **Netzwerk**.
    - Wählen Sie Ihre aktive Netzwerkverbindung aus (z. B. Wi-Fi oder Ethernet).
    - Klicken Sie auf die Schaltfläche **Details...**.
    - Suchen Sie nach der aufgelisteten **IP-Adresse**.
    - Fällt diese IP-Adresse in einen der oben erwähnten privaten RFC 1918-Bereiche? Bei den meisten Heim- und Büronetzwerken ist dies der Fall.
2. **Identifizieren Sie die LAN-IP Ihres Routers:**
    - Suchen Sie in den gleichen Netzwerkdetails auf Ihrem Mac nach der Adresse **Router**. Dies ist die private IP-Adresse Ihres Routers in Ihrem lokalen Netzwerk. Er fungiert als Gateway für Ihre Geräte, um andere Netzwerke, einschließlich des Internets, zu erreichen. Diese Adresse liegt normalerweise auch in einem privaten IP-Bereich (oft so etwas wie "192.168.1.1" oder "10.0.0.1").

## Das Gateway: Netzwerk-Adressübersetzung (NAT)


![[Pasted image 20250929210555.png]]

Wenn also Geräte in Ihrem lokalen Netzwerk über private IP-Adressen verfügen, die nicht für das Internet zugelassen sind, wie können sie dann auf Websites zugreifen, E-Mails senden oder Videos streamen? An dieser Stelle kommt **Network Address Translation (NAT)** ins Spiel.

NAT ist ein Prozess, der in der Regel von Ihrem Router (oder einer speziellen Firewall) durchgeführt wird und der es mehreren Geräten in einem privaten Netzwerk ermöglicht, eine einzige öffentliche IP-Adresse zu nutzen, um eine Verbindung mit dem Internet herzustellen. Der Router befindet sich an der Grenze zwischen Ihrem privaten Netz und dem öffentlichen Internet. Er verfügt über mindestens zwei IP-Adressen:

- Eine **private IP-Adresse** im lokalen Netz (z. B. "192.168.1.1"), die als Standard-Gateway für Ihre Geräte dient.
- Eine **öffentliche IP-Adresse**, die von Ihrem Internet Service Provider (ISP) zugewiesen wird, die weltweit eindeutig ist und über das Internet geroutet werden kann.

**Wie NAT funktioniert (eine vereinfachte Darstellung):**

1. **Ausgehender Verkehr (Ihr Computer zum Internet):**
    - Ihr Computer (z.B. mit der privaten IP `192.168.1.100`) möchte eine Anfrage an einen Webserver im Internet (z.B. `www.google.com` mit der öffentlichen IP `142.250.180.196`) senden.
    - Das Paket verlässt Ihren Computer mit:
        - Quell-IP: `192.168.1.100` (privat)
        - Ziel-IP: `142.250.180.196` (öffentlich)
    - Das Paket erreicht Ihren Router. Der Router führt NAT durch:
        - Er ändert die **Quell-IP-Adresse** von der privaten IP Ihres Computers (192.168.1.100) in die **öffentliche IP-Adresse** des Routers (z. B. 80.100.20.30).
        - Er speichert diese Umwandlung (private IP + ursprünglicher Quellport ↔ öffentliche IP + neuer Quellport) in einer speziellen Tabelle, der **NAT-Tabelle**.
        - Das geänderte Paket, jetzt mit einer öffentlichen Quell-IP, wird ins Internet gesendet.
2. **Eingehender Verkehr (Internet zurück zu Ihrem Computer):**
    - Der Webserver (142.250.180.196) sendet eine Antwort. Diese Antwort ist an die öffentliche IP-Adresse Ihres Routers (80.100.20.30) adressiert, da dies die Quell-IP-Adresse war, die der Server sah.
    - Das Paket kommt bei Ihrem Router an mit:
        - Quell-IP: `142.250.180.196` (öffentlich)
        - Ziel-IP: `80.100.20.30` (die öffentliche IP Ihres Routers)
    - Der Router konsultiert seine NAT-Tabelle. Er sucht den Eintrag, der mit dem eingehenden Paket verbunden ist (basierend auf den Portnummern, die wir als nächstes besprechen werden).
    - Er findet die ursprüngliche private IP-Adresse (192.168.1.100), von der diese Kommunikation ausging.
    - Er ändert die **Ziel-IP-Adresse** des Pakets von seiner eigenen öffentlichen IP (80.100.20.30) zurück zur privaten IP Ihres Computers (192.168.1.100).
    - Das Paket wird dann an Ihren Computer im lokalen Netz weitergeleitet.

Ihr Router fungiert also als Proxy, der den gesamten von Ihrem privaten Netz ausgehenden Datenverkehr so aussehen lässt, als stamme er von seiner einzigen öffentlichen IP-Adresse.
## Handling Multiple Devices: Port Address Translation (PAT)

![[Pasted image 20250929210613.png]]

Es stellt sich eine häufige Frage: Wenn mehrere Geräte in Ihrem privaten Netzwerk (z. B. Ihr Laptop, Ihr Telefon, ein Smart-TV) alle NAT verwenden, um sich dieselbe öffentliche IP-Adresse zu teilen, wie kann der Router dann wissen, für welches Gerät ein eingehendes Antwortpaket bestimmt ist?

Hier kommt **Port Address Translation (PAT)**, auch bekannt als **NAT Overload**, ins Spiel. PAT ist die häufigste Art von NAT.

Wenn Ihr Computer ein ausgehendes Paket sendet, hat es nicht nur eine Quell-IP-Adresse, sondern auch eine **Quellportnummer**. Wenn Ihr Browser zum Beispiel eine Web-Anfrage stellt, könnte er einen zufälligen Quell-Port wie "51000" verwenden. Der Zielport ist normalerweise "80" (für HTTP) oder "443" (für HTTPS).

PAT macht sich diese Portnummern zunutze:

- Wenn der Router die private Quell-IP in seine öffentliche IP übersetzt, übersetzt er oft auch die Quell-Portnummer.
    
- Dadurch wird sichergestellt, dass jede aktive Sitzung von einem internen Gerät in der NAT-Tabelle einer eindeutigen Kombination aus (öffentlicher IP-Adresse des Routers + eindeutiger Quellportnummer) zugeordnet wird.
    
- Ein Beispiel:
    
    - Ihr Laptop (192.168.1.100, Quellport 51000) sendet eine Anfrage. Der Router könnte diese auf (`Public_IP`, Quellport `34001`) abbilden.
    - Ihr Telefon (`192.168.1.101`, Quellport `52000`) sendet gleichzeitig eine Anfrage. Der Router könnte diese auf (`Public_IP`, Quellport `34002`) abbilden.
    
    |private IP|privater Port|öffentliche IP|öffentlicher Port|
 |---|---|---|---|
 |192.168.1.100|51000|80.100.20.30|34001|
 |192.168.1.101|52000|80.100.20.30|34002|
    
- Wenn eine Antwort an die öffentliche IP-Adresse des Routers zurückkommt, sieht sich der Router die **Ziel-Portnummer** im eingehenden Paket an (das war die Quell-Portnummer, die er zugewiesen und aufgezeichnet hat). Anhand dieser Portnummer kann er eindeutig feststellen, für welches interne Gerät das Paket bestimmt ist.
    
- Anschließend wird die Ziel-IP-Adresse in die korrekte private IP-Adresse und der Ziel-Port in den ursprünglichen Quell-Port des internen Geräts zurückübersetzt.
    

Durch die Verwendung unterschiedlicher Quellportnummern auf der öffentlichen Seite für verschiedene interne Sitzungen kann eine einzige öffentliche IP-Adresse von vielen privaten IP-Geräten gemeinsam genutzt werden, wodurch die einzelne öffentliche IP-Adresse effektiv "überlastet" wird. Aus diesem Grund kann Ihr gesamter Haushalt gleichzeitig im Internet surfen und dabei nur eine einzige öffentliche IP-Adresse verwenden, die Ihnen von Ihrem ISP zur Verfügung gestellt wird.

### Denken Sie darüber nach

- **Skalierbarkeit:** Wie verbessert PAT die Skalierbarkeit der IPv4-Nutzung im Vergleich zu einem einfachen NAT, das nur die IP-Adressen ändert?
- **Auswirkungen auf die Sicherheit:** Wenn jemand im Internet versucht, ein unerwünschtes Paket an die öffentliche IP-Adresse Ihres Routers zu senden, wie würde NAT/PAT normalerweise damit umgehen, wenn in der NAT-Tabelle kein Eintrag für diesen Datenverkehr vorhanden ist? (Hinweis: Dies ist ein wichtiger Grund, warum NAT oft als eine grundlegende Form der Firewall betrachtet wird).
- **Einschränkungen:** Fallen Ihnen Anwendungen oder Dienste ein, die Probleme haben könnten, durch NAT korrekt zu funktionieren? (Denken Sie an Anwendungen, die erfordern, dass eingehende Verbindungen aus dem Internet initiiert werden, oder an Protokolle, die IP-Adressinformationen in ihre Daten-Nutzlast einbetten).

Dieses Material sollte Ihnen eine solide Grundlage über private IP-Adressen, NAT und PAT vermitteln. In unserer nächsten Live-Sitzung werden wir diese Konzepte vertiefen, verschiedene Arten von NAT untersuchen und ihre Auswirkungen diskutieren.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Networking-12-Private-IPs-NAT-PAT-fuj6j8gan6dbxv4?mode=doc](https://gamma.app/docs/Networking-12-Private-IPs-NAT-PAT-fuj6j8gan6dbxv4?mode=doc)

Try not to peek before class - spoilers inside!

</aside>