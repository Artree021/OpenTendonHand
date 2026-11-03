# Mechanical Design

> **Status: placeholder.** The mechanical design has not started. This document
> defines what will live here, so the structure does not have to be invented
> later.

## Scope

The mechanical subsystem covers everything that has a shape: palm, finger
segments and joints, tendon routing and tensioning hardware, the coupling
between the hand and the actuator bundle, and the frame that holds the fingers
in an anthropomorphic arrangement.

## Planned contents

| Section | Content | State |
| --- | --- | --- |
| Kinematics | Joint axes, link lengths, range of motion | Not started |
| Fingers | Segment design, joint bearings, tendon anchors | Not started |
| Palm | Structural frame, tendon manifold, sensor board mounting | Not started |
| Tendon routing | Path, bend radii, friction budget, tensioning | Not started |
| Materials | Printed vs. machined, tolerances, wear surfaces | Not started |
| Manufacturing | Print orientation, post-processing, hardware list | Not started |

## Interfaces

| Interface | Counterpart | Agreed? |
| --- | --- | --- |
| Tendon bundle exit point | Electronics actuator pack | No |
| Sensor board footprint | Electronics fingertip PCB | No |
| Hand base mount | Wrist / test stand | No |
| Cable tension range | Firmware tension limits | No |

## Open design questions

- Antagonistic tendon pair vs. passive return spring per joint.
- Bearing choice for finger joints: plastic-on-plastic bushing, brass bushing,
  or miniature ball bearing.
- How to make a finger replaceable without re-stringing the whole hand.
- Thumb CMC joint topology.

## Where the files will live

```text
hardware/mechanical/
├── cad/        Native CAD + STEP exports
├── drawings/   Dimensioned PDFs for machined parts
├── print/      Oriented, ready-to-slice print files
└── bom/        Bill of materials
```

See [specs.md](specs.md) for the parameter table.
