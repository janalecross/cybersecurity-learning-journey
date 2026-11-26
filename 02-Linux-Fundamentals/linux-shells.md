### 1. Introduction to Linux Shells

A Linux shell is a command-line program that acts as a bridge between the user and the operating system.

It allows users to interact with Linux by entering commands.

**What I learned:**

I learned that a shell interprets commands and allows me to interact with the operating system.

I also learned that the terminal, shell and kernel are different things.

- **Terminal** — Where I enter commands.
- **Shell** — Interprets and runs my commands.
- **Kernel** — The core of the operating system that manages system resources.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding Linux shells can help me use commands to navigate systems, investigate logs and perform security-related tasks.

### 2. How to Interact With a Shell

A Linux shell allows me to interact with the operating system by typing commands.

**PWD (Print Working Directory)**

The `pwd` command shows my current location in the Linux filesystem.

**Linux Bash Example:**

```bash
pwd
```

**PowerShell Equivalent:**

```powershell
Get-Location
```

**What I learned:**

I learned that `pwd` tells me which directory I'm currently in.

I also learned that the shell interprets my commands and helps execute them.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, knowing my current directory can help me navigate Linux systems and avoid working in the wrong location when investigating files.

### 3. Types of Linux Shells

Linux has different types of shells, such as Bash, Zsh and Fish.

**Bash (Bourne Again Shell)**

Bash is one of the most commonly used Linux shells.

It's important to learn because it's widely used for Linux commands, system administration and scripting.

**Zsh (Z Shell)**

Zsh is another Linux shell that has more customisation options and advanced interactive features.

It supports plugins, themes and command completion.

It also supports many of the same commands as Bash.

**Fish (Friendly Interactive Shell)**

Fish is a beginner-friendly shell.

It has features such as automatic command suggestions and syntax highlighting, which can make it easier to use.

**What I learned:**

I learned that Linux has different shells that allow users to interact with the operating system.

Bash is commonly used, while Zsh offers more customisation and Fish focuses on being user-friendly.

I also learned that even though these shells support many of the same commands, their scripting syntax can be different.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding different Linux shells can help me work with Linux systems.

Learning Bash is especially useful because I can use it to investigate files, check logs and automate tasks using scripts.

### 4. Shell Scripting and Components

A Bash script is a file containing commands that can be executed together.

Bash scripts commonly use the `.sh` file extension.

**What I learned:**

I learned that Bash scripting can help save time by automating repetitive tasks.

For example, instead of manually typing the same commands every time, I can put them into a script and run them whenever I need.

This makes tasks more efficient and reduces repetitive work.

I also learned that scripts can contain multiple commands that execute in order.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use Bash scripts to help automate security checks and collect system information.

For example, I could create a script that checks system information or collects certain log entries.

However, I need to understand what a script does before running it because scripts can also make changes to a system.

**Shebang**

A shebang tells Linux which interpreter should be used to run a script.

**Bash Example:**

```bash
#!/bin/bash
```

**What I learned:**

I learned that the shebang is important because different shells can interpret scripts differently.

For example, a script written for Bash might not work properly with another shell because their scripting syntax can be different.

Using a shebang helps make sure the correct interpreter is used when running the script directly.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding shebangs can help me identify which interpreter a script is intended to use.

This can be useful when examining suspicious scripts during an investigation.

### 5. The Locker Script

The Locker Script is a Bash script that checks information entered by a user before allowing access.

**What I learned:**

I learned that Bash scripts can be used to create a simple access-checking system.

For example, the script can ask someone to enter their username and PIN.

It then checks whether the information matches what the script expects.

If the information is correct, access is granted. Otherwise, access is denied.

I also learned that Bash scripts use variables and conditional statements to make decisions.

However, this is only a basic example and doesn't provide the same protection as a real security system.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding Bash scripts can help me investigate suspicious scripts and understand how they work.

I can also use this knowledge to understand how scripts collect information and make decisions.

**What I learned about if/else:**

I learned that `if/else` statements allow Bash scripts to make decisions based on conditions.

For example, if someone enters the correct PIN, the script can display an access-granted message.

Otherwise, it displays an access-denied message.

This helps me understand how scripts can respond differently depending on the information entered.


