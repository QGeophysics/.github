<div align="center">
  <h1>The QGeophysics Manifesto</h1>
  <p><strong>Subsurface Insight • Open Standards • Enterprise QGIS Ecosystem</strong></p>
</div>

---

## 1. The Problem to Address

The subsurface interpretation landscape is structurally broken, creating severe friction across industry enterprises, independent practitioners, and academic institutions.

*   **Discipline Silos:** Geophysical domains are trapped in segregated software ecosystems. Seismologists, potential-field geophysicists, and petrophysicists operate in isolated environments, making truly integrated, multi-physics subsurface correlation inefficient and difficult.
*   **The GIS-Subsurface Divide:** Traditional GIS platforms excel at surface geography ($X, Y$) and spatial data infrastructures but have historically treated depth ($Z$) and time ($T$) as secondary attributes. Conversely, specialized geophysical software treats spatial geodetic reference systems as an afterthought.
*   **Inaccessible Open-Source Power:** Immense computational power exists within open-source Python frameworks (`SimPEG`, `ObsPy`, `Fatiando a Terra`, `welly`, etc.). However, these libraries lack cohesive, professional Graphical User Interfaces (GUIs), restricting their use to code-heavy environments and preventing rapid visual QC or real-time exploration.
*   **Commercial Lock-In:** Proprietary enterprise interpretation suites are closed-source and inflexible. They often price out research initiatives and mid-sized enterprise teams while creating restrictive barriers around data formats and custom algorithmic extension.

---

## 2. The Vision & Architectural Paradigm

### The Core Objective
Build an open, modular, and extensible geophysical ecosystem inside QGIS that delivers an industry-grade user experience across all subsurface disciplines. `qgeophysics` is envisioned to act as the unified GUI orchestration layer, bridging enterprise geographic mapping with multi-dimensional subsurface interpretation.

### Hub-and-Spoke Architecture
To guarantee stability and scalability without succumbing to software bloat, `qgeophysics` strictly rejects a monolithic design in favor of a modular, decoupled framework:

*   **`qgeophysics-core`:** The foundational installation. It establishes a unified subsurface data registry, manages spatial-to-depth synchronization, coordinates complex CRS transformations, and provides global visualization standards (color maps, layout viewports, cross-section canvases).
*   **Domain Modules:** Independent, pluggable extensions (`qgeophysics-seismic`, `qgeophysics-wells`, `qgeophysics-potentialfields`, etc.) that interface cleanly with the core framework. Users need to install only the specific disciplinary capabilities their workflows demand.

---

## 3. Extensibility & Research Integration

While `qgeophysics` leverages established standard libraries for foundational tasks, the architecture is fundamentally open to innovation. The modular design ensures that new computational methods, experimental algorithms, and active academic research can be integrated directly into the workspace.

When a novel numerical approach solves a practical subsurface problem, the framework provides a clear, structured GUI pathway to implement and validate it alongside standard industry workflows. Innovation is not a closed door; applied research and practical experimentation are core contributors to the ecosystem's evolution.

---

## 4. Unbounded Domain Scope

`qgeophysics` defines an open, extensible domain architecture. While active development anchors around foundational geophysical pillars, the ecosystem is explicitly structured to scale into any subsurface or spatial-scientific domain.

### Foundational Pillars (Active Core Trajectory)
*   **Seismic Interpretation (`qgeophysics-seismic`):** 2D/3D navigation, horizon and fault picking, attribute computation, and interactive seismic-to-well tie calibration.
*   **Well & Borehole Analytics (`qgeophysics-wells`):** Multi-format log ingestion (LAS/DLIS), 3D trajectory visualization, customizable correlation tracks, and petrophysical cross-plotting.
*   **Potential Fields (`qgeophysics-potentialfields`):** Gridded scalar field management (Gravity and Magnetics), regional/residual filtering, and profile forward modeling.
*   **Electrical & Electromagnetics (`qgeophysics-em`):** Sounding curve visualization, pseudosections, and magnetotelluric (MT) workflow integration.
*   **Seismology & Geomechanics (`qgeophysics-seismology`):** Earthquake hypocenter mapping, focal mechanism plotting, waveform inspection, and stress-field visualization.

### Unlimited Ecosystem Expansion
Because `qgeophysics-core` abstracts the underlying subsurface data structures and spatial-to-depth rendering engines, the ecosystem natively supports unbounded expansion. Community developers, enterprise R&D teams, and academic researchers are most welcome to build custom domain modules without altering or compromising the core infrastructure.

---

## 5. Architectural Principles

To ensure long-term sustainability and future-proof the platform against technological shifts, `qgeophysics` enforces strict structural standards:

*   **Orchestration Over Reinvention:** We do not waste engineering hours rewriting mature computational libraries or standard file parsers. `qgeophysics` serves as the premier UI, visualization, and orchestration bridge, wrapping trusted open-source backends (`segyio`, `welly`, `Harmonica`, `SimPEG`, `ObsPy`, `pyGIMLi`) to transform script-only engines into interactive graphical tools.
*   **Scalable Compute Pipelines:** The desktop canvas is optimized for interactive interpretation, visual correlation, parameter setup, and QC. Heavy, large-scale computational processing is cleanly decoupled and designed to delegate execution to local high-performance computing (HPC) clusters or cloud pipelines.
*   **Uncompromising Open Standards:** The platform strictly reads and writes universally recognized scientific and geospatial data standards (SEG-Y, LAS, NetCDF, GeoTIFF, OME-Zarr, I3S), ensuring zero vendor lock-in and complete data sovereignty for enterprise teams.
