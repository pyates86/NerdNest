# Chapter 4: Users, Permissions & Sudo

Linux is a multi-user operating system by design. This means the system must have a way to prevent User A from deleting User B’s files, and more importantly, prevent everyone from accidentally breaking the core Operating System.

In this chapter, we explore the Linux security model: who you are, what you can touch, and how to gain "Superpowers" when you need them.

---

## 4.1 The Three Identities
Every file and directory in Linux is assigned to three levels of ownership:
1.  **User (u):** The individual person who owns the file (usually the creator).
2.  **Group (g):** A collection of users who share specific access (e.g., the "developers" group).
3.  **Others (o):** Everyone else on the system.

---

## 4.2 Understanding `rwx` Permissions
When you run `ls -l`, you will see a string of characters like `-rwxr-xr--`. This is the permission map.



The characters stand for:
* **r (Read):** Permission to view the file's contents or list a directory's files.
* **w (Write):** Permission to modify a file or add/delete files in a directory.
* **x (Execute):** Permission to run a file as a program or "enter" a directory.

The string is broken into three triplets:
`- [rwx] [r-x] [r--]`
* The first `-` indicates it's a file (a `d` means directory).
* `rwx`: The **User** can read, write, and execute.
* `r-x`: The **Group** can read and execute.
* `r--`: **Others** can only read.

---

## 4.3 Changing Permissions: `chmod` and `chown`
To change these settings, we use two primary commands:

### `chmod` (Change Mode)
You can use letters or numbers to change permissions.
* **Symbolic:** `chmod u+x script.sh` (Adds **e**xecute permission for the **u**ser).
* **Numeric:** `chmod 755 script.sh`
    * 4 = Read, 2 = Write, 1 = Execute.
    * 7 (4+2+1) = rwx | 5 (4+1) = r-x | 5 (4+1) = r-x.

### `chown` (Change Owner)
Used to change which user or group owns a file.
* `chown alice:developers report.txt` (Changes owner to Alice and group to Developers).

---

## 4.4 Sudo: With Great Power...
The **Root User** (or "Superuser") is a special account that has total control over the system. It can read any file and delete any part of the OS. 

Because staying logged in as Root is dangerous, we use **`sudo`** (SuperUser DO).

* **Usage:** `sudo apt update`
* **Why use it?** It allows a regular user to execute a single command with root privileges. 
* **The Sudoers File:** Not every user can use `sudo`. Their username must be added to a special configuration file (usually `/etc/sudoers`).

---

## 4.5 Common Permission Pitfalls
* **Permission Denied:** You are trying to edit a system file (like a config in `/etc/`) without `sudo`.
* **Script won't run:** You created a `.sh` file but forgot to `chmod +x` it.
* **Directory Access:** To enter a directory (`cd`), you need **Execute (x)** permissions on that directory, not just Read.

---

## 🛠 Hands-on: Securing a File
Try this sequence to see permissions in action:

1.  **Create a secret file:** `touch secret.txt`
2.  **View current permissions:** `ls -l secret.txt`
3.  **Remove all access for others:** `chmod o-rwx secret.txt`
4.  **Verify:** `ls -l secret.txt` (The last three dashes should be `---`).
5.  **Try to read a root-only file:** `cat /etc/shadow` (This will fail).
6.  **Use your "Superpowers":** `sudo cat /etc/shadow` (This will work—be careful!).

---

> **Note:** Now that you can unlock the system, you need to learn how to manipulate data at scale. In **Chapter 5: Pipes, Redirection & Streams**, we will learn how to send the output of one command into another.
