# Security Policy

This project produces a physical machine. "Security" here means both software
and, more importantly, **physical safety**.

## Reporting a vulnerability

Please **do not** open a public issue for:

- a software vulnerability (command injection in a tool, unsafe deserialisation,
  a dependency with a known CVE);
- a hardware safety defect — a failure mode that can injure a person, damage the
  hand, or cause a fire (motor stall without current limit, tendon fraying into
  a pinch point, a connector that can be plugged in backwards).

Report privately through
[GitHub Security Advisories](https://github.com/Artree021/OpenTendonHand/security/advisories/new)
or by email to `TBD@example.com` (placeholder — replace before release).

Include: what you did, what happened, what you expected, and the revision or
commit you were on. For hardware issues, photos help.

## What to expect

- Acknowledgement within 7 days.
- A fix or a documented mitigation for confirmed safety issues before the next
  tagged release.
- Credit in the release notes and `SECURITY.md`, unless you prefer otherwise.

## Scope

In scope: firmware, host software, build instructions that lead to an unsafe
build, and undocumented failure modes.

Out of scope: modified designs that removed current limits, disabled the
emergency stop, or replaced safety-relevant parts with unverified equivalents.

## Safety notes for builders

- The actuator pack can produce enough torque to injure a finger. Keep the
  emergency stop reachable during first power-on.
- Never leave the hand powered and unattended during commissioning.
- Tendons under tension store energy; cut them slowly and wear eye protection.
