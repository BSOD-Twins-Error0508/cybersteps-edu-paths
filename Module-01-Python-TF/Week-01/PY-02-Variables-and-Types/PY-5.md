Write a Python program that:

1. Prompts the user for a short message with: `"Enter message: "`
2. Reads the message.
3. Prompts the user for a number of times to repeat it with: `"Repeat count: "`
4. Reads the repeat count, ensuring it's treated as a whole number.
5. Creates a new string by repeating the input message the specified number of times.
6. Prints the resulting repeated string.

```
message = input("Enter message: ")

repeat_count = int(input("Repeat count: "))

count_message = message * repeat_count

print(count_message)
```