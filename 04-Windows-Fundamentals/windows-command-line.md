### 1. Basic System Information

The `systeminfo` command shows information about a Windows computer, such as its operating system, hardware and system configuration.

**What I learned:**

I learned that `systeminfo` allows me to check information about my computer, including the Windows version, processor and installed memory.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `systeminfo` to check what Windows version a computer is running.

This can help me investigate whether the system might have known security vulnerabilities.

**Whoami Command**

The `whoami` command shows which user account is currently running the command.

**What I learned:**

I learned that `whoami` can help me identify the current user account in Windows.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use this command to check which account I'm using when investigating a Windows system.

### 2. Network Troubleshooting

**IPCONFIG**

The `ipconfig` command shows information about my computer's network configuration.

It can show my IP address, subnet mask and default gateway.

**What I learned:**

I learned that `ipconfig` helps me check the network settings of my computer.

At first, I thought it also showed listening ports, but I learned that `netstat` is used for checking network connections and listening ports.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `ipconfig` to check a computer's network information when investigating network problems or suspicious activity.

**PING**

The `ping` command is used to check if another computer or server is responding over a network.

It uses the ICMP protocol to send requests and check for replies.

**What I learned:**

I learned that `ping` can help check whether a computer or server is responding.

I also learned that if a ping fails, it doesn't automatically mean the server is offline because some firewalls block ping requests.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `ping` to help troubleshoot network connectivity problems.

**TRACERT**

The `tracert` command traces the path that network packets take to reach their destination.

It shows the different routers or hops that packets pass through.

**What I learned:**

I learned that `tracert` can help me understand the path that network traffic takes to reach another computer or server.

It can also help identify where network problems might be happening.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `tracert` to help investigate network connectivity problems and understand how traffic travels across a network.

**NSLOOKUP**

The `nslookup` command is used to look up a domain name and find its IP address using DNS.

**What I learned:**

I learned that `nslookup` allows me to check which IP address is associated with a domain.

It can also provide other DNS information.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `nslookup` to investigate suspicious domains and find their associated IP addresses.

I can then use this information for further investigation.

### 3. File and Disk Management

**DIR**

The `dir` command shows a list of files and folders inside a directory.

**What I learned:**

I learned that `dir` allows me to see what files and folders are inside my current directory.

It's similar to the `ls` command in Linux.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `dir` to look for files and folders when investigating suspicious activity on a Windows computer.

**CD (Change Directory)**

The `cd` command allows me to move between directories using Command Prompt.

**What I learned:**

I learned that `cd` allows me to change my current directory.

I can also use `cd ..` to move back to the parent directory.

At first, I thought `cd` could also open files, but I learned that it only changes directories.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `cd` to navigate through different directories when looking for files or investigating suspicious activity.

**MKDIR (Make Directory)**

The `mkdir` command allows me to create a new directory or folder.

**What I learned:**

I learned that `mkdir` creates folders, while `cd` allows me to move between folders.

At first, I thought `mkdir` creates files, but I learned that it creates directories.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `mkdir` to create folders to organise my investigation files and notes.

**RMDIR (Remove Directory)**

The `rmdir` command allows me to remove a directory in Windows.

**What I learned:**

I learned that `rmdir` removes empty directories.

If a directory contains files, I can use the `/s` option to remove the directory and everything inside it.

However, I need to be careful because I could accidentally delete important files.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I need to understand commands that can delete files and folders.

I should be careful when handling investigation evidence because deleting files could affect an investigation.

**COPY**

The `copy` command allows me to copy files from one location to another or create another copy of a file.

**What I learned:**

I learned that `copy` creates a copy of a file while keeping the original.

At first, I thought it copied directories, but I learned that it is mainly used for copying files.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding the `copy` command can help me work with files during investigations.

I also need to be careful when handling important evidence.

**MOVE**

The `move` command allows me to move files from one location to another.

**What I learned:**

I learned that `move` transfers a file to another location.

Unlike `copy`, which keeps the original file, `move` removes the file from its previous location.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding `move` can help me manage files.

However, I need to be careful when moving investigation evidence because changing its location could affect an investigation.

**DEL (Delete)**

The `del` command allows me to delete files using Windows Command Prompt.

**What I learned:**

I learned that `del` removes files from a directory.

I also learned that I need to be careful because deleting files could remove important information.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I need to be careful when handling suspicious files.

Deleting a file without investigating it first could destroy important evidence.

### 4. Task and Process Management

**TASKLIST**

The `tasklist` command shows a list of processes currently running on a Windows computer.

It's similar to Windows Task Manager.

**What I learned:**

I learned that `tasklist` allows me to check which applications and background processes are currently running.

It also shows the Process ID (PID) of each process.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use `tasklist` to help identify suspicious processes running on a computer.

I would investigate any unfamiliar processes before deciding whether they're malicious.

**TASKKILL**

The `taskkill` command allows me to stop a running process using its Process ID (PID).

**What I learned:**

I learned that `taskkill` can stop processes running on a Windows computer.

However, I shouldn't immediately stop a process just because I don't recognise it.

It could be a legitimate process that's important for the system.

Even if it's malware, I need to be careful because stopping it could affect the investigation.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I need to investigate suspicious processes before taking action.

If I find a malicious process, I should follow the company's incident response procedures and report or escalate it when necessary.

## Reflection

### What Did I Find Challenging?

One thing I found challenging was trying to remember the different commands and what they do.

Sometimes I get confused between commands because some of them have similar functions.

I've learned quite a few commands in a short time, so I'm worried I might forget some of them.

However, I can always come back to my notes and practise again.

### What Skills Do I Need to Improve?

- **Memory** — I need to review the commands more often.
- **Practice** — I need to use the commands instead of just reading about them.
- **Patience** — I need to slow down when learning.
- **Attention to detail** — I need to pay attention to what each command does.

### How Can I Apply These Skills as a SOC Analyst?

As a SOC Analyst, knowing Windows commands can help me investigate suspicious activities.

For example, I can use `netstat` to check network connections and `tasklist` to check running processes.

I also need to be careful when using commands like `taskkill` and `del` because I could accidentally stop an important process or delete evidence.

### My Biggest Takeaway

I learned that Windows Command Prompt has different commands that can help me manage files, troubleshoot networks and investigate running processes.

I still need more practice to remember them, but I think documenting my learning and using the commands regularly will help me improve.




