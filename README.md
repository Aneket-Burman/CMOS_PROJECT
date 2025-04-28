# 2-Bit Vedic Multiplier using CMOS Technology

## Overview
This project implements a **2-bit Vedic Multiplier** using **CMOS technology**.  
It focuses on optimizing speed, area, and power using 5T AND gates and 9T Half Adders.  
The design was simulated using **Microwind** and **NGSpice** tools.

---

## Table of Contents
- [What is a Vedic Multiplier](#what-is-a-vedic-multiplier)
- [Block Diagram](#block-diagram)
- [Optimized Circuit Design](#optimized-circuit-design)
- [MicroWind Layouts](#microwind-layouts)
- [Netlist](#netlist)
- [Outputs](#outputs)
- [Advantages](#advantages)
- [Applications](#applications)

---

## What is a Vedic Multiplier?

The **Vedic Multiplier** is a high-speed, low-power architecture based on the ancient Indian "Urdhva Tiryakbhyam" sutra (vertical and crosswise multiplication).  
It enables **parallel partial product generation**, reducing computation time and enhancing efficiency — ideal for **DSP**, **image processing**, and **embedded systems**.

---

## Block Diagram

<!-- Insert Block Diagram Image here -->
![Block Diagram](path/to/block_diagram.png)

---

## Optimized Circuit Design

### 5T AND Gate
- Uses pass transistor logic.
- **B** is output when **A = 1**, otherwise **0**.
- Saves 1 transistor per gate compared to traditional 6T AND.

### 9T Half Adder
- Combines a 5T AND gate and a 4T XOR gate.
- Focuses on **high-speed**, **low-power**, and **full-swing operation**.
- Reduces transistor count and ensures reliable cascading.

---

## MicroWind Layouts

<!-- Insert Layout Images here -->
![Microwind Layout 1](path/to/microwind_layout1.png)
![Microwind Layout 2](path/to/microwind_layout2.png)

---

## Netlist

The complete project netlist is provided in the [`CMOS_FINAL.cir`](path/to/CMOS_FINAL.cir) file.

Here’s a snippet of the NGSpice netlist used for simulation:

```plaintext
*** POWER SUPPLY SOURCES ***
VDD 1 0 DC 2.00
...
.model N1 nmos level=14 VTH0=0.55
.model P1 pmos level=14 VTH0=-0.55
...
.tran 0.01n 10n
.control
run
plot v(46)
plot v(26)
plot v(66)
plot v(20)
.endc
.end
