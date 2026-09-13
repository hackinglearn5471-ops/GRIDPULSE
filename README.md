# GRIDPULSE - Distribution Grid Simulation & Analysis Platform

<div align="center">

**Professional-Grade Electrical Distribution Network Analysis System**

*Built for Smart India Hackathon 2024*

[Features](#features) • [Technical Details](#technical-details) • [Getting Started](#getting-started) • [Documentation](#documentation)

</div>

---

## Overview

GRIDPULSE is a mature, government-grade distribution grid simulation platform designed for utility engineers, system operators, and government officials. It provides real-time power flow analysis, interactive network visualization, and comprehensive system monitoring capabilities.

### Key Capabilities

- **Real-Time Power Flow Analysis**: Advanced backward/forward sweep algorithm
- **Interactive Single Line Diagram**: Drag, zoom, and manipulate network components
- **Intelligent Battery Management**: BITS mode with safety thresholds
- **Comprehensive Monitoring**: 12 real-time KPIs with status indicators
- **Scenario Management**: 12 predefined operational scenarios
- **Fault Simulation**: 5 fault types with protection coordination
- **Data Export**: JSON export for reporting and analysis
- **Baseline Comparison**: Quantify system improvements

---

## Features

### 1. Professional Dashboard

**System Summary Bar** - 12 critical KPIs displayed in a compact, information-dense format:
- Total Load (MW/MVAr)
- Solar Generation (MW)
- Battery Power (kW)
- Grid Flow (MW)
- System Losses (kW/%)
- Voltage Levels (pu)
- Transformer Loading (%)
- Power Factor
- Active Faults
- System Frequency (Hz)
- Reverse Power Flow
- Component Count

Each KPI features color-coded status indicators for immediate identification of system conditions.

### 2. Interactive Single Line Diagram

Professional electrical schematic with full interactivity:
- **Drag & Drop**: Reposition buses, transformers, loads, and other components
- **Zoom & Pan**: Mouse wheel zoom (0.3x to 3x) and click-drag panning
- **Hover Tooltips**: Real-time data display for all components
- **Click Selection**: Visual highlighting with detailed inspector panel
- **Right-Click Menus**: Quick actions for component management
- **Toggle Controls**: Open/close breakers and switch capacitors
- **Dynamic Updates**: Add or delete components with automatic power flow recalculation

### 3. Equipment Data Tables

Comprehensive tabular data for all network components:
- **Buses**: Voltage, angle, power flow, status
- **Transformers**: Loading, rating, impedance, tap position
- **Lines**: Current, losses, voltage drop, thermal rating
- **Loads**: Active/reactive power, power factor, consumer count
- **Solar PV**: Output, capacity, irradiance, temperature
- **Batteries**: SOC, power, mode, capacity, BITS status
- **Capacitors**: Steps, reactive power, switching state

### 4. Intelligent Battery Management (BITS Mode)

Revolutionary discharge control system:
- **Safe Discharge Limit**: 20% SOC threshold
- **Critical Limit**: 10% SOC - discharge stops completely
- **Gradual Reduction**: Linear power reduction between 20% and 10%
- **Visual Indicators**: "BITS" (amber) and "STOP" (red) status labels
- **All Modes Supported**: Peak shaving, solar self-consumption, grid support, load following

### 5. Time-Series Simulation

24-hour dynamic simulation with realistic profiles:
- **Load Profiles**: Residential, commercial, and industrial patterns
- **Solar Irradiance**: Sunrise to sunset generation curves
- **Temperature Variations**: Affects solar efficiency and load
- **Battery SOC Tracking**: State of charge evolution
- **Playback Controls**: Play, pause, reset, step forward
- **Speed Control**: 0.5x, 1x, 2x, 5x, 10x simulation speed
- **Quick Navigation**: Jump to Dawn, Noon, Peak, Night

### 6. Scenario Management

12 predefined operational scenarios:
1. Normal Grid Operation
2. Peak Summer Load
3. High Solar Generation
4. Solar + Battery Dispatch
5. Transformer Overload
6. Feeder Fault
7. Voltage Drop
8. Reverse Power Flow
9. Capacitor Compensation
10. EV Charging Surge
11. Night Base Load
12. Morning Ramp Up

### 7. Fault Injection & Protection

5 fault types with realistic simulation:
- **SLG**: Single Line-to-Ground
- **LL**: Line-to-Line
- **DLG**: Double Line-to-Ground
- **LLL**: Three-Phase Fault
- **HIF**: High Impedance Fault

Features:
- Configurable fault resistance (0.01 - 10 Ω)
- Automatic fault current calculation
- Protection system response simulation
- Circuit breaker trip logic
- Auto-clear after duration
- System reconfiguration

### 8. AI-Powered Analysis

Intelligent insights based on actual simulation results:
- Voltage violation detection with recommendations
- Transformer overload warnings
- Line thermal limit alerts
- Power factor analysis
- Loss reduction suggestions
- Battery optimization recommendations
- Grid health assessment

### 9. Baseline Comparison

Quantify system improvements:
- Save current configuration as baseline
- Apply different scenarios or modifications
- Side-by-side comparison of key metrics
- Percentage change calculations
- Visual improvement indicators

### 10. Export Functionality

JSON export includes:
- Timestamp and configuration
- All simulation results
- Bus voltages and statuses
- Transformer loading data
- Line currents and losses
- Complete network state

---

## Technical Details

### Power Flow Engine

**Algorithm**: Backward/Forward Sweep Method

**Calculations**:
- Voltage drop: ΔV = I(R·cosφ + X·sinφ)·L
- Power losses: P_loss = 3·I²·R
- Current: I = S/(√3·V)
- Power factor: PF = P/S

**Performance**:
- Convergence in 1-2 iterations for radial networks
- Calculation time: <100ms for 9-bus system
- Real-time updates at 60 FPS

### Network Model

**Default Configuration**:
- 9 Buses (1 source, 3 distribution, 5 load/generation)
- 7 Lines (3 feeders, 4 LV lines)
- 4 Transformers (1 main, 3 distribution)
- 6 Loads (residential, commercial, industrial)
- 3 Solar PV systems
- 2 Battery Energy Storage Systems
- 2 Capacitor Banks
- 7 Circuit Breakers

**Voltage Levels**:
- Grid: 33 kV
- Distribution: 11 kV
- Low Voltage: 0.415 kV

### Technology Stack

**Frontend**:
- React 18.2 with TypeScript
- Vite 6.3 (build tool)
- Tailwind CSS 4.1 (styling)
- Recharts 2.10 (charts)

**Simulation Engine**:
- Custom TypeScript power flow solver
- Time-series profile generator
- Battery management system
- Fault analysis module

### Design Principles

**Professional Aesthetics**:
- Clean, minimal interface
- Information-dense layout
- Government-grade appearance
- Clear visual hierarchy
- Status-coded indicators

**Engineering Accuracy**:
- Real electrical calculations
- Physically meaningful results
- Industry-standard algorithms
- Validation and error handling

---

## Getting Started

### Prerequisites

- Node.js 18+ and npm
- Modern web browser (Chrome, Firefox, Safari, Edge)

### Installation

```bash
# Clone repository
git clone <repository-url>
cd gridpulse

# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build
```

### Usage

1. Open browser to `http://localhost:5173`
2. System loads with default 33kV/11kV/0.415kV network
3. Use simulation controls to advance time
4. Interact with circuit diagram (drag, zoom, click)
5. Select scenarios from right panel
6. Monitor KPIs in summary bar
7. Export results for reporting

---

## Documentation

### User Guides

- [MATURE_DESIGN.md](MATURE_DESIGN.md) - Professional design philosophy
- [BATTERY_DISCHARGE_CONTROL.md](BATTERY_DISCHARGE_CONTROL.md) - BITS mode documentation
- [INTERACTIVE_CIRCUIT.md](INTERACTIVE_CIRCUIT.md) - Circuit interaction guide
- [FEATURES.md](FEATURES.md) - Detailed feature showcase
- [SIH_PRESENTATION.md](SIH_PRESENTATION.md) - Presentation guide for judges

### Technical Documentation

- [README.md](README.md) - This file
- Code comments in source files
- TypeScript type definitions in `src/engine/types.ts`

---

## Use Cases

### For Utility Engineers
- Voltage profile analysis
- Loss reduction studies
- Capacity planning
- Renewable integration assessment

### For System Operators
- Real-time grid monitoring
- Fault analysis and response
- Scenario planning
- Battery optimization

### For Government Officials
- Grid health overview
- System performance metrics
- Compliance monitoring
- Report generation

### For Students & Researchers
- Power flow concepts
- Distribution system operation
- Renewable energy integration
- Protection coordination

---

## Validation & Accuracy

### Electrical Calculations

All displayed values are calculated from actual power flow solutions:
- ✅ Bus voltages from power flow
- ✅ Line currents from P, Q, V
- ✅ Transformer loading from actual power
- ✅ Losses from I²R calculations
- ✅ Power factor from P/S ratio
- ✅ Fault currents from network impedance

### Validation Checks

- Power balance verification
- Voltage range validation (0.8 - 1.2 pu)
- Transformer loading limits
- Line thermal limits
- Solver convergence detection
- Invalid parameter detection

---

## Future Enhancements

### Planned Features

**Backend Integration**:
- Python FastAPI backend
- pandapower integration for advanced power flow
- OpenDSS integration for time-series simulation
- WebSocket API for real-time updates

**Advanced Analysis**:
- Unbalanced three-phase analysis
- Harmonic studies
- Transient stability simulation
- Optimal power flow (OPF)
- State estimation

**Operational Features**:
- Multi-user support with authentication
- Audit logging
- Historical data storage
- Alarm system (email/SMS)
- PDF report generation

**Visualization**:
- Geographic map integration
- 3D network visualization
- Heat maps for voltage/loading
- Animation playback

---

## License

This project is developed for Smart India Hackathon 2024.

---

## Acknowledgments

GRIDPULSE is inspired by professional power system analysis tools:
- ETAP
- DIgSILENT PowerFactory
- PSS®E
- OpenDSS
- pandapower

Built with modern web technologies to provide an accessible, professional platform for distribution grid analysis.

---

<div align="center">

**GRIDPULSE v2.0**  
*Professional Distribution Grid Simulation & Analysis Platform*

**Smart India Hackathon 2024**

</div>
