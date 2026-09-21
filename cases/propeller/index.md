---
layout: default
title: Propeller Geometry Mesh
description: Geometry-only inspection of the propeller OpenFOAM mesh with surface, crinkle sections, patches, and quality diagnostics.
---

<div class="case-nav"><a href="{{ '/' | relative_url }}">Home</a> / <a href="{{ '/geometry/' | relative_url }}">Geometry meshes</a> / Propeller</div>

# Propeller — geometry-only mesh inspection

<div class="scope-banner">GEOMETRY ONLY · NO CFD RUN OR CFD RESULT IS USED ON THIS PAGE</div>
<div class="download-box"><strong>Download source meshes:</strong> <a class="button button-primary" href="{{ '/downloads/geometry-meshes.zip' | relative_url }}">Download geometry-only ZIP</a></div>

<div class="metric-row"><div class="metric"><div class="metric-label">Cells</div><div class="metric-value">369,006</div></div><div class="metric"><div class="metric-label">Faces</div><div class="metric-value">1,202,547</div></div><div class="metric"><div class="metric-label">Propeller faces</div><div class="metric-value">62,590</div></div><div class="metric"><div class="metric-label">Boundary faces</div><div class="metric-value">73,092</div></div></div>

## Propeller surface tessellation

<div class="figure-block"><img src="{{ '/cases/propeller/images/propeller_surface.png' | relative_url }}" alt="Three-blade propeller surface mesh"><div class="figure-caption">The supplied object patch is `propeller` with 62,590 faces and 63,499 patch points.</div></div>

## Crinkle-style refinement views

<div class="figure-grid"><div class="figure-block"><img src="{{ '/cases/propeller/images/propeller_slice_xy.png' | relative_url }}" alt="Propeller XY crinkle mesh view"><div class="figure-caption">Crinkle view through the propeller plane. Original intersected cells are preserved, exposing the near-blade refinement footprint and its transition to the background mesh.</div></div><div class="figure-block"><img src="{{ '/cases/propeller/images/propeller_slice_yz.png' | relative_url }}" alt="Propeller YZ crinkle mesh view"><div class="figure-caption">Orthogonal crinkle view through the propeller region, useful for checking refinement thickness through the axial direction.</div></div></div>

The mesh shows strong local refinement following all three blades and the hub, with progressively larger cells away from the propeller. The crinkle presentation keeps the original mesh cells instead of generating a smooth planar cut.

## Boundary patches

<div class="figure-block"><img src="{{ '/cases/propeller/images/propeller_patches.png' | relative_url }}" alt="Propeller and outer-domain boundary patches"><div class="figure-caption">Propeller object patch highlighted against the outer computational-domain patches.</div></div>

| Patch | Faces |
|---|---:|
| `Box0.XMIN` | 1,200 |
| `Box0.XMAX` | 1,200 |
| `Box0.YMIN` | 1,000 |
| `Box0.YMAX` | 1,000 |
| `Box0.ZMIN` | 3,102 |
| `Box0.ZMAX` | 3,000 |
| `propeller` | 62,590 |

## Geometry-based quality diagnostics

<div class="figure-block"><img src="{{ '/cases/propeller/images/propeller_quality.png' | relative_url }}" alt="Propeller mesh quality distributions"><div class="figure-caption">Cell-size distribution, internal-face non-orthogonality, and centroid-line skewness proxy for the supplied propeller mesh.</div></div>

| Diagnostic | Median | p95 | p99 |
|---|---:|---:|---:|
| Internal-face non-orthogonality | 0.108° | 25.24° | 27.17° |
| Centroid-line skewness proxy | 0.00052 | 0.1421 | 0.1747 |
