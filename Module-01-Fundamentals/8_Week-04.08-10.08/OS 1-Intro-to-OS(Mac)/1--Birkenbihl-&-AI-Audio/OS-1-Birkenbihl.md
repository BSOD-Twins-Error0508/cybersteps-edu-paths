Welcome to your first look at operating systems! This preparatory material will guide you through the fundamental concepts of what an operating system is, what it does, and why it is a critical component of every computing device, with particular emphasis on macOS, which you will be using. Understanding the operating system is fundamental to cybersecurity, as it often forms the basis for both defensive measures and attack vectors.

Willkommen zu Ihrem ersten Blick auf Betriebssysteme! Dieses Vorbereitungsmaterial führt Sie durch die grundlegenden Konzepte, was ein Betriebssystem ist, was es tut und warum es eine kritische Komponente jedes Computergeräts ist, mit besonderem Schwerpunkt auf macOS, das Sie verwenden werden. Das Verständnis des Betriebssystems ist für die Cybersicherheit von grundlegender Bedeutung, da es oft die Grundlage für Abwehrmaßnahmen und Angriffsvektoren bildet.

What is an operating system?

Was ist ein Betriebssystem?

Imagine a bustling city. For the city to function, it needs infrastructure like roads, power lines, water supply, traffic management, law enforcement, and a way for various services such as shops, offices, and residences to operate and interact. An operating system, or OS, plays a similar role for your computer. It is sophisticated software that acts as the central coordinator and manager of all the hardware and software resources of your computer. Without an operating system, your computer would just be a collection of electronic components unable to perform any useful tasks.

Stellen Sie sich eine belebte Stadt vor. Damit die Stadt funktioniert, braucht sie Infrastruktur wie Straßen, Stromleitungen, Wasserversorgung, Verkehrsmanagement, Strafverfolgung und eine Möglichkeit für verschiedene Dienste wie Geschäfte, Büros und Wohnungen, zu arbeiten und zu interagieren. Ein Betriebssystem spielt eine ähnliche Rolle für Ihren Computer. Es ist eine hochentwickelte Software, die als zentraler Koordinator und Verwalter aller Hardware- und Softwareressourcen Ihres Computers fungiert. Ohne ein Betriebssystem wäre Ihr Computer nur eine Ansammlung elektronischer Komponenten, die keine nützlichen Aufgaben erfüllen könnten.

The primary goals of an operating system are twofold. First, user convenience. The computer system should be user-friendly and accessible. The operating system provides a layer of abstraction, meaning it hides the incredibly complex, low-level workings of the hardware. Instead of knowing how to directly control the processor or write data to a specific sector on a hard drive, you interact with intuitive interfaces like icons, menus, or simple commands.

Die Hauptziele eines Betriebssystems sind zweierlei. Erstens, Komfort für den Benutzer. Das Computersystem soll benutzerfreundlich und zugänglich sein. Das Betriebssystem bietet eine Abstraktionsebene, das heißt, es verbirgt die unglaublich komplexe, niedrigstufige Funktionsweise der Hardware. Anstatt zu wissen, wie man den Prozessor direkt ansteuert oder Daten in einen bestimmten Sektor auf einer Festplatte schreibt, interagiert man mit intuitiven Schnittstellen wie Symbolen, Menüs oder einfachen Befehlen.

Second, operational efficiency. The computer system's resources, such as the central processing unit or CPU, random access memory or RAM, storage devices like hard drives and solid state drives, and input output peripherals like keyboard, mouse, printer, and network card, are managed optimally and fairly. This ensures that multiple programs can run smoothly and resources are allocated where they are most needed.

Zweitens, Effizienz des Betriebs. Die Ressourcen des Computersystems, wie die Zentraleinheit, der Arbeitsspeicher, die Speichergeräte wie Festplatten und Solid-State-Laufwerke und die Peripheriegeräte für die Ein- und Ausgabe wie Tastatur, Maus, Drucker und Netzwerkkarte, werden optimal und fair verwaltet. Dadurch wird sichergestellt, dass mehrere Programme reibungslos ausgeführt werden können und die Ressourcen dort zugewiesen werden, wo sie am meisten benötigt werden.

The core functions of an operating system include hardware abstraction. As mentioned, the operating system acts as an intermediary. Application programmers can write software that runs on different hardware configurations without having to adapt their code for each individual device. The operating system handles the translation through components like device drivers.

Zu den Kernfunktionen eines Betriebssystems gehört die Hardwareabstraktion. Wie bereits erwähnt, dient das Betriebssystem als Vermittler. Anwendungsprogrammierer können Software schreiben, die auf verschiedenen Hardwarekonfigurationen läuft, ohne dass sie ihren Code für jedes einzelne Gerät anpassen müssen. Das Betriebssystem übernimmt die Übersetzung durch Komponenten wie Gerätetreiber.

Resource management is a crucial function. The operating system decides which program may use the CPU for how long, allocates and releases memory to programs when they start and stop, manages storage space on storage devices, and controls access to input output devices.

Ressourcenverwaltung ist eine wichtige Funktion. Das Betriebssystem entscheidet, welches Programm die CPU wie lange nutzen darf, weist Programmen beim Starten und Beenden Speicher zu und gibt ihn wieder frei, verwaltet den Speicherplatz auf Speichergeräten und kontrolliert den Zugriff auf Ein- und Ausgabegeräte.

Process management. A process is essentially a program in execution. The operating system is responsible for creating, scheduling, and terminating processes. It enables multitasking, where multiple applications such as a web browser, word processor, and music player appear to run simultaneously by rapidly switching the CPU's attention between them.

Prozessverwaltung. Ein Prozess ist im Wesentlichen ein Programm in Ausführung. Das Betriebssystem ist für das Erstellen, Planen und Beenden von Prozessen verantwortlich. Es ermöglicht Multitasking, bei dem mehrere Anwendungen wie ein Webbrowser, ein Textverarbeitungsprogramm und ein Musikplayer gleichzeitig zu laufen scheinen, indem es die Aufmerksamkeit der CPU schnell zwischen ihnen umschaltet.

File system management. The operating system provides a structured way to organize, store, retrieve, and manage data on storage devices. It defines how files are named, how directories or folders are structured, and how access rights are handled. This allows users and applications to work with data in a logical and consistent manner.

Dateisystemverwaltung. Das Betriebssystem bietet eine strukturierte Möglichkeit, Daten auf Speichergeräten zu organisieren, zu speichern, abzurufen und zu verwalten. Es legt fest, wie Dateien benannt werden, wie Verzeichnisse oder Ordner strukturiert sind und wie die Zugriffsrechte gehandhabt werden. Auf diese Weise können Benutzer und Anwendungen auf logische und konsistente Weise mit Daten arbeiten.

User interface. This is the part of the operating system that allows you to interact with the computer. There is the graphical user interface or GUI, which uses windows, icons, menus, and a pointer controlled by a mouse for interaction. macOS and Windows are primarily GUI based.

Benutzeroberfläche. Dies ist der Teil des Betriebssystems, der es Ihnen ermöglicht, mit dem Computer zu interagieren. Es gibt die grafische Benutzeroberfläche, die Fenster, Symbole, Menüs und einen Zeiger verwendet, der durch eine Maus gesteuert wird. macOS und Windows sind hauptsächlich GUI-basiert.

The command line interface or CLI uses text-based commands. It is often preferred by technical users for its power and scriptability. The Terminal app on macOS provides a CLI.

Die Befehlszeilenschnittstelle verwendet textbasierte Befehle. Sie wird oft von technischen Benutzern wegen ihrer Leistungsfähigkeit und Skriptfähigkeit bevorzugt. Die Terminal-App auf macOS bietet eine Befehlszeilenschnittstelle.

Security and protection. The operating system implements security mechanisms to protect the integrity of the system and user data from unauthorized access, damage, and malicious software or malware. This includes features like user accounts, passwords, permissions, and firewalls.

Sicherheit und Schutz. Das Betriebssystem implementiert Sicherheitsmechanismen, um die Integrität des Systems und die Benutzerdaten vor unbefugtem Zugriff, Beschädigung und bösartiger Software zu schützen. Dazu gehören Funktionen wie Benutzerkonten, Passwörter, Berechtigungen und Firewalls.

Think about this. Consider your smartphone. It also runs an operating system like iOS or Android. How do its functions such as resource management, user interface, and process management differ from those of a desktop operating system? What are the particular challenges that an operating system on a mobile device must overcome?

Denken Sie darüber nach. Betrachten Sie Ihr Smartphone. Auf ihm läuft auch ein Betriebssystem wie iOS oder Android. Wie unterscheiden sich seine Funktionen wie Ressourcenmanagement, Benutzeroberfläche und Prozessmanagement von denen eines Desktop-Betriebssystems? Was sind die besonderen Herausforderungen, die ein Betriebssystem auf einem mobilen Gerät bewältigen muss?

Main components of an operating system. An operating system is not a single, monolithic piece of software, but rather a collection of interconnected components. The most important include the kernel. The kernel is often referred to as the heart or core of the operating system and is the central component that manages the basic operations of the computer.

Hauptkomponenten eines Betriebssystems. Ein Betriebssystem ist kein einzelnes, monolithisches Stück Software, sondern vielmehr eine Sammlung von miteinander verbundenen Komponenten. Zu den wichtigsten gehört der Kernel. Der Kernel wird oft als das Herz oder der Kern des Betriebssystems bezeichnet und ist die zentrale Komponente, die die grundlegenden Vorgänge des Computers verwaltet.

It is the first part of the operating system loaded into memory when the computer starts or boots up, and it remains resident in memory as long as the computer is running. The kernel has privileged access to the system's hardware and resources. Its main tasks include CPU scheduling, which determines which process may use the CPU at a given time.

Er ist der erste Teil des Betriebssystems, der in den Speicher geladen wird, wenn der Computer startet, und er bleibt im Speicher, solange der Computer läuft. Der Kernel hat privilegierten Zugriff auf die Hardware und die Ressourcen des Systems. Zu seinen Hauptaufgaben gehört die CPU-Planung, die bestimmt, welcher Prozess die CPU zu einem bestimmten Zeitpunkt nutzen darf.

Memory management involves allocating and releasing memory space for processes, tracking which parts of memory are being used and by whom, and managing virtual memory, which uses hard disk space as an extension of RAM.

Speicherverwaltung umfasst die Zuweisung und Freigabe von Speicherplatz für Prozesse, die Verfolgung, welche Teile des Speichers verwendet werden und von wem, und die Verwaltung des virtuellen Speichers, der Festplattenplatz als Erweiterung des RAM verwendet.

Device management involves interaction with hardware devices such as hard drives, network cards, and printers through their respective device drivers. A device driver is a specialized piece of software that knows how to communicate with a specific piece of hardware.

Geräteverwaltung beinhaltet die Interaktion mit Hardware-Geräten wie Festplatten, Netzwerkkarten und Druckern über ihre jeweiligen Gerätetreiber. Ein Gerätetreiber ist ein spezialisiertes Stück Software, das weiß, wie man mit einem bestimmten Stück Hardware kommuniziert.

System calls provide an interface through which application programs can request services from the kernel. For example, when an application wants to read a file, write to the screen, or open a network connection, it makes a system call to the kernel.

Systemaufrufe bieten eine Schnittstelle, über die Anwendungsprogramme Dienste vom Kernel anfordern können. Wenn eine Anwendung zum Beispiel eine Datei lesen, auf den Bildschirm schreiben oder eine Netzwerkverbindung öffnen möchte, führt sie einen Systemaufruf an den Kernel aus.

macOS uses a kernel called XNU. XNU is a hybrid kernel, meaning it combines features from two different kernel design philosophies. The Mach microkernel, which provides basic services like inter-process communication, memory management, and task scheduling, and components from Berkeley Software Distribution or BSD Unix, which provide features like networking and file systems. This hybrid approach aims to provide both flexibility and performance.

macOS verwendet einen Kernel namens XNU. XNU ist ein Hybrid-Kernel, das heißt, er kombiniert Funktionen aus zwei verschiedenen Kernel-Design-Philosophien: dem Mach-Mikrokernel, der grundlegende Dienste wie prozessübergreifende Kommunikation, Speicherverwaltung und Aufgabenplanung bereitstellt, und Komponenten von Berkeley Software Distribution Unix, die Funktionen wie Netzwerke und Dateisysteme bereitstellen. Dieser hybride Ansatz zielt darauf ab, sowohl Flexibilität als auch Leistung zu bieten.

The shell or command line interface. The shell is a special user program that provides a command line interface for interacting with the operating system. It reads commands entered by the user and then instructs the operating system to execute them. Shells are powerful tools for automation, scripting, and performing advanced administrative tasks.

Die Shell oder Befehlszeilenschnittstelle. Die Shell ist ein spezielles Benutzerprogramm, das eine Befehlszeilenschnittstelle für die Interaktion mit dem Betriebssystem bietet. Sie liest die vom Benutzer eingegebenen Befehle und weist dann das Betriebssystem an, sie auszuführen. Shells sind leistungsstarke Werkzeuge für die Automatisierung, die Erstellung von Skripten und die Durchführung erweiterter Verwaltungsaufgaben.

On macOS, the main application for accessing the shell is Terminal dot app. The default shell in modern macOS versions is Zsh or Z shell, which has replaced the older Bash shell. Zsh offers many advanced features like improved tab completion and theming.

Unter macOS ist die wichtigste Anwendung für den Zugriff auf die Shell Terminal. Die Standardshell in modernen macOS-Versionen ist Zsh, die die ältere Bash-Shell ersetzt hat. Zsh bietet viele fortgeschrittene Funktionen wie verbesserte Tab-Vervollständigung und Theming.

The graphical user interface or GUI. For most users, the GUI is the most visible part of the operating system. It provides a user-friendly environment with visual elements like windows, icons, menus, dialog boxes, and a pointer controlled by a mouse or trackpad. The GUI makes it easy to launch programs, manage files, and configure system settings without having to remember commands.

Die grafische Benutzeroberfläche. Für die meisten Benutzer ist die GUI der sichtbarste Teil des Betriebssystems. Sie bietet eine benutzerfreundliche Umgebung mit visuellen Elementen wie Fenstern, Symbolen, Menüs, Dialogfeldern und einem Zeiger, der durch eine Maus oder ein Trackpad gesteuert wird. Die GUI erleichtert das Starten von Programmen, das Verwalten von Dateien und das Konfigurieren von Systemeinstellungen, ohne dass man sich Befehle merken muss.

The macOS user interface, formerly known as Aqua, is known for its polished design and ease of use. Key components of the macOS interface include Finder for file management and launching programs, the Dock for quick access to applications and open windows, and the menu bar at the top of the screen.

Die macOS-Benutzeroberfläche, die früher unter dem Namen Aqua bekannt war, ist für ihr ausgefeiltes Design und ihre Benutzerfreundlichkeit bekannt. Zu den wichtigsten Komponenten der macOS-Benutzeroberfläche gehören der Finder für die Dateiverwaltung und das Starten von Programmen, das Dock für den schnellen Zugriff auf Anwendungen und geöffnete Fenster und die Menüleiste am oberen Rand des Bildschirms.

File system. A file system is the operating system component that controls how data is stored, organized, and retrieved from storage devices such as solid state drives, hard drives, and USB drives. It provides a hierarchical structure of files and directories or folders, allowing users and applications to find and access data efficiently.

Dateisystem. Ein Dateisystem ist die Betriebssystemkomponente, die steuert, wie Daten gespeichert, organisiert und von Speichergeräten wie Solid-State-Laufwerken, Festplatten und USB-Laufwerken abgerufen werden. Es bietet eine hierarchische Struktur von Dateien und Verzeichnissen oder Ordnern, die es Benutzern und Anwendungen ermöglicht, Daten effizient zu finden und darauf zuzugreifen.

Key functions include creating, deleting, renaming, reading, and writing files, as well as managing metadata, which is information about files such as size, creation date, and permissions.

Zu den wichtigsten Funktionen gehören das Erstellen, Löschen, Umbenennen, Lesen und Schreiben von Dateien sowie die Verwaltung von Metadaten, das sind Informationen über Dateien wie Größe, Erstellungsdatum und Berechtigungen.

Modern Macs primarily use the Apple File System or APFS. APFS is optimized for flash and solid state drives, which are standard in current Mac models. It includes advanced features like strong encryption, space sharing where multiple volumes can share free space on a single disk, snapshots for backups, and improved crash protection. Older Macs may use HFS Plus or Mac OS Extended.

Moderne Macs verwenden hauptsächlich das Apple File System. APFS ist für Flash- und Solid-State-Laufwerke optimiert, die in aktuellen Mac-Modellen Standard sind. Es enthält fortschrittliche Funktionen wie starke Verschlüsselung, gemeinsame Nutzung von Speicherplatz, wo mehrere Volumes sich den freien Speicherplatz auf einer einzigen Festplatte teilen können, Snapshots für Backups und verbesserten Schutz vor Abstürzen. Ältere Macs verwenden möglicherweise HFS Plus oder Mac OS Extended.

System utilities and programs. Operating systems come with a variety of utilities and basic applications that help users manage and maintain their system and perform common tasks. Examples on macOS include Activity Monitor, which allows viewing and managing running processes and monitoring CPU, memory, disk, and network usage.

Systemdienstprogramme und Programme. Betriebssysteme werden mit einer Vielzahl von Dienstprogrammen und grundlegenden Anwendungen ausgeliefert, die den Benutzern bei der Verwaltung und Wartung ihres Systems sowie bei der Durchführung allgemeiner Aufgaben helfen. Beispiele unter macOS sind der Aktivitätsmonitor, der die Anzeige und Verwaltung laufender Prozesse und die Überwachung der CPU-, Speicher-, Festplatten- und Netzwerknutzung ermöglicht.

Disk Utility is used to manage storage devices, including formatting, partitioning, and repairing disks. System Settings, formerly System Preferences, is the central application for configuring various aspects of the operating system, including network settings, display settings, user accounts, and security options.

Festplattendienstprogramm dient zur Verwaltung von Speichergeräten, einschließlich Formatierung, Partitionierung und Reparatur von Festplatten. Systemeinstellungen, früher Systempräferenzen, ist die zentrale Anwendung für die Konfiguration verschiedener Aspekte des Betriebssystems, einschließlich Netzwerkeinstellungen, Anzeigeeinstellungen, Benutzerkonten und Sicherheitsoptionen.

Basic applications include TextEdit, a simple text editor, Safari web browser, and Mail.

Grundlegende Anwendungen umfassen TextEdit, einen einfachen Texteditor, Safari Webbrowser und Mail.

Try it yourself. First, identify kernel processes. Open Activity Monitor through Finder, Applications, Utilities. Click on the CPU tab. Try to identify processes that seem to be fundamental to the operating system. You might see processes like kernel underscore task. What role do you think this process plays based on its name and resource usage? Don't worry if it's not entirely clear. We'll learn more about this later.

Versuchen Sie es selbst. Identifizieren Sie zunächst Kernel-Prozesse. Öffnen Sie den Aktivitätsmonitor über Finder, Anwendungen, Dienstprogramme. Klicken Sie auf die Registerkarte CPU. Versuchen Sie, Prozesse zu erkennen, die für das Betriebssystem grundlegend zu sein scheinen. Vielleicht sehen Sie Prozesse wie kernel task. Was glauben Sie, welche Rolle dieser Prozess aufgrund seines Namens und seiner Ressourcennutzung spielt? Keine Sorge, wenn das nicht ganz klar ist, wir werden später mehr darüber erfahren.

Second, navigate via CLI. Open Terminal. Type ls and press Enter. This lists the content of your current directory. Type cd Desktop and press Enter to change to your desktop directory. Type ls again. What is the difference from using Finder to see your desktop? Type cd and press Enter to return to your home directory.

Zweitens, navigieren Sie über die Befehlszeilenschnittstelle. Öffnen Sie Terminal. Geben Sie ls ein und drücken Sie Enter. Dies listet den Inhalt Ihres aktuellen Verzeichnisses auf. Geben Sie cd Desktop ein und drücken Sie Enter, um in das Verzeichnis Ihres Desktops zu wechseln. Geben Sie erneut ls ein. Was ist der Unterschied zur Verwendung des Finders, um Ihren Desktop zu sehen? Tippen Sie cd und drücken Sie die Eingabetaste, um zu Ihrem Heimatverzeichnis zurückzukehren.

Types of operating systems. Operating systems are diverse and can be categorized according to various criteria, such as the type of hardware they run on, the number of users they support, or the types of tasks they are designed for. Here are some common categories.

Arten von Betriebssystemen. Betriebssysteme sind vielfältig und können nach verschiedenen Kriterien kategorisiert werden, wie der Art der Hardware, auf der sie laufen, der Anzahl der Benutzer, die sie unterstützen, oder der Art der Aufgaben, für die sie entwickelt wurden. Hier sind einige gängige Kategorien.

Desktop operating systems are designed for use on personal computers, desktops, and laptops. They aim to provide a rich user experience with a wide range of applications for productivity, entertainment, and general use.

Desktop-Betriebssysteme sind für die Verwendung auf Personalcomputern, Desktops und Laptops konzipiert. Sie zielen darauf ab, ein reichhaltiges Benutzererlebnis mit einer breiten Palette von Anwendungen für Produktivität, Unterhaltung und allgemeinen Gebrauch zu bieten.

Their features typically support a single user at a time for interactive tasks, offer a robust graphical user interface, extensive multimedia capabilities, and support for a large number of peripheral devices. Examples include Apple macOS, Microsoft Windows, and Linux distributions such as Ubuntu, Fedora, and Mint.

Ihre Merkmale unterstützen in der Regel jeweils einen einzelnen Benutzer bei interaktiven Aufgaben, bieten eine robuste grafische Benutzeroberfläche, umfangreiche Multimedia-Funktionen und Unterstützung für eine große Anzahl von Peripheriegeräten. Beispiele sind Apple macOS, Microsoft Windows und Linux-Distributionen wie Ubuntu, Fedora und Mint.

Mobile operating systems are specifically developed for mobile devices like smartphones and tablets. They are optimized for touch-based input, power efficiency to maximize battery life, connectivity through Wi-Fi and cellular networks, and a wide range of mobile applications or apps. They often have more restrictive security models than desktop operating systems. Examples include Apple iOS for iPhone and iPad, and Google Android.

Mobile Betriebssysteme sind speziell für mobile Geräte wie Smartphones und Tablets entwickelt. Sie sind optimiert für berührungsbasierte Eingaben, Energieeffizienz zur Maximierung der Akkulaufzeit, Konnektivität durch Wi-Fi und Mobilfunknetze und eine breite Palette mobiler Anwendungen oder Apps. Sie haben oft restriktivere Sicherheitsmodelle als Desktop-Betriebssysteme. Beispiele sind Apple iOS für iPhone und iPad und Google Android.

Server operating systems are developed to run on server hardware, meaning powerful computers that provide services to other computers or clients over a network. These services can include web hosting, email, file sharing, databases, and application hosting.

Server-Betriebssysteme sind entwickelt für den Betrieb auf Server-Hardware, das heißt leistungsstarken Computern, die anderen Computern oder Clients über ein Netzwerk Dienste zur Verfügung stellen. Diese Dienste können Webhosting, E-Mail, Dateifreigabe, Datenbanken und Anwendungshosting umfassen.

They are optimized for stability, reliability, security, and performance under high load. They often support multiple users simultaneously and are designed to run for extended periods without interruption. They may or may not have a graphical user interface, as many servers are managed remotely via CLI. Examples include Linux distributions such as Red Hat Enterprise Linux, Ubuntu Server, and CentOS, Microsoft Windows Server, and UNIX variants like Solaris.

Sie sind optimiert für Stabilität, Zuverlässigkeit, Sicherheit und Leistung bei hoher Belastung. Sie unterstützen oft mehrere Benutzer gleichzeitig und sind darauf ausgelegt, über lange Zeiträume ohne Unterbrechung zu laufen. Sie können eine grafische Benutzeroberfläche haben oder auch nicht, da viele Server aus der Ferne über die Befehlszeilenschnittstelle verwaltet werden. Beispiele sind Linux-Distributionen wie Red Hat Enterprise Linux, Ubuntu Server und CentOS, Microsoft Windows Server und UNIX-Varianten wie Solaris.

Embedded operating systems are designed to perform specific, dedicated functions within larger electronic or mechanical systems, often with very limited hardware resources like CPU power, memory, and storage. They are highly specialized, compact, and efficient. They must be extremely reliable as they often control critical functions. Examples are found in a variety of devices including cars with engine control units and infotainment systems, household appliances like smart televisions and washing machines, medical devices such as pacemakers and patient monitors, industrial control systems, automated teller machines, and wearable technology. Examples include FreeRTOS, QNX, and VxWorks.

Eingebettete Betriebssysteme sind entwickelt, um spezifische, dedizierte Funktionen innerhalb größerer elektronischer oder mechanischer Systeme auszuführen, oft mit sehr begrenzten Hardwareressourcen wie CPU-Leistung, Speicher und Storage. Sie sind hochspezialisiert, kompakt und effizient. Sie müssen extrem zuverlässig sein, da sie oft kritische Funktionen steuern. Beispiele finden sich in einer Vielzahl von Geräten, darunter Autos mit Motorsteuergeräten und Infotainmentsystemen, Haushaltsgeräte wie intelligente Fernsehgeräte und Waschmaschinen, medizinische Geräte wie Herzschrittmacher und Patientenmonitore, industrielle Steuersysteme, Geldautomaten und tragbare Technologie. Beispiele sind FreeRTOS, QNX und VxWorks.

Real-time operating systems or RTOS are used in systems where the timing of operations is critical. They must process data and events within strict, predictable time constraints or deadlines. Failure to meet a deadline can have serious consequences. Their features focus on deterministic scheduling and low latency. They are frequently used in applications where delay could have catastrophic consequences. Examples include aerospace systems like flight control, industrial robotics, scientific instruments, and some medical devices. Many embedded operating systems also have real-time capabilities.

Echtzeitbetriebssysteme werden in Systemen verwendet, bei denen die zeitliche Abstimmung von Vorgängen kritisch ist. Sie müssen Daten und Ereignisse innerhalb strenger, vorhersehbarer Zeitvorgaben oder Fristen verarbeiten. Die Nichteinhaltung einer Frist kann schwerwiegende Folgen haben. Ihre Merkmale konzentrieren sich auf deterministische Zeitplanung und geringe Latenzzeit. Sie werden häufig in Anwendungen eingesetzt, bei denen eine Verzögerung katastrophale Folgen haben könnte. Beispiele sind Luft- und Raumfahrtsysteme wie Flugsteuerung, Industrierobotik, wissenschaftliche Instrumente und einige medizinische Geräte. Viele eingebettete Betriebssysteme haben auch Echtzeitfähigkeiten.

In this program, we primarily focus on desktop and server operating systems, as these are the environments where cybersecurity professionals most frequently work with securing systems, analyzing threats, and investigating incidents. However, understanding the diversity of operating system types is important for a holistic view of computing.

In diesem Programm konzentrieren wir uns in erster Linie auf Desktop- und Server-Betriebssysteme, da dies die Umgebungen sind, in denen Cybersicherheitsexperten am häufigsten mit der Sicherung von Systemen, der Analyse von Bedrohungen und der Untersuchung von Vorfällen arbeiten. Das Verständnis für die Vielfalt der Betriebssystemtypen ist jedoch wichtig für eine ganzheitliche Betrachtung der Datenverarbeitung.

Think about this. Why does a server operating system prioritize stability and security over the latest multimedia features, while a desktop operating system tries to balance all these factors? What are the security implications if an embedded operating system in a critical device, such as a car's braking system, has a vulnerability?

Denken Sie darüber nach. Warum gibt ein Server-Betriebssystem der Stabilität und Sicherheit den Vorrang vor den neuesten Multimedia-Funktionen, während ein Desktop-Betriebssystem versucht, einen Ausgleich zwischen all diesen Faktoren zu schaffen? Welche Auswirkungen hat es auf die Sicherheit, wenn ein eingebettetes Betriebssystem in einem kritischen Gerät, wie dem Bremssystem eines Autos, eine Schwachstelle aufweist?

Why is understanding the operating system crucial for cybersecurity? The operating system is not just a platform for running applications, but also an important battlefield in the world of cybersecurity. A deep understanding of operating system principles is essential for every cybersecurity professional for several reasons.

Warum ist das Verständnis des Betriebssystems für die Cybersicherheit von entscheidender Bedeutung? Das Betriebssystem ist nicht nur eine Plattform für die Ausführung von Anwendungen, sondern auch ein wichtiges Schlachtfeld in der Welt der Cybersicherheit. Ein tiefes Verständnis der Betriebssystemprinzipien ist für jeden Cybersicherheitsexperten aus mehreren Gründen unerlässlich.

Target of attacks. Vulnerabilities in operating systems are primary targets for attackers. Exploiting vulnerabilities in the kernel, system services, or applications bundled with the operating system can allow attackers to gain unauthorized access, escalate their privileges, for example from a normal user to an administrator, install malware, or exfiltrate sensitive data.

Ziel von Angriffen. Schwachstellen in Betriebssystemen sind Hauptziele für Angreifer. Das Ausnutzen von Schwachstellen im Kernel, in Systemdiensten oder in Anwendungen, die mit dem Betriebssystem gebündelt sind, kann es Angreifern ermöglichen, unbefugten Zugriff zu erlangen, ihre Privilegien zu erweitern, zum Beispiel von einem normalen Benutzer zu einem Administrator, Malware zu installieren oder sensible Daten zu exfiltrieren.

Platform for security tools. Most cybersecurity tools such as antivirus software, host-based intrusion detection and prevention systems, firewalls, and endpoint detection and response solutions operate at the operating system level or interact closely with it. Understanding the operating system helps in effectively deploying, configuring, and interpreting the results of these tools.

Plattform für Sicherheitstools. Die meisten Cybersecurity-Tools wie Antiviren-Software, Host-basierte Intrusion Detection und Prevention Systeme, Firewalls und Endpoint Detection and Response-Lösungen arbeiten auf Betriebssystemebene oder stehen in enger Wechselwirkung mit ihr. Das Verständnis des Betriebssystems hilft bei der effektiven Bereitstellung, Konfiguration und Interpretation der Ergebnisse dieser Tools.

Forensic analysis. When a security incident occurs, digital forensics investigators must analyze the affected systems. This involves examining operating system artifacts such as log files, registry entries on Windows, file system structures, memory dumps, and running processes to understand what happened, how the system was compromised, and what data was affected.

Forensische Analyse. Wenn ein Sicherheitsvorfall eintritt, müssen die Ermittler der digitalen Forensik die betroffenen Systeme analysieren. Dazu gehört die Untersuchung von Betriebssystemartefakten wie Protokolldateien, Registrierungseinträgen unter Windows, Dateisystemstrukturen, Speicherabzügen und laufenden Prozessen, um zu verstehen, was passiert ist, wie das System kompromittiert wurde und welche Daten betroffen waren.

Malware analysis. Malware, including viruses, worms, trojans, ransomware, and spyware, is specifically designed to run on and exploit specific operating systems. Analyzing malware behavior, such as how it infects, persists, communicates, and what damage it causes, requires a thorough understanding of operating system internals, including process management, memory allocation, file system interaction, and network APIs.

Malware-Analyse. Malware, einschließlich Viren, Würmer, Trojaner, Ransomware und Spyware, ist speziell darauf ausgelegt, auf bestimmten Betriebssystemen zu laufen und diese auszunutzen. Die Analyse des Verhaltens von Malware, wie sie infiziert, bestehen bleibt, kommuniziert und welchen Schaden sie anrichtet, erfordert ein gründliches Verständnis der Interna des Betriebssystems, einschließlich Prozessverwaltung, Speicherzuweisung, Interaktion mit dem Dateisystem und Netzwerk-APIs.

System hardening. A core practice in cybersecurity is hardening operating systems to reduce their attack surface. This includes securely configuring the operating system by disabling unnecessary services and features, promptly applying security patches, implementing strong access controls and permissions, enabling encryption, and configuring logging and auditing.

Systemhärtung. Eine zentrale Praxis der Cybersicherheit ist die Härtung von Betriebssystemen, um deren Angriffsfläche zu verringern. Dazu gehört die sichere Konfiguration des Betriebssystems durch die Deaktivierung unnötiger Dienste und Funktionen, die zeitnahe Anwendung von Sicherheits-Patches, die Implementierung starker Zugriffskontrollen und Berechtigungen, die Aktivierung von Verschlüsselung und die Konfiguration von Protokollierung und Auditing.

Vulnerability assessment and penetration testing. Security professionals conducting vulnerability assessments or penetration tests, also known as ethical hacking, must understand how operating systems work to identify potential vulnerabilities. They examine the operating system and its services for known vulnerabilities, misconfigurations, and design flaws.

Schwachstellenbewertung und Penetrationstests. Sicherheitsexperten, die Schwachstellenbewertungen oder Penetrationstests durchführen, müssen verstehen, wie Betriebssysteme funktionieren, um potenzielle Schwachstellen zu erkennen. Sie untersuchen das Betriebssystem und seine Dienste auf bekannte Schwachstellen, Fehlkonfigurationen und Designfehler.

Understanding attacker techniques. Many attack techniques, such as buffer overflows, privilege escalation, and rootkits, specifically target operating system mechanisms. Knowing how these mechanisms work is key to understanding and defending against such attacks.

Verstehen von Angreifertechniken. Viele Angriffstechniken wie Pufferüberläufe, Privilegienerweiterung und Rootkits zielen speziell auf Betriebssystemmechanismen ab. Zu wissen, wie diese Mechanismen funktionieren, ist der Schlüssel zum Verständnis und zur Verteidigung gegen solche Angriffe.

Essentially, the operating system is the fundamental layer on which all other software runs and where important data is managed. If the operating system is attacked, the security of the entire system is compromised.

Im Wesentlichen ist das Betriebssystem die grundlegende Schicht, auf der alle andere Software läuft und auf der wichtige Daten verwaltet werden. Wenn das Betriebssystem angegriffen wird, ist die Sicherheit des gesamten Systems gefährdet.

Introduction to macOS. Since you will be working with macOS during this program, let's highlight some key aspects relevant to our study. macOS is the operating system developed by Apple Incorporated for its Mac line of computers.

Einführung in macOS. Da Sie während dieses Programms mit macOS arbeiten werden, wollen wir einige wichtige Aspekte hervorheben, die für unser Studium relevant sind. macOS ist das Betriebssystem, das von Apple für seine Mac-Reihe entwickelt wurde.

Unix heritage. One of the most important features of macOS is its Unix-like foundation. More specifically, macOS is a certified UNIX 03 operating system built on a core set of components and philosophies derived from BSD or Berkeley Software Distribution Unix. This Unix heritage brings several advantages.

Unix-Erbe. Eines der wichtigsten Merkmale von macOS ist seine Unix-ähnliche Grundlage. Genauer gesagt ist macOS ein zertifiziertes UNIX 03-Betriebssystem, das auf einem Kernsatz von Komponenten und Philosophien aufbaut, die von BSD Unix abgeleitet sind. Dieses Unix-Erbe bringt mehrere Vorteile mit sich.

First, stability and robustness. Unix systems are generally known for their stability. Second, a powerful command line. Access to a wide variety of command line tools and utilities used across all Unix-like systems, including Linux. This is invaluable for developers, system administrators, and cybersecurity professionals.

Erstens, Stabilität und Robustheit. Unix-Systeme sind allgemein für ihre Stabilität bekannt. Zweitens, eine mächtige Befehlszeile. Zugang zu einer Vielzahl von Befehlszeilentools und Dienstprogrammen, die in allen Unix-ähnlichen Systemen, einschließlich Linux, verwendet werden. Dies ist von unschätzbarem Wert für Entwickler, Systemadministratoren und Cybersicherheitsexperten.

Third, multi-user capabilities. Designed from the ground up to support multiple users with different permissions and environments. Fourth, network stack. A mature and robust network stack.

Drittens, Mehrbenutzerfähigkeiten. Von Grund auf für die Unterstützung mehrerer Benutzer mit unterschiedlichen Berechtigungen und Umgebungen konzipiert. Viertens, Netzwerk-Stack. Ein ausgereifter und robuster Netzwerk-Stack.

Key user interface elements and concepts include the Dock, typically located at the bottom or side of the screen, providing quick access to frequently used programs, currently running programs, and minimized windows.

Schlüsselelemente und Konzepte der Benutzeroberfläche umfassen das Dock, das sich in der Regel am unteren oder seitlichen Rand des Bildschirms befindet und schnellen Zugriff auf häufig verwendete Programme, aktuell ausgeführte Programme und minimierte Fenster bietet.

Finder is the default file manager in macOS. It allows you to browse files, folders, programs, and connected drives. It is your main tool for navigating the file system via the graphical user interface.

Finder ist der Standard-Dateimanager in macOS. Mit ihm können Sie Dateien, Ordner, Programme und verbundene Laufwerke durchsuchen. Er ist Ihr wichtigstes Werkzeug, um über die grafische Benutzeroberfläche im Dateisystem zu navigieren.

System Settings, or System Preferences in older macOS versions, is the central hub for configuring all aspects of your Mac, from display and sound settings to network configurations, user accounts, and importantly, security and privacy settings.

Systemeinstellungen, oder Systempräferenzen bei älteren macOS-Versionen, ist die zentrale Anlaufstelle für die Konfiguration aller Aspekte Ihres Macs, von Anzeige- und Soundeinstellungen bis hin zu Netzwerkkonfigurationen, Benutzerkonten und, ganz wichtig, Sicherheits- und Datenschutzeinstellungen.

Spotlight Search is a powerful system-wide search function, accessible via Command plus Space or the magnifying glass icon in the menu bar, allowing you to quickly find files, programs, emails, perform calculations, or look up definitions.

Spotlight Search ist eine leistungsstarke systemweite Suchfunktion, zu erreichen über Befehl plus Leertaste oder das Lupensymbol in der Menüleiste, mit der Sie schnell Dateien, Programme, E-Mails finden und sogar Berechnungen durchführen oder Definitionen nachschlagen können.

Built-in security features. macOS includes several layers of security to protect users and their data. It is important to understand these to utilize them and recognize their limitations.

Eingebaute Sicherheitsfunktionen. macOS enthält mehrere Sicherheitsebenen zum Schutz der Benutzer und ihrer Daten. Es ist wichtig, diese zu verstehen, um sie zu nutzen und ihre Grenzen zu erkennen.

Gatekeeper prevents users from accidentally running malware by controlling which programs can be opened. By default, it allows applications from the Mac App Store and from identified developers.

Gatekeeper verhindert, dass Benutzer versehentlich Malware ausführen, indem es kontrolliert, welche Programme geöffnet werden können. Standardmäßig lässt es Anwendungen aus dem Mac App Store und von identifizierten Entwicklern zu.

XProtect is an anti-malware technology that provides basic signature-based detection and removal of known malware. It works in the background.

XProtect ist eine Anti-Malware-Technologie, die eine grundlegende signaturbasierte Erkennung und Entfernung von bekannter Malware bietet. Sie arbeitet im Hintergrund.

System Integrity Protection or SIP is a security technology that restricts the root user account, the superuser with all rights, and limits the actions that even the root user can perform on protected parts of macOS. This helps prevent malicious software or accidental changes from compromising important system files and folders.

Systemintegritätsschutz ist eine Sicherheitstechnologie, die den root-Benutzer-Account, den Superuser mit allen Rechten, einschränkt und die Aktionen begrenzt, die sogar der root-Benutzer auf geschützten Teilen des macOS durchführen kann. Dies hilft zu verhindern, dass bösartige Software oder versehentliche Änderungen wichtige Systemdateien und Ordner gefährden.

FileVault provides full disk encryption for your Mac's startup disk. When enabled, your data is automatically encrypted and unreadable without the login password or a recovery key. This is crucial for protecting data if your Mac is lost or stolen.

FileVault bietet eine vollständige Festplattenverschlüsselung für die Startfestplatte Ihres Macs. Wenn sie aktiviert ist, werden Ihre Daten automatisch verschlüsselt und sind ohne das Anmeldekennwort oder einen Wiederherstellungsschlüssel unlesbar. Dies ist entscheidend für den Schutz von Daten, wenn Ihr Mac verloren geht oder gestohlen wird.

Privacy controls. macOS includes extensive privacy controls, managed in System Settings, Privacy and Security, that require programs to obtain your explicit permission before accessing sensitive information like your location, contacts, photos, microphone, or camera.

Datenschutzkontrollen. macOS enthält umfangreiche Datenschutzkontrollen, verwaltet in den Systemeinstellungen, Datenschutz und Sicherheit, die Programme dazu verpflichten, Ihre ausdrückliche Erlaubnis einzuholen, bevor sie auf sensible Informationen wie Ihren Standort, Ihre Kontakte, Fotos, Ihr Mikrofon oder Ihre Kamera zugreifen.

Sandboxing. Programs, especially those from the Mac App Store, are often sandboxed. This means they run in a restricted environment with limited access to system resources and user data, reducing the potential damage if an application is compromised.

Sandboxing. Programme, vor allem solche aus dem Mac App Store, sind oft sandboxed. Das bedeutet, dass sie in einer eingeschränkten Umgebung mit begrenztem Zugriff auf Systemressourcen und Benutzerdaten ausgeführt werden, um den potenziellen Schaden zu verringern, wenn eine Anwendung kompromittiert wird.

Try it yourself. First, explore System Settings, Security and Privacy. Open System Settings or System Preferences. Navigate to Privacy and Security, or Security and Privacy in older versions.

Versuchen Sie es selbst. Untersuchen Sie zunächst die Systemeinstellungen, Sicherheit und Datenschutz. Öffnen Sie die Systemeinstellungen oder Systempräferenzen. Navigieren Sie zu Datenschutz und Sicherheit oder Sicherheit und Datenschutz bei älteren Versionen.

Look at the Firewall options. Is it on or off by default on your system? You don't need to change it now, just observe. Locate the FileVault section. Is it enabled?

Sehen Sie sich die Firewall-Optionen an. Ist sie auf Ihrem System standardmäßig ein- oder ausgeschaltet? Sie müssen sie jetzt nicht ändern, sondern nur beobachten. Suchen Sie den Abschnitt FileVault. Ist er aktiviert?

Under Application Security or similar, what are the current settings for allowing app downloads, for example, App Store and identified developers? This relates to Gatekeeper.

Wie lauten unter Anwendungssicherheit oder ähnlich die aktuellen Einstellungen für das Zulassen von App-Downloads, zum Beispiel App Store und identifizierte Entwickler? Dies bezieht sich auf Gatekeeper.

Second, check SIP status. This is optional and requires Terminal. Open Terminal. Type the command csrutil status and press Enter. It will tell you whether System Integrity Protection is enabled or disabled. For almost all users, it should be enabled and remain so.

Prüfen Sie zweitens den SIP-Status. Dies ist optional und erfordert Terminal. Öffnen Sie Terminal. Geben Sie den Befehl csrutil status ein und drücken Sie Enter. Es wird Ihnen angezeigt, ob der Systemintegritätsschutz aktiviert oder deaktiviert ist. Für fast alle Benutzer sollte er aktiviert sein und bleiben.

You now have a more detailed understanding of the fundamental concepts of operating systems, with a focus on macOS. This foundation will be crucial as we delve deeper into how operating systems work, how to secure them, and their attack points in the cybersecurity landscape.

Sie verfügen nun über ein detaillierteres Verständnis der grundlegenden Konzepte von Betriebssystemen, mit einem Schwerpunkt auf macOS. Diese Grundlage wird von entscheidender Bedeutung sein, wenn wir uns eingehender mit der Funktionsweise von Betriebssystemen, ihrer Absicherung und ihren Angriffspunkten in der Cybersicherheitslandschaft beschäftigen.

The slides for the live session can be viewed here. Try not to peek before class. Spoilers inside.

Die Folien für die Live-Sitzung können hier angesehen werden. Versuchen Sie nicht zu spicken vor dem Unterricht. Spoiler enthalten.