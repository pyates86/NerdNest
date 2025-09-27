# Bash One-Liner Cheat Sheet 

Below is a **Bash One-Liner Cheat Sheet** with a wide range of practical examples for common tasks in Linux/Unix environments. These one-liners are designed to be concise, powerful, and useful for scripting, system administration, and automation. They assume you're using a Bash shell.

## File and Directory Operations

### List files with details, sorted by modification time

```bash
ls -lt  
```
Lists files in long format, sorted by modification time (newest first).

### Find all .jpg files in the current directory and subdirectories
```bash
find . -type f -name "*.jpg"  
```
Searches for .jpg files recursively.

### Create a new empty file
```bash
touch newfile.txt
```
  
Creates an empty file named newfile.txt.

### Remove a directory and its contents
```bash
rm -rf directory/
``` 
Deletes directory/ and all its contents (use with caution).

### Copy all .png files to another directory
```bash
cp *.png /path/to/destination/
```
Copies all .png files to the specified directory.

## Text Processing

### Search for a string in a file 
```bash
grep "search_term" file.txt
```
Prints lines in file.txt containing "search\_term".

### Replace text across multiple files
```bash
find . -type f -exec sed -i 's/old/new/g' {} +
```
Replaces "old" with "new" in all files in the current directory.

### Print the first 5 lines of a file
```bash
head -n 5 file.txt
```  
Displays the first 5 lines of file.txt.

### Extract unique lines from a file
```bash
sort file.txt | uniq
```
Sorts and removes duplicate lines from file.txt.

### Count the number of words in a file
```bash
wc -w file.txt
```
Counts the words in file.txt.





## System Monitoring

### Show top 10 memory-consuming processes
```bash
ps aux --sort=-%mem | head -n 11
```
Lists processes sorted by memory usage, showing the top 10 (plus header).

### Check total disk space usage
```bash
df -h  
```
Displays disk usage for all mounted filesystems in human-readable format.

### Show CPU usage in real-time
```bash
top -bn1 | head -n 5
```
Displays the top 5 CPU-using processes in batch mode.

### Check current user and hostname
```bash
echo $USER@$HOSTNAME
```
Prints the current user and hostname (e.g., user@machine).

### List all running services
```bash
systemctl --type=service --state=running
``` 
Shows all active services on a systemd-based system.




## File Manipulation

### Overwrite a file with new content
```bash
echo "new content" > file.txt
```  
Writes "new content" to file.txt, overwriting it.

### Rename all .jpeg files to .jpg
```bash
for f in *.jpeg; do mv "$f" "${f%.jpeg}.jpg"; done
```
Renames all .jpeg files to .jpg.

### Find and delete empty files
```bash
find . -type f -empty -delete
```  
Deletes all empty files in the current directory and subdirectories.

### Create a tar archive of all .pdf files
```bash
tar -cvf pdfs.tar *.pdf
```
Archives all .pdf files into pdfs.tar.

### Extract a tar archive
```bash
tar -xvf archive.tar
```
Extracts the contents of archive.tar.

## Networking

### Test connectivity to a host
```bash
ping -c 4 example.com
```
Pings example.com 4 times to check connectivity.

### Download a webpage as HTML
```bash
curl -o webpage.html https://example.com
```
Saves the HTML of example.com to webpage.html.

### Check your local IP address
```bash
ip addr show | grep inet | grep -v 127.0.0.1 | awk '{print $2}' | cut -d/ -f1
```
Displays your local IP address (excluding loopback).

### Scan for open ports on localhost
```bash
ss -tuln
```  
Lists all listening TCP/UDP ports on the local machine.

### Upload a file to a remote server via SCP
```bash
scp file.txt user@remote:/path/to/destination/
```
Copies file.txt to a remote server using SCP.

## Process Management

### Kill a process by name
```bash
killall process_name
```
Terminates all processes named "process\_name".

### Find the process using a specific port
```bash
lsof -i :80
```
Shows the process using port 80\.

### Run a command with low priority
```bash
nice -n 19 command
```
Runs "command" with the lowest CPU priority.

### List all child processes of a PID
```bash
ps --ppid 1234
```
Lists all processes spawned by PID 1234\.

### Run a command after a delay
```bash
sleep 10 && command
```
Waits 10 seconds, then runs "command".

## Environment and Shell

### Add a directory to PATH
```bash
export PATH=$PATH:/new/path
```
Adds /new/path to the PATH for the current session.

### Check the current Bash version
```bash
bash --version
```
Displays the version of Bash you're using.

### List all aliases
```bash
alias 
```
Shows all defined aliases in the current shell.

### Create a temporary alias
```bash
alias ll='ls -lh'
```
Creates an alias "ll" for ls \-lh (long listing, human-readable).

### Execute a command with a different shell
```bash
sh -c "command"
```
Runs "command" in a new sh shell.

## Search and Filter

### Find a file by content
```bash
grep -l "content" *
```
Lists files in the current directory containing "content".

### Search for a file by size (larger than 100MB)
```bash
find / -type f -size +100M
```
Finds files larger than 100MB in the filesystem.

### List only hidden files
```bash
ls -a | grep "^\."
```
Shows only hidden files (starting with a dot) in the current directory.

### Filter lines NOT containing a string
```bash
grep -v "exclude_term" file.txt
```
Prints lines in file.txt that do NOT contain "exclude\_term".

### Monitor a log file for errors in real-time
```bash
tail -f error.log | grep "ERROR"
```
Watches error.log and prints lines containing "ERROR".

## Compression and Archives

### Compress a directory into a tar.gz
```bash
tar -zcvf dir.tar.gz directory/
```
Creates a compressed tar.gz archive of directory/.

### Extract a tar.bz2 file
```bash
tar -jxvf archive.tar.bz2
``` 
Extracts the contents of archive.tar.bz2.

### Create a zip file from multiple files
```bash
zip archive.zip file1.txt file2.txt
```
Zips file1.txt and file2.txt into archive.zip.

### List contents of a zip file without extracting
```bash
unzip -l archive.zip
```
Shows the contents of archive.zip.

### Compress a file with gzip
```bash
gzip file.txt
```
Compresses file.txt into file.txt.gz.

## System Administration

### Check the last 10 system reboots 
```bash
last -x | grep reboot | head -n 10
```
Shows the last 10 reboot events.

### Show all users currently logged in
```bash
who
```
Lists all users currently logged into the system.

### Change file permissions recursively
```bash
chmod -R 755 directory/
```
Sets permissions to rwxr-xr-x for directory/ and its contents.

### Create a new user
```bash
sudo useradd -m -s /bin/bash newuser
```
Creates a new user "newuser" with a home directory and Bash shell.

### Check the status of a service
```bash
systemctl status service_name
```
Shows the status of a service (e.g., `systemctl status sshd`).



## Miscellaneous

### Generate a random number between 1 and 100
```bash
echo $((RANDOM % 100 + 1))
```
Outputs a random number between 1 and 100\.

### Execute a command if another fails
```bash
command1 || command2
```
Runs command2 only if command1 fails (e.g., ping \-c 1 google.com || echo "Failed").

### Convert a file to lowercase
```bash
tr '[:upper:]' '[:lower:]' < input.txt > output.txt
```
Converts all text in input.txt to lowercase, saving to output.txt.

### Check the current date and time
```bash
date
```
Displays the current date and time.

### Run a command on all files in a directory
```bash
for f in *; do echo "Processing $f"; done
```
Loops through all files in the current directory and processes them (e.g., prints their names).

## Tips for Using Bash One-Liners

* **Pipe (**`|`**) and Redirect (**`>`**)**: Combine commands with pipes to pass output as input, or redirect output to files.  
* **Command Substitution (**`$(...)`**)**: Use `$(command)` to capture output (e.g., `echo "Today is $(date)"`).  
* **Safety**: Test commands on non-critical data first, especially destructive ones like rm.  
* **Man Pages**: Use `man` command (e.g., `man grep`) to learn more about any command.
