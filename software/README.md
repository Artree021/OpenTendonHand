# Software

> Empty for now — interfaces are sketched in
> [docs/software/architecture.md](../docs/software/architecture.md).

## Planned layout

| Directory | Contents |
| --- | --- |
| `sdk/python/` | Python package: device discovery, command API, state streaming |
| `control/` | Kinematics, tendon mapping, grasp primitives |
| `simulation/` | URDF, MuJoCo/Isaac scenes, test models |
| `tools/` | Calibration, logging, plotting, firmware flashing helpers |

## Principles

- One obvious way to do the common thing: `Hand.open()`, then read/write.
- No hidden threads in the SDK; explicit `poll()` or an opt-in background reader.
- Every command is idempotent or clearly documented as not.
- Errors are values, not silent log lines.

## Status

Nothing is implemented. The SDK table above is a plan, not a promise of stable
API. Anything published before v0.1.0 will break without notice.
