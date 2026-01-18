Welcome! In programming, we often need to repeat a block of code multiple times. Instead of writing the same code over and over again, we use loops. Loops allow us to execute a statement or a group of statements multiple times efficiently. Python provides two primary types of loops: `for` loops and `while` loops. We'll also look at ways to control the flow within loops using `break` and `continue`.

## Why Use Loops?

Imagine you need to print the numbers from 1 to 5. You could write:

```python
print(1)
print(2)
print(3)
print(4)
print(5)
```

This works, but what if you needed to print numbers from 1 to 100? Or 1 to 1,000,000? Writing a `print` statement for each number would be incredibly tedious and error-prone. Loops solve this problem by allowing you to specify the action (printing a number) and the range or condition for repetition.

## The `for` Loop

The `for` loop in Python is used for _iterating_ over a sequence (like a list, tuple, dictionary, set, or string) or other iterable object. With the `for` loop, we can execute a set of statements, once for each item in a sequence.

**Syntax:**

```python
for variable in sequence:
    # Code block to execute for each item
    # Indentation matters here!
    statement1
    statement2
    ...
```

- `variable`: In each iteration, this variable takes the value of the next item in the sequence.
- `sequence`: This is the collection of items you want to loop through (e.g., a list).
- The code block _inside_ the loop (indented) is executed for each item.

**Example: Looping Through a List**

```python
fruits = ["apple", "banana", "cherry"]
print("Available fruits:")
for fruit in fruits:
    print(f"- {fruit}")
print("Loop finished!")
```

**Output:**

```
Available fruits:
- apple
- banana
- cherry
Loop finished!
```

In this example, the `for` loop goes through the `fruits` list. In the first iteration, `fruit` is `"apple"`, and `- apple` is printed. In the second, `fruit` is `"banana"`, and `- banana` is printed. In the third, `fruit` is `"cherry"`, and `- cherry` is printed. After the last item, the loop ends, and "Loop finished!" is printed.

### The `range()` Function

Often, you want to loop a specific number of times, or loop through a sequence of numbers. The `range()` function is perfect for this. It generates a sequence of numbers.

- `range(stop)`: Generates numbers from 0 up to (but not including) `stop`.
    - `range(5)` generates `0, 1, 2, 3, 4`
- `range(start, stop)`: Generates numbers from `start` up to (but not including) `stop`.
    - `range(2, 6)` generates `2, 3, 4, 5`
- `range(start, stop, step)`: Generates numbers from `start` up to (but not including) `stop`, incrementing by `step`.
    - `range(1, 10, 2)` generates `1, 3, 5, 7, 9`

**Example: Using `range()`**

```python
# Print numbers 0 to 4
print("Numbers 0 to 4:")
for i in range(5):
    print(i)

# Print numbers 3 to 6
print("\\nNumbers 3 to 6:")
for number in range(3, 7):
    print(number)

# Print even numbers from 2 to 10
print("\\nEven numbers 2 to 10:")
for even_num in range(2, 11, 2):
    print(even_num)
```

**Output:**

```python
Numbers 0 to 4:
0
1
2
3
4

Numbers 3 to 6:
3
4
5
6

Even numbers 2 to 10:
2
4
6
8
10
```

### Try it yourself

- Write a `for` loop that prints the squares (number * number) of numbers from 1 to 5.
- Create a list of your favorite cybersecurity tools (as strings). Write a `for` loop to print each tool name.

## The `while` Loop

The `while` loop executes a set of statements as long as a specified condition is `True`. It's useful when you don't know beforehand how many times you need to loop, but you know the condition under which the loop should continue.

**Syntax:**

```python
while condition:
    # Code block to execute as long as condition is True
    # Indentation matters!
    statement1
    statement2
    ...
    # Often, you need to update variables used in the condition
    # to eventually make it False and exit the loop.
```

- `condition`: A boolean expression (evaluates to `True` or `False`). The loop continues as long as this is `True`.
- The code block inside the loop is executed repeatedly. **Crucially**, something inside the loop should eventually make the `condition` become `False`, otherwise you'll create an _infinite loop_.

**Example: Counting with `while`**

```python
count = 0
print("Counting up to 3:")
while count < 3:
    print(f"Count is: {count}")
    count = count + 1 # Increment count, crucial to avoid infinite loop!
print("Loop finished!")
```

**Output:**

```
Counting up to 3:
Count is: 0
Count is: 1
Count is: 2
Loop finished!
```

Here, the loop continues as long as `count` is less than 3. Inside the loop, we print the current value of `count` and then increment it (`count = count + 1`). When `count` becomes 3, the condition `count < 3` becomes `False`, and the loop terminates.

### Think about it

- When might you prefer a `while` loop over a `for` loop? Consider scenarios like waiting for user input or processing data until a specific marker is found.

## Controlling Loop Flow: `break` and `continue`

Sometimes you need more control over how a loop executes. Python provides two statements for this: `break` and `continue`.

### The `break` Statement

The `break` statement immediately terminates the current loop (the innermost loop if nested). Execution resumes at the first statement _after_ the loop.

**Example: Using `break`**

Let's find the first number divisible by 3 in a sequence.

```python
numbers = [1, 2, 4, 3, 5, 6]
print("Searching for the first number divisible by 3...")
for num in numbers:
    print(f"Checking {num}...")
    if num % 3 == 0: # The modulo operator (%) gives the remainder of a division
        print(f"Found it! {num} is divisible by 3.")
        break # Exit the loop immediately
print("Loop finished or broken.")
```

**Output:**

```
Searching for the first number divisible by 3...
Checking 1...
Checking 2...
Checking 4...
Checking 3...
Found it! 3 is divisible by 3.
Loop finished or broken.
```

Notice that once `num` becomes 3, the `if` condition is met, the message is printed, and `break` is executed. The loop stops immediately, and the numbers 5 and 6 are never checked.

### The `continue` Statement

The `continue` statement skips the rest of the code _inside the current iteration_ of the loop and proceeds to the next iteration.

**Example: Using `continue`**

Let's print only the even numbers from a list.

```python
numbers = [1, 2, 3, 4, 5, 6]
print("Printing even numbers:")
for num in numbers:
    if num % 2 != 0: # If the number is odd (not divisible by 2)
        continue # Skip the rest of this iteration and go to the next number
    # This print statement is only reached if the number is even
    print(num)
print("Loop finished.")
```

**Output:**

```
Printing even numbers:
2
4
6
Loop finished.
```

When `num` is 1, 3, or 5, the `if` condition `num % 2 != 0` is `True`. The `continue` statement is executed, skipping the `print(num)` line for that iteration. The loop then moves to the next number. When `num` is 2, 4, or 6, the `if` condition is `False`, `continue` is skipped, and `print(num)` is executed.

### Try it yourself

- Write a `while` loop that asks the user for input until they type "quit".
- Write a `for` loop using `range(1, 11)` that prints numbers, but skips printing the number 5 using `continue`.

## Summary

- **Loops** automate repetitive tasks.
- **`for` loops** iterate over sequences (lists, strings, `range()`, etc.). Use when you know how many times to iterate or want to process each item in a collection.
- **`while` loops** repeat as long as a condition is `True`. Use when the number of iterations is unknown beforehand. Be careful to avoid infinite loops!
- **`range(start, stop, step)`** generates sequences of numbers, often used with `for` loops.
- **`break`** exits the current loop entirely.
- **`continue`** skips the current iteration and moves to the next one.

Understanding loops is fundamental to writing effective Python code, especially in cybersecurity tasks like processing log files, scanning networks, or automating analyses. Make sure you're comfortable with these concepts before the class session!