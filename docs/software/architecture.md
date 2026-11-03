# Software Architecture

> Status: **draft** — interfaces only. No implementation yet.

## Layers

```text
+---------------------------------------------+
| Applications: teleoperation, grasp demos    |
+---------------------------------------------+
| SDK: Python (primary), C++ bindings later   |
+---------------------------------------------+
| Control: joint space, tendon space, safety  |
+---------------------------------------------+
| Transport: USB / CAN, message framing       |
+---------------------------------------------+
| Firmware: motor loop, encoders, limits      |
+---------------------------------------------+
```

## Design rules

1. **The safety supervisor never depends on the application layer.** Limits live
   in firmware and in the controller, not only in the Python script.
2. **Tendon space is the truth.** Joint angles are derived; the firmware owns
   tendon length and tension.
3. **Deterministic channels.** Commands carry timestamps; stale commands are
   rejected rather than executed late.
4. **Everything is observable.** Every control loop can be logged without
   changing code.

## Planned API surface

Sketch only — the names will change:

```python
from opentendonhand import Hand

hand = Hand.open()                 # discovers the USB device
hand.enable()                      # energises motors, applies soft limits
hand.home()                        # tendon zeroing routine

hand.finger("index").command(q=[0.0, 0.4, 0.3])   # radians, per joint
hand.grasp("power", effort=0.5)                   # high-level primitive

state = hand.read()                # joint positions, tendon tensions, forces
hand.disable()                     # relax
```

## Repository layout for software

```text
software/
├── sdk/python/     Python package
├── control/        Control algorithms (kinematics, grasp primitives)
├── simulation/     URDF / MuJoCo / Isaac models and test scenes
└── tools/          Calibration, logging, plotting
```

## Open questions

- Joint-space command interface vs. tendon-space, or both.
- Where grasp primitives live: firmware, controller, or host.
- Real-time guarantees for the USB transport; whether a dedicated bridge is
  needed for 500 Hz control.
- Simulation model fidelity: how much of the tendon elasticity is worth
  modelling.
