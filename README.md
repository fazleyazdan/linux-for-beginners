# Linux for Beginners

- [Introduction](#intro)
- [📘 Chapter 1: Essential Linux Commands for Beginners](#ch1)
- [🔐 Chapter 2: Understanding Users, File Permissions, and Ownership](#ch2)
- [⚙️ Chapter 3: Process Management and Task Automation](#ch3)
- [📦 Chapter 4: Installing and Managing Software with Package Managers](#ch4)
- [🌐 Chapter 5: Networking Basics in Linux](#ch5)
- [💻 Chapter 6: Shell Scripting Basics](#ch6)
- [🪵 Chapter 7: Log Management and Troubleshooting in Linux](#ch7)
- [📦 Chapter 8: File Compression, Archiving, and Backup in Linux](#ch8)


 
---

<a id="intro"></a>

## 🚀 Who This Is For

- Beginner testers working in Linux-based CI/CD environments  
- Developers transitioning to Linux  
- Anyone who wants to improve their command-line skills

---

### What is Linux?

Linux is a powerful, open-source operating system known for its stability, flexibility, and strong community support. Unlike traditional operating systems, Linux gives you full control over how your system runs — making it the go-to choice for developers, testers, sysadmins, and cybersecurity professionals around the globe.

### Why Linux?

- 💡 **Open Source**: Completely free and customizable.
- ⚙️ **Powerful Command Line**: Gives deep control over your system and workflows.
- 🖥️ **Lightweight & Efficient**: Runs smoothly even on older machines.
- 🔐 **Security-Focused**: Less vulnerable to common malware.
- 🌐 **Widely Used in Servers, DevOps, and Cloud Environments**.

### Great for Testers & Tech Enthusiasts

- 🧪 **Test Automation**: Works seamlessly with tools like Selenium, JMeter, and Playwright.
- 📂 **Scripting**: Bash, Python, and cron jobs allow easy automation of repetitive tasks.
- 🐧 **Real-World Dev Environments**: Mimics production-like setups used in CI/CD pipelines.
- 🔍 **Network & Log Analysis**: Built-in tools like `grep`, `awk`, `top`, and `netstat` simplify troubleshooting and performance analysis.

Whether you're a QA engineer, developer, or just tech-curious — learning Linux will give you a solid edge in the tech industry.

---

<a id="ch1"></a>

## 📘 Chapter 1: Essential Linux Commands for Beginners

Linux is all about the terminal. Below are some of the most useful and beginner-friendly commands to help you navigate and manage your system.

### 📂 File & Directory Navigation

| Command                  | Description                                 |
|:-------------------------|:-------------------------------------------|
| `pwd`                    | Shows the current working directory         |
| `ls`                     | Lists files and directories                 |
| `ls -l`                  | Lists in long format (permissions, size)    |
| `cd [directory]`         | Changes to the specified directory          |
| `cd ..`                  | Moves one directory up                      |
| `mkdir [foldername]`     | Creates a new directory                     |
| `rmdir [foldername]`     | Removes an empty directory                  |
| `rm -r [foldername]`     | Removes a directory and its contents        |

##

### 📄 File Operations

| Command                        | Description                                  |
|:-------------------------------|:---------------------------------------------|
| `touch [filename]`             | Creates a new empty file                     |
| `cp [source] [destination]`    | Copies a file or directory                   |
| `mv [source] [destination]`    | Moves or renames a file or directory         |
| `rm [filename]`                | Deletes a file                               |
| `cat [filename]`               | Displays contents of a file                  |
| `nano [filename]`              | Opens a file in the Nano text editor         |
| `head -n 10 [filename]`        | Shows the first 10 lines of a file           |
| `tail -n 10 [filename]`        | Shows the last 10 lines of a file            |

##

### ⚙️ System Information & Management

| Command           | Description                              |
|:------------------|:-----------------------------------------|
| `whoami`          | Shows the current user                   |
| `uname -a`        | Displays system information              |
| `df -h`           | Shows disk usage in human-readable form  |
| `free -h`         | Shows memory usage                       |
| `top`             | Displays real-time system processes      |
| `ps aux`          | Lists all running processes              |
| `kill [PID]`      | Kills a process by its PID               |

##

### 🔍 Searching & Finding

| Command                             | Description                                   |
|:------------------------------------|:----------------------------------------------|
| `find [dir] -name [filename]`       | Finds files with a specific name              |
| `grep [pattern] [filename]`         | Searches for a pattern inside a file          |
| `history`                           | Shows command history                         |
| `clear`                             | Clears the terminal screen                    |


These commands are just the beginning, but they'll help you become comfortable in a Linux environment. As we move forward, you’ll learn more advanced techniques like scripting, permissions, and process control.

---

<a id="ch2"></a>

## 🔐 Chapter 2: Understanding Users, File Permissions, and Ownership

in Linux, everything is treated as a file — and controlling who can access or modify files is critical. This chapter introduces users, groups, file permissions, and how to manage them.

### 👤 Users & Groups

| Command            | Description                                     |
|:-------------------|:------------------------------------------------|
| `whoami`           | Displays the current logged-in user             |
| `id`               | Shows the current user ID and group info        |
| `adduser [name]`   | Adds a new user (requires sudo)                 |
| `passwd [name]`    | Sets or changes a user’s password               |
| `groupadd [group]` | Creates a new user group                        |
| `usermod -aG [group] [user]` | Adds user to a group                 | 

##

### 📄 File Ownership

| Command                  | Description                                    |
|:-------------------------|:-----------------------------------------------|
| `ls -l`                  | Shows ownership and permission details         |
| `chown [user] [file]`    | Changes file owner                             |
| `chown user:group [file]`| Changes owner and group of a file              |

##

### 🔐 File Permissions

Linux uses a 3-part permission system:

- **Owner**: User who created the file.
- **Group**: Users who are part of the file's group.
- **Others**: Everyone else.

Permissions are shown as: `-rwxr-xr--`  
Example breakdown:
- `r` = read
- `w` = write
- `x` = execute

## 

### 🔧 Modifying Permissions

| Command                   | Description                                     |
|---------------------------|-------------------------------------------------|
| `chmod +x [file]`         | Makes a file executable                         |
| `chmod 755 [file]`        | Sets specific permissions using numbers         |
| `chmod u+x [file]`        | Adds execute permission to the file owner       |
| `chmod g-w [file]`        | Removes write permission from the group         |


#### Numeric Permission Reference

| Number | Permission     |
|--------|----------------|
| 7      | read + write + execute (rwx) |
| 6      | read + write (rw-)           |
| 5      | read + execute (r-x)         |
| 4      | read only (r--)              |
| 0      | no permissions (---)         |

Example:
```bash
chmod 644 myfile.txt
# Owner: read/write, Group: read, Others: read
```

##

### 💡 Pro Tips for Testers

> - Set up restricted test users with limited permissions to validate role-based access in web or system testing.
> - Always verify that log files and test reports have appropriate read/write permissions before and after automated test runs.
> - Use `chmod +x` to ensure test scripts or automation tools are executable.
> - Use `ls -l` to debug permission issues when automated scripts fail silently.


--- 

<a id="ch3"></a>

## ⚙️ Chapter 3: Process Management and Task Automation

Linux allows you to control running processes, monitor system performance, and schedule tasks — all from the command line. In this chapter, you’ll learn how to manage processes and automate recurring tasks using tools like `cron`, `ps`, and `kill`.

### 🧠 Understanding Processes

| Command             | Description                                   |
|---------------------|-----------------------------------------------|
| `ps aux`            | Lists all running processes                   |
| `top`               | Real-time view of active processes            |
| `htop`              | Interactive version of `top` (requires install) |
| `kill [PID]`        | Sends a signal to terminate a process         |
| `kill -9 [PID]`     | Forcefully terminates a process               |
| `pkill [name]`      | Kills process(es) by name                     |
| `nice`              | Starts a process with a defined priority      |
| `renice`            | Changes the priority of a running process     |

> 💡 Use `ps aux | grep <name>` to search for a specific process.

##

### 🕒 Scheduling Tasks with Cron

`cron` is a built-in scheduler in Linux for automating repetitive tasks like backups, script execution, or system checks.

#### Crontab Basics

| Command             | Description                            |
|---------------------|----------------------------------------|
| `crontab -e`        | Edit the current user's crontab file   |
| `crontab -l`        | List current user's scheduled tasks    |
| `crontab -r`        | Remove the current crontab             |

#### Cron Format

```text
* * * * * command_to_run
│ │ │ │ │
│ │ │ │ └── Day of the week (0-7) (Sunday is both 0 and 7)
│ │ │ └──── Month (1 - 12)
│ │ └────── Day of the month (1 - 31)
│ └──────── Hour (0 - 23)
└────────── Minute (0 - 59) 
```


#### Examples

```bash
# Run every day at 2 AM
0 2 * * * /home/user/backup.sh

# Run every 10 minutes
*/10 * * * * /home/user/script.sh

# Run every Monday at 5 PM
0 17 * * 1 /home/user/monday_task.sh
```

Learning how to monitor and automate tasks helps you manage systems more efficiently and focus on what really matters. In the next chapter, we’ll dive into Package Management in Linux — installing, updating, and removing software using tools like apt, yum, and dnf.

##

### 💡 Pro Tips for Testers

> - Use `ps aux | grep [tool]` to ensure your test tools (e.g., Selenium server, JMeter) are running.
> - Automate daily regression or smoke tests using `cron` jobs — schedule them during off-hours to save time.
> - Use `kill` or `pkill` to clean up hanging processes from failed test runs.
> - Monitor CPU and memory usage with `top` while running performance tests to detect bottlenecks.

---

<a id="ch4"></a>

## 📦 Chapter 4: Installing and Managing Software with Package Managers

One of the most powerful features of Linux is its package management system — a way to easily install, update, and remove software. Different Linux distributions use different package managers, but the concept is the same.

### 🏁 Common Package Managers by Distro

| Package Manager | Used By                        |
|------------------|-------------------------------|
| `apt`            | Debian, Ubuntu                |
| `yum` / `dnf`    | CentOS, RHEL, Fedora          |
| `pacman`         | Arch Linux                    |
| `zypper`         | openSUSE                      |


### 📥 Using `apt` (Debian/Ubuntu)

| Command                              | Description                              |
|--------------------------------------|------------------------------------------|
| `sudo apt update`                    | Refreshes package list                   |
| `sudo apt upgrade`                   | Updates all installed packages           |
| `sudo apt install [package]`         | Installs a package                       |
| `sudo apt remove [package]`          | Removes a package                        |
| `sudo apt purge [package]`           | Removes package + config files           |
| `sudo apt autoremove`                | Removes unused dependencies              |
| `apt list --installed`               | Lists all installed packages             |
| `apt search [package]`               | Searches available packages              |

##

### 🔄 Using `yum` / `dnf` (RHEL/CentOS/Fedora)

| Command                              | Description                              |
|--------------------------------------|------------------------------------------|
| `sudo dnf update`                    | Updates all packages                     |
| `sudo dnf install [package]`         | Installs a package                       |
| `sudo dnf remove [package]`          | Removes a package                        |
| `dnf list installed`                 | Lists installed packages                 |
| `dnf search [package]`               | Searches for packages                    |

> `yum` is older; `dnf` is its modern replacement.

##

### 📦 Installing `.deb` or `.rpm` Files Manually

```bash
# Install a .deb file (Ubuntu/Debian)
sudo dpkg -i filename.deb

# Fix missing dependencies
sudo apt --fix-broken install

# Install an .rpm file (Fedora/CentOS)
sudo rpm -ivh filename.rpm 
```

##

### 💡Pro Tips for Testers
> - Use apt list --upgradable to know which tools or libraries might affect your test environments.
> - Tools like curl, wget, git, docker, and testing frameworks can all be installed via package managers.
> - Keep test environments lean by removing unused packages: sudo apt autoremove.

---

<a id="ch5"></a>

## 🌐 Chapter 5: Networking Basics in Linux

Networking is an essential part of working with Linux, whether you're testing APIs, debugging servers, or checking internet connectivity. This chapter covers the most useful networking commands and tools every beginner should know.

### 🌍 Viewing Network Configuration

| Command              | Description                                       |
|----------------------|---------------------------------------------------|
| `ip a`               | Shows all IP addresses and interfaces             |
| `ifconfig`           | Shows network interfaces (older, may require install) |
| `hostname -I`        | Displays the IP address of the machine            |
| `ping [host]`        | Checks connectivity with another host             |
| `traceroute [host]`  | Shows the route packets take to a host            |
| `nslookup [domain]`  | Finds the IP address of a domain                  |
| `dig [domain]`       | Performs DNS lookup (requires installation)       |

## 

### 📡 Testing Network Connections

| Command                       | Description                                     |
|-------------------------------|-------------------------------------------------|
| `curl [url]`                 | Fetches data from a URL                         |
| `wget [url]`                 | Downloads files from a URL                      |
| `telnet [host] [port]`       | Tests if a specific port is open                |
| `netcat -zv [host] [port]`   | Checks port connectivity (`nc` command)         |
| `netstat -tulpn`             | Lists open ports and listening services         |
| `ss -tuln`                   | Faster alternative to `netstat`                 |

## 

### 🔄 Checking Active Connections & Services

| Command            | Description                                  |
|--------------------|----------------------------------------------|
| `netstat -anp`     | Shows all active connections and PIDs        |
| `lsof -i`          | Lists open files related to internet connections |
| `systemctl status network` | Shows network service status        |

> 💡 Note: `netstat`, `ifconfig`, and `lsof` may not be pre-installed on all systems. Use `sudo apt install net-tools` or `sudo yum install net-tools` as needed.

##

### 🌐 Useful for Testers

> - Check if the test server is reachable: `ping` and `curl`
> - Verify that test APIs are returning expected data: `curl` or `httpie`
> - Debug DNS or domain issues with `dig` or `nslookup`
> - Monitor open ports and services during test runs: `netstat`, `ss`

---

## 💻 Chapter 6: Shell Scripting Basics

Shell scripts allow you to automate repetitive tasks, set up test environments, run test suites, and monitor system behavior. This chapter introduces basic scripting in `bash`, the most commonly used shell.

### 📝 Creating a Simple Script 

```bash
#!/bin/bash
echo "Hello, World!"
```

* Save the file as hello.sh
* Make it executable: chmod +x hello.sh
* Run it: ./hello.sh

##  Useful Scripting Concepts

```text
| Concept                | Example                                   |
| ---------------------- | ----------------------------------------- |
| Variables              | `name="Fazle"`                            |
| Using variables        | `echo "Hello, $name"`                     |
| Conditional statements | `if [ $var -eq 1 ]; then ... fi`          |
| Loops                  | `for i in 1 2 3; do echo $i; done`        |
| Reading user input     | `read -p "Enter name: " username`         |
| Running commands       | `$(command)` or backticks `` `command` `` |
```

##  Sample: Automation Script

```bash
#!/bin/bash
echo "Running test suite..."
pytest tests/ > test-report.txt
echo "Tests finished. Report saved to test-report.txt"
```

## Pro Tips for Testers
> - Automate full test pipelines: install dependencies, run tests, clean artifacts.
> - Integrate shell scripts with cron jobs to schedule regression or smoke tests.
> - Create environment setup scripts to standardize local/CI test setups.
> - Add logs and exit codes in scripts to make CI/CD troubleshooting easier:

---
<a id="ch7"></a>


## 🪵 Chapter 7: Log Management and Troubleshooting in Linux

Logs are a goldmine for debugging and monitoring test environments and systems. Whether you're tracking test failures, server crashes, or performance bottlenecks, knowing how to read and manage logs is critical.

### 📁 Common Log Files

Most Linux log files are stored in the `/var/log/` directory.

| Log File                      | Description                                     |
|-------------------------------|-------------------------------------------------|
| `/var/log/syslog`             | System-wide logs (Debian-based systems)         |
| `/var/log/messages`           | General messages (RedHat/CentOS systems)        |
| `/var/log/auth.log`           | Authentication logs (logins, sudo, etc.)        |
| `/var/log/dmesg`              | Kernel ring buffer (boot & hardware info)       |
| `/var/log/apache2/error.log`  | Apache server error log                         |
| `/var/log/nginx/error.log`    | Nginx server error log                          |
| `/var/log/kern.log`           | Kernel logs                                     |


### 🔍 Viewing and Searching Logs

| Command                                 | Description                                    |
|-----------------------------------------|------------------------------------------------|
| `cat [logfile]`                         | Outputs entire log file                        |
| `less [logfile]`                        | View log with scroll/navigation                |
| `tail [logfile]`                        | Shows the last 10 lines of a file              |
| `tail -f [logfile]`                     | Live view of log updates (great for watching)  |
| `head [logfile]`                        | Shows the first 10 lines                       |
| `grep "error" [logfile]`                | Search log for keywords                        |
| `journalctl`                            | View logs from systemd (modern systems)        |
| `dmesg less`                          | View boot and kernel logs                      |
 
### 🧪 Pro Tips for Testers

> - Use `tail -f` during test runs to monitor logs live and catch real-time errors.
> - Combine `grep` with `tail` to find specific issues quickly:
  ```bash
  tail -f /var/log/syslog | grep "python" 
  ```

---

<a id="ch8"></a>


## 📦 Chapter 8: File Compression, Archiving, and Backup in Linux

Linux provides several built-in tools to compress, archive, and back up files and directories. This is especially helpful when you're dealing with large amounts of test data, saving logs, or preparing backups before deployment.

### 🗜️ Common Archiving and Compression Tools

| Tool        | Usage                     | Description                            |
|-------------|----------------------------|----------------------------------------|
| `tar`       | Archiving only             | Combines multiple files into one       |
| `gzip`      | Compression (single files) | Compresses `.tar` or other files       |
| `zip`       | Archive + compression      | Compresses and archives                |
| `rsync`     | Backup & sync              | Fast, reliable backup utility          |

### 📁 Creating Archives with `tar`

```bash
# Create a .tar archive
tar -cvf archive.tar folder/

# Extract a .tar archive
tar -xvf archive.tar

# Create a compressed .tar.gz archive
tar -czvf archive.tar.gz folder/

# Extract a .tar.gz archive
tar -xzvf archive.tar.gz
```

### 📦 Using zip and unzip

```bash
# Compress a folder or file
zip -r archive.zip folder/

# Extract a zip file
unzip archive.zip
```

### 🔄 Using rsync for Backup

```bash
# Backup folder to another directory
rsync -av folder/ /backup/location/

# Backup over SSH (remote)
rsync -avz folder/ user@host:/remote/backup/
```



---

## 🛠️ Contributing

Feel free to open an issue or a pull request to improve this guide. You can also suggest tools, corrections, or advanced tips.
