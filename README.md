
# Design and Layout of a Two-Stage Op-Amp
## EE653 – Analog IC Design Lab

This repository contains the schematic design, transistor sizing, layout, physical verification, and performance analysis of a **Miller-compensated two-stage operational amplifier** designed using **Cadence Virtuoso** in **SCL 180 nm CMOS technology**.

---

## 📌 Design Specifications

| Parameter                 | Specification        |
| ------------------------- | -------------------- |
| Technology                | SCL 180 nm CMOS      |
| Supply Voltage            | 1.8 V                |
| Supply Sources            | Single VDD source    |
| Minimum Overdrive Voltage | \(V_{OV} > 150\,mV\) |
| EDA Tool                  | Cadence Virtuoso     |
| PDK                       | SCL 180 nm           |

---

# 1. Two-Stage Op-Amp Design

The operational amplifier consists of a **5-transistor OTA as the first stage** followed by a **common-source second stage**.

Miller compensation is implemented using a compensation capacitor and a nulling resistor.

### Architecture

* **First Stage:** 5-T OTA
* **Second Stage:** Common-source amplifier
* **Compensation:** Miller compensation
* **Nulling:** Series nulling resistor

> **TODO: Add two-stage op-amp schematic here.**

```text
![Two-Stage Op-Amp Schematic](images/opamp_schematic.png)
```

---

## 1.1 Transistor Sizing

| Device          | Type | W (µm) | L (µm) | \(I_D\) (µA) |
| --------------- | ---- | -----: | -----: | -----------: |
| Input Pair      | NMOS |     16 |      1 |           10 |
| P Mirror        | PMOS |      8 |      1 |           10 |
| Tail Transistor | NMOS |     16 |      1 |           20 |
| Bias Transistor | NMOS |      8 |      1 |           10 |
| M7 (CS Stage)   | NMOS |     32 |      1 |           40 |
| M8 (CS Stage)   | PMOS |     34 |      1 |           40 |

## 1.2 Passive Components

| Component | Description                   |  Value |
| --------- | ----------------------------- | -----: |
| \(C_C\)   | Miller Compensation Capacitor | 464 fF |
| \(R_Z\)   | Nulling Resistor              | 7.7 kΩ |
| \(C_L\)   | Load Capacitor                |   1 pF |

---

# 2. Op-Amp Layout

The two-stage op-amp layout was designed in **Cadence Virtuoso** following the SCL 180 nm design rules.

Common-centroid techniques were used for the **differential input pair and current mirror loads** to minimize mismatch due to process gradients.

### Full Layout

> **TODO: Add complete op-amp layout image here.**

```text
![Two-Stage Op-Amp Layout](images/opamp_layout.png)
```

### NMOS Current Mirror

> **TODO: Add NMOS mirror common-centroid layout.**

```text
![NMOS Current Mirror](images/nmos_mirror_layout.png)
```

### PMOS Current Mirror

> **TODO: Add PMOS mirror common-centroid layout.**

```text
![PMOS Current Mirror](images/pmos_mirror_layout.png)
```

### Input Differential Pair

> **TODO: Add input pair layout.**

```text
![Input Differential Pair](images/input_pair_layout.png)
```

### Common-Source Stage

> **TODO: Add common-source stage layout.**

```text
![Common-Source Stage](images/common_source_layout.png)
```

### Miller Compensation Network

> **TODO: Add Miller capacitor and nulling resistor layout.**

```text
![Miller Compensation](images/compensation_layout.png)
```

---

# 3. Physical Verification

The completed layout was verified using:

* **DRC** – Design Rule Check
* **LVS** – Layout Versus Schematic
* **PEX** – Parasitic Extraction

## DRC

> **TODO: Add DRC results screenshot.**

```text
![DRC Results](images/opamp_drc.png)
```

## LVS

> **TODO: Add LVS results screenshot.**

```text
![LVS Results](images/opamp_lvs.png)
```

## PEX

> **TODO: Add PEX results screenshot.**

```text
![PEX Results](images/opamp_pex.png)
```

## Extracted View

> **TODO: Add extracted layout/view.**

```text
![PEX Extracted View](images/opamp_extracted.png)
```

---

# 4. Layout Area

| Parameter  |    Value |
| ---------- | -------: |
| Width      |  36.8 µm |
| Length     |  65.1 µm |
| Total Area | 2396 µm² |

---

# 5. Pre-Layout vs Post-Layout Analysis

The op-amp performance is evaluated before and after parasitic extraction to determine the impact of layout parasitics.

## 5.1 Gain Comparison

> **TODO: Add gain comparison plot.**

```text
![Gain Comparison](images/opamp_gain_comparison.png)
```

## 5.2 Phase Comparison

> **TODO: Add phase comparison plot.**

```text
![Phase Comparison](images/opamp_phase_comparison.png)
```

## 5.3 Transient Response Comparison

> **TODO: Add transient response comparison plot.**

```text
![Transient Response Comparison](images/opamp_transient_comparison.png)
```

---

# 6. Post-Layout Results

> ## 🚧 Post-Layout Results — To Be Added
>
> Final extracted-view simulation results will be added here.

| Parameter    | Pre-Layout | Post-Layout | Change (%) |
| ------------ | ---------: | ----------: | ---------: |
| DC Gain      |     100 dB |         TBD |        TBD |
| UGB          |  56.32 MHz |         TBD |        TBD |
| Phase Margin |        16° |         TBD |        TBD |
| Output Swing |     1.14 V |         TBD |        TBD |
| Power        |     125 µW |         TBD |        TBD |

### Additional Post-Layout Results

> **TODO: Add final post-layout plots and observations here.**

* DC Gain: `TBD`
* Unity-Gain Bandwidth: `TBD`
* Phase Margin: `TBD`
* Output Swing: `TBD`
* Power Consumption: `TBD`
* Slew Rate: `TBD`
* Settling Time: `TBD`

---

# 7. Tools Used

* **Cadence Virtuoso**
* **Spectre Simulator**
* **Calibre DRC / LVS / PEX**
* **SCL 180 nm CMOS PDK**

---

# 8. Repository Structure

```text
.
├── README.md
├── schematic/
│   └── two_stage_opamp/
├── layout/
│   └── two_stage_opamp/
├── simulations/
│   ├── pre_layout/
│   └── post_layout/
├── verification/
│   ├── DRC/
│   ├── LVS/
│   └── PEX/
├── images/
│   └── two_stage_opamp/
└── report/
    └── Assignment_9B.pdf
```

---

## Author

**Sushant Gudmewar**
B.Tech–M.Tech Dual Degree, Electrical Engineering
Indian Institute of Technology Gandhinagar

**Course:** EE653 – Analog IC Design Lab
**Assignment:** 9B – Two-Stage Op-Amp Design and Layout
