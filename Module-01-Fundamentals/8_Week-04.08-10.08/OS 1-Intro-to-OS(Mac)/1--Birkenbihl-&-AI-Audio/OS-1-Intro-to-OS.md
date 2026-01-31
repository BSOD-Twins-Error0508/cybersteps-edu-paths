Willkommen zu Ihrem ersten Blick auf Betriebssysteme! Dieses Vorbereitungsmaterial führt Sie durch die grundlegenden Konzepte, was ein Betriebssystem ist, was es tut und warum es eine kritische Komponente jedes Computergeräts ist, mit besonderem Schwerpunkt auf dem macOS, das Sie verwenden werden. Das Verständnis des Betriebssystems ist für die Cybersicherheit von grundlegender Bedeutung, da es oft die Grundlage für Abwehrmaßnahmen und Angriffsvektoren bildet.

## Was ist ein Betriebssystem?

Stellen Sie sich eine belebte Stadt vor. Damit die Stadt funktioniert, braucht sie Infrastruktur (Straßen, Stromleitungen, Wasserversorgung), Verkehrsmanagement, Strafverfolgung und eine Möglichkeit für den Betrieb und die Interaktion verschiedener Dienste (Geschäfte, Büros, Wohnungen). Ein Betriebssystem (OS) spielt eine ähnliche Rolle für Ihren Computer. Es handelt sich dabei um eine hochentwickelte Software, die als zentraler Koordinator und Verwalter aller Hardware- und Softwareressourcen Ihres Computers fungiert. Ohne ein Betriebssystem wäre Ihr Computer nur eine Ansammlung elektronischer Komponenten, die keine nützlichen Aufgaben erfüllen könnten.

![[Pasted image 20250930051630.png]]

Die Hauptziele eines Betriebssystems sind zweierlei:

1. **Komfort für den Benutzer:** Das Computersystem soll benutzerfreundlich und zugänglich sein. Das Betriebssystem bietet eine **Abstraktionsebene**, d. h. es verbirgt die unglaublich komplexe, niedrigstufige Funktionsweise der Hardware. Anstatt zu wissen, wie man den Prozessor direkt ansteuert oder Daten in einen bestimmten Sektor auf einer Festplatte schreibt, interagiert man mit intuitiven Schnittstellen wie Symbolen, Menüs oder einfachen Befehlen.
2. **Effizienz des Betriebs:** Die Ressourcen des Computersystems - wie die Zentraleinheit (CPU), der Arbeitsspeicher (RAM), die Speichergeräte (Festplatten, SSDs) und die Peripheriegeräte für die Ein- und Ausgabe (Tastatur, Maus, Drucker, Netzwerkkarte) - werden optimal und fair verwaltet. Dadurch wird sichergestellt, dass mehrere Programme reibungslos ausgeführt werden können und die Ressourcen dort zugewiesen werden, wo sie am meisten benötigt werden.

Zu den Kernfunktionen eines Betriebssystems gehören:

- **Hardwareabstraktion:** Wie bereits erwähnt, dient das Betriebssystem als Vermittler. Anwendungsprogrammierer können Software schreiben, die auf verschiedenen Hardwarekonfigurationen läuft, ohne dass sie ihren Code für jedes einzelne Gerät anpassen müssen. Das Betriebssystem übernimmt die Übersetzung durch Komponenten wie **Gerätetreiber**.

![[Pasted image 20250930051657.png]]

- **Ressourcenverwaltung:** Dies ist eine wichtige Funktion. Das Betriebssystem entscheidet, welches Programm die CPU wie lange nutzen darf (CPU-Scheduling), weist Programmen beim Starten und Beenden Speicher zu und gibt ihn wieder frei, verwaltet den Speicherplatz auf Speichergeräten und kontrolliert den Zugriff auf E/A-Geräte.

![[Pasted image 20250930051719.png]]

- **Prozessverwaltung:** Ein "Prozess" ist im Wesentlichen ein Programm in Ausführung. Das Betriebssystem ist für das Erstellen, Planen und Beenden von Prozessen verantwortlich. Es ermöglicht **Multitasking**, bei dem mehrere Anwendungen (z. B. ein Webbrowser, ein Textverarbeitungsprogramm und ein Musikplayer) gleichzeitig zu laufen scheinen, indem es die Aufmerksamkeit der CPU schnell zwischen ihnen umschaltet.

![[Pasted image 20250930051725.png]]![image.png](attachment:5d5678ac-b6c7-444d-a00e-af33e1b9bfa1:image.png)

- **Dateisystemverwaltung:** Das Betriebssystem bietet eine strukturierte Möglichkeit, Daten auf Speichergeräten zu organisieren, zu speichern, abzurufen und zu verwalten. Es legt fest, wie Dateien benannt werden, wie Verzeichnisse (Ordner) strukturiert sind und wie die Zugriffsrechte gehandhabt werden. Auf diese Weise können Benutzer und Anwendungen auf logische und konsistente Weise mit Daten arbeiten.

![[Pasted image 20250930051734.png]]

- **Benutzeroberfläche (UI):** Dies ist der Teil des Betriebssystems, der es Ihnen ermöglicht, mit dem Computer zu interagieren.
    
    - **Grafische Benutzeroberfläche (GUI):** Verwendet Fenster, Symbole, Menüs und einen Zeiger (Mauscursor) für die Interaktion. macOS und Windows sind hauptsächlich GUI-basiert.
    
    ![[Pasted image 20250930051743.png]]
    
    - **Command-Line Interface (CLI):** Verwendet textbasierte Befehle. Sie wird oft von technischen Benutzern wegen ihrer Leistungsfähigkeit und Skriptfähigkeit bevorzugt. Die Terminal-App auf macOS bietet ein CLI.
    
    ![[Pasted image 20250930051751.png]]
    
- **Sicherheit und Schutz:** Das Betriebssystem implementiert Sicherheitsmechanismen, um die Integrität des Systems und die Benutzerdaten vor unbefugtem Zugriff, Beschädigung und bösartiger Software (Malware) zu schützen. Dazu gehören Funktionen wie Benutzerkonten, Passwörter, Berechtigungen und Firewalls.    

### Denken Sie darüber nach

Betrachten Sie Ihr Smartphone. Auf ihm läuft auch ein Betriebssystem (wie iOS oder Android). Wie unterscheiden sich seine Funktionen (Ressourcenmanagement, Benutzeroberfläche, Prozessmanagement) von denen eines Desktop-Betriebssystems? Was sind die besonderen Herausforderungen, die ein Betriebssystem auf einem mobilen Gerät bewältigen muss?

## Hauptkomponenten eines Betriebssystems

Ein Betriebssystem ist kein einzelnes, monolithisches Stück Software, sondern vielmehr eine Sammlung von miteinander verbundenen Komponenten. Zu den wichtigsten gehören:

1. **Der Kernel:** Der Kernel wird oft als das "Herz" oder der "Kern" des Betriebssystems bezeichnet und ist die zentrale Komponente, die die grundlegenden Vorgänge des Computers verwaltet. Er ist der erste Teil des Betriebssystems, der in den Speicher geladen wird, wenn der Computer startet (hochfährt), und er bleibt im Speicher resident, solange der Computer läuft. Der Kernel hat privilegierten Zugriff auf die Hardware und die Ressourcen des Systems. Zu seinen Hauptaufgaben gehören:
    
    - **CPU-Planung:** Er bestimmt, welcher Prozess die CPU zu einem bestimmten Zeitpunkt nutzen darf.
    - **Speicherverwaltung:** Zuweisung und Freigabe von Speicherplatz für Prozesse, Verfolgung, welche Teile des Speichers verwendet werden und von wem, und Verwaltung des virtuellen Speichers (Verwendung von Festplattenplatz als Erweiterung des RAM).
    - **Geräteverwaltung:** Interaktion mit Hardware-Geräten (wie Festplatten, Netzwerkkarten, Drucker) über ihre jeweiligen **Gerätetreiber**. Ein Gerätetreiber ist ein spezialisiertes Stück Software, das weiß, wie man mit einem bestimmten Stück Hardware kommuniziert.
    - **Systemaufrufe:** Sie bieten eine Schnittstelle, über die Anwendungsprogramme Dienste vom Kernel anfordern können. Wenn eine Anwendung zum Beispiel eine Datei lesen, auf den Bildschirm schreiben oder eine Netzwerkverbindung öffnen möchte, führt sie einen Systemaufruf an den Kernel aus.
    - macOS verwendet einen Kernel namens **XNU**. XNU ist ein _Hybrid-Kernel_, d. h. er kombiniert Funktionen aus zwei verschiedenen Kernel-Design-Philosophien: dem _Mach-Mikrokernel_ (der grundlegende Dienste wie prozessübergreifende Kommunikation, Speicherverwaltung und Aufgabenplanung bereitstellt) und Komponenten von _Berkeley Software Distribution (BSD)_ Unix (die Funktionen wie Netzwerke und Dateisysteme bereitstellen). Dieser hybride Ansatz zielt darauf ab, sowohl Flexibilität als auch Leistung zu bieten.
    
    ![[Pasted image 20250930051824.png]]
    
2. **Die Shell (Command-Line Interface - CLI):** Die Shell ist ein spezielles Benutzerprogramm, das eine Befehlszeilenschnittstelle für die Interaktion mit dem Betriebssystem bietet. Sie liest die vom Benutzer eingegebenen Befehle und weist dann das Betriebssystem an, sie auszuführen. Shells sind leistungsstarke Werkzeuge für die Automatisierung, die Erstellung von Skripten und die Durchführung erweiterter Verwaltungsaufgaben.
    
    - Unter macOS ist die wichtigste Anwendung für den Zugriff auf die Shell **Terminal.app**.
    - Die Standardshell in modernen macOS-Versionen ist **Zsh (Z-Shell)**, die die ältere Bash-Shell ersetzt hat. Zsh bietet viele fortgeschrittene Funktionen wie verbesserte Tab-Vervollständigung und Theming.
    
    ![[Pasted image 20250930051858.png]]
    
3. **Die grafische Benutzeroberfläche (GUI):** Für die meisten Benutzer ist die GUI der sichtbarste Teil des Betriebssystems. Sie bietet eine benutzerfreundliche Umgebung mit visuellen Elementen wie Fenstern, Symbolen, Menüs, Dialogfeldern und einem Zeiger (gesteuert durch eine Maus oder ein Trackpad). Die GUI erleichtert das Starten von Programmen, das Verwalten von Dateien und das Konfigurieren von Systemeinstellungen, ohne dass man sich Befehle merken muss.
    
    - Die macOS-Benutzeroberfläche, die früher unter dem Namen "Aqua" bekannt war, ist für ihr ausgefeiltes Design und ihre Benutzerfreundlichkeit bekannt. Zu den wichtigsten Komponenten der macOS-Benutzeroberfläche gehören der **Finder** (für die Dateiverwaltung und das Starten von Programmen), das **Dock** (für den schnellen Zugriff auf Anwendungen und geöffnete Fenster) und die **Menüleiste** am oberen Rand des Bildschirms.
    
    ![[Pasted image 20250930051905.png]]
    
4. **Dateisystem:** Ein Dateisystem ist die Betriebssystemkomponente, die steuert, wie Daten gespeichert, organisiert und von Speichergeräten (wie SSDs, Festplatten, USB-Laufwerken) abgerufen werden. Es bietet eine hierarchische Struktur von Dateien und Verzeichnissen (Ordnern), die es Benutzern und Anwendungen ermöglicht, Daten effizient zu finden und darauf zuzugreifen.
    
    - Zu den wichtigsten Funktionen gehören das Erstellen, Löschen, Umbenennen, Lesen und Schreiben von Dateien sowie die Verwaltung von Metadaten (Informationen über Dateien wie Größe, Erstellungsdatum und Berechtigungen).
    - Moderne Macs verwenden hauptsächlich das **Apple File System (APFS)**. APFS ist für Flash- und Solid-State-Laufwerke (SSD) optimiert, die in aktuellen Mac Modellen Standard sind. Es enthält fortschrittliche Funktionen wie starke Verschlüsselung, gemeinsame Nutzung von Speicherplatz (mehrere Volumes können sich den freien Speicherplatz auf einer einzigen Festplatte teilen), Snapshots (für Backups) und verbesserten Schutz vor Abstürzen. Ältere Macs verwenden möglicherweise **HFS+ (Mac OS Extended)**.
5. **Systemdienstprogramme und Programme:** Betriebssysteme werden mit einer Vielzahl von Dienstprogrammen und grundlegenden Anwendungen ausgeliefert, die den Benutzern bei der Verwaltung und Wartung ihres Systems sowie bei der Durchführung allgemeiner Aufgaben helfen.
    
    - Beispiele unter macOS sind:
        - **Aktivitätsmonitor:** Ermöglicht die Anzeige und Verwaltung laufender Prozesse, die Überwachung der CPU-, Speicher-, Festplatten- und Netzwerknutzung.
        - **Disk Utility:** Dient zur Verwaltung von Speichergeräten, einschließlich Formatierung, Partitionierung und Reparatur von Festplatten.
        - **Systemeinstellungen (früher Systemeinstellungen):** Die zentrale Anwendung für die Konfiguration verschiedener Aspekte des Betriebssystems, einschließlich Netzwerkeinstellungen, Anzeigeeinstellungen, Benutzerkonten und Sicherheitsoptionen.
        - Grundlegende Anwendungen wie TextEdit (ein einfacher Texteditor), Safari (Webbrowser) und Mail.

- **Zweck:** Sie werden in Systemen eingesetzt, bei denen das Timing von Operationen kritisch ist. Sie müssen Daten und Ereignisse innerhalb strenger, vorhersehbarer Zeitvorgaben (Fristen) verarbeiten. Die Nichteinhaltung einer Frist kann schwerwiegende Folgen haben.
    - **Merkmale:** Schwerpunkt auf deterministischer Zeitplanung und geringer Latenzzeit. Wird häufig in Anwendungen eingesetzt, bei denen eine Verzögerung katastrophale Folgen haben könnte.
    - **Beispiele:** Luft- und Raumfahrtsysteme (Flugsteuerung), Industrierobotik, wissenschaftliche Instrumente und einige medizinische Geräte. Viele eingebettete Betriebssysteme haben auch Echtzeitfähigkeiten.

In diesem Programm konzentrieren wir uns in erster Linie auf **Desktop- und Server-Betriebssysteme**, da dies die Umgebungen sind, in denen Cybersicherheitsexperten am häufigsten mit der Sicherung von Systemen, der Analyse von Bedrohungen und der Untersuchung von Vorfällen arbeiten. Für eine ganzheitliche Betrachtung der Computertechnik ist es jedoch wichtig, die Vielfalt der Betriebssystemtypen zu verstehen.

### Denken Sie darüber nach

Warum gibt ein Server-Betriebssystem der Stabilität und Sicherheit den Vorrang vor den neuesten Multimedia-Funktionen, während ein Desktop-Betriebssystem versucht, einen Ausgleich zwischen all diesen Faktoren zu schaffen? Welche Auswirkungen hat es auf die Sicherheit, wenn ein eingebettetes Betriebssystem in einem kritischen Gerät (z. B. dem Bremssystem eines Autos) eine Schwachstelle aufweist?### Versuchen Sie es selbst

1. **Kernel-Prozesse identifizieren:** Öffnen Sie Activity Monitor (Finder > Anwendungen > Dienstprogramme). Klicken Sie auf die Registerkarte "CPU". Versuchen Sie, Prozesse zu erkennen, die für das Betriebssystem grundlegend zu sein scheinen. Vielleicht sehen Sie Prozesse wie `kernel_task`. Was glauben Sie, welche Rolle dieser Prozess aufgrund seines Namens und seiner Ressourcennutzung spielt? (Keine Sorge, wenn das nicht ganz klar ist, wir werden später mehr darüber erfahren!)
2. **Navigieren Sie über CLI:** Öffnen Sie Terminal. Geben Sie `ls` ein und drücken Sie Enter. Dies listet den Inhalt Ihres aktuellen Verzeichnisses auf. Geben Sie `cd Desktop` ein und drücken Sie Enter, um in das Verzeichnis Ihres Desktops zu wechseln. Geben Sie erneut `ls` ein. Was ist der Unterschied zur Verwendung des Finders, um Ihren Desktop zu sehen? Tippen Sie `cd` und drücken Sie die Eingabetaste, um zu Ihrem Heimatverzeichnis zurückzukehren.

## Arten von Betriebssystemen

Betriebssysteme sind vielfältig und können nach verschiedenen Kriterien kategorisiert werden, z. B. nach der Art der Hardware, auf der sie laufen, nach der Anzahl der Benutzer, die sie unterstützen, oder nach der Art der Aufgaben, für die sie entwickelt wurden. Hier sind einige gängige Kategorien:

- **Desktop-Betriebssysteme:**
    - **Zweck:** Sie sind für die Verwendung auf Personalcomputern (Desktops, Laptops) konzipiert. Sie zielen darauf ab, ein reichhaltiges Benutzererlebnis mit einer breiten Palette von Anwendungen für Produktivität, Unterhaltung und allgemeinen Gebrauch zu bieten.
    - **Merkmale:** Sie unterstützen in der Regel jeweils einen einzelnen Benutzer bei interaktiven Aufgaben, bieten eine robuste grafische Benutzeroberfläche, umfangreiche Multimedia-Funktionen und Unterstützung für eine große Anzahl von Peripheriegeräten.
    - **Beispiele:** Apple macOS, Microsoft Windows, Linux-Distributionen (z. B. Ubuntu, Fedora, Mint).
- **Mobile Betriebssysteme:**
    - **Zweck:** Speziell für mobile Geräte wie Smartphones und Tablets entwickelt.
    - **Merkmale:** Optimiert für berührungsbasierte Eingaben, Energieeffizienz (zur Maximierung der Akkulaufzeit), Konnektivität (Wi-Fi, Mobilfunk) und eine breite Palette mobiler Anwendungen ("Apps"). Sie haben oft restriktivere Sicherheitsmodelle als Desktop-Betriebssysteme.
    - **Beispiele:** Apple iOS (für iPhone und iPad), Google Android.
- **Server-Betriebssysteme:**
    - **Zweck:** Entwickelt für den Betrieb auf Server-Hardware, d. h. leistungsstarken Computern, die anderen Computern (Clients) über ein Netzwerk Dienste zur Verfügung stellen. Diese Dienste können Webhosting, E-Mail, Dateifreigabe, Datenbanken und Anwendungshosting umfassen.
    - **Merkmale:** Optimiert für Stabilität, Zuverlässigkeit, Sicherheit und Leistung bei hoher Belastung. Sie unterstützen oft mehrere Benutzer gleichzeitig und sind darauf ausgelegt, über lange Zeiträume ohne Unterbrechung zu laufen. Sie können eine grafische Benutzeroberfläche haben oder auch nicht, da viele Server aus der Ferne über CLI verwaltet werden.
    - **Beispiele:** Linux-Distributionen (z. B. Red Hat Enterprise Linux (RHEL), Ubuntu Server, CentOS), Microsoft Windows Server, UNIX-Varianten wie Solaris.
- **Eingebettete Betriebssysteme:**
    - **Zweck:** Entwickelt, um spezifische, dedizierte Funktionen innerhalb größerer elektronischer oder mechanischer Systeme auszuführen, oft mit sehr begrenzten Hardwareressourcen (CPU-Leistung, Speicher, Storage).
    - **Merkmale:** Hochspezialisiert, kompakt und effizient. Sie müssen extrem zuverlässig sein, da sie oft kritische Funktionen steuern.
    - **Beispiele:** Sie finden sich in einer Vielzahl von Geräten, darunter Autos (Motorsteuergeräte, Infotainmentsysteme), Haushaltsgeräte (intelligente Fernsehgeräte, Waschmaschinen), medizinische Geräte (Herzschrittmacher, Patientenmonitore), industrielle Steuersysteme, Geldautomaten und Wearable Technology. Beispiele sind FreeRTOS, QNX, VxWorks.
- **Echtzeitbetriebssysteme (RTOS):**
	- **Zweck:** Wird in Systemen verwendet, bei denen die zeitliche Abstimmung von Vorgängen kritisch ist. Sie müssen Daten und Ereignisse innerhalb strenger, vorhersehbarer Zeitvorgaben (Fristen) verarbeiten. Die Nichteinhaltung einer Frist kann schwerwiegende Folgen haben.
	- **Merkmale:** Schwerpunkt auf deterministischer Zeitplanung und geringer Latenzzeit. Wird häufig in Anwendungen eingesetzt, bei denen eine Verzögerung katastrophale Folgen haben könnte.
	- **Beispiele:** Luft- und Raumfahrtsysteme (Flugsteuerung), Industrierobotik, wissenschaftliche Instrumente und einige medizinische Geräte. Viele eingebettete Betriebssysteme haben auch Echtzeitfähigkeiten.

In diesem Programm konzentrieren wir uns in erster Linie auf **Desktop- und Server-Betriebssysteme**, da dies die Umgebungen sind, in denen Cybersicherheitsexperten am häufigsten mit der Sicherung von Systemen, der Analyse von Bedrohungen und der Untersuchung von Vorfällen arbeiten. Das Verständnis für die Vielfalt der Betriebssystemtypen ist jedoch wichtig für eine ganzheitliche Betrachtung der Datenverarbeitung.

![[Pasted image 20250930052009.png]]

## Warum ist das Verständnis des Betriebssystems für die Cybersicherheit von entscheidender Bedeutung?

Das Betriebssystem ist nicht nur eine Plattform für die Ausführung von Anwendungen, sondern auch ein wichtiges Schlachtfeld in der Welt der Cybersicherheit. Ein tiefes Verständnis der Betriebssystemprinzipien ist für jeden Cybersicherheitsexperten aus mehreren Gründen unerlässlich:

- **Ziel von Angriffen:** Schwachstellen in Betriebssystemen sind Hauptziele für Angreifer. Das Ausnutzen von Schwachstellen im Kernel, in Systemdiensten oder in Anwendungen, die mit dem Betriebssystem gebündelt sind, kann es Angreifern ermöglichen, unbefugten Zugriff zu erlangen, ihre Privilegien zu erweitern (z. B. von einem normalen Benutzer zu einem Administrator), Malware zu installieren oder sensible Daten zu exfiltrieren.
- **Plattform für Sicherheitstools:** Die meisten Cybersecurity-Tools wie Antiviren-Software, Host-basierte Intrusion Detection/Prevention Systeme (HIDS/HIPS), Firewalls und Endpoint Detection and Response (EDR)-Lösungen arbeiten auf Betriebssystemebene oder stehen in enger Wechselwirkung mit ihr. Das Verständnis des Betriebssystems hilft bei der effektiven Bereitstellung, Konfiguration und Interpretation der Ergebnisse dieser Tools.
- **Forensische Analyse:** Wenn ein Sicherheitsvorfall eintritt, müssen die Ermittler der digitalen Forensik die betroffenen Systeme analysieren. Dazu gehört die Untersuchung von Betriebssystemartefakten wie Protokolldateien, Registrierungseinträgen (unter Windows), Dateisystemstrukturen, Speicherabzügen und laufenden Prozessen, um zu verstehen, was passiert ist, wie das System kompromittiert wurde und welche Daten betroffen waren.
- **Malware-Analyse:** Malware (Viren, Würmer, Trojaner, Ransomware, Spyware) ist speziell darauf ausgelegt, auf bestimmten Betriebssystemen zu laufen und diese auszunutzen. Die Analyse des Verhaltens von Malware (wie sie infiziert, bestehen bleibt, kommuniziert und welchen Schaden sie anrichtet) erfordert ein gründliches Verständnis der Interna des Betriebssystems, z. B. der Prozessverwaltung, der Speicherzuweisung, der Interaktion mit dem Dateisystem und der Netzwerk-APIs.
- **Systemhärtung:** Eine zentrale Praxis der Cybersicherheit ist die "Härtung" von Betriebssystemen, um deren Angriffsfläche zu verringern. Dazu gehört die sichere Konfiguration des Betriebssystems durch die Deaktivierung unnötiger Dienste und Funktionen, die zeitnahe Anwendung von Sicherheits-Patches, die Implementierung starker Zugriffskontrollen und -berechtigungen, die Aktivierung von Verschlüsselung und die Konfiguration von Protokollierung und Auditing.
- **Schwachstellenbewertung und Penetrationstests:** Sicherheitsexperten, die Schwachstellenbewertungen oder Penetrationstests (Ethical Hacking) durchführen, müssen verstehen, wie Betriebssysteme funktionieren, um potenzielle Schwachstellen zu erkennen. Sie untersuchen das Betriebssystem und seine Dienste auf bekannte Schwachstellen, Fehlkonfigurationen und Designfehler.
- **Verstehen von Angreifertechniken:** Viele Angriffstechniken (z. B. Pufferüberläufe, Privilegienerweiterung, Rootkits) zielen speziell auf Betriebssystemmechanismen ab. Zu wissen, wie diese Mechanismen funktionieren, ist der Schlüssel zum Verständnis und zur Verteidigung gegen solche Angriffe.

Im Wesentlichen ist das Betriebssystem die grundlegende Schicht, auf der alle andere Software läuft und auf der wichtige Daten verwaltet werden. Wenn das Betriebssystem angegriffen wird, ist die Sicherheit des gesamten Systems gefährdet.

![[Pasted image 20250930052033.png]]
## Einführung in macOS

Da Sie während dieses Programms mit macOS arbeiten werden, wollen wir einige wichtige Aspekte hervorheben, die für unser Studium relevant sind. macOS ist das Betriebssystem, das von Apple Inc. für seine Mac-Reihe entwickelt wurde.

- **Unix-Erbe:** Eines der wichtigsten Merkmale von macOS ist seine **Unix-ähnliche Grundlage**. Genauer gesagt ist macOS ein zertifiziertes UNIX 03-Betriebssystem, das auf einem Kernsatz von Komponenten und Philosophien aufbaut, die von BSD (Berkeley Software Distribution) Unix abgeleitet sind. Dieses Unix-Erbe bringt mehrere Vorteile mit sich:
    - **Stabilität und Robustheit:** Unix-Systeme sind allgemein für ihre Stabilität bekannt.
    - **Mächtige Befehlszeile:** Zugang zu einer Vielzahl von Befehlszeilentools und Dienstprogrammen, die in allen Unix-ähnlichen Systemen (einschließlich Linux) verwendet werden. Dies ist von unschätzbarem Wert für Entwickler, Systemadministratoren und Cybersicherheitsexperten.
    - **Mehrbenutzerfähigkeiten:** Von Grund auf für die Unterstützung mehrerer Benutzer mit unterschiedlichen Berechtigungen und Umgebungen konzipiert.
    - **Netzwerk-Stack:** Ein ausgereifter und robuster Netzwerk-Stack.
    
- **Schlüsselelemente und Konzepte der Benutzeroberfläche:**
    - **Das Dock:** Das Dock befindet sich in der Regel am unteren oder seitlichen Rand des Bildschirms und bietet schnellen Zugriff auf häufig verwendete Programme, aktuell ausgeführte Programme und minimierte Fenster.
    - **Finder:** Der Standard-Dateimanager in macOS. Mit ihm können Sie Dateien, Ordner, Programme und verbundene Laufwerke durchsuchen. Er ist Ihr wichtigstes Werkzeug, um über die grafische Benutzeroberfläche im Dateisystem zu navigieren.
    - **Systemeinstellungen (oder Systemeinstellungen bei älteren macOS-Versionen):** Dies ist die zentrale Anlaufstelle für die Konfiguration aller Aspekte Ihres Macs, von Anzeige- und Soundeinstellungen bis hin zu Netzwerkkonfigurationen, Benutzerkonten und - ganz wichtig - Sicherheits- und Datenschutzeinstellungen.
    - **Spotlight Search:** Eine leistungsstarke systemweite Suchfunktion (zu erreichen über "Befehl + Leertaste" oder das Lupensymbol in der Menüleiste), mit der Sie schnell Dateien, Programme und E-Mails finden und sogar Berechnungen durchführen oder Definitionen nachschlagen können.
    
- **Eingebaute Sicherheitsfunktionen:** macOS enthält mehrere Sicherheitsebenen zum Schutz der Benutzer und ihrer Daten. Es ist wichtig, diese zu verstehen, um sie zu nutzen und ihre Grenzen zu erkennen:
    - **Gatekeeper:** Verhindert, dass Benutzer versehentlich Malware ausführen, indem es kontrolliert, welche Programme geöffnet werden können. Standardmäßig lässt es Anwendungen aus dem Mac App Store und von identifizierten Entwicklern zu.
    - **XProtect:** Eine Anti-Malware-Technologie, die eine grundlegende signaturbasierte Erkennung und Entfernung von bekannter Malware bietet. Sie arbeitet im Hintergrund.
    - **Systemintegritätsschutz (SIP):** Eine Sicherheitstechnologie, die den "root"-Benutzer-Account (den Superuser mit allen Rechten) einschränkt und die Aktionen begrenzt, die sogar der "root"-Benutzer auf geschützten Teilen des macOS durchführen kann. Dies hilft zu verhindern, dass bösartige Software oder versehentliche Änderungen wichtige Systemdateien und -ordner gefährden.
    - **FileVault:** Bietet eine vollständige Festplattenverschlüsselung für die Startfestplatte Ihres Macs. Wenn sie aktiviert ist, werden Ihre Daten automatisch verschlüsselt und sind ohne das Anmeldekennwort oder einen Wiederherstellungsschlüssel unlesbar. Dies ist entscheidend für den Schutz von Daten, wenn Ihr Mac verloren geht oder gestohlen wird.
    - **Datenschutzkontrollen:** macOS enthält umfangreiche Datenschutzkontrollen (verwaltet in den Systemeinstellungen > Datenschutz und Sicherheit), die Programme dazu verpflichten, Ihre ausdrückliche Erlaubnis einzuholen, bevor sie auf sensible Informationen wie Ihren Standort, Ihre Kontakte, Fotos, Ihr Mikrofon oder Ihre Kamera zugreifen.
    - **Sandboxing:** Programme, vor allem solche aus dem Mac App Store, sind oft "sandboxed". Das bedeutet, dass sie in einer eingeschränkten Umgebung mit begrenztem Zugriff auf Systemressourcen und Benutzerdaten ausgeführt werden, um den potenziellen Schaden zu verringern, wenn eine Anwendung kompromittiert wird.
### Versuchen Sie es selbst

1. **Systemeinstellungen (Sicherheit & Datenschutz) untersuchen:** Öffnen Sie die Systemeinstellungen (oder Systempräferenzen). Navigieren Sie zu "Datenschutz & Sicherheit" (oder "Sicherheit & Datenschutz" bei älteren Versionen).
    - Sehen Sie sich die "Firewall"-Optionen an. Ist sie auf Ihrem System standardmäßig ein- oder ausgeschaltet? (Sie müssen sie jetzt nicht ändern, sondern nur beobachten).
    - Suchen Sie den Abschnitt "FileVault". Ist er aktiviert?
    - Wie lauten unter "Anwendungssicherheit" (oder ähnlich) die aktuellen Einstellungen für das Zulassen von App-Downloads (z. B. "App Store und identifizierte Entwickler")? Dies bezieht sich auf Gatekeeper.
2. **SIP-Status prüfen (optional - erfordert Terminal):**
    - Öffnen Sie das Terminal.
    - Geben Sie den Befehl `csrutil status` ein und drücken Sie Enter.
    - Es wird Ihnen angezeigt, ob der Systemintegritätsschutz aktiviert oder deaktiviert ist. Für fast alle Benutzer sollte er aktiviert sein (und bleiben).

Sie verfügen nun über ein detaillierteres Verständnis der grundlegenden Konzepte von Betriebssystemen, wobei der Schwerpunkt auf macOS liegt. Diese Grundlage wird von entscheidender Bedeutung sein, wenn wir uns eingehender mit der Funktionsweise von Betriebssystemen, ihrer Absicherung und ihren Angriffspunkten in der Cybersicherheitslandschaft beschäftigen.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Operating-Systems-1-Intro-to-OS-yy1lw2suoziakl0?mode=doc](https://gamma.app/docs/Operating-Systems-1-Intro-to-OS-yy1lw2suoziakl0?mode=doc)

Try not to peek before class - spoilers inside!

</aside>