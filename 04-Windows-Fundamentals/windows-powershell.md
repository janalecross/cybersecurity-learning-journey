### 1. What is PowerShell?

PowerShell is a command-line tool used for system management and automation.

It's more advanced than the traditional Windows Command Prompt (CMD).

**What I learned:**

I learned that PowerShell allows users to manage their computers and automate tasks.

For example, instead of manually checking a security service on multiple computers, PowerShell can help automate the process.

This can save time and make repetitive tasks easier.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use PowerShell to check running processes, investigate system information and automate certain security tasks.

I also learned that attackers can misuse PowerShell, so understanding it can help me investigate suspicious activities..

### 2. PowerShell Basics

**Get-Process**

The `Get-Process` command allows me to see which applications and background processes are currently running on my computer. And CPU and memory usage information.

It's similar to the `tasklist` command in Windows CMD.

**What I learned:**

I learned that `Get-Process` shows running processes and information such as their Process IDs (PID), CPU and memory usage.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `Get-Process` to help investigate suspicious processes running on a computer.

However, I shouldn't automatically assume an unfamiliar process is malicious without investigating further.

**Get-Service**

The `Get-Service` command allows me to check information about Windows services and whether they're running or stopped.

**What I learned:**

I learned that `Get-Service` helps me check the status of services running on a computer.

For example, if I find that an important security service has unexpectedly stopped, I would find it suspicious.

However, this doesn't automatically mean someone disabled it.

I would investigate what happened, when it happened, what caused it and whether it was authorised.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `Get-Service` to investigate suspicious changes to Windows services.

This can help me identify possible security issues that need further investigation.

**Get-Help and Get-Command**

`Get-Help` allows me to find information about a PowerShell command and how to use it.

`Get-Command` helps me find commands available in PowerShell.

**What I learned:**

At first, I thought `Get-Help` listed all the commands available in PowerShell.

I learned that `Get-Command` is used to find commands, while `Get-Help` explains how a command works.

**Why is it useful?**

These commands are useful because I don't need to memorise every PowerShell command.

If I forget how a command works, I can use `Get-Help` to understand it better.

### 3. Navigating the File System

**Get-ChildItem**

The `Get-ChildItem` command allows me to see the files and folders inside a directory.

**What I learned:**

I learned that `Get-ChildItem` is similar to the `ls` command in Linux and `dir` in Windows CMD.

It helps me see what files and folders are inside my current directory.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `Get-ChildItem` to navigate through files and folders when investigating suspicious activity.

**Set-Location**

The `Set-Location` command allows me to change my current directory in PowerShell.

It's similar to the `cd` command in Linux and Windows CMD.

**What I learned:**

I learned that `Set-Location` allows me to move between different directories.

I also learned that I can use `cd` in PowerShell because it's an alias for `Set-Location`.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `Set-Location` to navigate directories when looking for files or investigating suspicious activity.

**Get-Content**

The `Get-Content` command allows me to read and display the contents of a file using PowerShell.

It's similar to the `cat` command in Linux.
```bash
Get-Content investigation.txt 
```
**What I learned:**

I learned that `Get-Content` allows me to read text files directly from PowerShell.

I can also use `-Tail` to view the last few lines of a file.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `Get-Content` to read log files and investigate suspicious activity.

For example, I could check recent log entries to help understand what happened.

**New-Item**

The `New-Item` command allows me to create new files or directories using PowerShell.

**What I learned:**

I learned that `New-Item` can create either files or directories depending on the options I use.

- `-Path` — Specifies where the file or directory will be created.
- `-ItemType File` — Creates a file.
- `-ItemType Directory` — Creates a directory.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `New-Item` to create folders and files to organise my investigation notes.

**Copy-Item**

The `Copy-Item` command allows me to copy a file while keeping the original.

**PowerShell Example:**

```powershell
Copy-Item -Path investigation.txt -Destination backup.txt
```

**Linux Bash Equivalent:**

```bash
cp investigation.txt backup.txt
```

Both commands copy `investigation.txt` and create another file called `backup.txt` while keeping the original.

**What I learned:**

I learned that `Copy-Item` can create a duplicate of a file.

The `-Path` option specifies the original file, while `-Destination` specifies where the copy should go or what it should be named.

I also learned that Linux uses the `cp` command to copy files.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `Copy-Item` or `cp` to copy files when needed.

However, I need to be careful when handling investigation evidence to avoid accidentally changing or overwriting important information.

**Move-Item**

The `Move-Item` command allows me to move a file from one location to another.

**PowerShell Example:**

```powershell
Move-Item investigation.txt C:\Evidence\
```

**Linux Bash Equivalent:**

```bash
mv investigation.txt /home/analyst/Evidence/
```

**What I learned:**

I learned that `Move-Item` moves a file to a new location, removing it from its previous location.

Unlike `Copy-Item`, which keeps the original file, `Move-Item` transfers the file to another location.

I also learned that Linux uses the `mv` command for the same purpose.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `Move-Item` to organise files.

However, I need to be careful when handling investigation evidence because moving important files could affect an investigation.

**Remove-Item**

The `Remove-Item` command allows me to delete files and directories using PowerShell.

**PowerShell Example:**

```powershell
Remove-Item investigation.txt
```

**Linux Bash Equivalent:**

```bash
rm investigation.txt
```

**What I learned:**

I learned that `Remove-Item` can delete files and directories.

At first, I thought the Linux equivalent was `rmdir`, but I learned that `rm` is used to remove files, while `rmdir` removes empty directories.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I need to be careful when using commands that delete files.

Deleting suspicious files without investigating them first could destroy important evidence.

### 4. Piping and Filtering Data

Piping allows me to pass information from one PowerShell command to another using the `|` symbol.

**PowerShell Example:**

```powershell
Get-Service | Where-Object Status -eq "Stopped"
```

This command shows Windows services that are currently stopped.

**Linux Bash Example:**

```bash
ps aux | grep ssh
```

This uses a pipe to pass process information to `grep`, which searches for lines containing `ssh`.

**What I learned:**

I learned that piping allows me to connect commands together.

I also learned that `Where-Object` helps filter information so I can find what I'm looking for.

Both PowerShell and Linux Bash support piping, although they handle the information differently.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use piping and filtering to find specific information when investigating suspicious activity.

This can save time instead of manually looking through a long list of results.

**Sort-Object**

The `Sort-Object` command allows me to sort information in PowerShell.

**PowerShell Example:**

```powershell
Get-Process | Sort-Object ProcessName
```

This sorts running processes by name from A to Z.

**Linux Bash Equivalent:**

```bash
ps -eo comm= | sort
```

This lists process names and sorts them alphabetically.

**What I learned:**

I learned that `Sort-Object` helps me organise information.

For example, I can sort running processes alphabetically instead of looking through an unorganised list.

I also learned that `-Descending` reverses the sorting order.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use sorting to organise information during investigations.

This can make it easier to review processes and other system information.

### 5. System and Network Information

**Get-ComputerInfo**

The `Get-ComputerInfo` command provides information about a Windows computer, including its hardware and operating system.

**PowerShell Example:**

```powershell
Get-ComputerInfo
```

**Linux Bash Similar Command:**

```bash
uname -a
```

This shows information about the Linux system and kernel, although it doesn't provide all the same details.

**What I learned:**

I learned that `Get-ComputerInfo` allows me to check information about my computer, such as its Windows version, processor and memory.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `Get-ComputerInfo` to check system information when investigating possible vulnerabilities.

For example, I can check which Windows version a computer is running and investigate whether it has known security weaknesses.

**Get-NetIPConfiguration**

The `Get-NetIPConfiguration` command shows information about my computer's network configuration.

It can show:
- IP Address — The address assigned to your computer's network adapter.
- Default Gateway — Usually your router's IP address.
- DNS Servers — Servers used to look up domain names.
- Network Adapter — Such as Wi-Fi or Ethernet.

**PowerShell Example:**

```powershell
Get-NetIPConfiguration
```

**Linux Bash Similar Command:**

```bash
ip addr
```

The Linux command shows IP addresses assigned to network interfaces.

**What I learned:**

I learned that `Get-NetIPConfiguration` allows me to check my computer's IP address, default gateway and DNS information.

It's similar to the `ipconfig` command in Windows CMD.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `Get-NetIPConfiguration` to check network information when investigating connectivity problems or suspicious activity.

**Get-NetTCPConnection**

TCP stands for Transmission Control Protocol. It allows computers to communicate over a network and helps make sure data arrives correctly and in the right order.

If data gets lost during transmission, TCP can retransmit the missing data.

**PowerShell Example:**

```powershell
Get-NetTCPConnection
```

**Linux Bash Similar Command:**

```bash
ss -tan
```

Both commands can show TCP connections and their states.

**What I learned:**

I learned that TCP is a networking protocol that provides reliable communication between computers.

I also learned that `Get-NetTCPConnection` allows me to check TCP connections, including IP addresses, ports and connection states.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `Get-NetTCPConnection` to investigate network connections.

For example, if I find an unfamiliar connection to an external IP address, I would investigate whether it's legitimate or suspicious.

However, an unfamiliar connection doesn't automatically mean there's an attack.

### 6. Real-Time System Analysis

**Get-WinEvent**

The `Get-WinEvent` command allows me to retrieve Windows event logs using PowerShell.

**PowerShell Example:**

```powershell
Get-WinEvent -LogName System -MaxEvents 10
```

**Linux Bash Similar Command:**

```bash
journalctl -n 10
```

This displays the 10 most recent entries from the systemd journal.

**What I learned:**

I learned that `Get-WinEvent` allows me to check Windows event logs without opening Event Viewer.

These logs can contain information about login attempts, system errors and other activities.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `Get-WinEvent` to help investigate suspicious activity.

For example, I can review security logs to investigate failed login attempts and collect information about what happened.

### 7. PowerShell Scripting

PowerShell scripting allows users to put multiple commands into one script to automate tasks.

PowerShell scripts normally use the `.ps1` file extension.

**Linux Bash Equivalent:**

Linux also supports scripting using Bash. Bash scripts commonly use the `.sh` file extension.

**What I learned:**

I learned that PowerShell scripts can help automate repetitive tasks.

Instead of manually typing the same commands every time, I can put them into a script and run them together.

This can save time and make tasks easier.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use PowerShell scripts to help automate security checks and collect system information.

For example, scripts can help check running processes, services and other system information.

However, I need to understand what a script does before running it because scripts can also make changes to a computer.

## Reflection

### What Did I Find Challenging?

I found piping and filtering a bit challenging because I'm still trying to understand how commands work together.

Sometimes I understand what a command does, but I struggle to understand the information it shows.

Scripting is also new to me. I understand that it helps automate tasks, but I'm not confident writing my own scripts yet.

Another challenge is remembering technical terms and knowing when to use what I've learned in a real situation.

I think I need more hands-on practice to understand these concepts better.

### What Skills Do I Need to Improve?

- **Piping and Filtering** — I need more practice combining commands and filtering information.
- **Understanding Output** — I need to get better at reading and understanding command results.
- **Scripting** — I want to learn how to create simple PowerShell scripts.
- **Technical Knowledge** — I need to review technical terms so I can remember what they mean.
- **Practical Skills** — I need to practise using commands in different situations instead of just memorising them.

### How Can I Apply These Skills as a SOC Analyst?

As a SOC Analyst, I can use PowerShell to investigate suspicious processes, network connections and system logs.

Piping and filtering can help me find specific information without having to look through everything manually.

Scripting can also help automate repetitive security checks.

However, I need to understand what the commands are showing me so I can investigate properly and explain my findings.

### My Biggest Takeaway

I learned that PowerShell is a powerful tool for system management and automation.

It's not just about typing commands. It's also about using commands together to find information and make tasks easier.

I still have a lot to learn, especially scripting and understanding command outputs.

I'll continue practising and reviewing my notes to improve my understanding.
