# Linux File System

The Linux file system follows a hierarchical structure (starting at the root (`/`) directory) with specific directories serving distinct purposes. Below is a list of the standard top-level directories in a Linux file system, along with a brief summary of their roles, based on the Filesystem Hierarchy Standard (FHS).

## / (Root Directory)

* **Summary**: The top-level directory of the file system, containing all other directories and files. It serves as the starting point for the entire hierarchy.  
* **Contents**: Subdirectories like `/bin`, `/etc`, `/home`, and mount points for other file systems.

## /bin (Binaries)

* **Summary**: Contains essential executable binary files (commands) required for system operation, accessible to all users.  
* **Contents**: Common utilities like `ls`, `cp`, `mv`, `cat`, and `bash`.  
* **Note**: Critical for system boot and repair.

## /sbin (System Binaries)

* **Summary**: Stores system administration binaries used by the root user for system maintenance and boot processes.  
* **Contents**: Commands like `fsck`, `reboot`, `ifconfig`, and `init`.  
* **Note**: Typically requires elevated privileges.

## /etc (Configuration Files)

* **Summary**: Holds system-wide configuration files for applications and services.  
* **Contents**: Files like `/etc/passwd` (user accounts), `/etc/fstab` (file system mounts), and `/etc/hosts` (network hosts).  
* **Note**: Text-based and editable by administrators.

## /home (User Home Directories)

* **Summary**: Contains personal directories for users to store their files, settings, and data.  
* **Contents**: Subdirectories like `/home/username` with user-specific files (e.g., documents, `.bashrc`).  
* **Note**: Root’s home is typically `/root`, not in `/home`.

## /root (Root User Home)

* **Summary**: The home directory for the root user, storing its configuration files and data.  
* **Contents**: Similar to `/home` but exclusive to the root account.  
* **Note**: Restricted access to prevent unauthorized changes.

## /var (Variable Data)

* **Summary**: Stores variable data that changes during system operation, such as logs, caches, and temporary files.  
* **Contents**: Subdirectories like `/var/log` (logs), `/var/cache` (cached data), `/var/spool` (print/mail queues).  
* **Note**: Often grows in size over time.

## /tmp (Temporary Files)

* **Summary**: A directory for temporary files created by applications and users, typically cleared on reboot.  
* **Contents**: Short-lived files, such as temporary downloads or session data.  
* **Note**: Usually world-writable with sticky bit permissions.

## /usr (User Programs)

* **Summary**: Contains user-installed software, libraries, and documentation, not essential for system boot.  
* **Contents**:  
  * `/usr/bin`: User-executable binaries (e.g., `gcc`, `python`).  
  * `/usr/lib`: Libraries for programs.  
  * `/usr/share`: Architecture-independent data (e.g., documentation, icons).  
* **Note**: Read-only in many setups.

## /lib (Libraries)

* **Summary**: Stores essential shared libraries and kernel modules required by `/bin` and `/sbin` binaries.  
* **Contents**: Dynamic libraries (e.g., `libc.so`) and kernel modules (e.g., `/lib/modules`).  
* **Note**: May have subdirectories like `/lib64` on 64-bit systems.

## /opt (Optional Software)

* **Summary**: Used for optional or third-party software packages not managed by the system’s package manager.  
* **Contents**: Self-contained applications (e.g., `/opt/google-chrome`).  
* **Note**: Common for proprietary or custom software.

## /boot (Boot Loader Files)

* **Summary**: Contains files required for the system boot process, including the kernel and bootloader configuration.  
* **Contents**: Files like `vmlinuz` (kernel), `initrd` (initial RAM disk), and `/boot/grub` (GRUB config).  
* **Note**: Critical and sensitive; modifications can break booting.

## /dev (Device Files)

* **Summary**: Stores special files representing hardware devices and virtual devices.  
* **Contents**: Device nodes like `/dev/sda` (hard disk), `/dev/null` (null device), and `/dev/random` (random number generator).  
* **Note**: Managed by the kernel and `udev`.

## /proc (Process Information)

* **Summary**: A virtual file system providing runtime system and process information.  
* **Contents**: Files like `/proc/cpuinfo` (CPU details), `/proc/meminfo` (memory usage), and `/proc/[pid]` (process data).  
* **Note**: Not stored on disk; generated dynamically by the kernel.

## /sys (System Information)

* **Summary**: A virtual file system exposing kernel and device information, used for system management.  
* **Contents**: Files like `/sys/class` (device classes), `/sys/block` (block devices).  
* **Note**: Used by tools like `udev` and for power management.

## /mnt (Mount Points)

* **Summary**: A directory for temporarily mounting file systems, such as external drives or network shares.  
* **Contents**: Subdirectories created for mounted devices (e.g., `/mnt/usb`).  
* **Note**: Usage varies by distribution; often replaced by `/media`.

## /media (Removable Media)

* **Summary**: Used for automatically mounting removable media like USB drives or CDs.  
* **Contents**: Subdirectories like `/media/username/usb` for mounted devices.  
* **Note**: Managed by desktop environments or `udisks`.

## /run (Runtime Data)

* **Summary**: A temporary file system (`tmpfs`) for runtime data used by running processes.  
* **Contents**: Files like `/run/lock` (lock files), `/run/user` (user runtime data), and PID files.  
* **Note**: Cleared on reboot; replaces older `/var/run`.

## /srv (Service Data)

* **Summary**: Stores data for services provided by the system, such as web or FTP servers.  
* **Contents**: Directories like `/srv/www` (web server files) or `/srv/ftp` (FTP files).  
* **Note**: Usage depends on system configuration.

## /lost+found

* **Summary**: Used by file system check tools (`fsck`) to store recovered files after file system errors.  
* **Contents**: Orphaned files or fragments from corrupted file systems.  
* **Note**: Specific to certain file systems (e.g., ext4); not always present.

# Notes:

* **Filesystem Hierarchy Standard (FHS)**: Most Linux distributions adhere to the FHS, but some (e.g., Arch, Ubuntu) may introduce minor variations.  
* **Virtual File Systems**: Directories like `/proc`, `/sys`, and `/dev` are not stored on disk but are dynamically generated by the kernel.  
* **Permissions**: Access to directories like `/root`, `/boot`, or `/etc` is often restricted to the root user or specific groups.  
* **Distribution-Specific Additions**: Some distributions add custom directories (e.g., `/snap` in Ubuntu for Snap packages).

To explore these directories, you can use commands like `ls /` to list top-level directories or `man hier` to read the file system hierarchy documentation.  
