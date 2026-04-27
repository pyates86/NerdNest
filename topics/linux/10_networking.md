# Chapter 10: Networking & SSH

Linux is the backbone of the internet. Whether you are deploying a web app, managing a database, or configuring a cloud instance, you are working with the Linux networking stack. In this chapter, we cover how to identify your system on a network, troubleshoot connections, and securely log into remote servers.

---

## 10.1 Identifying Your System
Before you can connect to anything, you need to know your own "address."

* **`ip addr`**: The modern way to show your IP addresses and network interfaces (replaces the older `ifconfig`).
    * Look for `eth0` (Ethernet) or `wlan0` (Wi-Fi).
    * **Loopback (`lo`):** The address `127.0.0.1` refers to "localhost" (your own machine).
* **`hostname -I`**: A quick way to see only your internal IP addresses.
* **`curl ifconfig.me`**: A trick to find your **Public IP** (how the outside world sees you).

---

## 10.2 Connectivity Troubleshooting
When "the internet is down," these tools help you find where the pipe is broken.

* **`ping <address>`**: Sends a tiny packet to a server to see if it responds. It tests basic connectivity and latency.
* **`dig <domain>`**: Used to look up DNS records. It tells you which IP address a domain name (like google.com) points to.
* **`traceroute <address>`**: Shows every "hop" (router) your data passes through to reach its destination.
* **`nmcli`**: The Network Manager Command Line Interface—used to manage Wi-Fi and Ethernet connections on modern distros.

---

## 10.3 Ports and Sockets
Applications communicate through **Ports**. Think of the IP address as the building and the Port as the specific door.

* **Common Ports:**
    * `22`: SSH (Secure Shell)
    * `80`: HTTP (Web)
    * `443`: HTTPS (Secure Web)
* **`ss -tulpn`**: Shows all "listening" ports on your machine. Essential for seeing if your web server or database is actually running.

---

## 10.4 SSH: Secure Shell
**SSH** is the standard way to log into a remote Linux server. It encrypts the entire session, so your password and data remain private.

### Basic Connection
```bash
ssh username@remote-ip-address
```

### SSH Keys (The "Pro" Way)
Passwords are easy to brute-force. Engineers use **SSH Keys** (public/private key pairs) for better security and password-less logins.

1.  **Generate a key:** `ssh-keygen -t ed25519`
2.  **Copy to server:** `ssh-copy-id username@remote-ip`
3.  **Connect:** Now, when you run `ssh`, it uses the key to authenticate you automatically.

---

## 10.5 Transferring Files
* **`scp` (Secure Copy):** Move files over SSH.
    * `scp local_file.txt user@remote:/home/user/`
* **`rsync`:** A smarter version of `scp` that only copies the *differences* between files. It is the gold standard for backups and deployments.
    * `rsync -avz local_folder/ user@remote:/backup/`

---

## 🛠 Hands-on: Remote Diagnostics
Try these commands to explore your network:

1.  **Find your local IP:** `ip addr | grep "inet "`
2.  **Test DNS:** `dig github.com`
3.  **Check if a website is alive:** `curl -I https://www.google.com` (The `-I` shows just the headers).
4.  **See what's listening:** `sudo ss -tulpn` (Look for port 22—that's your SSH service).

---

> **Note:** Networking is how we reach the server, but once we are there, we need to install software. In **Chapter 11: Package & Service Management**, we will learn how to manage software life cycles and background services.
