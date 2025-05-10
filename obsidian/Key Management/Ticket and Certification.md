# What Information Is Included in a Ticket or Certificate?

## Tickets (KDC-based Symmetric Key)
- **Session Key:** The temporary key for the session (e.g., KAB).
- **Identifiers:** Identities of initiator and recipient (e.g., A and B).
- **Lifetime/Expiration:** How long the ticket/session key remains valid.
- **Encrypted:** The key and information are encrypted with the recipient's long-term key.

## Certificates (CA-based Public Key)
- **Subject:** The entity (user, server) whose public key is certified.
- **Public Key:** The subject's public key.
- **Issuer:** The CA's identity.
- **Serial Number:** Unique certificate number.
- **Validity Period:** Start and expiration dates.
- **Signature:** Digital signature by the CA to protect the certificate's integrity and authenticity.

Certificates may include other optional fields (e.g., usage constraints, extensions).