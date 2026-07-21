<h1 align="center">Prarambh-1: Empirical Solid Rocket Motor Architecture 🚀</h1>
<h4 align="center">High-Fidelity Multi-Physics Simulation, Ballistics, & DSP Telemetry Analysis</h4>

<p>
  <br>
  <img src="https://img.shields.io/badge/OpenMotor-8B0000?style=for-the-badge&logo=rocket&logoColor=white" alt="OpenMotor"/>
  <img src="https://img.shields.io/badge/Ansys-8B0000?style=for-the-badge&logo=Ansys&logoColor=white" alt="Ansys"/>
  <img src="https://img.shields.io/badge/Design For Manufacturing-8B0000?style=for-the-badge&logo=DFM&logoColor=white" alt="DFM"/>
  <img src="https://img.shields.io/badge/MATLAB-FFD700?style=for-the-badge&logo=mathworks&logoColor=black" alt="MATLAB"/>
  <img src="https://img.shields.io/badge/Python-FFD700?style=for-the-badge&logo=python&logoColor=black" alt="Python"/>
  <img src="https://img.shields.io/badge/Fusion_360-00FFFF?style=for-the-badge&logo=Autodesk&logoColor=black" alt="Fusion 360"/>
  <img src="https://img.shields.io/badge/KiCad-00FFFF?style=for-the-badge&logo=KiCad&logoColor=black" alt="KiCad"/>
  <img src="https://img.shields.io/badge/Microsoft Office-00FFFF?style=for-the-badge&logo=MicrosoftOffice&logoColor=black" alt="Microsoft Office"/>
  <img src="https://img.shields.io/badge/KiCad-00FFFF?style=for-the-badge&logo=KiCad&l
</p>

<p align="center">
  <img src="https://via.placeholder.com/800x400/0a0a0a/00FFFF?text=[INSERT+STATIC+FIRE+GIF+OR+CAD+RENDER+HERE]" alt="Prarambh-1 Hardware Render" width="100%"/>
</p>

---

<details open>
  <summary><b>📑 DIRECTORY TERMINAL (TABLE OF CONTENTS)</b></summary>
  <ol>
    <li><a href="#overview">Executive Propulsion Overview</a></li>
    <li><a href="#datasheet">System Datasheet & Engineering Targets</a></li>
    <li><a href="#thermodynamics">Theoretical Ballistics & Thermodynamics</a></li>
    <li><a href="#hardware">Hardware Fabrication & Bill of Materials</a></li>
    <li><a href="#daq">Data Acquisition (DAQ) & Signal Processing</a></li>
    <li><a href="#architecture">Repository Architecture & CI/CD</a></li>
    <li><a href="#validation">Empirical Validation Matrix (14-Iteration Log)</a></li>
    <li><a href="#deployment">Deployment & Reproducibility</a></li>
    <li><a href="#team">Team Architecture & Project Jericho</a></li>
    <li><a href="#academic">Academic Trajectory</a></li>
    <li><a href="#citation">Academic Citation</a></li>
  </ol>
</details>



### <a id="overview"></a>🌐 EXECUTIVE PROPULSION OVERVIEW

<div align="justify">
This repository archives the structural engineering parameters, mathematical modeling scripts, and empirical data analysis pipelines for the <b>Prarambh-1</b> solid rocket motor. Engineered as a foundational analytical model for high-altitude sounding rockets, the overriding objective was to simulate, track, and validate a predictable, high-performance burn profile.

By rejecting purely theoretical assumptions, the internal ballistics were validated through a rigorous data-driven, hardware-in-the-loop methodology. Across <b>14 empirical static-fire data sets</b>, raw telemetry was systematically ingested, passed through digital signal processing (DSP) filters, and mapped to perfectly align physical force readouts with high-fidelity computational simulations from OpenMotor.
</div>

---

### <a id="datasheet"></a>📋 SYSTEM DATASHEET & ENGINEERING TARGETS

<div align="justify">
The architecture bridges the critical gap between theoretical thermodynamic modeling, multiphysics flight simulation, and empirical data validation:
</div>

| Subsystem | Specification | Engineering Objective |
| :--- | :--- | :--- |
| **Propellant Matrix** | $64\%$ $KNO_3$ \| $35\%$ $C_6H_{14}O_6$ \| $1\%$ $Fe_2O_3$ | Achieve optimized linear burn rate ($r$) and thermodynamic stability. |
| **Grain Architecture** | Inhibited BATES Cylindrical | Maintain neutral thrust curve over the full temporal burn duration. |
| **Nozzle Expansion** | Convergent-Divergent (De Laval) | Optimize exhaust gas velocity ($v_e$) at sea-level ambient conditions. |
| **Telemetry DAQ** | High-Frequency Load Cell + 24-bit ADC | High-resolution temporal capture of transient pressure anomalies. |
| **Software Pipeline** | Python (Pandas/SciPy), MATLAB, OpenMotor | End-to-end signal processing and empirical-to-theoretical overlay. |
| **Safety Factor ($\eta$)**| > 2.5x Peak Operating Pressure | Absolute mitigation of Catastrophic Failure (CATO) scenarios. |
| **Project Status** | **VALIDATED** (14 Iterations) | Computational models cleared for future aerodynamic integration. |

---

### <a id="thermodynamics"></a>🧪 THEORETICAL BALLISTICS & THERMODYNAMICS

<div align="justify">
To ensure mathematical precision, the transient chamber pressure ($P_c$) and burn surface area evolution were rigorously modeled using foundational gas dynamics. The linear regression rate ($r$) is governed by Saint Robert’s Law:
</div>

$$r = a \cdot P_c^n$$

<div align="justify">
Through the analysis of static fire data, the empirical burn rate coefficient ($a$) and pressure exponent ($n$) were isolated. The theoretical efficiency of the combustion process is measured via its Characteristic Velocity ($c^*$), defining performance independent of nozzle expansion geometries:
</div>

$$c^* = \frac{P_c \cdot A_t}{\dot{m}}$$

<div align="justify">
Furthermore, the physical nozzle's efficiency in converting thermal energy into kinetic energy is modeled using the Thrust Coefficient ($C_f$), accounting for specific heat ratios ($\gamma$) and pressure differentials:
</div>

$$C_f = \sqrt{\frac{2\gamma^2}{\gamma-1}\left(\frac{2}{\gamma+1}\right)^{\frac{\gamma+1}{\gamma-1}}\left[1-\left(\frac{P_e}{P_c}\right)^{\frac{\gamma-1}{\gamma}}\right]} + \left(\frac{P_e - P_a}{P_c}\right)\frac{A_e}{A_t}$$

<div align="justify">
Overall macroscopic system efficiency is dynamically evaluated by computing the Specific Impulse ($I_{sp}$) by integrating the raw thrust curve ($F$) over the total burn time ($t$):
</div>

$$I_{sp} = \frac{\int_{0}^{t} F(t) \, dt}{m_p \cdot g_0}$$

---

### <a id="hardware"></a>⚙️ HARDWARE FABRICATION & BILL OF MATERIALS

<div align="justify">
To withstand extreme thermal gradients and transient pressure spikes, the hardware architecture was designed using strict industrial pressure vessel tolerances and rapid-prototyping workflows.
</div>

* 🛡️ **Motor Casing Dynamics:** Analyzed for critical burst pressure ($\sigma_{burst}$) utilizing Barlow's formula for primary hoop stress to establish a strict structural safety factor exceeding the peak expected chamber pressure. 
* 🌪️ **Nozzle Expansion Geometry:** The thermodynamic expansion ratio ($A_e/A_t$) was analytically derived to match exit pressure ($P_e$) with ambient pressure ($P_a$), maximizing thrust efficiency and preventing flow separation.
* ⚠️ **Thermal Inhibition & Ablation:** Strategic implementation of non-combustible internal liners to mitigate casing heat-soak. The liner thickness was calculated based on the maximum anticipated burn time.

**Primary Hardware Bill of Materials (BOM):**
| Component | Material / Specification | Subsystem |
| :--- | :--- | :--- |
| **Primary Casing** | 6061-T6 Aluminum Alloy | Pressure Vessel |
| **Convergent Nozzle** | Precision Machined Graphite | Thermodynamics / Exhaust |
| **Load Cell Sensor** | S-Type 100kg Industrial Strain Gauge | DAQ Telemetry |
| **Signal Amplifier** | HX711 (24-bit ADC) | DAQ Telemetry |
| **Test Stand Chassis** | Heavy-Gauge Welded Steel | Structural Containment |

---

### <a id="daq"></a>📡 DATA ACQUISITION (DAQ) & SIGNAL PROCESSING

<div align="justify">
Raw static fire telemetry is inherently noisy due to mechanical resonance, thrust stand vibrations, and electromagnetic interference (EMI). A core component of this repository is the custom digital signal processing (DSP) pipeline engineered to extract clean thrust metrics:
</div>

1. **High-Resolution Hardware Ingestion:** Raw CSV data is captured via industrial S-type load cells processed through high-precision ADCs. The sampling rate was engineered to adhere to the Nyquist sampling theorem for capturing micro-millisecond transient pressure spikes.
2. **Algorithmic Filtering Pipeline (Python):** * **Fast Fourier Transform (FFT):** Applied via `SciPy` to identify and isolate the frequencies of physical test-stand resonance.
   * **Butterworth Low-Pass Filter:** Implemented to attenuate the isolated high-frequency mechanical noise without degrading the integrity or dampening the amplitude of the primary thrust curve.
3. **Comparative Analysis Layer (MATLAB):** The cleaned data arrays are automatically ingested into MATLAB, calculating standard deviations, impulse integrations, and generating comparative visual overlays against the theoretical OpenMotor `.om` curves.

---

### <a id="architecture"></a>🗄️ REPOSITORY ARCHITECTURE & CI/CD

<div align="justify">
<i>Structured for absolute peer-reviewed reproducibility, establishing a transparent pipeline from initial 3D simulation to automated data-parsing.</i>
</div>

```text
📁 Prarambh-1-Solid-Motor/
│
├── 📁 .github/workflows/     # CI/CD: Automated linting and tests for Python DSP scripts
├── 📁 CAD_Models/            # Hardware boundaries, nozzle geometries (STEP/SLDPRT)
├── 📁 simulations/           # Native multi-physics profiles (.om, .ork)
├── 📁 data/                  # Load-cell telemetry (Note: Files >100MB excluded via .gitignore)
│   ├── raw_static_fire/      # Unprocessed CSV pressure/thrust transients
│   └── empirical_logs/       # Matrix logs for all 14 empirical test iterations
│
├── 📁 src/                   # Signal processing and validation pipeline
│   ├── filter_telemetry.py   # Python DSP script (FFT and Butterworth filtering)
│   ├── calculate_isp.py      # Numerical integration script for total impulse
│   └── compare_thrust.m      # MATLAB script overlaying empirical data onto OpenMotor targets
│
├── 📁 docs/                  # Mathematical derivations and SOPs
├── requirements.txt          # Python environment dependencies
└── README.md                 # Main propulsion dossier
