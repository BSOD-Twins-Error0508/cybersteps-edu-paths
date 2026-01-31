Hello! Welcome to the world of encryption. It might sound like something out of a spy movie, but it's a super important part of how we keep information safe online and on our computers every single day. Think of it as a way to write secret messages that only the right person can read. In this guide, we'll learn what encryption is, why it's a big deal, and some of the basic ways it works.

## What is Encryption?

![image.png](attachment:50de26f4-dc96-4bf4-8d61-7c72cef0ef91:image.png)

Imagine you have a secret message you want to send to a friend. You wouldn't want just anyone to read it, right? Encryption is like a special secret code for your digital messages and files.

Here's the basic idea:

- You start with your normal, readable message. This is called **plaintext**. (For example, "Let's meet at the park.")
- You use a secret coding method (called an **algorithm** or **cipher**) and a secret password or phrase (called a **key**) to scramble your message.
- The scrambled, unreadable message is called **ciphertext**. (It might look like a jumble of random letters, like "XqZ7#Ps3!")
- Only someone who knows the same secret coding method and the exact same key can unscramble it back into your original plaintext message. This unscrambling is called **decryption**.

The main reason we use encryption is for **confidentiality** – that’s a fancy word for keeping information private and secret from people who aren't supposed to see it.

## Core Terminology - The Basic Lingo

Let's get familiar with a few key terms. Don't worry, we'll keep it simple!

- **Plaintext**: Your original, easy-to-read message or information. (e.g., "My password is cat123")
- **Ciphertext**: The scrambled, secret-coded version of your plaintext. (e.g., "aGv#7!kLp")
- **Algorithm (Cipher)**: The specific recipe or set of rules used to turn plaintext into ciphertext, and ciphertext back into plaintext. Think of it as the _method_ of scrambling and unscrambling.
- **Key**: A secret piece of information (like a special password) that the algorithm uses. The key makes your encryption unique. If someone has your ciphertext but doesn't have the right key, they can't read your message. The secrecy of the key is super important!
- **Encryption**: The act of changing plaintext into ciphertext. (Scrambling the message)
- **Decryption**: The act of changing ciphertext back into plaintext. (Unscrambling the message)

## Why is Encryption So Important in Cybersecurity?

Encryption is like a digital bodyguard for your information. It's used everywhere to protect us:

- **Keeping Stored Information Safe (Data at Rest)**: Think about the files on your computer, your phone, or a USB stick. If your device gets lost or stolen, encryption can stop thieves from looking at your private photos, documents, or bank details. This is like having a super strong safe for your digital stuff.
- **Protecting Information on the Move (Data in Transit)**: When you send an email, shop online, or log into a website, your information travels over the internet. Encryption scrambles this information so that if bad guys try to spy on it, they just see jumbled nonsense. You know this is happening when you see a little padlock icon and `https://` in your web browser's address bar.
- **Following Rules and Laws**: Many laws around the world say that companies _must_ use encryption to protect people's personal information (like your name, address, or health records).
- **Making Sure Information is Real and Unchanged**: Encryption, especially when combined with other tricks, can also help prove that a message really came from the person who claims to have sent it (**authenticity**) and that nobody has messed with it along the way (**integrity**).

### Think about it

Can you think of three times today you might have used something that relies on encryption without even realizing it? (Hint: Using your phone, browsing the web, or sending a message?)

## Types of Encryption - Different Ways to Scramble

There are two main flavors of encryption, and they differ in how they use their keys:

### 1. Symmetric Encryption (One Secret Key for Everything)

![Screenshot 2025-06-14 at 23.23.01.png](attachment:54efbf61-8fff-446d-9773-5862d69679c6:Screenshot_2025-06-14_at_23.23.01.png)

Symmetric encryption is like having a secret diary that you lock with a special key. Only someone who has an identical copy of _that exact same key_ can open it and read what's inside.

- **How it works**:
    1. You and your friend agree on one secret key.
    2. You write your message (plaintext), then use the secret key and a symmetric algorithm to encrypt it into ciphertext.
    3. You send the ciphertext to your friend.
    4. Your friend uses the _exact same_ secret key and the same algorithm to decrypt it back into plaintext.
- **Real-world examples**: AES is a very common and strong symmetric algorithm used for things like protecting files on your computer or securing Wi-Fi networks. (DES and 3DES are older examples you might hear about, but they are less secure now).
- **Good things about it (Pros)**:
    - **Super Fast**: Symmetric encryption is generally very quick, which is great for encrypting lots of data, like big files or streaming movies.
- **Challenges (Cons)**:
    - **Sharing the Key is Tricky**: The biggest headache is: how do you safely give the secret key to your friend in the first place? If you send it in a normal email, someone could intercept it. And if the key isn't secret anymore, your encryption is useless! This is called the "key distribution problem."
    - **Too Many Keys?**: If you want to communicate secretly with lots of different people, you'd need a different secret key for each person. Imagine trying to remember hundreds of different keys – it would be a nightmare!

### 2. Asymmetric Encryption (Two Keys are Better Than One!)

![Screenshot 2025-06-14 at 23.23.21.png](attachment:bf271556-c211-4421-aad4-74868ad78bb7:Screenshot_2025-06-14_at_23.23.21.png)

Asymmetric encryption is a bit more clever. It uses a pair of keys for each person: one **public key** and one **private key**.

- **Public Key**: You can share this key with anyone! Shout it from the rooftops, put it on your website – it doesn't matter. It's like giving out your home mailing address; anyone can use it to send you a letter.
- **Private Key**: This key is YOURS and yours alone. You must keep it super secret, like the key to your personal safe.

These two keys are mathematically linked, but it's practically impossible to figure out your secret private key just by knowing your public key.

- **Analogy - The Special Mailbox**: Imagine you have a special mailbox.
    - It has a slot where anyone can drop a letter (this is like using your **public key** to send you an encrypted message).
    - Once a letter is in, the slot locks.
    - Only YOU have the special key (your **private key**) that can open the mailbox and read the letters. So, anyone can use your public key to "lock" (encrypt) a message for you, but only your private key can "unlock" (decrypt) it.
- **How it works for sending secret messages**:
    1. Let's say your friend Sarah wants to send you a secret message.
    2. Sarah asks for your **public key** (which you can give her freely).
    3. Sarah uses your public key to encrypt her message. Now it's ciphertext.
    4. She sends this ciphertext to you.
    5. You use your **private key** (which only you have) to decrypt the message. Voila! Even if someone else gets a copy of the ciphertext and your public key, they can't read the message because they don't have your secret private key.
- **Real-world examples**: RSA and ECC are common asymmetric algorithms. They are used in many places, like securing website connections and creating digital "signatures" (which we'll talk about later).
- **Good things about it (Pros)**:
    - **Solves the Key Sharing Problem (for secret keys)**: You don't need a pre-existing secret channel to share your public key. This makes starting a secure conversation much easier.
    - **Digital Signatures**: This is a cool feature! Asymmetric keys can also be used to "sign" digital documents. It's like a tamper-proof seal that proves who sent the message and that it hasn't been changed. (More on this in the "Certificates & Signatures" lesson!)
- **Challenges (Cons)**:
    - **Slower**: Asymmetric encryption involves more complicated math, so it's quite a bit slower than symmetric encryption. It's not ideal for encrypting very large amounts of data directly.

### Try it yourself - A Simple Code

Let's try a very basic, old-fashioned (and definitely not secure for real secrets!) encryption called the Caesar Cipher. Here, you just shift each letter in your message a certain number of places down the alphabet. The "key" is how many places you shift. Let's use a key of **3**. Plaintext: `DOG`

1. D shifts 3 letters forward: D -> E -> F -> G
2. O shifts 3 letters forward: O -> P -> Q -> R
3. G shifts 3 letters forward: G -> H -> I -> J Ciphertext: `GRJ`

Now, can you decrypt `GRJ` using the same key (3), but shifting backwards? What word do you get? What if you had the ciphertext `APPLE` and knew the key was a shift of `1` (backwards)? What was the original word?

This shows the basic idea: an algorithm (shifting letters) and a key (the number of shifts) change plaintext to ciphertext and back. Real encryption used today is thousands of times more complex and secure!

## Hybrid Encryption: Using the Best of Both!

![image.png](attachment:fc10c9fd-824b-4d3b-8daa-fd88bd1d59c6:image.png)

So, symmetric encryption is fast but has key-sharing problems. Asymmetric encryption is great for sharing keys but is slow. What if we could combine them? That's exactly what **hybrid encryption** does!

This is how most secure stuff on the internet works (like when you see `https://` in your browser):

1. **Securely Share a Secret Key**: Your computer and the website's server first use the slower _asymmetric encryption_(public and private keys) just to safely create and agree on a brand new, temporary _symmetric key_ (a single secret key). This is like using the special mailbox system just to securely pass over the key to a regular diary.
2. **Fast Data Scrambling**: Once they both have this new symmetric key, they switch to the much faster _symmetric encryption_ to scramble and unscramble all the actual information you're sending and receiving (like your password, or the webpage content).

This way, you get the secure key-sharing magic of asymmetric encryption and the speedy data protection of symmetric encryption. It's the best of both worlds!

## Hashing: Encryption's Cousin (But Different!)

![image.png](attachment:b14b6a58-7d18-4144-a029-6ccaed642dc5:image.png)

You'll often hear about **hashing** when people talk about encryption. They are related, but they do different jobs.

- **Hashing is a One-Way Street**: A hash function takes your input (like a password or a whole file) and squishes it down into a short, fixed-length string of letters and numbers. This string is called a **hash value** (or sometimes a "fingerprint" or "digest").
- **Key Things About Hashing**:
    - **One-Way Only**: You _cannot_ get the original input back from its hash value. It's like trying to unbake a cake to get the original eggs, flour, and sugar. Impossible!
    - **Always the Same Hash for the Same Input**: If you put the same data into the hash function, you'll always get the exact same hash value out.
    - **Fixed Length**: No matter how big or small your input is, the hash value is always the same length (e.g., a SHA-256 hash is always 64 characters long).
    - **Tiny Change, Big Difference (Avalanche Effect)**: If you change even one tiny bit of the input data, the hash value will change completely and look totally different.
- **What's Hashing Used For?**:
    - **Checking if Files are Unchanged (Integrity)**: Companies often provide a hash value for software downloads. You can download the file, calculate its hash yourself, and compare it to the one the company provides. If they match, you know the file hasn't been messed with.
    - **Storing Passwords Safely**: Websites should _never_ store your actual password. Instead, they store a hash of your password. When you try to log in, they hash the password you type and compare it to the stored hash. If the hashes match, you're in! If a hacker steals the database, they get a list of hashes, not your actual passwords (though good sites add extra protections like "salting" to make these hashes even harder to crack).
- **Examples of Hash Functions**: You might see names like MD5 (older, not so secure anymore), SHA-1 (also getting old), and SHA-256 or SHA-3 (these are strong and widely used).

**The Big Difference**:

- **Encryption** is a _two-way_ process (plaintext -> ciphertext -> plaintext). Its main job is to keep information **secret (confidentiality)**.
- **Hashing** is a _one-way_ process (input -> hash). Its main job is to check if data has been **changed (integrity)** or to help with things like password protection.

### Think about it

1. If a website stores only hashes of passwords, and a hacker steals those hashes, why is it _still_ a very bad idea to use the same password on many different websites? (Hint: What if the hacker figures out the original password for one hash?)
2. Why is it so important that hashing is "one-way" for storing passwords? What could happen if it was easy to turn a hash back into the original password?

## Common Use Cases Revisited - Encryption in Your Daily Life

Now that you know a bit about the different types, let's see where they pop up:

- **Secure Websites (HTTPS)**: That little padlock and `https://` in your browser mean your connection to the website is encrypted.
    - It uses _asymmetric encryption_ (public/private keys) at the very start to secretly agree on a temporary _symmetric key_ with the website's server.
    - Then, it uses that faster _symmetric key_ to scramble all the information (like your login details or what you're browsing) for the rest of your visit. This keeps your online activity private from snoops.
- **Encrypted Email**: Some email services let you send encrypted messages.
    - Often, your email program will scramble the email content using a fast _symmetric key_.
    - Then, it will use the recipient's _public key_ (asymmetric encryption) to securely send them that symmetric key so they can unlock the message.
- **Protecting Your Device's Files (Full-Disk Encryption)**: Software like BitLocker (for Windows) or FileVault (for Macs) can scramble all the files on your computer's hard drive.
    - This usually uses strong _symmetric encryption_.
    - If your computer is lost or stolen, the thief can't get to your files without your password, which is needed to unlock the encryption.
- **VPNs (Virtual Private Networks)**: A VPN creates a secret, encrypted "tunnel" for your internet traffic.
    - This means even if you're using public Wi-Fi (like at a café), your data is scrambled and hidden from others on that network.
    - VPNs typically use _symmetric encryption_ for the data flowing through the tunnel and _asymmetric encryption_ to set up the secure connection in the first place.
- **Password Managers**: These apps are like super-secure digital safes for all your passwords.
    - They store your passwords in an encrypted vault, usually using strong _symmetric encryption_.
    - You only need to remember one "master password" to unlock the vault and access all your other passwords.

Understanding these basic ideas about encryption is a big first step! It's a key ingredient in keeping our digital world safe. Make sure to go over these concepts, as they're foundational to many other topics in cybersecurity.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Technical-Foundations-10-Encryption-may7n9yeazv3h97?mode=doc](https://gamma.app/docs/Technical-Foundations-10-Encryption-may7n9yeazv3h97?mode=doc)

Try not to peek before class - spoilers inside!

</aside>