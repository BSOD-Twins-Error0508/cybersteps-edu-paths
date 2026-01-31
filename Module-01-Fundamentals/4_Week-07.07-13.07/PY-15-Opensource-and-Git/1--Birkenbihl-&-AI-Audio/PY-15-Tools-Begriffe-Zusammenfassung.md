# Python Lektion 15: Open Source, Git & GitHub

## Kategorisierung der Themen

|Kategorie|Begriff|Bedeutung|
|---|---|---|
|**Verwendete Tools**|Git|Verteiltes Versionskontrollsystem für Code-Verwaltung|
||GitHub|Online-Plattform zum Hosten und Kollaborieren an Git-Projekten|
||Terminal/Command Line|Kommandozeilen-Interface für Git-Befehle (Windows: CMD, PowerShell, Git Bash)|
||Git Bash (Windows)|Unix-ähnliche Kommandozeile für Git auf Windows|
||Text Editor|Zum Bearbeiten von Code und Commit-Nachrichten|
||Web Browser|Zum Zugriff auf GitHub.com|
|**Technische Fachbegriffe**|Open Source Software (OSS)|Software mit öffentlich zugänglichem Quellcode|
||Proprietary Software|Geschlossene Software mit geheimem Quellcode|
||Source Code (Quellcode)|Menschen-lesbarer Programmcode|
||Version Control System (VCS)|System zur Verfolgung von Code-Änderungen|
||Distributed VCS|Jeder Entwickler hat vollständige Projekt-Historie|
||Repository (Repo)|Projekt-Ordner mit vollständiger Git-Historie|
||Remote Repository|Online-gehostetes Repository (z.B. auf GitHub)|
||Local Repository|Git-Repository auf lokalem Computer|
||Commit|Gespeicherter Snapshot des Projektzustands|
||Branch (Zweig)|Separate Entwicklungslinie im Projekt|
||Main/Master Branch|Haupt-Entwicklungszweig|
||Merge|Zusammenführen von Branches|
||Checkout|Wechsel zu anderem Branch oder Commit|
||Clone|Kopieren eines Remote-Repositories auf lokalen Computer|
||Push|Hochladen lokaler Commits zu Remote-Repository|
||Pull|Herunterladen von Änderungen aus Remote-Repository|
||Pull Request (PR)|Formale Anfrage, Änderungen in Projekt einzubringen|
||Issue|Verfolgung von Bugs und Feature-Anfragen|
||Fork|Persönliche Kopie eines fremden Repositories|
||License (Lizenz)|Rechtliche Bedingungen für Nutzung/Verteilung|
||Collaboration (Zusammenarbeit)|Gemeinsames Arbeiten an Projekten|
||Code Review|Überprüfung von Code durch andere Entwickler|
||Transparency (Transparenz)|Offenlegung von Quellcode|
||Community|Gemeinschaft von Entwicklern und Nutzern|
|**Wichtige Vokabeln**|`git --version`|Zeigt installierte Git-Version|
||`git config --global user.name`|Setzt Git-Benutzernamen|
||`git config --global user.email`|Setzt Git-E-Mail-Adresse|
||`git init`|Initialisiert neues Git-Repository|
||`git status`|Zeigt Status des Working Directory|
||`git add`|Fügt Dateien zur Staging Area hinzu|
||`git commit`|Erstellt Commit mit Snapshot|
||`git log`|Zeigt Commit-Historie|
||`git branch`|Verwaltet Branches|
||`git checkout`|Wechselt Branch oder stellt alte Version wieder her|
||`git merge`|Führt Branches zusammen|
||`git clone`|Klont Remote-Repository|
||`git push`|Lädt Commits zu Remote hoch|
||`git pull`|Holt Änderungen von Remote|
||Commit Message|Beschreibung der Änderungen im Commit|
||Working Directory|Aktueller Arbeitsordner mit Dateien|
||Staging Area|Zwischenbereich vor Commit|
||.git Folder|Versteckter Ordner mit Git-Daten|
||README.md|Projekt-Beschreibungsdatei (Markdown)|
||.gitignore|Datei mit zu ignorierenden Dateien|

---

## Anpassungen für Windows 11 (statt macOS)

|macOS|Windows 11|
|---|---|
|**Terminal öffnen:** Applications > Utilities > Terminal|**CMD/PowerShell:** Windows-Taste → "cmd" oder "powershell" eingeben|
|**Oder:** Spotlight → "Terminal"|**Oder:** Git Bash (empfohlen nach Git-Installation)|
|**Git installieren:** Command Line Developer Tools oder git-scm.com|**Git installieren:** https://git-scm.com/download/win|
|`git --version` prüfen|`git --version` prüfen (in CMD, PowerShell oder Git Bash)|
|Terminal-Befehle: Unix-basiert|**Git Bash:** Unix-ähnliche Befehle (empfohlen)|
||**CMD/PowerShell:** Windows-Befehle (funktioniert, aber Git Bash besser)|
|Pfadtrennzeichen: `/`|Pfadtrennzeichen: `\` (Git Bash akzeptiert beide)|

**Wichtig für Windows:**

- **Git Bash installieren:** Kommt mit Git für Windows (bei Installation Option "Git Bash Here" anhaken)
- **Git Bash verwenden:** Rechtsklick im Ordner → "Git Bash Here"
- **Alternative:** Visual Studio Code integriertes Terminal (empfohlen!)

**Installation auf Windows 11:**

1. Download: https://git-scm.com/download/win
2. Installer ausführen
3. Wichtige Optionen:
    - "Git Bash Here" aktivieren
    - "Git from the command line and also from 3rd-party software"
    - Default Editor nach Wahl (VS Code empfohlen)
4. Nach Installation: Git Bash oder VS Code Terminal öffnen
5. Konfiguration wie im Text beschrieben

---

## Zusammenfassung nach dem 80/20-Prinzip

### Die 20% Kernwissen, die 80% der praktischen Anwendung abdecken:

---

## **TEIL 1: OPEN SOURCE – DIE PHILOSOPHIE**

### **1. Was ist Open Source?**

**Definition:**

- **Quellcode ist öffentlich** zugänglich
- Jeder kann Code **sehen, ändern, teilen**
- Basiert auf **Transparenz** und **Gemeinschaft**

**Gegenteil: Proprietary (Geschlossen)**

- Code ist geheim (z.B. Windows, Photoshop)
- Nur Hersteller kann ändern
- "Blackbox"-Ansatz

---

**Bekannte Open Source Beispiele:**

- **Linux** (Betriebssystem)
- **Python** (Programmiersprache!)
- **Firefox** (Browser)
- **Android** (Mobil-OS, basiert auf Linux)
- **Nmap** (Netzwerk-Scanner)
- **Wireshark** (Packet-Analyse)
- **Metasploit** (Penetration Testing)

---

### **2. Die 3 Freiheiten von Open Source**

**1. Studieren**

```python
# Du kannst sehen, WIE ein Tool funktioniert
# Beispiel: Nmap Quellcode auf GitHub ansehen
# → Lerne von den Besten!
```

**2. Modifizieren**

```python
# Funktioniert fast, aber nicht ganz?
# → Ändere es selbst!
# Beispiel: Security-Script für dein Netzwerk anpassen
```

**3. Teilen**

```python
# Verbesserung gemacht?
# → Teile mit der Community!
# → Andere profitieren, du baust Reputation auf
```

---

### **3. Warum Open Source in Cybersecurity?**

**1. Vertrauen durch Transparenz**

```
Closed Source: "Vertrau uns, es ist sicher" 🤷
Open Source: "Hier ist der Code, prüf selbst" ✅
```

**2. Sicherheit durch "Viele Augen"**

- Tausende Entwickler weltweit prüfen Code
- Fehler werden schneller gefunden
- "Many eyes make all bugs shallow"

**3. Anpassbarkeit**

- Tool macht fast was du brauchst?
- Ändere es für deine Bedürfnisse

**4. Lernen**

- Beste Lernquelle: Code von Profis lesen
- Verstehe, wie echte Tools funktionieren

---

## **TEIL 2: VERSIONSKONTROLLE – DAS PROBLEM**

### **4. Das Chaos ohne Versionskontrolle**

**Szenario 1: Solo-Entwicklung**

```
projekt_final.py
projekt_final_v2.py
projekt_final_v2_wirklich_final.py
projekt_final_v2_wirklich_final_diesmal_echt.py
projekt_final_NEU.py
```

- Welche Version funktioniert?
- Was war der Unterschied?
- Wie zurück zur funktionierenden Version?

---

**Szenario 2: Team-Arbeit**

```
Alice: projekt_v1.py
  ↓ (E-Mail an Bob)
Bob: projekt_v2.py (ändert Funktion A)
  ↓ (E-Mail zurück)
Alice: projekt_v3.py (ändert gleichzeitig Funktion B)

Wie kombinieren? 😱
```

**Probleme:**

- ❌ Änderungen gehen verloren
- ❌ Konflikte beim Zusammenführen
- ❌ Keine Rückverfolgung, wer was geändert hat
- ❌ Kein einfaches "Zurück" zur alten Version

---

## **TEIL 3: GIT – DIE LÖSUNG**

### **5. Was ist Git?**

**Git = Zeitmaschine für deinen Code**

- Erstellt von **Linus Torvalds** (Linux-Erfinder)
- **Verteiltes** System (jeder hat vollständige Historie)
- Schnell, flexibel, mächtig
- Industrie-Standard

**Metapher:**

- Git = Detailliertes Labor-Notizbuch
- Jede Änderung wird aufgezeichnet
- Jederzeit zurückblättern möglich

---

### **6. Git-Grundkonzepte**

**1. Repository (Repo)**

- Projektordner mit Git-Historie
- Enthält `.git` Ordner (versteckt)

**2. Commit**

- Snapshot/Foto des gesamten Projekts zu bestimmtem Zeitpunkt
- Mit Beschreibung: "Was wurde geändert?"

**3. Branch**

- Separate Entwicklungslinie
- `main` = Haupt-Branch
- Feature-Branches für neue Features

**4. Merge**

- Zusammenführen von Branches

---

### **7. Git-Workflow visualisiert**

```
Working Directory     Staging Area         Repository
(Deine Dateien)       (Vorbereitung)      (Commits)
     
     [file.py] -----> git add -----> [file.py] -----> git commit -----> [Commit]
                                                                          ↓
                                                                    Historie
```

**Die 3 Bereiche:**

1. **Working Directory:** Wo du arbeitest
2. **Staging Area:** Vorbereitung für Commit (was soll gespeichert werden?)
3. **Repository:** Gespeicherte Commits (Historie)

---

### **8. Grundlegende Git-Befehle**

**Setup (einmalig):**

```bash
# Git-Identität setzen
git config --global user.name "Dein Name"
git config --global user.email "deine@email.com"

# Version prüfen
git --version
```

**Repository erstellen:**

```bash
# Neues Git-Repo initialisieren
git init

# Status anzeigen
git status
```

**Änderungen speichern:**

```bash
# Dateien zur Staging Area hinzufügen
git add datei.py          # Einzelne Datei
git add .                 # Alle Dateien

# Commit erstellen
git commit -m "Beschreibung der Änderung"

# Historie anzeigen
git log
git log --oneline         # Kompakte Ansicht
```

---

### **9. Praktisches Beispiel: Erste Schritte**

```bash
# 1. Ordner erstellen und hineinwechseln
mkdir mein_projekt
cd mein_projekt

# 2. Git initialisieren
git init
# Output: Initialized empty Git repository in ...

# 3. Datei erstellen
echo "print('Hallo Welt')" > hallo.py

# 4. Status prüfen
git status
# Output: Untracked files: hallo.py

# 5. Zur Staging Area hinzufügen
git add hallo.py

# 6. Status erneut prüfen
git status
# Output: Changes to be committed: new file: hallo.py

# 7. Commit erstellen
git commit -m "Erste Version: Hallo Welt Programm"

# 8. Historie ansehen
git log
# Zeigt: Commit-ID, Autor, Datum, Nachricht
```

---

### **10. Branches – Parallele Entwicklung**

**Warum Branches?**

- Experimentiere ohne Hauptcode zu gefährden
- Arbeite an Features isoliert
- Mehrere Entwickler arbeiten parallel

```bash
# Neuen Branch erstellen und wechseln
git checkout -b feature-login

# Änderungen machen...
echo "def login(): pass" > login.py
git add login.py
git commit -m "Login-Feature hinzugefügt"

# Zurück zu main
git checkout main

# Feature-Branch mergen
git merge feature-login
```

**Visualisierung:**

```
main:     [A] ──────────────── [D (merge)]
                    ↘              ↗
feature:              [B] ── [C]
```

---

## **TEIL 4: GITHUB – DIE ONLINE-PLATTFORM**

### **11. Was ist GitHub?**

**GitHub = Social Network für Code**

- Online-Plattform für Git-Repositories
- **Remote Repository** (in der Cloud)
- Kollaborations-Features
- Portfolio für Entwickler

**Hauptfunktionen:**

1. **Code hosten** (Backup + Zugriff überall)
2. **Zusammenarbeiten** (Pull Requests, Issues)
3. **Entdecken** (Millionen Open Source Projekte)
4. **Lernen** (Code von anderen ansehen)
5. **Profil aufbauen** (lebendes Portfolio)

---

### **12. GitHub-Grundkonzepte**

**1. Remote Repository**

- Repository auf GitHub-Servern
- Zentraler Ort für Zusammenarbeit

**2. Clone**

- Kopiert Remote-Repo auf lokalen Computer

```bash
git clone https://github.com/username/repository.git
```

**3. Push**

- Lädt lokale Commits zu GitHub hoch

```bash
git push origin main
```

**4. Pull**

- Holt Änderungen von GitHub

```bash
git pull origin main
```

**5. Pull Request (PR)**

- Formale Anfrage: "Ich möchte diese Änderungen einbringen"
- Code-Review möglich
- Diskussion über Änderungen

**6. Issues**

- Bug-Tracking
- Feature-Anfragen
- Diskussionen

**7. Fork**

- Persönliche Kopie eines fremden Repos
- Basis für eigene Änderungen

---

### **13. GitHub-Workflow**

```
Lokaler Computer                    GitHub (Remote)
     
[Lokales Repo] ────── git push ────→ [Remote Repo]
       ↑                                    ↓
       └──────────── git pull ──────────────┘
                                            
                                        [Fork]
                                            ↓
                                    [Pull Request]
```

**Typischer Ablauf:**

1. Repository auf GitHub erstellen
2. Lokal clonen: `git clone`
3. Änderungen machen und committen
4. Zu GitHub pushen: `git push`
5. Auf GitHub: Pull Request erstellen (bei Team-Projekten)

---

### **14. GitHub-Account erstellen**

**Schritte:**

1. Gehe zu https://github.com
2. "Sign up" klicken
3. **Username:** Professionell wählen (wird öffentlich sichtbar!)
4. **E-Mail:** Verwende gleiche wie bei `git config`
5. E-Mail verifizieren
6. Profil vervollständigen (optional aber empfohlen)

**Profil-Tipps:**

- ✅ Klares Profilbild
- ✅ Bio mit Fähigkeiten
- ✅ Link zu Portfolio/LinkedIn
- ✅ Pinned Repositories (beste Projekte zeigen)

---

## **TEIL 5: GIT + GITHUB ZUSAMMEN**

### **15. Erstes Projekt auf GitHub**

**Lokales Projekt zu GitHub:**

```bash
# 1. Auf GitHub: Neues Repository erstellen
#    → "New" Button
#    → Name: "mein-erstes-projekt"
#    → Public oder Private wählen
#    → NICHT "Initialize with README" (schon lokal vorhanden)

# 2. Lokal: Remote hinzufügen
git remote add origin https://github.com/username/mein-erstes-projekt.git

# 3. Ersten Push (zu GitHub hochladen)
git push -u origin main

# 4. Auf GitHub refreshen → Code ist online! 🎉
```

**Zukünftige Pushes:**

```bash
# Änderungen machen
git add .
git commit -m "Feature XYZ hinzugefügt"
git push  # Kurz, weil -u origin main schon gesetzt
```

---

### **16. Fremdes Projekt clonen und beitragen**

**Workflow:**

```bash
# 1. Auf GitHub: Interessantes Projekt finden

# 2. Forken (eigene Kopie erstellen)
#    → "Fork" Button auf GitHub

# 3. Lokal clonen
git clone https://github.com/DEIN-USERNAME/projekt-name.git
cd projekt-name

# 4. Änderungen machen
# ... Code bearbeiten ...
git add .
git commit -m "Bug in Funktion X behoben"

# 5. Zu deinem Fork pushen
git push origin main

# 6. Auf GitHub: Pull Request erstellen
#    → "New Pull Request"
#    → Beschreibung der Änderung
#    → Original-Autor kann Review machen und mergen
```

---

## **PRAKTISCHE BEISPIELE**

### **17. Beispiel 1: Python-Projekt mit Git**

```bash
# Projekt-Setup
mkdir password-generator
cd password-generator
git init

# Erste Version
cat > generator.py << 'EOF'
import random
import string

def generate_password(length=12):
    characters = string.ascii_letters + string.digits
    return ''.join(random.choice(characters) for _ in range(length))

if __name__ == "__main__":
    print(generate_password())
EOF

git add generator.py
git commit -m "Initial commit: Basic password generator"

# Feature hinzufügen: Sonderzeichen
cat > generator.py << 'EOF'
import random
import string

def generate_password(length=12, special_chars=True):
    characters = string.ascii_letters + string.digits
    if special_chars:
        characters += string.punctuation
    return ''.join(random.choice(characters) for _ in range(length))

if __name__ == "__main__":
    print(generate_password(16, True))
EOF

git add generator.py
git commit -m "Feature: Add special characters option"

# Historie ansehen
git log --oneline
```

---

### **18. Beispiel 2: Branch für experimentelles Feature**

```bash
# Haupt-Code bleibt stabil
git checkout -b experimental-encryption

# Experimentelle Funktion
cat >> generator.py << 'EOF'

def encrypt_password(password, key):
    # Einfache XOR-Verschlüsselung (nur Demo!)
    return ''.join(chr(ord(c) ^ key) for c in password)
EOF

git add generator.py
git commit -m "Experimental: Password encryption"

# Testen...
# Wenn erfolgreich: Zurück zu main und mergen
git checkout main
git merge experimental-encryption

# Wenn nicht erfolgreich: Branch löschen
# git branch -d experimental-encryption
```

---

### **19. Beispiel 3: .gitignore verwenden**

```bash
# Bestimmte Dateien von Git ausschließen
cat > .gitignore << 'EOF'
# Python
__pycache__/
*.pyc
*.pyo
*.pyd

# Virtual Environment
venv/
env/

# IDE
.vscode/
.idea/

# OS
.DS_Store
Thumbs.db

# Secrets
.env
config.secret.json
EOF

git add .gitignore
git commit -m "Add .gitignore for Python project"
```

**Wichtig:** Niemals Passwörter oder API-Keys committen!

---

## **SCHNELLREFERENZ**

### **Git-Cheatsheet:**

```bash
# Setup
git config --global user.name "Name"
git config --global user.email "email@example.com"

# Repository
git init                    # Neues Repo
git clone <url>             # Remote clonen

# Änderungen
git status                  # Status anzeigen
git add <file>              # Datei zur Staging Area
git add .                   # Alle Dateien
git commit -m "message"     # Commit erstellen

# Historie
git log                     # Vollständige Historie
git log --oneline           # Kompakte Ansicht

# Branches
git branch                  # Branches anzeigen
git checkout -b <name>      # Neuen Branch erstellen
git checkout <name>         # Branch wechseln
git merge <branch>          # Branch mergen

# Remote (GitHub)
git remote add origin <url> # Remote hinzufügen
git push origin main        # Zu GitHub pushen
git pull origin main        # Von GitHub pullen
```

### **GitHub-Workflow:**

```
1. Fork → 2. Clone → 3. Branch → 4. Commit → 5. Push → 6. Pull Request
```

---

## **HÄUFIGE FEHLER UND LÖSUNGEN**

### **20. Fehler 1: Commit-Message vergessen**

```bash
# ❌ Fehler
git commit
# Öffnet Editor, verwirrend für Anfänger

# ✅ Lösung: -m Flag verwenden
git commit -m "Aussagekräftige Nachricht"
```

---

### **21. Fehler 2: Falsche E-Mail bei git config**

```bash
# ❌ Problem: E-Mail bei GitHub anders als bei Git
# → Commits werden nicht mit GitHub-Profil verknüpft

# ✅ Lösung: Prüfen und korrigieren
git config --global user.email
git config --global user.email "richtige@email.com"
```

---

### **22. Fehler 3: Sensible Daten committet**

```bash
# ❌ Passwörter/API-Keys committet
git add config.py  # enthält Passwort!
git commit -m "Config hinzugefügt"

# ✅ Lösung: Aus Historie entfernen (kompliziert!)
# Besser: VORHER .gitignore nutzen und niemals committen!

# Wenn schon passiert:
git rm --cached config.py
# Füge zu .gitignore hinzu
echo "config.py" >> .gitignore
git commit -m "Remove sensitive file"
```

**Wichtig:** Einmal gepusht = schwer rückgängig zu machen!

---

## **ÜBUNGSAUFGABEN**

**Aufgabe 1:** Erstelle lokales Git-Repository für Python-Projekt. Mache 3 Commits mit verschiedenen Änderungen.

**Aufgabe 2:** Erstelle GitHub-Account und pushe dein lokales Repository online.

**Aufgabe 3:** Finde Open Source Python-Projekt auf GitHub (z.B. "requests" Library). Klone es und schaue die Commit-Historie an.

**Aufgabe 4:** Erstelle Branch für neues Feature in deinem Projekt. Merge es zurück zu main.

---

### **Merksätze:**

🎯 **Open Source = Transparenz, Teilen, Gemeinschaft**  
🎯 **Git = Zeitmaschine für Code (Commits = Snapshots)**  
🎯 **GitHub = Social Network + Cloud für Git-Projekte**  
🎯 **Workflow: Add → Commit → Push**  
🎯 **Branches = sichere Experimente, Main = stabiler Code**  
🎯 **Niemals Passwörter/API-Keys committen! (.gitignore nutzen)**  
🎯 **Git-Email = GitHub-Email (für Profil-Verknüpfung)**