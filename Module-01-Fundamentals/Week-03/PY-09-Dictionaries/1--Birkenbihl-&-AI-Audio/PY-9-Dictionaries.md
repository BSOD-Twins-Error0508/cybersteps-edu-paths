Welcome! In previous lessons, you learned about lists, which are ordered sequences of items. Now, we'll explore another fundamental Python data structure: **dictionaries**. Dictionaries are incredibly useful for storing and retrieving data based on a unique identifier, much like looking up a word in a real dictionary or finding a phone number in a contact list.

## What is a Dictionary?

```python
myDict = {"hey": "there", "abc": 123, 456: ["word", -0.5]}
```

Think about a real-world dictionary. You look up a _word_ (the key) to find its _definition_ (the value). Python dictionaries work similarly. They store data as **key-value pairs**.

- **Key**: A unique identifier used to look up data. Keys must be _immutable_ types, meaning they cannot be changed after creation. Common immutable types include strings, numbers (integers, floats), and tuples (if they contain only immutable elements). You cannot use lists or other dictionaries as keys.
- **Value**: The data associated with a key. Values can be of _any_ data type (strings, numbers, lists, other dictionaries, etc.).

Unlike lists, dictionaries are **unordered** (or, more accurately, insertion order is preserved in recent Python versions, but you shouldn't rely on this for accessing elements like you do with list indices). You access values using their specific keys, not by their position or index number.

## Creating Dictionaries

You can create dictionaries in a couple of ways:

1. **Using Curly Braces `{}`**: This is the most common way.
    
    ```python
    # An empty dictionary
    empty_dict = {}
    
    # A dictionary of student grades
    student_grades = {
        "Alice": 85,
        "Bob": 92,
        "Charlie": 78
    }
    
    # A dictionary describing a user profile
    user_profile = {
        "username": "coder123",
        "level": 5,
        "interests": ["Python", "Cybersecurity"],
        "is_active": True
    }
    
    print(student_grades)
    print(user_profile)
    ```
    
2. **Using the `dict()` constructor**: This can be useful for creating dictionaries from other sequences or keyword arguments.
    
    ```python
    # From keyword arguments
    settings = dict(theme="dark", font_size=12, notifications_enabled=True)
    print(settings)
    
    # From a list of key-value tuples (less common)
    pairs = [('item', 'laptop'), ('quantity', 1)]
    inventory_item = dict(pairs)
    print(inventory_item)
    ```
    

### Try it yourself

- Create an empty dictionary called `my_contacts`.
- Create a dictionary called `book_details` containing the keys "title" (string), "author" (string), and "pages" (integer) with appropriate values. Print the `book_details` dictionary.

## Accessing Values

To get the value associated with a specific key, you use square brackets `[]` with the key inside:

```python
student_grades = {"Alice": 85, "Bob": 92, "Charlie": 78}

alices_grade = student_grades["Alice"]
print(f"Alice's grade is: {alices_grade}") # Output: Alice's grade is: 85

bobs_grade = student_grades["Bob"]
print(f"Bob's grade is: {bobs_grade}")   # Output: Bob's grade is: 92
```

**What if the key doesn't exist?**

If you try to access a key that isn't in the dictionary using square brackets, Python will raise a `KeyError`.

```python
# This will cause an error!
davids_grade = student_grades["David"] # Raises KeyError: 'David'
```

**Safer Access with `.get()`**

To avoid errors, you can use the `.get()` method. It returns the value for the key if it exists, or `None` (by default) if it doesn't. You can also provide a default value to return instead of `None`.

```python
student_grades = {"Alice": 85, "Bob": 92, "Charlie": 78}

# Get Alice's grade (exists)
alices_grade = student_grades.get("Alice")
print(f"Alice's grade (using get): {alices_grade}") # Output: Alice's grade (using get): 85

# Try to get David's grade (doesn't exist)
davids_grade = student_grades.get("David")
print(f"David's grade (using get): {davids_grade}") # Output: David's grade (using get): None

# Try to get David's grade with a default value
davids_grade_default = student_grades.get("David", "Not found")
print(f"David's grade (with default): {davids_grade_default}") # Output: David's grade (with default): Not found
```

### Try it yourself

- Using the `book_details` dictionary you created earlier, print the value associated with the "author" key.
- Try to access the value for a key named "genre" using square brackets `[]`. Observe the error.
- Now, access the value for "genre" using the `.get()` method. Print the result.
- Access the value for "genre" using `.get()`, but provide a default value of "Unknown". Print the result.

## Adding and Updating Items

Adding a new key-value pair or updating the value of an existing key is done using the square bracket assignment syntax:

```python
student_grades = {"Alice": 85, "Bob": 92}
print(f"Original grades: {student_grades}")

# Add a new student
student_grades["David"] = 88
print(f"After adding David: {student_grades}")

# Update Bob's grade
student_grades["Bob"] = 95
print(f"After updating Bob: {student_grades}")
```

If the key already exists, its value is overwritten. If the key doesn't exist, the new key-value pair is added.

### Try it yourself

- Add a new key-value pair "published_year": 1997 to your `book_details` dictionary.
- Update the "pages" value in `book_details` to a new number.
- Print the final `book_details` dictionary.

## Removing Items

There are several ways to remove items from a dictionary:

1. **`del` keyword**: Removes the item with the specified key. Raises a `KeyError` if the key doesn't exist.
    
    ```python
    settings = {"theme": "dark", "font_size": 12, "auto_save": True}
    print(f"Settings before del: {settings}")
    del settings["auto_save"]
    print(f"Settings after del: {settings}")
    # del settings["nonexistent_key"] # Would cause KeyError
    ```
    
2. **`.pop(key)` method**: Removes the item with the specified key _and returns its value_. Raises a `KeyError` if the key doesn't exist, unless you provide a default return value.
    
    ```python
    settings = {"theme": "dark", "font_size": 12, "auto_save": True}
    print(f"Settings before pop: {settings}")
    removed_value = settings.pop("font_size")
    print(f"Settings after pop: {settings}")
    print(f"Removed value: {removed_value}")
    
    # Pop a non-existent key with a default value
    removed_default = settings.pop("language", "English")
    print(f"Removed non-existent key (with default): {removed_default}")
    # removed_error = settings.pop("language") # Would cause KeyError
    ```
    
3. **`.popitem()` method**: Removes and returns the _last inserted_ key-value pair as a tuple. In older Python versions (before 3.7), it removed an arbitrary pair. Raises a `KeyError` if the dictionary is empty.
    
    ```python
    settings = {"theme": "dark", "font_size": 12, "auto_save": True}
    print(f"Settings before popitem: {settings}")
    last_item = settings.popitem()
    print(f"Settings after popitem: {settings}")
    print(f"Removed item: {last_item}") # Output might be ('auto_save', True)
    ```
    

### Try it yourself

- Create a dictionary `user_prefs = {"theme": "dark", "fontSize": 12, "notifications": True}`.
- Remove the "fontSize" item using `del`.
- Remove the "notifications" item using `.pop()` and print the removed value.
- Print the final `user_prefs` dictionary.

## Checking for Keys

You can easily check if a key exists in a dictionary using the `in` operator:

```python
student_grades = {"Alice": 85, "Bob": 92, "Charlie": 78}

if "Alice" in student_grades:
    print("Alice is in the dictionary.")
else:
    print("Alice is not in the dictionary.")

if "David" not in student_grades:
    print("David is not in the dictionary.")
else:
    print("David is in the dictionary.")
```

## Useful Dictionary Methods

Dictionaries have several built-in methods to work with their contents:

- **`.keys()`**: Returns a _view object_ containing all the keys in the dictionary.
- **`.values()`**: Returns a _view object_ containing all the values in the dictionary.
- **`.items()`**: Returns a _view object_ containing all the key-value pairs as tuples `(key, value)`.

View objects are dynamic – they reflect changes made to the dictionary. You can easily convert them to lists if needed.

```python
settings = {"theme": "dark", "font_size": 12, "auto_save": True}

keys = settings.keys()
values = settings.values()
items = settings.items()

print(f"Keys: {keys}")       # Output: Keys: dict_keys(['theme', 'font_size', 'auto_save'])
print(f"Values: {values}")   # Output: Values: dict_values(['dark', 12, True])
print(f"Items: {items}")     # Output: Items: dict_items([('theme', 'dark'), ('font_size', 12), ('auto_save', True)])

# Convert to lists
key_list = list(keys)
value_list = list(values)
item_list = list(items)

print(f"Key list: {key_list}")     # Output: Key list: ['theme', 'font_size', 'auto_save']
print(f"Value list: {value_list}") # Output: Value list: ['dark', 12, True]
print(f"Item list: {item_list}")   # Output: Item list: [('theme', 'dark'), ('font_size', 12), ('auto_save', True)]

# You often use these methods in loops (which we'll cover more in class)
print("\\nIterating through items:")
for key, value in settings.items():
    print(f"  Key: {key}, Value: {value}")
```

### Think about it

- When would using a dictionary be more advantageous than using a list? Think about scenarios where you need to look up information quickly based on a specific identifier rather than its position.

That's the basics of Python dictionaries! Spend some time experimenting with the examples above in VS Code. Having a good grasp of these concepts will prepare you well for the live session where we'll dive deeper and see how dictionaries are used in practice.