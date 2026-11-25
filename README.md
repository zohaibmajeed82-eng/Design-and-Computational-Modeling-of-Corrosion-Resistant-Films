# Design and Computational Modeling of Corrosion-Resistant Films on Mg-Y Alloys

**Complex Engineering Problem (CEP)**, Surface Science Engineering (SSE 405)
Department of Metallurgical & Materials Engineering, University of Engineering & Technology, Lahore · Session 2022–2026

**Author:** Muhammad Zohaib Majeed (2022-MM-20) · **Instructor:** Dr. Ehsan

---

## 📄 Documents
- **[Full Report (PDF)](Corrosion-Resistant_slides.pdf)**
- **[Presentation Slides (PDF)](report.pdf)**

## Overview
Magnesium is the lightest structural metal (1.74 g/cm³), which makes it attractive for aerospace,
automotive and biomedical parts. Its native MgO film does not protect it, though: with a
Pilling-Bedworth Ratio (PBR) of 0.81, the oxide is porous and in tension, so oxygen keeps reaching the metal.

This project designs a **self-forming protective oxide** on magnesium by alloying it with yttrium,
with no external coating. Yttrium forms the Mg₂₄Y₅ precipitate, which oxidises preferentially to
**Y₂O₃ (PBR = 1.1923)**, a dense, adherent film inside the protective 1.0–2.0 window.

**Design outcome:** an **Mg-7Y alloy heat-treated in air at 450 °C for 1 hour** gives the highest
Y₂O₃ fraction and a predicted protective film of **~1.5 µm, about three times thicker than on pure Mg**.

## Methodology: three linked computational scales
| Scale | Tools | What it gives |
|---|---|---|
| Atomic | DFT (Quantum ESPRESSO, GPAW), MatterSim ML potential, GNoME, Materials Project | Formation energies, diffusion barriers, oxygen-vacancy energies |
| Thermodynamic | CALPHAD (Thermo-Calc TCBIN, PyCalphad) | Phase stability and heat-treatment temperature window |
| Kinetic / mesoscale | Phase Field (Allen-Cahn model, 1D finite-difference solver in Python) | Oxide film growth over time and morphology |
| Validation | Experimental data from Jiang et al. (2021), *Frontiers in Materials* | SEM, TGA and corrosion-current benchmarks |

## Key Results
- **PBR (hand calculation):** Y₂O₃ from Mg₂₄Y₅ = 1.1923 (matches the reference paper); MgO = 0.81
- **DFT:** Y₂O₃ formation energy ≈ −3.65 eV/atom vs. MgO ≈ −3.08 eV/atom. Y₂O₃ is ~0.58 eV/atom more stable, and all atomistic methods agree within 0.3 eV/atom
- **Defect energetics:** oxygen vacancies cost far more energy in Y₂O₃ than in MgO, so the film resists oxygen transport
- **CALPHAD:** Thermo-Calc and PyCalphad phase boundaries agree within ±5 K over 0–15 wt% Y, 300–1100 °C
- **Phase Field:** predicts a continuous, protective Y₂O₃-rich film of ~1.5 µm for the optimum condition
- **Multi-criteria ranking:** only Mg-7Y simultaneously achieves a protective PBR, adequate thickness (>1 µm) and high thermodynamic stability

All three computational scales independently arrive at the same design recommendation.

## Files

- `report.pdf`: full CEP report
- `slides.pdf`: presentation slides


## Contact
Muhammad Zohaib Majeed · <zohaibmajeed82@gmail.com>

---
Reference study: Jiang et al. (2021), *Frontiers in Materials*.
© 2026 Muhammad Zohaib Majeed
