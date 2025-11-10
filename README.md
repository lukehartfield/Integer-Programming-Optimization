---

*Optimization I – MSBA | McCombs School of Business, UT Austin*

---

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

### 📈 Key Results

### ✅ Linear Program (ROI Set 1)

- Optimal ROI: **$543,640**
- Heavy allocation to **Email, Facebook, Instagram**, and **TV**
- Satisfies constraints like:
    - TV + Print ≤ Facebook + Email
    - Social ≥ 2 × (SEO + AdWords)
    - Per-platform max = $3M

### ⚠️ MIP with ROI Set 2

- Optimal ROI: **$452,827**
- Allocation shifts to **AdWords**, **Facebook**, **LinkedIn**, and **Print**
- If mismatched with true ROI, can result in a **$415K loss** → shows the cost of **model mis-specification**

### ✅ With Minimum Spend Constraints

- Solution unchanged: key channels were already above minimum thresholds
- ROI improved to **$495K** due to avoidance of inefficient fractional investments

---

### 🔁 Multi-Month Reinvestment Model

- Starting Budget: $10M
- 50% of monthly return reinvested
- Ending Budget (December): **$13.2M**
- Per-month ROI stable; compounding effect leads to sustainable growth

> Enforced:
> 
> - Platform-level caps
> - ROI tier structure
> - Social/Traditional balance constraints
> - Minimum activation threshold rules

---

### 📉 Stability Analysis (Operational Feasibility)

Defined "stable" as:

> No platform may change monthly allocation by more than ±$1M
> 

Example Instabilities

---

AdWords: +$2.55M (Jan → Feb)

---

Facebook: +$3M (May → June)

---

SEO: +$3M (Aug → Sep)

---

Twitter: 2–3M shifts multiple times

---

> 🔴 Result: The unconstrained solution is not stable
> 
> 
> → Real-world execution would suffer from planning, vendor, and delivery lags
> 

> ✅ Proposed fix: Add a continuity constraint across months in the MIP
> 
> 
> `|x[p, m] - x[p, m-1]| ≤ 1`
> 
> Ensures realistic month-over-month shifts
> 

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
