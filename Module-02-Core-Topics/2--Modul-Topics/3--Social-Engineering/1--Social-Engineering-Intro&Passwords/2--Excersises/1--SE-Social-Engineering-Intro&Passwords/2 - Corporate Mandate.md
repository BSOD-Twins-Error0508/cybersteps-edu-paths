_Ihre Passwortpolitik ist... interessant_.

**Ziel**

Verwenden Sie regelbasierte und maskenbasierte Angriffe sowohl mit John the Ripper als auch mit Hashcat, um Passwörter zu knacken, die einem vorhersehbaren Unternehmensmuster folgen.

**Anleitung**

Das Unternehmen Innovate Technologies hat eine Passwortrichtlinie, nach der Benutzer ein gängiges englisches Wort wählen, den ersten Buchstaben groß schreiben und `@Innovate` anhängen müssen. Beispiel: `Passwort@Innovate`. Sie haben zwei Hashes für Benutzer abgefangen, die diese Richtlinie befolgt haben.

- **MD5 Hash:** `d1ab8225fa1d6970be6a0647ef57f4d2`
- **NTLM Hash:** `9ef754967589121ab9ba99eba0f785d5`

Ihre Aufgabe ist es, beide Hashes mit zwei verschiedenen Methoden zu knacken:

1. **John the Ripper:** Finde eine allgemeine englische Wortliste online. Erstellen Sie eine benutzerdefinierte Regel in Ihrer `john.conf` (oder benutzen Sie die Kommandozeile), die den ersten Buchstaben eines Wortes groß schreibt und `@Innovate` anhängt. Verwenden Sie diese Regel, um den MD5-Hash zu knacken.
2. **Hashcat:** Verwenden Sie die Maskenangriffsfunktion von Hashcat, um den NTLM-Hash zu knacken. Sie müssen den richtigen Hash-Modus für NTLM finden und eine Maske konstruieren, die das Passwortmuster darstellt (z. B. `?u?l?l...?l@Innovate`).

**Einreichung**

Reichen Sie zwei Bildschirmfotos ein:

1. Der Befehl "john", Ihre benutzerdefinierte Regel und das geknackte MD5-Passwort.
2. Der Befehl "hashcat" und das geknackte NTLM-Passwort.