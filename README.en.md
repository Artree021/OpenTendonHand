<div align="right">

[![README-EN](https://img.shields.io/badge/README-English-blue)](README.en.md) [![README-ZH](https://img.shields.io/badge/README-%E4%B8%AD%E6%96%87-red)](README.md)

</div>

# OpenTendonHand

**An open-source high-DOF tendon-driven dexterous hand**

This repository publishes the mechanical models, PCB files and design
documentation of a tendon-driven dexterous hand, for study, reproduction and
further development.

![The hand](images/hand-photo.jpg)

## Contents

| Directory | Contents |
| --- | --- |
| `solidworks/` | SolidWorks 2025 source models: 60 parts + 8 assemblies, features intact |
| `step/` | Whole-hand STEP, opens in any CAD software |
| `pcb/` | PCB, with schematic and layout published on OSHWHub |
| `images/` | Photos, PCB renders and schematic |
| `docs/` | Design document |

## PCB

The controller board (AD7606B) is published on OSHWHub (Chinese), together with
its schematic, PCB, BOM and fabrication files:

**https://oshwhub.com/shusheng60602/ad7606b**

**3D render**
![3D render](images/ad7606b-3d-render.png)

**PCB front**
![PCB front](images/ad7606b-pcb-front.png)

**Schematic**
![Schematic](images/ad7606b-schematic.png)

## Notes

- Units: millimetres (mm).
- Just want to look at the structure, or use another CAD package: open `step/`.
- Want to modify the design: open `solidworks/`, the features are intact.
- This is a design archive. Files are published as-is and are not actively
  maintained.

## License

Mechanical models, PCB files and documentation are released under
[CERN-OHL-S-2.0](LICENSE): free to use, modify and manufacture; modified design
files must be published under the same license. Personal builds and academic use
are unrestricted.

## Feedback

Issues are welcome and will be recorded.
