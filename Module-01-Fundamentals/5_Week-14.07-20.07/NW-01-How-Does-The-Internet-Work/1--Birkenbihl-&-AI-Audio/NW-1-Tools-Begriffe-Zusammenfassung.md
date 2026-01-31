| Begriff                                           | Bedeutung                                                                                                                                                                |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Verwendete Tools**                              |                                                                                                                                                                          |
| Eingabeaufforderung (cmd) oder Windows PowerShell | Die Kommandozeilen-Anwendung auf Windows 11, über die man Befehle direkt an den Computer eingeben kann. Öffnen mit Windows-Taste, dann „cmd" oder „PowerShell" eingeben. |
| Ping                                              | Ein Befehl, der ein kleines Datenpaket an einen Zielcomputer sendet und auf Antwort wartet, um die Erreichbarkeit und Latenz zu prüfen. Befehl: ping www.google.com      |
| ipconfig                                          | Ein Befehl, der die Netzwerkkonfiguration des eigenen Computers anzeigt, einschließlich der lokalen IP-Adresse. Ersetzt den macOS-Befehl ifconfig.                       |
| Windows-Suche                                     | Die Suchfunktion auf Windows 11, die mit der Windows-Taste aufgerufen wird                                                                                               |
| Steuerung und C                                   | Tastenkombination zum Abbrechen eines laufenden Befehls in der Eingabeaufforderung                                                                                       |
| **Technische Fachbegriffe**                       |                                                                                                                                                                          |
| DNS (Domain Name System)                          | System, das Webseiten-Namen wie www.google.com in IP-Adressen übersetzt                                                                                                  |
| TCP (Transmission Control Protocol)               | Protokoll, das eine zuverlässige Verbindung zwischen Client und Server herstellt                                                                                         |
| HTTP/HTTPS                                        | Protokoll zur Übertragung von Webseiten-Inhalten, HTTPS ist die verschlüsselte Variante über Port 443                                                                    |
| IP-Adresse                                        | Eine eindeutige Zahlenreihe, die ein Gerät im Netzwerk identifiziert und lokalisiert                                                                                     |
| IPv4                                              | Eine Version des Internet-Protokolls mit Adressen im Format wie 172.217.160.142                                                                                          |
| Port                                              | Eine Nummer, die einen bestimmten Dienst auf einem Server kennzeichnet, zum Beispiel Port 443 für HTTPS                                                                  |
| Pakete                                            | Kleine Dateneinheiten, in die Informationen für die Übertragung im Netzwerk aufgeteilt werden                                                                            |
| Firewall                                          | Ein Sicherheitssystem, das den Datenverkehr filtert und kontrolliert                                                                                                     |
| Latenz                                            | Die Zeit, die ein Signal für den Hin- und Rückweg durch das Netzwerk benötigt, gemessen in Millisekunden                                                                 |
| Internet-Backbone                                 | Das Hauptnetzwerk aus leistungsstarken Kernroutern, das den globalen Internetverkehr trägt                                                                               |
| **Wichtige Vokabeln**                             |                                                                                                                                                                          |
| Netzwerk                                          | Zwei oder mehr Computer, die miteinander verbunden sind, um Ressourcen oder Informationen zu teilen                                                                      |
| Internet                                          | Ein riesiges globales Netzwerk aus Netzwerken, das Milliarden von Geräten weltweit verbindet                                                                             |
| Client                                            | Ein Gerät oder Programm, das Informationen oder Dienste von einem Server anfordert                                                                                       |
| Server                                            | Ein leistungsstarker Computer oder Programm, das Informationen oder Dienste für Clients bereitstellt                                                                     |
| Router                                            | Ein Netzwerkgerät, das den Datenverkehr zwischen verschiedenen Netzwerken lenkt und weiterleitet                                                                         |
| ISP (Internet Service Provider)                   | Ein Unternehmen wie Deutsche Telekom oder Vodafone, das Internetzugang bereitstellt                                                                                      |
| Lokale IP-Adresse                                 | Die interne Adresse eines Geräts im Heimnetzwerk, zum Beispiel 192.168.1.x oder 10.0.0.x                                                                                 |
| Öffentliche IP-Adresse                            | Die Adresse, mit der das gesamte Heimnetzwerk im Internet sichtbar ist                                                                                                   |
| WLAN                                              | Drahtloses lokales Netzwerk zur Verbindung von Geräten ohne Kabel                                                                                                        |
| Netzwerkadapter                                   | Die Verbindungsstelle eines Windows-Computers zum Netzwerk, sichtbar unter den Netzwerkverbindungen                                                                      |

---

## Zusammenfassung nach dem 80/20-Prinzip

Die 20 Prozent des Wissens, die 80 Prozent des Verständnisses liefern:

**Das Grundprinzip:** Das Internet funktioniert nach dem Client-Server-Modell. Dein Gerät (Client) stellt Anfragen, und ein anderer Computer (Server) liefert die gewünschten Daten zurück. Dieses einfache Prinzip liegt allem zugrunde, was du online tust, ob Webseiten, E-Mails, Streaming oder Online-Spiele.

**Die drei Schlüsselkomponenten:** Erstens brauchst du eine IP-Adresse als eindeutige Kennung deines Geräts im Netzwerk, vergleichbar mit deiner Hausadresse. Zweitens leiten Router deine Daten von Netzwerk zu Netzwerk, bis sie ihr Ziel erreichen, wie intelligente Postämter. Drittens verbindet dein Internetanbieter (ISP) dein Heimnetzwerk mit dem globalen Internet und ist dein Tor zur Online-Welt.

**Der Ablauf einer Webseiten-Anfrage:** Wenn du eine Adresse wie www.google.com eingibst, übersetzt DNS diesen Namen in eine IP-Adresse. Dein Browser baut eine TCP-Verbindung auf und sendet eine HTTP-Anfrage. Diese reist als kleine Datenpakete durch deinen Router, über das Netzwerk deines Internetanbieters, durch Kernrouter im Internet-Backbone zum Zielserver. Die Antwort nimmt den Rückweg, und dein Browser setzt die Pakete wieder zusammen.

**Praktische Überprüfung unter Windows 11:** Öffne die Eingabeaufforderung über die Windows-Suche und gib cmd ein. Mit dem Befehl ping www.google.com testest du, ob ein Server erreichbar ist und wie hoch die Latenz ist. Drücke Steuerung und C zum Beenden. Mit dem Befehl ipconfig siehst du deine eigene Netzwerkkonfiguration. Suche nach dem Eintrag IPv4-Adresse unter deinem aktiven Netzwerkadapter, um deine lokale IP-Adresse zu finden.