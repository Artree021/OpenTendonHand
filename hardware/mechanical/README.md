# Mechanical Design Files

> Empty for now — the mechanical design has not started. This README describes
> what goes where so files land in a predictable place.

| Directory | Contents |
| --- | --- |
| `cad/` | Native CAD (Fusion/FreeCAD/SolidWorks) plus STEP AP214 exports |
| `drawings/` | Dimensioned 2D drawings (PDF) for machined or laser-cut parts |
| `print/` | 3D-print files (STL/3MF), pre-oriented and ready to slice |
| `bom/` | Mechanical bill of materials (CSV + xlsx) |

## Rules

- Every part has a neutral export next to the native file.
- Part naming: `OTH-<subsystem>-<part>-<rev>`, e.g. `OTH-FINGER-INDEX-PROXIMAL-r1`.
- Print files are oriented as they should be printed and include the layer
  height and material in the file name: `OTH-FINGER-INDEX-PROXIMAL-r1_PETG_0.2.stl`.
- Large binaries go through Git LFS; the rules are already in `.gitattributes`.

Related documentation: [docs/mechanical/](../../docs/mechanical/README.md) and
[specs](../../docs/mechanical/specs.md).
