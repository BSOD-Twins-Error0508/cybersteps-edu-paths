Trusts: A trust is a relationship established between domains that allows users in one domain to be authenticated and authorized to access resources in another.
Trusts: Ein Trust ist eine Beziehung zwischen Domänen, die es Benutzern in einer Domäne ermöglicht, in einer anderen authentifiziert und autorisiert zu werden, um auf Ressourcen zuzugreifen.

Think of it like two allied countries agreeing to recognize each other's passports.
Stellen Sie es sich vor wie zwei verbündete Länder, die sich einig sind, die Pässe des anderen anzuerkennen.

By default, all domains within a single forest have a two-way, transitive trust.
Standardmäßig haben alle Domänen in einem einzelnen Forest einen bidirektionalen, transitiven Trust.

This means if Domain A trusts Domain B, and Domain B trusts Domain C, then Domain A automatically trusts Domain C.
Das bedeutet, wenn Domäne A Domäne B vertraut und Domäne B Domäne C vertraut, dann vertraut Domäne A automatisch Domäne C.

From a security perspective, this is critical: a compromised high-privilege account in one domain can potentially be used to move laterally and attack other domains in the forest.
Aus Sicherheits-Sicht ist das entscheidend: Ein kompromittiertes Konto mit hohen Privilegien in einer Domäne kann potenziell verwendet werden, um lateral zu bewegen und andere Domänen im Forest anzugreifen.

Global Catalog: The Global Catalog is a special, partial, read-only copy of every object from every domain in the forest.
Global Catalog: Der Global Catalog ist eine spezielle, partielle, schreibgeschützte Kopie jedes Objekts aus jeder Domäne im Forest.

Its purpose is to enable fast and efficient searches across the entire forest.
Sein Zweck ist es, schnelle und effiziente Suchen im gesamten Forest zu ermöglichen.

Without the Global Catalog, finding a user in a different domain would require a slow query to that domain's specific controller.
Ohne den Global Catalog würde das Finden eines Benutzers in einer anderen Domäne eine langsame Abfrage an den spezifischen Controller dieser Domäne erfordern.

The Global Catalog contains the most commonly searched attributes (like name and email address), allowing you to quickly find any resource in the forest.
Der Global Catalog enthält die am häufigsten gesuchten Attribute (wie Name und E-Mail-Adresse), was es Ihnen ermöglicht, jede Ressource im Forest schnell zu finden.

It is hosted on specific Domain Controllers designated as Global Catalog servers.
Er wird auf spezifischen Domain Controllern gehostet, die als Global Catalog-Server designiert sind.

Interacting with Active Directory
Interaktion mit Active Directory

Two key protocols govern how users and computers interact with Active Directory: Kerberos for authentication and LDAP for querying.
Zwei Schlüsselprotokolle regeln, wie Benutzer und Computer mit Active Directory interagieren: Kerberos für die Authentifizierung und LDAP für Abfragen.

Authentication: Kerberos
Authentifizierung: Kerberos

The primary authentication protocol in Active Directory is Kerberos.
Das primäre Authentifizierungsprotokoll in Active Directory ist Kerberos.

Instead of sending your password over the network for every action, Kerberos uses a ticket-based system.
Statt Ihr Passwort für jede Aktion über das Netzwerk zu senden, verwendet Kerberos ein ticket-basiertes System.

Initial Login: You log in with your password.
Erste Anmeldung: Sie melden sich mit Ihrem Passwort an.

Your computer sends an authentication request to the Domain Controller.
Ihr Computer sendet eine Authentifizierungsanfrage an den Domain Controller.

The Domain Controller validates your credentials and issues a TGT (Ticket Granting Ticket), a temporary, encrypted proof of identity.
Der Domain Controller validiert Ihre Anmeldedaten und stellt ein TGT (Ticket Granting Ticket) aus, einen temporären, verschlüsselten Beweis Ihrer Identität.

Requesting Service Access: When you want to access a resource (like a file share), your computer presents the TGT to the Domain Controller and requests a service ticket for that specific resource.
Anfordern des Service-Zugriffs: Wenn Sie auf eine Ressource zugreifen möchten (wie eine Dateifreigabe), präsentiert Ihr Computer das TGT dem Domain Controller und fordert ein Service-Ticket für diese spezifische Ressource an.

The Domain Controller provides a Service Ticket, which is specific to the resource and has a short lifespan.
Der Domain Controller stellt ein Service-Ticket zur Verfügung, das spezifisch für die Ressource ist und eine kurze Lebensdauer hat.

Accessing the Resource: Your computer presents the service ticket to the file server, which verifies it and grants access.
Zugriff auf die Ressource: Ihr Computer präsentiert das Service-Ticket dem Dateiserver, der es überprüft und den Zugriff gewährt.

The key security benefit is that your password is only sent once.
Der wichtigste Sicherheitsvorteil ist, dass Ihr Passwort nur einmal gesendet wird.

All subsequent operations use these temporary tickets, minimizing the risk of password theft from network sniffing.
Alle nachfolgenden Operationen verwenden diese temporären Tickets, was das Risiko des Passwortdiebstahls durch Netzwerk-Sniffing minimiert.

Querying Active Directory: LDAP (Lightweight Directory Access Protocol)
Abfragen von Active Directory: LDAP (Lightweight Directory Access Protocol)

While Kerberos handles proving who you are, LDAP is the protocol used to ask questions of the directory.
Während Kerberos sich um den Beweis kümmert, wer Sie sind, ist LDAP das Protokoll, das verwendet wird, um Fragen an das Directory zu stellen.

It's the language used to find, read, and modify objects and their attributes.
Es ist die Sprache, die verwendet wird, um Objekte und ihre Attribute zu finden, zu lesen und zu modifizieren.

For example, an application might use an LDAP query to:
Zum Beispiel könnte eine Anwendung eine LDAP-Abfrage verwenden, um:

Find the email address for a user named John Smith.
Die E-Mail-Adresse für einen Benutzer namens John Smith zu finden.

List all members of the Domain Admins group.
Alle Mitglieder der Domain Admins-Gruppe aufzulisten.

Get the phone number attribute for all users in the Sales Organizational Unit.
Das Telefonnummer-Attribut für alle Benutzer in der Sales Organizational Unit zu holen.

From a security standpoint, LDAP is a primary tool for reconnaissance.
Aus Sicherheits-Sicht ist LDAP ein primäres Werkzeug für Reconnaissance.

Attackers will use LDAP queries to map out the domain, find privileged users, and identify potential targets.
Angreifer werden LDAP-Abfragen verwenden, um die Domäne zu kartieren, privilegierte Benutzer zu finden und potenzielle Ziele zu identifizieren.

Misconfigurations that allow anonymous LDAP queries (queries without authentication) can provide an attacker with a complete blueprint of the internal network.
Fehlkonfigurationen, die anonyme LDAP-Abfragen erlauben (Abfragen ohne Authentifizierung), können einem Angreifer einen vollständigen Bauplan des internen Netzwerks liefern.