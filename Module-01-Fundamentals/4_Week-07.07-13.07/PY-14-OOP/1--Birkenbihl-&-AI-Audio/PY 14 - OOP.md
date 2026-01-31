Welcome! Before our live session on Object-Oriented Programming (OOP), please go through this material. Understanding these concepts will help you get the most out of our class.

## What is Object-Oriented Programming?

```python
class Dog:
    def __init__(self, name):
        self.name = name

    def bark(self):
        print(f"{self.name} says woof!")

dog1 = Dog("Buddy")
dog1.bark()
```

Up until now, you've likely been writing Python code in a _procedural_ way. You write sequences of instructions, perhaps organizing reusable pieces into functions. This works well for many tasks, but as programs become larger and more complex, managing them can become difficult.

Object-Oriented Programming (OOP) is a different way of thinking about and structuring your code. Instead of focusing primarily on procedures (functions), OOP focuses on _objects_.

Think about the real world. It's full of objects: cars, dogs, computers, network packets, log entries, user accounts. Each of these objects has:

1. **State:** Characteristics or data associated with the object (e.g., a car has a color, make, and model; a log entry has a timestamp, source IP, and message).
2. **Behavior:** Actions the object can perform or actions that can be performed on it (e.g., a car can start, accelerate, and brake; a log entry can be parsed or filtered).

OOP allows us to model these real-world (or conceptual) objects directly in our code. We create blueprints for objects, define their state and behavior, and then create and interact with instances of those objects.

Why use OOP?

- **Organization:** Groups related data and functions together, making code easier to understand, manage, and maintain.
- **Reusability:** Allows you to define object blueprints (called classes) once and reuse them to create multiple objects. You can also reuse code through mechanisms like inheritance (which we might touch upon later).
- **Modularity:** Objects are often self-contained, making it easier to work on different parts of a program independently.
- **Modeling:** Provides a natural way to model complex systems and real-world entities. In cybersecurity, this could be modeling things like network connections, security alerts, malware samples, or configuration settings.

## Core Concepts

Let's break down the fundamental building blocks of OOP in Python.

### Classes

A **class** is like a blueprint or template for creating objects. It defines the properties (state) and actions (behavior) that all objects created from that class will share. You define a class using the `class` keyword.

```python
# Example of a simple class definition
class Dog:
    # This is a special method called the constructor (more on this soon)
    def __init__(self, name, breed):
        # These are attributes (state)
        self.name = name
        self.breed = breed

    # This is a method (behavior)
    def bark(self):
        print(f"{self.name} says Woof!")
```

In this blueprint:

- `Dog` is the name of the class (by convention, class names start with a capital letter).
- `__init__` is a special method called the _constructor_. It's automatically called when you create a new object from the class. It's used to initialize the object's state. The `self` parameter refers to the specific object being created.
- `name` and `breed` are _attributes_. They store the data associated with a specific dog object. We assign the values passed during creation to `self.name` and `self.breed`.
- `bark` is a _method_. It defines an action that a `Dog` object can perform. Notice it also takes `self` as its first parameter, allowing the method to access the object's attributes (like `self.name`).

### Objects (Instances)

An **object** (also called an **instance**) is a specific entity created from a class. If `Dog` is the blueprint, then individual dogs like Fido, Rex, or Luna are the objects created _from_ that blueprint. Each object has its own set of attribute values.

You create an object by calling the class name as if it were a function, passing any arguments required by the `__init__`method:

```python
# Creating objects (instances) of the Dog class
my_dog = Dog("Fido", "Golden Retriever")
your_dog = Dog("Rex", "German Shepherd")
```

Now, `my_dog` and `your_dog` are two distinct `Dog` objects.

### Attributes

**Attributes** are variables that belong to an object. They represent the object's state or data. You access an object's attributes using dot notation (`object.attribute`).

```python
print(f"My dog's name is: {my_dog.name}")  # Output: My dog's name is: Fido
print(f"Your dog's breed is: {your_dog.breed}") # Output: Your dog's breed is: German Shepherd

# You can also modify attributes (if appropriate)
my_dog.name = "Buddy"
print(f"My dog's new name is: {my_dog.name}") # Output: My dog's new name is: Buddy
```

Each object maintains its own values for its attributes. Changing `my_dog.name` does not affect `your_dog.name`.

### Methods

**Methods** are functions that belong to an object. They define the object's behavior or actions. You call an object's methods using dot notation (`object.method()`).

```python
# Calling methods on the objects
my_dog.bark()  # Output: Buddy says Woof!
your_dog.bark() # Output: Rex says Woof!
```

When you call `my_dog.bark()`, the `bark` method defined in the `Dog` class is executed _for the `my_dog` object_. The `self`parameter inside the `bark` method automatically refers to `my_dog` in this case, allowing it to access `my_dog.name`. Similarly, when `your_dog.bark()` is called, `self` refers to `your_dog`.

### The `self` Parameter

The `self` parameter is crucial. It's the first parameter of instance methods (including `__init__`) within a class definition. It represents the specific instance (object) on which the method is being called. Python passes the object itself automatically as the first argument when you call a method using dot notation (e.g., `my_dog.bark()` implicitly passes `my_dog` as `self` to the `bark` method). You must include `self` in the method definition to access the object's attributes and other methods.

### Think about it

Consider a simple cybersecurity scenario: analyzing log entries. How could you represent a single log entry using a class? What attributes (state) would a `LogEntry` object need? What methods (behavior) might be useful? (e.g., timestamp, source IP, message, severity? A method to check if it's an error?)

### Try it yourself

1. Open your Python interpreter or create a new `.py` file in VS Code.
2. Copy the `Dog` class definition from above.
3. Create two different `Dog` objects with different names and breeds.
4. Print the name of the first dog.
5. Call the `bark` method on the second dog.
6. Try changing the breed of the first dog and print its new breed.

```python
# Starter code for you to complete:

class Dog:
    def __init__(self, name, breed):
        self.name = name
        self.breed = breed

    def bark(self):
        print(f"{self.name} says Woof!")

# --- Your code below ---

# 1. Create dog_one (e.g., name "Lassie", breed "Collie")

# 2. Create dog_two (e.g., name "Bolt", breed "White Shepherd")

# 3. Print the name of dog_one

# 4. Call the bark method on dog_two

# 5. Change dog_one's breed to "Rough Collie"

# 6. Print dog_one's new breed

```

## Summary

Object-Oriented Programming helps structure code by modeling real-world or conceptual entities as objects.

- **Class:** A blueprint defining attributes (state) and methods (behavior).
- **Object (Instance):** A specific item created from a class, with its own attribute values.
- **Attribute:** Data/variable belonging to an object. Accessed via `object.attribute`.
- **Method:** Function belonging to an object, defining its actions. Called via `object.method()`.
- **`__init__`:** The constructor method, used to initialize a new object's state.
- **`self`:** Refers to the specific object instance within its class methods.

This is just the beginning of OOP. In our live session, we'll dive deeper into more advanced topics.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Python-14-OOP-nugmu8basprwo5b?mode=doc](https://gamma.app/docs/Python-14-OOP-nugmu8basprwo5b?mode=doc)

Try not to peek before class - spoilers inside!

</aside>