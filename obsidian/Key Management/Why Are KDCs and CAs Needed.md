# Why Are KDCs and CAs Needed?

## Key Distribution Center (KDC)
In symmetric key systems, every pair of users needs to securely share a secret key. Directly managing separate keys for each pair does not scale, as it would require each user to remember O(n) keys for n users.

A **KDC** serves as a trusted intermediary, helping users establish secure, temporary session keys when they need to communicate. Each user shares just one long-term secret (with the KDC), simplifying key management and improving scalability.

## Certification Authority (CA)
In public-key systems, verifying that a public key actually belongs to the claimed entity is crucial. When users exchange public keys, attackers might substitute their own keys (man-in-the-middle attack).

A **CA** solves this by vouching for the authenticity of public keys. It issues certificates that securely bind a user's identity to their public key, allowing others to trust the key's ownership.