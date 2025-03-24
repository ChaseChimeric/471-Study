# Digital signature schemes|Digital Signature Schemes

## Overview  
Digital signature schemes provide varying levels of security based on different requirements and attack models. They ensure message integrity, authenticity, and non-repudiation.  

## Security Requirements and Attack Models  
Digital signatures must be resistant to several types of attacks, categorized into three main models:  

1. **Key-Only Attack**: The attacker only has access to the public key and tries to forge a signature.  
2. **Known Message Attack**: The attacker has valid message-signature pairs and attempts forgery.  
3. **Chosen Message Attack**: The attacker can request signatures for messages of their choice to find weaknesses.  

## RSA Signatures  
RSA-based digital signatures rely on the RSA cryptosystem and typically follow a "hash-then-sign" approach.  

### Construction  
1. Generate an RSA key pair: a **public key (e, N)** and a **private key (d, N)**.  
2. Compute a cryptographic hash of the message.  
3. Encrypt the hash using the private key to produce the signature.  
4. The recipient verifies the signature by decrypting it with the public key and comparing it to the expected hash.  

### Possible Attacks  
- **Signature Forgery**: If the hash function is weak or improperly used, an attacker may craft a different message with the same signature.  
- **RSA Key Factorization**: If the modulus \(N\) is weak or improperly generated, an attacker could factor it and derive the private key.  
- **Bleichenbacher’s Attack**: A padding oracle attack that exploits incorrect padding validation in RSA implementations.  

### Hash Then Sign  
Using a cryptographic hash function before signing improves security:  
- Reduces message size, making signature computation more efficient.  
- Prevents direct manipulation of the message, ensuring authenticity.  
- Hash functions like **SHA-256** are commonly used to mitigate length-extension attacks.  

Proper implementation of digital signature schemes ensures secure authentication and data integrity.  
