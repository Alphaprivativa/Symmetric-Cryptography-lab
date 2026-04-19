# 🔐 Symmetric Cryptography & Finite Fields — MAGMA Assignments

This repository contains implementations, test scripts, and reference materials for the MAGMA-based cryptography labs from the course **Symmetric Cryptography and Finite Fields**, at the University of Trento.

Each assignment focuses on implementing core cryptographic primitives and cryptanalytic techniques using the **MAGMA** computer algebra system.

---



---

## 📘 Assignment Breakdown

| Lab | Assignment | Topic | Key Implementations | Deadline |
|-----|------------|-------|---------------------|----------|
| **Lab 3** | First MAGMA Assignment | Alphabetic Ciphers & Cryptanalysis | `ShiftCrypt/Decrypt`, `SubCrypt/Decrypt`, `VigCrypt/Decrypt`, `Frequencies`, `Kasiski` | Oct 25, 23:59 |
| **Lab 4** | Second MAGMA Assignment | Boolean Functions & Cryptographic Properties | `ANF`, `WalshTransform`, `WalshSpectrum`, `Isbent`, `CorrelationImmunity` | Nov 8, 23:59 |
| **Lab 5** | Third MAGMA Assignment | Stream Ciphers & Correlation Attacks | `Berlekamp_Massey`, `InitialStates`, `CorrelationAttack(~L)` | Nov 15, 23:59 |
| **Lab 7** | Fourth MAGMA Assignment | Vectorial Boolean Functions (S-boxes) | `Univariate`, `NonLinearity`, `DDT`, `CCZeq` | Nov 29, 23:59 |
| **Lab 8** | Fifth MAGMA Assignment | Linear & Differential Attacks on 16-bit SPN | `LinearAttack()`, `DifferentialAttack()` | Dec 6, 23:59 |
| **Final** | **MIDORI64 Project** | **Subspace Invariant Attack on Lightweight Cipher** | `MIDORI64_enc/dec`, `MIDORI64_KeyRecovery`, `MIDORI64_SubspaceAttack` | **Code: Dec 17 • Report: Jan 7, 2026** |

---

## 🚀 Final Project: MIDORI64 & Subspace Attack

### 📋 Overview
Implement the **MIDORI64** lightweight block cipher and a **subspace invariant attack** against it using MAGMA. The project combines practical cipher implementation with advanced cryptanalytic techniques targeting weak key classes.

### 🎯 Attack Mechanism
- **Weak Keys:** `K0, K1 ∈ 𝒦 = {0,1}^16` (each cell is 0 or 1)
- **Invariant Subspace:** Plaintexts `P ∈ 𝒮 = {8,9}^16` remain in `𝒮` after encryption
- **Why it works:** `8` and `9` are fixed points of MIDORI64's S-box (`Sb0`). Under weak keys + `𝒮` plaintexts, the S-box acts as identity, reducing the cipher to a **linear transformation** over `GF(2)`.
- **Recovery:** Solves a 32×32 binary linear system using one pair, then uniquely determines the key with a second pair in `O(2^16)` time.

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