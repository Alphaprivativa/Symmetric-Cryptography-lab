# Lab 3: First MAGMA Assignment
**Alphabetic Ciphers and Cryptanalysis**  
*Date:* October 15, 2025  
*Deadline:* October 25, 23:59

## 📖 Description
This assignment requires implementing five cryptographic and cryptanalytic functions using the **MAGMA** computer algebra system. The tasks cover classical substitution ciphers and statistical cryptanalysis techniques commonly used in introductory cryptography courses.

## 🛠️ Exercises

### Exercise 1: Shift Cipher
Implement encryption and decryption for the Shift (Caesar) cipher.
- `ShiftCrypt(x, K)`: Encrypts string `x` with integer key `K` (0–25).
- `ShiftDecrypt(y, K)`: Decrypts string `y` with integer key `K` (0–25).
- **Verification:** Load `test1.mag` and execute `test1()`.

### Exercise 2: Substitution Cipher
Implement encryption and decryption using a full alphabet permutation.
- `SubCrypt(x, pi)`: Encrypts string `x` using permutation `pi` ∈ $S_{26}$.
- `SubDecrypt(y, pi)`: Decrypts string `y` using permutation `pi`.
- **Verification:** Load `test2.mag` and execute `test2()`.

### Exercise 3: Vigenère Cipher
Implement encryption and decryption for the Vigenère cipher with a repeating string key.
- `VigCrypt(x, K)`: Encrypts `x` with string key `K`. The key repeats until its length ≥ plaintext length. **Important:** Spaces and punctuation do *not* count when aligning/chunking the plaintext.
- `VigDecrypt(y, K)`: Decrypts `y` with string key `K`.
- **Verification:** Load `test3.mag` and execute `test3()`.

### Exercise 4: Character Frequencies & Index of Coincidence
Compute letter occurrence probabilities and the Index of Coincidence (IoC) for a given text.
- `Frequencies(L)`: Takes string `L` and returns:
  - `F`: A list of 26 real numbers where `F[i]` is the probability of the i-th letter of $A_\ell$ in `L`.
  - `index`: The Index of Coincidence of `L` (probability that two randomly selected letters from `L` are identical).
- **Requirements:** Skip all non-alphabetic characters. Perform calculations using `RealField(5)`.
- **Verification:** Load `test4.mag` and execute `test4()`.

### Exercise 5: Kasiski Test
Implement the Kasiski examination to estimate the key length of a Vigenère-encrypted ciphertext.
- `Kasiski(y, index)`: Takes ciphertext `y` and the expected IoC for the underlying language (`index`).
- **Output:** `seq` (estimated key length as an integer).
- **Verification:** Load `test5.mag` and execute `test5()`.
