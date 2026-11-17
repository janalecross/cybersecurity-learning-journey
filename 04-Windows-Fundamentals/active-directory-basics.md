
### 1. Active Directory (AD)

Active Directory is a Microsoft directory service that helps companies organise and manage users, computers and security policies.

It's like a table of contents that keeps information about different users and devices in one place.

**What I learned:**

I learned that Active Directory allows companies to manage multiple users and computers from a central system.

Instead of managing every computer separately, IT administrators can use Active Directory to manage user accounts, permissions and security policies.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding Active Directory can help me investigate suspicious user account activity.

For example, I can investigate unusual logins, changes to user permissions and possible unauthorised access.

### 2. Windows Domains

A Windows Domain allows companies to manage multiple users, computers and resources from a central system using Active Directory.

**What I learned:**

I learned that Windows Domains make it easier for companies to manage users and computers.

I also learned that Domain Administrator accounts have more permissions than normal user accounts.

If an attacker gains access to a Domain Administrator account, they could potentially control multiple computers, change permissions and manage other user accounts.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding Windows Domains can help me investigate suspicious account activity.

For example, if a Domain Administrator account is compromised, I would consider it a serious security risk because it has powerful permissions across the domain.

I would need to investigate the activity and escalate it to the appropriate team.

### 3. Managing Users in Active Directory

Active Directory allows IT administrators to manage user accounts and their permissions from one place.

They can create, disable and manage accounts. They can also assign users to security groups.

**What I learned:**

I learned that Active Directory makes it easier for companies to manage employee accounts.

For example, when an employee leaves the company, IT can disable their domain account to help prevent them from accessing company resources.

I also learned that users should only have access to what they need for their job. This is called the Principle of Least Privilege.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can investigate suspicious changes to user accounts and permissions.

For example, if a warehouse employee suddenly gets access to payroll information, I would investigate who gave them access, when it happened and whether it was authorised.

I shouldn't immediately assume it's an attack without checking further.

### 4. Managing Computers in Active Directory

Active Directory allows IT administrators to manage and organise computers connected to a Windows domain.

Computers can be organised into different Organisational Units (OUs), such as Warehouse, Finance and IT.

**What I learned:**

I learned that Active Directory can help companies manage multiple computers instead of managing them separately.

I also learned that finding an unknown computer account could be suspicious.

For example, if I find an unfamiliar computer account, I would investigate who created it, when it was created and whether it was authorised.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, I can investigate suspicious computer accounts or changes in Active Directory.

I would gather information and report my findings to the appropriate team if further investigation is needed.

### 5. Group Policies

Group Policy allows IT administrators to manage and apply settings to multiple users and computers from one place.

For example, instead of changing the firewall settings on every computer, an administrator can use Group Policy to manage these settings.

**What I learned:**

I learned that Group Policy makes it easier for companies to manage security settings across multiple computers.

However, this can also be a security risk if someone makes an unauthorised change.

For example, if I find that a Group Policy was changed to disable Windows Firewall on 100 computers, I would find it suspicious.

I would investigate who changed the policy, when it happened, why it happened and whether it was authorised.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding Group Policy can help me investigate suspicious changes to company security settings.

I also learned that one policy change could affect multiple computers.

If I find something suspicious, I would report it to the appropriate team and investigate further before making conclusions.

### 6. Authentication Methods (Kerberos)

Kerberos is an authentication protocol used in Windows Active Directory.

It uses tickets to help verify the identity of users and allow them to authenticate to network services.

**What I learned:**

I learned that Kerberos uses authentication tickets when users try to access resources on a network.

Instead of sending their password to every service, Kerberos uses tickets to help prove their identity.

I also learned that authentication and authorisation are different. Authentication verifies who you are, while authorisation checks what you're allowed to access.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding Kerberos can help me investigate suspicious login activity and possible misuse of authentication tickets.

For example, if I notice unusual authentication activity involving a user account, I would investigate whether the activity is legitimate.

### 7. Trees, Forests and Trusts

**Tree**

A tree is a group of related Active Directory domains that share the same naming structure.

**Forest**

A forest is a collection of one or more Active Directory domain trees.

**Trusts**

A trust relationship allows users from one domain to authenticate when accessing resources in another domain.

**What I learned:**

I learned that companies can have multiple domains, even in different cities, states or countries.

For example, a company might have one domain in Sydney and another in Melbourne.

Trust relationships allow users from different domains to authenticate across them.

I also learned that domains within the same forest normally have automatic trust relationships.

However, having a trust doesn't mean everyone can access everything. Users still need the correct permissions.

**Why is it useful for a SOC Analyst?**

As a SOC Analyst, understanding trusts can help me investigate suspicious access between domains.

For example, if I find an employee accessing resources in another domain, I would investigate whether they have permission and whether the activity is legitimate.

## Reflection

### What Did I Find Challenging?

I found it challenging because a lot of new information was introduced in such a short time.

I'm worried that I might forget some of the things I've learned, especially the different terms and how Active Directory works.

However, I can always come back to my notes and review what I've learned.

### What Skills Do I Need to Improve?

- **Memory** — I need to review what I've learned more often.
- **Patience** — I need to slow down instead of rushing through topics.
- **Communication** — I need to get better at explaining things in my own words.
- **Practice** — I need more hands-on experience to understand the concepts better.

### How Can I Apply These Skills as a SOC Analyst?

As a SOC Analyst, I need to understand how Active Directory works because companies use it to manage users, computers and permissions.

Knowing these concepts can help me investigate suspicious account activity, changes to permissions and possible unauthorised access.

I also need to be patient and pay attention to details when investigating.

### My Biggest Takeaway

I learned that Active Directory makes it easier for companies to manage users, computers and security policies.

There is still a lot I need to understand, but I think reviewing my notes and practising what I've learned will help me improve.
