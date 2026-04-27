# Chapter 11: Package & Service Management

In a Windows or macOS environment, you often download an `.exe` or `.dmg` file from a website to install software. In Linux, we use **Package Managers**. These are centralized systems that handle downloading, installing, and updating software from trusted "Repositories."

Once software is installed, we use **Service Managers** to ensure it starts automatically and stays running.

---

## 11.1 Package Managers: APT and DNF
Different Linux families use different package managers, but they all serve the same purpose: dependency management (ensuring all the "extra" pieces a program needs are installed too).

### Debian/Ubuntu (APT)
* **Update the list of available software:** `sudo apt update`
* **Install a package:** `sudo apt install htop`
* **Remove a package:** `sudo apt remove htop`
* **Upgrade all installed software:** `sudo apt upgrade`

### Red Hat/Fedora (DNF/YUM)
* **Install a package:** `sudo dnf install htop`
* **Remove a package:** `sudo dnf remove htop`

---

## 11.2 Understanding Repositories
A **Repository** (or "Repo") is a digital warehouse of software. When you run `apt install`, your computer looks at its list of repos (stored in `/etc/apt/sources.list`), finds the latest version of the software, and downloads it.
* **PPA (Personal Package Archive):** Sometimes you need software that isn't in the official repos. You can add a third-party PPA to get newer or specialized versions.

---

## 11.3 Managing Services with `systemd`
Most server software (like web servers or databases) needs to run in the background without a terminal window open. In modern Linux, we use **systemd** to manage these "daemons" (services).

The primary tool for this is **`systemctl`**.

* **Start a service:** `sudo systemctl start nginx`
* **Stop a service:** `sudo systemctl stop nginx`
* **Restart a service:** `sudo systemctl restart nginx`
* **Check the status:** `systemctl status nginx` (Essential for seeing if a service crashed).

### Automation: Enable vs. Start
* **Start:** Runs the service *now*, but it won't start automatically after a reboot.
* **Enable:** Ensures the service starts automatically every time the computer boots up.
* **Disable:** Prevents a service from starting at boot.

---

## 11.4 Reading Service Logs with `journalctl`
If a service fails to start, you won't see an error in your terminal; you have to look at the system logs. **`journalctl`** is the tool that collects all output from `systemd` services.

* **View logs for a specific service:**
  `journalctl -u nginx`
* **View the most recent logs in real-time:**
  `journalctl -u nginx -f`
* **See only today's logs:**
  `journalctl --since today`

---

## 🛠 Hands-on: Installing and Running a Web Server
Let's install the Nginx web server and manage its lifecycle:

1.  **Install it:** `sudo apt update && sudo apt install nginx -y`
2.  **Check if it's running:** `systemctl status nginx`
3.  **Enable it for boot:** `sudo systemctl enable nginx`
4.  **Test it:** Open your browser and go to `http://localhost`. You should see the "Welcome to nginx!" page.
5.  **Stop it:** `sudo systemctl stop nginx`
6.  **Verify it's dead:** Try refreshing the browser page. It should fail.

---

> **Note:** As you install more software and services, things will inevitably go wrong. In **Chapter 12: Linux Troubleshooting**, we will learn how to read logs, diagnose hardware issues, and fix common "system breaks."
