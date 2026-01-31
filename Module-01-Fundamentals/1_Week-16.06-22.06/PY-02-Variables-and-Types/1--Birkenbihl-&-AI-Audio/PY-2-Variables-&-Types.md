Welcome to your second Python lesson! In the first lesson, you got Python running and executed some basic commands using the interactive interpreter. Now, we'll dive into one of the most fundamental concepts in programming: **variables** and **data types**. Understanding these is crucial for writing any useful program.

## What is a Variable?

Think of a variable as a labeled box where you can store information (data). You give the box a name (the variable name), and you put something inside it (the value). You can then refer to the box by its name to see what's inside or even change what's inside.

In Python, you create a variable by choosing a name and using the equals sign (`=`), known as the **assignment operator**, to give it a value. You do this directly in the Python interpreter (the `>>>` prompt).

```python
message = "Hello, Cybersecurity!"
student_count = 120
pi_approx = 3.14
is_online = True
```

In this example:

- `message` is a variable storing text.
- `student_count` is a variable storing a whole number.
- `pi_approx` is a variable storing a number with a decimal point.
- `is_online` is a variable storing a true/false value.

Once you've assigned a value to a variable, you can use the variable name in place of the value. For example, typing the variable name itself into the interpreter will usually show its value, or you can use the `print()` function.

```python
# In the interpreter, after defining message and student_count above:
print(message)
# Output: Hello, Cybersecurity!

# Typing the variable name often shows its value too:
# student_count
# Output: 120
```

### Variable Naming Rules

Choosing good variable names makes your code much easier to read and understand. Python has some rules and conventions:

1. **Must start with a letter or underscore (`_`):** `my_var` and `_internal` are valid, but `1var` is not.
2. **Can only contain letters, numbers, and underscores:** `user_id_1` is valid, but `user-id` or `user id` are not.
3. **Case-sensitive:** `myVariable` is different from `myvariable`.
4. **Cannot be a Python keyword:** You can't name a variable `if`, `else`, `for`, `while`, `class`, etc. These words have special meanings in Python.

**Convention:** Use `snake_case` for variable names (all lowercase words separated by underscores). This is the standard practice in the Python community and makes code readable. Examples: `user_name`, `ip_address`, `file_path`.

### Try it yourself

1. Open your terminal application.
    
2. Start the Python interpreter by typing `python3` (or just `python` depending on your system) and pressing Enter. You should see the `>>>` prompt.
    
3. At the prompt, create a variable named `my_name` and assign your name (as text, enclosed in quotes) to it. Press Enter.
    
    ```python
    my_name = "Your Name Here"
    ```
    
4. Create a variable named `my_age` and assign your age (as a whole number) to it. Press Enter.
    
    ```python
    my_age = 30 # Use your actual age
    ```
    
5. Use the `print()` function to display the values of both variables. Type each line and press Enter.
    
    ```python
    print(my_name)
    print(my_age)
    ```
    
6. Observe the output printed by the interpreter.
    

## Data Types: What Kind of Data?

The "something" you put inside the variable's box has a specific **type**. Python needs to know the type of data to understand how to work with it (e.g., you can do math with numbers, but not directly with text). Python figures out the type automatically when you assign a value.

Here are the fundamental data types we'll start with:

1. **Integer (`int`):** Whole numbers, positive or negative, without decimals.
    - Examples: `10`, `5`, `0`, `12345`
2. **Float (`float`):** Numbers with a decimal point or numbers written in exponential notation.
    - Examples: `3.14`, `0.5`, `2.0`, `1.5e3` (which means 1.5 * 10^3 = 1500.0)
3. **String (`str`):** Sequences of characters (text). You define strings using single quotes (`'...'`) or double quotes (`"..."`).
    - Examples: `"Hello"`, `'Cybersecurity'`, `"123"`, `' '` (a space is also a character)
4. **Boolean (`bool`):** Represents truth values. Can only be `True` or `False` (note the capital letters). Booleans are essential for making decisions in code.
    - Examples: `True`, `False`

### Checking the Type

You can use the built-in `type()` function to find out the data type of a variable or a value directly in the interpreter.

```python
# Define some variables first in the interpreter:
message = "File not found"
error_code = 404
severity = 3.5
is_critical = False

# Now check their types (and the types of literal values):
type(message)      # Output: <class 'str'>
type(error_code)   # Output: <class 'int'>
type(severity)     # Output: <class 'float'>
type(is_critical)  # Output: <class 'bool'>
type(99)           # Output: <class 'int'>
type("Alert!")     # Output: <class 'str'>
```

Just type each `type(...)` command at the `>>>` prompt and press Enter to see the result immediately.

### Try it yourself

1. In the same Python interpreter session (or start a new one if you closed it), define the following variables by typing each line and pressing Enter:
    
    ```python
    score = 1500
    player_name = "Hero"
    game_over = False
    time_elapsed = 123.5
    ```
    
2. Now, check the type of each variable using the `type()` function. Type each line and press Enter:
    
    ```python
    type(score)
    type(player_name)
    type(game_over)
    type(time_elapsed)
    ```
    
3. Observe the output for each command. Does it match what you expected based on the definitions?
    

## Basic Operations

The type of a variable determines what operations you can perform with it. You can try these directly in the interpreter.

- **Numbers (`int`, `float`):** You can perform standard arithmetic operations:
    
    - Addition: `+`
    - Subtraction: `-`
    - Multiplication: `*`
    - Division: `/` (always results in a `float`)
    - Floor Division: `//` (divides and rounds _down_ to the nearest whole number, result type depends on operands)
    - Modulo (remainder): `%`
    - Exponentiation: `**`
    
    ```python
    x = 10
    y = 3.0
    
    x + y   # Output: 13.0
    x - y   # Output: 7.0
    x * y   # Output: 30.0
    x / y   # Output: 3.3333333333333335
    x // y  # Output: 3.0
    x % y   # Output: 1.0
    x ** 2  # Output: 100
    ```
    
- **Strings (`str`):**
    
    - Concatenation (joining strings): `+`
    - Repetition: `*` (with an integer)
    
    ```python
    first_name = "Ada"
    last_name = "Lovelace"
    full_name = first_name + " " + last_name # Add a space in between!
    print(full_name) # Output: Ada Lovelace
    
    separator = "-" * 10 # Repeat "-" ten times
    print(separator)   # Output: ----------
    ```
    

**Important:** You generally cannot mix types in operations without explicitly converting them. For example, typing `10 + "5"` into the interpreter will cause a `TypeError` because Python doesn't know whether you want to do math or join text. Try it!

```python
10 + "5"
# This will produce a TypeError as shown in the text above
```

We'll learn how to handle such situations (type conversion) later in the lesson.

### Think about it

- Why is `10 / 2` a `float` (`5.0`) and not an `int` (`5`) in Python? (Hint: Think about consistency).
- What do you think `10 // 3.0` results in? What about `10.0 // 3`? Try them out in the interpreter!
- If you have a variable `count = 5`, how could you create the string `"Count: 5"` using the variable and string concatenation? (This will actually cause a `TypeError`. We'll see how to fix this soon!).

## Dynamic Typing

One characteristic of Python is **dynamic typing**. This means you don't have to declare the type of a variable when you create it, and you can even change the type of data a variable holds later on.

Try this in the interpreter:

```python
# Type these lines sequentially into the interpreter:
my_variable = 100
type(my_variable)      # Output: <class 'int'>

my_variable = "Now I'm a string"
type(my_variable)      # Output: <class 'str'>

my_variable = True
type(my_variable)      # Output: <class 'bool'>
```

While flexible, this means you need to be mindful of what type of data your variable currently holds, especially before performing operations on it.

That covers the basics of variables and fundamental data types! Spend some time experimenting with these concepts in the Python interpreter. Create different variables, check their types, and try some basic operations. This will prepare you well for our live session where we'll build upon this foundation. To exit the interpreter, you can type `exit()` or press `Ctrl+D`.

<aside> 📌

The slides for the live session can be viewed here:

[Python 2 - Variables & Types](https://gamma.app/docs/Python-2-Variables-Types-lf7qs2tabchz58u)

Try not to peek before class - spoilers inside!

</aside>

# Variables: Labeled Boxes

**Store data (values)**

**Use names (identifiers) to refer to data**

**Assignment: variable_name = value**

**Naming Rules & snake_case Convention (PEP8!)**

# Demo: Browsing PEP8

PEP 8 – Style Guide for Python Code | [peps.python.org](http://peps.python.org) - Python Enhancement Proposals (PEPs)

# Basic Data Types

|**int**|Whole numbers (e.g., 10, -3, 0)|
|---|---|
|**float**|Numbers with decimals (e.g., 3.14, -0.5, 2.0)|
|**str**|Text/Sequences of characters (e.g., "Hello", 'Cyber')|
|**bool**|Truth values (True, False)|

Use type() to check!

# Numeric Operations

### +

Addition

Subtraction

Multiplication

### /

Float division

### //

Floor division

### %

Modulo

### *

Exponent

# String Operations

### + (concatenation)

Joins strings together

```
"Hello" + " World"
# Result: "Hello World"

```

### (repetition)

Repeats a string

```
"Python " * 3
# Result: "Python Python Python "

```

# TypeError: Mixing Incompatible Types

Python often doesn't know how to combine different types automatically.

Example: 5 + " apples" -> TypeError

Need to convert types explicitly.

### Incompatible Types

5 + " apples"

### TypeError

Can't add int and str

### Solution

str(5) + " apples"

# Numeric Operations

### +

Addition

Subtraction

Multiplication

### /

Float division

### //

Floor division

### %

Modulo

### *

Exponent

# String Operations

### + (concatenation)

Joins strings together

```
"Hello" + " World"
# Result: "Hello World"

```

### (repetition)

Repeats a string

```
"Python " * 3
# Result: "Python Python Python "

```

# TypeError: Mixing Incompatible Types

Python often doesn't know how to combine different types automatically.

Example: 5 + " apples" -> TypeError

Need to convert types explicitly.

### Incompatible Types

5 + " apples"

### TypeError

Can't add int and str

### Solution

str(5) + " apples"

**What happens if you run value = "100" and then print(value / 2)? Why?**You get a TypeError. value is a string ("100"), and you cannot perform mathematical division (/) directly on a string. You would need to convert value to a number first (e.g., int(value)).

`value = "100"

# This will cause an error:

# print(value / 2)

# Correct approach:

print(int(value) / 2) # Output: 50.0`

# f-string

```
name = "Alice"
age = 30
# f-string example
print(f"Hello, {name}! You are {age} years old.")
# Output: Hello, Alice! You are 30 years old.

```

### Benefits of f-strings:

- More readable than other string formatting methods
- Can include expressions: f"Result: {2 * 3}"
- Format specifiers available: f"Pi: {3.14159:.2f}"

# Using isinstance() for Type Checking

### What is isinstance()?

A built-in function that checks if an object is an instance of a specified class or type.

Syntax: `isinstance(object, classinfo)`

- Returns **True** if object is an instance of classinfo
- Returns **False** otherwise

**Examples:**

`x = 5 print(isinstance(x, int)) # True print(isinstance(x, float)) # False

name = "Python" print(isinstance(name, str)) # True`

Unlike `type()`, `isinstance()` also handles inheritance, making it more flexible for class hierarchies.

# Summary

**Variables store data using names.**

**Core types: int, float, str, bool.**

**type() checks the data type.**

*_Operators work based on type (+, _, /, //, etc.).__

**TypeError happens when mixing incompatible types.**

**Use int(), float(), str() to convert types.**

**Follow snake_case naming convention (as recommended by PEP 8).**