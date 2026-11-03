# OpenTendonHand Documentation

Start here. The documentation is organised by subsystem, mirroring the
repository layout.

## Read in this order

1. [Project overview](../README.md) — what the hand is and why it exists.
2. [Design overview](design/overview.md) — how it is put together.
3. [Requirements](design/requirements.md) — the numbers we are designing to.
4. [Roadmap](roadmap.md) — where the project is and what comes next.

## Design

| Document | Contents |
| --- | --- |
| [design/overview.md](design/overview.md) | System architecture, DOF allocation, design principles |
| [design/requirements.md](design/requirements.md) | Functional requirements, performance targets, acceptance criteria |
| [design/nomenclature.md](design/nomenclature.md) | Terms, joint names, coordinate conventions |

## Subsystems

| Document | Contents | State |
| --- | --- | --- |
| [mechanical/README.md](mechanical/README.md) | Fingers, palm, tendon routing, materials | Placeholder |
| [mechanical/specs.md](mechanical/specs.md) | Mechanical parameter table | Placeholder |
| [electronics/README.md](electronics/README.md) | Controller board, actuator pack, sensing | Placeholder |
| [electronics/specs.md](electronics/specs.md) | Electrical parameter table | Placeholder |
| [software/architecture.md](software/architecture.md) | Control stack, SDK, interfaces | Draft |

## Build and operate

| Document | Contents | State |
| --- | --- | --- |
| [build/assembly-guide.md](build/assembly-guide.md) | Step-by-step assembly, tendon tensioning | Placeholder |
| [build/calibration.md](build/calibration.md) | Encoder zeroing, tendon preload, force calibration | Placeholder |

## Project

| Document | Contents |
| --- | --- |
| [roadmap.md](roadmap.md) | Milestones and exit criteria |
| [licensing.md](licensing.md) | Which license applies to which files |
| [../CONTRIBUTING.md](../CONTRIBUTING.md) | How to contribute |
| [../CHANGELOG.md](../CHANGELOG.md) | Release history |

## Conventions

- Units: SI, millimetres for geometry, grams for mass, newtons for force.
- Joint naming: `<finger>_<joint>` — e.g. `index_mcp`, `thumb_ip`.
- Left/right handedness is always stated explicitly; nothing is assumed to be
  symmetric by default.
- Files that exist but are not written yet contain a `Status: placeholder`
  banner. If a document stops matching the design, fix the document first.
