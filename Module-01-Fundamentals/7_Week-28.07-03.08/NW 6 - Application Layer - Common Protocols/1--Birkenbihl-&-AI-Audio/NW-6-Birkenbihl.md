Welcome! In previous lessons, we started exploring the Application Layer, the layer where user-facing applications interact with the network. Willkommen! In vorherigen Lektionen haben wir begonnen, die Anwendungsschicht zu erkunden, die Schicht, in der benutzerseitige Anwendungen mit dem Netzwerk interagieren.

Today, we'll dive into several other essential application layer protocols that you'll frequently encounter in networking and cybersecurity. Heute werden wir uns mit mehreren anderen wesentlichen Anwendungsschicht-Protokollen befassen, denen Sie häufig im Networking und in der Cybersicherheit begegnen werden.

Understanding their purpose and basic mechanics is crucial. Das Verständnis ihres Zwecks und ihrer grundlegenden Mechanik ist entscheidend.

We'll cover email protocols: SMTP, POP3, IMAP. File transfer: FTP. Remote access: Telnet, SSH, RDP. Wir werden E-Mail-Protokolle behandeln: SMTP, POP3, IMAP. Dateiübertragung: FTP. Fernzugriff: Telnet, SSH, RDP.

Email Protocols: Sending and Receiving Messages. E-Mail-Protokolle: Nachrichten senden und empfangen.

Email seems simple, but behind the scenes, several protocols work together. E-Mail scheint einfach zu sein, aber hinter den Kulissen arbeiten mehrere Protokolle zusammen.

SMTP, Simple Mail Transfer Protocol. SMTP, Simple Mail Transfer Protocol.

Purpose: Primarily used for sending email messages from an email client, like Apple Mail or Outlook, to an email server, and also for transferring email between mail servers. Zweck: Wird hauptsächlich zum Senden von E-Mail-Nachrichten von einem E-Mail-Client, wie Apple Mail oder Outlook, zu einem E-Mail-Server verwendet, und auch zur Übertragung von E-Mails zwischen Mail-Servern.

How it works: When you hit "send," your client connects to your outgoing mail server, for example smtp.yourprovider.com, using SMTP. So funktioniert es: Wenn Sie auf "Senden" klicken, verbindet sich Ihr Client mit Ihrem ausgehenden Mail-Server, zum Beispiel smtp.yourprovider.com, unter Verwendung von SMTP.

This typically happens on port 25, the standard, often unencrypted port, or port 587, the standard for client submission, usually requires encryption like TLS or STARTTLS, or port 465, an older standard, uses implicit TLS or SSL. Dies geschieht typischerweise auf Port 25, dem Standard, oft unverschlüsselten Port, oder Port 587, dem Standard für Client-Übermittlung, der normalerweise Verschlüsselung wie TLS oder STARTTLS erfordert, oder Port 465, einem älteren Standard, der implizites TLS oder SSL verwendet.

The server then relays the message towards the recipient's mail server, potentially involving several hops between SMTP servers. Der Server leitet dann die Nachricht zum Mail-Server des Empfängers weiter, was möglicherweise mehrere Sprünge zwischen SMTP-Servern beinhaltet.

Key characteristic: SMTP is a "push" protocol. It pushes messages from the client to the server and between servers. Hauptmerkmal: SMTP ist ein "Push"-Protokoll. Es schiebt Nachrichten vom Client zum Server und zwischen Servern.

It's generally not used for retrieving email from a server. Es wird im Allgemeinen nicht zum Abrufen von E-Mails von einem Server verwendet.

Security: Basic SMTP on port 25 is often unencrypted, meaning email content and credentials could be intercepted. Sicherheit: Basis-SMTP auf Port 25 ist oft unverschlüsselt, was bedeutet, dass E-Mail-Inhalte und Anmeldedaten abgefangen werden könnten.

Modern implementations use encryption, TLS or SSL, via STARTTLS on port 587 or implicit TLS on port 465. Moderne Implementierungen verwenden Verschlüsselung, TLS oder SSL, über STARTTLS auf Port 587 oder implizites TLS auf Port 465.

POP3, Post Office Protocol version 3. POP3, Post Office Protocol Version 3.

Purpose: Used for retrieving email messages from a mail server to an email client. Zweck: Wird zum Abrufen von E-Mail-Nachrichten von einem Mail-Server zu einem E-Mail-Client verwendet.

How it works: Your email client connects to the incoming mail server, for example pop.yourprovider.com, using POP3. So funktioniert es: Ihr E-Mail-Client verbindet sich mit dem eingehenden Mail-Server, zum Beispiel pop.yourprovider.com, unter Verwendung von POP3.

This typically happens on port 110, unencrypted, or port 995, encrypted with TLS or SSL. Dies geschieht typischerweise auf Port 110, unverschlüsselt, oder Port 995, verschlüsselt mit TLS oder SSL.

POP3 usually downloads emails to your local device and removes them from the server, though configuration options sometimes allow leaving copies. POP3 lädt normalerweise E-Mails auf Ihr lokales Gerät herunter und entfernt sie vom Server, obwohl Konfigurationsoptionen manchmal das Belassen von Kopien ermöglichen.

Key characteristic: Designed for offline access. Download once, read locally. Hauptmerkmal: Entwickelt für Offline-Zugriff. Einmal herunterladen, lokal lesen.

This means emails aren't typically synchronized across multiple devices. Dies bedeutet, dass E-Mails normalerweise nicht über mehrere Geräte hinweg synchronisiert werden.

If you read an email on your phone using POP3, it won't appear read on your laptop. Wenn Sie eine E-Mail auf Ihrem Telefon mit POP3 lesen, wird sie auf Ihrem Laptop nicht als gelesen angezeigt.

Security: Basic POP3 on port 110 is unencrypted. Port 995 provides encryption. Sicherheit: Basis-POP3 auf Port 110 ist unverschlüsselt. Port 995 bietet Verschlüsselung.

IMAP, Internet Message Access Protocol. IMAP, Internet Message Access Protocol.

Purpose: Also used for retrieving email messages from a mail server, but with more features than POP3. Zweck: Wird auch zum Abrufen von E-Mail-Nachrichten von einem Mail-Server verwendet, aber mit mehr Funktionen als POP3.

How it works: Your client connects to the incoming mail server, for example imap.yourprovider.com, using IMAP. So funktioniert es: Ihr Client verbindet sich mit dem eingehenden Mail-Server, zum Beispiel imap.yourprovider.com, unter Verwendung von IMAP.

This typically happens on port 143, unencrypted or STARTTLS, or port 993, encrypted with TLS or SSL. Dies geschieht typischerweise auf Port 143, unverschlüsselt oder STARTTLS, oder Port 993, verschlüsselt mit TLS oder SSL.

Unlike POP3, IMAP generally keeps emails on the server. Im Gegensatz zu POP3 behält IMAP im Allgemeinen E-Mails auf dem Server.

Your client accesses and manages the emails directly on the server. Ihr Client greift auf die E-Mails direkt auf dem Server zu und verwaltet sie.

Key characteristic: Designed for online and multi-device access. Hauptmerkmal: Entwickelt für Online- und Multi-Geräte-Zugriff.

Changes made on one device, reading, deleting, moving to folders, are reflected across all devices connected to the same account because the "master copy" stays on the server. Änderungen, die auf einem Gerät vorgenommen werden, wie Lesen, Löschen, Verschieben in Ordner, werden auf allen Geräten, die mit demselben Konto verbunden sind, widergespiegelt, weil die "Masterkopie" auf dem Server bleibt.

It supports server-side folders. Es unterstützt serverseitige Ordner.

Security: Basic IMAP on port 143 can be unencrypted, but STARTTLS can add encryption. Port 993 provides encryption from the start. Sicherheit: Basis-IMAP auf Port 143 kann unverschlüsselt sein, aber STARTTLS kann Verschlüsselung hinzufügen. Port 993 bietet Verschlüsselung von Anfang an.

Think about it. Denken Sie darüber nach.

Why might a company block standard port 25 for outgoing email from employee laptops and require them to use port 587 instead? Warum könnte ein Unternehmen den Standard-Port 25 für ausgehende E-Mails von Mitarbeiter-Laptops blockieren und verlangen, dass sie stattdessen Port 587 verwenden?

If you want to access your email seamlessly from your laptop, phone, and tablet, keeping everything synchronized, which protocol would you choose for retrieving mail: POP3 or IMAP? Why? Wenn Sie nahtlos von Ihrem Laptop, Telefon und Tablet auf Ihre E-Mails zugreifen möchten und alles synchronisiert halten möchten, welches Protokoll würden Sie zum Abrufen von E-Mails wählen: POP3 oder IMAP? Warum?

File Transfer Protocol, FTP. File Transfer Protocol, FTP.

Purpose: Used for transferring files between a client and a server over a network. It's one of the oldest internet protocols. Zweck: Wird zur Übertragung von Dateien zwischen einem Client und einem Server über ein Netzwerk verwendet. Es ist eines der ältesten Internetprotokolle.

How it works: FTP uses two separate TCP connections. So funktioniert es: FTP verwendet zwei separate TCP-Verbindungen.

First, the control connection on port 21. This is used for sending commands, like USER, PASS, LIST, RETR, STOR, and receiving responses. Erstens, die Steuerverbindung auf Port 21. Diese wird zum Senden von Befehlen verwendet, wie USER, PASS, LIST, RETR, STOR, und zum Empfangen von Antworten.

This connection stays open for the duration of the session. Diese Verbindung bleibt für die Dauer der Sitzung offen.

Second, the data connection on a variable port. This is used for the actual transfer of file data or directory listings. Zweitens, die Datenverbindung auf einem variablen Port. Diese wird für die tatsächliche Übertragung von Dateidaten oder Verzeichnislisten verwendet.

The port used for this connection depends on whether the mode is active or passive. Der für diese Verbindung verwendete Port hängt davon ab, ob der Modus aktiv oder passiv ist.

Active mode: The client tells the server which port it's listening on, and the server initiates the data connection back to the client. Aktiver Modus: Der Client teilt dem Server mit, auf welchem Port er lauscht, und der Server initiiert die Datenverbindung zurück zum Client.

This can be problematic with firewalls on the client-side. Dies kann problematisch sein mit Firewalls auf der Client-Seite.

Passive mode: The client asks the server to listen on a specific port, and the client initiates the data connection to the server on that port. Passiver Modus: Der Client fordert den Server auf, auf einem bestimmten Port zu lauschen, und der Client initiiert die Datenverbindung zum Server auf diesem Port.

This is generally more firewall-friendly. Dies ist im Allgemeinen firewall-freundlicher.

Key characteristic: Designed purely for file transfer. It includes commands for listing directories, creating directories, deleting files, and so on. Hauptmerkmal: Entwickelt ausschließlich für Dateiübertragung. Es beinhaltet Befehle zum Auflisten von Verzeichnissen, Erstellen von Verzeichnissen, Löschen von Dateien und so weiter.

Security: Standard FTP on port 21 is insecure. Both credentials, username and password, and file data are sent in clear text, making them easily interceptable. Sicherheit: Standard-FTP auf Port 21 ist unsicher. Sowohl Anmeldedaten, Benutzername und Passwort, als auch Dateidaten werden im Klartext gesendet, was sie leicht abfangbar macht.

Secure alternatives include FTPS, FTP Secure, and SFTP, SSH File Transfer Protocol. Sichere Alternativen sind FTPS, FTP Secure, und SFTP, SSH File Transfer Protocol.

FTPS adds TLS or SSL encryption to FTP. It can be explicit, where the client connects on port 21 and requests encryption with AUTH TLS, or implicit, where the client connects directly using TLS on port 990. FTPS fügt TLS- oder SSL-Verschlüsselung zu FTP hinzu. Es kann explizit sein, wobei der Client sich auf Port 21 verbindet und Verschlüsselung mit AUTH TLS anfordert, oder implizit, wobei der Client sich direkt mit TLS auf Port 990 verbindet.

SFTP is often confused with FTPS, but it's a completely different protocol that runs over SSH, usually on port 22. SFTP wird oft mit FTPS verwechselt, aber es ist ein völlig anderes Protokoll, das über SSH läuft, normalerweise auf Port 22.

It provides file transfer capabilities within a secure SSH tunnel. It only uses a single connection. Es bietet Dateiübertragungsfähigkeiten innerhalb eines sicheren SSH-Tunnels. Es verwendet nur eine einzige Verbindung.

Try it yourself. Probieren Sie es selbst aus.

Most operating systems have a built-in command-line FTP client. Die meisten Betriebssysteme haben einen eingebauten Befehlszeilen-FTP-Client.

Open your Terminal on macOS, search for Terminal in Spotlight, and try connecting to a public anonymous FTP server, one that doesn't require a specific username or password. Öffnen Sie Ihr Terminal auf macOS, suchen Sie nach Terminal in Spotlight, und versuchen Sie, sich mit einem öffentlichen anonymen FTP-Server zu verbinden, einem, der keinen spezifischen Benutzernamen oder Passwort erfordert.

A common one is ftp.dlptest.com. Username: dlpuser, Password: rNrKYTX9g7z3RgJRmxWuGHbeu. Ein gängiger ist ftp.dlptest.com. Benutzername: dlpuser, Passwort: rNrKYTX9g7z3RgJRmxWuGHbeu.

Make sure you have Homebrew installed at https://brew.sh/. Stellen Sie sicher, dass Sie Homebrew installiert haben unter https://brew.sh/.

Install ftp service on macOS: brew install tnftp. Installieren Sie den FTP-Dienst auf macOS: brew install tnftp.

Type: ftp ftp.dlptest.com. Tippen Sie: ftp ftp.dlptest.com.

When prompted for Name, enter: dlpuser. Wenn Sie nach dem Namen gefragt werden, geben Sie ein: dlpuser.

When prompted for Password, enter: rNrKYTX9g7z3RgJRmxWuGHbeu. Wenn Sie nach dem Passwort gefragt werden, geben Sie ein: rNrKYTX9g7z3RgJRmxWuGHbeu.

Once logged in, type ls or dir to list files. Sobald Sie angemeldet sind, tippen Sie ls oder dir, um Dateien aufzulisten.

Type pwd to see the current directory on the server. Tippen Sie pwd, um das aktuelle Verzeichnis auf dem Server zu sehen.

Type quit to exit. Tippen Sie quit, um zu beenden.

Remote Access Protocols. Fernzugriffsprotokolle.

These protocols allow you to connect to and control another computer over a network. Diese Protokolle ermöglichen es Ihnen, sich mit einem anderen Computer über ein Netzwerk zu verbinden und ihn zu steuern.

Telnet. Telnet.

Purpose: Provides a bidirectional, interactive text-based communication facility using a virtual terminal connection. Zweck: Bietet eine bidirektionale, interaktive textbasierte Kommunikationseinrichtung unter Verwendung einer virtuellen Terminalverbindung.

Essentially, it allows you to log in to a remote machine and run commands as if you were sitting in front of it. Im Wesentlichen ermöglicht es Ihnen, sich bei einem entfernten Rechner anzumelden und Befehle auszuführen, als ob Sie davor sitzen würden.

How it works: Telnet client connects to a Telnet server, typically on TCP port 23. So funktioniert es: Telnet-Client verbindet sich mit einem Telnet-Server, typischerweise auf TCP-Port 23.

It establishes a connection and then simply relays keystrokes from the client to the server and displays output from the server back to the client. Es stellt eine Verbindung her und leitet dann einfach Tastenanschläge vom Client zum Server weiter und zeigt die Ausgabe vom Server zurück zum Client an.

Key characteristic: Very simple, widely implemented in the past. Hauptmerkmal: Sehr einfach, in der Vergangenheit weit verbreitet implementiert.

Security: Telnet is highly insecure. All data, including usernames and passwords, is transmitted in clear text. Sicherheit: Telnet ist hochgradig unsicher. Alle Daten, einschließlich Benutzernamen und Passwörtern, werden im Klartext übertragen.

Anyone monitoring the network can capture your credentials and see everything you type and all the output. Jeder, der das Netzwerk überwacht, kann Ihre Anmeldedaten erfassen und alles sehen, was Sie tippen und die gesamte Ausgabe.

Avoid using Telnet for logins whenever possible. Vermeiden Sie die Verwendung von Telnet für Anmeldungen wann immer möglich.

Its main modern use is sometimes for quick banner grabbing or testing if a specific port is open on a remote server, but even that should be done cautiously. Seine hauptsächliche moderne Verwendung ist manchmal für schnelles Banner-Grabbing oder Testen, ob ein bestimmter Port auf einem entfernten Server offen ist, aber selbst das sollte vorsichtig gemacht werden.

SSH, Secure Shell. SSH, Secure Shell.

Purpose: Provides a secure way to access a remote computer. Zweck: Bietet einen sicheren Weg, auf einen entfernten Computer zuzugreifen.

It allows secure remote login, command execution, and other secure network services, like SFTP and port forwarding, over an insecure network. Es ermöglicht sichere Fernzugriffe, Befehlsausführung und andere sichere Netzwerkdienste, wie SFTP und Port-Weiterleitung, über ein unsicheres Netzwerk.

How it works: SSH client connects to an SSH server, typically on TCP port 22. So funktioniert es: SSH-Client verbindet sich mit einem SSH-Server, typischerweise auf TCP-Port 22.

It establishes an encrypted connection before any authentication or data transfer occurs. Es stellt eine verschlüsselte Verbindung her, bevor irgendeine Authentifizierung oder Datenübertragung stattfindet.

It uses public-key cryptography to authenticate the server, preventing man-in-the-middle attacks, and allows for various client authentication methods, passwords, public or private key pairs. Es verwendet Public-Key-Kryptographie, um den Server zu authentifizieren, was Man-in-the-Middle-Angriffe verhindert, und ermöglicht verschiedene Client-Authentifizierungsmethoden, Passwörter, öffentliche oder private Schlüsselpaare.

Key characteristic: Encryption and authentication are built-in. It replaces insecure tools like Telnet and rlogin. Hauptmerkmal: Verschlüsselung und Authentifizierung sind eingebaut. Es ersetzt unsichere Tools wie Telnet und rlogin.

Security: Designed with security as a primary goal. All traffic, logins, commands, output, is encrypted. Sicherheit: Mit Sicherheit als primäres Ziel entworfen. Aller Verkehr, Anmeldungen, Befehle, Ausgabe, ist verschlüsselt.

Think about it. Denken Sie darüber nach.

You need to log into a remote Linux server to update some configuration files. Should you use Telnet or SSH? Sie müssen sich bei einem entfernten Linux-Server anmelden, um einige Konfigurationsdateien zu aktualisieren. Sollten Sie Telnet oder SSH verwenden?

Why is the other choice a bad idea? Warum ist die andere Wahl eine schlechte Idee?

RDP, Remote Desktop Protocol. RDP, Remote Desktop Protocol.

Purpose: A proprietary protocol developed by Microsoft, allowing a user to connect to another computer over a network with a full graphical interface. Zweck: Ein proprietäres Protokoll, das von Microsoft entwickelt wurde und es einem Benutzer ermöglicht, sich mit einem anderen Computer über ein Netzwerk mit einer vollständigen grafischen Benutzeroberfläche zu verbinden.

It makes the remote machine's desktop appear on your local machine. Es lässt den Desktop des entfernten Rechners auf Ihrem lokalen Rechner erscheinen.

How it works: An RDP client connects to an RDP server, typically a Windows machine, though servers exist for other operating systems, usually on TCP port 3389. So funktioniert es: Ein RDP-Client verbindet sich mit einem RDP-Server, typischerweise einem Windows-Rechner, obwohl Server für andere Betriebssysteme existieren, normalerweise auf TCP-Port 3389.

It transmits keyboard input, mouse movements, and screen updates over the network. Modern RDP uses encryption. Es überträgt Tastatureingaben, Mausbewegungen und Bildschirmaktualisierungen über das Netzwerk. Modernes RDP verwendet Verschlüsselung.

Key characteristic: Provides graphical remote access, unlike the text-based access of Telnet or SSH. Hauptmerkmal: Bietet grafischen Fernzugriff, im Gegensatz zum textbasierten Zugriff von Telnet oder SSH.

Commonly used for remote administration of Windows servers and accessing remote desktops. Wird häufig zur Fernverwaltung von Windows-Servern und zum Zugriff auf entfernte Desktops verwendet.

Security: While modern RDP includes encryption, older versions had vulnerabilities. Sicherheit: Während modernes RDP Verschlüsselung beinhaltet, hatten ältere Versionen Schwachstellen.

Security also depends heavily on strong authentication, passwords, multi-factor authentication, and ensuring only authorized users can connect. Die Sicherheit hängt auch stark von starker Authentifizierung ab, Passwörtern, Mehr-Faktor-Authentifizierung und der Sicherstellung, dass nur autorisierte Benutzer sich verbinden können.

Exposing RDP directly to the internet, port 3389 open on the firewall, is a significant security risk and a common target for attackers. Das direkte Aussetzen von RDP ans Internet, Port 3389 offen in der Firewall, ist ein erhebliches Sicherheitsrisiko und ein häufiges Ziel für Angreifer.

Network Level Authentication, or NLA, adds a layer of security by requiring authentication before a full session is established. Network Level Authentication, oder NLA, fügt eine Sicherheitsschicht hinzu, indem sie Authentifizierung erfordert, bevor eine vollständige Sitzung eingerichtet wird.

Summary Table. Zusammenfassungstabelle.

Protocol SMTP: Default ports 25, 587 with TLS, 465 with SSL. Purpose: Sending email. Security: Often clear on port 25. Key feature: Pushes email to and between servers. Protokoll SMTP: Standard-Ports 25, 587 mit TLS, 465 mit SSL. Zweck: E-Mails senden. Sicherheit: Oft unverschlüsselt auf Port 25. Hauptmerkmal: Schiebt E-Mails zu und zwischen Servern.

Protocol POP3: Default ports 110, 995 with SSL or TLS. Purpose: Retrieving email. Security: Often clear on port 110. Key feature: Downloads email, often removes from server. Protokoll POP3: Standard-Ports 110, 995 mit SSL oder TLS. Zweck: E-Mails abrufen. Sicherheit: Oft unverschlüsselt auf Port 110. Hauptmerkmal: Lädt E-Mails herunter, entfernt sie oft vom Server.

Protocol IMAP: Default ports 143, 993 with SSL or TLS. Purpose: Retrieving and managing email. Security: Often clear on port 143. Key feature: Manages email on server, syncs across devices. Protokoll IMAP: Standard-Ports 143, 993 mit SSL oder TLS. Zweck: E-Mails abrufen und verwalten. Sicherheit: Oft unverschlüsselt auf Port 143. Hauptmerkmal: Verwaltet E-Mails auf dem Server, synchronisiert über Geräte.

Protocol FTP: Default port 21 for control, data varies. Purpose: File transfer. Security: Insecure. Key feature: Separate control and data channels, clear text. Protokoll FTP: Standard-Port 21 für Steuerung, Daten variieren. Zweck: Dateiübertragung. Sicherheit: Unsicher. Hauptmerkmal: Separate Steuer- und Datenkanäle, Klartext.

Protocol Telnet: Default port 23. Purpose: Remote text login. Security: Insecure. Key feature: Simple, clear text. Protokoll Telnet: Standard-Port 23. Zweck: Fernzugriff mit Text. Sicherheit: Unsicher. Hauptmerkmal: Einfach, Klartext.

Protocol SSH: Default port 22. Purpose: Secure remote login and execution. Security: Secure. Key feature: Encrypted, authenticated. Protokoll SSH: Standard-Port 22. Zweck: Sicherer Fernzugriff und Ausführung. Sicherheit: Sicher. Hauptmerkmal: Verschlüsselt, authentifiziert.

Protocol RDP: Default port 3389. Purpose: Remote graphical desktop. Security: Encrypted in modern versions. Key feature: Graphical interface, Windows-centric. Protokoll RDP: Standard-Port 3389. Zweck: Grafischer Fernzugriff auf Desktop. Sicherheit: Verschlüsselt in modernen Versionen. Hauptmerkmal: Grafische Benutzeroberfläche, Windows-zentriert.

Understanding these protocols, their purposes, default ports, and especially their security implications is vital for network administration and cybersecurity. Das Verständnis dieser Protokolle, ihrer Zwecke, Standard-Ports und besonders ihrer Sicherheitsimplikationen ist entscheidend für Netzwerkverwaltung und Cybersicherheit.

You'll use this knowledge to configure systems, troubleshoot network issues, and analyze network traffic for potential threats. Sie werden dieses Wissen verwenden, um Systeme zu konfigurieren, Netzwerkprobleme zu beheben und Netzwerkverkehr auf potenzielle Bedrohungen zu analysieren.

The slides for the live session can be viewed here. Try not to peek before class, spoilers inside! Die Folien für die Live-Sitzung können hier angesehen werden. Versuchen Sie nicht, vor dem Unterricht zu spähen, Spoiler enthalten!