# Electronics Design Files

> Empty for now — the electronics design has not started. This README describes
> what goes where.

| Directory | Contents |
| --- | --- |
| `schematics/` | Source project (KiCad preferred) and PDF exports |
| `pcb/` | Board layout files |
| `gerbers/` | Fabrication output, drill files, assembly (POS/BOM) files |
| `bom/` | Electronics bill of materials |

## Rules

- Schematic PDF is always exported with the source project; a PDF alone is not a
  design file.
- Gerbers are zipped per board and per revision: `OTH-CTRL-r1-gerbers.zip`.
- Include a `README` next to each board with the fabrication parameters
  (stackup, thickness, finish, impedance if any).
- Include test points and their expected voltages in the board README. Future you
  will debug this board at 2 a.m.

Related documentation: [docs/electronics/](../../docs/electronics/README.md) and
[specs](../../docs/electronics/specs.md).
