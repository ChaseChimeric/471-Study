# RSA Cryptosystem

## Key Generation
1. **Choose Two Prime Numbers**  
   - Select two large prime numbers, $p$ and $q$.  
   - Compute $n = p \times q$ (modulus).  
   
2. **Compute Euler's Totient Function**  
   - $\phi(n) = (p-1) \times (q-1)$.  

3. **Choose a Public Exponent $e$**  
   - Select $e$ such that $1 < e < \phi(n)$ and $\gcd(e, \phi(n)) = 1$.  
   - Common choice: $e = 65537$.  

4. **Compute the Private Exponent $d$**  
   - Find $d$ such that $d \equiv e^{-1} \mod \phi(n)$.  
   - This means $d \times e \equiv 1 \mod \phi(n)$.  

5. **Public and Private Keys**  
   - Public Key: $(n, e)$.  
   - Private Key: $(n, d)$.  

---

## Encryption and Decryption

### Encryption (Using Public Key)
1. Convert message $M$ into an integer representation.  
2. Compute ciphertext:  
   $$
   C = M^e \mod n
   $$
3. Transmit $C$.  

### Decryption (Using Private Key)
1. Compute plaintext:  
   $$
   M = C^d \mod n
   $$
2. Convert back to readable format.  

---

## Vulnerabilities of Textbook RSA

### 1. **Deterministic Encryption**  
   - Same plaintext always encrypts to the same ciphertext.  
   - **Remedy**: Use *Optimal Asymmetric Encryption Padding (OAEP)*.  

### 2. **Small Exponent Attack**  
   - If $e$ is small and messages are short, they can be easily recovered.  
   - **Remedy**: Use padding and ensure the message is large.  

### 3. **Factorization Attack**  
   - If $n$ is small or $p, q$ are not strong primes, attackers can factorize $n$.  
   - **Remedy**: Use sufficiently large, strong primes.  

### 4. **Timing Attacks**  
   - Observing decryption time may reveal $d$.  
   - **Remedy**: Implement constant-time operations.  

### 5. **Chosen Ciphertext Attacks (CCA)**  
   - Attackers can manipulate ciphertexts to learn information about plaintexts.  
   - **Remedy**: Use RSA with padding schemes like *OAEP* or use hybrid encryption.  

---

## Summary
- RSA uses modular exponentiation for encryption and decryption.  
- Security depends on the difficulty of factoring large numbers.  
- Padding schemes (e.g., OAEP) are essential to mitigate vulnerabilities.  
