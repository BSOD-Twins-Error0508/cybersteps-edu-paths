Welcome to the fascinating world of Windows credentials.
Willkommen in der faszinierenden Welt der Windows-Anmeldeinformationen.

Before our live session, we'll lay the groundwork by understanding how Windows handles user authentication, both for local accounts and within a domain environment.
Vor unserer Live-Session legen wir die Grundlage, indem wir verstehen, wie Windows die Benutzerauthentifizierung handhabt, sowohl für lokale Konten als auch in einer Domänenumgebung.

This foundational knowledge is crucial for understanding how attackers might compromise systems by targeting credentials.
Dieses grundlegende Wissen ist entscheidend, um zu verstehen, wie Angreifer Systeme kompromittieren könnten, indem sie Anmeldeinformationen angreifen.

Understanding Windows Credentials.
Das Verständnis von Windows-Anmeldeinformationen.

At its core, a credential is a piece of information that verifies a user's identity.
Im Kern ist eine Anmeldeinformation ein Stück Information, das die Identität eines Benutzers überprüft.

In Windows, this typically involves a username and a password.
In Windows umfasst das typischerweise einen Benutzernamen und ein Passwort.

However, Windows doesn't store passwords in plain text.
Allerdings speichert Windows Passwörter nicht im Klartext.

Instead, it uses various mechanisms to store and verify them securely, or, in some cases, less securely.
Stattdessen verwendet es verschiedene Mechanismen, um sie sicher zu speichern und zu überprüfen, oder in manchen Fällen weniger sicher.

Local Account Credentials.
Lokale Konto-Anmeldeinformationen.

When you create a user account on a standalone Windows machine, one that is not connected to a larger organizational network or domain, it's called a local account.
Wenn Sie ein Benutzerkonto auf einer eigenständigen Windows-Maschine erstellen, die nicht mit einem größeren organisatorischen Netzwerk oder einer Domäne verbunden ist, wird das ein lokales Konto genannt.

The credentials for these accounts, meaning the username and the password information, are stored directly on that specific computer.
Die Anmeldeinformationen für diese Konten, also der Benutzername und die Passwortinformationen, werden direkt auf diesem spezifischen Computer gespeichert.

The central place where Windows stores this local account information is called the Security Account Manager database.
Der zentrale Ort, an dem Windows diese lokalen Kontoinformationen speichert, heißt Security Account Manager-Datenbank.

Think of the Security Account Manager database as a locked filing cabinet on your computer that holds all the local user profiles and their password secrets.
Stellen Sie sich die Security Account Manager-Datenbank als einen verschlossenen Aktenschrank auf Ihrem Computer vor, der alle lokalen Benutzerprofile und ihre Passwortgeheimnisse enthält.

NTLM Hashes.
NTLM-Hashes.

Windows doesn't store your actual password, for example, MySuperSecretPassword123!, directly in the Security Account Manager database.
Windows speichert Ihr tatsächliches Passwort, zum Beispiel MySuperSecretPassword123!, nicht direkt in der Security Account Manager-Datenbank.

This is a security best practice: if an attacker were to gain access to the Security Account Manager database, they wouldn't immediately see your password.
Das ist eine bewährte Sicherheitsmaßnahme: Wenn ein Angreifer Zugang zur Security Account Manager-Datenbank erhält, würde er Ihr Passwort nicht sofort sehen.

Instead, Windows stores a cryptographic hash of your password.
Stattdessen speichert Windows einen kryptografischen Hash Ihres Passworts.

For local accounts, the specific type of hash commonly used is the NT LAN Manager hash.
Für lokale Konten ist der spezifische Hash-Typ, der häufig verwendet wird, der NT LAN Manager-Hash.

Here's how it works.
So funktioniert es.

When you create a password, Windows calculates its NT LAN Manager hash and stores this hash in the Security Account Manager database.
Wenn Sie ein Passwort erstellen, berechnet Windows seinen NT LAN Manager-Hash und speichert diesen Hash in der Security Account Manager-Datenbank.

When you try to log in, Windows takes the password you type, calculates its NT LAN Manager hash again, and then compares this newly calculated hash to the one stored in the Security Account Manager database.
Wenn Sie sich anmelden möchten, nimmt Windows das eingegebene Passwort, berechnet erneut seinen NT LAN Manager-Hash und vergleicht diesen neu berechneten Hash mit dem in der Security Account Manager-Datenbank gespeicherten.

If the two hashes match, Windows knows you've provided the correct password, and you're authenticated.
Wenn die beiden Hashes übereinstimmen, weiß Windows, dass Sie das richtige Passwort angegeben haben, und Sie werden authentifiziert.

The one-way nature of hashing means it's extremely difficult to reverse the hash to get the original password.
Die Einweg-Natur des Hashings bedeutet, dass es extrem schwierig ist, den Hash umzukehren, um das ursprüngliche Passwort zu erhalten.

However, if an attacker gets hold of the NT LAN Manager hash, they might try to guess the original password by brute-force attacks: Trying every possible combination of characters until they find one that produces the same hash.
Allerdings könnte ein Angreifer, der den NT LAN Manager-Hash in die Hände bekommt, versuchen, das ursprüngliche Passwort durch Brute-Force-Attacken zu erraten: Indem er jede mögliche Kombination von Zeichen ausprobiert, bis er eine findet, die denselben Hash erzeugt.

Dictionary attacks: Using a list of common passwords, a dictionary, and hashing each one to see if it matches the stolen hash.
Dictionary-Attacken: Indem er eine Liste gängiger Passwörter, ein Wörterbuch, verwendet und jedes hashst, um zu sehen, ob es mit dem gestohlenen Hash übereinstimmt.

This is why strong, unique passwords are so important, even with hashing.
Deshalb sind starke, einzigartige Passwörter so wichtig, selbst mit Hashing.

Domain Account Credentials and Active Directory.
Domänen-Konto-Anmeldeinformationen und Active Directory.

Many organizations, from small businesses to large enterprises, use a centralized system to manage their computers, users, and other network resources.
Viele Organisationen, von kleinen Unternehmen bis zu großen Konzernen, verwenden ein zentralisiertes System, um ihre Computer, Benutzer und andere Netzwerkressourcen zu verwalten.

This system is often a domain, and in Windows environments, it's powered by Active Directory.
Dieses System ist oft eine Domäne, und in Windows-Umgebungen wird es von Active Directory betrieben.

Active Directory is like a central phone book and security guard for an entire organization's network.
Active Directory ist wie ein zentrales Telefonbuch und ein Sicherheitswächter für das gesamte Netzwerk einer Organisation.

It's a directory service developed by Microsoft that stores information about almost everything on the network: user accounts, computer accounts, shared printers, applications, and more.
Es handelt sich um einen Directory-Dienst, der von Microsoft entwickelt wurde und Informationen über fast alles im Netzwerk speichert: Benutzerkonten, Computerkonten, freigegebene Drucker, Anwendungen und mehr.

When a computer is joined to an Active Directory domain, it means that computer is now managed by the central Active Directory system.
Wenn ein Computer einer Active Directory-Domäne beitritt, bedeutet das, dass dieser Computer nun vom zentralen Active Directory-System verwaltet wird.

User accounts are typically created and managed centrally within Active Directory, not locally on each individual machine.
Benutzerkonten werden typischerweise zentral in Active Directory erstellt und verwaltet, nicht lokal auf jeder einzelnen Maschine.

This allows a user to log in to any computer joined to the domain using their single domain credential, one username and password for everything.
Das ermöglicht es einem Benutzer, sich an jedem Computer anzumelden, der der Domäne beigetreten ist, mit seiner einzigen Domänen-Anmeldeinformation, also einem Benutzernamen und Passwort für alles.

This simplifies management and provides a consistent experience for users.
Das vereinfacht die Verwaltung und bietet eine konsistente Erfahrung für die Benutzer.

Authentication Protocols in a Domain.
Authentifizierungsprotokolle in einer Domäne.

Within an Active Directory domain, Windows primarily uses two authentication protocols to verify user identities.
Innerhalb einer Active Directory-Domäne verwendet Windows hauptsächlich zwei Authentifizierungsprotokolle, um Benutzeridentitäten zu überprüfen.

NTLM: While Kerberos is preferred, NTLM is still used in domain environments for compatibility with older systems or in specific situations where Kerberos might not be available, for example, authenticating to a server that isn't part of the domain, or when Kerberos fails.
NTLM: Obwohl Kerberos bevorzugt wird, wird NTLM in Domänenumgebungen immer noch für die Kompatibilität mit älteren Systemen oder in spezifischen Situationen verwendet, in denen Kerberos möglicherweise nicht verfügbar ist, zum Beispiel bei der Authentifizierung an einem Server, der nicht Teil der Domäne ist, oder wenn Kerberos fehlschlägt.

Its process is similar to local NTLM authentication but involves communication with a central server called a domain controller.
Der Prozess ist ähnlich wie bei der lokalen NTLM-Authentifizierung, beinhaltet aber die Kommunikation mit einem zentralen Server, der Domain Controller genannt wird.

Kerberos: This is the more modern, preferred, and generally more secure authentication protocol for Active Directory.
Kerberos: Das ist das modernere, bevorzugte und generell sicherere Authentifizierungsprotokoll für Active Directory.

Kerberos uses a system of tickets to prove identity, rather than repeatedly sending password hashes.
Kerberos verwendet ein System von Tickets, um die Identität zu beweisen, anstatt Passwort-Hashes wiederholt zu senden.

It's designed to work securely over potentially insecure networks.
Es ist so konzipiert, dass es sicher über potenziell unsichere Netzwerke funktioniert.

Kerberos Basics.
Kerberos-Grundlagen.

Let's simplify the Kerberos process.
Lassen Sie uns den Kerberos-Prozess vereinfachen.

The Central Authority: Key Distribution Center.
Die zentrale Autorität: Key Distribution Center.

The Key Distribution Center is a service that runs on a domain controller, a server that manages the Active Directory domain.
Das Key Distribution Center ist ein Dienst, der auf einem Domain Controller läuft, einem Server, der die Active Directory-Domäne verwaltet.

It's the ticket master and identity verifier for the entire domain.
Es ist der Ticket-Meister und Identitätsprüfer für die gesamte Domäne.

The Key Distribution Center has two main parts.
Das Key Distribution Center hat zwei Hauptteile.

Authentication Service: Its job is to verify who you are.
Authentication Service: Seine Aufgabe ist es, zu überprüfen, wer Sie sind.

Ticket Granting Service: Its job is to give you tickets to access specific services.
Ticket Granting Service: Seine Aufgabe ist es, Ihnen Tickets zu geben, um auf spezifische Dienste zuzugreifen.

The Authentication Process, Simplified Flow.
Der Authentifizierungsprozess, vereinfachter Ablauf.

Step 1: Get a Master Ticket, Ticket Granting Ticket.
Schritt 1: Holen Sie sich ein Master-Ticket, Ticket Granting Ticket.

When you first log in to a domain-joined computer, your computer sends a request to the Key Distribution Center's Authentication Service.
Wenn Sie sich zum ersten Mal an einem domänenverbundenen Computer anmelden, sendet Ihr Computer eine Anfrage an den Authentication Service des Key Distribution Centers.

This request includes your username and a timestamp, all encrypted using a key derived from your password.
Diese Anfrage enthält Ihren Benutzernamen und einen Zeitstempel, alles verschlüsselt mit einem Schlüssel, der aus Ihrem Passwort abgeleitet ist.

The Authentication Service looks up your username in Active Directory, verifies the encrypted timestamp, proving you know the password without sending the password itself, and if successful, issues you a special ticket called a Ticket Granting Ticket.
Der Authentication Service sucht Ihren Benutzernamen in Active Directory nach, überprüft den verschlüsselten Zeitstempel, was beweist, dass Sie das Passwort kennen, ohne das Passwort selbst zu senden, und bei Erfolg stellt er Ihnen ein spezielles Ticket aus, das Ticket Granting Ticket genannt wird.

Think of the Ticket Granting Ticket as your master ticket or hall pass for the domain.
Stellen Sie sich das Ticket Granting Ticket als Ihr Master-Ticket oder Ihren Hallenpass für die Domäne vor.

It's encrypted so only you and the Key Distribution Center can understand it.
Es ist verschlüsselt, sodass nur Sie und das Key Distribution Center es verstehen können.

Your computer stores this Ticket Granting Ticket.
Ihr Computer speichert dieses Ticket Granting Ticket.

Step 2: Get a Service Ticket.
Schritt 2: Holen Sie sich ein Service-Ticket.

Now, let's say you want to access a shared folder on another server in the domain.
Nehmen wir an, Sie möchten auf einen freigegebenen Ordner auf einem anderen Server in der Domäne zugreifen.

Your computer doesn't send your password again.
Ihr Computer sendet Ihr Passwort nicht erneut.

Instead, it presents your Ticket Granting Ticket to the Key Distribution Center's Ticket Granting Service.
Stattdessen präsentiert er Ihr Ticket Granting Ticket dem Ticket Granting Service des Key Distribution Centers.

The Ticket Granting Service verifies your Ticket Granting Ticket and, if valid, issues you a service ticket specifically for accessing that shared folder on that particular server.
Der Ticket Granting Service überprüft Ihr Ticket Granting Ticket und, wenn es gültig ist, stellt er Ihnen ein Service-Ticket speziell für den Zugriff auf diesen freigegebenen Ordner auf diesem bestimmten Server aus.

This service ticket is like a specific entry ticket for that one service.
Dieses Service-Ticket ist wie ein spezifisches Eintrittsticket für diesen einen Dienst.
