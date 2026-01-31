Welcome! Before our live session on Data Encoding, please go through this material. We'll explore how computers represent information, focusing on text and binary data. Understanding this is fundamental to many areas of computing and cybersecurity.

## What is Data Encoding?

At their core, computers only understand numbers, specifically binary numbers (0s and 1s). Data encoding is the process of converting information (like text, images, or other data) into a specific format, often binary, so that computers can store, process, and transmit it. Conversely, decoding is translating that format back into a human-readable or usable form.

Think of it like Morse code – dots and dashes represent letters, allowing communication over telegraph wires. Similarly, data encodings use patterns (often of bits) to represent different kinds of information within computer systems.

## Binary Basics Recap

From our previous lesson on Numeral Systems, you'll remember that computers use the binary system (base-2). Each digit in binary is called a **bit**, and it can be either a `0` or a `1`. Eight bits together form a **byte**.

For example:

- The decimal number `65` is represented in binary as `01000001`.
- The decimal number `97` is represented in binary as `01100001`.

Computers use these binary patterns to represent everything. But how do they represent letters, symbols, and other characters we use every day?

## Character Encoding: Giving Meaning to Bits

To represent text, computers need a standard way to map characters (like 'A', 'b', '!', '?') to specific binary numbers. This mapping is called **character encoding**. Without a standard encoding, one computer might interpret `01000001` as 'A', while another might think it's 'Z', leading to chaos!

### ASCII: The Grandfather of Character Sets

One of the earliest and most influential character encoding standards is **ASCII** (American Standard Code for Information Interchange).

- **Structure:** Standard ASCII uses 7 bits to represent characters. Since 7 bits can represent 2^7=128 different values (0 to 127), ASCII defines mappings for these numbers.
- **Content:** It includes:
    - Uppercase and lowercase English letters (A-Z, a-z)
    - Digits (0-9)
    - Common punctuation symbols (!, @, #, $, etc.)
    - Control characters (like newline, tab, backspace – these aren't printed but control how text is displayed or processed).
- **Example:**
    - The character 'A' is assigned the decimal value 65, which is `01000001` in binary.
    - The character 'a' is assigned the decimal value 97, which is `01100001` in binary.
    - The character '!' is assigned the decimal value 33, which is `00100001` in binary.

### Try it yourself

Most systems have an ASCII table available. On macOS or Linux, you can often use the `man ascii` command in your terminal to view it. Find the ASCII decimal and binary values for:

- Your first initial (uppercase)
- The '$' symbol
- The space character

### ASCII's Limitations

ASCII was revolutionary, but it was designed primarily for English. It has no way to represent characters from other languages (like German umlauts ä, ö, ü, French accents é, à, ç, or characters from Greek, Cyrillic, Chinese, Japanese, etc.). This limitation became a major problem as computing became global.

### Unicode and UTF-8: The Universal Solution

![image.png](attachment:6aba3115-d009-4a04-8b38-1f2b9401e1b2:image.png)

To address ASCII's limitations, **Unicode** was developed.

- **Concept:** Unicode is a _universal character set_ that aims to assign a unique number (called a **code point**) to _every character_ in _every language_, plus symbols, emojis, and more. It defines over 149,000 characters!
- **Encoding Forms:** Unicode itself is just the standard mapping characters to code points. To store or transmit these code points as binary data, we need an _encoding form_. The most common one by far is **UTF-8** (Unicode Transformation Format - 8-bit).
- **UTF-8:**
    - **Variable-Width:** UTF-8 is clever because it uses a variable number of bytes per character.
        - For characters that are also in the original ASCII set (code points 0-127), UTF-8 uses just **one byte**, identical to the ASCII representation. This makes it backward compatible with ASCII!
        - For characters outside the ASCII range (like '€', 'ü', 'é', '猫'), UTF-8 uses **two, three, or even four bytes**.
    - **Dominance:** UTF-8 is the dominant character encoding on the Web and in most modern systems because of its universality and backward compatibility with ASCII.

### Think about it

- Why is backward compatibility with ASCII a significant advantage for UTF-8?
- What problems might occur if a file saved using UTF-8 encoding is mistakenly opened as if it were encoded in plain ASCII?

## Base64 Encoding: Representing Binary Data as Text

Sometimes, we need to send or store binary data (like images, compiled programs, or compressed files) in systems that are designed primarily for text (like email or some web protocols). These systems might misinterpret certain byte values found in raw binary data, corrupting the data.

**Base64** is an encoding scheme designed to solve this problem. It translates _any_ binary data into a sequence of printable ASCII characters.

- **Purpose:** To make binary data safe for transmission over text-only channels.
- **Mechanism (Simplified):**
    1. It takes the binary data stream three bytes (24 bits) at a time.
    2. It divides these 24 bits into four 6-bit chunks.
    3. Each 6-bit chunk can represent 2^6=64 different values (0-63).
    4. These 64 values are mapped to a specific set of 64 printable ASCII characters: `A-Z`, `a-z`, `0-9`, `+`, and `/`.
    5. If the original binary data isn't a multiple of three bytes, padding characters (`=`) are added at the end of the Base64 output to make the total length a multiple of four characters.
- **Important:** Base64 is an **encoding**, not **encryption**. It's easily reversible (decoded) by anyone who knows it's Base64. It provides _no_ confidentiality or security, only a way to safely represent binary data in text environments.

### Example

Let's encode the 3-byte ASCII string "Man":

1. ASCII: 'M' = 77, 'a' = 97, 'n' = 110
2. Binary (8 bits per char): `01001101 01100001 01101110` (24 bits total)
3. Split into 6-bit chunks: `010011` `010110` `000101` `101110`
4. Decimal value of chunks: 19, 22, 5, 46
5. Map to Base64 characters (0=A, 1=B, ..., 25=Z, 26=a, ..., 51=z, 52=0, ..., 61=9, 62=+, 63=/):
    - 19 -> 'T'
    - 22 -> 'W'
    - 5 -> 'F'
    - 46 -> 'u'
6. Result: "TWFu"

### Try it yourself

Use an online Base64 encoder/decoder (search for "Base64 encode online").

1. Encode the text: `Hello World!`
2. Decode the text: `UEMgaXMgZnVuIQ==` (What does it say?)

### Think about it

- Why is it crucial to understand that Base64 is not encryption, especially in cybersecurity?
- Can you think of situations where sending binary data directly might cause problems in text-based systems?

That's it for the pre-class preparation! Come to the live session ready to discuss these concepts and see them in action.