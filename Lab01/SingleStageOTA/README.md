EN4430 Analog IC Design - Assignment 01 (Single-Stage OTA)
This repository contains the design, analysis, and simulation files for the single-stage Operational Transconductance Amplifier (OTA) as part of Assignment 01 for the EN4430 Analog IC Design module, implemented in 45 nm CMOS technology.
Simulation Images
The following images, located in the images/SingleStage/ directory, illustrate the single-stage OTA design and simulation results:

SingleStageOTA.png: Schematic of the single-stage OTA, showing the differential pair (M1, M2), NMOS current mirror (M3, M4), and PMOS active load (M5, M6).
OpenLoopOTA.png: Testbench for open-loop configuration, used for transient and AC analysis without feedback.
ClosedLoopOTA.png: Testbench for closed-loop configuration with unity gain feedback.
TransientResponse(OpenLoop).png: Transient response plot for open-loop case, used to calculate slew rate.
TransientResponse(ClosedLoop).png: Transient response plot for closed-loop case, showing slew rate performance.
ACResponse.png: AC response plot for open-loop configuration, displaying gain, unity gain frequency, and phase margin.
ACResponseClosedloop.png: AC response plot for closed-loop configuration.

The single-stage OTA is a differential amplifier designed with a current mirror biasing scheme and an active load to meet specified performance requirements. Key tasks include:

Device sizing calculations for transistors M1-M6 to achieve desired specifications.
Simulation of open-loop and closed-loop configurations using Cadence Virtuoso.
Analysis of transient and AC responses to evaluate slew rate, DC gain, unity gain frequency, and phase margin.

Performance Specifications

Technology: 45 nm CMOS
Supply Voltage: 1 V
Output Load Capacitance: 2 pF
DC Gain: ≥ 40 dB
Unity Gain Frequency: ≥ 20 MHz
Phase Margin: > 45°
Slew Rate: > 10 V/μs
Power Consumption: ≤ 1000 μW

Simulation Results
Open-Loop Configuration

DC Gain: 22.3856 dB (specification: ≥ 40 dB, not met)
Unity Gain Frequency: 1.12173 MHz (specification: ≥ 20 MHz, not met)
Phase Margin: 94.3286° (specification: > 45°, met)
Slew Rate: 6.6061 V/μs (specification: > 10 V/μs, not met)
Calculated from transient response: Vout transitions from 100 mV to 900 mV over 11.0399 μs to 11.161 μs.



Closed-Loop Configuration (Unity Gain Feedback)

Slew Rate: 6.6803 V/μs (specification: > 10 V/μs, not met)
Calculated from transient response: Vout transitions from 158.34011 mV to 777.86979 mV over 1.0375 μs to 1.1302 μs.


