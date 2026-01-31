Welcome to the world of digital trust! Willkommen in der Welt des digitalen Vertrauens!

In our previous discussions on encryption, we learned how to protect data from unauthorized eyes. In unseren vorherigen Diskussionen über Verschlüsselung haben wir gelernt, wie man Daten vor unbefugten Blicken schützt.

Now, we'll explore how we can verify identities and ensure data integrity in the digital realm. Jetzt werden wir erforschen, wie wir Identitäten überprüfen und Datenintegrität im digitalen Bereich sicherstellen können.

This is where digital signatures and certificates come into play. Hier kommen digitale Signaturen und Zertifikate ins Spiel.

They are fundamental building blocks for secure communication and transactions online, from secure web browsing to verifying software downloads and securing email. Sie sind grundlegende Bausteine für sichere Kommunikation und Transaktionen online, von sicherem Surfen im Internet bis zur Überprüfung von Software-Downloads und der Sicherung von E-Mails.

Digital Signatures: Sealing the Digital Envelope. Digitale Signaturen: Das Versiegeln des digitalen Umschlags.

Imagine receiving a critical document, like a contract or an official announcement. Stellen Sie sich vor, Sie erhalten ein wichtiges Dokument, wie einen Vertrag oder eine offizielle Ankündigung.

In the physical world, a handwritten signature provides some assurance about who sent it and that it hasn't been altered. In der physischen Welt bietet eine handschriftliche Unterschrift eine gewisse Sicherheit darüber, wer es gesendet hat und dass es nicht verändert wurde.

Digital signatures provide similar assurances, but with much stronger cryptographic backing. Digitale Signaturen bieten ähnliche Sicherheiten, aber mit einer viel stärkeren kryptographischen Grundlage.

What is a Digital Signature? Was ist eine digitale Signatur?

A digital signature is a cryptographic mechanism used to verify the authenticity, integrity, and non-repudiation of digital data, like messages, documents, or software. Eine digitale Signatur ist ein kryptographischer Mechanismus, der verwendet wird, um die Authentizität, Integrität und Nichtabstreitbarkeit digitaler Daten zu überprüfen, wie Nachrichten, Dokumente oder Software.

Authenticity: It confirms that the sender of the message is who they claim to be. Authentizität: Sie bestätigt, dass der Absender der Nachricht derjenige ist, der er vorgibt zu sein.

Integrity: It ensures that the message has not been altered in transit since it was signed. Integrität: Sie stellt sicher, dass die Nachricht seit ihrer Signierung während der Übertragung nicht verändert wurde.

Non-repudiation: It provides proof that the sender actually sent the message, and they cannot later deny it. Nichtabstreitbarkeit: Sie liefert den Beweis, dass der Absender die Nachricht tatsächlich gesendet hat, und er kann dies später nicht abstreiten.

Digital signatures rely on asymmetric cryptography. Digitale Signaturen beruhen auf asymmetrischer Kryptographie.

Remember, in asymmetric cryptography, we have a key pair: a private key, kept secret by the owner, and a public key, shared openly. Denken Sie daran, in asymmetrischer Kryptographie haben wir ein Schlüsselpaar: einen privaten Schlüssel, der vom Besitzer geheim gehalten wird, und einen öffentlichen Schlüssel, der offen geteilt wird.

How Digital Signatures Work. Wie digitale Signaturen funktionieren.

Creating a digital signature involves two main steps: hashing and encryption. Das Erstellen einer digitalen Signatur umfasst zwei Hauptschritte: Hashing und Verschlüsselung.

Hashing the Data: First, the sender takes the original data, for example, an email message or a document, and creates a condensed version of it called a hash or message digest. Hashing der Daten: Zuerst nimmt der Absender die ursprünglichen Daten, zum Beispiel eine E-Mail-Nachricht oder ein Dokument, und erstellt eine komprimierte Version davon, die als Hash oder Nachrichtendigest bezeichnet wird.

This is done using a cryptographic hash function, like SHA-256, which you encountered in the Encryption lesson. Dies wird mithilfe einer kryptographischen Hash-Funktion durchgeführt, wie SHA-256, die Sie in der Verschlüsselungslektion kennengelernt haben.

A hash function produces a fixed-size string of characters, unique to the input data. Eine Hash-Funktion erzeugt eine Zeichenkette fester Größe, die einzigartig für die Eingabedaten ist.

Even a tiny change in the original data will result in a completely different hash. Selbst eine winzige Änderung in den ursprünglichen Daten führt zu einem völlig anderen Hash.

It's computationally infeasible to reverse the hash function to get the original data. Es ist rechnerisch nicht möglich, die Hash-Funktion umzukehren, um die ursprünglichen Daten zu erhalten.

It's also computationally infeasible to find two different messages that produce the same hash, collision resistance. Es ist auch rechnerisch nicht möglich, zwei verschiedene Nachrichten zu finden, die denselben Hash erzeugen, das nennt man Kollisionsresistenz.

Encrypting the Hash: Next, the sender encrypts this hash value using their private key. Verschlüsseln des Hashs: Als nächstes verschlüsselt der Absender diesen Hash-Wert mit seinem privaten Schlüssel.

The result of this encryption is the digital signature. Das Ergebnis dieser Verschlüsselung ist die digitale Signatur.

This digital signature is then typically appended to the original data or sent alongside it. Diese digitale Signatur wird dann typischerweise an die ursprünglichen Daten angehängt oder zusammen mit ihnen gesendet.

Verifying a Digital Signature. Überprüfen einer digitalen Signatur.

When the recipient receives the data and the digital signature, they perform the following steps to verify it. Wenn der Empfänger die Daten und die digitale Signatur erhält, führt er die folgenden Schritte durch, um sie zu überprüfen.

Decrypting the Signature: The recipient uses the sender's public key to decrypt the digital signature. Entschlüsseln der Signatur: Der Empfänger verwendet den öffentlichen Schlüssel des Absenders, um die digitale Signatur zu entschlüsseln.

This decryption reveals the original hash value that the sender computed, let's call this Hash A. Diese Entschlüsselung offenbart den ursprünglichen Hash-Wert, den der Absender berechnet hat, nennen wir ihn Hash A.

Hashing the Received Data: The recipient takes the received data and independently computes its hash using the same hash function that the sender used, let's call this Hash B. Hashing der empfangenen Daten: Der Empfänger nimmt die empfangenen Daten und berechnet unabhängig deren Hash mit derselben Hash-Funktion, die der Absender verwendet hat, nennen wir ihn Hash B.

Comparing the Hashes: The recipient compares Hash A, from decrypting the signature, with Hash B, from hashing the received data. Vergleichen der Hashes: Der Empfänger vergleicht Hash A, aus der Entschlüsselung der Signatur, mit Hash B, aus dem Hashing der empfangenen Daten.

If Hash A and Hash B are identical, the signature is valid. Wenn Hash A und Hash B identisch sind, ist die Signatur gültig.

This means: The data came from the owner of the private key corresponding to the public key used for decryption, Authenticity. Dies bedeutet: Die Daten stammen vom Besitzer des privaten Schlüssels, der dem für die Entschlüsselung verwendeten öffentlichen Schlüssel entspricht, Authentizität.

The data has not been altered since it was signed, Integrity. Die Daten wurden seit ihrer Signierung nicht verändert, Integrität.

If the hashes do not match, the signature is invalid. Wenn die Hashes nicht übereinstimmen, ist die Signatur ungültig.

This could mean the data was tampered with, or the signature was not created by the claimed sender. Dies könnte bedeuten, dass die Daten manipuliert wurden oder die Signatur nicht vom angegebenen Absender erstellt wurde.

The Guarantees: Authenticity, Integrity, Non-Repudiation. Die Garantien: Authentizität, Integrität, Nichtabstreitbarkeit.

Authenticity: Only the holder of the private key could have encrypted the hash to create the signature that successfully decrypts with their public key. Authentizität: Nur der Besitzer des privaten Schlüssels hätte den Hash verschlüsseln können, um die Signatur zu erstellen, die erfolgreich mit seinem öffentlichen Schlüssel entschlüsselt werden kann.

Integrity: If the data was changed even slightly after signing, the hash computed by the recipient, Hash B, would not match the hash decrypted from the signature, Hash A. Integrität: Wenn die Daten nach der Signierung auch nur geringfügig geändert wurden, würde der vom Empfänger berechnete Hash, Hash B, nicht mit dem aus der Signatur entschlüsselten Hash, Hash A, übereinstimmen.

Non-repudiation: Because only the sender possesses the private key, they cannot later deny having signed the message if the signature is valid. Nichtabstreitbarkeit: Da nur der Absender den privaten Schlüssel besitzt, kann er nicht später leugnen, die Nachricht signiert zu haben, wenn die Signatur gültig ist.

Think about it. Denken Sie darüber nach.

Consider the concept of non-repudiation. Betrachten Sie das Konzept der Nichtabstreitbarkeit.

Why is it particularly important in legal or financial transactions conducted online? Warum ist es besonders wichtig bei rechtlichen oder finanziellen Transaktionen, die online durchgeführt werden?

Can you think of a scenario where proving the origin and integrity of a digital message is crucial? Können Sie sich ein Szenario vorstellen, in dem der Nachweis der Herkunft und Integrität einer digitalen Nachricht entscheidend ist?

Digital Certificates: The Internet's ID Cards. Digitale Zertifikate: Die Ausweise des Internets.

Digital signatures are great for verifying the sender and the integrity of data. Digitale Signaturen sind großartig, um den Absender und die Integrität von Daten zu überprüfen.

But there's a crucial question: How do you know that a specific public key truly belongs to the person or entity you think it does? Aber es gibt eine entscheidende Frage: Woher wissen Sie, dass ein bestimmter öffentlicher Schlüssel wirklich zu der Person oder Organisation gehört, von der Sie denken, dass er ihr gehört?

If Alice wants to send a secure message to Bob, how does she get Bob's authentic public key? Wenn Alice eine sichere Nachricht an Bob senden möchte, wie erhält sie Bobs authentischen öffentlichen Schlüssel?

What if an attacker, Eve, tricks Alice into using Eve's public key, pretending it's Bob's? Was ist, wenn eine Angreiferin, Eve, Alice dazu bringt, Eves öffentlichen Schlüssel zu verwenden, indem sie vorgibt, es sei Bobs?

This is where digital certificates come in. Hier kommen digitale Zertifikate ins Spiel.

The Problem: Whose Public Key is it Anyway? Das Problem: Wessen öffentlicher Schlüssel ist es überhaupt?

Distributing public keys securely is a challenge. Die sichere Verteilung öffentlicher Schlüssel ist eine Herausforderung.

You could exchange them in person, but that's not scalable for the internet. Sie könnten sie persönlich austauschen, aber das ist für das Internet nicht skalierbar.

You could post your public key on your website, but how does someone know the website itself hasn't been compromised? Sie könnten Ihren öffentlichen Schlüssel auf Ihrer Website veröffentlichen, aber woher weiß jemand, dass die Website selbst nicht kompromittiert wurde?

What is a Digital Certificate? Was ist ein digitales Zertifikat?

A digital certificate, often following the X.509 standard, is an electronic document that uses a digital signature to bind a public key with an identity, information such as the name of a person or an organization, their address, and so on. Ein digitales Zertifikat, das oft dem X.509-Standard folgt, ist ein elektronisches Dokument, das eine digitale Signatur verwendet, um einen öffentlichen Schlüssel mit einer Identität zu verknüpfen, Informationen wie den Namen einer Person oder einer Organisation, ihre Adresse und so weiter.

Think of it like a digital passport or driver's license. Denken Sie daran wie an einen digitalen Reisepass oder Führerschein.

It provides assurance that a particular public key belongs to a specific entity. Es bietet die Gewissheit, dass ein bestimmter öffentlicher Schlüssel zu einer bestimmten Entität gehört.

Key Information in a Certificate. Wichtige Informationen in einem Zertifikat.

A digital certificate typically contains: Ein digitales Zertifikat enthält typischerweise:

Subject's Identifying Information: Details about the entity the certificate is issued to, for example, a person's name, a company's name, a website's domain name like www.google.com. Identifizierende Informationen des Inhabers: Details über die Entität, für die das Zertifikat ausgestellt wurde, zum Beispiel der Name einer Person, der Name eines Unternehmens, ein Website-Domainname wie www.google.com.

Subject's Public Key: The public key that is being certified. Öffentlicher Schlüssel des Inhabers: Der öffentliche Schlüssel, der zertifiziert wird.

Issuer's, Certificate Authority, Identifying Information: Name of the entity that issued the certificate. Identifizierende Informationen des Ausstellers, der Zertifizierungsstelle: Name der Entität, die das Zertifikat ausgestellt hat.

Issuer's Digital Signature: The CA signs the certificate with its own private key to vouch for its authenticity. Digitale Signatur des Ausstellers: Die Zertifizierungsstelle signiert das Zertifikat mit ihrem eigenen privaten Schlüssel, um für dessen Authentizität zu bürgen.

This is the crucial part, it's a trusted third party saying, "Yes, we've verified this public key belongs to this subject." Dies ist der entscheidende Teil, es ist eine vertrauenswürdige dritte Partei, die sagt: "Ja, wir haben überprüft, dass dieser öffentliche Schlüssel zu diesem Inhaber gehört."

Validity Period: The dates for which the certificate is valid, a "valid from" and "valid to" date. Gültigkeitszeitraum: Die Daten, für die das Zertifikat gültig ist, ein "Gültig ab" und "Gültig bis" Datum.

Certificates don't last forever. Zertifikate halten nicht ewig.

Serial Number: A unique identifier for the certificate. Seriennummer: Eine eindeutige Kennung für das Zertifikat.

Key Usage: Specifies the approved uses of the public key, for example, for encrypting data, verifying signatures, server authentication. Schlüsselverwendung: Gibt die genehmigten Verwendungszwecke des öffentlichen Schlüssels an, zum Beispiel für die Verschlüsselung von Daten, die Überprüfung von Signaturen, die Server-Authentifizierung.

Try it yourself. Probieren Sie es selbst aus.

Next time you visit a secure website, one starting with https, look for a padlock icon in your browser's address bar. Wenn Sie das nächste Mal eine sichere Website besuchen, eine, die mit https beginnt, suchen Sie nach einem Vorhängeschloss-Symbol in der Adressleiste Ihres Browsers.

Clicking on it usually allows you to view the website's digital certificate. Wenn Sie darauf klicken, können Sie normalerweise das digitale Zertifikat der Website anzeigen.

You don't need to understand all the details yet, but just notice that it's there, providing a layer of trust. Sie müssen noch nicht alle Details verstehen, aber bemerken Sie einfach, dass es da ist und eine Vertrauensebene bietet.

We'll explore this more in class. Wir werden dies im Unterricht genauer untersuchen.

Certificate Authorities: The Guardians of Trust. Zertifizierungsstellen: Die Wächter des Vertrauens.

So, who issues these digital ID cards? Also, wer stellt diese digitalen Ausweise aus?

Trusted third-party organizations called Certificate Authorities. Vertrauenswürdige Drittorganisationen, die Zertifizierungsstellen genannt werden.

Who Issues Certificates? Wer stellt Zertifikate aus?

CAs are responsible for: Zertifizierungsstellen sind verantwortlich für:

Verifying the identity of individuals or organizations applying for a certificate. Die Überprüfung der Identität von Personen oder Organisationen, die ein Zertifikat beantragen.

The rigor of this verification can vary depending on the type of certificate. Die Strenge dieser Überprüfung kann je nach Art des Zertifikats variieren.

Issuing digital certificates that bind the verified identity to a public key. Die Ausstellung digitaler Zertifikate, die die überprüfte Identität an einen öffentlichen Schlüssel binden.

Signing these certificates with their own private key. Die Signierung dieser Zertifikate mit ihrem eigenen privaten Schlüssel.

This signature is what makes the certificate trustworthy. Diese Signatur macht das Zertifikat vertrauenswürdig.

Managing certificates, which includes revoking them if they are compromised or no longer valid, for example, if a private key is stolen or a company goes out of business. Die Verwaltung von Zertifikaten, was auch das Widerrufen einschließt, wenn sie kompromittiert oder nicht mehr gültig sind, zum Beispiel, wenn ein privater Schlüssel gestohlen wird oder ein Unternehmen den Betrieb einstellt.

Information about revoked certificates is made available through Certificate Revocation Lists or the Online Certificate Status Protocol. Informationen über widerrufene Zertifikate werden über Zertifikatswiderrufslisten oder das Online-Zertifikatsstatus-Protokoll verfügbar gemacht.

Examples of well-known CAs include Let's Encrypt, DigiCert, GlobalSign, and Comodo, now Sectigo. Beispiele für bekannte Zertifizierungsstellen sind Let's Encrypt, DigiCert, GlobalSign und Comodo, jetzt Sectigo.

The Chain of Trust. Die Vertrauenskette.

Your computer, operating system, and web browser come pre-loaded with a list of Root CA certificates. Ihr Computer, Betriebssystem und Webbrowser kommen mit einer Liste von Root-CA-Zertifikaten vorinstalliert.

These are CAs that are considered inherently trustworthy. Dies sind Zertifizierungsstellen, die als von Natur aus vertrauenswürdig angesehen werden.

When a CA issues a certificate, it signs it with its private key. Wenn eine Zertifizierungsstelle ein Zertifikat ausstellt, signiert sie es mit ihrem privaten Schlüssel.

Your browser can verify this signature using the CA's public key, which it might already have if it's a Root CA, or it can trace it back. Ihr Browser kann diese Signatur mit dem öffentlichen Schlüssel der Zertifizierungsstelle überprüfen, den er möglicherweise bereits hat, wenn es sich um eine Root-CA handelt, oder er kann ihn zurückverfolgen.

Sometimes, CAs delegate issuing authority to Intermediate CAs. Manchmal delegieren Zertifizierungsstellen die Ausstellungsbefugnis an Zwischen-CAs.

So, a Root CA might issue a certificate for an Intermediate CA, and that Intermediate CA then issues a certificate for a website. Also könnte eine Root-CA ein Zertifikat für eine Zwischen-CA ausstellen, und diese Zwischen-CA stellt dann ein Zertifikat für eine Website aus.

This creates a "chain of trust." Dies erzeugt eine "Vertrauenskette."

The website's certificate is signed by Intermediate CA X. Das Zertifikat der Website ist von der Zwischen-CA X signiert.

Intermediate CA X's certificate is signed by Root CA Y. Das Zertifikat der Zwischen-CA X ist von der Root-CA Y signiert.

Root CA Y's certificate is self-signed and is already in your browser's trust store. Das Zertifikat der Root-CA Y ist selbst signiert und befindet sich bereits im Vertrauensspeicher Ihres Browsers.

If your browser can trace this chain back to a trusted Root CA in its store, it will trust the website's certificate. Wenn Ihr Browser diese Kette zu einer vertrauenswürdigen Root-CA in seinem Speicher zurückverfolgen kann, wird er dem Zertifikat der Website vertrauen.

If it can't, or if any certificate in the chain is invalid, for example, expired, revoked, or the signature doesn't match, it will typically warn you that the connection might not be secure. Wenn er es nicht kann, oder wenn ein Zertifikat in der Kette ungültig ist, zum Beispiel abgelaufen, widerrufen oder die Signatur nicht übereinstimmt, wird er Sie normalerweise warnen, dass die Verbindung möglicherweise nicht sicher ist.

Think about it. Denken Sie darüber nach.

What are the potential consequences if a Certificate Authority's private key is compromised? Was sind die möglichen Folgen, wenn der private Schlüssel einer Zertifizierungsstelle kompromittiert wird?

Why is the security of Root CAs so critical for the entire system of trust on the internet? Warum ist die Sicherheit von Root-CAs so entscheidend für das gesamte Vertrauenssystem im Internet?

Public Key Infrastructure: The Big Picture. Public-Key-Infrastruktur: Das große Ganze.

Digital signatures, digital certificates, and Certificate Authorities are all components of a larger system called a Public Key Infrastructure. Digitale Signaturen, digitale Zertifikate und Zertifizierungsstellen sind alles Komponenten eines größeren Systems, das Public-Key-Infrastruktur genannt wird.

A PKI is essentially the overall system, comprising technology, policies, and procedures, that allows us to create, manage, distribute, use, store, and revoke digital certificates. Eine PKI ist im Wesentlichen das Gesamtsystem, das Technologie, Richtlinien und Verfahren umfasst, das es uns ermöglicht, digitale Zertifikate zu erstellen, zu verwalten, zu verteilen, zu verwenden, zu speichern und zu widerrufen.

It's the framework that makes widespread use of digital signatures and certificates possible and reliable. Es ist das Rahmenwerk, das die weit verbreitete Nutzung digitaler Signaturen und Zertifikate möglich und zuverlässig macht.

Think of it as the entire ecosystem that supports the "digital ID card" system, certificates, and the "digital notary service", signatures. Denken Sie daran als das gesamte Ökosystem, das das "digitale Ausweissystem", die Zertifikate, und den "digitalen Notardienst", die Signaturen, unterstützt.

Key functions enabled by a PKI include: Wichtige Funktionen, die durch eine PKI ermöglicht werden, umfassen:

Issuing and validating digital certificates. Das Ausstellen und Validieren digitaler Zertifikate.

Managing the lifecycle of certificates, including revocation. Die Verwaltung des Lebenszyklus von Zertifikaten, einschließlich des Widerrufs.

Distributing public keys in a trustworthy manner. Die Verteilung öffentlicher Schlüssel auf vertrauenswürdige Weise.

Understanding that PKI is this overarching framework helps you see how all the individual pieces, signatures, certificates, CAs, fit together to enable digital trust. Das Verständnis, dass PKI dieses übergreifende Rahmenwerk ist, hilft Ihnen zu sehen, wie alle einzelnen Teile, Signaturen, Zertifikate, Zertifizierungsstellen, zusammenpassen, um digitales Vertrauen zu ermöglichen.

Setup. Einrichtung.

For this pre-class preparation, no special software installation is required beyond a standard web browser, which you already use. Für diese Vorbereitung vor dem Unterricht ist keine spezielle Softwareinstallation erforderlich, außer einem Standard-Webbrowser, den Sie bereits verwenden.

We will explore practical examples and tools during our live session. Wir werden praktische Beispiele und Tools während unserer Live-Sitzung erkunden.

This pre-class material should give you a solid understanding of what digital signatures and certificates are, why they are needed, and how they work. Dieses Vorbereitungsmaterial sollte Ihnen ein solides Verständnis davon geben, was digitale Signaturen und Zertifikate sind, warum sie benötigt werden und wie sie funktionieren.

In our upcoming lesson, we will delve deeper into these concepts, look at real-world examples, and discuss their importance in various cybersecurity contexts. In unserer kommenden Lektion werden wir tiefer in diese Konzepte eintauchen, uns reale Beispiele ansehen und ihre Bedeutung in verschiedenen Cybersicherheitskontexten diskutieren.