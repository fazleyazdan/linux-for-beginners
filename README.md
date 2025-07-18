# Linux for Beginners

- [Intro](#intro)
- [📘 Chapter 1: Essential Linux Commands for Beginners](#ch1)
- [🔐 Chapter 2: Understanding Users, File Permissions, and Ownership](#ch2)

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

### 📄 File Ownership

| Command                  | Description                                    |
|:-------------------------|:-----------------------------------------------|
| `ls -l`                  | Shows ownership and permission details         |
| `chown [user] [file]`    | Changes file owner                             |
| `chown user:group [file]`| Changes owner and group of a file              |

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

---

## 🛠️ Contributing

Feel free to open an issue or a pull request to improve this guide. You can also suggest tools, corrections, or advanced tips.
