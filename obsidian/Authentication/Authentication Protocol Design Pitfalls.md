# Authentication Protocol Design Principles and Pitfalls

## Design Principles
- Never transmit passwords in cleartext.
- Use secure cryptographic protocols (e.g., challenge-response, TLS).
- Employ random nonces or timestamps to prevent replay attacks.
- Design so that compromise of session keys or secrets does not expose other sessions (forward secrecy).

## Common Handshake Pitfalls and Attacks

### Replay Attack
- **What:** Attacker reuses intercepted valid authentication messages.
- **How:** Captures a valid login, replays it to gain unauthorized access.
- **Defense:** Use of nonces (random, unique values) or timestamps in protocols to ensure each authentication attempt is fresh.

### Reflection Attack
- **What:** Occurs in symmetric challenge-response protocols.
- **How:** Attacker reflects a challenge back to the originator, tricking the client into authenticating the attacker.
- **Defense:** Use different keys for each direction, include identifiers in messages, or use asymmetric methods.

## Role of Nonces
- Nonces ensure messages are unique and cannot be replayed.
- Random nonces are included in challenges and responses in authentication protocols.