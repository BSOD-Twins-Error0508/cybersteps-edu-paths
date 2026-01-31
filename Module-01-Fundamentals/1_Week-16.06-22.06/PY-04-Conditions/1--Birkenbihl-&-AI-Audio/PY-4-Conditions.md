Welcome to the world of decision-making in Python! So far, our scripts have run line by line, from top to bottom. But what if we want our program to do different things based on certain situations? That's where conditions come in. They allow our code to react dynamically to different inputs or states.

## What are Conditions?

```python
if days_learning_python > 0:
	print("Keep going!")
else:
	print("It's never too late to start")
```

In programming, conditions are statements that evaluate to either true or false. Think of them like questions the program asks itself. Based on the answer (true or false), the program decides which block of code to execute next. This ability to make decisions is fundamental to creating useful and interactive programs.

## Boolean Values: The Heart of Conditions

At the core of every condition is a simple concept: **Boolean values**. A Boolean value can only be one of two things:

- `True`
- `False`

Notice the capitalization – Python is case-sensitive, so `True` and `False` must start with a capital letter. These values represent the answers to the "questions" our conditions ask.

## Asking Questions: Comparison Operators

How do we form these questions in Python? We use **comparison operators**. These operators compare two values and produce a Boolean result (`True` or `False`). Here are the most common ones:

|Operator|Meaning|Example|Result|
|---|---|---|---|
|`==`|Equal to|`5 == 5`|`True`|
|`!=`|Not equal to|`5 != 6`|`True`|
|`>`|Greater than|`10 > 5`|`True`|
|`<`|Less than|`3 < 8`|`True`|
|`>=`|Greater than or equal to|`7 >= 7`|`True`|
|`<=`|Less than or equal to|`4 <= 3`|`False`|

**Important:** Don't confuse the assignment operator (`=`) with the equality comparison operator (`==`).

- `x = 5` _assigns_ the value 5 to the variable `x`.
- `x == 5` _checks if_ the value of `x` is equal to 5 and results in `True` or `False`.

### Try it yourself

Open your Python interpreter (or create a simple `.py` file in VS Code and run it) and try out these comparisons. Use the `print()` function to see the results:

```python
print(10 == 10)
print("hello" == "world")
print(5 > 2)
age = 25
print(age >= 18)
print(age != 25)
```

## Making Decisions: The `if` Statement

The simplest way to use a condition is with an `if` statement. Its structure is:

```python
if condition:
    # Code to execute if the condition is True
    # This block MUST be indented
    print("The condition was true!")
# Code here runs regardless, as it's not indented under the if
print("This line runs anyway.")
```

1. **`if` keyword:** Starts the statement.
2. **`condition`:** An expression that evaluates to `True` or `False` (e.g., `age > 18`, `name == "Alice"`).
3. **Colon `:`:** Marks the end of the condition.
4. **Indented Block:** The code that runs _only_ if the condition is `True`. Indentation is crucial in Python; it defines code blocks. Usually, this is four spaces.

**Example:**

```python
temperature = 32
if temperature > 30:
    print("It's a hot day!")
print("Have a nice day!")
```

In this example, because `temperature` (32) is greater than 30, the message "It's a hot day!" will be printed. "Have a nice day!" will always be printed because it's not indented under the `if`.

### Think about it

What would happen in the example above if `temperature` was set to 25? Which lines would be printed?

## Handling the "Otherwise": The `else` Statement

What if you want to do something specific when the `if` condition is _not_ met? That's what `else` is for. It provides an alternative block of code.

```python
if condition:
    # Runs if condition is True
    print("Condition is True.")
else:
    # Runs if condition is False
    print("Condition is False.")
```

**Example:**

```python
user_age = 17
if user_age >= 18:
    print("Access granted.")
else:
    print("Access denied. You must be 18 or older.")
```

Here, since `user_age` (17) is not greater than or equal to 18, the condition is `False`, and the code under `else` is executed.

## Checking Multiple Conditions: The `elif` Statement

Sometimes you have more than two possibilities. You can use `elif` (short for "else if") to check additional conditions _only if_ the preceding `if` and `elif` conditions were `False`.

```python
score = 75

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
else:
    print("Grade: D")
```

Python checks the conditions in order:

1. Is `score >= 90`? No (75 is not >= 90).
2. Is `score >= 80`? No (75 is not >= 80).
3. Is `score >= 70`? Yes (75 is >= 70). Print "Grade: C" and stop checking.
4. The `else` block is skipped because a previous `elif` was `True`.

You can have multiple `elif` statements, but only one `else` at the very end, which acts as a catch-all if none of the `if` or `elif` conditions are met.

### Try it yourself

Modify the grading example above. What happens if the score is 95? What if it's 60? Predict the output, then run the code to check.

## Combining Conditions: Logical Operators

Often, you need to check if multiple conditions are true, or if at least one of several conditions is true. Logical operators help combine Boolean values:

- **`and`**: Returns `True` only if _both_ conditions on its left and right are `True`.
    
    ```python
    age = 25
    has_ticket = True
    if age >= 18 and has_ticket == True:
        print("Allowed entry.") # This will print
    ```
    
- **`or`**: Returns `True` if _at least one_ of the conditions on its left or right is `True`.
    
    ```python
    is_weekend = False
    has_holiday = True
    if is_weekend or has_holiday:
        print("Enjoy your day off!") # This will print
    ```
    
- **`not`**: Reverses the Boolean value. `not True` becomes `False`, and `not False` becomes `True`.
    
    ```python
    is_raining = False
    if not is_raining:
        print("No need for an umbrella.") # This will print
    ```
    

### Think about it

Consider this code:

```python
credits = 15
gpa = 3.0
if credits >= 12 and gpa >= 2.0:
    print("Good standing.")
else:
    print("Needs review.")

if credits < 12 or gpa < 2.0:
    print("Needs review.")
else:
    print("Good standing.")
```

Do these two `if`/`else` blocks achieve the same outcome? Why or why not? (Hint: Think about the relationship between `and` and `or` when conditions are negated).

That's the basics of conditions in Python! By understanding `if`, `elif`, `else`, comparison operators, and logical operators, you can start writing programs that make intelligent decisions.