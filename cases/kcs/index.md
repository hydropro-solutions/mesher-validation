---
layout: default
title: KCS Geometry Mesh
description: Geometry-only KCS OpenFOAM mesh inspection with full-hull surface view, crinkle slices, patches, and quality diagnostics.
---

<div class="case-nav"><a href="{{ '/' | relative_url }}">Home</a> / <a href="{{ '/geometry/' | relative_url }}">Geometry meshes</a> / KCS</div>

# KCS hull — geometry-only mesh inspection

<div class="scope-banner">GEOMETRY ONLY · NO CFD RUN OR CFD RESULT IS USED ON THIS PAGE</div>
<div class="download-box"><strong>Download source meshes:</strong> <a class="button button-primary" href="{{ '/downloads/geometry-meshes.zip' | relative_url }}">Download geometry-only ZIP</a></div>

<div class="metric-row"><div class="metric"><div class="metric-label">Cells</div><div class="metric-value">120,060</div></div><div class="metric"><div class="metric-label">Faces</div><div class="metric-value">382,356</div></div><div class="metric"><div class="metric-label">Hull patch faces</div><div class="metric-value">8,267</div></div><div class="metric"><div class="metric-label">Boundary faces</div><div class="metric-value">17,689</div></div></div>

## Full hull surface

<div class="figure-block"><img src="{{ '/cases/kcs/images/kcs_surface.png' | relative_url }}" alt="Complete KCS hull surface mesh"><div class="figure-caption">The supplied mesh is a half-domain about y = 0. For this surface visualization the 8,267-face hull patch is mirrored about the symmetry plane so the complete KCS hull is visible. Mesh counts remain those of the original half-domain.</div></div>

## Crinkle-style mesh sections

<div class="figure-grid"><div class="figure-block"><img src="{{ '/cases/kcs/images/kcs_slice_longitudinal.png' | relative_url }}" alt="KCS longitudinal crinkle-style mesh section"><div class="figure-caption">Near-symmetry longitudinal crinkle view. Original cells intersecting the reference plane are retained; color shows equivalent cell length.</div></div><div class="figure-block"><img src="{{ '/cases/kcs/images/kcs_slice_transverse.png' | relative_url }}" alt="KCS transverse crinkle-style mesh section"><div class="figure-caption">Transverse crinkle view showing the local refinement structure around the hull.</div></div></div>

The refinement structure is concentrated tightly around the hull and transitions outward through several mesh scales. Because the crinkle views retain original intersected cells, the refinement steps and local cell topology are visible directly rather than through a flat geometric cut.

## Complete KCS object patch

<div class="figure-block"><img src="{{ '/cases/kcs/images/kcs_patches.png' | relative_url }}" alt="Complete mirrored KCS object patch top view"><div class="figure-caption">Top view of the complete hull patch, mirrored across y = 0 for presentation.</div></div>

| Patch | Faces |
|---|---:|
| `Box0.XMIN` | 130 |
| `Box0.XMAX` | 130 |
| `Box0.YMIN` | 8,187 |
| `Box0.YMAX` | 520 |
| `Box0.ZMIN` | 136 |
| `Box0.ZMAX` | 319 |
| `kcs` | 8,267 |

## Geometry-based quality diagnostics

<div class="figure-block"><img src="{{ '/cases/kcs/images/kcs_quality.png' | relative_url }}" alt="KCS mesh quality distributions"><div class="figure-caption">Cell-size distribution, internal-face non-orthogonality, and centroid-line skewness proxy.</div></div>

| Diagnostic | Median | p95 | p99 |
|---|---:|---:|---:|
| Internal-face non-orthogonality | 0.00° | 26.04° | 61.47° |
| Centroid-line skewness proxy | 0.0000004 | 0.1463 | 0.4978 |
