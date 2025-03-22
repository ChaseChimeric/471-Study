# Perfect Secrecy
## Definition of Perfect Secrecy
Perfect secrecy refers to a property of a cryptosystem where the ciphertext provides no information about the plaintext. In other words, ***no matter what ciphertext is observed, every possible plaintext is equally likely.***

Formally, a cryptosystem achieves perfect secrecy if the probability distribution of the plaintext is the same before and after the ciphertext is seen. Mathematically, this is expressed as:

$$ P(Plaintext | Ciphertext) = P(Plaintext) $$

where $ P(Plaintext | Ciphertext) $ is the conditional probability of the plaintext given the ciphertext, and $( P(Plaintext) )$ is the probability of the plaintext before observing the ciphertext.

## How to Prove Perfect Secrecy
To test whether a cryptosystem is perfectly secure, you can perform the following steps:

### Mathematical Proof
 Derive the relationship between the plaintext and ciphertext and show that the conditional probability $( P(Plaintext | Ciphertext) )$ equals the prior probability $( P(Plaintext) )$. 

### Example
One example of perfect secrecy is [[OneTimePad]]

### Entropy Analysis
 Analyze the entropy of the plaintext and ciphertext. In a perfectly secure system, the entropy of the ciphertext should equal the entropy of the plaintext. If knowing the ciphertext does not reduce the uncertainty about the plaintext, the system is perfectly secure. (How we did in the Lab)
