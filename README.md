# CVX4 Gold

**High-precision parallel port stereo DAC with gold-plated connectors**

CVX4 Gold is a passive R2R DAC designed for retro PC parallel port (LPT) audio output. Based on the classic COVOX design with CVX4-style lowpass filtering (from [VOGONS](https://www.vogons.org/viewtopic.php?t=51483) forum), this version features precision components, optimized PCB layout, and full gold-plated connectors for superior audio quality.

## Features

- **Precision 0.01% R2R ladder** - Ultra-low DNL/INL for excellent linearity
- **5-stage lowpass filter** - C0G/NP0 ceramic capacitors for minimal distortion
- **Gold-plated connectors** - DB25 parallel port, 3.5mm stereo jack, RCA output
- **Stereo/mono selectable** - DIP switch configuration
- **Passive design** - No external power supply required
- **SMD 0805 components** - Compact PCB layout

## Specifications

| Parameter | Value |
|-----------|-------|
| **Input** | DB25 parallel port (LPT) |
| **Output** | 3.5mm stereo jack + RCA |
| **DAC Resolution** | 8-bit |
| **DAC Type** | R2R resistor ladder (100kΩ, 0.01% tolerance) |
| **Lowpass Filter** | 5-stage (1nF, 4.7nF, 10nF, 47nF, 100nF C0G/NP0) |
| **DC Blocking** | 100µF polymer tantalum |
| **Resistor Tolerance** | R2R ladder: 0.01%, Volume divider: 0.05% |
| **Capacitor Tolerance** | Filter: 5%, DC blocking: 20% |

## Bill of Materials (BOM)

See [bom.csv](bom.csv) for full component list with tested part numbers.

**Critical components:**
- **R1-R26 (25×):** 100kΩ 0.01% precision resistors (R2R ladder)
- **C1-C5:** C0G/NP0 ceramic capacitors (temperature-stable, low-distortion)
- **J2:** 3.5mm stereo jack, gold-plated (audio output)
- **J3:** RCA jack, gold-plated (audio output)

**Note:** Precision components (0.01% resistors, C0G/NP0 caps) are required for optimal audio quality. Generic 1% resistors or X7R capacitors will degrade performance.

## Assembly

Interactive BOM with component placement guide: [Open IBOM](ibom.html)

**Requirements:**
- SMD soldering experience (0805 components)
- Precision soldering iron (fine tip recommended)
- Flux and quality solder

**Assembly tips:**
1. Start with smallest components (R, C)
2. Through-hole connectors last (J1, J3, SW1)

## Schematic & PCB Files

- **Schematic:** [schematic.pdf](schematic.pdf)
- **Gerbers:** [gerbers.zip](gerbers.zip) (for PCB fabrication)

## Usage

### DIP Switch Configuration (SW1)

**9-position DIP switch (ON = enabled):**

| Position | Function | Description |
|----------|----------|-------------|
| **1-5** | Low Pass Filter | Enables individual lowpass filter stages (C1-C5) |
| **6-7** | Volume Divider | Enables volume attenuation (R27, R28) |
| **8** | DC Bypass | Bypasses DC blocking capacitor (C6) for DC-coupled output |
| **9** | Stereo | Enables stereo output mode |

**Recommended configuration:**
- **Position 2 ON (4.7nF filter), all others OFF**
- Adjust filter stages for desired frequency response if needed
- DC bypass (pos. 8): Use only with AC-coupled amplifiers

### Connections

- **J1 (DB25):** Connect to PC parallel port (LPT1/LPT2/LPT3)
- **J2 (3.5mm jack):** Stereo output (headphones, active speakers)
- **J3 (RCA):** Line output (amplifier, mixer)

### Software Compatibility

Compatible with DOS/retro PC software that supports LPT DAC output:
- COVOX/Disney Sound Source compatible players
- Tracker software (FastTracker 2, Impulse Tracker)
- DOS games with LPT audio support

## Credits

Based on the CVX4 design (COVOX parallel port DAC + lowpass filters).

**This version adds:**
- Stereo output support
- Optimized PCB layout
- Precision component selection (0.01% resistors, C0G/NP0 caps)
- Full gold-plated connectors

PCB design by Lopo, 2025.

## Copyright & Usage

Copyright © 2025 Lopo
Based on CVX4 community design (VOGONS forum).

**Permitted:**
- Personal and educational use
- Modifications and improvements
- Sharing modified designs (attribution required)

**Required:**
- Credit original design: "Based on CVX4 Gold by Lopo"
- Link to this repository when sharing

**Prohibited:**
- Commercial manufacturing without permission
- Claiming design as your own work

---

**Note:** This is a passive audio device. Audio quality depends on:
- Component precision (0.01% resistors critical for R2R linearity)
- C0G/NP0 capacitors (temperature-stable, low distortion)
- Clean PC parallel port signal (some modern motherboards may have noisy LPT output)
