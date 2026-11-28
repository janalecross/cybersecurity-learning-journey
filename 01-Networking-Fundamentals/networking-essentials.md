# Networking Essentials — TryHackMe

**Learning Path:** Cyber Security 101  
**Room:** Networking Essentials  
**Topics:** DHCP, ARP, ICMP, Routing and NAT

## 1. DHCP — Dynamic Host Configuration Protocol

### What I learned

DHCP automatically provides devices with the network settings they need to communicate.

Imagine manually configuring 100 computers in a workplace. That would take a lot of time. DHCP makes this process easier by automatically assigning network settings.

DHCP can provide:

- **IP address:** Identifies my device on the network.
- **Subnet mask:** Helps determine which IP addresses belong to my local network.
- **Default gateway:** Allows my device to reach other networks.
- **DNS server:** Helps translate domain names into IP addresses.

### How DHCP works — DORA

DHCP uses a process called DORA:

1. **Discover:** My laptop looks for a DHCP server.
2. **Offer:** The DHCP server offers an IP address and network settings.
3. **Request:** My laptop requests the offered settings.
4. **Acknowledge:** The server confirms the assignment.

### Questions I had

**Shouldn't my laptop already know its IP address?**

My laptop might remember an old IP address, but that address might not work when I connect to another network.

For example, an IP address used at home might not be suitable for my workplace network.

That's why my laptop may need to request new network settings from DHCP.

**Is a DHCP server a physical computer?**

Not necessarily.

A DHCP server can be:

- A service running on my home router.
- A physical server.
- A virtual server.
- A supported network device.

**Can two computers have the same private IP address?**

Yes, if they're on separate networks.

For example, my laptop at home and another computer at work could both use `192.168.1.50` without causing a conflict, provided their networks are separate.

However, two devices using the same IP address on the same local subnet can cause an IP address conflict.

### Useful Windows command

```cmd
ipconfig /all
```

This can show my IP address, subnet mask, default gateway, DNS servers and DHCP information.

### SOC Analyst connection

DHCP logs can help identify which device was assigned a particular IP address at a specific time.

This can be useful when investigating suspicious network activity.

---

## 2. ARP — Address Resolution Protocol

### What I learned

ARP is used to find the MAC address associated with an IPv4 address on a local network.

For example:

- Computer A: `192.168.1.10`
- Computer B: `192.168.1.20`

Computer A knows Computer B's IP address, but it doesn't know its MAC address.

Computer A sends an ARP request asking which device owns `192.168.1.20`.

Computer B responds with its MAC address.

Computer A can then use that MAC address to send an Ethernet frame to Computer B.

**Important:** ARP discovers the MAC address. It doesn't deliver the application data itself.

### What happens when the destination is on another network?

If Computer B is on another subnet, Computer A doesn't use ARP to find Computer B's MAC address.

Instead, Computer A uses ARP to find the MAC address of its **default gateway**.

It then sends the Ethernet frame to the gateway so the packet can be forwarded towards the other network.

### Useful Windows command

```cmd
arp -a
```

This displays ARP cache entries, including known IPv4 and MAC address mappings.

### SOC Analyst connection

Attackers can use a technique called **ARP spoofing**.

This involves sending misleading ARP information to associate an IP address with the wrong MAC address.

An attacker might use this to redirect or intercept traffic.

However, unusual ARP activity should be investigated before assuming an attack has occurred.

---

## 3. ICMP — Internet Control Message Protocol

### What I learned

ICMP helps devices report network errors and provides information useful for troubleshooting connections.

Two commands I learned about are `ping` and `tracert`.

### Ping

```cmd
ping 8.8.8.8
```

Ping commonly uses ICMP Echo Requests and Echo Replies to test whether a destination responds.

If I receive a reply, it means the destination responded to the ICMP request.

If I receive:

```text
Request timed out.
```

It means my computer didn't receive the expected reply within the timeout period.

### Does a failed ping mean the server is offline?

No.

There could be different reasons:

- The server is offline.
- A firewall is blocking ICMP.
- There is a network connectivity problem.
- Network devices are dropping the packets.

I shouldn't immediately assume the server is offline just because the ping failed.

### Tracert

```cmd
tracert 8.8.8.8
```

This command helps investigate the network path towards a destination.

On Windows, `tracert` uses ICMP messages to help identify routers along the route.

However, some routers might not respond, so missing hops don't automatically mean the network is broken.

### SOC Analyst connection

ICMP can be used for legitimate troubleshooting, but attackers may also use it to discover active devices on a network.

This can include **ping sweeping**, where multiple IP addresses are checked for responses.

I learned that unusual activity doesn't automatically mean malicious activity.

---

## 4. Routing and Default Gateway

### What I learned

Routing allows packets to travel between different networks.

A router uses a **routing table** to determine where a packet should be forwarded.

### Example

Computer A:

```text
192.168.1.50/24
```

Computer B:

```text
192.168.2.60/24
```

Both computers belong to different subnets.

The `/24` means the first 24 bits identify the network portion.

In this example:

- Computer A's network: `192.168.1.0/24`
- Computer B's network: `192.168.2.0/24`

Because the network portions are different, the computers normally need a router to communicate.

### What is a default gateway?

This was something I didn't completely understand at first.

A default gateway is usually my router's IP address on my local network.

I think of it like the exit door of my local network.

For example:

```text
My laptop:       192.168.1.50
Subnet mask:     255.255.255.0
Default gateway: 192.168.1.1
```

If my laptop wants to communicate with another network, it can send the packet to the default gateway.

The router then checks its routing table to decide where to forward it.

### How routing connects to ARP

If the destination is on another subnet:

1. My laptop determines that the destination is outside its local network.
2. It identifies the default gateway as the next destination for the Ethernet frame.
3. It uses ARP to find the gateway's MAC address if needed.
4. It sends the frame to the router.
5. The router forwards the IP packet towards the destination.

The packet keeps the destination server's IP address while travelling through the network, unless something such as NAT changes it.

### Useful Windows commands

Check my IP address and default gateway:

```cmd
ipconfig
```

View my computer's routing table:

```cmd
route print
```

### SOC Analyst connection

Routing problems can prevent employees from accessing services on other networks.

Possible causes include incorrect gateway settings, routing problems or firewall rules.

I should investigate the evidence before deciding what caused the problem.

---

## 5. NAT — Network Address Translation

### What I learned

NAT allows IP addresses to be translated when traffic moves between networks.

A common use of NAT is allowing multiple devices with private IPv4 addresses to share one public IPv4 address.

This helps reduce the number of public IPv4 addresses needed.

### Example

Three computers are connected to the same network:

```text
Computer A: 192.168.1.10
Computer B: 192.168.1.20
Computer C: 192.168.1.30
```

The router uses this example public IP address:

```text
203.0.113.10
```

All three computers can access the internet using that public IP address.

**Important:** The computers still have their own private IP addresses. The router translates their connections to use its public IP address.

### PAT — Port Address Translation

PAT is a type of NAT that uses port numbers to keep track of different connections.

For example:

| Computer | Translated public connection |
|---|---|
| Computer A | `203.0.113.10:40001` |
| Computer B | `203.0.113.10:40002` |
| Computer C | `203.0.113.10:40003` |

These port numbers are examples.

PAT doesn't permanently give each computer its own port. It manages translations for individual connections.

The router uses a translation table to determine where returning traffic should go.

### Does NAT provide encryption?

No.

NAT translates network addresses. It doesn't automatically encrypt traffic.

It also doesn't replace the need for a firewall.

### SOC Analyst connection

Imagine I discover suspicious traffic from:

```text
203.0.113.10
```

I cannot immediately identify which employee's computer was responsible because multiple devices might share that public IP address.

I would investigate:

1. **NAT logs:** To match the public connection to an internal IP address.
2. **Ports and timestamps:** To identify the relevant connection.
3. **DHCP logs:** To determine which device used that internal IP address.
4. **Authentication logs:** To investigate which user account was active.
5. **Device activity:** To understand what generated the connection.

I also learned that identifying a device doesn't automatically prove which employee caused the activity.

---

## 6. Commands I Learned

| Command | Purpose |
|---|---|
| `ipconfig` | Shows basic network settings, including my IP address and default gateway |
| `ipconfig /all` | Shows more detailed network configuration |
| `arp -a` | Displays known IPv4-to-MAC address mappings |
| `ping 8.8.8.8` | Checks whether a destination responds to ICMP |
| `tracert 8.8.8.8` | Helps investigate the network path |
| `route print` | Shows my computer's routing table |

## 7. How These Concepts Work Together

This is how I understand the process when my laptop connects to another network:

1. **DHCP** provides my laptop with network settings.
2. The **subnet mask** helps my laptop determine whether the destination is on the same subnet.
3. If the destination is on another network, my laptop uses its **default gateway**.
4. **ARP** can help my laptop discover the gateway's MAC address.
5. The **router** forwards the packet using its routing table.
6. **NAT/PAT** may translate the connection when accessing the internet.
7. **ICMP** can help troubleshoot connectivity problems.

These protocols and technologies work together to make network communication possible.

---

## 8. My Reflection

### What I learned

I learned more about how devices communicate with each other through a network.

Before this lesson, I knew that routers help devices connect to the internet, but I didn't completely understand how DHCP, ARP, routing and NAT work together.

I now have a better understanding of why devices need IP addresses, how they find MAC addresses and how packets travel between different networks.

### What I found challenging

I found the default gateway and NAT/PAT confusing at first.

I also made a mistake when identifying the octets of an IP address.

Sometimes I understand the general idea, but I struggle to explain the technical details clearly.

### What I need to improve

- Remembering the purpose of each protocol.
- Understanding how different networking concepts connect.
- Paying more attention to IP addresses and subnet masks.
- Explaining technical topics clearly in my own words.
- Taking my time before reaching a conclusion.

### How I can apply this as a SOC Analyst

I learned that investigating network activity requires patience.

For example, if a ping fails, I shouldn't immediately assume the server is offline.

If I discover suspicious traffic from a public IP address, I shouldn't immediately assume I know which device or employee was responsible.

I need to examine logs, timestamps and other evidence before making a conclusion.

**My biggest takeaway is that I should focus on understanding what the evidence tells me instead of rushing to an answer.**
