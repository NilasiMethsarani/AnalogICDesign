# Type IV Fully Differential CC LC-VCO Design and Analysis  

## Overview  
This repository contains the design, simulation, and analysis of the **Type IV Fully Differential Cross-Coupled (CC) LC Voltage-Controlled Oscillator (VCO)**. This topology integrates **dual NMOS-PMOS cross-coupled stages** and a **center-tapped symmetric inductor** for **higher output swing** and **low phase noise performance**.

## Design Features  
- **Topology**: Fully differential NMOS-PMOS cross-coupled LC tank.  
- **Target Frequency**: **3 GHz oscillation**.  
- **Supply Voltage**: **1 V**.  
- **Bias Current**: **500 μA**.  
- **Tuning Mechanism**: **MOS varactors** for fine frequency control.  

## Performance Summary  
| Parameter        | Type IV Fully Differential CC LC-VCO |
|-----------------|-------------------------------------|
| **Tuning Range** | **69% (1.9–3.9 GHz)** |
| **Output Swing** | **3.382 V (peak-to-peak)** |
| **Phase Noise**  | **−83.77 dBc/Hz @ 100 kHz** |
| **VCO Gain \( K_{VCO} \)** | **1.95 GHz/V** |

## Simulation Files  
- **Schematics**: `TypeIV_LCVCO.sch`  
- **Simulation Scripts**:  
  - **Transient Analysis** (`tran`)  
  - **Phase Noise Simulation** (`noise`)  

## Improvements & Future Work  
1. **Hybrid capacitor bank** for multi-stage tuning.  
2. **Balanced varactor biasing** to stabilize **\( K_{VCO} \)**.  

