# Cryptanalysis and the Four Main Attack Approaches

Cryptanalysis is the study of analyzing and breaking cryptographic systems. When attacking a cipher, an adversary tries to determine the original plaintext without knowing the secret key. There are four major cryptanalysis attack models, each defined by the amount of information available to the attacker.

---

## 1. Ciphertext-Only Attack (COA)
**Definition:**  
- The attacker **only has access to the encrypted text** (ciphertext) and tries to deduce the plaintext or the encryption key.
  
**Example Application:**  
- If an attacker intercepts encrypted messages without context, they may look for **patterns**, **frequency analysis**, or known structures in the language (e.g., "the" in English).
  
**How to Break Simple Ciphers (Example: Caesar Cipher)**  
- In a **Caesar cipher** (where letters are shifted by a fixed amount), an attacker can count letter frequencies (since "E" is the most common letter in English) and match patterns to break the encryption.

**Key Concept:**  
- **Statistical analysis** and **brute-force decryption** are the primary techniques.

---

## 2. Known-Plaintext Attack (KPA)
**Definition:**  
- The attacker has **some pairs of plaintext and corresponding ciphertext** and uses this information to decrypt additional messages or find the key.

**Example Application:**  
- If an enemy captures an encrypted military message and its decrypted version, they can compare them to find a pattern in the encryption method.

**How to Break Simple Ciphers (Example: Simple Substitution Cipher)**  
- If an attacker knows that "ATTACK" encrypts to "GYYGZU", they can infer which letters are mapped to others and gradually reconstruct the key.

**Key Concept:**  
- The more known plaintext-ciphertext pairs an attacker has, the easier it is to determine the encryption method or key.

---

## 3. Chosen-Plaintext Attack (CPA)
**Definition:**  
- The attacker can **choose plaintexts** and obtain their corresponding ciphertexts, giving them more control over the analysis.

**Example Application:**  
- If an attacker has access to an **encryption oracle** (a system that encrypts any input for them), they can feed in strategic plaintexts to analyze how the cipher works.

**How to Break Simple Ciphers (Example: Vigenère Cipher)**  
- By encrypting a known plaintext like "AAAAAA...", the attacker can reveal repeating patterns and deduce the key length.

**Key Concept:**  
- This attack is useful against **block ciphers** and **stream ciphers**, as attackers can manipulate input-output relationships.

---

## 4. Chosen-Ciphertext Attack (CCA)
**Definition:**  
- The attacker can **choose a ciphertext** and obtain its corresponding plaintext.

**Example Application:**  
- Used against systems where partial decryption results can be obtained (e.g., RSA padding oracle attacks in web security).

**How to Break Simple Ciphers (Example: RSA Encryption)**  
- If an attacker can alter a ciphertext and observe how decryption changes, they may learn how the encryption function works.

**Key Concept:**  
- This is a powerful attack model, especially when combined with **side-channel attacks** (where attackers gather extra information like timing delays or error messages).

---

## Summary Table

| **Attack Type**          | **What the Attacker Knows** | **Example Cipher to Break** | **Common Techniques** |
|--------------------------|----------------------------|-----------------------------|------------------------|
| **Ciphertext-Only (COA)** | Only ciphertext             | Caesar Cipher, Substitution | Frequency analysis, brute-force |
| **Known-Plaintext (KPA)** | Some plaintext-ciphertext pairs | Substitution, Vigenère      | Pattern matching, key recovery |
| **Chosen-Plaintext (CPA)** | Can encrypt chosen messages | Vigenère, Block Ciphers     | Predictive encryption patterns |
| **Chosen-Ciphertext (CCA)** | Can decrypt chosen ciphertexts | RSA, Block Ciphers         | Oracle attacks, error analysis |

---


