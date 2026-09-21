---
layout: default
title: Geometry Meshes
description: Geometry-only OpenFOAM mesh cases for KCS, sphere, and propeller.
---

<div class="case-nav"><a href="{{ '/' | relative_url }}">Home</a> / Geometry meshes</div>

# Geometry-only mesh inspection

<div class="download-box"><strong>Download the exact geometry-only mesh bundle:</strong> <a class="button button-primary" href="{{ '/downloads/geometry-meshes.zip' | relative_url }}">Download KCS + sphere + propeller</a><div class="small-note"></div></div>

| Case | Cells | Faces | Boundary faces | Object patch | Object faces |
|---|---:|---:|---:|---|---:|
| [KCS]({{ '/cases/kcs/' | relative_url }}) | 120,060 | 382,356 | 17,689 | `kcs` | 8,267 |
| [Sphere]({{ '/cases/sphere/' | relative_url }}) | 52,280 | 166,196 | 9,768 | `sphere` | 4,368 |
| [Propeller]({{ '/cases/propeller/' | relative_url }}) | 369,006 | 1,202,547 | 73,092 | `propeller` | 62,590 |

## Analysis outputs

Each case page contains an object-surface rendering, patch inspection, crinkle-style mesh sections, and geometry-based quality distributions. These pages analyze the mesh only; they do not infer CFD accuracy or solver performance.
