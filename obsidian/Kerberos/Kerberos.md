# Kerberos

## Function of Kerberos V4 and Security Services

Kerberos V4 is a network authentication protocol designed to provide secure authentication over untrusted networks using secret-key cryptography.

### Security Services Provided
- **Authentication**: Verifies identities of users and services.
- **Replay protection**: Includes timestamps to prevent replay attacks.
- **Session confidentiality**: Uses session keys to secure communications.
- **Ticket-based access**: Minimizes repeated use of long-term credentials.

Kerberos V4 does not provide encryption of data traffic (only authentication), and assumes trusted time synchronization among systems.

---

## Basic Model and Configuration

- **Client (User/Principal)**: A person or process requesting services.
- **Server**: Provides a service that a client wants to access.
- **Key Distribution Center (KDC)**: Central server handling authentication.
  - Composed of:
    - **Authentication Server (AS)**
    - **Ticket Granting Server (TGS)**

Each principal shares a **long-term key** with the KDC:
- For users, derived from a password.
- For services, preconfigured securely.

All credentials are managed in the KDC’s database as `<principal, key>` pairs.

📌 Diagram: [![Kerberos_Configuration]](https://en.wikipedia.org/wiki/Kerberos_(protocol)#/media/File:Kerberos_protocol.svg)

---

## Kerberos Authentication Mechanism

### Key Concepts

| Term | Description |
|------|-------------|
| **Long-term key** | Shared between user and KDC (e.g., KA) |
| **Session key** | Temporary key for client-server communication (e.g., KAB) |
| **Ticket** | Encrypted data allowing access to services |
| **Ticket-Granting Ticket (TGT)** | Special ticket used to obtain other tickets |
| **Authenticator** | A timestamped message proving the sender's identity |
| **Credential** | Ticket + session key issued to the client |

### Message Exchange Flow

#### 1. Authentication Request (AS_REQ / AS_REP)
- Client → AS: Request access
- AS → Client: Response includes
  - Session key SA (for TGS)
  - Ticket-Granting Ticket (TGT)

