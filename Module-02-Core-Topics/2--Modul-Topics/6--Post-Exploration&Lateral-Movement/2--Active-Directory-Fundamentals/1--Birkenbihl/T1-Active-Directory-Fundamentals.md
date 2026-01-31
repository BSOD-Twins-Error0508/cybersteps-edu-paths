Welcome to the world of Active Directory, the backbone of most corporate networks.
Willkommen in der Welt von Active Directory, dem Rückgrat der meisten Unternehmensnetzwerke.

Understanding Active Directory is not just an IT administration skill; for a cybersecurity professional, it's like understanding the layout of a fortress you're tasked with defending or attacking.
Das Verständnis von Active Directory ist nicht nur eine Fähigkeit für IT-Administratoren; für einen Cybersicherheitsexperten ist es wie das Verständnis des Grundrisses einer Festung, die man verteidigen oder angreifen soll.

Most large organizations run on Active Directory, making it a critical area of focus for security.
Die meisten großen Organisationen basieren auf Active Directory, was es zu einem entscheidenden Schwerpunkt für die Sicherheit macht.

What is a Directory Service?
Was ist ein Directory Service?

At its core, a directory service is a database that keeps track of users and resources in a network.
Im Kern ist ein Directory Service eine Datenbank, die Benutzer und Ressourcen in einem Netzwerk verfolgt.

Think of it as the ultimate address book for a company.
Stellen Sie es sich als das ultimative Adressbuch für ein Unternehmen vor.

Instead of just storing names and phone numbers, it stores information about user accounts, computers, printers, file shares, and security policies.
Statt nur Namen und Telefonnummern zu speichern, speichert es Informationen über Benutzerkonten, Computer, Drucker, Dateifreigaben und Sicherheitsrichtlinien.

It provides a centralized way to manage and secure these resources.
Es bietet eine zentrale Möglichkeit, diese Ressourcen zu verwalten und zu sichern.

Without a directory service, if a company has 100 employees and 100 computers, you would need to create a separate user account for each employee on every single computer they need to access.
Ohne einen Directory Service müssten Sie in einem Unternehmen mit 100 Mitarbeitern und 100 Computern für jeden Mitarbeiter ein separates Benutzerkonto auf jedem Computer erstellen, den sie nutzen müssen.

If someone forgets their password, you'd have to reset it on each machine individually.
Wenn jemand sein Passwort vergisst, müssten Sie es auf jeder Maschine einzeln zurücksetzen.

This is inefficient and a security nightmare.
Das ist ineffizient und ein Sicherheitsalbtraum.

A directory service solves this by creating a single identity for each user that can be used across the entire network.
Ein Directory Service löst das, indem er eine einzige Identität für jeden Benutzer schafft, die im gesamten Netzwerk verwendet werden kann.

Active Directory: The Microsoft Implementation
Active Directory: Die Microsoft-Implementierung

Active Directory is Microsoft's implementation of a directory service.
Active Directory ist Microsofts Implementierung eines Directory Service.

It's a suite of services that runs on Windows Server and is the default choice for domain management in virtually all Windows-based corporate environments.
Es handelt sich um eine Suite von Diensten, die auf Windows Server läuft und die Standardwahl für die Domänenverwaltung in fast allen Windows-basierten Unternehmensumgebungen ist.

Active Directory is responsible for authenticating and authorizing all users and computers within a network, assigning and enforcing security policies, and managing all other network resources.
Active Directory ist verantwortlich für die Authentifizierung und Autorisierung aller Benutzer und Computer in einem Netzwerk, das Zuweisen und Durchsetzen von Sicherheitsrichtlinien sowie das Verwalten aller anderen Netzwerkressourcen.

Core Components of Active Directory
Kernkomponenten von Active Directory

To understand Active Directory, you need to know its fundamental building blocks.
Um Active Directory zu verstehen, müssen Sie seine grundlegenden Bausteine kennen.

Objects.
Objekte.

An object is the most basic element in Active Directory.
Ein Objekt ist das grundlegendste Element in Active Directory.

An object represents a single entity, such as a user, a group, a computer, or a printer.
Ein Objekt repräsentiert eine einzelne Entität, wie einen Benutzer, eine Gruppe, einen Computer oder einen Drucker.

Each object has a set of attributes that define its characteristics.
Jedes Objekt hat eine Reihe von Attributen, die seine Eigenschaften definieren.

For example, a user object has attributes like displayName, sAMAccountName (the login name), userPassword, and memberOf (which groups the user belongs to).
Zum Beispiel hat ein Benutzerobjekt Attribute wie displayName, sAMAccountName (den Anmeldenamen), userPassword und memberOf (welchen Gruppen der Benutzer angehört).

Domain Controller.
Domain Controller.

A Domain Controller is a server that runs the Active Directory Domain Services role.
Ein Domain Controller ist ein Server, der die Active Directory Domain Services-Rolle ausführt.

It is the gatekeeper of the domain.
Er ist der Torwächter der Domäne.

Its primary responsibilities are:
Seine Hauptaufgaben sind:

Storing the Directory Database: It holds a copy of the Active Directory database for its domain.
Speichern der Directory-Datenbank: Er enthält eine Kopie der Active Directory-Datenbank für seine Domäne.

This database contains all the objects and their attributes.
Diese Datenbank enthält alle Objekte und ihre Attribute.

Authentication: When a user logs in, the Domain Controller verifies their credentials (username and password).
Authentifizierung: Wenn ein Benutzer sich anmeldet, überprüft der Domain Controller ihre Anmeldedaten (Benutzername und Passwort).

Authorization: After authentication, the Domain Controller determines what resources the user is allowed to access.
Autorisierung: Nach der Authentifizierung bestimmt der Domain Controller, auf welche Ressourcen der Benutzer zugreifen darf.

Enforcing Policies: It enforces security policies, such as password complexity requirements and account lockout rules.
Durchsetzung von Richtlinien: Er setzt Sicherheitsrichtlinien durch, wie Anforderungen an die Passwortkomplexität und Regeln für die Kontosperrung.

In any serious network, there will be at least two Domain Controllers for redundancy.
In jedem seriösen Netzwerk gibt es mindestens zwei Domain Controller für Redundanz.

If one fails, the other can take over.
Wenn einer ausfällt, kann der andere übernehmen.

Domains.
Domänen.

A domain is a logical grouping of objects (users, computers, groups) that share a common directory database, security policies, and trust relationships with other domains.
Eine Domäne ist eine logische Gruppierung von Objekten (Benutzer, Computer, Gruppen), die eine gemeinsame Directory-Datenbank, Sicherheitsrichtlinien und Vertrauensbeziehungen zu anderen Domänen teilen.

For example, a company might have a domain called megacorp.local.
Zum Beispiel könnte ein Unternehmen eine Domäne namens megacorp.local haben.

All users and computers belonging to that company would be part of this domain.
Alle Benutzer und Computer, die zu diesem Unternehmen gehören, wären Teil dieser Domäne.

Organizational Units.
Organisational Units.

An Organizational Unit is a container object within a domain that you can use to organize other objects.
Eine Organizational Unit ist ein Container-Objekt innerhalb einer Domäne, das Sie verwenden können, um andere Objekte zu organisieren.

Organizational Units are used to delegate administrative control and apply specific policies.
Organizational Units werden verwendet, um administrative Kontrolle zu delegieren und spezifische Richtlinien anzuwenden.

For instance, you could create separate Organizational Units for the Sales, HR, and IT departments.
Zum Beispiel könnten Sie separate Organizational Units für die Abteilungen Sales, HR und IT erstellen.

This allows you to assign a specific IT staff member to manage only the users and computers in the Sales Organizational Unit, without giving them control over the entire domain.
Das ermöglicht es Ihnen, einem bestimmten IT-Mitarbeiter zuzuweisen, nur die Benutzer und Computer in der Sales Organizational Unit zu verwalten, ohne ihm Kontrolle über die gesamte Domäne zu geben.

Think about it.
Denken Sie darüber nach.

What is the key difference between a Group and an Organizational Unit?
Was ist der wesentliche Unterschied zwischen einer Gruppe und einer Organizational Unit?

A user can be a member of multiple groups, but an object can only reside in one Organizational Unit at a time.
Ein Benutzer kann Mitglied mehrerer Gruppen sein, aber ein Objekt kann nur in einer Organizational Unit gleichzeitig sein.

Why is this distinction important for managing security?
Warum ist diese Unterscheidung wichtig für die Verwaltung der Sicherheit?

Scaling Active Directory: Trees, Forests, and Trusts
Skalierung von Active Directory: Trees, Forests und Trusts

As organizations grow, their network structure becomes more complex.
Wenn Organisationen wachsen, wird ihre Netzwerkstruktur komplexer.

Active Directory scales to accommodate this growth through a hierarchical structure.
Active Directory skaliert, um dieses Wachstum durch eine hierarchische Struktur aufzunehmen.

Tree: A tree is a collection of one or more domains grouped in a hierarchical structure, sharing a contiguous namespace.
Tree: Ein Tree ist eine Sammlung von einer oder mehreren Domänen, die in einer hierarchischen Struktur gruppiert sind und einen kontinuierlichen Namespace teilen.

For example, you could have the root domain megacorp.local, and then child domains like sales.megacorp.local and emea.megacorp.local.
Zum Beispiel könnten Sie die Root-Domäne megacorp.local haben und dann Child-Domänen wie sales.megacorp.local und emea.megacorp.local.

Forest: A forest is the highest-level container, comprising one or more trees.
Forest: Ein Forest ist der höchste Container, der aus einem oder mehreren Trees besteht.

All domains in a forest share a common schema (the blueprint for the Active Directory database) and trust each other.
Alle Domänen in einem Forest teilen ein gemeinsames Schema (den Bauplan für die Active Directory-Datenbank) und vertrauen einander.

Even a single domain is considered a forest.
Selbst eine einzelne Domäne wird als Forest betrachtet.

