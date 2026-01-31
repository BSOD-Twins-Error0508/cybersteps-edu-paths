Welcome to the world of file handling in Python! So far, most of the data you've worked with (like variables) disappears when your script finishes running. Files allow you to store data persistently, meaning it stays saved even after your program closes, and you can read data created by other programs or stored previously. This is essential for many real-world applications, from saving user preferences to processing large datasets or logs.

## What are Files?

![image.png](attachment:e50d12bc-5934-47a8-85bb-501bf78f0cec:image.png)

At its core, a file is just a named location on your computer's storage (like a hard drive or SSD) where data is stored. You interact with files constantly: text documents, images, music, program code – they are all files. Python provides built-in ways to interact with these files programmatically.

## Opening Files

Before you can read from or write to a file in Python, you need to "open" it. This establishes a connection between your script and the file on the disk. The primary tool for this is the built-in `open()` function.

The `open()` function typically takes two arguments:

1. **File Path:** A string specifying the location and name of the file (e.g., `"my_document.txt"` or `"/Users/yourname/Documents/report.txt"`).
2. **Mode:** A string indicating how you want to interact with the file (read, write, append, etc.).

```python
# Example: Opening a file named "hello.txt" in read mode
file_object = open("hello.txt", "r")
# ... do something with the file ...
file_object.close() # Don't forget to close it!
```

## File Modes

The "mode" tells Python what you intend to do with the file. Here are the most common modes:

- `'r'` - **Read Mode:** (Default) Opens the file for reading. If the file doesn't exist, it raises a `FileNotFoundError`. The file pointer is placed at the beginning of the file.
- `'w'` - **Write Mode:** Opens the file for writing. **Crucially, if the file already exists, its contents are deleted!** If the file doesn't exist, it creates a new one.
- `'a'` - **Append Mode:** Opens the file for appending. Any data written to the file is automatically added to the end. If the file doesn't exist, it creates a new one.
- `'b'` - **Binary Mode:** This is added to other modes (e.g., `'rb'`, `'wb'`). It tells Python to handle the file as raw bytes rather than text (useful for images, executables, etc.). We'll mostly focus on text files for now.
- `'+'` - **Update Mode:** This can be added to other modes (e.g., `'r+'`, `'w+'`, `'a+'`) to allow both reading and writing.

### Think about it

What do you think might happen if you try to open a file in `'r'` mode, but the file doesn't actually exist on your computer? What about if you open an existing file in `'w'` mode?

## Reading from Files

Once a file is opened in read mode (`'r'` or `'r+'`), you can read its contents using several methods:

- `read()`: Reads the entire content of the file and returns it as a single string. Be careful with very large files, as this loads everything into memory.
- `readline()`: Reads a single line from the file, including the newline character (`\\n`) at the end. Each time you call it, it reads the next line.
- `readlines()`: Reads all lines from the file and returns them as a list of strings, where each string is a line including its newline character.

```python
# Assume "example.txt" contains:
# Line 1
# Line 2
# Line 3

# Using read()
file = open("example.txt", "r")
content = file.read()
print("--- Using read() ---")
print(content)
file.close()

# Using readline()
file = open("example.txt", "r")
print("--- Using readline() ---")
line1 = file.readline()
print(f"Line 1: {line1.strip()}") # .strip() removes leading/trailing whitespace like \\n
line2 = file.readline()
print(f"Line 2: {line2.strip()}")
file.close()

# Using readlines()
file = open("example.txt", "r")
lines = file.readlines()
print("--- Using readlines() ---")
print(lines) # Output: ['Line 1\\n', 'Line 2\\n', 'Line 3']
for i, line in enumerate(lines):
    print(f"Line {i+1}: {line.strip()}")
file.close()
```

## Writing to Files

To write data, open the file in write (`'w'`) or append (`'a'`) mode.

- `write(string)`: Writes the given string to the file. It does _not_ automatically add a newline character. You need to include `\\n` if you want lines separated.
- `writelines(list_of_strings)`: Writes each string from the list to the file. Like `write()`, it does _not_ add newlines automatically.

```python
# Writing using write()
file = open("output.txt", "w") # Opens (or creates) output.txt and clears it
file.write("Hello there!\\n")   # Add \\n for a new line
file.write("This is the second line.")
file.close() # Content is saved when closed

# Appending using writelines()
lines_to_add = ["\\nThird line.", "\\nFourth line."] # Need \\n here too
file = open("output.txt", "a") # Open in append mode
file.writelines(lines_to_add)
file.close()
```

### Try it yourself

1. Create a new Python file (e.g., `file_practice.py`).
2. Write code to create a new text file named `my_notes.txt`.
3. Write three lines of text into `my_notes.txt`. Make sure each line appears on a new line in the actual file.
4. Close the file.
5. Now, write code to open `my_notes.txt` again, read its entire content, and print it to the console.
6. Close the file.
7. Run your Python script and then check if `my_notes.txt` was created and contains the text you wrote.

## Closing Files: The Importance of `close()`

When you're finished with a file, it's crucial to close it using the `file_object.close()` method. Why?

1. **Flushing the Buffer:** When you write to a file, the changes might not be saved to the disk immediately. Python often buffers the output (holds it in memory temporarily) for efficiency. Closing the file ensures that all buffered data is written ("flushed") to the disk. If your program crashes before closing, you might lose data.
2. **Releasing Resources:** Operating systems limit the number of files a program can have open simultaneously. Closing files releases these resources. Leaving many files open unnecessarily can cause problems.

## The `with` Statement: The Preferred Way

Forgetting to close a file is a common mistake. Python provides a cleaner, safer way to handle files using the `with`statement. It automatically takes care of closing the file, even if errors occur within the block.

```python
# Using 'with' for reading
try:
    with open("example.txt", "r") as file:
        content = file.read()
        print("--- Reading with 'with' ---")
        print(content)
    # File is automatically closed here, even if errors happened inside the 'with' block
except FileNotFoundError:
    print("Error: example.txt not found!")

# Using 'with' for writing
lines_to_write = ["First line\\n", "Second line\\n"]
try:
    with open("new_output.txt", "w") as file:
        file.writelines(lines_to_write)
        # Maybe some error happens here? File will still be closed.
    # File is automatically closed here
    print("Successfully wrote to new_output.txt")
except IOError: # A more general error for I/O problems
    print("Error: Could not write to file.")
```

Using `with` is strongly recommended for file operations in Python. It makes your code more readable and robust.

### Think about it

Why is using the `with` statement generally safer than manually calling `open()` and `close()`? What kind of problems does it help prevent?

## File Paths

When you specify a filename like `"my_notes.txt"`, Python looks for (or creates) the file in the _current working directory_. This is usually the directory where you ran your Python script from.

You can also use:

- **Relative Paths:** Paths relative to the current directory (e.g., `"data/input.csv"`, `"../scripts/config.txt"`).
- **Absolute Paths:** Full paths starting from the root directory (e.g., `"/Users/yourname/Documents/project/data.txt"` on macOS/Linux or `"C:\\\\Users\\\\yourname\\\\Documents\\\\project\\\\data.txt"` on Windows). Note the double backslashes `\\\\`needed in Windows strings, or use _raw strings_ like `r"C:\\Users\\yourname\\..."`.

Using relative paths often makes your code more portable, as it doesn't depend on specific user directory structures. The `os` module (which you might have seen in the Modules lesson preview or will see soon) has helpful functions for working with paths (like `os.path.join()` to create paths correctly across different operating systems).

That covers the basics of file handling! You're now ready to read data from files and save your program's results persistently.

<aside> 📌

The slides for the live session can be viewed here: [https://gamma.app/docs/Python-12-Files-kxscmlqiylwf3kg?mode=doc](https://gamma.app/docs/Python-12-Files-kxscmlqiylwf3kg?mode=doc)

Try not to peek before class - spoilers inside!

</aside>