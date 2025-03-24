# Applications of Public Key Encryption and Digital Signatures

## Basic Applications

### 1. **Secure Communication (Confidentiality)**
   - Public key encryption ensures that only the intended recipient can read a message.
   - Example: **SSL/TLS (HTTPS)** encrypts web traffic using asymmetric cryptography.

### 2. **Authentication**
   - Digital signatures verify the identity of the sender.
   - Example: **Code signing** ensures that software comes from a trusted source.

### 3. **Data Integrity**
   - Digital signatures prevent unauthorized modifications to data.
   - Example: **Signed documents** (e.g., PDFs) ensure content has not been altered.

### 4. **Key Exchange**
   - Asymmetric encryption helps securely exchange symmetric encryption keys.
   - Example: **Diffie-Hellman key exchange** combined with RSA.

---

## Combining Signature and Encryption for Confidentiality & Integrity

To achieve **both confidentiality and authentication/integrity protection**, we must securely combine **digital signatures** and **encryption**.

### **Method 1: Sign-Then-Encrypt (STE)**
1. Sender **signs** the message using their private key:
   $$
   S = \text{Sign}_{\text{priv}_S}(M)
   $$
2. Sender **encrypts** both the message and the signature using the recipient’s public key:
   $$
   C = \text{Encrypt}_{\text{pub}_R}(M, S)
   $$
3. Recipient **decrypts** the ciphertext using their private key:
   $$
   (M, S) = \text{Decrypt}_{\text{priv}_R}(C)
   $$
4. Recipient **verifies** the signature using the sender’s public key:
   $$
   \text{Verify}_{\text{pub}_S}(M, S)
   $$

✅ **Pros:** Ensures confidentiality, authentication, and integrity.  
❌ **Cons:** If the recipient’s private key is compromised, the signature can be extracted.

---

### **Method 2: Encrypt-Then-Sign (ETS)**
1. Sender **encrypts** the message using the recipient’s public key:
   $$
   C = \text{Encrypt}_{\text{pub}_R}(M)
   $$
2. Sender **signs** the ciphertext using their private key:
   $$
   S = \text{Sign}_{\text{priv}_S}(C)
   $$
3. Recipient **verifies** the signature:
   $$
   \text{Verify}_{\text{pub}_S}(C, S)
   $$
4. Recipient **decrypts** the ciphertext:
   $$
   M = \text{Decrypt}_{\text{priv}_R}(C)
   $$

✅ **Pros:** Signature is protected from decryption attacks.  
❌ **Cons:** Does not prove the sender intended to send a specific message (signature is over ciphertext, not plaintext).

---

### **Method 3: Sign-And-Encrypt-And-Sign (SEES)**
1. Sender signs the message:  
   $S_1 = \text{Sign}_{\text{priv}_S}(M)$  
2. Encrypts both the message and the first signature:  
   $C = \text{Encrypt}_{\text{pub}_R}(M, S_1)$  
3. Adds an outer signature on the ciphertext:  
   $S_2 = \text{Sign}_{\text{priv}_S}(C)$  
4. Recipient verifies the outer signature, decrypts the message, and verifies the inner signature.

✅ **Pros:** Strongest security guarantees.  
❌ **Cons:** Computationally expensive.

---

## Summary
- Public key encryption provides **confidentiality**.
- Digital signatures provide **authentication and integrity**.
- **Sign-Then-Encrypt (STE)** is widely used but exposes the signature if decryption fails.
- **Encrypt-Then-Sign (ETS)** is more secure but does not guarantee message intent.
- **Sign-And-Encrypt-And-Sign (SEES)** offers the best security but is resource-intensive.
