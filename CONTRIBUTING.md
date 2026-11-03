# Contributing to OpenTendonHand

Thanks for wanting to help. This project is a hardware/software co-design, so
"contributing" means very different things depending on what you are good at —
all of them are useful.

- [Ways to contribute](#ways-to-contribute)
- [Before you start](#before-you-start)
- [Opening an issue](#opening-an-issue)
- [Pull requests](#pull-requests)
- [Style guides](#style-guides)
- [Design file conventions](#design-file-conventions)
- [Licensing of contributions](#licensing-of-contributions)
- [Code of conduct](#code-of-conduct)

## Ways to contribute

| Area | Examples |
| --- | --- |
| Mechanical | CAD parts, tendon routing, tolerance review, BOM alternatives |
| Electronics | Schematic review, motor driver design, sensor selection, PCB layout |
| Firmware | Real-time loop, encoder handling, CAN transport, safety limits |
| Software | SDK ergonomics, kinematics, teleoperation, simulation, tests |
| Documentation | Fixing errors, translating, writing the build guide |
| Review | Telling us a design cannot be manufactured or will not survive |

## Before you start

1. Check the [roadmap](docs/roadmap.md) and existing issues so you do not
   duplicate work.
2. For anything larger than a typo, **open an issue first**. Design changes that
   touch interfaces (mounting patterns, cable paths, message formats) need
   agreement before code or CAD is written.
3. Keep changes focused. One PR, one topic.

## Opening an issue

Use the templates under `.github/ISSUE_TEMPLATE/`:

- **Bug report** — something is broken or documented incorrectly.
- **Feature request** — new capability.
- **Design proposal** — a change to the mechanical or electrical architecture.

Include what you have already tried, and attach photos, screenshots or file
references where they help.

## Pull requests

1. Fork the repository and create a topic branch:
   `git switch -c feature/tendon-tensioner`.
2. Make the change, keeping commits reasonably small.
3. Update the documentation that the change invalidates — specifications, BOM
   rows, and the changelog entry under `## [Unreleased]`.
4. Run the checks that apply (`git lfs status`, any tests in `software/`).
5. Open the PR and describe **what changed and why**, not just what files moved.

Maintainers review for correctness, manufacturability, maintainability and
consistency with the design targets in
[docs/design/requirements.md](docs/design/requirements.md).

## Style guides

| Thing | Rule |
| --- | --- |
| Markdown | One sentence per line is not required; keep lines under ~100 characters |
| Commit messages | `area: short imperative summary` — e.g. `firmware: add encoder zeroing` |
| Branches | `feature/…`, `fix/…`, `docs/…` |
| Units | SI, millimetres for geometry, grams for mass |
| Dates | ISO 8601 (`2026-11-03`) |
| Language | English for code, comments, commit messages and docs; Chinese is fine in issues and discussions |

## Design file conventions

- **CAD** — export a neutral format (STEP AP214/AP242) next to the native file;
  native formats are welcome but must never be the only copy.
- **Naming** — `OTH-<subsystem>-<part>-<rev>`, e.g. `OTH-FINGER-INDEX-PROXIMAL-r2`.
- **Print files** — oriented and ready to slice, unit-checked, in
  `hardware/mechanical/print/`.
- **Schematics/PCB** — include the source project (KiCad preferred) and the
  generated PDF/Gerber output.
- **BOM** — one row per part, with a manufacturer part number when one exists.
- **Binaries** — anything over a few hundred kilobytes goes through Git LFS; see
  `.gitattributes`.

## Licensing of contributions

By contributing you agree that:

- hardware contributions (CAD, PCB, drawings) are licensed under
  **CERN-OHL-S-2.0**;
- firmware and software contributions are licensed under **MIT**;
- documentation contributions are licensed under **CC BY 4.0**.

Do not paste in code, models or images you do not have the right to relicense.
If you adapt someone else's design, say so in the PR and in the file header.

## Code of conduct

Participation is covered by [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md). Be
straight about technical problems, generous about people.
