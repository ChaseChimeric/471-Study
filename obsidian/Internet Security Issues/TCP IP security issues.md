# TCP/IP Security Vulnerabilities and Attacks

## 1. ARP Cache Poisoning

**Description**:  
ARP (Address Resolution Protocol) cache poisoning is a type of attack where a malicious actor sends fake ARP messages on a local network. This leads to incorrect mappings between IP addresses and MAC addresses in the ARP cache of network devices.

**Impacts**:
- Redirecting traffic to the attacker (Man-in-the-Middle attack)
- Disrupting network communication
- Data theft or session hijacking

**Defense**:
- Use static ARP entries where possible
- Monitor and alert on unexpected ARP changes
- Employ network segmentation and VLANs

---

## 2. DDoS Attack (Smurf Attack)

**Description**:  
A smurf attack is a type of Distributed Denial of Service (DDoS) attack that uses ICMP echo requests (pings) directed to an IP broadcast address. The attacker's source IP is spoofed to be the victim's IP, causing all the responses to flood the victim with traffic.

**Impacts**:
- Overwhelms targeted network resources and bandwidth
- Causes denial of service to legitimate users

**Defense**:
- Disable ICMP responses to broadcast requests on routers
- Use ingress/egress filtering to prevent spoofed packets
- Maintain strong network monitoring

---

## 3. IP Address Spoofing (ICMP Protocol)

**Description**:  
IP address spoofing is the crafting of IP packets with a false source IP address, often used in conjunction with ICMP protocols to impersonate other hosts or perform attacks like the "Smurf" attack.

**Impacts**:
- Enables denial of service and reflection attacks
- Hides attacker identity
- Facilitates session hijacking

**Defense**:
- Implement packet filtering to drop packets with spoofed addresses
- Apply ingress and egress filtering on network perimeter devices
- Use authentication for sensitive communications

---

## 4. Eavesdropping

**Description**:  
Eavesdropping refers to the unauthorized interception of network traffic. On unsecured networks, attackers can capture packets and obtain sensitive information such as passwords and session cookies.

**Impacts**:
- Theft of private data (passwords, credit card numbers)
- Session hijacking
- Compromise of authentication information

**Defense**:
- Use end-to-end encryption for sensitive communications (TLS/SSL)
- Use secure protocols instead of plain-text protocols (e.g., SSH instead of telnet)
- Implement network segmentation

---

## 5. TCP SYN Flooding Attack

**Description**:  
A TCP SYN flood is a denial of service attack where the attacker rapidly sends SYN (synchronize) requests to a target's server in an attempt to exhaust server resources, leaving many connections half-open.

**Impacts**:
- Server unable to accept new connections
- Denial of service to legitimate users

**Defense**:
- Use SYN cookies and increasing backlog queue sizes
- Lower SYN timeout periods
- Employ intrusion detection/prevention systems

---

## Summary Table

| Attack Type           | Vulnerability/Method              | Impact                              | Defense Measures                |
|-----------------------|-----------------------------------|-------------------------------------|---------------------------------|
| ARP Cache Poisoning   | Spoofed ARP replies               | MITM, DoS, session hijacking        | Static ARP, monitoring, VLANs   |
| Smurf DDoS Attack     | ICMP echo to broadcast w/ spoofed IP | Network flooding, DoS              | Disable ICMP, filtering         |
| IP Spoofing (ICMP)    | Forged source IP                  | Reflection attacks, hiding identity | Filtering, authentication       |
| Eavesdropping         | Packet sniffing on unencrypted net| Data theft, session hijacking       | Use encryption                  |
| TCP SYN Flooding      | SYN/ACK handshake abuse           | Server/Service DoS                  | SYN cookies, IDS, timeouts      |

---