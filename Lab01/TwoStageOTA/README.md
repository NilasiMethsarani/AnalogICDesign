# EN4430 Analog IC Design - Assignment 01 (Two-Stage OTA)

This repository contains the design, analysis, and simulation files for the **two-stage Operational Transconductance Amplifier (OTA)**, specifically a **three current-mirror OTA**, as part of **Assignment 01** for the **EN4430 Analog IC Design** module, implemented in **45 nm CMOS technology**.

## Simulation Images

The following images, located in the `images/TwoStage/` directory, illustrate the **two-stage OTA design and simulation results**:

- `TwoStageOTA.png`: Schematic of the two-stage **single-ended symmetric OTA**, showing the **differential pair (M1, M2)**, **self-biased inverters (M1, M3 and M2, M4)**, and **current mirrors (M3, M5, M4, M6, M7, M8, M9, M10)**.
- `SingleAndTwoStageOTA.png`: Comparison of **single-stage and two-stage OTA schematics**.
- `OpenloopTestbench(Two Stage).png`: Testbench for **open-loop configuration**, used for transient and AC analysis without feedback.
- `ClosedLoopTestBench.png`: Testbench for **closed-loop configuration** with unity gain feedback.
- `SlewRate(OpenLoop).png`: **Transient response plot** for open-loop case, used to calculate **slew rate**.
- `TransientResponseClosedLoop.png`: **Transient response plot** for closed-loop case, showing **slew rate performance**.
- `AcResponse(OpenLoop).png`: **AC response plot** for open-loop configuration, displaying **gain, unity gain frequency, and phase margin**.
- `ACResponse(ClosedLoop).png`: **AC response plot** for closed-loop configuration.



## Design Overview

The **two-stage OTA**, also known as a **three current-mirror OTA**, enhances the **single-stage OTA** by incorporating **self-biased loads** and additional **current mirrors** to improve gain and output swing. 

### Design Features:
- **Differential pair (M1, M2)** for input amplification.
- **Self-biased inverters formed by (M1, M3) and (M2, M4)**.
- **Current mirrors (M3, M5; M4, M6; M7, M8; M9, M10)** for biasing and load.
- **Symmetry in transistor matching (M1 = M2, M3 = M4, M5 = M6, M7 = M8)** to simplify design and ensure balanced performance.

### Key Tasks:
- **Device sizing calculations** for **transistors M1-M10**, mapped from **single-stage OTA ratios**.
- **Simulation of open-loop and closed-loop configurations** using **Cadence Virtuoso**.
- **Analysis of transient and AC responses** to evaluate **slew rate, DC gain, unity gain frequency, and phase margin**.

## Performance Specifications

| Parameter                | Specification |
|--------------------------|--------------|
| **Technology**           | 45 nm CMOS   |
| **Supply Voltage**       | 1 V          |
| **Output Load Capacitance** | 2 pF     |
| **DC Gain**              | ≥ 40 dB      |
| **Unity Gain Frequency** | ≥ 20 MHz     |
| **Phase Margin**         | > 45°        |
| **Slew Rate**            | > 10 V/μs    |
| **Power Consumption**    | ≤ 1000 μW    |

## Simulation Results

### Open-Loop Configuration

| Parameter            | Result     | Specification | Met? |
|----------------------|-----------|--------------|------|
| **DC Gain**         | 21.1052 dB | ≥ 40 dB      | ❌   |
| **Unity Gain Frequency** | 10.2355 MHz | ≥ 20 MHz | ❌   |
| **Phase Margin**    | 85.3505°   | > 45°       | ✅   |
| **Slew Rate**       | 8.3691 V/μs | > 10 V/μs  | ❌   |

- **Slew rate calculation**: Vout transitions **from 100 mV to 900 mV** over **5.08923 μs to 5.18482 μs**.

### Closed-Loop Configuration (Unity Gain Feedback)

| Parameter            | Result     | Specification | Met? |
|----------------------|-----------|--------------|------|
| **Slew Rate**       | 12.4142 V/μs | > 10 V/μs  | ✅   |

- **Slew rate calculation**: Vout transitions **from 275.849 mV to 809.658 mV** over **14.5777 μs to 14.6207 μs**.

## Device Sizing Summary

The **W/L ratios** for the **two-stage OTA** are derived from the **single-stage OTA calculations**, with adjustments for **current distribution**:

| Transistor Pair | W/L Ratio | Width (W) | Unit |
|----------------|----------|----------|------|
| **M1, M2 (Differential Pair)** | 20 | 2.4 | μm |
| **M3, M4 (Self-Biased Inverters)** | 2 | 0.24 | μm |
| **M5, M6 (Current Mirror)** | 4 | 0.48 | μm |
| **M7, M8 (Current Mirror)** | 84 | 10 | μm |
| **M9, M10 (Current Mirror)** | 84 | 10 | μm |


