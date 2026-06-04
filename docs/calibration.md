# Calibration System — AmazingHand

The calibration system defines how the AmazingHand robotic system establishes consistent, repeatable, and safe motion across all actuators (servos) and tendon-driven fingers.

This is critical because servo-based tendon systems drift over time and require initialization alignment.

---

## 1. Purpose of Calibration

Calibration ensures:

- Each servo starts from a known zero position
- Finger joints align with mechanical limits
- Tendon tension is balanced
- Motion commands produce predictable results
- Hardware safety is maintained during startup

---

## 2. Calibration Types

### 2.1 Servo Neutral Calibration

Each servo is assigned a neutral (center) position:

- Typically 90° for standard hobby servos
- May vary depending on mechanical setup
- Used as reference “home position”

---

### 2.2 Finger Zero Position Calibration

Each finger must be aligned to its:

- Fully extended position (open hand state)
- Or mechanically defined home stop

This ensures consistency across all fingers.

---

### 2.3 Tendon Tension Calibration

For tendon-driven systems:

- Ensure equal tension across flexor cables
- Avoid slack that causes motion delay
- Avoid over-tension that strains motors

---

### 2.4 Joint Limit Calibration

Each joint is restricted to safe movement bounds:

- Minimum angle (fully extended)
- Maximum angle (fully flexed)
- Firmware enforces these limits

---

## 3. Servo Mapping Table (Logical Model)

| Finger  | Joint        | Servo Index | Function |
|----------|-------------|-------------|----------|
| Thumb    | Base        | S1          | Opposition / rotation |
| Thumb    | Flexion     | S2          | Bend thumb |
| Index    | Flexion     | S3          | Primary grasp |
| Middle   | Flexion     | S4          | Stability support |
| Ring     | Flexion     | S5          | Grip reinforcement |
| Pinky    | Flexion     | S6          | Fine stability |

> NOTE: Actual servo mapping must be verified in hardware implementation.

---

## 4. Calibration Procedure (Startup Sequence)

### Step 1 — Power Initialization
- Ensure stable 5–6V power supply
- Avoid load on fingers during startup

### Step 2 — Servo Reset
- Move all servos to neutral (90° or defined center)
- Hold for stabilization

### Step 3 — Finger Extension Alignment
- Move all fingers to fully open position
- Confirm mechanical symmetry

### Step 4 — Save Zero Offsets
- Store calibration offsets in firmware memory (EEPROM or config file)

### Step 5 — Test Motion Sweep
- Slowly flex and extend each finger
- Ensure no mechanical obstruction

---

## 5. Calibration Data Storage

Calibration values are stored in:

- Firmware EEPROM (preferred)
- Configuration file (Python/ROS systems)
- Hardcoded fallback values (not recommended)

---

## 6. Safety Constraints During Calibration

- Never exceed servo physical limits
- Avoid sudden full-speed movements
- Always calibrate without external load
- Stop immediately if jitter or strain is observed

---

## 7. Future Improvements

- Auto-calibration using position sensors
- Force-based calibration correction
- Real-time drift compensation
- Machine learning-based motion tuning

---

## 8. Summary

Calibration ensures that the AmazingHand behaves consistently across:

- Power cycles
- Motion commands
- Different environments

Without calibration, tendon-driven robotic systems lose precision and repeatability.
