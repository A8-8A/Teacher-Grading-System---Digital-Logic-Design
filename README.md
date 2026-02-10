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
