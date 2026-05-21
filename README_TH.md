[Read English Version](README.md)

# GSL Engine
**สถาปัตยกรรมเชิงกำหนดสำหรับการแก้ปัญหา Vehicle Routing Problem (VRP)**

GSL Engine (Geo Strategy Logistic Engine) คือสถาปัตยกรรมการคำนวณแบบ proprietary ที่ออกแบบขึ้นเพื่อศึกษาวิธีการจัดเส้นทางโลจิสติกส์เชิงกำหนด (Deterministic Routing) สำหรับปัญหาการเพิ่มประสิทธิภาพด้านโลจิสติกส์ที่มีความซับซ้อนสูง

Repository นี้ทำหน้าที่เป็นศูนย์กลางด้านผลงานวิจัย การทดสอบประสิทธิภาพ และบันทึกการประมวลผลของระบบ GSL โดยครอบคลุม VRP หลายรูปแบบ รวมถึงการทดสอบบนฮาร์ดแวร์ระดับ Mobile Edge

**หมายเหตุ:** ซอร์สโค้ดหลักของระบบไม่ได้เปิดเผยสู่สาธารณะ Repository นี้เปิดสำหรับการแลกเปลี่ยนทางวิชาการ การวิจัย และการประยุกต์ใช้งานในระดับอุตสาหกรรม

---

## โครงสร้างระบบและประเภทปัญหาที่รองรับ

GSL Engine ถูกออกแบบในลักษณะ Modular Architecture เพื่อรองรับ VRP หลายประเภทภายใต้แนวคิดการประมวลผลเชิงกำหนด (Deterministic Feasibility-Oriented Execution)

- **CVRP (Capacitated VRP)** Module: `GSL_CVRP_V22`
- **VRPTW (VRP with Time Windows)** Module: `GSL_VRPTW_V111`
- **MDVRP (Multi-Depot VRP)** Module: `GSL_MDVRP_MASTER_V28`
- **MDVRPTW (Multi-Depot VRP with Time Windows)** Modules: `GSL_MDVRPTW_V38` และ `GSL_MDVRPTW_REAL_V29`
- **PDPTW (Pickup & Delivery with Time Windows)** อยู่ระหว่างการพัฒนา (Core Logic Completed)

---

## สภาพแวดล้อมการประมวลผล

- **Platform:** Android (Mobile Edge)
- **Runtime:** Python ผ่าน Pydroid 3
- **CPU:** Snapdragon Architecture (ARM-based)
- **Execution Mode:** Sequential / Batch Processing
- **Constraint Handling:** การตรวจสอบ Feasibility แบบ Deterministic โดยไม่ใช้การสุ่มเชิง stochastic

---

## Milestone 1: CVRP Benchmark (CVRPLib-Based)

**Module:** `GSL_CVRP_V22`

### Zero-Tuning Policy

ระบบใช้ Execution Configuration เดียวกันกับทุก Dataset โดยไม่มีการปรับ Parameter เฉพาะราย Instance เพื่อศึกษาพฤติกรรมการทำงานข้ามชุดข้อมูลภายใต้โครงสร้างเดียวกัน

---

### Repository การทดสอบประสิทธิภาพ

เพื่อความชัดเจนของข้อมูล Benchmark การทดสอบถูกแยกออกเป็น Repository เฉพาะทางดังนี้:

* 📁 **[GSL-CVRP-SETX](https://github.com/CT1-deMo-goG/GSL-CVRP-SETX)**  
  การทดสอบบน Uchoa Set X (100 - 1,000 Nodes)

* 📁 **[GSL-CVRP-SETXL](https://github.com/CT1-deMo-goG/GSL-CVRP-SETXL)**  
  การทดสอบ Hyper-Scale (1,000 - 10,001 Nodes)

---

### ตัวอย่างการทดสอบ Hyper-Scale (Set XL)

ระบบสามารถสร้างคำตอบที่ผ่านเงื่อนไข Feasibility สำหรับโจทย์ขนาดใหญ่บนฮาร์ดแวร์ระดับ Mobile ได้

| Instance | GSL Cost | Recorded BKS | Gap (%) | Status |
| :--- | :--- | :--- | :--- | :--- |
| XL-n5406-k783 | 1,050,660.38 | 1,040,536.0 | +0.97% | FEASIBLE |
| XL-n10001-k1570 | 2,432,382.86 | 2,333,757.0 | +4.23% | FEASIBLE |

---

### สรุปการครอบคลุม Dataset

| Dataset | จำนวน Instance | Avg. Gap to BKS | Avg. Runtime |
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

ระบบถูกทดสอบบนชุดข้อมูล Solomon และ Homberger ภายใต้แนวทาง Zero-Tuning เดียวกัน โดยผลลัพธ์ที่รายงานผ่านการตรวจสอบ Capacity และ Time Window Feasibility ตามเงื่อนไขของโจทย์

🔗 **[View VRPTW Benchmark Portfolio & Logs](https://github.com/CT1-demo-goG/GSL-VRPTW-Portfolio)**

---

## Milestone 3: MDVRP Benchmark

**Module:** `GSL_MDVRP_MASTER_V28`

- ทดสอบบนโจทย์ MDVRP ขนาดใหญ่ รวมถึงกรณี 10,000 Nodes / 100 Depots บน Mobile Hardware
- สร้างคำตอบที่ผ่าน Feasibility แบบ Deterministic บนชุดข้อมูล Cordeau p-series และ pr-series

🔗 **[View MDVRP Benchmark Portfolio & Logs](https://github.com/CT1-demo-goG/gsl-mdvrp-engine)**

---

## Milestone 4: MDVRPTW Benchmark

**Modules:** `GSL_MDVRPTW_V38` และ `GSL_MDVRPTW_REAL_V29`

- ทดสอบบนชุดข้อมูลจริงที่มี Multi-Depot, Time Windows, Asymmetric Distance และ Dual-Capacity Constraints
- การทดสอบภายในพบแนวโน้มการลดต้นทุนเส้นทางภายใต้การประมวลผลเชิงกำหนด
- มีการประเมินเพิ่มเติมบนชุดข้อมูล Vidal (สูงสุด 960 Nodes)

🔗 **[View MDVRPTW Benchmark Portfolio & Logs](https://github.com/CT1-demo-goG/gsl-mdvrptw-engine)**

---

## Research & Architecture Notes

### Deterministic Single-Pass Routing Architecture

Repository นี้ยังรวมเอกสารเชิงสำรวจ (Exploratory Technical Notes) เกี่ยวกับ:

- deterministic routing execution
- low-latency dispatch systems
- edge-constrained VRP computation
- variance-free execution behavior
- mobile-scale logistics optimization

📄 `Docs/deterministic_single_pass_whitepaper.md`

---

## Technical Strategy

- **Geometric Sensing:** การจัดกลุ่มเชิงพื้นที่และการเริ่มต้นเส้นทางแบบ Deterministic
- **Adaptive Fleet Structuring:** การกระจายภาระงานและจัดความหนาแน่นของ Capacity แบบ Dynamic
- **Universal Parsing Core:** ระบบอ่าน Dataset หลายรูปแบบพร้อมการตรวจจับโครงสร้างอัตโนมัติ

---

## ขอบเขตปัญหาและรายละเอียด Benchmark

แกนการคำนวณหลักของ GSL Engine ถูกออกแบบสำหรับปัญหา **Capacitated Vehicle Routing Problem (CVRP)** ภายใต้แนวทางการประมวลผลเชิงกำหนด

เป้าหมายหลักของระบบประกอบด้วย:
- การใช้ความจุรถให้เกิดประสิทธิภาพสูงสุด
- การรักษา Feasibility ของเส้นทาง
- การลดระยะทางรวมของระบบขนส่ง

### หมายเหตุเกี่ยวกับ Legacy Benchmarks (เช่น CMT Series)

Benchmark บางชุด เช่น Christofides / CMT มีข้อจำกัดเพิ่มเติมแฝงอยู่ เช่น Route Distance Ceiling

ผลลัพธ์บางส่วนใน Repository นี้จึงสะท้อนการประเมินภายใต้เงื่อนไข Capacity-Constrained เป็นหลัก เว้นแต่จะระบุเพิ่มเติมไว้โดยเฉพาะ

ปัญหาที่ต้องควบคุมข้อจำกัดด้านเวลาและระยะทางอย่างเข้มงวด จะถูกแยกไปประเมินในระบบเฉพาะทาง เช่น:
- VRPTW
- MDVRPTW

เพื่อรักษาความเป็น Modular และประสิทธิภาพการประมวลผลของแต่ละระบบ

---

## GSL-Solver Platform

**Deterministic Routing Platform**

เข้าถึงแพลตฟอร์มได้ที่:

https://gsl-solver.com

---

## Professional Contact

**Independent Researcher:** Chonmapoohm Thamsuwan (CTSuwan)  
📧 ctsuwan@proton.me
