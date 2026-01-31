Welcome to the world of Regular Expressions, often shortened to regex or regexp! Willkommen in der Welt der regulären Ausdrücke, oft abgekürzt als Regex oder Regexp!

This is an incredibly powerful tool for text processing, pattern matching, and data extraction. Dies ist ein unglaublich mächtiges Werkzeug für Textverarbeitung, Mustererkennung und Datenextraktion.

You'll find regex indispensable for a wide variety of tasks, from simple text searches to complex data manipulation across many fields. Du wirst Regex als unverzichtbar für eine Vielzahl von Aufgaben finden, von einfachen Textsuchen bis zu komplexer Datenmanipulation in vielen Bereichen.

This preparation material will introduce you to the fundamental concepts. Dieses Vorbereitungsmaterial wird dich in die grundlegenden Konzepte einführen.

What are Regular Expressions? Was sind reguläre Ausdrücke?

At its core, a regular expression is a sequence of characters that defines a search pattern. Im Kern ist ein regulärer Ausdruck eine Sequenz von Zeichen, die ein Suchmuster definiert.

Think of it as a highly specialized find and replace tool on steroids. Denk daran wie an ein hochspezialisiertes Suchen-und-Ersetzen-Werkzeug auf Steroiden.

Instead of searching for a fixed, literal string, you can search for patterns. Anstatt nach einer festen, wörtlichen Zeichenkette zu suchen, kannst du nach Mustern suchen.

For example, you could use a regex to find all email addresses in a document. Zum Beispiel könntest du einen Regex verwenden, um alle E-Mail-Adressen in einem Dokument zu finden.

All IP addresses in a log file. Alle IP-Adressen in einer Log-Datei.

All lines in a configuration file that start with a specific word. Alle Zeilen in einer Konfigurationsdatei, die mit einem bestimmten Wort beginnen.

All strings that look like a date or a phone number. Alle Zeichenketten, die wie ein Datum oder eine Telefonnummer aussehen.

Specific code structures or syntax errors in program files. Bestimmte Codestrukturen oder Syntaxfehler in Programmdateien.

Why are they important in Cybersecurity? Warum sind sie wichtig in der Cybersicherheit?

In cybersecurity, regular expressions are like a digital magnifying glass and a super-fast sorting tool combined. In der Cybersicherheit sind reguläre Ausdrücke wie eine digitale Lupe und ein superschnelles Sortierwerkzeug kombiniert.

They help professionals quickly find specific pieces of text-based information that could indicate a security issue or help in an investigation. Sie helfen Fachleuten, schnell bestimmte Teile textbasierter Informationen zu finden, die auf ein Sicherheitsproblem hinweisen oder bei einer Untersuchung helfen könnten.

Here's how. So funktioniert es.

Finding Needles in Haystacks, Log Analysis. Nadeln im Heuhaufen finden, Log-Analyse.

Imagine searching through millions of lines of computer logs. Stell dir vor, durch Millionen von Zeilen Computer-Logs zu suchen.

Regex can quickly pinpoint suspicious activity, like multiple failed login attempts from the same IP address, or specific error messages that might signal an attack. Regex kann schnell verdächtige Aktivitäten lokalisieren, wie mehrere fehlgeschlagene Login-Versuche von derselben IP-Adresse oder bestimmte Fehlermeldungen, die einen Angriff signalisieren könnten.

Spotting Bad Stuff, Intrusion Detection slash Prevention. Schlechte Dinge erkennen, Intrusion Detection Schrägstrich Prevention.

Security systems, IDS slash IPS, often use regex to define patterns of known malicious code, like viruses or malware signatures, or network traffic that looks like an attack. Sicherheitssysteme, IDS Schrägstrich IPS, verwenden oft Regex, um Muster bekannter bösartiger Codes zu definieren, wie Viren oder Malware-Signaturen, oder Netzwerkverkehr, der wie ein Angriff aussieht.

If data matches these bad patterns, the system can raise an alarm or block it. Wenn Daten mit diesen schlechten Mustern übereinstimmen, kann das System Alarm schlagen oder sie blockieren.

Validating Information, Data Validation. Informationen validieren, Datenvalidierung.

When systems ask for input, like a username or an email address, regex can check if the input looks correct. Wenn Systeme nach Eingaben fragen, wie einem Benutzernamen oder einer E-Mail-Adresse, kann Regex überprüfen, ob die Eingabe korrekt aussieht.

This helps prevent errors and can stop some types of attacks where attackers try to submit malicious or malformed data. Dies hilft, Fehler zu vermeiden und kann einige Arten von Angriffen stoppen, bei denen Angreifer versuchen, bösartige oder fehlerhafte Daten einzureichen.

Pulling Out Clues, Data Extraction and Forensics. Hinweise herausziehen, Datenextraktion und Forensik.

During a security investigation, digital forensics, regex can be used to extract specific artifacts from large amounts of data. Während einer Sicherheitsuntersuchung, digitale Forensik, kann Regex verwendet werden, um bestimmte Artefakte aus großen Datenmengen zu extrahieren.

Such as email addresses, credit card numbers, or fragments of malicious scripts from compromised files or network captures. Wie E-Mail-Adressen, Kreditkartennummern oder Fragmente bösartiger Skripte aus kompromittierten Dateien oder Netzwerkerfassungen.

Automating Security Tasks, Scripting. Sicherheitsaufgaben automatisieren, Skripting.

Cybersecurity professionals often write scripts to automate repetitive tasks. Cybersicherheitsfachleute schreiben oft Skripte, um sich wiederholende Aufgaben zu automatisieren.

Regex is a key part of these scripts for parsing command outputs, configuration files, or scan results to identify relevant security information. Regex ist ein wichtiger Teil dieser Skripte zum Parsen von Befehlsausgaben, Konfigurationsdateien oder Scan-Ergebnissen, um relevante Sicherheitsinformationen zu identifizieren.

Understanding Malware. Malware verstehen.

Analysts use regex to dissect malware code, looking for patterns like specific function calls, embedded URLs, or encryption keys that help them understand what the malware does and how to stop it. Analysten verwenden Regex, um Malware-Code zu zerlegen und nach Mustern wie bestimmten Funktionsaufrufen, eingebetteten URLs oder Verschlüsselungsschlüsseln zu suchen, die ihnen helfen zu verstehen, was die Malware tut und wie man sie stoppt.

Essentially, regex helps cybersecurity experts to efficiently sift through vast amounts of text data to identify threats, understand attacks, and protect systems. Im Wesentlichen hilft Regex Cybersicherheitsexperten, effizient durch riesige Mengen an Textdaten zu sichten, um Bedrohungen zu identifizieren, Angriffe zu verstehen und Systeme zu schützen.

Testing Your Regex: Online Tools. Deinen Regex testen: Online-Werkzeuge.

The best way to learn and understand regular expressions is by experimenting with them. Der beste Weg, reguläre Ausdrücke zu lernen und zu verstehen, ist, mit ihnen zu experimentieren.

Online regex testers are fantastic for this. Online-Regex-Tester sind fantastisch dafür.

They let you type a regex pattern, provide some test text, and see immediately what your pattern matches or doesn't match. Sie ermöglichen es dir, ein Regex-Muster einzugeben, einen Testtext bereitzustellen und sofort zu sehen, was dein Muster findet oder nicht findet.

They often provide explanations of your regex too. Sie bieten oft auch Erklärungen deines Regex.

For our purposes, we recommend using Regex one zero one dot com. Für unsere Zwecke empfehlen wir die Verwendung von Regex eins null eins Punkt com.

Let's get started with Regex one zero one. Lass uns mit Regex eins null eins beginnen.

Open your web browser and navigate to https colon slash slash regex one zero one dot com. Öffne deinen Webbrowser und navigiere zu https Doppelpunkt Schrägstrich Schrägstrich regex eins null eins Punkt com.

You'll see a few main areas. Du wirst einige Hauptbereiche sehen.

REGULAR EXPRESSION field at the top: This is where you'll type your regex patterns. REGULAR EXPRESSION Feld oben: Hier gibst du deine Regex-Muster ein.

TEST STRING field in the middle: This is where you'll put the text you want to search within. TEST STRING Feld in der Mitte: Hier fügst du den Text ein, in dem du suchen möchtest.

EXPLANATION on the right sidebar: Regex one zero one does a great job of breaking down your pattern and explaining what each part does. EXPLANATION in der rechten Seitenleiste: Regex eins null eins leistet großartige Arbeit beim Zerlegen deines Musters und Erklären, was jeder Teil tut.

MATCH INFORMATION below TEST STRING or on the right: This shows you what parts of your test string were matched by your regex. MATCH INFORMATION unter TEST STRING oder rechts: Dies zeigt dir, welche Teile deines Teststrings von deinem Regex gefunden wurden.

FLAVOR on the left sidebar, often defaults to PCRE two: Regex has different flavors or versions with slight variations. FLAVOR in der linken Seitenleiste, oft standardmäßig PCRE zwei: Regex hat verschiedene Varianten oder Versionen mit leichten Unterschieden.

Python uses a flavor very similar to PCRE, Perl Compatible Regular Expressions. Python verwendet eine Variante, die PCRE sehr ähnlich ist, Perl Compatible Regular Expressions.

For now, the default PCRE two on Regex one zero one is fine. Vorerst ist das Standard-PCRE zwei auf Regex eins null eins in Ordnung.

Keep Regex one zero one open as you go through the concepts below. Halte Regex eins null eins offen, während du die Konzepte unten durchgehst.

Try out the examples and experiment! Probiere die Beispiele aus und experimentiere!

Basic Building Blocks of Regex. Grundlegende Bausteine von Regex.

Regular expressions are built from a combination of literal characters and special characters called metacharacters. Reguläre Ausdrücke werden aus einer Kombination von wörtlichen Zeichen und speziellen Zeichen namens Metazeichen aufgebaut.

Literal Characters. Wörtliche Zeichen.

The simplest form of regex is a literal string. Die einfachste Form von Regex ist eine wörtliche Zeichenkette.

Definition: A literal character is a character that matches itself. Definition: Ein wörtliches Zeichen ist ein Zeichen, das sich selbst entspricht.

For example, the regex a matches the letter a, and the regex hello matches the string hello. Zum Beispiel entspricht der Regex a dem Buchstaben a, und der Regex hello entspricht der Zeichenkette hello.

Example: If your regex is log and your test string is catalog, it will match log. Beispiel: Wenn dein Regex log ist und dein Teststring catalog ist, wird es log finden.

Try it on Regex one zero one. Probiere es auf Regex eins null eins aus.

In the REGULAR EXPRESSION field on Regex one zero one, type cat. Im REGULAR EXPRESSION Feld auf Regex eins null eins, gib cat ein.

In the TEST STRING field, type: The cat sat on the mat. The catalog was on the table. Im TEST STRING Feld, gib ein: The cat sat on the mat. The catalog was on the table.

Observe how cat is highlighted in both cat and catalog. Beobachte, wie cat sowohl in cat als auch in catalog hervorgehoben wird.

Metacharacters. Metazeichen.

Metacharacters are the heart of regex power. Metazeichen sind das Herz der Regex-Kraft.

They don't represent themselves but rather have special meanings. Sie repräsentieren sich nicht selbst, sondern haben besondere Bedeutungen.

Anchors. Anker.

Anchors specify the position in the string where a match must occur. Anker geben die Position in der Zeichenkette an, wo eine Übereinstimmung auftreten muss.

They don't match actual characters but rather invisible positions. Sie finden keine tatsächlichen Zeichen, sondern unsichtbare Positionen.

Caret: Matches the beginning of a line or string. Caret: Findet den Anfang einer Zeile oder Zeichenkette.

Example: Caret Start will match Start of the line but not This is the Start. Beispiel: Caret Start wird Start of the line finden, aber nicht This is the Start.

Dollar sign: Matches the end of a line or string. Dollarzeichen: Findet das Ende einer Zeile oder Zeichenkette.

Example: end dollar sign will match This is the end but not end of the line. Beispiel: end Dollarzeichen wird This is the end finden, aber nicht end of the line.

Backslash b: Matches a word boundary. Backslash b: Findet eine Wortgrenze.

A word boundary is a position between a word character, letter, digit, or underscore, and a non-word character, or at the beginning slash end of a string if the first slash last characters are word characters. Eine Wortgrenze ist eine Position zwischen einem Wortzeichen, Buchstabe, Ziffer oder Unterstrich, und einem Nicht-Wortzeichen, oder am Anfang Schrägstrich Ende einer Zeichenkette, wenn die ersten Schrägstrich letzten Zeichen Wortzeichen sind.

Example: Backslash b cat backslash b will match cat in The cat sat but not in catalog or concatenate. Beispiel: Backslash b cat backslash b wird cat in The cat sat finden, aber nicht in catalog oder concatenate.

Backslash B: Matches a non-word boundary. Backslash B: Findet eine Nicht-Wortgrenze.

Example: Backslash B cat backslash B would match cat in concatenate but not in the cat. Beispiel: Backslash B cat backslash B würde cat in concatenate finden, aber nicht in the cat.

Try it on Regex one zero one. Probiere es auf Regex eins null eins aus.

Test string: cat catalog, newline, concatenate cat. Teststring: cat catalog, neue Zeile, concatenate cat.

Try the regex caret cat. What does it match? Probiere den Regex Caret cat. Was findet er?

Try cat dollar sign. What does it match? Probiere cat Dollarzeichen. Was findet er?

Try backslash b cat backslash b. How is this different from just cat? Probiere Backslash b cat Backslash b. Wie unterscheidet sich das von nur cat?

Try backslash B cat backslash B. Probiere Backslash B cat Backslash B.

Character Classes, Character Sets. Zeichenklassen, Zeichensätze.

Character classes allow you to define a set of characters you want to match at a particular position. Zeichenklassen ermöglichen es dir, eine Menge von Zeichen zu definieren, die du an einer bestimmten Position finden möchtest.

Dot: Matches any single character except for a newline character by default. Punkt: Findet jedes einzelne Zeichen außer einem Zeilenumbruchzeichen standardmäßig.

Example: a dot c will match abc, a one c, a ampersand c, etcetera, but not a backslash n c. Beispiel: a Punkt c wird abc, a eins c, a Ampersand c, et cetera finden, aber nicht a Backslash n c.

Square brackets: Matches any single character that is contained within the brackets. Eckige Klammern: Findet jedes einzelne Zeichen, das innerhalb der Klammern enthalten ist.

Example: Opening bracket a e i o u closing bracket will match any lowercase vowel. Beispiel: Öffnende Klammer a e i o u schließende Klammer wird jeden Kleinbuchstaben-Vokal finden.

Opening bracket zero dash nine closing bracket will match any digit. Öffnende Klammer null Bindestrich neun schließende Klammer wird jede Ziffer finden.

Opening bracket a dash z A dash Z closing bracket will match any uppercase or lowercase letter. Öffnende Klammer a Bindestrich z A Bindestrich Z schließende Klammer wird jeden Groß- oder Kleinbuchstaben finden.

Ranges can be specified: opening bracket a dash f zero dash five closing bracket matches a through f or zero through five. Bereiche können angegeben werden: öffnende Klammer a Bindestrich f null Bindestrich fünf schließende Klammer findet a bis f oder null bis fünf.

Opening bracket caret dot dot dot closing bracket, Negated square brackets: Matches any single character that is not contained within the brackets after the caret. Öffnende Klammer Caret Punkt Punkt Punkt schließende Klammer, negierte eckige Klammern: Findet jedes einzelne Zeichen, das nicht innerhalb der Klammern nach dem Caret enthalten ist.

Example: opening bracket caret zero dash nine closing bracket will match any character that is not a digit. Beispiel: öffnende Klammer Caret null Bindestrich neun schließende Klammer wird jedes Zeichen finden, das keine Ziffer ist.

Opening bracket caret a e i o u closing bracket will match any character that is not a lowercase vowel. Öffnende Klammer Caret a e i o u schließende Klammer wird jedes Zeichen finden, das kein Kleinbuchstaben-Vokal ist.

Try it on Regex one zero one. Probiere es auf Regex eins null eins aus.

Test string: Can you find c dot t, c at sign t, c space t, but not coat? Also numbers one two three and symbols hash question mark exclamation mark. Teststring: Can you find c Punkt t, c at-Zeichen t, c Leerzeichen t, but not coat? Also numbers eins zwei drei and symbols Raute Fragezeichen Ausrufezeichen.

Try c dot t. What does it match? Probiere c Punkt t. Was findet es?

Try c opening bracket a e i o u closing bracket t. Probiere c öffnende Klammer a e i o u schließende Klammer t.

Try opening bracket caret zero dash nine closing bracket. What does it match? It will match many things! Probiere öffnende Klammer Caret null Bindestrich neun schließende Klammer. Was findet es? Es wird viele Dinge finden!

Try opening bracket zero dash nine closing bracket. Probiere öffnende Klammer null Bindestrich neun schließende Klammer.

Predefined Character Classes. Vordefinierte Zeichenklassen.

For convenience, regex offers several predefined character classes, these are often called shorthand character classes. Der Einfachheit halber bietet Regex mehrere vordefinierte Zeichenklassen, diese werden oft Kurzzeichen-Klassen genannt.

Backslash d: Matches any digit. Equivalent to opening bracket zero dash nine closing bracket. Backslash d: Findet jede Ziffer. Entspricht öffnende Klammer null Bindestrich neun schließende Klammer.

Backslash D: Matches any non-digit character. Equivalent to opening bracket caret zero dash nine closing bracket. Backslash D: Findet jedes Nicht-Ziffern-Zeichen. Entspricht öffnende Klammer Caret null Bindestrich neun schließende Klammer.

Backslash w: Matches any word character, alphanumeric characters: a dash z, A dash Z, zero dash nine, plus underscore. Backslash w: Findet jedes Wortzeichen, alphanumerische Zeichen: a Bindestrich z, A Bindestrich Z, null Bindestrich neun, plus Unterstrich.

Equivalent to opening bracket a dash z A dash Z zero dash nine underscore closing bracket. Entspricht öffnende Klammer a Bindestrich z A Bindestrich Z null Bindestrich neun Unterstrich schließende Klammer.

Backslash W: Matches any non-word character. Equivalent to opening bracket caret a dash z A dash Z zero dash nine underscore closing bracket. Backslash W: Findet jedes Nicht-Wortzeichen. Entspricht öffnende Klammer Caret a Bindestrich z A Bindestrich Z null Bindestrich neun Unterstrich schließende Klammer.

Backslash s: Matches any whitespace character, space, tab, newline, carriage return, form feed, vertical tab. Backslash s: Findet jedes Leerraumzeichen, Leerzeichen, Tabulator, Zeilenumbruch, Wagenrücklauf, Seitenvorschub, vertikaler Tabulator.

Backslash S: Matches any non-whitespace character. Backslash S: Findet jedes Nicht-Leerraumzeichen.

Try it on Regex one zero one. Probiere es auf Regex eins null eins aus.

Test string: IP: one nine two dot one six eight dot one dot one Date: two zero two four dash zero five dash one seven User underscore ID: test underscore user. Teststring: IP: eins neun zwei Punkt eins sechs acht Punkt eins Punkt eins Date: zwei null zwei vier Bindestrich null fünf Bindestrich eins sieben User Unterstrich ID: test Unterstrich user.

Try backslash d backslash d backslash d. What does it match? Probiere Backslash d Backslash d Backslash d. Was findet es?

Try backslash w plus. We'll cover plus next, but for now, it means one or more. Probiere Backslash w Plus. Wir werden Plus als Nächstes behandeln, aber vorerst bedeutet es eins oder mehr.

Try backslash s. How many matches do you get? Probiere Backslash s. Wie viele Treffer bekommst du?

Quantifiers. Quantifikatoren.

Quantifiers specify how many times a preceding character, group, or character class must occur to be considered a match. Quantifikatoren geben an, wie oft ein vorausgehendes Zeichen, eine Gruppe oder eine Zeichenklasse vorkommen muss, um als Übereinstimmung betrachtet zu werden.

Asterisk: Matches the preceding item zero or more times. Sternchen: Findet das vorausgehende Element null oder mehr Male.

Example: a b asterisk c will match ac, zero bs, abc, one b, abbc, two bs, etcetera. Beispiel: a b Sternchen c wird ac finden, null bs, abc, ein b, abbc, zwei bs, et cetera.

Plus sign: Matches the preceding item one or more times. Pluszeichen: Findet das vorausgehende Element ein oder mehr Male.

Example: a b plus c will match abc, abbc, but not ac. Beispiel: a b Plus c wird abc, abbc finden, aber nicht ac.

Question mark: Matches the preceding item zero or one time. It makes the preceding item optional. Fragezeichen: Findet das vorausgehende Element null oder ein Mal. Es macht das vorausgehende Element optional.

Example: c o l o u question mark r will match color, zero us, and colour, one u. Beispiel: c o l o u Fragezeichen r wird color finden, null us, und colour, ein u.

Opening brace n closing brace: Matches the preceding item exactly n times. Öffnende geschweifte Klammer n schließende geschweifte Klammer: Findet das vorausgehende Element genau n Mal.

Example: backslash d opening brace three closing brace will match exactly three digits, like one two three. Beispiel: Backslash d öffnende geschweifte Klammer drei schließende geschweifte Klammer wird genau drei Ziffern finden, wie eins zwei drei.

Opening brace n comma closing brace: Matches the preceding item n or more times. Öffnende geschweifte Klammer n Komma schließende geschweifte Klammer: Findet das vorausgehende Element n oder mehr Male.

Example: backslash d opening brace two comma closing brace will match two or more digits, like one two, one two three, one two three four. Beispiel: Backslash d öffnende geschweifte Klammer zwei Komma schließende geschweifte Klammer wird zwei oder mehr Ziffern finden, wie eins zwei, eins zwei drei, eins zwei drei vier.

Opening brace n comma m closing brace: Matches the preceding item at least n times but not more than m times. Öffnende geschweifte Klammer n Komma m schließende geschweifte Klammer: Findet das vorausgehende Element mindestens n Mal, aber nicht mehr als m Mal.

Example: backslash d opening brace two comma four closing brace will match one two, one two three, one two three four, but not one or one two three four five. Beispiel: Backslash d öffnende geschweifte Klammer zwei Komma vier schließende geschweifte Klammer wird eins zwei, eins zwei drei, eins zwei drei vier finden, aber nicht eins oder eins zwei drei vier fünf.

Try it on Regex one zero one. Probiere es auf Regex eins null eins aus.

Test string: err error errrror file one dot txt file zero one dot txt file zero zero one dot txt. Teststring: err error errrror file eins Punkt txt file null eins Punkt txt file null null eins Punkt txt.

Try e r asterisk o r. Probiere e r Sternchen o r.

Try e r plus o r. Probiere e r Plus o r.

Try file backslash d opening brace two closing brace backslash dot txt. What does backslash dot mean here? We'll cover it under Escaping. Probiere file Backslash d öffnende geschweifte Klammer zwei schließende geschweifte Klammer Backslash Punkt txt. Was bedeutet Backslash Punkt hier? Wir werden es unter Escaping behandeln.

Try e r r question mark o r. Probiere e r r Fragezeichen o r.

Greedy versus Non-Greedy, Lazy, Matching. Gierig versus Nicht-Gierig, Faul, Matching.

By default, quantifiers like asterisk, plus, and opening brace n comma m closing brace are greedy. Standardmäßig sind Quantifikatoren wie Sternchen, Plus und öffnende geschweifte Klammer n Komma m schließende geschweifte Klammer gierig.

This means they try to match as much text as possible while still allowing the overall regex to match. Das bedeutet, sie versuchen, so viel Text wie möglich zu finden, während sie immer noch dem gesamten Regex erlauben zu finden.

Example, Greedy: Given the string opening angle bracket div closing angle bracket Hello opening angle bracket slash div closing angle bracket opening angle bracket div closing angle bracket World opening angle bracket slash div closing angle bracket, the regex opening angle bracket div dot asterisk closing angle bracket would match the entire string. Beispiel, Gierig: Bei der Zeichenkette öffnende spitze Klammer div schließende spitze Klammer Hello öffnende spitze Klammer Schrägstrich div schließende spitze Klammer öffnende spitze Klammer div schließende spitze Klammer World öffnende spitze Klammer Schrägstrich div schließende spitze Klammer, würde der Regex öffnende spitze Klammer div Punkt Sternchen schließende spitze Klammer die gesamte Zeichenkette finden.

Because dot asterisk greedily consumes everything, including the first opening angle bracket slash div closing angle bracket opening angle bracket div closing angle bracket, until the very last closing angle bracket in the string. Weil Punkt Sternchen gierig alles konsumiert, einschließlich der ersten öffnenden spitzen Klammer Schrägstrich div schließenden spitzen Klammer öffnenden spitzen Klammer div schließenden spitzen Klammer, bis zur allerletzten schließenden spitzen Klammer in der Zeichenkette.

You can make a quantifier non-greedy or lazy by adding a question mark after it: asterisk question mark, plus question mark, opening brace n comma m closing brace question mark. Du kannst einen Quantifikator nicht-gierig oder faul machen, indem du ein Fragezeichen danach hinzufügst: Sternchen Fragezeichen, Plus Fragezeichen, öffnende geschweifte Klammer n Komma m schließende geschweifte Klammer Fragezeichen.

A non-greedy quantifier tries to match as little text as possible. Ein nicht-gieriger Quantifikator versucht, so wenig Text wie möglich zu finden.

Example, Non-Greedy: Given the same string, opening angle bracket div dot asterisk question mark closing angle bracket would match opening angle bracket div closing angle bracket Hello opening angle bracket slash div closing angle bracket. Beispiel, Nicht-Gierig: Bei derselben Zeichenkette würde öffnende spitze Klammer div Punkt Sternchen Fragezeichen schließende spitze Klammer öffnende spitze Klammer div schließende spitze Klammer Hello öffnende spitze Klammer Schrägstrich div schließende spitze Klammer finden.

As dot asterisk question mark matches up to the first closing angle bracket. Da Punkt Sternchen Fragezeichen bis zur ersten schließenden spitzen Klammer findet.

If you were to search again from the end of this match, it would then find opening angle bracket div closing angle bracket World opening angle bracket slash div closing angle bracket. Wenn du erneut vom Ende dieses Treffers suchen würdest, würde es dann öffnende spitze Klammer div schließende spitze Klammer World öffnende spitze Klammer Schrägstrich div schließende spitze Klammer finden.

Try it on Regex one zero one. Probiere es auf Regex eins null eins aus.

Test string: opening angle bracket b closing angle bracket Bold text opening angle bracket slash b closing angle bracket and opening angle bracket i closing angle bracket italic text opening angle bracket slash i closing angle bracket. Teststring: öffnende spitze Klammer b schließende spitze Klammer Bold text öffnende spitze Klammer Schrägstrich b schließende spitze Klammer and öffnende spitze Klammer i schließende spitze Klammer italic text öffnende spitze Klammer Schrägstrich i schließende spitze Klammer.

Try the greedy regex opening angle bracket dot asterisk closing angle bracket. What does it match? Probiere den gierigen Regex öffnende spitze Klammer Punkt Sternchen schließende spitze Klammer. Was findet er?

Try the non-greedy regex opening angle bracket dot asterisk question mark closing angle bracket. What does it match now? How many matches? Probiere den nicht-gierigen Regex öffnende spitze Klammer Punkt Sternchen Fragezeichen schließende spitze Klammer. Was findet er jetzt? Wie viele Treffer?

Grouping and Capturing. Gruppieren und Erfassen.

Parentheses: Groups multiple tokens together. This has two main effects. Runde Klammern: Gruppiert mehrere Token zusammen. Dies hat zwei Haupteffekte.

Apply quantifiers to the group: opening parenthesis a b closing parenthesis plus matches ab, abab, ababab, etcetera. The plus applies to the whole ab sequence. Quantifikatoren auf die Gruppe anwenden: öffnende runde Klammer a b schließende runde Klammer Plus findet ab, abab, ababab, et cetera. Das Plus gilt für die gesamte ab-Sequenz.

Create a capturing group: The text matched by the part of the regex inside the parentheses is captured and can be extracted or referred to later. Eine erfassende Gruppe erstellen: Der Text, der vom Teil des Regex innerhalb der Klammern gefunden wird, wird erfasst und kann später extrahiert oder darauf verwiesen werden.

Most regex tools number these groups starting from one. Die meisten Regex-Werkzeuge nummerieren diese Gruppen beginnend mit eins.

Example: opening parenthesis backslash d opening brace three closing brace closing parenthesis dash opening parenthesis backslash d opening brace three closing brace closing parenthesis dash opening parenthesis backslash d opening brace four closing brace closing parenthesis could match a phone number like one two three dash four five six dash seven eight nine zero. Beispiel: öffnende runde Klammer Backslash d öffnende geschweifte Klammer drei schließende geschweifte Klammer schließende runde Klammer Bindestrich öffnende runde Klammer Backslash d öffnende geschweifte Klammer drei schließende geschweifte Klammer schließende runde Klammer Bindestrich öffnende runde Klammer Backslash d öffnende geschweifte Klammer vier schließende geschweifte Klammer schließende runde Klammer könnte eine Telefonnummer wie eins zwei drei Bindestrich vier fünf sechs Bindestrich sieben acht neun null finden.

Group one would capture one two three. Gruppe eins würde eins zwei drei erfassen.

Group two would capture four five six. Gruppe zwei würde vier fünf sechs erfassen.

Group three would capture seven eight nine zero. Gruppe drei würde sieben acht neun null erfassen.

Sometimes you want to group for quantification but don't need to capture. This is a non-capturing group: opening parenthesis question mark colon dot dot dot closing parenthesis. Manchmal möchtest du für die Quantifizierung gruppieren, aber nicht erfassen. Dies ist eine nicht-erfassende Gruppe: öffnende runde Klammer Fragezeichen Doppelpunkt Punkt Punkt Punkt schließende runde Klammer.

Example: opening parenthesis question mark colon a b closing parenthesis plus groups ab for the plus but doesn't create a numbered capture group for ab. Beispiel: öffnende runde Klammer Fragezeichen Doppelpunkt a b schließende runde Klammer Plus gruppiert ab für das Plus, erstellt aber keine nummerierte Erfassungsgruppe für ab.

Try it on Regex one zero one. Probiere es auf Regex eins null eins aus.

Test string: ababab call one two three dash four five six dash seven eight nine zero or nine eight seven dash six five four dash three two one zero. Teststring: ababab call eins zwei drei Bindestrich vier fünf sechs Bindestrich sieben acht neun null or neun acht sieben Bindestrich sechs fünf vier Bindestrich drei zwei eins null.

Try opening parenthesis a b closing parenthesis plus. Notice the group information in Regex one zero one. Probiere öffnende runde Klammer a b schließende runde Klammer Plus. Beachte die Gruppeninformationen in Regex eins null eins.

Try opening parenthesis backslash d opening brace three closing brace closing parenthesis dash opening parenthesis backslash d opening brace three closing brace closing parenthesis dash opening parenthesis backslash d opening brace four closing brace closing parenthesis. Probiere öffnende runde Klammer Backslash d öffnende geschweifte Klammer drei schließende geschweifte Klammer schließende runde Klammer Bindestrich öffnende runde Klammer Backslash d öffnende geschweifte Klammer drei schließende geschweifte Klammer schließende runde Klammer Bindestrich öffnende runde Klammer Backslash d öffnende geschweifte Klammer vier schließende geschweifte Klammer schließende runde Klammer.

Examine the captured groups in the MATCH INFORMATION panel on Regex one zero one. Untersuche die erfassten Gruppen im MATCH INFORMATION Panel auf Regex eins null eins.

Alternation, OR. Alternation, ODER.

Pipe: Acts like an OR operator. Matches either the expression before or the expression after the pipe. Pipe: Wirkt wie ein ODER-Operator. Findet entweder den Ausdruck vor oder den Ausdruck nach dem Pipe.

Example: cat pipe dog will match cat or dog. Beispiel: cat Pipe dog wird cat oder dog finden.

It's often used within groups: caret opening parenthesis Error pipe Warning closing parenthesis colon will match lines starting with Error colon or Warning colon. Es wird oft innerhalb von Gruppen verwendet: Caret öffnende runde Klammer Error Pipe Warning schließende runde Klammer Doppelpunkt wird Zeilen finden, die mit Error Doppelpunkt oder Warning Doppelpunkt beginnen.

The group opening parenthesis Error pipe Warning closing parenthesis means match Error OR Warning. Die Gruppe öffnende runde Klammer Error Pipe Warning schließende runde Klammer bedeutet finde Error ODER Warning.

Try it on Regex one zero one. Probiere es auf Regex eins null eins aus.

Test string: I like cats. I like dogs. I like birds. Teststring: I like cats. I like dogs. I like birds.

Try cats pipe dogs. Probiere cats Pipe dogs.

Try I like opening parenthesis cats pipe birds closing parenthesis backslash dot. Probiere I like öffnende runde Klammer cats Pipe birds schließende runde Klammer Backslash Punkt.

Escaping Metacharacters. Metazeichen escapen.

What if you want to match a character that is normally a metacharacter literally, for example, you want to find an actual dot or an asterisk or a dollar sign? Was, wenn du ein Zeichen finden möchtest, das normalerweise ein Metazeichen ist, wörtlich, zum Beispiel möchtest du einen tatsächlichen Punkt oder ein Sternchen oder ein Dollarzeichen finden?

You need to escape it with a backslash. Du musst es mit einem Backslash escapen.

Backslash dot matches a literal dot character. Backslash Punkt findet ein wörtliches Punkt-Zeichen.

Backslash asterisk matches a literal asterisk character. Backslash Sternchen findet ein wörtliches Sternchen-Zeichen.

Backslash caret matches a literal caret character. Backslash Caret findet ein wörtliches Caret-Zeichen.

Backslash dollar sign matches a literal dollar sign character. Backslash Dollarzeichen findet ein wörtliches Dollarzeichen-Zeichen.

Backslash backslash matches a literal backslash character. Backslash Backslash findet ein wörtliches Backslash-Zeichen.

Backslash opening square bracket matches a literal opening square bracket, backslash opening parenthesis matches opening parenthesis, etcetera. Backslash öffnende eckige Klammer findet eine wörtliche öffnende eckige Klammer, Backslash öffnende runde Klammer findet öffnende runde Klammer, et cetera.

Try it on Regex one zero one. Probiere es auf Regex eins null eins aus.

Test string: The file is main dot py. Its size is five asterisk four KB. Teststring: The file is main Punkt py. Its size is fünf Sternchen vier KB.

How would you match main dot py literally? Try main backslash dot py. Wie würdest du main Punkt py wörtlich finden? Probiere main Backslash Punkt py.

How would you match five asterisk four? Try five backslash asterisk four. Wie würdest du fünf Sternchen vier finden? Probiere fünf Backslash Sternchen vier.

Try it yourself, Consolidated. Probiere es selbst aus, Konsolidiert.

Now, using Regex one zero one dot com, try to solve these with the string: Report generated on two zero two four dash zero three dash one five by user underscore admin. Contact: info at sign example dot com or support at sign example dot org. Issue ID: hash one two three four five. Criticality: HIGH. Jetzt, mit Regex eins null eins Punkt com, versuche diese zu lösen mit der Zeichenkette: Report generated on zwei null zwei vier Bindestrich null drei Bindestrich eins fünf by user Unterstrich admin. Contact: info at-Zeichen example Punkt com or support at-Zeichen example Punkt org. Issue ID: Raute eins zwei drei vier fünf. Criticality: HIGH.

Write a regex to match the full date, for example, two zero two four dash zero three dash one five. Schreibe einen Regex, um das vollständige Datum zu finden, zum Beispiel zwei null zwei vier Bindestrich null drei Bindestrich eins fünf.

Write a regex to match both email addresses. Schreibe einen Regex, um beide E-Mail-Adressen zu finden.

Write a regex to match the Issue ID including the hash, for example, hash one two three four five. Schreibe einen Regex, um die Issue ID einschließlich der Raute zu finden, zum Beispiel Raute eins zwei drei vier fünf.

Write a regex to match lines starting with Report. Schreibe einen Regex, um Zeilen zu finden, die mit Report beginnen.

Think about it. Denk darüber nach.

How would you match a line that is completely empty? Hint: Anchors are key. Wie würdest du eine Zeile finden, die komplett leer ist? Hinweis: Anker sind der Schlüssel.

If dot matches any character, and asterisk means zero or more, what do you think dot asterisk would match in a greedy context? Wenn Punkt jedes Zeichen findet, und Sternchen null oder mehr bedeutet, was denkst du, würde Punkt Sternchen in einem gierigen Kontext finden?

What about dot asterisk question mark in a non-greedy context? Was ist mit Punkt Sternchen Fragezeichen in einem nicht-gierigen Kontext?

What's the difference between opening square bracket a b c closing square bracket and opening parenthesis a pipe b pipe c closing parenthesis? Was ist der Unterschied zwischen öffnende eckige Klammer a b c schließende eckige Klammer und öffnende runde Klammer a Pipe b Pipe c schließende runde Klammer?

Regex in Python. Regex in Python.

You've been learning Python, and it has excellent built-in support for regular expressions through the re module. Du hast Python gelernt, und es hat ausgezeichnete eingebaute Unterstützung für reguläre Ausdrücke durch das re-Modul.

You don't need to master this for the pre-class, but it's good to know it exists. Du musst dies nicht für die Vorbereitung vor dem Unterricht beherrschen, aber es ist gut zu wissen, dass es existiert.

To use regex in Python, you would typically import re. Um Regex in Python zu verwenden, würdest du normalerweise import re verwenden.

Use functions like re dot search with pattern comma string: Scans through a string looking for the first location where the regex pattern produces a match. Verwende Funktionen wie re Punkt search mit Muster Komma Zeichenkette: Durchsucht eine Zeichenkette und sucht die erste Stelle, an der das Regex-Muster eine Übereinstimmung erzeugt.

re dot match with pattern comma string: Tries to apply the pattern at the start of the string. re Punkt match mit Muster Komma Zeichenkette: Versucht, das Muster am Anfang der Zeichenkette anzuwenden.

re dot findall with pattern comma string: Finds all non-overlapping matches of the pattern in the string and returns them as a list of strings. re Punkt findall mit Muster Komma Zeichenkette: Findet alle nicht überlappenden Treffer des Musters in der Zeichenkette und gibt sie als Liste von Zeichenketten zurück.

re dot finditer with pattern comma string: Similar to findall, but returns an iterator yielding match objects. re Punkt finditer mit Muster Komma Zeichenkette: Ähnlich wie findall, gibt aber einen Iterator zurück, der Übereinstimmungsobjekte liefert.

re dot sub with pattern comma replacement comma string: Replaces occurrences of the pattern in the string with a replacement. re Punkt sub mit Muster Komma Ersetzung Komma Zeichenkette: Ersetzt Vorkommen des Musters in der Zeichenkette durch eine Ersetzung.

Example: import re, text equals My phone number is one two three dash four five six dash seven eight nine zero, pattern equals r backslash d opening brace three closing brace dash backslash d opening brace three closing brace dash backslash d opening brace four closing brace. Beispiel: import re, text gleich My phone number is eins zwei drei Bindestrich vier fünf sechs Bindestrich sieben acht neun null, Muster gleich r Backslash d öffnende geschweifte Klammer drei schließende geschweifte Klammer Bindestrich Backslash d öffnende geschweifte Klammer drei schließende geschweifte Klammer Bindestrich Backslash d öffnende geschweifte Klammer vier schließende geschweifte Klammer.

Note: r quote quote denotes a raw string, good for regex. Hinweis: r Anführungszeichen Anführungszeichen bezeichnet eine rohe Zeichenkette, gut für Regex.

match equals re dot search with pattern comma text, if match: print with f Found phone number: opening brace match dot group with zero closing brace. Übereinstimmung gleich re Punkt search mit Muster Komma Text, if Übereinstimmung: print mit f Found phone number: öffnende geschweifte Klammer Übereinstimmung Punkt group mit null schließende geschweifte Klammer.

group with zero is the whole match. group mit null ist die gesamte Übereinstimmung.

We'll explore the re module more in practical exercises later. Wir werden das re-Modul später in praktischen Übungen weiter erforschen.

For now, focus on understanding the regex patterns themselves using tools like Regex one zero one. Konzentriere dich vorerst darauf, die Regex-Muster selbst zu verstehen, indem du Werkzeuge wie Regex eins null eins verwendest.

Regex Flavors. Regex-Varianten.

It's important to know that while the core concepts of regex are quite standard, there can be slight variations in syntax or available features between different programming languages, command-line tools, like grep, sed, or text editors. Es ist wichtig zu wissen, dass die Kernkonzepte von Regex zwar ziemlich standardisiert sind, es aber leichte Variationen in der Syntax oder verfügbaren Funktionen zwischen verschiedenen Programmiersprachen, Befehlszeilenwerkzeugen wie grep, sed, oder Texteditoren geben kann.

These variations are often referred to as regex flavors, for example, PCRE, Perl Compatible Regular Expressions, POSIX BRE, Basic Regular Expressions, POSIX ERE, Extended Regular Expressions. Diese Variationen werden oft als Regex-Varianten bezeichnet, zum Beispiel PCRE, Perl Compatible Regular Expressions, POSIX BRE, Basic Regular Expressions, POSIX ERE, Extended Regular Expressions.

Regex one zero one dot com allows you to select different flavors in its settings, usually on the left sidebar. Regex eins null eins Punkt com ermöglicht es dir, verschiedene Varianten in seinen Einstellungen auszuwählen, normalerweise in der linken Seitenleiste.

Python's re module is very similar to PCRE. Pythons re-Modul ist PCRE sehr ähnlich.

For this course, we'll focus on this widely used PCRE-like syntax. Für diesen Kurs werden wir uns auf diese weit verbreitete PCRE-ähnliche Syntax konzentrieren.

Pre-Class Exploration Task. Erkundungsaufgabe vor dem Unterricht.

Your main task before the live session is to get comfortable with the basic regex concepts by actively experimenting. Deine Hauptaufgabe vor der Live-Sitzung ist es, mit den grundlegenden Regex-Konzepten durch aktives Experimentieren vertraut zu werden.

Ensure you have Regex one zero one dot com open. Stelle sicher, dass du Regex eins null eins Punkt com geöffnet hast.

Go back through each metacharacter type explained above: Anchors, Character Classes, Quantifiers, etcetera. Gehe zurück durch jeden oben erklärten Metazeichentyp: Anker, Zeichenklassen, Quantifikatoren, et cetera.

For each concept: Read the explanation. Für jedes Konzept: Lies die Erklärung.

Look at the examples provided. Schau dir die bereitgestellten Beispiele an.

Crucially, type the example regex and test strings into Regex one zero one yourself. Entscheidend, gib die Beispiel-Regex und Teststrings selbst in Regex eins null eins ein.

Modify the examples slightly. What happens if you change a quantifier? What if you add a character to a class? Modifiziere die Beispiele leicht. Was passiert, wenn du einen Quantifikator änderst? Was, wenn du ein Zeichen zu einer Klasse hinzufügst?

Pay attention to the EXPLANATION panel in Regex one zero one to see how it interprets your pattern. Achte auf das EXPLANATION-Panel in Regex eins null eins, um zu sehen, wie es dein Muster interpretiert.

Attempt the Try it yourself, Consolidated, challenges above. Versuche die Probiere es selbst aus, Konsolidiert, Herausforderungen oben.

Don't worry if you don't get them perfect, the goal is to try and learn from the process. Mach dir keine Sorgen, wenn du sie nicht perfekt hinbekommst, das Ziel ist es, zu versuchen und aus dem Prozess zu lernen.

Reflect on the Think about it questions. Denke über die Denk darüber nach Fragen nach.

Try to formulate answers or even test your ideas on Regex one zero one. Versuche, Antworten zu formulieren oder teste sogar deine Ideen auf Regex eins null eins.

This hands-on experimentation is the best way to start building an intuition for how regular expressions work. Dieses praktische Experimentieren ist der beste Weg, um ein Gespür dafür zu entwickeln, wie reguläre Ausdrücke funktionieren.

There's no specific software to install for this pre-class beyond using your web browser. Es gibt keine spezifische Software, die für diese Vorbereitung vor dem Unterricht installiert werden muss, außer der Verwendung deines Webbrowsers.

This concludes your pre-class preparation. Dies schließt deine Vorbereitung vor dem Unterricht ab.

You should now have a foundational understanding of what regular expressions are, their basic components, and, most importantly, how to start testing and building them using an online tool. Du solltest jetzt ein grundlegendes Verständnis davon haben, was reguläre Ausdrücke sind, ihre grundlegenden Komponenten, und vor allem, wie du beginnen kannst, sie mit einem Online-Werkzeug zu testen und zu erstellen.

The slides for the live session can be viewed at a specific link. Die Folien für die Live-Sitzung können unter einem bestimmten Link angesehen werden.

Try not to peek before class, spoilers inside! Versuche nicht vor dem Unterricht zu spähen, Spoiler drinnen!