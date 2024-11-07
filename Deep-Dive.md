---
permalink: /
geometry:
  - top=1in
  - bottom=1in
  - left=1in
  - right=1in
fontsize: 4pt
documentclass: article
markdown: kramdown
kramdown:
  input: GFM
  math_engine: mathjax
  syntax_highlighter: rouge
header-includes:
  - \usepackage{sectsty}
  - \allsectionsfont{\centering}
  - \usepackage{fancyhdr}
  - \usepackage{anyfontsize}
  - \usepackage{setspace}
  - |
    \makeatletter
    \renewcommand\normalsize{%
      \@setfontsize\normalsize{8pt}{10pt}%
      \abovedisplayskip 8pt
      \abovedisplayshortskip 4pt
      \belowdisplayshortskip 4pt
      \belowdisplayskip 8pt
      \abovedisplayskip 8pt
      \abovedisplayshortskip 4pt
      \belowdisplayshortskip 4pt
      \belowdisplayskip 8pt
    }
    \makeatother
---

# Cool Results from Euler's Totient Function

## Introduction

Euler's Totient Function, denoted as $φ(n)$, is a important concept that is used widely in number theory that counts the number of positive integers up to a given integer $n$ that are relatively prime to $n$. This function plays a crucial role in various applications, including cryptography, algebra, and the study of prime numbers. Euler's function serves as important piece of Euler's Theorem, a generalization of Fermat's Little Theorem, which states that if $\gcd(a, n) = 1$, then $a^{\phi(n)} \equiv 1 \pmod{n}$. This theorem implications in modular arithmetic and is key to the security of widely used cryptographic algorithms such as RSA. Additionally, the totient function provides deep insights into the multiplicative structure of integers. Historically, the development of the totient function is attributed to the illustrious mathematician Leonhard Euler in the 18th century. Euler introduced φ(n) to generalize Fermat's work and to address problems related to the distribution of prime numbers. His work laid the groundwork for modern number theory, influencing subsequent generations of mathematicians.

## Definition and Fundamental Properties

### Formal Definition

Euler's Totient Function, denoted as $\phi(n)$, is defined as the number of positive integers up to $n$ that are relatively prime to $n$. Formally,

$$
\phi(n) = \left| \{ k \in \mathbb{N} \mid 1 \leq k \leq n \text{ and } \gcd(k, n) = 1 \} \right|
$$

where $\gcd(k, n)$ represents the greatest common divisor of $k$ and $n$.

### Key Properties

Euler's Totient Function possesses several important properties that make it a powerful tool in number theory:

1. **Value at One:**
   $$
   \phi(1) = 1
   $$
   Since the only positive integer up to 1 is 1 itself, and it is trivially relatively prime to 1.

2. **Prime Numbers:**
   If $p$ is a prime number, then
   $$
   \phi(p) = p - 1
   $$
   This is because all positive integers less than $p$ are relatively prime to $p$.

3. **Multiplicativity:**
   Euler's Totient Function is multiplicative for coprime integers. That is, if $m$ and $n$ are two integers such that $\gcd(m, n) = 1$, then
   $$
   \phi(mn) = \phi(m) \cdot \phi(n)
   $$

4. **Prime Powers:**
   For a prime number $p$ and a positive integer $k$,
   $$
   \phi(p^k) = p^k - p^{k-1} = p^{k-1}(p - 1)
   $$
   This follows from the fact that among the first $p^k$ positive integers, exactly $p^{k-1}$ multiples of $p$ are not relatively prime to $p^k$.

5. **General Formula:**
   For any positive integer $n$ with prime factorization $n = p_1^{k_1} p_2^{k_2} \cdots p_r^{k_r}$,
   $$
   \phi(n) = n \prod_{i=1}^{r} \left(1 - \frac{1}{p_i}\right)
   $$
   This formula is derived from the multiplicative property and the value of $\phi$ at prime powers.

### Examples

To illustrate the computation of Euler's Totient Function, consider the following examples:

1. **Example 1: Compute $\phi(6)$**

   - Prime factorization of 6: $6 = 2 \times 3$
   - Applying the multiplicative property:
     $$
     \phi(6) = \phi(2) \cdot \phi(3) = (2 - 1) \cdot (3 - 1) = 1 \cdot 2 = 2
     $$
   - Therefore, $\phi(6) = 2$.

2. **Example 2: Compute $\phi(10)$**

   - Prime factorization of 10: $10 = 2 \times 5$
   - Applying the multiplicative property:
     $$
     \phi(10) = \phi(2) \cdot \phi(5) = (2 - 1) \cdot (5 - 1) = 1 \cdot 4 = 4
     $$
   - Therefore, $\phi(10) = 4$.

3. **Example 3: Compute $\phi(15)$**

   - Prime factorization of 15: $15 = 3 \times 5$
   - Applying the multiplicative property:
     $$
     \phi(15) = \phi(3) \cdot \phi(5) = (3 - 1) \cdot (5 - 1) = 2 \cdot 4 = 8
     $$
   - Therefore, $\phi(15) = 8$.

4. **Example 4: Compute $\phi(28)$**

   - Prime factorization of 28: $28 = 2^2 \times 7$
   - Applying the formula for prime powers and the multiplicative property:
     $$
     \phi(28) = \phi(2^2) \cdot \phi(7) = (2^2 - 2^{2-1}) \cdot (7 - 1) = (4 - 2) \cdot 6 = 2 \cdot 6 = 12
     $$
   - Therefore, $\phi(28) = 12$.

5. **Example 5: Compute $\phi(35)$**

   - Prime factorization of 35: $35 = 5 \times 7$
   - Applying the multiplicative property:
     $$
     \phi(35) = \phi(5) \cdot \phi(7) = (5 - 1) \cdot (7 - 1) = 4 \cdot 6 = 24
     $$
   - Therefore, $\phi(35) = 24$.

### Summary of Fundamental Properties

  - **Identity Element:** $\phi(1) = 1$.
  - **Prime Argument:** For prime $p$, $\phi(p) = p - 1$.
  - **Multiplicative Function:** If $\gcd(m, n) = 1$, then $\phi(mn) = \phi(m) \cdot \phi(n)$.
  - **Prime Power:** For prime $p$ and integer $k \geq 1$, $\phi(p^k) = p^k - p^{k-1}$.
  - **Euler's Product Formula:** For $n = p_1^{k_1} p_2^{k_2} \cdots p_r^{k_r}$,
  $$
  \phi(n) = n \prod_{i=1}^{r} \left(1 - \frac{1}{p_i}\right)
  $$

These properties not only facilitate the computation of $\phi(n)$ for various integers but also lay the groundwork for deeper explorations into number theory and its applications.

## Interesting Results and Identities 

#### Sum of Totients Identity

The Sum of Totients identity states that the sum of Euler's totient function values $\phi(d)$ over all positive divisors $d$ of an integer $n$ is equal to $n$: $$
  \sum_{d\,|\,n} \phi(d) = n
  $$ where $d \ | \ n$ means $d$ is a divisor of $n$

#### Perfect Totient Numbers

A perfect totient number is an integer that is equal to the sum of its iterated totients. We apply Euler's totient function $\phi(n)$ to a number $n$, apply it again to the resulting totient, and so on, until the number 1 is reached, and add together the resulting sequence of numbers. If this sum equals $n$, then $n$ is a perfect totient number.
**Example**: Let $n = 9$

$\phi(9) = 6$

$\phi(6) = 2$

$\phi(2) = 1$

By adding up the results, $6+2+1=9$ , 9 is a perfect totient number.

#### Fermat's Little Theorem and Totients

Fermat's little theorem states that if $p$ is a prime number, then for any integer $a$, the number $a^{p} - a$ is an integer multiple of $p$. This can be expressed as $$a^{p} \equiv a \mod p $$ However, if $a$ is coprime to $p$, then Fermat's little theorem says that $a^{p-1}-1$ is an integer multiple of $p$. This can be expressed as $$a^{p-1} \equiv 1 \mod p $$ Euler's Totient function, $\phi(n)$, can be used to generalize Fermat's Little Theorem. This looks like the following: $$a^{\phi(n)} \equiv 1 \mod n $$ This applies specifically when $n$ is a prime $p$ since $\phi(p) = p - 1$ .

#### Consecutive Totients and Totient Chains

An interesting property of Euler's Totient Function is that it is possible to find sequences of numbers called totient chains. A totient chain is when you repeatedly apply the totient function to $n$ until you reach 1.

**Example**: Let $n = 20$

$\phi(20) = 8$

$\phi(8) = 4$

$\phi(4) = 2$

$\phi(2) = 1$

The corresponding totient chain being $$20\rightarrow 8 \rightarrow 4 \rightarrow2 \rightarrow1$$

#### Asymptotic Growth of Totient Inverses

The sum of the reciprocals of the totient function values diverges. This means as you take the infinite series of $\frac{1}{\phi(n)}$ it will go off to infinity. In symbols this is expressed as $$\sum_{n=1}^{\infty} \frac{1}{\phi(n)} = \infty$$ This result shows that the values of $\phi(n)$ are distributed sparsely enough to allow their reciprocals to sum to infinity.

#### Totient Function and Perfect Numbers

For an even perfect number $n$, which has the form $n = 2^{p-1}(2^{p} - 1)$ where $2^{p} -1$  is a Mersenne prime, there is an interesting result: $$\phi(n) = n - 2^{p-1} $$This result is due to the structure of perfect even numbers and gives insight into their divisor structure and properties. The totient function value for a perfect number is always relatively close to the number itself.

**Example**: Let $p = 3$
$n = 2^{3-1}(2^{3}-1) = 4(7) = 28$
$\phi(n) = \phi(28) = 28 - 2^{3-1} = 28 - 4 = 24$

#### Totient Function and Möbius Function

The Möbius function is a multiplicative function in number theory introduced by the German mathematician August Ferdinand Möbius.

The Möbius function can be defined by the following piecewise function:
$$\mu(n) =  \begin{cases}
      1 & if\ \ n=1 \\
      (-1)^{k} & if \ n \ is \ the \ product \ of \ k \ distinct \ primes \\
      0 & if \ n \ is \ divisible \ by \ a \ square > 1
   \end{cases}
$$Now it can be seen an interesting relationship exists between Euler's totient function and the Möbius function where the totient function can be expressed using an alternating sum involving divisors. This can be expressed as the following: $$\phi(n) = n\sum_{d|n}\frac{\mu(d)}{d}$$where $d$ runs over the divisors of $n$. This formula shows a connection between the structure of divisors and prime factorization properties.

#### Carmichael's Totient Conjecture

Carmichael's conjecture (still unproven), believes that for every integer $m$, there exists at least one integer $n$ such that $\phi(n) = m$. This conjecture is believed to be true, but has not been proven. The existence of such an $n$ for each $m$ would undermine the totient function's ability to cover all positive integers, highlighting its versatility in producing values throughout the natural numbers.

## Applications in Cryptography

#### RSA Encryption

RSA encryption is a widely used encryption system based on public-key cryptography, which allows for secure data transmission between two parties. RSA is based on the mathematical properties of prime numbers and modular arithmetic.

**How it works**:
In RSA, each user has two keys:

1. **A public key** which is used to encrypt messages and can be shared openly.
2. **A private key** which is used to decrypt messages and is kept secret.

These keys are generated as follows:

1. Choose two large prime numbers, $p$ and $q$, and calculate their product, $n = p * q$. The value $n$ is part of the public key.
2. Compute Euler's Totient Function, $\phi(n)$. In RSA, $\phi(n) = (p-1)(q-1)$, since $n$ is the product of two primes.

**Role of Euler's Totient Function in RSA**:
Euler's Totient Function is crucial in RSA because it helps in choosing an encryption exponent $e$ and in calculating the decryption exponent $d$.

1. **Choosing the encryption exponent $e$** : The encryption exponent $e$ must be a number that is relatively prime to $\phi(n)$ (i.e. gcd($e,\phi(n)) = 1$). This ensures that $e$ has a modular inverse with respect to $\phi(n)$, which allows for decryption to be possible.
2. **Calculating the decryption exponent $d$** : The decryption exponent $d$ is the modular inverse of $e$ with respect to $\phi(n)$. This means $d$ is chosen such that $e * d \equiv 1 \mod \phi(n)$. The private key consists of the values $d$ and $n$, which allows the original message to be decrypted.

**Euler's Totient Function Importance**:
Euler's Totient Function makes RSA secure because finding $\phi(n)$ without knowing the prime factors of $n$ ($p$ and $q$) is challenging. The security of RSA relies on the difficulty of factoring large numbers. Since $\phi(n)$ depends on the prime factors, anyone without $p$ and $q$ can't easily determine $\phi(n)$, and therefore can't calculate the decryption key, $d$.

## Conclusion

In summary, Euler's Totient Function $\phi(n)$ is a fundamental and important concept  in number theory. Being defined as the count of positive integers up to $n$ that are relatively prime to $n$. We explored many of its key properties, including its behavior with prime numbers, its multiplicative nature, and its application in calculating totients of prime powers and composite numbers through Euler's product formula. Euler's Totient Function also had several intriguing identities and results, such as the Sum of Totients Identity, perfect totient numbers, and the relationship between $\phi(n)$ and other mathematical functions like the Möbius function. Additionally, we explored the role of Euler's Totient Function in modern cryptography, where it is used in the RSA encryption algorithm, where it is critical to the security of encrypted communications.

