# Comparative Analysis and Benchmark Context

To evaluate the performance of the GSL Engine V22, results are compared against widely reported benchmarks in the CVRP literature, including Best Known Solutions (BKS) and representative results from state-of-the-art solvers.

State-of-the-art methods, particularly the Hybrid Genetic Search (HGS-CVRP) framework developed by Thibaut Vidal, have demonstrated near-optimal performance on standard benchmark sets such as Set X, often achieving solutions that closely match or reach BKS values.

However, publicly available results for ultra-large-scale instances (e.g., Set XL with more than 10,000 nodes) remain limited and are not consistently reported across all instances in the literature.

Due to computational constraints and the lack of complete large-scale reference datasets, direct reimplementation or full-scale replication of such methods was not performed in this study. Instead, published benchmark results and BKS references are used as a comparative baseline.

The evaluation is therefore structured across three benchmark tiers:

- **Set A (small-scale):** Used to validate baseline feasibility and correctness.
- **Set X (medium- to large-scale):** Used for comparison against established benchmarks and literature-reported performance.
- **Set XL (ultra-large-scale):** Used to evaluate scalability and structural robustness in scenarios where standardized comparisons are limited.

Across Set X, the GSL Engine V22 produces solutions that are consistently close to BKS, indicating competitive performance relative to state-of-the-art methods under comparable evaluation conditions.

For Set XL, where direct benchmark comparisons are not consistently available, results demonstrate that GSL maintains stable solution quality even as problem size increases significantly. This contrasts with the typical performance degradation observed in iteration-bounded metaheuristics when scaling to very large instances.

The underlying reason for this behavior lies in the deterministic structure of the GSL framework, which follows a cluster-first, route-second paradigm. Unlike stochastic metaheuristics that rely on repeated search iterations, GSL constructs solutions through structured decomposition, allowing it to scale more predictably under constrained computational environments.

Notably, in a small number of instances, GSL results slightly outperform reported BKS values; these cases may be due to rounding differences or reference updates and should be interpreted with caution.

Overall, the results suggest that deterministic routing approaches provide a viable and scalable alternative for solving large-scale CVRP instances, particularly in environments with limited computational resources.

---
**Detailed Reports:**
- [Performance vs. Metaheuristic Baseline (LNS)](./GSL_vs_LNS.md)
- [Performance vs. Standard Constructive Heuristic (CW)](./GSL_vs_CW.md)
