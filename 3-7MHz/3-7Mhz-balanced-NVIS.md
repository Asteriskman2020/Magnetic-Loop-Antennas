# 3-7MHz-Balanced-NVIS -- Magnetic Loop Optimised for Near-Vertical Radiation

> **NVIS variant | Same 2.0 m balanced loop | Vertical mount at 5 m | Peak radiation at zenith | 0-500 km range**

---

## 1. Design Objective

Reconfigure the 2.0 m balanced magnetic loop for **NVIS
(Near Vertical Incidence Skywave)** propagation on 80 m and 40 m.
The goal is to push the take-off angle as close to vertical (90 deg
elevation) as possible, enabling reliable short-range HF coverage
out to ~500 km -- ideal for regional emergency nets, daytime 80 m,
and tactical communications.

The 2.0 m balanced design was chosen as the optimal trade-off between
efficiency and physical practicality. This NVIS variant exploits the
same hardware, simply changing the mounting height and adding a ground
screen to redirect radiation upward for regional coverage.

### What Changes from the Original Design

| Parameter            | Original (DX)                    | NVIS Variant                     |
|----------------------|----------------------------------|----------------------------------|
| Loop orientation     | Vertical (standard)              | **Vertical (same)**              |
| Centre height        | 2-3 m (typical)                  | **5.0 m above ground**           |
| Bottom clearance     | ~1-2 m                           | **4.0 m minimum**                |
| Ground system        | None required                    | **Ground screen recommended**    |
| Peak radiation       | Broadside (horizon)              | **Zenith (straight up)**         |
| Take-off angle       | Low to medium (DX)               | **70 deg-90 deg elevation (NVIS)** |
| Primary use          | DX (> 500 km)                    | **Regional (0-500 km)**          |
| Loop / cap / tube    | 2.0 m, vacuum cap, 5/8" Cu      | **Identical -- no changes**      |
| Efficiency           | 8.5% (80m), 51.2% (40m)         | **Identical**                    |

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
**full strength straight up** -- there is no zenith null.

When the loop is placed over a ground plane at height *h*:

- The horizontally polarised signal reflects off the ground.
- At low heights (h < lambda/4), the direct and reflected waves
  combine constructively at high elevation angles and destructively
  at the horizon.
- The result: **radiation peaked at zenith, with a null at the
  horizon** -- exactly the pattern needed for NVIS.

### Ground-Reflection Array Factor (Broadside Direction)

```
E(alpha) = 2 |sin(k h sin(alpha))|

where:
  alpha = elevation angle (0 deg = horizon, 90 deg = zenith)
  k     = 2 pi / lambda
  h     = loop centre height above ground
```

For h < lambda/4, this function peaks at alpha = 90 deg (zenith) and
equals zero at alpha = 0 deg (horizon). The antenna radiates **upward
only** -- the ground suppresses low-angle radiation.

### Normalised Pattern Formula

When the zenith is the peak (h < lambda/4), the normalised elevation
pattern in the broadside direction is:

```
E_norm(alpha) = sin(k h sin(alpha)) / sin(k h)
```

This normalises the zenith value to unity for convenient comparison
across elevation angles.

---

## 3. NVIS Elevation Patterns

### Mounting Height: 5.0 m Centre

The 2.0 m diameter loop mounted vertically with its centre at 5.0 m
places the top of the loop at 6.0 m and the bottom at 4.0 m above
ground. This provides generous clearance (4.0 m) well above head
height, while positioning the loop centre at a height that produces
strong NVIS radiation on both 80 m and 40 m.

Height-to-wavelength ratios:

| Band   | Frequency | lambda   | h/lambda | kh (rad) |
|--------|-----------|----------|----------|----------|
| 80 m   | 3.500 MHz | 85.71 m  | 0.058    | 0.367    |
| 40 m   | 7.000 MHz | 42.86 m  | 0.117    | 0.734    |

### Zenith Array Factor AF(90 deg) = 2|sin(kh)|

| Band   | kh (rad) | sin(kh)  | AF(90 deg) |
|--------|----------|----------|------------|
| 80 m   | 0.367    | 0.359    | 0.718      |
| 40 m   | 0.734    | 0.669    | 1.338      |

On 40 m the array factor exceeds unity, meaning the ground reflection
provides a net gain over the free-space pattern at zenith. On 80 m the
array factor is less than unity due to the very low height-to-wavelength
ratio, but the zenith is still the peak direction.

### Normalised Elevation Pattern (Broadside Direction, PEC Ground)

```
E_norm(alpha) = sin(kh sin(alpha)) / sin(kh)
```

| Elevation     | 80 m (3.5 MHz)       | 40 m (7.0 MHz)       |
|---------------|----------------------|----------------------|
| 90 deg (zenith) | **1.000** (0 dB)  | **1.000** (0 dB)     |
| 80 deg        | 0.985 (-0.1 dB)      | 0.989 (-0.1 dB)      |
| 70 deg        | 0.942 (-0.5 dB)      | 0.952 (-0.4 dB)      |
| 60 deg        | 0.872 (-1.2 dB)      | 0.887 (-1.0 dB)      |
| 50 deg        | 0.774 (-2.2 dB)      | 0.796 (-2.0 dB)      |
| 45 deg        | 0.716 (-2.9 dB)      | 0.742 (-2.6 dB)      |
| 30 deg        | 0.509 (-5.9 dB)      | 0.536 (-5.4 dB)      |
| 20 deg        | 0.349 (-9.1 dB)      | 0.371 (-8.6 dB)      |
| 10 deg        | 0.177 (-15.0 dB)     | 0.190 (-14.4 dB)     |
| 0 deg (horizon) | 0.000 (null)      | 0.000 (null)         |

> **Key result:** On both bands, the signal at 70 deg elevation is within
> 0.5 dB of the zenith peak. The -3 dB beamwidth in elevation covers
> roughly **45 deg-90 deg** -- the entire NVIS cone. Low-angle radiation is
> suppressed by more than 15 dB at 10 deg elevation, effectively
> eliminating skip-zone interference at long distances.

### NVIS Coverage vs Elevation Angle

Assuming F2-layer reflection at 300 km altitude:

| Elevation | Ground Radius | Round-Trip Distance | Application          |
|-----------|---------------|---------------------|----------------------|
| 90 deg    | 0 km          | 600 km              | Directly overhead    |
| 80 deg    | 53 km         | 606 km              | Local (city-wide)    |
| 70 deg    | 109 km        | 624 km              | Regional             |
| 60 deg    | 173 km        | 660 km              | Inter-city           |
| 45 deg    | 300 km        | 735 km              | Extended regional    |
| 30 deg    | 520 km        | 866 km              | Limit of NVIS zone  |

The ground radius is calculated from:

```
R = H_iono x tan(90 deg - alpha)

where H_iono = 300 km (F2-layer height)
```

---

## 4. System Diagram -- NVIS Mounting

```
                       5.0 m centre height
                       above ground

                          Vacuum Cap
                          (84-335 pF)
                          +--||--+
                     -----'  ||  '-----
                    /        ||        \
                   |   5/8" Cu tube    |
                   |                   |
     6.0 m ------>|    D = 2.0 m      |    Main loop
     (top)        |                   |    (vertical,
                   |                   |     facing
                   |                   |     broadside)
                    \                 /
                     --+           +--
     4.0 m ------>    | Coupling  |
     (bottom)         |  Loop     |
                      |  0.40 m   |
                      |  Faraday  |
                      +--||-------+
                           |
                        Coax (RG-213)
                        down mast
                           |
                           |
    ----------------------------------------- Ground level (0 m)
    =========================================
         Ground screen (4 m x 4 m)
         chicken wire or 8 radial wires (10 m each)
         centred below loop

    Min. mast height: 6 m (fibreglass or wooden)
```

The loop is mounted **vertically** (perpendicular to ground) with
its centre at **5.0 m height**. The bottom of the loop clears the
ground by 4.0 m -- well above head height for safety and comfortably
above the 2.5 m minimum safety clearance.

The loop plane should be oriented so the broadside direction (the
direction of maximum NVIS radiation at moderate angles) faces the
desired coverage area. For omnidirectional NVIS coverage, orient
the loop plane North-South (broadside East-West).

### Key Dimensions

| Dimension                  | Value                |
|----------------------------|----------------------|
| Loop centre height         | 5.0 m above ground   |
| Top of loop                | 6.0 m above ground   |
| Bottom of loop             | 4.0 m above ground   |
| Bottom clearance           | 4.0 m (safe)         |
| Minimum mast height        | 6.0 m                |
| Ground screen              | 4 m x 4 m below loop |
| Coax run (mast to ground)  | ~6 m minimum         |

---

## 5. Ground Screen

A ground screen dramatically improves the NVIS pattern by:

1. Creating a more consistent and predictable ground reflection
2. Increasing the effective ground conductivity directly under the loop
3. Reducing ground absorption losses
4. Making the array factor calculations (based on PEC ground) more
   accurate in practice

### Recommended Ground Screen

| Parameter          | Value                              |
|--------------------|------------------------------------|
| Type               | Chicken wire (25 mm mesh)          |
| Size               | 4 m x 4 m (minimum)               |
| Alternative        | 8 radial wires, 10 m each         |
| Placement          | On ground surface, centred below loop |
| Bonding            | Connect to station ground          |

### Ground Screen Construction Notes

- **Chicken wire option:** Lay a 4 m x 4 m sheet of galvanised
  chicken wire (poultry netting) flat on the ground directly beneath
  the loop. Secure with ground staples or tent pegs. Bond to the
  station ground with a short copper strap.

- **Radial wire option:** Lay 8 equally-spaced radial wires (10 m
  each, 14 AWG or heavier) emanating from a central hub directly
  below the loop. This is lighter and easier to install in uneven
  terrain. Use insulated wire to prevent corrosion.

For sites with poor soil (dry, sandy, rocky), the ground screen is
**strongly recommended**. On sites with good soil (moist, clay),
the bare ground is often adequate, though a screen still provides
measurable improvement.

---

## 6. Comparison: NVIS vs DX Mounting

### Elevation Pattern Comparison (40 m, Broadside Direction)

```
90 deg (zenith) ████████████████████████████████████  NVIS: 1.000
                ░░░░░░░░░░░                           DX:   0.000 (null)

80 deg          ███████████████████████████████████   NVIS: 0.989
                ░░░░░░░░░░░░░░░░░░                    DX:   0.174

70 deg          ██████████████████████████████████    NVIS: 0.952
                ░░░░░░░░░░░░░░░░░░░░░░░░░             DX:   0.342

45 deg          ██████████████████████████           NVIS: 0.742
                ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░     DX:   0.707

20 deg          █████████████                        NVIS: 0.371
                ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  DX:   0.940

10 deg          ██████                               NVIS: 0.190
                ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░ DX:   0.985

0 deg (horizon)                                       NVIS: 0.000 (null)
                ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░ DX:   1.000

████  NVIS (vertical loop at 5 m, over ground)
░░░░  DX (free space, broadside pattern)
```

The NVIS mounting completely **inverts** the elevation pattern:
the original broadside design peaks at the horizon for DX, while
the NVIS variant peaks at the zenith for regional coverage.

### Side-by-Side Parameter Comparison

| Parameter            | Original (DX)                    | NVIS Variant                     |
|----------------------|----------------------------------|----------------------------------|
| Loop orientation     | Vertical (standard)              | Vertical (same)                  |
| Centre height        | 2-3 m (typical)                  | 5.0 m above ground               |
| Bottom clearance     | ~1-2 m                           | 4.0 m minimum                    |
| Ground system        | None required                    | Ground screen recommended         |
| Peak radiation       | Broadside (horizon)              | Zenith (straight up)             |
| Take-off angle       | Low to medium (DX)               | 70 deg-90 deg elevation (NVIS)   |
| Primary use          | DX (> 500 km)                    | Regional (0-500 km)              |
| Loop / cap / tube    | 2.0 m, vacuum cap, 5/8" Cu      | Identical -- no changes          |
| Efficiency           | 8.5% (80m), 51.2% (40m)         | Identical                        |

---

## 7. Performance Summary

### 7.1 NVIS Take-Off Angles

| Band   | Freq      | Peak Elevation   | -3 dB Cone    | -6 dB Cone    |
|--------|-----------|------------------|---------------|---------------|
| 80 m   | 3.500 MHz | **90 deg (zenith)** | 45 deg-90 deg | 28 deg-90 deg |
| 80 m   | 3.800 MHz | **90 deg (zenith)** | 47 deg-90 deg | 30 deg-90 deg |
| 40 m   | 7.000 MHz | **90 deg (zenith)** | 44 deg-90 deg | 27 deg-90 deg |
| 40 m   | 7.300 MHz | **90 deg (zenith)** | 46 deg-90 deg | 29 deg-90 deg |

The -3 dB cone (half-power beamwidth) spans approximately 45 deg to
90 deg on both bands. This covers the entire NVIS propagation cone
with minimal pattern loss. Signals arriving from beyond 500 km
(elevation below ~30 deg) are suppressed by 6 dB or more, reducing
interference from distant stations.

### 7.2 Efficiency (Unchanged from DX Variant)

The antenna hardware is identical; efficiency is purely a function of
the loop's electrical properties and does not change with mounting height.

| Band   | Freq      | Efficiency | Eff (dB) |
|--------|-----------|------------|----------|
| 80 m   | 3.500 MHz | 8.5 %      | -10.71   |
| 80 m   | 3.800 MHz | 11.0 %     | -9.58    |
| 40 m   | 7.000 MHz | 51.2 %     | -2.91    |
| 40 m   | 7.300 MHz | 54.9 %     | -2.60    |

### 7.3 Typical NVIS Link Budget (40 m, 100 W, 300 km)

| Parameter                 | Value              |
|---------------------------|--------------------|
| Transmit power            | 100 W (+50.0 dBm)  |
| Antenna efficiency        | 51.2% (-2.9 dB)    |
| Antenna gain at zenith    | +2.7 dBi (est., incl. ground gain) |
| EIRP                      | +52.7 dBm          |
| Path loss (600 km via F2) | -125 dB (typ.)     |
| Ionospheric absorption    | -10 dB (typ.)      |
| Receive antenna gain      | +2.7 dBi           |
| Received signal           | -79.6 dBm          |
| Noise floor (40m, 4 kHz)  | -100 dBm (typ.)    |
| **SNR**                   | **+20.4 dB**       |

> SNR of +20 dB is comfortable for SSB voice and digital modes.
> Even at 25 W, the link closes with +14 dB SNR -- adequate for
> SSB and very comfortable for FT8/JS8Call digital modes.

### 7.4 Link Budget Notes

The estimated zenith gain of +2.7 dBi for this 2.0 m balanced loop
is lower than the +4.8 dBi estimated for the 3.0 m efficiency-optimised
variant. This difference is primarily due to:

1. **Lower efficiency:** 51.2% vs 83.3% on 40 m (-2.9 dB vs -0.8 dB),
   a difference of approximately 2.1 dB.
2. **Identical array factor:** Both variants at 5.0 m height produce
   the same ground-reflection gain at zenith.

Despite the lower gain, the +20 dB SNR on 40 m provides a comfortable
margin for reliable NVIS communications. On 80 m, the lower efficiency
(8.5%) reduces the SNR but NVIS links on 80 m benefit from lower
path loss and the natural quiet-time conditions on the band.

---

## 8. Increasing Height for Better 80 m NVIS

At 5 m, the 80 m performance is good but can be improved by raising
the loop. The following table shows the effect of height on zenith
signal strength (array factor with PEC ground):

### Height Optimisation Table

| Height (m) | h/lambda (80m) | Zenith AF (80m) | h/lambda (40m) | Zenith AF (40m) |
|------------|----------------|-----------------|----------------|-----------------|
| 3          | 0.035          | 0.436           | 0.070          | 0.852           |
| 4          | 0.047          | 0.578           | 0.093          | 1.105           |
| **5**      | **0.058**      | **0.718**       | **0.117**      | **1.338**       |
| 8          | 0.093          | 1.110           | 0.187          | 1.814           |
| 10         | 0.117          | 1.338           | 0.234          | 1.961           |
| 15         | 0.175          | 1.814           | 0.350          | 1.377 *         |
| 21.4 (lambda/4) | 0.250    | **2.000 (max)** | 0.500          | 0.000 (null!) * |

```
* At heights above lambda/4 on 40 m (10.7 m), the zenith signal begins
  to DECREASE as the ground reflection shifts from constructive to
  destructive. At exactly lambda/4 on 40 m the zenith AF is maximised,
  but at lambda/4 on 80 m (21.4 m) the 40 m zenith signal is a NULL.

  This is the fundamental height compromise for dual-band NVIS:
  the optimal height for one band may degrade the other.
```

### Optimal Heights

| Band     | Optimal h for zenith  | h in metres | Practical? |
|----------|-----------------------|-------------|------------|
| 80 m     | lambda/4 = 21.4 m    | 21.4 m      | Difficult  |
| 80 m     | 0.1 lambda           | 8.6 m       | Feasible   |
| 40 m     | lambda/4 = 10.7 m    | 10.7 m      | Feasible   |
| 40 m     | 0.1 lambda           | 4.3 m       | Easy       |
| **Both** | **5 m (compromise)** | **5.0 m**   | **Recommended** |

### Why 5.0 m is the Recommended Compromise

At 5.0 m centre height:

- **80 m:** The zenith AF of 0.718 is modest but sufficient. The
  loop is simply too low relative to the 80 m wavelength for maximum
  ground gain, but the zenith is still the peak direction and NVIS
  propagation works.

- **40 m:** The zenith AF of 1.338 indicates constructive ground
  reflection providing a net gain at zenith. This is a sweet spot --
  well below the lambda/4 height (10.7 m) where the pattern would
  start to develop a zenith null.

- **Practicality:** 5.0 m centre height requires a mast of only 6 m
  (to clear the top of the 2.0 m loop). This is achievable with a
  single section of fibreglass mast or a wooden pole.

- **Safety:** The 4.0 m bottom clearance exceeds the 2.5 m safety
  minimum by a comfortable margin.

---

## 9. Construction Notes for NVIS Mounting

### 9.1 Support Structure

1. Use a **fibreglass or wooden mast**, minimum 6 m tall.
   - Fibreglass push-up masts (e.g., Spiderbeam or MFJ fibreglass
     poles) are ideal -- lightweight, non-conductive, and portable.
   - A treated wooden pole (round or square, 75-100 mm cross-section)
     is a lower-cost alternative.
   - **Avoid metal masts** within 1 m of the loop. A metal mast
     close to the loop will couple to it, detune the resonance,
     and reduce efficiency.

2. The 2.0 m loop hangs vertically from a **cross-arm** at the top
   of the mast, with its centre at 5.0 m above ground. The cross-arm
   should be non-conductive (fibreglass tube, wooden dowel) and
   extend at least 0.5 m either side.

3. Bottom of loop clears ground by **4.0 m** (safe from contact).
   This exceeds the 2.5 m minimum safety clearance for 100 W
   operation, providing additional margin for people walking beneath.

4. **Guy wires** (non-metallic -- Dacron, polypropylene, or nylon
   rope) provide stability in wind. Attach guys to the mast below
   the loop, not to the loop itself.

### 9.2 Loop Orientation for NVIS

For pure NVIS (directly overhead coverage), loop orientation does not
matter significantly -- the zenith signal is the same regardless of
which direction the loop faces. However, the azimuth pattern at
moderate elevation angles is still a figure-8. For best all-around
regional coverage:

- **Orient the loop plane North-South** (broadside East-West).
  This puts the figure-8 lobes East and West, providing coverage
  in those directions at moderate elevation angles (50-70 deg).

- At true zenith (90 deg), the signal is omnidirectional and loop
  orientation has no effect.

- For coverage in a specific direction at moderate angles, orient
  the broadside toward the target area.

### 9.3 Coax Routing

- Run the coax (RG-213 recommended) down the inside of the mast
  or strapped to the outside with UV-resistant cable ties.
- At the base of the mast, make a service loop (1-2 turns of coax,
  ~30 cm diameter) as a choke balun to suppress common-mode currents.
- Alternatively, use a ferrite-core 1:1 current balun at the feed
  point or at the base of the mast.

### 9.4 Switching Between NVIS and DX

The same loop can serve both purposes:

- **NVIS mode:** Mount at 5+ m with ground screen -- high-angle peak
- **DX mode:** Mount at 2-3 m without ground screen -- broadside peak

A **tilting mast or pulley system** allows quick reconfiguration.
With a hinged base plate, the mast can be walked up for NVIS
operation and lowered for DX use in minutes.

---

## 10. Key Formulae (NVIS-Specific)

```
Array factor (broadside, over PEC ground):
  AF(alpha) = 2 |sin(k h sin(alpha))|

  where:
    alpha = elevation angle (0 deg = horizon, 90 deg = zenith)
    k     = 2 pi / lambda  (wavenumber)
    h     = loop centre height above ground (m)

Normalised elevation pattern (when zenith is peak):
  E_norm(alpha) = sin(k h sin(alpha)) / sin(k h)

Zenith array factor:
  AF(90 deg) = 2 |sin(k h)|

Optimal height for max zenith signal:
  h_opt = lambda / 4

NVIS ground radius (single hop):
  R = H_iono x tan(90 deg - alpha)

  where:
    H_iono = ionospheric layer height (~300 km for F2)
    alpha  = elevation angle

Round-trip path length:
  d = 2 x H_iono / sin(alpha)
```

### Worked Examples

**80 m at 5.0 m height:**

```
k = 2 pi / 85.71 = 0.07330 rad/m
kh = 0.07330 x 5.0 = 0.3665 rad
AF(90 deg) = 2 |sin(0.3665)| = 2 x 0.3584 = 0.717
```

**40 m at 5.0 m height:**

```
k = 2 pi / 42.86 = 0.14661 rad/m
kh = 0.14661 x 5.0 = 0.7330 rad
AF(90 deg) = 2 |sin(0.7330)| = 2 x 0.6691 = 1.338
```

---

## 11. Design Validation Checklist (NVIS)

### 11.1 Antenna Hardware (Unchanged)

- [x] Loop diameter: 2.0 m
- [x] Tube: 5/8" (15.875 mm OD) Type M copper
- [x] Inductance: 6.18 uH
- [x] Circumference: 6.283 m, Area: 3.142 m^2
- [x] Coupling loop: 0.40 m diameter, Faraday shielded
- [x] Capacitor: 84-335 pF vacuum variable, >= 10 kV
- [x] Max power: 100 W

### 11.2 NVIS Configuration

- [x] Centre height 5.0 m gives zenith peak on both bands
- [x] Bottom clearance 4.0 m exceeds safety minimum (2.5 m)
- [x] -3 dB NVIS cone covers 45 deg-90 deg elevation
- [x] Low-angle radiation suppressed > 15 dB below 10 deg elevation
- [x] Ground screen specified for improved performance
- [x] Efficiency identical to original design (8.5% / 51.2%)
- [x] Mast requirement: minimum 6 m, non-metallic

### 11.3 Pattern Validation

- [x] Zenith AF (80 m): 0.718 -- zenith is peak direction (h < lambda/4)
- [x] Zenith AF (40 m): 1.338 -- zenith is peak direction (h < lambda/4)
- [x] Horizon null confirmed on both bands (AF = 0 at alpha = 0)
- [x] -3 dB cone width consistent between 80 m and 40 m (~45 deg)
- [x] No unwanted secondary lobes (h well below lambda/2 on both bands)

### 11.4 Link Budget Validation

- [x] 40 m NVIS at 100 W: SNR = +20.4 dB (comfortable for SSB)
- [x] 40 m NVIS at 25 W: SNR = +14.4 dB (adequate for SSB/digital)
- [x] Path loss estimate (-125 dB for 600 km F2 hop) is conservative
- [x] Noise floor estimate (-100 dBm for 40 m, 4 kHz BW) is typical

---

## Appendix A: Antenna Parameters Quick Reference

```
 BALANCED MAGNETIC LOOP -- NVIS VARIANT
 =======================================
 Loop:    2.0 m dia, 5/8" Cu Type M
 L:       6.18 uH
 Cap:     84-335 pF vacuum variable (>= 10 kV)
 Couple:  0.40 m Faraday shielded
 Mount:   Vertical, centre at 5.0 m AGL
 Mast:    Fibreglass/wood, min 6 m
 Ground:  4 m x 4 m screen or 8 x 10 m radials

 80m: 3.5 MHz  335 pF   8.5%  -10.7 dB  Q=2023  BW=1.7 kHz
      3.8 MHz  284 pF  11.0%   -9.6 dB  Q=1897  BW=2.0 kHz

 40m: 7.0 MHz   84 pF  51.2%   -2.9 dB  Q=1525  BW=4.6 kHz
      7.3 MHz   77 pF  54.9%   -2.6 dB  Q=1450  BW=5.0 kHz

 NVIS Performance:
   Peak radiation:    Zenith (90 deg)
   -3 dB cone:        45 deg - 90 deg elevation
   Take-off angle:    70 deg - 90 deg (NVIS)
   Coverage:          0 - 500 km (F2 single hop)
   Zenith AF (80m):   0.718
   Zenith AF (40m):   1.338

 Max power: 100 W SSB/CW (vacuum cap >= 10 kV)
 Feed:      50 Ohm coax, RG-213 recommended
 =======================================
```

---

## Appendix B: Comparison with 3.0 m Efficiency-Optimised NVIS

For operators choosing between the 2.0 m balanced and 3.0 m
efficiency-optimised designs for NVIS use:

| Parameter              | 2.0 m Balanced (this doc) | 3.0 m Efficiency-Optimised |
|------------------------|---------------------------|----------------------------|
| Loop diameter          | 2.0 m                     | 3.0 m                      |
| Tube                   | 5/8" (15.875 mm)          | 7/8" (22.225 mm)           |
| Weight (loop only)     | ~7 kg                     | ~12 kg                     |
| Transportable?         | Fits through doorway      | Requires disassembly       |
| 80 m efficiency        | 8.5%                      | 30.5%                      |
| 40 m efficiency        | 51.2%                     | 83.3%                      |
| 80 m eff. difference   | --                        | +5.5 dB better             |
| 40 m eff. difference   | --                        | +2.1 dB better             |
| NVIS centre height     | 5.0 m                     | 5.0 m                      |
| Bottom clearance       | 4.0 m                     | 3.5 m                      |
| Min mast height        | 6 m                       | 7 m                        |
| NVIS link SNR (40m)    | +20.4 dB                  | +23.8 dB                   |
| Capacitor voltage      | 6,438 V peak (40m, 100W)  | Similar                    |
| Installation           | One person                 | Two people recommended     |

**Summary:** The 3.0 m loop has 2-5 dB more gain but is significantly
larger, heavier, and harder to install. For portable or field NVIS
deployments, the 2.0 m balanced loop is the better choice. For a
fixed NVIS station where maximum performance justifies the size,
the 3.0 m design is superior.

---

*NVIS variant of the 3-7MHz balanced magnetic loop.
Same antenna hardware, optimised mounting for near-vertical radiation.
Based on ground-reflection array theory applied to small magnetic loops.*

<!-- Tags: magnetic-loop, NVIS, 80m, 40m, balanced, 2.0m, HF, skywave,
     regional, emergency, vertical-loop, ground-screen, 3.5MHz, 7.0MHz -->
