## **DES (Data Encryption Standard)**
### **Feistel Structure and Mangler Function**
- DES follows a **Feistel network**, where encryption involves multiple rounds of:
  - **S-Boxes (Substitution Boxes):** Introduce non-linearity.
  - **Permutation:** Spreads information for security.
- **Key length of DES**:  
  - DES uses a **56-bit key**, which is too short by modern standards and vulnerable to **brute force attacks**.

### **How to Strengthen DES?**
- **Triple DES (3DES)**: Encrypts data three times using two or three different DES keys.
- **Meet-in-the-Middle Attack**:
  - A known-plaintext attack where an attacker exploits double encryption's weakness by storing intermediate results and reducing brute-force complexity.
- **Why 3DES?**
  - Addresses DES's vulnerability to brute force while still being compatible with DES hardware.

---

## **AES (Advanced Encryption Standard)**
- **High-level structure**:
  - Unlike DES, AES does **not** use a Feistel structure.
  - Instead, it follows an **SPN (Substitution-Permutation Network)** model. [[Substitution-Permutation networks]]
- **Security properties**:
  - Uses **128-bit, 192-bit, or 256-bit keys** (unlike DES’s 56-bit).
  - More resistant to brute-force attacks.
- **Comparison with DES**:
  - AES is **faster**, more **secure**, and does **not rely on Feistel networks**.
  - AES uses **Rijndael's S-Boxes** and **MixColumns transformation** for better diffusion.

---

## **Why is a Block Cipher Secure?**
A secure block cipher must satisfy:
- **Non-linearity**: Resistance to algebraic attacks.
- **Strict Avalanche Property (SAP)**: Changing a single input bit changes **half of the output bits**.
- **Bit Independence**: No correlation between output bits.
- **Key mixing and diffusion**: Prevents pattern recognition in ciphertexts.

### **Why AES and DES Satisfy These?**
- DES uses **S-Boxes and permutations** to introduce non-linearity and diffusion.
- AES applies **byte substitution, shift rows, mix columns**, and **add round keys** to achieve strong security properties.

---

## **Five Modes of Encryption**
(Block ciphers must operate in specific modes to encrypt large messages)
1. **ECB (Electronic Codebook)** – Least secure, identical blocks encrypt the same way.
2. **CBC (Cipher Block Chaining)** – Each block depends on the previous one, reducing pattern visibility.
3. **CFB (Cipher Feedback)** – Converts block cipher into a self-synchronizing stream cipher.
4. **OFB (Output Feedback)** – Similar to CFB but more resistant to transmission errors.
5. **CTR (Counter Mode)** – Encrypts blocks in parallel using a counter.

**Pros and Cons**:
- **ECB** is weak against patterns in plaintext.
- **CBC, CFB, and OFB** provide better security but require proper initialization vectors (IVs).
- **CTR** enables fast, parallel encryption and is widely used in modern protocols.

---