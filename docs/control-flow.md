# Control Flow — AmazingHand

This document describes how commands travel through the AmazingHand system from user intent to physical finger movement.

It defines the full end-to-end execution pipeline across software, communication, firmware, and hardware layers.

---

## 1. High-Level Control Pipeline

The system follows a hierarchical command execution flow:

User Input  
→ Command Interface  
→ Control Software (Python / API / GUI)  
→ Command Processing Layer  
→ Communication Layer (Serial / USB / ROS)  
→ Microcontroller Firmware  
→ PWM Signal Generation  
→ Servo Actuation  
→ Tendon / Linkage System  
→ Finger Movement  

---

## 2. Detailed Execution Stages

### 2.1 User Input Layer

Input sources may include:

- GUI control panel
- Predefined gesture scripts
- API calls
- Manual test commands

**Output:** Desired finger pose or gesture request

---

### 2.2 Command Interface Layer

This layer translates raw input into structured commands.

Responsibilities:

- Validate input commands
- Format motion instructions
- Convert gestures into joint targets

**Output:** Structured command packet

---

### 2.3 Control Software Layer (Python / API)

This is the main brain of the system.

Responsibilities:

- Motion planning
- Finger coordination logic
- Mapping gestures to joint angles
- Sending commands to firmware

**Output:** Serialized command data

---

### 2.4 Communication Layer

Handles transmission between computer and microcontroller.

Protocols:

- Serial (UART over USB)
- Optional ROS messages
- Custom packet formats

Responsibilities:

- Ensure data integrity
- Handle latency
- Manage command queue

**Output:** Raw bytes to firmware

---

### 2.5 Firmware Layer (Microcontroller)

Runs on Arduino / STM32-class device.

Responsibilities:

- Parse incoming commands
- Map commands to servo channels
- Apply safety constraints
- Generate PWM signals

**Output:** Electrical PWM signals

---

### 2.6 Actuation Layer

This is the physical execution stage.

Components:

- Servo motors
- Tendon cables or linkages
- Joint structures

Responsibilities:

- Convert PWM → angular motion
- Apply force to tendons
- Move finger joints

**Output:** Mechanical finger motion

---

## 3. Timing and Synchronization

To ensure smooth motion:

- Commands are executed sequentially or in synchronized batches
- Servo updates must avoid sudden jumps
- Firmware may interpolate motion over time

---

## 4. Safety Control Points

Safety checks occur at multiple levels:

### Software level:
- Reject invalid angles
- Limit motion ranges

### Firmware level:
- Enforce servo constraints
- Prevent overload commands

### Hardware level:
- Mechanical hard stops
- Power regulation limits

---

## 5. Communication Structure (Example)

Example command packet:
[FINGER_ID, JOINT_ID, TARGET_ANGLE, SPEED]

Example:
[INDEX, 1, 45°, 50% speed]

---

## 6. System Behavior Model

The system is deterministic:

Same input → same output (assuming calibration is correct)

However, real-world factors include:

- Servo drift
- Cable elasticity
- Power fluctuations

---

## 7. Future Improvements

- Closed-loop feedback control (sensors on fingers)
- Real-time trajectory planning
- ROS2 integration
- Adaptive motion smoothing
- Force feedback control

---

## 8. Summary

The AmazingHand control system is a layered pipeline that converts human or programmatic intent into precise mechanical motion through structured software, communication, firmware, and actuation stages.
