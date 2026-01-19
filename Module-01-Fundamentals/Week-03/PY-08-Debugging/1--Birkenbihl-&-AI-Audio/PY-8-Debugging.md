Welcome! Before our live session on debugging, please go through this material. It introduces the concept of bugs in programming and the basic techniques we use to find and fix them.

## What is a Bug?

![image.png](attachment:3c557b51-db04-4295-aaf2-e44af2418e91:image.png)

```
                                                           *Computer bugs used to be actual bugs!*
```

In programming, a "bug" is simply an error or flaw in your code that causes it to produce an incorrect or unexpected result, or to behave in unintended ways. Bugs can range from simple typos to complex logical errors. The process of finding and fixing these bugs is called **debugging**.

Think of writing code like giving instructions to a computer. If your instructions are unclear, ambiguous, or just plain wrong, the computer won't do what you want it to do.

## Common Types of Bugs

There are three main categories of bugs you'll encounter:

1. **Syntax Errors:** These are like grammatical errors in your code. Python has strict rules about how code must be written (its syntax). If you break these rules, Python won't even be able to run your code. These are often the easiest to find because Python will usually tell you exactly where the error occurred.
    - Example: Forgetting a colon `:` at the end of an `if` statement or a `for` loop definition, misspelling a keyword like `whlie` instead of `while`, or having mismatched parentheses.
2. **Runtime Errors:** These errors occur _while_ your program is running. The syntax might be correct, but something unexpected happens during execution. The program starts running but crashes partway through.
    - Example: Trying to divide a number by zero, trying to access an item in a list using an index that doesn't exist (e.g., accessing `my_list[10]` when the list only has 5 items), or trying to use a variable that hasn't been defined yet. Python will usually report a "Traceback" when a runtime error occurs, giving clues about where the problem happened.
3. **Logic Errors:** These are often the trickiest bugs. The code runs without crashing (no syntax or runtime errors), but it doesn't do what you intended it to do. The result is incorrect or unexpected. The computer is doing exactly what you told it to do, but what you told it to do was wrong.
    - Example: You want to calculate the average of a list of numbers, but you accidentally divide by the wrong count. You write a condition for an `if` statement that doesn't quite capture the logic you needed. You use `>`(greater than) when you meant to use `>=` (greater than or equal to).

### Think about it

Consider the following code snippet which aims to print numbers from 0 to 4:

```python
count = 0
while count > 5:
  print(count)
  count = count + 1
```

What type of error is this (Syntax, Runtime, or Logic)? Why won't it work as intended?

## The Debugging Process

Debugging isn't just randomly changing code until it works. It's a systematic process:

1. **Understand the Problem:** Reproduce the bug consistently. Know what the _expected_ output or behavior is and what the _actual_ (incorrect) output or behavior is.
2. **Find the Source (Isolate the Bug):** Narrow down where in the code the error is occurring. This is often the hardest part.
3. **Fix the Bug:** Correct the code.
4. **Test the Fix:** Run the code again, including tests for edge cases, to ensure the bug is gone and you haven't introduced new ones.

## Basic Debugging Technique: Print Statements

One of the simplest yet most effective debugging techniques is using `print()` statements. You can insert `print()` calls at various points in your code to check the values of variables or see which parts of your code are being executed.

Example: Imagine a loop isn't behaving as expected.

```python
# Original code (buggy)
numbers = [1, 2, 3, 4, 5]
total = 10 # Start with an incorrect initial total
for num in numbers:
  total = total + num
# Expected total is 1+2+3+4+5 = 15, but we started total at 10

print(f"Final total: {total}") # Output: Final total: 25 (Incorrect!)

# --- Debugging with print ---
numbers = [1, 2, 3, 4, 5]
total = 10 # Start with an incorrect initial total
print(f"Starting total: {total}") # Check initial value
for num in numbers:
  print(f"Current number: {num}") # Check number being processed
  total = total + num
  print(f"Total after adding {num}: {total}") # Check total in each iteration

print(f"Final total: {total}")
```

By adding print statements, you can trace the execution flow and see exactly where the `total` variable's value goes wrong (in this case, you'd see it started at 10 instead of 0). Once you find the bug, you remove the debug print statements.

### Try it yourself

Take the buggy code from the "Think about it" section earlier. Add print statements inside and outside the loop to understand why it's not executing. What do you observe?

## Introduction to IDE Debuggers (VS Code)

![image.png](attachment:b3fbdc0e-8016-4f55-8b8b-1edb09538678:image.png)

While print statements are useful, Integrated Development Environments (IDEs) like Visual Studio Code (VS Code) have built-in debugging tools that are much more powerful. They allow you to:

1. **Set Breakpoints:** Mark lines in your code where you want the execution to pause.
2. **Step Through Code:** Execute your code line by line (`Step Over`), step into functions (`Step Into`), or step out of functions (`Step Out`).
3. **Inspect Variables:** Examine the values of variables at any point while the code is paused.
4. **Watch Expressions:** Monitor specific variables or expressions as the code executes.
5. **View the Call Stack:** See the sequence of function calls that led to the current point in the code.

Using a debugger lets you observe your program's state in detail without cluttering your code with temporary print statements.

## Setup

1. **VS Code:** Ensure you have VS Code installed and the Python extension is enabled. You should already have this from previous lessons.
    
2. **Basic Python File:** Create a simple Python file (e.g., `debugger_test.py`) with the following code:
    
    ```python
    def add_numbers(a, b):
        result = a + b
        return result
    
    x = 5
    y = 10
    sum_result = add_numbers(x, y)
    
    print(f"The sum of {x} and {y} is: {sum_result}")
    
    if sum_result > 10:
        print("The result is greater than 10.")
    else:
        print("The result is not greater than 10.")
    
    print("Finished!")
    ```
    
3. **Practice Setting a Breakpoint:**
    
    - Open `debugger_test.py` in VS Code.
        
    - Click in the gutter (the space to the left of the line numbers) next to the line `result = a + b` inside the `add_numbers` function. A red dot should appear – this is a breakpoint.
        
        ![Screenshot 2025-06-14 at 16.23.28.png](attachment:f41bfdda-ccff-4e0c-abad-1d473d25b095:Screenshot_2025-06-14_at_16.23.28.png)
        
    - Click in the gutter next to the line `print(f"The sum of {x} and {y} is: {sum_result}")`. Add another breakpoint here.
        
4. **Run with Debugger:**
    
    - Go to the "Run and Debug" view in VS Code (usually looks like a play button with a bug icon on the left sidebar).
        
        ![Screenshot 2025-06-14 at 16.28.20.png](attachment:ec6a8378-388a-4843-9ddb-5ce657fe6f20:Screenshot_2025-06-14_at_16.28.20.png)
        
    - Click the "Run and Debug" button (it might ask you to select a configuration, choose "Python File").
        
    - Observe that the execution pauses at the first breakpoint inside the `add_numbers` function.
        
    - Explore the Debug view: Look at the "Variables" panel to see the values of `a` and `b`. Use the controls at the top (Continue, Step Over, Step Into, Step Out) to control execution. Press "Continue" (the play icon) to run until the next breakpoint. Press "Continue" again to finish execution.
        

Familiarize yourself with setting breakpoints and stepping through this simple script. We will explore the debugger in more detail during the live session.