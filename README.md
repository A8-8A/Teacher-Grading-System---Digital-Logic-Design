# Teacher Grading System – Digital Logic Design

## Overview
This project presents a grading system implemented using **combinational digital logic**.  
The system evaluates an input grade, applies predefined grading constraints, and outputs the processed grade along with a visual indicator signaling whether a modification occurred.

The design was developed using **Quartus II schematic capture**, validated through waveform simulation, and physically implemented on a breadboard using discrete logic ICs.

---

## System Rules
The grading logic follows the constraints below:

- Grades range from **0 to 10**
- A grade of **5 or higher is considered passing**
- Odd grades are adjusted to the **nearest lower even value**
- A passing grade must **never be converted into a failing grade**
- Visual feedback is provided using LEDs:
  - **Green LED** → grade unchanged
  - **Red LED** → grade adjusted

---

## Inputs
- **4-bit binary input (A, B, C, D)** representing the initial grade

## Outputs
- **4-bit binary output (A1, B1, C1, D1)** representing the final grade
- **X (status signal)** indicating whether a modification occurred

---

## Truth Table
![TruthTable](https://github.com/user-attachments/assets/1ee1e6f0-60c8-4280-a6c8-8c3459f24a5e)

After analyzing the truth table, it was observed that the upper bits (A, B, C) remain unchanged under the grading constraints, while the least significant logic adjustments affect the output and status signal.

---

## Derivation of Logic Equations
![Analyzing patterns for D1 and deriving it from the truth table using K-maps](https://github.com/user-attachments/assets/0802eac3-46dd-4421-9fd2-5444261ea36f)

### Derivation of Status Signal X
![Finding X](https://github.com/user-attachments/assets/f96aabda-4123-404f-9cee-498c73c274f0)


From the minimization process, the final Boolean expressions obtained were:

- **D1 = B C' D**
- **X = (B' + C) D**

---

## Logic Circuit Design
A key design constraint was minimizing hardware usage by limiting the implementation to **two ICs**.  
This required careful gate-level optimization and efficient Boolean minimization.

The final circuit was implemented using:
- **7 NAND gates**
- Equivalent to **2 × 74LS00 ICs (quad NAND gates)**

This approach demonstrates a NAND-based realization of the derived Boolean equations while maintaining hardware efficiency.

![First successful Sketch](https://github.com/user-attachments/assets/3f802fd1-c8bc-4d60-91ff-2c47f49c6a80)

---

## Quartus Implementation
The system was modeled in Quartus using schematic design, where:
- Inputs A, B, C, D represent the initial grade
- Outputs A1, B1, C1, D1 represent the processed grade
- X acts as a status indicator (0 = unchanged, 1 = modified)

![Implementation on Quartus](https://github.com/user-attachments/assets/c571f533-7fab-41a9-902c-a0a5f25297d5)

---

## Simulation & Verification
The circuit was simulated across all valid input grades (0–10) to ensure:
- Correct grade adjustment behavior
- Accurate status signal activation
- Proper handling of edge cases (especially near the passing threshold)

![Successful simulation of the design](https://github.com/user-attachments/assets/6581ed8e-c933-41a4-90b4-fe6b0494bef0)

---

## Hardware Implementation
The design was physically implemented on a breadboard using:

- **2 × 74LS00 NAND ICs**
- Breadboard (PB-503A Lab Trainer)
- Discrete wiring and LED indicators

![The successful Solution to the problem in circuitry](https://github.com/user-attachments/assets/e207145e-73ee-47bf-bf73-3a8e6bf38517)

---

## Key Design Highlights
- Pure combinational logic implementation
- NAND-only optimized hardware realization
- Full verification through simulation and physical testing
- Efficient IC utilization under hardware constraints












## Future Improvements
- HDL (Verilog/VHDL) implementation
- FPGA deployment
- Seven-segment display output for grade visualization




