[อ่านภาษาไทยคลิกที่นี่](README_TH.md)
# GSL Engine
**A high-performance deterministic optimization engine for the Vehicle Routing Problem (VRP).**

The GSL Engine (Geo Strategy Logistic Engine) is a proprietary computational core designed to solve complex logistics optimization problems with strong efficiency and absolute determinism. This repository serves as the central performance portfolio, showcasing benchmark verification, execution logs, and multi-variant capabilities.

**Disclaimer:** Source code is proprietary and not publicly available. This project is open for research collaboration and industrial applications.

---

## Engine Architecture & Supported Variants
The GSL Engine is modular and designed to support multiple VRP variants with 100% deterministic feasibility:

- **CVRP (Capacitated VRP)** Module: `GSL_CVRP_V22` -> Deployed & Verified
- **VRPTW (VRP with Time Windows)** Module: `GSL_VRPTW_V111` -> Deployed & Verified
- **MDVRP (Multi-Depot VRP)** Module: `GSL_MDVRP_MASTER_V28` -> Deployed & Verified
- **MDVRPTW (Multi-Depot VRP with Time Windows)** Modules: `GSL_MDVRPTW_V38` & `GSL_MDVRPTW_REAL_V29` -> Deployed & Verified
- **PDPTW (Pickup & Delivery with Time Windows)** Status: Development (Core Logic Completed)

---

## Execution Environment
- **Platform:** Android (Mobile Edge)
- **Runtime:** Python via Pydroid 3
- **CPU:** Snapdragon Architecture (ARM-based)
- **Execution Mode:** High-Speed Sequential / Batch Processing
- **Constraint Handling:** Fully deterministic feasibility validation (Zero Stochastic Variance)

---

## Milestone 1: CVRP Benchmark (CVRPLib-Based)
**Module: GSL_CVRP_V22**

**Zero-Tuning Policy:** A single unified script was used across all datasets without instance-specific parameter tuning, demonstrating superior algorithmic generalization.

### **Detailed Performance Repositories**
To maintain transparency and data integrity, detailed benchmarks are separated into specialized repositories:

* 📁 **[GSL-CVRP-SETX](https://github.com/CT1-deMo-goG/GSL-CVRP-SETX)**: Focuses on the Uchoa Set X (100 - 1,000 nodes). Verified 100% Feasible.
* 📁 **[GSL-CVRP-SETXL](https://github.com/CT1-deMo-goG/GSL-CVRP-SETXL)**: Focuses on Hyper-Scale instances (1,000 - 10,001 nodes). Verified 100% Feasible.

### **Hyper-Scale Sample (Set XL)**
The engine successfully solved extreme-scale instances on a mobile device with verified feasibility:

| Instance | GSL Cost (Feasible) | Recorded BKS | Gap (%) | Status |
| :--- | :--- | :--- | :--- | :--- |
| **XL-n5406-k783** | 1,050,660.38 | 1,040,536.0 | +0.97% | FEASIBLE |
| **XL-n10001-k1570** | 2,432,382.86 | 2,333,757.0 | +4.23% | FEASIBLE (+63) |

**Dataset Coverage Summary**
| Dataset | Instances | Avg. Gap to BKS | Avg. Runtime |
| :--- | :--- | :--- | :--- |
| Set X (Uchoa) | 100 | ~7.5% | 0.20s – 1.00s |
| Set XL (Hyper) | 100 | 1% – 15% | 6s – 2,172s |
| Set Tai (Taillard) | 13 | ~4.5% | < 0.30s |
| Set CMT | 14 | ~3.0% | < 0.10s |

**Proof of Execution:** [Video Demonstration (10,000 Instances Run)](https://youtu.be/rsIjlrckyxw)

---

## Milestone 2: VRPTW Benchmark
**Module: GSL_VRPTW_V111**
Evaluated on Solomon and Homberger benchmarks using the same zero-tuning approach. All solutions are fully feasible (Capacity + Time Windows verified).

**[View VRPTW Benchmark Portfolio & Logs](https://github.com/CT1-demo-goG/GSL-VRPTW-Portfolio)**

---

## Milestone 3: MDVRP Benchmark
**Module: GSL_MDVRP_MASTER_V28**
- **Extreme Scale:** Solved a 10,000-node, 100-depot MDVRP network in **8.9 seconds**.
- **Cordeau Benchmark:** Achieved 100% deterministic feasibility across p-series and pr-series.

**[View MDVRP Benchmark Portfolio & Logs](https://github.com/CT1-demo-goG/gsl-mdvrp-engine)**

---

## Milestone 4: MDVRPTW Benchmark
**Modules: GSL_MDVRPTW_V38 & GSL_MDVRPTW_REAL_V29**
- **Commercial Case Study:** Optimized a real-world distribution dataset, achieving a **31.4% cost reduction** in 0.0078 seconds.
- **Vidal Benchmark:** Established mobile execution baselines for large-scale datasets (up to 960 nodes).

**[View MDVRPTW Benchmark Portfolio & Logs](https://github.com/CT1-demo-goG/gsl-mdvrptw-engine)**

---

## Technical Strategy
- **Geometric Sensing:** Spatial clustering and route initialization via deterministic logic.
- **Fleet Optimization (K-Focus):** Prioritizing vehicle minimization before distance refinement.
- **Universal Parsing Core:** Robust ingestion of multiple data formats with auto-K detection.

---

## Problem Scope & Benchmark Specifications

The core optimization module of the Geo Strategy Logistic (GSL) Engine is engineered strictly for the standard **Capacitated Vehicle Routing Problem (CVRP)**, focusing on maximizing fleet capacity utilization and minimizing overall Travel Distance (TD) under uniform demand profiles.

### Technical Note on Legacy Benchmarks (e.g., CMT Series):
* Certain legacy problem sets, such as the Christofides (CMT) series, contain multi-constraint profiles including implicit distance-duration ceilings (`DISTANCE` limits).
* Current evaluation logs for these specific instances reflect the engine's performance under a **Capacity-Constrained Only** environment.
* Advanced routing problems that require strict distance-ceiling enforcement or time-window integration are systematically separated into specialized routing layers (such as VRPTW / MDVRPTW modules) to maintain maximum computation speed and code modularity.

*
---
## GSL-Solver Platform
**The Enterprise Route Optimization Portal** Access the production-ready engine here: [**https://gsl-solver.com**](https://gsl-solver.com)

---

## Professional Contact
**Independent Researcher:** Chonmapoohm Thamsuwan (CTSuwan)  
**Email:** [ctsuwan@proton.me](mailto:ctsuwan@proton.me) 


