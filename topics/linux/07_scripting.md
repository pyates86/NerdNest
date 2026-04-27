# Chapter 7: Shell Scripting Fundamentals

In the previous chapter, we mastered "One-Liners." These are powerful, but they are hard to remember and difficult to edit. **Shell Scripting** allows you to save those commands into a file, add complex logic (like "if this, then that"), and run them whenever you need.

A script is essentially a text file containing a sequence of commands that the shell (usually Bash) executes in order.

---

## 7.1 The Anatomy of a Script
Every Bash script should start with a **Shebang** (`#!`). This tells the operating system which interpreter to use to run the code.

```bash
#!/bin/bash

# This is a comment
echo "Starting the backup process..."
```

### Steps to Create and Run a Script:
1.  **Create the file:** `touch backup.sh`
2.  **Add the Shebang:** Open it in Vim and add `#!/bin/bash` at the top.
3.  **Add permissions:** You must make the file executable: `chmod +x backup.sh`.
4.  **Run it:** Use `./backup.sh`.

---

## 7.2 Variables: Storing Data
Variables allow you to store strings or numbers to be reused throughout your script. 
* **Note:** Do not put spaces around the `=` sign.

```bash
NAME="Server-01"
LOG_DIR="/var/log/myapp"

echo "Checking logs for $NAME in $LOG_DIR"
```

You can also store the output of a command into a variable using **Command Substitution**:
```bash
CURRENT_DATE=$(date +%Y-%m-%d)
echo "Today's date is $CURRENT_DATE"
```

---

## 7.3 Conditional Logic (If/Else)
Conditional statements allow your script to make decisions. In Bash, we use square brackets `[ ]` for tests.

```bash
FILE="config.json"

if [ -f "$FILE" ]; then
    echo "$FILE exists. Proceeding..."
else
    echo "Error: $FILE not found!"
    exit 1
fi
```
**Common Flags:**
* `-f`: Check if a file exists.
* `-d`: Check if a directory exists.
* `-z`: Check if a variable is empty.

---

## 7.4 Loops: Handling Repetition
Loops are used to perform the same action on multiple items, such as a list of files or a range of numbers.

**The For Loop:**
```bash
for FILE in *.txt; do
    echo "Backing up $FILE"
    cp "$FILE" "$FILE.bak"
done
```

---

## 7.5 Arguments: Passing Data into Scripts
You can pass data into your script when you run it using positional parameters:
* `$1`: The first argument.
* `$2`: The second argument.
* `$@`: All arguments.
* `$#`: The number of arguments.

**Example:** If you run `./script.sh hello world`, then `$1` is "hello" and `$2` is "world".

---

## 🛠 Hands-on: The System Health Reporter
Let's build a script that checks disk usage and alerts the user if it's too high.

1.  **Create the file:** `vim health_check.sh`
2.  **Paste the following code:**

```bash
#!/bin/bash

THRESHOLD=80
USAGE=$(df / | grep / | awk '{ print $5 }' | sed 's/%//')

echo "Current Disk Usage: $USAGE%"

if [ "$USAGE" -gt "$THRESHOLD" ]; then
    echo "WARNING: Disk usage is above $THRESHOLD%!"
else
    echo "Disk usage is within safe limits."
fi
```

3.  **Make it executable:** `chmod +x health_check.sh`
4.  **Run it:** `./health_check.sh`

---

> **Note:** Scripts automate the "User Space." But to understand how these scripts interact with hardware and memory, we need to go deeper. In **Chapter 8: The Linux Kernel & Architecture**, we will explore the engine that powers these commands.
