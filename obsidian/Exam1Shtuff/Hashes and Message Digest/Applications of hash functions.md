# Applications of Hash Functions

## 1. Common Applications
Cryptographic hash functions are widely used in various security applications, including:

- **Integrity Check**: Verifies that data has not been altered (e.g., file checksums, digital signatures).
- **Authentication**: Used in password hashing and challenge-response authentication schemes.
- **Commitment Protocols**: Helps in securing commitments before revealing information.
- **Encryption**: Often used in conjunction with encryption for additional security.

## 2. Securely Combining Hash Functions with Encryption
To achieve both **confidentiality** and **authentication/integrity protection**, different cryptographic techniques can be combined:

### a) **Encrypt-then-MAC (EtM)**
- Encrypt the plaintext with a symmetric cipher (e.g., [[DES and AES#**AES (Advanced Encryption Standard)**|AES]]).
- Compute a [[Message authentication codes|Message Authentication Code (MAC)]] on the ciphertext.
- Send both the ciphertext and MAC.
- **Security**: Ensures integrity and authenticity before decryption.

### b) **MAC-then-Encrypt**
- Compute a MAC on the plaintext.
- Encrypt both the plaintext and the MAC together.
- **Security**: Less secure than EtM but used in some legacy systems.

### c) **Encrypt-and-MAC**
- Encrypt the plaintext.
- Compute a MAC on the plaintext separately.
- Send both the ciphertext and MAC.
- **Security**: Vulnerable to certain attacks, not recommended.

### d) **AEAD (Authenticated Encryption with Associated Data)**
- Uses specialized encryption modes (e.g., GCM, CCM) to provide both confidentiality and integrity.
- **Recommended** for modern cryptographic applications.

## 3. Best Practices
- **Use strong hash functions** (e.g., SHA-256, SHA-3).
- **Avoid broken hash functions** (e.g., MD5, SHA-1).
- **Use HMAC for authentication** rather than raw hash functions.
- **Prefer AEAD modes** for encrypting data securely.

