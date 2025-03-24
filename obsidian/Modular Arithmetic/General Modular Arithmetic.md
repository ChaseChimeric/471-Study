# Modular Arithmetic and Number Theory

## 1. Introduction
Modular arithmetic is a fundamental concept in number theory and cryptography. It deals with operations on integers where numbers wrap around upon reaching a certain value (the modulus).

## 2. Modular Addition
For two integers $a$ and $b$ with modulus $m$:
$$ (a + b) \mod m $$
Properties:
- Commutative: $(a + b) \mod m = (b + a) \mod m$
- Associative: $((a + b) + c) \mod m = (a + (b + c)) \mod m$
- Identity: $(a + 0) \mod m = a \mod m$

## 3. Modular Multiplication
For two integers $a$ and $b$ with modulus $m$:
$$ (a \cdot b) \mod m $$
Properties:
- Commutative: $(a \cdot b) \mod m = (b \cdot a) \mod m$
- Associative: $((a \cdot b) \cdot c) \mod m = (a \cdot (b \cdot c)) \mod m$
- Distributive: $(a \cdot (b + c)) \mod m = ((a \cdot b) + (a \cdot c)) \mod m$

## 4. Modular Exponentiation
Modular exponentiation is used in cryptographic applications. It computes:
$$ a^b \mod m $$
Efficiently computed using the method of exponentiation by squaring:
1. If $b$ is even: $a^b = (a^{b/2})^2$
2. If $b$ is odd: $a^b = a \cdot a^{b-1}$

## 5. Euclidean Algorithm
The Euclidean algorithm finds the greatest common divisor (GCD) of two numbers $a$ and $b$ using the relation:
$$ \gcd(a, b) = \gcd(b, a \mod b) $$
Repeatedly applying this formula until $b = 0$ gives:
$$ \gcd(a, b) = a $$

## 6. Fermat's Theorem
Fermat’s Little Theorem states that if $p$ is a prime number and $a$ is an integer not divisible by $p$:
$$ a^{p-1} \equiv 1 \mod p $$
A useful corollary provides modular inverses:
$$ a^{-1} \equiv a^{p-2} \mod p $$

## 7. Euler's Theorem
A generalization of Fermat’s theorem using Euler’s totient function $\phi(n)$:
$$ a^{\phi(n)} \equiv 1 \mod n $$
where $\phi(n)$ counts the integers less than $n$ that are coprime to $n$.

## 8. Chinese Remainder Theorem
The Chinese Remainder Theorem helps solve systems of modular congruences:
If:
$$ x \equiv a_1 \mod m_1 $$
$$ x \equiv a_2 \mod m_2 $$
where $m_1$ and $m_2$ are coprime, then there exists a unique solution modulo $m_1 \cdot m_2$.

## 9. Extended Euclidean Algorithm
Used to find modular inverses. Given:
$$ ax \equiv 1 \mod m $$
The extended Euclidean algorithm finds $x$ such that:
$$ ax + my = 1 $$

## 10. Applications
- Cryptography (RSA, Diffie-Hellman, ECC)
- Computer Science (Hashing, Checksums)
- Discrete Mathematics and Number Theory

This structured document provides a comprehensive reference on modular arithmetic and number theory principles in an Obsidian-compatible format.

