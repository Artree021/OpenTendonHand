# Roadmap

Milestones are cumulative. Each one has an exit criterion that can be checked by
someone who is not the author.

## M0 — Repository scaffold

**Status:** done (this commit)

- [x] Repository structure and documentation hub
- [x] Licensing (hardware / software / docs)
- [x] Contribution guide, code of conduct, security policy
- [x] Issue and pull-request templates
- [x] Git LFS configuration

**Exit:** the repository is public, readable, and a stranger knows what this is
within one minute.

## M1 — Requirements and kinematics frozen

- [ ] Requirements table filled; every `TBD` either resolved or explicitly
      dropped
- [ ] DOF allocation fixed and documented
- [ ] Tendon routing concept sketches
- [ ] Forward/inverse kinematics model of the hand (even if planar)

**Exit:** `docs/design/requirements.md` has no unresolved *Must* row, and a
reviewer has signed off in an issue.

## M2 — Mechanical design frozen

- [ ] Full CAD assembly, parametric where it matters
- [ ] STEP exports + native files, drawings for machined parts
- [ ] Print files oriented and test-printed
- [ ] BOM with real part numbers and prices
- [ ] Tolerance and tendon-path review

**Exit:** a volunteer builds one finger from the published files without asking
questions that are not answered in the docs.

## M3 — Electronics and firmware bring-up

- [ ] Schematic and PCB for the controller and one actuator channel
- [ ] Gerbers, BOM, assembly notes
- [ ] Firmware: FOC or PWM motor loop, encoder read, safety limits
- [ ] Single-finger closed-loop position test

**Exit:** one finger tracks a step input with the documented repeatability.

## M4 — Full-hand integration

- [ ] All fingers assembled, tendons tensioned, calibrated
- [ ] High-level API and Python SDK
- [ ] Teleoperation demo
- [ ] Benchmark report: force, speed, repeatability, mass

**Exit:** benchmark report published with raw logs.

## M5 — v1.0 release

- [ ] Complete build guide with photos
- [ ] Calibration and maintenance procedures
- [ ] Tagged release, archived on Zenodo with a DOI
- [ ] Errata section for known issues

**Exit:** release notes list every known limitation.

## Out of scope for v1

- Tactile skin with high spatial resolution
- In-hand manipulation policies
- Wireless operation
- Wrist module

These are candidates for v2 and are tracked as issues, not promises.
