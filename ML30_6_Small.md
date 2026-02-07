# ML30-6 Small: Size-Optimized Magnetic Loop Antenna

## 30 m through 6 m — 10 W Max — 3/8" Copper Tube — Compact / Portable

### Design Philosophy

This design prioritises **minimum physical size** for portable, field, and
balcony operation. Efficiency is traded for compactness. Two configurations
are presented:

| Config | Footprint | Bands | Avg Efficiency | Weight (copper) |
|--------|-----------|-------|----------------|-----------------|
| **A — Single Loop** | 0.44 m (17") dia | 30 m – 6 m | 32 % | 0.32 kg |
| **B — Concentric Dual** | 0.60 m (24") dia | 30 m – 6 m | 45 % | 0.70 kg |

Both use 3/8" (9.525 mm) OD soft copper tube throughout.

---

## Configuration A — Single Loop, 0.44 m

The **smallest possible single magnetic loop** that covers 30 m through 6 m.
At 6 m (54 MHz) the circumference reaches 0.25 λ — the upper limit for
magnetic-loop behaviour — so this is the physical maximum diameter.

### System Diagram

```
            ┌─ Variable Cap ─┐    ← 10–250 pF air variable
        ────┘     ╫╫╫╫╫     └────     or toggle to 6 m trimmer
       /          ╫╫╫╫╫          \
      │                           │   Main loop
      │    0.44 m (17.3 in) dia   │   3/8" Cu tube
      │       L = 1.08 μH        │
       \                         /
        ──┐    ┌─────────┐   ┌──
          │    │ Coupling │   │   100 mm (4") coupling loop
          │    │  loop    │   │   1/4.4 ratio
          │    └───┤├─────┘   │
          └───────────────────┘
                  ││
              50 Ω coax
```

Total height × width: **0.44 m × 0.44 m (17.3" × 17.3")**

### Physical Parameters

| Parameter | Value |
|-----------|-------|
| Main loop diameter | 0.44 m (17.3 in) |
| Circumference | 1.38 m (4.5 ft) |
| Tube | 3/8" OD soft copper, Type L |
| Inductance | 1.08 μH |
| Area | 0.152 m² |
| Coupling loop diameter | 100 mm (4.0 in) — 1 : 4.4 ratio |
| Main loop tube length | 1.38 m |
| Coupling loop tube length | 0.31 m |
| **Copper weight** | **0.32 kg (0.7 lb)** |

### Performance Table — Config A (Single 0.44 m)

| Band | Freq (MHz) | C (pF) | Circ/λ | Rr (mΩ) | Rloss (mΩ) | η (%) | dB | BW (kHz) | Vcap (V) | ERP (W) |
|------|-----------|--------|--------|---------|-----------|-------|------|---------|---------|---------|
| 30 m | 10.125 | 229 | 0.047 | 0.9 | 38.3 | **2.4** | −16.2 | 5.8 | 1 097 | 0.24 |
| 20 m | 14.175 | 117 | 0.065 | 3.6 | 45.4 | **7.4** | −11.3 | 7.2 | 1 376 | 0.74 |
| 17 m | 18.100 | 72 | 0.083 | 9.6 | 51.3 | **16** | −8.0 | 9.0 | 1 576 | 1.6 |
| 15 m | 21.225 | 52 | 0.098 | 18.1 | 55.5 | **25** | −6.1 | 10.8 | 1 680 | 2.5 |
| 12 m | 24.940 | 38 | 0.115 | 34.5 | 60.2 | **36** | −4.4 | 13.9 | 1 741 | 3.6 |
| 10 m | 28.500 | 29 | 0.131 | 58.7 | 64.3 | **48** | −3.2 | 18.1 | 1 746 | 4.8 |
| 6 m | 50.100 | 9.3 | 0.231 | 561 | 85.3 | **87** | −0.6 | 95.1 | 1 339 | 8.7 |

> **Honest assessment:** On 30 m and 20 m the loop is only 0.05–0.07 λ in
> circumference. At 10 W input you get 0.24–0.74 W ERP. This is marginal
> for SSB but **workable for FT8, WSPR, and CW** — modes that decode at
> very low S/N. From 12 m upward, efficiency exceeds 36 % and the antenna
> becomes competitive.

### Capacitor System — Config A

The single loop requires **9.3 pF (6 m) to 229 pF (30 m)** — a 25:1 ratio.
A standard air-variable capacitor cannot reliably tune below ~12 pF including
stray capacitance, making a single-knob all-band tuning difficult.

**Recommended: Two-range system with toggle switch.**

```
           ┌──── Toggle Switch ────┐
           │                       │
    ┌──────┤  Position 1:          │  Position 2:
    │      │  Air variable         │  Trimmer cap
    │      │  10–250 pF            │  5–15 pF
    │      │  (30 m – 10 m)        │  (6 m only)
    Loop   └───────────────────────┘
    gap
```

| Range | Component | Bands Covered | Plate Gap |
|-------|-----------|---------------|-----------|
| HF | Air variable, 10–250 pF | 30 m – 10 m | ≥ 2 mm |
| VHF | Ceramic trimmer, 5–15 pF | 6 m | any (V < 1.4 kV) |

**At 5 W,** all voltages drop below 1 235 V. A compact air variable with
1.5 mm plate gap works for the HF range. The total capacitor system fits
in a 40 × 40 × 30 mm enclosure.

---

## Configuration B — Concentric Dual Loop

Two loops mounted concentrically on the same mast, same plane, nesting
inside each other. The outer loop handles 30 m – 10 m with 2–7× higher
efficiency than the single loop. The inner loop covers 6 m.

### System Diagram

```
          ┌── Cap (var or trimmer) ──┐
      ────┘                          └────
     /    ┌── Trimmer (6m only) ──┐       \
    │ ────┘                       └──── │  │
    │ │                               │ │  │ ← Outer: 0.60 m
    │ │        0.44 m inner           │ │  │   Inner: 0.44 m
    │ │        (6 m only)             │ │  │
    │ ────┐                       ┌──── │  │
     \    └───────────────────────┘       /
      ────┐       ┌───────┐       ┌────
          │       │Coupling│      │
          │       │ Loop   │      │    ← 120 mm, shared
          │       └──┤├────┘      │
          └───────────────────────┘
                     ││
                 50 Ω coax

    DPDT switch at top selects which loop + cap is active.
    Inactive loop left open-circuit (negligible detuning).
```

Total height × width: **0.60 m × 0.60 m (23.6" × 23.6")**

### Physical Parameters

| Parameter | Outer Loop | Inner Loop |
|-----------|-----------|-----------|
| Diameter | 0.60 m (23.6 in) | 0.44 m (17.3 in) |
| Circumference | 1.89 m (6.2 ft) | 1.38 m (4.5 ft) |
| Inductance | 1.59 μH | 1.08 μH |
| Area | 0.283 m² | 0.152 m² |
| Tube length | 1.89 m | 1.38 m |
| Coupling loop | 120 mm (4.7 in) shared — 1 : 5 of outer |
| **Total copper weight** | **0.70 kg (1.5 lb)** |

### Performance Table — Config B Outer Loop (0.60 m) — 30 m to 10 m

| Band | Freq (MHz) | C (pF) | Circ/λ | Rr (mΩ) | Rloss (mΩ) | η (%) | dB | BW (kHz) | Vcap (V) | ERP (W) |
|------|-----------|--------|--------|---------|-----------|-------|------|---------|---------|---------|
| 30 m | 10.125 | 155 | 0.064 | 3.2 | 52.3 | **5.8** | −12.4 | 5.6 | 1 359 | 0.58 |
| 20 m | 14.175 | 79 | 0.089 | 12.4 | 61.9 | **17** | −7.8 | 7.9 | 1 645 | 1.7 |
| 17 m | 18.100 | 48 | 0.114 | 33.1 | 69.9 | **32** | −4.9 | 10.3 | 1 785 | 3.2 |
| 15 m | 21.225 | 35 | 0.133 | 62.5 | 75.7 | **45** | −3.4 | 13.8 | 1 807 | 4.5 |
| 12 m | 24.940 | 26 | 0.157 | 119 | 82.1 | **59** | −2.3 | 20.1 | 1 758 | 5.9 |
| 10 m | 28.500 | 20 | 0.179 | 203 | 87.7 | **70** | −1.6 | 29.0 | 1 674 | 7.0 |

### Performance — Config B Inner Loop (0.44 m) — 6 m

| Band | Freq (MHz) | C (pF) | Circ/λ | η (%) | dB | BW (kHz) | Vcap (V) | ERP (W) |
|------|-----------|--------|--------|-------|------|---------|---------|---------|
| 6 m | 50.100 | 9.3 | 0.231 | **87** | −0.6 | 95.1 | 1 339 | 8.7 |

### Capacitor System — Config B

| Loop | Component | Range | Plate Gap |
|------|-----------|-------|-----------|
| Outer (30 m–10 m) | Air variable, 15–200 pF | 20–155 pF needed | ≥ 2 mm |
| Inner (6 m) | Ceramic trimmer, 5–15 pF | ~9 pF needed | any |

A DPDT toggle or rotary switch at the capacitor gap selects which loop and
capacitor are connected. The inactive loop is left open-circuit.

---

## Side-by-Side Comparison

### Efficiency (η) — Config A vs Config B

| Band | Config A (0.44 m) | Config B (0.60 + 0.44 m) | B improves by |
|------|-------------------|--------------------------|---------------|
| 30 m | 2.4 % (−16.2 dB) | 5.8 % (−12.4 dB) | **+3.8 dB** |
| 20 m | 7.4 % (−11.3 dB) | 17 % (−7.8 dB) | **+3.5 dB** |
| 17 m | 16 % (−8.0 dB) | 32 % (−4.9 dB) | **+3.1 dB** |
| 15 m | 25 % (−6.1 dB) | 45 % (−3.4 dB) | **+2.7 dB** |
| 12 m | 36 % (−4.4 dB) | 59 % (−2.3 dB) | **+2.1 dB** |
| 10 m | 48 % (−3.2 dB) | 70 % (−1.6 dB) | **+1.6 dB** |
| 6 m | 87 % (−0.6 dB) | 87 % (−0.6 dB) | 0 dB |

### Physical Comparison

| Attribute | Config A | Config B |
|-----------|----------|----------|
| Max diameter | 0.44 m (17") | 0.60 m (24") |
| Copper tube needed | 1.7 m (5.6 ft) | 3.6 m (12 ft) |
| Copper weight | 0.32 kg (0.7 lb) | 0.70 kg (1.5 lb) |
| Packed kit weight (est.) | 0.6 kg (1.3 lb) | 1.2 kg (2.6 lb) |
| Number of loops | 1 | 2 (concentric) |
| Capacitors | 1 var + 1 trimmer | 1 var + 1 trimmer + DPDT |
| Fits in backpack? | Yes — daypack | Yes — medium pack |
| Setup time | 2 min | 4 min |

### Comparison with ML30-6 Efficiency-Optimized Design

| Band | **ML30_6 Small A** | **ML30_6 Small B** | **ML30_6 (Eff. Opt.)** |
|------|-------------------|-------------------|----------------------|
| 30 m | 2.4 % | 5.8 % | **54 %** |
| 20 m | 7.4 % | 17 % | **79 %** |
| 17 m | 16 % | 32 % | **57 %** |
| 15 m | 25 % | 45 % | **70 %** |
| 12 m | 36 % | 59 % | **81 %** |
| 10 m | 48 % | 70 % | **87 %** |
| 6 m | 87 % | 87 % | **87 %** |
| **Max diameter** | **0.44 m** | **0.60 m** | **1.60 m** |

The efficiency-optimized design (3 loops, 1.6 m max) is 5–13 dB better on
the lower bands — but it is 3–4× larger and not backpack-portable.

---

## Construction Notes

### Forming the Loops

1. **Anneal** the tube (cherry-red, quench) before bending.
2. **Config A:** Bend the 0.44 m loop around a 17" wheel or bucket form.
3. **Config B:** Bend the 0.60 m outer loop around a 24" barrel or drum.
   Nest the 0.44 m inner loop concentrically.
4. Leave a **12 mm gap** at the top for capacitor terminals.
5. Flatten and drill tube ends for bolted connection.

### Efficiency-Critical Details

Even in a small-size design, these practices preserve what efficiency
the small loop can deliver:

- **Silver-solder all joints.** On 30 m, Rr is only 0.9–3.2 mΩ. A single
  bad solder joint (0.5 mΩ) measurably reduces the already-low efficiency.
- **Short capacitor leads** (< 8 mm). Use flattened copper strap.
- **Polish tube before assembly.** Remove all oxide with 400-grit sandpaper.
- **Keep the loop circular.** Circles have lower loss than octagons.

### Coupling Loop

| Config | Coupling Diameter | Tube Length | Ratio |
|--------|------------------|-------------|-------|
| A | 100 mm (4.0 in) | 314 mm | 1 : 4.4 |
| B | 120 mm (4.7 in), shared | 377 mm | 1 : 5 (outer) |

The coupling loop sits at 6 o'clock, co-planar, inside the main loop
(inside the inner loop in Config B). Tilt to adjust 50 Ω match.

### Concentric Loop Interaction (Config B)

When the outer loop is active, the inner loop is open-circuit and carries
negligible current — its effect on tuning is minimal. No shorting,
grounding, or disconnection of the inactive loop is required beyond
opening the DPDT switch.

In practice, the inactive loop may shift the active loop's resonance by
1–3 pF equivalent. Compensate by slight retuning of the variable capacitor.

---

## Bill of Materials

### Config A — Single Loop

| Qty | Item | Est. Cost |
|-----|------|-----------|
| 2 m (7 ft) | 3/8" OD soft copper tube | $5 |
| 1 | Air variable capacitor, 10–250 pF, 2 mm gap | $15–25 |
| 1 | Ceramic trimmer, 5–15 pF (for 6 m) | $3 |
| 1 | SPDT toggle switch (cap selector) | $3 |
| 1 | BNC panel-mount connector | $3 |
| 1 | PVC pipe section, 0.5 m, for mast | $3 |
| — | Silver solder, hardware, wire | $10 |
| | **Total** | **$40–55** |

### Config B — Concentric Dual

| Qty | Item | Est. Cost |
|-----|------|-----------|
| 4 m (14 ft) | 3/8" OD soft copper tube | $10 |
| 1 | Air variable capacitor, 15–200 pF, 2 mm gap | $15–25 |
| 1 | Ceramic trimmer, 5–15 pF | $3 |
| 1 | DPDT toggle switch | $4 |
| 1 | BNC panel-mount connector | $3 |
| 1 | PVC pipe section, 0.7 m, for mast | $3 |
| — | Silver solder, hardware, wire | $10 |
| | **Total** | **$50–60** |

---

## Portable Field Kit

### Config A Packing List — 0.6 kg total

```
┌──────────────────────────────┐
│  Daypack / padded sleeve     │
│  ┌────────────────────────┐  │
│  │ 0.44 m Cu loop (rolled │  │   17" × 17" × 2"
│  │ coupling loop inside)  │  │
│  └────────────────────────┘  │
│  Cap assembly in small box   │   40 × 40 × 30 mm
│  BNC-BNC coax patch, 0.3 m  │
│  PVC mast section            │
│  Camera tripod (optional)    │
└──────────────────────────────┘
```

### Config B Packing List — 1.2 kg total

```
┌────────────────────────────────┐
│  Medium padded bag             │
│  ┌──────────────────────────┐  │
│  │ 0.60 m outer loop       │  │  24" × 24" × 2"
│  │  └ 0.44 m inner (nested)│  │  (loops nest concentrically)
│  │    └ coupling (nested)  │  │
│  └──────────────────────────┘  │
│  Cap assembly + switch box     │
│  BNC coax, 0.3 m              │
│  PVC mast section              │
│  Camera tripod (optional)      │
└────────────────────────────────┘
```

### Field Setup Procedure

1. Attach loop(s) to mast or tripod (two zip-ties or PVC clamps).
2. Bolt capacitor assembly across the gap at the top.
3. Plug coax into coupling loop BNC at bottom.
4. Connect rig → tune for minimum SWR → operate.
5. **Retune when changing frequency** — the antenna is narrowband.

---

## Operating Tips for Small Loops

1. **Use digital modes.** FT8 decodes at −24 dB S/N. Even 0.24 W ERP on
   30 m (Config A) can make intercontinental contacts with FT8/WSPR.

2. **Orient the loop broadside** to the target direction. The magnetic loop
   has a figure-8 pattern with nulls off the loop edges.

3. **The loop is quiet.** Its biggest advantage over wire antennas is **very
   low noise pickup**. In noisy urban environments, the S/N improvement can
   more than offset the efficiency loss.

4. **Height helps.** Even 1 m above ground improves performance. A camera
   tripod or fence-post mount is ideal for field use.

5. **Don't exceed 10 W.** At 10 W, peak capacitor voltage is 1 807 V. At
   15 W it reaches 2 214 V — close to the breakdown limit of a 2 mm air gap.

6. **Retune intervals** (SWR < 2:1 window ≈ 75 % of −3 dB BW):

   | Band | Config A | Config B |
   |------|----------|----------|
   | 30 m | 4 kHz | 4 kHz |
   | 20 m | 5 kHz | 6 kHz |
   | 17 m | 7 kHz | 8 kHz |
   | 15 m | 8 kHz | 10 kHz |
   | 12 m | 10 kHz | 15 kHz |
   | 10 m | 14 kHz | 22 kHz |
   | 6 m | 71 kHz | 71 kHz |

---

## Calculation Basis

```
L  = μ₀ R [ ln(8R/a) − 2 ]         Inductance
C  = 1 / (4π²f²L)                   Resonant capacitance
Rr = 31171 (A/λ²)²                  Radiation resistance
Rs = √(πfμ₀ / σ_Cu)                 Surface resistance
Rl = Rs × circ / (π × tube_OD)      Loss resistance
η  = Rr / (Rr + Rl)                 Efficiency
Q  = 2πfL / (Rr + Rl)               Quality factor
BW = f / Q                           −3 dB bandwidth
Vc = √(P × 2πfL × Q)               Peak capacitor voltage
```

a = 4.76 mm, σ_Cu = 5.8 × 10⁷ S/m. Capacitor and joint losses not included.

---

*Design: 3/8" copper tube magnetic loop, size-optimized for portable use.*
*30 m – 6 m, 10 W max. Config A: single 0.44 m loop. Config B: concentric*
*0.60 m + 0.44 m dual loop. Silver-soldered joints assumed throughout.*
