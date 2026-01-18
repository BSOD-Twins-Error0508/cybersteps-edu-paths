Write a Python program that:

1. Prompts the user for their first name with: `"Enter your first name: "`
2. Reads the first name.
3. Prompts the user for their last name with: `"Enter your last name: "`
4. Reads the last name.
5. Creates a greeting string in the format: `"Hello, [first_name] [last_name]!"` (Make sure there's a space between the first and last name).
6. Prints the complete greeting string.

```
first_name = input("Enter your first name: ")
last_name = input("Enter your last name: ")

greets = f"Hello, {first_name} {last_name}!"

print(greets)
```