[อ่านภาษาไทยคลิกที่นี่](README_TH.md)

# GSL Engine
**A deterministic optimization architecture for the Vehicle Routing Problem (VRP).**

The GSL Engine (Geo Strategy Logistic Engine) is a proprietary computational architecture designed to explore scalable and deterministic approaches for complex logistics optimization problems. This repository serves as a centralized performance and research portfolio, showcasing benchmark evaluations, execution logs, and multi-variant routing capabilities.

**Disclaimer:** Source code is proprietary and not publicly available. This project is open to research collaboration, technical discussion, and industrial exploration.

---

## Engine Architecture & Supported Variants

The GSL Engine is modular and designed to support multiple VRP variants through deterministic feasibility-oriented execution:

- **CVRP (Capacitated VRP)** Module: `GSL_CVRP_V22`
- **VRPTW (VRP with Time Windows)** Module: `GSL_VRPTW_V111`
- **MDVRP (Multi-Depot VRP)** Module: `GSL_MDVRP_MASTER_V28`
- **MDVRPTW (Multi-Depot VRP with Time Windows)** Modules: `GSL_MDVRPTW_V38` & `GSL_MDVRPTW_REAL_V29`
- **PDPTW (Pickup & Delivery with Time Windows)** Status: Development Phase (Core Logic Completed)

---

## Execution Environment

- **Platform:** Android (Mobile Edge)
- **Runtime:** Python via Pydroid 3
- **CPU:** Snapdragon Architecture (ARM-based)
- **Execution Mode:** Sequential / Batch Processing
- **Constraint Handling:** Deterministic feasibility validation with zero stochastic sampling

---

## Milestone 1: CVRP Benchmark (CVRPLib-Based)

**Module:** `GSL_CVRP_V22`

### Zero-Tuning Policy
A unified execution configuration was used across all datasets without instance-specific parameter tuning, demonstrating consistent cross-dataset execution behavior.

### Detailed Performance Repositories

To maintain benchmark transparency and repository organization, detailed evaluations are separated into specialized repositories:

* 📁 **[GSL-CVRP-SETX](https://github.com/CT1-deMo-goG/GSL-CVRP-SETX)**  
  Uchoa Set X benchmark evaluations (100 - 1,000 nodes)

* 📁 **[GSL-CVRP-SETXL](https://github.com/CT1-deMo-goG/GSL-CVRP-SETXL)**  
  Hyper-scale benchmark evaluations (1,000 - 10,001 nodes)

---

### Hyper-Scale Sample (Set XL)

The engine produced feasible solutions for large-scale benchmark instances on mobile-class hardware:

| Instance | GSL Cost | Recorded BKS | Gap (%) | Status |
| :--- | :--- | :--- | :--- | :--- |
| XL-n5406-k783 | 1,050,660.38 | 1,040,536.0 | +0.97% | FEASIBLE |
| XL-n10001-k1570 | 2,432,382.86 | 2,333,757.0 | +4.23% | FEASIBLE |

---

### Dataset Coverage Summary

| Dataset | Instances | Avg. Gap to BKS | Avg. Runtime |
| :--- | :--- | :--- | :--- |
| Set X (Uchoa) | 100 | ~7.5% | 0.20s – 1.00s |
| Set XL (Hyper) | 100 | 1% – 15% | 6s – 2,172s |
| Set Tai (Taillard) | 13 | ~4.5% | < 0.30s |
| Set CMT | 14 | ~3.0% | < 0.10s |

---

### Proof of Execution

📹 **[Video Demonstration (10,000 Instances Run)](https://youtu.be/rsIjlrckyxw)**

---

## Milestone 2: VRPTW Benchmark

**Module:** `GSL_VRPTW_V111`

Evaluated on Solomon and Homberger benchmark families using the same zero-tuning execution strategy. Reported solutions satisfy capacity and time-window feasibility constraints under the tested configurations.

🔗 **[View VRPTW Benchmark Portfolio & Logs](https://github.com/CT1-demo-goG/GSL-VRPTW-Portfolio)**

---

## Milestone 3: MDVRP Benchmark

**Module:** `GSL_MDVRP_MASTER_V28`

- Evaluated on large-scale MDVRP scenarios, including a 10,000-node / 100-depot stress test executed on mobile hardware.
- Produced deterministic feasible solutions across evaluated Cordeau p-series and pr-series benchmark instances.

🔗 **[View MDVRP Benchmark Portfolio & Logs](https://github.com/CT1-demo-goG/gsl-mdvrp-engine)**

---

## Milestone 4: MDVRPTW Benchmark

**Modules:** `GSL_MDVRPTW_V38` & `GSL_MDVRPTW_REAL_V29`

- Evaluated using real-world logistics datasets involving multi-depot routing, time windows, asymmetric distances, and dual-capacity constraints.
- Internal deployment testing observed measurable routing cost reductions under deterministic execution conditions.
- Additional benchmark evaluations were conducted on Vidal dataset families (up to 960 nodes).

🔗 **[View MDVRPTW Benchmark Portfolio & Logs](https://github.com/CT1-demo-goG/gsl-mdvrptw-engine)**

---

## Research & Architecture Notes

### Deterministic Single-Pass Routing Architecture

This project also includes exploratory technical notes discussing:

- deterministic routing execution,
- low-latency dispatch systems,
- edge-constrained VRP computation,
- variance-free execution behavior,
- and mobile-scale logistics optimization.

📄 `Docs/deterministic_single_pass_whitepaper.md`

---

## Technical Strategy

- **Geometric Sensing:** Spatial clustering and deterministic route initialization.
- **Adaptive Fleet Structuring:** Dynamic workload balancing and capacity-oriented route construction.
- **Universal Parsing Core:** Multi-format dataset ingestion with automatic structural parsing.

---

## Problem Scope & Benchmark Specifications

The core optimization layer of the GSL Engine is designed primarily for the standard **Capacitated Vehicle Routing Problem (CVRP)** under deterministic execution constraints.

Primary optimization targets include:
- fleet capacity utilization,
- routing feasibility,
- and total travel distance minimization.

### Technical Note on Legacy Benchmarks (e.g., CMT Series)

Certain historical benchmark families (such as Christofides / CMT datasets) contain additional implicit constraints including route-distance ceilings.

Current evaluation logs for these instances reflect execution under a capacity-constrained interpretation unless otherwise specified.

Problems requiring strict duration ceilings or chronological feasibility enforcement are evaluated separately through specialized routing layers such as:
- VRPTW
- MDVRPTW

This separation is intended to preserve modularity and maintain computational efficiency across different routing environments.

---

## GSL-Solver Platform

**Deterministic Routing Platform**  
Access the platform here:

https://gsl-solver.com

---

## Professional Contact

**Independent Researcher:** Chonmapoohm Thamsuwan (CTSuwan)  
📧 ctsuwan@proton.me
