# EN4430 Analog IC Design - Assignment 01 (Single-Stage OTA)

This repository contains the design, analysis, and simulation files for the single-stage **Operational Transconductance Amplifier (OTA)** as part of **Assignment 01** for the **EN4430 Analog IC Design** module, implemented in **45 nm CMOS technology**.

## Simulation Images

The following images, located in the `images/SingleStage/` directory, illustrate the **single-stage OTA design and simulation results**:

- `SingleStageOTA.png`: Schematic of the single-stage OTA, showing the differential pair (**M1, M2**), NMOS current mirror (**M3, M4**), and PMOS active load (**M5, M6**).
- `OpenLoopOTA.png`: Testbench for **open-loop configuration**, used for transient and AC analysis without feedback.
- `ClosedLoopOTA.png`: Testbench for **closed-loop configuration** with unity gain feedback.
- `TransientResponse(OpenLoop).png`: **Transient response** plot for open-loop case, used to calculate **slew rate**.
- `TransientResponse(ClosedLoop).png`: **Transient response** plot for closed-loop case, showing **slew rate performance**.
- `ACResponseOpenloop.png`: **AC response** plot for open-loop configuration, displaying **gain, unity gain frequency, and phase margin**.
- `ACResponseClosedloop.png`: **AC response** plot for closed-loop configuration.

## Design Overview

The **single-stage OTA** is a differential amplifier designed with a **current mirror biasing scheme** and an **active load** to meet specified performance requirements. Key tasks include:

- **Device sizing calculations** for transistors **M1-M6** to achieve desired specifications.
- **Simulation of open-loop and closed-loop configurations** using **Cadence Virtuoso**.
- **Analysis of transient and AC responses** to evaluate **slew rate, DC gain, unity gain frequency, and phase margin**.

## Performance Specifications

| Parameter              | Specification |
|------------------------|--------------|
| **Technology**        | 45 nm CMOS    |
| **Supply Voltage**    | 1 V           |
| **Output Load Capacitance** | 2 pF  |
| **DC Gain**          | ≥ 40 dB       |
| **Unity Gain Frequency** | ≥ 20 MHz |
| **Phase Margin**     | > 45°         |
| **Slew Rate**        | > 10 V/μs     |
| **Power Consumption** | ≤ 1000 μW    |

## Simulation Results

### Open-Loop Configuration

| Parameter            | Result     | Specification | Met? |
|----------------------|-----------|--------------|------|
| **DC Gain**         | 22.3856 dB | ≥ 40 dB      | ❌   |
| **Unity Gain Frequency** | 1.12173 MHz | ≥ 20 MHz | ❌   |
| **Phase Margin**    | 94.3286°   | > 45°       | ✅   |
| **Slew Rate**       | 6.6061 V/μs | > 10 V/μs  | ❌   |

- **Slew rate calculation**: Vout transitions **from 100 mV to 900 mV** over **11.0399 μs to 11.161 μs**.

### Closed-Loop Configuration (Unity Gain Feedback)

| Parameter            | Result     | Specification | Met? |
|----------------------|-----------|--------------|------|
| **Slew Rate**       | 6.6803 V/μs | > 10 V/μs  | ❌   |

- **Slew rate calculation**: Vout transitions **from 158.34011 mV to 777.86979 mV** over **1.0375 μs to 1.1302 μs**.

---

This repository provides all necessary **design files, analysis reports, and simulation results** for evaluating the **single-stage OTA's performance** in both **open-loop and closed-loop configurations**.

