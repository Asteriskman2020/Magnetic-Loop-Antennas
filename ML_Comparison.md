# Magnetic Loop Antenna Design Comparison

## All Eight Designs — Side by Side

All designs use **3/8" (9.525 mm) OD soft copper tube** for both the main
radiator and coupling loop.

---

## 1. Design Overview

| | **ML160-6** | **ML80-6** | **ML30-6** | **Small A** | **Small B** | **ML20-6E** | **ML20-6** | **ML20-10** |
|---|---|---|---|---|---|---|---|---|
| **File** | ML160_6.md | ML80_6.md | ML30_6.md | ML30_6_Small.md | ML30_6_Small.md | ML20_6_Efficiency.md | ML20_6.md | ML20_10.md |
| **Coverage** | 160 m – 6 m | 80 m – 6 m | 30 m – 6 m | 30 m – 6 m | 30 m – 6 m | 20 m – 6 m | 20 m – 6 m | 20 m – 10 m |
| **Freq range** | 1.8 – 54 MHz | 3.5 – 54 MHz | 10.1 – 54 MHz | 10.1 – 54 MHz | 10.1 – 54 MHz | 14 – 54 MHz | 14 – 54 MHz | 14 – 29.7 MHz |
| **Bands** | 11 | 10 | 7 | 7 | 7 | 6 | 6 | 5 |
| **Optimised for** | Max coverage | Coverage | Efficiency | Min size | Size + eff. | Eff. (cap Q) | Balanced | Simplicity |
| **Max power** | 100 W | 100 W | 10 W | 10 W | 10 W | 10 W | 10 W | 10 W |
| **Number of loops** | 3 | 2 | 3 | 1 | 2 (concentric) | 1 | 2 | 1 |
| **Largest loop** | 2.00 m | 1.00 m | 1.60 m | 0.44 m | 0.60 m | 0.44 m | 0.80 m | 0.80 m |
| **Smallest loop** | 0.40 m | 0.40 m | 0.44 m | 0.44 m | 0.44 m | 0.44 m | 0.44 m | 0.80 m |

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
| Outer | 0.60 m | 30 m – 10 m | 120 mm (1:5) shared |
| Inner | 0.44 m | 6 m | (shared with outer) |

### ML20-6E (Efficiency) — Single Loop

| Loop | Diameter | Bands | Coupling |
|------|----------|-------|----------|
| — | 0.44 m | 20 m – 6 m (all) | 100 mm (1:4.4) |

### ML20-6 — Two Loops

| Loop | Diameter | Bands | Coupling |
|------|----------|-------|----------|
| 1 | 0.80 m | 20 m, 17 m, 15 m, 12 m, 10 m | 160 mm (1:5) |
| 2 | 0.44 m | 6 m | 110 mm (1:4) |

### ML20-10 — Single Loop

| Loop | Diameter | Bands | Coupling |
|------|----------|-------|----------|
| — | 0.80 m | 20 m, 17 m, 15 m, 12 m, 10 m | 160 mm (1:5) |

---

## 3. Band-by-Band Efficiency — Theoretical Maximum (Q = ∞)

This table compares **loop geometry only** — all designs at theoretical
maximum (lossless capacitor). This is the fairest apples-to-apples
comparison. Real-world efficiency will be lower depending on capacitor
quality (see Section 4).

Each cell shows **efficiency %** and **(dB loss)**. Blank = band not covered.

| Band | f (MHz) | **ML160-6** | **ML80-6** | **ML30-6** | **Sm A** | **Sm B** | **ML20-6E** | **ML20-6** | **ML20-10** |
|------|---------|------------|-----------|-----------|---------|---------|------------|-----------|------------|
| 160 m | 1.85 | 0.6 (−22) | | | | | | | |
| 80 m | 3.55 | 5.5 (−13) | 0.7 (−21) | | | | | | |
| 60 m | 5.35 | 20 (−7.1) | 3.0 (−15) | | | | | | |
| 40 m | 7.10 | 40 (−4.0) | 7.6 (−11) | | | | | | |
| 30 m | 10.1 | 69 (−1.6) | 22 (−6.5) | 54 (−2.7) | 2.4 (−16) | 5.8 (−12) | | | |
| **20 m** | 14.2 | 48 (−3.2) | 48 (−3.2) | **79 (−1.0)** | 7.4 (−11) | 17 (−7.8) | 7.4 (−11) | 32 (−4.9) | 32 (−4.9) |
| **17 m** | 18.1 | **69 (−1.6)** | **69 (−1.6)** | 57 (−2.4) | 16 (−8.0) | 32 (−4.9) | 16 (−8.0) | 53 (−2.8) | 53 (−2.8) |
| **15 m** | 21.2 | **79 (−1.0)** | **79 (−1.0)** | 70 (−1.5) | 25 (−6.1) | 45 (−3.4) | 25 (−6.1) | 66 (−1.8) | 66 (−1.8) |
| **12 m** | 24.9 | 30 (−5.2) | 30 (−5.2) | **81 (−0.9)** | 36 (−4.4) | 59 (−2.3) | 36 (−4.4) | 78 (−1.1) | 78 (−1.1) |
| **10 m** | 28.5 | 41 (−3.9) | 41 (−3.9) | **87 (−0.6)** | 48 (−3.2) | 70 (−1.6) | 48 (−3.2) | 85 (−0.7) | 85 (−0.7) |
| **6 m** | 50.1 | 83 (−0.8) | 83 (−0.8) | 87 (−0.6) | 87 (−0.6) | 87 (−0.6) | 87 (−0.6) | **88 (−0.5)** | |

### Best Design Per Band (Theoretical)

| Band | Best Design | η | Runner-up | η |
|------|------------|---|-----------|---|
| 160 m | ML160-6 (only option) | 0.6 % | — | — |
| 80 m | ML160-6 | 5.5 % | ML80-6 | 0.7 % |
| 60 m | ML160-6 | 20 % | ML80-6 | 3.0 % |
| 40 m | ML160-6 | 40 % | ML80-6 | 7.6 % |
| 30 m | ML160-6 | 69 % | ML30-6 | 54 % |
| 20 m | **ML30-6** | 79 % | ML160-6 / ML80-6 | 48 % |
| 17 m | ML160-6 / ML80-6 | 69 % | ML30-6 | 57 % |
| 15 m | ML160-6 / ML80-6 | 79 % | ML30-6 | 70 % |
| 12 m | **ML30-6** | 81 % | ML20-6 / ML20-10 | 78 % |
| 10 m | **ML30-6** | 87 % | ML20-6 / ML20-10 | 85 % |
| 6 m | ML20-6 | 88 % | ML30-6 / Sm A / Sm B / ML20-6E | 87 % |

> **Key insights:**
> - ML30-6 dominates on 12 m, 10 m, and 20 m due to per-band loop sizing
> - ML160-6 / ML80-6 share the same 1.0 m loop, so they tie on 17 m / 15 m
> - ML20-6 and ML20-10 share the same 0.80 m loop — identical on 20 m – 10 m
> - ML20-6E and Small A share the same 0.44 m loop — identical on 20 m – 10 m
> - On 6 m, all 0.40–0.44 m loops perform within 1 % of each other

---

## 4. Realistic Efficiency (with Capacitor Losses)

Real-world efficiency depends heavily on capacitor quality. Each design's
headline performance uses different capacitor assumptions:

| Design | Capacitor basis | Q assumed |
|--------|----------------|-----------|
| ML160-6 | Theoretical (Q=∞) | ∞ |
| ML80-6 | Theoretical (Q=∞) | ∞ |
| ML30-6 | Theoretical (Q=∞) | ∞ |
| Small A | Theoretical (Q=∞) | ∞ |
| Small B | Theoretical (Q=∞) | ∞ |
| ML20-6E | Butterfly split-stator | 5 000 |
| ML20-6 | Standard air variable | 2 000 |
| ML20-10 | Standard air variable | 2 000 |

### ML20-6 and ML20-10 with Cap Losses (Q = 2 000)

These designs include realistic capacitor ESR in their performance tables.
The impact is significant:

| Band | Theoretical η | η with Q=2000 | Efficiency lost |
|------|--------------|---------------|-----------------|
| 20 m | 32.3 % | 17.7 % | −14.6 pts |
| 17 m | 53.0 % | 32.1 % | −20.9 pts |
| 15 m | 66.2 % | 44.0 % | −22.2 pts |
| 12 m | 77.5 % | 56.8 % | −20.7 pts |
| 10 m | 85.2 % | 67.7 % | −17.5 pts |

> **Takeaway:** A Q=2000 capacitor costs 15–22 percentage points of
> efficiency on a 0.80 m loop. The loss is worst on 15–17 m where
> inductive reactance is high relative to radiation resistance.

### ML20-6E with Cap Losses (Q = 5 000)

| Band | Theoretical η | η with Q=5000 | Efficiency lost |
|------|--------------|---------------|-----------------|
| 20 m | 7.4 % | 5.3 % | −2.1 pts |
| 17 m | 15.7 % | 11.2 % | −4.5 pts |
| 15 m | 24.6 % | 17.7 % | −6.9 pts |
| 12 m | 36.4 % | 26.8 % | −9.6 pts |
| 10 m | 47.7 % | 36.3 % | −11.4 pts |
| 6 m | 86.8 % | 78.5 % | −8.3 pts |

> **Note:** All other designs (ML160-6 through Small B) would also lose
> efficiency from capacitor ESR. Their published numbers represent the
> theoretical ceiling. Expect 10–25 % lower efficiency in practice
> depending on capacitor quality.

---

## 5. Physical and Practical Comparison

| Attribute | **ML160-6** | **ML80-6** | **ML30-6** | **Sm A** | **Sm B** | **ML20-6E** | **ML20-6** | **ML20-10** |
|-----------|------------|-----------|-----------|---------|---------|------------|-----------|------------|
| Max diameter | 2.00 m | 1.00 m | 1.60 m | 0.44 m | 0.60 m | 0.44 m | 0.80 m | 0.80 m |
| Max diameter (inches) | 78.7" | 39.4" | 63.0" | 17.3" | 23.6" | 17.3" | 31.5" | 31.5" |
| Main loops | 3 | 2 | 3 | 1 | 2 | 1 | 2 | 1 |
| Coupling loops | 3 | 2 | 3 | 1 | 1 shared | 1 | 2 | 1 |
| Total Cu tube | 14.4 m | 5.3 m | 12.1 m | 1.7 m | 3.6 m | 2.0 m | 5.0 m | 3.1 m |
| Total Cu tube (ft) | 47 ft | 18 ft | 40 ft | 6 ft | 12 ft | 7 ft | 16 ft | 10 ft |
| Cu weight | 2.7 kg | 1.0 kg | 2.3 kg | 0.32 kg | 0.70 kg | 0.38 kg | 1.0 kg | 0.35 kg |
| Total weight (est.) | ~4 kg | ~1.5 kg | ~3.5 kg | 0.6 kg | 1.2 kg | 0.5 kg | 1.3 kg | 0.7 kg |
| Support frame? | Yes (2 m) | No | Yes (1.6 m) | No | No | No | No | No |
| Backpack portable? | No | Marginal | No | **Yes** | **Yes** | **Yes** | Marginal | Marginal |
| Field setup time | ~15 min | ~8 min | ~12 min | **~2 min** | **~4 min** | **~3 min** | ~6 min | **~4 min** |

---

## 6. Capacitor Requirements

| | **ML160-6** | **ML80-6** | **ML30-6** | **Sm A** | **Sm B** | **ML20-6E** | **ML20-6** | **ML20-10** |
|---|---|---|---|---|---|---|---|---|
| **Max Vc** | 6 200 V | 5 900 V | 1 913 V | 1 746 V | 1 807 V | 1 746 V | 1 426 V | 1 426 V |
| **(at band)** | 40 m | 20 m | 30 m | 10 m | 15 m | 10 m | 17 m | 17 m |
| **Cap type** | Vacuum | Vacuum | Air var. | Air var. | Air var. | Butterfly | Air var. | Air var. |
| **HV relay?** | Yes | Yes | No | No | No | No | No | No |
| **Vacuum parts** | Required | Required | None | None | None | None | None | None |
| **Cap ranges** | 10–1000 pF | 5–500 pF | 13–47 pF | 9–229 pF | 20–155 pF | 9–117 pF | 13–56 pF | 13–56 pF |
| | +100 pF fixed | +200 pF fixed | +7–35 pF | +trimmer | +trimmer | (single cap) | +3–25 pF | (single cap) |
| | +butterfly | +butterfly | +trimmer | | | | | |
| **Band switch** | Relay | Relay | Manual swap | Toggle | DPDT | None | Coax swap | None |

### Capacitor Complexity Ranking (simplest first)

1. **ML20-10** — one air variable, one loop, no switching
2. **ML20-6E** — one butterfly, one loop, no switching
3. **ML20-6** — one air variable + one trimmer, coax swap between loops
4. **Small A** — one air variable + toggle to trimmer for 6 m
5. **Small B** — one air variable + trimmer + DPDT switch
6. **ML30-6** — three separate caps, manual loop swap
7. **ML80-6** — vacuum variable + relay + butterfly, manual loop swap
8. **ML160-6** — vacuum variable + relay + butterfly, manual loop swap

---

## 7. Cost Comparison

| Component | **ML160-6** | **ML80-6** | **ML30-6** | **Sm A** | **Sm B** | **ML20-6E** | **ML20-6** | **ML20-10** |
|-----------|------------|-----------|-----------|---------|---------|------------|-----------|------------|
| Copper tube | $50 | $20 | $35 | $5 | $10 | $5 | $25 | $15 |
| Vacuum cap | $150–300 | $150–300 | — | — | — | — | — | — |
| Air / butterfly cap | $15–30 | $15–30 | $35–65 | $18–35 | $18–35 | $25–50 | $33 | $25 |
| HV relay + fixed | $40–60 | $30–40 | — | — | — | — | — | — |
| Connectors, hardware | $25 | $20 | $25 | $15 | $15 | $16 | $19 | $12 |
| Silver solder | $15 | $15 | $15 | $10 | $10 | $12 | $15 | $15 |
| PVC / mast | $20 | $10 | $18 | $3 | $5 | $3 | $12 | $10 |
| Vernier drive | — | — | — | — | — | $12 | $20 | $20 |
| **Total** | **$315–500** | **$260–435** | **$128–178** | **$51–68** | **$58–75** | **$61–93** | **$124** | **$97** |

### Cost per Band

| Design | Total cost | Bands | Cost/band |
|--------|-----------|-------|-----------|
| Small A | $60 | 7 | **$9** |
| Small B | $67 | 7 | **$10** |
| ML20-6E | $77 | 6 | $13 |
| ML20-10 | $97 | 5 | $19 |
| ML20-6 | $124 | 6 | $21 |
| ML30-6 | $153 | 7 | $22 |
| ML80-6 | $348 | 10 | $35 |
| ML160-6 | $408 | 11 | $37 |

> The 100 W designs are dominated by the cost of a vacuum variable
> capacitor. The 10 W designs avoid vacuum parts entirely and cost
> 3–8× less.

---

## 8. Bandwidth Comparison (−3 dB, kHz)

Wider bandwidth = less frequent retuning.

Note: ML20-6 and ML20-10 bandwidths include Q=2000 cap loading (wider).
ML20-6E includes Q=5000 cap (narrower). Other designs are theoretical.

| Band | **ML160-6** | **ML80-6** | **ML30-6** | **Sm A** | **Sm B** | **ML20-6E** | **ML20-6** | **ML20-10** |
|------|-----------|-----------|-----------|---------|---------|------------|-----------|------------|
| 160 m | 1.7 | | | | | | | |
| 80 m | 2.5 | 2.8 | | | | | | |
| 60 m | 3.7 | 3.5 | | | | | | |
| 40 m | 5.7 | 4.2 | | | | | | |
| 30 m | 13.3 | 6.0 | 9.2 | 5.8 | 5.6 | | | |
| 20 m | 10.6 | 10.6 | **24.2** | 7.2 | 7.9 | 5.4 | 15.7 | 15.7 |
| 17 m | 20 | 20 | 15.1 | 9.0 | 10.3 | 6.7 | **23.0** | **23.0** |
| 15 m | 33 | 33 | 23.4 | 10.8 | 13.8 | 8.1 | **31.6** | **31.6** |
| 12 m | 13 | 12.9 | 38.8 | 13.9 | 20.1 | 10.3 | **46.7** | **46.7** |
| 10 m | 16 | 16.4 | 61.3 | 18.1 | 29.0 | 13.6 | **70.2** | **70.2** |
| 6 m | 76 | 76 | 95.1 | 95.1 | 95.1 | 71 | **135** | |

> ML20-6 and ML20-10 show the widest bandwidths on 12–10 m because their
> cap losses (Q=2000) broaden the resonance. ML30-6 has wide bandwidth
> for the right reason — high radiation resistance from its optimally
> sized loops.

---

## 9. Effective Radiated Power at Max Power

ERP = input power × efficiency. The 100 W designs naturally have higher
ERP despite lower efficiency.

| Band | **ML160-6** | **ML80-6** | **ML30-6** | **Sm A** | **Sm B** | **ML20-6E** | **ML20-6** | **ML20-10** |
|------|---|---|---|---|---|---|---|---|
| | 100 W | 100 W | 10 W | 10 W | 10 W | 10 W | 10 W | 10 W |
| 160 m | 0.6 W | | | | | | | |
| 80 m | 5.5 W | 0.7 W | | | | | | |
| 60 m | 20 W | 3.0 W | | | | | | |
| 40 m | 40 W | 7.6 W | | | | | | |
| 30 m | 69 W | 22 W | 5.4 W | 0.24 W | 0.58 W | | | |
| 20 m | 48 W | 48 W | 7.9 W | 0.74 W | 1.7 W | 0.53 W | 1.8 W | 1.8 W |
| 17 m | 69 W | 69 W | 5.7 W | 1.6 W | 3.2 W | 1.1 W | 3.2 W | 3.2 W |
| 15 m | 79 W | 79 W | 7.0 W | 2.5 W | 4.5 W | 1.8 W | 4.4 W | 4.4 W |
| 12 m | 30 W | 30 W | 8.1 W | 3.6 W | 5.9 W | 2.7 W | 5.7 W | 5.7 W |
| 10 m | 41 W | 41 W | 8.7 W | 4.8 W | 7.0 W | 3.6 W | 6.8 W | 6.8 W |
| 6 m | 83 W | 83 W | 8.7 W | 8.7 W | 8.7 W | 7.9 W | 7.1 W | |

> **Note:** ML20-6E and ML20-6/ML20-10 ERP values include cap losses.
> Other designs show theoretical ERP; real ERP will be 10–30 % lower.

---

## 10. Average Efficiency by Band Group (Theoretical, Q = ∞)

Comparing only bands shared by each design:

### 20 m – 10 m (5 HF bands — shared by all designs except ML30-6 on 30 m)

| Design | 20 m | 17 m | 15 m | 12 m | 10 m | **Average** |
|--------|------|------|------|------|------|-------------|
| ML30-6 | 79 | 57 | 70 | 81 | 87 | **74.8 %** |
| ML20-6 / ML20-10 | 32 | 53 | 66 | 78 | 85 | **62.8 %** |
| ML160-6 / ML80-6 | 48 | 69 | 79 | 30 | 41 | **53.4 %** |
| Small B | 17 | 32 | 45 | 59 | 70 | **44.6 %** |
| Small A / ML20-6E | 7 | 16 | 25 | 36 | 48 | **26.4 %** |

> **ML30-6 wins** on average across 20–10 m due to its per-band loop
> sizing. ML20-6 / ML20-10 (0.80 m single loop) comes second with 63 %,
> beating even the 100 W designs' 1.00 m loop on 12 m and 10 m.

### 20 m – 6 m (6 bands — all that include 6 m)

| Design | Average η (theoretical) |
|--------|------------------------|
| ML30-6 | **76.8 %** |
| ML20-6 | **67.1 %** |
| ML160-6 / ML80-6 | **58.3 %** |
| Small B | **51.7 %** |
| Small A | **36.6 %** |
| ML20-6E | **36.4 %** |

---

## 11. Design Trade-Off Axes

```
    More bands ◄──────────────────────────────────► Fewer bands
    ML160-6      ML80-6     ML30-6    ML20-6    ML20-10
    (11)         (10)       Sm A/B    ML20-6E   (5)
                            (7)       (6)

    Larger ◄──────────────────────────────────────► Smaller
    ML160-6    ML30-6     ML80-6   ML20-6   Sm B    Sm A
    (2.0 m)    (1.6 m)    (1.0 m)  ML20-10  (0.6 m) ML20-6E
                                   (0.8 m)          (0.44 m)

    Higher power ◄────────────────────────────────► Lower power
    ML160-6 / ML80-6                All others
    (100 W, vacuum)                 (10 W, air caps)

    Higher cost ◄─────────────────────────────────► Lower cost
    ML160-6    ML80-6    ML30-6    ML20-6   ML20-10  ML20-6E  Sm B   Sm A
    ($408)     ($348)    ($153)    ($124)   ($97)    ($77)    ($67)  ($60)

    More complex ◄────────────────────────────────► Simpler
    ML160-6    ML80-6    ML30-6    ML20-6   Sm B    Sm A    ML20-6E  ML20-10
    (3 loops   (2 loops  (3 loops  (2 loops (DPDT   (toggle) (1 cap)  (1 cap
     +relay)    +relay)   3 caps)   2 caps)  sw.)            1 loop)  1 loop)

    Higher HF efficiency ◄────────────────────────► Lower HF efficiency
    (20 m – 10 m avg, theoretical)
    ML30-6    ML20-6    ML160-6   Sm B      Sm A
    (75%)     ML20-10   ML80-6    (45%)     ML20-6E
              (63%)     (53%)               (26%)
```

---

## 12. Which Design Should You Build?

### Choose ML160-6 if:
- You want **160 m and 80 m** coverage
- You operate at **100 W** and need maximum ERP
- You have space for a **2.0 m loop** with support frame
- Budget allows a **vacuum variable capacitor** ($150–300)

### Choose ML80-6 if:
- You want **80 m through 6 m** without the 160 m complexity
- You operate at **100 W** but don't need 160 m
- A **1.0 m** loop is your size limit

### Choose ML30-6 (Efficiency) if:
- You want **the highest efficiency** on 30 m – 6 m
- Average **75 % efficiency** across 20 m – 10 m is worth 3 loops
- You don't mind the **1.6 m** largest loop with support frame
- **Best overall value** for performance per dollar

### Choose ML20-6E (Efficiency) if:
- **Portability is paramount** — fits in a daypack
- You mostly operate **6 m** (79 %) and use **FT8/CW** on lower bands
- You want the highest possible efficiency from a **0.44 m single loop**
- A **high-Q butterfly** capacitor is your primary investment

### Choose ML20-6 if:
- You want a **balanced** design: good HF + 6 m coverage
- **Two loops** (0.80 m + 0.44 m) are acceptable
- You want significantly better HF performance than the single 0.44 m designs
- Home station or **semi-portable** use

### Choose ML20-10 if:
- You want **maximum simplicity**: one loop, one cap, no switching
- You don't need 6 m
- **0.80 m single loop** covers 20 m – 10 m with no compromises
- The **cheapest 0.80 m** design at $97
- Add a 0.44 m loop later if you want 6 m

### Choose Small A if:
- **Lightest, smallest, cheapest** magnetic loop possible
- **0.44 m** diameter fits anywhere
- You accept low HF efficiency (2–7 %) on 30 m / 20 m
- SOTA / POTA / backpacking with **FT8** operation

### Choose Small B if:
- Better efficiency than Small A with manageable size increase
- **0.60 m** diameter in a concentric dual-loop package
- Good **12–10 m** performance (59–70 %) in a portable package

---

## 13. Quick Selection Matrix

| Your Priority | Recommended Design |
|--------------|-------------------|
| "I want 160 m" | ML160-6 |
| "I want 80 m + 40 m at 100 W" | ML160-6 or ML80-6 |
| "Maximum efficiency on 20 m" | **ML30-6** (79 %) |
| "Maximum efficiency on 10 m" | **ML30-6** (87 %) |
| "Best HF eff. from a single loop" | **ML20-10** (63 % avg, 0.80 m) |
| "Single loop covering 20 m – 6 m" | ML20-6E (0.44 m) |
| "Balanced 20 m – 6 m" | ML20-6 (2-loop) |
| "Maximum simplicity (HF only)" | **ML20-10** |
| "Backpack portable" | Small A or ML20-6E |
| "Portable with decent HF eff." | Small B |
| "Apartment / balcony" | Small B or ML20-6E |
| "SOTA / POTA" | Small A (ultra-light) or Small B |
| "Budget under $75" | Small A, Small B, or ML20-6E |
| "Budget under $100" | ML20-10 ($97) |
| "Budget under $130" | ML20-6 ($124) |
| "No vacuum capacitors" | Any 10 W design |
| "No band switching at all" | **ML20-10** or **ML20-6E** |
| "I want to add 6 m later" | Start with ML20-10, add 0.44 m loop |

---

## 14. Efficiency Heat Map

Visual comparison across all bands and designs. Rating scale:

```
[    ] < 5 %    [=   ] 5–25 %    [==  ] 25–50 %    [=== ] 50–75 %    [====] > 75 %
```

```
Band    ML160-6  ML80-6   ML30-6   Sm A     Sm B     ML20-6E  ML20-6   ML20-10
────    ───────  ──────   ──────   ─────    ─────    ───────  ──────   ───────
160 m   [=   ]
 80 m   [=   ]   [    ]
 60 m   [==  ]   [    ]
 40 m   [=== ]   [=   ]
 30 m   [====]   [==  ]   [=== ]   [    ]   [=   ]
 20 m   [=== ]   [=== ]   [====]   [=   ]   [=   ]   [=   ]   [==  ]   [==  ]
 17 m   [====]   [====]   [=== ]   [=   ]   [==  ]   [=   ]   [=== ]   [=== ]
 15 m   [====]   [====]   [====]   [==  ]   [=== ]   [==  ]   [====]   [====]
 12 m   [==  ]   [==  ]   [====]   [==  ]   [=== ]   [==  ]   [====]   [====]
 10 m   [=== ]   [=== ]   [====]   [=== ]   [====]   [=== ]   [====]   [====]
  6 m   [====]   [====]   [====]   [====]   [====]   [====]   [====]
────    ───────  ──────   ──────   ─────    ─────    ───────  ──────   ───────
```

---

## 15. Design Family Tree

```
                    ┌─ ML160-6 (160m–6m, 100W, 3 loops)
                    │
    Full-coverage ──┤
                    │
                    └─ ML80-6 (80m–6m, 100W, 2 loops)


                    ┌─ ML30-6 (30m–6m, 10W, 3 loops, max efficiency)
                    │
    Efficiency ─────┤
                    │
                    └─ ML20-6E (20m–6m, 10W, 1 loop, high-Q cap)


                    ┌─ Small A (30m–6m, 10W, 1 × 0.44m, ultra-portable)
                    │
    Portable ───────┤
                    │
                    └─ Small B (30m–6m, 10W, 2 × concentric, portable)


                    ┌─ ML20-6 (20m–6m, 10W, 2 loops, balanced)
                    │
    Balanced ───────┤
                    │
                    └─ ML20-10 (20m–10m, 10W, 1 loop, simplest)
```

---

## 16. Common Elements Across All Designs

All eight configurations share:

- **Tube:** 3/8" (9.525 mm) OD soft copper, Type L
- **Joints:** Silver solder (56 % Ag) for all copper-to-copper connections
- **Feed:** Coupling loop at 6 o'clock, co-planar, fed with 50 Ω coax
- **Mounting:** Non-conductive PVC or fibreglass mast
- **Tuning:** Narrowband — always retune when changing frequency
- **Pattern:** Figure-8, maximum radiation off loop edges, nulls broadside
- **Loop formula:** L = μ₀ R [ln(8R/a) − 2], Rr = 31 171 (A/λ²)²
- **Safety:** Never touch loop top / capacitor during transmit

---

*Comparison of all magnetic loop antenna designs.*
*All designs: 3/8" copper tube, silver-soldered, standard mag-loop equations.*
*Updated: 2026-02-07 — now includes ML20_6_Efficiency.md, ML20_6.md, ML20_10.md*
