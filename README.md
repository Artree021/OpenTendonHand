<div align="center">

<img src="assets/logo/logo.svg" alt="OpenTendonHand" width="112" height="112" />

# OpenTendonHand

**An open-source, high-DOF tendon-driven dexterous hand.**

Mechanical design · Electronics · Firmware · Control — developed in the open.

[![Hardware license: CERN-OHL-S-2.0](https://img.shields.io/badge/hardware-CERN--OHL--S--2.0-blue)](LICENSE-HARDWARE)
[![Software license: MIT](https://img.shields.io/badge/software-MIT-green)](LICENSE)
[![Status: design phase](https://img.shields.io/badge/status-design%20phase-orange)](#project-status)
[![Contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen)](CONTRIBUTING.md)

[English](README.md) · [简体中文](README.zh-CN.md)

</div>

---

## Overview

OpenTendonHand is a dexterous robotic hand built around a **tendon-driven
architecture**: the actuators sit in the forearm, and Bowden-cable tendon
routing carries motion into the fingers. The hand itself stays light and slim,
while the actuation package keeps its mass where it is easy to support.

The project aims to publish one reproducible design — CAD, schematics,
firmware, control software and a build guide — so that labs, students and
hobbyists can build and modify a high degree-of-freedom hand without starting
from a blank page.

> **Status: early design phase.** The repository currently contains the project
> skeleton, design documentation structure and licensing. Mechanical and
> electronic documents are intentionally left as placeholders for now.

## Why tendon drive?

- **Mass where it matters.** Actuators live in the forearm, not in the fingers.
- **Small hands, many DOF.** Cable routing allows 20+ DOF in an
  anthropomorphic envelope.
- **Compliance for free.** Tendons and series elasticity make contact safer and
  easier to control than rigid linkages.
- **Serviceable.** Cables wear; the design should let you re-string a finger
  rather than throw a module away.

## Project status

| Area | Status |
| --- | --- |
| Documentation & repo scaffold | 🟡 In progress |
| Mechanical design (CAD, BOM) | ⬜ Not started |
| Electronics (schematic, PCB) | ⬜ Not started |
| Firmware | ⬜ Not started |
| SDK & high-level control | ⬜ Not started |
| Simulation | ⬜ Not started |

See the [roadmap](docs/roadmap.md) for milestones and [docs/design/requirements.md](docs/design/requirements.md)
for the parameter targets.

## Design targets

These are **targets**, not measurements. Values marked `TBD` are still open and
will be fixed during the requirements phase.

| Parameter | Target | Status |
| --- | --- | --- |
| Degrees of freedom | 20–24 (anthropomorphic, 5 fingers) | TBD |
| Actuation | Tendon-driven, remote actuators in forearm | TBD |
| Transmission | Bowden cable + differential pulley coupling | TBD |
| Hand mass (fingers + palm) | < 800 g | TBD |
| Fingertip force | ≥ 10 N | TBD |
| Sensing | Joint angle, fingertip force, motor current | TBD |
| Host interface | USB-C (plus a fieldbus for the actuator pack) | TBD |
| Materials | 3D-printed PA12/PETG + 6061 aluminium frame | TBD |

Full table: [docs/design/requirements.md](docs/design/requirements.md).

## Repository layout

```text
OpenTendonHand/
├── docs/                 Design, build and specification documents
│   ├── design/           Architecture, requirements, nomenclature
│   ├── mechanical/       Mechanical specifications and BOM
│   ├── electronics/      Electronics specifications and BOM
│   ├── software/         Control stack architecture
│   └── build/            Assembly and calibration guide
├── hardware/
│   ├── mechanical/       CAD, drawings, 3D-print files, BOM
│   └── electronics/      Schematics, PCB, gerbers, BOM
├── firmware/             Motor drivers, sensing, real-time control
├── software/             SDK, high-level control, simulation, tools
├── assets/               Logo, renders, photos
└── scripts/              Helper scripts (release packaging, checks)
```

CAD, PCB and mesh binaries are tracked with [Git LFS](#working-with-git-lfs).

## Roadmap

| Milestone | Scope |
| --- | --- |
| **M0** | Repository scaffold, licensing, documentation skeleton |
| **M1** | Requirements and kinematics frozen |
| **M2** | Mechanical design frozen, CAD released |
| **M3** | Electronics and firmware bring-up on a single finger |
| **M4** | Full-hand integration, teleoperation, benchmark report |
| **M5** | v1.0 release: complete build guide and assembly instructions |

## Getting started

Nothing to build yet — the first design files land at M2/M3. Once they do:

```bash
git clone https://github.com/Artree021/OpenTendonHand.git
cd OpenTendonHand
git lfs pull
```

## Documentation

| Document | What it covers |
| --- | --- |
| [docs/index.md](docs/index.md) | Documentation hub |
| [docs/design/overview.md](docs/design/overview.md) | System architecture and DOF allocation |
| [docs/design/requirements.md](docs/design/requirements.md) | Design targets and acceptance criteria |
| [docs/mechanical/](docs/mechanical/README.md) | Mechanical design notes *(placeholder)* |
| [docs/electronics/](docs/electronics/README.md) | Electronics design notes *(placeholder)* |
| [docs/software/architecture.md](docs/software/architecture.md) | Control stack and SDK |
| [docs/build/assembly-guide.md](docs/build/assembly-guide.md) | Assembly and calibration |
| [docs/roadmap.md](docs/roadmap.md) | Milestones |
| [docs/licensing.md](docs/licensing.md) | What license applies to what |

## Working with Git LFS

Binary design files are stored through Git LFS:

```bash
git lfs install
git lfs pull
```

If you add a new binary format, update `.gitattributes` in the same commit.

## Contributing

Contributions of any size are welcome — CAD, PCB review, firmware, control
theory, documentation, or just telling us the design will not work.

- Read [CONTRIBUTING.md](CONTRIBUTING.md) first.
- Open an issue before starting significant work, so we do not duplicate effort.
- Discussions and questions: use [GitHub Discussions](https://github.com/Artree021/OpenTendonHand/discussions).

This project follows a [Code of Conduct](CODE_OF_CONDUCT.md).

## License

| Part of the project | License |
| --- | --- |
| Hardware (CAD, drawings, PCB, BOM) | [CERN-OHL-S-2.0](LICENSE-HARDWARE) |
| Firmware and software | [MIT](LICENSE) |
| Documentation and images | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) |

See [docs/licensing.md](docs/licensing.md) for the details and the copyright notice.

## Citation

If you use this design in academic work, please cite it — see
[CITATION.cff](CITATION.cff).

```bibtex
@misc{opentendonhand,
  title  = {OpenTendonHand: An Open-Source High-DOF Tendon-Driven Dexterous Hand},
  author = {{OpenTendonHand Contributors}},
  year   = {2026},
  url    = {https://github.com/Artree021/OpenTendonHand}
}
```

## Acknowledgements

Design decisions will be documented as they are made, together with the papers
and open hardware projects they borrow from.
