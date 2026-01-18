Write a Python program that:

1. Prompts the user for an item name with: `"Enter item name: "`
2. Reads the item name.
3. Prompts the user for the quantity of the item with: `"Enter quantity: "`
4. Reads the quantity, treating it as a whole number.
5. Prompts the user for the price per item with: `"Enter price per item: "`
6. Reads the price, treating it as a number that might have decimal places.
7. Calculates the total cost for all items.
8. Creates an output string in the format: `"[Quantity] [Item Name] cost $[Total Cost]"` (e.g., `3 Gadget cost $37.5`).
9. Prints the output string.

```
item_name = input("Enter item name: ")

quantity = int(input("Enter quantity: "))

price = float(input("Enter price per item: "))

total_cost = quantity * price

print(f"{quantity} {item_name} cost ${total_cost}")
```