Welcome! In previous lessons, we started exploring the Application Layer, the layer where user-facing applications interact with the network. Today, we'll dive into several other essential application layer protocols that you'll frequently encounter in networking and cybersecurity. Understanding their purpose and basic mechanics is crucial.

We'll cover:

- Email Protocols: SMTP, POP3, IMAP
- File Transfer: FTP
- Remote Access: Telnet, SSH, RDP

## Email Protocols: Sending and Receiving Messages

![image.png](attachment:33f23e30-618c-47e8-bd3c-3279ca003944:image.png)

Email seems simple, but behind the scenes, several protocols work together.

**SMTP (Simple Mail Transfer Protocol)**

- **Purpose:** Primarily used for **sending** email messages from an email client (like Apple Mail or Outlook) to an email server, and also for transferring email between mail servers.
- **How it works:** When you hit "send," your client connects to your outgoing mail server (e.g., [smtp.yourprovider.com](http://smtp.yourprovider.com)) using SMTP, typically on **port 25** (standard, often unencrypted) or **port 587** (standard for client submission, usually requires encryption like TLS/STARTTLS) or **port 465** (older standard, uses implicit TLS/SSL). The server then relays the message towards the recipient's mail server, potentially involving several hops between SMTP servers.
- **Key Characteristic:** SMTP is a "push" protocol; it pushes messages from the client to the server and between servers. It's generally not used for retrieving email _from_ a server.
- **Security:** Basic SMTP (port 25) is often unencrypted, meaning email content and credentials could be intercepted. Modern implementations use encryption (TLS/SSL) via STARTTLS on port 587 or implicit TLS on port 465.

**POP3 (Post Office Protocol version 3)**

- **Purpose:** Used for **retrieving** email messages from a mail server to an email client.
- **How it works:** Your email client connects to the incoming mail server (e.g., [pop.yourprovider.com](http://pop.yourprovider.com)) using POP3, typically on **port 110** (unencrypted) or **port 995** (encrypted with TLS/SSL). POP3 usually downloads emails to your local device and _removes_ them from the server (though configuration options sometimes allow leaving copies).
- **Key Characteristic:** Designed for offline access. Download once, read locally. This means emails aren't typically synchronized across multiple devices. If you read an email on your phone using POP3, it won't appear read on your laptop.
- **Security:** Basic POP3 (port 110) is unencrypted. Port 995 provides encryption.

**IMAP (Internet Message Access Protocol)**

- **Purpose:** Also used for **retrieving** email messages from a mail server, but with more features than POP3.
- **How it works:** Your client connects to the incoming mail server (e.g., [imap.yourprovider.com](http://imap.yourprovider.com)) using IMAP, typically on **port 143** (unencrypted or STARTTLS) or **port 993** (encrypted with TLS/SSL). Unlike POP3, IMAP generally keeps emails **on the server**. Your client accesses and manages the emails directly on the server.
- **Key Characteristic:** Designed for online and multi-device access. Changes made on one device (reading, deleting, moving to folders) are reflected across all devices connected to the same account because the "master copy" stays on the server. It supports server-side folders.
- **Security:** Basic IMAP (port 143) can be unencrypted, but STARTTLS can add encryption. Port 993 provides encryption from the start.

### Think about it

- Why might a company block standard port 25 for outgoing email from employee laptops and require them to use port 587 instead?
- If you want to access your email seamlessly from your laptop, phone, and tablet, keeping everything synchronized, which protocol would you choose for retrieving mail: POP3 or IMAP? Why?

## File Transfer Protocol (FTP)

![image.png](attachment:b1614ddd-c338-40b8-aa8e-1c1f1ab2ff7e:image.png)

- **Purpose:** Used for transferring files between a client and a server over a network. It's one of the oldest internet protocols.
    
- **How it works:** FTP uses **two separate TCP connections**:
    
    - **Control Connection (Port 21):** Used for sending commands (like `USER`, `PASS`, `LIST`, `RETR`, `STOR`) and receiving responses. This connection stays open for the duration of the session.
    - **Data Connection (Variable Port):** Used for the actual transfer of file data or directory listings. The port used for this connection depends on whether the mode is _Active_ or _Passive_.
        - _Active Mode:_ The client tells the server which port it's listening on, and the server _initiates_ the data connection back to the client. This can be problematic with firewalls on the client-side.
            
        - _Passive Mode:_ The client asks the server to listen on a specific port, and the client _initiates_ the data connection to the server on that port. This is generally more firewall-friendly.
            
            ![Screenshot 2025-07-11 at 13.55.57.png](attachment:abc7836f-377d-4e7a-816c-346794480309:Screenshot_2025-07-11_at_13.55.57.png)
            
- **Key Characteristic:** Designed purely for file transfer. It includes commands for listing directories, creating directories, deleting files, etc.
    
- **Security:** Standard FTP (port 21) is **insecure**. Both credentials (username/password) and file data are sent in **clear text**, making them easily interceptable.
    
- **Secure Alternatives:**
    
    - **FTPS (FTP Secure):** Adds TLS/SSL encryption to FTP. Can be _Explicit_ (client connects on port 21 and requests encryption with `AUTH TLS`) or _Implicit_ (client connects directly using TLS on port 990).
    - **SFTP (SSH File Transfer Protocol):** Often confused with FTPS, but it's a completely different protocol that runs over SSH (usually on port 22). It provides file transfer capabilities within a secure SSH tunnel. It only uses a single connection.

### Try it yourself

Most operating systems have a built-in command-line FTP client. Open your Terminal (on macOS, search for Terminal in Spotlight) and try connecting to a public anonymous FTP server (one that doesn't require a specific username/password). A common one is `ftp.dlptest.com` (Username: `dlpuser`, Password: `rNrKYTX9g7z3RgJRmxWuGHbeu`).

1. Make sure you have Homebrew installed [https://brew.sh/](https://brew.sh/)
2. Install ftp service on macos: `brew Install tnftp`
3. Type: `ftp ftp.dlptest.com`
4. When prompted for Name, enter: `dlpuser`
5. When prompted for Password, enter: `rNrKYTX9g7z3RgJRmxWuGHbeu`
6. Once logged in, type `ls` or `dir` to list files.
7. Type `pwd` to see the current directory on the server.
8. Type `quit` to exit.

## Remote Access Protocols

These protocols allow you to connect to and control another computer over a network.

**Telnet**

- **Purpose:** Provides a bidirectional, interactive text-based communication facility using a virtual terminal connection. Essentially, it allows you to log in to a remote machine and run commands as if you were sitting in front of it.
- **How it works:** Telnet client connects to a Telnet server, typically on **TCP port 23**. It establishes a connection and then simply relays keystrokes from the client to the server and displays output from the server back to the client.
- **Key Characteristic:** Very simple, widely implemented in the past.
- **Security:** Telnet is **highly insecure**. All data, including usernames and passwords, is transmitted in **clear text**. Anyone monitoring the network can capture your credentials and see everything you type and all the output. **Avoid using Telnet for logins whenever possible.** Its main modern use is sometimes for quick banner grabbing or testing if a specific port is open on a remote server, but even that should be done cautiously.

**SSH (Secure Shell)**

![image.png](attachment:9dc3459d-5e99-497a-a813-9259f27d57d9:image.png)

- **Purpose:** Provides a **secure** way to access a remote computer. It allows secure remote login, command execution, and other secure network services (like SFTP and port forwarding) over an insecure network.
- **How it works:** SSH client connects to an SSH server, typically on **TCP port 22**. It establishes an **encrypted** connection _before_ any authentication or data transfer occurs. It uses public-key cryptography to authenticate the server (preventing man-in-the-middle attacks) and allows for various client authentication methods (passwords, public/private key pairs).
- **Key Characteristic:** Encryption and authentication are built-in. It replaces insecure tools like Telnet and rlogin.
- **Security:** Designed with security as a primary goal. All traffic (logins, commands, output) is encrypted.

### Think about it

- You need to log into a remote Linux server to update some configuration files. Should you use Telnet or SSH? Why is the other choice a bad idea?

**RDP (Remote Desktop Protocol)**

![image.png](attachment:0f02d7ca-0ba9-4cab-bfec-b9955894b926:image.png)

- **Purpose:** A proprietary protocol developed by Microsoft, allowing a user to connect to another computer over a network with a full graphical interface. It makes the remote machine's desktop appear on your local machine.
- **How it works:** An RDP client connects to an RDP server (typically a Windows machine, though servers exist for other OSs), usually on **TCP port 3389**. It transmits keyboard input, mouse movements, and screen updates over the network. Modern RDP uses encryption.
- **Key Characteristic:** Provides graphical remote access, unlike the text-based access of Telnet/SSH. Commonly used for remote administration of Windows servers and accessing remote desktops.
- **Security:** While modern RDP includes encryption, older versions had vulnerabilities. Security also depends heavily on strong authentication (passwords, multi-factor authentication) and ensuring only authorized users can connect. Exposing RDP directly to the internet (port 3389 open on the firewall) is a significant security risk and a common target for attackers. Network Level Authentication (NLA) adds a layer of security by requiring authentication before a full session is established.

## Summary Table

|Protocol|Default Port(s)|Purpose|Security|Key Feature(s)|
|---|---|---|---|---|
|SMTP|25, 587 (TLS), 465 (SSL)|Sending Email|Often clear (25)|Pushes email to/between servers|
|POP3|110, 995 (SSL/TLS)|Retrieving Email|Often clear (110)|Downloads email, often removes from server|
|IMAP|143, 993 (SSL/TLS)|Retrieving/Managing Email|Often clear (143)|Manages email on server, syncs across devices|
|FTP|21 (Control), Data varies|File Transfer|**Insecure**|Separate control/data channels, clear text|
|Telnet|23|Remote Text Login|**Insecure**|Simple, clear text|
|SSH|22|Secure Remote Login/Exec|**Secure**|Encrypted, authenticated|
|RDP|3389|Remote Graphical Desktop|Encrypted (Modern)|Graphical interface, Windows-centric|

Understanding these protocols, their purposes, default ports, and especially their security implications is vital for network administration and cybersecurity. You'll use this knowledge to configure systems, troubleshoot network issues, and analyze network traffic for potential threats.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Networking-6-Application-Layer-Common-Protocols-276udg69x0l4924?mode=doc](https://gamma.app/docs/Networking-6-Application-Layer-Common-Protocols-276udg69x0l4924?mode=doc)

Try not to peek before class - spoilers inside!

</aside>