# Hardware

Design files for the physical hand. Everything in this directory is licensed
under [CERN-OHL-S-2.0](../LICENSE-HARDWARE).

| Directory | Contents | State |
| --- | --- | --- |
| [mechanical/](mechanical/README.md) | CAD, drawings, print files, mechanical BOM | Empty — design not started |
| [electronics/](electronics/README.md) | Schematics, PCB, Gerbers, electronics BOM | Empty — design not started |

## File conventions

- One revision per part, encoded in the file name:
  `OTH-<subsystem>-<part>-<rev>.step`
- Always ship a neutral format (STEP) alongside the native file.
- Text files (KiCad, source code) are versioned normally; binaries go through
  Git LFS as configured in [.gitattributes](../.gitattributes).
- A released design is a git tag, not a folder named `final_v3`.

## Status

The mechanical and electronic descriptions are intentionally blank for now. The
directory structure exists so that files land in a predictably named place
instead of in a chat message.
