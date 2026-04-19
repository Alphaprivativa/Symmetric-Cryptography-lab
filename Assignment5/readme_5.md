# Lab 8: Fifth MAGMA Assignment
**Linear and Differential Attacks on Block Ciphers**  
*Instructors:* Marco Calderini, Irene Villa  
*Date:* November 26, 2025  
*Deadline:* December 6, 23:59

## 📖 Description
This assignment focuses on implementing linear and differential cryptanalysis attacks on a custom 16-bit Toy Block Cipher (based on a Substitution-Permutation Network). You will use the **MAGMA** computer algebra system to mount both attacks, recover the last round subkey, and reverse the key schedule to obtain the master key. The cipher structure, S-box, permutation layer, and key schedule are defined in `Toy Block Cipher.pdf`, while attack methodologies and trail examples are provided in the accompanying cryptanalysis PDFs.

## 🛠️ Exercises

### Exercise 1: Linear Cryptanalysis Attack
Implement a linear attack to recover the master key of the Toy Block Cipher.
- `LinearAttack()`: Takes no input.
- **Output:** `mk`, a sequence of 16 bits representing the recovered master key.
- **Requirements:**
  - Construct linear trails (e.g., using the approximation from page 13 of `Linear Cryptanalysis.pdf`).
  - Use the provided `Enc(M)` oracle to generate plaintext-ciphertext pairs (**max 5000 pairs**).
  - Partially decrypt the last round, evaluate candidate subkeys against the linear approximation, and select the one with the highest bias.
  - Reverse the key schedule to recover the master key.

### Exercise 2: Differential Cryptanalysis Attack
Implement a differential attack to recover the master key of the Toy Block Cipher.
- `DifferentialAttack()`: Takes no input.
- **Output:** `mk`, a sequence of 16 bits representing the recovered master key.
- **Requirements:**
  - Construct differential trails (e.g., using the characteristic from page 24 of `Differential Cryptanalysis.pdf`).
  - For each trail, generate at most **2000 chosen plaintext pairs** (1000 pairs `(X, Enc(X))` and 1000 pairs `(X ⊕ ΔX, Enc(X ⊕ ΔX))`).
  - Partially decrypt the last round for candidate subkeys, count occurrences of the expected input difference, and select the subkey with the highest count.
  - Reverse the key schedule to recover the master key.
