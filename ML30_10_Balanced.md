# ML30_10_Balanced — Magnetic Loop Antenna: 30 m – 10 m (Balanced)

> **Dual 0.80 m loops | 6 bands | 3/8" copper tube | 10 W max | balanced size & efficiency**

---

## 1. Design Overview

A balanced magnetic loop antenna covering **six bands** from 30 m
through 10 m (10.100–29.700 MHz). Two identical 0.80 m loops are
stacked coaxially on the same mast. Each loop is optimised for its
band group with a dedicated capacitor, selected by a simple coax
switch at the base.

| Parameter          | Value                                       |
|--------------------|---------------------------------------------|
| Band coverage      | 30 m, 20 m, 17 m, 15 m, 12 m, 10 m         |
| Frequency range    | 10.100 – 29.700 MHz                         |
| Max power          | 10 W                                        |
| Loop diameter      | **0.80 m** (31.5") — both loops identical   |
| Radiator material  | 3/8" (9.525 mm OD) soft copper tube Type L  |
| Number of loops    | **2** (same size, stacked)                  |
| Coupling loops     | 3/8" tube, 160 mm diameter (×2)             |
| Band switching     | SP3T coax switch (loop select)              |

### Band Assignment

| Loop | Bands | Capacitor | Q | Tuning |
|------|-------|-----------|---|--------|
| **A** | 30 m | Fixed 100 pF C0G + trimmer | ≈ 5 000 | Trimmer adjust |
| **B** | 20 m, 17 m, 15 m, 12 m, 10 m | Butterfly 2×100 pF | ≈ 5 000 | 6:1 vernier |

### Why This Split?

- **30 m needs ~109 pF** — far beyond any butterfly's range. A fixed
  C0G capacitor with a small trimmer is the practical solution. Since
  30 m is only 50 kHz wide, continuous tuning is unnecessary.
- **20m–10m needs 13–57 pF** — perfectly suited to a butterfly cap.
  Five bands are covered by simply turning the vernier knob.
- Both loops use Q ≈ 5 000 capacitors, maximising efficiency across
  all bands.

### Why 0.80 m?

The loop diameter is constrained by 10 m (29.7 MHz): circ/λ must
stay ≤ 0.25, limiting diameter to 0.80 m. At 30 m (10.1 MHz) the
ratio is 0.085 — valid but low, which limits 30 m efficiency. This
is the fundamental trade-off of covering such a wide frequency range
from a compact antenna.

---

## 2. Material Properties

| Property                       | Value                          |
|--------------------------------|--------------------------------|
| Copper tube OD                 | 9.525 mm (3/8")                |
| Copper tube wall (Type L)      | 0.762 mm                       |
| Tube radius *a*                | 4.7625 mm                      |
| Copper conductivity σ          | 5.8 × 10⁷ S/m                 |
| Permeability μ₀                | 4π × 10⁻⁷ H/m                 |

---

## 3. Electrical Parameters (Each Loop)

| Parameter    | Value         |
|--------------|---------------|
| Diameter     | 0.80 m        |
| Radius R     | 0.40 m        |
| Circumference| 2.513 m       |
| Area A       | 0.5027 m²     |
| Inductance L | **2.267 μH**  |

```
L = μ₀ × 0.40 × [ln(8 × 0.40 / 0.004763) − 2]
  = 5.026e-7 × [ln(671.8) − 2]
  = 5.026e-7 × 4.510
  = 2.267 μH
```

---

## 4. Band-by-Band Performance

### 4.1 Loop A — 30 m (Fixed + Trimmer, Q ≈ 5 000)

| Parameter | Value |
|-----------|-------|
| f_mid | 10.125 MHz |
| λ | 29.61 m |
| circ/λ | 0.085 |
| C | 109 pF |
| X_L | 144.2 Ω |
| Rr | 10.2 mΩ |
| Rl | 69.6 mΩ |
| Rc (Q=5k) | 28.8 mΩ |
| **R_total** | **108.6 mΩ** |
| **η** | **9.4 %** |
| Vc | 1 382 V |
| BW | 7.7 kHz |

```
Rr = 31171 × (0.5027 / 29.61²)²
   = 31171 × (5.731e-4)²
   = 10.2 mΩ

Rs = √(π × 10.125e6 × μ₀/σ) = 8.30e-4 Ω/sq
Rl = 8.30e-4 × 2.513 / (π × 0.009525) = 69.6 mΩ
```

With 7.7 kHz bandwidth, 7 tuning positions cover the full 50 kHz
band. Most operators park on one frequency (e.g. 10.136 MHz FT8).

### 4.2 Loop B — 20 m through 10 m (Butterfly, Q ≈ 5 000)

| Band | f_mid (MHz) | λ (m) | circ/λ | C (pF) | X_L (Ω) | Rr (mΩ) | Rl (mΩ) | Rc (mΩ) | R_total (mΩ) | η (%) | Vc (V) | BW (kHz) |
|------|-------------|-------|--------|--------|----------|----------|---------|---------|---------------|-------|--------|----------|
| 20 m | 14.175 | 21.15 | 0.119 | 55.6 | 201.8 | 39.4 | 82.5 | 40.4 | 162.3 | **24.3** | 1 584 | 13.6 |
| 17 m | 18.118 | 16.55 | 0.152 | 34.0 | 257.8 | 105.0 | 93.2 | 51.6 | 249.8 | **42.0** | 1 631 | 19.6 |
| 15 m | 21.225 | 14.13 | 0.178 | 24.8 | 302.1 | 197.7 | 100.9 | 60.4 | 359.0 | **55.1** | 1 594 | 26.3 |
| 12 m | 24.940 | 12.02 | 0.209 | 18.0 | 355.1 | 377.3 | 109.4 | 71.0 | 557.7 | **67.7** | 1 505 | 38.7 |
| 10 m | 28.850 | 10.39 | 0.242 | 13.4 | 410.6 | 676.2 | 117.6 | 82.1 | 875.9 | **77.2** | 1 387 | 58.2 |

### 4.3 Efficiency Summary

| Band | η (%) | ERP (W) | Rating |
|------|-------|---------|--------|
| 30 m | 9.4 | 1.4 | FT8/CW viable |
| 20 m | 24.3 | 3.6 | Solid digital + CW |
| 17 m | 42.0 | 6.3 | Good all-mode |
| 15 m | 55.1 | 8.3 | Very good |
| 12 m | 67.7 | 10.2 | Excellent |
| 10 m | 77.2 | 11.6 | Excellent |
| **Average** | **46.0** | **6.9** | |

> **Average efficiency: 46 %** across six bands from a 0.80 m
> footprint. The high bands (17m–10m) are genuinely competitive.
> The lower bands (30m, 20m) are the compromise — acceptable for
> digital modes and CW, modest for SSB.

---

## 5. Effective Radiated Power (ERP)

Directivity = 1.5 (1.76 dBi). Input = 10 W.

| Band | η (%) | P_rad (W) | ERP (W) |
|------|-------|-----------|---------|
| 30 m | 9.4 | 0.9 | 1.4 |
| 20 m | 24.3 | 2.4 | 3.6 |
| 17 m | 42.0 | 4.2 | 6.3 |
| 15 m | 55.1 | 5.5 | 8.3 |
| 12 m | 67.7 | 6.8 | 10.2 |
| 10 m | 77.2 | 7.7 | 11.6 |

---

## 6. Tuning Capacitors

### Loop A — Fixed + Trimmer (30 m)

| Component | Value |
|-----------|-------|
| Fixed capacitor | 100 pF C0G/NP0, ≥ 2 kV |
| Air trimmer | 1–10 pF |
| Total at resonance | ~109 pF |
| Estimated Q | ≈ 5 000 |
| Combined cost | $11 |

The 30 m band is only 50 kHz wide (C swing: 1.1 pF). Set the trimmer
once and leave it. Retune by slight trimmer adjustment only if needed.

### Loop B — Butterfly Split-Stator (20 m – 10 m)

| Parameter           | Value                            |
|---------------------|----------------------------------|
| Type                | Butterfly split-stator 2×100 pF  |
| Effective range     | 0 – 50 pF (series sections)     |
| Required range      | 13.4 – 55.6 pF                  |
| Plate spacing       | ≥ 1.0 mm (3 000 V effective)    |
| Estimated Q         | 5 000                            |
| Cost                | $50 – $65                        |

Note: With stray capacitance (2–5 pF), the effective range of
0–50 pF + stray covers the required 13.4–55.6 pF. If 20 m bottom
(56.8 pF) cannot be reached, add a small 8–10 pF C0G capacitor in
parallel with the butterfly to shift the range up.

### Tuning Drive

A **6:1 vernier reduction drive** on Loop B's butterfly cap. Narrowest
bandwidth is 13.6 kHz on 20 m — manageable with a 6:1 ratio. Loop A
uses a trimmer adjusted with an insulated screwdriver (no drive needed).

---

## 7. Coupling Loops

Each loop has its own coupling loop. Both are identical.

| Parameter            | Value (each)                  |
|----------------------|-------------------------------|
| Diameter             | 160 mm (6.3")                 |
| Ratio to main loop   | 1 : 5                         |
| Material             | 3/8" soft copper tube         |
| Tube length          | 0.55 m (incl. pigtails)       |
| Connector            | SO-239 chassis mount          |
| Position             | Bottom of each main loop      |

### Switching

An **SP3T coax switch** at the base selects the active loop:
- Position 1: Loop A (30 m)
- Position 2: Loop B (20 m – 10 m)
- Position 3: Bypass / Off

At 10 W, any standard SO-239-based coax switch is adequate.

---

## 8. Physical Layout

```
         ┌── [Fixed 100pF + trimmer] ──┐
         │                               │
    ┌────┘    LOOP A (30 m)         └────┐
   │          D = 0.80 m                  │
   │          Fixed C0G + trimmer        │
    └────┐                          ┌────┘
         │    ┌──[Coupling A]──┐     │
         │    │   160 mm       │     │
         └────┘    └────┬──────┘ ────┘
                        │
               150-200 mm spacing
                        │
         ┌── [Butterfly + 6:1 vernier] ──┐
         │                                │
    ┌────┘    LOOP B (20m–10m)       └────┐
   │          D = 0.80 m                   │
   │          Butterfly Q=5000            │
    └────┐                           ┌────┘
         │    ┌──[Coupling B]──┐      │
         │    │   160 mm       │      │
         └────┘    └────┬──────┘ ─────┘
                        │
                   ─────┼───── Nylon U-bolt clamps
                        │
                   ┌────┴────┐
                   │  PVC    │  1" Schedule 40
                   │  mast   │  0.8 m
                   └────┬────┘
                        │
                  ──────┴────── PVC cross base
```

### SP3T Switch Wiring

```
Loop A (SO-239) ─── coax ─── SP3T pos 1 ─┐
                                           ├─ common ─ to radio
Loop B (SO-239) ─── coax ─── SP3T pos 2 ─┘
                              SP3T pos 3 ── (open)
```

---

## 9. Mechanical Specifications

| Dimension                | Value                        |
|--------------------------|------------------------------|
| Overall width            | 0.80 m (31.5")              |
| Overall height           | ≈ 1.20 m (with mast + base) |
| Loop A weight            | 0.29 kg                      |
| Loop B weight            | 0.29 kg                      |
| Coupling loops (×2)      | 0.12 kg                      |
| Hardware + caps           | ≈ 0.6 kg                     |
| **Total weight**         | **≈ 1.3 kg (2.9 lb)**       |
| Tube: main loops (×2)   | 5.10 m                       |
| Tube: coupling (×2)     | 1.10 m                       |
| **Total tube**           | **6.20 m (20.3 ft)**        |

---

## 10. Bill of Materials

| # | Item | Qty | Est. Cost |
|---|------|-----|-----------|
| 1 | 3/8" soft copper tube Type L, 25 ft | 1 | $35 |
| 2 | Butterfly split-stator 2×100 pF (Loop B) | 1 | $55 |
| 3 | Fixed C0G/NP0 100 pF, 2 kV (Loop A) | 1 | $5 |
| 4 | Air trimmer 1–10 pF (Loop A) | 1 | $6 |
| 5 | 6:1 vernier reduction drive (Loop B) | 1 | $20 |
| 6 | SO-239 chassis-mount connector | 2 | $6 |
| 7 | SP3T coax switch | 1 | $12 |
| 8 | 56 % silver solder + flux | 1 | $15 |
| 9 | 1" PVC pipe + fittings | 1 set | $12 |
| 10 | ABS project boxes | 2 | $8 |
| 11 | Nylon U-bolts, zip ties, hardware | 1 set | $6 |
| | | **Total** | **$180** |

| Upgrade | Delta | New total |
|---------|-------|-----------|
| Premium butterfly Q=7000 | +$20 | $200 |
| 8–10 pF C0G padding cap for 20 m reach | +$2 | $182 |
| Stepper motor remote tune (Loop B) | +$25 | $205 |
| Camera tripod adapter | +$8 | $188 |

---

## 11. Construction Guide

### Step 1 — Form Two 0.80 m Loops

1. Cut two lengths of 2.55 m (8.4 ft) from 3/8" tube
2. Fill with sand, bend into 0.80 m diameter circles
3. Leave 15 mm gap at top of each, clean and tin all four ends

### Step 2 — Form Two Coupling Loops

1. Cut two lengths of 0.55 m (22") from 3/8" tube
2. Bend each into 160 mm diameter circles
3. Leave 10–15 mm gap, clean and tin

### Step 3 — Install Capacitors

**Loop A (30 m):**
1. Solder the 100 pF C0G directly across the gap (short leads!)
2. Mount air trimmer in small project box, wire in parallel
3. Keep total lead length < 15 mm

**Loop B (20m–10m):**
1. Mount butterfly cap in project box at loop top
2. Install 6:1 vernier drive on shaft
3. Connect butterfly to loop ends via copper straps
4. If needed, solder 8–10 pF C0G in parallel for 20 m range

### Step 4 — Solder Coupling Loops

Each coupling loop → its own SO-239 (56 % silver solder).

### Step 5 — Mount on Mast

1. Mount Loop A at top, Loop B 150–200 mm below
2. Both coaxial and coplanar
3. Nylon U-bolts at 2 points per loop
4. Route coax lines down to SP3T switch at base

### Step 6 — Test

1. **Loop A (30 m):** NanoVNA sweep 9.5–10.7 MHz. Adjust trimmer
   for resonance at 10.125 MHz. Adjust coupling loop for SWR < 1.5:1.
2. **Loop B (20m–10m):** Sweep 14–30 MHz. Verify resonances on all
   five bands. Adjust coupling loop for best SWR across bands.

---

## 12. Operating Notes

### Quick-Start

1. Flip SP3T switch to select band group
2. **30 m:** Already tuned by trimmer. Just key up and go.
   Fine-adjust trimmer if you change frequency within 30 m.
3. **20m–10m:** Turn vernier knob to the desired band. Watch SWR
   meter, find the sharp dip, transmit.

### Bandwidth and Retuning

| Band | BW (kHz) | Retune interval |
|------|----------|-----------------|
| 30 m | 7.7 | Every 6–7 kHz (7 positions for whole band) |
| 20 m | 13.6 | Every 10–12 kHz |
| 17 m | 19.6 | Covers most of band |
| 15 m | 26.3 | Every 20–25 kHz |
| 12 m | 38.7 | Covers full band |
| 10 m | 58.2 | Every 50–60 kHz |

### Voltage Safety

| Band | Vc (V) | Status |
|------|--------|--------|
| 30 m | 1 382 | Safe — 2 kV C0G OK |
| 20 m | 1 584 | Safe — butterfly 3 kV eff. OK |
| 17 m | 1 631 | Safe — highest voltage |
| 15 m | 1 594 | Safe |
| 12 m | 1 505 | Safe |
| 10 m | 1 387 | Safe |

Maximum voltage: **1 631 V** on 17 m. All capacitors operate well
within their ratings. No exotic voltage handling required.

### What Can You Work?

| Band | ERP (W) | FT8 DX | CW DX | SSB |
|------|---------|--------|-------|-----|
| 30 m | 1.4 | Worldwide | Continental | Regional |
| 20 m | 3.6 | Worldwide | Continental | Regional |
| 17 m | 6.3 | Worldwide | Worldwide | Regional+ |
| 15 m | 8.3 | Worldwide | Worldwide | Good |
| 12 m | 10.2 | Worldwide | Worldwide | Good |
| 10 m | 11.6 | Worldwide | Worldwide | Good |

---

## 13. Heat Dissipation

| Band | η (%) | P_heat (W) |
|------|-------|------------|
| 30 m | 9.4 | 9.1 |
| 20 m | 24.3 | 7.6 |
| 17 m | 42.0 | 5.8 |
| 15 m | 55.1 | 4.5 |
| 12 m | 67.7 | 3.2 |
| 10 m | 77.2 | 2.3 |

Worst case: 9.1 W on 30 m. Each loop has ~750 cm² copper surface.
No thermal concerns at 10 W.

---

## 14. Design Validation

| Check | Criterion | Status |
|-------|-----------|--------|
| circ/λ range | 0.04–0.25 all bands | 0.085–0.242 OK |
| Max voltage | < cap ratings | 1 631 V < 2 000 V OK |
| Tube bend radius | > 38 mm | All bends ≥ 80 mm OK |
| Coupling loops | 160 mm, 3/8" tube | OK |
| Loop A cap | Covers 30 m | 109 pF from 100+trimmer OK |
| Loop B cap | Covers 20m–10m | 13–57 pF butterfly OK |
| Total weight | One-person carry | 1.3 kg OK |
| Width | Fits through doors | 0.80 m OK |

---

## 15. Comparison with Other Designs

| Aspect | ML20_10 | ML20_10_EFF | **ML30_10_Balanced** |
|--------|---------|-------------|----------------------|
| Bands | 20m–10m (5) | 20m–10m (5) | **30m–10m (6)** |
| Loops | 1 | 2 | **2** |
| 30 m | No | No | **Yes (9.4 %)** |
| 20 m η | 17.7 % (Q=2k) | 24.3 % (Q=5k) | **24.3 %** (Q=5k) |
| 17m–10m η | 32–68 % (Q=2k) | 42–77 % (split) | **42–77 %** (Q=5k) |
| Avg η | 43.7 % (Q=2k) | 46.9 % | **46.0 %** |
| Width | 0.80 m | 0.80 m | **0.80 m** |
| Switching | None | SP3T | **SP3T** |
| Weight | 0.7 kg | 1.2 kg | **1.3 kg** |
| Cost | $97–127 | $210 | **$180** |

> **Verdict:** This design adds 30 m coverage to the ML20_10 family
> with no increase in footprint. 20m–10m performance matches the
> best single-loop Q=5000 numbers. 30 m at 9.4 % is a physics
> compromise at 0.80 m — but 1.4 W ERP is enough for FT8 and CW
> contacts worldwide. For serious 30 m efficiency, see the dedicated
> ML30_EFF designs (1.60 m or 2.00 m loops).

---

## 16. Simplified Alternative — Single Loop, No Switching

For operators who want **zero complexity**, a single 0.80 m loop with
one air variable capacitor covers all six bands:

| Parameter | Value |
|-----------|-------|
| Loop | 1 × 0.80 m |
| Capacitor | Air variable 10–150 pF, Q ≈ 2 000 |
| Bands | 30 m – 10 m continuous |
| Switching | **None** — just turn the knob |
| Cost | ~$97 |

| Band | η (Q=2k) | ERP |
|------|----------|-----|
| 30 m | 6.7 % | 1.0 W |
| 20 m | 17.7 % | 2.7 W |
| 17 m | 32.1 % | 4.8 W |
| 15 m | 44.0 % | 6.6 W |
| 12 m | 56.8 % | 8.5 W |
| 10 m | 67.7 % | 10.2 W |
| **Average** | **37.5 %** | |

This gives up 8.5 % average efficiency vs the dual-loop design
(37.5 % vs 46.0 %, or −0.9 dB) but eliminates the second loop,
switch, and butterfly cap. For many operators, this simplicity is
worth the trade.

---

## 17. Upgrade Paths

### Path A — Add 6 m

Add a third 0.44 m loop below Loop B with its own small cap and
coupling loop. Extends coverage to 50 MHz. See ML20_6 for the 0.44 m
loop specifications.

### Path B — Improve 30 m

Replace Loop A with a dedicated 2-turn 0.80 m loop (series-connected)
for 30 m. This boosts 30 m efficiency from 9.4 % to ~15 % (+2 dB).
See ML30_Balanced for the 2-turn 30 m approach.

### Path C — Remote Tuning

Stepper motor on Loop B's vernier drive. Essential for mast-mounted
operation. Loop A needs no motor (set-and-forget trimmer for 30 m).

---

*Design: ML30_10_Balanced | 3/8" copper tube | dual 0.80 m | 10 W | 30 m – 10 m | 6 bands*
*Generated: 2026-02-07*
