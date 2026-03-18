# GSL Engine 🚀

**A proprietary, high-performance heuristic optimization engine for the Vehicle Routing Problem (VRP).**

The GSL Engine is a closed-source computational core designed to solve complex logistics optimization problems with strong efficiency and adaptability.  
This repository serves as a **performance portfolio**, including benchmark verification, execution logs, and proof-of-capability.

> ⚠️ **Disclaimer:** Source code is proprietary and not publicly available.  
> This project is open for **research collaboration and industrial applications**.

---

## 📌 Engine Architecture & Supported Variants

The GSL Engine is modular and designed to support multiple VRP variants:

- **CVRP** (Capacitated VRP)  
  *Module:* `GSL_CVRP_V22` → ✅ Deployed & Verified  

- **VRPTW** (VRP with Time Windows)  
  *Module:* `GSL_VRPTW_V111` → ✅ Deployed & Verified  

- **PDPTW** (Pickup & Delivery with Time Windows)  
  *Status:* 🔄 Development (Core Logic Completed, Pending Benchmark)  

- **MDVRP** (Multi-Depot VRP)  
  *Status:* 🔄 Development (Script Frozen, Pending Benchmark)

---

## ⚙️ Execution Environment

- Platform: Android (Mobile)
- Runtime: Python via Pydroid 3
- CPU: Snapdragon Architecture
- Execution Mode: Sequential / Batch Processing
- Constraint Handling: Fully deterministic feasibility validation

> The engine is designed to scale beyond mobile environments and can be deployed on servers or high-performance systems.

---

## 🔬 Milestone 1: CVRP Benchmark (CVRPLib-Based)

**Module:** `GSL_CVRP_V22`  

### 🧠 Zero-Tuning Policy
A **single unified script** was used across all datasets:

- ❌ No instance-specific parameter tuning  
- ❌ No manual adjustment per dataset  
- ✅ Fully autonomous solving behavior  

This demonstrates **algorithmic generalization and robustness**.

---

### 🌟 Large-Scale Performance (Set XL)

The engine successfully solved **large-scale instances (10,000+ nodes)** on a mobile device.

**Observed Results (Snapshot):**

| Instance | GSL Distance | Recorded BKS | Relative Difference |
| :--- | :--- | :--- | :--- |
| XL-n1374-k278 | 232,139.97 | 233,049.00 | -0.39% |
| XL-n10001-k1570 | 2,332,319.27 | 2,333,757.00 | -0.06% |

> 📌 These results are **preliminary observations** and are subject to independent verification.
👉 **[View Full Set XL Benchmark Repository & Logs]
[Click here] (https://github.com/CT1-deMo-goG/GSL-Engine-SetXL-Benchmark.git)
**


---

### 📊 Dataset Coverage

| Dataset | Instances | Avg. Gap to BKS | Avg. Runtime |
| :--- | :---: | :---: | :---: |
| Set X (Uchoa) | 100 | ~7.5% | 0.20s – 1.00s |
| Set Tai (Taillard) | 13 | ~4.5% | < 0.30s |
| Golden / Li | 32 | 19% – 37% | 1s – 60s |
| Set A, B, E, F, M, P | 95 | 4% – 12% | < 0.15s |
| Set CMT | 14 | ~3.0% | < 0.10s |

---

### 🏁 Endurance Test: Large Batch Execution

- Total Instances: 10,000+  
- Dataset Type: XML-based (CVRPLib format derived)  
- Failure Rate: **0%**  
- Output: Complete `.sol` files generated for all instances  

📎 *[Insert Video Proof Link]*

---

## ⏱️ Milestone 2: VRPTW Benchmark

**Module:** `GSL_VRPTW_V111`  

The engine was evaluated on **Solomon and Homberger benchmarks** using the same zero-tuning approach.

---

### 📊 Performance Summary

| Dataset | Scale | BKS Match Rate | Avg. Runtime |
| :--- | :--- | :---: | :---: |
| Solomon-100 | Small | 46.4% | ~2.78 s |
| Solomon-200 | Medium | 51.7% | ~7.57 s |
| Homberger-400 | Large | 35.0% | ~20 s |
| Homberger-600 | Large | 30.0% | ~29.2 s |
| Homberger-800 | Massive | 35.0% | ~31.15 s |
| Homberger-1000 | Massive | 21.6% | ~38.22 s |

> ✅ All solutions are **fully feasible** (capacity + time windows verified)

---

## 🔁 Reproducibility & Verification

All reported results:

- ✔ Deterministically reproducible under identical inputs  
- ✔ Verified for feasibility constraints  
- ✔ Exported in standard `.sol` format  
- ✔ Supported by execution logs and recorded outputs  

📎 *[Click here] (https://github.com/CT1-deMo-goG/GSL-Axiomatic-TW-Portfolio.git)*

---

## 🧠 Technical Strategy

The GSL Engine focuses on **targeted heuristic intelligence**, avoiding brute-force complexity:

1. **Geometric Sensing**  
   Spatial clustering and route initialization using geometric logic  

2. **Deterministic Vehicle Minimization (K-Focus)**  
   Prioritizing fleet reduction before distance optimization  

3. **Temporal Constraint Synchronization**  
   Efficient handling of time windows without exponential growth  

4. **Universal Parsing Core**  
   Robust data ingestion across multiple formats (including auto-K detection)

---

## 🌍 Vision

The GSL Engine is designed not only as a solver but as a **scalable routing intelligence core**:

- From mobile execution → to server deployment  
- From benchmark solving → to real-world logistics systems  
- From research prototype → to commercial optimization platform  

---

## 💼 Professional Contact

**Independent Researcher:**  
Chonmapoohm Thamsuwan (CTSuwan)  

📧 Email: ctsuwan@proton.me  

---

## 🤝 Collaboration

Open to:

- Industrial routing optimization projects  
- Research collaboration  
- High-performance logistics systems  

📎 *[Upwork Profile ] [Clickhere] (https://www.upwork.com/freelancers/~0173b4a58a1a327fd6?mp_source=share)
*  
📎 *[Fastwork Profile – Insert Link]*

—

