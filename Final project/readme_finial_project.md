# Final Project: MIDORI64 and the Subspace Attack
**Block Cipher Implementation & Cryptanalysis**  
*Date:* December 3, 2025  
*Deadline for code:* December 17, 2025 (lab session)  
*Deadline for report:* January 7, 2026 (23:59)

## 📖 Description
This project consists of two main tasks implemented in the **MAGMA** computer algebra system. First, you will implement the lightweight block cipher **MIDORI64** (encryption and decryption) according to the specifications in `Midori.pdf`. Second, you will implement the **invariant subspace attack** described in `MidoriSubspaceAttack.pdf`, which recovers weak keys and distinguishes them from random keys. All functions must be placed in a single text file named `yourgroupname.mag` and will be evaluated during the lab session on December 17th. A final report (≤15 pages, in English) must be submitted by January 7, 2026, detailing the mathematical background, implementation choices, and individual contributions.

## 🛠️ Exercises

### Exercise 1: MIDORI64 Encryption and Decryption
Write MAGMA functions that implement the full MIDORI64 cipher.

- `MIDORI64_enc(P, K)`
  - **Input:**  
    - `P` – a string of **16 hexadecimal characters** (plaintext, 64 bits)  
    - `K` – a string of **32 hexadecimal characters** (key, 128 bits)  
  - **Output:**  
    - `C` – a string of **16 hexadecimal characters** (ciphertext)

- `MIDORI64_dec(C, K)`
  - **Input:**  
    - `C` – a string of **16 hexadecimal characters** (ciphertext)  
    - `K` – a string of **32 hexadecimal characters** (key)  
  - **Output:**  
    - `P` – a string of **16 hexadecimal characters** (plaintext)



### Exercise 2: Subspace Attack – Key Recovery
Implement the key recovery procedure for the invariant subspace attack on MIDORI64.

- `MIDORI64_KeyRecovery(P, C, P1, C1)`
  - **Input:**  
    - `P`, `C` – first plaintext‑ciphertext pair (each as 16‑char hex strings)  
    - `P1`, `C1` – second plaintext‑ciphertext pair (each as 16‑char hex strings)  
  - **Output:**  
    - `K` – the recovered 128‑bit key as a **32‑character hex string**

The function must work for weak keys where both plaintexts belong to the affine subspace \( \mathcal{S} = \{8,9\}^{16} \) and the key lies in the weak‑key class \( \mathbb{K} = \{0,1\}^{32} \). The recovery solves a linear system derived from the fact that the S‑box becomes identity on \( \mathcal{S} \).

### Exercise 3: Subspace Attack – Distinguisher and Verification
Implement a function that demonstrates the full subspace attack on a given key.

- `MIDORI64_SubspaceAttack(K)`
  - **Input:**  
    - `K` – a 32‑character hex string (the key to test)  
  - **Output:**  
    - `b` – a boolean value (`true` if the attack succeeds on this key, i.e., the key is recovered correctly; `false` otherwise)

The function must internally:
1. Choose a suitable plaintext `P` from the affine subspace \( \mathcal{S} \) (e.g., all cells equal to `8`).
2. Compute `C = MIDORI64_enc(P, K)`.
3. Choose a second plaintext `P1` (also in \( \mathcal{S} \), different from `P`) and compute `C1`.
4. Call `MIDORI64_KeyRecovery(P, C, P1, C1)` and compare the result with the original `K`.

## 📄 Report Requirements
- **Length:** ≤ 15 pages, written in English.
- **Content must include:**
  - The contribution of each team member to the project.
  - A complete mathematical overview of the implemented algorithms (MIDORI64 structure, round transformations, key schedule, and the invariant subspace attack).
  - An in-depth explanation of the implementation choices (how the state is represented, how S‑boxes and linear layers are handled, how the linear system for key recovery is constructed and solved).
- **The report should not contain the entire source code** – only relevant pseudocode or high‑level descriptions.
