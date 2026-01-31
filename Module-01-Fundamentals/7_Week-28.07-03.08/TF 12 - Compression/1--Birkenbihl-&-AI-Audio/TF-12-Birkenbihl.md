Welcome to the topic of data compression! Before our live session, please go through the material below. Willkommen zum Thema Datenkompression! Bitte gehen Sie vor unserer Live-Sitzung das folgende Material durch.

This will introduce you to the fundamental concepts of why and how we make files smaller. Dies wird Sie in die grundlegenden Konzepte einführen, warum und wie wir Dateien kleiner machen.

What is Data Compression? Was ist Datenkompression?

At its core, data compression is the process of encoding information using fewer bits than the original representation. Im Kern ist Datenkompression der Prozess, Informationen mit weniger Bits zu kodieren als in der ursprünglichen Darstellung.

Think of it like creating a shorthand for frequently used phrases. Stellen Sie es sich vor wie das Erstellen einer Kurzschrift für häufig verwendete Ausdrücke.

Instead of writing "Laugh Out Loud" every time, we often use "LOL". Anstatt jedes Mal "Laugh Out Loud" zu schreiben, verwenden wir oft "LOL".

Compression algorithms do something similar but for digital data, such as text, images, videos, and so on. Kompressionsalgorithmen machen etwas Ähnliches, aber für digitale Daten wie Text, Bilder, Videos und so weiter.

Why do we compress data? There are two main reasons. Warum komprimieren wir Daten? Es gibt zwei Hauptgründe.

First, saving storage space. Compressed files take up less disk space, allowing us to store more data on our devices or in the cloud. Erstens, Speicherplatz sparen. Komprimierte Dateien belegen weniger Speicherplatz, sodass wir mehr Daten auf unseren Geräten oder in der Cloud speichern können.

Second, faster data transfer. Smaller files transmit more quickly over networks like the internet, saving time and bandwidth. Zweitens, schnellere Datenübertragung. Kleinere Dateien werden schneller über Netzwerke wie das Internet übertragen, was Zeit und Bandbreite spart.

This is crucial for everything from downloading software to streaming videos. Dies ist entscheidend für alles, vom Herunterladen von Software bis zum Streamen von Videos.

In cybersecurity, understanding compression is important. In der Cybersicherheit ist das Verstehen von Kompression wichtig.

Log files are often compressed to save space, malware might be compressed to evade detection, and compressed archives are common ways to package and transfer data, sometimes containing malicious payloads. Protokolldateien werden oft komprimiert, um Platz zu sparen, Malware könnte komprimiert werden, um der Erkennung zu entgehen, und komprimierte Archive sind gängige Methoden, um Daten zu verpacken und zu übertragen, manchmal mit schädlichen Inhalten.

Lossless versus Lossy Compression. Verlustfreie versus verlustbehaftete Kompression.

There are two main categories of compression algorithms. Es gibt zwei Hauptkategorien von Kompressionsalgorithmen.

First, lossless compression. This method reduces file size without losing any original data. Erstens, verlustfreie Kompression. Diese Methode reduziert die Dateigröße ohne Verlust von Originaldaten.

When you decompress a file compressed with a lossless algorithm, you get back an exact copy of the original. Wenn Sie eine Datei dekomprimieren, die mit einem verlustfreien Algorithmus komprimiert wurde, erhalten Sie eine exakte Kopie des Originals zurück.

This is essential for data where perfect accuracy is critical, such as text documents like code, articles, books. Dies ist wesentlich für Daten, bei denen perfekte Genauigkeit entscheidend ist, wie Textdokumente, zum Beispiel Code, Artikel, Bücher.

Also for executable programs, log files, and certain image formats like PNG or GIF where perfect fidelity is needed. Auch für ausführbare Programme, Protokolldateien und bestimmte Bildformate wie PNG oder GIF, bei denen perfekte Genauigkeit benötigt wird.

Common lossless formats include ZIP, Gzip, Bzip2, and XZ. Gängige verlustfreie Formate sind ZIP, Gzip, Bzip2 und XZ.

Second, lossy compression. This method achieves much higher compression ratios, meaning much smaller files, by permanently discarding some data that is considered less important or less noticeable to human perception. Zweitens, verlustbehaftete Kompression. Diese Methode erreicht viel höhere Kompressionsraten, also viel kleinere Dateien, indem sie dauerhaft einige Daten verwirft, die als weniger wichtig oder für die menschliche Wahrnehmung weniger bemerkbar gelten.

When you decompress a lossy file, you get back something very similar to the original, but not identical. Wenn Sie eine verlustbehaftete Datei dekomprimieren, erhalten Sie etwas zurück, das dem Original sehr ähnlich ist, aber nicht identisch.

This is acceptable for data where perfect accuracy isn't the primary goal, and some loss of quality is a reasonable trade-off for significantly smaller file sizes. Dies ist akzeptabel für Daten, bei denen perfekte Genauigkeit nicht das Hauptziel ist und ein gewisser Qualitätsverlust ein vernünftiger Kompromiss für deutlich kleinere Dateigrößen ist.

Examples include images like JPEG or JPG, audio like MP3 or AAC, and video like MP4 or AVI using specific codecs. Beispiele sind Bilder wie JPEG oder JPG, Audio wie MP3 oder AAC und Video wie MP4 oder AVI mit bestimmten Codecs.

The algorithm decides which bits of information are less critical. Der Algorithmus entscheidet, welche Informationsbits weniger kritisch sind.

For example, in a photo, it might discard subtle variations in color that the human eye wouldn't easily detect. Zum Beispiel könnte er bei einem Foto subtile Farbvariationen verwerfen, die das menschliche Auge nicht leicht erkennen würde.

In audio, it might remove frequencies outside the typical range of human hearing. Bei Audio könnte er Frequenzen außerhalb des typischen Bereichs des menschlichen Gehörs entfernen.

Think about it. When would using lossy compression be a really bad idea in a cybersecurity context? Denken Sie darüber nach. Wann wäre die Verwendung verlustbehafteter Kompression eine wirklich schlechte Idee im Cybersicherheitskontext?

When might it be acceptable or even necessary? Wann könnte sie akzeptabel oder sogar notwendig sein?

How Does Lossless Compression Work? Wie funktioniert verlustfreie Kompression?

Lossless compression algorithms work by finding and eliminating statistical redundancy. Verlustfreie Kompressionsalgorithmen funktionieren, indem sie statistische Redundanz finden und eliminieren.

They don't throw away information; they just represent it more efficiently. Sie werfen keine Informationen weg, sie stellen sie nur effizienter dar.

Here are a couple of simplified ideas behind common techniques. Hier sind einige vereinfachte Ideen hinter gängigen Techniken.

Run-Length Encoding, or RLE. Imagine a line in an image that is just 100 white pixels in a row. Run-Length-Encoding oder RLE. Stellen Sie sich eine Zeile in einem Bild vor, die nur aus 100 weißen Pixeln in einer Reihe besteht.

Instead of storing "white, white, white" 100 times, RLE stores something like "100 white". Anstatt "weiß, weiß, weiß" 100 Mal zu speichern, speichert RLE etwas wie "100 weiß".

It replaces sequences of repeating data with a count and a single instance of the data. Es ersetzt Sequenzen sich wiederholender Daten durch eine Anzahl und eine einzelne Instanz der Daten.

Original image line: 20 white circles. Compressed with RLE: 20 times white circle. Ursprüngliche Bildzeile: 20 weiße Kreise. Mit RLE komprimiert: 20 Mal weißer Kreis.

Dictionary Coding, for example LZ77 or LZ78 family used in Gzip and ZIP. Dictionary-Coding, zum Beispiel die LZ77- oder LZ78-Familie, die in Gzip und ZIP verwendet wird.

These algorithms build a dictionary of data sequences encountered so far. Diese Algorithmen erstellen ein Wörterbuch von bisher angetroffenen Datensequenzen.

When a sequence reappears, instead of writing the sequence again, the algorithm writes a short reference, a pointer, to its previous occurrence in the dictionary. Wenn eine Sequenz erneut auftritt, schreibt der Algorithmus, anstatt die Sequenz erneut zu schreiben, eine kurze Referenz, einen Zeiger, auf ihr vorheriges Vorkommen im Wörterbuch.

For example, if the phrase "the quick brown fox" appears multiple times in a document, the compressor might store it fully the first time and then use short pointers for subsequent occurrences. Wenn zum Beispiel die Phrase "the quick brown fox" mehrmals in einem Dokument vorkommt, könnte der Kompressor sie beim ersten Mal vollständig speichern und dann kurze Zeiger für nachfolgende Vorkommen verwenden.

Original text: "the quick brown fox jumps over the lazy dog. the quick brown fox sleeps." Ursprünglicher Text: "the quick brown fox jumps over the lazy dog. the quick brown fox sleeps."

Step 1: Build a dictionary of repeated sequences. Entry 1 equals "the quick brown fox". Schritt 1: Erstellen Sie ein Wörterbuch wiederholter Sequenzen. Eintrag 1 entspricht "the quick brown fox".

Step 2: Replace repeated sequences with references. Schritt 2: Ersetzen Sie wiederholte Sequenzen durch Referenzen.

Compressed text: Entry 1 jumps over the lazy dog. Entry 1 sleeps. Komprimierter Text: Eintrag 1 jumps over the lazy dog. Eintrag 1 sleeps.

Archiving versus Compression. Archivierung versus Kompression.

It's common to encounter tar.gz or zip files. These often involve two related but distinct concepts. Es ist üblich, auf tar.gz- oder zip-Dateien zu stoßen. Diese beinhalten oft zwei verwandte, aber unterschiedliche Konzepte.

Archiving. This is the process of combining multiple files and directories into a single file, the archive. Archivierung. Dies ist der Prozess, mehrere Dateien und Verzeichnisse in eine einzige Datei, das Archiv, zu kombinieren.

This makes it easier to manage and transfer groups of files. Dies erleichtert die Verwaltung und Übertragung von Dateigruppen.

The tar, or Tape Archive, command on Unix-like systems is a classic example. Der tar- oder Tape-Archive-Befehl auf Unix-ähnlichen Systemen ist ein klassisches Beispiel.

Archiving itself does not necessarily compress the data, although some archive formats might include compression. Die Archivierung selbst komprimiert die Daten nicht zwingend, obwohl einige Archivformate möglicherweise Kompression beinhalten.

Compression. This is the process of reducing the size of data, as discussed above. Kompression. Dies ist der Prozess der Reduzierung der Datengröße, wie oben besprochen.

Tools like gzip, bzip2, or xz typically operate on a single file or data stream. Tools wie gzip, bzip2 oder xz arbeiten typischerweise mit einer einzelnen Datei oder einem Datenstrom.

Often, these two steps are combined. Oft werden diese beiden Schritte kombiniert.

For example, tar is used to bundle multiple files or directories into a single tar archive file. Zum Beispiel wird tar verwendet, um mehrere Dateien oder Verzeichnisse in eine einzige tar-Archivdatei zu bündeln.

Then gzip is used to compress that single tar file, resulting in a tar.gz file. Dann wird gzip verwendet, um diese einzelne tar-Datei zu komprimieren, was zu einer tar.gz-Datei führt.

ZIP files are a common format that typically combines both archiving and compression into a single step and format. ZIP-Dateien sind ein gängiges Format, das typischerweise sowohl Archivierung als auch Kompression in einem einzigen Schritt und Format kombiniert.

Common Compression Tools on macOS or Linux. Gängige Kompressions-Tools auf macOS oder Linux.

Your Mac comes with command-line tools for handling common compression formats. Ihr Mac wird mit Befehlszeilen-Tools für gängige Kompressionsformate geliefert.

gzip or gunzip. One of the most common lossless compression tools for gz files. gzip compresses, gunzip decompresses. gzip oder gunzip. Eines der gängigsten verlustfreien Kompressions-Tools für gz-Dateien. gzip komprimiert, gunzip dekomprimiert.

bzip2 or bunzip2. Another lossless compression tool, often achieving better compression than gzip but sometimes slower for bz2 files. bzip2 oder bunzip2. Ein weiteres verlustfreies Kompressions-Tool, das oft bessere Kompression als gzip erreicht, aber manchmal langsamer für bz2-Dateien ist.

xz or unxz. A more modern lossless compression tool, often providing the best compression ratios but can be slower, especially for compression of xz files. xz oder unxz. Ein moderneres verlustfreies Kompressions-Tool, das oft die besten Kompressionsraten bietet, aber langsamer sein kann, besonders bei der Kompression von xz-Dateien.

tar. Used for archiving or bundling files. It has options to call compression tools directly. tar. Wird zum Archivieren oder Bündeln von Dateien verwendet. Es hat Optionen, um Kompressions-Tools direkt aufzurufen.

For example, tar -czf archive.tar.gz files creates a gzipped tar archive. Zum Beispiel erstellt tar -czf archive.tar.gz files ein gzipptes tar-Archiv.

zip or unzip. Handles zip archives, which combine archiving and compression. zip oder unzip. Verarbeitet zip-Archive, die Archivierung und Kompression kombinieren.

Try it yourself. Probieren Sie es selbst aus.

Open your Terminal application. You can find it using Spotlight search. Press Command plus Space and type "Terminal". Öffnen Sie Ihre Terminal-Anwendung. Sie können sie mit der Spotlight-Suche finden. Drücken Sie Befehl plus Leertaste und tippen Sie "Terminal".

Create a simple text file. Type the following command and press Enter. Erstellen Sie eine einfache Textdatei. Geben Sie den folgenden Befehl ein und drücken Sie Enter.

echo "This is a test file. Repetition is the key to compression. Repetition is the key to compression. Repetition is the key to compression." > test.txt echo "This is a test file. Repetition is the key to compression. Repetition is the key to compression. Repetition is the key to compression." > test.txt

Check the size of the file: ls -l test.txt Überprüfen Sie die Größe der Datei: ls -l test.txt

Note the size in bytes, the number before the date. Notieren Sie die Größe in Bytes, die Zahl vor dem Datum.

Compress the file using gzip: gzip test.txt Komprimieren Sie die Datei mit gzip: gzip test.txt

List the files again. What is the new file name? Check its size: ls -l test.txt.gz Listen Sie die Dateien erneut auf. Wie lautet der neue Dateiname? Überprüfen Sie seine Größe: ls -l test.txt.gz

How does the size compare to the original? Wie vergleicht sich die Größe mit dem Original?

Decompress the file: gunzip test.txt.gz Dekomprimieren Sie die Datei: gunzip test.txt.gz

Check the contents to ensure it's the same as the original: cat test.txt Überprüfen Sie den Inhalt, um sicherzustellen, dass er mit dem Original übereinstimmt: cat test.txt

You've just performed lossless compression and decompression! Sie haben gerade verlustfreie Kompression und Dekompression durchgeführt!

That's the basic introduction to compression. We'll explore these concepts and tools more interactively in the live session. Das ist die grundlegende Einführung in die Kompression. Wir werden diese Konzepte und Tools interaktiver in der Live-Sitzung erkunden.

The slides for the live session can be viewed here. Try not to peek before class, spoilers inside! Die Folien für die Live-Sitzung können hier angesehen werden. Versuchen Sie nicht, vor dem Unterricht zu spähen, Spoiler enthalten!