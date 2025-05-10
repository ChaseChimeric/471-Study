# Components of IEEE 802.11i Wireless LAN Security Architecture

IEEE 802.11i (also known as Robust Security Network, RSN) enhances wireless LAN security through:

- **IEEE 802.1X Authentication:**  
  - Uses the Extensible Authentication Protocol (EAP) over LAN (EAPOL).
  - Three roles: supplicant (client), authenticator (AP), and authentication server (often RADIUS).
  - Enables dynamic, per-user authentication.
- **Four-Way Handshake:**  
  - Used to derive fresh session keys (Pairwise Transient Key, PTK) after authentication.
  - Ensures mutual authentication between client and AP.
- **Data Encryption:**  
  - Temporal Key Integrity Protocol (TKIP) for backward compatibility.
  - Counter Mode CBC-MAC Protocol (CCMP) with AES for strong encryption.
- **Key Hierarchy and Management:**  
  - Distinction between long-term credentials (passwords/certificates) and session keys.
- **Replay Protection & Integrity:**  
  - Use of nonces, message integrity codes (MIC), and replay counters.
- **Robust Security Network (RSN) Capabilities:**  
  - Defines authentication and encryption suites for APs and clients.

802.11i design adds strong authentication and encryption to wireless networks, greatly improving upon earlier methods.