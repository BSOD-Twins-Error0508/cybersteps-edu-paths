Welcome! Before our live session on Numeral Systems, please go through this material. Willkommen! Bitte arbeite dieses Material durch, bevor wir uns zur Live-Sitzung über Zahlensysteme treffen.

Understanding how computers represent and manipulate numbers at a low level is fundamental in computing and especially crucial in cybersecurity. Zu verstehen, wie Computer Zahlen auf niedriger Ebene darstellen und verarbeiten, ist grundlegend in der Informatik und besonders wichtig in der Cybersicherheit.

It's key for analyzing network traffic, understanding file formats, reverse engineering, memory forensics, and much more. Es ist entscheidend für die Analyse von Netzwerkverkehr, das Verstehen von Dateiformaten, Reverse Engineering, Speicherforensik und vieles mehr.

What are Numeral Systems? Was sind Zahlensysteme?

At its core, a numeral system is simply a way of representing numbers. Im Kern ist ein Zahlensystem einfach eine Methode, Zahlen darzustellen.

The system you use daily is the decimal system, also known as base ten. Das System, das du täglich verwendest, ist das Dezimalsystem, auch bekannt als Basis zehn.

It uses ten digits, zero through nine, and the position of a digit determines its value, based on place value and powers of ten. Es verwendet zehn Ziffern, null bis neun, und die Position einer Ziffer bestimmt ihren Wert, basierend auf Stellenwert und Zehnerpotenzen.

Example: six hundred fifty-four thousand three hundred twenty-one equals six times ten to the power of five, plus five times ten to the power of four, plus four times ten to the power of three, plus three times ten to the power of two, plus two times ten to the power of one, plus one times ten to the power of zero. Beispiel: sechshundertvierundfünfzigtausenddreihunderteinundzwanzig entspricht sechs mal zehn hoch fünf, plus fünf mal zehn hoch vier, plus vier mal zehn hoch drei, plus drei mal zehn hoch zwei, plus zwei mal zehn hoch eins, plus eins mal zehn hoch null.

This equals six hundred thousand plus fifty thousand plus four thousand plus three hundred plus twenty plus one, which equals six hundred fifty-four thousand three hundred twenty-one. Das ergibt sechshunderttausend plus fünfzigtausend plus viertausend plus dreihundert plus zwanzig plus eins, was sechshundertvierundfünfzigtausenddreihunderteinundzwanzig ergibt.

This concept of base and place value is crucial. Dieses Konzept von Basis und Stellenwert ist entscheidend.

Binary, Base Two: The Language of Computers. Binär, Basis zwei: Die Sprache der Computer.

Computers use binary, base two, because their fundamental components, transistors, exist in two states: on, which is one, or off, which is zero. Computer verwenden Binär, Basis zwei, weil ihre grundlegenden Komponenten, Transistoren, in zwei Zuständen existieren: an, was eins ist, oder aus, was null ist.

All data, numbers, text, instructions, is ultimately stored and processed as sequences of these ones and zeros, called bits. Alle Daten, Zahlen, Text, Anweisungen, werden letztendlich als Sequenzen dieser Einsen und Nullen gespeichert und verarbeitet, die Bits genannt werden.

In a binary number, the Most Significant Bit is the bit with the highest value position on the left, while the Least Significant Bit is the bit with the lowest value position on the right. In einer Binärzahl ist das höchstwertige Bit das Bit mit der höchsten Wertposition links, während das niederwertigste Bit das Bit mit der niedrigsten Wertposition rechts ist.

Binary uses only two digits: zero and one. Binär verwendet nur zwei Ziffern: null und eins.

Each position represents a power of two. Jede Position repräsentiert eine Zweierpotenz.

A group of eight bits is called a byte, a standard unit of digital information. Eine Gruppe von acht Bits wird Byte genannt, eine Standardeinheit digitaler Information.

Example: Binary one zero zero one zero one one zero. Beispiel: Binär eins null null eins null eins eins null.

One zero zero one zero one one zero equals one times two to the power of seven, plus zero times two to the power of six, plus zero times two to the power of five, plus one times two to the power of four, plus zero times two to the power of three, plus one times two to the power of two, plus one times two to the power of one, plus zero times two to the power of zero. Eins null null eins null eins eins null entspricht eins mal zwei hoch sieben, plus null mal zwei hoch sechs, plus null mal zwei hoch fünf, plus eins mal zwei hoch vier, plus null mal zwei hoch drei, plus eins mal zwei hoch zwei, plus eins mal zwei hoch eins, plus null mal zwei hoch null.

This equals one hundred twenty-eight plus zero plus zero plus sixteen plus zero plus four plus two plus zero, which equals one hundred fifty in decimal. Das ergibt einhundertachtundzwanzig plus null plus null plus sechzehn plus null plus vier plus zwei plus null, was einhundertfünfzig im Dezimalsystem ergibt.

Think about it. Denk darüber nach.

Computers use base two. Computer verwenden Basis zwei.

Humans commonly use base ten. Menschen verwenden üblicherweise Basis zehn.

Why might this difference sometimes lead to confusion when discussing storage sizes, like kilobytes versus kibibytes? Warum könnte dieser Unterschied manchmal zu Verwirrung führen, wenn man über Speichergrößen spricht, wie Kilobytes gegenüber Kibibytes?

Hexadecimal, Base Sixteen: A Programmer's Shorthand. Hexadezimal, Basis sechzehn: Eine Kurzschrift für Programmierer.

Binary numbers get long quickly. One one one one one one one one is just two hundred fifty-five in decimal. Binärzahlen werden schnell lang. Eins eins eins eins eins eins eins eins ist nur zweihundertfünfundfünfzig im Dezimalsystem.

Hexadecimal, base sixteen or hex, provides a more human-friendly way to represent binary data. Hexadezimal, Basis sechzehn oder Hex, bietet eine menschenfreundlichere Methode, Binärdaten darzustellen.

Hexadecimal uses sixteen symbols: zero through nine and A through F, representing decimal ten through fifteen. Hexadezimal verwendet sechzehn Symbole: null bis neun und A bis F, die Dezimal zehn bis fünfzehn repräsentieren.

Each position represents a power of sixteen. Jede Position repräsentiert eine Potenz von sechzehn.

Example: Hexadecimal two F. Beispiel: Hexadezimal zwei F.

Two F equals two times sixteen to the power of one, plus fifteen times sixteen to the power of zero. Zwei F entspricht zwei mal sechzehn hoch eins, plus fünfzehn mal sechzehn hoch null.

This equals thirty-two plus fifteen, which equals forty-seven in decimal. Das ergibt zweiunddreißig plus fünfzehn, was siebenundvierzig im Dezimalsystem ergibt.

Why Hexadecimal is Useful. Warum Hexadezimal nützlich ist.

The real power of hex is its direct relationship with binary: one hex digit represents exactly four binary digits, a nibble. Die wahre Stärke von Hex ist seine direkte Beziehung zu Binär: eine Hex-Ziffer repräsentiert genau vier Binärziffern, ein Nibble.

Binary one one one zero zero one zero one, split: one one one zero, zero one zero one, convert: E, five, hex: E five, often written zero x E five. Binär eins eins eins null null eins null eins, geteilt: eins eins eins null, null eins null eins, umgewandelt: E, fünf, Hex: E fünf, oft geschrieben als null x E fünf.

This makes it ideal for memory analysis: viewing raw memory dumps. Das macht es ideal für Speicheranalyse: Betrachten von rohen Speicherabbildern.

Network Packet Analysis: Tools like Wireshark display raw packet data often in hex alongside interpretations. Netzwerkpaket-Analyse: Werkzeuge wie Wireshark zeigen rohe Paketdaten oft in Hex zusammen mit Interpretationen.

MAC addresses are hex. MAC-Adressen sind Hex.

IPv six addresses use hex. IPv sechs Adressen verwenden Hex.

Executable Code: Examining machine code instructions. Ausführbarer Code: Untersuchen von Maschinencode-Anweisungen.

Web Development: Defining colors, for example, hash F F zero zero zero zero for Red. Webentwicklung: Definieren von Farben, zum Beispiel Raute F F null null null null für Rot.

Data Representation: Providing a compact view of binary data in debugging and configuration files. Datendarstellung: Bereitstellen einer kompakten Ansicht von Binärdaten in Debug- und Konfigurationsdateien.

Performing Conversions. Durchführen von Umwandlungen.

Understanding how to convert between bases manually is important for grasping the concepts. Zu verstehen, wie man zwischen Basen manuell umwandelt, ist wichtig, um die Konzepte zu erfassen.

Binary to Decimal: Sum the values of positions containing a one, which are powers of two. Binär zu Dezimal: Addiere die Werte der Positionen, die eine Eins enthalten, das sind Zweierpotenzen.

Decimal to Binary: Find the largest power of two less than or equal to the number, subtract it, and repeat with the remainder, marking the corresponding binary positions with one. Dezimal zu Binär: Finde die größte Zweierpotenz, die kleiner oder gleich der Zahl ist, subtrahiere sie und wiederhole mit dem Rest, markiere die entsprechenden Binärpositionen mit Eins.

Hex to Decimal: Sum the values of each position, which is digit value times power of sixteen. Hex zu Dezimal: Addiere die Werte jeder Position, das ist Ziffernwert mal Potenz von sechzehn.

Decimal to Hex: Repeatedly divide the decimal number by sixteen. The remainders, converted to hex digits zero through F, form the hex number, read from bottom up. Dezimal zu Hex: Teile die Dezimalzahl wiederholt durch sechzehn. Die Reste, umgewandelt in Hex-Ziffern null bis F, bilden die Hex-Zahl, von unten nach oben gelesen.

Binary to Hex: Group binary digits into sets of four, starting from the right, and convert each group to its corresponding hex digit, zero through F. Binär zu Hex: Gruppiere Binärziffern in Vierergruppen, beginnend von rechts, und wandle jede Gruppe in ihre entsprechende Hex-Ziffer um, null bis F.

Hex to Binary: Convert each hex digit to its four-bit binary equivalent. Hex zu Binär: Wandle jede Hex-Ziffer in ihr vierstelliges Binäräquivalent um.

Using Tools for Conversion. Verwendung von Werkzeugen zur Umwandlung.

While manual conversion builds understanding, in practice, you'll often use tools. Während manuelle Umwandlung das Verständnis fördert, wirst du in der Praxis oft Werkzeuge verwenden.

Calculators: Most operating systems include a calculator with a Programmer or Scientific mode that can perform conversions between decimal, binary, and hexadecimal. Taschenrechner: Die meisten Betriebssysteme enthalten einen Taschenrechner mit einem Programmierer- oder Wissenschaftsmodus, der Umwandlungen zwischen Dezimal, Binär und Hexadezimal durchführen kann.

On mac O S, the built-in Calculator app has a Programmer view. Auf mac O S hat die integrierte Taschenrechner-App eine Programmierer-Ansicht.

Online Converters: Numerous websites offer quick conversion tools. Search for binary to hex converter, decimal to binary converter, etcetera. Online-Konverter: Zahlreiche Webseiten bieten schnelle Umwandlungswerkzeuge. Suche nach Binär-zu-Hex-Konverter, Dezimal-zu-Binär-Konverter, et cetera.

Be mindful of pasting sensitive data into online tools. Sei vorsichtig beim Einfügen sensibler Daten in Online-Werkzeuge.

Programming Languages: Languages like Python have built-in functions to handle conversions, for example, bin, hex, int with x and base. Programmiersprachen: Sprachen wie Python haben eingebaute Funktionen für Umwandlungen, zum Beispiel bin, hex, int mit x und base.

Introduction to Bitwise Operations. Einführung in bitweise Operationen.

Computers can perform operations directly on the individual bits of numbers. Computer können Operationen direkt auf den einzelnen Bits von Zahlen durchführen.

These bitwise operations are fundamental in low-level programming, networking, and cryptography. Diese bitweisen Operationen sind grundlegend in Low-Level-Programmierung, Netzwerken und Kryptographie.

Let's consider two four-bit numbers: A equals one one zero zero, which is twelve in decimal, and B equals one zero one zero, which is ten in decimal. Betrachten wir zwei Vier-Bit-Zahlen: A entspricht eins eins null null, was zwölf im Dezimalsystem ist, und B entspricht eins null eins null, was zehn im Dezimalsystem ist.

AND: Result bit is one only if both input bits are one. UND: Das Ergebnisbit ist eins, nur wenn beide Eingangsbits eins sind.

One one zero zero, A, AND one zero one zero, B, equals one zero zero zero, which is eight in decimal. Eins eins null null, A, UND eins null eins null, B, ergibt eins null null null, was acht im Dezimalsystem ist.

Use Case: Masking, checking if specific bits are set, for example, checking permission flags. Anwendungsfall: Maskierung, Überprüfen, ob bestimmte Bits gesetzt sind, zum Beispiel Überprüfen von Berechtigungsflags.

OR: Result bit is one if either input bit is one. ODER: Das Ergebnisbit ist eins, wenn eines der Eingangsbits eins ist.

One one zero zero, A, OR one zero one zero, B, equals one one one zero, which is fourteen in decimal. Eins eins null null, A, ODER eins null eins null, B, ergibt eins eins eins null, was vierzehn im Dezimalsystem ist.

Use Case: Setting specific bits to one, for example, granting a permission. Anwendungsfall: Setzen bestimmter Bits auf eins, zum Beispiel Gewähren einer Berechtigung.

XOR: Result bit is one if input bits are different. XOR: Das Ergebnisbit ist eins, wenn die Eingangsbits unterschiedlich sind.

One one zero zero, A, XOR one zero one zero, B, equals zero one one zero, which is six in decimal. Eins eins null null, A, XOR eins null eins null, B, ergibt null eins eins null, was sechs im Dezimalsystem ist.

Use Case: Simple encryption, toggling bits, error checking. Anwendungsfall: Einfache Verschlüsselung, Umschalten von Bits, Fehlerprüfung.

XORing a value with itself always results in zero. XORen eines Wertes mit sich selbst ergibt immer null.

XORing a value with zero leaves it unchanged. XORen eines Wertes mit null lässt ihn unverändert.

NOT: Inverts all bits. Zero becomes one, one becomes zero. NICHT: Invertiert alle Bits. Null wird eins, eins wird null.

This is a unary operator, it acts on one operand. Dies ist ein unärer Operator, er wirkt auf einen Operanden.

NOT one one zero zero, A, equals zero zero one one, which is three in decimal, ignoring signed representation for now. NICHT eins eins null null, A, ergibt null null eins eins, was drei im Dezimalsystem ist, wobei vorzeichenbehaftete Darstellung vorerst ignoriert wird.

Note: The actual decimal result depends on how negative numbers are handled, see below. Hinweis: Das tatsächliche Dezimalergebnis hängt davon ab, wie negative Zahlen behandelt werden, siehe unten.

Shift Operations: Move bits left or right. Schiebe-Operationen: Verschiebe Bits nach links oder rechts.

One one zero zero left shift by one becomes one one zero zero zero, which effectively multiplies by two. Eins eins null null nach links verschoben um eins wird eins eins null null null, was effektiv mit zwei multipliziert.

One one zero zero right shift by one becomes zero one one zero, which effectively divides by two, integer division. Eins eins null null nach rechts verschoben um eins wird null eins eins null, was effektiv durch zwei dividiert, Ganzzahldivision.

Representing Negative Numbers: Two's Complement. Darstellung negativer Zahlen: Zweierkomplement.

How do computers represent negative numbers like minus five using only ones and zeros? Wie stellen Computer negative Zahlen wie minus fünf dar, wenn sie nur Einsen und Nullen verwenden?

The most common method is Two's Complement. Die gebräuchlichste Methode ist Zweierkomplement.

For a fixed number of bits, for example, eight bits: Take the positive binary representation. For example, five is zero zero zero zero zero one zero one. Für eine feste Anzahl von Bits, zum Beispiel acht Bits: Nimm die positive Binärdarstellung. Zum Beispiel ist fünf null null null null null eins null eins.

Invert all the bits, NOT operation: one one one one one zero one zero. Invertiere alle Bits, NICHT-Operation: eins eins eins eins eins null eins null.

This is the One's Complement. Dies ist das Einerkomplement.

Add one: one one one one one zero one zero plus one equals one one one one one zero one one. Addiere eins: eins eins eins eins eins null eins null plus eins ergibt eins eins eins eins eins null eins eins.

This is the Two's Complement representation of minus five. Dies ist die Zweierkomplement-Darstellung von minus fünf.

The most significant bit, the leftmost one, acts as a sign indicator: zero for positive, one for negative in Two's Complement. Das höchstwertige Bit, das linkeste, fungiert als Vorzeichenindikator: null für positiv, eins für negativ im Zweierkomplement.

We will explore this further in the course. Wir werden dies im Kurs weiter erforschen.

Try it yourself. Probiere es selbst aus.

Perform the following conversions and operations manually first, then use an online converter to verify your results. Führe die folgenden Umwandlungen und Operationen zuerst manuell durch, dann verwende einen Online-Konverter, um deine Ergebnisse zu überprüfen.

Search for numeral system converter or bitwise calculator. Suche nach Zahlensystem-Konverter oder bitweisem Taschenrechner.

One: Convert the decimal number forty-two to binary and hexadecimal. Eins: Wandle die Dezimalzahl zweiundvierzig in Binär und Hexadezimal um.

Two: Convert the hexadecimal number zero x F A C E to binary. Zwei: Wandle die Hexadezimalzahl null x F A C E in Binär um.

Three: What is the decimal result of the bitwise operation one zero one one AND zero one zero one? Drei: Was ist das Dezimalergebnis der bitweisen Operation eins null eins eins UND null eins null eins?

Four: If you have the binary number zero zero one one zero one zero zero, what is the result of left-shifting it by two in binary? Vier: Wenn du die Binärzahl null null eins eins null eins null null hast, was ist das Ergebnis, wenn du sie um zwei nach links verschiebst, in Binär?

What does this do to the decimal value? Was macht das mit dem Dezimalwert?

This revised material introduces concepts you'll encounter frequently. Dieses überarbeitete Material führt Konzepte ein, denen du häufig begegnen wirst.

Focus on understanding the purpose of binary and hex, the basic idea of bitwise operations, and the neat mapping between hex and binary. Konzentriere dich darauf, den Zweck von Binär und Hex zu verstehen, die grundlegende Idee bitweiser Operationen und die elegante Zuordnung zwischen Hex und Binär.

Practice the conversions manually and using tools. Übe die Umwandlungen manuell und mit Werkzeugen.

We'll reinforce these in the live session! Wir werden diese in der Live-Sitzung vertiefen!