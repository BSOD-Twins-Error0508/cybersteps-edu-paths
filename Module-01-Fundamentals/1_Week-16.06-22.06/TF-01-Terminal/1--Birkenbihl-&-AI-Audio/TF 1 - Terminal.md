Welcome to your first step into the world of the command line! Before our live session, please work through this material. It will introduce you to the terminal, a fundamental tool in cybersecurity and many other tech fields. Don't worry if it seems unfamiliar; we'll build on these concepts together.

## What is the Terminal?

![image.png](attachment:d1640f20-9800-4702-b52e-558a4aa76d02:image.png)

Think about how you usually interact with your computer. You probably click on icons, open windows, drag files, and use menus. This is called a **Graphical User Interface (GUI)**. It's visual and intuitive for many tasks. The **Terminal**, also known as the **Command-Line Interface (CLI)**, is a different way to interact with your computer. Instead of clicking icons, you type commands as text, and the computer responds with text output. It might look simple or even old-fashioned at first glance, but it's incredibly powerful.

- **GUI:** Uses graphics (icons, windows, menus), controlled by mouse clicks and gestures. Examples: macOS Finder, Windows Explorer, web browsers.
- **CLI (Terminal):** Uses text commands, controlled by keyboard input. Examples: macOS Terminal app, Windows Command Prompt, Linux shell.

## Why Use the Terminal?

If GUIs are so user-friendly, why bother with the text-based terminal?

- **Efficiency:** For certain tasks, typing a short command can be much faster than clicking through multiple menus and windows.
- **Automation:** You can string commands together into scripts to automate repetitive tasks. Imagine renaming 1000 files with one command!
- **Power & Control:** Some tools and settings are _only_ accessible through the terminal, giving you more direct control over the system. This is crucial in cybersecurity for analysis and system interaction.
- **Remote Access:** When connecting to other computers (like servers), you often only have terminal access.
- **Resource Light:** CLIs use fewer system resources than GUIs.

In cybersecurity, you'll constantly use the terminal to run security tools, analyze logs, manage systems, and automate processes. It's an essential skill.

## The Shell

When you open the Terminal application, you're interacting with a program called the **shell**. The shell's job is to:

1. Read the command you type.
2. Interpret what you want to do.
3. Execute the command (run the program or perform the action).
4. Display the output.

There are different types of shells (like bash, zsh, fish), but they all serve this fundamental purpose. macOS uses **zsh** by default in recent versions, which is very similar to **bash**, another common shell. For now, you don't need to worry too much about the specific shell type.

## Your First Commands: Navigating the Filesystem

Your computer organizes files and folders (also called **directories**) in a hierarchical structure, like a tree. The terminal allows you to move around this structure and see what's inside.

- **`pwd` (Print Working Directory):** Shows you exactly where you are currently located in the filesystem hierarchy. Think of it as "You are here" on a map.
    - **Try it yourself:** Open the Terminal app (see Setup below if you haven't already). Type `pwd` and press Enter. What path does it show? This is your "home" directory.
- **`ls` (List):** Lists the files and directories inside your current working directory.
    - **Try it yourself:** Type `ls` and press Enter. What files and folders do you see? These are the contents of your home directory.
- **`cd` (Change Directory):** Allows you to move to a different directory.
    - `cd <directory_name>`: Moves you _into_ the specified directory (e.g., `cd Documents`).
    - `cd ..`: Moves you _up_ one level in the hierarchy (to the parent directory).
    - `cd`: Takes you back to your home directory from anywhere.
    - `cd /`: Takes you to the root directory, the very top of the filesystem tree.
    - `cd ~`: Also takes you to your home directory (the tilde `~` is a shortcut for home).
    - **Try it yourself:**
        1. Type `ls` to see your directories. Pick one (like `Documents` or `Downloads`).
        2. Type `cd Documents` (replace `Documents` with your chosen directory) and press Enter.
        3. Type `pwd`. Notice how the path has changed?
        4. Type `ls`. See the contents of this new directory?
        5. Type `cd ..` and press Enter.
        6. Type `pwd`. Where are you now? You should be back where you started (your home directory).
        7. Try `cd /` and then `ls`. What do you see at the root?
        8. Type `cd` to get back home quickly.

## Paths: Absolute vs. Relative

When you specify a file or directory for a command like `cd`, you're using a **path**. There are two types:

- **Absolute Path:** Specifies the location starting from the root directory (`/`). It's the complete, unambiguous address. Example: `/Users/yourusername/Documents/report.txt`
- **Relative Path:** Specifies the location _relative_ to your current working directory (`pwd`). It's shorter but depends on where you are now. Example: If `pwd` shows `/Users/yourusername`, then `Documents/report.txt` refers to the same file as the absolute path above. `../Pictures` would refer to the Pictures directory, which is one level up and then down into Pictures.
    - **Think about it:** When might you prefer using an absolute path? When might a relative path be more convenient?

## Environment Variables

Environment variables are dynamic named values that can affect the way running processes will behave on a computer. They are part of the "environment" in which a process runs. Think of them as settings or configurations that programs can read.

For example, the `PATH` environment variable tells the shell which directories to search for executable programs. When you type a command like `ls`, the shell looks for an executable file named `ls` in the directories listed in your `PATH`variable.

- **`printenv` or `env`:** Displays all environment variables.
    - **Try it yourself:** Type `printenv` and press Enter. You'll see a list of variables and their values. Look for one called `HOME` (your home directory) or `USER` (your username).
- **`echo $<VARIABLE_NAME>`:** Displays the value of a specific environment variable. The `$` tells the shell to substitute the variable's name with its value.
    - **Try it yourself:** Type `echo $SHELL` and press Enter. This will show you the path to your default shell program. Try `echo $PATH`.
- **Setting Variables (Temporary):** You can set an environment variable for your current terminal session like this: `export MY_VARIABLE="hello world"`. This variable will only exist in that terminal window and will be gone when you close it.
    - **Try it yourself:**
        1. Type `export GREETING="Hello from the Terminal"` and press Enter.
        2. Type `echo $GREETING`. You should see "Hello from the Terminal".
        3. Open a _new_ Terminal window and type `echo $GREETING`. You'll see nothing, because the variable was only set in the first window.
- **Persistent Variables:** Making environment variables permanent usually involves editing shell configuration files (like `.zshrc` for zsh or `.bashrc` for bash), which is a more advanced topic we'll cover later.

Understanding environment variables is important because they control many aspects of how your system and applications behave, especially in scripting and development.

## Getting Help: `man` pages

How do you know what commands exist or what they do? Most commands come with a built-in manual page.

- **`man <command_name>` (Manual):** Displays the manual page for a command. Example: `man ls` shows you all about the `ls` command, including options (like `ls -l` for a long listing format or `ls -a` to show hidden files).
    - Press `q` to quit the manual page viewer. Use the arrow keys or spacebar to navigate within the `man` page.
    - **Try it yourself:** Type `man ls` and press Enter. Look for options like `l` and `a`. What do they do? Press `q` to exit. Now try `ls -la` in your terminal. See the difference?

## Setup: Finding and Opening the Terminal on macOS

The Terminal application is already installed on your Mac. Here's how to find it:

1. Click the Spotlight icon (the magnifying glass) in the top-right corner of your screen, or press **Command + Spacebar**.
2. Type **Terminal** in the search bar.
3. Double-click the "Terminal" application that appears.
4. A window will open with a text prompt – you're ready to type commands!

**(Optional but Recommended):** Drag the Terminal icon from the search results (or find it in Applications > Utilities) to your Dock for easy access later.

That's it for the pre-class reading! Experiment with the commands (`pwd`, `ls`, `cd`, `man`, `printenv`, `echo`) to get comfortable navigating your filesystem and understanding basic environment concepts. Don't worry about memorizing everything perfectly yet. The goal is to understand the basic concepts of what the terminal is, why it's useful, and how to perform fundamental navigation and inspection tasks.