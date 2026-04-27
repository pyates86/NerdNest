# Chapter 6: Bash One-Liners for Efficiency

A "One-Liner" is a powerful combination of commands compressed into a single line of code. For a Linux engineer, these are the "Swiss Army Knife" solutions to common problems. Instead of writing a complex script or manual searching, a well-crafted one-liner can process thousands of files in seconds.

---

## 6.1 System Monitoring One-Liners
Quickly check the health and status of your machine without opening heavy GUI tools.

* **Find the top 5 memory-consuming processes:**
  `ps aux --sort=-%mem | head -n 6`
* **Check disk usage in a human-readable format, sorted by size:**
  `du -sh * | sort -h`
* **Watch network connections in real-time:**
  `watch -n 1 'netstat -tulpn'`

---

## 6.2 Log Analysis & Text Processing
As a developer or admin, you will spend a lot of time digging through logs. These one-liners use `awk`, `sed`, and `grep` to extract the signal from the noise.

* **Count unique IP addresses in an access log:**
  `cat access.log | awk '{print $1}' | sort | uniq -c | sort -nr`
  *(Extracts the first column (IP), sorts them, counts unique occurrences, and sorts by highest count).*
* **Find and replace text in multiple files at once:**
  `sed -i 's/old-api-url/new-api-url/g' *.config`
* **Extract specific lines (e.g., lines 50 to 100) from a large file:**
  `sed -n '50,100p' large_file.log`

---

## 6.3 File Management One-Liners
Cleaning up directories and managing bulk files is a common chore.

* **Find and delete all files larger than 100MB:**
  `find . -type f -size +100M -exec rm -v {} \;`
* **Find all files modified in the last 24 hours:**
  `find . -mtime -1`
* **Rename all `.txt` files to `.bak` in the current folder:**
  `for f in *.txt; do mv "$f" "${f%.txt}.bak"; done`

---

## 6.4 The "Power User" Shortcuts
* **Run the last command as root (if you forgot `sudo`):**
  `sudo !!`
* **Clear your terminal history for the current session:**
  `history -c`
* **Create a quick HTTP server in any directory (Python required):**
  `python3 -m http.server 8080`

---

## 6.5 Understanding the "One-Liner" Logic
Most effective one-liners follow a standard pattern of **Filter → Process → Format**:



1.  **Filter:** Use `find` or `cat` to get the raw data.
2.  **Process:** Use `grep`, `sed`, or `awk` to isolate what you need.
3.  **Format:** Use `sort`, `uniq`, or `column` to make the data readable.

---

## 🛠 Hands-on: The Log Hunter
Imagine you have a file named `auth.log` and you want to see how many times "Failed password" appears for each user. 

1.  **Create a dummy log:**
    `echo -e "Failed password for root\nFailed password for admin\nFailed password for root" > auth.log`
2.  **Run the One-Liner:**
    `grep "Failed password" auth.log | awk '{print $NF}' | sort | uniq -c`
    * `grep` finds the failures.
    * `awk '{print $NF}'` prints the **N**umber of **F**ields (the last word in the line, which is the username).
    * `sort | uniq -c` counts the attempts.

---

> **Note:** One-liners are great for speed, but when logic becomes complex, it’s time to save it as a file. In **Chapter 7: Shell Scripting Fundamentals**, we will learn how to turn these commands into reusable programs.
