# Lab 7: Fourth MAGMA Assignment
**Vectorial Boolean Functions**  
*Date:* November 19, 2025  
*Deadline:* November 29, 23:59

## 📖 Description
This assignment requires implementing four functions related to vectorial Boolean functions (S-boxes) and their cryptographic properties using the **MAGMA** computer algebra system. The tasks cover conversions between Algebraic Normal Form (ANF) and univariate representations, nonlinearity computation, Difference Distribution Table (DDT) generation, and CCZ equivalence testing.

## 🛠️ Exercises

### Exercise 1: Univariate Representation
Convert an $(n, n)$-function from its multivariate ANF representation to a univariate polynomial over the extension field.
- `Univariate(F)`: Takes a list `F` of $n$ polynomials in $n$ variables over GF(2).
- **Output:** A univariate polynomial `f` over GF($2^n$).

### Exercise 2: Nonlinearity
Compute the nonlinearity of a vectorial Boolean function given in univariate form.
- `NonLinearity(f)`: Takes a polynomial `f` over GF($2^n$).
- **Output:** An integer `v` representing the nonlinearity.

### Exercise 3: Difference Distribution Table (DDT)
Compute the DDT for an $(n, m)$-function given in ANF form.
- `DDT(F)`: Takes a list `F` of $m$ polynomials in $n$ variables over GF(2).
- **Output:** A list `T` of sequences of integers. `T[i_a][i_b]` contains the number of solutions to $D_a F(x) = b$, following MAGMA's default vector space ordering.

### Exercise 4: CCZ Equivalence
Determine whether two $(n, n)$-functions in univariate representation are CCZ equivalent.
- `CCZeq(f, g)`: Takes two polynomials `f` and `g` over GF($2^n$).
- **Output:** A boolean value (`true` if CCZ equivalent, `false` otherwise).