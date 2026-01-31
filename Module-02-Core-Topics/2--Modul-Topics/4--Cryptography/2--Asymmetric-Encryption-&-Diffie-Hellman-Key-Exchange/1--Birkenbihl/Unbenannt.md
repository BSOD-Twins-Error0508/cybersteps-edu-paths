In our last session, we explored symmetric encryption, where a single shared key is used to both encrypt and decrypt information. This is fast and efficient, but it introduces a significant challenge: How do you securely share the secret key with the other party in the first place? If an attacker intercepts the key as you send it, your entire secure channel is compromised. This is known as the **key distribution problem**.

Asymmetric encryption, also called public-key cryptography, provides a brilliant solution to this problem.

## What is Asymmetric Encryption?

Asymmetric encryption uses a pair of mathematically related keys to encrypt and decrypt data: a **public key** and a **private key**.

- **Public Key:** This key is made available to everyone. You can share it freely through email, on your website, or in public key directories. Its purpose is to encrypt data.
- **Private Key:** This key is kept secret and must never be shared. Only the owner of the key pair has access to it. Its purpose is to decrypt data that has been encrypted with the corresponding public key.

The core principle is that a message encrypted with a public key can _only_ be decrypted by its corresponding private key. This one-way relationship is the foundation of modern secure communication.

![image.png](attachment:f165e920-d33b-4cd8-8230-5d054ad62953:image.png)

### The Mailbox Analogy

Think of the process like a personal mailbox with a special lock.

1. You buy a unique padlock (your **public key**) and distribute copies of this open padlock to anyone who wants to send you a letter.
2. Anyone can place a letter in your mailbox and snap your padlock shut. Once locked, the message is secure.
3. You are the only person who possesses the unique key (your **private key**) that can open the padlock and read the letters.

Even if someone steals one of the open padlocks (the public key), they can't use it to open your mailbox. They can only use it to lock messages that only you can open.

### How it's Used for Confidentiality

Let's say Alice wants to send a confidential message to Bob.

1. **Key Generation:** Bob generates his own public/private key pair.
2. **Key Sharing:** Bob sends his **public key** to Alice. He can send this over an insecure channel; it doesn't matter if an attacker, Eve, intercepts it.
3. **Encryption:** Alice uses Bob's public key to encrypt her message to him.
4. **Transmission:** Alice sends the encrypted message (ciphertext) to Bob.
5. **Decryption:** Bob uses his **private key** to decrypt the message and read its contents.

If Eve intercepts the encrypted message, she cannot read it because she does not have Bob's private key.

### Think about it

What happens if Bob loses his private key? Can he still read messages encrypted with his public key? What are the implications for all the data that was previously encrypted for him?

_One of the most famous asymmetric encryption algorithms is RSA, you can read more about how it works [here](https://www.cryptool.org/en/cto/rsa-step-by-step/)_

## Digital Signatures: Proving Authenticity and Integrity

The key pair's magic works in reverse, too. While encrypting with a public key provides confidentiality, encrypting with a private key provides **authenticity**, **integrity**, and **non-repudiation**. This reverse process is the basis of a **digital signature**.

Here’s how it works:

![image.png](attachment:4cd350ae-f399-4cd3-b110-c455d13ad0e8:image.png)

1. **Hashing:** Alice writes a message and creates a hash of it (a unique, fixed-size fingerprint of the data).
2. **Signing (Encrypting the Hash):** Alice uses her **private key** to encrypt the hash. This encrypted hash is her digital signature.
3. **Transmission:** She sends the original message (in plaintext) along with the digital signature to Bob.
4. **Verification (Decrypting the Hash):** Bob receives the message and the signature. He uses Alice's **public key** to decrypt the signature, which reveals the original hash (Hash A).
5. **Comparison:** Bob then calculates his own hash of the message he received (Hash B).
6. **Validation:** If Hash A matches Hash B, Bob has successfully verified the signature.

This process proves three things:

- **Authenticity:** Only the holder of Alice's private key could have created the signature. Therefore, the message must have come from Alice.
- **Integrity:** The matching hashes prove that the message was not altered in transit. If even one character had been changed, the hashes would not match.
- **Non-repudiation:** Alice cannot later deny sending the message, because only she could have created the signature.

## The Diffie-Hellman Key Exchange: Agreeing on a Secret

Asymmetric encryption is powerful, but it's also computationally intensive—it's much slower than symmetric encryption. For sending large amounts of data, it would be too inefficient.

So, in practice, we get the best of both worlds: we use **asymmetric** encryption to securely establish a temporary, shared key, and then use that key for fast **symmetric** encryption for the rest of the conversation.

The Diffie-Hellman key exchange is a famous method that allows two parties, who have no prior knowledge of each other, to jointly establish a shared secret key over an insecure channel.

### The Paint Mixing Analogy

![1-_aF4uglKXQ1DY-5a8lw37A.png](attachment:d32b1837-90c6-40c4-a269-4abd4e740a15:1-_aF4uglKXQ1DY-5a8lw37A.png)

This is the most famous analogy for explaining Diffie-Hellman:

1. **Common Paint:** Alice and Bob publicly agree on a common starting color of paint (e.g., yellow). This is public knowledge; any eavesdropper can see it.
2. **Secret Colors:** Alice secretly chooses her own color (e.g., red). Bob secretly chooses his own color (e.g., blue). They do not share these secret colors.
3. **First Mix:**
    - Alice mixes the common yellow paint with her secret red paint, creating a new orange mixture.
    - Bob mixes the common yellow paint with his secret blue paint, creating a new light blue mixture.
4. **Public Exchange:** Alice sends her orange mixture to Bob, and Bob sends his light blue mixture to Alice. They send these new mixtures over the public, insecure channel. An eavesdropper can intercept both of these mixtures.
5. **Final Shared Secret:**
    - Alice takes Bob's light blue mixture and adds her own secret red paint.
    - Bob takes Alice's orange mixture and adds his own secret blue paint.

Both Alice and Bob now have the exact same final color—a brownish-purple mixture.

An eavesdropper, who only saw the common yellow paint and the two intermediate mixtures (orange and light blue), cannot easily determine the final shared secret color. To do so, they would need to "un-mix" the paint, which is a computationally difficult problem, just as the underlying math of Diffie-Hellman is difficult to reverse. This final color becomes the shared secret key for their symmetric encryption session.

### The Math Behind Diffie-Hellman

The "magic" of the paint analogy is made possible by a mathematical principle involving modular arithmetic. It's often called "clock arithmetic" because it deals with remainders after division. For example, on a 12-hour clock, 4 hours after 9 o'clock is 1 o'clock, not 13. This is because `13 mod 12 = 1`. This "wrapping around" property is a key part of what makes the process secure.

![1200px-Clock_group.svg.png](attachment:647d5034-7123-4832-9bcf-facdba10b925:1200px-Clock_group.svg.png)

The core idea is that it's easy to perform an exponentiation operation but incredibly difficult to reverse it (this is known as the **discrete logarithm problem**).

Here's how the math maps to the analogy:

![image.png](attachment:f77ab7cc-1572-4617-baff-ac25cc413fa2:image.png)

1. **Common Numbers (Common Paint):** Alice and Bob publicly agree on two numbers: a large prime number, `p`, and a generator, `g`. These are not secret.
2. **Secret Numbers (Secret Colors):**
    - Alice chooses a secret integer `a`.
    - Bob chooses a secret integer `b`.
3. **First Calculation (First Mix):**
    - Alice calculates `A = g^a mod p`.
    - Bob calculates `B = g^b mod p`. (The `mod p` operation means taking the remainder after dividing by `p`. This keeps the numbers within a manageable range).
4. **Public Exchange:** Alice sends her result `A` to Bob, and Bob sends his result `B` to Alice. An eavesdropper can see `p`, `g`, `A`, and `B`.
5. **Final Shared Secret Calculation:**
    - Alice takes Bob's number `B` and calculates the secret key `s = B^a mod p`.
    - Bob takes Alice's number `A` and calculates the secret key `s = A^b mod p`.

Both of them arrive at the exact same secret key, `s`.

**Why does this work?**

- Alice's calculation is `s = (g^b)^a mod p`, which simplifies to `g^(b*a) mod p`.
- Bob's calculation is `s = (g^a)^b mod p`, which simplifies to `g^(a*b) mod p`.

Since `b*a` is the same as `a*b`, they both compute the same final value. An eavesdropper, however, cannot easily find `a`or `b` just by looking at the public values, making it impossible for them to compute the shared secret `s`.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Module-2-Week-2-Session-2-Asymmetric-Encryption-Diffie-Hellman-kdyizw71zschnkz?mode=doc](https://gamma.app/docs/Module-2-Week-2-Session-2-Asymmetric-Encryption-Diffie-Hellman-kdyizw71zschnkz?mode=doc)

Try not to peek before class - spoilers inside!

</aside>