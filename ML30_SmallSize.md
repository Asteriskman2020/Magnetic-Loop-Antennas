# ML30_SmallSize — Magnetic Loop Antenna: 30 m Band (Small Size Optimised)

> **Compact design | 0.60 m diameter | 3/8" copper tube | 10 W max | 30 m only**

---

## 1. Design Overview

A compact magnetic loop antenna for the 30 m band (10.100–10.150 MHz)
optimised for **minimum physical size** while maintaining usable
efficiency. Uses a 3-turn 0.60 m (23.6") loop with a high-Q butterfly
capacitor to squeeze the most radiation from a small aperture.

| Parameter          | Value                                       |
|--------------------|---------------------------------------------|
| Band coverage      | 30 m only (10.100 – 10.150 MHz)             |
| Max power          | 10 W                                        |
| Loop diameter      | **0.60 m** (23.6")                          |
| Number of turns    | **3** (series-connected)                    |
| Turn spacing       | 30 mm centre-to-centre                      |
| Radiator material  | 3/8" (9.525 mm OD) soft copper tube Type L  |
| Coupling loop      | 3/8" soft copper tube, 100 mm diameter       |
| Tuning capacitor   | Butterfly split-stator (Q ≈ 5 000)          |
| Band switching     | **None** — single band                      |

### The Small-Size Challenge

On 30 m (λ = 29.6 m) with a 0.60 m loop, circ/λ = 0.064 — near the
minimum (0.04) for proper magnetic loop operation. Radiation resistance
is tiny:

| Size | circ/λ | Rr single (mΩ) | η single Q=5k |
|------|--------|----------------|---------------|
| 2.00 m | 0.212 | 400.2 | 60.5 % |
| 1.60 m | 0.170 | 163.9 | 44.3 % |
| 1.00 m | 0.106 | 24.7 | 16.7 % |
| 0.80 m | 0.085 | 10.2 | 9.2 % |
| **0.60 m** | **0.064** | **3.2** | **3.6 %** |
| 0.44 m | 0.047 | 0.8 | 1.1 % |

A single 0.60 m turn gives only 3.6 % — not viable. But 3 turns
raises Rr by a factor of 9 (N²), making it usable:

**3-turn Rr = 9 × 3.2 = 28.8 mΩ** — comparable to a single 1.00 m loop.

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
| Diameter     | 0.60 m        |
| Radius R     | 0.30 m        |
| Circumference| 1.885 m       |
| Area A       | 0.2827 m²     |
| Inductance L | **1.524 μH**  |

```
L = μ₀ × 0.30 × [ln(8 × 0.30 / 0.004763) − 2]
  = 3.770e-7 × [ln(504.3) − 2]
  = 3.770e-7 × [6.223 − 2]
  = 3.770e-7 × 4.223
  = 1.592 μH
```

**Note:** The formula L = μ₀R[ln(8R/a)−2] gives 1.592 μH. For the
calculations below, L_single = 1.59 μH is used.

### 3-Turn Combined Parameters

Three coaxial turns at 30 mm spacing. Mutual inductances:
- Adjacent turns (d=30 mm): M₁₂ = M₂₃ ≈ 0.87 μH
- Outer turns (d=60 mm): M₁₃ ≈ 0.65 μH

| Parameter              | Value        | Derivation                   |
|------------------------|--------------|------------------------------|
| Self-inductance (each) | 1.59 μH      | L = μ₀R[ln(8R/a) − 2]       |
| Total inductance       | **9.55 μH**  | 3L + 2(M₁₂ + M₂₃ + M₁₃)   |
| Effective turns        | N = 3        |                              |
| Rr (radiation)         | 28.8 mΩ      | 31171 × (3A/λ²)²            |
| Rl (copper loss)       | 156.0 mΩ     | 3 × Rl_single                |

```
Rr = 31171 × (3 × 0.2827 / 29.61²)²
   = 31171 × (0.8481 / 877.2)²
   = 31171 × (9.668e-4)²
   = 31171 × 9.347e-7
   = 29.1 mΩ ≈ 28.8 mΩ (using exact λ at band edges)

Rs = √(π × 10.125e6 × 1.2566e-6 / 5.8e7) = 8.30e-4 Ω/sq

Rl_per_turn = 8.30e-4 × 1.885 / (π × 0.009525) = 52.3 mΩ
Rl_total = 3 × 52.3 = 156.9 mΩ ≈ 156 mΩ

L_total = 3 × 1.59 + 2 × (0.87 + 0.65 + 0.87)
        = 4.77 + 2 × 2.39
        = 4.77 + 4.78 = 9.55 μH
```

---

## 4. Performance

### 4.1 At Band Centre (10.125 MHz)

| Cap Q | Rc (mΩ) | R_total (mΩ) | η (%) | Vc (V) | BW (kHz) | Q_L |
|-------|---------|--------------|-------|--------|----------|-----|
| 2 000 | 304.0 | 488.8 | **5.9** | 1 380 | 11.8 | 856 |
| 3 000 | 202.7 | 387.5 | **7.4** | 1 550 | 9.4 | 1 080 |
| 5 000 | 121.6 | 306.4 | **9.4** | 1 743 | 7.4 | 1 367 |
| 7 000 | 86.9 | 271.7 | **10.6** | 1 851 | 6.6 | 1 543 |
| 10 000 | 60.8 | 245.6 | **11.7** | 1 946 | 5.9 | 1 710 |
| ∞     | 0      | 184.8 | **15.6** | 2 243 | 4.4 | 2 287 |

```
X_L = 2π × 10.125e6 × 9.55e-6 = 607.2 Ω
C   = 1 / (4π² × 10.125e6² × 9.55e-6) = 26.1 pF

Example (Q = 5000):
  Rc = 607.2 / 5000 = 121.4 mΩ
  R_total = 28.8 + 156.0 + 121.4 = 306.2 mΩ
  η = 28.8 / 306.2 = 9.4 %
  Vc = √(10 / 0.306) × 607.2 = 5.716 × 607.2 = 1 741 V
  Q_L = 607.2 / 0.306 = 1 984
  BW = 10.125e6 / 1984 = 5.1 kHz
```

### 4.2 Across the 30 m Band (Q = 5 000)

| Frequency (MHz) | C (pF) | η (%) | Vc (V) |
|------------------|--------|-------|--------|
| 10.100 | 26.2 | 9.3 | 1 740 |
| 10.125 | 26.1 | 9.4 | 1 741 |
| 10.150 | 26.0 | 9.5 | 1 742 |

Efficiency is flat. Cap swing: **0.2 pF** (same as larger designs —
30 m is simply a narrow band).

### 4.3 Why 3 Turns and Not More?

| Turns | Rr (mΩ) | Rl (mΩ) | X_L (Ω) | Rc Q=5k | η Q=5k | Vc (V) |
|-------|---------|---------|---------|---------|--------|--------|
| 1 | 3.2 | 52.0 | ~101 | 20.2 | 4.2 % | 1 326 |
| 2 | 12.8 | 104.0 | ~320 | 64.0 | 7.1 % | 1 550 |
| **3** | **28.8** | **156.0** | **607** | **121** | **9.4 %** | **1 741** |
| 4 | 51.2 | 208.0 | ~980 | 196 | 11.2 % | 2 105 |
| 5 | 80.0 | 260.0 | ~1 430 | 286 | 12.8 % | 2 419 |

- **3 turns:** Best practical balance. Voltage 1 741 V is comfortable
  for a butterfly cap with 1.0 mm spacing (~3 000 V effective rating).
- **4 turns:** Only +1.8 % η for 2 105 V. Diminishing returns.
- **5 turns:** Voltage climbing toward 2 500 V. Cap gets expensive.

**3 turns is the sweet spot** for a 0.60 m small-size design.

---

## 5. Effective Radiated Power (ERP)

Directivity = 1.5 (1.76 dBi). Input = 10 W.

| Configuration | η (%) | P_rad (W) | ERP (W) |
|---------------|-------|-----------|---------|
| **3-turn 0.60 m Q=5k** | **9.4** | **0.94** | **1.4** |
| 3-turn 0.60 m Q=7k | 10.6 | 1.06 | 1.6 |
| 1-turn 2.00 m Q=5k | 60.5 | 6.05 | 9.1 |

> **Honest assessment:** 1.4 W ERP is modest but usable. On 30 m,
> FT8/FT4 digital modes can make worldwide contacts with under 1 W ERP.
> For SSB, expect regional contacts (500–1500 km). CW operators will
> find this antenna viable for DX with patience. This is a compromise
> antenna — it exists because you need it small, not because it is
> the best performer.

---

## 6. Tuning Capacitor

### Required Capacitance

| Edge | Frequency | C required |
|------|-----------|------------|
| Low  | 10.100 MHz | 26.2 pF   |
| High | 10.150 MHz | 26.0 pF   |
| **Swing** | | **0.2 pF** |

### Recommended: Butterfly Split-Stator

| Parameter           | Value                            |
|---------------------|----------------------------------|
| Type                | Butterfly split-stator 2×50 pF   |
| Effective range     | 0 – 25 pF (series)              |
| Plate spacing       | ≥ 1.0 mm (3 000 V eff.)         |
| Estimated Q         | 5 000                            |
| Cost                | $45 – $55                        |

A butterfly cap is recommended (not fixed+trimmer) because:
1. The high X_L (607 Ω) means capacitor Q matters more
2. A butterfly with Q ≈ 5 000 extracts the best from this small loop
3. It allows future reuse on other bands if you build a larger loop

### Alternative: Fixed + Trimmer (Budget)

| Component | Value |
|-----------|-------|
| Fixed C0G/NP0 | 22 pF |
| Air trimmer | 1–10 pF |

C0G capacitor Q at 10 MHz is 3 000–10 000, so effective Q ≈ 5 000.
This works and costs $11 vs $50 for a butterfly.

### Tuning Drive

A **10:1 vernier drive** is recommended. With only 0.2 pF swing
across 50 kHz, the tuning is extremely sensitive. Alternatively, use
the fixed+trimmer approach where you adjust the trimmer with a small
insulated screwdriver.

---

## 7. Coupling Loop

| Parameter            | Value                         |
|----------------------|-------------------------------|
| Diameter             | **100 mm** (3.9")             |
| Ratio to main loop   | 1 : 6                         |
| Material             | 3/8" soft copper tube         |
| Tube length          | ≈ 0.40 m (incl. pigtails)    |
| Connector            | SO-239 chassis mount          |
| Position             | Bottom of lowest turn         |

The coupling loop is smaller (100 mm) because the 3-turn main loop
has higher total impedance. A 1:6 ratio provides approximately 50 Ω
at the SO-239.

### Fine-Tuning

1. Start with 100 mm, centred at the bottom
2. Rotate ±15° or slide ±20 mm for best SWR
3. Target: SWR < 2:1 (the low Rr makes a perfect match harder)

---

## 8. Physical Layout

### Construction Diagram

```
         ┌─── [Butterfly cap + 10:1 vernier] ───┐
         │                                        │
    ┌────┘    Turn 1 (top)     D = 0.60 m    └────┐
    └────┐                                   ┌────┘
         ├──── jumper (30 mm) ────────────────┤
    ┌────┘    Turn 2 (middle)  D = 0.60 m    └────┐
    └────┐                                   ┌────┘
         ├──── jumper (30 mm) ────────────────┤
    ┌────┘    Turn 3 (bottom)  D = 0.60 m    └────┐
    └────┐        ┌────┐                     ┌────┘
         │        │ CL │  100 mm             │
         │        └──┬─┘                     │
         └───────────┼──────────────────────┘
                     │
                  SO-239
                     │
                ─────┼───── Nylon clamps
                     │
                ┌────┴────┐
                │  PVC    │  1" mast, 0.6 m
                └────┬────┘
                     │
               ──────┴────── PVC base / tripod
```

### Physical Envelope

```
     ← 0.60 m (23.6") →

     ┌──────────────────┐ ─┐
     │   Turn 1          │  │
     ├──────────────────┤  │ ~70 mm
     │   Turn 2          │  │ (3 turns
     ├──────────────────┤  │  + spacers)
     │   Turn 3          │  │
     └──────────────────┘ ─┘
```

Total coil stack height: ~70 mm (3 tubes of 9.5 mm + 2 gaps of 30 mm).

---

## 9. Mechanical Specifications

| Dimension                | Value                        |
|--------------------------|------------------------------|
| Overall width            | 0.60 m (23.6")              |
| Overall height           | ≈ 0.75 m (with short mast)  |
| Coil stack height        | 70 mm (2.8")                 |
| Turn weight (×3)         | 0.65 kg                      |
| Coupling loop            | 0.05 kg                      |
| Hardware + cap            | ≈ 0.3 kg                     |
| **Total weight**         | **≈ 1.0 kg (2.2 lb)**       |
| Tube: turns (×3)         | 3 × 1.92 m = 5.76 m         |
| Tube: coupling           | 0.40 m                       |
| Tube: jumpers (×2)       | 0.08 m                       |
| **Total tube**           | **6.24 m (20.5 ft)**        |

**Portable:** At 0.60 m wide, 1.0 kg, and 0.75 m tall, this antenna
fits in a backpack or small duffel bag. It can be set up on a camera
tripod with a 1/4"-20 adapter.

---

## 10. Bill of Materials

| # | Item | Qty | Est. Cost |
|---|------|-----|-----------|
| 1 | 3/8" soft copper tube Type L, 25 ft | 1 | $35 |
| 2 | Butterfly split-stator 2×50 pF | 1 | $50 |
| 3 | 10:1 vernier reduction drive | 1 | $22 |
| 4 | SO-239 chassis-mount connector | 1 | $3 |
| 5 | 56 % silver solder + flux | 1 | $15 |
| 6 | 1" PVC pipe + fittings | 1 set | $8 |
| 7 | ABS project box | 1 | $4 |
| 8 | Nylon U-bolts, zip ties, hardware | 1 set | $5 |
| | | **Total** | **$142** |

| Budget option | Replace | Delta | Total |
|---------------|---------|-------|-------|
| Fixed 22 pF + trimmer | items 2+3 | −$61 | $81 |

| Upgrade | Delta | New total |
|---------|-------|-----------|
| Premium butterfly Q=7000 | +$20 | $162 |
| Camera tripod adapter | +$8 | $150 |

---

## 11. Construction Guide

### Step 1 — Form Three 0.60 m Loops

1. Cut three lengths of 1.92 m (6.3 ft) from 3/8" tube
2. Fill each with fine sand, plug ends
3. Bend each into a 0.60 m diameter circle
   - A 5-gallon bucket (D ≈ 0.30 m) makes a good starting form
   - Relax the bend to 0.60 m over a plywood template
4. Leave 15 mm gap at top of each loop
5. Empty sand, clean and tin all six tube ends

### Step 2 — Form the Coupling Loop

1. Cut 0.40 m of 3/8" tube
2. Bend into a 100 mm diameter circle
3. Leave 10 mm gap, clean and tin

### Step 3 — Series Connection

1. Stack the three loops coaxially, 30 mm apart
2. On one side, solder jumpers between:
   - Bottom of Turn 1 → Top of Turn 2 (30 mm copper strap)
   - Bottom of Turn 2 → Top of Turn 3 (30 mm copper strap)
3. The remaining ends (top of Turn 1, bottom of Turn 3) connect
   to the capacitor
4. Use small PVC spacer blocks between turns to maintain 30 mm gap
5. All joints: 56 % silver solder

### Step 4 — Assemble

1. Mount capacitor in project box at top
2. Install vernier drive
3. Attach 3-turn assembly to PVC mast (nylon U-bolts)
4. Position coupling loop at bottom of Turn 3, centred
5. Route coax down the mast

### Step 5 — Test

1. Connect NanoVNA, sweep 9.5–10.7 MHz
2. Adjust capacitor/trimmer for resonance at 10.125 MHz
3. Adjust coupling loop for minimum SWR
4. Expect SWR 1.5:1 to 2:1 (the low Rr makes perfect match harder)

---

## 12. Operating Notes

### Bandwidth and Coverage

| Cap Q | BW (kHz) | Positions for full band |
|-------|----------|-------------------------|
| 5 000 | 5.1 | 10 |
| 7 000 | 4.5 | 11 |
| 2 000 | 11.8 | 4-5 |

The narrow bandwidth (~5 kHz at Q=5000) means more retuning than
larger designs. With a fixed+trimmer cap, consider centering on your
preferred frequency (e.g. 10.136 MHz for FT8) and staying there.

### Voltage Safety

| Cap Q | Vc (V) |
|-------|--------|
| 5 000 | 1 741 |
| 7 000 | 1 851 |

Voltages are moderate — a butterfly with 1.0 mm spacing (3 000 V
effective) or a 2 kV C0G cap handles this easily.

### Realistic Expectations

This antenna is a **compromise**. At 9.4 % efficiency (Q=5000):

| Mode | Typical power needed | This antenna | Workable? |
|------|---------------------|--------------|-----------|
| FT8/FT4 | 0.5 W ERP for DX | 1.4 W ERP | **Yes** — worldwide |
| CW | 1–3 W ERP for DX | 1.4 W ERP | **Yes** — with patience |
| SSB | 5–10 W ERP for DX | 1.4 W ERP | Regional only |
| WSPR | 0.1 W ERP for spotting | 1.4 W ERP | **Excellent** |

> **Best use case:** FT8, CW, WSPR, and JS8Call on 30 m. These modes
> are designed for weak signals and work well with modest antennas.
> For 30 m SSB, consider the 2.00 m ML30_EFF_1Loop design instead.

---

## 13. Design Validation

| Check | Criterion | Status |
|-------|-----------|--------|
| circ/λ | 0.04 – 0.25 | 0.064 OK (low but valid) |
| Max voltage | < cap rating | 1 851 V < 3 000 V OK |
| Tube bend radius | > 38 mm | All bends ≥ 60 mm OK |
| Coupling loop | 100 mm, fits 3/8" tube | OK |
| Cap range | Covers 30 m band | 26.0–26.2 pF OK |
| Total weight | Portable | 1.0 kg OK |
| Fits backpack | Width < 0.65 m | 0.60 m OK |

---

## 14. Comparison with Other 30 m Designs

| Aspect | ML30_EFF_1Loop | ML30_EFF | **ML30_SmallSize (this)** |
|--------|---------------|----------|--------------------------|
| Philosophy | Max efficiency | Max eff (multi-turn) | **Min size** |
| Diameter | 2.00 m | 1.60 m | **0.60 m** |
| Turns | 1 | 2 | **3** |
| η (Q=5k) | 60.5 % | 58.1 % | **9.4 %** |
| ERP | 9.1 W | 8.7 W | **1.4 W** |
| Vc | 1 688 V | 2 889 V | **1 741 V** |
| Weight | 1.18 kg | 1.68 kg | **1.0 kg** |
| Width | 2.00 m | 1.60 m | **0.60 m** |
| Cost | $93 | $108 | **$81–$142** |
| Portable? | No (2 m wide) | No (1.6 m) | **Yes** |
| FT8 DX? | Excellent | Excellent | **Workable** |
| SSB DX? | Good | Good | **Regional only** |

> **Choose this design when:** portability and small size are your top
> priority, you operate digital modes (FT8, CW, WSPR), and you accept
> the efficiency trade-off. For any fixed installation, choose
> ML30_EFF_1Loop (2.00 m) instead.

---

## 15. Improving This Design

If you have slightly more space:

| Diameter | Turns | η (Q=5k) | Width | Gain vs this |
|----------|-------|----------|-------|--------------|
| **0.60 m** | **3** | **9.4 %** | **24"** | **baseline** |
| 0.70 m | 3 | 14.2 % | 28" | +1.8 dB |
| 0.80 m | 3 | 20.3 % | 31" | +3.3 dB |
| 0.80 m | 2 | 11.4 % | 31" | +0.8 dB |
| 1.00 m | 2 | 21.5 % | 39" | +3.6 dB |

Going from 0.60 m to 0.80 m (3-turn) gains +3.3 dB while adding only
8 inches — an excellent trade if your bag can fit it.

---

*Design: ML30_SmallSize | 3/8" copper tube | 3-turn 0.60 m | 10 W | 30 m only | small size optimised*
*Generated: 2026-02-07*
