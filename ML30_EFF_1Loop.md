# ML30_EFF_1Loop — Magnetic Loop Antenna: 30 m Band (Single Loop, Efficiency Optimised)

> **Single-loop design | 2.00 m diameter | 3/8" copper tube | 10 W max | 30 m only**

---

## 1. Design Overview

A single-loop magnetic loop antenna optimised for maximum efficiency on
the 30 m band (10.100–10.150 MHz). The key optimisation lever for a
single loop is **maximising loop diameter** — radiation resistance
scales as diameter⁴ while copper loss scales only as diameter¹.
A 2.00 m (78.7") loop delivers 60.5 % efficiency with a Q=5000
butterfly capacitor — excellent for a single-turn design.

| Parameter          | Value                                       |
|--------------------|---------------------------------------------|
| Band coverage      | 30 m only (10.100 – 10.150 MHz)             |
| Max power          | 10 W                                        |
| Loop diameter      | **2.00 m** (78.7")                          |
| Number of turns    | **1**                                       |
| Radiator material  | 3/8" (9.525 mm OD) soft copper tube Type L  |
| Coupling loop      | 3/8" soft copper tube, 400 mm diameter       |
| Tuning capacitor   | Fixed C0G/NP0 + air trimmer (or butterfly)  |
| Band switching     | **None** — single band                      |

### Why 2.00 m?

For maximum efficiency, the loop should be as large as possible while
keeping circ/λ ≤ 0.25. At 10.15 MHz, the absolute maximum is D = 2.35 m.
A 2.00 m loop gives circ/λ = 0.212 — well within the optimal range and
the largest practical diameter that one person can transport and set up.

### Why Diameter Matters So Much

| Diameter | circ/λ | η (Q=5k) | η (Q=∞) | Vc (V) |
|----------|--------|----------|---------|--------|
| 0.80 m | 0.085 | 9.2 % | 12.7 % | 1 544 |
| 1.00 m | 0.106 | 17.2 % | 24.9 % | 1 570 |
| 1.20 m | 0.128 | 27.0 % | 36.9 % | 1 617 |
| 1.40 m | 0.149 | 36.3 % | 46.8 % | 1 658 |
| 1.60 m | 0.170 | 44.3 % | 54.0 % | 1 730 |
| 1.80 m | 0.191 | 53.1 % | 62.9 % | 1 718 |
| **2.00 m** | **0.212** | **60.5 %** | **69.7 %** | **1 688** |
| 2.20 m | 0.233 | 67.0 % | 75.4 % | 1 642 |
| 2.35 m | 0.249 | 71.1 % | 78.8 % | 1 601 |

> **Key insight:** Doubling the diameter from 1.00 m to 2.00 m raises
> efficiency from 17 % to 60 % — a factor of 3.5×, or +5.5 dB.
> No capacitor upgrade can achieve this. Size is king.

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

### Loop Constants

| Parameter    | Value         |
|--------------|---------------|
| Diameter     | 2.00 m        |
| Radius R     | 1.00 m        |
| Circumference| 6.283 m       |
| Area A       | 3.142 m²      |
| Inductance L | **6.822 μH**  |

```
L = μ₀ × R × [ln(8R/a) − 2]
  = 1.2566e-6 × 1.00 × [ln(8 × 1.00 / 0.004763) − 2]
  = 1.2566e-6 × [ln(1680) − 2]
  = 1.2566e-6 × 5.426
  = 6.822 μH
```

### At Band Centre (10.125 MHz)

| Quantity         | Value    | Derivation                          |
|------------------|----------|-------------------------------------|
| λ                | 29.61 m  | c / f                               |
| circ/λ           | 0.212    | 6.283 / 29.61                       |
| X_L              | 433.9 Ω  | 2πfL                                |
| C (resonant)     | 36.4 pF  | 1 / (4π²f²L)                       |
| Rr (radiation)   | 400.2 mΩ | 31171 × (A/λ²)²                    |
| Rs (skin effect) | 0.830 mΩ/sq | √(πfμ₀/σ)                       |
| Rl (copper loss) | 174.2 mΩ | Rs × circ / (π × OD)               |
| Rr/Rl ratio      | **2.30**  | Favourable — Rr dominates          |

```
Rr = 31171 × (3.142 / 29.61²)²
   = 31171 × (3.142 / 877.2)²
   = 31171 × (3.583e-3)²
   = 31171 × 1.284e-5
   = 400.2 mΩ

Rl = √(π × 10.125e6 × 1.2566e-6 / 5.8e7) × 6.283 / (π × 0.009525)
   = 8.302e-4 × 209.8
   = 174.2 mΩ
```

---

## 4. Performance

### 4.1 Efficiency vs Capacitor Quality (at 10.125 MHz)

| Cap Q | Rc (mΩ) | R_total (mΩ) | η (%) | Vc (V) | BW (kHz) | Q_L |
|-------|---------|--------------|-------|--------|----------|-----|
| 1 000 | 433.9 | 1 008.3 | **39.7** | 1 365 | 24.5 | 413 |
| 2 000 | 217.0 | 791.4 | **50.6** | 1 542 | 18.5 | 549 |
| 3 000 | 144.6 | 719.0 | **55.7** | 1 618 | 16.8 | 604 |
| 5 000 | 86.8 | 661.2 | **60.5** | 1 688 | 15.4 | 656 |
| 7 000 | 62.0 | 636.4 | **62.9** | 1 720 | 14.8 | 682 |
| 10 000 | 43.4 | 617.8 | **64.8** | 1 747 | 14.4 | 702 |
| ∞     | 0      | 574.4 | **69.7** | 1 811 | 13.2 | 755 |

```
Example (Q = 5000):
  Rc = 433.9 / 5000 = 86.8 mΩ
  R_total = 400.2 + 174.2 + 86.8 = 661.2 mΩ
  η = 400.2 / 661.2 = 60.5 %
  Vc = √(10 / 0.6612) × 433.9 = 3.889 × 433.9 = 1 688 V
  Q_L = 433.9 / 0.6612 = 656
  BW = 10.125e6 / 656 = 15.4 kHz
```

### 4.2 Across the 30 m Band (Q = 5 000)

| Frequency (MHz) | C (pF) | Rr (mΩ) | Rl (mΩ) | Rc (mΩ) | η (%) | Vc (V) |
|------------------|--------|---------|---------|---------|-------|--------|
| 10.100 | 36.5 | 396.5 | 173.9 | 86.6 | 60.4 | 1 688 |
| 10.125 | 36.4 | 400.2 | 174.2 | 86.8 | 60.5 | 1 688 |
| 10.150 | 36.3 | 404.2 | 174.4 | 87.0 | 60.7 | 1 688 |

**Efficiency is flat across the entire 50 kHz band (±0.2 %).**

Capacitance swing: 36.3 – 36.5 pF (**only 0.2 pF**).

### 4.3 Comparison: Effect of Loop Size (single turn, Q = 5 000)

| Loop diameter | Rr (mΩ) | Rl (mΩ) | Rc (mΩ) | η (%) | Gain vs 0.80 m |
|---------------|---------|---------|---------|-------|----------------|
| 0.80 m | 10.2 | 69.6 | 28.8 | 9.4 | baseline |
| 1.00 m | 24.7 | 87.1 | 35.9 | 16.7 | +2.5 dB |
| 1.60 m | 163.9 | 139.4 | 66.5 | 44.3 | +6.7 dB |
| **2.00 m** | **400.2** | **174.2** | **86.8** | **60.5** | **+8.1 dB** |
| 2.35 m (max) | 762.9 | 204.6 | 104.9 | 71.1 | +8.8 dB |

---

## 5. Effective Radiated Power (ERP)

Directivity = 1.5 (1.76 dBi). Input = 10 W.

| Configuration | η (%) | P_rad (W) | ERP (W) |
|---------------|-------|-----------|---------|
| 0.80 m Q=5000 | 9.4 | 0.9 | 1.4 |
| 1.60 m Q=5000 | 44.3 | 4.4 | 6.6 |
| **2.00 m Q=5000** | **60.5** | **6.1** | **9.1** |
| 2.00 m Q=7000 | 62.9 | 6.3 | 9.4 |
| 2.00 m Q=∞ | 69.7 | 7.0 | 10.5 |

> At 60 % efficiency, this antenna delivers 9.1 W ERP from 10 W input.
> On 30 m, that is sufficient for worldwide DX contacts via FT8/FT4 and
> competitive for SSB/CW regional work.

---

## 6. Tuning Capacitor

### Required Capacitance

| Edge | Frequency | C required |
|------|-----------|------------|
| Low  | 10.100 MHz | 36.5 pF   |
| High | 10.150 MHz | 36.3 pF   |
| **Swing** | | **0.2 pF** |

The 0.2 pF swing is too narrow for any practical variable capacitor
to tune reliably, even with a 10:1 vernier.

### Recommended: Fixed + Trimmer (Lowest Cost)

| Component | Value | Purpose |
|-----------|-------|---------|
| Fixed capacitor (C0G/NP0) | 33 pF | Baseline |
| Air trimmer | 1 – 10 pF | Fine tune to resonance |
| **Total at resonance** | **~36.4 pF** | Covers full band |

1. Solder a 33 pF C0G/NP0 ceramic capacitor across the loop gap
   (voltage rating ≥ 2 kV)
2. Add a 1–10 pF air trimmer in parallel
3. Adjust trimmer to centre resonance at 10.125 MHz
4. The trimmer provides far more range than the 0.2 pF needed

**C0G/NP0 capacitor Q** at 10 MHz: typically 3 000–10 000.
Combined with quality air trimmer, effective Q ≈ 5 000.

### Alternative: Butterfly Cap (Multi-Band Flexibility)

| Parameter           | Value                            |
|---------------------|----------------------------------|
| Type                | Butterfly split-stator 2×100 pF  |
| Effective range     | 0 – 50 pF (series)              |
| Plate spacing       | ≥ 1.0 mm (2 000 V eff. adequate)|
| Estimated Q         | 5 000                            |
| Cost                | $45 – $65                        |

A butterfly cap enables future multi-band use if combined with a relay
switching system. For 30 m only, the fixed+trimmer approach is simpler,
cheaper, and equally effective.

---

## 7. Coupling Loop

| Parameter            | Value                         |
|----------------------|-------------------------------|
| Diameter             | **400 mm** (15.7")            |
| Ratio to main loop   | 1 : 5                         |
| Circumference        | 1.257 m                       |
| Tube length required | ≈ 1.30 m (incl. pigtails)     |
| Material             | 3/8" soft copper tube         |
| Connector            | SO-239 chassis mount          |
| Position             | Bottom of main loop           |

### Fine-Tuning the Match

1. Start with 400 mm coupling loop centred at the bottom
2. Adjust SWR by rotating ±15° off-axis or sliding ±30 mm
3. Target: SWR < 1.5:1 at resonance
4. If SWR is too low, increase coupling loop diameter slightly
5. If SWR is too high, decrease or offset the coupling loop

---

## 8. Physical Layout

### Construction Diagram

```
                 ┌───[Cap box: 33 pF + trimmer]───┐
                 │                                  │
            ┌────┘                             └────┐
           │                                         │
          │           Main Loop                       │
          │           D = 2.00 m (78.7")              │
          │           3/8" copper tube                │
          │                                           │
           │                                         │
            └────┐                             ┌────┘
                 │       ┌──────────┐           │
                 │       │ Coupling │           │
                 │       │  loop    │           │
                 │       │ 400 mm   │           │
                 │       └────┬─────┘           │
                 └────────────┼─────────────────┘
                              │
                           SO-239
                              │
                         ─────┼───── Nylon clamps (3 pts)
                              │
                         ┌────┴────┐
                         │  PVC    │  1.5" Schedule 40
                         │  mast   │  1.2 m
                         └────┬────┘
                              │
                        ──────┴────── Heavy PVC base
                                      or ground stake
```

### Support Note

A 2.00 m loop is large — approximately the height of a door frame.
Three support points on the mast are recommended (top and two sides).
Use **1.5" PVC** or a wooden dowel for the mast. A heavy PVC cross
base or ground stake prevents tipping.

---

## 9. Mechanical Specifications

| Dimension                | Value                        |
|--------------------------|------------------------------|
| Overall width            | 2.00 m (78.7")              |
| Overall height           | ≈ 2.25 m (with mast + base) |
| Main loop weight         | 0.73 kg (1.6 lb)             |
| Coupling loop weight     | 0.15 kg (0.3 lb)             |
| Hardware + cap            | ≈ 0.3 kg                     |
| **Total weight**         | **≈ 1.18 kg (2.6 lb)**      |
| Tube: main loop          | 6.35 m (20.8 ft)             |
| Tube: coupling loop      | 1.30 m (4.3 ft)              |
| **Total tube**           | **7.65 m (25.1 ft)**        |

---

## 10. Bill of Materials

| # | Item | Qty | Est. Cost |
|---|------|-----|-----------|
| 1 | 3/8" soft copper tube Type L, 25 ft | 1 | $35 |
| 2 | Fixed C0G/NP0 33 pF, 2 kV | 1 | $5 |
| 3 | Air trimmer 1–10 pF | 1 | $6 |
| 4 | SO-239 chassis-mount connector | 1 | $3 |
| 5 | 56 % silver solder + flux | 1 | $15 |
| 6 | 1.5" PVC pipe + fittings + base | 1 set | $18 |
| 7 | ABS project box | 1 | $4 |
| 8 | Nylon U-bolts, zip ties, hardware | 1 set | $7 |
| | | **Total** | **$93** |

| Upgrade | Delta | New total |
|---------|-------|-----------|
| Butterfly cap (multi-band flex) | +$35 | $128 |
| Premium butterfly Q=7000 | +$65 | $158 |
| Stepper motor remote tune | +$25 | $118–$183 |
| 2.20 m loop (η +6.5 %) | +$5 tube | $98 |
| 2.35 m loop (η +10.6 %) | +$10 tube | $103 |

---

## 11. Construction Guide

### Step 1 — Form the Main Loop

1. Cut 6.35 m (20.8 ft) of 3/8" soft copper tube
2. Fill with fine dry sand, plug both ends with masking tape
3. Mark the centre point (3.175 m) — this will be the loop bottom
4. Bend into a 2.00 m diameter circle:
   - A large sheet of plywood with a 2.00 m circle drawn on it makes
     a good bending jig
   - Screw small wooden blocks along the circle line as guides
   - Work gradually from the centre outward, alternating sides
   - **Two people make this step much easier** — one holds, one bends
5. Leave a **15–20 mm gap** at the top
6. Empty sand, clean tube ends with 220-grit emery cloth
7. Tin tube ends with 56 % silver solder

### Step 2 — Form the Coupling Loop

1. Cut 1.30 m (4.3 ft) of 3/8" tube
2. Bend into a 400 mm diameter circle using a paint bucket as form
3. Leave 10–15 mm gap, clean and tin

### Step 3 — Install Capacitors

1. Solder the 33 pF C0G/NP0 capacitor directly across the gap
   - Keep leads as short as possible (< 10 mm)
   - Use wide copper strap from tube ends to cap terminals
2. Mount the air trimmer in the ABS project box
3. Wire the trimmer in parallel with the fixed cap
4. Total lead length from loop to caps: < 15 mm

### Step 4 — Solder Coupling Loop

1. Solder one tube end to SO-239 centre pin
2. Solder the other to SO-239 ground lug
3. Use 56 % silver solder for all joints

### Step 5 — Mount

1. Attach main loop to mast at 3 points (nylon U-bolts)
2. Position coupling loop at the exact bottom, centred and coplanar
3. Route coax from SO-239 down the mast

### Step 6 — Test and Tune

1. Connect NanoVNA, sweep 9.5–10.7 MHz
2. Adjust trimmer to place resonance at 10.125 MHz (band centre)
3. Check SWR — adjust coupling loop position for < 1.5:1
4. With 15 kHz bandwidth, the resonance covers a good portion of the
   50 kHz band from a single trimmer setting

---

## 12. Operating Notes

### Bandwidth and Coverage

| Cap Q | BW (kHz) | Positions for full band |
|-------|----------|-------------------------|
| 2 000 | 18.5 | 3 |
| 5 000 | 15.4 | 3–4 |
| 7 000 | 14.8 | 3–4 |

The 30 m band is only 50 kHz wide. With 15–18 kHz bandwidth, **just
3 trimmer adjustments** cover the entire allocation. Most operators
park on one frequency (e.g. 10.136 MHz for FT8) and never retune.

### Voltage Safety

| Cap Q | Vc (V) | Rating needed |
|-------|--------|---------------|
| 2 000 | 1 542 | ≥ 2 000 V |
| 5 000 | 1 688 | ≥ 2 000 V |
| 7 000 | 1 720 | ≥ 2 000 V |

- Voltages are **moderate** — a 2 kV rated C0G cap and air trimmer
  handle this comfortably
- Standard air variable capacitors (1.5 mm plate spacing ≈ 2 000 V)
  are also adequate
- No need for butterfly or vacuum caps from a voltage standpoint
- Still maintain 0.5 m clearance during TX — RF burns are painful
  even at 1 700 V

### Heat Dissipation

| Cap Q | η (%) | P_radiated (W) | P_heat (W) |
|-------|-------|----------------|------------|
| 2 000 | 50.6 | 5.1 | 4.9 |
| 5 000 | 60.5 | 6.1 | 3.9 |

At 10 W, worst case 4.9 W dissipated over ~1 900 cm² copper surface.
No thermal concerns.

### Placement

- Mount vertically, as high as practical
- Keep ≥ 1.5 m from metal objects (the 2 m loop has a larger
  near-field zone than smaller loops)
- Null is broadside to the loop plane — orient for desired direction
- No ground plane or radials needed
- The large loop is more sensitive to nearby metallic objects than
  smaller designs — site carefully

---

## 13. Design Validation

| Check | Criterion | Status |
|-------|-----------|--------|
| circ/λ | 0.04 – 0.25 | 0.212 OK |
| Max voltage | < cap rating | 1 720 V < 2 000 V OK |
| Tube bend radius | > 38 mm | All bends = 1 000 mm OK |
| Coupling loop | Fits 3/8" tube | 400 mm dia OK |
| Cap range | Covers 30 m band | 36.3–36.5 pF OK |
| Total weight | Manageable | 1.18 kg OK |
| Total tube | Fits 25 ft coil | 7.65 m OK |

---

## 14. Comparison with Other 30 m Designs

| Aspect | ML30-6 Loop A | ML30_EFF (2-turn) | **ML30_EFF_1Loop (this)** |
|--------|--------------|-------------------|--------------------------|
| Design | Multi-band 3 loops | 2-turn 1.60 m | **Single loop 2.00 m** |
| Bands | 30m–6m (7) | 30m only | **30m only** |
| Loop diameter | 1.60 m | 1.60 m × 2 turns | **2.00 m** |
| Turns | 1 | 2 | **1** |
| η (Q=5000) | ~44 % | 58.1 % | **60.5 %** |
| η (Q=∞) | 54.0 % | 70.2 % | **69.7 %** |
| Vc (Q=5000) | ~1 350 V | 2 889 V | **1 688 V** |
| Voltage concern | None | High | **None** |
| Weight | 3.5 kg (3 loops) | 1.68 kg | **1.18 kg** |
| Cost | $153 | $108 | **$93** |
| Complexity | Switching + 3 caps | Series jumper | **Simplest** |
| Physical size | 1.60 m | 1.60 m (tall) | **2.00 m (wide)** |

### Single Loop vs 2-Turn: Head-to-Head

| Metric | 2-turn 1.60 m | 1-loop 2.00 m | Winner |
|--------|--------------|---------------|--------|
| η (Q=5000) | 58.1 % | 60.5 % | **1-loop** (+0.2 dB) |
| η (Q=∞) | 70.2 % | 69.7 % | 2-turn (tie) |
| Voltage | 2 889 V | 1 688 V | **1-loop** (much safer) |
| Weight | 1.68 kg | 1.18 kg | **1-loop** |
| Cost | $108 | $93 | **1-loop** |
| Width | 1.60 m | 2.00 m | 2-turn (more compact) |
| Complexity | Series wiring | Single loop | **1-loop** |

> **Verdict:** For 30 m, the single 2.00 m loop narrowly **beats** the
> 2-turn 1.60 m design on efficiency while being simpler, cheaper,
> lighter, and running at much lower voltage. The only trade-off is
> physical size — 2.00 m wide vs 1.60 m. If space allows, the single
> large loop is the superior approach. If space is constrained to
> ≤ 1.60 m, use the 2-turn ML30_EFF design instead.

---

## 15. Scaling to Larger Diameters

If space permits, a larger loop yields even more efficiency:

| Diameter | η (Q=5k) | η (Q=2k) | Vc (V) | Extra tube cost |
|----------|----------|----------|--------|-----------------|
| **2.00 m (this)** | **60.5 %** | **50.6 %** | **1 688** | **baseline** |
| 2.10 m | 63.6 % | 53.5 % | 1 668 | +$3 |
| 2.20 m | 67.0 % | 57.4 % | 1 642 | +$5 |
| 2.35 m (max) | 71.1 % | 62.0 % | 1 601 | +$10 |

Going from 2.00 m to 2.35 m adds +0.7 dB for only $10 more tube. If
you have the space, it is worth it.

---

## 16. Upgrade Paths

### Path A — Go Bigger (Easiest +dB)

Increase diameter to 2.20 m or 2.35 m. Same design, same cap, more
tube. η jumps to 67–71 %. The cheapest upgrade possible.

### Path B — Premium Cap

Replace fixed+trimmer with butterfly Q=7000: η rises from 60.5 % to
62.9 % (+0.2 dB). Marginal improvement — the large loop already
pushes most loss into copper, not the cap.

### Path C — Add 20 m

Add a 0.80 m loop inside the 2.00 m loop with its own cap and coupling
loop. Switch between them with a coax switch. The 0.80 m loop handles
20m–10m (see ML20_10).

### Path D — Remote Tuning

Stepper motor on the trimmer. Essential if the antenna is on a mast
above reach. With only 3 tuning positions for the whole band, a simple
3-position switch could also work.

---

*Design: ML30_EFF_1Loop | 3/8" copper tube | single 2.00 m loop | 10 W | 30 m only | efficiency optimised*
*Generated: 2026-02-07*
