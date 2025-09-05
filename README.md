# CMOS Inverter Design and Analysis using Cadence Virtuoso

## Overview

This repository contains the design, simulation, and comprehensive analysis of a CMOS inverter circuit implemented using Cadence Virtuoso. The project focuses on understanding the fundamental building block of digital circuits through detailed DC analysis, voltage transfer characteristics (VTC), and noise margin calculations.

## Project Description

The CMOS inverter consists of complementary PMOS and NMOS transistors configured in a push-pull arrangement. This project explores:

- **Schematic Design**: Complete CMOS inverter circuit design in Cadence Virtuoso
- **DC Analysis**: Voltage Transfer Characteristic (VTC) curve generation
- **Noise Margin Analysis**: Calculation of VIH, VIL, VOH, VOL parameters
- **Operating Regions**: Analysis of current flow in different operating modes
- **Trip Point Calculation**: Determination of switching threshold voltage

## Circuit Specifications

### Transistor Dimensions
- **PMOS (M0)**: W = 180.0n, L = 50n/1.50n
- **NMOS (M1)**: W = 90n, L = 50n/1.50n
- **Supply Voltage**: VDD = 1.2V (typical)
- **Load Capacitance**: 1fF

### Key Parameters Analyzed
- **VOH**: Output High Voltage
- **VOL**: Output Low Voltage  
- **VIH**: Input High Voltage (unity gain point)
- **VIL**: Input Low Voltage (unity gain point)
- **VM**: Trip point/Switching threshold voltage
- **NMH**: High-level noise margin
- **NML**: Low-level noise margin

## Repository Structure

```
├── README.md                          # This file
├── schematics/                        # Cadence Virtuoso schematic files
│   ├── inverter_schematic/            # Main inverter circuit
│   └── testbench/                     # Simulation testbench
├── simulation_results/                # Output waveforms and data
│   ├── vtc_analysis/                  # Voltage transfer characteristics
│   ├── noise_margin_plots/            # VIH, VIL, VOH, VOL analysis
│   └── operating_regions/             # Current analysis results
├── netlists/                          # SPICE netlists
├── documentation/                     # Additional documentation
│   ├── design_methodology.md          # Design approach and methodology
│   └── analysis_report.md             # Detailed analysis results
└── .gitignore                         # Git ignore file for Cadence files
```

## Analysis Results

### Voltage Transfer Characteristics (VTC)
The VTC curve demonstrates the inverter's switching behavior:
- Sharp transition region indicating high gain
- Full rail-to-rail output swing (0V to VDD)
- Switching threshold approximately at VDD/2 for balanced design

### Noise Margin Analysis
Noise margins calculated using unity gain method:
- **NMH = VOH - VIH**: High-level noise margin
- **NML = VIL - VOL**: Low-level noise margin

### Operating Regions
Five distinct operating regions analyzed:
1. **Region I**: NMOS off, PMOS linear
2. **Region II**: NMOS saturated, PMOS linear  
3. **Region III**: NMOS saturated, PMOS saturated (transition region)
4. **Region IV**: NMOS linear, PMOS saturated
5. **Region V**: NMOS linear, PMOS off

## Tools and Software

- **Cadence Virtuoso**: Schematic capture and simulation
- **SPICE Simulator**: DC and transient analysis
- **Technology**: Generic PDK (process design kit)

## Simulation Setup

### DC Analysis
- Input voltage swept from 0V to VDD
- Output voltage recorded at each input point
- VTC curve plotted and analyzed

### Noise Margin Calculation
- Unity gain points identified (slope = -1)
- Critical voltage levels extracted
- Noise margins calculated using standard definitions

## Key Insights

1. **Balanced Design**: Equal rise and fall times achieved with proper PMOS/NMOS sizing
2. **High Noise Immunity**: Good noise margins ensure robust digital operation
3. **Low Power**: Complementary structure ensures minimal static power consumption
4. **Scalability**: Design principles applicable to advanced technology nodes

## Files Description

- `inverter_schematic.jpg`: Main CMOS inverter schematic from Virtuoso
- `Noise_margin_inverter1.jpg`: VTC analysis showing VIH, VIL, VOH, VOL points
- `inverter_operation_region2.jpg`: Current analysis and operating regions

## Usage Instructions

1. **Opening in Virtuoso**: Load the schematic files in Cadence Virtuoso
2. **Running Simulations**: Execute DC analysis for VTC generation
3. **Parameter Extraction**: Use calculator functions to extract noise margin parameters
4. **Plotting Results**: Generate VTC and current characteristic plots

## Design Methodology

The design follows industry-standard practices:
- Proper transistor sizing for balanced switching
- Adequate biasing and load considerations  
- Comprehensive corner analysis for robustness
- Layout considerations for parasitics

## Future Enhancements

- Layout design and DRC/LVS verification
- AC analysis for frequency response
- Temperature and process variation analysis
- Power consumption optimization
- Scaling to advanced technology nodes

## Contributing

Feel free to contribute to this project by:
- Improving simulation accuracy
- Adding new analysis features
- Optimizing design parameters
- Enhancing documentation

## References

1. Rabaey, J. M., Chandrakasan, A., & Nikolic, B. (2003). Digital integrated circuits: a design perspective.
2. Weste, N. H., & Harris, D. (2010). CMOS VLSI design: a circuits and systems perspective.
3. Cadence Virtuoso Documentation
4. Industry-standard CMOS design practices

## Contact

For questions or collaboration opportunities, please reach out through the repository's issue tracker.

---

**Note**: This project is part of academic coursework in digital VLSI design and serves as a fundamental study of CMOS inverter characteristics.
