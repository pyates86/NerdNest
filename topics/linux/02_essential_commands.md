# Chapter 2: Essential Linux Commands

In the Linux world, the command line is your primary interface. While a GUI (Graphical User Interface) is fine for casual use, the **CLI (Command Line Interface)** allows for speed, precision, and automation.

In this chapter, we cover the "Navigation and Manipulation" basics that every engineer must have in their muscle memory.

---

## 2.1 Navigation: Moving Around
Before you can work on files, you need to know where you are.

* **`pwd` (Print Working Directory):** Shows the full path of the directory you are currently in.
* **`ls` (List):** Lists the files and folders in your current directory.
    * `ls -l`: Lists with "long" details (size, owners, permissions).
    * `ls -a`: Shows hidden files (those starting with a `.`).
* **`cd` (Change Directory):** Moves you between folders.
    * `cd /`: Go to the root directory.
    * `cd ~`: Go to your home directory.
    * `cd ..`: Move up one level.

---

## 2.2 File Operations: Creating and Moving
In Linux, creating and organizing files is done through a few core verbs.

* **`mkdir` (Make Directory):** Creates a new folder.
    * `mkdir -p project/src/bin`: Creates the entire nested path at once.
* **`touch`:** Creates an empty file or updates the timestamp of an existing one.
* **`cp` (Copy):** Copies files or directories.
    * `cp file.txt backup.txt`
    * `cp -r folder/ backup_folder/` (The `-r` stands for recursive, needed for folders).
* **`mv` (Move):** Moves or **renames** a file. 
    * `mv old_name.txt new_name.txt` (Renaming).
    * `mv file.txt /tmp/` (Moving).
* **`rm` (Remove):** Deletes a file.
    * **Warning:** There is no "Trash Can" in the CLI. Once you `rm`, it is gone.
    * `rm -rf folder/`: Forcefully and recursively deletes a folder and everything in it. **Use with extreme caution.**

---

## 2.3 Reading Files: Peeking Inside
You don't always need to open a full editor like Vim to see what is in a file.

* **`cat` (Concatenate):** Dumps the entire contents of a file into your terminal.
* **`head` / `tail`:** Shows the first or last 10 lines of a file.
    * `tail -f log.txt`: "Follows" the file, updating your screen in real-time as new lines are added (essential for debugging).
* **`less`:** Opens a file in a searchable, scrollable view that doesn't clutter your terminal history. Use `q` to quit.

---

## 2.4 Finding Things
When you're working in a large codebase, finding a file or a string of text is a daily task.

* **`find`:** Searches for files based on name, size, or time.
    * `find . -name "*.py"`: Find all Python files in the current directory and subdirectories.
* **`grep` (Global Regular Expression Print):** Searches for text *inside* files.
    * `grep "error" server.log`: Finds every line containing the word "error".

---

## 🛠 Hands-on: Terminal Parkour
Try this sequence in your terminal to practice the commands above:

1.  **Create a playground:** `mkdir -p ~/linux_practice/sandbox`
2.  **Enter it:** `cd ~/linux_practice/sandbox`
3.  **Create a file:** `touch notes.txt`
4.  **Write to it (quick way):** `echo "Hello Linux" > notes.txt`
5.  **Read it:** `cat notes.txt`
6.  **Rename it:** `mv notes.txt readme.md`
7.  **Check your work:** `ls -l`
8.  **Clean up:** `cd .. && rm -rf sandbox`

---

> **Note:** Now that you can move and manage files, you need to be able to edit them properly. In **Chapter 3: Mastering the Vim Editor**, we will learn how to write and edit code without ever leaving the terminal.
