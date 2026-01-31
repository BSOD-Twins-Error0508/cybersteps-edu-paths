Willkommen zu Ihrer Vorbereitung auf unsere Sitzung über die Netzwerkschicht! Diese Schicht ist entscheidend dafür, wie Daten über das Internet und innerhalb lokaler Netze transportiert werden. Das Verständnis ihrer Funktionen, insbesondere IP-Adressierung und Routing, ist für die Cybersicherheit von grundlegender Bedeutung. Nehmen Sie sich die Zeit, diese Materialien durchzugehen, da sie die Grundlage für unseren Live-Kurs bilden.

### The Network Layer: The Internet's Postal Service
![[0d415093c4d2160530541f0170204200c89111d3.svg]]

In unserem Schichtenmodell der Vernetzung (Sie erinnern sich vielleicht an das 5-Schichten-Modell) befindet sich die Netzwerkschicht auf Schicht 3. Ihre Hauptaufgabe besteht darin, die Adressierung und Weiterleitung von Datenpaketen über verschiedene Netze hinweg zu regeln. Stellen Sie sich die Netzwerkschicht wie den Teil des Postdienstes vor, der herausfindet, in welche Stadt und an welche Straße ein Brief geschickt werden muss, auch wenn er Tausende von Kilometern entfernt ist. Zu den wichtigsten Aufgaben der Netzwerkschicht gehören:

- **Logische Adressierung**: Die Zuweisung eindeutiger Adressen an Geräte, damit diese netzübergreifend identifiziert werden können. Die gebräuchlichste Form dieser Adresse ist die IP-Adresse.
- **Routing**: Bestimmung des besten Pfads für Datenpakete, die von einem Quellgerät zu einem Zielgerät gelangen sollen. Dazu sind spezielle Geräte, so genannte Router, erforderlich.
- **Paketweiterleitung (oder Paketvermittlung)**: Der eigentliche Prozess des Sendens von Paketen von einem Router zum nächsten entlang des festgelegten Pfads.

Die Netzwerkschicht stellt Dienste für die darüber liegende Transportschicht bereit (die sicherstellt, dass die Daten korrekt und in der richtigen Reihenfolge ankommen) und nutzt die Dienste der darunter liegenden Datenverbindungsschicht (die die Kommunikation zwischen Geräten im _gleichen_ lokalen Netz abwickelt).

### Internet-Protokoll (IP): Das Arbeitspferd

Das Internetprotokoll (IP) ist das wichtigste Protokoll auf der Netzwerkschicht. Es ist das Regelwerk, das regelt, wie Daten von einem Computer zu einem anderen über das Internet gesendet werden. Wichtige Merkmale von IP:

- **Verbindungslos**: IP baut vor dem Senden von Daten keine Verbindung auf. Jedes Paket (ein kleiner Teil Ihrer Daten) wird unabhängig behandelt. Stellen Sie sich vor, Sie verschicken jede Seite eines langen Briefes in einem separaten Umschlag, jeweils mit der vollständigen Zieladresse.
- **Best-Effort-Zustellung**: IP versucht sein Bestes, um Pakete zuzustellen, aber es gibt keine Garantie für die Zustellung. Pakete können verloren gehen, dupliziert werden oder nicht in der richtigen Reihenfolge ankommen. In der Regel sind es Protokolle auf höherer Ebene (wie TCP auf der Transportschicht), die diese Probleme lösen und eine zuverlässige Kommunikation gewährleisten.

### IP-Adressierung: Wer ist wer im Netzwerk

![[Pasted image 20250929202527.png]]
Sie ist sehr nützlich, um Netzwerksoftware zu testen, ohne tatsächlich Pakete in das Netzwerk zu senden.

**Öffentliche vs. private IP-Adressen**
Eine IP-Adresse ist eine eindeutige numerische Kennzeichnung, die jedem Gerät (Computer, Telefon, Server usw.) zugewiesen wird, das an einem Computernetz teilnimmt, das das Internetprotokoll für die Kommunikation verwendet. Sie hat zwei Hauptfunktionen: Sie identifiziert den Host (oder genauer gesagt, seine Netzwerkschnittstelle) und gibt seinen Standort im Netzwerk an.

**IPv4-Adressen** Seit vielen Jahren ist IPv4 (IP Version 4) der Standard.

Eine IPv4-Adresse ist eine 32-Bit-Zahl. Damit sie für Menschen leichter zu lesen und zu schreiben ist, wird sie normalerweise in **gepunkteter Dezimalschreibweise** ausgedrückt, z. B. "192.168.1.100". Jede der vier Zahlen (Oktette) kann von 0 bis 255 reichen.

### Subnetting: Aufteilung von Netzwerken

Eine IP-Adresse besteht nicht nur aus einer einzigen langen Zahl, sondern ist in zwei wichtige Teile unterteilt. Der Prozess dieser Unterteilung wird Subnetting genannt. Ein Subnetz oder Subnetzwerk ist eine logische Unterteilung eines IP-Netzwerks. Stellen Sie sich ein großes Unternehmen mit vielen Abteilungen vor (Vertrieb, Marketing, Technik). Anstatt alle Computer in einem großen Netzwerk zu haben, könnte jede Abteilung ihr eigenes Subnetz haben.

Warum ein Subnetz?

- **Organisation:** Hält die Netzwerke übersichtlich und verwaltbar.
- **Sicherheit:** Kann Teile eines Netzwerks isolieren. Wenn ein Subnetz kompromittiert wird, können andere sicher bleiben.
- **Leistung:** Reduziert den gesamten Netzwerkverkehr, indem der Broadcast-Verkehr auf kleinere Domänen beschränkt wird.
- **Adressverwaltung:** Ermöglicht eine effizientere Nutzung eines begrenzten Blocks von IP-Adressen.

### Subnetzmasken und Netzwerk-/Hostabschnitte

Eine **Subnetzmaske** teilt einem Computer mit, welcher Teil einer IP-Adresse der Netzwerkteil und welcher Teil der Hostteil ist. Wie eine IP-Adresse ist sie eine 32-Bit-Zahl, die oft in punktierter Dezimalschreibweise angegeben wird (z. B. "255.255.255.0").

- Der **Netzwerkteil** identifiziert das spezifische Netzwerk, zu dem das Gerät gehört. Die "255" (oder binären 1en) in der Maske "maskieren" diesen Teil aus.
- Der **Host-Teil** identifiziert das spezifische Gerät innerhalb dieses Netzwerks. Die "0" (oder binären 0er) in der Maske identifizieren diesen Teil.

Beispiel: Ihre IP lautet "192.168.1.100" und Ihre Subnetzmaske "255.255.255.0":

- Der Teil `255.255.255` der Maske bedeutet, dass `192.168.1` der **Netzteil** ist.
- Der Teil `.0` der Maske bedeutet, dass `.100` der **Host-Teil** ist.

Eine andere Möglichkeit, Subnetzmasken darzustellen, ist die **CIDR-Notation (Classless Inter-Domain Routing)**. Dies ist ein Schrägstrich, gefolgt von der Anzahl der Bits im Netzwerkteil. Zum Beispiel ist "255.255.255.0" gleichbedeutend mit "24", weil die ersten 24 Bits (3 Oktette x 8 Bits/Oktett) für das Netzwerk sind. 192.168.1.100/24" definiert also sowohl die IP als auch das Subnetz.

### Spezielle IPv4-Adressen

Jetzt, wo wir das Subnetz verstehen, können wir einige spezielle Adressen definieren, die in jedem Subnetz existieren:

- **Netzwerkadresse**: Eine IP-Adresse, bei der alle Host-Bits Null sind (z. B. "192.168.1.0" für ein typisches Heimnetzwerk mit einer "24"-Maske). Diese Adresse repräsentiert das Netzwerk selbst, nicht ein bestimmtes Gerät.
- **Broadcast-Adresse**: Eine IP-Adresse, bei der alle Host-Bits eins sind (z. B. "192.168.1.255" für ein "24"-Netz). Pakete, die an diese Adresse gesendet werden, werden an alle Geräte in diesem spezifischen Netzwerk zugestellt.
- **Loopback-Adresse**: 127.0.0.1" ist eine spezielle Adresse, die Geräte verwenden können, um Pakete an sich selbst zu senden. 


![[Pasted image 20250929202548.png]]

- **Öffentliche IP-Adressen**: Dies sind weltweit eindeutige Adressen, die Geräten zugewiesen werden, die direkt mit dem Internet verbunden sind. Ihr Heimrouter hat beispielsweise eine öffentliche IP-Adresse, die von Ihrem Internetdienstanbieter (ISP) zugewiesen wurde.
- **Private IP-Adressen**: Da nur eine begrenzte Anzahl von IPv4-Adressen zur Verfügung steht, sind bestimmte Bereiche für die Verwendung in privaten Netzen (z. B. zu Hause oder im Büro) reserviert. Diese Adressen sind im öffentlichen Internet nicht routbar. Zu den üblichen privaten IP-Adressbereichen gehören "10.0.0.0/8", "172.16.0.0/12" und "192.168.0.0/16". Die Geräte in diesen privaten Netzen verwenden diese Adressen für die interne Kommunikation. Für den Zugriff auf das Internet wird in der Regel ein Verfahren namens **Network Address Translation (NAT)** vom Router verwendet, das es mehreren Geräten ermöglicht, eine einzige öffentliche IP-Adresse zu nutzen. Wir werden uns in der nächsten Lektion ausführlicher mit privaten IP-Adressen und NAT beschäftigen.

### Denk mal drüber nach

- Ihr Computer hat die IP-Adresse `10.0.1.50` mit einer Subnetzmaske von `255.255.0.0`. Wie lautet seine Netzwerkadresse? Wie lautet die Broadcast-Adresse für dieses Subnetz?
- Warum sollte ein großer Universitätscampus sein Netz in viele Subnetze aufteilen wollen?

### Versuchen Sie es selbst

Finden Sie Ihre Netzwerkkonfiguration:

- Unter macOS: Öffnen Sie **Terminal** (Sie können es über die Spotlight-Suche finden). Geben Sie "ifconfig en0" ein (bei Wi-Fi ist "en0" normalerweise Ihre Wi-Fi-Schnittstelle; bei kabelgebundenem Ethernet könnte es "en1" oder eine andere Nummer sein. Suchen Sie nach einer aktiven Schnittstelle mit einer `inet`-Adresse).
- Alternativ kann unter neuerem macOS: `ip address show en0` oder einfach `ip a` alle Schnittstellen anzeigen.
- Identifizieren Sie Ihre IPv4-Adresse (oft mit `inet` beschriftet), Ihre Subnetzmaske (`netmask`) und Ihr Standard-Gateway (unter macOS können Sie `netstat -nr | grep default` in das Terminal eingeben; die Adresse neben "default" ist Ihr Gateway).

Pingen Sie sich selbst an:

- Geben Sie im Terminal "ping 127.0.0.1" ein. Sie sollten Antworten sehen. Dies bestätigt, dass der Netzwerkstack Ihres Computers funktioniert. Drücken Sie `Strg+C` zum Beenden.

Pingen Sie Ihr Gateway an:

- Pingen Sie die IP-Adresse des Standard-Gateways an, die Sie gefunden haben. Damit testen Sie die Verbindung zu Ihrem lokalen Router.

### IPv6: Die nächste Generation

![[Pasted image 20250929202556.png]]

IPv4 war unglaublich erfolgreich, aber es hat eine große Einschränkung: Es gibt nicht genügend eindeutige IPv4-Adressen für alle Geräte, die jetzt eine Verbindung zum Internet herstellen (Telefone, intelligente Geräte usw.). Dies wird als Erschöpfung der IPv4-Adressen bezeichnet. **IPv6 (IP Version 6)** ist der Nachfolger, der dieses Problem lösen und weitere Verbesserungen bieten soll.

Die wichtigsten Merkmale von IPv6:

- **Extrem größerer Adressraum**: IPv6-Adressen sind 128 Bit lang (im Vergleich zu 32 Bit bei IPv4). Damit steht eine astronomische Anzahl eindeutiger Adressen zur Verfügung (etwa 3,4×1038), was bedeutet, dass diese in absehbarer Zeit wohl nicht ausgehen werden.
- **Format**: IPv6-Adressen werden als acht Gruppen von vier hexadezimalen Ziffern geschrieben, die durch Doppelpunkte getrennt sind. Example: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`.
- **Abkürzungsregeln**:
    - Führende Nullen in jeder Gruppe können weggelassen werden: "0db8" ist gleichbedeutend mit "db8".
    - Eine Folge von aufeinanderfolgenden Gruppen von Nullen kann durch einen Doppelpunkt (`::`) ersetzt werden. Zum Beispiel kann `2001:0db8:0000:0000:1234:0000:0000:5678` als `2001:db8::1234:0:0:5678` geschrieben werden. Das `::` darf nur einmal in einer Adresse verwendet werden, um Mehrdeutigkeiten zu vermeiden. Das Beispiel `2001:0db8:85a3:0000:0000:8a2e:0370:7334` könnte `2001:db8:85a3::8a2e:370:7334` sein.
- **Vereinfachter Header**: Der IPv6-Paketkopf ist einfacher als der von IPv4, was zu einer effizienteren Verarbeitung durch Router führen kann.
- **Kein NAT (in der Regel)**: Bei so vielen Adressen ist Network Address Translation (NAT) in der Regel nicht erforderlich, was eine echte End-to-End-Konnektivität ermöglicht.
- **Eingebaute Sicherheit (obligatorische IPSec-Unterstützung)**: IPSec (Internet Protocol Security) gibt es zwar schon für IPv4, aber seine Unterstützung ist bei IPv6 obligatorisch, was die Sicherheit der Kommunikation erleichtern kann (die tatsächliche Nutzung ist jedoch unterschiedlich).

In vielen Netzen werden heute IPv4 und IPv6 gleichzeitig betrieben (dies wird als "Dual-Stack" bezeichnet).

### Versuchen Sie es selbst

- Prüfen Sie, ob Ihr Computer eine IPv6-Adresse hat. Unter macOS suchen Sie in der Ausgabe von `ifconfig en0` (oder Ihrer aktiven Schnittstelle) nach einer Adresse mit der Bezeichnung `inet6`. Es handelt sich um eine lange hexadezimale Zeichenfolge.
- Versuchen Sie, eine IPv6-Adresse anzupingen. Der öffentliche DNS-Server von Google hat zum Beispiel eine IPv6-Adresse: `ping6 2001:4860:4860::8888` (unter macOS verwenden Sie `ping6`).

### Routing: Den besten Pfad finden
![[routing-diagram.svg]]

Unter Routing versteht man den Prozess der Auswahl von Pfaden in einem Netz, auf denen Datenpakete von einer Quelle zu einem Ziel gelangen. Hierfür sind Geräte namens **Router** zuständig. Router arbeiten auf der Netzwerkschicht und führen **Routing-Tabellen**.

**Routing-Tabellen**: Eine Routing-Tabelle ist wie eine Karte für einen Router. Sie enthält Informationen über:

- **Zielnetz**: Das Netzwerk, das das Paket zu erreichen versucht.
- **Nächster Hop**: Die IP-Adresse des nächsten Routers auf dem Weg zum Zielnetz.
- **Schnittstelle**: Die physische Netzwerkschnittstelle (z. B. Ethernet-Port), die der Router verwenden soll, um das Paket an den nächsten Hop zu senden.
- **Metrik**: Ein Maß für die "Kosten" einer Route (z. B. die Anzahl der Sprünge, die Geschwindigkeit der Verbindung). Router versuchen, den Weg mit der niedrigsten Metrik zu wählen.

Wenn ein Router ein Paket empfängt, prüft er die Ziel-IP-Adresse im Header des Pakets. Dann konsultiert er seine Routing-Tabelle, um die beste Übereinstimmung für dieses Zielnetz zu finden, und leitet das Paket an den entsprechenden nächsten Hop oder direkt an das Ziel weiter, wenn es sich in einem verbundenen Netz befindet.

**Arten von Routing (kurzer Überblick)**:

- **Statisches Routing**: Netzwerkadministratoren konfigurieren Routen manuell in der Routing-Tabelle. Dies ist für kleine Netze einfach, lässt sich aber nicht gut skalieren und kann sich nicht automatisch an Netzänderungen anpassen.
- **Dynamisches Routing**: Router verwenden spezielle Routing-Protokolle (wie OSPF, EIGRP, BGP, RIP), um miteinander zu kommunizieren und automatisch von verfügbaren Routen und Änderungen der Netztopologie zu erfahren. Dies ist komplexer, aber viel skalierbarer und robuster.

**Standard-Gateway**: Die meisten Endgeräte (z. B. Ihr Computer) sind selbst keine Router und verfügen nicht über umfangreiche Routing-Tabellen. Sie kennen in der Regel nur ihr lokales Netzwerk. Wenn ein Gerät ein Paket an ein Ziel _außerhalb_ seines lokalen Netzwerks senden möchte, sendet es das Paket an sein **Standard-Gateway**. Das Standard-Gateway ist ein Router im lokalen Netz, der weiß, wie man Pakete an andere Netze (einschließlich des Internets) weiterleitet.

### Versuchen Sie es selbst

Zeigen Sie Ihre Routing-Tabelle an:

- Unter macOS: Öffnen Sie Terminal und geben Sie `netstat -nr` ein. Suchen Sie nach der "Standard"-Route - dies ist Ihr Standard-Gateway. Sie werden auch Routen zu direkt verbundenen Netzwerken sehen.

### Denken Sie darüber nach

- Wenn das Standard-Gateway Ihres Computers ausgefallen ist, können Sie dann noch auf Websites im Internet zugreifen? Können Sie noch auf einem Drucker in Ihrem lokalen Netzwerk drucken?
- Warum ist dynamisches Routing trotz seiner Komplexität für große Netzwerke wie das Internet vorzuziehen?

Dieses Vorbereitungsmaterial deckt die grundlegenden Konzepte der Netzwerkschicht ab. Machen Sie sich keine Sorgen, wenn noch nicht alles klar ist; wir werden diese Themen in unserer Live-Sitzung mit praktischen Demonstrationen überprüfen und erweitern. Das Ziel ist es, Sie mit der Terminologie und den grundlegenden Ideen vertraut zu machen.

### Einrichtung: Installation von Cisco Packet Tracer

![[Pasted image 20250929202639.png]]![image.png](attachment:ea193ac9-c4f1-46c6-b490-986e13248e57:image.png)

Für die kommenden Lektionen und Übungen werden wir **Cisco Packet Tracer** verwenden, ein leistungsstarkes Netzwerksimulationstool, mit dem Sie virtuelle Netzwerke aufbauen, konfigurieren und Fehler beheben können. Bitte installieren Sie es vor unserer Live-Sitzung.

**Installation von Cisco Packet Tracer**

1. **Kontoerstellung:**
    - Rufen Sie die Website der Cisco Networking Academy auf: [https://www.netacad.com/](https://www.netacad.com/)
    - Sie müssen ein kostenloses Konto erstellen. Suchen Sie nach Optionen wie "Packet Tracer" oder "Kurse" und dann "Packet Tracer", was normalerweise zu einer Anmelde- oder Login-Seite führt. Oft wird ein "Introduction to Packet Tracer"-Kurs angeboten, der den Zugang ermöglicht.
    - Melden Sie sich für ein Konto an. Dies kann bedeuten, dass Sie sich für einen kurzen Einführungskurs anmelden (den Sie nicht unbedingt vollständig abschließen müssen, der Ihnen aber Zugang zum Download verschafft).
2. **Download:**
    - Sobald Sie in Ihrem NetAcad-Konto eingeloggt sind, navigieren Sie zum Download-Bereich für Packet Tracer. Diesen finden Sie normalerweise unter "Ressourcen" > "Packet Tracer herunterladen".
    - Laden Sie die neueste Version von Cisco Packet Tracer für **macOS:** [https://www.netacad.com/resources/lab-downloads?courseLang=en-US](https://www.netacad.com/resources/lab-downloads?courseLang=en-US)
3. **Installation:**
    - Öffnen Sie die heruntergeladene `.dmg`-Datei.
    - Folgen Sie den Anweisungen auf dem Bildschirm, um Packet Tracer zu installieren. In der Regel müssen Sie die Packet Tracer-Anwendung in Ihren Anwendungsordner ziehen.
4. **Erster Start & Anmeldung:**
    - Starten Sie Packet Tracer aus Ihrem Anwendungsordner.
    - Wenn Sie Packet Tracer zum ersten Mal starten (und gelegentlich danach), werden Sie aufgefordert, sich mit Ihren Cisco Networking Academy (NetAcad)-Zugangsdaten anzumelden, die Sie in Schritt 1 erstellt haben. Dies ist für die volle Funktionalität erforderlich.
    - Wenn Sie die Wahl zwischen "Networking Academy" und "Skills For All" haben, wählen Sie "Skills For All".

Vergewissern Sie sich, dass Packet Tracer installiert ist und Sie sich _vor_ dem Kurs erfolgreich anmelden können. Dadurch sparen Sie wertvolle Zeit während der Sitzung. Sollten Sie auf Probleme stoßen, suchen Sie bitte online nach Lösungen zum Thema "Cisco Packet Tracer Installation macOS" oder wenden Sie sich an unseren Support.

Außerdem sind die Standard-Schriftarten von Cisco Packet Tracer ziemlich klein (vor allem in der CLI der Computer). Es wird empfohlen, die Schriftart über das obere Menü zu vergrößern: Cisco Packet Tracer > Preferences > Font > CLI Change to 18 (und vergessen Sie nicht, unten auf der Seite auf Apply zu klicken)

![[Pasted image 20250929202655.png]]

![[Pasted image 20250929202700.png]]

![[Pasted image 20250929202711.png]]

<aside> 📌

The slides for the live session can be viewed here: [http://gamma.app/docs/Networking-11-Network-Layer-IP-Subnets-Routing-hx4p3b7m1ihk9mm?mode=doc](http://gamma.app/docs/Networking-11-Network-Layer-IP-Subnets-Routing-hx4p3b7m1ihk9mm?mode=doc)

Try not to peek before class - spoilers inside!

</aside>