Welcome to the second lesson in Technical Foundations! In the previous lesson, you became familiar with the terminal, the command-line interface that is a fundamental tool for many tasks in IT and cybersecurity. Now, we'll focus on another essential tool: the text editor, and the related skill of using keyboard shortcuts effectively.

Whether you're writing code, configuring systems, analyzing logs, or documenting findings, you'll constantly be working with text files. Using the right editor and knowing how to use it—and your computer in general—efficiently can dramatically speed up your workflow and reduce frustration.

## What is a Text Editor?

![image.png](attachment:8c4c9a71-2e1e-4087-9cc1-285c884f7dbe:image.png)

At its core, a text editor is a program used for editing plain text files. What's "plain text"? It's text without any fancy formatting like different fonts, colors, sizes, or embedded images. Think of files ending in `.txt`, `.py` (Python code), `.sh`(shell scripts), `.conf` (configuration files), `.log` (log files), `.xml`, `.css`, `.js`, etc. These files contain only character data.

This is fundamentally different from word processors like Microsoft Word or Google Docs, which create "rich text" documents. These documents embed complex formatting information alongside the text. Trying to open a `.docx` file in a plain text editor will show you a jumble of unreadable characters because the editor doesn't understand the formatting codes. Conversely, saving code or configuration files using a word processor often adds hidden formatting that can break the code or configuration.

**Key takeaway:** For coding, configuration, and most cybersecurity tasks involving text files, always use a **plain text editor**.

## Types of Text Editors

Text editors come in various forms, broadly categorized as:

1. **Command-Line Interface (CLI) Editors:** These editors run directly within your terminal window. You interact with them using keyboard commands, not a mouse. They are essential when working on remote servers or systems without a graphical user interface (GUI).
    
    - **Nano:** A simple, beginner-friendly CLI editor. It displays helpful commands at the bottom of the screen. Often available by default on Linux and macOS.
    
    ![image.png](attachment:0bf5d8e2-98ca-4762-aaa1-87b914af1357:image.png)
    
    - **Vim (or Vi):** A very powerful but notoriously complex modal editor. It has different "modes" (e.g., insert mode for typing, normal mode for commands). Vim has a steep learning curve but is incredibly efficient once mastered. It's a favorite among many experienced developers and system administrators. Available on almost every Unix-like system.
    - **Emacs:** Another extremely powerful and extensible CLI (and GUI) editor. Often described as an operating system in itself due to its vast capabilities. Like Vim, it has a significant learning curve.
2. **Graphical User Interface (GUI) Editors:** These are standalone applications with familiar graphical elements like menus, buttons, and mouse support.
    
    - **Simple Editors:** Such as TextEdit on macOS (when set to plain text mode) or Notepad on Windows. Good for quick, basic edits, but lack features for complex tasks.
    - **Code Editors:** These are sophisticated GUI editors designed specifically for programming and development, but they are excellent for general text editing too. They offer features well beyond simple editors.

### **Sublime Text**

![image.png](attachment:0f90fc3f-dd47-4613-99c6-47b8930b068b:image.png)

This is a very popular, sophisticated, and highly regarded commercial text editor known for its speed, attractive interface, and powerful features. While it requires a license for continued use, it offers an unlimited free evaluation period. It runs on Windows, macOS, and Linux.

It provides features like:

- **Syntax Highlighting:** Displays code elements (keywords, variables, strings) in different colors for readability across many languages.
- **Command Palette:** A quick way to access most commands and settings using the keyboard.
- **Multi-Cursor / Multi-Select:**Allows editing multiple places in the file simultaneously.
- **Package Control:** An integrated package manager allowing easy installation of extensions (packages) for added functionality and language support.
- **Project Management:**Organize multiple files within a project folder.
- **High Customizability:** Themes, color schemes, key bindings, and settings can be extensively modified.

**This (Sublime Text) will be the primary editor we focus on in this program.**

### Try it yourself

1. Open your terminal (you learned this in TF1).
2. Type `nano testfile.txt` and press Enter.
3. Type a few lines of text.
4. Notice the commands at the bottom (e.g., `^X Exit`). The `^` symbol usually means the `Ctrl` key. On macOS, for `nano` specifically in the macOS terminal, it's usually `Ctrl`. Try pressing `Ctrl+X`.
5. It will ask if you want to save. Press `Y` (for Yes).
6. It will confirm the filename. Press Enter.
7. You're back at the command prompt. Type `ls` to see `testfile.txt`. Type `cat testfile.txt` to see its contents.
8. Type `rm testfile.txt` to delete the file.

This gave you a taste of a CLI editor. While powerful editors like Vim are valuable, we'll focus on the graphical Sublime Text for most of our work due to its user-friendliness and rich features suitable for learning.

## Why Efficiency Matters: The Power of Shortcuts

Imagine writing an essay by carving letters into stone versus typing on a keyboard. Both achieve the goal, but the speed and effort involved are vastly different. The same applies to editing text _and_ using your computer in general.

Manually performing actions like selecting text with the mouse, right-clicking to copy, moving the cursor, right-clicking again to paste, or navigating menus is _slow_. Keyboard shortcuts allow you to perform these common actions instantly without taking your hands off the keyboard.

Learning fundamental shortcuts is crucial for productivity in any technical field. Even saving a few seconds per action adds up significantly over hours, days, and weeks. Importantly, many shortcuts are standardized:

- **Within the Operating System:** Many shortcuts work consistently across different applications on your Mac (e.g., Copy/Paste).
- **Within Applications:** Specific applications like Sublime Text have their own powerful shortcuts for specialized tasks.

Mastering shortcuts in your primary tools (like your OS, text editor, browser, terminal) is a key part of becoming technically proficient.

**Common Shortcut Categories:**

- **Navigation:** Moving the cursor or focus (character by character, word by word, line by line, start/end of file, between applications, between tabs).
- **Selection:** Highlighting text (often by combining navigation shortcuts with the `Shift` key).
- **Editing:** Cut, Copy, Paste, Undo, Redo, Indent, Outdent.
- **File Operations:** Save, Save As, Open, New File, Close File/Window/Tab.
- **Searching:** Find, Find and Replace.
- **Application/Window Management:** Switching apps, closing apps, opening search.

## Common macOS Shortcuts to Explore

Before the class, try experimenting with these common shortcuts in different applications (like a simple text file, your browser, or Finder) to see how they work. Don't worry about memorizing them all now; the goal is to get familiar with the _concept_ and see their utility.

- `Cmd + C`: Copy selected text/item.
- `Cmd + X`: Cut selected text/item.
- `Cmd + V`: Paste copied/cut text/item.
- `Cmd + Z`: Undo the last action.
- `Cmd + Shift + Z`: Redo the last undone action.
- `Cmd + A`: Select All (e.g., all text in a document, all files in a folder).
- `Cmd + F`: Find (opens a search bar in most apps).
- `Cmd + S`: Save the current file.
- `Cmd + P`: Print.
- `Cmd + Q`: Quit the current application.
- `Cmd + W`: Close the current window or tab.
- `Cmd + T`: Open a new tab (in apps that support tabs, like browsers or Sublime Text).
- `Cmd + Tab`: Switch to the next most recently used application among your open applications. Hold `Cmd` and keep pressing `Tab` to cycle through.
- `Cmd + Space`: Open Spotlight search (useful for quickly launching apps or finding files).
- `Option + Left/Right Arrow`: Move the text cursor one word left/right.
- `Cmd + Left/Right Arrow`: Move the text cursor to the beginning/end of the current line.
- `Shift + Arrow Keys` (or `Shift + Option/Cmd + Arrow Keys`): Select text while moving the cursor.
- `Cmd + Shift + 3`: Take a screenshot of the entire screen (saved to Desktop).
- `Cmd + Shift + 4`: Take a screenshot of a selected area (cursor turns into crosshairs, click and drag).

Checkout more [Mac shortcuts](https://support.apple.com/en-il/102650)

### Think about it

- When might you _have_ to use a CLI editor like Nano or Vim instead of a GUI editor like Sublime Text?
- Beyond speed, what other benefits might come from learning keyboard shortcuts?
- **Research Task:** Open the built-in TextEdit application on your Mac (`Applications -> TextEdit`). Go to `Format -> Make Plain Text`. Now, compare this to what you see on the Sublime Text website or in descriptions/reviews online. Identify at least **one specific feature** that Sublime Text offers for editing text or code that TextEdit (in plain text mode) does not have. Be ready to share what you found.

## Setup

For this course, we will standardize on **Sublime Text** as our primary editor. Please ensure the latest version is installed on your Mac before the live session.

1. **Check if Sublime Text is installed:** Open your Applications folder (you can use Finder). Look for "Sublime Text". If it's there, double-click to launch it and make sure it opens without errors. If it opens, you're all set!
2. **Install Sublime Text (if necessary):**
    - Go to the official Sublime Text download page: [https://www.sublimetext.com/download](https://www.sublimetext.com/download)
    - Click the download link for **macOS**. This will download a `.dmg` (Disk Image) file.
    - Open your Downloads folder and find the downloaded `.dmg` file (e.g., `Sublime Text Build xxxx.dmg`).
    - Double-click the `.dmg` file. A new window will open showing the Sublime Text application icon and usually a shortcut to the Applications folder.
    - Drag the `Sublime Text` application icon into the `Applications` folder icon within that window.
    - Close the disk image window. You can also eject the "Sublime Text" disk image from Finder (like ejecting a USB drive).
    - (Optional but recommended) Launch Sublime Text from your Applications folder. You might get a security warning since you downloaded it from the internet; click "Open". Once open, right-click the Sublime Text icon in your Dock and choose `Options -> Keep in Dock` for easy access.
3. **Launch Sublime Text:** Open Sublime Text to familiarize yourself briefly with its interface. Don't worry about understanding everything yet; we'll cover the essentials in the lesson. You might see a popup mentioning it's an evaluation version; you can simply close this.

That's it for preparation! We'll dive into using Sublime Text and mastering essential shortcuts during our live session. Be ready to practice!