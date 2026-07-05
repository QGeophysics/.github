<div align="center">
  <h1>The QGeophysics Manifesto</h1>
  <p><strong>Subsurface Information • Open Standards • QGIS Ecosystem</strong></p>
</div>

---

## 1. The Problem

- **Discipline silos.** Seismic, potential-field, well-log, and electromagnetic geophysics each live in separate software ecosystems. Cross-discipline correlation is manual and error-prone.
- **The GIS–subsurface divide.** GIS platforms handle surface geography well but treat depth as a secondary attribute. Geophysical software handles depth well but treats spatial reference systems as an afterthought.
- **Locked-away computation.** Strong open-source computational libraries exist across geophysics, but most lack an interactive front end, limiting their use to script-based workflows.
- **Closed commercial platforms.** Proprietary interpretation suites restrict data formats, algorithmic extension, and long-term data access.

---

## 2. Core Objective

QGeophysics is an open, modular geophysical ecosystem built inside QGIS. It is envisioned to provide a single interpretation environment across subsurface disciplines, connecting surface geographic mapping with multi-dimensional subsurface data.

---

## 3. Architecture

**Hub-and-spoke design.** A single core module handles shared infrastructure; independent domain modules plug into it. No monolithic build.

| Component | Role |
|---|---|
| `QGeophysics-core` | Shared data registry, coordinate reference handling, spatial synchronization with QGIS, base infrastructure for module integration |
| Domain modules | Independent, optional extensions for each discipline |

Users install only the modules their work requires.

---

## 4. Domain Modules

| Module | Scope |
|---|---|
| `QGeophysics-seismic` | Seismic navigation, horizon/fault picking, attribute computation, seismic-to-well tie |
| `QGeophysics-wells` | Log ingestion, trajectory visualization, correlation tracks, petrophysical cross-plotting |
| `QGeophysics-potentialfields` | Gravity/magnetic grid handling, regional-residual separation, forward modeling |
| `QGeophysics-em` | Sounding curves, pseudosections, magnetotelluric workflows |
| `QGeophysics-seismology` | Hypocenter mapping, focal mechanisms, waveform inspection |

The module list is not fixed. New domains — geothermal, hydrogeophysics, environmental geophysics, or fields not yet defined — can be added without modifying the core.

---

## 5. Architectural Principles

- **Orchestration, not reinvention.** The core does not replace established open-source computational libraries. It wraps them with a consistent, interactive front end. Specific libraries in use are documented separately and may change over time; the framework's role as an orchestration layer does not.
- **Separation of interaction and computation.** Interactive review, parameter setup, and QC happen inside the ecosystem. Heavy computation (large inversions, full-volume processing) is delegated to external compute resources like local, HPC, or cloud as appropriate.
- **Open data standards.** Reading and writing rely on established open scientific and geospatial formats. As formats evolve or new open standards emerge, support extends to them; no format is treated as permanent or exclusive.
- **Interface neutrality.** The interpretation layer is defined by function, not by a specific technology. As interaction paradigms evolve, the ecosystem is expected to adapt its front end without changing its underlying architecture.

---

## 6. Why QGIS

- **Mature spatial foundation.** Coordinate reference handling, rendering, and vector/raster interoperability are already solved problems in QGIS, refined over two decades by a broad user base.
- **Independent governance.** QGIS is maintained by OSGeo, not a single commercial vendor. This removes a single point of commercial failure or re-licensing risk from the foundation layer.
- **Shared ceiling, accepted.** QGeophysics inherits both the strengths and the limits of QGIS. Improvements in QGIS's own capabilities (3D rendering, mesh handling, plugin infrastructure) extend to QGeophysics without additional effort. This dependency is a deliberate design choice.

---

## 7. Scope and Extension

QGeophysics defines a stable core and an open set of domain modules. Contribution by individuals, research groups, or organizations occurs at the module level, without requiring changes to core infrastructure. The ecosystem is expected to expand into domains not anticipated at the time of this document.
