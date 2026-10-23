# Prokon Projects

Structural analysis and member design in **Prokon** (W5.0), including a linked beam analysis → section design calculation.

## Featured: RC beam analysis and section design

Two Prokon modules used together, as in a design office calculation package:

**1. [Simple span beam](Simple%20span%20beam) (module A11: single-span beam analysis)**

| Input | Value |
|---|---|
| Span | 5.0 m, fixed at the left support, pinned at the right |
| Section | 220 × 220 mm RC, I = 182 × 10⁻⁶ m⁴, E = 25 GPa |
| Loads | Linearly varying distributed load, point load and applied moments (see output) |
| ULS load factors | 1.4 and 1.6 (per load row) |

| Result | Value |
|---|---|
| Maximum bending moment | **15.79 kN·m** at 4.0 m |
| Maximum shear force | **8.31 kN** at the fixed support |
| Maximum deflection | **2.89 mm** at 3.1 m (span/1730) |

**2. [beam section](beam%20section) (module C22: concrete section design)** uses the A11 results as design actions:

| Input | Value |
|---|---|
| M<sub>u</sub> / V<sub>u</sub> | 15.79 kN·m / 8.31 kN |
| Section | 220 × 220 mm, 40 mm to the reinforcement centroid |
| Materials | f′c = 30 MPa, f<sub>y</sub> = 460 MPa (main), f<sub>yv</sub> = 250 MPa (links) |
| Design code | ACI 318-14 |

| Result | Value |
|---|---|
| Moment capacity | 59.1 kN·m |
| Required tension steel | 223 mm² (A<sub>s,min</sub> = 121 mm²) |
| Suggested bars | 3Y10 (236 mm²) or 2Y12 (226 mm²) |
| Concrete shear capacity V<sub>c</sub> | 26.3 kN > 8.31 kN, so nominal links only |

| A11 beam analysis | C22 section design |
|---|---|
| ![A11 output](Simple%20span%20beam/images/a11-beam-analysis.png) | ![C22 output](beam%20section/images/c22-section-design.png) |

Full outputs: [A11 Output.pdf](Simple%20span%20beam/Output.pdf) · [C22 output.pdf](beam%20section/output.pdf) (8 pages with detailed ACI 318 calculations)

## Other projects

| Project | Description | Status |
|---|---|---|
| [custom beam](custom%20beam) | User-defined cross-section in the section-properties module (`.G01`) | 🟡 Input file only |
| [Walkway](Walkway) | 3D frame model of a walkway in Prokon Sumo | 🟡 Model only, no output exported |

## Opening the files

Open the input files in the matching **Prokon** module (`.A11` single-span beam, `.C22` concrete section, `.G01` section properties, `.Sumo` frame). The PDF outputs can be viewed directly on GitHub.
