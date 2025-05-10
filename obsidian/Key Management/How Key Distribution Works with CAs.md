# How Key Distribution Works with CAs

## Public Key Distribution via CA

1. **Key Generation and Certification:**
    - Each user generates a public/private key pair.
    - User submits their public key and identity information to a CA.
    - CA verifies the user's identity and issues a digitally signed certificate binding the user's identity to their public key.

2. **Certificate Usage:**
    - User presents their certificate to others.
    - Recipients verify the digital signature using the CA's well-known public key, establishing that the public key belongs to the claimed user.

## CA Benefits
- Enables secure discovery of public keys across potentially untrusted networks.
- Scalable design; trust is anchored in the widely recognized CA public key.