# GSL Engine: Benchmark Methodology

This document outlines the standard operating procedures, environmental constraints, and evaluation metrics used to benchmark the **GSL Engine** across various Vehicle Routing Problem (VRP) datasets.

## 1. Execution Environment & Hardware Constraints
Unlike conventional heuristic solvers that rely on distributed computing, high-performance desktop CPUs, or compiled C++ libraries, the GSL Engine benchmarks were executed under extreme hardware constraints to prove algorithmic efficiency.

* **Hardware:** Standard Mobile Device (ARM-based Snapdragon Processor)
* **OS / Environment:** Android OS
* **Interpreter:** Pydroid 3 (Native Python 3.x environment)
* **Memory Handling:** Strict mobile RAM limitations (Proving zero memory leaks even on 10,000-node instances).

## 2. Algorithmic Consistency (The "Zero-Tuning" Policy)
To ensure absolute academic and industrial integrity, the GSL Engine strictly adheres to a **Zero-Tuning Policy**. 
* **Single Unified Script:** A single algorithm version (e.g., `GSL_CVRP_V22` for CVRP) was used to solve **all** instances within a module. 
* **No Instance-Specific Overfitting:** There were no hard-coded parameter adjustments, conditional logic tweaks, or manual interventions tailored to specific datasets (such as altering behavior for Set A vs. Set XL). The engine relies entirely on dynamic spatial sensing to adapt to the data autonomously.

## 3. Distance Metrics & Calculation Standards
* **Distance Formula:** Standard 2D Euclidean distance (exact floating-point precision) was strictly utilized across all coordinates unless a pre-calculated explicit distance matrix was provided by the dataset (e.g., Set E).
* **Legacy Scaling:** Certain legacy datasets (e.g., DIMACS format) utilize artificial scaling factors (multiplying coordinates by 10 or 100 to force integer rounding). The GSL Engine computes raw Euclidean distances. When comparing against scaled BKS, the scaling factor was mathematically normalized to ensure an accurate, apples-to-apples comparison.

## 4. Evaluation Metrics
The primary metric for solution quality is the **Relative Gap** to the Best Known Solution (BKS) recorded in the CVRPLIB repository.
* **Formula:** `Gap (%) = ((GSL_Distance - BKS) / BKS) * 100`
* **Feasibility Audit:** Every output route is strictly audited to ensure 100% compliance with vehicle capacity (CVRP) and temporal constraints (VRPTW). Overloaded routes or time-window violations result in an immediate fail state.
* 
