# How Certificates are Verified

1. **Presenting the Certificate:**  
   The entity (e.g., a website) presents its digital certificate to a user or another entity.

2. **Signature Validation:**  
   The receiver uses the CA’s public key to verify the digital signature on the certificate, confirming it was indeed issued by the trusted CA.

3. **Chain of Trust:**  
   If the issuing CA's certificate is not known directly (not in the trusted root store), the receiver checks the issuer's own certificate, repeating the process up a chain of certificates ending with a trusted root CA.

4. **Certificate Validity Check:**  
   The certificate’s validity period is checked, and revocation status is verified (e.g., using CRL or OCSP).

5. **Identity Match:**  
   The subject name (e.g., domain name) on the certificate is compared to the entity to ensure they match.

If all checks succeed, the presented public key is trusted to belong to the named entity.