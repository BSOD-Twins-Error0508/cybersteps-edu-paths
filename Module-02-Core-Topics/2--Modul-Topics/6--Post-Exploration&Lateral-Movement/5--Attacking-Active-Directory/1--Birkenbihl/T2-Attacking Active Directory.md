Part Two:

How it works.
So funktioniert es.

An attacker compromises a system and performs credential dumping to extract NTLM hashes from memory.
Ein Angreifer kompromittiert ein System und führt Credential Dumping durch, um NTLM-Hashes aus dem Speicher zu extrahieren.

Using a tool, the attacker injects a captured NTLM hash into their current session or uses it to initiate a new session to a remote system.
Mit einem Tool injiziert der Angreifer einen erfassten NTLM-Hash in seine aktuelle Session oder verwendet ihn, um eine neue Session zu einem remote System zu initiieren.

The remote system authenticates the attacker using the hash.
Das remote System authentifiziert den Angreifer mit dem Hash.

Think about it.
Denken Sie darüber nach.

Pass-the-Hash is a classic lateral movement technique.
Pass-the-Hash ist eine klassische Lateral-Movement-Technik.

Given that it relies on hashes in memory, what are some modern Windows security features or configurations that aim to mitigate the risk of credential dumping and subsequent Pass-the-Hash attacks?
Angesichts dass es auf Hashes im Speicher angewiesen ist, was sind einige moderne Windows-Sicherheitsfeatures oder Konfigurationen, die darauf abzielen, das Risiko von Credential Dumping und nachfolgenden Pass-the-Hash-Angriffen zu mindern?

Privilege Escalation.
Privilege Escalation.

After gaining initial access and moving laterally, the next goal is to escalate privileges from a standard user to a high-powered account, like a service account or administrator.
Nach dem Erlangen initialen Zugriffs und Lateral Movement ist das nächste Ziel, Privilegien von einem Standardbenutzer zu einem hochprivilegierten Konto zu eskalieren, wie einem Service-Account oder Administrator.

Kerberoasting.
Kerberoasting.

Kerberoasting specifically targets service accounts that have a Service Principal Name registered in Active Directory.
Kerberoasting zielt speziell auf Service-Accounts ab, die einen Service Principal Name in Active Directory registriert haben.

These accounts are used by services (like SQL Server or web applications) and their tickets are encrypted with the service account's NTLM hash.
Diese Konten werden von Diensten verwendet (wie SQL Server oder Web-Anwendungen) und ihre Tickets sind mit dem NTLM-Hash des Service-Accounts verschlüsselt.

An attacker, as any authenticated user, can request a service ticket for these Service Principal Names.
Ein Angreifer, als jeder authentifizierte Benutzer, kann ein Service-Ticket für diese Service Principal Names anfordern.

The Domain Controller encrypts this ticket with the service account's NTLM hash.
Der Domain Controller verschlüsselt dieses Ticket mit dem NTLM-Hash des Service-Accounts.

The attacker then captures this encrypted ticket and attempts to crack the hash offline.
Der Angreifer erfasst dann dieses verschlüsselte Ticket und versucht, den Hash offline zu knacken.

This is highly effective if service accounts use weak or default passwords.
Das ist hoch effektiv, wenn Service-Accounts schwache oder Standard-Passwörter verwenden.

How it works.
So funktioniert es.

An attacker, as any authenticated user, requests a Kerberos service ticket (TGS) for a known Service Principal Name.
Ein Angreifer, als jeder authentifizierte Benutzer, fordert ein Kerberos-Service-Ticket (TGS) für einen bekannten Service Principal Name an.

The Domain Controller issues the TGS, encrypted with the NTLM hash of the service account.
Der Domain Controller stellt das TGS aus, verschlüsselt mit dem NTLM-Hash des Service-Accounts.

The attacker intercepts this encrypted TGS.
Der Angreifer fängt dieses verschlüsselte TGS ab.

Offline, the attacker cracks the NTLM hash to recover the plaintext password.
Offline knackt der Angreifer den NTLM-Hash, um das Klartext-Passwort wiederherzustellen.

Persistence.
Persistence.

Once high-level privileges are gained, the final stage is establishing persistence.
Sobald hohe Privilegien erlangt sind, ist die finale Stufe das Etablieren von Persistence.

This ensures an attacker can maintain access even if their initial foothold is lost or passwords are changed.
Das stellt sicher, dass ein Angreifer den Zugriff aufrechterhalten kann, selbst wenn ihr initialer Fußhalt verloren geht oder Passwörter geändert werden.

Golden Ticket Attack: Ultimate Persistence.
Golden Ticket Attack: Ultimative Persistence.

The Golden Ticket attack is a highly impactful post-compromise technique that allows an attacker to forge a Kerberos Ticket Granting Ticket.
Der Golden Ticket Attack ist eine hoch wirkungsvolle Post-Compromise-Technik, die einem Angreifer ermöglicht, ein Kerberos Ticket Granting Ticket zu fälschen.

By forging a Ticket Granting Ticket, an attacker can impersonate any user in the domain, including domain administrators, and gain unlimited access to any resource in the domain, even without knowing their passwords.
Durch das Fälschen eines Ticket Granting Tickets kann ein Angreifer jeden Benutzer in der Domäne imitieren, einschließlich Domain-Administratoren, und unbegrenzten Zugriff auf jede Ressource in der Domäne erlangen, sogar ohne ihre Passwörter zu kennen.

This attack provides powerful persistence due to the ability to set the ticket's validity for an extended period.
Dieser Angriff bietet mächtige Persistence aufgrund der Möglichkeit, die Gültigkeit des Tickets für eine erweiterte Periode zu setzen.

This attack requires the NTLM hash of the krbtgt account.
Dieser Angriff erfordert den NTLM-Hash des krbtgt-Accounts.

The krbtgt account is a special service account in Active Directory responsible for encrypting and signing all Kerberos tickets.
Der krbtgt-Account ist ein spezieller Service-Account in Active Directory, verantwortlich für das Verschlüsseln und Signieren aller Kerberos-Tickets.

Compromising this account's hash (typically by compromising a Domain Controller) is the ultimate prize for an attacker in an Active Directory environment.
Das Kompromittieren dieses Account-Hashs (typischerweise durch Kompromittierung eines Domain Controllers) ist der ultimative Preis für einen Angreifer in einer Active Directory-Umgebung.

How it works.
So funktioniert es.

An attacker obtains the NTLM hash of the krbtgt account (for example, by compromising a Domain Controller).
Ein Angreifer erhält den NTLM-Hash des krbtgt-Accounts (zum Beispiel durch Kompromittierung eines Domain Controllers).

Using this hash, the attacker crafts a forged Ticket Granting Ticket.
Mit diesem Hash erstellt der Angreifer ein gefälschtes Ticket Granting Ticket.

This forged ticket can be set to be valid for an extended period and can grant arbitrary group memberships (for example, Domain Admins).
Dieses gefälschte Ticket kann für eine erweiterte Periode gültig gesetzt werden und kann beliebige Gruppenmitgliedschaften gewähren (zum Beispiel Domain Admins).

The attacker injects this forged Ticket Granting Ticket into their current session.
Der Angreifer injiziert dieses gefälschte Ticket Granting Ticket in seine aktuelle Session.

The attacker can now access any resource in the domain as any user, with any privileges they desire, for the duration of the ticket's validity.
Der Angreifer kann nun auf jede Ressource in der Domäne als jeder Benutzer zugreifen, mit allen Privilegien, die er wünscht, für die Dauer der Gültigkeit des Tickets.

Silver Ticket Attack: Targeted Persistence.
Silver Ticket Attack: Gezielte Persistence.

The Silver Ticket attack is another form of credential forgery that provides persistence on a specific service on a specific server.
Der Silver Ticket Attack ist eine weitere Form der Anmeldeinformationsfälschung, die Persistence auf einem spezifischen Dienst auf einem spezifischen Server bietet.

Unlike a Golden Ticket (which grants domain-wide access), a Silver Ticket targets a Service Ticket (TGS) rather than the initial Ticket Granting Ticket (TGT).
Im Gegensatz zu einem Golden Ticket (das domänenweiten Zugriff gewährt), zielt ein Silver Ticket auf ein Service Ticket (TGS) ab statt auf das initiale Ticket Granting Ticket (TGT).

This attack requires the NTLM hash of the service account that runs the targeted service.
Dieser Angriff erfordert den NTLM-Hash des Service-Accounts, der den zielgerichteten Dienst ausführt.

The advantage of a Silver Ticket for persistence is that it doesn't require interaction with the Domain Controller for authentication to the specific service, making it harder to detect.
Der Vorteil eines Silver Tickets für Persistence ist, dass es keine Interaktion mit dem Domain Controller für die Authentifizierung zum spezifischen Dienst erfordert, was es schwieriger zu erkennen macht.

How it works.
So funktioniert es.

An attacker compromises a system and obtains the NTLM hash of a service account (for example, a SQL service account, like a web server service account) that runs a specific service on a target server.
Ein Angreifer kompromittiert ein System und erhält den NTLM-Hash eines Service-Accounts (zum Beispiel ein SQL-Service-Account, wie ein Web-Server-Service-Account), der einen spezifischen Dienst auf einem Zielserver ausführt.

Using this service account's NTLM hash, the attacker crafts a forged TGS for the specific service.
Mit dem NTLM-Hash dieses Service-Accounts erstellt der Angreifer ein gefälschtes TGS für den spezifischen Dienst.

The attacker injects this forged TGS into their current session.
Der Angreifer injiziert dieses gefälschte TGS in seine aktuelle Session.

The attacker can now access the targeted service on the specific server, bypassing the Domain Controller for that particular service authentication.
Der Angreifer kann nun auf den zielgerichteten Dienst auf dem spezifischen Server zugreifen und umgeht den Domain Controller für diese besondere Dienst-Authentifizierung.

Group Policy Objects: Configuration, Exploitation, and Persistence.
Group Policy Objects: Konfiguration, Exploitation und Persistence.

Group Policy Objects are a fundamental component of Active Directory that allow administrators to centrally manage and configure operating systems, applications, and user settings across an enterprise.
Group Policy Objects sind eine fundamentale Komponente von Active Directory, die Administratoren ermöglicht, Betriebssysteme, Anwendungen und Benutzereinstellungen zentral über ein Unternehmen zu managen und zu konfigurieren.

Group Policy Objects are incredibly powerful and can enforce security settings, deploy software, manage user rights, and much more.
Group Policy Objects sind unglaublich mächtig und können Sicherheitsrichtlinien durchsetzen, Software bereitstellen, Benutzerrechte managen und vieles mehr.

While Group Policy Objects are essential for security and management, misconfigurations or inherent design elements can introduce vulnerabilities that attackers can exploit for privilege escalation, and especially for persistence.
Während Group Policy Objects für Sicherheit und Management essenziell sind, können Fehlkonfigurationen oder inhärente Designelemente Vulnerabilitäten einführen, die Angreifer für Privilege Escalation ausnutzen können, und besonders für Persistence.

Common GPO Exploitation Scenarios.
Gängige Exploitation-Szenarien für Group Policy Objects.

Weak Permissions on Group Policy Objects: If attackers gain write access to a Group Policy Object, they can modify it to deploy malicious scripts, change security settings, or grant themselves elevated privileges.
Schwache Berechtigungen auf Group Policy Objects: Wenn Angreifer Schreibzugriff auf ein Group Policy Object erlangen, können sie es modifizieren, um bösartige Skripte bereitzustellen, Sicherheitsrichtlinien zu ändern oder sich selbst erhöhte Privilegien zu gewähren.

Delegated GPO Management: Overly permissive delegation of Group Policy Object management can allow lower-privileged users to create or modify Group Policy Objects, leading to compromise.
Delegierte GPO-Verwaltung: Übermäßig permissive Delegation der Group Policy Object-Verwaltung kann niedrig privilegierten Benutzern erlauben, Group Policy Objects zu erstellen oder zu modifizieren, was zu Kompromittierung führt.

Immediate Tasks/Startup Scripts: Group Policy Objects can be used to deploy immediate tasks or startup scripts that run with elevated privileges on target machines.
Immediate Tasks/Startup Scripts: Group Policy Objects können verwendet werden, um immediate Tasks oder Startup-Skripte bereitzustellen, die mit erhöhten Privilegien auf Zielmaschinen laufen.

If an attacker can modify such a Group Policy Object, they can execute arbitrary code upon system startup or user logon, providing robust persistence.
Wenn ein Angreifer ein solches Group Policy Object modifizieren kann, kann er beliebigen Code bei Systemstart oder Benutzeranmeldung ausführen, was robuste Persistence bietet.

Restricted Groups: Misconfigured Restricted Groups policies can inadvertently grant administrative privileges to unintended users, leading to privilege escalation.
Restricted Groups: Fehlkonfigurierte Restricted Groups-Richtlinien können unbeabsichtigt administrative Privilegien an unbeabsichtigte Benutzer gewähren, was zu Privilege Escalation führt.

Password Policy Weaknesses: While not a direct exploitation of Group Policy Objects, Group Policy Objects define password policies.
Passwortrichtlinie-Schwächen: Obwohl keine direkte Exploitation von Group Policy Objects, definieren Group Policy Objects Passwortrichtlinien.

Weak password policies (for example, short passwords, no complexity requirements) make credential-based attacks easier.
Schwache Passwortrichtlinien (zum Beispiel kurze Passwörter, keine Komplexitätsanforderungen) machen credential-basierte Angriffe einfacher.

Think about it.
Denken Sie darüber nach.

The Golden Ticket attack offers both privilege escalation and persistence.
Der Golden Ticket Attack bietet sowohl Privilege Escalation als auch Persistence.

From a defender's perspective, what makes detecting and remediating a Golden Ticket attack particularly challenging compared to other credential-based attacks?
Aus Sicht eines Verteidigers, was macht die Erkennung und Behebung eines Golden Ticket Attacks besonders herausfordernd im Vergleich zu anderen credential-basierten Angriffen?