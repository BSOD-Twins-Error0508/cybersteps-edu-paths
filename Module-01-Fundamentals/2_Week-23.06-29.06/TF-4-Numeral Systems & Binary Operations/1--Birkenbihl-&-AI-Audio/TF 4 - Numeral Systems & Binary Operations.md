Welcome! Before our live session on Numeral Systems, please go through this material. Understanding how computers represent and manipulate numbers at a low level is fundamental in computing and especially crucial in cybersecurity. It's key for analyzing network traffic, understanding file formats, reverse engineering, memory forensics, and much more.

## What are Numeral Systems?

![image.png](attachment:54eacfcd-908d-4f5b-9bc5-157ac0a1ea9a:image.png)

At its core, a numeral system is simply a way of representing numbers. The system you use daily is the **decimal** system, also known as **base-10**. It uses ten digits (0-9), and the position of a digit determines its value (place value based on powers of 10).

Example:

```
654321 = (6×10⁵) + (5×10⁴) + (4×10³) + (3×10²) + (2×10¹) + (1×10⁰)
= 600000 + 50000 + 4000 + 300 + 20 + 1 = 654321
```

This concept of base and place value is crucial.

## Binary (Base-2): The Language of Computers

Computers use **binary** (base-2) because their fundamental components (transistors) exist in two states: ON (1) or OFF (0). All data—numbers, text, instructions—is ultimately stored and processed as sequences of these 1s and 0s, called **bits**. In a binary number, the **Most Significant Bit (MSB)** is the bit with the highest value position (on the left), while the **Least Significant Bit (LSB)** is the bit with the lowest value position (on the right).

Binary uses only two digits: 0 and 1. Each position represents a power of 2.

A group of 8 bits is called a **byte**, a standard unit of digital information.

![image.png](attachment:ba76f115-1665-446b-a728-2816896637df:image.png)

Example: Binary `10010110`

```
10010110 = (1×2⁷) + (0×2⁶) + (0×2⁵) + (1×2⁴) + (0×2³) + (1×2²) + (1×2¹) + (0×2⁰)
= 128 + 0 + 0 + 16 + 0 + 4 + 2 + 0
= 150 (decimal)
```

### Think about it

Computers use base-2. Humans commonly use base-10. Why might this difference sometimes lead to confusion when discussing storage sizes (like kilobytes vs. kibibytes)?

## Hexadecimal (Base-16): A Programmer's Shorthand

Binary numbers get long quickly (`11111111` is just 255 in decimal). **Hexadecimal** (base-16 or 'hex') provides a more human-friendly way to represent binary data.

Hexadecimal uses 16 symbols: 0-9 and A-F (representing decimal 10-15). Each position represents a power of 16.

|Decimal|Hex|Binary|
|---|---|---|
|...|...|...|
|10|A|1010|
|11|B|1011|
|12|C|1100|
|13|D|1101|
|14|E|1110|
|15|F|1111|

Example: Hexadecimal `2F`

```
2F = (2×16¹) + (15×16⁰)
= 32 + 15 = 47 (decimal)
```

**Why Hexadecimal is Useful**

The real power of hex is its direct relationship with binary: **one hex digit represents exactly four binary digits (a nibble)**.

- Binary `11100101` -> Split: `1110 0101` -> Convert: `E 5` -> Hex: `E5` (often written `0xE5`)

This makes it ideal for:

- **Memory Analysis:** Viewing raw memory dumps.
- **Network Packet Analysis:** Tools like Wireshark display raw packet data often in hex alongside interpretations. MAC addresses are hex. IPv6 addresses use hex.
- **Executable Code:** Examining machine code instructions.
- **Web Development:** Defining colors (e.g., `#FF0000` for Red).
- **Data Representation:** Providing a compact view of binary data in debugging and configuration files.

## Performing Conversions

Understanding how to convert between bases manually is important for grasping the concepts:

- **Binary to Decimal:** Sum the values of positions containing a '1' (powers of 2).
- **Decimal to Binary:** Find the largest power of 2 less than or equal to the number, subtract it, and repeat with the remainder, marking the corresponding binary positions with '1'.
- **Hex to Decimal:** Sum the values of each position (digit value * power of 16).
- **Decimal to Hex:** Repeatedly divide the decimal number by 16; the remainders (converted to hex digits 0-F) form the hex number, read from bottom up.
- **Binary to Hex:** Group binary digits into sets of 4 (starting from the right), and convert each group to its corresponding hex digit (0-F).
- **Hex to Binary:** Convert each hex digit to its 4-bit binary equivalent.

**Using Tools for Conversion**

While manual conversion builds understanding, in practice, you'll often use tools:

- **Calculators:** Most operating systems include a calculator with a "Programmer" or "Scientific" mode that can perform conversions between decimal, binary, and hexadecimal. On macOS, the built-in Calculator app (Cmd+Space, type "Calculator") has a Programmer view (View > Programmer or Shift+Cmd+3).
- **Online Converters:** Numerous websites offer quick conversion tools (search for "binary to hex converter", "decimal to binary converter", etc.). Be mindful of pasting sensitive data into online tools.
- **Programming Languages:** Languages like Python have built-in functions to handle conversions (e.g., `bin()`, `hex()`, `int(x, base)`).

## Introduction to Bitwise Operations

Computers can perform operations directly on the individual bits of numbers. These **bitwise operations** are fundamental in low-level programming, networking, and cryptography.

Let's consider two 4-bit numbers: `A = 1100` (12 decimal) and `B = 1010` (10 decimal).

- **AND (`&`)**: Result bit is 1 only if _both_ input bits are 1.
    
    ```
      1100  (A)
    & 1010  (B)
    ------
      1000  (Result = 8 decimal)
    ```
    
    _Use Case:_ Masking - checking if specific bits are set (e.g., checking permission flags).
    
- **OR (`|`)**: Result bit is 1 if _either_ input bit is 1.
    
    ```
      1100  (A)
    | 1010  (B)
    ------
      1110  (Result = 14 decimal)
    ```
    
    _Use Case:_ Setting specific bits to 1 (e.g., granting a permission).
    
- **XOR (`^`)**: Result bit is 1 if input bits are _different_.
    
    ```
      1100  (A)
    ^ 1010  (B)
    ------
      0110  (Result = 6 decimal)
    ```
    
    _Use Case:_ Simple encryption, toggling bits, error checking. XORing a value with itself always results in 0. XORing a value with 0 leaves it unchanged.
    
- **NOT (`~`)**: Inverts all bits (0 becomes 1, 1 becomes 0). This is a unary operator (acts on one operand).
    
    ```
    ~ 1100  (A)
    ------
      0011  (Result = 3 decimal, *ignoring signed representation for now*)
    ```
    
    _Note:_ The actual decimal result depends on how negative numbers are handled (see below).
    

**Bitwise operation table**

| X | Y | X&Y | X|Y | X^Y | ~X | | --- | --- | --- | --- | --- | --- | | 0 | 0 | 0 | 0 | 0 | 1 | | 0 | 1 | 0 | 1 | 1 | 1 | | 1 | 0 | 0 | 1 | 1 | 0 | | 1 | 1 | 1 | 1 | 0 | 0 |

- **Shift Operations (`<<`, `>>`)**: Move bits left or right.
    - `1100 << 1` (Left shift by 1) -> `11000` (effectively multiplies by 2)
    - `1100 >> 1` (Right shift by 1) -> `0110` (effectively divides by 2, integer division)

## Representing Negative Numbers: Two's Complement

How do computers represent negative numbers like -5 using only 1s and 0s? The most common method is **Two's Complement**.

For a fixed number of bits (e.g., 8 bits):

1. Take the positive binary representation (e.g., 5 is `00000101`).
2. Invert all the bits (NOT operation): `11111010`. This is the One's Complement.
3. Add 1: `11111010 + 1 = 11111011`. This is the Two's Complement representation of -5.

The most significant bit (the leftmost one) acts as a sign indicator: 0 for positive, 1 for negative in Two's Complement. We will explore this further in the course.

### Try it yourself

Perform the following conversions and operations manually first, then use an online converter (search for "numeral system converter" or "bitwise calculator") to verify your results.

1. Convert the decimal number 42 to binary and hexadecimal.
2. Convert the hexadecimal number `0xFACE` to binary.
3. What is the decimal result of the bitwise operation `1011 & 0101`?
4. If you have the binary number `00110100`, what is the result of left-shifting it by 2 (`<< 2`) in binary? What does this do to the decimal value?

This revised material introduces concepts you'll encounter frequently. Focus on understanding the _purpose_ of binary and hex, the basic idea of bitwise operations, and the neat mapping between hex and binary. Practice the conversions manually and using tools. We'll reinforce these in the live session!