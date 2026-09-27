# Physical Geography Sim

**A browser-based, drag-to-steer hurricane and multi-hazard simulation for physical geography education**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![WebGL](https://img.shields.io/badge/WebGL-Three.js-orange)](https://threejs.org/)
[![No Install](https://img.shields.io/badge/No%20Install-Open%20in%20Browser-success)](#quick-start)

Students steer a hurricane, intensify it, place secondary hazards, and watch coastal flooding, wind damage, orographic precipitation, and settlement impacts unfold in real time over elevation-informed terrain.

---

## Quick Start

1. Open [`Physical-Geography-sim.html`](Physical-Geography-sim.html) in any modern browser (Chrome, Firefox, Edge, Safari).
2. No installation, plugins, or accounts required.
3. Or serve the folder as a static site:

```bash
npx serve .
# or
python -m http.server 8000
```

Then visit the local URL shown in the terminal.

---

## What It Does

| Capability | Description |
|------------|-------------|
| **Hurricane steering** | Drag yellow track points to change the storm’s path. Intensity responds to sea-surface temperature, landfall, and a manual slider. |
| **Asymmetric damage** | Storm-surge and wind damage are stronger in the lower-right (southeast) quadrant, approximating a well-known feature of Northern Hemisphere tropical cyclones. |
| **Multi-hazard placement** | Select lightning, tornado, wildfire, extreme-rain burst, or fluvial-flood seed, then click the map. |
| **Fluvial interaction** | High precipitation on low ground contributes to flood damage, letting students explore the link between hurricane rainfall and inland flooding. |
| **Coastline selection** | Four real U.S. coast-to-inland elevation transects (South Carolina, North Carolina, Florida, Gulf Coast) with live Open-Elevation/SRTM data and a procedural fallback. |
| **Guided scenarios** | Pre-set investigations (Hugo-like landfall, stay-offshore challenge, orographic focus, Gulf surge) with observation prompts. |
| **Overlays** | Circulation belts, precipitation accumulation, and wind-damage extent. |
| **Research logging** | Every major action is recorded; export a JSON log for classroom or evaluation use. |
| **Camera** | Mouse orbit + scroll, WASD pan, arrow-key tilt/rotate, and full touch support. |

All processes are deliberately simplified pedagogical proxies. See the accompanying method paper for the exact relationships, what is omitted, and the design rationale.

---

## Pedagogical Notes

- Pair the tool with explicit instructor framing. Free exploration alone is often less effective for novices than guided investigation (Kirschner, Sweller & Clark, 2006).
- The intensity slider is a “what-if” control, not a physical driver—use it to contrast SST-driven intensity with arbitrary intensification.
- Damage thresholds for buildings are uniform by design; discuss structural vulnerability as a real-world complication the model omits.
- Recommended sequence: load a guided scenario → observe → intervene with a secondary hazard → switch overlays → export the log for reflection.

---

## Technical Overview

- **Stack**: Single HTML file + Three.js (r128 via CDN). No build step, no server-side code.
- **Terrain**: 81 × 81 vertex mesh. Elevation from a 36-point coast-to-inland transect (Open-Elevation / SRTM) with 2-D-aware procedural variation and a coastline-specific fallback.
- **Damage model**: Persistent, distance-weighted channels for flood, hurricane wind, and scorch; shared visual encoding so hazards remain distinguishable.
- **Browser support**: Any recent browser with WebGL. Works offline once the page and Three.js cache are loaded (live elevation requires network).

---

## Citation & Paper

This tool is described in a method paper submitted to *Journal of Geography*:

> Sokol, N. J., & Roman, M. (submitted). A drag-to-steer hurricane simulation for physical geography education: a browser-based interactive method. *Journal of Geography*.

If you use the simulation in teaching or research, please cite the paper (once published) and link to this repository.

---

## Repository Contents

```
Physical-Geography-sim.html   ← the simulation (open this)
README.md                     ← this file
LICENSE                       ← MIT
```

Older prototypes and manuscript versions may appear in the commit history.

---

## Contributing

Issues and pull requests are welcome.

- Bug reports and feature ideas → GitHub Issues
- Proposed changes to simplified physical relationships → open an issue first so the pedagogical intent can be discussed
- Keep the single-file, zero-install constraint unless there is a compelling reason to change it

---

## License

MIT License. See [LICENSE](LICENSE) for details.

---

## Acknowledgments

Developed in the Department of Geography & Sustainability, University of Tennessee, Knoxville.  
Feedback from departmental colleagues improved both the tool and the accompanying manuscript.

---

*Open the HTML file and start exploring. The storm is waiting.*
