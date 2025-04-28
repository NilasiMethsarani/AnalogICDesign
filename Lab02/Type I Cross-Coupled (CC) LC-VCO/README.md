# Type I Cross-Coupled (CC) LC-VCO Design and Analysis  

## Overview  
This repository contains the design, simulation, and analysis of the **Type I Cross-Coupled LC Voltage-Controlled Oscillator (VCO)**. It features an **NMOS-only cross-coupled architecture** with a standard **LC tank**, implemented in **45 nm CMOS technology**.  

## Design Features  
- **Topology**: NMOS-only cross-coupled pair with LC tank.  
- **Target Frequency**: **3 GHz oscillation**.  
- **Supply Voltage**: **1 V**.  
- **Bias Current**: **800 μA**.  
- **Tuning Mechanism**: **MOS varactors** with **fixed capacitors**.  

## Performance Summary  
| Parameter        | Type I CC LC-VCO |
|-----------------|------------------|
| **Tuning Range** | **8.17% (2.875–3.12 GHz)** |
| **Output Swing** | **432 mV** |
| **Phase Noise**  | **−82.2 dBc/Hz @ 100 kHz** |
| **VCO Gain \( K_{VCO} \)** | **0.57 GHz/V** |

## Simulation Files  
- **Schematics**: `TypeI_LCVCO.sch`  
- **Simulation Scripts**:  
  - **Transient Analysis** (`tran`)  
  - **Phase Noise Simulation** (`noise`)  

## Improvements & Future Work  
1. **Enhanced capacitor bank tuning** for wider frequency range.  
2. **Optimization of bias current** to improve efficiency.  
 

## Dependencies  
- **CMOS 45 nm PDK** for device models.  
- **RF Toolbox** for inductor/varactor modeling.  

##
