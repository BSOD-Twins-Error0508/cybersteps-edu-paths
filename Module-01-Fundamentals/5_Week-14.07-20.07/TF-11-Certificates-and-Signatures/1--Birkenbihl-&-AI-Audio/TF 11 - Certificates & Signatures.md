Welcome to the world of digital trust! In our previous discussions on encryption, we learned how to protect data from unauthorized eyes. Now, we'll explore how we can verify identities and ensure data integrity in the digital realm. This is where digital signatures and certificates come into play. They are fundamental building blocks for secure communication and transactions online, from secure web browsing (HTTPS) to verifying software downloads and securing email.

## Digital Signatures: Sealing the Digital Envelope

Imagine receiving a critical document, like a contract or an official announcement. In the physical world, a handwritten signature provides some assurance about who sent it and that it hasn't been altered. Digital signatures provide similar assurances, but with much stronger cryptographic backing.

### What is a Digital Signature?

A digital signature is a cryptographic mechanism used to verify the **authenticity**, **integrity**, and **non-repudiation** of digital data (like messages, documents, or software).

- **Authenticity**: It confirms that the sender of the message is who they claim to be.
- **Integrity**: It ensures that the message has not been altered in transit since it was signed.
- **Non-repudiation**: It provides proof that the sender actually sent the message, and they cannot later deny it.

Digital signatures rely on asymmetric cryptography. Remember, in asymmetric cryptography, we have a key pair: a private key (kept secret by the owner) and a public key (shared openly).

### How Digital Signatures Work

![image.png](attachment:ebe5fc7d-0956-408b-bc39-ec2205ad2dd1:image.png)

Creating a digital signature involves two main steps: hashing and encryption.

1. **Hashing the Data**: First, the sender takes the original data (e.g., an email message, a document) and creates a condensed version of it called a **hash** (or message digest). This is done using a cryptographic hash function (like SHA-256, which you encountered in the Encryption lesson).
    - A hash function produces a fixed-size string of characters, unique to the input data.
    - Even a tiny change in the original data will result in a completely different hash.
    - It's computationally infeasible to reverse the hash function to get the original data.
    - It's also computationally infeasible to find two different messages that produce the same hash (collision resistance).
2. **Encrypting the Hash**: Next, the sender encrypts this hash value using their **private key**. The result of this encryption is the digital signature.

This digital signature is then typically appended to the original data or sent alongside it.

### Verifying a Digital Signature

When the recipient receives the data and the digital signature, they perform the following steps to verify it:

1. **Decrypting the Signature**: The recipient uses the sender's **public key** to decrypt the digital signature. This decryption reveals the original hash value that the sender computed (let's call this Hash A).
2. **Hashing the Received Data**: The recipient takes the received data and independently computes its hash using the _same_ hash function that the sender used (let's call this Hash B).
3. **Comparing the Hashes**: The recipient compares Hash A (from decrypting the signature) with Hash B (from hashing the received data).
    - If Hash A and Hash B are identical, the signature is **valid**. This means:
        - The data came from the owner of the private key corresponding to the public key used for decryption (Authenticity).
        - The data has not been altered since it was signed (Integrity).
    - If the hashes do not match, the signature is **invalid**. This could mean the data was tampered with, or the signature was not created by the claimed sender.

### The Guarantees: Authenticity, Integrity, Non-Repudiation

- **Authenticity**: Only the holder of the private key could have encrypted the hash to create the signature that successfully decrypts with their public key.
- **Integrity**: If the data was changed even slightly after signing, the hash computed by the recipient (Hash B) would not match the hash decrypted from the signature (Hash A).
- **Non-repudiation**: Because only the sender possesses the private key, they cannot later deny having signed the message if the signature is valid.

### Think about it

Consider the concept of non-repudiation. Why is it particularly important in legal or financial transactions conducted online? Can you think of a scenario where proving the origin and integrity of a digital message is crucial?

## Digital Certificates: The Internet's ID Cards

Digital signatures are great for verifying the sender and the integrity of data. But there's a crucial question: How do you know that a specific public key truly belongs to the person or entity you think it does? If Alice wants to send a secure message to Bob, how does she get Bob's _authentic_ public key? What if an attacker, Eve, tricks Alice into using Eve's public key, pretending it's Bob's?

This is where digital certificates come in.

### The Problem: Whose Public Key is it Anyway?

Distributing public keys securely is a challenge. You could exchange them in person, but that's not scalable for the internet. You could post your public key on your website, but how does someone know the website itself hasn't been compromised?

### What is a Digital Certificate?

A **digital certificate** (often following the X.509 standard) is an electronic document that uses a digital signature to bind a public key with an identity — information such as the name of a person or an organization, their address, and so on. Think of it like a digital passport or driver's license. It provides assurance that a particular public key belongs to a specific entity.

### Key Information in a Certificate

![image.png](attachment:98e7fdea-7583-403d-9380-5df890040a9e:image.png)

A digital certificate typically contains:

- **Subject's Identifying Information**: Details about the entity the certificate is issued to (e.g., a person's name, a company's name, a website's domain name like `www.google.com`).
- **Subject's Public Key**: The public key that is being certified.
- **Issuer's (Certificate Authority) Identifying Information**: Name of the entity that issued the certificate.
- **Issuer's Digital Signature**: The CA signs the certificate with its own private key to vouch for its authenticity. This is the crucial part – it's a trusted third party saying, "Yes, we've verified this public key belongs to this subject."
- **Validity Period**: The dates for which the certificate is valid (a "valid from" and "valid to" date). Certificates don't last forever.
- **Serial Number**: A unique identifier for the certificate.
- **Key Usage**: Specifies the approved uses of the public key (e.g., for encrypting data, verifying signatures, server authentication).

### Try it yourself

Next time you visit a secure website (one starting with `https://`), look for a padlock icon in your browser's address bar. Clicking on it usually allows you to view the website's digital certificate. You don't need to understand all the details yet, but just notice that it's there, providing a layer of trust. We'll explore this more in class.

## Certificate Authorities (CAs): The Guardians of Trust

So, who issues these digital ID cards? Trusted third-party organizations called **Certificate Authorities (CAs)**.

### Who Issues Certificates?

CAs are responsible for:

1. **Verifying the identity** of individuals or organizations applying for a certificate. The rigor of this verification can vary depending on the type of certificate.
2. **Issuing digital certificates** that bind the verified identity to a public key.
3. **Signing these certificates** with their own private key. This signature is what makes the certificate trustworthy.
4. **Managing certificates**, which includes revoking them if they are compromised or no longer valid (e.g., if a private key is stolen or a company goes out of business). Information about revoked certificates is made available through Certificate Revocation Lists (CRLs) or the Online Certificate Status Protocol (OCSP).

Examples of well-known CAs include Let's Encrypt, DigiCert, GlobalSign, and Comodo (now Sectigo).

### The Chain of Trust

![image.png](attachment:c78bb33a-218b-43d7-8186-6cd9a7bee696:image.png)

Your computer, operating system, and web browser come pre-loaded with a list of **Root CA certificates**. These are CAs that are considered inherently trustworthy.

When a CA issues a certificate, it signs it with its private key. Your browser can verify this signature using the CA's public key (which it might already have if it's a Root CA, or it can trace it back).

Sometimes, CAs delegate issuing authority to **Intermediate CAs**. So, a Root CA might issue a certificate for an Intermediate CA, and that Intermediate CA then issues a certificate for a website. This creates a "chain of trust":

- The website's certificate is signed by Intermediate CA X.
- Intermediate CA X's certificate is signed by Root CA Y.
- Root CA Y's certificate is self-signed and is already in your browser's trust store.

If your browser can trace this chain back to a trusted Root CA in its store, it will trust the website's certificate. If it can't, or if any certificate in the chain is invalid (e.g., expired, revoked, or the signature doesn't match), it will typically warn you that the connection might not be secure.

### Think about it

What are the potential consequences if a Certificate Authority's private key is compromised? Why is the security of Root CAs so critical for the entire system of trust on the internet?

## Public Key Infrastructure (PKI): The Big Picture

Digital signatures, digital certificates, and Certificate Authorities are all components of a larger system called a **Public Key Infrastructure (PKI)**.

A PKI is essentially the overall system—comprising technology, policies, and procedures—that allows us to create, manage, distribute, use, store, and revoke digital certificates. It's the framework that makes widespread use of digital signatures and certificates possible and reliable. Think of it as the entire ecosystem that supports the "digital ID card" system (certificates) and the "digital notary service" (signatures).

Key functions enabled by a PKI include:

- Issuing and validating digital certificates.
- Managing the lifecycle of certificates (including revocation).
- Distributing public keys in a trustworthy manner.

Understanding that PKI is this overarching framework helps you see how all the individual pieces (signatures, certificates, CAs) fit together to enable digital trust.

## Setup

For this pre-class preparation, no special software installation is required beyond a standard web browser, which you already use. We will explore practical examples and tools during our live session.

This pre-class material should give you a solid understanding of what digital signatures and certificates are, why they are needed, and how they work. In our upcoming lesson, we will delve deeper into these concepts, look at real-world examples, and discuss their importance in various cybersecurity contexts.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Technical-Foundations-11-Certificates-Signatures-ye49cu1spouw6pb?mode=doc](https://gamma.app/docs/Technical-Foundations-11-Certificates-Signatures-ye49cu1spouw6pb?mode=doc)

Try not to peek before class - spoilers inside!

</aside>