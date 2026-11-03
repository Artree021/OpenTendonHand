# Licensing

This project uses three licenses, because hardware, code and prose are
different things and each has a license that fits.

| Path | Content | License |
| --- | --- | --- |
| `hardware/**` | CAD, drawings, 3D-print files, PCB, Gerbers, BOM | [CERN-OHL-S-2.0](../LICENSE-HARDWARE) |
| `firmware/**`, `software/**`, `scripts/**` | Source code | [MIT](../LICENSE) |
| `docs/**`, `assets/**`, root `*.md` | Documentation, images, diagrams | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) |

Where a file is ambiguous, the license of the directory wins. If a file inside
an MIT directory is clearly a mechanical drawing, tell us — we will move it.

## Why these three

- **CERN-OHL-S-2.0** is a strongly reciprocal open hardware license: it keeps
  derivative hardware open, requires shipping the design files with a product,
  and is written for hardware rather than being a software license bent into
  shape.
- **MIT** keeps the software usable by anyone, including companies embedding it
  in a product, with no strings.
- **CC BY 4.0** lets people reuse and translate the documentation with
  attribution only.

## Copyright notice

```text
Copyright (c) 2026 OpenTendonHand contributors

Hardware design files: CERN Open Hardware Licence Version 2 - Strongly
Reciprocal. See LICENSE-HARDWARE.

Software: MIT License. See LICENSE.

Documentation: Creative Commons Attribution 4.0 International.
```

## What CERN-OHL-S means in practice

If you build and sell a hand based on these files, you must:

- make the complete design files available to recipients, under the same
  license;
- keep notices and attribution intact;
- state the modifications you made.

Building one for yourself, in your lab, is unrestricted.

## Contributions

Inbound contributions are accepted under the license of the directory they land
in. See [CONTRIBUTING.md](../CONTRIBUTING.md#licensing-of-contributions).

## Trademark

The name **OpenTendonHand** and the logo identify the project. Forks are
welcome and should use their own name; see [TRADEMARK.md](../TRADEMARK.md).
