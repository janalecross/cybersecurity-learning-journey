### 1. Terminal Text Editors

A terminal text editor allows users to create, edit and modify text files using the Linux terminal.

It's similar to Microsoft Word, but instead of using a normal graphical interface, we use commands and keyboard shortcuts.

In TryHackMe, I learned how to use Nano.

**What I learned:**

- `nano filename.txt` — Opens a text file in Nano.
- `Ctrl + O` — Saves the file.
- `Ctrl + X` — Exits Nano.
- `Ctrl + W` — Searches for text.

**Why is it useful for a SOC Analyst?**

Nano can be useful when working with Linux files, such as notes, scripts and configuration files.

It allows me to edit text files directly from the terminal without needing a graphical interface.

**What I learned:**

I learned what a Linux terminal text editor does and how to use Nano to create, edit and modify text files.

### 2. General/Useful Utilities

In this section, I learned three Linux commands that can be used to download, transfer and share files.

**Wget**

`wget` is a command that allows me to download files from the web using a URL.

**SCP (Secure Copy)**

`scp` allows me to securely transfer files between computers using SSH.

I learned that I can use it to upload or download files from another computer.

**Python HTTP Server**

`python3 -m http.server` allows me to start a simple web server using Python.

Other computers can connect to the web server and download files that are being shared.

**What I learned:**

I learned that Linux has different ways to download and transfer files.

Wget downloads files from the web, SCP securely transfers files using SSH, and Python can create a simple HTTP server for sharing files.

**Why is it useful for a SOC Analyst?**

These commands can help me understand how files are transferred between computers.

They can also help me recognise file transfers when investigating suspicious activity on a system.


### 3. Linux Processes 101

A process is a program that is currently running on a Linux system.

Every process has a Process ID (PID), which helps Linux identify and manage running processes.

**Commands I learned:**

- `ps` — Shows information about running processes.
- `ps aux` — Shows processes running across the system.
- `top` — Shows running processes and how much resources they use.
- `kill` — Sends a signal to a process, usually to stop it.
- `fg` — Brings a job to the foreground.
- `bg` — Resumes a stopped job in the background.

**What I learned:**

I learned that Linux has different commands to check and manage running processes.

I also learned that I shouldn't immediately stop a process just because I don't recognise it.

I need to investigate first because it might be an important part of the system, and stopping it could cause problems.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use process information to investigate suspicious activity.

I need to understand what a process does, who started it and whether it is supposed to be running before deciding what action to take.

### 4. Automation (Cron)

Cron is a Linux service that allows users to schedule tasks to run automatically at a certain time or interval.

Instead of manually doing the same task repeatedly, cron can automate it.

**What I learned:**

I learned that cron can automate tasks such as backing up files or running scripts.

This helps save time, avoids repetitive work and allows users to focus on other tasks.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding cron can help me investigate scheduled tasks on a Linux system.

For example, an attacker might use cron to automatically run a malicious script.

I would need to investigate whether a scheduled task is legitimate or suspicious before taking action.

Imagine you're investigating a Linux server and find this scheduled cron task:

*/5 * * * * /tmp/update.sh

**What I learned from the exercise:**

I learned that cron can be used to run scripts automatically at certain times.

For example, if I find an unknown script running every five minutes from the `/tmp` directory, I would find it suspicious and investigate further.

At first, I thought someone might be using `/tmp` to hide their activity, but I learned that this doesn't automatically mean it's malicious.

As a SOC Analyst, I should check what the script does, who created it and whether it's supposed to be running before making a decision.

### 5. Package Management

Package management in Linux allows users to install, update and remove software.

It's similar to downloading and updating apps on your phone.

**Commands I learned:**

- `sudo apt update` — Updates the list of available packages.
- `sudo apt upgrade` — Upgrades installed packages.
- `sudo apt install` — Installs software.
- `sudo apt remove` — Removes software.
- `apt list --upgradable` — Shows which packages have updates available.

**What I learned:**

I learned that Linux uses package managers to install, update and remove software.

I also learned the difference between `apt update` and `apt upgrade`. At first, I got them confused, but now I understand that `update` refreshes the package list while `upgrade` installs available package upgrades.

**Why is it useful for a SOC Analyst?**

Package management can help me understand what software is installed on a Linux system.

It can also help me identify outdated software that might contain security vulnerabilities.

### 6. System Logs

System logs are records of activities and events happening on a Linux system.

SOC Analysts use logs to investigate suspicious activities and understand what happened on a system.

Logs can contain information such as:

- Login attempts
- System errors
- Services starting or stopping
- IP addresses
- Commands executed, if command auditing is enabled

**What I learned:**

I learned that system logs are useful for investigating suspicious activities.

As a SOC Analyst, I can use logs to help understand what happened, when it happened, who was involved and how it happened.

However, not all logs contain the same information, and sometimes further investigation is needed.

**Why is it useful for a SOC Analyst?**

Logs can help me identify suspicious login attempts, investigate security alerts and collect evidence during an investigation.

14:01 Failed password for admin
from 198.51.100.25

14:02 Failed password for admin
from 198.51.100.25

14:03 Accepted password for admin
from 198.51.100.25

### System Logs — Practice Investigation

During a practice investigation, I looked at SSH logs showing two failed login attempts followed by a successful login from the same IP address.

At first, I thought the attempts happened one second apart and might be an automated brute-force attack.

After looking at the timestamps again, I realised they happened one minute apart.

