# Finger Model — AmazingHand

This document defines the mechanical structure, actuation mapping, and kinematic behavior of each finger in the AmazingHand robotic system.

It focuses on tendon routing, servo assignment, and degrees of freedom (DOF).

---

## 1. System Overview

The AmazingHand uses a tendon-driven actuation system, where:

- Servo motors pull tendons  
- Tendons flex finger joints  
- Elastic elements or passive forces return fingers to neutral  

This allows lightweight fingers with remote actuation.

---

## 2. Global Finger Architecture

Each finger typically consists of:

- Proximal phalanx (base segment)  
- Middle phalanx  
- Distal phalanx  
- Tendon routing channel  
- One or more tendons (flexor system)

---

## 3. Degrees of Freedom (DOF)

| Finger | DOF | Notes |
|--------|-----|------|
| Thumb  | 3–4 | Most complex (opposition + rotation) |
| Index  | 2–3 | Precision grasp |
| Middle | 2   | Stability support |
| Ring   | 2   | Coupled motion common |
| Pinky  | 2   | Reduced actuation |

---

## 4. Servo-to-Finger Mapping (Conceptual Model)

> NOTE: Exact servo IDs depend on hardware configuration.

| Servo | Controls | Function |
|------|----------|----------|
| S1 | Thumb flexion | Main tendon pull |
| S2 | Thumb opposition | Lateral movement |
| S3 | Index flexion | Grip control |
| S4 | Middle flexion | Support motion |
| S5 | Ring flexion | Coupled actuation |
| S6 | Pinky flexion | Stability assist |

---

## 5. Tendon Routing Model

Each tendon follows this path:

Servo spool → guide channel → finger entry point → phalanx routing → distal anchor

### Key properties:
- Low friction routing is critical  
- Tendon tension must be balanced  
- Elastic return or spring assist used for extension  

---

## 6. Thumb Kinematics (Critical Section)

The thumb is biomechanically different from other fingers.

It includes:

- Flexion/extension  
- Abduction/adduction  
- Opposition movement  

### Functional behavior:
- Enables pinch grasp  
- Enables power grasp  
- Requires multi-axis actuation  

---

## 7. Motion Behavior Model

Finger movement follows this chain:

Servo rotation  
→ tendon pull force  
→ joint torque generation  
→ phalanx rotation  
→ fingertip displacement  

---

## 8. Calibration Considerations

Each finger requires calibration for:

- Neutral position (0° reference)  
- Maximum flexion limit  
- Tendon slack compensation  
- Servo offset correction  

---

## 9. System Limitations

- No direct force feedback (open-loop system)  
- Tendon elasticity introduces minor error  
- Servo precision limits fine control accuracy  

---

## 10. Future Improvements

- Add force sensors in fingertips  
- Add position encoders  
- Implement closed-loop control  
- Improve thumb opposability mechanism  
- Add adaptive grip control  
EOF
