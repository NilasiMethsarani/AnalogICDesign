# Device Sizing Calculations

All MOSFETs are assumed to operate in the **saturation region**. The following calculations determine the **device sizes** based on performance specifications.

## Output Current (\(I_o\)) for Slew Rate

The **slew rate (SR)** is defined as the maximum rate of change of output voltage:


\[
SR = \frac{I_o}{C_L}
\]


where:
- \( SR > 10 \, \text{V}/\mu\text{s} \)
- \( C_L = 2 \, \text{pF} \)

Solving for \( I_o \):


\[
I_o = SR \cdot C_L
\]


Substituting values:


\[
I_o = 10 \times 10^6 \times 2 \times 10^{-12} = 20 \times 10^{-6} \, \text{A} = 20 \, \mu\text{A}
\]



## \(W/L\) Ratio for \(M_5\) and \(M_6\) (ICMR\(^+\) Constraint)

The **drain-source voltage** must satisfy the **saturation condition** for \( M_1 \):


\[
V_{DS} \geq V_{GS} - V_{th}
\]


For **ICMR\(^+\) = 0.9 V**, the voltage at node \( V_1 \) must be:


\[
V_1 \geq V_{in} - V_{th}
\]


Substituting values:


\[
V_1 = 0.9 - 0.4 = 0.5 \, \text{V}
\]


Thus, \( V_{DS} \) is:


\[
V_{DS} = V_{DD} - V_1 = 1 - 0.5 = 0.5 \, \text{V}
\]


Device sizing:


\[
\frac{W}{L} = \frac{2 I_D}{\mu_n C_{ox} (V_{GS} - V_{th})^2}
\]


Substituting values:


\[
\frac{W}{L} = \frac{2 \times 10 \times 10^{-6}}{0.3 \times 10^{-3} \times (0.2)^2} \approx 2
\]


Chosen values:
- **\( L = 0.1 \, \mu\text{m} \)**
- **\( W = 0.2 \, \mu\text{m} \)**

## Transconductance (\(g_{m1,2}\)) Calculation

The **gain-bandwidth product (GB)** is given by:


\[
GB = \frac{g_{m1,2}}{2 \pi C_L}
\]


Substituting values:


\[
g_{m1,2} = 20 \times 10^6 \times 2 \pi \times 2 \times 10^{-12} \approx 251.33 \, \mu\text{S}
\]



## \(W/L\) Ratio for \(M_1\) and \(M_2\)

MOSFET **drain current equation**:


\[
I_D = \frac{1}{2} \mu C_{ox} \frac{W}{L} (V_{GS} - V_t)^2
\]


Transconductance equation:


\[
g_m^2 = 2 \mu C_{ox} \frac{W}{L} I_D
\]


Rearranging for **\(W/L\)**:


\[
\frac{W}{L} = \frac{g_m^2}{2 \mu C_{ox} I_D}
\]


Substituting values:


\[
\frac{W}{L} = \frac{(251.33 \times 10^{-6})^2}{2 \times 0.3 \times 10^{-3} \times 10 \times 10^{-6}} \approx 10.52
\]


Chosen value: **\( W/L = 20 \)**.

## Gate-Source Voltage for \(M_1\)



\[
V_{GS} - V_{TH} = \sqrt{\frac{2 I_D}{\mu C_{ox} \frac{W}{L}}}
\]


Substituting values:


\[
V_{GS} = 0.4 + 0.0577 \approx 0.46 \, \text{V}
\]



## \(W/L\) Ratio for \(M_3\) and \(M_4\)

The condition:


\[
V_{IN} > V_{GS} + V_{DSAT}
\]


Device sizing equation:


\[
\frac{W}{L} = \frac{2 I_D}{\mu C_{ox} V_{DSAT}^2}
\]


Substituting values:


\[
\frac{W}{L} \approx 84
\]


Chosen values:
- **\( L = 0.1 \, \mu\text{m} \)**
- **\( W = 8.4 \, \mu\text{m} \)**

## Summary of Calculated Values

| Parameter | Symbol | Approximated \( W/L \) | Chosen \( W/L \) | Unit |
|-----------|--------|----------------|---------------|------|
| Channel Length | \(L\) | - | 0.1 | \( \mu\text{m} \) |
| \( W/L \) for \(M_1, M_2\) | \( \frac{W}{L}_{M1,M2} \) | 10.52 | 20 | - |
| \( W/L \) for \(M_3, M_4\) | \( \frac{W}{L}_{M3,M4} \) | 83.33 | 84 | - |
| \( W/L \) for \(M_5, M_6\) | \( \frac{W}{L}_{M5,M6} \) | 1.67 | 2 | - |
| Output Current | \( I_o \) | - | 20 | \( \mu\text{A} \) |
| Transconductance | \( g_{m1,2} \) | - | 251.33 | \( \mu\text{S} \) |
| Gate-Source Voltage for \(M_1\) | \( V_{GS} \) | - | 0.46 | V |
| NMOS \( \mu C_{ox} \) | \( \mu_n C_{ox} \) | - | 0.3 | mA/V\(^2\) |
| PMOS \( \mu C_{ox} \) | \( \mu_p C_{ox} \) | - | 0.3 | mA/V\(^2\) |
| NMOS Threshold Voltage | \( V_{th,NMOS} \) | - | 0.4 | V |
| PMOS Threshold Voltage | \( V_{th,PMOS} \) | - | -0.3 | V |

---

This README provides detailed **device sizing calculations**, ensuring proper operation within **performance constraints**. Let me know if you need modifications!
