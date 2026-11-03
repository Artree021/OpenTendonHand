# Requirements and Design Targets

> Status: **draft / placeholder**. Everything here is a target, not a
> measurement. Values marked `TBD` are open — they are the agenda for milestone
> M1.

## How to read this document

- **FR** — functional requirement: what the hand must be able to do.
- **PT** — performance target: a number with a tolerance.
- **CN** — constraint: a hard boundary (cost, process, safety).
- **AC** — acceptance criterion: how we verify a requirement is met.

A target is only real once it has a verification method. Rows without an `AC`
are still under discussion.

## Functional requirements

| ID | Requirement | Priority | Status |
| --- | --- | --- | --- |
| FR-01 | Anthropomorphic five-finger hand, 20–24 actuated DOF | Must | Proposed |
| FR-02 | Power grasp of common objects (bottle, tool handle, ball) | Must | TBD |
| FR-03 | Precision pinch between thumb and index | Must | TBD |
| FR-04 | Independent finger motion (no mechanical coupling across fingers) | Must | TBD |
| FR-05 | Per-joint position control with tendon tension feedback | Must | TBD |
| FR-06 | Passive compliance in the tendon path | Should | TBD |
| FR-07 | Replaceable finger module; re-tensioning without full disassembly | Must | TBD |
| FR-08 | Hand relaxes on power loss | Must | TBD |
| FR-09 | Host API over USB-C, usable from Python | Should | TBD |
| FR-10 | Teleoperation from a handheld controller or glove | Could | TBD |

## Performance targets

| ID | Parameter | Target | Tolerance | Status |
| --- | --- | --- | --- | --- |
| PT-01 | Actuated DOF | 20–24 | — | TBD |
| PT-02 | Hand mass (palm + fingers, no tendons) | < 800 g | — | TBD |
| PT-03 | Fingertip force (single finger, blocked) | ≥ 10 N | ±10 % | TBD |
| PT-04 | Finger flexion time (full range) | ≤ 0.5 s | — | TBD |
| PT-05 | Joint position resolution | ≤ 0.5° | — | TBD |
| PT-06 | Position repeatability (unloaded) | ≤ 1° | — | TBD |
| PT-07 | Payload, power grasp | TBD | — | TBD |
| PT-08 | Control loop rate | ≥ 500 Hz | — | TBD |
| PT-09 | Hand envelope | Adult-male anthropomorphic | — | TBD |
| PT-10 | Continuous operating time (on battery, if any) | TBD | — | TBD |

## Constraints

| ID | Constraint | Status |
| --- | --- | --- |
| CN-01 | Buildable with consumer FDM printing plus off-the-shelf hardware | Proposed |
| CN-02 | Electronics: JLCPCB/PCBWay-compatible 2–4 layer stackup | Proposed |
| CN-03 | BOM cost target for a single hand | TBD |
| CN-04 | No custom injection moulds, no exotic processes | Proposed |
| CN-05 | All design files published under an open license | Must |
| CN-06 | Firmware buildable from source with a documented toolchain | Must |

## Acceptance criteria

| ID | Verification |
| --- | --- |
| AC-01 | Range-of-motion measured per joint on a built unit, compared to anthropometric data |
| AC-02 | Blocked fingertip force measured with a load cell at 3 finger poses |
| AC-03 | Ten-minute grasp-and-lift cycle without tendon slip > 2 mm |
| AC-04 | Repeatability test: 100 moves to a setpoint, position logged |
| AC-05 | Power-cut test: hand opens within 1 s, no component damage |

## Anthropometric basis

Hand dimensions follow a 50th-percentile adult male for v1, with the intent to
publish a scaling table later. Reference values (`TBD` — to be filled from a
cited source):

| Measure | Value (mm) | Source |
| --- | --- | --- |
| Hand length (wrist crease → middle fingertip) | TBD | TBD |
| Palm width | TBD | TBD |
| Index finger length | TBD | TBD |
| Thumb length | TBD | TBD |
