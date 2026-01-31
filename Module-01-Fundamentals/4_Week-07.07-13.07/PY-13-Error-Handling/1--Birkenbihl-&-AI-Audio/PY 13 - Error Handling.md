Welcome to the world of Python Error Handling! Sometimes, even the best-written code encounters unexpected situations or outright mistakes. What happens then? Does the program just crash? Often, yes! But Python provides powerful tools to gracefully manage these errors, prevent crashes, and make your programs more robust and user-friendly. This preparation will introduce you to the fundamental concepts of errors and how to start handling them.

## What Are Errors in Programming?

![image.png](attachment:ea9c4f7d-5343-4076-a8be-5b6e7237b16f:image.png)

Think about following a recipe. If the recipe tells you to "add 1 cup of sugar" but you don't have any sugar, you've encountered an issue. You can't proceed as instructed. Similarly, if a step says "mix vigorously" but doesn't specify _what_ to mix, that's a different kind of problem – an ambiguity or mistake in the instructions themselves.

In programming, errors are similar. They represent situations where the Python interpreter cannot execute the instructions as written, either because the instructions themselves are malformed or because some condition arises during execution that prevents the instruction from completing successfully.

There are generally two main categories of errors in Python:

1. **Syntax Errors:** These are mistakes in the structure or grammar of the Python code itself. The interpreter spots these before the program even starts running. It's like trying to read a sentence where words are misspelled or punctuation is missing – you can't understand it.
    - Example: Forgetting a colon `:` at the end of an `if` statement, misspelling a keyword like `whle` instead of `while`, or having unmatched parentheses. Python will refuse to run the code and point out the location of the syntax error.
2. **Exceptions (Runtime Errors):** These errors occur _during_ the execution of the program, even if the syntax is perfectly correct. They happen when the code encounters an unexpected situation it doesn't know how to handle. It's like the recipe example: the instruction "add 1 cup of sugar" is grammatically correct, but the error occurs _when you try to execute it_ because you lack the ingredient.
    - Example: Trying to divide a number by zero (`ZeroDivisionError`), trying to access an item in a list using an index that doesn't exist (`IndexError`), trying to open a file that isn't there (`FileNotFoundError`), or trying to add a number to a string (`TypeError`).

This lesson focuses on **Exceptions** – how to anticipate and manage these runtime errors.

### Try it yourself

Open your Python interpreter or create a small `.py` file and try running these lines, one at a time. Observe the output:

```python
# Cause a TypeError
result = "hello" + 5
print(result)
# Cause an IndexError
my_list = [1, 2, 3]
print(my_list[5])
# Cause a ZeroDivisionError
result = 10 / 0
print(result)
```

You'll see Python stops execution and prints a "traceback," showing where the error occurred and what type of exception it was.

## Why Handle Exceptions?

When an exception occurs and is not handled, the default behavior is for the program to stop immediately (crash) and print the traceback message. This might be acceptable for a quick script you wrote for yourself, but it's terrible for users of your software!

Imagine using a web application, filling out a long form, and clicking "Submit," only to have the entire application crash because you accidentally typed text into a field expecting a number. That's a frustrating user experience.

Proper exception handling allows you to:

- **Prevent Crashes:** Catch errors gracefully instead of letting the program terminate abruptly.
- **Provide User Feedback:** Inform the user about what went wrong in a helpful way (e.g., "Invalid input: Please enter a number.") instead of showing a scary traceback.
- **Perform Cleanup Actions:** Ensure critical resources (like files or network connections) are closed properly, even if an error occurs.
- **Allow Recovery:** In some cases, you can correct the error condition or try an alternative approach.
- **Log Errors:** Record details about errors to help with debugging and monitoring application health.

## Introducing `try`, `except`, and `finally`

The core mechanism for handling exceptions in Python involves the `try`, `except`, and optionally `finally` clauses. The basic structure looks like this:

```python
try:
    # Code that might potentially raise an exception
    # ... suspicious code goes here ...
    print("Attempting the risky operation...")
    # Example 1: No error
    # risky_result = 10 / 2
    # Example 2: Error
    risky_result = 10 / 0 # This will cause a ZeroDivisionError
    print("This line will not be reached if an error occurs above.")

except ZeroDivisionError:
    # Code that runs ONLY if a ZeroDivisionError occurs in the 'try' block
    print("Caught the division by zero error!")

except Exception as e:
    # Code that runs if ANY OTHER exception (that is a subclass of Exception) occurs
    print(f"Caught some other error: {e}")

finally:
    # Code that ALWAYS runs, regardless of whether an exception
    # occurred or was caught.
    print("This 'finally' block always executes, for cleanup perhaps.")

print("Execution continues after the try-except-finally block.")
```

**How it works:**

1. Python starts executing the code inside the `try` block.
2. **If no exception occurs:**
    - The entire `try` block completes successfully.
    - Any `except` blocks are skipped.
    - The `finally` block (if present) is executed.
    - Execution continues with the code after the `try...except...finally` structure.
3. **If an exception occurs inside the `try` block:**
    - Python immediately stops executing the rest of the code _within_ the `try` block.
    - It looks for an `except` block whose specified exception type matches the one that occurred.
    - **If a matching `except` block is found:**
        - The code inside that `except` block is executed.
        - The `finally` block (if present) is executed.
        - Execution continues with the code after the `try...except...finally` structure.
    - **If no matching `except` block is found:**
        - The `finally` block (if present) is still executed.
        - After the `finally` block, the exception is "unhandled" (re-raised), and the program crashes unless caught by an outer `try...except`.

**The `finally` Clause:**

The key purpose of the `finally` block is to guarantee that certain code runs, no matter what happens in the `try` or `except` blocks. This is crucial for cleanup operations, such as:

- Closing files that were opened.
- Releasing network connections.
- Disconnecting from databases.
- Resetting configurations.

Even if an error occurs and is caught, or if an error occurs and isn't caught, or even if the `try` block finishes successfully, the `finally` block provides a safe place to ensure these cleanup tasks happen.

## Common Built-in Exceptions

Python has many built-in exceptions for common errors. You've already seen some. Here are a few you'll encounter frequently:

- `Exception`: The base class for almost all built-in exceptions. Catching `Exception` will catch most errors (but usually, it's better to be more specific).
- `SyntaxError`: Error in the code's syntax (cannot be caught by `try...except` as it happens before execution).
- `TypeError`: An operation or function is applied to an object of an inappropriate type (e.g., `len(123)` or `"hello" + 5`).
- `ValueError`: An operation or function receives an argument that has the right type but an inappropriate value (e.g., `int("abc")`).
- `NameError`: A variable or function name is used before it has been assigned a value.
- `IndexError`: A sequence subscript (like list index) is out of range.
- `KeyError`: A dictionary key is not found.
- `FileNotFoundError`: Trying to open a file that does not exist for reading.
- `ZeroDivisionError`: Trying to divide by zero.
- `ImportError`: Python cannot find the module you're trying to import.
- `AttributeError`: Trying to access an attribute or method that doesn't exist on an object (e.g., `mylist.appeend(1)` - misspelled `append`).

### Try it yourself

1. Modify the earlier examples to use `try...except` blocks to catch the specific exceptions and print a user-friendly message instead of crashing.
    
    Example for `TypeError`:
    
    ```python
    try:
        result = "hello" + 5
        print(result)
    except TypeError:
        print("Oops! Looks like you tried to combine text and a number in a way Python doesn't like.")
    finally:
        print("Cleanup step after TypeError attempt.")
    
    print("Program continues running!")
    ```
    
    Try this for `IndexError` and `ZeroDivisionError` as well.
    
2. Experiment with catching a _different_ exception type than the one that actually occurs (e.g., `except ValueError:`when a `TypeError` happens) to see that the error is _not_ caught, but the `finally` block _still_ runs before the program crashes.
    
3. Also try using a generic `except Exception:` to see that it catches the error, and the `finally` block runs afterwards.
    

### Think about it

Why is it generally better to catch specific exceptions (like `except ValueError:`) rather than using a generic `except:`or `except Exception:`? What potential problems could arise from catching _all_ possible exceptions without distinguishing them?

## Can't We Get By Without Error Handling?

Python offers two styles to manage potential errors:

### LBYL (Look Before You Leap)

Check conditions before acting. Example:

```python
if 'key' in my_dict:
    value = my_dict['key']
else:
    value = 'default'
```

Good when checking is cheap and reliable.

### EAFP (Easier to Ask Forgiveness than Permission)

Try first, handle errors if they happen. Example:

```python
try:
    value = my_dict['key']
except KeyError:
    value = 'default'
```

This is more Pythonic: it's cleaner, and more efficient where failure is rare.

Sometimes we must handle exceptions for situations we can't prevent, like import errors, network failures, or file access issues.

Example:

```python
try:
    import non_existent_module
except ImportError:
    print("Module not found, using alternative solution")
    # Use alternative implementation or fallback
```

**Bottom Line:** We _can't_ always avoid error handling. Even in simple cases, deciding between LBYL and EAFP shapes how you write robust, readable code.

This introduction should give you a good foundation for understanding what exceptions are and why and how we start to handle them using `try`, `except`, and `finally`. In the live lesson, we'll dive deeper into more advanced techniques and best practices.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Python-13-Error-Handling-dtvld6dvcsq6itb?mode=doc](https://gamma.app/docs/Python-13-Error-Handling-dtvld6dvcsq6itb?mode=doc)

Try not to peek before class - spoilers inside!

</aside>