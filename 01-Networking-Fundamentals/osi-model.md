# Networking Concepts — OSI Model

**Platform:** TryHackMe  
**Room:** Networking Concepts

## What I Learned

The OSI Model stands for Open Systems Interconnection. It has 7 layers that help explain how computers communicate over a network.

### The 7 Layers

| Layer | Name | What I Understand |
|---|---|---|
| 7 | Application | Provides network services like HTTP and DNS |
| 6 | Presentation | Handles data formatting and encryption |
| 5 | Session | Manages communication sessions |
| 4 | Transport | Uses protocols like TCP and UDP to transfer data |
| 3 | Network | Uses IP addresses to route packets between networks |
| 2 | Data Link | Uses MAC addresses for communication on a local network |
| 1 | Physical | Handles physical connections and signals, like Ethernet cables |

## What I Understand

- **Physical Layer:** If an Ethernet cable is unplugged, I would investigate Layer 1.
- **Data Link Layer:** A switch uses MAC addresses to help forward data to the correct device on a local network.
- **Network Layer:** A router uses IP addresses and its routing table to forward packets between networks.
- **Transport Layer:** TCP provides reliable data delivery, while UDP doesn't guarantee delivery.
- **Session Layer:** Helps manage communication sessions between applications.
- **Presentation Layer:** Deals with how data is represented, including formatting and encryption.
- **Application Layer:** Includes protocols like DNS, HTTP and HTTPS.

## How This Helps a SOC Analyst

Understanding the OSI Model can help me investigate network problems and identify where the issue might be.

For example, if an employee can access a website using its IP address but not its domain name, I would investigate DNS.

I also learned that something unusual doesn't automatically mean it's malicious. I still need evidence before making a conclusion.

## My Reflection

I learned how the OSI Model works and the responsibilities of each layer.

One thing I found challenging was understanding the difference between TCP and encryption. I initially thought TCP encrypts data, but I learned that TCP provides reliable delivery. Encryption is handled by other protocols, such as TLS or SSH.

I still need to improve my understanding of networking and remembering technical terms.

I will continue reviewing my notes and practising what I've learned.
