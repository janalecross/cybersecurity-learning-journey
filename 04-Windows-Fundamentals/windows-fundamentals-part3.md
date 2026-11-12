### 1. Windows Updates

Windows Update is a Microsoft feature that allows users to check, download and install updates for their Windows system.

These updates can include security patches, bug fixes and other improvements.

**What I learned:**

I learned that Windows Update helps keep computers updated with the latest available security patches.

Security patches are important because they can fix known vulnerabilities that attackers might take advantage of.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding Windows Update can help me investigate whether a computer is missing important security patches.

Outdated systems may contain known vulnerabilities that could put a company at risk.

### Windows Update — Practice Investigation

During a practice investigation, I found out that a company hadn't installed a security patch released two months ago.

At first, I thought someone might have ignored the update and that the system could be compromised.

**What I learned:**

I learned that missing security patches can leave a computer vulnerable to attacks.

However, this doesn't automatically mean the computer has been hacked.

Sometimes companies delay updates for testing or because of technical problems.

As a SOC Analyst, I would investigate why the patch wasn't installed, check how serious the vulnerability is and report my findings.

If necessary, I would escalate the issue to the appropriate team.

I also learned that I shouldn't make assumptions without checking the evidence first.

### 2. Windows Security

Windows Security is a built-in Microsoft application that helps protect your computer from viruses, malware and other security threats.

It includes different security features such as antivirus protection, firewall and network protection.

**What I learned:**

I learned that Windows Settings, Windows Update and Windows Security have different purposes.

- Windows Settings allows users to manage their computer settings.
- Windows Update helps keep the system updated with the latest available patches.
- Windows Security helps protect the computer from security threats.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding Windows Security can help me investigate malware detections and other security alerts.

I can use the information to understand what was detected and whether further investigation is needed.

### 3. Virus & Threat Protection

Virus & Threat Protection is a Windows security feature that helps protect the computer from viruses, malware and other threats.

**What I learned:**

I learned that when Microsoft Defender detects malware, it can take different actions to protect the computer.

For example, it can block, quarantine or remove the threat.

Quarantine means isolating the suspicious file so it cannot normally run and cause damage.

I also learned that antivirus software cannot detect every threat.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can use Virus & Threat Protection to investigate malware detections.

I would check what was detected, which file was involved and what action Windows Defender took.

I also need to investigate whether the threat was successfully contained or if further action is needed.

### 4. Firewall & Network Protection

A firewall is like a security guard for network traffic.

It allows or blocks incoming and outgoing network traffic based on security rules.

Different services use different ports to communicate over a network.

**What I learned:**

I learned that firewalls help protect a computer by controlling which network traffic is allowed or blocked.

At first, I thought disabling the firewall meant everything could enter the system.

However, I learned that other security protections may still exist.

Disabling the firewall can increase security risks because unwanted network traffic might no longer be blocked.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding firewalls can help me investigate suspicious network activity.

For example, if I discover that Windows Firewall has been disabled, I would investigate when it happened, why it happened and whether the change was authorised.

I shouldn't immediately assume it was an attacker without checking further.

### 5. App & Browser Control

App & Browser Control is a Windows security feature that helps protect the computer from malicious applications, files and websites.

It can identify potentially dangerous applications and warn users before they open them.

**What I learned:**

I learned that App & Browser Control helps protect the computer by identifying suspicious applications, files and websites.

For example, if I download a suspicious program, Windows may warn me before I open it.

However, I also learned that it cannot detect every threat.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding App & Browser Control can help me investigate suspicious downloads and applications.

I can check whether Windows warned or blocked a program and investigate if the activity was legitimate or malicious.

### 6. Device Security

Device Security is part of Windows Security. It shows security features that help protect the computer at the hardware and operating system level.

Two important features I learned are Secure Boot and TPM.

**Secure Boot**

Secure Boot helps protect the computer when it's starting up.

It checks whether the software used during startup is trusted and helps prevent tampered or untrusted boot software from loading.

**TPM (Trusted Platform Module)**

TPM is a security component designed to perform cryptographic operations and protect important security keys.

It can also help protect information used by security features such as BitLocker.

### 8. Volume Shadow Copy Service (VSS)

Volume Shadow Copy Service (VSS) is a Windows feature that helps create snapshots of files and data at a certain point in time.

These snapshots can be used by backup and recovery tools to help restore previous versions of files.

**What I learned:**

I learned that VSS can help with recovering files if something goes wrong.

I also learned that some ransomware attacks try to delete shadow copies to make it harder to recover files.

However, deleting shadow copies doesn't automatically mean there's ransomware because administrators might also delete them for maintenance.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can investigate suspicious activity involving shadow copies.

For example, if I find that someone deleted all the shadow copies, I would investigate who did it, when it happened and whether it was authorised.

I would also check for other signs of ransomware before making a conclusion.

## Reflection

### What Did I Find Challenging?

One thing I found challenging was understanding how the different Windows security features work.

Sometimes I get confused between features like Windows Update, Windows Settings and Windows Security.

I also find it difficult to explain technical concepts in my own words, even when I understand the general idea.

### What Skills Do I Need to Improve?

- **Communication** — I need to improve how I explain what I've learned.
- **Patience** — I need to slow down instead of rushing.
- **Attention to detail** — I need to carefully read and understand information.
- **Critical thinking** — I need to investigate further instead of making assumptions.

### How Can I Apply These Skills as a SOC Analyst?

As a SOC Analyst, understanding Windows Security can help me investigate threats and protect company systems.

For example, I can investigate malware detections using Windows Security, check firewall settings and look for suspicious changes to security features.

I also learned that attackers might try to disable security protections or delete shadow copies to make recovery more difficult.

I need to investigate suspicious activity, collect evidence and report my findings before making conclusions.

### My Biggest Takeaway

I learned that Windows has different security features that work together to protect the computer.

I also learned that no single security feature can protect a computer from every attack.

I still need more practice, but documenting what I've learned is helping me understand cybersecurity better.
