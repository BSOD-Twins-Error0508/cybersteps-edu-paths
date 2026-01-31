Welcome! Before our live session on the Hypertext Transfer Protocol (HTTP), please go through this material. We'll explore how your browser requests web pages and how web servers respond. Understanding HTTP is fundamental to understanding how the web works.

## What is the Application Layer?

In our 5-layer network model (Physical, Datalink, Network, Transport, Application), the Application Layer is at the top. It's the layer where network applications, the software you interact with directly, create and interpret data. Think of web browsers, email clients, or file transfer programs. These applications need rules, or **protocols**, to communicate effectively across the network. HTTP is one of the most important application layer protocols – it's the foundation of the World Wide Web.

## Introducing HTTP: The Language of the Web

HTTP stands for **Hypertext Transfer Protocol**. At its core, it's a set of rules that defines how web clients (like your browser) request information from web servers, and how those servers respond. It's a text-based protocol, meaning the messages exchanged are human-readable text, although often quite structured.

Key characteristics of HTTP:

1. **Client-Server Model:** HTTP operates based on a request-response cycle between a client and a server.
    
    - **Client:** The entity initiating the request. Usually, this is your web browser (Chrome, Firefox, Safari, Edge), but it can also be other software like command-line tools (`curl`) or scripts.
    - **Server:** The entity hosting the resource (like a web page, image, or data) and responding to the client's request. Examples include Apache, Nginx, or Microsoft IIS web server software running on powerful computers somewhere on the internet.
2. **Resources and URLs:** HTTP is used to access **resources** on the web. A resource is anything that can be identified by a **Uniform Resource Locator (URL)**. This could be an HTML document, a CSS stylesheet, a JavaScript file, an image, a video, or data from an API.
    
    - A URL typically looks like this: `http://www.example.com/path/to/resource?query=value#fragment`
        - `http://`: The **scheme** (protocol). `https://` indicates HTTP secured with encryption (more on this later).
            
        - `www.example.com`: The **host** or domain name, which resolves to an IP address via DNS (Domain Name System).
            
        - `/path/to/resource`: The **path** specifying the location of the resource on the server.
            
        - `?query=value`: An optional **query string** used to pass parameters to the server.
            
        - `#fragment`: An optional **fragment identifier**, processed by the client (browser) to navigate within the resource (e.g., jump to a section of a page).
            
            ![fetching-a-page.svg](attachment:805d16d9-d670-4d72-87c3-d12c91dfecff:fetching-a-page.svg)
            
3. **Statelessness:** This is a crucial concept. Each HTTP request from a client to a server is treated independently. The server does not store any information about previous requests from the same client by default. If state (like knowing who is logged in) is needed, it's usually managed using other mechanisms like cookies or session data, which are built on top of HTTP.
    

## The HTTP Request-Response Cycle

![image.png](attachment:e35ee159-0a2f-45dd-8912-4ac43bdbd2aa:image.png)

1. **Client Sends Request:** Your browser (the client) wants to fetch `http://www.example.com/index.html`. It constructs an HTTP request message and sends it to the server located at `www.example.com` (using the IP address obtained via DNS) over the transport layer (usually TCP on port 80 for HTTP, or port 443 for HTTPS).
2. **Server Processes Request:** The web server receives the request, identifies the requested resource (`/index.html`), processes any parameters, and determines the appropriate action.
3. **Server Sends Response:** The server constructs an HTTP response message, including the requested resource (if found and accessible) or an error message, and sends it back to the client.
4. **Client Receives Response:** Your browser receives the response, interprets it (e.g., renders the HTML), and displays the result. If the HTML page references other resources (images, CSS, JavaScript), the browser will initiate separate HTTP requests for each of those.

## Anatomy of an HTTP Message

![http-request.svg](attachment:217a9c32-32b5-4bea-bc19-eb9a498efba3:http-request.svg)

![http-response.svg](attachment:e608617c-7d4d-4bd7-9d0d-0b595bc67ff5:http-response.svg)

_HTTP Request vs HTTP Response_

Both requests and responses have a similar structure:

1. **Start Line:**
    - **Request Line:** Contains the HTTP Method, the Request Target (usually the path from the URL), and the HTTP Version. Example: `GET /index.html HTTP/1.1`
    - **Status Line:** Contains the HTTP Version, a Status Code, and a Reason Phrase. Example: `HTTP/1.1 200 OK`
2. **Headers:** Zero or more lines providing metadata about the request or response. Each header is a name-value pair, separated by a colon. Examples:
    - `Host: www.example.com` (Required in HTTP/1.1 requests)
    - `User-Agent: Mozilla/5.0 ...` (Identifies the client software)
    - `Accept: text/html` (Tells the server what kind of content the client prefers)
    - `Content-Type: text/html; charset=UTF-8` (In a response, tells the client the type of the content in the body)
    - `Content-Length: 1234` (Specifies the size of the message body in bytes)
3. **Empty Line:** A single blank line (CRLF - Carriage Return Line Feed) separates the headers from the message body.
4. **Message Body (Optional):** Contains the actual data being transferred.
    - In a request (like a POST request), this might be form data or JSON data.
    - In a response, this is often the HTML content, image data, etc. GET requests typically don't have a body.

### HTTP Methods (Verbs)

The HTTP method indicates the desired action to be performed on the resource. Common methods include:

- **`GET`:** Requests a representation of the specified resource. This is the most common method, used when you click a link or type a URL in your browser. GET requests should only retrieve data and have no other effect (they are _idempotent_ and _safe_).
- **`POST`:** Submits data to be processed to the specified resource (e.g., submitting a web form, uploading a file, sending JSON data to an API). POST requests often result in a change in state on the server.
- **`PUT`:** Replaces the current representation of the target resource with the request payload.
- **`DELETE`:** Deletes the specified resource.
- **`HEAD`:** Similar to GET, but asks for the response headers only, without the message body. Useful for checking if a resource exists or getting its metadata without downloading it.
- **`OPTIONS`:** Requests information about the communication options available for the target resource (e.g., which methods are supported).
- **`PATCH`:** Applies partial modifications to a resource.

### HTTP Status Codes

The status code in the response indicates the outcome of the request. They are grouped into categories:

- **`1xx` (Informational):** Request received, continuing process. (Rarely seen by users)
- **`2xx` (Successful):** The action was successfully received, understood, and accepted.
    - `200 OK`: Standard success response.
    - `201 Created`: The request has been fulfilled and resulted in a new resource being created.
    - `204 No Content`: The server successfully processed the request but is not returning any content.
- **`3xx` (Redirection):** Further action needs to be taken by the client to complete the request.
    - `301 Moved Permanently`: The requested resource has been permanently moved to a new URL (given in the `Location` header).
    - `302 Found` (or `307 Temporary Redirect`): The resource is temporarily at a different URL.
- **`4xx` (Client Error):** The request contains bad syntax or cannot be fulfilled.
    - `400 Bad Request`: The server could not understand the request due to invalid syntax.
    - `401 Unauthorized`: Authentication is required and has failed or has not yet been provided.
    - `403 Forbidden`: The server understood the request, but refuses to authorize it. You don't have permission.
    - `404 Not Found`: The server cannot find the requested resource. This is one of the most famous codes!
- **`5xx` (Server Error):** The server failed to fulfill an apparently valid request.
    - `500 Internal Server Error`: A generic error message, given when an unexpected condition was encountered.
    - `503 Service Unavailable`: The server is not ready to handle the request (e.g., down for maintenance or overloaded).

### Think about it

Why is it useful to have different methods like GET and POST? Why not just use GET for everything and put data in the URL?

### Try it yourself

Most modern web browsers have built-in "Developer Tools" that let you inspect network traffic.

1. Open your web browser (Chrome or Firefox recommended).
2. Right-click anywhere on a web page (like [google.com](http://google.com)) and select "Inspect" or "Inspect Element".
3. Find and click on the "Network" tab in the developer tools panel.
4. Make sure recording is enabled (usually a red or grey circle icon). You might need to refresh the page (Cmd+R or F5).
5. You'll see a list of requests made by the browser to load the page. Click on the first request (usually the main HTML document).
6. Look at the "Headers" section for that request. Can you identify the Request Method (e.g., GET)? The Status Code (e.g., 200)? The `User-Agent` header? The `Content-Type` header in the _response_ headers?

Don't worry about understanding everything you see yet. The goal is just to get familiar with where to find this information.

## HTTP vs. HTTPS

You've likely seen `https://` in URLs more often than `http://`. HTTPS stands for **HTTP Secure**. It's essentially the standard HTTP protocol layered on top of an encryption layer, usually TLS (Transport Layer Security) or its predecessor SSL (Secure Sockets Layer).

- **HTTP:** Transmits data in plain text. Anyone intercepting the traffic (e.g., on the same Wi-Fi network) can read it.
- **HTTPS:** Encrypts the data exchanged between the client and server. This provides:
    - **Confidentiality:** Protects against eavesdropping.
    - **Integrity:** Ensures the data hasn't been tampered with during transit.
    - **Authentication:** Often involves verifying the server's identity using digital certificates, helping prevent "man-in-the-middle" attacks.

For security reasons, especially when sensitive data like passwords or credit card numbers are involved, HTTPS is essential and is now standard practice for almost all websites. We'll delve deeper into encryption and certificates in later modules. For now, understand that HTTPS is HTTP with a crucial security layer added via the Transport Layer.

That concludes the pre-class reading on HTTP basics. We'll explore these concepts further with live demonstrations in our session!

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Networking-5-Application-Layer-HTTP-07k96b3eps4k76r?mode=doc](https://gamma.app/docs/Networking-5-Application-Layer-HTTP-07k96b3eps4k76r?mode=doc)

Try not to peek before class - spoilers inside!

</aside>