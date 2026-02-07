# ML20_EFF — Magnetic Loop Antenna: 20 m Band (Efficiency Optimised)

> **2-turn design | 0.80 m diameter | 3/8" copper tube | 10 W max | 20 m only**

---

## 1. Design Overview

A **2-turn** magnetic loop antenna optimised for maximum efficiency on
the 20 m band (14.000–14.350 MHz). Two identical 0.80 m loops are
stacked coaxially 50 mm apart and connected in series, forming a 2-turn
inductor. A single high-Q butterfly capacitor tunes the entire band.

| Parameter          | Value                                       |
|--------------------|---------------------------------------------|
| Band coverage      | 20 m only (14.000 – 14.350 MHz)             |
| Max power          | 10 W                                        |
| Loop diameter      | **0.80 m** (31.5") — both turns identical   |
| Number of turns    | **2** (series-connected)                    |
| Turn spacing       | 50 mm centre-to-centre                      |
| Radiator material  | 3/8" (9.525 mm OD) soft copper tube Type L  |
| Coupling loop      | 3/8" soft copper tube, 130 mm diameter       |
| Tuning capacitor   | Butterfly split-stator (Q ≈ 5 000)          |
| Band switching     | **None** — single band, single capacitor    |

### Why 2 Turns?

On 20 m with a 0.80 m loop, the single biggest loss is **copper loss**
(Rl = 82.5 mΩ vs Rr = 39.4 mΩ). Even a perfect capacitor only yields
32.3 % efficiency. The 2-turn approach changes the physics:

- **Radiation resistance scales as N²:** Rr(2-turn) = 4 × 39.4 = 157.6 mΩ
- **Copper loss scales as N:** Rl(2-turn) = 2 × 82.5 = 165.0 mΩ
- **Rr/Rl ratio doubles:** from 0.48 (single) to 0.96 (2-turn)

The theoretical max efficiency jumps from 32.3 % to **48.9 %** — a
+1.8 dB improvement that no capacitor upgrade can achieve with a
single turn.

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
| Diameter     | 0.80 m        |
| Radius R     | 0.40 m        |
| Circumference| 2.513 m       |
| Area A       | 0.5027 m²     |
| Inductance L | 2.267 μH      |

### 2-Turn Combined Parameters

Two coaxial turns at 50 mm spacing have significant mutual inductance
M ≈ 1.09 μH (coupling coefficient k = 0.48).

| Parameter              | Value       | Derivation                  |
|------------------------|-------------|-----------------------------|
| Self-inductance (each) | 2.267 μH    | L = μ₀R[ln(8R/a) − 2]      |
| Mutual inductance M    | 1.09 μH     | Neumann formula, d = 50 mm  |
| **Total inductance**   | **6.71 μH** | L_tot = 2L + 2M             |
| Effective turns ratio  | N = 2       |                             |
| Rr (radiation)         | 157.6 mΩ    | 31171 × (2A/λ²)²           |
| Rl (copper loss)       | 165.0 mΩ    | 2 × Rl_single               |

```
L_single = μ₀ × 0.40 × [ln(8×0.40/0.004763) − 2]
         = 5.026e-7 × 4.510 = 2.267 μH

L_total  = 2 × 2.267 + 2 × 1.09 = 6.71 μH

Rr = 31171 × (2 × 0.5027 / 21.15²)²
   = 31171 × (1.0054 / 447.3)²
   = 31171 × 5.054e-6 = 157.6 mΩ

Rl = 2 × [√(π×14.175e6×μ₀/σ) × 2.513 / (π×0.009525)]
   = 2 × 82.5 = 165.0 mΩ
```

---

## 4. Performance

### 4.1 At Band Centre (14.175 MHz)

| Cap Q | Rc (mΩ) | R_total (mΩ) | η (%) | Vc (V) | BW (kHz) | Q_L |
|-------|---------|--------------|-------|--------|----------|-----|
| 2 000 | 298.3 | 620.9 | **25.4** | 2 395 | 14.8 | 961 |
| 3 000 | 198.8 | 521.4 | **30.2** | 2 614 | 12.4 | 1 144 |
| 5 000 | 119.3 | 441.9 | **35.7** | 2 838 | 10.5 | 1 350 |
| 7 000 | 85.2 | 407.8 | **38.6** | 2 954 | 9.7 | 1 463 |
| ∞     | 0      | 322.6 | **48.9** | 3 322 | 7.7 | 1 850 |

```
X_L = 2π × 14.175e6 × 6.71e-6 = 597.4 Ω
C   = 1 / (4π² × 14.175e6² × 6.71e-6) = 18.8 pF

Example (Q = 5000):
  Rc = 597.4 / 5000 = 119.5 mΩ
  R_total = 157.6 + 165.0 + 119.5 = 442.1 mΩ
  η = 157.6 / 442.1 = 35.6 %
  Vc = √(10 / 0.442) × 597.4 = 4.76 × 597.4 = 2 844 V
  Q_L = 597.4 / 0.442 = 1 352
  BW = 14.175e6 / 1352 = 10.5 kHz
```

### 4.2 Across the 20 m Band (Q = 5 000)

| Frequency | Segment | C (pF) | Rr (mΩ) | Rl (mΩ) | Rc (mΩ) | η (%) | Vc (V) |
|-----------|---------|--------|----------|---------|---------|-------|--------|
| 14.000 MHz | CW     | 19.3   | 149.8    | 164.0   | 117.8   | 34.7  | 2 835  |
| 14.070 MHz | Digital | 19.1   | 153.0    | 164.4   | 118.4   | 35.1  | 2 837  |
| 14.175 MHz | SSB     | 18.8   | 157.6    | 165.0   | 119.3   | 35.7  | 2 838  |
| 14.300 MHz | SSB     | 18.5   | 163.3    | 165.7   | 120.3   | 36.3  | 2 838  |
| 14.350 MHz | Top     | 18.4   | 165.5    | 166.0   | 120.8   | 36.6  | 2 840  |

**Efficiency variation across band:** 34.7 – 36.6 % (only ±1 %)

### 4.3 Comparison with Single-Turn Designs

| Configuration | η (%) | Vc (V) | Gain vs baseline |
|---------------|-------|--------|------------------|
| 1-turn, Q=2000 (ML20_10 baseline) | 17.7 | 1 352 | — |
| 1-turn, Q=5000 | 24.3 | 1 584 | +1.4 dB |
| 1-turn, Q=7000 | 26.1 | 1 642 | +1.7 dB |
| **2-turn, Q=5000 (this design)** | **35.7** | **2 838** | **+3.0 dB** |
| 2-turn, Q=7000 | 38.6 | 2 954 | +3.4 dB |
| 1-turn, Q=∞ (theoretical ceiling) | 32.3 | — | +2.6 dB |
| 2-turn, Q=∞ (theoretical ceiling) | 48.9 | — | +4.4 dB |

> **Key insight:** The 2-turn Q=5000 design (35.7 %) **exceeds the
> theoretical maximum** of a single-turn loop with a perfect lossless
> capacitor (32.3 %). No single-turn capacitor upgrade can match what
> the 2-turn geometry delivers. The +3.0 dB gain over the Q=2000
> baseline means your 10 W sounds like 20 W on the other end.

---

## 5. Effective Radiated Power (ERP)

Directivity = 1.5 (1.76 dBi). Input = 10 W.

| Configuration | η (%) | P_rad (W) | ERP (W) |
|---------------|-------|-----------|---------|
| 1-turn Q=2000 | 17.7 | 1.8 | 2.7 |
| 1-turn Q=5000 | 24.3 | 2.4 | 3.6 |
| **2-turn Q=5000** | **35.7** | **3.6** | **5.4** |
| 2-turn Q=7000 | 38.6 | 3.9 | 5.8 |

---

## 6. Tuning Capacitor

### Required Capacitance

| Edge | Frequency | C required |
|------|-----------|------------|
| Low  | 14.000 MHz | 19.3 pF   |
| High | 14.350 MHz | 18.4 pF   |
| **Swing** | | **0.9 pF** |

The tuning swing is extremely narrow (0.9 pF) — this is normal for a
high-inductance 2-turn loop on a single band. A fine vernier drive is
essential.

### Recommended Capacitor

| Parameter           | Value                            |
|---------------------|----------------------------------|
| Type                | Butterfly (split-stator)         |
| Sections            | 2 × 50 pF (series ≈ 0–25 pF)   |
| Plate spacing       | ≥ 1.5 mm (3 kV effective)       |
| Voltage rating      | ≥ 3 000 V effective              |
| Estimated Q         | 5 000                            |
| Cost                | $45 – $65                        |

> **Why butterfly?** The peak voltage of 2 838 V at 10 W demands a cap
> rated well above this. A butterfly with 1.5 mm spacing provides
> ~4 500 V effective rating (each section sees half the voltage). No
> wiping contacts eliminates arcing and intermittent noise. The high Q
> directly translates to higher efficiency.

### Tuning Strategy

With only 0.9 pF swing across 350 kHz, tuning requires extreme
precision. Options:

1. **Fine vernier drive (10:1 ratio)** — Recommended. A 10:1 vernier
   on a butterfly cap gives sufficient resolution. Standard 6:1 drives
   work but are touchy.

2. **Fixed + trimmer** — Solder a fixed 18 pF (C0G/NP0) capacitor in
   parallel with a 1–5 pF air trimmer. The trimmer covers the 0.9 pF
   swing with plenty of margin. Lower Q than butterfly but simpler.

3. **Varactor remote tuning** — A reverse-biased varactor diode
   (BB910 or similar) controlled by DC voltage via RF choke. Enables
   remote tuning but reduces Q to ~1 000–2 000.

---

## 7. Coupling Loop

| Parameter            | Value                         |
|----------------------|-------------------------------|
| Diameter             | **130 mm** (5.1")             |
| Ratio to main loop   | 1 : 6.15                      |
| Material             | 3/8" soft copper tube         |
| Tube length          | ≈ 0.50 m (incl. pigtails)    |
| Connector            | SO-239 chassis mount          |
| Position             | Bottom of lower turn          |

The 2-turn loop has ~2.7× higher total R than a single turn, which
changes the impedance transformation. The coupling loop is reduced
from 160 mm (single-turn) to **130 mm** to maintain a 50 Ω match.

### Fine-Tuning the Match

1. Start with 130 mm coupling loop centred at the bottom
2. Adjust SWR by rotating coupling loop ±15° off-axis
3. Or slide coupling loop up/down ±30 mm along the main loop
4. Target: SWR < 1.5:1 at resonance

---

## 8. Physical Layout

### Construction Diagram

```
             ┌─── [Butterfly Cap + 10:1 Vernier] ───┐
             │                                        │
        ┌────┘    TURN 1 (top)                   └────┐
       │          D = 0.80 m                           │
       │          3/8" Cu tube                         │
        └────┐                                   ┌────┘
             │                                    │
             ├──── copper jumper (50 mm) ────────┤
             │                                    │
        ┌────┘    TURN 2 (bottom)                └────┐
       │          D = 0.80 m                           │
       │          3/8" Cu tube                         │
        └────┐                                   ┌────┘
             │         ┌──────┐                   │
             │         │ C/L  │                   │
             │         │130mm │                   │
             │         └──┬───┘                   │
             └────────────┼───────────────────────┘
                          │
                       SO-239
                          │
                     ─────┼───── Nylon U-bolt clamps
                          │
                     ┌────┴────┐
                     │  PVC    │  1" Schedule 40 PVC
                     │  mast   │  0.8 m
                     └────┬────┘
                          │
                    ──────┴────── PVC cross base
```

### Series Connection Detail

```
     Cap terminal A          Cap terminal B
          │                       │
          │     15 mm gap         │
     ┌────┘                  └────┐
     │        Turn 1 (top)        │  ← 0.80 m loop
     └────┐                  ┌────┘
          │                  │
          │   Cu jumper      │
          │   50 mm          │
          │                  │
     ┌────┘                  └────┐
     │       Turn 2 (bottom)      │  ← 0.80 m loop
     └────┐                  ┌────┘
          │                  │
          └──── connected ───┘
               at bottom
```

The two turns connect in series: Cap A → Turn 1 (clockwise) →
jumper → Turn 2 (clockwise) → Cap B. Current flows in the same
direction through both turns, creating additive magnetic moment.

---

## 9. Mechanical Specifications

| Dimension                | Value                        |
|--------------------------|------------------------------|
| Overall width            | 0.80 m (31.5")              |
| Overall height           | ≈ 0.95 m (with mast clamp)  |
| Turn 1 weight            | 0.29 kg                      |
| Turn 2 weight            | 0.29 kg                      |
| Coupling loop            | 0.06 kg                      |
| Hardware + cap            | ≈ 0.3 kg                     |
| **Total weight**         | **≈ 0.94 kg (2.1 lb)**      |
| Tube: turn 1             | 2.55 m                       |
| Tube: turn 2             | 2.55 m                       |
| Tube: coupling loop      | 0.50 m                       |
| Tube: jumper             | 0.10 m                       |
| **Total tube**           | **5.70 m (18.7 ft)**        |

---

## 10. Bill of Materials

| # | Item | Qty | Est. Cost |
|---|------|-----|-----------|
| 1 | 3/8" soft copper tube Type L, 20 ft | 1 | $25 |
| 2 | Butterfly split-stator 2×50 pF | 1 | $55 |
| 3 | 10:1 vernier reduction drive | 1 | $22 |
| 4 | SO-239 chassis-mount connector | 1 | $3 |
| 5 | 56 % silver solder + flux | 1 | $15 |
| 6 | 1" PVC pipe + fittings | 1 set | $10 |
| 7 | ABS project box | 1 | $4 |
| 8 | Nylon U-bolts, zip ties, hardware | 1 set | $5 |
| | | **Total** | **$139** |

| Upgrade | Delta | New total |
|---------|-------|-----------|
| Premium butterfly Q=7000 | +$30 | $169 |
| Stepper motor remote tune | +$25 | $164–$194 |
| Camera tripod adapter | +$8 | $147–$202 |

---

## 11. Construction Guide

### Step 1 — Form Two 0.80 m Loops

1. Cut two lengths of 2.55 m (8.4 ft) from 3/8" soft copper tube
2. Fill each with fine dry sand, plug ends with tape
3. Bend each into a 0.80 m diameter circle using a plywood disc
   or 5-gallon bucket as starting form
4. Leave a **15 mm gap** at the top of each loop
5. Empty sand, clean tube ends with 220-grit emery cloth
6. Tin all four tube ends with 56 % silver solder

### Step 2 — Form the Coupling Loop

1. Cut 0.50 m of 3/8" tube
2. Bend into a 130 mm diameter circle
3. Leave 10–15 mm gap, clean and tin

### Step 3 — Series Connection

1. Position Turn 1 and Turn 2 coaxially, 50 mm apart
2. On one side (the "jumper side"), solder a 50 mm copper jumper
   between the bottom end of Turn 1 and the top end of Turn 2
3. The remaining two ends (top of Turn 1, bottom of Turn 2) connect
   to the capacitor terminals via copper straps
4. All joints: 56 % silver solder, not lead-tin

### Step 4 — Mount and Assemble

1. Mount capacitor in ABS project box at the top
2. Install 10:1 vernier drive on capacitor shaft
3. Attach the 2-turn assembly to PVC mast (nylon U-bolts, 2 points)
4. Position coupling loop at the bottom of Turn 2, centred
5. Route coax from SO-239 down the mast

### Step 5 — Test and Calibrate

1. Connect NanoVNA or antenna analyser to the SO-239
2. Sweep 13.5–14.8 MHz — look for one deep SWR dip
3. Tune capacitor to place resonance at 14.175 MHz (band centre)
4. Adjust coupling loop for minimum SWR (target < 1.5:1)
5. Note: with 10.5 kHz bandwidth, the SWR dip is **extremely sharp**
6. Mark CW, digital, and SSB positions on the dial

---

## 12. Operating Notes

### Tuning

| Segment | Frequency | Retune from centre? |
|---------|-----------|---------------------|
| CW      | 14.000–14.070 | Yes, ~2 turns on vernier |
| Digital | 14.070–14.099 | Yes, ~1 turn |
| SSB     | 14.100–14.350 | Every 8–10 kHz |

With a bandwidth of ~10 kHz (Q=5000), you cover most SSB QSOs without
retuning. For band scanning, you will retune about 35 times to sweep
the full 350 kHz.

### Voltage Safety

| Cap Q | Vc (V) | Cap rating needed |
|-------|--------|-------------------|
| 5 000 | 2 838 | ≥ 3 000 V |
| 7 000 | 2 954 | ≥ 3 000 V |

- **Never touch** the capacitor, loop top, or jumper while transmitting
- RF burns at 2 800+ V are severe even at 10 W
- Maintain at least **0.5 m clearance** from loop surface during TX
- Consider a polycarbonate shield over the capacitor box
- The butterfly cap with 1.5 mm spacing provides ~4 500 V effective
  rating — adequate margin

### Heat Dissipation

| Cap Q | η (%) | P_radiated (W) | P_heat (W) |
|-------|-------|----------------|------------|
| 5 000 | 35.7 | 3.6 | 6.4 |
| 7 000 | 38.6 | 3.9 | 6.1 |

At 10 W input, worst case is 6.4 W dissipated. The two turns provide
~1 500 cm² of copper surface area — no thermal concerns.

---

## 13. Design Validation

| Check | Criterion | Status |
|-------|-----------|--------|
| circ/λ | 0.04 – 0.25 | 0.117 – 0.120 OK |
| Max voltage | < cap rating | 2 954 V < 4 500 V OK |
| Tube bend radius | > 38 mm | All bends ≥ 80 mm OK |
| Coupling loop | Fits 3/8" tube | 130 mm dia OK |
| Cap range | Covers 20 m band | 18.4–19.3 pF OK |
| Total weight | Manageable | 0.94 kg OK |
| Total tube | Fits 20 ft coil | 5.70 m (18.7 ft) OK |

---

## 14. Comparison with Other Designs

| Aspect | ML20_10 single | ML20_10_EFF (20m perf.) | **ML20_EFF (this)** |
|--------|---------------|------------------------|---------------------|
| Band coverage | 20m–10m (5 bands) | 20m–10m (5 bands) | **20m only** |
| Loop diameter | 0.80 m | 0.80 m × 2 stacked | 0.80 m × 2 coaxial |
| Turns | 1 | 1 per loop (2 loops) | **2 (series)** |
| 20 m efficiency (Q=5k) | 24.3 % | 24.3 % | **35.7 %** |
| Improvement on 20 m | baseline | same | **+1.7 dB** |
| vs Q=2000 baseline | — | — | **+3.0 dB** |
| Voltage (Q=5k) | 1 584 V | 1 584 V | 2 838 V |
| Weight | 0.7 kg | 1.2 kg | 0.94 kg |
| Cost | $97–$127 | $210 | **$139** |
| Complexity | Simplest | SP3T switch | Series jumper |

> **Verdict:** If 20 m is your primary band and you want the best
> possible efficiency from a 0.80 m antenna, this 2-turn design
> delivers +3.0 dB over the standard single-loop approach. It exceeds
> the theoretical maximum efficiency of any single-turn 0.80 m loop,
> regardless of capacitor quality. The trade-off is higher voltage
> (requiring a butterfly cap) and single-band operation.

---

## 15. Why 2 Turns Is the Optimum

| Turns | Rr (mΩ) | Rl (mΩ) | X_L (Ω) | Rc Q=5k (mΩ) | η (%) | Vc (V) |
|-------|---------|---------|---------|-------------|-------|--------|
| 1 | 39.4 | 82.5 | 201.8 | 40.4 | 24.3 | 1 584 |
| **2** | **157.6** | **165.0** | **597** | **119** | **35.7** | **2 838** |
| 3 | 354.6 | 247.5 | ~1 340 | ~268 | 40.8 | ~4 590 |
| 4 | 630.4 | 330.0 | ~2 380 | ~476 | 43.8 | ~6 120 |

- **1 turn:** Low efficiency, low voltage. Budget option.
- **2 turns:** Best practical trade-off. +3 dB. Voltage manageable
  with butterfly cap.
- **3 turns:** Moderate gain (+2.3 dB over 2-turn) but voltage
  exceeds 4 500 V — needs vacuum variable cap ($80–$150).
- **4 turns:** Diminishing returns. Extreme voltage. Impractical
  at 10 W without vacuum cap.

**2 turns is the sweet spot** — it captures most of the multi-turn
benefit while keeping voltage within butterfly capacitor range.

---

## 16. Upgrade Paths

### Path A — Premium Cap (Q = 7 000)

Replace standard butterfly with premium: η rises from 35.7 % to
38.6 % (+0.3 dB). Cost: +$30.

### Path B — Add Multi-Band Capability

Add a third loop (0.80 m, single turn) with its own cap below the
2-turn assembly. Switch between the 2-turn (20 m optimised) and
single-turn (17m–10m general) using an SP3T switch. Combines ML20_EFF
and ML20_10 into one antenna.

### Path C — Remote Tuning

Stepper motor on the vernier drive, controlled by Arduino. Essential
if the antenna is above head height, since body proximity within 1 m
detunes the loop.

---

*Design: ML20_EFF | 3/8" copper tube | 2-turn 0.80 m | 10 W | 20 m only | efficiency optimised*
*Generated: 2026-02-07*
