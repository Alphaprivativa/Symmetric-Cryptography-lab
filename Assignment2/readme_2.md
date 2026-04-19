# Lab 4: Second MAGMA Assignment
**Boolean Functions and Cryptographic Properties**  
*Date:* October 29, 2025  
*Deadline:* November 8, 23:59

## 📖 Description
This assignment requires implementing five functions related to Boolean functions and their cryptographic properties using the **MAGMA** computer algebra system. The tasks cover the computation of the Algebraic Normal Form (ANF), Walsh transforms, bent function verification, and correlation immunity analysis.

## 🛠️ Exercises

### Exercise 1: Algebraic Normal Form (ANF)
Compute the ANF of a Boolean function from its truth table.
- `ANF(T)`: Takes a list `T` of $2^n$ bits representing the truth table of $f: \mathbb{F}_2^n \to \mathbb{F}_2$.
- **Output:** A square-free multivariate polynomial in $\mathbb{F}_2[x_1, \dots, x_n]$.

### Exercise 2: Walsh Transform
Evaluate the Walsh transform of a Boolean function at a specific input vector.
- `WalshTransform(f, a)`: Takes a Boolean function `f` (in ANF) and an $n$-bit vector `a`.
- **Output:** An integer representing the Walsh transform value $W_f(a)$.

### Exercise 3: Walsh Spectrum
Compute the complete set of Walsh transform values for a Boolean function.
- `WalshSpectrum(f)`: Takes a Boolean function `f` (in ANF).
- **Output:** A list of integers corresponding to $W_f(u)$ for all $u \in \mathbb{F}_2^n$.

### Exercise 4: Bent Function Check
Determine whether a given Boolean function satisfies the bent property.
- `Isbent(f)`: Takes a Boolean function `f` (in ANF).
- **Output:** A boolean value (`true` if bent, `false` otherwise).

### Exercise 5: Correlation Immunity
Compute the maximum order of correlation immunity for a Boolean function.
- `CorrelationImmunity(f)`: Takes a Boolean function `f` (in ANF).
- **Output:** An integer $t$ ($0 \le t \le n$) such that $f$ is $t$-th order correlation immune but not $(t+1)$-th order.
