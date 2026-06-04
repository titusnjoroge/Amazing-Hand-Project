# System Architecture — AmazingHand

The AmazingHand system is a multi-layer robotic hand architecture integrating mechanical, electronic, firmware, and software systems into a unified control pipeline.

---

## 1. Hardware Layer

This layer represents the physical robotic structure.

### Components:
- Servo motors (actuators)
- 3D-printed finger segments (phalanges)
- Tendon routing system (cables or strings)
- Mechanical joints (pin or flexible joints)
- Palm housing structure

### Function:
Converts electrical motor commands into physical finger movement.

---

## 2. Software Layer

This layer defines high-level control logic.

### Components:
- Python control scripts / API layer
- Motion planning logic
- Optional GUI or external interface
- Serial communication handler

### Function:
Transforms user intent into structured motor commands.

---

## 3. Communication Layer

Acts as a bridge between software and hardware.

### Protocols:
- Serial (USB/UART)
- Optional ROS integration (future)
- Packet-based command structure

### Function:
Ensures reliable transmission of movement commands to firmware.

---

## 4. Firmware Layer

Runs on microcontroller (Arduino / STM32-class device).

### Responsibilities:
- Receive commands from software
- Parse motion instructions
- Generate PWM signals
- Manage timing and synchronization
- Enforce safe servo limits

---

## 5. Control Flow (SYSTEM PIPELINE)

The full system operates as a hierarchical pipeline:

User Input  
→ Command Interface (GUI / Script / API)  
→ Python Controller  
→ Serial Communication Layer  
→ Microcontroller Firmware  
→ PWM Signal Generation  
→ Servo Actuation  
→ Tendon Pulling Mechanism  
→ Finger Movement  

---

## 6. Hardware–Software Mapping

Each software command maps directly to hardware actions:

- Finger commands → individual servo motors
- Gesture commands → predefined motion sequences
- Position values → PWM duty cycles
- High-level API calls → multi-finger coordination

---

## 7. Feedback and Future Extensions

Currently, the system is open-loop (no sensing feedback).

Future upgrades may include:
- Finger position sensors
- Force feedback sensors
- Closed-loop PID control
- Auto-calibration system

---

## 8. Safety System

To prevent hardware damage:

- Servo angle limits enforced in firmware
- Power regulation required for stability
- Command filtering for sudden spikes
- Emergency stop mechanism (future feature)

---

## 9. System Summary

The AmazingHand architecture is divided into:

- Input Layer → user intent
- Control Layer → command processing
- Hardware Layer → physical execution

This separation enables modular design, scalability, and future robotic intelligence upgrades.
