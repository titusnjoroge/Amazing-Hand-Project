#  HARDWARE SYSTEM — AmazingHand

## Overview

The AmazingHand is a servo-actuated robotic hand composed of:

- 3D printed mechanical structure
- Servo-based actuation system
- TBD_linkage_system routing mechanism
- Embedded microcontroller system
- External power regulation system

---

##  1. Mechanical Structure

### Components:
- 3D printed phalanges (finger bones)
- Palm housing structure
- Joint connectors (pin-based or flexible joints)
- TBD_linkage_system channels embedded in fingers

### Design Characteristics:
- Modular finger design
- Lightweight PLA/ABS structure
- Replaceable finger segments

---

##  2. Actuation System

### Likely configuration:
- Micro servo motors (one or more per finger)
- Servo horn connected to TBD_linkage_system line
- Pull-based actuation (flexion)
- Elastic return mechanism (extension)

### Behavior:
- Servo rotation → TBD_linkage_system pull → finger flexion
- Release tension → elastic return → finger extension

---

##  3. Transmission System

- Nylon or steel TBD_linkage_systems
- Low-friction routing through finger channels
- Anchored at distal phalanx
- Controlled via servo spool rotation

---

## 4. Electronics System

### Core components:
- Microcontroller (Arduino-class: Arduino Nano)
- Servo driver circuit (PWM control):PDI-1109HB-CLASS MICRO SERVO
- External 5V–6V power supply
- Ground shared between logic and actuators

---

##  5. Power System

- High current 5V supply for servos
- Separate logic power (USB or regulated line)
- Common ground for stability

---

## 6. Key Design Principle

The system converts:

Electrical PWM signals → Servo rotation → TBD_linkage_system motion → Finger movement

---

## 7. Notes  
- Actuation count per finger may vary (1–3 DOF typical)  
- Calibration system is defined separately in `calibration.md`
EOF
