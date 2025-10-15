<img width="1366" height="768" alt="Screenshot from 2025-10-09 16-00-38" src="https://github.com/user-attachments/assets/bf2fbe96-a32c-4e3d-a832-fcf134e2cca4" />

# Image 1: Cadence Virtuoso Schematic Editor - BGR Current Mirror Circuit

## Window Overview

This image shows the **Cadence Virtuoso Analog Design Environment** schematic editor displaying a bandgap reference (BGR) circuit with current mirror topology. 

## Application Header

- **Application**: Virtuoso® Analog Design Environment L
- **Current Design**: `new_OTA BGR_current_mirror_TEST schematic`
- **Window Title**: Shows "Editing: new_OTA BGR_current_mirror_TEST schematic"
- **Company**: Cadence (shown in top-right branding)

## Menu Bar and Toolbars

### Main Menu Bar
From left to right:
- **Launch**: Access to design hierarchy and libraries
- **File**: File operations (save, open, close)
- **Edit**: Editing operations (copy, paste, delete)
- **View**: View controls and zoom options
- **Create**: Component placement and wire drawing
- **Check**: Design rule checks and verification
- **Options**: Preferences and settings
- **Window**: Window management
- **PVS**: Physical verification system
- **Help**: Documentation and support

### Icon Toolbar (First Row)
Contains standard schematic editing tools including:
- New/Open/Save file icons
- Undo/Redo arrows
- Component browser
- Wire/Pin tools
- Text and label tools
- Zoom and pan controls
- Selection tools

### Design-Specific Toolbar (Second Row)
- **Technology Library**: Shows "ADE L" dropdown (Analog Design Environment Library)
- **Simulation Controls**: Green play button, red stop button for simulations
- **Search Bar**: Located on the right with "Search" text field
- **Sim Time**: Indicator showing current simulation time setting

## Navigator Panel (Left Side)

### Schematic Tab
Currently selected tab showing:
- **Cell Name**: BGR_current_mirror_TEST
- **Design Hierarchy**: Shows schematic view is active

### Objects Section
Organized component list with counts:
- **All**: Expandable category
- **Instances**: 13 component instances
- **Nets**: 10 net connections
- **Pins**: 1 pin definition
- **Nets and Pins**: Additional subcategory

### Groups Section
Below Objects, used for organizing design elements

### View Controls
- Minimize (-) button
- Maximize (+) button
- Close button at bottom

## Main Schematic Canvas

### Canvas Properties
- **Background**: Black with white grid dots for alignment
- **Grid**: Fine dot grid pattern for precise component placement
- **Color Scheme**: 
  - Cyan/blue for wires and connections
  - Red text for annotations and DC operating point values
  - Green boxes for component boundaries
  - Yellow/orange labels for node names

### Circuit Layout Overview

The schematic is divided into several functional sections:

#### **Left Section - Input Stage**
Contains:
- Current sources labeled "Is" and "ib"
- Voltage source "va"
- PMOS transistors including "pmos_1B tuk" and "M1_Vdd"
- Input biasing circuitry with connections to "vb" (bias voltage)

#### **Top Center - Current Mirror Array**
Three PMOS current mirror transistors arranged horizontally:
- **pmos_1B M3_Vdd**: Leftmost mirror
- **pmos_1B M2_Vdd**: Center mirror  
- **pmos_1B M1**: Right mirror
- All connected to **vdd** (top rail, positive supply)
- Gates tied together at **vb** node for current mirroring
- Outputs feed into nodes labeled "vb", "net1", "net3"

#### **Center - Bandgap Core**
Large triangular/pyramid structure (appears as a specialized symbol):
- **Shape**: Outlined triangle with internal structure
- **Connections**: Multiple pins around the periphery
- **Labels visible**: "vdd", "vb", "gnd", "fref", "net1"
- **Color**: Outlined in cyan with node labels
- **Purpose**: This is likely a hierarchical subcell containing the complete bandgap reference core with BJT transistors and resistors

#### **Right Section - Output Stage**
Upper right contains:
- **pmos_1B M6_Vdd**: Output current mirror
- **pmos_1B M4_Vdd**: Intermediate stage
- **pmos_1B M1_Vref**: Reference voltage generation
- **Node "Vref"**: Primary reference voltage output (highlighted in cyan box)
- Additional components labeled "M5", "Rl", "frf", "Vver_Rl", "Ri"

#### **Bottom Right - Current Sink Network**
NMOS transistor array:
- **nmos_1B net4**: Connected to intermediate node
- **nmos_1B net3**: Current sinking device
- **nmos_1B vss**: Ground connection transistors
- Multiple ground connections: "vss", "vga", "vaa"
- Bias nodes: "Vbea_11", "VBen_1"

### Critical Voltage Nodes Visible

Red and yellow labels identify key measurement points:
- **vdd**: Power supply node (top of circuit)
- **vb**: Bias voltage (distributed to all PMOS gates)
- **Vref**: Reference voltage output (right side, in cyan box)
- **net1, net3, net4**: Internal circuit nodes
- **vss, vaa, vga**: Ground/substrate connections
- **Visa**, **Vsa**: Internal voltage references
- **Vver_Rl**, **Vter_Ol**: Verification/test nodes

### DC Operating Point Annotations

Red text scattered throughout shows simulated values:
- Small numerical values indicating voltages at various nodes
- These appear after running DC operating point analysis
- Typical values visible include fractions of volts
- Some annotations show "v1", "v2" indicating voltage probe locations

### Wire Connections

- **Cyan lines**: Primary signal and power connections
- **Connection dots**: Red circles at wire junctions
- **Wire labels**: Yellow text boxes showing net names
- **Bus connections**: Wider or multiple parallel lines for multi-bit signals (if present)

## Property Editor Panel (Bottom Left)

### Tabs
- **Schemat**: Schema/netlist view (currently selected, shown in red)
- **Attributes**: Component attribute editor

### Current Properties Display
Showing cell properties:
- **Library**: new_OTA
- **Cell**: BGR_current_mirror_TEST  
- **View**: schematic
- **Mode**: Editable (with checkbox)
- **Last Saved**: Thu Oct 9 (partial date visible)
- **Locked By**: CHIPS@ca... (username truncated)
- **Units**: inch (measurement units)

### Window Controls
Standard minimize, maximize, close buttons with help (?) icon

## Bottom Status Bar

### Left Side
- **Mouse Mode**: "mouseL schSingleSelectPt()" 
  - Indicates left mouse button is in single-select mode
- **Cell Count**: "1(13)" - showing 1 cell with 13 instances

### Center Section  
- **Zoom Level**: "M: schZoomIn(1.0 0.9)"
  - Current zoom multiplier and position coordinates
- **Command**: Cmd: Sel: 0
  - Shows no items currently selected

### Right Side
- **Status**: "Status: Ready" - Editor ready for input
- **Temperature**: T=27 C - Simulation temperature setting
- **Simulator**: "Simulator: spectre" - Using Spectre simulator
- **Analysis**: "State: unr" - Current simulation state (unrun)

## System Taskbar (Bottom)

Application icons visible:
1. **File Manager** icon (folder symbol)
2. **pratap**: Text editor window
3. **capstone**: Another application window
4. **CHIPS@cadence...**: Terminal or command window
5. **Virtuoso® 6.1.8-...**: Main Virtuoso window (current active)
6. **Virtuoso® Analo...**: This schematic window (highlighted)
7. **[ADE L (2) - new...**: Analysis environment window
8. **Virtuoso (R) Vis...**: Visualization window (for waveforms)
9. Empty workspace slot

## Design Information

### Cell Details
- **Library**: new_OTA (custom design library)
- **Cell Name**: BGR_current_mirror_TEST
- **View Type**: schematic (circuit diagram view)
- **Design Intent**: Temperature-stable voltage reference circuit
- **Topology**: Current mirror-based bandgap reference

### Component Types Identified
1. **PMOS Transistors**: pmos_1B instances (8 visible)
2. **NMOS Transistors**: nmos_1B instances (3+ visible)
3. **Voltage Sources**: For testing and biasing
4. **Current Sources**: Input biasing
5. **Hierarchical Cell**: Central bandgap core symbol
6. **Resistors**: Part of internal BGR core
7. **Wiring**: Signal, power, and ground interconnections

## Visual Design Elements

### Color Coding
- **Black**: Background canvas
- **White**: Grid dots
- **Cyan/Blue**: Wires, component outlines, active nets
- **Red**: DC operating point values, connection dots
- **Yellow**: Net labels, important node names
- **Green**: Component boundaries, selection highlights
- **Gray**: Inactive elements

### Typography
- **Component Labels**: Clear sans-serif font
- **Node Names**: Smaller text in yellow
- **DC Values**: Red italic text for measurements
- **Menu Text**: Standard system font

### Spatial Organization
- **Top**: Power supply (VDD) connections
- **Center**: Signal processing (bandgap core)
- **Bottom**: Ground/sink connections (VSS)
- **Left**: Input and bias generation
- **Right**: Output and reference voltage

## Circuit Functionality Summary

This schematic implements a **bandgap voltage reference** that generates a stable ~1.15-1.2V output (Vref) independent of temperature variations. The circuit uses:

1. **Current Mirrors**: PMOS transistors replicate bias currents accurately
2. **Bandgap Core**: Central cell combines PTAT and CTAT voltages
3. **Current Sinks**: NMOS devices provide return paths to ground
4. **Bias Network**: Distributes stable bias voltage to all mirrors

The design targets operation from -20°C to 125°C with minimal voltage drift, making it suitable for precision analog applications requiring stable voltage references.

## Editing State

- **Mode**: Active editing (not read-only)
- **Saved**: Last save on October 9th
- **User**: CHIPS@cadence (locked by current user)
- **Grid**: Enabled for alignment
- **Snap**: Component snap-to-grid active

## Simulation Readiness

The circuit is prepared for simulation with:
- DC operating point annotations visible (indicating previous simulation)
- Voltage sources configured
- Node names assigned for probing
- Simulator set to Spectre
- Ready to run temperature sweep analysis

This schematic serves as the design entry point for the circuit that will be simulated in the subsequent images showing temperature characterization results.
