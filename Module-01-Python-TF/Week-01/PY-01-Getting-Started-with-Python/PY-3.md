Write a Python program that asks for two pieces of information and prints a summary sentence.

1. Ask the user for their first name. The prompt must be exactly: `First name:`
2. Ask the user for their favorite hobby. The prompt must be exactly: `Favorite hobby:`
3. Print a summary sentence on a single line, formatted exactly as: `Summary: [Name]'s favorite hobby is [Hobby].` where `[Name]` and `[Hobby]` are the values entered by the user.

_Hint: You can combine strings using the `+` operator or pass multiple items to the `print()` function separated by commas._

```
Name = input("First name: ")
Hobby = input("Favorite hobby: ")

print("Summary: " + Name + "'s favorite hobby is " + Hobby + ".")
# print(f"Summary: {Name}'s favorite hobby is {Hobby}")
# print("First name:", Name + "Favorite hobby:", Hobby +
# "Summary: ", Name, "'s favorite hobby is ", Hobby, ".")
```