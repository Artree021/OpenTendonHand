# Electronics Design

> **Status: placeholder.** No schematics exist yet. This document states what the
> electronics subsystem is responsible for, so the schematic and PCB work has a
> target.

## Scope

Three boards or board groups, depending on how the design splits:

1. **Hand controller** — host interface (USB-C), motion planning interface,
   safety supervisor, connection to the actuator pack.
2. **Motor driver channels** — one channel per tendon, with current sensing and
   encoder input. Either integrated into the controller or distributed in the
   actuator pack.
3. **Sensor boards** — fingertip force pads and joint angle sensing, if they are
   not integrated into the finger structure.

## Planned contents

| Section | Content | State |
| --- | --- | --- |
| Power tree | Input voltage, rails, current budget, protection | Not started |
| Motor drive | Topology (FOC vs. brushed PWM), current limits | Not started |
| Encoders | Type, resolution, interface | Not started |
| Sensing | Fingertip force, tendon tension, temperature | Not started |
| Host interface | USB-C, protocol, ESD protection | Not started |
| Safety | E-stop, watchdog, power-loss behaviour | Not started |
| PCB | Stackup, connectors, mechanical mounting | Not started |

## Interfaces

| Interface | Counterpart | Agreed? |
| --- | --- | --- |
| Motor + encoder connector | Actuator pack mechanics | No |
| Fingertip sensor footprint | Finger structure | No |
| Host protocol | Software control stack | No |
| Power input | Bench supply / battery | No |

## Design rules

- Every motor channel needs a hardware current limit that does not depend on
  firmware being alive.
- Power loss must relax the hand, not lock it.
- Connectors must be keyed — no orientation that can be forced in backwards.
- Test points on every rail; the first unit will be debugged by hand.

## Where the files will live

```text
hardware/electronics/
├── schematics/   Source project (KiCad) + PDF exports
├── pcb/          Layout files
├── gerbers/      Fabrication output + assembly files
└── bom/          Bill of materials
```

See [specs.md](specs.md) for the electrical parameter table.
