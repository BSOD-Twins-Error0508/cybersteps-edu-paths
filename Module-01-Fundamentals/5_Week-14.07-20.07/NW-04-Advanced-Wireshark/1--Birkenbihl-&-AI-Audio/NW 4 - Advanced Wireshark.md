In our previous session, we captured our first network packets with Wireshark and learned how basic display filters (`ip.addr == ...`, `tcp.port == ...`) help us start making sense of the traffic. We saw the raw data, but now we need better tools to analyze it effectively.

Network captures can quickly grow to immense sizes. To find the information that matters, we need to move beyond simple filters. This session introduces more advanced Wireshark features that let you precisely filter traffic, reconstruct full conversations from individual packets, get high-level statistical summaries of network activity, and even extract files directly from network traffic. Think of it as upgrading from a magnifying glass to a full analysis toolkit.

## Refining Your View: Advanced Display Filters & Finding Packets

![image.png](attachment:d91832cb-bcee-4a24-be04-548c22748011:image.png)

Simple filters are often just the starting point.

- **Combining Conditions:** Use logical operators:
    - `&&` (or `and`): Matches packets meeting **both** conditions (e.g., `ip.src == 192.168.1.50 && tcp.dstport == 80`).
    - `||` (or `or`): Matches packets meeting **either** condition (e.g., `udp.port == 53 || tcp.port == 53`).
    - `!` (or `not`): Excludes packets matching a condition. Use parentheses `()` for clarity, especially with `!`: `ip.addr == 192.168.1.1 && !(tcp.port == 22)`.
- **Using Comparisons:** Go beyond simple equality (`==`) with operators like `!=` (Not equal), `>` (Greater than), `<`(Less than), `>=` (Greater than or equal to), `<=` (Less than or equal to).
    - Example: `frame.len > 1000` shows packets larger than 1000 bytes. `tcp.flags.reset == 1` finds TCP Reset packets.
- **Filtering on Specific Fields:** Target any dissected field identified by Wireshark (e.g., `http.request.method == "POST"`, `dns.flags.rcode != 0` for DNS errors). Use the right-click -> "Apply as Filter" option in the Packet Details pane to easily learn the syntax for a field you're interested in.

**Finding Specific Packets:** Sometimes filtering isn't enough, or you want to quickly jump to a specific piece of data. Use the "Find Packet" feature (`Edit > Find Packet...` or `Cmd+F`). This lets you search through the currently displayed packets for:

- A specific **Display filter** expression.
- A **Hex value** (searching the raw byte data).
- A **String** (searching the raw byte data, case-sensitive or insensitive). This is excellent for finding specific usernames, error messages, filenames, or other text data within packets.

### Try it yourself

Open Wireshark. Type a combined filter into the display filter bar, like `ip.addr == 8.8.8.8 || ip.addr == 1.1.1.1`. Notice the bar stays green if the syntax is correct. Load a capture file if you have one, or capture some traffic. Use `Cmd+F` to search for a string you expect might be in the traffic (e.g., "google" if you visited [google.com](http://google.com), or "GET" for HTTP traffic).

## Reconstructing Conversations: Following Protocol Streams

![image.png](attachment:b827c7c4-0c4c-4772-a615-b2467439f503:image.png)

Network applications communicate via streams of data, often broken into many small packets. Trying to read a web page or understand a file transfer by looking at individual packets is impractical.

Wireshark's "Follow Stream" feature reconstructs the application-level data for specific conversations. **How to access it:** Right-click a packet belonging to a TCP, UDP, HTTP, or TLS/SSL conversation -> `Follow > [Protocol] Stream`. This opens a new window showing the reassembled data flow, such as the complete HTTP requests and responses between a client and server. It's essential for understanding what was actually communicated at the application layer.

## Summarizing Traffic: Wireshark Statistics

![image.png](attachment:89c9a5e6-ab99-4793-8bd2-b051dea06190:image.png)

Before diving into individual packets, or after filtering down the traffic, get a high-level overview using the **Statistics** menu:

- **Endpoints:** Lists all unique devices (MACs, IPs, TCP/UDP ports) involved and their traffic volume. (`Statistics > Endpoints`) Answers: _Who_ was communicating?
- **Conversations:** Shows communication _between pairs_ of endpoints, with details like packet/byte counts per direction and duration. (`Statistics > Conversations`) Answers: _Who talked to whom, and how much?_
- **Protocol Hierarchy:** Displays the distribution of different protocols in the capture, organized by layers, showing packet and byte percentages. (`Statistics > Protocol Hierarchy`) Answers: _What kind of traffic is present? Is anything unusual?_
- **IO Graphs:** Visualizes traffic rates (packets/sec, bytes/sec) over time. You can graph overall traffic or apply display filters to focus on specific types. (`Statistics > IO Graphs`) Answers: _When did traffic peaks occur?_

### Think about it

You are investigating slow network performance. Which two statistical tools would likely be most useful initially to identify potential bottlenecks or bandwidth hogs? Why?

## Extracting Information: Exporting Objects

![image.png](attachment:c4ea0734-833f-4269-93ad-0f2fc00bd7e0:image.png)

Sometimes, files are transferred directly within the network traffic (e.g., images on a webpage, files downloaded via HTTP, files transferred over SMB). Wireshark can often identify and extract these objects.

**Example: HTTP Objects:** For unencrypted HTTP traffic:

1. Go to `File > Export Objects > HTTP...`
2. A window lists detected objects (images, HTML files, scripts, etc.).
3. Select objects and click "Save As..." to extract them.

This is invaluable for security analysis (extracting malware payloads or exfiltrated data) or simply understanding what files were transferred. Similar options exist for other protocols (like SMB) under the `File > Export Objects` menu.

## Finding Practice Files: Sample Captures

The best way to master Wireshark is to practice on diverse traffic. While you can capture your own traffic, exploring pre-made capture files exposes you to protocols and scenarios you might not encounter locally.

The Wireshark Wiki maintains a page dedicated to **Sample Captures**: [https://wiki.wireshark.org/SampleCaptures](https://wiki.wireshark.org/SampleCaptures)

This page contains a large collection of `.pcap` or `.pcapng` files demonstrating various protocols (from common ones like DNS, DHCP, HTTP, SMB to more obscure or specialized ones), network problems, and even security-related traffic captures (like malware communication).

**Recommendation:** Visit this page. Find a capture file related to a protocol you're curious about (perhaps HTTP, DNS, or ARP) or a scenario (like a basic web browse). Download it and open it in Wireshark. Try applying the filtering, stream following, and statistical techniques discussed here.

### Try it yourself

Go to the Sample Captures wiki page linked above. Browse the sections. Download one or two captures that look interesting (e.g., `http.cap`, `dns.pcap`, or one from the `malware-traffic-analysis.net` section if you're feeling adventurous). Open them in Wireshark and just explore!

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Networking-4-Advanced-Wireshark-7e2bdlzzfy3gm3i?mode=doc](https://gamma.app/docs/Networking-4-Advanced-Wireshark-7e2bdlzzfy3gm3i?mode=doc)

Try not to peek before class - spoilers inside!

</aside>