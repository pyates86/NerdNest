# Chapter 12: Linux Troubleshooting

Every Linux engineer eventually faces a system that won't boot, a service that won't start, or a disk that is mysteriously full. Troubleshooting is the art of following a trail of clues (logs) to find the "Root Cause." 

This chapter provides a systematic framework for diagnosing and fixing common Linux issues.

---

## 12.1 The Troubleshooting Framework
When something breaks, ask these four questions in order:
1.  **Is it a process issue?** (Is the program even running?)
2.  **Is it a resource issue?** (Is the CPU, RAM, or Disk at 100%?)
3.  **Is it a network issue?** (Can the service talk to the outside world?)
4.  **What do the logs say?** (The most important step).

---

## 12.2 Investigating the Logs
Logs are the "black box" recorder of a Linux system. Most logs are stored in text format in `/var/log`.

* **`/var/log/syslog` (or `messages`):** General system logs. Start here for mystery issues.
* **`/var/log/auth.log`:** Logs for login attempts and `sudo` usage.
* **`/var/log/dmesg`:** Kernel-level messages (hardware failures, driver issues).
* **`journalctl -xe`:** The "Emergency" command. Shows the most recent systemd errors with extra explanatory text.

---

## 12.3 High CPU or RAM Usage
If the system is sluggish, a single process might be "runaway."

* **The Fix:** 1. Run `htop` or `top`. 
    2. Press `P` to sort by CPU or `M` to sort by Memory.
    3. Identify the PID.
    4. Use `kill -15 <PID>` to stop it gracefully.

---

## 12.4 The "Disk Full" Crisis
If a disk hits 100%, services will fail to start because they cannot write temporary files or logs.

* **Identify:** `df -h` (Shows which partition is full).
* **Locate the Culprit:** `sudo du -sh /* | sort -h` (Shows which folder is consuming the most space).
* **Clean up:** Check `/var/log` for massive log files or `/tmp` for old temporary data.
* **Pro Tip:** If you delete a large log file but `df` still shows 100%, a process might still have that file "open." Restart the service to release the space.

---

## 12.5 "Permission Denied" Errors
This is the most common error for developers. It usually means one of two things:
1.  **You forgot `sudo`:** You are trying to edit a file in `/etc` or `/root`.
2.  **Incorrect Ownership:** The webserver (user `www-data`) is trying to read your files, but your files are owned by your user and have `600` (private) permissions.
    * **The Fix:** `ls -l` to check permissions, then `chmod` or `chown` accordingly.

---

## 12.6 Network "Ghost" Issues
If you can't reach a service:
1.  **Check if it's listening:** `sudo ss -tulpn | grep :80` (Replace 80 with your port).
2.  **Check the Firewall:** Linux often uses `ufw` or `iptables`. 
    * `sudo ufw status` (Is it blocking your port?)
3.  **Test Localhost:** Use `curl localhost:80`. If it works locally but not remotely, your cloud provider's firewall (Security Group) is likely the blocker.

---

## 🛠 Hands-on: Fixing a "Broken" Service
Let's simulate a failure and fix it:

1.  **Break it:** Create a typo in a config file (e.g., `/etc/nginx/nginx.conf`).
2.  **Try to restart:** `sudo systemctl restart nginx`. It will fail.
3.  **Find the error:** Run `journalctl -u nginx -n 20`. 
4.  **Read carefully:** The log will usually say something like: *"nginx: [emerg] unknown directive 'server_name_typo' in /etc/nginx/nginx.conf:24"*.
5.  **The Fix:** Open the file at line 24, fix the typo, and restart.

---

> **Note:** Troubleshooting is a skill built through experience. For more deep dives, check out **Chapter 13: Additional Resources**, where we link to advanced debugging guides and community forums.
