Welcome to the world of User Datagram Protocol (UDP), a core protocol of the Internet's transport layer. Unlike its counterpart TCP, which you might have encountered earlier, UDP takes a different approach to data transmission. It prioritizes speed and simplicity over reliability and order. This preparation material will introduce you to UDP, its characteristics, how it works, and where it's commonly used.

## The Transport Layer: A Quick Recap

Before diving into UDP, let's briefly recall the role of the transport layer in the network model (like the TCP/IP model or OSI model). The transport layer is responsible for logical communication between application processes running on different hosts. It takes data from applications, segments it if necessary, and passes it to the network layer. On the receiving end, it reassembles the data and delivers it to the correct application. Two main protocols operate at this layer: TCP (Transmission Control Protocol) and UDP (User Datagram Protocol).

## What is UDP?

UDP stands for User Datagram Protocol. It's a simple, lightweight, and connectionless protocol. Think of it as sending a postcard: you write the message, address it, and drop it in the mail. You don't establish a connection with the recipient beforehand, and you don't get a confirmation when they receive it. It might get lost, it might arrive out of order if you send multiple postcards, but it's fast and doesn't involve much overhead.

Key characteristics of UDP include:

- **Connectionless**: UDP does not establish a connection (no "handshake") before sending data. Each UDP datagram (a unit of data in UDP) is an independent entity, unrelated to any other datagram.
- **Unreliable**: UDP provides no guarantee that the data will reach its destination. There are no acknowledgments, no retransmission of lost packets, and no built-in mechanisms to ensure data integrity beyond an optional checksum. If a datagram is lost, it's lost.
- **Not Ordered**: UDP does not ensure that datagrams arrive in the order they were sent. If Application A sends datagram 1, then datagram 2, they might arrive as datagram 2, then datagram 1, or one might not arrive at all.
- **Low Overhead**: UDP headers are very small (only 8 bytes), which means less protocol-related data is added to your actual data. This contributes to its speed.
- **Fast**: Because there's no connection setup, no acknowledgments, and minimal header information, UDP is generally faster than TCP for transmitting data.

## The UDP Header

![image.png](attachment:738b4efd-c9ce-49e3-86e1-88bf65b7b78d:image.png)

The simplicity of UDP is reflected in its header structure. A UDP header is only 8 bytes long and consists of four fields:

- **Source Port (16 bits)**: Identifies the port number of the sending application process. This field is optional, and if not used, it should be set to zero. It's important for the receiver if it needs to send a reply.
- **Destination Port (16 bits)**: Identifies the port number of the receiving application process on the destination host. This is a crucial field for delivering the data to the correct application.
- **Length (16 bits)**: Specifies the length in bytes of the UDP header and the UDP data (payload). The minimum length is 8 bytes (the header itself, with no data).
- **Checksum (16 bits)**: Used for error detection. It calculates a checksum value for the UDP header, the UDP data, and parts of the IP header (pseudo-header).
    - For IPv4, the checksum is optional. If not used, it's set to all zeros.
    - For IPv6, the checksum is mandatory.
    - If the checksum calculation at the receiver doesn't match the checksum value in the header, the datagram is typically discarded silently. This provides a basic level of integrity checking.

### Think About It

Why do you think the UDP checksum is optional for IPv4 but mandatory for IPv6? What might have changed in the design philosophy or network environment?

## Ports Reminder

Both UDP and TCP use port numbers to differentiate between various application processes running on a single host. When data arrives at a host, the transport layer uses the destination port number to pass the data to the correct application.

- **Well-Known Ports (0 to 1023)**: These are reserved for common services and applications (e.g., HTTP uses TCP port 80, DNS uses UDP port 53).
- **Registered Ports (1024 to 49151)**: These can be registered by software vendors for specific applications.
- **Dynamic/Private/Ephemeral Ports (49152 to 65535)**: These are used for temporary or private connections, often assigned dynamically by the client's operating system when initiating a connection.

When a client wants to communicate with a server (e.g., making a DNS query), the client usually uses a dynamic port as its source port and the well-known port of the service (e.g., port 53 for DNS) as the destination port.

## When is UDP the Right Choice?

Given its "best-effort" delivery, UDP might seem like a poor choice. However, its speed and low overhead make it ideal for certain types of applications:

- **Applications Tolerant of Data Loss**: If occasional loss of data is acceptable, or if the application has its own mechanisms for handling errors and retransmissions.
- **Real-time Applications**:
    - **Streaming Media**: For live video and audio streaming (e.g., online gaming, VoIP like Skype or Zoom), receiving data quickly is more important than receiving every single bit. A lost frame in a video stream or a slight glitch in audio is often preferable to a long delay caused by retransmissions.
    - **Online Gaming**: Fast updates are crucial. Old data is often useless.
- **Query-Response Protocols**:
    - **DNS (Domain Name System)**: DNS queries are typically small and expect a quick response. If a query is lost, the client can simply resend it. Using UDP keeps DNS fast.
    - **DHCP (Dynamic Host Configuration Protocol)**: Used for obtaining IP addresses. It operates in a local network where packet loss is generally low.
- **Multicasting/Broadcasting**: UDP supports sending a single datagram to multiple recipients (multicast) or all recipients on a subnet (broadcast) efficiently. TCP is designed for one-to-one communication.
- **TFTP (Trivial File Transfer Protocol)**: A simplified version of FTP that uses UDP. It's often used for booting diskless workstations or transferring firmware to network devices.
- **SNMP (Simple Network Management Protocol)**: Used for managing and monitoring network devices.

### Try It Yourself

Think about the applications you use daily.

1. Which ones do you think might be using UDP?
2. For each, why would UDP be a suitable choice (or not)? Consider what would happen if some data packets were lost or arrived out of order.

## UDP vs. TCP: A Quick Comparison

![tcp-vs-udp.svg](attachment:82afe0d7-ad4a-4bee-9182-2b174014f7ca:tcp-vs-udp.svg)

|Feature|UDP (User Datagram Protocol)|TCP (Transmission Control Protocol)|
|---|---|---|
|**Connection**|Connectionless|Connection-oriented|
|**Reliability**|Unreliable (best-effort delivery)|Reliable (guaranteed delivery)|
|**Ordering**|Not guaranteed|Guaranteed in-order delivery|
|**Overhead**|Low (8-byte header)|Higher (20-byte header minimum)|
|**Speed**|Generally faster|Slower due to connection setup & acks|
|**Flow Control**|No|Yes|
|**Congestion Ctrl**|No|Yes|
|**Use Cases**|DNS, DHCP, VoIP, streaming, gaming|Web (HTTP/S), email (SMTP), FTP|

## What Happens to Lost UDP Packets?

Simply put, they are gone. UDP itself does not attempt to recover lost packets. It's up to the application layer to deal with this, if necessary. For example:

- A DNS client will typically time out and resend the query if it doesn't receive a response.
- A VoIP application might just accept a momentary glitch in the audio. It won't try to recover the lost audio packet because, by the time it could be retransmitted, the conversation would have moved on, and the old audio would be irrelevant.

This "application-level recovery" is a common pattern for services built on UDP that require some form of reliability but still want the benefits of UDP's low overhead.

### Think About It

Consider a video streaming service. If it uses UDP and a packet is lost, what do you see? How might the application try to make this less jarring for the user, even without UDP retransmitting the packet?

This pre-class material should give you a solid foundation on UDP. We will explore these concepts further, look at UDP in action, and discuss its security implications in the live session.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Networking-10-Transport-Layer-UDP-qtjf56re63j2rj1?mode=doc](https://gamma.app/docs/Networking-10-Transport-Layer-UDP-qtjf56re63j2rj1?mode=doc)

Try not to peek before class - spoilers inside!

</aside>