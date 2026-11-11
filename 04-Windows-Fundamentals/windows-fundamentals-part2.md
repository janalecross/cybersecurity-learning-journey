### 1. System Configuration (msconfig)

Msconfig is an advanced Windows tool used for startup diagnostics and troubleshooting.

It allows users to change startup settings, manage boot options and troubleshoot system services.

**What I learned:**

I learned that msconfig can help identify problems when Windows is starting up.

It also allows users to troubleshoot services that might be causing problems.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding msconfig can help me investigate unusual startup settings or disabled services.

I should investigate any suspicious changes before assuming they were caused by an attacker.

### 2. User Account Control (UAC) Settings

UAC is a Windows security feature that asks for approval when a program needs administrator permissions to make changes to the computer.

Windows allows users to change how often UAC notifications appear.

**What I learned:**

I learned that setting UAC to Never notify can be a security risk.

This means Windows will no longer show the usual UAC approval prompts when programs request higher permissions.

This could be dangerous because an attacker might take advantage of the weaker security settings to run malicious programs.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I need to understand how UAC settings affect security.

If I notice that UAC has been disabled or changed to Never notify, I would investigate why it happened and whether the change was authorised.

I shouldn't immediately assume it was an attacker without checking further.

### 3. Computer Management (Event Viewer)

Computer Management is a Windows tool that allows users to access different system management tools.

One of these tools is Event Viewer.

Event Viewer shows system and security event logs that can help investigate activities happening on a computer.

**What I learned:**

I learned that Event Viewer can help SOC Analysts investigate suspicious activities and possible attacks.

It can provide information that helps understand what happened, when it happened, where it happened and how it may have started.

However, not every event means an attack happened, so further investigation may be needed.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use Event Viewer to investigate suspicious login attempts, system errors and security events.

This can help me collect evidence and understand what happened during a possible security incident.

### 4. System Information (msinfo32)

System Information is a Windows tool that provides information about the computer's hardware, operating system and system configuration.

You can open it by using the `msinfo32` command.

**What I learned:**

I learned that System Information can help identify what Windows version and build a computer is running.

This is useful because older Windows versions may have fewer security features or might not receive security updates anymore.

I also learned that System Information doesn't directly tell me if all the latest security updates are installed.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use System Information to help investigate whether a computer might be affected by known vulnerabilities.

For example, I can check the Windows version and compare it with security advisories to see if the system needs further investigation.

### 5. Resource Monitor

Resource Monitor is a Windows tool similar to Task Manager, but it provides more detailed information about how the computer is using its resources.

It shows CPU, memory, disk and network usage.

**What I learned:**

I learned that Resource Monitor can help identify which programs or processes are using a lot of computer resources.

For example, if I notice an unknown program using a high percentage of CPU, I would find it suspicious and investigate further.

I also learned that attackers can use someone's computer resources to mine cryptocurrency without their permission. This is called cryptojacking.

However, high CPU usage doesn't automatically mean the computer is infected because legitimate programs can also use a lot of resources.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use Resource Monitor to investigate unusual CPU, memory, disk and network activity.

I would check which process is using the resources and whether that activity is normal or suspicious before making a conclusion.

### Resource Monitor — Practice Investigation

During a practice investigation, I found a process called `update_service.exe` using 96% CPU with continuous network activity.

At first, I thought it might be a legitimate Windows update because updates can use a lot of resources and network connections.

However, I learned that I shouldn't assume a process is safe just because its name looks legitimate.

**What I learned:**

I learned that attackers can disguise malicious programs using names that look like normal Windows programs.

I should investigate the process, check its file location and look at its network connections before making a conclusion.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I need to investigate suspicious processes and gather enough evidence to understand whether the activity is legitimate or malicious.

I shouldn't immediately assume something is safe or dangerous without checking further.

### 6. Windows Command Prompt

Command Prompt (CMD) is a Windows tool that allows users to interact with the computer by typing commands instead of using the graphical interface.

It's similar to the Linux terminal.

**Commands I learned:**

- `dir` — Shows files and folders.
- `cd` — Changes directory.
- `cls` — Clears the screen.
- `ipconfig` — Shows network information.
- `whoami` — Shows the current user.
- `netstat -ano` — Shows network connections, listening ports and Process IDs.
- `systeminfo` — Shows system information.

**What I learned:**

I learned that Command Prompt allows me to use commands to check information about a Windows computer.

For example, `netstat -ano` can help me check which ports are listening and what network connections are active.

I also learned that the PID can help identify which process is using a network connection.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use Command Prompt to help investigate suspicious network activity.

For example, I can check network connections and investigate which processes are communicating with other computers.

However, an open port or network connection doesn't automatically mean it's malicious.

### 7. Windows Registry Editor

Windows Registry is a database that stores settings and configurations for Windows and installed programs.

Registry Editor, also known as `regedit`, allows users to view and change these settings.

**What I learned:**

I learned that Windows uses the Registry to store important system and program settings.

I also learned that attackers can change Registry settings to make malicious programs run automatically when someone logs in.

This is called persistence.

However, not every program that starts automatically is malicious.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use Registry information to investigate suspicious programs or changes to Windows settings.

For example, if I find an unknown program that automatically starts when someone logs in, I would investigate what the program does, where it came from and whether it's supposed to be there.

I shouldn't immediately delete anything without checking first.

## Reflection

### What Did I Find Challenging?

One thing I found challenging was remembering the different Windows tools and what they're used for.

Sometimes I understand what a tool does, but I struggle to explain it properly in my own words.

I also tend to rush when learning something, which causes me to overlook small details.

### What Skills Do I Need to Improve?

- **Communication** — I need to get better at explaining what I've learned.
- **Patience** — I need to slow down instead of rushing through topics.
- **Attention to detail** — I need to check information carefully before making conclusions.
- **Critical thinking** — I need to understand the difference between something suspicious and an actual security threat.

### How Can I Apply These Skills as a SOC Analyst?

As a SOC Analyst, I need to understand how Windows works and how to use its tools to investigate suspicious activities.

For example, I can use Event Viewer to check logs, Resource Monitor to investigate unusual system activity, and Command Prompt to check network connections.

I also learned that attackers can use legitimate Windows tools and Registry settings for malicious activities.

Instead of immediately assuming something is an attack, I need to investigate further and collect evidence.

I also need to improve how I explain and document my findings so other security team members can understand what happened.

### My Biggest Takeaway

I learned that Windows has different tools that can help investigate security incidents.

I also learned that not everything suspicious is malicious.

I still have a lot to learn, especially with remembering commands and explaining technical concepts, but documenting my progress is helping me understand things better.
