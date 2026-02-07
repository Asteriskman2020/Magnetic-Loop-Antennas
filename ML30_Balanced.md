# ML30_Balanced — Magnetic Loop Antenna: 30 m Band (Balanced Size & Efficiency)

> **2-turn design | 1.00 m diameter | 3/8" copper tube | 10 W max | 30 m only**

---

## 1. Design Overview

A magnetic loop antenna for the 30 m band (10.100–10.150 MHz) that
**balances physical size against efficiency**. A 1.00 m (39.4") loop
is compact enough to fit through doorways, set up on a balcony, and
transport in a car — yet large enough to deliver useful radiation
when combined with a 2-turn series configuration and a high-Q
butterfly capacitor.

| Parameter          | Value                                       |
|--------------------|---------------------------------------------|
| Band coverage      | 30 m only (10.100 – 10.150 MHz)             |
| Max power          | 10 W                                        |
| Loop diameter      | **1.00 m** (39.4")                          |
| Number of turns    | **2** (series-connected)                    |
| Turn spacing       | 80 mm centre-to-centre                      |
| Radiator material  | 3/8" (9.525 mm OD) soft copper tube Type L  |
| Coupling loop      | 3/8" soft copper tube, 170 mm diameter       |
| Tuning capacitor   | Butterfly split-stator (Q ≈ 5 000)          |
| Band switching     | **None** — single band                      |

### Where This Design Sits

| Design | Diameter | η (Q=5k) | Size class |
|--------|----------|----------|------------|
| ML30_SmallSize | 0.60 m | 9.4 % | Backpack portable |
| **ML30_Balanced (this)** | **1.00 m** | **26.3 %** | **Apartment / balcony** |
| ML30_EFF_1Loop | 2.00 m | 60.5 % | Garden / field station |

The 1.00 m loop sits at the geometric midpoint of the design family.
It is 3× more efficient than the small design and half the width of
the large one.

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

## 3. Electrical Parameters

### Single-Turn Constants (each turn)

| Parameter    | Value         |
|--------------|---------------|
| Diameter     | 1.00 m        |
| Radius R     | 0.50 m        |
| Circumference| 3.142 m       |
| Area A       | 0.7854 m²     |
| Inductance L | **2.975 μH**  |

```
L = μ₀ × 0.50 × [ln(8 × 0.50 / 0.004763) − 2]
  = 6.283e-7 × [ln(840.2) − 2]
  = 6.283e-7 × [6.734 − 2]
  = 6.283e-7 × 4.734
  = 2.975 μH
```

### 2-Turn Combined Parameters

Two coaxial turns at 80 mm spacing: M ≈ 1.21 μH (k = 0.41).

| Parameter              | Value        | Derivation                   |
|------------------------|--------------|------------------------------|
| Self-inductance (each) | 2.975 μH     | L = μ₀R[ln(8R/a) − 2]       |
| Mutual inductance M    | 1.21 μH      | Neumann formula, d = 80 mm   |
| **Total inductance**   | **8.37 μH**  | L_tot = 2L + 2M              |
| Effective turns        | N = 2        |                              |
| Rr (radiation)         | 100.0 mΩ     | 31171 × (2A/λ²)²            |
| Rl (copper loss)       | 174.2 mΩ     | 2 × Rl_single                |

```
Rr = 31171 × (2 × 0.7854 / 29.61²)²
   = 31171 × (1.5708 / 877.2)²
   = 31171 × (1.791e-3)²
   = 31171 × 3.208e-6
   = 100.0 mΩ

Rs = √(π × 10.125e6 × μ₀ / σ) = 8.30e-4 Ω/sq
Rl_per_turn = 8.30e-4 × 3.142 / (π × 0.009525) = 87.1 mΩ
Rl_total = 2 × 87.1 = 174.2 mΩ
```

---

## 4. Performance

### 4.1 At Band Centre (10.125 MHz)

| Cap Q | Rc (mΩ) | R_total (mΩ) | η (%) | Vc (V) | BW (kHz) | Q_L |
|-------|---------|--------------|-------|--------|----------|-----|
| 2 000 | 266.1 | 540.3 | **18.5** | 2 290 | 10.3 | 985 |
| 3 000 | 177.4 | 451.6 | **22.1** | 2 504 | 8.6 | 1 179 |
| 5 000 | 106.4 | 380.6 | **26.3** | 2 727 | 7.2 | 1 399 |
| 7 000 | 76.0 | 350.2 | **28.6** | 2 843 | 6.7 | 1 520 |
| ∞     | 0      | 274.2 | **36.5** | 3 215 | 5.2 | 1 941 |

```
X_L = 2π × 10.125e6 × 8.37e-6 = 532.2 Ω
C   = 1 / (4π² × 10.125e6² × 8.37e-6) = 29.7 pF

Example (Q = 5000):
  Rc = 532.2 / 5000 = 106.4 mΩ
  R_total = 100.0 + 174.2 + 106.4 = 380.6 mΩ
  η = 100.0 / 380.6 = 26.3 %
  Vc = √(10 / 0.381) × 532.2 = 5.12 × 532.2 = 2 727 V
  Q_L = 532.2 / 0.381 = 1 397
  BW = 10.125e6 / 1397 = 7.2 kHz
```

### 4.2 Across the 30 m Band (Q = 5 000)

| Frequency (MHz) | C (pF) | Rr (mΩ) | Rl (mΩ) | η (%) | Vc (V) |
|------------------|--------|---------|---------|-------|--------|
| 10.100 | 29.8 | 99.1 | 173.9 | 26.1 | 2 726 |
| 10.125 | 29.7 | 100.0 | 174.2 | 26.3 | 2 727 |
| 10.150 | 29.5 | 101.0 | 174.4 | 26.4 | 2 727 |

Efficiency is flat (±0.2 %). Cap swing: **0.3 pF**.

### 4.3 Single-Turn Comparison

| Approach | η (Q=5k) | Vc (V) | Complexity |
|----------|----------|--------|------------|
| 1-turn 1.00 m Q=5000 | 16.7 % | 1 545 | Simplest |
| **2-turn 1.00 m Q=5000 (this)** | **26.3 %** | **2 727** | Series jumper |
| 1-turn 1.00 m Q=∞ | 22.3 % | — | Theoretical |
| 2-turn 1.00 m Q=∞ | 36.5 % | — | Theoretical |

The 2-turn design at Q=5000 **exceeds** what a single-turn loop can
achieve even with a perfect lossless capacitor (22.3 %). The penalty
is higher voltage (2 727 V vs 1 545 V), comfortably within butterfly
cap range.

---

## 5. Effective Radiated Power (ERP)

Directivity = 1.5 (1.76 dBi). Input = 10 W.

| Configuration | η (%) | P_rad (W) | ERP (W) |
|---------------|-------|-----------|---------|
| 1-turn 1.00 m Q=5k | 16.7 | 1.7 | 2.5 |
| **2-turn 1.00 m Q=5k** | **26.3** | **2.6** | **3.9** |
| 2-turn 1.00 m Q=7k | 28.6 | 2.9 | 4.3 |

> At 3.9 W ERP, this antenna is capable of worldwide DX on FT8/CW
> and solid regional SSB contacts on 30 m. Not a contest antenna, but
> a reliable everyday performer from a 1 m footprint.

---

## 6. Tuning Capacitor

### Required Capacitance

| Edge | Frequency | C required |
|------|-----------|------------|
| Low  | 10.100 MHz | 29.8 pF   |
| High | 10.150 MHz | 29.5 pF   |
| **Swing** | | **0.3 pF** |

### Recommended: Butterfly Split-Stator

| Parameter           | Value                            |
|---------------------|----------------------------------|
| Type                | Butterfly split-stator 2×50 pF   |
| Effective range     | 0 – 25 pF (series)              |
| Plate spacing       | ≥ 1.5 mm (4 500 V effective)    |
| Voltage rating      | ≥ 3 000 V effective              |
| Estimated Q         | 5 000                            |
| Cost                | $50 – $65                        |

A butterfly cap is the right choice here because:
1. The 2-turn topology produces 2 727 V — needs ≥ 3 kV cap rating
2. Butterfly with 1.5 mm spacing provides ~4 500 V effective — good margin
3. High Q (5 000) is important since capacitor loss is a significant
   fraction of total loss at this loop size

### Tuning Drive

A **10:1 vernier reduction drive** is essential. With 0.3 pF swing,
tuning sensitivity is extreme. The 10:1 ratio provides the resolution
needed.

### Alternative: Fixed + Trimmer (Budget)

| Component | Value |
|-----------|-------|
| Fixed C0G/NP0 | 27 pF, ≥ 3 kV rating |
| Air trimmer | 1–10 pF |

This works at ~$11 vs $65 for a butterfly. However, finding a 3 kV
rated C0G capacitor at 27 pF may require ordering from specialty
suppliers (Vishay, AVX, Murata high-voltage series).

---

## 7. Coupling Loop

| Parameter            | Value                         |
|----------------------|-------------------------------|
| Diameter             | **170 mm** (6.7")             |
| Ratio to main loop   | 1 : 5.9                       |
| Material             | 3/8" soft copper tube         |
| Tube length          | ≈ 0.60 m (incl. pigtails)    |
| Connector            | SO-239 chassis mount          |
| Position             | Bottom of lower turn          |

The 2-turn loop has higher total impedance than a single turn. The
coupling loop is sized at 170 mm (smaller than the standard 200 mm
for single-turn 1.00 m) to maintain a 50 Ω match.

### Fine-Tuning

1. Start with 170 mm coupling loop, centred at the bottom
2. Rotate ±15° off-axis or slide ±25 mm to minimise SWR
3. Target: SWR < 1.5:1 at resonance

---

## 8. Physical Layout

### Construction Diagram

```
          ┌── [Butterfly cap + 10:1 vernier] ──┐
          │                                      │
     ┌────┘     Turn 1 (top)                └────┐
    │            D = 1.00 m                       │
    │            3/8" Cu tube                     │
     └────┐                                 ┌────┘
          │                                  │
          ├──── Cu jumper (80 mm) ───────────┤
          │                                  │
     ┌────┘     Turn 2 (bottom)             └────┐
    │            D = 1.00 m                       │
    │            3/8" Cu tube                     │
     └────┐                                 ┌────┘
          │       ┌──────┐                   │
          │       │ C/L  │                   │
          │       │170mm │                   │
          │       └──┬───┘                   │
          └──────────┼───────────────────────┘
                     │
                  SO-239
                     │
                ─────┼───── Nylon U-bolt clamps
                     │
                ┌────┴────┐
                │  PVC    │  1" Schedule 40
                │  mast   │  0.8 m
                └────┬────┘
                     │
               ──────┴────── PVC cross base
                              or camera tripod
```

### Physical Envelope

The entire antenna occupies a **1.00 m × 1.00 m × 1.10 m** volume
(width × depth × height including short mast).

- Fits through standard doorways (typical 0.81 m) — angle slightly
- Fits flat in a car boot or back seat
- One person can carry and set up in < 10 minutes

---

## 9. Mechanical Specifications

| Dimension                | Value                        |
|--------------------------|------------------------------|
| Overall width            | 1.00 m (39.4")              |
| Overall height           | ≈ 1.10 m (with mast)        |
| Coil stack height        | ~90 mm (2 turns + gap)       |
| Turn 1 weight            | 0.37 kg                      |
| Turn 2 weight            | 0.37 kg                      |
| Coupling loop            | 0.07 kg                      |
| Hardware + cap            | ≈ 0.3 kg                     |
| **Total weight**         | **≈ 1.1 kg (2.4 lb)**       |
| Tube: turn 1             | 3.20 m                       |
| Tube: turn 2             | 3.20 m                       |
| Tube: coupling           | 0.60 m                       |
| Tube: jumper             | 0.10 m                       |
| **Total tube**           | **7.10 m (23.3 ft)**        |

---

## 10. Bill of Materials

| # | Item | Qty | Est. Cost |
|---|------|-----|-----------|
| 1 | 3/8" soft copper tube Type L, 25 ft | 1 | $35 |
| 2 | Butterfly split-stator 2×50 pF | 1 | $55 |
| 3 | 10:1 vernier reduction drive | 1 | $22 |
| 4 | SO-239 chassis-mount connector | 1 | $3 |
| 5 | 56 % silver solder + flux | 1 | $15 |
| 6 | 1" PVC pipe + fittings | 1 set | $10 |
| 7 | ABS project box | 1 | $4 |
| 8 | Nylon U-bolts, zip ties, hardware | 1 set | $5 |
| | | **Total** | **$149** |

| Budget option | Replace | Delta | Total |
|---------------|---------|-------|-------|
| Fixed 27 pF + trimmer | items 2+3 | −$66 | $83 |

| Upgrade | Delta | New total |
|---------|-------|-----------|
| Premium butterfly Q=7000 | +$20 | $169 |
| Camera tripod adapter | +$8 | $157 |
| Stepper motor remote tune | +$25 | $174 |

---

## 11. Construction Guide

### Step 1 — Form Two 1.00 m Loops

1. Cut two lengths of 3.20 m (10.5 ft) from 3/8" soft copper tube
2. Fill each with fine dry sand, plug ends
3. Bend each into a 1.00 m diameter circle:
   - Mark centre at 1.60 m
   - Use a plywood disc or draw circle on flat surface as guide
   - Work gradually from centre outward
4. Leave 15 mm gap at top of each loop
5. Empty sand, clean and tin all four tube ends

### Step 2 — Form the Coupling Loop

1. Cut 0.60 m of 3/8" tube
2. Bend into a 170 mm circle (paint can as form)
3. Leave 10–15 mm gap, clean and tin

### Step 3 — Series Connection

1. Stack the two loops coaxially, 80 mm apart
2. On one side, solder an 80 mm copper jumper between the bottom end
   of Turn 1 and the top end of Turn 2
3. Use PVC spacer blocks (2 places) to hold 80 mm gap
4. The remaining ends connect to the butterfly cap
5. All joints: 56 % silver solder

### Step 4 — Assemble

1. Mount butterfly cap in ABS project box at loop top
2. Install 10:1 vernier drive
3. Attach 2-turn assembly to PVC mast (nylon U-bolts, 2 points)
4. Position coupling loop at bottom of Turn 2, centred
5. Route coax from SO-239 down the mast

### Step 5 — Test

1. Connect NanoVNA, sweep 9.5–10.7 MHz
2. Adjust butterfly cap to place resonance at 10.125 MHz
3. Adjust coupling loop position for SWR < 1.5:1
4. Mark dial position — the entire 30 m band fits within ~2–3 small
   turns of the vernier knob

---

## 12. Operating Notes

### Bandwidth and Coverage

| Cap Q | BW (kHz) | Positions for full 50 kHz |
|-------|----------|---------------------------|
| 2 000 | 10.3 | 5 |
| 5 000 | 7.2 | 7 |
| 7 000 | 6.7 | 7–8 |

With 7 kHz bandwidth (Q=5000), about 7 tuning positions cover the
entire 30 m allocation. For FT8 (centred at 10.136 MHz), one position
covers the entire FT8 window.

### Voltage Safety

| Cap Q | Vc (V) | Cap rating |
|-------|--------|------------|
| 5 000 | 2 727 | 4 500 V butterfly OK |
| 7 000 | 2 843 | 4 500 V butterfly OK |

- Butterfly cap with 1.5 mm plate spacing = ~4 500 V effective rating
- Adequate margin (2 727 V / 4 500 V = 61 % of rating)
- **Never touch** the loop top, capacitor, or jumper while transmitting
- Maintain 0.5 m clearance during TX

### Heat Dissipation

| Cap Q | η (%) | P_radiated (W) | P_heat (W) |
|-------|-------|----------------|------------|
| 5 000 | 26.3 | 2.6 | 7.4 |
| 7 000 | 28.6 | 2.9 | 7.1 |

At 10 W, worst case is 7.4 W dissipated over ~1 900 cm² of copper
surface (two turns). No thermal concerns.

### What Can You Work?

| Mode | Typical minimum | This antenna (ERP) | Reach |
|------|----------------|-------------------|-------|
| FT8/FT4 | 0.5 W | 3.9 W | **Worldwide DX** |
| CW | 1–3 W | 3.9 W | **Continental DX** |
| WSPR | 0.1 W | 3.9 W | **Worldwide** |
| SSB | 5–10 W | 3.9 W | **Regional (500–2000 km)** |
| JS8Call | 0.5 W | 3.9 W | **Worldwide** |

> **Summary:** This antenna is a solid everyday performer on 30 m.
> It won't win contests but it will reliably make contacts from a
> balcony, apartment, park, or field day site.

---

## 13. Design Validation

| Check | Criterion | Status |
|-------|-----------|--------|
| circ/λ | 0.04 – 0.25 | 0.106 OK |
| Max voltage | < cap rating | 2 843 V < 4 500 V OK |
| Tube bend radius | > 38 mm | All bends = 500 mm OK |
| Coupling loop | 170 mm, fits 3/8" tube | OK |
| Cap range | Covers 30 m band | 29.5–29.8 pF OK |
| Total weight | Manageable one-hand | 1.1 kg OK |
| Fits through door | Width < 1.0 m | 1.00 m (slight angle) OK |

---

## 14. Full Design Family Comparison (30 m)

| | SmallSize | **Balanced (this)** | EFF 2-turn | EFF 1-Loop |
|-|-----------|---------------------|------------|------------|
| **Diameter** | 0.60 m | **1.00 m** | 1.60 m | 2.00 m |
| **Turns** | 3 | **2** | 2 | 1 |
| **η (Q=5k)** | 9.4 % | **26.3 %** | 58.1 % | 60.5 % |
| **ERP** | 1.4 W | **3.9 W** | 8.7 W | 9.1 W |
| **Vc** | 1 741 V | **2 727 V** | 2 889 V | 1 688 V |
| **Weight** | 1.0 kg | **1.1 kg** | 1.68 kg | 1.18 kg |
| **Cost** | $81–142 | **$83–149** | $108 | $93 |
| **Portable** | Backpack | **Car / carry** | Awkward | Difficult |
| **Setup** | 1 person | **1 person** | 1 person | 2 people |
| **FT8 DX** | Workable | **Good** | Excellent | Excellent |
| **SSB DX** | Regional | **Regional** | Good | Good |
| **Best for** | Hiking/POTA | **Apartment/balcony** | Fixed QTH | Fixed QTH |

---

## 15. Scaling Options

If you can spare a bit more space, every extra 10 cm of diameter helps:

| Diameter | Turns | η (Q=5k) | ERP | Gain vs 1.00 m |
|----------|-------|----------|-----|-----------------|
| 0.80 m | 2 | 16.4 % | 2.5 W | −2.0 dB |
| **1.00 m** | **2** | **26.3 %** | **3.9 W** | **baseline** |
| 1.10 m | 2 | 31.2 % | 4.7 W | +0.8 dB |
| 1.20 m | 2 | 37.3 % | 5.6 W | +1.5 dB |
| 1.20 m | 1 | 25.5 % | 3.8 W | −0.1 dB |

> If you can fit 1.20 m: the 2-turn version gives 37 % efficiency
> (+1.5 dB), a worthwhile gain for just 20 cm more diameter.

---

*Design: ML30_Balanced | 3/8" copper tube | 2-turn 1.00 m | 10 W | 30 m only | balanced size & efficiency*
*Generated: 2026-02-07*
