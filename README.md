# Cryptography and Security: AES Implementation & Side-Channel Attacks

This repository contains two comprehensive Jupyter Notebook assignments focusing on the Advanced Encryption Standard (AES). The projects cover both the foundational implementation of AES-128 from scratch and the practical exploitation of hardware vulnerabilities using Correlation Power Analysis (CPA) on AES implementations.

Both projects were completed by Aarya Bhatt (Student ID: 240016).

---

## 📂 Repository Contents

### 1. Side-Channel Attacks and Power Analysis (`source_1.ipynb`)

This notebook demonstrates how mathematically secure cryptographic primitives can be compromised through inappropriate implementations that leak information via physical side-channel effects, specifically power consumption.

**Key Features:**

* **Correlation Power Analysis (CPA):** Implements CPA using the Pearson Correlation Coefficient to match theoretical power consumption with real collected power traces.


* **Leakage Modeling:** Utilizes the Hamming Weight (HW) leakage model to estimate power consumption based on the HW of output values.


* **8-bit AES-128 Attacks:** Demonstrates divide-and-conquer CPA attacks targeting the `AddRoundKey` and `SubByte` operations to extract the master secret key byte-by-byte.


* **32-bit AES-256 Decryption Attack:** Extends the CPA methodology to attack a 32-bit AES-256 decryption machine, specifically targeting the $RK_{14}$ and $RK_{13}$ round keys to reveal the master key.



### 2. Practical AES-128 Implementation (`source_2.ipynb`)

This notebook focuses on the low-level, from-scratch implementation of the AES-128 algorithm and its integration with a block-cipher mode of operation.

**Key Features:**

* **Data Formatting:** Implements functions to convert 1-D byte arrays into the 4x4 2-D column-major order matrices required by AES.


* **Core Transformations:** Contains ground-up implementations of AES round operations, including `AddRoundKey`, `SubBytes`, `ShiftRows`, and `MixColumns` (including Galois Field $GF(2^8)$ arithmetic) along with their inverse operations.


* **Key Scheduling:** Implements the Rijndael key schedule to expand a 16-byte master key into 11 distinct round keys.


* **Cipher Block Chaining (CBC):** Builds on the raw AES encryption/decryption functions to implement AES-CBC mode, complete with byte-level padding and unpadding to handle arbitrary plaintext lengths.



---

## 🛠️ Dependencies and Execution

* **Language:** Python 3 (Tested on Python 3.10).


* **Libraries:**
* The AES implementation notebook is built completely from scratch and prohibits the use of external libraries.


* The Side-Channel Attack notebook strictly requires `numpy` (for matrix/array calculations) and `matplotlib` (for plotting power traces and correlation peaks).




* **External Assets Needed:** The side-channel notebook relies on external trace arrays (`AES-8-attack.npz` and `AES-32-attack.npz`) to compute the correlation coefficients.



## 📝 Academic Integrity Note

These notebooks contain signed declarations of academic honesty. They represent individual work, and any reuse or unauthorized collaboration is strictly prohibited and subject to Academic Misconduct policies.
