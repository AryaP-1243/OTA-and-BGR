# Analog Circuit Design Projects - Cadence Virtuoso

This repository contains analog circuit designs simulated using Cadence Virtuoso Analog Design Environment. The projects include operational amplifier circuits with detailed schematics and simulation results.

## Projects Overview

### 1. OTA Closeloop OpAmp Circuit
A closed-loop operational transconductance amplifier configuration demonstrating AC analysis and transient response.

### 2. BGR Current Mirror Test Circuit
A Bandgap Reference (BGR) circuit with current mirror topology, including DC sweep analysis for temperature characterization.

## Repository Structure

```
.
├── README.md
├── closeloop_opamp/
│   ├── schematic_description.md
│   ├── simulation_results.md
│   └── screenshots/
│       ├── schematic.png
│       └── transient_response.png
├── BGR_current_mirror/
│   ├── schematic_description.md
│   ├── simulation_results.md
│   └── screenshots/
│       ├── schematic.png
│       ├── dc_sweep.png
│       └── dc_response.png
└── simulation_setup/
    └── simulation_parameters.md
```

## Circuit 1: OTA Closeloop OpAmp

### Key Features
- Operational transconductance amplifier in closed-loop configuration
- Multiple PMOS and NMOS transistor stages
- Bias voltage network for proper DC operating point
- Output voltage swing: ~190-230 mV
- Input reference voltage: ~800 mV

### Simulation Results
- **Transient Analysis**: Shows sinusoidal output response
- **Output Frequency**: Clean periodic waveform observed
- **Voltage Rails**: VDD supply with proper biasing

### Applications
- Low-power analog signal processing
- Sensor interface circuits
- Active filters and oscillators

## Circuit 2: BGR Current Mirror Test

### Key Features
- Bandgap reference topology
- Current mirror configuration for temperature-independent biasing
- Triangle/pyramid symbol indicating specialized bandgap core
- Multiple current sources and voltage reference nodes

### Simulation Results
- **DC Sweep Analysis**: Temperature sweep from -20°C to 125°C
- **Output Characteristics**:
  - `/Vbe`: Linear increase (44-72 mV range)
  - `/Vref`: Stable reference (~1.15V with minimal drift)
  - Demonstrates excellent temperature stability

### Applications
- Voltage reference generation
- Temperature-independent biasing
- ADC/DAC reference circuits
- Power management ICs

## Tools Used

- **Design Tool**: Cadence Virtuoso Analog Design Environment L
- **Simulation**: Virtuoso Visualization & Analysis XL (Spectre simulator)
- **Operating System**: Linux (visible in screenshots)
- **PDK**: Standard CMOS process (specific details in schematics)

## Simulation Details

### OTA Closeloop OpAmp
- **Analysis Type**: Transient Response
- **Time Window**: 0-10 ms
- **Signals Monitored**: 
  - `/vout` (Output voltage)
  - `/VIN1` (Input reference)

### BGR Current Mirror
- **Analysis Type**: DC Temperature Sweep
- **Temperature Range**: -20°C to 125°C
- **Signals Monitored**:
  - `/Vbe` (Base-emitter voltage)
  - `/Vref` (Reference voltage output)

## Getting Started

### Prerequisites
- Cadence Virtuoso (version 6.1.8 or later)
- Valid PDK installation
- Spectre simulator license

### Running Simulations

1. Open Cadence Virtuoso
2. Load the respective schematic from `closeloop_opamp` or `BGR_current_mirror` directory
3. Configure simulation parameters in ADE L
4. Run the specified analysis (Transient or DC)
5. View results in Visualization & Analysis XL

## Performance Metrics

### OTA Closeloop OpAmp
- Supply voltage: VDD (value specified in schematic)
- Output amplitude: ~20 mV peak-to-peak
- Input bias: ~800 mV
- Operating frequency: Visible in transient response

### BGR Current Mirror
- Reference voltage: ~1.15V
- Temperature coefficient: Minimal drift over full range
- Vbe variation: 28 mV over temperature range
- Operating range: -20°C to 125°C

## Future Enhancements

- Corner analysis (FF, SS, TT, FS, SF)
- Monte Carlo simulation for process variation
- Noise analysis
- Power consumption characterization
- Layout design and post-layout simulation

## Author

Arya P

## License

This project is intended for educational and research purposes.

## Acknowledgments

- Cadence Design Systems for Virtuoso tools
- Circuit design principles from standard analog IC design references

## Contact

For questions or collaboration, please open an issue in this repository.
