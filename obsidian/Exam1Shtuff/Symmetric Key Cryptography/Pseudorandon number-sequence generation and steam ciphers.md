## **Pseudorandom Number/Sequence Generation (PRNG/PRSG)**
### **Evaluating PRNG/PRSG Security**
1. **Periodicity** – A good PRNG should have a long period before repeating.
2. **Statistical randomness** – Output should pass randomness tests.
3. **Cryptographic unpredictability** – Past outputs should not reveal future values.

### **Common PRNG/PRSG Methods**
- **Linear Congruential Generators (LCGs)** – Simple but not cryptographically secure.
- **Cryptographic PRNGs** – Use block ciphers or hash functions (e.g., Fortuna, Yarrow).
- **Stream Ciphers (RC4, ChaCha20)** – Generate a pseudorandom keystream for encryption.

---