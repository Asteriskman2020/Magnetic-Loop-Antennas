# ML20-6: Single-Loop Efficiency-Optimized Magnetic Loop

## 20 m through 6 m — Single Loop — 10 W Max — 3/8" Copper Tube

### Design Philosophy

A single magnetic loop covering 20 m to 6 m (14.0–54 MHz, 3.9:1 frequency
ratio). The loop is sized at the **maximum diameter** that maintains proper
magnetic-loop behaviour across the entire range.

At 54 MHz (top of 6 m), the circumference must stay at or below 0.25 λ.
This sets the **absolute maximum diameter at 0.44 m** (17.3 inches). No
single loop can be more efficient while covering the full 20 m – 6 m range.

With the loop diameter fixed by physics, the **primary efficiency lever is
capacitor quality.** This design document quantifies the impact of capacitor
Q on real-world efficiency — the single most important and most overlooked
factor in small magnetic loop performance.

---

## Loop Specifications

```
            ┌── Butterfly Cap ──┐
        ────┘   (split-stator)  └────     10–150 pF effective
       /         high Q ≥ 5000       \
      │                               │
      │    0.44 m (17.3 in) diameter  │    Main loop
      │       L = 1.08 μH            │    3/8" Cu tube
      │       A = 0.152 m²           │
       \                             /
        ──┐    ┌───────────┐    ┌──
          │    │  Coupling  │   │     100 mm (4") coupling loop
          │    │   Loop     │   │     3/8" Cu tube, 1:4.4 ratio
          │    └────┤├──────┘   │
          └─────────────────────┘
                    ││
                50 Ω coax
```

| Parameter | Value |
|-----------|-------|
| Main loop diameter | 0.44 m (17.3 in) |
| Circumference | 1.38 m (4.5 ft) |
| Tube | 3/8" OD (9.525 mm) soft copper, Type L |
| Inductance | 1.08 μH |
| Loop area | 0.152 m² |
| Coupling loop diameter | 100 mm (4.0 in) |
| Circ / λ range | 0.065 (20 m) – 0.249 (6 m) |

### Why 0.44 m Is Optimal

The maximum loop diameter for magnetic-loop behaviour at frequency f is:

    d_max = 0.25 × c / (π × f_max) = 0.25 × 300 / (π × 54) = 0.442 m

At 0.44 m, the circumference is exactly 0.249 λ at 54 MHz — the
theoretical ceiling. Any larger loop leaves magnetic-loop behaviour on 6 m.
Any smaller loop sacrifices efficiency on 20 m with no benefit.

---

## Theoretical Performance (Perfect Capacitor)

These values assume a lossless tuning capacitor (Q = ∞). They represent the
**absolute maximum** efficiency achievable with a 0.44 m / 3/8" copper loop.
Real performance depends on capacitor quality — see the next section.

| Band | Freq (MHz) | C (pF) | Circ/λ | Rr (mΩ) | Rloss (mΩ) | η_max (%) | dB | BW (kHz) | Vcap (V) |
|------|-----------|--------|--------|---------|-----------|----------|------|---------|---------|
| 20 m | 14.175 | 117 | 0.065 | 3.6 | 45.4 | **7.4** | −11.3 | 7.2 | 1 376 |
| 17 m | 18.100 | 72 | 0.083 | 9.6 | 51.3 | **15.7** | −8.0 | 9.0 | 1 576 |
| 15 m | 21.225 | 52 | 0.098 | 18.1 | 55.5 | **24.6** | −6.1 | 10.8 | 1 680 |
| 12 m | 24.940 | 38 | 0.115 | 34.5 | 60.2 | **36.4** | −4.4 | 13.9 | 1 741 |
| 10 m | 28.500 | 29 | 0.131 | 58.7 | 64.3 | **47.7** | −3.2 | 18.1 | 1 746 |
| 6 m | 50.100 | 9.3 | 0.231 | 561 | 85.3 | **86.8** | −0.6 | 95.1 | 1 339 |

> These are **upper bounds**. No real build will reach them. The next section
> shows what you actually get.

---

## The Critical Role of Capacitor Q

In a magnetic loop, the tuning capacitor carries the **full circulating
current** of the resonant circuit. At resonance the reactive energy sloshes
between the loop inductance and the capacitor. Any loss in the capacitor
is burned as heat and directly reduces radiated power.

The capacitor's equivalent series resistance is:

    R_cap = X_L / Q_cap

Where X_L is the loop's inductive reactance (= capacitive reactance at
resonance) and Q_cap is the capacitor's quality factor.

In this loop, X_L ranges from **96 Ω (20 m) to 340 Ω (6 m)**. Even a
modest dissipation factor (1/Q) creates tens of milliohms of loss —
comparable to or exceeding the copper loss of the loop itself.

### Efficiency vs Capacitor Q — Full Table

Three realistic build tiers plus the theoretical maximum:

| | **Budget Build** | **Mid-Range** | **Best Practical** | **Theoretical** |
|---|---|---|---|---|
| **Capacitor type** | Air var. w/ wipers | Decent butterfly | Premium butterfly | Perfect (ref.) |
| **Typical Q** | 1 500 | 3 000 | 5 000 | ∞ |

| Band | R_cap (mΩ) | η (%) | R_cap (mΩ) | η (%) | R_cap (mΩ) | η (%) | η_max (%) |
|------|-----------|-------|-----------|-------|-----------|-------|----------|
| | Q=1500 | | Q=3000 | | Q=5000 | | Q=∞ |
| 20 m | 64.2 | **3.2** | 32.1 | **4.4** | 19.3 | **5.3** | 7.4 |
| 17 m | 81.9 | **6.7** | 41.0 | **9.4** | 24.6 | **11.2** | 15.7 |
| 15 m | 96.1 | **10.7** | 48.0 | **14.9** | 28.8 | **17.7** | 24.6 |
| 12 m | 112.9 | **16.6** | 56.5 | **22.8** | 33.9 | **26.8** | 36.4 |
| 10 m | 129.1 | **23.3** | 64.5 | **31.3** | 38.7 | **36.3** | 47.7 |
| 6 m | 226.9 | **64.2** | 113.4 | **73.8** | 68.1 | **78.5** | 86.8 |
| **Avg** | | **20.8** | | **26.1** | | **29.3** | 36.4 |

### What This Means

```
Efficiency on 10 m:

  Budget (Q=1500):     ████████████░░░░░░░░░░░░░░░░░░░░░  23 %
  Mid-range (Q=3000):  ███████████████░░░░░░░░░░░░░░░░░░░  31 %
  Best pract. (Q=5000):██████████████████░░░░░░░░░░░░░░░░  36 %
  Theory (Q=∞):        ████████████████████████░░░░░░░░░░░  48 %
                       0%              25%             50%

Efficiency on 6 m:

  Budget (Q=1500):     ████████████████████████████████░░░  64 %
  Mid-range (Q=3000):  ██████████████████████████████████░  74 %
  Best pract. (Q=5000):████████████████████████████████████ 79 %
  Theory (Q=∞):        ████████████████████████████████████ 87 %
                       0%              50%            100%
```

**Upgrading from a budget to a best-practical capacitor improves 10 m
efficiency by 56 % (relative) and 6 m by 22 %.** This is a bigger gain
than any other single design change — larger than increasing the loop
diameter by 10 % (which isn't possible here anyway).

---

## Recommended Build: Q ≈ 5000 Butterfly

### Why a Butterfly (Split-Stator) Capacitor

| Property | Standard air var. | Butterfly (split-stator) |
|----------|------------------|-------------------------|
| Q at HF | 1 000 – 2 500 | 3 000 – 7 000 |
| Wiping contacts | Yes (lossy) | **None** (rotor floats) |
| Voltage handling | V_total | **2 × V_per_section** |
| Common-mode current | Yes | **Minimal** (balanced) |
| Typical price | $10–20 | $25–50 |

The butterfly's floating rotor eliminates lossy sliding contacts — the
primary source of resistive loss in standard air variables. Each half
sees half the voltage, effectively doubling the voltage rating.

### Capacitor Sizing

For a butterfly with two equal sections of C_section each:

    C_effective = C_section / 2    (series combination)

| Parameter | Requirement | Butterfly Spec |
|-----------|------------|----------------|
| C_eff max (20 m) | 117 pF | C_section ≥ 234 pF → **use 2 × 250 pF** |
| C_eff min (6 m) | 9.3 pF | C_section ≥ 18.6 pF → typical min ~10 pF ✓ |
| Voltage at 10 W | 1 746 V peak | Per section: 873 V → **2 mm gap OK** |
| Plate spacing | ≥ 1 mm per section | 1.5–2 mm recommended |

A **2 × 250 pF butterfly** with 2 mm plate spacing covers the full
20 m – 6 m range in a single component:

    C_eff range: ~5 pF (min) to ~125 pF (max)
    + stray capacitance: ~3–5 pF

    Total range: ~8–130 pF

- At 20 m (117 pF needed): butterfly near full mesh — ✓
- At 6 m (9.3 pF needed): butterfly near minimum + stray — tight but
  achievable with short leads (< 5 mm) and clean construction.

**One component. No switches. No trimmers. Full band coverage.**

### If 6 m Tuning Is Tight

If stray capacitance prevents reaching 50 MHz at the cap's minimum setting:
1. Shorten the capacitor-to-loop leads to < 5 mm
2. Remove any unnecessary wire between the gap terminals
3. If still short: trim 5–10 mm from the loop gap (slightly reduces L)

---

## Realistic Performance — Recommended Build (Q = 5000)

This is what you should expect from a well-built antenna with a quality
butterfly capacitor.

| Band | Freq (MHz) | η (%) | dB | BW (kHz) | ERP @ 10 W | Modes |
|------|-----------|-------|------|---------|-----------|-------|
| 20 m | 14.175 | **5.3** | −12.8 | 5.4 | 0.53 W | FT8, CW, WSPR |
| 17 m | 18.100 | **11** | −9.5 | 6.7 | 1.1 W | FT8, CW, digi |
| 15 m | 21.225 | **18** | −7.5 | 8.1 | 1.8 W | FT8, CW, SSB (marginal) |
| 12 m | 24.940 | **27** | −5.7 | 10.3 | 2.7 W | All modes |
| 10 m | 28.500 | **36** | −4.4 | 13.6 | 3.6 W | All modes |
| 6 m | 50.100 | **79** | −1.1 | 71 | 7.9 W | All modes inc. FM |

### Effective Radiated Power Comparison by Build Quality

| Band | Budget (Q=1500) | Recommended (Q=5000) | Theory (Q=∞) |
|------|----------------|---------------------|-------------|
| 20 m | 0.32 W | **0.53 W** | 0.74 W |
| 17 m | 0.67 W | **1.12 W** | 1.57 W |
| 15 m | 1.07 W | **1.77 W** | 2.46 W |
| 12 m | 1.66 W | **2.68 W** | 3.64 W |
| 10 m | 2.33 W | **3.63 W** | 4.77 W |
| 6 m | 6.42 W | **7.85 W** | 8.68 W |

> A quality butterfly delivers 50–65 % more ERP than a budget capacitor
> on every band. That's the equivalent of doubling your transmitter power.

---

## Coupling Loop

| Parameter | Value |
|-----------|-------|
| Diameter | 100 mm (4.0 in) |
| Tube | 3/8" OD soft copper, same as main loop |
| Tube length | 314 mm (12.4 in) |
| Ratio to main | 1 : 4.4 |
| Position | Bottom (6 o'clock), co-planar, centred |
| Connector | BNC panel-mount at loop bottom |

For a single loop spanning a wide frequency range, the coupling factor
changes across bands. Fine-tune the 50 Ω match by tilting the coupling
loop:
- **SWR too high on low bands (20 m):** move coupling loop closer to
  main loop plane (increase coupling)
- **SWR too high on high bands (6 m):** tilt coupling loop away from
  main loop plane (decrease coupling)
- Set the coupling angle for best compromise at your most-used band,
  then accept slightly higher SWR on others.

---

## Power Handling at 10 W

| Band | Vcap (V) | I_loop (A) | Safe? (2 mm gap butterfly) |
|------|---------|-----------|---------------------------|
| 20 m | 1 376 | 14.3 | ✓ (per section: 688 V) |
| 17 m | 1 576 | 12.8 | ✓ (per section: 788 V) |
| 15 m | 1 680 | 11.7 | ✓ (per section: 840 V) |
| 12 m | 1 741 | 10.3 | ✓ (per section: 871 V) |
| 10 m | 1 746 | 9.0 | ✓ (per section: 873 V) |
| 6 m | 1 339 | 3.9 | ✓ (per section: 670 V) |

Breakdown voltage of a 2 mm air gap ≈ 3 000 V per section. Worst-case
per-section voltage is 873 V (10 m). Safety margin: **3.4 : 1.** Comfortable.

At **5 W**, all voltages drop by √2, giving even wider margins.

**Do not exceed 10 W.** At 15 W, worst-case Vcap reaches 2 138 V
(per-section 1 069 V) — still within breakdown limits but approaching
the recommended derating of 50 % of breakdown voltage.

---

## Construction — Maximising Efficiency

Every milliohm matters in a small magnetic loop. The loop's radiation
resistance on 20 m is only **3.6 mΩ**. A single 1 mΩ loss costs 28 %
relative efficiency at that frequency.

### Critical Practices (ranked by impact)

| Priority | Practice | Why |
|----------|---------|-----|
| **1** | **High-Q butterfly capacitor** | Saves 5–15 mΩ over budget cap |
| **2** | **Silver-solder all joints** | Each joint < 0.1 mΩ vs 0.5–2 mΩ clamped |
| **3** | **Shortest possible cap leads** | < 5 mm copper strap, not wire |
| **4** | **Polish tube before assembly** | Removes oxide layer (adds ~0.1 mΩ) |
| **5** | **Circular loop shape** | Maximum area for given circumference |
| **6** | **No metal within 0.5 m** | Prevents eddy-current losses in nearby objects |
| **7** | **Mount ≥ 1 m above ground** | Reduces ground loss |

### Loop Forming

1. **Anneal** the tube — heat to cherry-red, quench in water.
2. Bend around a 17" wheel or bucket form into a **circle**.
3. Leave a **12 mm gap** at the top.
4. Flatten the tube ends and drill for M4 bolts (capacitor terminals).
5. **Polish the entire tube** with 400-grit sandpaper, then wipe with
   isopropyl alcohol immediately before assembly.

### Capacitor Mounting

```
      Flattened tube end        Flattened tube end
      ──────┐    ┌──────
            │    │
            └─┤├─┘  ← Butterfly cap, bolted directly
              ╫╫      to flattened tube ends.
              ╫╫      Leads: < 5 mm. No wire.
```

Bolt the capacitor stator terminals directly to the flattened tube ends.
Use copper or brass bolts. Keep the distance from tube end to capacitor
plate as short as physically possible.

---

## Bill of Materials

| Qty | Item | Est. Cost |
|-----|------|-----------|
| 2 m (7 ft) | 3/8" OD soft copper tube, Type L | $5 |
| 1 | Butterfly capacitor, 2 × 250 pF, 2 mm gap | $25–50 |
| 1 | BNC panel-mount connector | $3 |
| 1 | Reduction-drive knob or vernier dial | $8–15 |
| 1 | PVC pipe section, 0.5 m, for mast | $3 |
| — | Silver solder (56 % Ag) + flux | $12 |
| — | SS hardware, nylon spacers | $5 |
| | **Total** | **$61–93** |

### Copper Tube Allocation

| Piece | Length |
|-------|--------|
| Main loop (0.44 m dia) | 1 382 mm |
| Coupling loop (100 mm dia) | 314 mm |
| Spare / waste | ~300 mm |
| **Total** | **~2 m (7 ft)** |

---

## Comparison With Other ML Designs on Shared Bands

Efficiency shown for recommended-build capacitor quality (Q ≈ 5000).
Other designs shown at theoretical max (Q = ∞) for comparison.

| Band | **This design** (Q=5000) | ML30-6 Eff. (Q=∞) | ML80-6 (Q=∞) | ML30-6 Small A (Q=∞) |
|------|------------------------|-------------------|-------------|---------------------|
| 20 m | 5.3 % | **79 %** (1.6 m loop) | 48 % (1.0 m) | 7.4 % (0.44 m) |
| 17 m | 11 % | **57 %** (0.85 m) | 69 % (1.0 m) | 16 % (0.44 m) |
| 15 m | 18 % | **70 %** (0.85 m) | 79 % (1.0 m) | 25 % (0.44 m) |
| 12 m | 27 % | **81 %** (0.85 m) | 30 % (0.40 m) | 36 % (0.44 m) |
| 10 m | 36 % | **87 %** (0.85 m) | 41 % (0.40 m) | 48 % (0.44 m) |
| 6 m | 79 % | **87 %** (0.44 m) | 83 % (0.40 m) | 87 % (0.44 m) |

> This single-loop design cannot match multi-loop systems on the lower bands.
> Its strength is **simplicity**: one loop, one capacitor, no switching —
> while achieving 79 % on 6 m and usable digital-mode performance on 20 m.

---

## Operating Guidelines

| Band | Realistic BW (kHz) | Retune Interval | Best Modes |
|------|-------------------|-----------------|------------|
| 20 m | 5.4 | Every 4 kHz | FT8, WSPR, CW |
| 17 m | 6.7 | Every 5 kHz | FT8, CW, digital |
| 15 m | 8.1 | Every 6 kHz | FT8, CW, SSB (marginal) |
| 12 m | 10.3 | Every 8 kHz | All modes |
| 10 m | 13.6 | Every 10 kHz | All modes |
| 6 m | 71 | Every 50 kHz | All modes inc. FM |

> **Bandwidth narrows with a better capacitor** (higher Q → narrower BW).
> The realistic BW values above include the capacitor Q = 5000. With a
> budget cap (Q = 1500) the bandwidths are about 30 % wider — but you lose
> efficiency. You cannot have both wide bandwidth and high efficiency.

### Digital Mode Sweet Spot

This antenna is optimised for **FT8 and WSPR** on the lower bands:
- FT8 decodes at −24 dB S/N. At 0.53 W ERP (20 m), intercontinental
  contacts are routine.
- WSPR at −28 dB S/N. Even 0.5 W ERP spans oceans.
- The 5.4 kHz bandwidth on 20 m covers the entire FT8 window
  (14.074–14.078 MHz) without retuning.

### SSB Viability

| Band | ERP @ 10 W | SSB viable? |
|------|-----------|-------------|
| 20 m | 0.53 W | Marginal — short-range only |
| 17 m | 1.1 W | Marginal |
| 15 m | 1.8 W | Possible with good conditions |
| 12 m | 2.7 W | Yes, with patience |
| 10 m | 3.6 W | Yes |
| 6 m | 7.9 W | Yes, comfortable |

---

## Design Limitations

1. **20 m efficiency is fundamentally limited.** The loop is 0.065 λ at
   14 MHz. No capacitor, solder, or construction technique can fix this.
   For efficient 20 m operation, use the ML30-6 multi-loop design (79 %).

2. **Narrowband operation** requires retuning every 4–10 kHz. A vernier
   reduction drive (6:1 or 8:1) makes this manageable. Motor tuning is
   optional but not essential — bandwidths are wide enough for FT8 windows.

3. **Capacitor Q dominates the efficiency budget.** A cheap capacitor
   halves the efficiency on every band. This is the single most important
   component choice in the entire build.

4. **6 m tuning requires careful stray-C management.** At 9.3 pF, every
   millimetre of excess lead length adds stray capacitance. Keep
   capacitor-to-loop connections as short as physically possible.

---

## Summary

| Attribute | Value |
|-----------|-------|
| Loop diameter | 0.44 m (17.3 in) — single loop |
| Bands | 20 m through 6 m (6 bands) |
| Max power | 10 W |
| Key component | Butterfly cap, 2 × 250 pF, Q ≥ 5000 |
| Best band | 6 m at 79 % (recommended build) |
| Weakest band | 20 m at 5.3 % (recommended build) |
| Cost | $61–93 |
| Weight | < 0.5 kg copper |
| Unique focus | Capacitor Q impact analysis |

*Design: single 0.44 m magnetic loop, 20 m – 6 m, 10 W.*
*3/8" copper tube, efficiency-optimised via high-Q butterfly capacitor.*
*Realistic performance values include capacitor loss (Q = 5000).*
