[อ่านภาษาไทยคลิกที่นี่](README_TH.md)
# GSL Engine
A proprietary, high-performance heuristic optimization engine for the Vehicle Routing Problem (VRP).

The GSL Engine is a closed-source computational core designed to solve complex logistics optimization problems with strong efficiency and adaptability. 
This repository serves as a performance portfolio, including benchmark verification, execution logs, and proof-of-capability.

**Disclaimer:** Source code is proprietary and not publicly available. 
This project is open for research collaboration and industrial applications.

---

## Engine Architecture & Supported Variants
The GSL Engine is modular and designed to support multiple VRP variants:

- **CVRP (Capacitated VRP)** Module: `GSL_CVRP_V22` -> Deployed & Verified

- **VRPTW (VRP with Time Windows)** Module: `GSL_VRPTW_V111` -> Deployed & Verified

- **MDVRP (Multi-Depot VRP)** Module: `GSL_MDVRP_MASTER_V28` -> Deployed & Verified

- **MDVRPTW (Multi-Depot VRP with Time Windows)** Modules: `GSL_MDVRPTW_V38` & `GSL_MDVRPTW_REAL_V29` -> Deployed & Verified

- **PDPTW (Pickup & Delivery with Time Windows)** Status: Development (Core Logic Completed, Pending Benchmark)

---

## Execution Environment
- **Platform:** Android (Mobile Edge)
- **Runtime:** Python via Pydroid 3
- **CPU:** Snapdragon Architecture
- **Execution Mode:** Sequential / Batch Processing
- **Constraint Handling:** Fully deterministic feasibility validation

*The engine is designed to scale beyond mobile environments and can be deployed on servers or high-performance systems.*

---

## Milestone 1: CVRP Benchmark (CVRPLib-Based)
**Module: GSL_CVRP_V22**

**Zero-Tuning Policy** A single unified script was used across all datasets:
- No instance-specific parameter tuning
- No manual adjustment per dataset
- Fully autonomous solving behavior  
*This demonstrates algorithmic generalization and robustness.*

**Large-Scale Performance (Set XL)** The engine successfully solved large-scale instances (10,000+ nodes) on a mobile device.

| Instance | GSL Distance | Recorded BKS | Relative Difference |
| :--- | :--- | :--- | :--- |
| XL-n1374-k278 | 232,139.97 | 233,049.00 | -0.39% |
| XL-n10001-k1570 | 2,332,319.27 | 2,333,757.00 | -0.06% |

*Note: These results are preliminary observations and are subject to independent verification.* **View Full Set XL Benchmark Repository & Logs**

**Dataset Coverage**
| Dataset | Instances | Avg. Gap to BKS | Avg. Runtime |
| :--- | :--- | :--- | :--- |
| Set X (Uchoa) | 100 | ~7.5% | 0.20s – 1.00s |
| Set Tai (Taillard) | 13 | ~4.5% | < 0.30s |
| Golden / Li | 32 | 19% – 37% | 1s – 60s |
| Set A, B, E, F, M, P | 95 | 4% – 12% | < 0.15s |
| Set CMT | 14 | ~3.0% | < 0.10s |

**Detailed Performance Analysis** For an in-depth evaluation of GSL Engine V22 against industry-standard benchmarks, visit the comparative study folder. This analysis provides the necessary engineering context for the results observed above:
- **Comparative Context:** Methodology regarding BKS and State-of-the-art (HGS) baselines.
- **GSL vs. LNS:** Analysis against Metaheuristic search (demonstrating 87% Win Rate in Set X).
- **GSL vs. CW:** Time-Complexity validation showing $O(1)$ scalability vs. $O(N^2 \log N)$.  

**Endurance Test: Large Batch Execution**
- Total Instances: 10,000+
- Dataset Type: XML-based (CVRPLib format derived)
- Failure Rate: 0%
- Output: Complete `.sol` files generated for all instances

**Proof of Execution** This video demonstrates large-scale execution of the GSL Engine on CVRPLib XML datasets (10,000 instances).
- Continuous run
- Full solution generation (.sol)
- Zero-tuning approach  
**Video:** https://youtu.be/rsIjlrckyxw

---

## Milestone 2: VRPTW Benchmark
**Module: GSL_VRPTW_V111**

The engine was evaluated on Solomon and Homberger benchmarks using the same zero-tuning approach.

**Performance Summary**
| Dataset | Scale | BKS Match Rate | Avg. Runtime |
| :--- | :--- | :--- | :--- |
| Solomon-100 | Small | 46.4% | ~2.78 s |
| Solomon-200 | Medium | 51.7% | ~7.57 s |
| Homberger-400 | Large | 35.0% | ~20.0 s |
| Homberger-600 | Large | 30.0% | ~29.2 s |
| Homberger-800 | Massive | 35.0% | ~31.15 s |
| Homberger-1000 | Massive | 21.6% | ~38.22 s |

*All solutions are fully feasible (capacity + time windows verified)*

**Reproducibility & Verification**
All reported results:
- Deterministically reproducible under identical inputs  
- Verified for feasibility constraints  
- Exported in standard `.sol` format  
- Supported by execution logs and recorded outputs  
**[View VRPTW Benchmark Portfolio & Logs](https://github.com/CT1-demo-goG/GSL-VRPTW-Portfolio)**

---

## Milestone 3: MDVRP Benchmark
**Module: GSL_MDVRP_MASTER_V28**

Demonstrating world-class execution speed and benchmark verification for Multi-Depot constraints on mobile edge architecture.

- **Extreme Scale Stress Test:** Solved a massive **10,000-node, 100-depot** MDVRP network in just **8.9 seconds**.
- **Cordeau Benchmark:** Achieved 100% deterministic feasibility across all standard academic instances (p-series and pr-series) in sub-second execution times.  
**[View MDVRP Benchmark Portfolio & Logs](https://github.com/CT1-demo-goG/gsl-mdvrp-engine)**

---

## Milestone 4: MDVRPTW Benchmark (Real-World & Academic)
**Modules: GSL_MDVRPTW_V38 & GSL_MDVRPTW_REAL_V29**

This represents the most complex routing architecture in the GSL framework. It handles multiple depots, strict 2D-capacity constraints, asymmetric distances, and rigid time windows simultaneously.

- **Commercial Proof of Concept (Bosnia Dataset):** Tested against a real-world logistics dataset from a major distribution company. The GSL engine optimized the legacy system, saving 169.08 KM per delivery cycle (**31.4% Cost Reduction**) in just **0.0078 seconds**.
- **Vidal Large-Scale Benchmark:** Established new mobile execution baselines for massive datasets (up to 960 nodes).  
**[View MDVRPTW Benchmark Portfolio & Logs](https://github.com/CT1-demo-goG/gsl-mdvrptw-engine)**

---

## Technical Strategy
The GSL Engine focuses on targeted heuristic intelligence, avoiding brute-force complexity:

- **Geometric Sensing:** Spatial clustering and route initialization using geometric logic
- **Deterministic Vehicle Minimization (K-Focus):** Prioritizing fleet reduction before distance optimization
- **Temporal Constraint Synchronization:** Efficient handling of time windows without exponential growth
- **Universal Parsing Core:** Robust data ingestion across multiple formats (including auto-K detection)

---

## Vision
The GSL Engine is designed not only as a solver but as a **scalable routing intelligence core**:

- From mobile execution -> to server deployment
- From benchmark solving -> to real-world logistics systems
- From research prototype -> to commercial optimization platform

---

## GSL-Solver Platform
**The Enterprise Route Optimization Portal** Access the production-ready deterministic engine here:  
**[https://gsl-solver.com](https://gsl-solver.com)**

---

## Professional Contact
**Independent Researcher:** Chonmapoohm Thamsuwan (CTSuwan)  
**Email:** [ctsuwan@proton.me](mailto:ctsuwan@proton.me)  

---

## Services & Collaboration
Open to professional engagement in the following areas:

- **Logistics-as-a-Service (LaaS):** Real-time route optimization for enterprise fleets.
- **High-Precision Modeling:** Custom algorithmic solutions for complex supply chain constraints.
- **Technical Consultancy:** Large-scale network stress-testing and optimization audits.

