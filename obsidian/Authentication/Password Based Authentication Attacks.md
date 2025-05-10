# Password-Based Authentication and Attacks

## Principles of Password-Based Authentication
- User provides a secret (password) that only they know.
- System verifies the secret against stored information (ideally salted and hashed).

## Common Attacks

### 1. Eavesdropping
- Attacker intercepts communication (e.g., over insecure networks).
- Can capture plain-text passwords if not encrypted.

### 2. Database Reading (Data Breaches)
- If an attacker gains access to the authentication database, they can steal password data.
- If passwords are stored in plaintext or using weak hashing, it's easier for attackers to obtain user credentials.

### 3. Password Guessing
- **Online guessing:**  
    - Attacker repeatedly attempts to log in by trying different passwords.
    - Often limited by lockout mechanisms or rate limiting.

- **Offline guessing:**  
    - Attacker has a copy of password hashes.
    - Performs brute-force or dictionary attacks on hashes without interacting with the authentication server.

## Defenses
- Enforce strong password policies and rate limits.
- Store passwords securely: salted and hashed.
- Use Multi-Factor Authentication.
- Monitor authentication attempts and implement account lockouts.