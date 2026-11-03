# Design Overview

> Status: **draft** — architecture level only. Numbers are provisional and live
> in [requirements.md](requirements.md).

## System decomposition

The hand is split into two physically separated assemblies, connected by a
tendon bundle:

1. **The hand** — palm, five fingers, tendon paths, fingertip sensors. Low mass,
   no motors.
2. **The actuator pack** — motors, gearboxes, spool drums, tensioners, driver
   electronics. Mounted on the forearm or on a bench stand for early bench tests.
3. **The controller** — a host-connected board that closes the position/force
   loops and exposes a stable API.

```text
            +-----------------------------------+
            |   Host: ROS 2 / Python SDK / GUI  |
            +------------------+----------------+
                               | USB-C
            +------------------v----------------+
            |      Hand controller board        |
            |  motor channels | encoders | ADC  |
            +--------+------------------+-------+
                     | PWM / FOC        | sensor bus
            +--------v--------+  +------v--------+
            |  Actuator pack  |  | Fingertip     |
            |  (forearm)      |  | sensors       |
            +--------+--------+  +---------------+
                     | tendon bundle (Bowden)
            +--------v--------------------------+
            |  Hand: palm + 5 fingers           |
            +-----------------------------------+
```

## Degrees of freedom

Target: anthropomorphic, 20–24 actuated DOF. Exact joint set is decided at M1.

| Finger | Joints | DOF | Notes |
| --- | --- | --- | --- |
| Thumb | CMC (flex/ext, abd), MCP, IP | 3–4 | Opposition is the hard part; CMC rotation is `TBD` |
| Index | MCP flex, MCP abd, PIP, DIP | 4 | DIP may be coupled to PIP |
| Middle | MCP flex, MCP abd, PIP, DIP | 4 | |
| Ring | MCP flex, MCP abd, PIP, DIP | 4 | |
| Little | MCP flex, MCP abd, PIP | 3 | Often underactuated |
| **Total** | | **18–19 flex/abd + coupling** | Final count: `TBD` |

Underactuation is allowed — and expected — within a finger (one tendon driving
PIP and DIP through a differential), but not across fingers.

## Actuation and transmission

- **Motors** in the actuator pack, one spool per tendon.
- **Tendon path** through PTFE-lined Bowden conduits from the pack to each
  finger; minimum bend radius is a design constraint, not an afterthought.
- **Tensioning** at the pack end, reachable without disassembling the hand.
- **Return force** — either an antagonistic tendon pair or a passive spring per
  joint. Decision at M1 (`TBD`).
- **Compliance** — series elasticity in the tendon or at the drum, so impacts do
  not turn into gearbox failures.

## Sensing

| Quantity | Candidate | Status |
| --- | --- | --- |
| Motor position | Magnetic encoder on the motor shaft | TBD |
| Tendon tension / joint torque | Load cell or current sensing | TBD |
| Fingertip force | Resistive or capacitive pad | TBD |
| Contact / proximity | Optional | TBD |

## Design principles

1. **Modular fingers.** A finger should be replaceable without cutting every
   tendon in the hand.
2. **Serviceable tendons.** Re-stringing is a maintenance task, not a rebuild.
3. **Printable where possible, machined where necessary.** Load paths get metal;
   shapes get printed.
4. **Backdrivable.** You must be able to move the hand by hand without damaging
   it.
5. **Fail safe.** Loss of power means the hand relaxes, not that it clamps.
6. **Documented as built.** Every revision update ships with the doc change that
   explains it.

## Open questions

Tracked as issues; kept here so the architecture does not pretend to be settled.

- Antagonistic tendons vs. passive return springs for finger extension.
- Coupled DIP or independent DIP actuation.
- Thumb CMC: 2-DOF universal joint vs. 3-DOF ball joint with tendon routing.
- Wrist: separate module or out of scope for v1.
- Fieldbus inside the actuator pack: CAN-FD vs. RS-485.
