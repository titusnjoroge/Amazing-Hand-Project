# System Architecture

The AmazingHand system is a multi-layer robotic control system that integrates mechanical, electronic, and software components.

---

## 1. Hardware Layer

This layer represents the physical structure of the robotic hand.

It includes:

- Servo motors (for finger movement)
- Finger linkage mechanisms
- Mechanical joints
- Mounting structure

These components are responsible for converting electrical signals into physical movement.

---

## 2. Software Layer

This layer handles control logic and command processing.

It typically includes:

- Python control scripts or API
- Arduino / embedded firmware
- Serial communication interfaces

The software layer translates user commands into motor instructions.

---

## 3. System Input Layer

The system can receive commands from different input sources such as:

- User interfaces (GUI or web applications)
- Predefined motion scripts
- API calls (future extension)

These inputs define the desired finger positions or gestures.

## 4. Control Flow

The system follows a layered control pipeline:

User Input
    ↓
Command Interface (GUI / Script / API)
    ↓
Control Logic (Python Controller)
    ↓
Communication Layer (Serial / USB / ROS)
    ↓
Embedded Firmware (Microcontroller)
    ↓
PWM Signal Generation
    ↓
Servo Actuation
    ↓
Mechanical Finger Movement

---

## 5. Firmware Responsibilities

The embedded firmware (e.g., Arduino-based system) is responsible for:

- Receiving control signals from the software layer
- Interpreting movement commands
- Generating PWM signals for servos
- Managing timing and synchronization of finger movements


## 6. System Summary

The AmazingHand architecture separates the system into three main layers:

- Input Layer → defines user intent
- Control Layer → processes and translates commands
- Hardware Layer → executes physical movement

This modular design allows for scalability, maintainability, and future integration of advanced robotics features such as feedback control and autonomous motion planning.
