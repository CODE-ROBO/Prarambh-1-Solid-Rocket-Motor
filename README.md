<div align="center">
  <code>
  [SYS_INIT]... PROPULSION_LABORATORY_ACTIVE<br>
  [DESIGNATION]... PRARAMBH-1_SOLID_MOTOR_ARCHIVE<br>
  [STATUS]... STATIC_FIRE_VALIDATED // CATO_AVOIDED
  </code>
</div>

<h1 align="center">Prarambh-1: Empirical Solid Rocket Motor Architecture 🚀</h1>
<h4 align="center">High-Fidelity Multi-Physics Simulation & Applied Hardware Fabrication</h4>

<p align="center">
  <img src="https://img.shields.io/badge/OpenMotor-8B0000?style=for-the-badge&logo=rocket&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenRocket-8B0000?style=for-the-badge&logo=rocket&logoColor=white" />
  <img src="https://img.shields.io/badge/MATLAB-FFD700?style=for-the-badge&logo=mathworks&logoColor=black" />
  <img src="https://img.shields.io/badge/Python-FFD700?style=for-the-badge&logo=python&logoColor=black" />
  <img src="https://img.shields.io/badge/SolidWorks-00FFFF?style=for-the-badge&logo=solidworks&logoColor=black" />
</p>

---

### 📋 SYSTEM DATASHEET & ENGINEERING SPECIFICATIONS

| Metric | Specification | Engineering Objective |
| :--- | :--- | :--- |
| **Propellant Base** | KNSB (Potassium Nitrate / Sorbitol) | High specific impulse ($I_{sp}$) with castable geometry. |
| **Chemical Matrix** | $64\%$ $KNO_3$ \| $35\%$ $C_6H_{14}O_6$ \| $1\%$ $Fe_2O_3$ | Optimized burn rate ($r$) and thermal stability. |
| **Grain Architecture** | Inhibited BATES Cylindrical | Maintain neutral thrust curve over full burn duration. |
| **Core Software** | OpenMotor, OpenRocket, MATLAB | Multi-physics modeling and transient pressure analysis. |
| **Project Status** | **VALIDATED** (14 Iterations) | Flight-ready for sounding rocket integration (Project Jericho). |

---

### 🌐 EXECUTIVE PROPULSION OVERVIEW
<div align="justify">
This repository documents the structural engineering, mathematical modeling, and empirical optimization of the <b>Prarambh-1</b> solid rocket motor. Engineered as the foundational propulsion unit for high-altitude sounding rockets, the overriding objective was to establish a predictable, high-performance burn profile while preventing catastrophic structural failure under extreme internal thermal and pressure loads.

Rejecting purely theoretical models, this motor was developed using a rigorous, first-principles hardware methodology. Across <b>14 empirical testing iterations</b>, chemical purity levels, grain geometries, and casting parameters were systematically isolated and optimized to perfectly align physical static-fire load-cell telemetry with high-fidelity computational simulations.
</div>

---

### 🧪 PROPELLANT CHEMISTRY & INTERNAL BALLISTICS
<div align="justify">
Prarambh-1 utilizes a highly optimized Potassium Nitrate-Sorbitol (KNSB) propellant matrix. To ensure safe operation and maximum efficiency, the transient chamber pressure ($P_c$) and burn surface area evolution were modeled. The linear regression rate ($r$) is characterized by Saint Robert’s Law:
</div>

<p align="center">
  $r = a \cdot P_c^n$
</p>

<div align="justify">
Through rigorous static fire testing, the burn rate coefficients ($a$ and $n$) were empirically tuned to match the actual performance of the 64:35:1 matrix. Overall engine efficiency is dynamically evaluated by calculating the Specific Impulse ($I_{sp}$) from load-cell thrust data:
</div>

<p align="center">
  $I_{sp} = \frac{\int_{0}^{t} F(t) \, dt}{m_p \cdot g_0}$
</p>

---

### ⚙️ HARDWARE FABRICATION & STRUCTURAL INTEGRITY
<div align="justify">
To withstand extreme thermal gradients and transient pressure spikes, the hardware architecture demands strict industrial tolerances:
</div>

* 🛡️ **Motor Casing Dynamics:** Analyzed for critical burst pressure ($\sigma_{burst}$) utilizing primary hoop stress calculations to establish a strict structural safety factor ($\eta$) exceeding peak expected chamber pressure.
* 🌪️ **Nozzle Expansion Geometry:** Convergent-divergent (De Laval) thermodynamic expansion ratio ($A_e/A_t$) was analytically derived and precision-machined to optimize exhaust gas velocity at sea-level ambient conditions.
* 🔥 **Thermal Insulation:** Strategic implementation of internal liners to mitigate casing heat-soak and prevent premature structural yield during the burn phase.

---

### 🗄️ REPOSITORY ARCHITECTURE (DEPLOYMENT READY)
<div align="justify">
<i>Structured for absolute peer-reviewed reproducibility, establishing a transparent pipeline from raw CAD to automated data-parsing.</i>
</div>

```text
📁 Prarambh-1-Solid-Motor/
│
├── 📁 CAD_Models/            # Hardware shell, nozzle geometries, and retention rings (STEP/SLDPRT)
├── 📁 simulations/           # Native OpenMotor (.om) and OpenRocket (.ork) flight profiles
├── 📁 data/                  # Load-cell telemetry (Note: Files >100MB excluded via .gitignore)
│   ├── raw_static_fire/      # Unprocessed CSV pressure/thrust transients
│   └── empirical_logs/       # Chemical variance and environmental tracking matrices
│
├── 📁 src/                   # Signal processing and validation pipeline
│   ├── parse_loadcell.py     # Noise filtering and signal smoothing for raw telemetry
│   └── compare_thrust.m      # MATLAB script overlaying empirical data onto OpenMotor targets
│
├── 📁 docs/                  # Structural safety calculations, expansion derivations, and SOPs
└── README.md                 # Main propulsion dossier (You are here)
