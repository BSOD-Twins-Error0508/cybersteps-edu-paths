Welcome! Before our live session on Data Encoding, please go through this material. Willkommen! Bitte arbeite dieses Material durch, bevor wir uns zur Live-Sitzung über Datenkodierung treffen.

We'll explore how computers represent information, focusing on text and binary data. Wir werden erforschen, wie Computer Informationen darstellen, mit Schwerpunkt auf Text und Binärdaten.

Understanding this is fundamental to many areas of computing and cybersecurity. Dies zu verstehen ist grundlegend für viele Bereiche der Informatik und Cybersicherheit.

What is Data Encoding? Was ist Datenkodierung?

At their core, computers only understand numbers, specifically binary numbers, zeros and ones. Im Kern verstehen Computer nur Zahlen, genauer gesagt Binärzahlen, Nullen und Einsen.

Data encoding is the process of converting information, like text, images, or other data, into a specific format, often binary, so that computers can store, process, and transmit it. Datenkodierung ist der Prozess, Informationen wie Text, Bilder oder andere Daten in ein bestimmtes Format umzuwandeln, oft binär, damit Computer sie speichern, verarbeiten und übertragen können.

Conversely, decoding is translating that format back into a human-readable or usable form. Umgekehrt ist Dekodierung das Übersetzen dieses Formats zurück in eine menschenlesbare oder nutzbare Form.

Think of it like Morse code: dots and dashes represent letters, allowing communication over telegraph wires. Stell es dir wie Morse-Code vor: Punkte und Striche repräsentieren Buchstaben und ermöglichen Kommunikation über Telegrafenleitungen.

Similarly, data encodings use patterns, often of bits, to represent different kinds of information within computer systems. Ähnlich verwenden Datenkodierungen Muster, oft aus Bits, um verschiedene Arten von Informationen innerhalb von Computersystemen darzustellen.

Binary Basics Recap. Wiederholung der Binär-Grundlagen.

From our previous lesson on Numeral Systems, you'll remember that computers use the binary system, base two. Aus unserer vorherigen Lektion über Zahlensysteme wirst du dich erinnern, dass Computer das Binärsystem verwenden, Basis zwei.

Each digit in binary is called a bit, and it can be either a zero or a one. Jede Ziffer im Binärsystem wird Bit genannt, und sie kann entweder eine Null oder eine Eins sein.

Eight bits together form a byte. Acht Bits zusammen bilden ein Byte.

For example: The decimal number sixty-five is represented in binary as zero one zero zero zero zero zero one. Zum Beispiel: Die Dezimalzahl fünfundsechzig wird im Binärsystem dargestellt als null eins null null null null null eins.

The decimal number ninety-seven is represented in binary as zero one one zero zero zero zero one. Die Dezimalzahl siebenundneunzig wird im Binärsystem dargestellt als null eins eins null null null null eins.

Computers use these binary patterns to represent everything. Computer verwenden diese Binärmuster, um alles darzustellen.

But how do they represent letters, symbols, and other characters we use every day? Aber wie stellen sie Buchstaben, Symbole und andere Zeichen dar, die wir täglich verwenden?

Character Encoding: Giving Meaning to Bits. Zeichenkodierung: Bits Bedeutung geben.

To represent text, computers need a standard way to map characters, like A, b, exclamation mark, question mark, to specific binary numbers. Um Text darzustellen, benötigen Computer eine Standardmethode, um Zeichen wie A, b, Ausrufezeichen, Fragezeichen auf bestimmte Binärzahlen abzubilden.

This mapping is called character encoding. Diese Abbildung wird Zeichenkodierung genannt.

Without a standard encoding, one computer might interpret zero one zero zero zero zero zero one as A, while another might think it's Z, leading to chaos! Ohne eine Standardkodierung könnte ein Computer null eins null null null null null eins als A interpretieren, während ein anderer denkt, es sei Z, was zu Chaos führt!

ASCII: The Grandfather of Character Sets. ASCII: Der Großvater der Zeichensätze.

One of the earliest and most influential character encoding standards is ASCII, American Standard Code for Information Interchange. Einer der frühesten und einflussreichsten Zeichenkodierungsstandards ist ASCII, American Standard Code for Information Interchange.

Structure: Standard ASCII uses seven bits to represent characters. Struktur: Standard-ASCII verwendet sieben Bits, um Zeichen darzustellen.

Since seven bits can represent two to the power of seven equals one hundred twenty-eight different values, zero to one hundred twenty-seven, ASCII defines mappings for these numbers. Da sieben Bits zwei hoch sieben gleich einhundertachtundzwanzig verschiedene Werte darstellen können, null bis einhundertsiebenundzwanzig, definiert ASCII Zuordnungen für diese Zahlen.

Content: It includes uppercase and lowercase English letters, A through Z, a through z. Inhalt: Es umfasst Groß- und Kleinbuchstaben des englischen Alphabets, A bis Z, a bis z.

Digits, zero through nine. Ziffern, null bis neun.

Common punctuation symbols, like exclamation mark, at sign, hash, dollar sign, etcetera. Gängige Satzzeichen wie Ausrufezeichen, At-Zeichen, Raute, Dollarzeichen, et cetera.

Control characters, like newline, tab, backspace. These aren't printed but control how text is displayed or processed. Steuerzeichen wie Zeilenumbruch, Tabulator, Rücktaste. Diese werden nicht gedruckt, sondern steuern, wie Text angezeigt oder verarbeitet wird.

Example: The character A is assigned the decimal value sixty-five, which is zero one zero zero zero zero zero one in binary. Beispiel: Dem Zeichen A wird der Dezimalwert fünfundsechzig zugewiesen, was null eins null null null null null eins im Binärsystem ist.

The character a is assigned the decimal value ninety-seven, which is zero one one zero zero zero zero one in binary. Dem Zeichen a wird der Dezimalwert siebenundneunzig zugewiesen, was null eins eins null null null null eins im Binärsystem ist.

The character exclamation mark is assigned the decimal value thirty-three, which is zero zero one zero zero zero zero one in binary. Dem Zeichen Ausrufezeichen wird der Dezimalwert dreiunddreißig zugewiesen, was null null eins null null null null eins im Binärsystem ist.

Try it yourself. Probiere es selbst aus.

Most systems have an ASCII table available. Die meisten Systeme haben eine ASCII-Tabelle verfügbar.

On mac O S or Linux, you can often use the man ascii command in your terminal to view it. Auf mac O S oder Linux kannst du oft den Befehl man ascii in deinem Terminal verwenden, um sie anzuzeigen.

Find the ASCII decimal and binary values for your first initial in uppercase, the dollar symbol, and the space character. Finde die ASCII-Dezimal- und Binärwerte für deinen ersten Buchstaben in Großschreibung, das Dollarzeichen und das Leerzeichen.

ASCII's Limitations. Die Einschränkungen von ASCII.

ASCII was revolutionary, but it was designed primarily for English. ASCII war revolutionär, aber es wurde hauptsächlich für Englisch entwickelt.

It has no way to represent characters from other languages, like German umlauts ä, ö, ü, French accents é, à, ç, or characters from Greek, Cyrillic, Chinese, Japanese, etcetera. Es hat keine Möglichkeit, Zeichen aus anderen Sprachen darzustellen, wie deutsche Umlaute ä, ö, ü, französische Akzente é, à, ç, oder Zeichen aus dem Griechischen, Kyrillischen, Chinesischen, Japanischen, et cetera.

This limitation became a major problem as computing became global. Diese Einschränkung wurde zu einem großen Problem, als Computer global wurden.

Unicode and UTF-8: The Universal Solution. Unicode und UTF-8: Die universelle Lösung.

To address ASCII's limitations, Unicode was developed. Um die Einschränkungen von ASCII zu beheben, wurde Unicode entwickelt.

Concept: Unicode is a universal character set that aims to assign a unique number, called a code point, to every character in every language, plus symbols, emojis, and more. Konzept: Unicode ist ein universeller Zeichensatz, der darauf abzielt, jedem Zeichen in jeder Sprache eine eindeutige Nummer zuzuweisen, die Code Point genannt wird, plus Symbole, Emojis und mehr.

It defines over one hundred forty-nine thousand characters! Es definiert über einhundertneunundvierzigtausend Zeichen!

Encoding Forms: Unicode itself is just the standard mapping characters to code points. Kodierungsformen: Unicode selbst ist nur die Standardzuordnung von Zeichen zu Code Points.

To store or transmit these code points as binary data, we need an encoding form. Um diese Code Points als Binärdaten zu speichern oder zu übertragen, benötigen wir eine Kodierungsform.

The most common one by far is UTF-8, Unicode Transformation Format, eight-bit. Die mit Abstand gebräuchlichste ist UTF-8, Unicode Transformation Format, acht Bit.

UTF-8: Variable-Width. UTF-8: Variable Breite.

UTF-8 is clever because it uses a variable number of bytes per character. UTF-8 ist clever, weil es eine variable Anzahl von Bytes pro Zeichen verwendet.

For characters that are also in the original ASCII set, code points zero through one hundred twenty-seven, UTF-8 uses just one byte, identical to the ASCII representation. Für Zeichen, die auch im ursprünglichen ASCII-Satz enthalten sind, Code Points null bis einhundertsiebenundzwanzig, verwendet UTF-8 nur ein Byte, identisch mit der ASCII-Darstellung.

This makes it backward compatible with ASCII! Das macht es rückwärtskompatibel mit ASCII!

For characters outside the ASCII range, like the Euro sign, ü, é, or the Chinese character for cat, UTF-8 uses two, three, or even four bytes. Für Zeichen außerhalb des ASCII-Bereichs, wie das Euro-Zeichen, ü, é oder das chinesische Zeichen für Katze, verwendet UTF-8 zwei, drei oder sogar vier Bytes.

Dominance: UTF-8 is the dominant character encoding on the Web and in most modern systems because of its universality and backward compatibility with ASCII. Dominanz: UTF-8 ist die vorherrschende Zeichenkodierung im Web und in den meisten modernen Systemen aufgrund seiner Universalität und Rückwärtskompatibilität mit ASCII.

Think about it. Denk darüber nach.

Why is backward compatibility with ASCII a significant advantage for UTF-8? Warum ist Rückwärtskompatibilität mit ASCII ein bedeutender Vorteil für UTF-8?

What problems might occur if a file saved using UTF-8 encoding is mistakenly opened as if it were encoded in plain ASCII? Welche Probleme könnten auftreten, wenn eine Datei, die mit UTF-8-Kodierung gespeichert wurde, fälschlicherweise geöffnet wird, als wäre sie in reinem ASCII kodiert?

Base64 Encoding: Representing Binary Data as Text. Base64-Kodierung: Binärdaten als Text darstellen.

Sometimes, we need to send or store binary data, like images, compiled programs, or compressed files, in systems that are designed primarily for text, like email or some web protocols. Manchmal müssen wir Binärdaten wie Bilder, kompilierte Programme oder komprimierte Dateien in Systemen senden oder speichern, die hauptsächlich für Text konzipiert sind, wie E-Mail oder einige Web-Protokolle.

These systems might misinterpret certain byte values found in raw binary data, corrupting the data. Diese Systeme könnten bestimmte Bytewerte in rohen Binärdaten falsch interpretieren und die Daten beschädigen.

Base64 is an encoding scheme designed to solve this problem. Base64 ist ein Kodierungsschema, das entwickelt wurde, um dieses Problem zu lösen.

It translates any binary data into a sequence of printable ASCII characters. Es übersetzt beliebige Binärdaten in eine Sequenz druckbarer ASCII-Zeichen.

Purpose: To make binary data safe for transmission over text-only channels. Zweck: Binärdaten für die Übertragung über reine Textkanäle sicher zu machen.

Mechanism, simplified: It takes the binary data stream three bytes, twenty-four bits, at a time. Mechanismus, vereinfacht: Es nimmt den Binärdatenstrom drei Bytes, vierundzwanzig Bits, auf einmal.

It divides these twenty-four bits into four six-bit chunks. Es teilt diese vierundzwanzig Bits in vier Sechs-Bit-Blöcke.

Each six-bit chunk can represent two to the power of six equals sixty-four different values, zero through sixty-three. Jeder Sechs-Bit-Block kann zwei hoch sechs gleich vierundsechzig verschiedene Werte darstellen, null bis dreiundsechzig.

These sixty-four values are mapped to a specific set of sixty-four printable ASCII characters: A through Z, a through z, zero through nine, plus, and slash. Diese vierundsechzig Werte werden auf einen bestimmten Satz von vierundsechzig druckbaren ASCII-Zeichen abgebildet: A bis Z, a bis z, null bis neun, Plus und Schrägstrich.

If the original binary data isn't a multiple of three bytes, padding characters, equals signs, are added at the end of the Base64 output to make the total length a multiple of four characters. Wenn die ursprünglichen Binärdaten kein Vielfaches von drei Bytes sind, werden Füllzeichen, Gleichheitszeichen, am Ende der Base64-Ausgabe hinzugefügt, um die Gesamtlänge zu einem Vielfachen von vier Zeichen zu machen.

Important: Base64 is an encoding, not encryption. Wichtig: Base64 ist eine Kodierung, keine Verschlüsselung.

It's easily reversible, decoded, by anyone who knows it's Base64. Sie ist leicht umkehrbar, dekodierbar, von jedem, der weiß, dass es Base64 ist.

It provides no confidentiality or security, only a way to safely represent binary data in text environments. Sie bietet keine Vertraulichkeit oder Sicherheit, nur eine Möglichkeit, Binärdaten in Textumgebungen sicher darzustellen.

Example: Let's encode the three-byte ASCII string Man. Beispiel: Lasst uns die Drei-Byte-ASCII-Zeichenkette Man kodieren.

ASCII: M equals seventy-seven, a equals ninety-seven, n equals one hundred ten. ASCII: M entspricht siebenundsiebzig, a entspricht siebenundneunzig, n entspricht einhundertzehn.

Binary, eight bits per character: zero one zero zero one one zero one, zero one one zero zero zero zero one, zero one one zero one one one zero, which is twenty-four bits total. Binär, acht Bits pro Zeichen: null eins null null eins eins null eins, null eins eins null null null null eins, null eins eins null eins eins eins null, was insgesamt vierundzwanzig Bits ergibt.

Split into six-bit chunks: zero one zero zero one one, zero one zero one one zero, zero zero zero one zero one, one zero one one one zero. Aufgeteilt in Sechs-Bit-Blöcke: null eins null null eins eins, null eins null eins eins null, null null null eins null eins, eins null eins eins eins null.

Decimal value of chunks: nineteen, twenty-two, five, forty-six. Dezimalwert der Blöcke: neunzehn, zweiundzwanzig, fünf, sechsundvierzig.

Map to Base64 characters: zero equals A, one equals B, and so on, twenty-five equals Z, twenty-six equals a, and so on, fifty-one equals z, fifty-two equals zero, and so on, sixty-one equals nine, sixty-two equals plus, sixty-three equals slash. Abbildung auf Base64-Zeichen: null entspricht A, eins entspricht B, und so weiter, fünfundzwanzig entspricht Z, sechsundzwanzig entspricht a, und so weiter, einundfünfzig entspricht z, zweiundfünfzig entspricht null, und so weiter, einundsechzig entspricht neun, zweiundsechzig entspricht Plus, dreiundsechzig entspricht Schrägstrich.

Nineteen becomes T, twenty-two becomes W, five becomes F, forty-six becomes u. Neunzehn wird T, zweiundzwanzig wird W, fünf wird F, sechsundvierzig wird u.

Result: T W F u. Ergebnis: T W F u.

Try it yourself. Probiere es selbst aus.

Use an online Base64 encoder slash decoder. Search for Base64 encode online. Verwende einen Online-Base64-Encoder slash Decoder. Suche nach Base64 encode online.

Encode the text: Hello World exclamation mark. Kodiere den Text: Hello World Ausrufezeichen.

Decode the text: U E M space i X M space Z n V u I Q equals equals. What does it say? Dekodiere den Text: U E M Leerzeichen i X M Leerzeichen Z n V u I Q gleich gleich. Was sagt es?

Think about it. Denk darüber nach.

Why is it crucial to understand that Base64 is not encryption, especially in cybersecurity? Warum ist es entscheidend zu verstehen, dass Base64 keine Verschlüsselung ist, besonders in der Cybersicherheit?

Can you think of situations where sending binary data directly might cause problems in text-based systems? Kannst du dir Situationen vorstellen, in denen das direkte Senden von Binärdaten Probleme in textbasierten Systemen verursachen könnte?

That's it for the pre-class preparation! Das war's für die Vorbereitung vor dem Unterricht!

Come to the live session ready to discuss these concepts and see them in action. Komm zur Live-Sitzung bereit, diese Konzepte zu diskutieren und sie in Aktion zu sehen.