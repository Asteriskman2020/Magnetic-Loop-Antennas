# ML10_Balanced — Magnetic Loop Antenna: 10 m Band (Balanced Size & Efficiency)

> **Single-loop design | 0.50 m diameter | 3/8" copper tube | 10 W max | 10 m only**

---

## 1. Design Overview

A magnetic loop antenna for the **10 m band** (28.000–29.700 MHz) that
balances physical size against efficiency. A 0.50 m (19.7") loop is
remarkably compact — small enough to sit on a desk, mount on a camera
tripod, or tuck inside a daypack — yet delivers **46 % efficiency**
thanks to the short wavelength of 10 m.

| Parameter          | Value                                       |
|--------------------|---------------------------------------------|
| Band coverage      | 10 m (28.000 – 29.700 MHz)                  |
| Band width         | 1.700 MHz                                   |
| Max power          | 10 W                                        |
| Loop diameter      | **0.50 m** (19.7")                          |
| Number of turns    | **1** (single loop)                         |
| Radiator material  | 3/8" (9.525 mm OD) soft copper tube Type L  |
| Coupling loop      | 3/8" soft copper tube, 100 mm diameter       |
| Tuning capacitor   | Butterfly split-stator (Q ≈ 5 000)          |
| Band switching     | **None** — single band, continuous tuning   |

### Why 10 m Is Ideal for Magnetic Loops

At 10 m (λ ≈ 10.4 m), even a small loop has a favourable circ/λ ratio.
The radiation resistance scales as (A/λ²)² — with short λ, Rr is much
larger relative to copper loss than on lower bands. A 0.50 m loop on
10 m has **Rr/Rl = 1.40** — radiation resistance already exceeds copper
loss. No multi-turn tricks are needed.

### Why 0.50 m?

The maximum allowed diameter (circ/λ ≤ 0.25 at 29.7 MHz) is 0.80 m.
A 0.50 m loop sits at the balanced midpoint:

| Diameter | circ/λ (mid) | η (Q=5k) | ERP (W) | Use case |
|----------|-------------|----------|---------|----------|
| 0.30 m | 0.091 | 16.4 % | 2.5 | Ultra-portable |
| 0.40 m | 0.121 | 31.1 % | 4.7 | Compact |
| **0.50 m** | **0.151** | **46.3 %** | **6.9** | **Balanced (this)** |
| 0.60 m | 0.181 | 59.4 % | 8.9 | Larger |
| 0.80 m | 0.242 | 77.2 % | 11.6 | Maximum |

> At 0.50 m you get nearly half the maximum possible efficiency in an
> antenna that fits through any doorway, sits on a shelf, and weighs
> under 0.5 kg. On 10 m, **band propagation is the limiting factor**,
> not the antenna — when the band opens, this loop works the world.

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
| Diameter     | 0.50 m        |
| Radius R     | 0.25 m        |
| Circumference| 1.571 m       |
| Area A       | 0.1963 m²     |
| Inductance L | **1.269 μH**  |

```
L = μ₀ × R × [ln(8R/a) − 2]
  = 4π×10⁻⁷ × 0.25 × [ln(8 × 0.25 / 0.004763) − 2]
  = 3.142e-7 × [ln(420.0) − 2]
  = 3.142e-7 × [6.040 − 2]
  = 3.142e-7 × 4.040
  = 1.269 μH
```

### At Band Centre (28.850 MHz)

| Quantity         | Value      | Derivation                          |
|------------------|------------|-------------------------------------|
| λ                | 10.39 m    | c / f                               |
| circ/λ           | 0.151      | 1.571 / 10.39                       |
| X_L              | 230.0 Ω    | 2πfL                                |
| C (resonant)     | 24.0 pF    | 1 / (4π²f²L)                       |
| Rr (radiation)   | 103.0 mΩ   | 31171 × (A/λ²)²                    |
| Rs (skin effect) | 1.401 mΩ/sq| √(πfμ₀/σ)                          |
| Rl (copper loss) | 73.6 mΩ    | Rs × circ / (π × OD)               |
| Rr/Rl ratio      | **1.40**   | Rr dominates — healthy ratio        |

```
Rr = 31171 × (0.1963 / 10.39²)²
   = 31171 × (0.1963 / 107.95)²
   = 31171 × (1.818e-3)²
   = 31171 × 3.305e-6
   = 103.0 mΩ

Rs = √(π × 28.85e6 × 1.2566e-6 / 5.8e7) = 1.401e-3 Ω/sq

Rl = 1.401e-3 × 1.571 / (π × 0.009525) = 73.6 mΩ
```

---

## 4. Performance

### 4.1 Efficiency vs Capacitor Quality (at 28.850 MHz)

| Cap Q  | Rc (mΩ) | R_total (mΩ) | η (%)     | Vc (V) | BW (kHz) | Q_L  |
|--------|---------|--------------|-----------|--------|----------|------|
| 1 000  | 230.0   | 406.6        | **25.3**  | 1 142  | 69.8     | 413  |
| 2 000  | 115.0   | 291.6        | **35.3**  | 1 347  | 49.3     | 585  |
| 3 000  | 76.7    | 253.3        | **40.7**  | 1 445  | 42.6     | 677  |
| 5 000  | 46.0    | 222.6        | **46.3**  | 1 542  | 36.6     | 789  |
| 7 000  | 32.9    | 209.5        | **49.2**  | 1 589  | 33.8     | 854  |
| 10 000 | 23.0    | 199.6        | **51.6**  | 1 630  | 31.6     | 913  |
| ∞      | 0       | 176.6        | **58.3**  | 1 737  | 26.5     | 1 089|

```
Example (Q = 5000):
  X_L = 230.0 Ω
  Rc = 230.0 / 5000 = 46.0 mΩ
  R_total = 103.0 + 73.6 + 46.0 = 222.6 mΩ
  η = 103.0 / 222.6 = 46.3 %
  Vc = √(10 / 0.2226) × 230.0 = 6.70 × 230.0 = 1 542 V
  Q_L = 230.0 / 0.2226 = 1 033
  BW = 28.85e6 / 1033 = 27.9 kHz
```

### 4.2 Across the 10 m Band (Q = 5 000)

| Freq (MHz) | λ (m) | circ/λ | C (pF) | X_L (Ω) | Rr (mΩ) | Rl (mΩ) | Rc (mΩ) | R_total (mΩ) | η (%) | Vc (V) | BW (kHz) |
|------------|-------|--------|--------|----------|---------|---------|---------|--------------|-------|--------|----------|
| 28.000 | 10.71 | 0.147 | 25.5 | 223.3 | 91.4 | 72.5 | 44.7 | 208.6 | **43.8** | 1 546 | 26.2 |
| 28.500 | 10.52 | 0.149 | 24.6 | 227.2 | 98.1 | 73.1 | 45.4 | 216.6 | **45.3** | 1 544 | 27.2 |
| 28.850 | 10.39 | 0.151 | 24.0 | 230.0 | 103.0 | 73.6 | 46.0 | 222.6 | **46.3** | 1 542 | 27.9 |
| 29.200 | 10.27 | 0.153 | 23.4 | 232.8 | 108.1 | 74.0 | 46.6 | 228.7 | **47.3** | 1 539 | 28.7 |
| 29.700 | 10.09 | 0.156 | 22.6 | 236.8 | 115.8 | 74.7 | 47.4 | 237.9 | **48.7** | 1 536 | 29.8 |

**Average efficiency: 46.3 %** across the full 1.7 MHz band.

Efficiency improves toward the top of the band (higher circ/λ → more
Rr). Voltage is nearly flat at ~1 540 V — very manageable.

Capacitance range: **22.6 – 25.5 pF** (swing: 2.9 pF).

### 4.3 Sub-Band Allocation

| Sub-band | Frequency (MHz) | Mode | η (%) | BW (kHz) |
|----------|-----------------|------|-------|----------|
| CW | 28.000 – 28.070 | CW/Beacon | 43.8 | 26.2 |
| Digital | 28.070 – 28.190 | FT8/FT4/RTTY | 44.2 | 26.6 |
| SSB low | 28.300 – 28.600 | Phone | 45.5 | 27.3 |
| SSB high | 28.600 – 29.000 | Phone | 46.5 | 28.0 |
| Satellite | 29.300 – 29.510 | Satellite | 47.7 | 29.0 |
| FM repeater | 29.510 – 29.700 | FM | 48.5 | 29.7 |

The FT8 calling frequency is **28.074 MHz**. With 26 kHz bandwidth,
a single cap setting covers the entire FT8 window.

---

## 5. Effective Radiated Power (ERP)

Directivity = 1.5 (1.76 dBi). Input = 10 W.

| Freq (MHz) | η (%) | P_rad (W) | ERP (W) |
|------------|-------|-----------|---------|
| 28.000 | 43.8 | 4.4 | 6.6 |
| 28.500 | 45.3 | 4.5 | 6.8 |
| 28.850 | 46.3 | 4.6 | 6.9 |
| 29.200 | 47.3 | 4.7 | 7.1 |
| 29.700 | 48.7 | 4.9 | 7.3 |

> At 6.6–7.3 W ERP on 10 m, this antenna is competitive for **all
> modes**. When 10 m is open (solar maximum, daytime F2 propagation),
> DX contacts are routine even with low power. 10 m is the one HF
> band where a small magnetic loop can genuinely compete.

---

## 6. Tuning Capacitor

### Required Capacitance

| Edge  | Frequency   | C required |
|-------|-------------|------------|
| Low   | 28.000 MHz  | 25.5 pF    |
| High  | 29.700 MHz  | 22.6 pF    |
| **Swing** |         | **2.9 pF** |

The 2.9 pF swing across 1.7 MHz is manageable with a butterfly cap
and a reduction drive.

### Recommended: Butterfly Split-Stator

| Parameter           | Value                            |
|---------------------|----------------------------------|
| Type                | Butterfly split-stator 2×50 pF   |
| Effective range     | 0 – 25 pF (series)              |
| Plate spacing       | ≥ 1.0 mm (3 000 V effective)    |
| Voltage rating      | ≥ 2 000 V effective              |
| Estimated Q         | 5 000                            |
| Cost                | $45 – $55                        |

With stray capacitance of 2–5 pF, the butterfly's effective range of
0–25 pF + stray covers the required 22.6–25.5 pF comfortably.

### Tuning Drive

A **6:1 vernier reduction drive** provides adequate resolution. The
10 m band is 1.7 MHz wide with ~28 kHz bandwidth — about 60 tuning
positions across the band. The 6:1 ratio makes this manageable.

### Alternative: Air Variable (Budget)

| Parameter           | Value                            |
|---------------------|----------------------------------|
| Type                | Air variable 10–50 pF            |
| Estimated Q         | 2 000                            |
| Voltage rating      | ≥ 2 000 V (1 mm spacing)        |
| Cost                | $15 – $25                        |

An air variable capacitor gives η = 35.3 % (vs 46.3 % with butterfly).
That's −1.2 dB — a modest penalty for significant cost savings.
Standard air variables with 1 mm plate spacing handle the 1 546 V
easily.

---

## 7. Coupling Loop

| Parameter            | Value                         |
|----------------------|-------------------------------|
| Diameter             | **100 mm** (3.9")             |
| Ratio to main loop   | 1 : 5                         |
| Circumference        | 0.314 m                       |
| Tube length required | ≈ 0.40 m (incl. pigtails)     |
| Material             | 3/8" soft copper tube         |
| Connector            | SO-239 chassis mount          |
| Position             | Bottom of main loop           |

### Fine-Tuning the Match

1. Start with 100 mm coupling loop centred at the bottom
2. Adjust SWR by rotating ±15° off-axis or sliding ±20 mm
3. Target: SWR < 1.5:1 at resonance
4. The coupling loop may need slight adjustment when moving
   between the CW and FM ends of the band (3.6 kΩ to 4.0 kΩ
   impedance shift)

---

## 8. Physical Layout

### Construction Diagram

```
            ┌───[Cap box: Butterfly + 6:1 vernier]───┐
            │                                         │
       ┌────┘                                    └────┐
      │                                                │
     │           Main Loop                              │
     │           D = 0.50 m (19.7")                     │
     │           3/8" copper tube                       │
      │                                                │
       └────┐                                    ┌────┘
            │          ┌──────┐                   │
            │          │ C/L  │                   │
            │          │100mm │                   │
            │          └──┬───┘                   │
            └─────────────┼───────────────────────┘
                          │
                       SO-239
                          │
                     ─────┼───── Nylon clamps
                          │
                     ┌────┴────┐
                     │  PVC    │  1" Sch 40
                     │  mast   │  0.5 m
                     └────┬────┘
                          │
                    ──────┴────── PVC base or
                                  camera tripod
```

### Physical Envelope

The entire antenna occupies a **0.50 × 0.50 × 0.70 m** volume
(width × depth × height including short mast).

- Fits easily through any doorway
- Sits on a desk, shelf, or window sill
- Mounts on any camera tripod with 1/4"-20 adapter
- Fits in a daypack or laptop bag for portable operation
- One person sets up in under 5 minutes

---

## 9. Mechanical Specifications

| Dimension                | Value                        |
|--------------------------|------------------------------|
| Overall width            | 0.50 m (19.7")              |
| Overall height           | ≈ 0.70 m (with mast)        |
| Main loop weight         | 0.19 kg (0.4 lb)             |
| Coupling loop weight     | 0.05 kg (0.1 lb)             |
| Hardware + cap            | ≈ 0.25 kg                    |
| **Total weight**         | **≈ 0.5 kg (1.1 lb)**       |
| Tube: main loop          | 1.62 m (5.3 ft)              |
| Tube: coupling loop      | 0.41 m (1.3 ft)              |
| **Total tube**           | **2.03 m (6.7 ft)**         |

At **0.5 kg (1.1 lb)** this is the lightest antenna in the design
family. It uses only 2 m of copper tube — a fraction of a standard
25 ft (7.6 m) coil.

---

## 10. Bill of Materials

| # | Item | Qty | Est. Cost |
|---|------|-----|-----------|
| 1 | 3/8" soft copper tube Type L, 25 ft | 1 | $35 |
| 2 | Butterfly split-stator 2×50 pF | 1 | $50 |
| 3 | 6:1 vernier reduction drive | 1 | $18 |
| 4 | SO-239 chassis-mount connector | 1 | $3 |
| 5 | 56 % silver solder + flux | 1 | $15 |
| 6 | 1" PVC pipe + fittings | 1 set | $8 |
| 7 | ABS project box | 1 | $4 |
| 8 | Nylon U-bolts, zip ties, hardware | 1 set | $5 |
| | | **Total** | **$138** |

> **Note:** Only 2.03 m of the 7.6 m (25 ft) copper tube coil is used.
> The remaining 5.6 m is enough for a second antenna or spare parts.

| Budget option | Replace | Delta | Total |
|---------------|---------|-------|-------|
| Air variable 10–50 pF (Q≈2000) | items 2+3 | −$48 | $90 |

| Upgrade | Delta | New total |
|---------|-------|-----------|
| Premium butterfly Q=7000 | +$20 | $158 |
| Camera tripod adapter | +$8 | $146 |
| Stepper motor remote tune | +$25 | $163 |

---

## 11. Construction Guide

### Step 1 — Form the Main Loop

1. Cut 1.62 m (5.3 ft) of 3/8" soft copper tube
2. Fill with fine sand, plug ends with masking tape
3. Bend into a 0.50 m diameter circle:
   - A paint can or bucket (D ≈ 250 mm) makes a starting form
   - Relax the bend to 0.50 m over a flat template
   - This is a small, easy bend — one person, no jig needed
4. Leave **15 mm gap** at the top
5. Empty sand, clean tube ends with 220-grit emery cloth
6. Tin tube ends with 56 % silver solder

### Step 2 — Form the Coupling Loop

1. Cut 0.41 m (16") of 3/8" tube
2. Bend into a 100 mm diameter circle (soda can as form)
3. Leave 10 mm gap, clean and tin

### Step 3 — Install Capacitor

1. Mount butterfly cap in ABS project box
2. Install 6:1 vernier reduction drive on shaft
3. Connect cap to loop ends via short copper straps (< 10 mm lead)
4. Mount box at top of loop gap

### Step 4 — Solder Coupling Loop

1. Solder one tube end to SO-239 centre pin
2. Solder the other to SO-239 ground lug
3. Use 56 % silver solder for all joints

### Step 5 — Mount

1. Attach main loop to PVC mast with nylon U-bolts (2 points)
2. Position coupling loop at bottom, centred and coplanar
3. Route coax from SO-239 down the mast

### Step 6 — Test and Tune

1. Connect NanoVNA or SWR meter
2. Sweep 27.5–30.0 MHz — find the resonance dip
3. Turn vernier to tune across the band
4. Adjust coupling loop position for SWR < 1.5:1
5. Mark key dial positions: FT8 (28.074), CW (28.050),
   SSB (28.400), FM (29.600)

---

## 12. Operating Notes

### Bandwidth and Coverage

| Cap Q | BW (kHz) | Tuning positions for full 1.7 MHz |
|-------|----------|-----------------------------------|
| 2 000 | 49.3 | ~35 |
| 5 000 | 27.9 | ~61 |
| 7 000 | 25.7 | ~66 |

With 28 kHz bandwidth (Q=5000), the FT8 window (28.074 ± 3 kHz) is
covered by a single setting. For ragchew SSB, retune every 20–25 kHz
as you move across the band.

### Key 10 m Frequencies

| Frequency (MHz) | Mode | Notes |
|-----------------|------|-------|
| 28.050 | CW | CW calling |
| 28.074 | FT8 | FT8 calling frequency |
| 28.078 | FT4 | FT4 calling frequency |
| 28.120 | RTTY | RTTY calling |
| 28.200 | Beacons | NCDXF/IARU beacons |
| 28.400 | SSB | SSB calling frequency |
| 29.520 | FM | FM simplex |
| 29.600 | FM | FM calling frequency |

### Voltage Safety

| Cap Q | Vc (V) | Rating needed |
|-------|--------|---------------|
| 2 000 | 1 347 | ≥ 1 500 V |
| 5 000 | 1 542 | ≥ 2 000 V |
| 7 000 | 1 589 | ≥ 2 000 V |

Voltages are **moderate**. A butterfly cap with 1.0 mm plate spacing
(~3 000 V effective) handles this with excellent margin. Even a
standard air variable cap (1 mm spacing ≈ 2 000 V) is adequate.

- Maintain 0.3 m clearance during TX
- RF burns at 1 500 V are painful but the small loop size makes
  accidental contact unlikely

### What Can You Work?

10 m is a **propagation-dependent** band. When the band opens
(solar maximum, high solar flux, daytime F2 layer), worldwide DX
is routine. When closed, even a beam antenna hears nothing.

| Mode | ERP needed | This antenna | When band open |
|------|-----------|--------------|----------------|
| FT8/FT4 | 0.5 W | 6.9 W | **Worldwide DX** |
| CW | 1–3 W | 6.9 W | **Worldwide DX** |
| SSB | 5–10 W | 6.9 W | **Good DX** |
| FM | 5–10 W | 7.3 W | **Local + skip** |
| Beacon | — | — | **Monitor worldwide** |

> **Key insight:** On 10 m, the antenna is not the bottleneck —
> propagation is. At 6.9 W ERP, this loop is competitive with a
> dipole at the same power level. When the band is open, you will
> work DX. Focus on operating when solar conditions are favourable.

### Heat Dissipation

| Cap Q | η (%) | P_heat (W) |
|-------|-------|------------|
| 2 000 | 35.3 | 6.5 |
| 5 000 | 46.3 | 5.4 |

Worst case: 6.5 W dissipated over ~470 cm² copper surface. No
thermal concerns at 10 W.

---

## 13. Design Validation

| Check | Criterion | Status |
|-------|-----------|--------|
| circ/λ range | 0.04–0.25 | 0.147–0.156 OK |
| Max voltage | < cap rating | 1 589 V < 3 000 V OK |
| Tube bend radius | > 38 mm | All bends = 250 mm OK |
| Coupling loop | 100 mm, fits 3/8" tube | OK |
| Cap range | Covers full band | 22.6–25.5 pF OK |
| Total weight | Ultra-light | 0.5 kg OK |
| Fits through doors | Width < 0.8 m | 0.50 m OK |
| Total tube | Fits 25 ft coil | 2.03 m << 7.6 m OK |

---

## 14. Comparison with Other Designs

### 10 m Loop at Different Sizes

| Diameter | circ/λ | η (Q=5k) | ERP (W) | Vc (V) | Weight | Best for |
|----------|--------|----------|---------|--------|--------|----------|
| 0.30 m | 0.091 | 16.4 % | 2.5 | 1 388 | 0.3 kg | QRP backpack |
| 0.40 m | 0.121 | 31.1 % | 4.7 | 1 479 | 0.4 kg | Compact travel |
| **0.50 m** | **0.151** | **46.3 %** | **6.9** | **1 542** | **0.5 kg** | **Balanced (this)** |
| 0.60 m | 0.181 | 59.4 % | 8.9 | 1 578 | 0.6 kg | Home/balcony |
| 0.80 m | 0.242 | 77.2 % | 11.6 | 1 387 | 0.9 kg | Maximum eff |

### Cross-Band Comparison at 0.50 m

| Band | circ/λ | Rr (mΩ) | η (Q=5k) | ERP (W) |
|------|--------|---------|----------|---------|
| 30 m | 0.016 | 0.05 | 0.1 % | 0.02 |
| 20 m | 0.024 | 0.4 | 0.4 % | 0.06 |
| 15 m | 0.083 | 7.4 | 8.2 % | 1.2 |
| 12 m | 0.131 | 28.5 | 26.2 % | 3.9 |
| **10 m** | **0.151** | **103.0** | **46.3 %** | **6.9** |

> A 0.50 m loop is impractical on lower bands but **excellent on
> 10 m**. This is the band where small loops truly shine.

---

## 15. 10 m Band Characteristics

### When Does 10 m Open?

10 m propagation is driven by the **solar cycle** and **F2 layer**
ionisation:

| Solar flux (SFI) | Typical propagation | Conditions |
|-------------------|---------------------|------------|
| > 150 | Worldwide, all day | Solar maximum |
| 100–150 | Continental, midday | Moderate activity |
| 70–100 | Sporadic E, local | Low activity |
| < 70 | Usually closed | Solar minimum |

- **Best operating times:** 0800–1800 local time during solar maximum
- **Sporadic E:** May–July, brief openings up to 2000+ km
- **F2 propagation:** October–March peaks during solar max years
- **Current solar cycle 25** peaked in 2024–2025, making 2025–2027
  excellent years for 10 m operation

### Why 10 m + Small Loop = Great Combination

1. **Short λ** → high Rr even from small aperture
2. **When open, band is loud** → even modest ERP works DX
3. **Wide band (1.7 MHz)** → diverse modes: CW, FT8, SSB, FM, satellite
4. **Low noise** → 10 m has less atmospheric noise than lower bands
5. **Compact antenna** → 0.50 m loop is genuinely portable

---

## 16. Upgrade Paths

### Path A — Go Bigger (+dB for Free)

Increase diameter to 0.60 m (+2.1 dB, η = 59 %) or 0.80 m (+4.0 dB,
η = 77 %). Same cap, same design, just more tube.

### Path B — Add 12 m

Use the same 0.50 m loop with a slightly higher capacitance setting.
At 24.94 MHz (12 m), the loop gives η = 26.2 %. Two bands from
one loop and one cap — just turn the knob.

### Path C — Premium Cap

Butterfly Q=7000 raises efficiency from 46.3 % to 49.2 % (+0.3 dB).
Marginal improvement — cap Q matters less on 10 m where Rr is already
strong.

### Path D — Remote Tuning

Stepper motor on the vernier for remote/mast-mounted operation.
With 60+ tuning positions across 1.7 MHz, remote tuning is
valuable for hands-free band scanning.

---

*Design: ML10_Balanced | 3/8" copper tube | single 0.50 m loop | 10 W | 10 m only | balanced size & efficiency*
*Generated: 2026-02-07*
