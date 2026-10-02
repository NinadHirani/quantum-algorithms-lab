# Shor’s Algorithm — Complete Theory Notes

# Introduction

Shor’s Algorithm is a quantum algorithm developed by mathematician and computer scientist Peter Shor in 1994. It is designed to factor large integers exponentially faster than the best-known classical algorithms.

The algorithm became one of the most important discoveries in quantum computing because it showed that quantum computers could theoretically break RSA encryption, which is widely used in cybersecurity.

---

# What Problem Does Shor’s Algorithm Solve?

Shor’s Algorithm solves the:

## Integer Factorization Problem

Given a large integer:

N

find its prime factors.

Example:

15 = 3 × 5

21 = 3 × 7

Classically, factoring very large numbers becomes computationally difficult.

For sufficiently large numbers, classical computers may require an impractical amount of time.

Quantum computers, using Shor’s Algorithm, can solve this much more efficiently.

---

# Why Factorization Matters

Modern cryptography systems like RSA rely on the difficulty of factoring large numbers.

RSA security works because:

* Multiplying two large primes is easy
* Factoring their product is extremely difficult classically

Example:

p × q = N

If p and q are very large primes:

* Creating N is easy
* Recovering p and q from N is difficult

Shor’s Algorithm threatens RSA because it can efficiently recover these prime factors.

---

# Classical vs Quantum Complexity

Classical factoring algorithms become extremely slow for very large integers.

Shor’s Algorithm provides polynomial-time complexity.

This is considered an exponential quantum speedup over classical methods.

---

# Main Idea Behind Shor’s Algorithm

The most important insight of Shor’s Algorithm is:

Factorization can be transformed into a period-finding problem.

This is the heart of the algorithm.

Instead of directly factoring a number, the algorithm searches for the periodicity of a mathematical function.

---

# Mathematical Foundation

Suppose:

N = integer to factor

Choose a random integer:

1 < a < N

such that:

gcd(a, N) = 1

Now define the function:

f(x) = a^x mod N

This function becomes periodic.

The repeating interval is called the:

## Period r

That means:

f(x + r) = f(x)

for all x.

The quantum computer is mainly used to efficiently determine this period.

---

# Why Period Finding Helps

Once the period r is found:

If:

* r is even
* a^(r/2) ≠ -1 mod N

then factors of N can be computed using:

gcd(a^(r/2) − 1, N)

gcd(a^(r/2) + 1, N)

These gcd operations reveal non-trivial factors.

---

# Example: Factoring 15

Let:

N = 15

Choose:

a = 2

Now compute:

2^1 mod 15 = 2

2^2 mod 15 = 4

2^3 mod 15 = 8

2^4 mod 15 = 16 mod 15 = 1

The sequence starts repeating.

Therefore:

r = 4

Now:

2^(r/2) = 2^2 = 4

Compute:

gcd(4 − 1, 15)

gcd(3, 15) = 3

and:

gcd(4 + 1, 15)

gcd(5, 15) = 5

Therefore:

15 = 3 × 5

The factors are successfully recovered.

---

# Important Mathematical Concepts

# 1. Modular Arithmetic

Modular arithmetic works with remainders.

Example:

17 mod 5 = 2

because:

17 = 5 × 3 + 2

Modular arithmetic is essential in cryptography and Shor’s Algorithm.

---

# 2. Greatest Common Divisor (gcd)

The gcd of two numbers is the largest number dividing both.

Example:

gcd(15, 5) = 5

Shor’s Algorithm uses gcd operations to extract factors.

---

# 3. Periodicity

A periodic function repeats after some interval.

Example:

sin(x)

repeats every:

2π

Similarly:

f(x) = a^x mod N

repeats after period r.

---

# Quantum Concepts Used in Shor’s Algorithm

# 1. Superposition

Quantum bits (qubits) can exist in multiple states simultaneously.

This allows the quantum computer to evaluate many inputs in parallel.

---

# 2. Quantum Parallelism

Because of superposition, a quantum computer can compute:

f(x)

for many x values simultaneously.

This creates a quantum state containing hidden periodic information.

---

# 3. Interference

Quantum amplitudes interfere constructively and destructively.

Correct periodic states become amplified.

Incorrect states cancel out.

---

# 4. Quantum Fourier Transform (QFT)

The Quantum Fourier Transform is the most important component of Shor’s Algorithm.

Its purpose is:

## Extracting hidden periodicity from quantum states

QFT transforms the periodic quantum state into measurable frequency information.

This allows recovery of the period r.

The QFT provides the quantum advantage in Shor’s Algorithm.

---

# Why QFT Is Powerful

The Quantum Fourier Transform performs a Fourier transform exponentially faster than classical methods.

QFT converts:

periodic structure → frequency information

This is why Shor’s Algorithm can efficiently detect periodicity.

---

# High-Level Steps of Shor’s Algorithm

# Step 1 — Choose Random a

Select:

1 < a < N

---

# Step 2 — Compute gcd(a, N)

If:

gcd(a, N) ≠ 1

then a factor has already been found.

---

# Step 3 — Prepare Superposition

Create a quantum superposition of many possible x values.

---

# Step 4 — Modular Exponentiation

Compute:

f(x) = a^x mod N

using a quantum circuit.

---

# Step 5 — Apply QFT

Apply the Quantum Fourier Transform.

This extracts periodic information.

---

# Step 6 — Measurement

Measure the quantum state.

Measurement gives information related to the hidden period.

---

# Step 7 — Classical Post-Processing

Use classical mathematics to recover the period r.

---

# Step 8 — Recover Factors

Use:

gcd(a^(r/2) ± 1, N)

to obtain factors.

---

# Quantum Circuit Components

Important circuit components include:

* Hadamard gates
* Controlled unitary operations
* Phase rotations
* Quantum Fourier Transform
* Measurement gates

These components together enable period finding.

---

# Role of Phase Estimation

Quantum Phase Estimation is heavily connected to Shor’s Algorithm.

It helps estimate eigenvalues related to modular exponentiation.

QFT is a core component of phase estimation.

---

# Real-World Limitations

Current quantum computers are still noisy and limited.

As a result:

* Large RSA keys cannot yet be broken practically
* Most demonstrations factor small integers like 15 or 21
* Error correction is still an active research area

However, Shor’s Algorithm proved that sufficiently advanced quantum computers could threaten current cryptographic systems.

---

# Impact on Cybersecurity

Shor’s Algorithm changed the cybersecurity field completely.

It motivated research into:

* Post-quantum cryptography
* Quantum-safe encryption
* Lattice-based cryptography
* Hash-based cryptography

Governments and companies are now preparing for future quantum threats.

---

# Importance in Quantum Computing

Shor’s Algorithm is historically important because it:

* Demonstrated exponential quantum advantage
* Proved quantum computers are computationally powerful
* Accelerated quantum computing research worldwide
* Connected quantum mechanics with computational complexity

It remains one of the foundational algorithms in quantum computing.

---

# Advantages of Shor’s Algorithm

* Exponential speedup for factoring
* Efficient period finding
* Major theoretical breakthrough
* Strong cryptographic implications

---

# Limitations of Shor’s Algorithm

* Requires large fault-tolerant quantum computers
* Current hardware is insufficient for large-scale factoring
* Quantum noise affects reliability
* Complex implementation

---

# Applications

Potential applications include:

* Breaking RSA encryption
* Cryptanalysis
* Number theory research
* Quantum algorithm development
* Studying computational complexity

---

# Conclusion

Shor’s Algorithm is one of the most revolutionary algorithms in computer science and quantum computing.

Its true breakthrough comes from converting integer factorization into a quantum period-finding problem.

Using superposition, interference, and the Quantum Fourier Transform, the algorithm can determine periodicity exponentially faster than classical approaches.

Although modern hardware is still limited, Shor’s Algorithm fundamentally changed cybersecurity and proved the immense computational potential of quantum computers.

---

# Ultra-Short Summary

Shor’s Algorithm factors large integers by transforming factorization into a period-finding problem. Quantum superposition and Quantum Fourier Transform efficiently extract the hidden period, allowing the factors to be recovered using classical gcd operations.
