## 1. Secret Key Cryptography (Symmetric Cryptography)
- **Description**: Uses a single shared key for both encryption and decryption.
- **Common Algorithms**: AES, DES, 3DES
- **Security Goals Achieved**:
  - **Confidentiality**: Ensures that only authorized parties with the key can read the data.
  - **Integrity** (to some extent): If combined with cryptographic hash functions or message authentication codes (MACs).
  - **Authentication**: Can be used for authentication protocols but typically requires additional mechanisms.

## 2. Public Key Cryptography (Asymmetric Cryptography)
- **Description**: Uses a key pair (public key for encryption/signing verification, private key for decryption/signing).
- **Common Algorithms**: RSA, ECC, Diffie-Hellman, DSA
- **Security Goals Achieved**:
  - **Confidentiality**: Messages encrypted with the public key can only be decrypted by the private key owner.
  - **Integrity**: Digital signatures ensure that messages have not been altered.
  - **Authentication**: Digital signatures prove the identity of the sender.
  - **Non-repudiation**: Digital signatures prevent the sender from denying their message.

## 3. Hash Functions
- **Description**: Converts data into a fixed-length hash value, which is unique to the input.
- **Common Algorithms**: SHA-256, SHA-3, MD5 (not recommended for security).
- **Security Goals Achieved**:
  - **Integrity**: Ensures data has not been modified by generating a unique hash.
  - **Authentication** (when used with HMAC): Verifies message authenticity in combination with a secret key.
  - **Non-repudiation** (indirectly): Digital signatures rely on hashing to prevent message tampering.

---

### Summary Table

| Cryptography Type  | Confidentiality | Integrity             | Authentication                           | Non-repudiation |
| ------------------ | --------------- | --------------------- | ---------------------------------------- | --------------- |
| **Secret Key**     | ✅ Yes           | ⚠️ Partial (with MAC) | ⚠️ Possible (with additional mechanisms) | ❌ No            |
| **Public Key**     | ✅ Yes           | ✅ Yes                 | ✅ Yes                                    | ✅ Yes           |
| **Hash Functions** | ❌ No            | ✅ Yes                 | ⚠️ Possible (with HMAC)                  | ⚠️ Indirectly   |

