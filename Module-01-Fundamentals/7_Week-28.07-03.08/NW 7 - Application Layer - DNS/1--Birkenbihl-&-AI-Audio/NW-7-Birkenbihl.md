Welcome to the Domain Name System, DNS! Before our live session, please go through this material to understand the basics of how we navigate the internet using names instead of numbers. Willkommen zum Domain Name System, DNS! Bitte gehen Sie dieses Material durch, bevor unsere Live-Sitzung beginnt, um die Grundlagen zu verstehen, wie wir im Internet mit Namen statt mit Zahlen navigieren.

What is DNS and Why Do We Need It? Was ist DNS und warum brauchen wir es?

Computers on the internet communicate using numerical addresses called IP addresses, like 142.250.180.142 or 2a00:1450:4005:80a::200e. Computer im Internet kommunizieren über numerische Adressen, die man IP-Adressen nennt, wie zum Beispiel 142.250.180.142 oder 2a00:1450:4005:80a::200e.

Imagine trying to remember the phone numbers of all your contacts, it would be impossible! Stellen Sie sich vor, Sie müssten sich die Telefonnummern aller Ihrer Kontakte merken, das wäre unmöglich!

Similarly, remembering IP addresses for every website you visit is impractical. Ebenso ist es unpraktisch, sich die IP-Adressen jeder Website zu merken, die Sie besuchen.

Humans prefer using memorable names, like google.com or wikipedia.org. Menschen bevorzugen einprägsame Namen wie google.com oder wikipedia.org.

The Domain Name System, DNS, acts like the internet's phonebook. Das Domain Name System, DNS, funktioniert wie das Telefonbuch des Internets.

Its primary job is to translate these human-friendly domain names into the computer-friendly IP addresses needed to locate and connect to servers. Seine Hauptaufgabe ist es, diese menschenfreundlichen Domainnamen in die computerfreundlichen IP-Adressen zu übersetzen, die benötigt werden, um Server zu finden und sich mit ihnen zu verbinden.

Without DNS, navigating the web would involve typing long strings of numbers for every site, making the internet far less user-friendly. Ohne DNS würde das Navigieren im Web bedeuten, dass man für jede Website lange Zahlenfolgen eintippen müsste, was das Internet weitaus weniger benutzerfreundlich machen würde.

The DNS Hierarchy: A Global Directory Die DNS-Hierarchie: Ein globales Verzeichnis

DNS isn't just one giant phonebook, it's a distributed, hierarchical system. DNS ist nicht nur ein riesiges Telefonbuch, sondern ein verteiltes, hierarchisches System.

Think of it like an upside-down tree. Denken Sie daran wie an einen umgedrehten Baum.

Root Zone: At the very top are the root servers. Wurzelzone: Ganz oben befinden sich die Wurzel-Server.

There isn't just one, but a network of hundreds of servers worldwide managed by various organizations. Es gibt nicht nur einen, sondern ein Netzwerk von Hunderten von Servern weltweit, die von verschiedenen Organisationen verwaltet werden.

They don't know the IP address for www.google.com directly, but they know where to find the servers responsible for the next level down, the Top-Level Domains. Sie kennen die IP-Adresse für www.google.com nicht direkt, aber sie wissen, wo sie die Server finden, die für die nächste Ebene darunter zuständig sind, die Top-Level-Domains.

You often don't see the final dot in web addresses, but it's implicitly there, for example, google.com. is the fully qualified name. Man sieht den letzten Punkt in Webadressen oft nicht, aber er ist implizit vorhanden, zum Beispiel ist google.com. der vollständig qualifizierte Name.

Top-Level Domains, TLDs: These are the familiar endings like .com, .org, .net, .gov, .uk, .de, etc. Top-Level-Domains, TLDs: Das sind die bekannten Endungen wie .com, .org, .net, .gov, .uk, .de und so weiter.

Each TLD has its own set of authoritative name servers that manage the domains directly under them. Jede TLD hat ihre eigenen autoritativen Nameserver, die die Domains direkt darunter verwalten.

The root servers direct queries to the appropriate TLD servers. Die Wurzel-Server leiten Anfragen an die entsprechenden TLD-Server weiter.

For example, if you ask for google.com, the root server says, I don't know, but ask the .com servers. Wenn Sie zum Beispiel nach google.com fragen, sagt der Wurzel-Server: Ich weiß es nicht, aber fragen Sie die .com-Server.

Second-Level Domains, SLDs: This is the part you usually register, like google in google.com or wikipedia in wikipedia.org. Second-Level-Domains, SLDs: Das ist der Teil, den man normalerweise registriert, wie google in google.com oder wikipedia in wikipedia.org.

The organization that registers the domain, for example, Google LLC, Wikimedia Foundation, manages its own authoritative name servers, or delegates this to their hosting provider. Die Organisation, die die Domain registriert, zum Beispiel Google LLC oder die Wikimedia Foundation, verwaltet ihre eigenen autoritativen Nameserver oder delegiert dies an ihren Hosting-Anbieter.

These servers hold the actual records that map names to IP addresses for that specific domain. Diese Server enthalten die tatsächlichen Einträge, die Namen zu IP-Adressen für diese bestimmte Domain zuordnen.

Subdomains: Organizations can further divide their domains using subdomains, like mail.google.com or en.wikipedia.org. Subdomains: Organisationen können ihre Domains weiter unterteilen, indem sie Subdomains verwenden, wie mail.google.com oder en.wikipedia.org.

The authoritative name servers for the main domain, google.com, wikipedia.org, also handle requests for their subdomains or delegate them to other specific name servers. Die autoritativen Nameserver für die Hauptdomain, google.com oder wikipedia.org, bearbeiten auch Anfragen für ihre Subdomains oder delegieren sie an andere spezifische Nameserver.

This hierarchical structure makes the system scalable and resilient. Diese hierarchische Struktur macht das System skalierbar und widerstandsfähig.

No single entity holds all the information, and responsibility is delegated down the tree. Keine einzelne Instanz hält alle Informationen, und die Verantwortung wird entlang des Baumes nach unten delegiert.

How Does a DNS Query Work? Wie funktioniert eine DNS-Anfrage?

When you type www.example.com into your browser, a multi-step process happens behind the scenes, often involving several types of DNS servers. Wenn Sie www.example.com in Ihren Browser eingeben, läuft im Hintergrund ein mehrstufiger Prozess ab, der oft mehrere Arten von DNS-Servern einbezieht.

Local Cache Check: Your computer first checks its own DNS cache, a temporary memory of recent lookups, and your browser checks its cache. Lokale Cache-Prüfung: Ihr Computer prüft zunächst seinen eigenen DNS-Cache, einen temporären Speicher kürzlicher Abfragen, und Ihr Browser prüft seinen Cache.

If the IP address for www.example.com was recently looked up and is still valid, based on its Time-To-Live or TTL value, the IP address is returned immediately, and the process stops here. Wenn die IP-Adresse für www.example.com kürzlich abgefragt wurde und basierend auf ihrem Time-To-Live- oder TTL-Wert noch gültig ist, wird die IP-Adresse sofort zurückgegeben und der Prozess endet hier.

Your operating system might also check a local hosts file first, which manually maps names to IPs. Ihr Betriebssystem könnte auch zuerst eine lokale Hosts-Datei prüfen, die Namen manuell zu IPs zuordnet.

Recursive Resolver, Your ISP or Public DNS: If the address isn't in the local cache, your computer sends the query to its configured DNS resolver. Rekursiver Resolver, Ihr ISP oder öffentliches DNS: Wenn die Adresse nicht im lokalen Cache ist, sendet Ihr Computer die Anfrage an seinen konfigurierten DNS-Resolver.

This is usually provided by your Internet Service Provider, ISP, but you might configure it to use a public resolver like Google's, 8.8.8.8, or Cloudflare's, 1.1.1.1. Dieser wird normalerweise von Ihrem Internetdienstanbieter, dem ISP, bereitgestellt, aber Sie können ihn auch so konfigurieren, dass er einen öffentlichen Resolver wie den von Google, 8.8.8.8, oder den von Cloudflare, 1.1.1.1, verwendet.

This resolver acts on your behalf to find the answer. Dieser Resolver handelt in Ihrem Auftrag, um die Antwort zu finden.

This type of query is called a recursive query because the client asks the resolver to perform the full lookup process and return the final answer. Diese Art von Anfrage nennt man eine rekursive Anfrage, weil der Client den Resolver bittet, den vollständigen Suchprozess durchzuführen und die endgültige Antwort zurückzugeben.

Root Server Query: The recursive resolver, if it doesn't have the answer cached, starts by asking one of the root name servers: Where can I find the IP for www.example.com? Wurzel-Server-Anfrage: Der rekursive Resolver fragt, wenn er die Antwort nicht im Cache hat, zunächst einen der Wurzel-Nameserver: Wo finde ich die IP für www.example.com?

TLD Server Query: The root server doesn't know the final answer but knows who manages the .com TLD. TLD-Server-Anfrage: Der Wurzel-Server kennt die endgültige Antwort nicht, weiß aber, wer die .com-TLD verwaltet.

It replies with the addresses of the .com TLD name servers. Er antwortet mit den Adressen der .com-TLD-Nameserver.

The resolver then asks a .com TLD server: Where can I find the IP for www.example.com? Der Resolver fragt dann einen .com-TLD-Server: Wo finde ich die IP für www.example.com?

Authoritative Name Server Query: The .com TLD server doesn't know the final answer but knows the authoritative name servers responsible for the example.com domain, these were specified when the domain was registered. Autoritative Nameserver-Anfrage: Der .com-TLD-Server kennt die endgültige Antwort nicht, weiß aber, welche autoritativen Nameserver für die Domain example.com zuständig sind, diese wurden bei der Registrierung der Domain angegeben.

It replies with the addresses of example.com's authoritative name servers. Er antwortet mit den Adressen der autoritativen Nameserver von example.com.

The resolver then asks one of example.com's authoritative name servers: What is the IP address for www.example.com? Der Resolver fragt dann einen der autoritativen Nameserver von example.com: Was ist die IP-Adresse für www.example.com?

Final Answer: The authoritative name server for example.com checks its records and finds the IP address associated with the www subdomain. Endgültige Antwort: Der autoritative Nameserver für example.com prüft seine Einträge und findet die IP-Adresse, die mit der Subdomain www verbunden ist.

It sends this IP address back to the recursive resolver. Er sendet diese IP-Adresse zurück an den rekursiven Resolver.

The queries performed by the resolver, steps 3 to 5, are called iterative queries because the resolver asks each server level for the next step until it gets the final answer. Die vom Resolver durchgeführten Anfragen, Schritte 3 bis 5, nennt man iterative Anfragen, weil der Resolver jede Serverebene nach dem nächsten Schritt fragt, bis er die endgültige Antwort erhält.

Caching and Response: The recursive resolver receives the IP address, stores it in its cache for future requests, respecting the TTL, and finally sends the IP address back to your computer. Caching und Antwort: Der rekursive Resolver erhält die IP-Adresse, speichert sie unter Berücksichtigung der TTL in seinem Cache für zukünftige Anfragen und sendet die IP-Adresse schließlich zurück an Ihren Computer.

Connection: Your computer now has the IP address and can establish a connection to the web server hosting www.example.com. Verbindung: Ihr Computer hat jetzt die IP-Adresse und kann eine Verbindung zum Webserver herstellen, der www.example.com hostet.

This entire process usually happens in milliseconds! Dieser gesamte Prozess geschieht normalerweise in Millisekunden!

Think about it: What are the potential benefits and drawbacks of using a public DNS resolver, like 1.1.1.1 or 8.8.8.8, instead of the one provided by your ISP? Denken Sie darüber nach: Was sind die möglichen Vorteile und Nachteile, wenn man einen öffentlichen DNS-Resolver wie 1.1.1.1 oder 8.8.8.8 verwendet, anstatt den, der von Ihrem ISP bereitgestellt wird?

Common DNS Record Types Gängige DNS-Eintragstypen

Authoritative name servers store information in DNS records. Autoritative Nameserver speichern Informationen in DNS-Einträgen.

While there are many types, here are some of the most common ones you'll encounter. Obwohl es viele Typen gibt, sind hier einige der häufigsten, denen Sie begegnen werden.

A Record, Address Mapping: Maps a hostname to an IPv4 address, for example, google.com to 142.250.180.142. A-Eintrag, Adresszuordnung: Ordnet einen Hostnamen einer IPv4-Adresse zu, zum Beispiel google.com zu 142.250.180.142.

This is the most fundamental record type. Dies ist der grundlegendste Eintragstyp.

AAAA Record, IPv6 Address Mapping: Maps a hostname to an IPv6 address, for example, google.com to 2a00:1450:4005:80a::200e. AAAA-Eintrag, IPv6-Adresszuordnung: Ordnet einen Hostnamen einer IPv6-Adresse zu, zum Beispiel google.com zu 2a00:1450:4005:80a::200e.

Pronounced Quad-A. Ausgesprochen Quad-A.

CNAME Record, Canonical Name: Creates an alias, pointing one domain name to another, for example, www.example.com might be a CNAME pointing to example.com. CNAME-Eintrag, Kanonischer Name: Erstellt einen Alias, der einen Domainnamen auf einen anderen zeigt, zum Beispiel könnte www.example.com ein CNAME sein, der auf example.com zeigt.

The DNS lookup will continue with the target name, example.com, to find its A or AAAA record. Die DNS-Abfrage wird mit dem Zielnamen, example.com, fortgesetzt, um seinen A- oder AAAA-Eintrag zu finden.

This is useful when multiple services run on the same IP address. Dies ist nützlich, wenn mehrere Dienste auf derselben IP-Adresse laufen.

MX Record, Mail Exchanger: Specifies the mail servers responsible for receiving email for a domain. MX-Eintrag, Mail-Exchanger: Gibt die Mailserver an, die für den Empfang von E-Mails für eine Domain zuständig sind.

It includes a priority value, indicating the order in which servers should be tried, lower number equals higher priority. Er enthält einen Prioritätswert, der die Reihenfolge angibt, in der Server versucht werden sollten, niedrigere Zahl bedeutet höhere Priorität.

NS Record, Name Server: Delegates a domain or subdomain to a set of authoritative name servers. NS-Eintrag, Nameserver: Delegiert eine Domain oder Subdomain an eine Gruppe von autoritativen Nameservern.

These records are what the TLD servers use to point resolvers to the domain's specific name servers. Diese Einträge verwenden die TLD-Server, um Resolver auf die spezifischen Nameserver der Domain zu verweisen.

TXT Record, Text: Allows administrators to store arbitrary text in a DNS record. TXT-Eintrag, Text: Ermöglicht es Administratoren, beliebigen Text in einem DNS-Eintrag zu speichern.

Often used for verifying domain ownership, for example, for Google Workspace or SSL certificates, email security policies like SPF, DKIM, DMARC, or other informational purposes. Wird häufig zur Überprüfung des Domain-Eigentums verwendet, zum Beispiel für Google Workspace oder SSL-Zertifikate, E-Mail-Sicherheitsrichtlinien wie SPF, DKIM, DMARC oder andere Informationszwecke.

PTR Record, Pointer: The reverse of A or AAAA records. PTR-Eintrag, Zeiger: Das Gegenteil von A- oder AAAA-Einträgen.

Maps an IP address back to a hostname. Ordnet eine IP-Adresse zurück zu einem Hostnamen zu.

Used in reverse DNS lookups, often for logging or verification purposes. Wird bei umgekehrten DNS-Abfragen verwendet, oft für Protokollierungs- oder Überprüfungszwecke.

DNS Caching and Time-To-Live, TTL DNS-Caching und Time-To-Live, TTL

To reduce the load on DNS servers and speed up lookups, DNS responses are cached at various levels: in your browser, your operating system, and recursive resolvers. Um die Last auf DNS-Servern zu reduzieren und Abfragen zu beschleunigen, werden DNS-Antworten auf verschiedenen Ebenen zwischengespeichert: in Ihrem Browser, Ihrem Betriebssystem und rekursiven Resolvern.

Each DNS record comes with a Time-To-Live, TTL, value, specified in seconds. Jeder DNS-Eintrag hat einen Time-To-Live-, TTL-Wert, der in Sekunden angegeben wird.

This tells caches how long they are allowed to store and reuse that specific record before they must ask the authoritative server again. Dies teilt den Caches mit, wie lange sie diesen spezifischen Eintrag speichern und wiederverwenden dürfen, bevor sie den autoritativen Server erneut fragen müssen.

Short TTL, for example, 60 to 300 seconds: Changes propagate quickly, but it increases the load on authoritative servers as caches expire faster. Kurze TTL, zum Beispiel 60 bis 300 Sekunden: Änderungen verbreiten sich schnell, aber es erhöht die Last auf autoritativen Servern, da Caches schneller ablaufen.

Useful for records that might change frequently or during migrations. Nützlich für Einträge, die sich häufig ändern könnten oder während Migrationen.

Long TTL, for example, 86400 seconds equals 24 hours: Reduces server load and can speed up lookups for frequently accessed names, but changes take longer to propagate across the internet as caches hold onto old data longer. Lange TTL, zum Beispiel 86400 Sekunden entspricht 24 Stunden: Reduziert die Serverlast und kann Abfragen für häufig aufgerufene Namen beschleunigen, aber Änderungen brauchen länger, um sich im Internet zu verbreiten, da Caches alte Daten länger behalten.

Choosing appropriate TTL values involves balancing performance, server load, and the speed at which changes need to take effect. Die Wahl angemessener TTL-Werte erfordert ein Gleichgewicht zwischen Leistung, Serverlast und der Geschwindigkeit, mit der Änderungen wirksam werden müssen.

Try it yourself: Open the Terminal application on your Mac, you can find it using Spotlight search: Command plus Space, then type Terminal. Probieren Sie es selbst aus: Öffnen Sie die Terminal-Anwendung auf Ihrem Mac, Sie können sie mit der Spotlight-Suche finden: Befehl plus Leertaste, dann tippen Sie Terminal.

Type the command ping -c 1 google.com and press Enter. Geben Sie den Befehl ping -c 1 google.com ein und drücken Sie Enter.

Look at the output. Schauen Sie sich die Ausgabe an.

You should see an IP address in parentheses next to the domain name. Sie sollten eine IP-Adresse in Klammern neben dem Domainnamen sehen.

This IP address was likely obtained via a DNS lookup. Diese IP-Adresse wurde wahrscheinlich über eine DNS-Abfrage erhalten.

Type ping -c 1 heise.de and press Enter. Geben Sie ping -c 1 heise.de ein und drücken Sie Enter.

Note the different IP address. Beachten Sie die unterschiedliche IP-Adresse.

Now, try ping -c 1 non-existent-domain-12345.com. Versuchen Sie jetzt ping -c 1 non-existent-domain-12345.com.

What happens? Was passiert?

You should see an error indicating the host could not be resolved, meaning DNS failed to find an IP address for that name. Sie sollten eine Fehlermeldung sehen, die anzeigt, dass der Host nicht aufgelöst werden konnte, was bedeutet, dass DNS keine IP-Adresse für diesen Namen finden konnte.

This simple exercise demonstrates DNS in action, translating names you type into the IP addresses ping needs to send its request. Diese einfache Übung demonstriert DNS in Aktion, wie es Namen, die Sie eingeben, in die IP-Adressen übersetzt, die ping benötigt, um seine Anfrage zu senden.