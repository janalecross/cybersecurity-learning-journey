# TryHackMe — Search Skills

**Platform:** TryHackMe  
**Room:** Search Skills  
**Category:** Cybersecurity Fundamentals  
**Status:** In Progress

## Objective

Learn how to effectively search for cybersecurity-related information using specialised search engines, threat intelligence tools, vulnerability databases, and technical documentation.

## Tools and Resources

- Shodan
- VirusTotal
- CVE Databases
- Linux Manual Pages
- GitHub

## What I Learned

### 1. Shodan

**What is it?**

Shodan is like a search engine that helps user find devices and service networks that is connected to the internet 

**Cybersecurity relevance:**

Shodan can be use full for a SOC analyst and an attacker to gather information internet facing system( any device that is directly accesible to public internet ) 

As an aspiring SOC Analyst, I learned that Shodan can be useful for Security professional and Hackers to help them indentify and exposed vulnerabilities that require futher investigation

**My key takeaway:**

I learned that devices connected to the internet may expose information about themselves. Understanding what information is publicly accessible can help security analysts identify possible security risks.

### 2. VirusTotal

**What is it?**

VirusTotal is an online security analysis platform that gathers results from over 70 antivirus engines and URL/domain blocklisting services, along with other security tools.

It allows users to investigate suspicious files, URLs, domains, and IP addresses.

**Cybersecurity relevance:**

VirusTotal is useful for SOC Analysts investigating suspicious files, websites, and network activity.

It can help analysts assess potential threats, identify relationships between malicious indicators, and collect evidence during investigations.

**My key takeaway:**

I learned that VirusTotal combines information from multiple security tools to help analysts investigate potential threats.

I also learned that detection results are not always conclusive. A file flagged by an antivirus engine is not necessarily malicious, and a clean result does not guarantee that a file is safe.

Analysts must examine additional evidence before making a final assessment.

### 3. CVE Databases

**What is a CVE?**

CVE stands for Common Vulnerabilities and Exposures.

From what I've learned, CVE is like a dictionary that provides a standardised list of publicly known security vulnerabilities affecting software and hardware.

Each vulnerability is assigned a unique identification number, allowing security professionals to reference and investigate the same security flaw.

THE FORMAT LOOKS LIKE THIS: 
CVE-YYYY-NNNN

CVE: Common Vulnerabilities and Exposures

YYYY: The year associated with the CVE identifier

NNNN: A unique sequence number containing four or more digits

**Cybersecurity relevance:**

CVE databases are useful for security analysts because they help identify known vulnerabilities in systems and software.

SOC Analysts can use CVE information to:

Research vulnerabilities affecting an organisation's systems.

Understand potential security risks.

Investigate whether software versions are affected.

Determine which vulnerabilities require further investigation or escalation.

**My key takeaway:**

I learned that CVEs provide a common identification system for publicly known vulnerabilities.

I also learned that a CVE represents a security weakness, not necessarily an actual cyberattack or confirmed compromise.

### 4. Linux Manual Pages

Linux manual pages, also known as man pages, are built-in documentation that helps users understand Linux commands, their functions, and available options.

[Your explanation.]



I learned that Linux manual pages are a useful resource for understanding commands without having to memorise every option.

### 5. GitHub

**What did I learn?**

GITHIB i dont understand it completely but from understanding It can be use to stay udated to latest threats and vulnerabilities. Users also use to publish Proof of Concept ( POC ) Code, Expoilation tool techincal reports that are faster the the offical channels. But be careful some repositories contains malwares covered as security research.

I learned that GitHub is more than a platform for storing code. It can also be a useful source of cybersecurity research and information.

I also learned that Proof of Concept code can help researchers demonstrate vulnerabilities, but it does not necessarily mean a vulnerability has been exploited in the real world.

As an aspiring SOC Analyst, I can use GitHub to document my progress, research security threats, and improve my technical understanding.

My Key Takeaway — Evaluating Proof of Concept Code

I learned that not all Proof of Concept (PoC) code published on GitHub is authentic or trustworthy.

Before trusting security research, I should verify the vulnerability using authoritative sources such as CVE databases, the NVD, and official vendor security advisories.

I also understand that a published PoC does not automatically mean every affected system can be exploited.

As an aspiring SOC Analyst, I should evaluate evidence carefully rather than make assumptions based on publicly available information.

## Reflection

**What did I find challenging?**

One of my biggest challenges was documenting what I learned and explaining concepts in my own words.

I've never documented my learning journey before, so this is a new experience for me.

Sometimes I understand the general idea but struggle to organise my thoughts and explain it clearly.

I also tend to rush because I get impatient. This causes me to make simple mistakes, overlook details, or forget information I've learned.

Although documenting my progress feels slow, I believe it's one of the best ways to understand complex subjects and improve my communication skills.

**What skills did I improve?**

Communication: Explain technical concepts clearly in my own words.

Patience: Slow down and focus on understanding rather than finishing quickly.

Attention to Detail: Review information carefully and avoid missing important details.

Documentation: Organise my thoughts and record what I've learned.

Critical Thinking: Question information and verify findings before reaching conclusions.

Time Management: Give myself enough time to learn and practise.


---

*This document reflects my personal learning and practical experience from TryHackMe.*
