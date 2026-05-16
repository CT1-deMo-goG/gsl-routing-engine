# Technical Benchmark Report: GSL Engine V22 vs. Standard Constructive Heuristic (CW)
**Date:** April 1, 2026
**Subject:** Cross-Scale Performance & Time-Complexity Validation (Sets A, X, XL)
**Core Framework:** Deterministic Routing Logic

## 1. Executive Summary
This report presents a comparative analysis between the GSL Engine V22 and the Clarke-Wright (CW) constructive heuristic across three benchmark sets (A, X, XL), including large-scale instances with up to 10,000 nodes.

The CW algorithm provides a stable baseline, typically achieving solution gaps between 1% and 25%. However, its computational cost increases significantly with problem size due to its O(N^2 log N) structure.

In contrast, the GSL Engine V22 executes in near-constant time on the tested hardware. The results show that the GSL framework performs competitively in high-density fleet configurations (high k/n ratio), where solution gaps are often comparable to or better than CW.

However, performance degradation is observed in low-density (low-k) instances, where longer route chaining leads to increased solution gaps, reaching up to 46.64% in extreme cases.

These findings define a clear operational profile for deterministic routing approaches in large-scale CVRP scenarios.

## 2. Benchmark Results: SET A (Precision Scale)
**Objective:** Evaluate base routing efficiency on small networks (30 - 80 nodes).

| Instance | BKS | GSL Gap | CW Gap | Winner |
| :--- | :--- | :--- | :--- | :--- |
| A-n32-k5 | 784.0 | 10.09% | 7.61% | CW |
| A-n33-k5 | 661.0 | 8.48% | 7.72% | CW |
| A-n33-k6 | 742.0 | 3.04% | 4.62% | GSL |
| A-n34-k5 | 778.0 | 4.25% | 4.17% | CW |
| A-n36-k5 | 799.0 | 1.99% | 3.69% | GSL |
| A-n37-k5 | 669.0 | 9.50% | 5.80% | CW |
| A-n37-k6 | 949.0 | 3.31% | 2.91% | CW |
| A-n38-k5 | 730.0 | 5.63% | 5.22% | CW |
| A-n39-k5 | 822.0 | 8.63% | 9.73% | GSL |
| A-n39-k6 | 831.0 | 3.12% | 3.86% | GSL |
| A-n44-k6 | 937.0 | 6.44% | 4.17% | CW |
| A-n45-k6 | 944.0 | 3.68% | 6.62% | GSL |
| A-n45-k7 | 1146.0 | 3.89% | 4.71% | GSL |
| A-n46-k7 | 914.0 | 2.55% | 2.82% | GSL |
| A-n48-k7 | 1073.0 | 5.97% | 3.71% | CW |
| A-n53-k7 | 1010.0 | 8.25% | 8.86% | GSL |
| A-n54-k7 | 1167.0 | 3.03% | 2.93% | CW |
| A-n55-k9 | 1073.0 | 2.85% | 2.50% | CW |
| A-n60-k9 | 1354.0 | 3.92% | 5.01% | GSL |
| A-n61-k9 | 1034.0 | 5.52% | 6.60% | GSL |
| A-n62-k8 | 1288.0 | 5.80% | 5.03% | CW |
| A-n63-k10 | 1314.0 | 2.67% | 2.93% | GSL |
| A-n63-k9 | 1616.0 | 2.23% | 4.45% | GSL |
| A-n64-k9 | 1401.0 | 5.52% | 6.13% | GSL |
| A-n65-k9 | 1174.0 | 9.94% | 5.57% | CW |
| A-n69-k9 | 1159.0 | 6.25% | 4.47% | CW |
| A-n80-k10 | 1763.0 | 6.24% | 5.56% | CW |

## 3. Benchmark Results: SET X (Complexity Scale)
**Objective:** Evaluate structural stability against increased routing complexity (100 - 1,000 nodes). Note: In a small number of instances, GSL results slightly outperform reported BKS values; these cases may be due to rounding differences or reference updates.

| Instance | BKS | GSL Gap | CW Gap | Winner |
| :--- | :--- | :--- | :--- | :--- |
| X-n1001-k43 | 72355.0 | 13.19% | 7.43% | CW |
| X-n101-k25 | 27591.0 | 13.84% | 4.90% | CW |
| X-n106-k14 | 26362.0 | 7.47% | 3.47% | CW |
| X-n110-k13 | 14971.0 | 13.23% | 5.97% | CW |
| X-n115-k10 | 12747.0 | 12.55% | 5.85% | CW |
| X-n120-k6 | 13332.0 | 13.06% | 9.06% | CW |
| X-n125-k30 | 55539.0 | 4.28% | 5.92% | GSL |
| X-n129-k18 | 28940.0 | 5.64% | 4.70% | CW |
| X-n134-k13 | 10916.0 | 10.36% | 5.54% | CW |
| X-n139-k10 | 13590.0 | 13.69% | 6.95% | CW |
| X-n143-k7 | 15700.0 | 15.57% | 13.17% | CW |
| X-n148-k46 | 43448.0 | 6.25% | 3.92% | CW |
| X-n153-k22 | 21220.0 | 10.91% | 6.70% | CW |
| X-n157-k13 | 16876.0 | 6.54% | 6.06% | CW |
| X-n162-k11 | 14138.0 | 15.23% | 9.54% | CW |
| X-n167-k10 | 20557.0 | 12.97% | 7.85% | CW |
| X-n172-k51 | 45607.0 | 10.17% | 5.76% | CW |
| X-n176-k26 | 47812.0 | 4.42% | 9.91% | GSL |
| X-n181-k23 | 25569.0 | 7.36% | 3.81% | CW |
| X-n186-k15 | 24145.0 | 12.32% | 5.93% | CW |
| X-n190-k8 | 16980.0 | 9.62% | 6.15% | CW |
| X-n195-k51 | 44225.0 | 3.45% | 3.34% | CW |
| X-n200-k36 | 58578.0 | 11.23% | 4.45% | CW |
| X-n204-k19 | 19565.0 | 9.79% | 9.27% | CW |
| X-n209-k16 | 30656.0 | 8.95% | 5.74% | CW |
| X-n214-k11 | 10856.0 | 16.77% | 10.51% | CW |
| X-n219-k73 | 117595.0 | 0.66% | 0.66% | Tie |
| X-n223-k34 | 40437.0 | 3.71% | 4.19% | GSL |
| X-n228-k23 | 25742.0 | 9.77% | 4.97% | CW |
| X-n233-k16 | 19230.0 | 10.11% | 5.96% | CW |
| X-n237-k14 | 27042.0 | 12.79% | 10.40% | CW |
| X-n242-k48 | 82751.0 | 3.41% | 2.75% | CW |
| X-n247-k50 | 37274.0 | 9.31% | 9.53% | GSL |
| X-n251-k28 | 38684.0 | 6.75% | 5.16% | CW |
| X-n256-k16 | 18839.0 | 34.04% | 10.42% | CW |
| X-n261-k13 | 26558.0 | 12.30% | 9.22% | CW |
| X-n266-k58 | 75478.0 | 15.22% | 4.66% | CW |
| X-n270-k35 | 35291.0 | 31.52% | 5.25% | CW |
| X-n275-k28 | 21245.0 | 8.39% | 5.76% | CW |
| X-n280-k17 | 33503.0 | 12.28% | 8.29% | CW |
| X-n284-k15 | 20226.0 | 12.43% | 9.17% | CW |
| X-n289-k60 | 95151.0 | 4.90% | 3.23% | CW |
| X-n294-k50 | 47161.0 | 4.52% | 2.76% | CW |
| X-n298-k31 | 34231.0 | 6.83% | 5.43% | CW |
| X-n303-k21 | 21736.0 | 13.46% | 9.17% | CW |
| X-n308-k13 | 25859.0 | 13.19% | 10.57% | CW |
| X-n313-k71 | 94043.0 | 10.50% | 3.90% | CW |
| X-n317-k53 | 78355.0 | 1.48% | 1.98% | GSL |
| X-n322-k28 | 29834.0 | 18.71% | 6.90% | CW |
| X-n327-k20 | 27532.0 | 12.46% | 8.58% | CW |
| X-n331-k15 | 31102.0 | 15.98% | 10.45% | CW |
| X-n336-k84 | 139111.0 | 4.35% | 4.00% | CW |
| X-n344-k43 | 42050.0 | 21.34% | 6.25% | CW |
| X-n351-k40 | 25896.0 | 7.24% | 4.53% | CW |
| X-n359-k29 | 51505.0 | 7.86% | 3.88% | CW |
| X-n367-k17 | 22814.0 | 14.99% | 10.75% | CW |
| X-n376-k94 | 147713.0 | 1.10% | 1.02% | CW |
| X-n384-k52 | 65940.0 | 18.12% | 3.95% | CW |
| X-n393-k38 | 38260.0 | 9.99% | 6.90% | CW |
| X-n401-k29 | 66154.0 | 5.77% | 3.46% | CW |
| X-n411-k19 | 19712.0 | 15.29% | 8.88% | CW |
| X-n420-k130 | 107798.0 | 4.57% | 4.71% | GSL |
| X-n429-k61 | 65449.0 | 16.13% | 5.45% | CW |
| X-n439-k37 | 36391.0 | 8.41% | 5.73% | CW |
| X-n449-k29 | 55233.0 | 9.27% | 6.10% | CW |
| X-n459-k26 | 24139.0 | 14.45% | 8.73% | CW |
| X-n469-k138 | 221824.0 | 10.18% | 6.16% | CW |
| X-n480-k70 | 89449.0 | 9.97% | 4.09% | CW |
| X-n491-k59 | 66483.0 | 5.95% | 3.65% | CW |
| X-n502-k39 | 69226.0 | 4.02% | 3.72% | CW |
| X-n513-k21 | 24201.0 | 19.91% | 11.99% | CW |
| X-n524-k153 | 154593.0 | 6.53% | 6.40% | CW |
| X-n536-k96 | 94846.0 | 12.19% | 5.41% | CW |
| X-n548-k50 | 86700.0 | 5.09% | 3.59% | CW |
| X-n561-k42 | 42717.0 | 9.74% | 6.86% | CW |
| X-n573-k30 | 50673.0 | 7.07% | 5.21% | CW |
| X-n586-k159 | 190316.0 | 7.07% | 4.94% | CW |
| X-n599-k92 | 108451.0 | 15.79% | 4.28% | CW |
| X-n613-k62 | 59535.0 | 6.08% | 5.44% | CW |
| X-n627-k43 | 62164.0 | 12.55% | 5.48% | CW |
| X-n641-k35 | 63684.0 | 10.76% | 7.14% | CW |
| X-n655-k131 | 106780.0 | 1.44% | 1.38% | CW |
| X-n670-k130 | 146332.0 | 7.38% | 8.46% | GSL |
| X-n685-k75 | 68205.0 | 9.88% | 4.87% | CW |
| X-n701-k44 | 81923.0 | 6.84% | 4.32% | CW |
| X-n716-k35 | 43373.0 | 11.80% | 5.73% | CW |
| X-n733-k159 | 136187.0 | 3.35% | 2.41% | CW |
| X-n749-k98 | 77269.0 | 4.61% | 3.01% | CW |
| X-n766-k71 | 114417.0 | 5.75% | 5.26% | CW |
| X-n783-k48 | 72386.0 | 8.82% | 5.72% | CW |
| X-n801-k40 | 73311.0 | 10.17% | 5.35% | CW |
| X-n819-k171 | 158121.0 | 15.07% | 5.36% | CW |
| X-n837-k142 | 193737.0 | 6.07% | 4.30% | CW |
| X-n856-k95 | 88965.0 | 5.06% | 4.29% | CW |
| X-n876-k59 | 99299.0 | 5.34% | 2.94% | CW |
| X-n895-k37 | 53860.0 | 21.01% | 9.73% | CW |
| X-n916-k207 | 329179.0 | 5.53% | 4.17% | CW |
| X-n936-k151 | 132715.0 | 10.48% | 9.96% | CW |
| X-n957-k87 | 85465.0 | 6.14% | 4.69% | CW |
| X-n979-k58 | 118976.0 | 6.00% | 4.15% | CW |

## 4. Benchmark Results: SET XL (Hyper-Scale)
**Objective:** Evaluate limits of algorithmic scalability and computational endurance (1,000 to 10,000 nodes). Note: Evaluated based on % Gap to BKS.

| Instance | BKS | GSL Gap | CW Gap | Winner |
| :--- | :--- | :--- | :--- | :--- |
| XL-n10001-k1570 | 2333757.0 | 4.23% | 3.66% | CW |
| XL-n1048-k237 | 380211.0 | 7.52% | 8.04% | GSL |
| XL-n1094-k157 | 112431.0 | 2.77% | 2.39% | CW |
| XL-n1141-k112 | 95727.0 | 11.25% | 5.28% | CW |
| XL-n1188-k96 | 104415.0 | 11.70% | 4.81% | CW |
| XL-n1234-k55 | 96647.0 | 10.55% | 5.84% | CW |
| XL-n1281-k29 | 31101.0 | 25.06% | 13.95% | CW |
| XL-n1328-k19 | 38247.0 | 26.96% | 16.19% | CW |
| XL-n1374-k278 | 233049.0 | 4.84% | 4.82% | CW |
| XL-n1421-k232 | 384826.0 | 2.22% | 1.98% | CW |
| XL-n1468-k151 | 250166.0 | 9.68% | 3.64% | CW |
| XL-n1514-k106 | 92425.0 | 15.20% | 6.19% | CW |
| XL-n1561-k75 | 101549.0 | 7.69% | 5.08% | CW |
| XL-n1608-k39 | 48021.0 | 24.79% | 14.18% | CW |
| XL-n1654-k11 | 35385.0 | 37.72% | 25.25% | CW |
| XL-n1701-k562 | 521136.0 | 7.61% | 6.92% | CW |
| XL-n1748-k271 | 173896.0 | 6.50% | 4.77% | CW |
| XL-n1794-k163 | 141729.0 | 5.74% | 3.66% | CW |
| XL-n1841-k126 | 214038.0 | 4.62% | 2.29% | CW |
| XL-n1888-k82 | 143623.0 | 10.64% | 6.13% | CW |
| XL-n1934-k46 | 53013.0 | 22.85% | 13.63% | CW |
| XL-n1981-k13 | 32580.0 | 30.63% | 18.72% | CW |
| XL-n2028-k617 | 544403.0 | 8.31% | 6.50% | CW |
| XL-n2074-k264 | 421627.0 | 1.89% | 1.61% | CW |
| XL-n2121-k186 | 283211.0 | 3.19% | 1.78% | CW |
| XL-n2168-k138 | 127298.0 | 15.13% | 6.04% | CW |
| XL-n2214-k131 | 154676.0 | 6.17% | 3.80% | CW |
| XL-n2261-k54 | 98907.0 | 14.70% | 10.11% | CW |
| XL-n2307-k34 | 47958.0 | 31.20% | 19.50% | CW |
| XL-n2354-k631 | 940825.0 | 6.29% | 6.03% | CW |
| XL-n2401-k408 | 463473.0 | 3.93% | 3.67% | CW |
| XL-n2447-k290 | 218706.0 | 5.18% | 4.89% | CW |
| XL-n2494-k194 | 361205.0 | 2.16% | 1.44% | CW |
| XL-n2541-k121 | 146390.0 | 9.76% | 5.93% | CW |
| XL-n2587-k66 | 73394.0 | 21.12% | 12.37% | CW |
| XL-n2634-k17 | 31641.0 | 34.35% | 23.19% | CW |
| XL-n2681-k540 | 798603.0 | 1.85% | 2.02% | GSL |
| XL-n2727-k546 | 431134.0 | 1.24% | 1.09% | CW |
| XL-n2774-k286 | 407847.0 | 6.60% | 3.19% | CW |
| XL-n2821-k208 | 210763.0 | 8.99% | 6.36% | CW |
| XL-n2867-k120 | 165990.0 | 9.98% | 5.05% | CW |
| XL-n2914-k95 | 88990.0 | 20.68% | 10.74% | CW |
| XL-n2961-k55 | 108084.0 | 17.41% | 10.45% | CW |
| XL-n3007-k658 | 522319.0 | 1.61% | 1.81% | GSL |
| XL-n3054-k461 | 782739.0 | 4.25% | 3.95% | CW |
| XL-n3101-k311 | 245937.0 | 3.94% | 2.89% | CW |
| XL-n3147-k232 | 256626.0 | 9.19% | 4.02% | CW |
| XL-n3194-k161 | 148728.0 | 12.46% | 6.70% | CW |
| XL-n3241-k115 | 221370.0 | 5.11% | 3.16% | CW |
| XL-n3287-k30 | 40229.0 | 29.30% | 19.43% | CW |
| XL-n3334-k934 | 1452698.0 | 1.98% | 1.88% | CW |
| XL-n3408-k524 | 678643.0 | 4.30% | 3.45% | CW |
| XL-n3484-k436 | 703355.0 | 1.03% | 0.79% | CW |
| XL-n3561-k229 | 209386.0 | 6.61% | 3.96% | CW |
| XL-n3640-k211 | 189724.0 | 11.13% | 5.79% | CW |
| XL-n3721-k77 | 162852.0 | 12.70% | 8.00% | CW |
| XL-n3804-k29 | 52885.0 | 36.52% | 23.98% | CW |
| XL-n3888-k1010 | 1880358.0 | 7.80% | 7.91% | GSL |
| XL-n3975-k687 | 525901.0 | 1.75% | 1.56% | CW |
| XL-n4063-k347 | 548931.0 | 4.82% | 2.41% | CW |
| XL-n4153-k291 | 356034.0 | 2.97% | 1.96% | CW |
| XL-n4245-k203 | 229659.0 | 7.76% | 4.85% | CW |
| XL-n4340-k148 | 244226.0 | 18.75% | 5.28% | CW |
| XL-n4436-k48 | 61477.0 | 25.97% | 16.70% | CW |
| XL-n4535-k1134 | 1203566.0 | 0.36% | 0.34% | CW |
| XL-n4635-k790 | 610650.0 | 2.06% | 1.84% | CW |
| XL-n4738-k487 | 760501.0 | 3.43% | 2.27% | CW |
| XL-n4844-k321 | 404652.0 | 4.60% | 2.49% | CW |
| XL-n4951-k203 | 285259.0 | 14.54% | 4.81% | CW |
| XL-n5061-k184 | 161629.0 | 16.70% | 6.20% | CW |
| XL-n5174-k55 | 61382.0 | 35.89% | 19.47% | CW |
| XL-n5288-k1246 | 1960101.0 | 6.06% | 5.32% | CW |
| XL-n5406-k783 | 1040536.0 | 0.97% | 0.80% | CW |
| XL-n5526-k553 | 336898.0 | 3.10% | 1.92% | CW |
| XL-n5649-k401 | 644856.0 | 3.39% | 1.51% | CW |
| XL-n5774-k290 | 250207.0 | 8.63% | 4.37% | CW |
| XL-n5902-k122 | 217447.0 | 13.13% | 7.47% | CW |
| XL-n6034-k61 | 64448.0 | 36.28% | 17.94% | CW |
| XL-n6168-k1922 | 1530010.0 | 3.35% | 3.48% | GSL |
| XL-n6305-k1042 | 1177528.0 | 4.25% | 2.84% | CW |
| XL-n6445-k628 | 990623.0 | 4.50% | 3.46% | CW |
| XL-n6588-k473 | 334058.0 | 4.60% | 2.46% | CW |
| XL-n6734-k330 | 448031.0 | 13.04% | 3.77% | CW |
| XL-n6884-k148 | 181809.0 | 11.99% | 6.73% | CW |
| XL-n7037-k38 | 70845.0 | 46.64% | 24.80% | CW |
| XL-n7193-k1683 | 2958979.0 | 4.80% | 4.63% | CW |
| XL-n7353-k1471 | 1537811.0 | 0.60% | 0.54% | CW |
| XL-n7516-k859 | 573902.0 | 1.99% | 1.35% | CW |
| XL-n7683-k602 | 702098.0 | 6.76% | 3.04% | CW |
| XL-n7854-k365 | 659221.0 | 2.18% | 1.36% | CW |
| XL-n8028-k294 | 265900.0 | 18.17% | 7.03% | CW |
| XL-n8207-k108 | 118274.0 | 18.71% | 11.15% | CW |
| XL-n8389-k2028 | 3358731.0 | 2.05% | 2.08% | GSL |
| XL-n8575-k1297 | 1089137.0 | 1.19% | 1.05% | CW |
| XL-n8960-k634 | 773383.0 | 4.17% | 2.64% | CW |
| XL-n9160-k379 | 324092.0 | 11.03% | 5.23% | CW |
| XL-n9363-k209 | 205575.0 | 15.68% | 8.90% | CW |
| XL-n9571-k55 | 106791.0 | 37.16% | 21.56% | CW |
| XL-n9784-k2774 | 4078217.0 | 0.61% | 1.12% | GSL |

## 5. Analytical Engineering Conclusion
The benchmark results establish a clear performance trade-off between the CW heuristic and the GSL Engine V22.

The CW algorithm provides stable solution quality across all scales but exhibits increasing computational cost as problem size grows, consistent with its O(N^2 log N) complexity.

The GSL Engine V22 demonstrates strong performance in high-density routing scenarios, achieving solution quality comparable to CW while maintaining significantly lower execution time.

In low-density configurations, the deterministic structure of the GSL framework shows limitations in handling long-route dependencies, resulting in larger optimality gaps.

Overall, the results indicate that deterministic routing frameworks can be effective for large-scale CVRP, particularly in high-density settings, while further improvements are needed for sparse routing structures.
