# Firmware

> Empty for now. Target MCU, RTOS choice and toolchain are `TBD`.

## Responsibility

The firmware owns the hard real-time loop and the hard safety limits:

- closed-loop motor control per tendon channel;
- encoder reading and zeroing;
- tendon tension estimation and limit enforcement;
- watchdog and power-loss handling;
- a framed command/telemetry protocol to the host.

## Planned layout

```text
firmware/
├── boards/     Board support: pin maps, clock setup, linker scripts
├── lib/        Shared drivers (encoders, current sense, protocol)
└── README.md
```

## Non-negotiables

1. A hardware current limit exists independently of the firmware; the firmware
   limit is a second line of defence, not the first.
2. Watchdog resets the outputs to a safe state.
3. Communication timeouts relax the hand within a documented time.
4. Every tunable parameter has a documented default and a documented range.

## Toolchain

`TBD` — will be pinned in a `toolchain.md` with exact versions, because "it
builds on my machine" is not a build instruction.
