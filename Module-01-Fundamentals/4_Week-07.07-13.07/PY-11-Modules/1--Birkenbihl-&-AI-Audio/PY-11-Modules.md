Welcome! Before our live session on Python Modules, please go through this material. Understanding these concepts will help you get the most out of our class.

## What are Modules?

![image.png](attachment:6047f9e3-97ff-4630-a488-066418bd8f93:image.png)

Imagine you're building a large project, like a house. You wouldn't build every single component from scratch right there on the site, would you? You'd likely use pre-fabricated parts like doors, windows, and maybe even entire wall sections. These pre-made components save time, ensure consistency, and are built by specialists.

In Python, **modules** are like those pre-fabricated parts. They are simply Python files (`.py` files) containing Python definitions and statements (like functions, classes, and variables). Modules allow you to logically organize your Python code. Grouping related code into a module makes the code easier to understand, use, and maintain. It also allows you to reuse code across different projects without copying and pasting.

## Why Use Modules?

1. **Organization:** Instead of writing one enormous script, you can break down your project into smaller, manageable modules, each handling a specific part of the task.
2. **Reusability:** Write a function or class once in a module, and you can use it in many different scripts or projects just by importing the module. This follows the DRY principle: "Don't Repeat Yourself".
3. **Collaboration:** Different team members can work on different modules simultaneously.
4. **Namespace Management:** Modules help prevent naming conflicts. A function named `calculate` in `module_a.py` won't clash with a function named `calculate` in `module_b.py` because you'll access them as `module_a.calculate()` and `module_b.calculate()`.
5. **Using Existing Code:** Python comes with a vast **Standard Library** – a collection of built-in modules providing tools for common tasks (math operations, file I/O, networking, randomness, etc.). You don't have to write these yourself! There are also countless third-party modules created by the community for almost any task imaginable.

## How to Use Modules: The `import` Statement

To use the code defined in a module within your current Python script, you need to **import** it. The simplest way is using the `import` keyword followed by the module name (the filename without the `.py` extension).

```python
import module_name
```

Once imported, you can access the functions, variables, or classes defined inside that module using **dot notation**: `module_name.item_name`.

**Example: Using the `math` module**

Python's standard library includes a module named `math` that provides various mathematical functions and constants.

```python
# Import the entire math module
import math

# Use the sqrt function from the math module
number = 16
square_root = math.sqrt(number)
print(f"The square root of {number} is {square_root}")

# Use the pi constant from the math module
radius = 5
area = math.pi * (radius ** 2)
print(f"The area of a circle with radius {radius} is {area}")
```

Output:

```
The square root of 16 is 4.0
The area of a circle with radius 5 is 78.53981633974483
```

### Try it yourself

Open VS Code, create a new Python file (e.g., `try_math.py`), type or paste the code above, and run it. See the output for yourself.

## Importing Specific Items: `from ... import ...`

Sometimes, you only need one or two specific items from a module, or you might find typing the module name repeatedly cumbersome. In such cases, you can use the `from ... import ...` statement.

```python
from module_name import item_name1, item_name2
```

When you use `from ... import ...`, the imported items are added directly to your script's namespace, so you can use them without the `module_name.` prefix.

**Example: Using `from ... import ...` with `random`**

The `random` module provides functions for generating random numbers.

```python
# Import only the randint function from the random module
from random import randint

# Now we can use randint directly without the 'random.' prefix
random_number = randint(1, 10) # Generates a random integer between 1 and 10 (inclusive)
print(f"A random integer between 1 and 10: {random_number}")

# If we try to use another function from random, like choice, it won't work
# because we didn't import it directly.
# The following line would cause an error:
# print(random.choice(['a', 'b', 'c'])
```

**Caution:** While convenient, using `from ... import ...` extensively can sometimes make it harder to tell where a specific function or variable came from, especially if different modules have items with the same name. Importing the whole module (`import module_name`) is often clearer for larger scripts.

You can also import everything from a module using `*`, like `from math import *`. However, this is generally **discouraged** because it pollutes your script's namespace with all the names from the module, potentially overwriting your own variables or functions without you realizing it, and making the code harder to read and debug.

## The Python Standard Library

Python comes "batteries included," meaning it has a rich standard library full of useful modules. You don't need to install anything extra to use them; you just import them. We've already seen `math` and `random`. Here are a few others you might encounter:

- `os`: Provides functions for interacting with the operating system (like working with files and directories, getting environment variables).
- `sys`: Access to system-specific parameters and functions (like command-line arguments).
- `datetime`: For working with dates and times.
- `json`: For working with JSON data.
- `re`: For working with regular expressions.

You can explore the full list and documentation here (no need to memorize it now, just be aware it exists): [https://docs.python.org/3/library/](https://docs.python.org/3/library/)

### Try it yourself

Let's try the `datetime` module to get the current date and time.

1. Create a new Python file in VS Code (e.g., `try_datetime.py`).
    
2. Type or paste the following code:
    
    ```python
    # Import the datetime module
    import datetime
    
    # Get the current date and time
    now = datetime.datetime.now()
    
    # Print it out
    print("The current date and time is:")
    print(now)
    
    # You can also format it
    formatted_time = now.strftime("%Y-%m-%d %H:%M:%S")
    print("Formatted time:")
    print(formatted_time)
    ```
    
3. Run the file. Observe how the `datetime` module provides the `datetime` object, which has methods like `now()` to get the current time and `strftime()` to format it as a string.
    

### Think about it

Why is it beneficial that Python includes a standard library? How does this compare to having to find and install basic tools for every project?

## Summary

- Modules are Python files (`.py`) containing reusable code (functions, classes, variables).
- They help organize code, promote reusability, and prevent naming conflicts.
- Use `import module_name` to bring a module's code into your script.
- Access items within an imported module using dot notation: `module_name.item_name`.
- Use `from module_name import item_name` to import specific items directly into your namespace (use with caution).
- Python has a vast Standard Library of built-in modules for common tasks.

That's it for the pre-class preparation! Spend some time reviewing these concepts and try the examples. We'll build upon this foundation in our live session.