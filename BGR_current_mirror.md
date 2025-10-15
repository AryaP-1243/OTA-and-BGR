<img width="1366" height="768" alt="Screenshot from 2025-10-09 16-00-38" src="https://github.com/user-attachments/assets/bf2fbe96-a32c-4e3d-a832-fcf134e2cca4" />

# BGR Current Mirror Test Circuit - Schematic Description

## Circuit Overview

This schematic implements a Bandgap Reference (BGR) circuit with current mirror topology designed for temperature-independent voltage reference generation. The circuit uses BJT devices in a bandgap configuration combined with MOSFET current mirrors for precise biasing.

## Schematic File

**File**: `new_OTA BGR_current_mirror_TEST_schematic`  
**Library**: new_OTA  
**Cell**: BGR_current_mirror_TEST  
**View**: schematic  
**Temperature**: 27°C (default simulation temperature)

## Circuit Topology

### Bandgap Core (Triangle/Pyramid Symbol)
- **Central Element**: Large triangular/pyramid structure (specialized bandgap core)
- **Pins**: Multiple connection points including:
  - `vdd` (top connections)
  - `vb` (bias voltage)
  - `gnd` (ground connections)
  - `vss` (substrate/negative supply)
  - `fref` (reference node)
  - `net1` (internal node)

### Input Section (Left Side)

#### Voltage Sources and Input Stage
- **Is**: Current source on left edge
- **va**: Voltage source/node
- **ib**: Current source connection
- **Transistors**: Multiple devices in diode-connected configuration

#### PMOS Current Sources (Top Left)
- **pmos_1B instances**: M1_Vdd, tuk
- **Connections**: 
  - vb → vdd connections
  - Provides bias current to bandgap core

### Current Mirror Network (Top Section)

#### Primary Current Mirrors
- **pmos_1B M3_Vdd**: Main mirror transistor
- **pmos_1B M2_Vdd**: Reference branch transistor
- **pmos_1B M1**: Additional mirroring stage
- **Nodes**: vb, vdd, net1, net3

#### Mirror Configuration
```
VDD → [M3_Vdd] → [M2_Vdd] → [M1] → Bandgap Core
      |         |         |
      vb        vb        vb (gate connections for mirroring)
```

### Right Side Current Mirrors

#### PMOS Mirrors
- **pmos_1B M6_Vdd**: Output stage mirror
- **pmos_1B M4_Vdd**: Intermediate mirror
- **pmos_1B M1_Vref**: Reference voltage generation stage
- **Critical Nodes**:
  - Vref: Reference voltage output node
  - net4: Internal connection
  - Vver_Rl: Verification/load node

#### Additional Components
- **M5**: Connected to Vref output
- **Rl, frf, Vver_R1, Ri**: Load and verification elements

### Output Stage (Bottom Right)

#### Current Sinking Network
- **nmos_1B net4**: Bottom current sink
- **nmos_1B net3**: Intermediate sink
- **nmos_1B vss**: Ground connection transistor
- **Voltage References**: 
  - Visa, Vsa: Internal voltage nodes
  - Vter_Ol: Output verification node

#### Bottom Current Sources
- **vss, vga, vaa**: Multiple ground/substrate connections
- **Vbea_11, VBen_1**: BJT bias voltage nodes

### Reference Voltage Nodes

Key voltage monitoring points identified:
- **Vref**: Primary reference voltage output (~1.15V from simulation)
- **Visa**: Internal bias voltage
- **Vsa**: Substrate/source voltage
- **Vaa**: Additional reference point
- **Visa_Ol, Oca_Ol**: Output characterization nodes

## Circuit Operating Principle

### Bandgap Reference Theory
1. **CTAT Component**: Vbe of BJT has negative temperature coefficient (~-2 mV/°C)
2. **PTAT Component**: ΔVbe across BJTs with different current densities has positive TC
3. **Combination**: Weighted sum of CTAT and PTAT yields temperature-independent reference

### Current Mirror Function
- **Replication**: Mirrors bias current to different circuit sections
- **Matching**: Careful layout ensures matched current densities
- **Stability**: Provides stable operating point across temperature and process

### Temperature Compensation
- BJT bandgap core generates ~1.2V reference (bandgap of silicon)
- Current mirrors ensure consistent biasing
- Result: Vref with minimal temperature coefficient

## Key Design Parameters

### Voltage Nodes (from schematic)
- **VDD**: Positive supply rail
- **Vref**: ~1.15V reference output
- **Vbias (vb)**: Current mirror bias voltage
- **VSS**: Ground/negative rail

### Device Sizing
- Multiple PMOS devices for current mirroring
- NMOS devices for current sinking
- BJT devices in bandgap core (internal to pyramid symbol)
- Resistor elements for PTAT generation

## Annotated Operating Points

Visible in red text on schematic:
- Various node voltages at DC operating point
- Current values through key branches
- Small-signal parameters (gm values)
- Temperature-dependent characteristics

## Design Considerations

### Matching Requirements
1. **Current Mirrors**: Precise matching for accurate current replication
2. **BJT Area Ratios**: Specific ratios for PTAT voltage generation
3. **Resistor Ratios**: Set temperature coefficient cancellation

### Stability Considerations
1. **Start-up Circuit**: Ensures circuit doesn't settle in zero-current state (not explicitly shown but typically included)
2. **Phase Margin**: Internal compensation for stability
3. **Load Regulation**: Output impedance considerations

### Noise Performance
1. **Low-frequency Noise**: From current sources and resistors
2. **Thermal Noise**: From resistors in PTAT generation
3. **Flicker Noise**: From MOSFETs in mirrors

## Component Inventory

### PMOS Transistors
- M1, M1_Vref, M2_Vdd, M3_Vdd, M4_Vdd, M5, M6_Vdd, tuk
- Function: Current sources and mirrors

### NMOS Transistors  
- net3, net4, vss (multiple instances)
- Function: Current sinks and level shifters

### Bandgap Core
- Central pyramid symbol (integrated BGR cell)
- Contains: BJTs, resistors, internal compensation

### Voltage Sources (for testing)
- Is, ib, va: Bias and test sources
- VDD supply

## Simulation Test Points

### Critical Nodes to Monitor
1. **Vref**: Primary output - should be ~1.15-1.2V
2. **Vbe nodes**: Monitor CTAT behavior
3. **ΔVbe**: PTAT voltage generation
4. **Current mirror branches**: Verify matching
5. **Supply current**: Total power consumption

### Expected Behavior
- Vref should remain constant (~1.15V) across temperature
- Low temperature coefficient (<50 ppm/°C target)
- Good PSRR (Power Supply Rejection Ratio)
- Fast startup time

## Connectivity Summary

```
Input Power:
VDD → PMOS mirrors → Bandgap Core → NMOS sinks → VSS/GND

Reference Path:
Bandgap Core → Current Mirror (M1_Vref) → Vref output

Bias Distribution:
vb (bias node) → All PMOS mirror gates → Consistent biasing
```

## Layout Considerations (for future work)

1. **Symmetry**: Mirror devices must be laid out symmetrically
2. **Common Centroid**: For best matching
3. **Guard Rings**: Isolate from substrate noise
4. **Thermal Matching**: Keep matched devices at same temperature
5. **Metal Routing**: Low-resistance paths for current mirrors

## Notes

- Circuit optimized for temperature stability (-20°C to 125°C range)
- Uses standard CMOS process with BJT option
- Red annotations show simulated DC operating points
- Triangle symbol is likely a hierarchical cell containing complete BGR core
- All grounds (gnd, vss, vaa) should be connected to same net in layout
