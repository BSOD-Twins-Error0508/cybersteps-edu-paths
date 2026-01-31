Welcome to the world of Regular Expressions, often shortened to "regex" or "regexp"! This is an incredibly powerful tool for text processing, pattern matching, and data extraction. You'll find regex indispensable for a wide variety of tasks, from simple text searches to complex data manipulation across many fields. This preparation material will introduce you to the fundamental concepts.

## What are Regular Expressions?

![image.png](attachment:a1fb2f38-2e4f-416e-9e02-6c9d20549689:image.png)

At its core, a regular expression is a sequence of characters that defines a search pattern. Think of it as a highly specialized "find and replace" tool on steroids. Instead of searching for a fixed, literal string, you can search for patterns. For example, you could use a regex to find:

- All email addresses in a document.
- All IP addresses in a log file.
- All lines in a configuration file that start with a specific word.
- All strings that look like a date or a phone number.
- Specific code structures or syntax errors in program files.

## Why are they important in Cybersecurity?

In cybersecurity, regular expressions are like a digital magnifying glass and a super-fast sorting tool combined. They help professionals quickly find specific pieces of text-based information that could indicate a security issue or help in an investigation. Here’s how:

- **Finding Needles in Haystacks (Log Analysis):** Imagine searching through millions of lines of computer logs. Regex can quickly pinpoint suspicious activity, like multiple failed login attempts from the same IP address, or specific error messages that might signal an attack.
- **Spotting Bad Stuff (Intrusion Detection/Prevention):** Security systems (IDS/IPS) often use regex to define patterns of known malicious code (like viruses or malware signatures) or network traffic that looks like an attack. If data matches these "bad patterns," the system can raise an alarm or block it.
- **Validating Information (Data Validation):** When systems ask for input, like a username or an email address, regex can check if the input looks correct. This helps prevent errors and can stop some types of attacks where attackers try to submit malicious or malformed data.
- **Pulling Out Clues (Data Extraction & Forensics):** During a security investigation (digital forensics), regex can be used to extract specific artifacts from large amounts of data, such as email addresses, credit card numbers, or fragments of malicious scripts from compromised files or network captures.
- **Automating Security Tasks (Scripting):** Cybersecurity professionals often write scripts to automate repetitive tasks. Regex is a key part of these scripts for parsing command outputs, configuration files, or scan results to identify relevant security information.
- **Understanding Malware:** Analysts use regex to dissect malware code, looking for patterns like specific function calls, embedded URLs, or encryption keys that help them understand what the malware does and how to stop it.

Essentially, regex helps cybersecurity experts to efficiently sift through vast amounts of text data to identify threats, understand attacks, and protect systems.

## Testing Your Regex: Online Tools

The best way to learn and understand regular expressions is by experimenting with them. Online regex testers are fantastic for this. They let you type a regex pattern, provide some test text, and see immediately what your pattern matches (or doesn't match!). They often provide explanations of your regex too.

For our purposes, we recommend using **[Regex101.com](http://Regex101.com)**.

**Let's get started with Regex101:**

1. **Open your web browser and navigate to [https://regex101.com/.**](https://regex101.com/.**)
2. You'll see a few main areas:
    - **REGULAR EXPRESSION field (top):** This is where you'll type your regex patterns.
    - **TEST STRING field (middle):** This is where you'll put the text you want to search within.
    - **EXPLANATION (right sidebar):** Regex101 does a great job of breaking down your pattern and explaining what each part does.
    - **MATCH INFORMATION (below TEST STRING or on the right):** This shows you what parts of your test string were matched by your regex.
    - **FLAVOR (left sidebar, often defaults to PCRE2):** Regex has different "flavors" or versions with slight variations. Python uses a flavor very similar to PCRE (Perl Compatible Regular Expressions). For now, the default PCRE2 on Regex101 is fine.

Keep Regex101 open as you go through the concepts below. Try out the examples and experiment!

## Basic Building Blocks of Regex

Regular expressions are built from a combination of literal characters and special characters called "metacharacters."

### Literal Characters

The simplest form of regex is a literal string.

- **Definition:** A literal character is a character that matches itself. For example, the regex `a` matches the letter "a", and the regex `hello` matches the string "hello".
- **Example:** If your regex is `log` and your test string is `catalog`, it will match "log".

### Try it on Regex101:

1. In the "REGULAR EXPRESSION" field on Regex101, type `cat`.
2. In the "TEST STRING" field, type: `The cat sat on the mat. The catalog was on the table.`
3. Observe how "cat" is highlighted in both "cat" and "catalog".

### Metacharacters

Metacharacters are the heart of regex power. They don't represent themselves but rather have special meanings.

### Anchors

Anchors specify the position in the string where a match must occur. They don't match actual characters but rather invisible positions.

- `^` (Caret): Matches the beginning of a line or string.
    - Example: `^Start` will match "Start of the line" but not "This is the Start".
- `$` (Dollar sign): Matches the end of a line or string.
    - Example: `end$` will match "This is the end" but not "end of the line".
- `\\b`: Matches a word boundary. A word boundary is a position between a word character (letter, digit, or underscore) and a non-word character, or at the beginning/end of a string if the first/last characters are word characters.
    - Example: `\\bcat\\b` will match "cat" in "The cat sat" but not in "catalog" or "concatenate".
- `\\B`: Matches a non-word boundary.
    - Example: `\\Bcat\\B` would match "cat" in "concatenate" but not in "the cat".

### Try it on Regex101:

1. Test string: `cat catalog\\nconcatenate cat` (where `\\n` represents a newline, or just press Enter in Regex101).
2. Try the regex `^cat`. What does it match?
3. Try `cat$`. What does it match?
4. Try `\\bcat\\b`. How is this different from just `cat`?
5. Try `\\Bcat\\B`.

### Character Classes (Character Sets)

Character classes allow you to define a set of characters you want to match at a particular position.

- `.` (Dot): Matches any single character _except_ for a newline character (by default).
    - Example: `a.c` will match "abc", "a1c", "a&c", etc., but not "a\nc".
- `[...]` (Square brackets): Matches any single character that is contained within the brackets.
    - Example: `[aeiou]` will match any lowercase vowel. `[0-9]` will match any digit. `[a-zA-Z]` will match any uppercase or lowercase letter.
    - Ranges can be specified: `[a-f0-5]` matches 'a' through 'f' or '0' through '5'.
- `[^...]` (Negated square brackets): Matches any single character that is _not_ contained within the brackets after the caret `^`.
    - Example: `[^0-9]` will match any character that is not a digit. `[^aeiou]` will match any character that is not a lowercase vowel.

### Try it on Regex101:

1. Test string: `Can you find c.t, c@t, c t, but not coat? Also numbers 123 and symbols #?!`
2. Try `c.t`. What does it match?
3. Try `c[aeiou]t`.
4. Try `[^0-9]`. What does it match? (It will match many things!)
5. Try `[0-9]`.

### Predefined Character Classes

For convenience, regex offers several predefined character classes (these are often called "shorthand character classes"):

- `\\d`: Matches any digit. Equivalent to `[0-9]`.
- `\\D`: Matches any non-digit character. Equivalent to `[^0-9]`.
- `\\w`: Matches any word character (alphanumeric characters: `a-z`, `A-Z`, `0-9`, plus underscore `_`). Equivalent to `[a-zA-Z0-9_]`.
- `\\W`: Matches any non-word character. Equivalent to `[^a-zA-Z0-9_]`.
- `\\s`: Matches any whitespace character (space, tab `\\t`, newline `\\n`, carriage return `\\r`, form feed `\\f`, vertical tab `\\v`).
- `\\S`: Matches any non-whitespace character.

### Try it on Regex101:

1. Test string: `IP: 192.168.1.1 Date: 2024-05-17 User_ID: test_user`
2. Try `\\d\\d\\d`. What does it match?
3. Try `\\w+`. (We'll cover `+` next, but for now, it means "one or more").
4. Try `\\s`. How many matches do you get?

### Quantifiers

Quantifiers specify how many times a preceding character, group, or character class must occur to be considered a match.

- (Asterisk): Matches the preceding item **zero or more** times.
    - Example: `ab*c` will match "ac" (zero 'b's), "abc" (one 'b'), "abbc" (two 'b's), etc.
- `+` (Plus sign): Matches the preceding item **one or more** times.
    - Example: `ab+c` will match "abc", "abbc", but _not_ "ac".
- `?` (Question mark): Matches the preceding item **zero or one** time. It makes the preceding item optional.
    - Example: `colou?r` will match "color" (zero 'u's) and "colour" (one 'u').
- `{n}`: Matches the preceding item exactly _n_ times.
    - Example: `\\d{3}` will match exactly three digits, like "123".
- `{n,}`: Matches the preceding item _n_ or more times.
    - Example: `\\d{2,}` will match two or more digits, like "12", "123", "1234".
- `{n,m}`: Matches the preceding item at least _n_ times but not more than _m_ times.
    - Example: `\\d{2,4}` will match "12", "123", "1234", but not "1" or "12345".

### Try it on Regex101:

1. Test string: `err error errrror file1.txt file01.txt file001.txt`
2. Try `er*or`.
3. Try `er+or`.
4. Try `file\\d{2}\\.txt`. (What does `\\.` mean here? We'll cover it under Escaping)
5. Try `err?or`.

**Greedy vs. Non-Greedy (Lazy) Matching**

By default, quantifiers like `*`, `+`, and `{n,m}` are "greedy." This means they try to match as much text as possible while still allowing the overall regex to match.

- Example (Greedy): Given the string `<div>Hello</div><div>World</div>`, the regex `<div.*>` would match the entire string `<div>Hello</div><div>World</div>` because `.*` greedily consumes everything (including the first `</div><div>`) until the very last `>` in the string.

You can make a quantifier "non-greedy" (or "lazy") by adding a `?` _after_ it (`*?`, `+?`, `{n,m}?`). A non-greedy quantifier tries to match as little text as possible.

- Example (Non-Greedy): Given the same string, `<div.*?>` would match `<div>Hello</div>` (as `.*?` matches up to the _first_ `>`). If you were to search again from the end of this match, it would then find `<div>World</div>`.

### Try it on Regex101:

1. Test string: `<b>Bold text</b> and <i>italic text</i>`
2. Try the greedy regex `<.*>`. What does it match?
3. Try the non-greedy regex `<.*?>`. What does it match now? How many matches?

### Grouping and Capturing

- `(...)` (Parentheses): Groups multiple tokens together. This has two main effects:
    
    1. **Apply quantifiers to the group:** `(ab)+` matches "ab", "abab", "ababab", etc. The `+` applies to the whole "ab" sequence.
    2. **Create a capturing group:** The text matched by the part of the regex inside the parentheses is "captured" and can be extracted or referred to later. Most regex tools number these groups starting from 1.
    
    - Example: `(\\d{3})-(\\d{3})-(\\d{4})` could match a phone number like "123-456-7890".
        - Group 1 would capture "123".
        - Group 2 would capture "456".
        - Group 3 would capture "7890".
    - Sometimes you want to group for quantification but don't need to capture. This is a "non-capturing group": `(?:...)`. Example: `(?:ab)+` groups "ab" for the `+` but doesn't create a numbered capture group for "ab".

### Try it on Regex101:

1. Test string: `ababab call 123-456-7890 or 987-654-3210`
2. Try `(ab)+`. Notice the group information in Regex101.
3. Try `(\\d{3})-(\\d{3})-(\\d{4})`. Examine the captured groups in the "MATCH INFORMATION" panel on Regex101.

### Alternation (OR)

- `|` (Pipe): Acts like an OR operator. Matches either the expression before or the expression after the pipe.
    - Example: `cat|dog` will match "cat" or "dog".
    - It's often used within groups: `^(Error|Warning):` will match lines starting with "Error:" or "Warning:". The group `(Error|Warning)` means "match 'Error' OR 'Warning'".

### Try it on Regex101:

1. Test string: `I like cats. I like dogs. I like birds.`
2. Try `cats|dogs`.
3. Try `I like (cats|birds)\\.`.

### Escaping Metacharacters

What if you want to match a character that is normally a metacharacter literally (e.g., you want to find an actual dot `.` or an asterisk `*` or a dollar sign `$`?) You need to "escape" it with a backslash `\\`.

- `\\.` matches a literal dot character.
- `\\*` matches a literal asterisk character.
- `\\^` matches a literal caret character.
- `\\$` matches a literal dollar sign character.
- `\\\\` matches a literal backslash character.
- `\\[` matches a literal `[`, `\\(` matches `(`, etc.

### Try it on Regex101:

1. Test string: `The file is main.py. Its size is 5*4KB.`
2. How would you match `main.py` literally? Try `main\\.py`.
3. How would you match `5*4`? Try `5\\*4`.

### Try it yourself (Consolidated)

Now, using [Regex101.com](http://Regex101.com), try to solve these with the string: `Report generated on 2024-03-15 by user_admin. Contact: info@example.com or support@example.org. Issue ID: #12345. Criticality: HIGH.`

1. Write a regex to match the full date (e.g., "2024-03-15").
2. Write a regex to match both email addresses.
3. Write a regex to match the Issue ID including the `#` (e.g., "#12345").
4. Write a regex to match lines starting with "Report".

### Think about it

- How would you match a line that is completely empty? (Hint: Anchors are key)
- If `.` matches any character, and  means "zero or more", what do you think `.*` would match in a greedy context? What about `.*?` in a non-greedy context?
- What's the difference between `[abc]` and `(a|b|c)`?

## Regex in Python

You've been learning Python, and it has excellent built-in support for regular expressions through the `re` module. You don't need to master this for the pre-class, but it's good to know it exists.

To use regex in Python, you would typically:

1. `import re`
2. Use functions like:
    - `re.search(pattern, string)`: Scans through a string looking for the first location where the regex pattern produces a match.
    - `re.match(pattern, string)`: Tries to apply the pattern at the start of the string.
    - `re.findall(pattern, string)`: Finds all non-overlapping matches of the pattern in the string and returns them as a list of strings.
    - `re.finditer(pattern, string)`: Similar to `findall`, but returns an iterator yielding match objects.
    - `re.sub(pattern, replacement, string)`: Replaces occurrences of the pattern in the string with a replacement.

Example:

```python
import re

text = "My phone number is 123-456-7890."
pattern = r"\\d{3}-\\d{3}-\\d{4}" # r"" denotes a raw string, good for regex

match = re.search(pattern, text)
if match:
  print(f"Found phone number: {match.group(0)}") # group(0) is the whole match
```

We'll explore the `re` module more in practical exercises later. For now, focus on understanding the regex patterns themselves using tools like Regex101.

## Regex Flavors

It's important to know that while the core concepts of regex are quite standard, there can be slight variations in syntax or available features between different programming languages, command-line tools (like `grep`, `sed`), or text editors. These variations are often referred to as "regex flavors" (e.g., PCRE - Perl Compatible Regular Expressions, POSIX BRE - Basic Regular Expressions, POSIX ERE - Extended Regular Expressions).

[Regex101.com](http://Regex101.com) allows you to select different flavors in its settings (usually on the left sidebar). Python's `re` module is very similar to PCRE. For this course, we'll focus on this widely used PCRE-like syntax.

## Pre-Class Exploration Task

Your main task before the live session is to get comfortable with the basic regex concepts by actively experimenting.

1. **Ensure you have [Regex101.com](http://Regex101.com) open.**
2. **Go back through each metacharacter type explained above (Anchors, Character Classes, Quantifiers, etc.).**
3. For each concept:
    - Read the explanation.
    - Look at the examples provided.
    - **Crucially, type the example regex and test strings into Regex101 yourself.**
    - Modify the examples slightly. What happens if you change a quantifier? What if you add a character to a class?
    - Pay attention to the "EXPLANATION" panel in Regex101 to see how it interprets your pattern.
4. **Attempt the "Try it yourself (Consolidated)" challenges above.** Don't worry if you don't get them perfect, the goal is to try and learn from the process.
5. **Reflect on the "Think about it" questions.** Try to formulate answers or even test your ideas on Regex101.

This hands-on experimentation is the best way to start building an intuition for how regular expressions work. There's no specific software to install for this pre-class beyond using your web browser.

This concludes your pre-class preparation. You should now have a foundational understanding of what regular expressions are, their basic components, and, most importantly, how to start testing and building them using an online tool.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Technical-Foundations-12-Regular-Expressions-h1m4hzotogj3689?mode=doc](https://gamma.app/docs/Technical-Foundations-12-Regular-Expressions-h1m4hzotogj3689?mode=doc)

Try not to peek before class - spoilers inside!

</aside>