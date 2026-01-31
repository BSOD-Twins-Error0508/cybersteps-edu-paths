Welcome! In this session, we'll explore how websites remember you and your preferences.

## The Stateless Web and the Need for State

You've learned that HTTP (Hypertext Transfer Protocol) is the foundation of data communication for the World Wide Web. One of its core characteristics is that it's a **stateless protocol**. This means each request from a client (your browser) to a server is treated as an independent transaction. The server doesn't inherently remember anything about previous requests

This is where the concept of **state management** comes in. Web applications often need to "remember" information about users and their interactions across multiple requests or visits. This "memory" is what we refer to as state. Without it, every time you clicked a link or loaded a new page on a site, it would be like visiting for the very first time.

Common scenarios requiring state management include:

- **User Authentication:** Keeping a user logged in across different pages.
- **Shopping Carts:** Remembering items a user intends to purchase.
- **User Preferences:** Storing settings like language, theme, or personalized content.
- **Tracking User Behavior:** Understanding how users navigate a site (though this has privacy implications).

from the same client.

### Think about it

Which websites don’t need to manage state?

## Introducing Cookies: The Web's Memory

![image.png](attachment:42e3b08b-0e34-484f-89d4-c7173a12c853:image.png)

**Cookies** are one of the most common mechanisms for maintaining state on the web. A cookie is a small piece of data that a server sends to a user's web browser. The browser then stores this data and sends it back to the same server with subsequent requests. This allows the server to "remember" information associated with that browser.

Think of cookies like a cloakroom ticket. When you hand over your coat (information), you get a ticket (cookie). The next time you visit the cloakroom (server), you present your ticket, and they can retrieve your specific coat.

## How Cookies Work: A Two-Way Conversation

![image.png](attachment:648af936-80c6-4ee6-86c0-f15b75ca5bf7:image.png)

The process of using cookies involves a few steps:

1. **Initial Request:** Your browser makes a request to a web server (e.g., visiting a website for the first time).
2. **Server Response with `Set-Cookie` Header:** If the server wants to store a cookie on your browser, it includes a `Set-Cookie` header in its HTTP response. This header contains the name and value of the cookie, along with other attributes that control its behavior. _Example `Set-Cookie` header:_ `Set-Cookie: userID=12345; Expires=Wed, 21 Oct 2025 07:28:00 GMT`
3. **Browser Stores the Cookie:** Your browser receives the response and stores the cookie, associating it with the website's domain.
4. **Subsequent Requests with `Cookie` Header:** For every subsequent request your browser makes to the _same server_(or a server within the cookie's specified domain and path), it includes a `Cookie` header containing the names and values of all relevant stored cookies. _Example `Cookie` header:_ `Cookie: userID=12345`
5. **Server Reads the Cookie:** The server receives the request, reads the `Cookie` header, and can use the information (e.g., `userID=12345`) to identify the user, retrieve their session, load their preferences, etc.

This back-and-forth allows the server to link multiple requests from the same browser, effectively creating a "session" or remembering past interactions.

## Dissecting a Cookie: Attributes and Their Meanings

Besides a name and value, cookies can have several attributes that define their behavior and lifecycle:

- **`Expires=<date>` or `Max-Age=<seconds>`:**
    - `Expires`: Specifies a date and time when the cookie will expire. After this date, the browser will delete the cookie.
    - `Max-Age`: Specifies the lifetime of the cookie in seconds from the time it's set. If both `Expires` and `Max-Age`are set, `Max-Age` takes precedence.
    - If neither is set, the cookie is a **session cookie** and will be deleted when the browser session ends (i.e., when the browser is closed).
- **`Domain=<domain-name>`:**
    - Specifies the domain for which the cookie is valid. If set, the cookie will be sent to that domain and its subdomains. For example, if `Domain=example.com`, the cookie would be sent to `www.example.com` and `api.example.com`.
    - If not set, it defaults to the host of the document that set the cookie (but not its subdomains).
- **`Path=<path>`:**
    - Specifies the URL path for which the cookie is valid. If set to `/`, the cookie is valid for all paths within the domain. If set to `/profile/`, it's only valid for requests to `/profile/` and its subdirectories.
- **`Secure`:**
    - If this attribute is present, the cookie will only be transmitted over encrypted HTTPS connections. It will not be sent over unencrypted HTTP. This is crucial for protecting sensitive information in cookies.
- **`HttpOnly`:**
    - If this attribute is present, the cookie cannot be accessed by client-side JavaScript (e.g., using `document.cookie`). This is an important security measure that helps mitigate Cross-Site Scripting (XSS) attacks, where an attacker might try to steal cookies using malicious scripts.
- **`SameSite=<Strict|Lax|None>`:**
    - This attribute helps protect against Cross-Site Request Forgery (CSRF) attacks. It controls whether a cookie is sent with requests initiated from third-party websites.
        - **`Strict`**: The cookie will only be sent with requests originating from the same site that set the cookie.
        - **`Lax`**: The cookie is sent with same-site requests and with top-level navigations (e.g., clicking a link to the target site from an external site). This is the default in many modern browsers.
        - **`None`**: The cookie will be sent with all requests, both same-site and cross-site. If `SameSite=None` is used, the `Secure` attribute _must_ also be set (i.e., the cookie must be sent over HTTPS).

## Managing Cookies: Session vs. Persistent

Based on their lifespan, cookies can be broadly categorized into two types:

- **Session Cookies:**
    - These cookies do not have an `Expires` or `Max-Age` attribute.
    - They are temporary and are stored in the browser's memory only for the duration of the current browsing session.
    - When the user closes their browser, session cookies are automatically deleted.
    - Often used for things like temporarily storing shopping cart contents or maintaining a logged-in state for the current visit.
- **Persistent Cookies:**
    - These cookies have an `Expires` or `Max-Age` attribute set to some point in the future.
    - They are stored on the user's hard drive and survive browser restarts.
    - They remain valid until their expiration date is reached or they are manually deleted by the user.
    - Used for remembering user preferences, login details (e.g., "Remember Me" functionality), or tracking user behavior across multiple sessions.

### Think about it

When might a website choose to use a session cookie over a persistent cookie, and vice-versa? What are the trade-offs?

## Peeking into the Cookie Jar: Using Browser Developer Tools

Modern web browsers provide developer tools that allow you to inspect cookies stored for a particular website. This is incredibly useful for understanding how a site uses cookies and for debugging web applications.

### Try it yourself

1. Open your web browser (e.g., Chrome or Firefox).
2. Visit a few different websites (e.g., a news site, an e-commerce site, a social media site).
3. Open the browser's developer tools:
    - Usually by right-clicking on the page and selecting "Inspect" or "Inspect Element".
    - Alternatively, press `F12` (Windows/Linux) or `Cmd+Opt+I` (Mac).
4. Find the "Application" tab (in Chrome) or "Storage" tab (in Firefox).
5. In the left-hand panel, look for "Cookies" under the "Storage" or "Application" section. Expand it to see the cookies associated with the current domain.
6. Click on a domain to see the list of cookies. You'll see their names, values, domain, path, expiration dates, and other attributes like `HttpOnly`, `Secure`, and `SameSite`.
7. Also, explore the "Network" tab in the developer tools. When you load a page or interact with it, look at the HTTP requests and responses. You can often find `Set-Cookie` headers in responses from the server and `Cookie` headers in requests sent by your browser.

Observe the different types of information stored in cookies. Do you see any session IDs? Any user preferences?

## Cookies and Security: A Double-Edged Sword

While cookies are essential for modern web functionality, they also introduce potential security risks if not handled carefully.

- **Session Hijacking:** If an attacker manages to steal a user's session cookie (which often contains a session ID), they can potentially impersonate that user and gain unauthorized access to their account. This is why `Secure` and `HttpOnly` attributes are important.
- **Cross-Site Scripting (XSS):** If a website is vulnerable to XSS, an attacker might inject malicious JavaScript code that steals cookies. If a cookie is not `HttpOnly`, JavaScript can access it. The stolen cookie (especially a session cookie) can then be used for session hijacking.
- **Cross-Site Request Forgery (CSRF):** In a CSRF attack, an attacker tricks a logged-in user into unknowingly submitting a malicious request to a website where they are authenticated. Cookies are sent automatically with requests to their originating domain, so the malicious request would appear legitimate. The `SameSite` attribute is a key defense against CSRF.
- **Tracking:** Cookies, especially third-party cookies (set by a domain different from the one the user is currently visiting, often from ads or tracking scripts), can be used to track users' browsing habits across multiple websites. This raises privacy concerns and has led to browsers implementing stricter controls over third-party cookies.

Developers must be mindful of these risks and implement cookies securely, using attributes like `HttpOnly`, `Secure`, and `SameSite` appropriately.

## Beyond Cookies: Server-Side Sessions

![image.png](attachment:587a12bc-a6cb-4d7f-8d94-e278bcb3a079:image.png)

While cookies are great for storing small amounts of data or identifiers on the client-side, storing large amounts of sensitive information directly in cookies is generally not recommended. An alternative and often complementary approach is **server-side sessions**.

Here's the basic idea:

1. When a user starts a session (e.g., logs in), the server creates a unique **session ID**.
2. The server stores the actual session data (e.g., user details, shopping cart contents) on the server itself, associated with this unique session ID. This data can be stored in memory, a database, or a dedicated session store.
3. The server sends _only_ the session ID back to the client, typically stored in a cookie (a session cookie is perfect for this).
4. On subsequent requests, the client sends the session ID cookie back to the server.
5. The server uses this ID to look up the corresponding session data stored on its side.

**Advantages of server-side sessions:**

- **Security:** Sensitive data is kept on the server, not transmitted back and forth or stored on the client's machine (beyond the session ID). This reduces the risk if a cookie is compromised.
- **Data Capacity:** Servers can store much more session data than what can be practically stored in cookies (which have size limits).

Often, cookies and server-side sessions work together. The cookie on the client acts as the key (the session ID) to unlock the data stored on the server.

This concludes your pre-class preparation on cookies and state. Take some time to digest this information, and come prepared with any questions for our live session!

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Web-4-Cookies-State-br5d06kz2lx3k5s?mode=doc](https://gamma.app/docs/Web-4-Cookies-State-br5d06kz2lx3k5s?mode=doc)

Try not to peek before class - spoilers inside!

</aside>