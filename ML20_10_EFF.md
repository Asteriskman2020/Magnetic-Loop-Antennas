# ML20_10_EFF — Magnetic Loop Antenna: 20 m – 10 m (Efficiency Optimised)

> **Multi-loop design | Same 0.80 m diameter | 3/8" copper tube | 10 W max | 5 HF bands**

---

## 1. Design Overview

An efficiency-optimised magnetic loop antenna covering 20 m through 10 m
(14.000–29.700 MHz) using **two identical 0.80 m loops** stacked
coaxially, each covering a different sub-range. By splitting the five
bands between two dedicated loops, each loop operates closer to its
optimum circumference/λ ratio, raising efficiency significantly compared
to the single-loop ML20_10 design.

| Parameter          | Value                                       |
|--------------------|---------------------------------------------|
| Band coverage      | 20 m, 17 m, 15 m, 12 m, 10 m               |
| Frequency range    | 14.000 – 29.700 MHz                         |
| Max power          | 10 W                                        |
| Loop diameter      | **0.80 m** (31.5") — both loops identical   |
| Radiator material  | 3/8" (9.525 mm OD) soft copper tube Type L  |
| Coupling loops     | 3/8" soft copper tube, 160 mm diameter (×2) |
| Number of loops    | **2** (same size, stacked)                  |
| Band switching     | SP3T toggle switch (loop select + bypass)   |

### Why Two Identical Loops?

A single 0.80 m loop covering 20m–10m works, but on the lower bands
(20 m, 17 m) the circumference/λ ratio is small (0.12–0.15), which
means low radiation resistance and low efficiency. The physics cannot
be changed — but we can **optimise the capacitor Q** differently for
each band group:

- **Loop A (Low-Band):** Covers 20 m + 17 m (14.0–18.2 MHz).
  Uses a high-Q butterfly capacitor (Q ≈ 5000) to minimise capacitor
  loss where Rr is smallest and cap loss dominates.

- **Loop B (High-Band):** Covers 15 m + 12 m + 10 m (21.0–29.7 MHz).
  Uses a standard air variable (Q ≈ 2000). On these bands Rr is
  large enough that capacitor Q matters less — the standard cap is
  adequate and keeps cost down.

This "split Q" strategy puts the expensive capacitor where it matters
most (low bands) and saves money on the high bands where efficiency
is already good.

---

## 2. Material Properties

| Property                       | Value                          |
|--------------------------------|--------------------------------|
| Copper tube OD                 | 9.525 mm (3/8")                |
| Copper tube wall (Type L)      | 0.762 mm                       |
| Tube radius *a*                | 4.7625 mm                      |
| Copper conductivity σ          | 5.8 × 10⁷ S/m                 |
| Permeability μ₀                | 4π × 10⁻⁷ H/m                 |
| Minimum bend radius            | ≈ 38 mm (4 × OD)              |

---

## 3. Loop Electrical Parameters

Both loops share identical physical dimensions.

### Loop Constants (each loop)

| Parameter    | Value         |
|--------------|---------------|
| Diameter     | 0.80 m        |
| Radius R     | 0.40 m        |
| Circumference| 2.513 m       |
| Area A       | 0.5027 m²     |
| Inductance L | **2.267 μH**  |

```
L = μ₀ × R × [ln(8R/a) − 2]
  = 1.2566e-6 × 0.40 × [ln(8 × 0.40 / 0.0047625) − 2]
  = 5.026e-7 × [ln(671.8) − 2]
  = 5.026e-7 × 4.510
  = 2.267 μH
```

### Formulae

| Quantity              | Formula                                  |
|-----------------------|------------------------------------------|
| Inductance            | L = μ₀ R [ln(8R/a) − 2]                 |
| Resonant capacitance  | C = 1 / (4π²f²L)                        |
| Radiation resistance  | Rr = 31 171 (A/λ²)²                     |
| Skin-effect Rs        | Rs = √(πfμ₀/σ)                          |
| Loss resistance       | Rl = Rs × circ / (π × OD)               |
| Capacitor loss        | Rc = X_L / Q_cap                         |
| Efficiency            | η = Rr / (Rr + Rl + Rc)                 |
| Loaded Q              | Q_L = 2πfL / (Rr + Rl + Rc)             |
| Bandwidth (−3 dB)     | BW = f / Q_L                             |
| Cap voltage           | Vc = √(P / R_total) × X_L               |

---

## 4. Band-by-Band Performance

### 4.1 Loop A — 20 m + 17 m (Butterfly Q = 5 000)

| Band | f_mid (MHz) | λ (m) | circ/λ | C (pF) | X_L (Ω) | Rr (mΩ) | Rl (mΩ) | Rc (mΩ) | R_total (mΩ) | η (%) | Vc (V) | BW (kHz) |
|------|-------------|-------|--------|--------|----------|----------|---------|---------|---------------|-------|--------|----------|
| 20 m | 14.175 | 21.15 | 0.119 | 55.6 | 201.8 | 39.4 | 82.5 | 40.4 | 162.3 | **24.3** | 1 584 | 13.6 |
| 17 m | 18.118 | 16.55 | 0.152 | 34.0 | 257.8 | 105.0 | 93.2 | 51.6 | 249.8 | **42.0** | 1 631 | 19.6 |

**Average efficiency (Loop A): 33.2 %**

### 4.2 Loop B — 15 m + 12 m + 10 m (Air Variable Q = 2 000)

| Band | f_mid (MHz) | λ (m) | circ/λ | C (pF) | X_L (Ω) | Rr (mΩ) | Rl (mΩ) | Rc (mΩ) | R_total (mΩ) | η (%) | Vc (V) | BW (kHz) |
|------|-------------|-------|--------|--------|----------|----------|---------|---------|---------------|-------|--------|----------|
| 15 m | 21.225 | 14.13 | 0.178 | 24.8 | 302.1 | 197.7 | 100.9 | 151.1 | 449.7 | **44.0** | 1 426 | 31.6 |
| 12 m | 24.940 | 12.02 | 0.209 | 18.0 | 355.1 | 377.3 | 109.4 | 177.6 | 664.3 | **56.8** | 1 378 | 46.7 |
| 10 m | 28.850 | 10.39 | 0.242 | 13.4 | 410.6 | 676.2 | 117.6 | 205.3 | 999.1 | **67.7** | 1 298 | 70.2 |

**Average efficiency (Loop B): 56.2 %**

### 4.3 What-If: Both Loops Use Butterfly Q = 5 000

To see the full efficiency potential if both loops use high-Q butterfly
capacitors:

| Band | Loop | Rc (mΩ) | R_total (mΩ) | η (%) | Vc (V) |
|------|------|---------|---------------|-------|--------|
| 20 m | A | 40.4 | 162.3 | **24.3** | 1 584 |
| 17 m | A | 51.6 | 249.8 | **42.0** | 1 631 |
| 15 m | B | 60.4 | 359.0 | **55.1** | 1 594 |
| 12 m | B | 71.0 | 557.7 | **67.7** | 1 505 |
| 10 m | B | 82.1 | 875.9 | **77.2** | 1 387 |

**Average efficiency (all Q=5000): 53.3 %** — a major step up from
the single-loop ML20_10 at Q=2000 (43.7 %).

### 4.4 What-If: Both Loops Use Butterfly Q = 7 000

With premium butterfly split-stator capacitors (Q ≈ 7 000):

| Band | Rc (mΩ) | R_total (mΩ) | η (%) |
|------|---------|---------------|-------|
| 20 m | 28.8 | 150.7 | **26.1** |
| 17 m | 36.8 | 235.0 | **44.7** |
| 15 m | 43.2 | 341.8 | **57.8** |
| 12 m | 50.7 | 537.4 | **70.2** |
| 10 m | 58.7 | 852.5 | **79.3** |

**Average efficiency (all Q=7000): 55.6 %**

### 4.5 Theoretical Maximum (Lossless Capacitor, Q = ∞)

| Band | Rr (mΩ) | Rl (mΩ) | η_max (%) |
|------|----------|----------|-----------|
| 20 m | 39.4  | 82.5  | 32.3 |
| 17 m | 105.0 | 93.2  | 53.0 |
| 15 m | 197.7 | 100.9 | 66.2 |
| 12 m | 377.3 | 109.4 | 77.5 |
| 10 m | 676.2 | 117.6 | 85.2 |

**Average theoretical max: 62.8 %**

### 4.6 Efficiency Comparison Summary

| Configuration | 20 m | 17 m | 15 m | 12 m | 10 m | **Average** |
|---------------|------|------|------|------|------|-------------|
| ML20_10 single (Q=2000) | 17.7 | 32.1 | 44.0 | 56.8 | 67.7 | **43.7 %** |
| **This design (Split Q)** | **24.3** | **42.0** | **44.0** | **56.8** | **67.7** | **46.9 %** |
| Both Q=5000 | 24.3 | 42.0 | 55.1 | 67.7 | 77.2 | **53.3 %** |
| Both Q=7000 | 26.1 | 44.7 | 57.8 | 70.2 | 79.3 | **55.6 %** |
| Theoretical max | 32.3 | 53.0 | 66.2 | 77.5 | 85.2 | **62.8 %** |

> **Key insight:** The split-Q strategy raises 20 m efficiency from
> 17.7 % to 24.3 % (+37 % relative, +1.4 dB) and 17 m from 32.1 %
> to 42.0 % (+31 %, +1.2 dB) — the bands that benefit the most.
> Going all-butterfly (Q=5000) on both loops lifts average efficiency
> from 43.7 % to 53.3 % — a +2.2 dB improvement across the board.

---

## 5. Effective Radiated Power (ERP)

Directivity = 1.5 (1.76 dBi), omnidirectional in the loop plane.
Input power = 10 W.

| Band | η (Split Q) | ERP (W) | η (All Q=5k) | ERP (W) |
|------|-------------|---------|--------------|---------|
| 20 m | 24.3 % | 3.6 | 24.3 % | 3.6 |
| 17 m | 42.0 % | 6.3 | 42.0 % | 6.3 |
| 15 m | 44.0 % | 6.6 | 55.1 % | 8.3 |
| 12 m | 56.8 % | 8.5 | 67.7 % | 10.2 |
| 10 m | 67.7 % | 10.2 | 77.2 % | 11.6 |

---

## 6. Tuning Capacitors

### Loop A — Butterfly Split-Stator (20 m + 17 m)

| Parameter           | Value                            |
|---------------------|----------------------------------|
| Type                | Butterfly (split-stator)         |
| Sections            | 2 × 100 pF                      |
| Effective range     | 0 – 50 pF (series)              |
| Required range      | 34.0 – 55.6 pF                  |
| Plate spacing       | ≥ 1.0 mm (doubled voltage)      |
| Voltage rating      | ≈ 3 500 V effective              |
| Estimated Q         | 5 000                            |
| Cost                | $45 – $65                        |

### Loop B — Air Variable (15 m + 12 m + 10 m)

| Parameter           | Value                            |
|---------------------|----------------------------------|
| Type                | Air variable, single-section     |
| Capacitance range   | 10 – 50 pF                      |
| Required range      | 13.4 – 24.8 pF                  |
| Plate spacing       | ≥ 1.5 mm                        |
| Voltage rating      | ≈ 2 000 V                        |
| Estimated Q         | 2 000                            |
| Cost                | $20 – $35                        |

### Stray Capacitance

At 10 m (C = 13.4 pF), stray capacitance (2–5 pF) is significant.
Keep leads from loop ends to capacitor < 15 mm. Use wide copper strap.

### Tuning Drives

Both capacitors need **6:1 vernier reduction drives**. The narrowest
bandwidth is 13.6 kHz on 20 m — bare-shaft tuning is unusable at this
scale.

---

## 7. Coupling Loops

Each loop has its own coupling loop. Dimensions are identical.

| Parameter            | Value (each)                  |
|----------------------|-------------------------------|
| Diameter             | 160 mm (6.3")                 |
| Ratio to main loop   | 1 : 5                         |
| Material             | 3/8" soft copper tube         |
| Connector            | SO-239 chassis mount          |
| Position             | Bottom of each main loop      |

### Switching

An **SP3T** coaxial switch at the base selects which loop feeds the
radio:
- Position 1: Loop A (20 m, 17 m)
- Position 2: Loop B (15 m, 12 m, 10 m)
- Position 3: Bypass / Off

At 10 W, a standard SO-239-based coax switch is adequate. No high-power
relay needed.

---

## 8. Physical Layout

### Stacked Coaxial Configuration

Both loops are **the same diameter (0.80 m)** and mounted coaxially
on the same mast, separated vertically by 150–200 mm. This keeps the
antenna footprint identical to a single-loop design.

```
           ┌────────[Butterfly Cap + Vernier]────────┐
           │                                          │
           │           LOOP A (20m, 17m)              │
           │           D = 0.80 m                     │
           │           High-Q butterfly               │
           │                                          │
           │          ┌──[Coupling A]──┐              │
           └────┐     │   160 mm       │     ┌────────┘
                │     └───────┬────────┘     │
                └─────────────┼──────────────┘
                              │
                     150-200 mm spacing
                              │
           ┌────────[Air Var Cap + Vernier]───────────┐
           │                                          │
           │           LOOP B (15m, 12m, 10m)         │
           │           D = 0.80 m                     │
           │           Standard air variable          │
           │                                          │
           │          ┌──[Coupling B]──┐              │
           └────┐     │   160 mm       │     ┌────────┘
                │     └───────┬────────┘     │
                └─────────────┼──────────────┘
                              │
                         ─────┼───── Nylon U-bolt clamps
                              │
                         ┌────┴────┐
                         │  PVC    │  1" Schedule 40 PVC
                         │  mast   │  or wooden dowel
                         │  1.0 m  │
                         └────┬────┘
                              │
                        ──────┴────── PVC cross base
                                      or camera tripod
```

### Mutual Coupling Consideration

Two coaxial loops at 150–200 mm spacing will have some mutual
inductance. However, **only one loop is active at a time** — the
inactive loop is disconnected by the coax switch and its coupling loop
presents a high impedance. The inactive main loop is open-circuit at
the capacitor gap, so it does not form a resonant circuit and coupling
is minimal.

If slight detuning is observed, increase spacing to 250 mm or offset
the inactive loop 10–15° in rotation.

---

## 9. Mechanical Specifications

| Dimension                | Value                        |
|--------------------------|------------------------------|
| Overall height           | ≈ 1.25 m (with mast + base) |
| Overall width            | 0.80 m (31.5")              |
| Loop A weight            | 0.29 kg                      |
| Loop B weight            | 0.29 kg                      |
| Coupling loops (×2)      | 0.12 kg                      |
| Hardware + caps          | ≈ 0.5 kg                     |
| **Total weight**         | **≈ 1.2 kg (2.6 lb)**       |
| Tube length (main ×2)    | 5.10 m (16.7 ft)            |
| Tube length (coupling ×2)| 1.10 m (3.6 ft)             |
| **Total tube**           | **6.20 m (20.3 ft)**        |

---

## 10. Bill of Materials

| # | Item | Qty | Est. Cost |
|---|------|-----|-----------|
| 1 | 3/8" soft copper tube Type L, 25 ft | 1 | $30 |
| 2 | Butterfly split-stator 2×100 pF (Loop A) | 1 | $55 |
| 3 | Air variable capacitor 10–50 pF (Loop B) | 1 | $25 |
| 4 | 6:1 vernier reduction drive | 2 | $40 |
| 5 | SO-239 chassis-mount connector | 2 | $6 |
| 6 | SP3T coax switch | 1 | $12 |
| 7 | 56 % silver solder + flux | 1 | $15 |
| 8 | 1" PVC pipe + fittings | 1 set | $12 |
| 9 | ABS project box (×2) | 2 | $8 |
| 10 | Nylon U-bolts, zip ties, hardware | 1 set | $7 |
| | | **Total** | **$210** |

| Upgrade path | Cost delta | New total |
|--------------|------------|-----------|
| Both loops butterfly Q=5000 (replace #3 with butterfly) | +$30 | $240 |
| Both loops butterfly Q=7000 (premium caps) | +$80 | $290 |
| Stepper motor remote tune (×2) | +$50 | $260–$340 |
| Camera tripod adapter | +$8 | $218–$348 |

---

## 11. Construction Guide

### Step 1 — Form Two Main Loops

1. Cut two lengths of 2.55 m (8.4 ft) from 3/8" soft copper tube
2. Fill each with fine dry sand, plug ends
3. Bend each into a 0.80 m diameter circle:
   - Mark centre at 1.275 m — this is the bottom of the loop
   - Use a plywood disc (0.80 m) or 5-gallon bucket as form
4. Leave **15–20 mm gap** at the top of each loop
5. Empty sand, clean, tin ends with 56 % silver solder

### Step 2 — Form Two Coupling Loops

1. Cut two lengths of 0.55 m (22") from 3/8" tube
2. Bend each into 160 mm diameter circles
3. Leave 10–15 mm gap, clean and tin

### Step 3 — Solder Connections

1. Each coupling loop → its own SO-239
2. Each main loop → its capacitor (copper strap or direct solder)
3. All joints: 56 % silver solder

### Step 4 — Mount on Mast

1. Mount Loop A at top of mast
2. Mount Loop B 150–200 mm below Loop A
3. Both loops coaxial, coplanar (same orientation)
4. Nylon U-bolts at 2 points per loop
5. Install vernier drives on both capacitors
6. Route both coax lines down the mast to the SP3T switch

### Step 5 — Wire the Switch

```
Loop A (SO-239) ──── coax ──── SP3T pos 1 ─┐
                                             ├── common ── to radio
Loop B (SO-239) ──── coax ──── SP3T pos 2 ─┘
                               SP3T pos 3 ── (open / dummy load)
```

### Step 6 — Test and Calibrate

1. Connect NanoVNA to the common port
2. Select Loop A (pos 1), sweep 14–18.2 MHz
   - Verify 20 m and 17 m resonances
   - Adjust coupling loop A for SWR < 1.5:1
3. Select Loop B (pos 2), sweep 21–30 MHz
   - Verify 15 m, 12 m, 10 m resonances
   - Adjust coupling loop B for SWR < 1.5:1
4. Mark tuning dial positions for each band

---

## 12. Operating Notes

### Quick-Start

1. Flip SP3T to select band group (A or B)
2. Set radio to frequency, low power (1–2 W), carrier
3. Turn the appropriate vernier knob — watch SWR meter
4. Find the sharp dip, fine-tune, increase to operating power (max 10 W)

### Bandwidth and Retuning

| Band | BW (kHz) | Retune interval |
|------|----------|-----------------|
| 20 m | 13.6 | Every 10–12 kHz |
| 17 m | 19.6 | Covers most of band |
| 15 m | 31.6 | Every 25 kHz |
| 12 m | 46.7 | Covers full band |
| 10 m | 70.2 | Every 50–70 kHz |

### Capacitor Voltage Safety

| Band | Vc (V) |
|------|--------|
| 20 m | 1 584 |
| 17 m | 1 631 |
| 15 m | 1 426 |
| 12 m | 1 378 |
| 10 m | 1 298 |

- **Maximum voltage: 1 631 V** on 17 m (Loop A, butterfly)
- Butterfly cap voltage rating ~3 500 V effective — adequate margin
- Air variable cap voltage rating ~2 000 V — adequate for Loop B
- Never touch loop top or capacitor while transmitting
- Keep 0.5 m clearance from all loop surfaces during TX

---

## 13. Heat Dissipation

| Band | η (%) | P_radiated (W) | P_heat (W) |
|------|-------|----------------|------------|
| 20 m | 24.3 | 2.4 | 7.6 |
| 17 m | 42.0 | 4.2 | 5.8 |
| 15 m | 44.0 | 4.4 | 5.6 |
| 12 m | 56.8 | 5.7 | 4.3 |
| 10 m | 67.7 | 6.8 | 3.2 |

Worst case: 7.6 W on 20 m. Each loop has ~750 cm² copper surface area.
No thermal concerns at 10 W.

---

## 14. Design Validation

| Check | Criterion | Status |
|-------|-----------|--------|
| circ/λ range | 0.04 – 0.25 all bands | 0.119 – 0.242 OK |
| Max voltage | < cap voltage rating | 1 631 V < 3 500 V OK |
| Tube bend radius | > 38 mm | All bends >= 80 mm OK |
| Coupling loops | 160 mm, fits 3/8" tube | OK |
| Cap ranges | Cover required pF | Loop A: 34–56 pF, Loop B: 13–25 pF OK |
| Total weight | Manageable | 1.2 kg OK |
| Spacing | Loops don't interfere | 150–200 mm separation OK |

---

## 15. Comparison with Other 20m–10m Designs

| Aspect | ML20_10 (single) | **ML20_10_EFF (this)** | ML20_10_EFF (all Q=5k) |
|--------|-------------------|------------------------|------------------------|
| Loops | 1 | 2 | 2 |
| Loop diameter | 0.80 m | 0.80 m × 2 | 0.80 m × 2 |
| Width | 0.80 m | 0.80 m (same!) | 0.80 m |
| Height | 0.90 m | 1.25 m | 1.25 m |
| Switching | None | SP3T switch | SP3T switch |
| 20 m efficiency | 17.7 % | **24.3 %** (+37%) | 24.3 % |
| 17 m efficiency | 32.1 % | **42.0 %** (+31%) | 42.0 % |
| 15 m efficiency | 44.0 % | 44.0 % | **55.1 %** (+25%) |
| 12 m efficiency | 56.8 % | 56.8 % | **67.7 %** (+19%) |
| 10 m efficiency | 67.7 % | 67.7 % | **77.2 %** (+14%) |
| Average efficiency | 43.7 % | **46.9 %** | **53.3 %** |
| Improvement | baseline | **+0.7 dB avg** | **+2.2 dB avg** |
| Weight | 0.7 kg | 1.2 kg | 1.2 kg |
| Cost | $97 | $210 | $240 |

### Why Not a Larger Loop?

The loop diameter is constrained to 0.80 m to keep circ/λ ≤ 0.25 at
29.7 MHz. Making the loop larger would exceed this limit on 10 m and
the antenna would no longer behave as a proper magnetic loop (coupling
becomes capacitive, pattern distorts).

### Why Not Three Loops?

Diminishing returns. Splitting 20 m and 17 m into separate loops
(each with its own butterfly cap) would gain only ~2 % on 20 m because
the fundamental limit is the copper loss — the loop simply doesn't
radiate well at circ/λ = 0.12 regardless of capacitor quality.

---

## 16. Upgrade Paths

### Path A — All-Butterfly (Recommended First Upgrade)

Replace the air variable on Loop B with a butterfly (Q=5000).
Cost: +$30. Gain: +2.2 dB average, with 15 m jumping from 44 % to 55 %.

### Path B — Premium Capacitors (Maximum Performance)

Both loops with premium butterfly caps (Q=7000).
Cost: +$80 over base. Gain: +2.7 dB average over single-loop baseline.

### Path C — Add 6 m

Add a third 0.44 m loop below Loop B for 6 m coverage, creating a
3-loop system with the same width. See ML20_6 design for the 0.44 m
loop specifications.

### Path D — Remote Tuning

Add stepper motors + Arduino on both vernier drives. Essential if the
antenna is mounted on a mast above head height, since body proximity
detunes the loop.

---

*Design: ML20_10_EFF | 3/8" copper tube | dual 0.80 m loops | 10 W | 20 m – 10 m | efficiency optimised*
*Generated: 2026-02-07*
