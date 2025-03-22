# One-Time Pad

## Construction of One-Time Pad
The One-Time Pad (OTP) is a symmetric key cipher where the plaintext is encrypted using a key that is randomly generated, as long as the plaintext message itself. Each character of the plaintext is combined with the key using an XOR operation. This is a [[Early ciphers#Stream and Block Ciphers#Stream Ciphers |Stream Cipher]]
- The key is completely random.
- Each key is used only once (hence "one-time").

## XOR Operation
The XOR (exclusive OR) operation is used in the One-Time Pad encryption. The XOR operation compares corresponding bits of the plaintext and key and returns 1 if the bits are different, and 0 if they are the same.

- **Formula**: 
  $$ C = P \oplus K $$  
  Where:
  - \( C \) = Ciphertext
  - \( P \) = Plaintext
  - \( K \) = Key
  - $( \oplus )$ = XOR operation

For example:
- Plaintext bit: `1101`
- Key bit: `1010`
- Ciphertext bit: `0111` (Result of XOR operation)

The XOR operation ensures that the ciphertext is completely unpredictable without knowing the key.

## Why the One-Time Pad is Perfectly Secure
The One-Time Pad achieves **perfect secrecy** because:
- Every possible plaintext is equally likely for any given ciphertext.
- The key is random, and since the key is as long as the message and never reused, it provides no patterns that could be exploited by an attacker.
- Given the ciphertext, the attacker cannot determine the plaintext without the key.

Mathematically, the OTP satisfies the condition for perfect secrecy:
$$ P(Plaintext | Ciphertext) = P(Plaintext) $$

## Pros and Cons of One-Time Pad
### Pros of the One-Time Pad
- **Perfect Security**: As long as the key is random, at least as long as the message, and never reused, the OTP provides perfect secrecy.
- **Simplicity**: The encryption and decryption process are simple and involve the XOR operation, which is easy to implement.

### Cons of the One-Time Pad
- **Key Management**: The key must be as long as the message, making key distribution and storage difficult, especially for large datasets.
- **Key Reuse**: If the key is reused, security is compromised, and the system is no longer perfectly secure.
- **Key Generation**: The key must be truly random, which can be challenging to generate in a secure way.

