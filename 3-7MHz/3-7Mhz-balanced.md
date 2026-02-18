# Magnetic Loop Antenna -- 3.5-7.3 MHz Balanced Design

> **Band Coverage:** 80 m (3.500-3.800 MHz) and 40 m (7.000-7.300 MHz)
> **Design Philosophy:** Balance efficiency with practical physical size
> **Revision:** 1.0 -- 2026-02-18

---

## 1. Design Objective

This design targets a **practical middle ground** between the compact-but-lossy
small magnetic loops and the high-efficiency-but-unwieldy large designs. A 2.0 m
diameter loop built from 5/8" copper tubing delivers meaningful efficiency gains
over the common 1 m / 3/8" configuration while remaining manageable for
**rooftop, balcony, or backyard** installation by a single operator.

| Goal                     | Target                                         |
|--------------------------|-------------------------------------------------|
| 80 m efficiency          | >= 8 %  (vs ~0.7 % for a 1 m loop)              |
| 40 m efficiency          | >= 50 % (vs ~7.6 % for a 1 m loop)              |
| Maximum dimension        | 2.0 m -- fits through a standard doorway         |
| Total weight (loop only) | ~7 kg -- one-person carry                        |
| Power handling           | 100 W continuous SSB/CW with vacuum capacitor    |
| Wind survival            | 100 km/h with appropriate bracing                |

The design is **not** intended to compete with a full-size dipole or beam on
40 m, but on 80 m it offers a viable alternative when space prohibits a
full-size wire antenna, and on 40 m it is genuinely competitive with
compromise wire antennas.

---

## 2. System Diagram

```
                        Vacuum Variable Capacitor
                         84 -- 335 pF, >= 10 kV
                       ┌──────┤ ├──────┐
                       │    ══════     │
                       │   (weather    │
                       │    housing)   │
                       │               │
                  ─────┘               └─────
                /                             \
              /    5/8" Cu Type M tubing        \
             │      OD = 15.875 mm               │
             │      Wall = 0.711 mm               │       ↑
             │                                    │       │
             │         Loop Diameter              │    2.0 m
             │           D = 2.0 m                │       │
             │                                    │       │
             │                                    │       ↓
              \                                  /
                \                              /
                  ─────┐               ┌─────
                       │               │
                       │   ┌───────┐   │
                       │   │       │   │
                       └───┤ Coup. ├───┘
                           │ Loop  │
                           │0.40 m │
                           │Faraday│
                           └───┬───┘
                               │
                            Coax to
                          Transceiver
                          (50 Ω, RG-213)
```

**Physical layout notes:**

- The main loop is mounted with the capacitor at the **top** (12 o'clock) to
  maximise clearance from ground and personnel.
- The coupling loop is centred at the **bottom** (6 o'clock), directly
  opposite the capacitor.
- The feed point is a BNC or SO-239 connector mounted on the coupling loop
  shield break.

---

## 3. Material Properties

### 3.1 Copper Conductivity

| Property                  | Value                          |
|---------------------------|--------------------------------|
| Conductivity (sigma)      | 5.800 x 10^7 S/m              |
| Relative permeability     | mu_r = 1.0                     |
| Tube specification        | ASTM B88, Type M, 5/8" nominal |
| Tube outer diameter (OD)  | 15.875 mm (0.625 in)           |
| Tube wall thickness       | 0.711 mm (0.028 in)            |
| Tube inner diameter       | 14.453 mm                      |

### 3.2 Skin Depth (delta)

The skin depth is calculated from:

```
delta = 1 / sqrt(pi * f * mu_0 * sigma)
```

| Frequency (MHz) | Skin Depth (um) | Wall / delta | Notes                     |
|------------------|-----------------|--------------|---------------------------|
| 3.500            | 35.1            | 20.3         | Current fully on surface   |
| 3.650            | 34.4            | 20.7         | Current fully on surface   |
| 3.800            | 33.7            | 21.1         | Current fully on surface   |
| 7.000            | 24.8            | 28.7         | Current fully on surface   |
| 7.100            | 24.6            | 28.9         | Current fully on surface   |
| 7.200            | 24.5            | 29.0         | Current fully on surface   |
| 7.300            | 24.3            | 29.3         | Current fully on surface   |

In all cases the wall thickness exceeds 20 skin depths, confirming that the
full cross-section of copper is utilised for RF current conduction and tube
wall thickness is not a limiting factor.

---

## 4. Loop Parameters

### 4.1 Physical Dimensions

| Parameter             | Symbol | Value          |
|----------------------|--------|----------------|
| Loop diameter         | D      | 2.000 m        |
| Loop radius           | b      | 1.000 m        |
| Tube outer diameter   | 2a     | 15.875 mm      |
| Tube outer radius     | a      | 7.9375 mm      |
| Circumference         | C      | 6.283 m        |
| Enclosed area         | A      | 3.142 m^2      |
| Ratio b/a             |        | 126.0          |

### 4.2 Loop Inductance

Inductance of a single-turn circular loop of round conductor:

```
L = mu_0 * b * [ ln(8b/a) - 2 ]
```

Substituting:

```
L = (4*pi*10^-7) * 1.000 * [ ln(8 * 1.000 / 0.0079375) - 2 ]
  = 1.2566 x 10^-6  * [ ln(1007.9) - 2 ]
  = 1.2566 x 10^-6  * [ 6.9155 - 2 ]
  = 1.2566 x 10^-6  * 4.9155
  = 6.18 x 10^-6 H
```

**L = 6.18 uH**

### 4.3 Electrical Size (Circumference / Wavelength)

| Frequency (MHz) | Wavelength (m) | C / lambda | Electrical Category |
|------------------|----------------|------------|---------------------|
| 3.500            | 85.71          | 0.073      | Very small           |
| 3.650            | 82.19          | 0.077      | Very small           |
| 3.800            | 78.95          | 0.080      | Very small           |
| 7.000            | 42.86          | 0.147      | Small                |
| 7.100            | 42.25          | 0.149      | Small                |
| 7.200            | 41.67          | 0.151      | Small                |
| 7.300            | 41.10          | 0.153      | Small                |

The loop is electrically small (C/lambda < 0.25) across the entire operating
range, validating the lumped-element model used throughout this analysis.

---

## 5. Tuning Capacitance

### 5.1 Required Capacitance

Resonance condition: `f = 1 / (2*pi*sqrt(L*C))`, solved for C:

```
C = 1 / ( (2*pi*f)^2 * L )
```

| Frequency (MHz) | C_tune (pF) |
|------------------|-------------|
| 3.500            | 335.0       |
| 3.650            | 308.2       |
| 3.800            | 283.8       |
| 7.000            | 83.6        |
| 7.100            | 81.3        |
| 7.200            | 79.1        |
| 7.300            | 77.0        |

**Required capacitance range: 77.0 -- 335.0 pF** (ratio 4.35:1)

### 5.2 Capacitor Selection

**Primary recommendation: Vacuum variable capacitor**

| Specification        | Requirement             | Recommended Part           |
|----------------------|-------------------------|----------------------------|
| Capacitance range    | 84 -- 335 pF minimum    | 10 -- 500 pF (provides margin) |
| Voltage rating       | >= 6,500 V peak (100 W) | >= 10 kV (safe margin)     |
| Current rating       | >= 10 A RMS             | Check at full power        |
| Type                 | Vacuum variable         | Jennings CSVF-500-0010 or equiv. |

Surplus vacuum variables from Jennings, Dolinko & Wilkens, or Russian
equivalents (e.g., KP1-4) are commonly available on the surplus market at
reasonable cost.

**Alternative for low power (< 25 W): High-voltage butterfly capacitor**

A split-stator butterfly capacitor rated at 3 kV or higher may be used at
QRP power levels. The butterfly configuration has the advantage of requiring
only 180 degrees of rotation for full range and eliminates wiper contact
resistance. However, voltage ratings are typically insufficient for 100 W
operation on 80 m where capacitor voltages exceed 5 kV.

### 5.3 Capacitor Mounting

The capacitor must be mounted at the top of the loop with:

- Minimum lead length (< 20 mm each side) to reduce stray inductance
- Weatherproof housing (UV-resistant polycarbonate or fibreglass)
- Reduction drive or stepper motor for remote tuning
- Reduction ratio >= 6:1 for adequate tuning resolution

---

## 6. Performance Tables

### 6.1 Radiation Resistance

Radiation resistance for a small loop:

```
R_rad = 31171 * (A / lambda^2)^2   [Ohms]

      = 31171 * (pi * b^2)^2 / lambda^4

      = 31171 * (3.142)^2 / lambda^4
```

### 6.2 Loss Resistance

The ohmic loss resistance of the loop conductor:

```
R_loss = ( C_loop / (2*pi*a) ) * sqrt( pi * f * mu_0 / sigma )

where:
  C_loop = circumference = 6.283 m
  a      = tube outer radius = 7.9375 mm
  sigma  = 5.800 x 10^7 S/m
```

### 6.3 Efficiency

```
eta = R_rad / (R_rad + R_loss)
```

### 6.4 80 m Band Performance (3.500 -- 3.800 MHz)

| Freq (MHz) | C_tune (pF) | Circ/lambda | R_rad (Ohm) | R_loss (Ohm) | Efficiency | eta (dB) | Q    | BW (kHz) | V_cap @ 100W (V) |
|------------|-------------|-------------|-------------|--------------|------------|----------|------|----------|-------------------|
| 3.500      | 335.0       | 0.073       | 0.00570     | 0.06147      | 8.5%       | -10.71   | 2023 | 1.73     | 5244              |
| 3.650      | 308.2       | 0.077       | 0.00674     | 0.06278      | 9.7%       | -10.13   | 1961 | 1.86     | 5338              |
| 3.800      | 283.8       | 0.080       | 0.00793     | 0.06407      | 11.0%      | -9.58    | 1897 | 2.00     | 5417              |

### 6.5 40 m Band Performance (7.000 -- 7.300 MHz)

| Freq (MHz) | C_tune (pF) | Circ/lambda | R_rad (Ohm) | R_loss (Ohm) | Efficiency | eta (dB) | Q    | BW (kHz) | V_cap @ 100W (V) |
|------------|-------------|-------------|-------------|--------------|------------|----------|------|----------|-------------------|
| 7.000      | 83.6        | 0.147       | 0.09127     | 0.08695      | 51.2%      | -2.91    | 1525 | 4.59     | 6438              |
| 7.100      | 81.3        | 0.149       | 0.09654     | 0.08759      | 52.4%      | -2.80    | 1501 | 4.73     | 6392              |
| 7.200      | 79.1        | 0.151       | 0.10209     | 0.08819      | 53.7%      | -2.70    | 1477 | 4.87     | 6341              |
| 7.300      | 77.0        | 0.153       | 0.10786     | 0.08881      | 54.9%      | -2.60    | 1450 | 5.03     | 6287              |

### 6.6 Summary

| Band | Efficiency Range | Gain vs Isotropic (dBi) | Typical Gain (dBi)      |
|------|------------------|-------------------------|-------------------------|
| 80 m | 8.5 -- 11.0 %    | -12.4 to -11.3          | -11.8 (mid-band)        |
| 40 m | 51.2 -- 54.9 %   | -4.6 to -4.3            | -4.5 (mid-band)         |

On 40 m this loop is only ~4.5 dB below an isotropic radiator, which is a
genuinely usable signal level. On 80 m the efficiency is modest but represents
a massive improvement over the 1 m standard design.

---

## 7. Coupling Loop

### 7.1 Dimensions

| Parameter              | Value                                |
|------------------------|--------------------------------------|
| Coupling loop diameter | 0.40 m (D/5 = 2.0/5)                |
| Coupling loop type     | Faraday shielded                     |
| Construction           | RG-213 or 1/4" copper with shield gap |
| Position               | Bottom centre (6 o'clock), coplanar  |
| Feed impedance target  | 50 Ohm unbalanced                    |

### 7.2 Faraday Shield

The coupling loop uses a **Faraday shield** (also called a shielded loop or
balanced coupling loop) to:

1. **Reject electric-field pickup** -- reduces local noise ingress from nearby
   electronic devices, power lines, and switching power supplies.
2. **Improve pattern symmetry** -- forces purely magnetic coupling to the
   main loop.
3. **Reduce capacitive coupling** -- prevents frequency pulling caused by
   proximity effects and hand capacitance during manual tuning.

Construction: Form the coupling loop from coaxial cable (RG-213 recommended).
Leave a gap in the shield at the point diametrically opposite the feed point.
The gap must be at least 10 mm wide. The inner conductor and shield connect
together at the feed point, forming a single-turn shielded loop.

```
          Shield gap (10 mm min)
                 ╱╲
                ╱  ╲
    ┌──────────╱    ╲──────────┐
    │         GAP               │
    │    Coupling Loop 0.40 m   │
    │                           │
    └─────────┬─────────────────┘
              │
         SO-239 / BNC
              │
         RG-213 to TX
```

### 7.3 Matching Adjustment

The coupling loop diameter of D/5 provides an approximate 50 Ohm match.
Fine adjustment is achieved by:

- **Rotating** the coupling loop slightly out of the main loop plane
  (typically 0-15 degrees).
- **Adjusting vertical position** -- sliding the coupling loop up or down
  relative to the bottom of the main loop.

Target: SWR < 1.5:1 at resonance across both bands. An SWR < 2.0:1 is
acceptable and will result in negligible additional feed line loss with
RG-213 at HF.

---

## 8. Voltage and Safety

### 8.1 Capacitor Voltage

The peak voltage across the tuning capacitor at resonance:

```
V_cap = sqrt( P * Q * X_L )

      = sqrt( P * Q * 2*pi*f*L )
```

where P is the applied power in watts.

| Freq (MHz) | Q    | X_L (Ohm) | V_cap @ 100W (V) | V_cap @ 25W (V) |
|------------|------|-----------|-------------------|------------------|
| 3.500      | 2023 | 135.9     | 5244              | 2622             |
| 3.650      | 1961 | 141.8     | 5338              | 2669             |
| 3.800      | 1897 | 147.6     | 5417              | 2709             |
| 7.000      | 1525 | 271.9     | 6438              | 3219             |
| 7.100      | 1501 | 275.8     | 6392              | 3196             |
| 7.200      | 1477 | 279.7     | 6341              | 3171             |
| 7.300      | 1450 | 283.6     | 6287              | 3144             |

### 8.2 Maximum Voltage

The **worst-case capacitor voltage is 6,438 V peak at 7.0 MHz and 100 W**.
This mandates:

- A capacitor rated at **>= 10 kV** to provide adequate safety margin
  (approximately 1.55x the peak operating voltage).
- **No vacuum variable capacitor with a rating below 7 kV** should be used
  even at reduced power.

### 8.3 Safety Precautions

**WARNING: Lethal RF voltages are present on the tuning capacitor and
adjacent loop conductor during transmission.**

1. **Minimum clearance:** The loop must be mounted so that no person can
   approach within **1.0 m** of any part of the main loop or capacitor
   during transmission.
2. **RF exposure:** At 100 W the loop produces significant near-field
   RF energy. Comply with your national RF exposure regulations (e.g.,
   FCC OET Bulletin 65, ISED RSS-102, ICNIRP guidelines).
3. **Capacitor housing:** The capacitor and its connections must be enclosed
   in an insulating, weatherproof housing. **Never** leave high-voltage
   connections exposed.
4. **Interlock:** If the capacitor is motorised, consider an interlock that
   inhibits transmission during tuning adjustment to prevent arcing.
5. **Grounding:** The coax shield at the feed point must be bonded to the
   station ground system. A static-drain resistor (100 kOhm, 2 W) across
   the capacitor terminals prevents static charge buildup.

---

## 9. Bandwidth and Tuning

### 9.1 3 dB Bandwidth

The loaded bandwidth at resonance:

```
BW_3dB = f / Q_loaded
```

| Freq (MHz) | Q    | 3 dB Bandwidth | Notes                              |
|------------|------|----------------|------------------------------------|
| 3.500      | 2023 | 1.73 kHz       | Retuning needed per QSO            |
| 3.650      | 1961 | 1.86 kHz       | Retuning needed per QSO            |
| 3.800      | 1897 | 2.00 kHz       | Retuning needed per QSO            |
| 7.000      | 1525 | 4.59 kHz       | Covers ~2 SSB channels             |
| 7.100      | 1501 | 4.73 kHz       | Covers ~2 SSB channels             |
| 7.200      | 1477 | 4.87 kHz       | Covers ~2 SSB channels             |
| 7.300      | 1450 | 5.03 kHz       | Covers ~2 SSB channels             |

### 9.2 Tuning Implications

The narrow bandwidth is an inherent property of high-Q small loops and is
**not a defect** -- it is the direct consequence of the low loss resistance
that enables the efficiency figures above. However, it has practical
consequences:

- **80 m:** With ~1.8 kHz bandwidth, the loop must be retuned for virtually
  every frequency change. A motor-driven capacitor with remote control is
  strongly recommended for 80 m operation.
- **40 m:** With ~4.7 kHz bandwidth, a single tuning setting covers
  approximately one CW segment or two SSB channels. Manual tuning is
  practical for casual 40 m use.
- **Tuning resolution:** The capacitance change per kHz is approximately
  0.09 pF/kHz on 80 m and 0.02 pF/kHz on 40 m. A high-ratio reduction
  drive (>= 6:1) or stepper motor with microstepping is essential.

### 9.3 SWR Bandwidth

The 2:1 SWR bandwidth is approximately 0.6 times the 3 dB bandwidth:

| Band | 2:1 SWR BW (approx.) |
|------|----------------------|
| 80 m | ~1.1 kHz             |
| 40 m | ~2.8 kHz             |

---

## 10. Construction Notes

### 10.1 Forming the Loop

1. **Copper tubing:** Purchase 7 m of 5/8" (15.875 mm OD) Type M copper
   tubing. Type M is the thinnest wall (0.711 mm) commonly available and is
   adequate -- wall thickness far exceeds skin depth at all operating
   frequencies (see Section 3.2).

2. **Bending:** Use a **tube bender** rated for 5/8" tubing, or bend around a
   circular form (e.g., a 2.0 m diameter plywood template). Anneal the copper
   first by heating to dull red with a propane torch and quenching, to prevent
   kinking. Alternatively, fill with dry sand and cap both ends before bending.

3. **Joint:** The loop is ideally a single piece. If a joint is necessary
   (e.g., for transport), use a **silver-soldered sleeve joint** with a
   minimum overlap of 50 mm. Mechanical compression fittings add unacceptable
   contact resistance at RF. **Never** use plumbing solder (tin-lead or
   lead-free) -- silver braze alloy (e.g., Harris Stay-Silv 45%) is required
   for reliable low-resistance joints.

4. **Gap:** Leave a gap of approximately 25-30 mm at the top for capacitor
   connection. Flatten the tube ends and drill for bolted connections to the
   capacitor terminals. Use stainless steel hardware with lock washers.

### 10.2 Capacitor Connection

- Keep leads between the loop ends and capacitor terminals as **short as
  possible** (ideally < 20 mm each side).
- Use copper strap (25 mm wide, 0.5 mm thick) rather than wire for the
  connections to minimise added inductance and resistance.
- All connections must be **silver-soldered or bolted with clean, bright
  copper-to-copper contact**. Apply conductive anti-oxidant paste (e.g.,
  Penetrox A) to bolted joints.

### 10.3 Support Structure

- The loop should be supported by a **non-conductive mast** (fibreglass,
  PVC, or treated wood) at the bottom centre.
- Use UV-resistant nylon or PTFE stand-offs to secure the loop to the mast.
  Avoid metal clamps on the loop conductor itself.
- For rooftop mounting, a non-conductive tripod base with guy wires provides
  adequate wind resistance.
- Keep the bottom of the loop at least **1.5 m above the roof or ground** to
  reduce ground losses and maintain safe clearance.

### 10.4 Weatherproofing

- Apply **clear lacquer** or conformal coating to the copper if long-term
  outdoor exposure is expected. Copper oxide increases surface resistance;
  however, in practice the effect is minor and some operators prefer to leave
  the copper bare.
- The capacitor housing must be fully sealed against moisture ingress.
  Desiccant packs inside the housing help prevent condensation.
- Seal all coax connectors with self-amalgamating tape and apply dielectric
  grease to connector threads.

---

## 11. Design Comparison

### 11.1 Three-Point Comparison

| Parameter              | Standard (1m/3/8")  | This Design (2m/5/8") | Max-Eff (3m/7/8")    |
|------------------------|---------------------|-----------------------|----------------------|
| Diameter               | 1.0 m               | 2.0 m                 | 3.0 m                |
| Tube                   | 3/8" (9.525 mm)     | 5/8" (15.875 mm)      | 7/8" (22.225 mm)     |
| Weight                 | ~3 kg               | ~7 kg                 | ~12 kg               |
| 80 m efficiency (eta)  | 0.7%                | 8.5%                  | 30.5%                |
| 40 m efficiency (eta)  | 7.6%                | 51.2%                 | 83.3%                |
| 80 m gain vs standard  | --                  | +10.8 dB              | +16.4 dB             |
| 40 m gain vs standard  | --                  | +8.3 dB               | +10.4 dB             |

### 11.2 Analysis

**Why the 2 m balanced design is the sweet spot:**

1. **Diminishing returns above 2 m:** Going from 1 m to 2 m yields +10.8 dB
   on 80 m. Going from 2 m to 3 m yields only an additional +5.6 dB. The
   first doubling delivers almost twice the dB improvement of the second
   50% increase.

2. **Practical size limit:** A 2 m loop fits through a standard doorway
   (typically 2.03 m / 80 inches) and can be transported in a mid-size
   vehicle. A 3 m loop cannot, and typically requires disassembly for
   transport.

3. **Weight:** At ~7 kg the 2 m loop can be lifted and installed by one
   person. The 12 kg 3 m loop requires two people and a more substantial
   support structure.

4. **Cost:** The 2 m design uses approximately half the copper and a similar
   capacitor to the 3 m design, at roughly half the materials cost.

5. **40 m competitiveness:** At 51.2% efficiency (-2.9 dB), the 2 m loop is a
   genuinely competitive antenna on 40 m. The loss compared to a full-size
   dipole is only about 5 dB -- easily compensated by favourable propagation,
   operator skill, or the loop's inherent noise-rejection advantage.

---

## 12. Bill of Materials (BOM)

### 12.1 Estimated Costs (USD, 2026)

| Item | Description | Qty | Est. Cost |
|------|-------------|-----|-----------|
| Copper tubing | 5/8" Type M, 7 m length | 1 | $40 -- $70 |
| Vacuum variable capacitor | 10-500 pF, >= 10 kV (surplus) | 1 | $80 -- $250 |
| Reduction drive / stepper | Vernier drive >= 6:1, or NEMA-17 stepper + controller | 1 | $20 -- $80 |
| Coupling loop | RG-213 coax, 1.3 m length | 1 | $5 -- $10 |
| Coax feed line | RG-213, 15 m | 1 | $25 -- $40 |
| Connectors | SO-239 / PL-259 / BNC as needed | 4 | $10 -- $20 |
| Capacitor housing | Polycarbonate or fibreglass enclosure | 1 | $15 -- $30 |
| Support mast | Fibreglass or PVC, 2.5 m | 1 | $20 -- $40 |
| Hardware | SS bolts, copper strap, stand-offs, cable ties | lot | $15 -- $30 |
| Silver brazing alloy | Harris Stay-Silv 45%, flux | 1 | $15 -- $25 |
| Weatherproofing | Self-amalgamating tape, dielectric grease, lacquer | lot | $10 -- $15 |
| | | **Total** | **$255 -- $610** |

### 12.2 Notes

- The **largest cost variable** is the vacuum capacitor. New units from
  manufacturers like Jennings or Comet can cost $500+. Surplus or used units
  from hamfests, eBay, or surplus dealers are typically $80 -- $250.
- Russian surplus vacuum capacitors (KP1-4, KP1-8 series) offer excellent
  value, typically $50 -- $150 shipped.
- The total cost target of **$250 -- $600** is achievable depending on
  capacitor sourcing.

---

## 13. Key Formulae

All formulae used in this design, collected for reference and validation.

### 13.1 Loop Inductance (single-turn circular loop, round conductor)

```
L = mu_0 * b * [ ln(8*b/a) - 2 ]

where:
  mu_0 = 4*pi*10^-7 H/m   (permeability of free space)
  b    = loop radius (m)
  a    = conductor outer radius (m)
```

### 13.2 Resonant Capacitance

```
C = 1 / [ (2*pi*f)^2 * L ]
```

### 13.3 Radiation Resistance (small circular loop)

```
R_rad = 31171 * (A / lambda^2)^2

where:
  A      = pi * b^2  (loop area, m^2)
  lambda = c / f     (wavelength, m)
  c      = 2.998 x 10^8 m/s
```

This can also be written as:

```
R_rad = 31171 * (pi * b^2)^2 * f^4 / c^4

      = 20 * pi^2 * (C_loop / lambda)^4 * (pi / 4)
```

### 13.4 Skin Depth

```
delta = 1 / sqrt( pi * f * mu_0 * sigma )

where:
  sigma = conductivity (S/m)
```

### 13.5 Loss Resistance

```
R_loss = ( C_loop / (2*pi*a) ) * R_s

where:
  R_s    = 1 / (sigma * delta)    (surface resistance, Ohm)
  C_loop = 2*pi*b                 (circumference, m)
  a      = conductor outer radius (m)

Equivalently:

R_loss = ( C_loop / (2*pi*a) ) * sqrt( pi*f*mu_0 / sigma )
```

### 13.6 Efficiency

```
eta = R_rad / (R_rad + R_loss)

eta (dB) = 10 * log10(eta)
```

### 13.7 Quality Factor

```
Q = 2*pi*f*L / (R_rad + R_loss)

  = X_L / R_total
```

### 13.8 Bandwidth

```
BW_3dB = f / Q   (Hz)
```

### 13.9 Capacitor Voltage

```
V_cap_peak = sqrt( P * Q * X_L )

where:
  P   = applied power (W)
  X_L = 2*pi*f*L (inductive reactance at resonance, Ohm)
```

### 13.10 Coupling Loop Diameter

```
D_coupling = D_main / 5

           = 2.0 / 5 = 0.40 m
```

This is a widely used rule of thumb for achieving an approximate 50 Ohm feed
impedance with magnetic coupling.

---

## 14. Validation Checklist

Use this checklist to verify the design calculations and the constructed
antenna before operation.

### 14.1 Design Validation

- [ ] **Inductance:** Confirm L = 6.18 uH using an antenna analyser or
      LC meter. Expected tolerance: +/- 5%.
- [ ] **Resonance on 80 m:** With C ~335 pF, confirm resonance at 3.500 MHz
      (+/- 20 kHz).
- [ ] **Resonance on 40 m:** With C ~84 pF, confirm resonance at 7.000 MHz
      (+/- 30 kHz).
- [ ] **Capacitance range:** Verify the variable capacitor tunes through the
      full range 77 -- 335 pF. Measure with a capacitance meter at several
      shaft positions.
- [ ] **Q measurement:** Measure 3 dB bandwidth at 7.0 MHz. Expected BW
      ~4.6 kHz (Q ~1525). Measured Q within 20% of calculated indicates
      acceptable construction quality.

### 14.2 Electrical Safety

- [ ] **Capacitor voltage rating:** >= 10 kV confirmed on capacitor nameplate
      or datasheet.
- [ ] **Clearance:** Minimum 1.0 m clearance from all accessible surfaces
      during TX.
- [ ] **RF exposure compliance:** Perform an RF exposure assessment per
      applicable regulations for 100 W at the installed location.
- [ ] **Static drain resistor:** 100 kOhm / 2 W across capacitor terminals.
- [ ] **Coax shield grounded:** Feed line shield bonded to station ground.

### 14.3 Mechanical

- [ ] **Joint quality:** All silver-soldered joints are smooth, bright, and
      mechanically sound. No cold joints.
- [ ] **Capacitor connections:** Copper strap connections are < 20 mm length,
      tight, and treated with anti-oxidant.
- [ ] **Loop circularity:** Loop is reasonably circular (minor deviations are
      acceptable; significant dents or kinks should be corrected).
- [ ] **Coupling loop:** Faraday shield gap is present, clean, and at least
      10 mm wide.
- [ ] **Weatherproofing:** Capacitor housing sealed; connectors taped and
      greased.

### 14.4 On-Air Verification

- [ ] **SWR at resonance:** < 1.5:1 on both bands. Adjust coupling loop
      angle/position if needed.
- [ ] **SWR bandwidth:** Approximately 1.1 kHz (80 m) and 2.8 kHz (40 m)
      for 2:1 SWR.
- [ ] **Receive noise floor:** Compare to a reference antenna. The loop
      should show a noticeably lower noise floor, especially on 80 m.
- [ ] **Transmit reports:** Confirm on-air signal reports are consistent with
      expected efficiency. On 40 m, reports should be within 5-10 dB of a
      full-size dipole at similar height.
- [ ] **Directional null:** Confirm a deep broadside null exists by rotating
      the loop. Useful for noise rejection and interference mitigation.

---

## Appendix A: Derivation Notes

### Radiation Resistance Cross-Check

At 7.0 MHz (lambda = 42.857 m):

```
R_rad = 31171 * (3.1416 / 42.857^2)^2
      = 31171 * (3.1416 / 1836.73)^2
      = 31171 * (0.001711)^2
      = 31171 * 2.928 x 10^-6
      = 0.09127 Ohm  [matches table]
```

At 3.5 MHz (lambda = 85.714 m):

```
R_rad = 31171 * (3.1416 / 85.714^2)^2
      = 31171 * (3.1416 / 7346.94)^2
      = 31171 * (4.277 x 10^-4)^2
      = 31171 * 1.829 x 10^-7
      = 0.00570 Ohm  [matches table]
```

### Loss Resistance Cross-Check

At 7.0 MHz:

```
R_s = sqrt(pi * 7.0x10^6 * 4*pi*10^-7 / 5.8x10^7)
    = sqrt(pi * 7.0x10^6 * 1.2566x10^-6 / 5.8x10^7)
    = sqrt(4.774 x 10^-7)
    = 6.910 x 10^-4 Ohm

R_loss = (6.283 / (2*pi*0.0079375)) * 6.910x10^-4
       = (6.283 / 0.04988) * 6.910x10^-4
       = 125.97 * 6.910x10^-4
       = 0.08704 Ohm  [close to table value 0.08695]
```

Minor rounding differences are expected and acceptable.

---

## Appendix B: Quick Reference Card

```
 BALANCED MAGNETIC LOOP -- 80m / 40m
 ====================================
 Loop:    2.0 m dia, 5/8" Cu Type M
 L:       6.18 uH
 Cap:     84-335 pF vacuum variable
 Couple:  0.40 m Faraday shielded

 80m: 3.5 MHz  335 pF   8.5%  -10.7 dB  Q=2023  BW=1.7 kHz   5244 V
      3.8 MHz  284 pF  11.0%   -9.6 dB  Q=1897  BW=2.0 kHz   5417 V

 40m: 7.0 MHz   84 pF  51.2%   -2.9 dB  Q=1525  BW=4.6 kHz   6438 V
      7.3 MHz   77 pF  54.9%   -2.6 dB  Q=1450  BW=5.0 kHz   6287 V

 Max power: 100 W SSB/CW (vacuum cap >= 10 kV)
 Feed:      50 Ohm coax, RG-213 recommended
 ====================================
```

---

*End of document.*
