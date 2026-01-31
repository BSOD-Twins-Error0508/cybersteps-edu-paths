Welcome to the world of server-side web development! So far, you've learned about what happens in a web browser (the client-side) using HTML, CSS, and JavaScript. Now, we'll explore what happens on the _server_ – the powerful machine that responds to your browser's requests and makes the web dynamic and interactive. In this lesson, we'll focus on Flask, a popular Python framework for building web applications.

## Client-Side vs. Server-Side

![38eacaa3-9cdb-4780-abcd-daed10c5dd6b.png](attachment:846bc945-a4a3-4928-993d-1068f1a00ba2:38eacaa3-9cdb-4780-abcd-daed10c5dd6b.png)

Think of a restaurant. The **client-side** is like the dining area and the menu you see. It's what you, the customer (or user), interact with directly. Your web browser renders HTML (the structure of the menu), CSS (how the menu looks), and JavaScript (any interactive elements on the menu, like a button to show daily specials).

The **server-side** is like the kitchen of the restaurant. It's hidden from you, but it's where all the important work happens:

- **Receiving Orders (Requests):** The kitchen receives an order from a waiter (your browser sending an HTTP request).
- **Preparing Food (Processing Logic):** Chefs (server-side code) use ingredients (data) and recipes (algorithms) to prepare your meal. This could involve looking up information in a database (like checking if an item is in stock), performing calculations, or making decisions based on your order.
- **Sending Out the Meal (Responses):** Once the meal is ready, it's sent back to your table (the server sends an HTTP response, often containing HTML, back to your browser).

**Key Differences:**

- **Execution Location:** Client-side code (HTML, CSS, JavaScript) runs in the user's web browser. Server-side code (e.g., Python with Flask) runs on a web server.
- **Access to Resources:** Server-side code can access resources that client-side code cannot, such as databases, file systems on the server, and other server-side services. This is crucial for security and data management.
- **Dynamic Content Generation:** While JavaScript can manipulate a page after it's loaded, server-side code is often responsible for generating the initial HTML content dynamically, tailoring it to the specific user or request. For example, showing your username after you log in, or displaying search results.

### Think about it

What are some tasks that _must_ happen on a server and cannot be done securely or efficiently in a user's browser?

## What is a Web Framework?

Imagine building a complex application like a social media site or an online store from scratch using only basic Python. You'd have to handle raw HTTP requests, manage URLs, structure your code in a maintainable way, connect to databases, ensure security, and much more. It would be a monumental task!

A **web framework** is a collection of tools, libraries, and conventions that simplifies the process of building web applications. It provides a structured way to develop web apps, handling many of an application's common, repetitive tasks, allowing developers to focus on the unique features of their application.

**Why use a web framework?**

- **Productivity:** Frameworks provide ready-made components for common tasks (like routing URLs or handling forms), speeding up development.
- **Organization:** They enforce a certain structure, making code more organized and easier for teams to work on.
- **Best Practices:** Good frameworks often incorporate best practices for security, performance, and scalability.
- **Community & Ecosystem:** Popular frameworks have large communities, meaning plenty of documentation, tutorials, and third-party packages.

## Introduction to Flask

![image.png](attachment:b209cce0-f1b1-421c-959e-3a952dfefd19:image.png)

**Flask** is a **micro web framework** written in Python. The term "micro" doesn't mean it's less powerful or can only build small applications. Instead, it means Flask aims to keep its core simple and extensible. It provides the basics for web development, like routing requests, but doesn't make many decisions for you about things like database layers or template engines (though it has excellent defaults and makes them easy to add).

**Key Characteristics of Flask:**

- **Lightweight:** It has a small, easy-to-understand core.
- **Flexible:** You can choose your own tools and libraries for tasks like database interaction or form validation.
- **Extensible:** Flask can be extended with numerous "Flask extensions" that add functionality (e.g., for database integration, user authentication, etc.).
- **Pythonic:** Flask feels natural to Python developers.

**Install Flask:**

- Open your terminal or command prompt.
    
- Install Flask using pip, Python's package installer. Type the following command and press Enter:
    
    ```python
    pip install Flask
    ```
    
    or if you have multiple Python versions or use `python3` command:
    
    ```python
    pip3 install Flask
    ```
    
- To verify Flask is installed, you can try to import it in a Python interpreter:
    
    - Type `python` or `python3` in your terminal to start the interpreter.
    - Then type `import flask` and press Enter.
    - If no errors appear, Flask is installed correctly. You can type `exit()` to leave the Python interpreter.

## Basic Flask Concepts

Let's look at the fundamental building blocks of a Flask application.

### Routing

When your browser sends a request to a URL (e.g., `http://example.com/about`), the web server needs to know which piece of code should handle that request. **Routing** is the mechanism that maps URLs to specific Python functions in your Flask application.

In Flask, you define routes using the `@app.route()` decorator above a function.

```python
from flask import Flask

# Create a Flask application instance
app = Flask(__name__)

# Define a route for the homepage URL ("/")
@app.route('/')
def home():
    return "Hello, this is the homepage!"

# Define a route for "/about"
@app.route('/about')
def about_page():
    return "This is the about page."

# (Code to run the app will go here later)
```

In this example:

- `app = Flask(__name__)` creates an instance of the Flask application. `__name__` is a special Python variable that gets the name of the current module. Flask uses this to locate resources.
- `@app.route('/')` tells Flask that if someone visits the root URL of your site (e.g., `http://127.0.0.1:5000/`), the `home()` function should be executed.
- `@app.route('/about')` tells Flask that visiting `/about` should execute the `about_page()` function.

### View Functions

The functions associated with routes (like `home()` and `about_page()` above) are called **view functions**. Their job is to:

1. Receive and process the incoming request (though in these simple examples, they don't do much processing).
2. Return a response that will be sent back to the client's browser. This response is typically HTML, but it can also be plain text, JSON, or other formats.

For now, our view functions are just returning simple strings. These strings will be displayed directly in the browser.

### Running a Flask Application

To actually run your Flask application and see it in action, you need to add a bit more code to your Python file. This code typically checks if the script is being run directly (as opposed to being imported into another script) and then starts a development web server.

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return "Hello, World! This is Flask."

@app.route('/profile/<username>')
def profile(username):
    return f"Hello, {username}! This is your profile page."

# This is the part that runs the app
if __name__ == '__main__':
    # host='0.0.0.0' makes the server accessible from other devices on your network
    # port=5000 is the default port Flask uses
    # debug=True enables debug mode, which is very helpful during development
    app.run(host='0.0.0.0', port=5000, debug=True)
```

**Explanation:**

- `if __name__ == '__main__':`: This is a standard Python construct. The code inside this block will only run when you execute the script directly (e.g., `python my_app.py`).
- `app.run(host='0.0.0.0', port=5000, debug=True)`: This line starts Flask's built-in development server.
    - `host='0.0.0.0'`: This makes the server accessible from any IP address on your machine, including from other devices on your local network if your firewall allows it. For local development, `127.0.0.1`(localhost) is also common.
    - `port=5000`: This specifies the port number the server will listen on. You'd access your app at `http://127.0.0.1:5000/` or `http://localhost:5000/`.
    - `debug=True`: This is **very important** during development. It does two things:
        1. **Activates the debugger:** If an error occurs in your code, Flask will show you a detailed traceback in your browser, making it easier to find and fix issues.
        2. **Activates the reloader:** Whenever you save changes to your Python code, the server will automatically restart, so you don't have to stop and start it manually to see your changes. **Caution:**Never run a Flask application with `debug=True` in a production environment, as it can pose security risks.

### Try it yourself

1. Create a new folder for your Flask project (e.g., `my_flask_app`).
2. Inside this folder, create a Python file named `app.py`.
3. Copy the complete Flask application code (including the `app.run` part) from the "Running a Flask Application" section above into your `app.py`.
4. Open your terminal or command prompt, navigate to your project folder (`my_flask_app`).
5. Run the command `python app.py`.
6. You should see output indicating the server is running, something like: `Running on <http://127.0.0.1:5000/> (Press CTRL+C to quit)` `Restarting with stat` `Debugger is active!` `Debugger PIN: ...`
7. Open your web browser and go to `http://127.0.0.1:5000/`. You should see "Hello, World! This is Flask."
8. Now try visiting `http://127.0.0.1:5000/profile/YourName` (replace `YourName` with your actual name). You should see a personalized greeting!

### Think about it

How might you design routes for a simple blog that needs to show:

1. A homepage listing all blog posts.
2. A page to display a single blog post, identified by a unique ID (e.g., `/post/123`).
3. A page where a user could create a new blog post (e.g., `/create-post`).

## The Request-Response Cycle with Flask

Let's revisit the request-response cycle, now with Flask in the picture:

1. **User Action:** You type `http://127.0.0.1:5000/profile/Alice` into your browser and press Enter.
2. **HTTP Request:** Your browser creates an HTTP GET request and sends it to the server at IP address `127.0.0.1`on port `5000`. The request path is `/profile/Alice`.
3. **Flask Receives Request:** Your running Flask application (via Werkzeug) receives this HTTP request.
4. **Routing:** Flask looks at its routing rules. It finds the rule `@app.route('/profile/<username>')` which matches the path `/profile/Alice`. It also extracts the `username` part (`Alice`) from the URL.
5. **View Function Called:** Flask calls the associated view function, `profile()`, and passes the extracted `username`("Alice") as an argument to it: `profile(username="Alice")`.
6. **View Function Processes:** The `profile` function executes: `return f"Hello, Alice! This is your profile page."`. It generates a string.
7. **HTTP Response Generated:** Flask takes this string, wraps it in an HTTP response (setting appropriate headers like `Content-Type: text/html`), and prepares to send it back.
8. **Response Sent:** Flask sends the HTTP response back to your browser.
9. **Browser Renders:** Your browser receives the response, sees it's HTML (or in this case, text that it will render as HTML), and displays "Hello, Alice! This is your profile page."

This cycle is fundamental to how web applications work.

## Dynamic Content with Templates

So far, our view functions have returned simple strings. In real web applications, you'll want to return rich HTML pages. Manually creating complex HTML strings in Python code can be messy and difficult to manage.

This is where **templating engines** come in. Flask uses Jinja2 by default. A template is essentially an HTML file with special placeholders for dynamic data. Your Flask view function can load a template, fill in the placeholders with data, and then "render" it to produce the final HTML to send to the browser.

For example, you might have a template `profile_template.html`:

```html
<!DOCTYPE html>
<html>
<head>
    <title>User Profile</title>
</head>
<body>
    <h1>Hello, {{ user_name_in_template }}!</h1>
    <p>This is your profile page.</p>
</body>
</html>
```

And your Flask view function would look something like this (this requires a bit more setup, like creating a `templates`folder, which we'll cover in class):

```python
from flask import Flask, render_template # Import render_template

app = Flask(__name__)

@app.route('/user/<name>')
def user_profile(name):
    # Instead of returning a string, we render a template
    # We pass the 'name' from the URL to the template as 'user_name_in_template'
    return render_template('profile_template.html', user_name_in_template=name)

if __name__ == '__main__':
    app.run(debug=True)
```

When someone visits `/user/Bob`, Flask would use `profile_template.html`, replace `{{ user_name_in_template }}`with "Bob", and send the resulting HTML to the browser. This makes it much easier to separate your application's logic (Python code) from its presentation (HTML). We'll dive deeper into templates during the live session.

That's it for the pre-class preparation! By understanding these core concepts of server-side development and Flask, you'll be well-prepared for our hands-on session where we'll build more interesting web applications.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Web-3-Server-Side-Flask-sasj4pbj0jcxo5f?mode=doc](https://gamma.app/docs/Web-3-Server-Side-Flask-sasj4pbj0jcxo5f?mode=doc)

Try not to peek before class - spoilers inside!

</aside>