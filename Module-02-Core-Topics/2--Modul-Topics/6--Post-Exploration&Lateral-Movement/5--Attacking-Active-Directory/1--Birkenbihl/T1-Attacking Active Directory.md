This pre-class material is designed to prepare you for understanding various techniques used to attack Active Directory environments.
Dieses Vorbereitungsmaterial soll Sie auf das Verständnis verschiedener Techniken vorbereiten, die verwendet werden, um Active Directory-Umgebungen anzugreifen.

We will explore how attackers move from initial access to gaining significant control and establishing persistence within a domain.
Wir werden erkunden, wie Angreifer vom initialen Zugriff zu erheblicher Kontrolle und dem Etablieren von Persistenz in einer Domäne übergehen.

This knowledge is crucial for both offensive (penetration testing) and defensive (security monitoring) cybersecurity roles.
Dieses Wissen ist entscheidend für offensive (Penetrationstests) und defensive (Sicherheitsüberwachung) Rollen in der Cybersicherheit.

We will build upon your existing knowledge of Active Directory fundamentals, user management, and credential handling.
Wir bauen auf Ihrem bestehenden Wissen über Active Directory-Grundlagen, Benutzerverwaltung und Umgang mit Anmeldeinformationen auf.

Active Directory Attack Lifecycle Overview.
Überblick über den Angriffslebenszyklus von Active Directory.

Attacking Active Directory follows a similar structure to a general cybersecurity attack.
Der Angriff auf Active Directory folgt einer ähnlichen Struktur wie ein allgemeiner Cybersicherheitsangriff.

Initial Access/Breaching: Gaining a foothold in the network, often leading to the compromise of initial credentials.
Initialer Zugriff/Durchbruch: Den Fuß in das Netzwerk setzen, oft führend zur Kompromittierung initialer Anmeldeinformationen.

Enumeration: Discovering information about the Active Directory environment, including users, groups, computers, and their relationships.
Enumeration: Entdecken von Informationen über die Active Directory-Umgebung, einschließlich Benutzer, Gruppen, Computer und ihrer Beziehungen.

Credential Harvesting/Dumping: Extracting credentials (hashes, plaintext passwords, tickets) from compromised systems.
Credential Harvesting/Dumping: Extrahieren von Anmeldeinformationen (Hashes, Klartext-Passwörter, Tickets) aus kompromittierten Systemen.

Lateral Movement: Using compromised credentials or techniques to move from one system to another within the network.
Lateral Movement: Verwenden kompromittierter Anmeldeinformationen oder Techniken, um von einem System zu einem anderen im Netzwerk zu wechseln.

Privilege Escalation/Exploitation: Gaining higher privileges, often leading to Domain Administrator access.
Privilege Escalation/Exploitation: Erlangen höherer Privilegien, oft führend zu Domain Administrator-Zugriff.

Persistence: Establishing long-term access to the compromised environment.
Persistence: Etablieren langfristigen Zugriffs auf die kompromittierte Umgebung.

In this preparation, we will focus on key techniques that span these phases, particularly emphasizing enumeration, exploitation, and persistence.
In dieser Vorbereitung konzentrieren wir uns auf Schlüsseltechniken, die diese Phasen umspannen, mit besonderem Schwerpunkt auf Enumeration, Exploitation und Persistence.

Initial Credential Acquisition (Breaching Active Directory).
Initiale Erwerbung von Anmeldeinformationen (Durchbruch in Active Directory).

Often, the first step in breaching Active Directory involves acquiring credentials.
Oft beinhaltet der erste Schritt beim Durchbrechen von Active Directory das Erwerben von Anmeldeinformationen.

One common Kerberos-based attack is particularly effective for this: AS-REP Roasting.
Ein gängiger Kerberos-basierter Angriff ist dafür besonders effektiv: AS-REP Roasting.

AS-REP Roasting targets user accounts with the Do not require Kerberos preauthentication flag enabled.
AS-REP Roasting zielt auf Benutzerkonten ab, bei denen das Flag Do not require Kerberos preauthentication aktiviert ist.

When preauthentication is disabled, the Domain Controller will issue a Ticket Granting Ticket to any user who requests it, without verifying their identity.
Wenn Preauthentication deaktiviert ist, stellt der Domain Controller ein Ticket Granting Ticket an jeden Benutzer aus, der es anfordert, ohne ihre Identität zu überprüfen.

This Ticket Granting Ticket is encrypted with the target user's NTLM hash.
Dieses Ticket Granting Ticket ist mit dem NTLM-Hash des Zielbenutzers verschlüsselt.

An attacker can request this Ticket Granting Ticket, capture it, and then attempt to crack the user's NTLM hash offline.
Ein Angreifer kann dieses Ticket Granting Ticket anfordern, es erfassen und dann versuchen, den NTLM-Hash des Benutzers offline zu knacken.

This is a common method to get initial user credentials if such misconfigurations exist.
Das ist eine gängige Methode, um initiale Benutzeranmeldeinformationen zu erhalten, wenn solche Fehlkonfigurationen existieren.

How it works.
So funktioniert es.

An attacker identifies user accounts with the Do not require Kerberos preauthentication flag set.
Ein Angreifer identifiziert Benutzerkonten, bei denen das Flag Do not require Kerberos preauthentication gesetzt ist.

The attacker sends an AS-REQ (Authentication Service Request) for one of these target user accounts.
Der Angreifer sendet eine AS-REQ (Authentication Service Request) für eines dieser Zielbenutzerkonten.

The Domain Controller responds with an AS-REP (Authentication Service Response) containing a Ticket Granting Ticket for that user, encrypted with the target user's NTLM hash, without requiring preauthentication.
Der Domain Controller antwortet mit einer AS-REP (Authentication Service Response), die ein Ticket Granting Ticket für diesen Benutzer enthält, verschlüsselt mit dem NTLM-Hash des Zielbenutzers, ohne Preauthentication zu erfordern.

The attacker captures this AS-REP and attempts to crack the NTLM hash offline.
Der Angreifer erfasst diese AS-REP und versucht, den NTLM-Hash offline zu knacken.

Think about it.
Denken Sie darüber nach.

Some legacy applications require Do not require Kerberos preauthentication to be disabled.
Einige Legacy-Anwendungen erfordern, dass Do not require Kerberos preauthentication deaktiviert wird.

From a security perspective, what are the primary risks associated with this setting, and what alternative solutions might an organization consider to mitigate these risks while maintaining application compatibility?
Aus Sicherheits-Sicht, was sind die primären Risiken, die mit dieser Einstellung verbunden sind, und welche alternativen Lösungen könnte eine Organisation in Betracht ziehen, um diese Risiken zu mindern, während die Anwendungskompatibilität erhalten bleibt?

Enumerating Active Directory: Finding Attack Paths.
Enumeration von Active Directory: Finden von Angriffspfaden.

Once initial access is gained, a critical phase is enumeration – understanding the Active Directory environment to identify potential attack paths.
Sobald initialer Zugriff erlangt ist, ist eine kritische Phase die Enumeration – das Verständnis der Active Directory-Umgebung, um potenzielle Angriffspfade zu identifizieren.

This involves mapping relationships between users, groups, computers, and their permissions.
Das beinhaltet das Kartieren von Beziehungen zwischen Benutzern, Gruppen, Computern und ihren Berechtigungen.

BloodHound: Graphing Active Directory Relationships.
BloodHound: Graphische Darstellung von Active Directory-Beziehungen.

BloodHound is an indispensable open-source tool for Active Directory enumeration.
BloodHound ist ein unverzichtbares Open-Source-Tool für die Active Directory-Enumeration.

It uses graph theory to reveal complex, often unintended, relationships within an Active Directory environment that can lead to privilege escalation.
Es verwendet Graphentheorie, um komplexe, oft unbeabsichtigte Beziehungen in einer Active Directory-Umgebung aufzudecken, die zu Privilege Escalation führen können.

BloodHound collects data about users, groups, computers, trusts, and Group Policy Objects, then visualizes these relationships in a Neo4j graph database.
BloodHound sammelt Daten über Benutzer, Gruppen, Computer, Trusts und Group Policy Objects und visualisiert diese Beziehungen in einer Neo4j-Graph-Datenbank.

Key Concepts in BloodHound.
Schlüsselkonzepte in BloodHound.

Nodes: Represent Active Directory objects (users, computers, groups, Group Policy Objects, Organizational Units, domains).
Nodes: Repräsentieren Active Directory-Objekte (Benutzer, Computer, Gruppen, Group Policy Objects, Organizational Units, Domänen).

Edges: Represent relationships between these objects, such as:
Edges: Repräsentieren Beziehungen zwischen diesen Objekten, wie:

MemberOf: A user or group is a member of another group.
MemberOf: Ein Benutzer oder eine Gruppe ist Mitglied einer anderen Gruppe.

AdminTo: A user or group has administrative privileges over a computer.
AdminTo: Ein Benutzer oder eine Gruppe hat administrative Privilegien über einen Computer.

HasSession: A user has an active session on a computer.
HasSession: Ein Benutzer hat eine aktive Session auf einem Computer.

CanRDP: A user can remotely connect to a computer via Remote Desktop Protocol.
CanRDP: Ein Benutzer kann sich remote über Remote Desktop Protocol mit einem Computer verbinden.

GPLink: A Group Policy Object is linked to an Organizational Unit, domain, or site.
GPLink: Ein Group Policy Object ist mit einer Organizational Unit, Domäne oder Site verknüpft.

Attack Paths: BloodHound can automatically identify and visualize sequences of these relationships that an attacker could exploit to gain control over a target, often leading to Domain Admin privileges.
Attack Paths: BloodHound kann automatisch Sequenzen dieser Beziehungen identifizieren und visualisieren, die ein Angreifer ausnutzen könnte, um Kontrolle über ein Ziel zu erlangen, oft führend zu Domain Admin-Privilegien.

This helps prioritize vulnerabilities.
Das hilft, Vulnerabilitäten zu priorisieren.

Try it yourself.
Probieren Sie es selbst aus.

You've collected BloodHound data from a target domain.
Sie haben BloodHound-Daten von einer Zieldomäne gesammelt.

You're looking for a quick path to a high-privileged user.
Sie suchen nach einem schnellen Pfad zu einem hochprivilegierten Benutzer.

What specific BloodHound query might you run to identify users who can directly administer a Domain Controller?
Welche spezifische BloodHound-Abfrage könnten Sie ausführen, um Benutzer zu identifizieren, die direkt einen Domain Controller administrieren können?

Try it yourself.
Probieren Sie es selbst aus.

Consider a scenario where you've gained a foothold in a network as a low-privileged user.
Betrachten Sie ein Szenario, in dem Sie als niedrig privilegierter Benutzer einen Fußhalt in einem Netzwerk erlangt haben.

You want to find potential targets for Kerberoasting (our next topic).
Sie wollen potenzielle Ziele für Kerberoasting finden (unser nächstes Thema).

What specific Active Directory attribute would you be looking for on user or computer objects to identify potential service accounts?
Welches spezifische Active Directory-Attribut würden Sie auf Benutzer- oder Computer-Objekten suchen, um potenzielle Service-Accounts zu identifizieren?

Credential Harvesting and Lateral Movement.
Credential Harvesting und Lateral Movement.

After enumeration, attackers often focus on credential harvesting from compromised machines and using those credentials for lateral movement to other systems.
Nach der Enumeration konzentrieren sich Angreifer oft auf Credential Harvesting von kompromittierten Maschinen und verwenden diese Anmeldeinformationen für Lateral Movement zu anderen Systemen.

Pass-the-Hash - A Core Lateral Movement Technique.
Pass-the-Hash - Eine Kerntechnik für Lateral Movement.

As a reminder from previous lessons, Pass-the-Hash is a powerful technique where an attacker authenticates to a remote system or service using a user's NTLM hash instead of the plaintext password.
Als Erinnerung aus vorherigen Lektionen ist Pass-the-Hash eine mächtige Technik, bei der ein Angreifer sich an einem remote System oder Dienst authentifiziert, indem er den NTLM-Hash eines Benutzers statt des Klartext-Passworts verwendet.

This is possible because Windows operating systems often store password hashes (specifically NTLM hashes) in memory for authentication purposes.
Das ist möglich, weil Windows-Betriebssysteme oft Passwort-Hashes (spezifisch NTLM-Hashes) im Speicher für Authentifizierungszwecke speichern.

If an attacker can extract these hashes from a compromised system (a process often called credential dumping, for example, from the LSASS process), they can reuse them to authenticate to other systems within the network that trust the same hash.
Wenn ein Angreifer diese Hashes aus einem kompromittierten System extrahieren kann (ein Prozess, der oft Credential Dumping genannt wird, zum Beispiel aus dem LSASS-Prozess), können sie sie wiederverwenden, um sich an anderen Systemen im Netzwerk zu authentifizieren, die demselben Hash vertrauen.

The plaintext password is never revealed, making this a stealthy and effective lateral movement technique.
Das Klartext-Passwort wird nie enthüllt, was das zu einer stealthy und effektiven Lateral-Movement-Technik macht.
