# ML30_EFF — Magnetic Loop Antenna: 30 m Band (Efficiency Optimised)

> **2-turn design | 1.60 m diameter | 3/8" copper tube | 10 W max | 30 m only**

---

## 1. Design Overview

A **2-turn** magnetic loop antenna optimised for maximum efficiency on
the 30 m band (10.100–10.150 MHz). Two identical 1.60 m loops are
stacked coaxially 80 mm apart and connected in series. A single high-Q
butterfly capacitor tunes the narrow 50 kHz band.

| Parameter          | Value                                       |
|--------------------|---------------------------------------------|
| Band coverage      | 30 m only (10.100 – 10.150 MHz)             |
| Max power          | 10 W                                        |
| Loop diameter      | **1.60 m** (63") — both turns identical     |
| Number of turns    | **2** (series-connected)                    |
| Turn spacing       | 80 mm centre-to-centre                      |
| Radiator material  | 3/8" (9.525 mm OD) soft copper tube Type L  |
| Coupling loop      | 3/8" soft copper tube, 270 mm diameter       |
| Tuning capacitor   | Butterfly split-stator (Q ≈ 5 000)          |
| Band switching     | **None** — single band, single capacitor    |

### Why 1.60 m?

The maximum loop diameter for circ/λ ≤ 0.25 at 10.15 MHz is 2.35 m
— impractically large. A 1.60 m loop gives circ/λ = 0.170 at band
centre, placing it in the efficient mid-range. This size matches the
existing ML30-6 design, allowing direct comparison.

### Why 2 Turns?

On 30 m a single 1.60 m loop achieves 54 % theoretical efficiency —
good but not great. The 2-turn approach boosts the Rr/Rl ratio:

- **Rr(2-turn) = 4 × 163.9 = 655.6 mΩ** (quadrupled)
- **Rl(2-turn) = 2 × 139.4 = 278.8 mΩ** (doubled)
- **Rr/Rl ratio doubles:** from 1.18 (single) to 2.35 (2-turn)
- **Theoretical max η:** 54 % → **70 %** (+1.1 dB)

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
| Diameter     | 1.60 m        |
| Radius R     | 0.80 m        |
| Circumference| 5.027 m       |
| Area A       | 2.011 m²      |
| Inductance L | **5.230 μH**  |

```
L = μ₀ × 0.80 × [ln(8 × 0.80 / 0.004763) − 2]
  = 1.005e-6 × [ln(1343.6) − 2]
  = 1.005e-6 × 5.203
  = 5.230 μH
```

### 2-Turn Combined Parameters

Two coaxial turns at 80 mm spacing: mutual inductance M ≈ 2.39 μH
(coupling coefficient k = 0.46).

| Parameter              | Value        | Derivation                   |
|------------------------|--------------|------------------------------|
| Self-inductance (each) | 5.230 μH     | L = μ₀R[ln(8R/a) − 2]       |
| Mutual inductance M    | 2.39 μH      | Neumann formula, d = 80 mm   |
| **Total inductance**   | **15.24 μH** | L_tot = 2L + 2M              |
| Effective turns        | N = 2        |                              |
| Rr (radiation)         | 655.6 mΩ     | 31171 × (2A/λ²)²            |
| Rl (copper loss)       | 278.8 mΩ     | 2 × Rl_single                |

```
L_total = 2 × 5.230 + 2 × 2.39 = 15.24 μH

Rr = 31171 × (2 × 2.011 / 29.61²)²
   = 31171 × (4.022 / 877.2)²
   = 31171 × 2.105e-5
   = 655.6 mΩ

Rs = √(π × 10.125e6 × μ₀ / σ) = 8.30e-4 Ω/sq

Rl = 2 × 8.30e-4 × 5.027 / (π × 0.009525)
   = 2 × 139.4 = 278.8 mΩ
```

---

## 4. Performance

### 4.1 At Band Centre (10.125 MHz)

| Cap Q | Rc (mΩ) | R_total (mΩ) | η (%) | Vc (V) | BW (kHz) | Q_L |
|-------|---------|--------------|-------|--------|----------|-----|
| 2 000 | 484.8 | 1 419.2 | **46.2** | 2 572 | 13.8 | 732 |
| 3 000 | 323.2 | 1 257.6 | **52.1** | 2 731 | 12.2 | 827 |
| 5 000 | 193.9 | 1 128.3 | **58.1** | 2 889 | 10.8 | 936 |
| 7 000 | 138.5 | 1 072.9 | **61.1** | 2 961 | 10.3 | 987 |
| ∞     | 0      | 934.4   | **70.2** | 3 177 | 8.9 | 1 137 |

```
X_L = 2π × 10.125e6 × 15.24e-6 = 969.1 Ω
C   = 1 / (4π² × 10.125e6² × 15.24e-6) = 16.3 pF

Example (Q = 5000):
  Rc = 969.1 / 5000 = 193.8 mΩ
  R_total = 655.6 + 278.8 + 193.8 = 1128.2 mΩ
  η = 655.6 / 1128.2 = 58.1 %
  Vc = √(10 / 1.128) × 969.1 = 2.978 × 969.1 = 2 886 V
  Q_L = 969.1 / 1.128 = 859
  BW = 10.125e6 / 859 = 11.8 kHz
```

### 4.2 Across the 30 m Band (Q = 5 000)

| Frequency (MHz) | C (pF) | Rr (mΩ) | Rl (mΩ) | Rc (mΩ) | η (%) | Vc (V) |
|------------------|--------|---------|---------|---------|-------|--------|
| 10.100 | 16.4 | 650.1 | 278.4 | 193.3 | 58.0 | 2 885 |
| 10.125 | 16.3 | 655.6 | 278.8 | 193.9 | 58.1 | 2 889 |
| 10.150 | 16.2 | 662.6 | 279.1 | 194.5 | 58.3 | 2 891 |

**Efficiency is essentially flat across the entire 50 kHz band.**

Capacitance swing: 16.2 – 16.4 pF (**only 0.2 pF**). The tuning
range is extremely narrow — see Section 6 for capacitor strategy.

### 4.3 Comparison with Single-Turn 1.60 m

| Configuration | η (%) | Vc (V) | Gain vs single Q=2k |
|---------------|-------|--------|----------------------|
| 1-turn, Q=2000 | 34.9 | 1 535 | — (baseline) |
| 1-turn, Q=5000 | 44.3 | 1 730 | +1.0 dB |
| 1-turn, Q=7000 | 46.7 | 1 782 | +1.3 dB |
| 1-turn, Q=∞ | 54.0 | — | +1.9 dB |
| **2-turn, Q=5000 (this)** | **58.1** | **2 889** | **+2.2 dB** |
| 2-turn, Q=7000 | 61.1 | 2 961 | +2.4 dB |
| 2-turn, Q=∞ | 70.2 | — | +3.0 dB |

> **Key insight:** The 2-turn Q=5000 design (58.1 %) exceeds the
> theoretical ceiling of a single-turn with lossless capacitor (54.0 %).
> The +2.2 dB gain over the single-turn Q=2000 baseline means your
> 10 W effectively becomes 16.6 W to the receiving station.

---

## 5. Effective Radiated Power (ERP)

Directivity = 1.5 (1.76 dBi). Input = 10 W.

| Configuration | η (%) | P_rad (W) | ERP (W) |
|---------------|-------|-----------|---------|
| 1-turn Q=2000 | 34.9 | 3.5 | 5.2 |
| 1-turn Q=5000 | 44.3 | 4.4 | 6.6 |
| **2-turn Q=5000** | **58.1** | **5.8** | **8.7** |
| 2-turn Q=7000 | 61.1 | 6.1 | 9.2 |

---

## 6. Tuning Capacitor

### Required Capacitance

| Edge | Frequency | C required |
|------|-----------|------------|
| Low  | 10.100 MHz | 16.4 pF   |
| High | 10.150 MHz | 16.2 pF   |
| **Swing** | | **0.2 pF** |

With only 0.2 pF swing across the entire 50 kHz band, a conventional
variable capacitor is impractical — even a 10:1 vernier drive cannot
resolve 0.2 pF from a 25 pF capacitor.

### Recommended Approach: Fixed + Trimmer

| Component | Value | Purpose |
|-----------|-------|---------|
| Fixed capacitor (C0G/NP0) | 15 pF | Sets baseline |
| Air trimmer | 1 – 5 pF | Fine tuning |
| **Total at resonance** | **~16.3 pF** | Covers full band |

1. Solder a high-quality 15 pF C0G/NP0 ceramic capacitor across the
   loop gap (voltage rating ≥ 3 kV)
2. Add a 1–5 pF air trimmer in parallel
3. Adjust trimmer to centre resonance in the band
4. The trimmer provides ≈ ±1 pF range — far more than the 0.2 pF needed

**Capacitor Q of the fixed C0G/NP0:** Typically 3 000–10 000 at 10 MHz.
Combined with a quality air trimmer, effective Q ≈ 5 000.

### Alternative: Butterfly Cap with Fine Vernier

If you prefer a continuously variable cap (e.g. for multi-band future
expansion), use a butterfly 2×50 pF with a **10:1 vernier drive**. The
usable rotation range for 30 m will be very small — perhaps 2–3 degrees
of shaft rotation.

| Parameter           | Value                            |
|---------------------|----------------------------------|
| Type                | Butterfly split-stator 2×50 pF   |
| Plate spacing       | ≥ 1.5 mm (4 500 V effective)     |
| Estimated Q         | 5 000                            |
| Cost                | $45 – $65                        |

---

## 7. Coupling Loop

| Parameter            | Value                         |
|----------------------|-------------------------------|
| Diameter             | **270 mm** (10.6")            |
| Ratio to main loop   | 1 : 5.9                       |
| Material             | 3/8" soft copper tube         |
| Tube length          | ≈ 1.0 m (incl. pigtails)     |
| Connector            | SO-239 chassis mount          |
| Position             | Bottom of lower turn          |

The 2-turn loop has higher total R (~1 128 mΩ) than a single turn
(~370 mΩ). The coupling loop is sized at 270 mm to maintain a 50 Ω
match — reduced from the 320 mm used for a single-turn 1.60 m loop.

### Fine-Tuning

1. Start with 270 mm coupling loop centred at the bottom
2. Adjust SWR by rotating ±15° off-axis or sliding ±30 mm
3. Target: SWR < 1.5:1 at resonance

---

## 8. Physical Layout

### Construction Diagram

```
              ┌── [Cap box + trimmer] ──┐
              │                          │
         ┌────┘    TURN 1 (top)     └────┐
        │          D = 1.60 m             │
        │          3/8" Cu tube           │
         └────┐                     ┌────┘
              │                      │
              ├── Cu jumper 80mm ────┤
              │                      │
         ┌────┘    TURN 2 (bottom)  └────┐
        │          D = 1.60 m             │
        │          3/8" Cu tube           │
         └────┐                     ┌────┘
              │      ┌──────┐        │
              │      │ C/L  │        │
              │      │270mm │        │
              │      └──┬───┘        │
              └─────────┼────────────┘
                        │
                     SO-239
                        │
                   ─────┼───── Nylon U-bolt clamps
                        │
                   ┌────┴────┐
                   │  PVC    │  1.25" Schedule 40
                   │  mast   │  1.2 m
                   └────┬────┘
                        │
                  ──────┴────── Heavy PVC base
                                or ground stake
```

### Series Connection Detail

The two turns connect: Cap terminal A → Turn 1 (clockwise) → jumper
→ Turn 2 (clockwise) → Cap terminal B. Both turns carry current in
the same direction, creating additive magnetic moment.

---

## 9. Mechanical Specifications

| Dimension                | Value                         |
|--------------------------|-------------------------------|
| Overall width            | 1.60 m (63")                 |
| Overall height           | ≈ 1.85 m (with mast + base)  |
| Turn 1 weight            | 0.58 kg                       |
| Turn 2 weight            | 0.58 kg                       |
| Coupling loop            | 0.12 kg                       |
| Hardware + cap            | ≈ 0.4 kg                      |
| **Total weight**         | **≈ 1.68 kg (3.7 lb)**       |
| Tube: turn 1             | 5.10 m                        |
| Tube: turn 2             | 5.10 m                        |
| Tube: coupling loop      | 1.00 m                        |
| Tube: jumper             | 0.12 m                        |
| **Total tube**           | **11.32 m (37.1 ft)**        |

---

## 10. Bill of Materials

| # | Item | Qty | Est. Cost |
|---|------|-----|-----------|
| 1 | 3/8" soft copper tube Type L, 20 ft | 2 | $50 |
| 2 | Fixed C0G 15 pF 3 kV capacitor | 1 | $8 |
| 3 | Air trimmer 1–5 pF | 1 | $6 |
| 4 | SO-239 chassis-mount connector | 1 | $3 |
| 5 | 56 % silver solder + flux | 1 | $15 |
| 6 | 1.25" PVC pipe + fittings | 1 set | $15 |
| 7 | ABS project box | 1 | $4 |
| 8 | Nylon U-bolts, zip ties, hardware | 1 set | $7 |
| | | **Total** | **$108** |

| Upgrade | Delta | New total |
|---------|-------|-----------|
| Butterfly cap (for multi-band flex) | +$40 | $148 |
| Premium butterfly Q=7000 | +$70 | $178 |
| Stepper motor remote tune | +$25 | $133–$203 |

---

## 11. Construction Guide

### Step 1 — Form Two 1.60 m Loops

1. Cut two lengths of 5.10 m (16.7 ft) from 3/8" soft copper tube
2. Fill each with fine dry sand, plug ends with tape
3. Bend each into a 1.60 m diameter circle:
   - Use a large plywood disc or draw a 1.60 m circle on a flat surface
   - Work gradually — the tube is soft but 5 m of tube has spring-back
   - A helper makes this step much easier
4. Leave a **15 mm gap** at the top of each loop
5. Empty sand, clean tube ends with 220-grit emery cloth
6. Tin all four tube ends with 56 % silver solder

### Step 2 — Form the Coupling Loop

1. Cut 1.0 m of 3/8" tube
2. Bend into a 270 mm diameter circle
3. Leave 10–15 mm gap, clean and tin

### Step 3 — Series Connection

1. Position Turn 1 and Turn 2 coaxially, 80 mm apart
2. On one side, solder a 80 mm copper jumper between the bottom end
   of Turn 1 and the top end of Turn 2
3. The remaining two ends connect to the capacitor
4. All joints: 56 % silver solder

### Step 4 — Install Capacitors

1. Solder the 15 pF C0G/NP0 capacitor across the gap (short leads!)
2. Mount the air trimmer in the project box, connected in parallel
3. Keep total lead length from loop ends to capacitors < 15 mm

### Step 5 — Mount and Test

1. Mount the 2-turn assembly on PVC mast (nylon U-bolts, 3 points)
2. Position coupling loop at the bottom of Turn 2, centred
3. Connect NanoVNA, sweep 9.5–10.7 MHz
4. Adjust trimmer to place resonance at 10.125 MHz
5. Fine-tune coupling loop for SWR < 1.5:1

---

## 12. Operating Notes

### Bandwidth and Coverage

| Cap Q | BW (kHz) | Band positions needed |
|-------|----------|-----------------------|
| 2 000 | 13.8 | 4 |
| 5 000 | 10.8 | 5 |
| 7 000 | 10.3 | 5 |

The 30 m band is only **50 kHz wide**. With 10–14 kHz bandwidth, you
need just 4–5 tuning positions to cover the entire allocation. Many
operators park at one frequency (e.g. 10.136 MHz FT8) and never retune.

### Voltage Safety

| Cap Q | Vc (V) | Cap rating needed |
|-------|--------|-------------------|
| 5 000 | 2 889 | ≥ 3 000 V |
| 7 000 | 2 961 | ≥ 3 000 V |

- **Never touch** the capacitor or loop top while transmitting
- Maximum voltage is 2 961 V at Q=7000 — the C0G capacitor must be
  rated ≥ 3 kV, and the trimmer must handle this voltage
- If using a butterfly cap, 1.5 mm plate spacing (4 500 V effective)
  provides comfortable margin
- Maintain at least 0.5 m clearance during TX

### Heat Dissipation

| Cap Q | η (%) | P_radiated (W) | P_heat (W) |
|-------|-------|----------------|------------|
| 5 000 | 58.1 | 5.8 | 4.2 |
| 7 000 | 61.1 | 6.1 | 3.9 |

At 10 W, worst case is 4.2 W dissipated. The two turns provide
~3 000 cm² of copper surface — no thermal concerns.

---

## 13. Design Validation

| Check | Criterion | Status |
|-------|-----------|--------|
| circ/λ | 0.04 – 0.25 | 0.170 OK |
| Max voltage | < cap rating | 2 961 V < 3 000+ V OK |
| Tube bend radius | > 38 mm | All bends ≥ 160 mm OK |
| Coupling loop | Fits 3/8" tube | 270 mm dia OK |
| Cap range | Covers 30 m band | 16.2–16.4 pF OK |
| Total weight | Manageable | 1.68 kg OK |
| Total tube | Two 20 ft coils | 11.32 m (37.1 ft) OK |

---

## 14. Comparison with Other Designs

| Aspect | ML30-6 (multi-band) | 1-turn 1.60m 30m | **ML30_EFF (this)** |
|--------|---------------------|-------------------|---------------------|
| Bands | 30m–6m (7 bands) | 30m only | **30m only** |
| Loops | 3 (different sizes) | 1 × 1.60m | **2 × 1.60m** |
| 30 m efficiency (Q=5k) | ~54 %* | 44.3 % | **58.1 %** |
| 30 m efficiency (Q=∞) | 54 % | 54.0 % | **70.2 %** |
| Improvement on 30 m | — | — | **+2.2 dB vs Q=2k** |
| Voltage (Q=5k) | ~1 350 V | 1 730 V | 2 889 V |
| Weight | 3.5 kg | ~1.0 kg | 1.68 kg |
| Cost | $153 | ~$80 | **$108** |
| Complexity | 3 loops + switching | Simplest | Series jumper |

*ML30-6 uses a different loop configuration for 30m; value approximate.

> **Verdict:** For dedicated 30 m operation, this 2-turn design
> delivers 58 % efficiency — substantially better than any single-turn
> design and rivalling the theoretical limit. The 50 kHz band is so
> narrow that a fixed+trimmer capacitor suffices, keeping cost low
> ($108). With 8.7 W ERP from 10 W input, this is a serious
> 30 m antenna despite its simplicity.

---

## 15. Why 2 Turns Is Optimal for 30 m

| Turns | Rr (mΩ) | Rl (mΩ) | η (Q=5k) | η (Q=∞) | Vc Q=5k (V) |
|-------|---------|---------|----------|---------|-------------|
| 1 | 163.9 | 139.4 | 44.3 % | 54.0 % | 1 730 |
| **2** | **655.6** | **278.8** | **58.1 %** | **70.2 %** | **2 889** |
| 3 | 1 475 | 418.2 | ~55 % | 77.9 % | ~3 800 |

- **1 turn:** Good efficiency, easy build. Budget choice.
- **2 turns:** Best practical balance. Voltage within butterfly range.
- **3 turns:** Voltage exceeds 3 800 V — needs vacuum variable cap.
  The η at Q=5000 actually *decreases* vs 2-turn because the massive
  X_L (~2 400 Ω) creates large Rc that offsets the Rr gain.

**2 turns is the sweet spot** — highest practical efficiency without
requiring a vacuum capacitor.

---

## 16. Upgrade Paths

### Path A — Butterfly Cap (Multi-Band Flexibility)

Replace fixed+trimmer with butterfly 2×50 pF. Enables future expansion
to other bands (e.g. add a third turn for 40 m, or use single turn for
20 m). Cost: +$40.

### Path B — Add 20 m Capability

Add a second pair of smaller loops (0.80 m, 2-turn) below this
assembly with a separate cap. Switch between band-optimised 2-turn
pairs using a coax switch. Combines ML20_EFF + ML30_EFF on one mast.

### Path C — Remote Tuning

Stepper motor on the trimmer, controlled by Arduino. Useful since the
1.60 m loop is large enough that hand-reaching the top is awkward.

---

*Design: ML30_EFF | 3/8" copper tube | 2-turn 1.60 m | 10 W | 30 m only | efficiency optimised*
*Generated: 2026-02-07*
