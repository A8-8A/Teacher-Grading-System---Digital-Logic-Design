# Teacher-Grading-System---Digital-Logic-Design

## Overview
This project implements a **grading system using combinational digital logic**.  
The system processes a student’s initial grade, applies a set of grading rules, and outputs a final grade along with visual status indicators.

The design was developed using **Quartus II schematic capture**, verified through simulation, and implemented on a **physical breadboard** using discrete logic components.

---

## System Rules
The grading logic follows these constraints:

- Grades range from **0 to 10**
- A grade of **5 or higher is considered passing**
- Odd grades are adjusted to the **nearest lower even value**
- A passing grade must **never be converted into a failing grade**
- Visual feedback is provided using LEDs:
  - **Green LED** → grade unchanged
  - **Red LED** → grade adjusted

---

## Inputs
- **4-bit binary input** representing the initial student grade

---

## Outputs
- **4-bit binary output** representing the final grade
- **Green LED** indicating an unchanged grade
- **Red LED** indicating a modified grade

---

## Logic Design Approach
The system is implemented using pure combinational logic and includes:

- Odd/even detection using the least significant bit (LSB)
- Conditional decrement logic for odd grades
- Pass-protection logic to prevent invalid grade reduction
- Status signaling logic to indicate grade modification

Special care was taken to correctly handle boundary cases such as grades at the passing threshold.

---

## Implementation
- Designed using **Quartus II schematic editor**
- Verified using **Quartus simulation waveforms**
- Implemented on a **breadboard** using logic ICs and LED indicators
- Optimized to use a **minimum number of integrated circuits**

---

## Project Structure
## Truth Table

![TruthTable](https://github.com/user-attachments/assets/1ee1e6f0-60c8-4280-a6c8-8c3459f24a5e)

- after observing patterns we found out that the bits ABC don't change by the equatiopn so they are always equal to there respective next phase


---

## Deriving Equations for x and D1
![Analyzing patterns for D1 and deriving it from the truth table using K-maps ](https://github.com/user-attachments/assets/12e62364-579f-4da2-b947-d5213fd72148)


![Finding X](https://github.com/user-attachments/assets/179e3274-9625-4086-9be9-54f0913e3408)

---
- finally we found the equations were D1 = BC'D & X = (B'+C)D

---

## Logic Circuit Design
- we were challanged to limit the number to only 2 ICs that meaned we can only use 2 types of gates from various types of gates XOR/NOR/NAND/AND/OR/
 - after a lot of brain storming and discussion and tens of sketches me and my team finally succeeded in implementing the equation successfuly using only 2 ICs (8 gates)
  - Using 7 NAND gates we sketched the logic design successfully

<img width="358" height="405" alt="First successful Sketch" src="https://github.com/user-attachments/assets/3f802fd1-c8bc-4d60-91ff-2c47f49c6a80" />

---

## Quartus Schematic

- I setup the inputs of the grades represented by the 4 bits A,B,C, and D and the grade after being processed to A1 ,B1, C1, and D1. X is the indicator that will flag a change to the grade were it turns green when it’s of value 0 and red when 1.

<img width="975" height="435" alt="Implementation on Quartus" src="https://github.com/user-attachments/assets/c571f533-7fab-41a9-902c-a0a5f25297d5" />

- We then simulated the design taking into consideration al the possible grades out of 10
<img width="975" height="375" alt="Successful simulation of the design" src="https://github.com/user-attachments/assets/6581ed8e-c933-41a4-90b4-fe6b0494bef0" />


## Finally 
## Circuit Design 
- using a Global Specialties PB-503ALAB - PB-503A provided by the Lebanese American University's Lab
- 2x 74LS00
- Lots of wires

  
  ![The successful Solution to the problem in circuitry](https://github.com/user-attachments/assets/e207145e-73ee-47bf-bf73-3a8e6bf38517)




