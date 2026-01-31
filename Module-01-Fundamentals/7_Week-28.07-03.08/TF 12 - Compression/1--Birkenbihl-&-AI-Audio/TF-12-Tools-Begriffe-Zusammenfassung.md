# Kategorisierung: Datenkompression

## Übersicht der verwendeten Elemente

|Kategorie|Begriffe/Tools|
|---|---|
|**Verwendete Tools (Windows 11)**|Windows PowerShell/Eingabeaufforderung, 7-Zip, WinRAR, Windows integrierte ZIP-Kompression, tar (in PowerShell ab Windows 10), Compress-Archive (PowerShell-Cmdlet), Expand-Archive (PowerShell-Cmdlet)|
|**Technische Fachbegriffe**|Datenkompression, Lossless Compression (verlustfreie Kompression), Lossy Compression (verlustbehaftete Kompression), Run-Length Encoding (RLE), Dictionary Coding, LZ77/LZ78-Algorithmen, Kompressionsrate, Archivierung, Codec, Redundanz, Bit-Codierung|
|**Wichtige Vokabeln**|Komprimieren, Dekomprimieren, Archiv, Speicherplatz, Bandbreite, Datenübertragung, Algorithmus, Originaldaten, Wiederherstellung, Payload, Logdateien, Malware|

## Bedeutungen

|Begriff|Bedeutung|
|---|---|
|**Verwendete Tools (Windows 11)**||
|Windows PowerShell/Eingabeaufforderung|Kommandozeilen-Schnittstellen in Windows zum Ausführen von Kompressionsbefehlen|
|7-Zip|Kostenloses Open-Source-Kompressionsprogramm für Windows (unterstützt .7z, .zip, .gz, .tar, etc.)|
|WinRAR|Kommerzielles Kompressionsprogramm für Windows (unterstützt .rar, .zip und andere Formate)|
|Windows integrierte ZIP-Kompression|In Windows Explorer integrierte Funktion zum Erstellen und Öffnen von ZIP-Archiven (Rechtsklick → "Senden an" → "ZIP-komprimierter Ordner")|
|tar (PowerShell)|Unix-Archivierungstool, seit Windows 10 in PowerShell verfügbar|
|Compress-Archive|PowerShell-Befehl zum Erstellen von ZIP-Archiven: `Compress-Archive -Path Datei.txt -DestinationPath Archiv.zip`|
|Expand-Archive|PowerShell-Befehl zum Entpacken von ZIP-Archiven: `Expand-Archive -Path Archiv.zip -DestinationPath Zielordner`|
|**Technische Fachbegriffe**||
|Datenkompression|Prozess der Kodierung von Informationen mit weniger Bits als in der ursprünglichen Darstellung|
|Lossless Compression|Verlustfreie Kompression – keine Originaldaten gehen verloren, perfekte Wiederherstellung möglich|
|Lossy Compression|Verlustbehaftete Kompression – einige Daten werden dauerhaft verworfen für höhere Kompressionsraten|
|Run-Length Encoding (RLE)|Einfaches Kompressionsverfahren, das wiederholte Datensequenzen durch Anzahl + Wert ersetzt|
|Dictionary Coding|Kompressionstechnik, die ein "Wörterbuch" häufiger Sequenzen erstellt und diese durch kurze Referenzen ersetzt|
|LZ77/LZ78-Algorithmen|Wörterbuch-basierte Kompressionsalgorithmen, die in ZIP und Gzip verwendet werden|
|Kompressionsrate|Verhältnis zwischen komprimierter und ursprünglicher Dateigröße (z.B. 50% bedeutet halbierte Größe)|
|Archivierung|Bündeln mehrerer Dateien und Verzeichnisse in eine einzige Datei (nicht zwingend komprimiert)|
|Codec|Technologie zum Kodieren/Dekodieren von Daten (besonders bei Audio/Video)|
|Redundanz|Überflüssige oder wiederholte Informationen in Daten, die komprimiert werden können|
|Bit-Codierung|Darstellung von Informationen in binärer Form (0 und 1)|
|**Wichtige Vokabeln**||
|Komprimieren|Daten verkleinern durch Anwendung eines Kompressionsalgorithmus|
|Dekomprimieren|Komprimierte Daten wieder in ihre ursprüngliche oder ähnliche Form zurückwandeln|
|Archiv|Einzelne Datei, die mehrere Dateien und Ordner enthält (z.B. .zip, .tar)|
|Speicherplatz|Verfügbarer Platz auf Festplatte, SSD oder in der Cloud zur Datenspeicherung|
|Bandbreite|Datenübertragungskapazität einer Netzwerkverbindung|
|Datenübertragung|Versenden von Daten über Netzwerke (Internet, LAN)|
|Algorithmus|Schrittweise Anleitung zur Lösung eines Problems (hier: zur Kompression)|
|Originaldaten|Unveränderte, unkomprimierte Ausgangsdaten|
|Wiederherstellung|Zurückgewinnen der Originaldaten nach Dekompression|
|Payload|Nutzlast – eigentlicher Inhalt einer Datei oder Nachricht (manchmal schädlich)|
|Logdateien|Protokolldateien, die Systemereignisse aufzeichnen|
|Malware|Schadsoftware (Viren, Trojaner, etc.)|

---

## 80/20 Zusammenfassung: Das Wichtigste zur Datenkompression

### Was ist Datenkompression?

Datenkompression bedeutet, Informationen mit weniger Bits darzustellen als im Original. Wie die Abkürzung "LOL" statt "Laugh Out Loud" – nur für digitale Daten.

**Zwei Hauptgründe für Kompression:**

1. **Speicherplatz sparen**: Mehr Daten auf Festplatte, SSD oder Cloud speichern
2. **Schnellere Übertragung**: Kleinere Dateien werden schneller über das Internet übertragen

**Cybersecurity-Relevanz:**

- Logdateien werden komprimiert, um Platz zu sparen
- Malware kann komprimiert sein, um Erkennung zu erschweren
- Komprimierte Archive können schädliche Inhalte enthalten

### Die zwei Hauptkategorien

#### 1. Verlustfreie Kompression (Lossless)

**Prinzip:** Keine Daten gehen verloren – nach Dekompression erhält man eine exakte Kopie des Originals.

**Anwendungsfälle:**

- Textdokumente und Programmcode
- Ausführbare Programme (.exe, .dll)
- Logdateien
- Bestimmte Bildformate (PNG, GIF)

**Gängige Formate:**

- ZIP (am verbreitetsten auf Windows)
- Gzip (.gz)
- Bzip2 (.bz2)
- XZ (.xz)
- 7z (von 7-Zip)

#### 2. Verlustbehaftete Kompression (Lossy)

**Prinzip:** Unwichtige Daten werden dauerhaft gelöscht, um viel höhere Kompressionsraten zu erreichen. Das Ergebnis ist dem Original sehr ähnlich, aber nicht identisch.

**Anwendungsfälle:**

- Bilder (JPEG/JPG)
- Audio (MP3, AAC)
- Video (MP4, AVI)

**Funktionsweise:** Algorithmen entfernen Informationen, die Menschen schwer wahrnehmen (z.B. Farbabstufungen im Bild, unhörbare Frequenzen in Audio).

**Wichtig für Cybersecurity:** Verlustbehaftete Kompression ist ungeeignet für Daten, wo jedes Bit zählt (Programme, Logs, Verschlüsselungsschlüssel)!

### Wie funktioniert verlustfreie Kompression?

Kompressionsalgorithmen eliminieren statistische Redundanz (Wiederholungen):

**1. Run-Length Encoding (RLE):**

```
Original: ⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪⚪
Komprimiert: "20 × ⚪"
```

Wiederholte Daten werden durch Anzahl + Wert ersetzt.

**2. Dictionary Coding (LZ77/LZ78 – in ZIP, Gzip):**

```
Original: "der schnelle Fuchs springt über den Hund. der schnelle Fuchs schläft."
Schritt 1: Wörterbuch erstellen
[1] = "der schnelle Fuchs"
Schritt 2: Wiederholungen durch Referenzen ersetzen
Komprimiert: "[1] springt über den Hund. [1] schläft."
```

### Archivierung vs. Kompression

**Unterschied:**

- **Archivierung**: Mehrere Dateien zu einer einzigen Datei bündeln (z.B. mit `tar`) – nicht zwingend komprimiert
- **Kompression**: Dateigröße reduzieren (z.B. mit `gzip`)

**Häufige Kombination:**

- `.tar.gz`: Erst mit `tar` archiviert, dann mit `gzip` komprimiert
- `.zip`: Kombiniert beide Schritte in einem Format

### Praktische Anwendung in Windows 11

#### Methode 1: Windows Explorer (GUI)

- **Komprimieren**: Rechtsklick auf Datei/Ordner → "Senden an" → "ZIP-komprimierter Ordner"
- **Dekomprimieren**: Rechtsklick auf ZIP-Datei → "Alle extrahieren..."

#### Methode 2: PowerShell (Kommandozeile)

**Test-Datei erstellen:**

```powershell
"Dies ist eine Testdatei. Wiederholung ist der Schlüssel zur Kompression. Wiederholung ist der Schlüssel zur Kompression. Wiederholung ist der Schlüssel zur Kompression." | Out-File test.txt
```

**Dateigröße prüfen:**

```powershell
Get-Item test.txt | Select-Object Name, Length
```

**Komprimieren:**

```powershell
Compress-Archive -Path test.txt -DestinationPath test.zip
```

**Größe der komprimierten Datei prüfen:**

```powershell
Get-Item test.zip | Select-Object Name, Length
```

**Dekomprimieren:**

```powershell
Expand-Archive -Path test.zip -DestinationPath entpackt
```

**Inhalt überprüfen:**

```powershell
Get-Content entpackt\test.txt
```

#### Methode 3: 7-Zip (empfohlen für fortgeschrittene Nutzer)

- Kostenlos von [7-zip.org](https://www.7-zip.org/) herunterladen
- Unterstützt mehr Formate (.7z, .tar, .gz, .bz2, .xz, .rar)
- Höhere Kompressionsraten als Standard-ZIP
- Rechtsklick-Integration in Windows Explorer

### Kernpunkte

✅ **Verlustfreie Kompression**: Für Programme, Code, Dokumente, Logs – alles wo Genauigkeit wichtig ist ✅ **Verlustbehaftete Kompression**: Für Multimedia (Bilder, Audio, Video) – wo geringe Qualitätsverluste akzeptabel sind ✅ **ZIP ist Standard**: Am verbreitetsten auf Windows, kombiniert Archivierung und Kompression ✅ **PowerShell für Automatisierung**: `Compress-Archive` und `Expand-Archive` für Skripte ✅ **7-Zip für Flexibilität**: Unterstützt mehr Formate und bessere Kompression