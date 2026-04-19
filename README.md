# 🔐 Symmetric Cryptography & Finite Fields — MAGMA Assignments

This repository contains implementations, test scripts, and reference materials for the MAGMA-based cryptography labs from the course **Symmetric Cryptography and Finite Fields**, at the University of Trento.

Each assignment focuses on implementing core cryptographic primitives and cryptanalytic techniques using the **MAGMA** computer algebra system.

---


---

## 📘 Assignment Breakdown

| Lab | Assignment | Topic | Key Implementations |
|-----|------------|-------|---------------------|
| **Lab 3** | First MAGMA Assignment | Alphabetic Ciphers & Cryptanalysis | `ShiftCrypt/Decrypt`, `SubCrypt/Decrypt`, `VigCrypt/Decrypt`, `Frequencies`, `Kasiski` |
| **Lab 4** | Second MAGMA Assignment | Boolean Functions & Cryptographic Properties | `ANF`, `WalshTransform`, `WalshSpectrum`, `Isbent`, `CorrelationImmunity` |
| **Lab 5** | Third MAGMA Assignment | Stream Ciphers & Correlation Attacks | `Berlekamp_Massey`, `InitialStates`, `CorrelationAttack(~L)` |
| **Lab 7** | Fourth MAGMA Assignment | Vectorial Boolean Functions (S-boxes) | `Univariate`, `NonLinearity`, `DDT`, `CCZeq` |
| **Lab 8** | Fifth MAGMA Assignment | Linear & Differential Attacks on Block Ciphers | `LinearAttack()`, `DifferentialAttack()` on a 16-bit Toy SPN |

---

## 💻 Prerequisites & Setup

- **MAGMA**: A commercial computer algebra system. Academic licenses are typically provided by the university. All scripts are written for `MAGMA V2.25+`.
- **No external dependencies**: All assignments rely solely on MAGMA's standard libraries and built-in finite field/polynomial operations.
---

## ▶️ How to Run & Test

1. **Launch MAGMA** (CLI or GUI).
2. **Navigate** to the specific assignment folder.
3. **Load your solution** followed by the corresponding test file:
   ```magma
   load "assignment1.mag";
   load "test1.mag";
   test1();  // Example for Assignment 1