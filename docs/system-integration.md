# System Integration — AmazingHand

This document connects all subsystems of the AmazingHand into a unified robotics system model.

---

## 1. Subsystem Overview

The system is composed of:

- Hardware Layer (fingers, tendons, servos)
- Software Layer (Python control logic)
- Communication Layer (Serial / ROS / USB)
- Firmware Layer (microcontroller PWM control)
- Calibration System (servo alignment + offsets)

---

## 2. Unified System Flow

User Intent  
→ Software Controller  
→ Command Mapping  
→ Communication Layer  
→ Firmware Execution  
→ Servo Actuation  
→ Tendon Mechanics  
→ Finger Movement  

---

## 3. Key Design Principle

The system follows a **separation of concerns architecture**:

- Software = intelligence + decision making
- Firmware = real-time execution
- Hardware = physical motion
- Calibration = correctness + stability

---

## 4. System Assumptions

- Servos are PWM-controlled
- Communication is serial-based
- Tendons introduce non-linear motion behavior
- No active force feedback is currently implemented

---

## 5. Failure Modes

The system may fail due to:

- Servo saturation
- Cable slack or breakage
- Power instability
- Incorrect calibration offsets
- Communication latency

---

## 6. Limitations

Current system limitations:

- Open-loop control only
- No sensor feedback
- No adaptive learning
- No real-time correction

---

## 7. Future Architecture Extensions

- Closed-loop feedback control
- Force sensing fingertips
- ROS2 full integration
- Dynamic motion planning
- Self-calibration routines

---

## 8. Engineering Summary

This system is a classical tendon-driven robotic hand architecture using layered software-hardware separation and PWM-based actuation.
