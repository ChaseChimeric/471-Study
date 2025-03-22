# Properties of Cryptographic Hash Functions

## 1. Desired Properties of Hash Functions
Cryptographic hash functions should satisfy the following properties:

- **One-way property (Preimage Resistance)**  
  - Given a hash value $h$, it should be computationally infeasible to find an input $x$ such that $H(x) = h$.  
  - **Why needed?** Prevents retrieval of original data from the hash.

- **Second Preimage Resistance**  
  - Given an input $x$, it should be hard to find another input $x'$ such that $H(x) = H(x')$.  
  - **Why needed?** Prevents forging of alternative inputs with the same hash.

- **Collision Resistance**  
  - It should be computationally infeasible to find two distinct inputs $x$ and $x'$ where $H(x) = H(x')$.  
  - **Why needed?** Ensures data integrity and prevents hash-based attacks.

- **Randomness**  
  - The output should appear random and unpredictable for any given input.  
  - **Why needed?** Prevents patterns that could be exploited by attackers.

## 2. Complexity of Breaking Each Property
- The difficulty of breaking each property is based on computational effort:
  - **Preimage resistance:** Requires **$2^n$** operations for an $n$-bit hash.
  - **Second preimage resistance:** Requires **$2^n$** operations.
  - **Collision resistance:** Due to the **Birthday Paradox**, it requires approximately **$2^{n/2}$** operations.

## 3. The Birthday Paradox and Probability Calculations
- The Birthday Paradox explains why collisions occur faster than expected.
- The probability of at least one collision among $k$ randomly chosen hashes is given by:  
  $$ 
  P \approx 1 - e^{-\frac{k^2}{2N}}
  $$  
  where $N = 2^n$ is the number of possible hash values for an $n$-bit hash function.

---

# Message Digest Length Requirements and Construction

## 1. Length Requirement for a Message Digest
- A secure hash function should have a sufficient bit length to resist attacks.
- Common recommendations:
  - **128-bit**: Weak by modern standards (MD5 is broken).
  - **160-bit**: SHA-1 is deprecated due to weaknesses.
  - **256-bit (SHA-256) or 512-bit (SHA-512)**: Recommended for strong security.

## 2. General Iterated Construction of Message Digests
- Most cryptographic hash functions follow an **iterated structure**:
  - **Merkle–Damgård construction**: Processes data in fixed-size blocks.
  - **Sponge construction** (e.g., SHA-3): Absorbs and squeezes input for higher security.
- Iterated designs help in handling large messages securely.

---

### Summary Table

| Property                  | Definition | Security Complexity |
|--------------------------|------------|---------------------|
| **Preimage Resistance**  | Hard to find $x$ from $H(x)$ | $2^n$ |
| **Second Preimage Resistance** | Hard to find $x'$ where $H(x) = H(x')$ | $2^n$ |
| **Collision Resistance** | Hard to find two $x, x'$ with $H(x) = H(x')$ | $2^{n/2}$ |
| **Randomness** | Hash output appears unpredictable | - |

