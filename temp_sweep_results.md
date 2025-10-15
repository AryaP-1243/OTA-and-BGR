<img width="1366" height="768" alt="Screenshot from 2025-10-09 16-01-40" src="https://github.com/user-attachments/assets/4c12089d-8906-45aa-8290-4467069e9f09" />

# Image 2: Virtuoso Visualization & Analysis XL - Temperature Sweep Results

## Window Overview

This image displays the **Virtuoso® (R) Visualization & Analysis XL** tool showing simulation results from a DC temperature sweep of the BGR current mirror circuit. The timestamp shows **Thursday 4:01 PM**, one minute after the schematic view was captured.

## Application Header

- **Application**: Virtuoso (R) Visualization & Analysis XL
- **Purpose**: Post-processing and visualization of Spectre simulation results
- **Company**: Cadence (branding visible in top-right)
- **Window Management**: Standard minimize, maximize, close buttons

## Menu Bar

Complete menu structure from left to right:
- **File**: Open, save, export plot data
- **Edit**: Copy, paste, modify plot properties
- **View**: Display options, layout management
- **Graph**: Graph type selection and properties
- **Axis**: Axis scaling, labels, and formatting
- **Trace**: Signal selection and trace properties
- **Marker**: Measurement cursors and markers
- **Measurements**: Automated measurement tools
- **Tools**: Calculation, expression evaluation
- **Window**: Window arrangement and management
- **Browser**: Signal browser and hierarchy
- **Help**: Documentation and support

## Toolbar (Icon Bar)

### Left Section - File Operations
- New plot window icon
- Open file icon  
- Save icon
- Print icon
- Export icon
- Clipboard icons

### Center Section - View Controls
- Zoom in/out icons
- Pan tool
- Fit to window
- Zoom to rectangle
- **Subwindow**: Dropdown showing "3" - indicates 3 plot subwindows active
- Grid toggle
- **Data Point**: Marker controls

### Right Section - Display Options
- **family**: Dropdown menu (likely for plot families/groups)
- Color scheme icons
- Legend controls
- **Classic**: Dropdown showing display style
- Property icons

## Design Context Tab

Located below the toolbar:
- **Tab**: "new_OTA BGR_current_mirror_TEST..." 
- **Close button**: X to close this dataset
- Shows the loaded simulation results from the schematic designed in Image 1

## Main Display Area - Three Subwindows

The visualization is divided into three vertically stacked plot windows, currently showing 2 visible plots.

---

## Subwindow 1 (Top Left Plot)

### Plot Header
- **Title Bar**: "(v('C'/Vbe' ?result 'dc')) - v('C'/VBEn' ?result 'dc'))"
- **Expression**: Shows the difference between two Vbe voltages
- **Timestamp**: "Thu Oct 9 16:01:07"
- **Subwindow Number**: "2" (shown in top-right corner)

### Plot Characteristics

#### X-Axis
- **Label**: "temp (C)" - Temperature in degrees Celsius
- **Range**: 0.0 to approximately 120°C
- **Scale**: Linear scaling
- **Grid**: Gray horizontal and vertical grid lines
- **Increments**: Major divisions at 25°C intervals (0, 25.0, 50.0, 75.0, 100.0)

#### Y-Axis  
- **Label**: "V (mV)" - Voltage in millivolts
- **Range**: 44.0 mV to 72.0 mV
- **Scale**: Linear scaling
- **Increments**: Major divisions every 4 mV (44.0, 48.0, 52.0, 56.0, 60.0, 64.0, 68.0, 72.0)

#### Trace Display
- **Color**: Red/orange line
- **Style**: Solid line
- **Data Points**: Visible as small dots along the trace
- **Behavior**: **Positive linear slope** - voltage increases steadily with temperature
- **Linearity**: Extremely linear relationship, nearly perfect straight line
- **Starting Point**: ~44 mV at 0°C
- **Ending Point**: ~72 mV at 120°C
- **Slope**: Approximately (72-44)/(120-0) = 0.233 mV/°C
- **Interpretation**: This is the **PTAT (Proportional To Absolute Temperature) voltage component** - the ΔVbe between two BJTs operating at different current densities

#### Signal Legend (Left Side)
- **Name Panel**: Shows signal name (partially visible)
- **Filter Icon**: Funnel-shaped icon for trace filtering
- **Visibility Controls**: Eye icons to show/hide traces
- **Trace Label**: "(v('C'/Vbe'...'ult 'v)" in red box indicating active trace

### Plot Interpretation
This graph demonstrates the **PTAT voltage generation** mechanism in the BGR circuit. The perfectly linear increase of ΔVbe with temperature provides the positive temperature coefficient component that will be combined with the negative temperature coefficient (CTAT) Vbe to create a temperature-stable reference.

---

## Subwindow 3 (Top Right Plot)

### Plot Header
- **Title Bar**: "DC Response"
- **Timestamp**: "Thu Oct 9 16:01:07" (same simulation run)
- **Subwindow Number**: "3" (shown in top-right corner)

### Plot Characteristics

#### X-Axis
- **Label**: "temp (C)" - Temperature in degrees Celsius  
- **Range**: 0.0 to approximately 125°C
- **Scale**: Linear scaling
- **Grid**: Fine gray grid for precise reading
- **Increments**: Major divisions at 25°C intervals

#### Y-Axis
- **Label**: "V (V)" - Voltage in volts
- **Range**: 0.6 V to 1.2 V
- **Scale**: Linear scaling
- **Increments**: Major divisions every 0.05 V (0.6, 0.65, 0.7, 0.75, 0.8, 0.85, 0.9, 0.95, 1.0, 1.05, 1.1, 1.15, 1.2)
- **Precision**: High resolution scale for observing small variations

#### Trace 1 - Green Line (/Vref)
- **Color**: Bright green
- **Style**: Solid line
- **Label**: "/Vref" (Reference voltage output)
- **Behavior**: **Nearly flat/horizontal** across entire temperature range
- **Voltage Level**: Approximately 1.15 V consistently
- **Variation**: Extremely small - appears to vary by less than ±10 mV across full range
- **Starting Point**: ~1.16 V at 0°C
- **Ending Point**: ~1.14 V at 125°C
- **Curvature**: Very slight downward bow (parabolic)
- **Peak**: Maximum voltage appears around 40-60°C region
- **Interpretation**: This is the **temperature-compensated bandgap reference output** showing excellent stability

#### Trace 2 - Red Line (/Vbe)
- **Color**: Red/orange
- **Style**: Solid line  
- **Label**: "/Vbe" (Base-emitter voltage of BJT)
- **Behavior**: **Strong negative linear slope**
- **Starting Point**: ~0.82 V at 0°C
- **Ending Point**: ~0.62 V at 125°C
- **Slope**: Approximately -(0.82-0.62)/(125-0) = -1.6 mV/°C
- **Linearity**: Highly linear decrease
- **Interpretation**: This is the **CTAT (Complementary To Absolute Temperature) component** showing the typical negative temperature coefficient of a BJT base-emitter junction

#### Signal Legend (Left Side)
- **Name Column**: Shows "Name" and "Vis" headers
- **Visibility Controls**: 
  - Eye icon next to "/Vbe" (red box) - trace visible
  - Eye icon next to "/Vref" (green box) - trace visible
- **Filter Icon**: Funnel at top for signal filtering
- **Purpose**: Allows toggling trace visibility and identification

### Plot Interpretation
This is the **key performance plot** showing:

1. **Vref (green)**: The successful temperature compensation - combining PTAT and CTAT components results in a nearly constant 1.15V reference
2. **Vbe (red)**: The CTAT component showing why compensation is needed - without correction, this voltage would drift by ~200 mV over temperature
3. **Temperature Coefficient**: The Vref line's flatness indicates successful bandgap operation with very low tempco

---

## Subwindow 2 (Not Fully Visible)

Based on the window indicators, there's a third plot window that would appear if scrolled, likely containing additional analysis data.

---

## Bottom Status Bar

### Left Section
- **Mouse Indicator**: "mouseL" - Left mouse button mode
- **Cell Reference**: "8(21) | Trace: /Vref, Context: /home/CHIPS/simulation/BGR_current_mirror_TEST/spectre/schematic/psf, Dataset: dc-dc"
  - **8(21)**: Signal index and total count
  - **Trace**: Currently selected signal is /Vref
  - **Context**: File path to simulation results
  - **Dataset**: dc-dc indicates DC analysis results

### Right Section  
- **Coordinate Display**: "R:" (likely ready for marker positioning)
- **Status Indicator**: "M:" (mouse/marker mode)

---

## Application Taskbar (Bottom of Screen)

Same applications visible as in Image 1:
1. File Manager
2. pratap (text editor)
3. capstone
4. CHIPS@cadence... (terminal)
5. Virtuoso® 6.1.8 (main application)
6. Virtuoso® Analog (schematic editor)
7. [ADE L (2) - new... (analog environment)
8. **Virtuoso (R) Vis... (CURRENTLY ACTIVE - highlighted)**
9. /home/CHIPS... (another window)

The Virtuoso Visualization window is highlighted, indicating it's the active foreground application.

---

## Data Analysis Summary

### Temperature Sweep Parameters
- **Start Temperature**: 0°C (or possibly -20°C based on axis)
- **Stop Temperature**: 125°C
- **Analysis Type**: DC sweep with temperature as the parameter
- **Simulation Timestamp**: October 9, 16:01:07

### Key Results

#### PTAT Voltage (Subwindow 1)
- **ΔVbe range**: 44 mV to 72 mV
- **Temperature coefficient**: +0.233 mV/°C (positive)
- **Linearity**: Excellent linear fit
- **Purpose**: Provides positive tempco to cancel Vbe's negative tempco

#### Reference Voltage Performance (Subwindow 3 - Green)
- **Nominal Vref**: ~1.15 V
- **Variation**: < 20 mV peak-to-peak across 125°C range
- **Temperature coefficient**: Estimated < 50 ppm/°C
- **Curvature**: Slight parabolic behavior (typical for BGRs)
- **Performance**: Excellent temperature stability

#### Vbe Behavior (Subwindow 3 - Red)
- **Nominal Vbe (27°C)**: ~0.75 V
- **Temperature coefficient**: -1.6 mV/°C (strongly negative)
- **Total variation**: ~200 mV across temperature range
- **Linearity**: Nearly perfect linear decrease

### Performance Metrics Visible

1. **Temperature Range**: 0-125°C operational range
2. **Output Stability**: Vref maintains 1.15V ± 0.5% across full range
3. **Compensation Success**: PTAT voltage successfully cancels Vbe drift
4. **Linear PTAT**: Clean PTAT generation without discontinuities
5. **No Startup Issues**: All voltages stable and well-defined

---

## Visualization Features

### Graph Quality
- **Resolution**: High-quality anti-aliased lines
- **Grid**: Professional fine grid for accurate reading
- **Colors**: High contrast - red, green, black background
- **Legend**: Clear signal identification
- **Axes**: Well-labeled with units

### User Interface Elements
- **Multiple Subwindows**: Allows simultaneous viewing of related signals
- **Independent Axes**: Each plot optimized for its signal range
- **Timestamp**: Maintains data provenance
- **Signal Browser**: Left panel for signal selection
- **Toolbar**: Comprehensive measurement and analysis tools

### Export Capabilities
Based on toolbar icons:
- Print plots
- Export to image formats
- Save raw data
- Copy to clipboard
- Generate reports

---

## Comparison to Expected BGR Behavior

### Theoretical vs. Actual

**Expected BGR Characteristics**:
- Vref ≈ 1.2V (silicon bandgap)
- TC < 50 ppm/°C
- PTAT voltage ∝ Temperature
- Vbe with -2 mV/°C tempco

**Observed Results**:
- ✓ Vref = 1.15V (within expected range)
- ✓ Minimal temperature variation visible
- ✓ Linear PTAT response
- ✓ Vbe shows expected negative coefficient

### Design Success Indicators

1. **Flat Vref curve**: Indicates proper PTAT/CTAT ratio
2. **No discontinuities**: No startup or stability issues
3. **Full range operation**: Works across entire temperature span
4. **Predictable behavior**: Linear PTAT and Vbe responses
5. **Low noise**: Smooth traces without artifacts

---

## Context in Design Flow

This visualization represents the **post-simulation analysis phase**:

1. **Previous**: Schematic design (Image 1)
2. **Current**: Temperature characterization analysis (Image 2)
3. **Next**: Will show detailed DC response plot (Image 3)

The results validate that the BGR circuit designed in Image 1 successfully achieves temperature-stable voltage reference generation, meeting the primary design objective.

## File and Data Information

### Simulation Results Location
- **Path**: /home/CHIPS/simulation/BGR_current_mirror_TEST/spectre/schematic/psf
- **Format**: PSF (Parametric Simulation Format) - Cadence's binary results format
- **Analysis**: dc-dc (DC operating point with parameter sweep)
- **Dataset**: Contains voltage, current, and operating point data for all circuit nodes

### Signal Naming Convention
- **Absolute paths**: "/Vref", "/Vbe" indicate top-level circuit nodes
- **Hierarchical**: "v('C'/Vbe'...)" shows subcircuit hierarchy
- **Expression evaluation**: Mathematical operations between signals visible in plot titles

This comprehensive visualization confirms the successful implementation and characterization of the temperature-compensated bandgap voltage reference circuit.
