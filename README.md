# Prarambh-1: Empirical Solid Rocket Motor Development 🚀💥

## 🛠️ Project Specifications
* **Propellant Base:** KNSB (64% Potassium Nitrate ($KNO_3$), 35% Sorbitol, 1% Iron Oxide ($Fe_2O_3$ catalyst))
* **Core Domains:** Solid Propulsion, Propulsion Chemistry, Transient Chamber Pressure ($P_c$) Analysis, Multi-Physics Simulation
* **Status:** Fully Validated via Physical Static Fire Testing

---

## 📌 Technical Overview & Propulsion Philosophy
This repository documents the structural engineering, mathematical modeling, and empirical optimization of the **Prarambh-1** solid rocket motor. The overriding engineering objective of this project was to establish a predictable, high-performance burn profile while preventing catastrophic structural failure (CATO) under extreme internal thermal and pressure loads.

Rather than relying purely on theoretical models, this motor was developed using a rigorous **hardware-first builder methodology**. Over the course of **14 physical propellant iterations**, chemical purity levels, grain geometries, and casting methods were systematically optimized to align physical static fire load-cell metrics with high-fidelity computational simulations.

### 🎯 Key Aerospace Engineering Highlights
* **Empirical Propellant Characterization:** Managed 14 iterative chemical variations to solve initial ignition delays and grain anomalies, ultimately standardizing a highly stable, high-impulse 64:35:1 KNSB composition.
* **Internal Ballistics Modeling:** Modeled multi-phase internal transient chamber pressure ($P_c$) and burn-surface area evolution over time using **OpenMotor**.
* **Structural Safety Limits:** Conducted extensive casing burst pressure calculations, establishing clear structural safety factors ($\eta$) to withstand severe chamber pressure spikes during peak thrust.
* **Flight Profile Simulation:** Mapped the empirical thrust curves into **OpenRocket** to generate accurate flight dynamics and structural velocity predictions for future integration into sounding rocket airframes (e.g., Project Jericho).

---

## 📂 Repository Architecture
* **`/simulations`**: Houses the native OpenMotor (`.om`) internal ballistics files and OpenRocket (`.ork`) multi-physics flight profile configurations.
* **`/data`**: Contains raw pressure/thrust data spreadsheets, regression rate tracking charts, and metrics logged across the 14 test iterations.
* **`/src`**: Houses processing scripts (MATLAB/Python) utilized to parse raw static fire data, overlay experimental thrust curves with simulation targets, and compute core propulsion metrics like total impulse ($I_{total}$) and specific impulse ($I_{sp}$).
* **`/docs`**: Contains structural casing calculations, nozzle throat-to-exit expansion geometries, and critical safety procedures.

---

## 📋 Iterative Development & Validation History
- [x] Analytical calculation of ideal expansion ratios and initial nozzle throat sizing
- [x] Propellant Processing Phase I (Iterations #1–#5): Overcoming chemical impurities and moisture absorption issues
- [x] Propellant Processing Phase II (Iterations #6–#10): Adjusting catalyst percentages to normalize linear regression rates
- [x] Internal Ballistics Matching (Iterations #11–#13): Tuning OpenMotor coefficients against measured static data
- [x] Final Validation (Iteration #14): Achieving flawless, stable, full-duration static fire execution matching target thrust curves
- [x] Final compilation of performance matrices and flight profile mapping inside OpenRocket

---

> *Note: Analytical calculations, simulation geometries, and sensor processing files are hosted within their respective directories for peer validation.*
