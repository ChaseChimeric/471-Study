# IPSec

## The Three Protocols in IPSec

### 1. **AH (Authentication Header)**
- **Services Provided**: Integrity and origin authentication.
- **Function**: Protects against packet tampering and spoofing by including an Integrity Check Value (ICV) using HMAC (e.g., HMAC-MD5-96, HMAC-SHA1-96).
- **Covers**: IP payload and immutable/predictable parts of IP header.
- **Limitation**: No confidentiality (encryption).

### 2. **ESP (Encapsulating Security Payload)**
- **Services Provided**: Confidentiality (encryption), and optionally integrity and authentication.
- **Function**: Encrypts payload and optionally authenticates it. 
- **Flexibility**: Can provide encryption-only, integrity-only, or both.
- **Limitation**: Does not protect IP header fields unless used in tunnel mode.

### 3. **IKE (Internet Key Exchange)**
- **Purpose**: Establishes the Security Associations (SA) for AH and ESP.
- **Function**: Negotiates keys, algorithms, and policies.
- **Critical Note**: If IKE is compromised, AH and ESP cannot offer protection.

---

## Security Association (SA), Security Policy, and SPI

- **Security Association (SA)**:
  - A one-way secure connection defined by: `<SPI, destination IP address, protocol (AH/ESP)>`.
  - Contains cryptographic parameters, sequence numbers, algorithms, and mode (transport/tunnel).
  - Two SAs are required for bidirectional communication.

- **Security Parameter Index (SPI)**:
  - A unique identifier included in AH or ESP headers.
  - Used with destination IP and protocol to identify the correct SA.

- **Security Association Database (SAD)**:
  - Stores active SAs.
  - Used to determine how to process incoming/outgoing packets.

- **Security Policy Database (SPD)**:
  - Contains rules to determine how to handle packets (e.g., discard, pass, or apply IPsec).
  - If IPsec is selected, the SPD guides whether to use an existing SA or initiate IKE negotiation.

---

## IPsec Modes: Transport vs Tunnel

### **Transport Mode**
- **Structure**: IPsec inserted between IP header and payload.
- **Protects**: Only the payload of the original IP packet.
- **Common Use**: End-to-end communication (e.g., host-to-host).
- **AH**: Authenticates payload and portions of IP header.
- **ESP**: Encrypts payload; IP header remains visible.

### **Tunnel Mode**
- **Structure**: Original IP packet encapsulated within a new IP packet.
- **Protects**: Entire original IP packet, including the header.
- **Common Use**: Gateway-to-gateway or host-to-gateway VPNs.
- **AH**: Authenticates the entire encapsulated packet and portions of new header.
- **ESP**: Encrypts and optionally authenticates entire inner packet.

---

## Packet Processing by AH and ESP

### **AH Header Structure**
[![AH Header Structure]](https://en.wikipedia.org/wiki/IPsec#/media/File:Ipsec-ah.svg)

**Processing**:
- Computes a MAC over:
  - Immutable and predictable IP header fields
  - Entire payload
  - AH header (excluding Authentication Data field)

### **ESP Header Structure**
[![ESP Header Structure]](https://en.wikipedia.org/wiki/IPsec#/media/File:Ipsec-esp-tunnel-and-transport.svg)

**Processing**:
- Encrypts payload (and optional padding).
- Authenticates entire ESP packet if enabled.

---

## VPN and IPSec

- **Virtual Private Network (VPN)**:
  - Extends a private network over a public one.
  - Provides secure remote access and site-to-site connectivity.

- **Relation to IPSec**:
  - IPSec is often used to implement VPNs.
  - **Tunnel mode** is typically used in VPNs to encapsulate and protect entire packets.
  - Ensures confidentiality, integrity, and authentication over untrusted networks.
