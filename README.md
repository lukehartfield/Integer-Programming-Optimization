
### 📍 Project Overview

We developed an advanced optimization model to allocate a **$10 million marketing budget** across 10 platforms (e.g., Facebook, LinkedIn, TV, SEO) with **tiered ROI curves**, **media mix constraints**, and **real-world feasibility rules** (minimum investments, stability, reinvestment). Using **linear and mixed-integer programming in Python (Gurobi)**, we generated robust strategies that adapt to conflicting ROI estimates from two consulting firms and analyzed long-term reinvestment and execution feasibility.

---

### 🎯 Project Goals

- Maximize marketing ROI using **tiered return structures**
- Account for **platform-specific constraints**, such as spend caps and minimum thresholds
- Compare allocations under **different ROI scenarios**
- Extend to **multi-month optimization with reinvestment and continuity controls**
- Provide actionable budget plans under **uncertainty and operational constraints**

---

### 🧮 Optimization Modeling Framework

| Modeling Stage | Approach |
| --- | --- |
| **Base Case (ROI Set 1)** | Linear Program with 40 tiered decision variables (10 platforms × 4 tiers) |
| **ROI Set 2 (non-concave)** | Mixed Integer Program to enforce tier order, binary activations, and no-skip logic |
| **Min Investment Constraint** | Platforms must receive minimum spend or zero, via binary-triggered thresholds |
| **Multi-Month Planning** | Rolling reinvestment model: budget grows based on monthly ROI × 50% reinvestment |
| **Stability Constraint (Defined)** | Limit month-to-month platform changes to ±$1M to reduce operational volatility |

---


### 💡 Strategic Insights

- ROI estimates must be accurate — wrong assumptions create **massive value loss**
- Tiered returns must be enforced with **binary logic and tier gating**
- Adding **minimum spend** constraints improves practicality without hurting results
- Reinvestment yields compounding benefits — but needs stability controls
- Without planning continuity, even optimal allocations become **impractical**

---

### 🧠 Skills Demonstrated

| Area | Techniques / Tools |
| --- | --- |
| **Optimization** | Gurobi, LP/MIP, tiered ROI modeling, piecewise convexity |
| **Modeling Constraints** | Binary activation, no-skip rules, continuity enforcement |
| **Scenario Testing** | ROI sensitivity (Set 1 vs. Set 2), mis-spec impact quantification |
| **Multi-Period Planning** | Budget growth simulation, reinvestment tracking |
| **Business Logic** | Media balance (TV vs Social), practical feasibility rules |

---
