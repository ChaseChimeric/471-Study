# Basic Concepts of Public Key Cryptography
Public key cryptography uses two keys: a **public key** (known to everyone) and a **private key** (known only to the owner). The public key is used for encryption and the private key for decryption. This system enables secure communication and digital signatures without the need for a shared secret key.

## Public Key Encryption
- **Public key encryption** allows anyone to encrypt messages using the public key, but only the recipient can decrypt the message using their private key.
- Achieves **confidentiality** by ensuring only the intended recipient can read the message.

## Digital Signatures
- A **digital signature** is used to verify the authenticity and integrity of a message. The sender signs the message using their private key, and the recipient verifies the signature using the sender's public key.
- Achieves **authentication** and **integrity**, ensuring the message is from the claimed sender and has not been altered.

## Security Properties
See [[Information Concepts]]
