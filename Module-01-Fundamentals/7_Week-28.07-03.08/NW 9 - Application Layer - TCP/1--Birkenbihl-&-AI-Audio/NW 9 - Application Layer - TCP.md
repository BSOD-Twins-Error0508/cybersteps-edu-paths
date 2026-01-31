
Welcome! Before our live session on the Transmission Control Protocol (TCP), please go through this material. We'll be diving into one of the most fundamental protocols that powers the internet. Understanding TCP is crucial for comprehending how reliable communication happens online, which is vital in cybersecurity for analyzing network traffic and understanding application behavior.

## The Transport Layer

Recall the 5-layer network model we discussed. Sandwiched between the Network Layer (handling IP addresses and routing) and the Application Layer (like HTTP or DNS) lies the **Transport Layer**.

The primary role of the Transport Layer is to provide logical communication between _applications_ running on different hosts. While the Network Layer gets packets from one host to another, the Transport Layer gets the data to the _correct application_ on that host. It acts like a mail sorting room within the destination computer, ensuring the data meant for your web browser doesn't end up delivered to your email client.

The two most common Transport Layer protocols are TCP and UDP (User Datagram Protocol). Today, we focus on TCP.

## What is TCP?

TCP stands for **Transmission Control Protocol**. It's defined in RFC 793 (and updated by many others). Think of TCP as the reliable, careful postal service of the internet. Its main goal is to ensure that data sent from one application arrives **reliably**, **in order**, and **error-checked** at the application on the receiving end.

TCP is **connection-oriented**. This means before any actual application data is exchanged, the two communicating devices (e.g., your computer and a web server) establish a connection through a process called a **handshake**. This ensures both sides are ready to communicate and agree on some initial parameters. Once the data transfer is complete, the connection is formally closed.

## Key Characteristics of TCP

TCP provides several features that make it suitable for applications requiring high reliability:

1. **Connection-Oriented:** As mentioned, TCP establishes a dedicated connection using a **three-way handshake** before data transfer begins.
    
    - **Step 1 (SYN):** The client wanting to connect sends a TCP segment with the SYN (Synchronize) flag set. This segment includes an initial sequence number (ISN).
    - **Step 2 (SYN-ACK):** The server responds with a TCP segment where both the SYN and ACK (Acknowledgment) flags are set. It acknowledges the client's ISN and proposes its own ISN.
    - **Step 3 (ACK):** The client sends back a segment with the ACK flag set, acknowledging the server's ISN.
    - At this point, the connection is established, and data transfer can begin.
    
    ```mermaid
    sequenceDiagram
        participant Client
        participant Server
    
        Client->>Server: SYN (seq = x)
        Server->>Client: SYN‑ACK (seq = y, ack = x+1)
        Client->>Server: ACK (ack = y+1)
    
        Note right of Server: Connection established
    ```
    
2. **Reliable Delivery:** TCP guarantees that data sent will arrive. It achieves this using:
    
    - **Sequence Numbers:** Each byte of data sent is assigned a sequence number.
    - **Acknowledgments (ACKs):** When the receiver gets data, it sends back an acknowledgment indicating the next sequence number it expects. If the sender doesn't receive an ACK within a certain time, it assumes the data was lost and **retransmits** it.
3. **Ordered Data Transfer:** IP packets can take different routes and arrive out of order. TCP uses the sequence numbers to reassemble the data segments in the correct order before passing them up to the application layer.
    
4. **Flow Control:** The receiver has a limited amount of buffer space. TCP uses a **sliding window** mechanism. The receiver advertises its available buffer space (the "window size") in the TCP header. The sender agrees not to send more data than the receiver can handle, preventing the receiver from being overwhelmed.
    
5. **Congestion Control:** TCP tries to prevent overwhelming the _network_ itself (not just the receiver). It uses algorithms to slow down its transmission rate if it detects signs of network congestion (like lost packets). This is crucial for the overall stability of the internet.
    

## Ports: Directing Traffic

How does TCP know which application (e.g., web browser, email client, game) on the destination host should receive the data? It uses **port numbers**.

Imagine an apartment building (the host computer) with many apartments (applications). The IP address gets you to the building, but the port number gets you to the specific apartment.

- Port numbers are 16-bit unsigned integers (0 to 65535).
- The combination of an IP address and a port number uniquely identifies a specific process on a specific host (this combination is often called a **socket**).
- **Well-Known Ports (0-1023):** Reserved for standard, universally known services (e.g., HTTP on port 80, HTTPS on port 443, SSH on port 22, FTP on port 21). On Unix-like systems, binding to these ports usually requires administrative privileges.
- **Registered Ports (1024-49151):** Used by specific applications and services registered with IANA (Internet Assigned Numbers Authority).
- **Dynamic/Private/Ephemeral Ports (49152-65535):** Used by client applications as their source port when initiating connections. These are typically assigned randomly by the operating system.

## The TCP Header

![image.png](attachment:fbf9330d-6faf-4232-bf5e-1896db62a5b4:image.png)

Like other protocols, TCP adds its own header to the data it receives from the application layer. This header contains crucial control information. Here are some key fields:

- **Source Port (16 bits):** Identifies the application port number on the sending host.
- **Destination Port (16 bits):** Identifies the application port number on the receiving host.
- **Sequence Number (32 bits):** Used for ordering data and reliability. It identifies the sequence number of the first byte of data in this segment.
- **Acknowledgment Number (32 bits):** Used for reliability. If the ACK flag is set, this field contains the sequence number of the _next_ byte the sender of the ACK expects to receive.
- **Flags (e.g., SYN, ACK, FIN, RST, PSH, URG):** These are single bits used for control purposes:
    - `SYN`: Synchronize sequence numbers (used in handshake).
    - `ACK`: Acknowledgment field is valid.
    - `FIN`: Finish; sender has no more data to send (used in connection termination).
    - `RST`: Reset the connection (abruptly closes the connection, often due to errors).
    - `PSH`: Push; tells the receiver to pass the data to the application immediately.
    - `URG`: Urgent pointer field is valid (rarely used).
- **Window Size (16 bits):** Used for flow control. Specifies the number of bytes the sender of this segment is willing to receive.
- **Checksum (16 bits):** Used for error detection. Calculated over the TCP header, TCP data, and parts of the IP header. If the checksum doesn't match upon arrival, the segment is discarded.

## TCP Connection Lifecycle

![image.png](attachment:8948635f-856b-4935-9b0e-4ecda0e070fe:image.png)

1. **Establishment:** The three-way handshake (SYN, SYN-ACK, ACK).
2. **Data Transfer:** Segments containing application data are exchanged, with sequence numbers and ACKs ensuring reliability and order. Flow and congestion control mechanisms operate during this phase.
3. **Termination:** When an application is finished sending data, it initiates connection closing. This typically involves a **four-way handshake**:
    - Side A sends a FIN segment.
    - Side B sends an ACK for Side A's FIN.
    - Side B, when ready to close its side, sends its own FIN segment.
    - Side A sends an ACK for Side B's FIN.
    - The connection is now closed. (A connection can also be abruptly closed using the RST flag).

### Think about it

Why is the reliability provided by TCP absolutely essential for web browsing (HTTP/HTTPS) or transferring files (FTP/SFTP), but perhaps less critical, or even detrimental, for applications like live video streaming or online gaming? What trade-offs are being made?

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Networking-9-Transport-Layer-TCP-zg2x07u5vsdnczp?mode=doc](https://gamma.app/docs/Networking-9-Transport-Layer-TCP-zg2x07u5vsdnczp?mode=doc)

Try not to peek before class - spoilers inside!

</aside>