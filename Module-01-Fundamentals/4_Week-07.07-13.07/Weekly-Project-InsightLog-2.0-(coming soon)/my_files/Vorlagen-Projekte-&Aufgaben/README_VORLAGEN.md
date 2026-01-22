# 📚 GitHub Aufgaben-Vorlagen

> Kompakte, effiziente Vorlagen zur professionellen Dokumentation von Ausbildungs- und Studienaufgaben

Diese Vorlagen-Sammlung bietet optimierte Markdown-Vorlagen für verschiedene Bereiche der IT-Ausbildung. Alle Vorlagen sind **schlank, fokussiert und wiederverwendbar**.

---

## 📁 Verfügbare Vorlagen

| Vorlage | Verwendung | Größe |
|---------|------------|-------|
| `vorlage_terminal.md` | Terminal, Prozesse, Dateisystem | ~150 Zeilen |
| `vorlage_python.md` | Python-Programmierung | ~120 Zeilen |
| `vorlage_web.md` | HTML/CSS/JavaScript Projekte | ~140 Zeilen |
| `vorlage_netzwerk.md` | Netzwerk, Wireshark, Protokolle | ~180 Zeilen |
| `vorlage_universal.md` | Allgemeine Aufgaben | ~80 Zeilen |

---

## 🚀 Schnellstart

### 1. Vorlage auswählen
Wähle die passende Vorlage für deine Aufgabe:
- **Terminal/Linux** → `vorlage_terminal.md`
- **Python Code** → `vorlage_python.md`
- **Webentwicklung** → `vorlage_web.md`
- **Netzwerk-Analyse** → `vorlage_netzwerk.md`
- **Sonstiges** → `vorlage_universal.md`

### 2. Vorlage kopieren
```bash
# In dein Projekt-Verzeichnis kopieren
cp vorlage_[typ].md dein-projekt/README.md
```

### 3. Anpassen
Ersetze die Platzhalter:
- `[Aufgaben-Titel]` → Dein Titel
- `[Kursname]` → Dein Kurs
- `[TT.MM.JJJJ]` → Datum
- `[Dein Name]` → Dein Name
- Beispiel-Code → Dein Code
- etc.

### 4. Zu GitHub hochladen
```bash
cd dein-projekt
git init
git add README.md
git commit -m "Initial commit"
git remote add origin https://github.com/benutzername/repo.git
git push -u origin main
```

---

## 💡 Verwendungsbeispiele

### Beispiel 1: Terminal-Aufgabe "Verzeichnis-Tanz"
```bash
# Neue Aufgabe erstellen
mkdir TF1_Verzeichnis-Tanz
cd TF1_Verzeichnis-Tanz
cp ~/vorlagen/vorlage_universal.md README.md

# Vorlage bearbeiten
nano README.md

# Titel ändern zu: TF1: Verzeichnis-Tanz
# Schritte dokumentieren
# pwd-Ausgaben einfügen

# Zu GitHub pushen
git init
git add .
git commit -m "TF1: Verzeichnis-Navigation abgeschlossen"
git push origin main
```

### Beispiel 2: Python-Projekt "Zeilen zählen"
```bash
mkdir Python_Zeilen-Zaehlen
cd Python_Zeilen-Zaehlen
cp ~/vorlagen/vorlage_python.md README.md

# Code schreiben in main.py
# README.md anpassen
# Tests dokumentieren

git init && git add . && git commit -m "Python: Zeilen-Zähler fertig"
git push
```

---

## 📖 Vorlagen-Struktur

Alle Vorlagen folgen dieser Struktur:

```markdown
# Titel
├── 📋 Aufgabenstellung (Was soll gemacht werden?)
├── 💻 Durchführung (Wie wurde es gemacht?)
├── ✅ Fragen & Antworten (Antworten auf Aufgabenfragen)
├── 💡 Erkenntnisse (Was wurde gelernt?)
└── Status & Metadaten
```

**Vorteile:**
- ✅ Konsistente Struktur über alle Aufgaben
- ✅ Schnell scanbar und lesbar
- ✅ Professionelles Aussehen
- ✅ Leicht durchsuchbar
- ✅ Kompakt (80-180 Zeilen statt 500+)

---

## ✏️ Anpassungstipps

### Farben & Emojis
Die Vorlagen nutzen Emojis für visuelle Orientierung:
- 📋 Aufgabe/Inhalt
- 💻 Code/Implementierung
- ✅ Fragen/Abschluss
- 💡 Lernen/Wissen
- 📚 Ressourcen
- 🚀 Deployment/Start

### Abschnitte hinzufügen
```markdown
## 🔧 Troubleshooting
[Deine Fehler und Lösungen]

## 📊 Performance
[Deine Messungen]
```

### Abschnitte entfernen
Lösche einfach nicht benötigte Abschnitte aus der Vorlage.

---

## 🎯 Best Practices

1. **Titel spezifisch wählen**
   - ❌ "Python Aufgabe"
   - ✅ "TF1_4.2: Sortieralgorithmus mit Quicksort"

2. **Code-Blöcke nutzen**
   ```bash
   # Gut dokumentiert
   ls -la ~/dokumente  # Zeige alle Dateien inklusive versteckter
   ```

3. **Screenshots einbinden**
   ```markdown
   ![Terminal Ausgabe](./screenshots/ausgabe.png)
   ```

4. **Status aktuell halten**
   - Status: 🔄 In Arbeit → ✅ Abgeschlossen
   - Zeit: Nach Fertigstellung eintragen

5. **Erkenntnisse direkt notieren**
   - Schreibe Lernpunkte während der Arbeit
   - Dokumentiere Probleme und Lösungen

---

## 📂 Empfohlene Repository-Struktur

```
ausbildung-2024/
├── README.md                    # Übersicht aller Aufgaben
├── vorlagen/                    # Deine Vorlagen-Sammlung
│   ├── vorlage_terminal.md
│   ├── vorlage_python.md
│   └── ...
├── TF1_Terminal/
│   ├── README.md               # Aufgabe 1
│   ├── screenshots/
│   └── dateien/
├── TF1_Python_Basics/
│   ├── README.md               # Aufgabe 2
│   ├── main.py
│   └── tests.py
└── Netzwerk_Wireshark/
    ├── README.md               # Aufgabe 3
    ├── screenshots/
    └── captures/
```

---

## 🔄 Updates & Wartung

Vorlagen regelmäßig aktualisieren:
```bash
# Vorlagen-Repo aktualisieren
cd ~/vorlagen
git pull

# Oder manuell neue Version herunterladen
```

---

## 📝 Lizenz

Diese Vorlagen sind frei verwendbar für Bildungszwecke.

---

## 🤝 Feedback

Verbesserungsvorschläge? Erstelle ein Issue oder Pull Request!

---

**Erstellt:** Januar 2026  
**Version:** 2.0 (Kompakt, Deutsch)  
**Autor:** [Dein Name]
