Part Two: 
Step 3: Access the Service.
Schritt 3: Greifen Sie auf den Dienst zu.

Your computer then presents this service ticket directly to the server hosting the shared folder.
Ihr Computer präsentiert dieses Service-Ticket direkt dem Server, der den freigegebenen Ordner hostet.

The server verifies the service ticket, it trusts tickets issued by the Key Distribution Center, and if valid, it grants you access to the shared folder.
Der Server überprüft das Service-Ticket, er vertraut Tickets, die vom Key Distribution Center ausgestellt wurden, und bei Gültigkeit gewährt er Ihnen Zugriff auf den freigegebenen Ordner.

The key advantage of Kerberos is that your actual password, or even its hash, is only used once at the very beginning to get your Ticket Granting Ticket.
Der wichtigste Vorteil von Kerberos ist, dass Ihr tatsächliches Passwort, oder sogar sein Hash, nur einmal am Anfang verwendet wird, um Ihr Ticket Granting Ticket zu erhalten.

After that, only tickets are exchanged, making it much harder for attackers to intercept your credentials on the network.
Danach werden nur Tickets ausgetauscht, was es für Angreifer viel schwieriger macht, Ihre Anmeldeinformationen im Netzwerk abzufangen.

The Threat of Credential Dumping.
Die Bedrohung durch Credential Dumping.

Despite these authentication mechanisms, attackers constantly seek ways to bypass them.
Trotz dieser Authentifizierungsmechanismen suchen Angreifer ständig nach Wegen, sie zu umgehen.

Credential dumping is a critical technique in a cyberattack where an attacker extracts account login information, like password hashes, Kerberos tickets, or sometimes even clear-text passwords, from a computer's memory or storage.
Credential Dumping ist eine entscheidende Technik in einem Cyberangriff, bei der ein Angreifer Konto-Anmeldeinformationen extrahiert, wie Passwort-Hashes, Kerberos-Tickets oder manchmal sogar Klartext-Passwörter, aus dem Speicher oder dem Speicherort eines Computers.

Why is this so dangerous?
Warum ist das so gefährlich?

Because if an attacker gains administrative access to a system, they can often run tools that dump these credentials.
Weil ein Angreifer, der administrativen Zugriff auf ein System erhält, oft Tools ausführen kann, die diese Anmeldeinformationen dumpen.

Once dumped, these credentials become powerful tools for the attacker.
Sobald sie gedumpt sind, werden diese Anmeldeinformationen zu mächtigen Werkzeugen für den Angreifer.

Pass-the-Hash attacks: If an attacker gets an NTLM hash, they don't need to crack it to find the original password.
Pass-the-Hash-Attacken: Wenn ein Angreifer einen NTLM-Hash erhält, muss er ihn nicht knacken, um das ursprüngliche Passwort zu finden.

They can use the hash directly to authenticate to other systems that accept NTLM authentication.
Sie können den Hash direkt verwenden, um sich an anderen Systemen zu authentifizieren, die NTLM-Authentifizierung akzeptieren.

It's like having a key that works without knowing what the key looks like.
Es ist wie ein Schlüssel, der funktioniert, ohne zu wissen, wie der Schlüssel aussieht.

Pass-the-Ticket attacks: Similar to Pass-the-Hash, if an attacker steals a Kerberos Ticket Granting Ticket or service ticket, they can use it to impersonate the legitimate user and access services without ever knowing the password.
Pass-the-Ticket-Attacken: Ähnlich wie Pass-the-Hash, wenn ein Angreifer ein Kerberos Ticket Granting Ticket oder ein Service-Ticket stiehlt, kann er es verwenden, um den legitimen Benutzer zu imitieren und auf Dienste zuzugreifen, ohne je das Passwort zu kennen.

Brute-forcing or dictionary attacks: As mentioned, dumped hashes can be fed into specialized software to try and recover the original plaintext passwords.
Brute-Forcing oder Dictionary-Attacken: Wie erwähnt, können gedumpte Hashes in spezialisierte Software eingespeist werden, um zu versuchen, die ursprünglichen Klartext-Passwörter wiederherzustellen.

Lateral Movement: This is a common goal.
Lateral Movement: Das ist ein häufiges Ziel.

By using compromised credentials, an attacker can move from the initial compromised system to other systems within the network, expanding their control and searching for more valuable targets.
Indem er kompromittierte Anmeldeinformationen verwendet, kann ein Angreifer vom anfänglich kompromittierten System zu anderen Systemen im Netzwerk wechseln, seine Kontrolle erweitern und nach wertvolleren Zielen suchen.

Common locations where credentials or their components might be dumped from include.
Häufige Orte, von denen Anmeldeinformationen oder ihre Komponenten gedumpt werden könnten, umfassen.

Local Security Authority Subsystem Service: This is a crucial Windows process, lsass.exe, that runs in memory.
Local Security Authority Subsystem Service: Das ist ein entscheidender Windows-Prozess, lsass.exe, der im Speicher läuft.

It's responsible for enforcing security policies, handling user logins, and storing sensitive information, including password hashes and active Kerberos tickets for currently logged-on users.
Er ist verantwortlich für die Durchsetzung von Sicherheitsrichtlinien, die Handhabung von Benutzeranmeldungen und die Speicherung sensibler Informationen, einschließlich Passwort-Hashes und aktiver Kerberos-Tickets für derzeit angemeldete Benutzer.

Because it holds such critical data, it's a primary target for credential dumping tools.
Weil er solch kritische Daten enthält, ist er ein primäres Ziel für Credential-Dumping-Tools.

Security Account Manager database: As discussed, this database stores local account NTLM hashes.
Security Account Manager-Datenbank: Wie besprochen, speichert diese Datenbank lokale Konto-NTLM-Hashes.

Attackers with administrative access can often extract these.
Angreifer mit administrativem Zugriff können diese oft extrahieren.

Registry: Certain parts of the Windows Registry, a central hierarchical database for Windows settings, can contain cached credentials or other sensitive information that attackers might target.
Registry: Bestimmte Teile der Windows-Registry, einer zentralen hierarchischen Datenbank für Windows-Einstellungen, können zwischengespeicherte Anmeldeinformationen oder andere sensible Informationen enthalten, die Angreifer anvisieren könnten.

Mimikatz: The Go-To Tool for Credential Dumping.
Mimikatz: Das Go-To-Tool für Credential Dumping.

When discussing credential dumping, it's impossible to ignore Mimikatz.
Bei der Diskussion über Credential Dumping ist es unmöglich, Mimikatz zu ignorieren.

This is an open-source post-exploitation tool widely used by both ethical hackers, for testing defenses, and malicious actors.
Das ist ein Open-Source-Post-Exploitation-Tool, das weit verbreitet von ethischen Hackern, zur Testung von Abwehrmaßnahmen, und bösartigen Akteuren verwendet wird.

It was originally created as a proof-of-concept to highlight how Windows handles authentication data in memory, but its effectiveness quickly made it a standard tool in many attack chains.
Es wurde ursprünglich als Proof-of-Concept erstellt, um zu zeigen, wie Windows Authentifizierungsdaten im Speicher handhabt, aber seine Wirksamkeit machte es schnell zu einem Standardtool in vielen Angriffsketten.

Mimikatz's primary power lies in its ability to extract various forms of authentication credentials directly from the memory of Windows operating systems.
Die primäre Stärke von Mimikatz liegt in seiner Fähigkeit, verschiedene Formen von Authentifizierungsanmeldeinformationen direkt aus dem Speicher von Windows-Betriebssystemen zu extrahieren.

It specifically targets the Local Security Authority Subsystem Service process to retrieve.
Es zielt speziell auf den Local Security Authority Subsystem Service-Prozess ab, um abzurufen.

Plaintext passwords: In certain configurations or older systems, Mimikatz can sometimes recover the actual password.
Klartext-Passwörter: In bestimmten Konfigurationen oder älteren Systemen kann Mimikatz manchmal das tatsächliche Passwort wiederherstellen.

NTLM hashes: These are the hashed versions of passwords, which can then be used in Pass-the-Hash attacks to authenticate to other systems without needing the original password.
NTLM-Hashes: Das sind die gehashten Versionen von Passwörtern, die dann in Pass-the-Hash-Attacken verwendet werden können, um sich an anderen Systemen zu authentifizieren, ohne das ursprüngliche Passwort zu benötigen.

Kerberos tickets: Crucially, Mimikatz can extract Ticket Granting Tickets and Service Tickets.
Kerberos-Tickets: Entscheidend ist, dass Mimikatz Ticket Granting Tickets und Service Tickets extrahieren kann.

These tickets are then used in Pass-the-Ticket attacks, allowing an attacker to impersonate the legitimate user and access resources within an Active Directory domain.
Diese Tickets werden dann in Pass-the-Ticket-Attacken verwendet, was einem Angreifer ermöglicht, den legitimen Benutzer zu imitieren und auf Ressourcen in einer Active Directory-Domäne zuzugreifen.

PINs and other sensitive information.
PINs und andere sensible Informationen.

Mimikatz is significant because it doesn't necessarily exploit a traditional software vulnerability.
Mimikatz ist bedeutsam, weil es nicht unbedingt eine traditionelle Software-Schwachstelle ausnutzt.

Instead, it leverages how Windows is designed to store and manage credentials in memory.
Stattdessen nutzt es aus, wie Windows konzipiert ist, um Anmeldeinformationen im Speicher zu speichern und zu verwalten.

This makes it a very effective tool for.
Das macht es zu einem sehr effektiven Tool für.

Lateral Movement: Moving from one compromised machine to other systems within the network using stolen credentials.
Lateral Movement: Das Bewegen von einer kompromittierten Maschine zu anderen Systemen im Netzwerk unter Verwendung gestohlener Anmeldeinformationen.

Privilege Escalation: Gaining higher levels of access on a system or within the domain.
Privilege Escalation: Das Erhalten höherer Zugriffsstufen auf einem System oder in der Domäne.

Persistence: Establishing long-term access, sometimes by forging powerful Golden Tickets that grant extensive domain control.
Persistence: Das Etablieren langfristigen Zugriffs, manchmal durch das Fälschen mächtiger Golden Tickets, die umfassende Domänen-Kontrolle gewähren.

We will cover this in later sessions.
Das werden wir in späteren Sessions behandeln.

Understanding these concepts will help you grasp the why behind many cybersecurity attacks and defenses, and why protecting credentials is a cornerstone of cybersecurity.
Das Verständnis dieser Konzepte hilft Ihnen, das Warum hinter vielen Cybersicherheitsangriffen und -verteidigungen zu erfassen, und warum der Schutz von Anmeldeinformationen ein Eckpfeiler der Cybersicherheit ist.

Think about it.
Denken Sie darüber nach.

Why would an attacker prefer to dump a Kerberos Ticket Granting Ticket over an NTLM hash if they had the choice?
Warum würde ein Angreifer es vorziehen, ein Kerberos Ticket Granting Ticket zu dumpen statt eines NTLM-Hashs, wenn er die Wahl hätte?

Consider the implications for accessing multiple services and the typical lifespan of each.
Berücksichtigen Sie die Implikationen für den Zugriff auf mehrere Dienste und die typische Lebensdauer von jedem.

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
