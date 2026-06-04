# Hardware Architecture — AmazingHand

## 1. System Overview

The AmazingHand is a robotic hand system designed for dexterous manipulation using servo-driven actuation and a modular mechanical structure.

---

## 2. Mechanical Structure

The system consists of:

- 3D printed finger segments (phalanges)
- Palm housing structure
- Joint connectors for finger articulation
- Tendon routing channels (if tendon-driven)

Each finger is composed of multiple joints to enable human-like motion.

---

## 3. Actuation System

The hand is driven by multiple servo motors.

### Key characteristics:
- One or more servos per finger
- Servo-driven joint actuation
- Movement controlled via PWM signals
- Likely tendon-driven transmission system

---

## 4. Transmission System

Motion is transmitted through:

- Tendons (cables) OR direct linkages
- Elastic return mechanisms (springs or rubber bands)
- Guide channels within printed parts

This allows flexible finger movement while keeping motors outside the finger structure.

---

## 5. Electronics

The electronic system includes:

- Microcontroller (Arduino / STM32 class device)
- Servo driver system (PWM control)
- External power supply (5–6V high current)

---

## 6. Power System

- Servo motors require high current supply
- Logic system powered separately from actuators
- Voltage regulation required for stability

---

## 7. System Summary

The hardware architecture separates:

- Mechanical structure (movement)
- Actuation system (force generation)
- Electronics (control interface)

This modular design improves maintainability and scalability.
