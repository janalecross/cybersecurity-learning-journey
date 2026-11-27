# Networking Concepts

**Platform:** TryHackMe  
**Learning Path:** Cyber Security 101  
**Room:** Networking Concepts

## 1. TCP/IP Model

The TCP/IP Model explains how computers communicate over networks, including the internet.

It has four layers:

| Layer | Name | What It Does |
|---|---|---|
| 4 | Application | Provides network services like HTTP, DNS and SSH |
| 3 | Transport | Uses TCP or UDP for communication between applications |
| 2 | Internet | Handles IP addressing and routing between networks |
| 1 | Network Access | Handles local network communication and physical connections |

### What I Understand

The TCP/IP Model is similar to the OSI Model, but it uses four layers instead of seven.

For example:

- OSI Network Layer = TCP/IP Internet Layer.
- OSI Transport Layer = TCP/IP Transport Layer.
- OSI Physical and Data Link Layers = TCP/IP Network Access Layer.

Understanding these layers can help me identify where a network problem might be happening.

For example, if a computer can communicate with other computers locally but cannot reach another network, I would investigate its IP configuration and routing.

However, I shouldn't automatically assume the router is responsible without investigating further.

---

## 2. IP Addresses

An IP address is a logical address assigned to a network interface.

It helps computers communicate and allows network devices to forward packets towards their destinations.

### IPv4 Addresses

An IPv4 address contains 32 bits divided into four octets.

Example:

`192.168.1.50`

Each octet contains 8 bits and can have a value between 0 and 255.

IP addresses can be divided into a network portion and a host portion.

---

## 3. Subnetting

This was one of the topics I found challenging.

### What Is a Subnet?

From my understanding, subnetting allows a larger IP address range to be divided into smaller networks.

For example, a company might have different subnets for:

- Human Resources
- Finance
- IT Department
- Security Department

This helps organise the network and can make it easier to control communication between departments.

### What Is a Subnet Mask?

A subnet mask tells us which part of an IP address identifies the network and which part identifies the host.

For example:

**IP Address:** `192.168.1.50`

**Subnet Mask:** `255.255.255.0`

This can also be written as:

`192.168.1.50/24`

With `/24`:

- Network portion: `192.168.1`
- Host portion: `50`
- Network address: `192.168.1.0/24`

The fourth octet doesn't disappear. It is used for the host portion.

### What Does /24 Mean?

An IPv4 address contains 32 bits.

The `/24` means the first 24 bits are used for the network portion.

Since each octet contains 8 bits:

8 + 8 + 8 = 24 bits.

That means the first three octets identify the network.

The remaining 8 bits are available for the host portion.

A typical `/24` subnet has:

- 256 total IP addresses.
- 254 usable host addresses.
- One network address.
- One broadcast address.

For example:

**Network:** `192.168.1.0/24`

**Usable host addresses:** `192.168.1.1` to `192.168.1.254`

**Broadcast address:** `192.168.1.255`

### What Does /16 Mean?

A `/16` uses the first 16 bits for the network portion.

Since each octet has 8 bits:

8 + 8 = 16 bits.

This means:

- First two octets = Network portion.
- Last two octets = Host portion.

Example:

**IP Address:** `192.168.5.42/16`

**Network portion:** `192.168`

**Network address:** `192.168.0.0/16`

A typical `/16` network contains 65,536 IP addresses, with 65,534 usable host addresses.

### Difference Between /16 and /24

| Feature | /24 | /16 |
|---|---|---|
| Subnet mask | 255.255.255.0 | 255.255.0.0 |
| Network bits | 24 | 16 |
| Host bits | 8 | 16 |
| Total IP addresses | 256 | 65,536 |
| Usable host addresses | 254 | 65,534 |

A `/16` has more host addresses because it uses fewer bits for the network portion.

### Can Smaller Subnets Exist Inside a Larger Network?

Yes.

For example:

`192.168.0.0/16`

This larger address range can be divided into smaller `/24` subnets:

- `192.168.1.0/24`
- `192.168.2.0/24`
- `192.168.3.0/24`
- `192.168.10.0/24`

All these smaller address ranges fit inside `192.168.0.0/16`.

However, if a company configures them as separate `/24` subnets, they remain separate networks and generally need routing to communicate.

### Example: Comparing Two Computers

Computer A: `192.168.10.50/24`

Computer B: `192.168.11.60/24`

These computers belong to different subnets because `/24` uses the first three octets as the network portion.

Their network addresses are:

- Computer A: `192.168.10.0/24`
- Computer B: `192.168.11.0/24`

But if both computers were configured with `/16`, they would belong to the same subnet:

`192.168.0.0/16`

**What I Need to Remember:**

The subnet mask determines which part of the IP address belongs to the network.

I shouldn't automatically assume that the first three octets always identify the network.

---

## 4. Public and Private IP Addresses

IP addresses can be public or private.

### Private IP Addresses

Private IP addresses are commonly used inside home and company networks.

The main private IPv4 ranges are:

- `10.0.0.0/8`
- `172.16.0.0/12`
- `192.168.0.0/16`

These addresses aren't directly routable over the public internet.

### Public IP Addresses

Public IP addresses are used for communication across the internet.

They require globally coordinated allocation to avoid conflicts.

### What I Learned

Both public and private IP addresses can be subnetted.

Subnetting tells us how an IP address range is divided.

Public or private addressing tells us how the address can be used.

### Why This Matters to a SOC Analyst

A SOC Analyst needs to understand where network traffic is coming from and where it is going.

For example:

**Source IP:** `192.168.1.50`

**Destination IP:** `8.8.8.8`

This shows traffic involving a private source IP and a public destination IP.

I would investigate whether the communication is expected and which internal device is responsible.

However, a connection to a public IP address doesn't automatically mean something malicious is happening.

---

## 5. TCP and UDP

TCP and UDP are Transport Layer protocols.

They both allow applications to communicate over networks, but they work differently.

### TCP — Transmission Control Protocol

TCP is designed to provide reliable and ordered data delivery.

It can:

- Track transmitted data.
- Retransmit missing data.
- Deliver information to an application in the correct order.

For example, if I'm transferring an important security log file, TCP is useful because I want the data to arrive completely and in order.

However, TCP doesn't automatically encrypt information.

### UDP — User Datagram Protocol

UDP sends datagrams without guaranteeing delivery or order.

It doesn't automatically retransmit missing data.

UDP can be useful for applications that need timely updates.

Examples include:

- Online multiplayer games.
- Voice communication.
- Real-time monitoring applications.

### Example: Online Gaming

Imagine I'm playing an online game.

The game constantly sends information about my character's position.

If an old position update gets lost, receiving the latest position may be more useful than waiting for the old update to be retransmitted.

That's one reason online games commonly use UDP.

### TCP vs UDP

| TCP | UDP |
|---|---|
| Reliable, ordered delivery | No built-in delivery guarantee |
| Retransmits missing data | Doesn't automatically retransmit missing data |
| Useful for file transfers | Useful for many real-time applications |
| Doesn't automatically encrypt | Doesn't automatically encrypt |

### What I Initially Misunderstood

I initially thought TCP provides encryption.

But I learned that TCP provides reliable data delivery, not encryption.

Protocols like TLS and SSH can provide encryption to protect information during transmission.

**What I Need to Remember:**

TCP = Reliable delivery.

UDP = No built-in delivery guarantee.

Encryption = A separate security function.

---

## 6. Encapsulation

Encapsulation was another topic I struggled to understand.

### What Is Encapsulation?

From my understanding, encapsulation is the process of adding information to data as it moves down the network layers before being transmitted.

Each layer adds different information to help the data reach the correct destination.

### Example: Sending a Message

Imagine Computer A wants to send the message:

`Hello`

To Computer B.

#### Step 1 — Application Layer

The application creates the original data.

Example:

`Hello`

#### Step 2 — Transport Layer

The Transport Layer adds information such as TCP or UDP port numbers.

Port numbers help identify which application or service should receive the data.

If TCP is used, the data is packaged into a TCP segment.

#### Step 3 — Internet Layer

The Internet Layer adds IP addressing information.

For example:

- Source IP: `192.168.1.10`
- Destination IP: `192.168.1.20`

The destination IP helps routers determine where to forward the packet.

The TCP segment is now inside an IP packet.

#### Step 4 — Network Access Layer

The Network Access Layer adds information such as MAC addresses for local network delivery.

For example:

- Source MAC address.
- Destination MAC address.

The IP packet is placed inside an Ethernet frame.

If the destination is on another network, the destination MAC address normally identifies the next local device, such as the router, rather than the final remote computer.

### What Encapsulation Looks Like

A simplified example:

**Ethernet Frame**

- Ethernet Header — MAC addresses
- IP Header — IP addresses
- TCP Header — Port numbers and TCP information
- Application Data — Original message
- Ethernet Trailer — Error-detection information

All this information is packaged together for transmission.

### What Is Decapsulation?

Decapsulation is the reverse process.

When the destination receives the data, it processes the information through the network layers.

The relevant headers are removed as the data moves up the layers until the application receives the original information.

### Why Is Encapsulation Important?

Each layer adds different information because each layer has a different responsibility.

For example:

- MAC address = Helps with local network delivery.
- IP address = Helps identify the destination across networks.
- Port number = Helps identify the receiving application.

I also learned that encapsulation doesn't automatically mean encryption.

Encapsulation is about packaging information for delivery.

Encryption is about protecting the information.

---

## 7. Viewing Encapsulation in a Terminal

I learned that encapsulation can be observed using packet-capture tools such as Wireshark or TShark.

TShark is the command-line version of Wireshark.

When examining a TCP packet, I might see:

- Ethernet II — MAC addresses.
- IPv4 — Source and destination IP addresses.
- TCP — Source and destination ports.
- Application data — If present and available to inspect.

This helps me understand how information is organised inside network packets.

I want to practise this using Wireshark when I reach that topic in TryHackMe.

---

## 8. Telnet

Telnet is a protocol that allows remote access to computers and network devices.

It commonly uses TCP port 23.

### Why Is Telnet Insecure?

Telnet doesn't encrypt its communication.

This means someone who can intercept the traffic may be able to read sensitive information, including:

- Usernames.
- Passwords.
- Commands.

### Telnet vs SSH

| Telnet | SSH |
|---|---|
| Normally uses TCP port 23 | Normally uses TCP port 22 |
| Doesn't encrypt communication | Encrypts communication |
| Insecure for remote administration | Preferred for secure remote administration |

I would recommend using SSH instead of Telnet when remotely managing company systems.

### Why Is Telnet Still Used?

Telnet was commonly used for remote access before SSH became widely available.

Some older devices still support or depend on Telnet.

A Telnet client can also be used to test TCP connectivity to a particular port.

For example:

`telnet 192.168.1.10 80`

This attempts to establish a TCP connection to port 80.

However, successfully connecting doesn't guarantee that the application is working correctly.

### PowerShell Alternative

On Windows, I can use:

`Test-NetConnection 192.168.1.10 -Port 80`

This checks whether a TCP connection to the specified port can be established.

---

## 9. How This Helps Me as a SOC Analyst

Understanding networking can help me investigate:

- Suspicious IP addresses.
- Unusual network connections.
- Communication between different networks.
- Unexpected open ports.
- Insecure remote-access protocols.
- Network configuration problems.

### Example: Troubleshooting

Imagine an employee can access a server using its IP address but cannot access it using its domain name.

I would investigate DNS because DNS is responsible for resolving domain names into IP addresses.

Another example is when a computer successfully pings a server but cannot connect to TCP port 443.

A successful ping only confirms that the destination responded to an ICMP request.

It doesn't prove that the HTTPS application is working.

I would investigate the TCP connection, the listening service and any firewall rules that might be blocking it.

### Important Lesson

I shouldn't assume that unusual network activity is automatically malicious.

I need to investigate, gather evidence and understand what happened before reaching a conclusion.

---

## 10. My Reflection

I found this room challenging, especially subnetting and encapsulation.

At first, I didn't understand how `/16` and `/24` worked or why smaller subnets could exist within a larger address range.

I kept asking questions because I wanted to understand the concept instead of just memorising the answer.

I learned that the subnet mask determines the network portion and host portion of an IP address.

I also struggled with encapsulation because I didn't understand why different layers needed to add different information.

After going through examples, I started to understand that each layer has its own responsibility.

Another thing I struggled with was confusing TCP reliability with encryption.

I now understand that TCP handles reliable delivery, while security protocols such as TLS or SSH can provide encryption.

### What I Need to Improve

- Remembering technical terms.
- Explaining networking concepts in my own words.
- Understanding how different networking concepts work together.
- Applying what I've learned to practical investigations.
- Taking my time instead of rushing.

I still don't think I've completely mastered subnetting, but I understand it better than when I started.

I plan to revisit these notes and practise using tools like Wireshark to improve my understanding.
