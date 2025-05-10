# How Key Distribution Works with KDCs

## Symmetric Key Distribution via KDC

1. **Initialization:**  
   - Each user securely shares a unique long-term secret key with the KDC.

2. **Session Key Setup:**  
   - When User A wants to communicate with User B:
     - A authenticates to the KDC and requests a session key for communicating with B.
     - KDC generates a temporary session key (KAB).
     - KDC sends EKA{KAB} to A (encrypted with A's key), and EKB{KAB} to A (for B, encrypted with B's key).
     - A then forwards EKB{KAB} (the "ticket") to B.

3. **Usage:**  
   - Both A and B now use KAB for mutual authentication and encryption during their session.

## KDC Benefits
- Only O(n) keys are needed.
- When a user is added/removed, only their individual key with the KDC must be updated.
- Single point for key distribution, but also a single point of vulnerability.