### 1. Windows Editions

I learned that Windows has different editions, such as Windows Home and Windows Pro.

Both are pretty similar, but Windows Pro has additional security and business features.

One example is BitLocker Drive Encryption.

**What I learned:**

I learned that BitLocker helps protect data on a computer by encrypting the hard drive.

At first, I thought BitLocker automatically locks the computer when it's lost or stolen.

But I learned that BitLocker needs to be enabled beforehand. If someone steals the device, encryption helps prevent them from accessing the data without the required authentication.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding BitLocker can help me understand how companies protect sensitive information if a laptop gets lost or stolen.

### 3. NTFS (New Technology File System)

NTFS stands for New Technology File System. It is a file system used by Windows to store and organise files.

Some features I learned about NTFS are:

- **Self-healing** — Can automatically repair some minor file system problems.
- **Encryption** — Supports protecting files through encryption.
- **File permissions** — Controls who can access or change files.

**What I learned:**

I learned that NTFS has features that help protect files and keep the file system working properly.

I also learned that file permissions are important because they help prevent people from accessing files they don't need.

For example, an employee should only have access to files required for their job.

This is called the Principle of Least Privilege.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding NTFS and file permissions can help me investigate unauthorised access to files.

It can also help me identify security risks when users have more permissions than they need.

### 4. Windows System32

System32 is an important Windows folder that contains files and programs needed for Windows to work properly.

It is normally located at `C:\Windows\System32`.

Some examples of files found in System32 are:

- `cmd.exe` — Windows Command Prompt.
- `taskmgr.exe` — Task Manager.
- `regedit.exe` — Registry Editor.

**What I learned:**

I learned that System32 contains important Windows files and programs.

I also learned that attackers can use legitimate Windows programs for malicious activities.

For example, `cmd.exe` is a normal Windows program, but an attacker could use it to execute malicious commands.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I need to understand that not every legitimate Windows program is being used safely.

I should investigate suspicious activity before making conclusions.

### 5. Windows User Accounts and Permissions

Windows has different types of user accounts, such as Standard User and Administrator.

- **Standard User** — Can use programs and access files they have permission to use.
- **Administrator** — Has more permissions to install software, manage accounts and change system settings.

**What I learned:**

I learned that not every employee needs administrator permissions.

For example, someone who only uses Excel and an inventory system doesn't need full access to the computer.

Giving someone unnecessary permissions can be a security risk if their account gets compromised.

This is also related to the Principle of Least Privilege, where users should only have the access they need to do their job.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding user permissions can help me investigate suspicious account activity and identify security risks.

I also need to understand why administrator accounts are more sensitive because they have greater access to the system.

### 6. User Account Control (UAC)

UAC stands for User Account Control. It is a Windows security feature that asks for permission when a program wants to make important changes to the computer.

**What I learned:**

I learned that UAC helps protect Windows from unauthorised changes.

For example, when installing software, Windows might ask for administrator permission before allowing the program to continue.

I also learned that attackers might take advantage of human error by tricking someone into approving a malicious program.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I need to understand how UAC works because attackers might try to gain higher permissions on a computer.

If an employee reports an unexpected UAC prompt, I should investigate which program caused it and whether it is legitimate.

### 7. Control Panel and Settings

Control Panel and Settings are Windows tools that allow users to manage and change computer settings.

Some examples are:

- Network settings
- Installed applications
- User accounts
- Devices
- Firewall settings

**What I learned:**

I learned that Windows has two ways to access and manage system settings.

Settings has a newer interface, while Control Panel is the older version that still contains some useful tools.

I also learned that unexpected changes to security settings, such as the firewall being disabled, could be suspicious.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding Windows settings can help me investigate suspicious changes to a computer.

For example, if a firewall is unexpectedly disabled, I should investigate when it happened, what caused it and whether the change was authorised.

I shouldn't immediately assume it was an attacker because there could be other reasons.

### 8. Task Manager

Task Manager is a Windows tool that allows users to see what programs and processes are running on a computer.

It also shows how much CPU, memory, disk and network resources are being used.

**What I learned:**

I learned that Task Manager can help me check running processes and how much resources they're using.

For example, if I find an unknown program using 95% CPU, I would find it suspicious and investigate further.

However, I shouldn't automatically assume it's malware because there could be other reasons for the high CPU usage.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use Task Manager to help investigate suspicious processes.

I would check what the process does, where it came from and whether it's supposed to be running before taking action.

## Reflection

### What Did I Find Challenging?

One thing I found challenging was understanding how some Windows security features work.

For example, at first I thought BitLocker automatically locks a computer when it gets stolen, but I learned that it protects the data through encryption.

I also find it challenging to explain what I've learned in my own words.

Sometimes I understand the general idea, but I struggle to explain it clearly.

### What Skills Do I Need to Improve?

- **Communication** — I need to get better at explaining what I've learned.
- **Patience** — I need to slow down instead of rushing.
- **Attention to detail** — I need to check information carefully before making conclusions.
- **Critical thinking** — I need to investigate further instead of assuming something is malicious.

### How Can I Apply These Skills as a SOC Analyst?

As a SOC Analyst, I need to understand how Windows works because many companies use Windows computers.

Knowing about file permissions, UAC, System32 and Task Manager can help me investigate suspicious activities.

For example, if I find an unknown process using a lot of CPU, I shouldn't immediately assume it's malware.

I need to investigate what the process does, where it came from and whether it's legitimate.

I also need to improve how I document and explain my findings because other security analysts might rely on my reports.

### My Biggest Takeaway

I learned that Windows has different security features that help protect computers and information.

I also learned that not everything suspicious means it's malicious.

I still need more practice, but I think learning these concepts and documenting them on GitHub will help me improve.
