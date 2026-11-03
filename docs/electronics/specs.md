# Electrical Specifications

> **Status: placeholder.** All values `TBD`.

## Power

| Parameter | Target | Actual | Verified |
| --- | --- | --- | --- |
| Input voltage (V) | TBD | TBD | No |
| Peak current (A) | TBD | TBD | No |
| Idle current (A) | TBD | TBD | No |
| Logic rails | TBD | TBD | No |
| Motor rail | TBD | TBD | No |
| Protection | TBD (fuse / eFuse / TVS) | TBD | No |

## Motor channels

| Parameter | Value | Status |
| --- | --- | --- |
| Channels | One per tendon (≈ 20–24) | TBD |
| Motor type | TBD (BLDC / brushed DC) | TBD |
| Drive topology | TBD (FOC / PWM H-bridge) | TBD |
| Current sensing | TBD | TBD |
| Control rate | ≥ 500 Hz (per channel) | TBD |
| Encoder interface | TBD (SPI / ABI / I²C) | TBD |
| Encoder resolution | TBD (counts/rev) | TBD |

## Host interface

| Parameter | Value | Status |
| --- | --- | --- |
| Physical | USB-C | Proposed |
| Protocol | TBD (CDC / vendor HID / custom) | TBD |
| Update rate | TBD (Hz) | TBD |
| Isolation | TBD | TBD |

## Sensing

| Sensor | Range | Resolution | Interface | Status |
| --- | --- | --- | --- | --- |
| Fingertip force | TBD | TBD | TBD | TBD |
| Tendon tension | TBD | TBD | TBD | TBD |
| Temperature | TBD | TBD | TBD | TBD |

## EMC and safety

To be defined with the first schematic: ESD on external connectors, motor noise
containment, watchdog behaviour, and the emergency-stop path.
