Welcome to the world of Python lists! Before our live session, please go through this material to get familiar with the basics.

## What is a List?

```python
myList = ["hey", 123, 456, "there!"]
```

In Python, a list is a way to store multiple items in a single variable. Think of it like a shopping list where you can write down several items you need to buy. Instead of having separate variables for each item (like `item1 = "milk"`, `item2 = "eggs"`, `item3 = "bread"`), you can group them together.

Lists are:

- **Ordered:** The items in a list have a specific position, and that order stays the same unless you change it.
- **Mutable:** You can change the contents of a list after it's created – add items, remove items, or change existing items.
- **Allow Duplicates:** A list can contain the same item multiple times.

## Creating a List

You create a list by placing items inside square brackets `[]`, separated by commas.

```python
# An empty list
empty_list = []
print(empty_list)

# A list of numbers (integers)
primes = [2, 3, 5, 7, 11]
print(primes)

# A list of strings
fruits = ["apple", "banana", "cherry"]
print(fruits)

# A list with mixed data types (though often you'll keep types consistent)
mixed_list = ["hello", 100, True, 3.14]
print(mixed_list)
```

### Try it yourself

1. Create a list named `planets` containing the names of the first three planets from the sun as strings ("Mercury", "Venus", "Earth").
2. Print the `planets` list.
3. Create a list named `scores` containing three integer scores: 10, 25, and 15.
4. Print the `scores` list.

## Tuples (Immutable Lists)

In Python, a **tuple** is very similar to a list — it can store multiple items in a single variable, items can be of mixed types, and their order matters. The key difference is that tuples cannot be changed after they are created. This means you can’t add, remove, or modify elements in a tuple.

You create a tuple by placing items inside parentheses `()` instead of square brackets `[]`.

```python
# A simple tuple
coordinates = (10.0, 20.0)
print(coordinates)

# A tuple with mixed data types
person = ("Alice", 30, "Engineer")
print(person)

# A tuple with one item needs a comma!
single_item = ("hello",)
print(single_item)

```

If you try to modify a tuple, Python will raise an error:

```python
numbers = (1, 2, 3)
# This will cause an error:
# numbers[1] = 5

```

Tuples are often used for data that should **not change**, like fixed coordinates, dates, or return values from functions that naturally come as groups.

You can still **access items** in a tuple using the same indexing as with lists:

```python
person = ("Alice", 30, "Engineer")
print(person[0])  # Output: Alice
print(person[-1]) # Output: Engineer

```

### Valid Operations

Even though tuples are immutable, you can still perform some operations:

```python
colors = ("red", "green", "blue")

# Access items by index
print(colors[0])    # Output: red

# Check if an item exists
print("green" in colors)   # Output: True

# Find length
print(len(colors))         # Output: 3

# Count occurrences
print(colors.count("red")) # Output: 1

# Find index of an item
print(colors.index("blue")) # Output: 2

# Concatenate tuples
new_colors = colors + ("yellow",)
print(new_colors)

```

### Iterating Over Tuples

You can loop through a tuple just like a list:

```python
animals = ("cat", "dog", "bird")
for a in animals:
    print(a)

```

### Immutability in Practice

Tuples cannot be changed directly, but if a tuple contains a **mutable object** (like a list), that object _can_ be modified.

```python
data = (1, [2, 3], 4)
data[1].append(5)
print(data)  # Output: (1, [2, 3, 5], 4)

```

Here, the tuple itself didn’t change — it still has three elements — but one of those elements (the list) was modified internally.

### Tuple Unpacking

Tuples can be “unpacked” into separate variables in a single step.

This is one of the most powerful and convenient uses of tuples.

```python
person = ("Alice", 30, "Engineer")

name, age, job = person
print(name)  # Output: Alice
print(age)   # Output: 30
print(job)   # Output: Engineer

```

You can even swap values easily using tuple unpacking:

```python
x, y = 10, 20
x, y = y, x
print(x, y)  # Output: 20 10

```

### Tuple Operations & Methods

Tuples support a small set of methods compared to lists, since they are immutable.

Commonly used methods include:

- `count(value)` — returns how many times a value appears in the tuple
- `index(value)` — returns the index of the first occurrence of the value

Most list methods like `append()`, `remove()`, or `sort()` are **not available** for tuples.

### Common Use Cases for Tuples

Tuples are used when:

- Data should not change (e.g., days of the week, fixed coordinates).
- You want a sequence to be hashable and used as a **dictionary key**.
- You need to **return multiple values** from a function.
- You want to **unpack** multiple values conveniently.

Example:

```python
def get_position():
    return (100, 200)

x, y = get_position()
print(x, y)

```

### List vs Tuple

|Feature|List|Tuple|
|---|---|---|
|Syntax|`[]`|`()`|
|Mutability|Mutable (can be changed)|Immutable (cannot be changed)|
|Methods|Many (`append`, `remove`, `sort`, etc.)|Few (`count`, `index`)|
|Performance|Slightly slower|Slightly faster|
|Use Case|Data that changes|Data that should remain constant|

### Think about it

How are tuples similar to lists?

How are they different?

Why might you want to use a tuple instead of a list in your own code?

## Accessing Items: Indexing

Each item in a list has a position, called an **index**. Python uses **zero-based indexing**, which means the _first_ item is at index 0, the second item is at index 1, and so on.

To access an item, you use the list name followed by the index in square brackets `[]`.

```python
fruits = ["apple", "banana", "cherry"]

# Access the first item (index 0)
first_fruit = fruits[0]
print(first_fruit)  # Output: apple

# Access the third item (index 2)
third_fruit = fruits[2]
print(third_fruit)  # Output: cherry
```

Trying to access an index that doesn't exist will cause an `IndexError`.

```python
# This will cause an error because index 3 doesn't exist (indices are 0, 1, 2)
# print(fruits[3])
```

You can also use negative indices. Index `-1` refers to the _last_ item, `-2` refers to the second-to-last item, and so on.

```python
fruits = ["apple", "banana", "cherry"]

# Access the last item
last_fruit = fruits[-1]
print(last_fruit) # Output: cherry

# Access the second-to-last item
second_last_fruit = fruits[-2]
print(second_last_fruit) # Output: banana
```

### Think about it

Consider the list `letters = ["a", "b", "c", "d", "e"]`.

- What is the index of the item `"a"`?
- What is the index of the item `"e"`?
- How would you access the item `"c"` using a positive index?
- How would you access the item `"d"` using a negative index?

### Try it yourself

Using the `planets` list you created earlier (`["Mercury", "Venus", "Earth"]`):

1. Print the planet at index 1.
2. Print the last planet using a negative index.

## Modifying List Items

Because lists are mutable, you can change their contents. To change an item, you access it using its index and assign a new value.

```python
colors = ["red", "green", "blue"]
print(colors) # Output: ['red', 'green', 'blue']

# Change the item at index 1
colors[1] = "yellow"
print(colors) # Output: ['red', 'yellow', 'blue']
```

### Try it yourself

1. Create a list `numbers = [1, 2, 30, 4, 5]`.
2. Change the item at index 2 to be `3`.
3. Print the updated `numbers` list.

## Getting the Length of a List

You can find out how many items are in a list using the built-in `len()` function.

```python
fruits = ["apple", "banana", "cherry"]
num_fruits = len(fruits)
print(num_fruits) # Output: 3

empty_list = []
num_items = len(empty_list)
print(num_items) # Output: 0
```

### Think about it

If a list has a length of 5, what is the index of the first item? What is the index of the last item?

## Adding Items to a List: `append()`

One of the most common list operations is adding a new item to the _end_ of the list. You can do this using the `append()`method. A "method" is like a function that belongs to an object (in this case, the list). You call it using a dot (`.`) after the list variable.

```python
fruits = ["apple", "banana"]
print(fruits) # Output: ['apple', 'banana']

# Add "cherry" to the end
fruits.append("cherry")
print(fruits) # Output: ['apple', 'banana', 'cherry']

# Add another fruit
fruits.append("orange")
print(fruits) # Output: ['apple', 'banana', 'cherry', 'orange']
```

Notice that `append()` modifies the original list directly (it's mutable!).

### Try it yourself

1. Start with the list `tasks = ["email boss", "buy groceries"]`.
2. Append the task `"call plumber"` to the list.
3. Print the `tasks` list.
4. Print the length of the updated `tasks` list.

That's it for the pre-class preparation! We'll dive deeper into lists, explore more ways to modify them (like inserting items at specific positions and removing items), and see how they interact with loops in our live session.