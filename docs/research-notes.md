# Research Notes

This document serves as a continuous research journal for understanding the AmazingHand open-source robotic hand project.

The goal is to document architecture, hardware components, software stack, and control mechanisms while identifying areas for improvement and contribution.

---

## Research Sessions

### Session 1 — Repository Setup and Documentation Foundation
Date: 2026-06-02

**Completed:**
- Created documentation repository
- Configured Git and SSH authentication
- Created documentation structure
- Added README, overview, setup, hardware, software, and architecture documents

**Outcome:**
- Documentation framework established
- Ready to begin technical investigation of the AmazingHand repository

---

### Session 2 — Architecture Documentation
Date: 2026-06-04

**Completed:**
- Expanded architecture documentation
- Added control flow descriptions
- Added firmware responsibilities
- Added system layering explanations

**Outcome:**
- High-level system architecture documented
- Need to validate design against actual repository implementation

---

## Investigation Framework

This section defines the areas of technical exploration.

### 1. Hardware Analysis
- Servo motors used in the system
- Number of actuators and degrees of freedom
- Mechanical design (TBD_linkage_systems, joints, structure)
- Electronics and microcontroller board
- Power requirements and wiring layout

### 2. Software Analysis
- Programming languages used
- Control scripts or frameworks
- Dependencies and libraries
- Communication protocol (Serial / ROS / custom API)

### 3. Control System
- How user input is captured
- How commands are processed
- How signals are transmitted to firmware
- How servo movement is generated

### 4. Calibration System
- Servo calibration method
- Offset storage
- Movement limits
- Repeatability handling

### 5. Safety and Reliability
- Protection against invalid commands
- Emergency stop handling
- Communication failure handling
- Mechanical safety constraints

---

## Open Questions (Active Investigation)

- What servo motors are used in the AmazingHand system?
- What microcontroller is used?
- How does software communicate with firmware?
- Is ROS used or a custom protocol?
- How is calibration handled?
- How are finger movements individually controlled?

---

## Current Findings (To be filled during investigation)

### Hardware Findings
(To be updated)

### Software Findings
(To be updated)

### Architecture Findings
(To be updated)

---

## Next Step

Begin deep analysis of the actual AmazingHand repository:
https://github.com/pollen-robotics/AmazingHand

Focus areas:
- Map real hardware vs documentation
- Validate control flow
- Identify missing system components
- Extract real firmware/software structure

---

## Notes

This is a living document and will evolve as the project investigation continues.
