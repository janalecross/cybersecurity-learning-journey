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

