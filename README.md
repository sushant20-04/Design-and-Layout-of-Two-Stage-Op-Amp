# Design and Layout of a Two-Stage Op-Amp

## EE653 – Analog IC Design Lab

This repository contains the schematic design, transistor sizing, layout, physical verification, and performance analysis of a **Miller-compensated two-stage operational amplifier** designed using **Cadence Virtuoso** in **SCL 180 nm CMOS technology**.

The project covers the complete analog IC design flow, including schematic design, transistor sizing, compensation, physical layout, DRC/LVS verification, parasitic extraction, and pre-layout/post-layout performance analysis.

Detailed schematics, layout views, simulation plots, and verification results are provided in the attached project report.

---

## 📌 Design Specifications

| Parameter | Specification |
| --- | --- |
| Technology | SCL 180 nm CMOS |
| Supply Voltage | 1.8 V |
| Supply Sources | Single VDD source |
| Minimum Overdrive Voltage | \(V\_{OV}\ > 150\,mV\) |
| EDA Tool | Cadence Virtuoso |
| PDK | SCL 180 nm |

---

# 1. Two-Stage Op-Amp Design

The operational amplifier consists of a **5-transistor OTA as the first stage**, followed by a **common-source second stage**. Miller compensation is implemented to improve frequency stability, along with a series nulling resistor to control the compensation zero.

### Architecture

- **First Stage:** 5-T OTA
- **Second Stage:** Common-source amplifier
- **Compensation:** Miller compensation
- **Nulling:** Series nulling resistor
- **Technology:** SCL 180 nm CMOS
- **Supply Voltage:** 1.8 V

The complete schematic and circuit implementation are documented in the attached project report.

---

## 1.1 Transistor Sizing

The transistor dimensions and operating currents were selected to satisfy the required biasing and performance constraints while maintaining the specified minimum overdrive voltage.

| Device | Type | W (µm) | L (µm) | \(I\_D\) (µA) |
| --- | --- | ---: | ---: | ---: |
| Input Pair | NMOS | 16 | 1 | 10 |
| P Mirror | PMOS | 8 | 1 | 10 |
| Tail Transistor | NMOS | 16 | 1 | 20 |
| Bias Transistor | NMOS | 8 | 1 | 10 |
| M7 (CS Stage) | NMOS | 32 | 1 | 40 |
| M8 (CS Stage) | PMOS | 34 | 1 | 40 |

---

## 1.2 Passive Components

The compensation and load components were selected to achieve the desired frequency response and stability characteristics.

| Component | Description | Value |
| --- | --- | ---: |
| \(C_C\) | Miller Compensation Capacitor | 464 fF |
| \(R_Z\) | Nulling Resistor | 7.7 kΩ |
| \(C_L\) | Load Capacitor | 1 pF |

---

# 2. Op-Amp Layout

The two-stage op-amp layout was designed in **Cadence Virtuoso** following the design rules of the **SCL 180 nm CMOS technology**.

Layout techniques such as **common-centroid placement** were used for the differential input pair and current mirror loads to reduce mismatch caused by process gradients.

The layout was designed with careful attention to:

- Device matching
- Symmetry
- Routing parasitics
- Power and signal routing
- Device placement
- Design-rule compliance
- Area optimization

Detailed layout views, including the complete op-amp layout, current mirrors, differential pair, common-source stage, and compensation network, are provided in the attached project report.

---

# 3. Physical Verification

The completed layout was physically verified using:

- **DRC** – Design Rule Check
- **LVS** – Layout Versus Schematic
- **PEX** – Parasitic Extraction

### DRC

The layout was checked against the SCL 180 nm design rules to ensure that the physical implementation satisfies the required geometric and connectivity constraints.

### LVS

Layout-versus-schematic verification was performed to confirm that the extracted circuit connectivity matches the original schematic.

### PEX

Parasitic extraction was performed to account for layout-dependent parasitic capacitances and resistances. The extracted netlist was subsequently used for post-layout simulations.

Detailed DRC, LVS, PEX results, and extracted views are available in the attached project report.

---

# 4. Layout Area

The final op-amp layout occupies an area of approximately **2396 µm²**.

| Parameter | Value |
| --- | ---: |
| Width | 36.8 µm |
| Length | 65.1 µm |
| Total Area | 2396 µm² |

---

# 5. Pre-Layout vs Post-Layout Analysis

The performance of the two-stage op-amp was evaluated before and after parasitic extraction to determine the impact of physical layout parasitics.

The following parameters were compared:

- DC Gain
- Unity-Gain Bandwidth (UGB)
- Phase Margin
- Output Swing
- Power Consumption

The corresponding simulation plots and detailed analysis are provided in the attached project report.

---

# 6. Post-Layout Results

Post-layout simulations were performed using the extracted circuit to evaluate the effect of layout parasitics on the op-amp performance.

| Parameter | Pre-Layout | Post-Layout | Δ (%) |
| --- | ---: | ---: | ---: |
| DC Gain (dB) | 100.436 | 100.456 | 0.02 |
| UGB (MHz) | 68.08 | 64.05 | 5.88 |
| Phase Margin (°) | 17.23 | 18.64 | 1.97 |
| Output Swing (V) | 1.14 | 1.14 | 0 |
| Power (µW) | 125 | 125 | 0 |

### Key Post-Layout Results

- **DC Gain:** 100.456 dB
- **Unity-Gain Bandwidth:** 64.05 MHz
- **Phase Margin:** 18.64°
- **Output Swing:** 1.14 V
- **Power Consumption:** 125 µW

### Performance Analysis

The post-layout simulation demonstrates that the circuit maintains performance close to the pre-layout design despite the presence of extracted parasitics.

- The **DC gain** changes by only **0.02%**, indicating negligible impact on low-frequency gain.
- The **UGB** decreases from **68.08 MHz to 64.05 MHz**, corresponding to a **5.88% reduction**, primarily due to additional parasitic capacitances introduced by the physical layout.
- The **phase margin** improves from **17.23° to 18.64°**, representing a **1.97% increase**.
- The **output swing** remains unchanged at **1.14 V**.
- The **power consumption** remains constant at **125 µW**.

Overall, the post-layout results demonstrate that the physical implementation preserves the key electrical characteristics of the designed two-stage op-amp with limited degradation in bandwidth.

---

# 7. Tools Used

- **Cadence Virtuoso** – Schematic design and physical layout
- **Cadence Spectre** – Circuit simulation
- **Calibre DRC/LVS/PEX** – Physical verification and parasitic extraction
- **SCL 180 nm CMOS PDK** – Technology design kit

---

# 8. Design Flow

The project followed a complete analog IC design flow:

```text
Specification
     ↓
Circuit Architecture
     ↓
Transistor Sizing
     ↓
Schematic Design
     ↓
Pre-Layout Simulation
     ↓
Physical Layout
     ↓
    DRC
     ↓
    LVS
     ↓
    PEX
     ↓
Post-Layout Simulation
     ↓
Pre-Layout / Post-Layout Comparison
