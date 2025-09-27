# Linux Terminal Commands Cheatsheet

This cheatsheet covers essential Linux terminal commands for file management, system monitoring, permissions, networking, package management, and more. Use it as a quick reference for navigating and managing Linux systems efficiently.

**NOTE:** Many of the commands below can be ran without additional parameters, e.g.; run `ls` to list files in current directory (`rm` for example needs additional operands).  To get a better understanding of how to use each command, you can use the 'help' or 'man' pages.  E.g.; `ls --help` will give you short instructions on how to use command, often including some examples of usage. Use `man ls` to get a more verbose manual of the ls command and how it is used. Therefore;

## Prerequisites
Open a Linux Terminal and run the following two commands to understand how the `help` and `man` pages work;

Firstly, run this command;

```
ls --help
```

Now run this command;

```
man ls
```

**NOTE:** You can use the space bar to move through the pages when using the `man ls` command, and use `q` to quit. 

## 1\. File and Directory Management

| Command | Description | Example |
| ----- | ----- | ----- |
| `ls` | List directory contents | `ls -la` (show all, including hidden, in long format) |
| `cd` | Change directory | `cd` /home/USER/Documents (navigate to docs folder) |
| `pwd` | Print working directory | `pwd` (show current path) |
| `mkdir` | Create a directory | `mkdir new_folder` (create new\_folder) |
| `rm` | Remove files or directories | `rm -r old_folder` (delete folder and contents recursively) |
| `cp` | Copy files or directories | `cp file.txt /backup/` (copy file.txt to backup) |
| `mv` | Move or rename files | `mv file.txt new_name.txt` (rename file) |
| `touch` | Create an empty file | `touch newfile.txt` (create newfile.txt) |
| `find` | Search for files | `find / -name "*.log"` (find all .log files) |
| `cat` | Display file contents | `cat file.txt` (show file.txt contents) |
| `less` | View file contents interactively | `less log.txt` (scroll through log.txt) |
| `grep` | Search text in files | `grep "error" log.txt` (find "error" in log.txt) |

## 2\. File Permissions

| Command | Description | Example |
| ----- | ----- | ----- |
| `chmod` | Change file permissions | `chmod 755 script.sh` (set executable for owner, read for others) |
| `chown` | Change file ownership | `chown user:group file.txt` (set user and group ownership) |
| `ls -l` | View permissions | `ls -l file.txt` (show permissions like `-rwxr-xr-x`) |

**Permissions Guide**:

`r` (read \= 4), `w` (write \= 2), `x` (execute \= 1\)

Example: `755` \= Owner (rwx \= 7), Group (rx \= 5), Others (rx \= 5\)

## 3\. System Monitoring and Processes

| Command | Description | Example |
| ----- | ----- | ----- |
| `top` | Display real-time system processes | `top` (monitor CPU, memory, processes) |
| `htop` | Interactive process viewer (if installed) | `htop` (user-friendly alternative to top) |
| `ps` | List running processes | `ps aux` (show all processes with details) |
| `kill` | Terminate a process by PID | `kill 1234` (kill process with PID 1234\) |
| `killall` | Terminate processes by name | `killall python` (kill all python processes) |
| `df` | Show disk usage | `df -h` (human-readable disk space) |
| `du` | Show directory/file size | `du -sh` /folder (size of folder in human-readable format) |
| `free` | Display memory usage | `free -m` (show memory in MB) |

## 4\. Networking

| Command | Description | Example |
| ----- | ----- | ----- |
| `ping` | Test network connectivity | `ping google.com` (check connectivity to google.com) |
| `curl` | Transfer data from/to a server | `curl -O https://example.com/file` (download file) |
| `wget` | Download files from the web | `wget https://example.com/file` (download file) |
| `netstat` | Display network connections | `netstat -tulpn` (show listening ports) |
| `ss` | Modern alternative to netstat | `ss -tuln` (show TCP/UDP ports) |
| `ifconfig` | Display network interfaces (older) | `ifconfig` (show network config) |
| `ip` | Modern network interface tool | `ip addr` (show IP addresses) |
| `ssh` | Securely connect to a remote server | `ssh user@192.168.1.100` (connect to remote server) |

## 5\. Package Management

| Command | Description | Example | System |
| ----- | ----- | ----- | ----- |
| `apt` | Manage packages (Debian/Ubuntu) | `sudo apt install vim` (install vim) | Debian/Ubuntu |
| `yum / dnf` | Manage packages (CentOS/RHEL) | `sudo dnf install httpd` (install Apache) | CentOS/RHEL |
| `pacman` | Manage packages (Arch Linux) | `sudo pacman -S python` (install python) | Arch Linux |
| `apt update` | Update package lists | `sudo apt update` (refresh package index) | Debian/Ubuntu |
| `apt upgrade` | Upgrade installed packages | `sudo apt upgrade` (update all packages) | Debian/Ubuntu |

## 6\. Text Processing and Scripting

| Command | Description | Example |
| ----- | ----- | ----- |
| `echo` | Print text or variables | `echo $PATH` (show PATH variable) |
| `sed` | Stream editor for text manipulation | `sed 's/old/new/g' file.txt` (replace “old” with “new”) |
| `awk` | Pattern scanning and processing | `awk '{print $1}' file.txt` (print first column) |
| `cut` | Extract sections from lines | `cut -d',' -f1 data.csv` (extract first column from CSV) |
| `sort` | Sort lines of text | `sort file.txt` (sort file alphabetically) |
| `uniq` | Remove duplicate lines | `uniq file.txt` (remove duplicates, requires sorted input) |
| `wc` | Count lines, words, or characters | `wc -l file.txt` (count lines in file.txt) |

## 7\. System Administration

| Command | Description | Example |
| ----- | ----- | ----- |
| `sudo` | Run a command as superuser | `sudo apt update` (run as root) |
| `whoami` | Display current user | `whoami` (show logged-in user) |
| `uptime` | Show system uptime and load | `uptime` (display system runtime) |
| `reboot` | Restart the system | `sudo reboot` (reboot server) |
| `shutdown` | Power off or schedule shutdown | `sudo shutdown -h now` (halt immediately) |
| `journalctl` | View system logs | `journalctl -u nginx` (show nginx service logs) |
| `crontab` | Schedule tasks | `crontab -e` (edit cron jobs for current user) |

## 8\. Archiving and Compression

| Command | Description | Example |
| ----- | ----- | ----- |
| `tar` | Archive files | `tar -cvf archive.tar /folder` (create tar archive) |
| `gzip` | Compress files | `gzip file.txt` (compress to file.txt.gz) |
| `gunzip` | Decompress .gz files | `gunzip file.txt.gz` (decompress file) |
| `zip` | Create zip archive | `zip archive.zip file.txt` (zip file.txt) |
| `unzip` | Extract zip archive | `unzip archive.zip` (extract files) |

## 9\. Miscellaneous

| Command | Description | Example |
| ----- | ----- | ----- |
| `man` | Display manual for a command | `man ls` (show ls command manual) |
| `history` | Show command history | `history` (list previously run commands) |
| `alias` | Create command shortcuts | `alias ll='ls -la'` (set ll as alias for ls \-la) |
| `clear` | Clear terminal screen | `clear` (refresh terminal display) |
| `env` | Display environment variables | `env` (list all variables) |

## Tips for Effective Use

* **Combine Commands**: Use pipes (`|`) to chain commands (e.g., `cat log.txt | grep "error"`).  
* **Autocomplete**: Press `Tab` to autocomplete commands or file names.  
* **Command History**: Use `↑`/`↓` arrows or `Ctrl+R` to search previous commands.  
* **Wildcards**: Use `*` for any characters (e.g., `rm *.log` deletes all .log files).  
* **Redirect Output**: Use `>` to write to a file (e.g., `ls > output.txt`) or `>>` to append.

## Common Options

* `-h`: Human-readable output (e.g., `df -h`).  
* `-r`: Recursive (e.g., `rm -r folder`).  
* `-v`: Verbose (e.g., `cp -v file.txt`).  
* `-f`: Force (e.g., `rm -f file.txt`).

