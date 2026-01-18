Welcome to the world of functions in Python! Functions are a fundamental concept in programming that allows you to write more organized, reusable, and efficient code. Think of them as named blocks of code that perform a specific task. Instead of writing the same sequence of steps multiple times, you can define it once as a function and then call that function whenever you need it.

## What is a Function?

At its core, a function is a block of organized, reusable code that is used to perform a single, related action. Functions provide better modularity for your application and a high degree of code reusing.

Imagine you're writing a script, and you find yourself calculating the area of a rectangle in several different places. Each time, you write:

```python
length = 10
width = 5
area = length * width
print("The area is:", area)

# ... some other code ...

length2 = 7
width2 = 3
area2 = length2 * width2
print("The area is:", area2)
```

This works, but it's repetitive. If you needed to change how the area is calculated or displayed, you'd have to find and modify every instance. A function solves this.

## Defining a Function

You can define your own functions using the `def` keyword. Here's the basic syntax:

```python
def function_name(parameters):
  """Optional docstring explaining what the function does."""
  # Code block (indented)
  # ... statements performing the task ...
  return value # Optional: returns a value from the function
```

Let's break this down:

1. **`def` keyword:** This signals the start of a function definition.
2. **`function_name`:** This is the name you give your function. Choose descriptive names (like variable names, use snake_case: lowercase words separated by underscores).
3. **`parameters` (in parentheses `()`):** These are inputs the function accepts. A function can have zero or more parameters, separated by commas. These act like variables inside the function. If there are no parameters, you still need the empty parentheses `()`.
4. **Colon (`:`):** Marks the end of the function header.
5. **Docstring (optional but recommended):** A string literal enclosed in triple quotes (`"""Docstring goes here"""`) right after the header. It explains the function's purpose, parameters, and what it returns. Good practice for documentation!
6. **Indented Code Block:** The actual code that performs the function's task. This block _must_ be indented (usually 4 spaces).
7. **`return` statement (optional):** Used to send a result back from the function to the place where it was called. If omitted, the function implicitly returns a special value `None`.

**Example: A Simple Greeting Function**

```python
def greet():
  """Prints a simple greeting."""
  print("Hello there!")

# Example: Calculating Rectangle Area
def calculate_rectangle_area(length, width):
  """Calculates the area of a rectangle."""
  area = length * width
  return area
```

## Calling a Function

Defining a function doesn't execute its code. It just creates the function. To run the code inside a function, you need to _call_ it. You call a function by using its name followed by parentheses `()`. If the function expects parameters (inputs), you provide values, called _arguments_, inside the parentheses.

```python
# Calling the greet function (no arguments needed)
greet()

# Calling the calculate_rectangle_area function with arguments
rect_length = 10
rect_width = 5
result_area = calculate_rectangle_area(rect_length, rect_width) # Arguments are 10 and 5
print("The calculated area is:", result_area)

# You can also pass literal values as arguments
another_area = calculate_rectangle_area(7, 3)
print("Another area:", another_area)
```

**Output of the above code:**

```
Hello there!
The calculated area is: 50
Another area: 21
```

Notice how `calculate_rectangle_area` _returns_ a value, which we store in variables (`result_area`, `another_area`) and then print. The `greet` function doesn't return anything explicitly (it returns `None`), it just performs an action (printing).

### Try it yourself

Define a function called `say_goodbye` that takes one parameter `name` and prints "Goodbye, [name]!". Then, call this function with your own name as the argument.

## Parameters vs. Arguments

These terms are often used interchangeably, but there's a subtle difference:

- **Parameters:** Variables listed inside the parentheses in the function _definition_. They are placeholders for the inputs. (e.g., `length` and `width` in `def calculate_rectangle_area(length, width):`)
- **Arguments:** The actual _values_ passed to the function when it is _called_. (e.g., `10` and `5` in `calculate_rectangle_area(10, 5)`)

## The `return` Statement

The `return` statement does two things:

1. Immediately exits the function (no code after `return` in the function block will be executed).
2. Sends a value back to the caller.

A function can return any type of value: numbers, strings, lists, booleans, even `None`.

```python
def add_numbers(x, y):
  """Adds two numbers and returns the sum."""
  total = x + y
  return total
  print("This line will never be printed.") # Code after return is unreachable

sum_result = add_numbers(5, 3)
print(sum_result) # Output: 8

def check_even(number):
  """Checks if a number is even."""
  if number % 2 == 0:
    return True # Return boolean True if even
  else:
    return False # Return boolean False if odd

is_10_even = check_even(10)
print(is_10_even) # Output: True

is_7_even = check_even(7)
print(is_7_even) # Output: False
```

If a function doesn't have a `return` statement, or just has `return` with no value, it automatically returns `None`.

```python
def simple_print(message):
  """Prints a message but doesn't return anything explicitly."""
  print(message)

result = simple_print("Hello again")
print(result)
```

**Output:**

```
Hello again
None
```

## Why Use Functions?

- **Organization:** Break down complex problems into smaller, manageable pieces. A program made of well-defined functions is easier to read and understand.
- **Reusability (DRY Principle):** DRY stands for "Don't Repeat Yourself". Write code once and reuse it multiple times by calling the function. This saves time and reduces errors.
- **Maintainability:** If you need to update or fix logic, you only need to change it in one place (the function definition).
- **Abstraction:** You can use a function without needing to know the details of _how_ it works internally. You just need to know its name, what inputs it needs (parameters), and what output it gives (return value).

### Think about it

Consider the programs you've written so far (using conditions, lists, loops). Can you identify parts of your code that were repeated? How could you rewrite those parts using functions to make the code shorter and cleaner?

## Scope: Where Variables Live

An important concept related to functions is _scope_. Scope refers to the region of your code where a variable can be accessed.

- **Local Scope:** Variables defined _inside_ a function (including its parameters) are local to that function. They can only be accessed from within that function. They are created when the function is called and destroyed when the function finishes.
- **Global Scope:** Variables defined _outside_ of any function have global scope. They can be accessed from anywhere in your script, including inside functions (though modifying global variables from within functions requires special care and is often discouraged).

```python
global_variable = "I am global"

def my_function():
  local_variable = "I am local"
  print(local_variable)      # Works: Accessing local variable inside the function
  print(global_variable)     # Works: Accessing global variable inside the function

my_function()

print(global_variable)     # Works: Accessing global variable outside the function
# print(local_variable)    # This would cause an error! Cannot access local_variable here.
```

Understanding scope helps prevent naming conflicts and unexpected behavior in your programs. For now, focus on the fact that variables created inside a function generally stay inside that function.

That's the basics of defining and using functions in Python! Prepare any questions you have for the live session.