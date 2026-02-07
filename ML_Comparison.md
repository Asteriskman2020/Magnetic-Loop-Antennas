# Magnetic Loop Antenna Design Comparison

## All Four Designs — Side by Side

All designs use **3/8" (9.525 mm) OD soft copper tube** for both the main
radiator and coupling loop.

---

## 1. Design Overview

| | **ML160-6** | **ML80-6** | **ML30-6** | **ML30-6 Small A** | **ML30-6 Small B** |
|---|---|---|---|---|---|
| **File** | ML160_6.md | ML80_6.md | ML30_6.md | ML30_6_Small.md | ML30_6_Small.md |
| **Coverage** | 160 m – 6 m | 80 m – 6 m | 30 m – 6 m | 30 m – 6 m | 30 m – 6 m |
| **Freq range** | 1.8 – 54 MHz | 3.5 – 54 MHz | 10.1 – 54 MHz | 10.1 – 54 MHz | 10.1 – 54 MHz |
| **Freq ratio** | 30 : 1 | 15 : 1 | 5.3 : 1 | 5.3 : 1 | 5.3 : 1 |
| **Optimised for** | Max coverage | Coverage | Efficiency | Min size | Size + efficiency |
| **Max power** | 100 W | 100 W | 10 W | 10 W | 10 W |
| **Number of loops** | 3 | 2 | 3 | 1 | 2 (concentric) |
| **Largest loop** | 2.00 m (6.6 ft) | 1.00 m (3.3 ft) | 1.60 m (5.2 ft) | 0.44 m (17") | 0.60 m (24") |
| **Smallest loop** | 0.40 m (16") | 0.40 m (16") | 0.44 m (17") | 0.44 m (17") | 0.44 m (17") |

---

## 2. Loop Inventory

### ML160-6 — Three Loops

| Loop | Diameter | Bands | Coupling |
|------|----------|-------|----------|
| A | 2.00 m | 160 m, 80 m, 60 m, 40 m, 30 m | 400 mm (1:5) |
| B | 1.00 m | 20 m, 17 m, 15 m | 200 mm (1:5) |
| C | 0.40 m | 12 m, 10 m, 6 m | 100 mm (1:4) |

### ML80-6 — Two Loops

| Loop | Diameter | Bands | Coupling |
|------|----------|-------|----------|
| A | 1.00 m | 80 m, 60 m, 40 m, 30 m, 20 m, 17 m, 15 m | 200 mm (1:5) |
| B | 0.40 m | 12 m, 10 m, 6 m | 100 mm (1:4) |

### ML30-6 (Efficiency) — Three Loops

| Loop | Diameter | Bands | Coupling |
|------|----------|-------|----------|
| A | 1.60 m | 30 m, 20 m | 320 mm (1:5) |
| B | 0.85 m | 17 m, 15 m, 12 m, 10 m | 170 mm (1:5) |
| C | 0.44 m | 6 m | 110 mm (1:4) |

### ML30-6 Small A — Single Loop

| Loop | Diameter | Bands | Coupling |
|------|----------|-------|----------|
| — | 0.44 m | 30 m – 6 m (all) | 100 mm (1:4.4) |

### ML30-6 Small B — Concentric Dual

| Loop | Diameter | Bands | Coupling |
|------|----------|-------|----------|
| Outer | 0.60 m | 30 m, 20 m, 17 m, 15 m, 12 m, 10 m | 120 mm (1:5) shared |
| Inner | 0.44 m | 6 m | (shared with outer) |

---

## 3. Band-by-Band Efficiency Comparison

The central table. Each cell shows **efficiency (%)** and **(dB loss)**.
Blank cells = band not covered by that design.

| Band | Freq | **ML160-6** | **ML80-6** | **ML30-6** | **Small A** | **Small B** |
|------|------|------------|-----------|-----------|------------|------------|
| 160 m | 1.85 MHz | 0.6 % (−22.3) | | | | |
| 80 m | 3.55 MHz | 5.5 % (−12.6) | 0.7 % (−21.4) | | | |
| 60 m | 5.35 MHz | 20 % (−7.1) | 3.0 % (−15.3) | | | |
| 40 m | 7.10 MHz | 40 % (−4.0) | 7.6 % (−11.2) | | | |
| **30 m** | 10.1 MHz | 69 % (−1.6) | 22 % (−6.5) | **54 % (−2.7)** | 2.4 % (−16.2) | 5.8 % (−12.4) |
| **20 m** | 14.2 MHz | 48 % (−3.2) | 48 % (−3.2) | **79 % (−1.0)** | 7.4 % (−11.3) | 17 % (−7.8) |
| **17 m** | 18.1 MHz | 69 % (−1.6) | 69 % (−1.6) | **57 % (−2.4)** | 16 % (−8.0) | 32 % (−4.9) |
| **15 m** | 21.2 MHz | 79 % (−1.0) | 79 % (−1.0) | **70 % (−1.5)** | 25 % (−6.1) | 45 % (−3.4) |
| **12 m** | 24.9 MHz | 30 % (−5.2) | 30 % (−5.2) | **81 % (−0.9)** | 36 % (−4.4) | 59 % (−2.3) |
| **10 m** | 28.5 MHz | 41 % (−3.9) | 41 % (−3.9) | **87 % (−0.6)** | 48 % (−3.2) | 70 % (−1.6) |
| **6 m** | 50.1 MHz | 83 % (−0.8) | 83 % (−0.8) | **87 % (−0.6)** | 87 % (−0.6) | 87 % (−0.6) |

### Best Design Per Band

| Band | Best Design | η | Runner-up | η |
|------|------------|---|-----------|---|
| 160 m | ML160-6 (only option) | 0.6 % | — | — |
| 80 m | ML160-6 | 5.5 % | ML80-6 | 0.7 % |
| 60 m | ML160-6 | 20 % | ML80-6 | 3.0 % |
| 40 m | ML160-6 | 40 % | ML80-6 | 7.6 % |
| 30 m | ML160-6 | 69 % | **ML30-6** | 54 % |
| 20 m | **ML30-6** | 79 % | ML160-6 / ML80-6 | 48 % |
| 17 m | ML160-6 / ML80-6 | 69 % | **ML30-6** | 57 % |
| 15 m | ML160-6 / ML80-6 | 79 % | **ML30-6** | 70 % |
| 12 m | **ML30-6** | 81 % | Small B | 59 % |
| 10 m | **ML30-6** | 87 % | Small B | 70 % |
| 6 m | ML30-6 / Small A / Small B | 87 % | ML160-6 / ML80-6 | 83 % |

> **Key insight:** ML160-6 and ML80-6 share the same 1.0 m and 0.4 m loops,
> so they are identical on 20 m – 6 m. The ML160-6 is simply ML80-6 with an
> additional 2.0 m loop added for 160 m – 40 m. The efficiency-optimised
> ML30-6 dominates on 12 m, 10 m, and 20 m due to its per-band loop sizing.

---

## 4. Physical and Practical Comparison

| Attribute | **ML160-6** | **ML80-6** | **ML30-6** | **Small A** | **Small B** |
|-----------|------------|-----------|-----------|------------|------------|
| Max diameter | 2.00 m | 1.00 m | 1.60 m | 0.44 m | 0.60 m |
| Number of main loops | 3 | 2 | 3 | 1 | 2 |
| Number of coupling loops | 3 | 2 | 3 | 1 | 1 (shared) |
| Total copper tube | 14.4 m (47 ft) | 5.3 m (18 ft) | 12.1 m (40 ft) | 1.7 m (6 ft) | 3.6 m (12 ft) |
| Copper weight | 2.7 kg | 1.0 kg | 2.3 kg | 0.32 kg | 0.70 kg |
| Needs support frame? | Yes (2 m oct.) | No | Yes (1.6 m oct.) | No | No |
| Backpack portable? | No | Marginal | No | **Yes** | **Yes** |
| Field setup time | ~15 min | ~8 min | ~12 min | **~2 min** | **~4 min** |

---

## 5. Capacitor Requirements

| | **ML160-6** | **ML80-6** | **ML30-6** | **Small A** | **Small B** |
|---|---|---|---|---|---|
| **Max V_cap** | 6 200 V | 5 900 V | 1 913 V | 1 746 V | 1 807 V |
| **(at band)** | (40 m) | (20 m) | (30 m) | (10 m) | (15 m) |
| **Cap type** | Vacuum var. | Vacuum var. | Air variable | Air variable | Air variable |
| **HV relay?** | Yes (160 m) | Yes (80 m) | No | No | No |
| **Vacuum parts** | Required | Required | Not needed | Not needed | Not needed |
| **Cap ranges** | 10–1000 pF + 100 pF | 5–500 pF + 200 pF | 13–47 pF | 9–229 pF | 20–155 pF + trimmer |
| | + butterfly 5–50 pF | + butterfly 5–50 pF | + 7–35 pF | + trimmer 5–15 pF | |
| | | | + trimmer 5–15 pF | | |

---

## 6. Cost Comparison

| Component | **ML160-6** | **ML80-6** | **ML30-6** | **Small A** | **Small B** |
|-----------|------------|-----------|-----------|------------|------------|
| Copper tube | $50 | $20 | $35 | $5 | $10 |
| Vacuum variable cap | $150–300 | $150–300 | — | — | — |
| Air variable caps | $15–30 | $15–30 | $35–65 | $18–35 | $18–35 |
| HV relay + fixed cap | $40–60 | $30–40 | — | — | — |
| Connectors, hardware | $25 | $20 | $25 | $15 | $15 |
| Silver solder | $15 | $15 | $15 | $10 | $10 |
| PVC frame / mast | $20 | $10 | $18 | $3 | $5 |
| **Total estimate** | **$315–500** | **$260–435** | **$128–178** | **$51–68** | **$58–75** |

> The 100 W designs are dominated by the cost of a vacuum variable capacitor.
> The 10 W designs avoid vacuum parts entirely and cost 3–8× less.

---

## 7. Bandwidth Comparison (−3 dB, kHz)

Wider bandwidth = less frequent retuning = more comfortable operation.

| Band | **ML160-6** | **ML80-6** | **ML30-6** | **Small A** | **Small B** |
|------|-----------|-----------|-----------|------------|------------|
| 160 m | 1.7 | | | | |
| 80 m | 2.5 | 2.8 | | | |
| 60 m | 3.7 | 3.5 | | | |
| 40 m | 5.7 | 4.2 | | | |
| 30 m | 13.3 | 6.0 | **9.2** | 5.8 | 5.6 |
| 20 m | 10.6 | 10.6 | **24.2** | 7.2 | 7.9 |
| 17 m | 20 | 20 | **15.1** | 9.0 | 10.3 |
| 15 m | 33 | 33 | **23.4** | 10.8 | 13.8 |
| 12 m | 13 | 12.9 | **38.8** | 13.9 | 20.1 |
| 10 m | 16 | 16.4 | **61.3** | 18.1 | 29.0 |
| 6 m | 76 | 76 | **95.1** | 95.1 | 95.1 |

> ML30-6 efficiency-optimised has the widest bandwidth on 20 m, 12 m, and
> 10 m thanks to its larger per-band loop sizes that increase radiation
> resistance and lower Q.

---

## 8. Effective Radiated Power at Max Power

ERP = input power × efficiency. Higher ERP = stronger signal.

| Band | **ML160-6** (100 W) | **ML80-6** (100 W) | **ML30-6** (10 W) | **Small A** (10 W) | **Small B** (10 W) |
|------|-----------|-----------|-----------|-----------|-----------|
| 160 m | 0.6 W | | | | |
| 80 m | 5.5 W | 0.7 W | | | |
| 60 m | 20 W | 3.0 W | | | |
| 40 m | 40 W | 7.6 W | | | |
| 30 m | 69 W | 22 W | **5.4 W** | 0.24 W | 0.58 W |
| 20 m | 48 W | 48 W | **7.9 W** | 0.74 W | 1.7 W |
| 17 m | 69 W | 69 W | **5.7 W** | 1.6 W | 3.2 W |
| 15 m | 79 W | 79 W | **7.0 W** | 2.5 W | 4.5 W |
| 12 m | 30 W | 30 W | **8.1 W** | 3.6 W | 5.9 W |
| 10 m | 41 W | 41 W | **8.7 W** | 4.8 W | 7.0 W |
| 6 m | 83 W | 83 W | **8.7 W** | 8.7 W | 8.7 W |

> At 100 W, ML160-6 and ML80-6 deliver high ERP — tens of watts on most
> bands. The 10 W designs deliver 5–9 W ERP on their best bands, which is
> ample for all digital and CW modes and competitive for SSB.

---

## 9. Design Trade-Off Summary

```
    More bands ◄──────────────────────────────► Fewer bands
    ML160-6          ML80-6         ML30-6      Small A/B
    (11 bands)       (10 bands)     (7 bands)   (7 bands)

    Larger ◄──────────────────────────────────► Smaller
    ML160-6          ML30-6         ML80-6      Small B    Small A
    (2.0 m)          (1.6 m)        (1.0 m)     (0.6 m)   (0.44 m)

    Higher power ◄────────────────────────────► Lower power
    ML160-6 / ML80-6                ML30-6 / Small A / Small B
    (100 W, vacuum cap)             (10 W, air caps)

    Higher cost ◄─────────────────────────────► Lower cost
    ML160-6          ML80-6         ML30-6      Small B    Small A
    ($315–500)       ($260–435)     ($128–178)  ($58–75)   ($51–68)

    Higher efficiency ◄───────────────────────► Lower efficiency
    (on 30m–6m bands)
    ML30-6           ML160-6/80-6   Small B     Small A
    (avg 74%)        (avg 56%)      (avg 45%)   (avg 32%)
```

---

## 10. Which Design Should You Build?

### Choose ML160-6 if:
- You want **160 m and 80 m coverage** (no other design has it efficiently)
- You operate at **100 W** and need maximum ERP
- You have space for a **2.0 m loop with support frame**
- Budget allows a **vacuum variable capacitor** ($150–300)
- You want the most versatile all-band system

### Choose ML80-6 if:
- You want **80 m through 6 m** in a simpler 2-loop system
- You operate at **100 W** but don't need 160 m
- A **1.0 m** largest loop is your space limit
- Budget allows a **vacuum variable capacitor**
- Good balance of coverage, size, and simplicity

### Choose ML30-6 (Efficiency) if:
- You operate **30 m through 6 m** (the most active HF bands)
- You want the **highest efficiency** possible from a magnetic loop
- **10 W** is your power level (QRP to mid-power)
- You want to **avoid expensive vacuum capacitors**
- You don't mind three loops with a **1.6 m** max diameter
- **Best overall value** — high performance, moderate cost

### Choose ML30-6 Small A (Single Loop) if:
- **Portability is paramount** — backpack, field day, SOTA, POTA
- You mostly operate **12 m, 10 m, and 6 m** where efficiency is good
- You use **FT8, WSPR, CW** on lower bands (low ERP is OK with weak-signal modes)
- You want the **cheapest, simplest, lightest** magnetic loop possible
- **0.44 m diameter** — fits in a daypack

### Choose ML30-6 Small B (Concentric Dual) if:
- You want **portable** operation with **better efficiency** than Small A
- You need usable 17 m and 15 m performance (32–45 % vs 16–25 %)
- The extra 16 cm diameter and 0.4 kg are acceptable
- **Best portable design** for operators who use all bands 30 m – 6 m
- **0.60 m diameter** — still fits in a medium bag

---

## 11. Quick Selection Matrix

| Your Priority | Recommended Design |
|--------------|-------------------|
| "I want 160 m" | ML160-6 |
| "I want 80 m + 40 m at 100 W" | ML160-6 or ML80-6 |
| "I want the best 20 m antenna" | ML30-6 (79 % eff.) |
| "I want the best 10 m antenna" | ML30-6 (87 % eff.) |
| "Maximum bands, maximum power" | ML160-6 |
| "Best efficiency per dollar" | ML30-6 |
| "Backpack portable" | Small A (ultra-light) or Small B (better) |
| "Apartment / balcony" | Small B (concentric, 24" footprint) |
| "SOTA / POTA field day" | Small A or Small B |
| "Budget under $75" | Small A or Small B |
| "Budget under $180" | ML30-6 |
| "No vacuum capacitors" | ML30-6, Small A, or Small B |

---

## 12. Efficiency Heat Map

Visual comparison across all bands. Rating: [====] excellent, [=== ] good,
[==  ] moderate, [=   ] poor, [    ] not covered.

```
Band    ML160-6    ML80-6     ML30-6     Small A    Small B
────    ───────    ──────     ──────     ───────    ───────
160 m   [=   ]
 80 m   [=   ]     [    ]
 60 m   [==  ]     [    ]
 40 m   [=== ]     [=   ]
 30 m   [====]     [==  ]     [=== ]     [    ]     [=   ]
 20 m   [=== ]     [=== ]     [====]     [=   ]     [=   ]
 17 m   [====]     [====]     [=== ]     [=   ]     [==  ]
 15 m   [====]     [====]     [====]     [==  ]     [=== ]
 12 m   [==  ]     [==  ]     [====]     [==  ]     [=== ]
 10 m   [=== ]     [=== ]     [====]     [=== ]     [====]
  6 m   [====]     [====]     [====]     [====]     [====]
────    ───────    ──────     ──────     ───────    ───────
        η scale: [    ] <5%  [=   ] 5–25%  [==  ] 25–50%
                  [=== ] 50–75%  [====] >75%
```

---

## 13. Common Elements Across All Designs

All five configurations share:

- **Tube:** 3/8" (9.525 mm) OD soft copper, Type L
- **Joints:** Silver solder (56 % Ag) for all copper-to-copper connections
- **Feed:** Coupling loop at 6 o'clock, co-planar, fed with 50 Ω coax
- **Mounting:** Non-conductive PVC or fibreglass mast, no metal in loop plane
- **Tuning:** Narrowband — always retune when changing frequency
- **Pattern:** Figure-8, broadside to loop plane, with edge nulls
- **Loop formula:** L = μ₀ R [ln(8R/a) − 2], Rr = 31171 (A/λ²)²

---

*Comparison of ML160_6.md, ML80_6.md, ML30_6.md, and ML30_6_Small.md.*
*All designs: 3/8" copper tube, silver-soldered, standard mag-loop equations.*
