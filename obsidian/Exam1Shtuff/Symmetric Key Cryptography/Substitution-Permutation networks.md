## Substitution-Permutation Networks (SPN)
- **General structure**: 
  - A **substitution** step replaces elements in the plaintext (e.g., via S-Boxes).
  - A **permutation** step shuffles data to spread the influence of each bit across the ciphertext.
- **Why do we need SPNs?**  
  - Provides **confusion** (makes the relationship between key and ciphertext complex) and **diffusion** (spreads plaintext influence across ciphertext).
  - Used in block ciphers like **AES** for security against attacks.

---