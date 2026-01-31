# Teil 1: Post-Exploitation & Windows Privilege Escalation

## Die 3 Ziele nach dem Einbruch

Nach dem ersten Zugriff auf ein System hat ein Angreifer 3 Hauptziele:

### 1. Persistence (Persistenz)

- **Problem:** Ein Neustart oder Abmelden beendet deine Shell
- **Lösung:** Automatische Mechanismen einrichten
    - Geplante Aufgaben
    - Registry-Schlüssel
    - Autostart-Programme

### 2. Privilege Escalation (Rechte-Erweiterung)

- Von normalem User → Administrator → SYSTEM
- **SYSTEM** = Ultimative Macht (mehr als Admin!)

### 3. Lateral Movement (Netzwerk-Bewegung)

- Von einem Computer zu anderen springen
- Ziel: Wertvollere Systeme (Server, Domain Controller)

---

## Windows Zugriffskontrolle verstehen

### SID (Security Identifier)

**Der wahre Name eines Users**

```
Beispiel: S-1-5-21-12345678-98765432-1001
```

- Username = Spitzname (änderbar)
- SID = echter Name (unveränderlich)
- **Alle Berechtigungen hängen am SID!**

### ACL & ACE

**ACL (Access Control List)**

- Liste von Regeln für ein Objekt (Datei, Ordner)

**ACE (Access Control Entry)**

- Eine einzelne Regel in der Liste
- Verbindet 3 Dinge:
    1. **SID** (wer?)
    2. **Aktion** (Read, Write, Full Control)
    3. **Effekt** (Allow oder Deny)

### Access Token

**Deine digitale ID-Karte**

Enthält:

- Dein SID
- SIDs deiner Gruppen (z.B. Administrators)
- Dein Privilege-Level

**Wichtig:** Jedes Programm erbt eine Kopie deines Tokens!

---

## Die 3 Privilege-Level

### 1. Standard User (Medium Integrity)

- Meistens dein Start nach Exploit
- Kann eigene Dateien nutzen
- ❌ Keine Systemdateien ändern

### 2. Administrator (High Integrity)

- Software installieren
- Systemeinstellungen ändern
- Fast alle Dateien zugreifen

### 3. NT AUTHORITY\SYSTEM (System Integrity)

- **Der ultimative Preis!**
- Mächtiger als Administrator
- Vollständige Kontrolle über alles
- Windows Services laufen als SYSTEM

**Ziel:** Von User → SYSTEM klettern

---

# Teil 2: Active Directory Grundlagen

## Was ist Active Directory?

**Das zentrale Adressbuch + Sicherheitssystem** eines Unternehmens

### Ohne AD:

- 100 Mitarbeiter × 100 Computer = 10.000 Benutzerkonten
- Passwort-Reset auf jeder Maschine einzeln
- **Alptraum!**

### Mit AD:

- 1 Identität für jeden User
- Gilt im ganzen Netzwerk
- Zentrale Verwaltung

---

## AD Kernkomponenten

### 1. Objects (Objekte)

Grundbausteine von AD:

- User (Benutzer)
- Computer
- Groups (Gruppen)
- Printer (Drucker)

Jedes Objekt hat **Attribute** (z.B. Name, E-Mail, Passwort)

### 2. Domain Controller (DC)

**Der Torwächter der Domäne**

Aufgaben:

- Speichert AD-Datenbank
- Authentifizierung (Login prüfen)
- Autorisierung (Rechte prüfen)
- Richtlinien durchsetzen

**Wichtig:** Immer mindestens 2 DCs für Redundanz!

### 3. Domain (Domäne)

Logische Gruppe von:

- Usern
- Computern
- Gemeinsamen Richtlinien

Beispiel: `megacorp.local`

### 4. Organizational Units (OUs)

Container zur Organisation innerhalb einer Domäne

```
megacorp.local
├── Sales OU
├── HR OU
└── IT OU
```

**Wichtiger Unterschied:**

- User kann in **mehreren Gruppen** sein
- Objekt nur in **einer OU** gleichzeitig

---

## AD Skalierung

### Tree (Baum)

Hierarchische Domänen-Struktur:

```
megacorp.local (Root)
├── sales.megacorp.local
└── emea.megacorp.local
```

### Forest (Wald)

- Höchster Container
- Enthält einen oder mehrere Trees
- Alle Domänen teilen:
    - Gemeinsames Schema
    - Vertrauen untereinander

### Trusts (Vertrauen)

**Wie alliierte Länder, die Pässe gegenseitig anerkennen**

- **Standard:** Alle Domänen in einem Forest vertrauen sich
- **Transitiv:** A vertraut B, B vertraut C → A vertraut C automatisch

**Sicherheitsrisiko:** Kompromittierter Admin in Domäne A kann andere Domänen angreifen!

### Global Catalog

- Teilkopie aller Objekte im Forest
- Ermöglicht schnelle Suche
- Enthält wichtigste Attribute (Name, E-Mail)

---

## AD Protokolle

### Kerberos (Authentifizierung)

**Ticket-basiertes System**

**Ablauf:**

1. **Login:** User gibt Passwort ein
2. **TGT erhalten:** DC gibt Ticket Granting Ticket
3. **Service-Zugriff:** User zeigt TGT, bekommt Service Ticket
4. **Ressourcen-Zugriff:** Service Ticket zum Server bringen

**Vorteil:** Passwort wird nur einmal gesendet!

### LDAP (Abfragen)

**Die Sprache für AD-Fragen**

Beispiel-Abfragen:

- "Finde E-Mail von John Smith"
- "Liste alle Domain Admins"
- "Zeige Telefonnummern der Sales OU"

**Sicherheitsrisiko:** Anonyme LDAP-Abfragen = Kompletter Netzwerk-Bauplan für Angreifer!

---

# Teil 3: Windows Credentials Attacks

## Wie Windows Credentials speichert

### Lokale Accounts

**SAM Datenbank (Security Account Manager)**

- Verschlossener Aktenschrank für lokale User
- Speichert: Username + Passwort-Hash

### NTLM Hash

**Nicht das Passwort, sondern der Hash!**

**Prozess:**

1. User erstellt Passwort: `MySuperSecret123!`
2. Windows berechnet NTLM-Hash
3. Hash wird in SAM gespeichert
4. Bei Login: Eingegebenes Passwort hashen → Vergleichen

**Warum trotzdem gefährlich?** Angreifer können Hash knacken durch:

- **Brute-Force:** Alle Kombinationen testen
- **Dictionary-Attacken:** Gängige Passwörter durchprobieren

---

## Domain Credentials

### NTLM in der Domäne

- Für Kompatibilität mit alten Systemen
- Wenn Kerberos nicht verfügbar
- Kommunikation mit Domain Controller

### Kerberos Details

**Key Distribution Center (KDC)**

- Läuft auf Domain Controller
- Zwei Teile:
    1. **Authentication Service** (Wer bist du?)
    2. **Ticket Granting Service** (Tickets ausgeben)

**Der Ablauf:**

**Schritt 1: TGT holen**

```
User → KDC: "Ich bin Max" (verschlüsselt mit Passwort)
KDC → User: "Hier ist dein TGT" (Master-Ticket)
```

**Schritt 2: Service Ticket holen**

```
User → KDC: "Ich will auf Fileserver" (zeigt TGT)
KDC → User: "Hier ist Service Ticket für Fileserver"
```

**Schritt 3: Ressource nutzen**

```
User → Fileserver: "Hier ist mein Service Ticket"
Fileserver: "OK, Zugriff gewährt!"
```

---

## Credential Dumping

**Das Extrahieren von Anmeldeinformationen aus Speicher**

### Gefährliche Fundstellen:

**1. LSASS.exe (Local Security Authority Subsystem Service)**

- Läuft im Speicher
- Enthält:
    - Passwort-Hashes
    - Kerberos Tickets
    - Für alle angemeldeten User

**2. SAM Datenbank**

- Lokale NTLM-Hashes
- Mit Admin-Rechten extrahierbar

**3. Windows Registry**

- Gecachte Credentials
- Sensitive Informationen

---

## Angriffstechniken mit Credentials

### Pass-the-Hash

**Hash direkt nutzen, ohne Passwort!**

```
Angreifer stiehlt: aad3b435b51404eeaad3b435b51404ee
Angreifer nutzt Hash → Login erfolgreich!
```

**Analogie:** NTLM-Hash = Keycard. Passwort = PIN für Keycard. Mit Keycard alle Türen öffnen, ohne PIN!

### Pass-the-Ticket

**Kerberos-Version von Pass-the-Hash**

```
Angreifer stiehlt: TGT oder Service Ticket
Angreifer injiziert Ticket → Zugriff als User!
```

**Analogie:** Festival-Armband gestohlen → Alle Stages besuchen wie der echte Besitzer

---

## Mimikatz – Das Super-Tool

**Open-Source Post-Exploitation Tool**

### Kann extrahieren:

1. **Klartext-Passwörter** (bei alten Systemen)
2. **NTLM-Hashes** → Pass-the-Hash
3. **Kerberos Tickets** → Pass-the-Ticket
4. **PINs** und mehr

### Warum so effektiv?

- Nutzt keine Software-Schwachstelle aus
- Nutzt Windows-Design selbst aus
- Liest aus LSASS-Speicher

### Einsatz für:

- **Lateral Movement** (von Maschine zu Maschine)
- **Privilege Escalation** (höhere Rechte)
- **Persistence** (Golden Tickets)

---

# Teil 4: Windows Lateral Movement

## Der Angriffspfad

```
Beachhead (Erster PC)
    ↓
Lateral Movement
    ↓
Wertvollere Ziele (Server, Datenbanken)
    ↓
Domain Controller (Jackpot!)
```

**Ziel:** Nicht ein PC, sondern das ganze Netzwerk!

---

## Lateral Movement Techniken

### 1. Pass-the-Hash (Wiederholung)

**Nutzt NTLM-Hashes für Remote-Login**

```
1. Hash von User dumpen
2. Hash an remote System senden
3. Remote System: "Hash stimmt, rein!"
```

**Kein Passwort-Cracking nötig!**

### 2. Pass-the-Ticket (Wiederholung)

**Nutzt Kerberos-Tickets**

```
1. TGT/Service Ticket aus Speicher stehlen
2. Ticket in eigene Session injizieren
3. Als User auf Ressourcen zugreifen
```

---

## Execution Tools

### PsExec

**Microsoft-Tool für Remote-Befehle**

**Wie es funktioniert:**

1. Verbindet zu `ADMIN$` Share via SMB (Port 445)
2. Lädt `PSEXESVC.exe` hoch
3. Startet Service via RPC
4. Gibt Command-Shell

**Vorteil für Angreifer:**

- Legitimes Microsoft-Tool
- Signiert
- Kein automatischer Alarm

### Windows Management Instrumentation (WMI)

**Eingebautes Windows-Management-Tool**

**Beispiel:**

```
wmic /node:TARGET_IP /user:USER /password:PASS 
process call create cmd.exe
```

**Vorteil:**

- **Fileless** (kein Binary auf Festplatte)
- Nutzt existierende Windows-Komponenten
- Sehr stealthy

### RDP (Remote Desktop Protocol)

**Die einfachste Methode**

```
1. Gültige Credentials haben
2. RDP-Client öffnen
3. IP + Credentials eingeben
4. Volle Desktop-Session!
```

**Nachteil:**

- Sehr "noisy" (auffällig)
- Event ID 4624 in Logs
- User sieht Session-Kick

---

## Praxis-Beispiel: SMB + WMI

**Simulation eines Angriffs:**

```bash
# 1. Payload erstellen
echo calc.exe > C:\Windows\Temp\payload.bat

# 2. Via WMI ausführen
wmic process call create C:\Windows\Temp\payload.bat
```

**Das simuliert:**

- Tool über SMB kopieren
- Remote ausführen

---

# Teil 5: Active Directory Angriffe

## Der AD-Angriffs-Lebenszyklus

```
1. Initial Access (Foothold)
   ↓
2. Enumeration (Erkundung)
   ↓
3. Credential Harvesting
   ↓
4. Lateral Movement
   ↓
5. Privilege Escalation
   ↓
6. Persistence
```

---

## Initiale Credential-Attacken

### AS-REP Roasting

**Nutzt falsch konfigurierte User-Accounts aus**

**Voraussetzung:**

- User mit Flag: "Do not require Kerberos preauthentication"

**Ablauf:**

1. Angreifer identifiziert solche Accounts
2. Sendet AS-REQ für User
3. DC sendet AS-REP mit TGT (verschlüsselt mit User-Hash)
4. Angreifer fängt ab und crackt Hash offline

**Warum gefährlich?**

- Keine Authentifizierung nötig
- Offline-Cracking möglich

---

## Enumeration mit BloodHound

**Graph-basiertes AD-Analyse-Tool**

### Wichtige Konzepte:

**Nodes (Knoten):**

- User
- Computer
- Gruppen
- Group Policy Objects (GPOs)

**Edges (Beziehungen):**

- `MemberOf` → User in Gruppe
- `AdminTo` → Admin-Rechte auf Computer
- `HasSession` → Aktive Session
- `CanRDP` → RDP-Zugriff möglich

**Attack Paths:** BloodHound findet automatisch Wege von deinem User zu Domain Admin!

### Beispiel-Query:

"Welche User können direkt einen DC administrieren?"

---

## Privilege Escalation

### Kerberoasting

**Zielt auf Service-Accounts ab**

**Was sind Service-Accounts?**

- Für Dienste (SQL Server, Web-Apps)
- Haben Service Principal Name (SPN)
- Oft mit schwachen Passwörtern!

**Ablauf:**

1. Als normaler User: Service Ticket für SPN anfordern
2. DC verschlüsselt Ticket mit Service-Account-Hash
3. Ticket abfangen
4. Hash offline cracken

**Warum effektiv?**

- Jeder authentifizierte User kann es machen
- Service-Accounts haben oft Admin-Rechte
- Schwache Passwörter häufig

---

## Persistence-Techniken

### Golden Ticket Attack

**Die ultimative Persistence!**

**Was ist das?** Gefälschtes Ticket Granting Ticket (TGT)

**Voraussetzung:** NTLM-Hash des `krbtgt`-Accounts

**Was ist krbtgt?**

- Spezieller Service-Account
- Verschlüsselt ALLE Kerberos-Tickets
- **Kompromittierung = Komplette Domänen-Kontrolle**

**Ablauf:**

1. `krbtgt`-Hash erbeuten (DC kompromittieren)
2. Gefälschtes TGT erstellen
3. Beliebige Gültigkeit setzen (Jahre!)
4. Beliebige Gruppen zuweisen (Domain Admins)
5. TGT injizieren
6. **Vollzugriff auf alles!**

**Warum so mächtig?**

- Domain-weiter Zugriff
- Lange Gültigkeit
- Als jeden User agieren
- Schwer zu erkennen

### Silver Ticket Attack

**Gezielte Service-Persistence**

**Unterschied zu Golden Ticket:**

- Zielt auf **einen spezifischen Service**
- Nicht domain-weit
- Braucht Service-Account-Hash (nicht krbtgt)

**Ablauf:**

1. Service-Account-Hash stehlen (z.B. SQL Service)
2. Gefälschtes Service Ticket (TGS) erstellen
3. TGS injizieren
4. Zugriff auf diesen Service

**Vorteil:**

- Kein DC-Kontakt nötig
- Schwerer zu erkennen
- Gezieltere Kontrolle

---

## Group Policy Objects (GPOs)

**Zentrale Konfigurations- und Sicherheits-Verwaltung**

### Was sind GPOs?

- Verwalten Einstellungen für viele Computer
- Können:
    - Sicherheitsrichtlinien durchsetzen
    - Software installieren
    - User-Rechte verwalten

### GPO-Angriffsvektoren:

**1. Schwache GPO-Berechtigungen**

- Angreifer bekommt Schreibzugriff
- Kann GPO modifizieren
- Malicious Scripts deployen

**2. Startup Scripts**

- GPO kann Scripts bei Start ausführen
- Mit erhöhten Rechten!
- Perfekte Persistence

**3. Immediate Tasks**

- Tasks sofort ausführen
- Auf vielen Maschinen gleichzeitig

**4. Restricted Groups**

- Fehlkonfiguration kann Admin-Rechte geben

---

# Schnell-Referenz

## Die 3 Post-Exploitation Ziele

1. **Persistence** → Zugriff behalten
2. **Privilege Escalation** → User → Admin → SYSTEM
3. **Lateral Movement** → Von PC zu PC

## Windows Zugriff

- **SID** = Echter User-Name (unveränderlich)
- **Token** = Digitale ID-Karte (enthält SID + Gruppen)
- **ACL/ACE** = Berechtigungslisten

## AD Kernkonzepte

- **DC** = Torwächter (Authentifizierung)
- **Domain** = Logische Gruppe
- **Forest** = Höchster Container
- **Kerberos** = Ticket-System
- **LDAP** = Abfrage-Sprache

## Credential Attacks

- **NTLM Hash** = Passwort-Hash
- **Pass-the-Hash** = Hash statt Passwort nutzen
- **Pass-the-Ticket** = Kerberos-Ticket stehlen
- **Mimikatz** = Super-Tool zum Credential-Dumping

## Lateral Movement Tools

- **PsExec** = Remote-Befehle (legitimes Tool)
- **WMI** = Fileless Remote-Execution
- **RDP** = Remote Desktop (einfach, aber laut)

## AD Angriffe

- **AS-REP Roasting** = Schwache User ohne Preauth
- **Kerberoasting** = Service-Account-Hashes cracken
- **BloodHound** = AD-Beziehungen visualisieren
- **Golden Ticket** = Vollzugriff (braucht krbtgt-Hash)
- **Silver Ticket** = Service-Zugriff (braucht Service-Hash)

## Wichtige Accounts

- **SYSTEM** = Mächtiger als Admin
- **krbtgt** = Master-Key für alle Kerberos-Tickets
- **Domain Admin** = Höchste Domänen-Rechte

## Kritische Prozesse

- **LSASS.exe** = Enthält Credentials im Speicher
- **SAM** = Lokale Passwort-Datenbank

---

# Verteidigungsstrategien (Bonus)

## Gegen Credential Dumping

- Credential Guard aktivieren
- Protected Users Gruppe nutzen
- LSA Protection einschalten
- Regelmäßig krbtgt-Hash ändern

## Gegen Lateral Movement

- Least Privilege Prinzip
- Admin-Accounts trennen
- Network Segmentation
- Monitor Event ID 4624 (RDP-Login)

## Gegen Golden/Silver Tickets

- krbtgt-Hash regelmäßig ändern (2×!)
- Ticket-Lebensdauer begrenzen
- Anomale Ticket-Requests monitoren

## GPO-Sicherheit

- GPO-Berechtigungen restriktiv setzen
- GPO-Änderungen auditieren
- Delegierung minimieren

---

# Wichtige Ports

```
445  → SMB (File Sharing, PsExec)
3389 → RDP (Remote Desktop)
88   → Kerberos
389  → LDAP
636  → LDAPS (LDAP Secure)
135  → RPC (Remote Procedure Call)
```

---

# Event IDs zum Monitoring

```
4624 → Erfolgreicher Login
4625 → Fehlgeschlagener Login
4672 → Admin-Rechte zugewiesen
4768 → Kerberos TGT angefordert
4769 → Kerberos Service Ticket angefordert
4776 → NTLM-Authentifizierung
```

---

**Tipp zum Lernen:**

1. Verstehe die **Beziehungen** zwischen Konzepten
2. Denke wie ein **Angreifer UND Verteidiger**
3. Jede Attacke hat eine **Gegenmaßnahme**
4. **Praktiziere** in einem Lab (nicht in Produktion!)

**Erfolg beim Lernen!** 🎯🔒