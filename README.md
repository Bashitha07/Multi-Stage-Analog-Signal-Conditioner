# Multi-Stage Analog Signal Conditioner

Analog signal conditioning circuit designed to isolate a 2 kHz to 12 kHz audio passband and amplify weak signals using a BC547 NPN transistor amplifier stage.

## Overview

This project implements a multi-stage analog filter and amplifier to:
- Isolate an audio passband from 2 kHz to 12 kHz (bandpass filtering).
- Amplify low-level signals using a BC547 BJT amplifier stage.
- Validate the design using Proteus simulation files and measured results.

## Features

- Bandpass filtering to suppress low-frequency noise and high-frequency interference.
- BJT amplification stage (BC547) for signal gain.
- Proteus simulation project (.pdsprj) for circuit simulation and frequency response analysis.
- Project report with design calculations and circuit photos.

## Repository structure

```text
├── AE Photos/                                   # Circuit schematics and setup photos
├── AE_Final.pdsprj                              # Proteus design file (simulation project)
├── Group No. 04 - AE - Final Assignment Report.pdf  # Detailed design & calculations report
└── README.md                                    # Project documentation
```

## Files of interest

- AE_Final.pdsprj — open with Proteus to run simulations and inspect the circuit.
- Group No. 04 - AE - Final Assignment Report.pdf — contains the design rationale, calculations, and results.
- AE Photos/ — images of the circuit layout and experimental setup.

## How to use

1. Open `AE_Final.pdsprj` in Proteus to view and run the circuit simulation.
2. Review the assignment report for component values, filter design, and analysis.
3. Refer to the photos in `AE Photos/` for wiring and build references.

## Notes

- The circuit is designed for audio-frequency signal conditioning within the specified passband; component tolerances and PCB layout can affect performance.
- If you want additional documentation (schematics exported as PNG/SVG, BOM, or simulation screenshots), I can add them.

## Contributors

- B.A.Sellapperuma
- L.P.Jayasinghe
