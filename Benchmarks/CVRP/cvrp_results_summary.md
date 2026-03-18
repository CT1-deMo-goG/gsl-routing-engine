# CVRP Detailed Benchmark Results 📊
**Module:** `GSL_CVRP_V22`  
**Platform:** Mobile Processor (Android / Pydroid 3)  
**Execution Policy:** Zero-Tuning (Single Unified Script)

This document contains the detailed instance-by-instance execution logs for the CVRP global benchmark datasets. All runs were executed natively on a mobile device to demonstrate the extreme computational efficiency of the GSL Engine.

---

## 1. Classical Datasets (Augerat, Christofides, Fisher)

### Dataset: Set A (Augerat)
| Instance | GSL Cost | BKS | Gap | k/K | Time (Mobile) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| A-n32-k5 | 863.10 | 784.0 | +10.09% | 5/5 | 0.01 s |
| A-n33-k5 | 717.04 | 661.0 | +8.48% | 5/5 | 0.01 s |
| A-n33-k6 | 764.54 | 742.0 | +3.04% | 6/6 | 0.01 s |
| A-n34-k5 | 811.09 | 778.0 | +4.25% | 5/5 | 0.01 s |
| A-n36-k5 | 814.89 | 799.0 | +1.99% | 5/5 | 0.01 s |
| A-n37-k5 | 732.55 | 669.0 | +9.50% | 5/5 | 0.01 s |
| A-n37-k6 | 980.39 | 949.0 | +3.31% | 6/6 | 0.01 s |
| A-n38-k5 | 771.07 | 730.0 | +5.63% | 5/5 | 0.01 s |
| A-n39-k5 | 892.90 | 822.0 | +8.63% | 5/5 | 0.03 s |
| A-n39-k6 | 856.93 | 831.0 | +3.12% | 6/6 | 0.01 s |
| A-n44-k6 | 997.37 | 937.0 | +6.44% | 6/6 | 0.02 s |
| A-n45-k6 | 981.28 | 944.0 | +3.95% | 6/6 | 0.01 s |
| A-n45-k7 | 1190.57 | 1146.0 | +3.89% | 7/7 | 0.05 s |
| A-n46-k7 | 937.28 | 914.0 | +2.55% | 7/7 | 0.01 s |
| A-n48-k7 | 1137.06 | 1073.0 | +5.97% | 7/7 | 0.01 s |
| A-n53-k7 | 1093.28 | 1010.0 | +8.25% | 7/7 | 0.04 s |
| A-n54-k7 | 1202.41 | 1167.0 | +3.03% | 7/7 | 0.02 s |
| A-n55-k9 | 1103.61 | 1073.0 | +2.85% | 9/9 | 0.04 s |
| A-n60-k9 | 1407.09 | 1354.0 | +3.92% | 9/9 | 0.02 s |
| A-n61-k9 | 1091.08 | 1034.0 | +5.52% | 9/9 | 0.06 s |
| A-n62-k8 | 1362.67 | 1288.0 | +5.80% | 8/8 | 0.02 s |
| A-n63-k10 | 1349.11 | 1314.0 | +2.67% | 10/10 | 0.02 s |
| A-n63-k9 | 1704.45 | 1616.0 | +5.47% | 9/9 | 0.02 s |
| A-n64-k9 | 1478.28 | 1401.0 | +5.52% | 9/9 | 0.16 s |
| A-n65-k9 | 1290.67 | 1174.0 | +9.94% | 9/9 | 0.07 s |
| A-n69-k9 | 1231.48 | 1159.0 | +6.25% | 9/9 | 0.05 s |
| A-n80-k10 | 1873.04 | 1763.0 | +6.24% | 10/10 | 0.08 s |

### Dataset: Set B (Augerat)
| Instance | GSL Cost | BKS | Gap | k/K | Time (Mobile) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| B-n31-k5 | 676.53 | 672.0 | +0.67% | 5/5 | 0.09 s |
| B-n34-k5 | 793.17 | 788.0 | +0.66% | 5/5 | 0.07 s |
| B-n35-k5 | 970.67 | 955.0 | +1.64% | 5/5 | 0.01 s |
| B-n38-k6 | 825.57 | 805.0 | +2.56% | 6/6 | 0.04 s |
| B-n39-k5 | 564.90 | 549.0 | +2.90% | 5/5 | 0.14 s |
| B-n41-k6 | 932.80 | 829.0 | +12.52% | 6/6 | 0.01 s |
| B-n43-k6 | 800.41 | 742.0 | +7.87% | 6/6 | 0.01 s |
| B-n44-k7 | 937.30 | 909.0 | +3.11% | 7/7 | 0.08 s |
| B-n45-k5 | 733.25 | 751.0 | -2.36% | 5/5 | 0.01 s |
| B-n45-k6 | 714.02 | 678.0 | +5.31% | 6/6 | 0.17 s |
| B-n50-k7 | 750.07 | 741.0 | +1.22% | 7/7 | 0.09 s |
| B-n50-k8 | 1375.33 | 1312.0 | +4.83% | 8/8 | 0.05 s |
| B-n51-k7 | 1056.10 | 1032.0 | +2.33% | 7/7 | 0.05 s |
| B-n52-k7 | 762.61 | 747.0 | +2.09% | 7/7 | 0.18 s |
| B-n56-k7 | 734.26 | 707.0 | +3.86% | 7/7 | 0.23 s |
| B-n57-k7 | 1260.07 | 1153.0 | +9.29% | 7/7 | 0.25 s |
| B-n57-k9 | 1651.52 | 1598.0 | +3.35% | 9/9 | 0.12 s |
| B-n63-k10 | 1596.13 | 1496.0 | +6.69% | 10/10 | 0.09 s |
| B-n64-k9 | 900.56 | 861.0 | +4.59% | 9/9 | 0.11 s |
| B-n66-k9 | 1385.27 | 1316.0 | +5.26% | 9/9 | 0.07 s |
| B-n67-k10 | 1093.12 | 1032.0 | +5.92% | 10/10 | 0.08 s |
| B-n68-k9 | 1307.57 | 1272.0 | +2.80% | 9/9 | 0.19 s |
| B-n78-k10 | 1262.00 | 1221.0 | +3.36% | 10/10 | 0.25 s |

### Dataset: Set E, F, M, P, CMT (Summary Logs)
*(Note: Full detailed records for Sets E, F, M, P, and CMT are available in the raw `.sol` archive. The engine achieved processing times generally under 0.10s per instance across these classical sets).*

---

## 2. Modern & Complex Datasets (Taillard, Golden, Li)

### Dataset: Set Tai (Taillard)
| Instance | GSL Cost | BKS | Gap | k/K | Time (Mobile) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| tai75a | 1646.66 | 1618.36 | +1.75% | 10/10 | 0.04 s |
| tai75b | 1386.23 | 1344.62 | +3.09% | 9/9 | 0.04 s |
| tai75c | 1370.13 | 1291.01 | +6.13% | 9/9 | 0.04 s |
| tai75d | 1362.03 | 1365.42 | -0.25% | 9/9 | 0.09 s |
| tai100a | 2166.72 | 2041.34 | +6.14% | 11/11 | 0.20 s |
| tai100b | 2018.42 | 1939.90 | +4.05% | 11/11 | 0.06 s |
| tai100c | 1437.84 | 1406.20 | +2.25% | 11/11 | 0.06 s |
| tai100d | 1649.55 | 1580.46 | +4.37% | 11/11 | 0.07 s |
| tai150a | 3356.94 | 3055.23 | +9.88% | 15/15 | 0.40 s |
| tai150b | 2866.49 | 2727.03 | +5.11% | 14/14 | 0.49 s |
| tai150c | 2457.48 | 2358.66 | +4.19% | 14/14 | 0.77 s |
| tai150d | 2746.35 | 2645.39 | +3.82% | 14/14 | 0.35 s |
| tai385 | 25941.20 | 24366.41 | +6.46% | 46/46 | 0.87 s |

### Dataset: Set Golden
| Instance | GSL Cost | BKS | Gap | k/K | Time (Mobile) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Golden_1 | 6507.70 | 5623.47 | +15.72% | 9/9 | 0.57 s |
| Golden_5 | 9067.13 | 6460.98 | +40.34% | 5/5 | 0.57 s |
| Golden_9 | 687.74 | 579.70 | +18.64% | 14/14 | 2.04 s |
| Golden_17 | 782.30 | 707.75 | +10.53% | 22/22 | 0.30 s |
| Golden_20 | 2005.78 | 1817.59 | +10.35% | 38/38 | 0.99 s |
*(Representative subset shown. Full Golden set successfully solved).*

### Dataset: Set Li
| Instance | GSL Cost | BKS | Gap | k/K | Time (Mobile) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Li_21 | 22762.77 | 16212.82 | +40.40% | 10/10 | 12.32 s |
| Li_22 | 16451.48 | 14499.04 | +13.47% | 14/14 | 6.26 s |
| Li_25 | 19333.90 | 16665.70 | +16.01% | 17/17 | 7.62 s |
| Li_27 | 19278.44 | 17320.00 | +11.31% | 19/19 | 9.36 s |
*(Representative subset shown. Full Li set successfully solved).*

---
**Status:** Verification Complete ✅  
*All raw `.sol` files are stored within their respective directory structures.*
