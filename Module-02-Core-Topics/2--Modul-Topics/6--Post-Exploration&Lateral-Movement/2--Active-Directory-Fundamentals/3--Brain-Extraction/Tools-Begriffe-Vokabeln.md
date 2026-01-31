### Verwendete Tools

| Tool | Bedeutung |
|------|-----------|
| Keine spezifischen Tools erwähnt | Der Text konzentriert sich auf konzeptionelle Aspekte von Active Directory und erwähnt keine spezifischen Software-Tools. Interaktionen mit AD erfolgen über Protokolle wie Kerberos und LDAP, die keine eigenständigen Tools sind, sondern in AD integriert sind. |

### Technische Fachbegriffe

| Fachbegriff | Bedeutung |
|-------------|-----------|
| Directory Service | Eine Datenbank, die Benutzer und Ressourcen in einem Netzwerk verwaltet, z. B. Benutzerkonten, Computer, Drucker und Sicherheitsrichtlinien, um eine zentrale Verwaltung und Sicherheit zu ermöglichen. |
| Active Directory (AD) | Microsofts Implementierung eines Directory Service, das auf Windows Server läuft und Authentifizierung, Autorisierung und Ressourcenverwaltung in Windows-Netzwerken übernimmt. |
| Domain Controller (DC) | Ein Server mit der Rolle Active Directory Domain Services (AD DS), der die AD-Datenbank speichert, Authentifizierung und Autorisierung durchführt und Sicherheitsrichtlinien durchsetzt. |
| Organizational Unit (OU) | Ein Container innerhalb einer Domäne, der verwendet wird, um Objekte wie Benutzer oder Computer zu organisieren, administrative Kontrolle zu delegieren und spezifische Richtlinien anzuwenden. |
| Tree | Eine hierarchische Sammlung von Domänen, die einen zusammenhängenden Namensraum teilen, z. B. megacorp.local und sales.megacorp.local. |
| Forest | Die höchste Ebene in AD, bestehend aus einem oder mehreren Trees, die ein gemeinsames Schema und Vertrauensbeziehungen teilen. |
| Trust | Eine Beziehung zwischen Domänen, die es Benutzern erlaubt, auf Ressourcen in einer anderen Domäne zuzugreifen, oft als bidirektionale, transitive Vertrauensstellung innerhalb eines Forests. |
| Global Catalog (GC) | Ein partieller, schreibgeschützter Katalog aller Objekte im Forest, der schnelle Suchen über Domänen hinweg ermöglicht und auf bestimmten Domain Controllern gehostet wird. |
| Kerberos | Das primäre Authentifizierungsprotokoll in AD, das ein Ticket-basiertes System (TGT und Service Tickets) verwendet, um Passwörter sicher zu handhaben und Netzwerkzugriffe zu authentifizieren. |
| LDAP (Lightweight Directory Access Protocol) | Ein Protokoll zum Abfragen und Ändern von AD-Objekten und Attributen, z. B. zum Finden von Benutzerinformationen oder Gruppenmitgliedern; wird oft für Reconnaissance genutzt. |

### Wichtige Vokabeln

| Vokabel | Bedeutung |
|---------|-----------|
| Object | Ein einzelnes Element in AD, wie ein Benutzer, eine Gruppe, ein Computer oder ein Drucker, definiert durch Attribute wie Name oder Passwort. |
| Attributes | Eigenschaften eines AD-Objekts, z. B. displayName, sAMAccountName (Login-Name), userPassword oder memberOf (zugehörige Gruppen). |
| Domain | Eine logische Gruppierung von Objekten (Benutzer, Computer, Gruppen), die eine gemeinsame Datenbank, Sicherheitsrichtlinien und Vertrauensbeziehungen teilen, z. B. megacorp.local. |
| sAMAccountName | Der Benutzername, der für die Anmeldung in AD verwendet wird, z. B. "jsmith". |
| Ticket Granting Ticket (TGT) | Ein verschlüsseltes, temporäres Identitätsnachweis, das bei der Anmeldung von einem Domain Controller ausgestellt wird und für die Beantragung von Service Tickets verwendet wird. |
| Service Ticket | Ein temporäres Ticket, das von einem Domain Controller für den Zugriff auf eine spezifische Ressource (z. B. ein Dateifreigabe) ausgestellt wird. |
| Schema | Der Bauplan der AD-Datenbank, der die Struktur und Attribute aller Objekte im Forest definiert. |
| Anonymous LDAP Queries | LDAP-Abfragen ohne Authentifizierung, die es Angreifern ermöglichen können, Informationen über das Netzwerk zu sammeln, wenn sie durch Fehlkonfigurationen erlaubt sind. |