Write a Python program that calculates the area of a rectangle.

1. Ask the user for the length of the rectangle. The prompt must be exactly: `Enter length:`
2. Ask the user for the width of the rectangle. The prompt must be exactly: `Enter width:`
3. Calculate the area by multiplying the length and width. **Important:** You will need to convert the input values (which are text) into integer numbers using `int()` before performing the multiplication.
4. Print the result formatted exactly as: `The area is: [Area]` where `[Area]` is the calculated area.

```
length = int(input("Enter length: "))

width = int(input("Enter width: "))

area = length * width

print("The area is:", area)
```