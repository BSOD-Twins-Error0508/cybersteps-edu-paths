Welcome to your first step into the world of web development! This preparation material will introduce you to the fundamental concepts of how websites are built and displayed. Understanding these basics is crucial as you embark on your cybersecurity journey, as web technologies are integral to many aspects of the digital world.

## The World Wide Web and Websites

![image.png](attachment:ca91db11-fad8-491f-80fc-830784f400b1:image.png)

_On August 6, 1991, [the first website](https://info.cern.ch/hypertext/WWW/TheProject.html) was introduced to the world._

Often, "Internet" and "World Wide Web" (or "the web") are used interchangeably, but they are not the same thing. The **Internet** is the global network of computers, the infrastructure that allows information to travel. The **World Wide Web**, on the other hand, is one of the many services that run on the Internet. It's a system of interlinked hypertext documents accessed via the Internet. Think of the Internet as the roads and the web as the system of addresses and destinations you can reach using those roads.

A **web page** is a single document, typically written in HTML, that can be displayed in a web browser. A **website** is a collection of related web pages, images, videos, or other digital assets that are hosted on at least one web server, usually accessible via the Internet.

Websites can be broadly categorized:

- **Static websites:** These consist of fixed content. Each page is coded in HTML and displays the same information to every visitor. They are simpler to create and host.
- **Dynamic websites:** These can display different content and provide user interaction. The content can be generated on-the-fly based on user actions, database information, or other parameters. Think of social media sites, e-commerce stores, or news portals. For now, we'll focus on the building blocks that underpin both.

## How the Web Works: Browsers and Servers

When you visit a website, a few key components work together:

- **Web Browser:** This is the software on your computer or mobile device that you use to access the web (e.g., Google Chrome, Apple Safari, Mozilla Firefox). Its main job is to fetch web pages from servers and display them to you.
- **Web Server:** This is a computer (or a program running on a computer) that stores website files (HTML documents, CSS stylesheets, images, etc.) and makes them available to browsers upon request.

This interaction is based on the **client-server model**:

1. You (the user) type a web address (URL, like `http://www.example.com`) into your browser or click a link.
2. Your browser (the **client**) sends an HTTP (HyperText Transfer Protocol) request to the web server that hosts the website. This request asks for the specific web page.
3. The web **server** processes the request. If the requested page exists and is accessible, the server sends the page's files (primarily HTML, CSS, and JavaScript) back to the browser as an HTTP response.
4. Your browser receives these files, interprets them, and **renders** (draws) the web page on your screen.

![0a1ab2c1-66a0-4d17-84f5-dc3e507343b5.png](attachment:3afb43ec-e38f-4306-84f2-4e97090999e3:0a1ab2c1-66a0-4d17-84f5-dc3e507343b5.png)

## Introduction to HTML: Structuring the Web

**HTML** stands for **HyperText Markup Language**. It's the standard markup language used to create web pages. "Markup language" means it uses tags to define the structure and content of a document. HTML tells the browser what each part of the page is—a heading, a paragraph, an image, a link, etc.

### Core HTML Components

- **Tags:** These are keywords surrounded by angle brackets, like `<p>`. Tags usually come in pairs: an opening tag (e.g., `<h1>`) and a closing tag (e.g., `</h1>`). The closing tag has a forward slash before the tag name.
- **Elements:** An element consists of an opening tag, some content, and a closing tag. For example: `<p>This is a paragraph.</p>`. Here, `<p>` is the opening tag, "This is a paragraph." is the content, and `</p>` is the closing tag. Some elements are "empty" or "void," meaning they don't have content or a closing tag in the traditional sense (e.g., `<img>` for images, `<br>` for line breaks).
- **Attributes:** These provide additional information about an HTML element and are always specified in the opening tag. Attributes come in name/value pairs like `name="value"`. For example, in `<a href="<https://www.example.com>">Visit Example</a>`, `href` is an attribute of the `<a>` (anchor/link) tag, and its value is the URL.

### Basic HTML Document Structure

A typical HTML document has a fundamental structure:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Page Title</title>
</head>
<body>
    <h1>My First Heading</h1>
    <p>My first paragraph. This is where the main content of the page goes.</p>
</body>
</html>
```

Let's break this down:

- `<!DOCTYPE html>`: This declaration defines the document type to be HTML5. It's important for browsers to render the page correctly.
- `<html>`: This is the root element of an HTML page. All other elements go inside it.
- `<head>`: This element contains meta-information about the HTML document, which is not displayed on the page itself. This includes things like the page title, character set, links to CSS files, etc.
    - `<meta charset="UTF-8">`: Specifies the character encoding for the document, UTF-8 is standard and supports a wide range of characters.
    - `<meta name="viewport" content="width=device-width, initial-scale=1.0">`: Configures the viewport for responsive web design, making the site adapt to different screen sizes (like mobile phones).
    - `<title>`: Sets the title of the web page, which appears in the browser tab or window title bar.
- `<body>`: This element contains the visible page content—all the headings, paragraphs, images, links, etc., that the user sees in the browser.

### Common HTML Tags

Here are a few common HTML tags you'll encounter:

- `<h1>` to `<h6>`: Heading tags. `<h1>` is the most important heading, `<h6>` is the least.
- `<p>`: Paragraph tag, for blocks of text.
- `<a>`: Anchor tag, for creating hyperlinks. The `href` attribute specifies the link's destination. Example: `<a href="<https://www.google.com>">Go to Google</a>`
- `<img>`: Image tag, for embedding images. The `src` attribute specifies the path to the image, and the `alt` attribute provides alternative text if the image cannot be displayed. Example: `<img src="image.jpg" alt="A descriptive text for the image">`
- `<div>`: Division tag. A generic container used to group other elements for styling or layout purposes.
- `<span>`: Span tag. An inline container used to group text or other inline elements, often for styling a small piece of content within a larger block.

### Try it yourself: Explore a Website's HTML

1. Visit one of your favorite websites.
2. Right-click anywhere on the page (not on an image or link, just on some text or background).
3. In the context menu that appears, look for an option like "View Page Source," "Inspect," or "Inspect Element." The exact wording might vary slightly depending on your browser (e.g., Chrome, Safari, Firefox).
    - **View Page Source:** This will typically open a new tab showing the raw HTML code of the page.
    - **Inspect / Inspect Element:** This will usually open a developer tools panel within the same browser window, often showing the HTML structure in a hierarchical way and allowing you to see CSS styles as well.
4. Take a look at the HTML. Can you spot `<h1>`, `<p>`, `<a>`, or `<img>` tags? Don't worry about understanding everything; just try to see how the text and elements you see on the rendered page correspond to the tags in the source code. This is a fundamental skill for web development and cybersecurity (e.g., understanding how a phishing page is constructed).

## Introduction to CSS: Styling the Web

**CSS** stands for **Cascading Style Sheets**. While HTML provides the structure and content, CSS is responsible for the presentation and appearance of the web page. It controls aspects like colors, fonts, spacing, layout, and even animations.

The key principle here is **separation of concerns**: HTML is for what the content _is_ (its meaning and structure), and CSS is for how the content _looks_ (its visual presentation). This makes your code cleaner, easier to maintain, and more flexible.

### Basic CSS Syntax

A CSS rule consists of two main parts:

- **Selector:** This defines which HTML element(s) the rule applies to. Selectors can target elements by their tag name (e.g., `p`), class name (e.g., `.my-class`), ID (e.g., `#my-id`), and more.
- **Declaration Block:** This is enclosed in curly braces `{}` and contains one or more declarations, separated by semicolons.
    - Each **declaration** includes a CSS **property** and a **value**, separated by a colon.
    - Example: `color: blue;` (property: `color`, value: `blue`)

Here's a complete CSS rule:

```css
p {
  color: navy;
  font-size: 16px;
}
```

This rule selects all `<p>` (paragraph) elements on the page and styles them to have navy blue text and a font size of 16 pixels.

### How to Include CSS

There are three main ways to add CSS to an HTML document:

1. **External CSS (Recommended):** You write your CSS rules in a separate file with a `.css` extension (e.g., `styles.css`). Then, you link this file to your HTML document using the `<link>` tag inside the `<head>` section:
    
    ```css
    <head>
        <title>My Styled Page</title>
        <link rel="stylesheet" href="styles.css">
    </head>
    ```
    
    This is the most common and preferred method because it keeps your styles separate from your HTML, making them easier to manage and reuse across multiple pages.
    
2. **Internal CSS:** You can embed CSS rules directly within the HTML document by placing them inside `<style>`tags, also within the `<head>` section:
    
    ```css
    <head>
        <title>My Internally Styled Page</title>
        <style>
            body {
                background-color: lightyellow;
            }
            h1 {
                color: green;
            }
        </style>
    </head>
    ```
    
    This can be useful for single-page websites or for page-specific styles, but for larger sites, external stylesheets are better.
    
3. **Inline CSS (Generally Avoid):** You can apply styles directly to an individual HTML element using the `style`attribute:
    
    ```css
    <p style="color: red; font-weight: bold;">This paragraph is styled inline.</p>
    ```
    
    While this works, it's generally discouraged because it mixes presentation with structure, making the HTML harder to read and maintain. It also has higher specificity, which can make it harder to override with external or internal styles.
    

## HTML and CSS Working Together

HTML and CSS are designed to work in tandem. HTML structures the content, and CSS tells the browser how to display that structured content. The browser reads the HTML to understand the elements on the page and then applies the CSS rules that match those elements.

For example, if your HTML has: `<h1>Welcome!</h1>`

And your linked CSS file has: `h1 { color: teal; text-align: center; }`

The browser will display the "Welcome!" heading in a teal color and centered on the page.

### Try it yourself: Create and Style Your First Web Page

**1. Set Up Your Workspace and Files:**

- Create a new folder on your computer (e.g., in Documents or Desktop) named `web1_intro_project`.
- Open VS Code, then open the `web1_intro_project` folder (File > Open Folder...).
- Inside this folder in VS Code, create two new files:
    - `index.html`
    - `style.css` Your folder should look like this:

```
web1_intro_project/
├── index.html
└── style.css
```

**2. Basic HTML Page:**

- Open your `index.html` file in VS Code.
- Type (or copy and paste) the basic HTML document structure provided earlier into this file.
- Change the `<title>` to "My First Web Page".
- Inside the `<body>`, add an `<h1>` element with the text "Hello World!"
- Add a `<p>` element below the `<h1>` with the text "I am learning HTML and CSS."
- Save the file (File > Save, or Cmd+S).
- To view your page, find the `index.html` file in your Finder, right-click it, and choose "Open With" your preferred web browser (e.g., Chrome, Safari). You should see your heading and paragraph.

**3. Link CSS and Add a Simple Style:**

- In your `index.html` file, inside the `<head>` section (e.g., below the `<title>` tag), add the following line to link your `style.css` file:
    
    ```html
    <link rel="stylesheet" href="style.css">
    ```
    
- Save the `index.html` file.
    
- Now, open your `style.css` file in VS Code.
    
- Add the following CSS rule to change the color of all `<h1>` elements to `dodgerblue`:
    
    ```css
    h1 {
        color: dodgerblue;
    }
    ```
    
- Add another rule to change the background color of the `<body>` to `#f0f0f0` (a light gray):
    
    ```css
    body {
        background-color: #f0f0f0;
    }
    ```
    
- Save the `style.css` file.
    
- Go back to your web browser where `index.html` is open and refresh the page (usually Cmd+R or the refresh button).
    
- Did your "Hello World!" heading change color? Did the page background change? If so, congratulations! You've successfully created and styled your first web page.
    

### Think about it

Why do you think separating HTML (structure) from CSS (style) is considered a good practice in web development? What problems might arise if all styling was done directly inside HTML tags?

This preparation should give you a solid foundation for our upcoming class. Don't worry if not everything is crystal clear yet; we'll review these concepts and build upon them in the live session. The most important thing is to get a feel for what HTML and CSS are and how they begin to interact.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Web-1-Intro-to-Web-HTML-CSS-cvnbc5utv9zgipv?mode=doc](https://gamma.app/docs/Web-1-Intro-to-Web-HTML-CSS-cvnbc5utv9zgipv?mode=doc)

Try not to peek before class - spoilers inside!

</aside>