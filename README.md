<p align="center">
  <img src="V-index_logo.jpg" width="300" title="V-index Logo">
</p>


# V-index Quantum Resistant Physical TRNG
**Physics powered security in your pocket.**

The first open‑source, browser‑based True Random Number Generator (TRNG) that uses real‑world acoustic entropy to create quantum‑resistant keys — **no hardware required**.

!License: GPL-3.0
!Live Demo
!DOI
!Made with JavaScript

---

## 🔍 TL;DR
- **Quantum‑resistant** randomness for encryption keys  
- **Physical entropy** harvested from your **microphone** (acoustically validated)  
- **V‑index metric** acts as an *Entropy Gate* (rejects weak/artificial noise)  
- **Zero data transfer**: runs entirely in your browser  
- **Open‑source** (GPL‑3.0). For commercial use: **kisnorbert87@gmail.com**

**Live demo:** https://kisnorbert87.github.io/V-index-Quantum-Resistant-Physical-TRNG/

---

## 🚀 Quick Start
1. Open the **Live Demo** (must be a secure context: HTTPS or `localhost`).
2. Click **INITIALIZE SYSTEM** and allow microphone access.
3. Create physical noise (paper crumpling, whispering, air movement).
4. When **V‑index > 1.5**, the **HARVEST KEY** button unlocks.
5. Click to generate your **24‑character** key.

> **Privacy:** No audio or keys leave your device. Everything runs locally in the browser.

---

## 🧠 Why V‑index (and why physics)?
Most “random” numbers behind passwords and encryption are math‑based simulations (PRNG/CSPRNG).  
**Future quantum computers** may break assumptions behind common math‑based cryptosystems.  
V‑index TRNG injects **physically grounded** entropy — real acoustic noise — and **validates** it *before* cryptographic mixing.

- **Acoustic entropy:** thermal noise + chaotic air movement  
- **V‑index metric:** real‑time measure of information density & stability  
- **Entropy Gate:** if the environment is too quiet or artificial, **generation is blocked**

---

## 🔐 Key Features
- **Acoustic Entropy (Web Audio API):** 32‑bit float PCM sampling across 128 bands
- **Real‑time V‑index validation:** rejects silence/monotony (**V < 1.5**)  
- **Hybrid mixing:** physical samples + metadata → **CSPRNG (crypto.getRandomValues)** → **SHA‑256 feedback buffer**
- **Health tests:** Repetition Count Test (RCT) & Adaptive Proportion Test (APT)
- **Output:** 24 characters, 70‑char alphabet, designed to target ~256‑bit strength
- **Zero data transfer:** no recordings, no telemetry
- **Open‑source:** GPL‑3.0 (contact for commercial licensing)

---

## 🏛 Architecture (high‑level)
 

┌─────────────┐     analog          ┌─────────────────┐        ┌──────────────────────┐ │ Environment │ ──> microphone ──>  │  Web Audio API  │  → →   │  V-index (Entropy    │ │  (noise)    │                     │  (PCM frames)   │        │  Gate, V>1.5 check)  │ └─────────────┘                     └─────────────────┘        └────────┬─────────────┘ │ allow/deny ▼ ┌───────────────────────────┐ │  Cryptographic Mixing     │ │  - crypto.getRandomValues │ │  - SHA-256 feedback buf   │ └───────────┬───────────────┘ ▼ ┌─────────────────────────┐ │  24-char Key (70 chars) │ └─────────────────────────┘

 

---

## 🧪 Security & Compliance
- **NIST SP 800‑90B**: physical, non‑deterministic entropy source (+ health tests)  
- **AIS 31 (PTG.2)**: physical source with internal fault/misuse detection (V‑index)  
- **FIPS 140‑2 principles**: continuous self‑testing; refuse output on low entropy  
- **ISO/IEC 18031**: output whitening via XOR‑based extraction + cryptographic mixing

---

## 📏 Output & Entropy Notes
- **Key length:** 24 chars (70‑char alphabet)  
- **Target strength:** ~256 bits (accounting for hashing/mixing)  
- **Design goal:** exceed brute‑force feasibility by orders of magnitude  
- **Quantum angle:** even with Grover’s algorithm, the effective security remains extremely high at this size class

---

## 🧰 Tech Stack
- **Language:** HTML5, CSS3, **JavaScript** (Web Audio API)
- **Crypto:** Browser **CSPRNG** (`crypto.getRandomValues`), **SHA‑256**
- **Visualization:** real‑time spectrum analyzer & particle viz

---

## 🧪 Reproduce & Test Randomness (optional)
Generate a batch of keys → test with external tools.

Save 1000 keys (one per line), then run:

Example on macOS/Linux if you have 'ent' installed
ent generated_keys.txt

Or use dieharder / NIST STS on the produced bitstreams
(convert chars → bits as needed before running suites)
 

 ---

## 📚 Publications & References

V‑index Preprint : https://doi.org/10.5281/zenodo.18147084



## 🤝 Contributing

Contributions are welcome! Please read CONTRIBUTING.md and follow the issue/PR templates.
By contributing you agree your code is licensed under GPL‑3.0.

Code of Conduct: CODE_OF_CONDUCT.md

Security Policy: SECURITY.md

 

## 🧾 License & Commercial Use

GPL‑3.0 — see LICENSE.
For commercial licensing, partnerships, or research collaboration: kisnorbert87@gmail.com

 

## 🙋 FAQ

Q: Will it work without HTTPS?
A: Browsers require a secure context for microphone access (HTTPS or  localhost  during development).

Q: Can I use it offline?
A: Yes. Once the page is loaded, processing is local. No data is sent anywhere.

Q: What if my room is very quiet?
A: If V < 1.5, generation is blocked. Create local noise (paper, whisper, rustle) to raise entropy.

Q: Is this “unbreakable”?
A: No system is absolutely unbreakable. This project adds a physical layer to standard cryptography, designed for strong practical and quantum‑resistant security.

 

## 🧑‍🔬 How to Cite

If you reference this project in academic work, please cite the preprint and the repository:

Norbert Kis, V-index Quantum Resistant Physical TRNG.  DOI: 10.5281/zenodo.18147084
GitHub: https://github.com/kisnorbert87/V-index-Quantum-Resistant-Physical-TRNG

 

## ❤️ Acknowledgments

Thanks to the open‑source community and browser teams behind Web Audio API and Web Crypto. Special thanks to early testers for feedback on V‑index behavior and UI.
