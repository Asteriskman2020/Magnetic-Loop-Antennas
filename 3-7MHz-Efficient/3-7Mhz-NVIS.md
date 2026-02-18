# 3-7MHz-NVIS — Magnetic Loop Optimised for Near-Vertical Radiation

> **NVIS variant | Same 3.0 m loop | Vertical mount at 5 m | Peak radiation at zenith | 0–500 km range**

---

## 1. Design Objective

Reconfigure the 3.0 m efficiency-optimised magnetic loop for **NVIS
(Near Vertical Incidence Skywave)** propagation on 80 m and 40 m.
The goal is to push the take-off angle as close to vertical (90°
elevation) as possible, enabling reliable short-range HF coverage
out to ~500 km — ideal for regional emergency nets, daytime 80 m,
and tactical communications.

### What Changes from the Original Design

| Parameter            | Original (DX)                    | NVIS Variant                     |
|----------------------|----------------------------------|----------------------------------|
| Loop orientation     | Vertical (standard)              | **Vertical (same)**              |
| Centre height        | Any (often 2–3 m)               | **5.0 m above ground**           |
| Bottom clearance     | Not specified                    | **3.5 m minimum**                |
| Ground system        | None required                    | **Ground screen recommended**    |
| Peak radiation       | Broadside (horizon)              | **Zenith (straight up)**         |
| Take-off angle       | Low to medium (DX)               | **70°–90° elevation (NVIS)**     |
| Primary use          | DX (> 500 km)                    | **Regional (0–500 km)**          |
| Loop / cap / tube    | 3.0 m, vacuum cap, 7/8" Cu      | **Identical — no changes**       |
| Efficiency           | 30.5% (80m), 83.3% (40m)        | **Identical**                    |

> **The antenna hardware is unchanged.** Only the mounting height and
> ground system are different. The same loop can be switched between
> DX mode (low mount) and NVIS mode (5 m mount with ground screen)
> by changing the support structure.

---

## 2. Why a Vertical Loop Gives High-Angle Radiation

A vertically mounted small magnetic loop has its magnetic moment
**horizontal**. The free-space radiation pattern is a torus (donut)
around this horizontal axis. Critically, the **zenith direction is
perpendicular to the magnetic moment**, so the loop radiates at
**full strength straight up** — there is no zenith null.

When the loop is placed over a ground plane at height *h*:

- The horizontally polarised signal reflects off the ground.
- At low heights (h < lambda/4), the direct and reflected waves
  combine constructively at high elevation angles and destructively
  at the horizon.
- The result: **radiation peaked at zenith, with a null at the
  horizon** — exactly the pattern needed for NVIS.

### Ground-Reflection Array Factor (Broadside Direction)

```
E(alpha) = 2 |sin(k h sin(alpha))|

where:
  alpha = elevation angle (0° = horizon, 90° = zenith)
  k     = 2 pi / lambda
  h     = loop centre height above ground
```

For h < lambda/4, this function peaks at alpha = 90° (zenith) and
equals zero at alpha = 0° (horizon). The antenna radiates **upward
only** — the ground suppresses low-angle radiation.

---

## 3. NVIS Elevation Patterns

### Mounting Height: 5.0 m Centre

Height-to-wavelength ratios:

| Band   | Frequency | lambda   | h/lambda | kh (rad) |
|--------|-----------|----------|----------|----------|
| 80 m   | 3.500 MHz | 85.66 m  | 0.058    | 0.367    |
| 40 m   | 7.000 MHz | 42.83 m  | 0.117    | 0.734    |

### Normalised Elevation Pattern (Broadside Direction, PEC Ground)

| Elevation | 80 m (3.5 MHz)       | 40 m (7.0 MHz)       |
|-----------|----------------------|----------------------|
| 90° (zenith) | **1.000** (0 dB)  | **1.000** (0 dB)     |
| 80°       | 0.985 (−0.1 dB)      | 0.989 (−0.1 dB)      |
| 70°       | 0.941 (−0.5 dB)      | 0.951 (−0.4 dB)      |
| 60°       | 0.870 (−1.2 dB)      | 0.888 (−1.0 dB)      |
| 50°       | 0.774 (−2.2 dB)      | 0.794 (−2.0 dB)      |
| 45°       | 0.716 (−2.9 dB)      | 0.742 (−2.6 dB)      |
| 30°       | 0.509 (−5.9 dB)      | 0.537 (−5.4 dB)      |
| 20°       | 0.349 (−9.1 dB)      | 0.371 (−8.6 dB)      |
| 10°       | 0.177 (−15.0 dB)     | 0.190 (−14.4 dB)     |
| 0° (horizon) | 0.000 (null)      | 0.000 (null)         |

> **Key result:** On both bands, the signal at 70° elevation is within
> 0.5 dB of the zenith peak. The −3 dB beamwidth in elevation covers
> roughly **45°–90°** — the entire NVIS cone. Low-angle radiation is
> suppressed by more than 15 dB at 10° elevation.

### NVIS Coverage vs Elevation Angle

Assuming F2-layer reflection at 300 km altitude:

| Elevation | Ground Radius | Round-Trip Distance | Application          |
|-----------|---------------|---------------------|----------------------|
| 90°       | 0 km          | 600 km              | Directly overhead    |
| 80°       | 53 km         | 606 km              | Local (city-wide)    |
| 70°       | 109 km        | 624 km              | Regional             |
| 60°       | 173 km        | 660 km              | Inter-city           |
| 45°       | 300 km        | 735 km              | Extended regional    |
| 30°       | 520 km        | 866 km              | Limit of NVIS zone  |

---

## 4. System Diagram — NVIS Mounting

```
                       5.0 m centre height
                       above ground

                          Vacuum Cap
                          ┌──╥──┐
                     ─────┘  ║  └─────
                    /        ║        \
                   │   7/8" Cu tube    │
                   │                   │    Main loop
     6.5 m ──────>│    D = 3.0 m      │    (vertical,
     (top)        │                   │     facing
                   │                   │     broadside)
                    \                 /
                     ──┐           ┌──
     3.5 m ──────>    │ Coupling  │
     (bottom)         │  Loop     │
                      └──┤├───────┘
                           │
                        Coax
    ─────────────────────────────────────── Ground level
    ═══════════════════════════════════════
         Optional ground screen (4 m × 4 m)
         chicken wire or radial wires
```

The loop is mounted **vertically** (perpendicular to ground) with
its centre at **5.0 m height**. The bottom of the loop clears the
ground by 3.5 m, well above head height for safety.

The loop plane should be oriented so the broadside direction (the
direction of maximum NVIS radiation) faces the desired coverage area.
For omnidirectional NVIS coverage, orient broadside North–South.

---

## 5. Ground Screen

A ground screen dramatically improves the NVIS pattern by:

1. Creating a more consistent and predictable ground reflection
2. Increasing the effective ground conductivity directly under the loop
3. Reducing ground absorption losses

### Recommended Ground Screen

| Parameter          | Value                              |
|--------------------|------------------------------------|
| Type               | Chicken wire (25 mm mesh)          |
| Size               | 4 m × 4 m (minimum)               |
| Alternative        | 8 radial wires, 10 m each         |
| Placement          | On ground surface, centred below loop |
| Bonding            | Connect to station ground          |

For sites with poor soil (dry, sandy, rocky), the ground screen is
**strongly recommended**. On sites with good soil (moist, clay),
the bare ground is often adequate.

---

## 6. Comparison: NVIS vs DX Mounting

### Elevation Pattern Comparison (40 m, Broadside Direction)

```
90° (zenith)  ████████████████████████████████████  NVIS: 1.000
              ░░░░░░░░░░░                           DX:   0.000 (null)

80°           ███████████████████████████████████   NVIS: 0.989
              ░░░░░░░░░░░░░░░░░░                    DX:   0.174

70°           ██████████████████████████████████    NVIS: 0.951
              ░░░░░░░░░░░░░░░░░░░░░░░░░             DX:   0.342

45°           ██████████████████████████           NVIS: 0.742
              ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░     DX:   0.707

20°           █████████████                        NVIS: 0.371
              ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  DX:   0.940

10°           ██████                               NVIS: 0.190
              ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░ DX:   0.985

0° (horizon)                                        NVIS: 0.000 (null)
              ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░ DX:   1.000

████  NVIS (vertical loop at 5 m, over ground)
░░░░  DX (free space, broadside pattern)
```

The NVIS mounting completely **inverts** the elevation pattern:
the original broadside design peaks at the horizon for DX, while
the NVIS variant peaks at the zenith for regional coverage.

---

## 7. Performance Summary

### NVIS Take-Off Angles

| Band   | Freq      | Peak Elevation | −3 dB Cone    | −6 dB Cone    |
|--------|-----------|----------------|---------------|---------------|
| 80 m   | 3.500 MHz | **90° (zenith)** | 45°–90°     | 28°–90°       |
| 80 m   | 3.800 MHz | **90° (zenith)** | 47°–90°     | 30°–90°       |
| 40 m   | 7.000 MHz | **90° (zenith)** | 44°–90°     | 27°–90°       |
| 40 m   | 7.300 MHz | **90° (zenith)** | 46°–90°     | 29°–90°       |

### Efficiency (Unchanged)

| Band   | Freq      | Efficiency | Eff (dB) |
|--------|-----------|------------|----------|
| 80 m   | 3.500 MHz | 30.5 %     | −5.16    |
| 40 m   | 7.000 MHz | 83.3 %     | −0.79    |

### Typical NVIS Link Budget (40 m, 100 W, 300 km)

| Parameter               | Value         |
|-------------------------|---------------|
| Transmit power          | 100 W (+50 dBm) |
| Antenna efficiency      | 83.3% (−0.8 dB) |
| Antenna gain at zenith  | +4.8 dBi (est., incl. ground gain) |
| EIRP                    | +54.0 dBm     |
| Path loss (600 km via F2) | −125 dB (typ.) |
| Ionospheric absorption  | −10 dB (typ.) |
| Receive antenna gain    | +4.8 dBi      |
| Received signal         | −76.2 dBm     |
| Noise floor (40m, 4kHz) | −100 dBm (typ.) |
| **SNR**                 | **+23.8 dB**  |

> SNR of +24 dB is comfortable for SSB voice and digital modes.
> Even at 10 W, the link closes with +14 dB SNR.

---

## 8. Increasing Height for Better 80 m NVIS

At 5 m, the 80 m performance is good but can be improved by raising
the loop. The following table shows the effect of height on zenith
signal strength (normalised to the maximum possible with PEC ground):

| Height (m) | h/lambda (80m) | Zenith AF (80m) | h/lambda (40m) | Zenith AF (40m) |
|------------|----------------|-----------------|----------------|-----------------|
| 3          | 0.035          | 0.436           | 0.070          | 0.852           |
| 5          | 0.058          | 0.718           | 0.117          | 1.338           |
| 8          | 0.093          | 1.110           | 0.187          | 1.814           |
| 10         | 0.117          | 1.338           | 0.234          | 1.961           |
| 15         | 0.175          | 1.814           | 0.350          | 1.377 *         |
| 21.4 (λ/4) | 0.250         | **2.000 (max)** | 0.500          | 0.000 (null!) * |

```
* At h = lambda/4 on 40 m (10.7 m), the zenith AF is maximised.
  Above this height, the 40 m zenith signal begins to DECREASE
  as the ground reflection shifts from constructive to destructive.
```

### Optimal Heights

| Band   | Optimal h for zenith | h in metres | Practical? |
|--------|---------------------|-------------|------------|
| 80 m   | lambda/4 = 21.4 m   | 21.4 m      | Difficult  |
| 80 m   | 0.1 lambda          | 8.6 m       | Feasible   |
| 40 m   | lambda/4 = 10.7 m   | 10.7 m      | Feasible   |
| 40 m   | 0.1 lambda          | 4.3 m       | Easy       |
| **Both** | **5 m (compromise)** | **5.0 m** | **Recommended** |

---

## 9. Construction Notes for NVIS Mounting

### Support Structure

1. Use a **fibreglass or wooden mast**, minimum 7 m tall.
2. The 3.0 m loop hangs vertically from a cross-arm at the top,
   with its centre at 5.0 m above ground.
3. Bottom of loop clears ground by 3.5 m (safe from contact).
4. Guy wires (non-metallic) provide stability in wind.

### Loop Orientation for NVIS

For pure NVIS (overhead coverage), loop orientation does not matter
much — the zenith signal is the same regardless of which direction
the loop faces. However, the azimuth pattern is still a figure-8 at
lower elevation angles. For best all-around regional coverage:

- **Orient the loop plane North–South** (broadside East–West).
  This puts the figure-8 lobes East and West, providing coverage
  in those directions at moderate elevation angles.

### Switching Between NVIS and DX

The same loop can serve both purposes:

- **NVIS mode:** Mount at 5+ m with ground screen → high-angle peak
- **DX mode:** Mount at 2–3 m without ground screen → broadside peak

A tilting mast or pulley system allows quick reconfiguration.

---

## 10. Key Formulae (NVIS-Specific)

```
Array factor (broadside, over PEC ground):
  AF(alpha) = 2 |sin(k h sin(alpha))|

Zenith array factor:
  AF(90°) = 2 |sin(k h)|

Optimal height for max zenith signal:
  h_opt = lambda / 4

NVIS ground radius (single hop):
  R = H_iono × tan(90° - alpha)

where H_iono = ionospheric layer height (~300 km)
```

---

## 11. Design Validation Checklist (NVIS)

- [x] Loop hardware unchanged from efficiency-optimised design
- [x] Centre height 5.0 m gives zenith peak on both bands
- [x] Bottom clearance 3.5 m exceeds safety minimum (2.5 m)
- [x] −3 dB NVIS cone covers 45°–90° elevation
- [x] Low-angle radiation suppressed > 15 dB below 10° elevation
- [x] Ground screen specified for improved performance
- [x] Efficiency identical to original design (30.5% / 83.3%)

---

*NVIS variant of the 3-7MHz maximum-efficiency magnetic loop.
Same antenna hardware, optimised mounting for near-vertical radiation.
Based on ground-reflection array theory applied to small magnetic loops.*
