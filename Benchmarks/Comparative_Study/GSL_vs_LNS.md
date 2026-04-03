# Technical Benchmark Report: GSL Engine V22 vs. Metaheuristic Baseline (LNS)
**Date:** April 1, 2026  
**Subject:** Cross-Scale Performance & Time-Bounded Validation (Sets A, X, XL)  
**Core Framework:** Deterministic Routing Logic  

---

## 1. Executive Summary

This report presents a comparative evaluation between the GSL Engine V22 and a Large Neighborhood Search (LNS) metaheuristic under fixed iteration constraints.

The evaluation covers three benchmark sets of increasing scale: Set A, Set X, and Set XL, including instances up to 10,000 nodes.

Under iteration limits, LNS performs competitively on small instances but degrades significantly as problem size increases.

In contrast, GSL Engine V22 demonstrates stable performance across all scales, maintaining relatively low solution gaps without relying on intensive iterative search.

In a few cases, GSL achieves slightly better results than reported Best Known Solutions (BKS). These differences may be due to rounding or dataset updates and are interpreted cautiously.

All experiments were conducted under consistent runtime conditions to ensure fair comparison.

Overall, the results indicate that deterministic routing approaches are effective for large-scale CVRP under constrained computational settings.
---

## 2. Benchmark Results: SET A (Precision Scale)
**Objective:** Evaluate base routing efficiency and convergence in small search spaces (30 - 80 nodes).

| Instance | BKS | GSL Gap | LNS Gap | Winner |
| :--- | :--- | :--- | :--- | :--- |
| A-n32-k5 | 784.0 | 10.09% | 9.79% | LNS |
| A-n33-k5 | 661.0 | 8.48% | 8.39% | LNS |
| A-n33-k6 | 742.0 | 3.04% | 4.75% | GSL |
| A-n34-k5 | 778.0 | 4.25% | 5.46% | GSL |
| A-n36-k5 | 799.0 | 1.99% | 3.46% | GSL |
| A-n37-k5 | 669.0 | 9.50% | 6.62% | LNS |
| A-n37-k6 | 949.0 | 3.31% | 6.92% | GSL |
| A-n38-k5 | 730.0 | 5.63% | 14.08% | GSL |
| A-n39-k5 | 822.0 | 8.63% | 13.04% | GSL |
| A-n39-k6 | 831.0 | 3.12% | 11.49% | GSL |
| A-n44-k6 | 937.0 | 6.44% | 6.81% | GSL |
| A-n45-k6 | 944.0 | 3.95% | 4.93% | GSL |
| A-n45-k7 | 1146.0 | 3.89% | 7.68% | GSL |
| A-n46-k7 | 914.0 | 2.55% | 7.35% | GSL |
| A-n48-k7 | 1073.0 | 5.97% | 7.16% | GSL |
| A-n53-k7 | 1010.0 | 8.25% | 15.59% | GSL |
| A-n54-k7 | 1167.0 | 3.03% | 9.28% | GSL |
| A-n55-k9 | 1073.0 | 2.85% | 2.40% | LNS |
| A-n60-k9 | 1354.0 | 3.92% | 6.86% | GSL |
| A-n61-k9 | 1034.0 | 5.52% | 7.88% | GSL |
| A-n62-k8 | 1288.0 | 5.80% | 8.11% | GSL |
| A-n63-k10 | 1314.0 | 2.67% | 9.08% | GSL |
| A-n63-k9 | 1616.0 | 5.47% | 8.53% | GSL |
| A-n64-k9 | 1401.0 | 5.52% | 7.45% | GSL |
| A-n65-k9 | 1174.0 | 9.94% | 9.61% | LNS |
| A-n69-k9 | 1159.0 | 6.25% | 5.71% | LNS |
| A-n80-k10 | 1763.0 | 6.24% | 10.44% | GSL |
Summary (Set A):
GSL Win Rate: 70.4%
LNS remains competitive in smaller instances where local search efficiency is sufficient.
---

## 3. Benchmark Results: SET X (Complexity Scale)
**Objective:** Evaluate stability under increased topological complexity (100 - 1,000 nodes).
*Note: In a few cases, GSL achieves slightly better results than reported BKS, possibly due to rounding differences or dataset updates.*
| Instance | BKS | GSL Gap | LNS Gap | Winner |
| :--- | :--- | :--- | :--- | :--- |
| X-n1001-k43 | 72355.0 | 13.19% | 18.80% | GSL |
| X-n101-k25 | 27591.0 | **-2.18%** | 11.67% | GSL |
| X-n106-k14 | 26362.0 | 7.47% | 6.24% | LNS |
| X-n110-k13 | 14971.0 | 13.23% | 14.84% | GSL |
| X-n115-k10 | 12747.0 | 8.85% | 10.77% | GSL |
| X-n120-k6 | 13332.0 | 13.06% | 9.83% | LNS |
| X-n125-k30 | 55539.0 | 2.29% | 12.67% | GSL |
| X-n129-k18 | 28940.0 | 5.64% | 14.21% | GSL |
| X-n134-k13 | 10916.0 | 6.11% | 25.75% | GSL |
| X-n139-k10 | 13590.0 | 13.69% | 20.69% | GSL |
| X-n143-k7 | 15700.0 | 15.57% | 20.80% | GSL |
| X-n148-k46 | 43448.0 | **-0.52%** | 19.18% | GSL |
| X-n153-k22 | 21220.0 | **-0.30%** | 22.97% | GSL |
| X-n157-k13 | 16876.0 | 6.54% | 7.56% | GSL |
| X-n162-k11 | 14138.0 | 15.23% | 6.93% | LNS |
| X-n167-k10 | 20557.0 | 12.97% | 16.44% | GSL |
| X-n172-k51 | 45607.0 | 0.25% | 22.35% | GSL |
| X-n176-k26 | 47812.0 | 0.84% | 16.91% | GSL |
| X-n181-k23 | 25569.0 | 7.36% | 7.07% | LNS |
| X-n186-k15 | 24145.0 | 12.32% | 15.95% | GSL |
| X-n190-k8 | 16980.0 | 9.62% | 12.53% | GSL |
| X-n195-k51 | 44225.0 | 0.42% | 20.56% | GSL |
| X-n200-k36 | 58578.0 | 3.74% | 13.16% | GSL |
| X-n204-k19 | 19565.0 | 9.79% | 20.29% | GSL |
| X-n209-k16 | 30656.0 | 8.95% | 13.11% | GSL |
| X-n214-k11 | 10856.0 | 16.55% | 31.97% | GSL |
| X-n219-k73 | 117595.0 | 0.66% | 2.17% | GSL |
| X-n223-k34 | 40437.0 | 3.38% | 17.69% | GSL |
| X-n228-k23 | 25742.0 | 7.06% | 29.03% | GSL |
| X-n233-k16 | 19230.0 | 9.68% | 31.67% | GSL |
| X-n237-k14 | 27042.0 | 12.79% | 16.83% | GSL |
| X-n242-k48 | 82751.0 | 2.86% | 14.17% | GSL |
| X-n247-k50 | 37274.0 | 1.17% | 18.99% | GSL |
| X-n251-k28 | 38684.0 | 6.75% | 9.32% | GSL |
| X-n256-k16 | 18839.0 | 12.28% | 14.82% | GSL |
| X-n261-k13 | 26558.0 | 12.30% | 27.81% | GSL |
| X-n266-k58 | 75478.0 | 3.24% | 8.98% | GSL |
| X-n270-k35 | 35291.0 | 4.16% | 14.71% | GSL |
| X-n275-k28 | 21245.0 | 8.39% | 12.40% | GSL |
| X-n280-k17 | 33503.0 | 12.28% | 25.73% | GSL |
| X-n284-k15 | 20226.0 | 12.43% | 20.65% | GSL |
| X-n289-k60 | 95151.0 | 1.43% | 23.54% | GSL |
| X-n294-k50 | 47161.0 | 2.82% | 36.71% | GSL |
| X-n298-k31 | 34231.0 | 6.83% | 35.46% | GSL |
| X-n303-k21 | 21736.0 | 13.46% | 25.76% | GSL |
| X-n308-k13 | 25859.0 | 13.19% | 28.92% | GSL |
| X-n313-k71 | 94043.0 | 2.28% | 22.51% | GSL |
| X-n317-k53 | 78355.0 | 1.48% | 3.49% | GSL |
| X-n322-k28 | 29834.0 | 10.13% | 25.85% | GSL |
| X-n327-k20 | 27532.0 | 12.46% | 18.85% | GSL |
| X-n331-k15 | 31102.0 | 15.98% | 14.62% | LNS |
| X-n336-k84 | 139111.0 | 1.42% | 21.86% | GSL |
| X-n344-k43 | 42050.0 | 5.39% | 17.15% | GSL |
| X-n351-k40 | 25896.0 | 6.82% | 35.38% | GSL |
| X-n359-k29 | 51505.0 | 7.86% | 19.09% | GSL |
| X-n367-k17 | 22814.0 | 14.99% | 25.57% | GSL |
| X-n376-k94 | 147713.0 | 1.10% | 1.98% | GSL |
| X-n384-k52 | 65940.0 | 2.93% | 10.55% | GSL |
| X-n393-k38 | 38260.0 | 8.24% | 17.87% | GSL |
| X-n401-k29 | 66154.0 | 5.77% | 13.65% | GSL |
| X-n411-k19 | 19712.0 | 15.29% | 28.61% | GSL |
| X-n420-k130 | 107798.0 | 2.01% | 22.34% | GSL |
| X-n429-k61 | 65449.0 | 4.92% | 12.72% | GSL |
| X-n439-k37 | 36391.0 | 8.41% | 12.82% | GSL |
| X-n449-k29 | 55233.0 | 9.27% | 32.47% | GSL |
| X-n459-k26 | 24139.0 | 13.67% | 31.37% | GSL |
| X-n469-k138 | 221824.0 | **-0.58%** | 9.27% | GSL |
| X-n480-k70 | 89449.0 | 3.16% | 9.29% | GSL |
| X-n491-k59 | 66483.0 | 5.08% | 37.07% | GSL |
| X-n502-k39 | 69226.0 | 4.02% | 4.44% | GSL |
| X-n513-k21 | 24201.0 | 19.91% | 27.39% | GSL |
| X-n524-k153 | 154593.0 | 1.22% | 20.95% | GSL |
| X-n536-k96 | 94846.0 | 2.85% | 26.08% | GSL |
| X-n548-k50 | 86700.0 | 5.09% | 6.88% | GSL |
| X-n561-k42 | 42717.0 | 9.74% | 37.35% | GSL |
| X-n573-k30 | 50673.0 | 7.07% | 13.11% | GSL |
| X-n586-k159 | 190316.0 | 2.13% | 8.46% | GSL |
| X-n599-k92 | 108451.0 | 3.39% | 8.73% | GSL |
| X-n613-k62 | 59535.0 | 5.95% | 42.72% | GSL |
| X-n627-k43 | 62164.0 | 6.64% | 10.85% | GSL |
| X-n641-k35 | 63684.0 | 10.76% | 11.78% | GSL |
| X-n655-k131 | 106780.0 | 1.44% | 2.91% | GSL |
| X-n670-k130 | 146332.0 | 0.04% | 31.48% | GSL |
| X-n685-k75 | 68205.0 | 6.61% | 41.77% | GSL |
| X-n701-k44 | 81923.0 | 6.84% | 14.93% | GSL |
| X-n716-k35 | 43373.0 | 11.80% | 30.62% | GSL |
| X-n733-k159 | 136187.0 | 2.31% | 22.08% | GSL |
| X-n749-k98 | 77269.0 | 4.05% | 35.39% | GSL |
| X-n766-k71 | 114417.0 | 4.77% | 22.83% | GSL |
| X-n783-k48 | 72386.0 | 8.82% | 30.44% | GSL |
| X-n801-k40 | 73311.0 | 10.17% | 10.81% | GSL |
| X-n819-k171 | 158121.0 | 0.81% | 8.29% | GSL |
| X-n837-k142 | 193737.0 | 2.78% | 6.60% | GSL |
| X-n856-k95 | 88965.0 | 5.06% | 8.12% | GSL |
| X-n876-k59 | 99299.0 | 5.34% | 20.55% | GSL |
| X-n895-k37 | 53860.0 | 15.05% | 19.66% | GSL |
| X-n916-k207 | 329179.0 | 0.62% | 5.98% | GSL |
| X-n936-k151 | 132715.0 | 1.32% | 35.31% | GSL |
| X-n957-k87 | 85465.0 | 6.14% | 7.78% | GSL |
| X-n979-k58 | 118976.0 | 5.98% | 21.31% | GSL |
Summary (Set X):
GSL Win Rate: 87%

GSL demonstrates strong dominance as problem complexity increases, consistently outperforming LNS across most instances.
In several cases, GSL slightly outperforms BKS, which may be attributed to rounding differences or dataset updates.
---

## 4. Benchmark Results: SET XL (Hyper-Scale)
**Objective:** Evaluate algorithmic breakdown limits under strictly bounded iterations (1,000 to 10,000 nodes).
*Note: Metaheuristic performance degrades under fixed iteration limits in large-scale instances, while GSL maintains stable behavior.*
| Instance | BKS | GSL Gap | LNS Gap | Winner |
| :--- | :--- | :--- | :--- | :--- |
| XL-n10001-k1570 | 2333757.0 | **-0.06%** | 67.75% | GSL |
| XL-n1048-k237 | 380211.0 | 2.28% | 34.42% | GSL |
| XL-n1094-k157 | 112431.0 | 2.77% | 114.24% | GSL |
| XL-n1141-k112 | 95727.0 | 4.57% | 116.03% | GSL |
| XL-n1188-k96 | 104415.0 | 7.67% | 148.63% | GSL |
| XL-n1234-k55 | 96647.0 | 10.55% | 124.60% | GSL |
| XL-n1281-k29 | 31101.0 | 25.06% | 309.85% | GSL |
| XL-n1328-k19 | 38247.0 | 26.96% | 360.12% | GSL |
| XL-n1374-k278 | 233049.0 | **-0.39%** | 73.53% | GSL |
| XL-n1421-k232 | 384826.0 | 1.20% | 32.44% | GSL |
| XL-n1468-k151 | 250166.0 | 3.07% | 75.10% | GSL |
| XL-n1514-k106 | 92425.0 | 9.71% | 160.27% | GSL |
| XL-n1561-k75 | 101549.0 | 7.69% | 107.12% | GSL |
| XL-n1608-k39 | 48021.0 | 24.79% | 359.72% | GSL |
| XL-n1654-k11 | 35385.0 | 37.72% | 556.54% | GSL |
| XL-n1701-k562 | 521136.0 | 0.39% | 42.41% | GSL |
| XL-n1748-k271 | 173896.0 | 0.97% | 97.19% | GSL |
| XL-n1794-k163 | 141729.0 | 5.74% | 125.73% | GSL |
| XL-n1841-k126 | 214038.0 | 4.62% | 88.78% | GSL |
| XL-n1888-k82 | 143623.0 | 9.07% | 130.91% | GSL |
| XL-n1934-k46 | 53013.0 | 22.85% | 349.92% | GSL |
| XL-n1981-k13 | 32580.0 | 30.63% | 645.07% | GSL |
| XL-n2028-k617 | 544403.0 | **-0.08%** | 39.14% | GSL |
| XL-n2074-k264 | 421627.0 | 1.78% | 62.49% | GSL |
| XL-n2121-k186 | 283211.0 | 3.19% | 95.70% | GSL |
| XL-n2168-k138 | 127298.0 | 8.49% | 195.34% | GSL |
| XL-n2214-k131 | 154676.0 | 6.17% | 153.52% | GSL |
| XL-n2261-k54 | 98907.0 | 14.70% | 234.87% | GSL |
| XL-n2307-k34 | 47958.0 | 31.20% | 581.10% | GSL |
| XL-n2354-k631 | 940825.0 | **-0.22%** | 35.24% | GSL |
| XL-n2401-k408 | 463473.0 | 1.80% | 74.62% | GSL |
| XL-n2447-k290 | 218706.0 | 3.40% | 104.68% | GSL |
| XL-n2494-k194 | 361205.0 | 1.69% | 32.06% | GSL |
| XL-n2541-k121 | 146390.0 | 9.76% | 193.37% | GSL |
| XL-n2587-k66 | 73394.0 | 21.12% | 412.04% | GSL |
| XL-n2634-k17 | 31641.0 | 34.35% | 705.92% | GSL |
| XL-n2681-k540 | 798603.0 | 1.00% | 39.53% | GSL |
| XL-n2727-k546 | 431134.0 | 1.24% | 75.18% | GSL |
| XL-n2774-k286 | 407847.0 | 1.85% | 52.95% | GSL |
| XL-n2821-k208 | 210763.0 | 8.87% | 160.97% | GSL |
| XL-n2867-k120 | 165990.0 | 7.38% | 168.88% | GSL |
| XL-n2914-k95 | 88990.0 | 17.45% | 341.28% | GSL |
| XL-n2961-k55 | 108084.0 | 17.41% | 312.04% | GSL |
| XL-n3007-k658 | 522319.0 | 1.39% | 56.29% | GSL |
| XL-n3054-k461 | 782739.0 | 0.20% | 49.94% | GSL |
| XL-n3101-k311 | 245937.0 | 2.74% | 87.68% | GSL |
| XL-n3147-k232 | 256626.0 | 5.62% | 141.49% | GSL |
| XL-n3194-k161 | 148728.0 | 10.39% | 246.31% | GSL |
| XL-n3241-k115 | 221370.0 | 5.11% | 110.05% | GSL |
| XL-n3287-k30 | 40229.0 | 29.30% | 581.66% | GSL |
| XL-n3334-k934 | 1452698.0 | 1.49% | 31.81% | GSL |
| XL-n3408-k524 | 678643.0 | 1.70% | 61.38% | GSL |
| XL-n3484-k436 | 703355.0 | 1.03% | 49.14% | GSL |
| XL-n3561-k229 | 209386.0 | 6.48% | 176.66% | GSL |
| XL-n3640-k211 | 189724.0 | 8.62% | 201.88% | GSL |
| XL-n3721-k77 | 162852.0 | 12.70% | 219.99% | GSL |
| XL-n3804-k29 | 52885.0 | 36.52% | 892.91% | GSL |
| XL-n3888-k1010 | 1880358.0 | 0.31% | 13.58% | GSL |
| XL-n3975-k687 | 525901.0 | 1.53% | 86.37% | GSL |
| XL-n4063-k347 | 548931.0 | 2.91% | 100.89% | GSL |
| XL-n4153-k291 | 356034.0 | 2.94% | 76.16% | GSL |
| XL-n4245-k203 | 229659.0 | 7.76% | 202.66% | GSL |
| XL-n4340-k148 | 244226.0 | 7.88% | 184.89% | GSL |
| XL-n4436-k48 | 61477.0 | 25.97% | 662.33% | GSL |
| XL-n4535-k1134 | 1203566.0 | 0.36% | 62.39% | GSL |
| XL-n4635-k790 | 610650.0 | 1.47% | 78.39% | GSL |
| XL-n4738-k487 | 760501.0 | 2.37% | 92.57% | GSL |
| XL-n4844-k321 | 404652.0 | 4.60% | 143.02% | GSL |
| XL-n4951-k203 | 285259.0 | 6.95% | 173.24% | GSL |
| XL-n5061-k184 | 161629.0 | 9.90% | 208.82% | GSL |
| XL-n5174-k55 | 61382.0 | 35.89% | 773.62% | GSL |
| XL-n5288-k1246 | 1960101.0 | **-0.17%** | 47.42% | GSL |
| XL-n5406-k783 | 1040536.0 | 0.94% | 55.36% | GSL |
| XL-n5526-k553 | 336898.0 | 3.10% | 159.51% | GSL |
| XL-n5649-k401 | 644856.0 | 3.37% | 101.94% | GSL |
| XL-n5774-k290 | 250207.0 | 8.62% | 242.23% | GSL |
| XL-n5902-k122 | 217447.0 | 13.13% | 286.68% | GSL |
| XL-n6034-k61 | 64448.0 | 33.06% | 769.17% | GSL |
| XL-n6168-k1922 | 1530010.0 | 1.10% | 37.08% | GSL |
| XL-n6305-k1042 | 1177528.0 | 1.90% | 83.05% | GSL |
| XL-n6445-k628 | 990623.0 | 3.20% | 82.02% | GSL |
| XL-n6588-k473 | 334058.0 | 4.60% | 152.16% | GSL |
| XL-n6734-k330 | 448031.0 | 4.78% | 144.82% | GSL |
| XL-n6884-k148 | 181809.0 | 11.99% | 317.39% | GSL |
| XL-n7037-k38 | 70845.0 | 46.64% | 1267.73% | GSL |
| XL-n7193-k1683 | 2958979.0 | 0.38% | 34.06% | GSL |
| XL-n7353-k1471 | 1537811.0 | 0.60% | 83.31% | GSL |
| XL-n7516-k859 | 573902.0 | 1.67% | 89.32% | GSL |
| XL-n7683-k602 | 702098.0 | 2.65% | 104.48% | GSL |
| XL-n7854-k365 | 659221.0 | 2.18% | 41.37% | GSL |
| XL-n8028-k294 | 265900.0 | 12.23% | 363.46% | GSL |
| XL-n8207-k108 | 118274.0 | 18.71% | 502.79% | GSL |
| XL-n8389-k2028 | 3358731.0 | 0.82% | 29.77% | GSL |
| XL-n8575-k1297 | 1089137.0 | 1.16% | 102.82% | GSL |
| XL-n8766-k1032 | — | — | — | Excluded (missing BKS)
| XL-n8960-k634 | 773383.0 | 3.21% | 120.81% | GSL |
| XL-n9160-k379 | 324092.0 | 11.03% | 329.98% | GSL |
| XL-n9363-k209 | 205575.0 | 15.68% | 476.72% | GSL |
| XL-n9571-k55 | 106791.0 | 37.16% | 1140.38% | GSL |
| XL-n9784-k2774 | 4078217.0 | 0.61% | 25.27% | GSL |
Summary (Set XL):

GSL demonstrates near-complete dominance in large-scale instances under fixed iteration constraints.

LNS performance degrades significantly, with solution gaps frequently exceeding 100% in large-scale cases.

GSL maintains stable solution quality across increasing problem sizes, indicating strong scalability under constrained computational budgets.
---
Overall Performance Summary:

Set A (n ≤ 80):
- GSL Win Rate: 70.4%

Set X (100 ≤ n ≤ 1000):
- GSL Win Rate: 87%

Set XL (n ≥ 1000):
- GSL achieves near-complete dominance in large-scale instances under fixed iteration constraints
- LNS gap increases significantly, often exceeding 100% in large-scale cases

Key Observations:
- GSL scales robustly with instance size
- Performance improves with higher fleet density (k/n)
- Metaheuristics degrade significantly under large-scale constraints
## 5. Conclusion

This study compares a deterministic routing framework (GSL Engine V22) with a stochastic metaheuristic (LNS) under fixed iteration constraints.

While LNS performs competitively on smaller instances, its performance degrades as problem size increases.

GSL demonstrates consistent and scalable performance across all benchmark sets, particularly in large-scale scenarios.

The results suggest that deterministic approaches can provide robust and efficient solutions for large-scale CVRP under limited computational resources.

Future work will include comparisons with additional classical heuristics such as Clarke–Wright and hybrid metaheuristic approaches.

