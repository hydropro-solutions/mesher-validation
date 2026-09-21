---
layout: default
title: Supplied Propeller-labelled Mesh
description: Geometry-only inspection of the supplied propeller-labelled OpenFOAM case, including a duplicate-surface integrity finding.
---

<div class="case-nav"><a href="{{ '/' | relative_url }}">Home</a> / <a href="{{ '/geometry/' | relative_url }}">Geometry meshes</a> / Supplied propeller-labelled case</div>

# Supplied `propeller` directory — geometry-only inspection

<div class="scope-banner">GEOMETRY ONLY · NO CFD RUN OR CFD RESULT IS USED ON THIS PAGE</div>

<div class="notice notice-warning">
  <strong>Data-integrity finding:</strong> the supplied directory is named <code>propeller</code>, but its object boundary patch is named <code>sphere</code>. The object patch has 4,368 faces and its surface-point coordinate signature is exactly the same as the supplied sphere case. This page therefore does not describe the object as a propeller geometry.
</div>

<div class="download-box">
  <strong>Download source mesh pack:</strong>
  <a class="button button-primary" href="https://drive.google.com/file/d/1EPs5qfkC8DxtvWGVCt7vpBQ5aKtF2_0K/view?usp=sharing">Open supplied mesh pack</a>
</div>

<div class="metric-row">
  <div class="metric"><div class="metric-label">Cells</div><div class="metric-value">55,362</div></div>
  <div class="metric"><div class="metric-label">Faces</div><div class="metric-value">176,533</div></div>
  <div class="metric"><div class="metric-label">Object patch</div><div class="metric-value"><code>sphere</code></div></div>
  <div class="metric"><div class="metric-label">Surface match</div><div class="metric-value">Sphere case</div></div>
</div>

## What is different from the sphere case?

The object boundary geometry is the same, but the volume mesh is not. This supplied directory contains 55,362 cells versus 52,280 in the sphere case, and its cell-type mix is also different.

| Quantity | Supplied `propeller` directory | Sphere case |
|---|---:|---:|
| Cells | 55,362 | 52,280 |
| Internal faces | 166,765 | 156,428 |
| Object faces | 4,368 | 4,368 |
| Hex cells | 41,151 | 39,680 |
| Polyhedron cells | 13,172 | 11,408 |
| Wedge cells | 1,008 | 1,192 |
| Tetra cells | 31 | 0 |
| Object surface area | 3.10780 | 3.10780 |

So the case is still useful as a **different volume-meshing result around the same sphere**, but not as evidence of propeller-geometry meshing in its current supplied form.

## Surface and mesh slices

<div class="figure-block">
  <img src="{{ '/cases/propeller/images/propeller_surface.png' | relative_url }}" alt="Object surface in supplied propeller-labelled directory">
  <div class="figure-caption">The supplied object surface is spherical and matches the sphere-case surface coordinate-for-coordinate.</div>
</div>

<div class="figure-grid">
  <div class="figure-block">
    <img src="{{ '/cases/propeller/images/propeller_slice_xy.png' | relative_url }}" alt="Supplied propeller-labelled case XY mesh slice">
    <div class="figure-caption">Center-plane XY mesh cut colored by equivalent cell length.</div>
  </div>
  <div class="figure-block">
    <img src="{{ '/cases/propeller/images/propeller_slice_xz.png' | relative_url }}" alt="Supplied propeller-labelled case XZ mesh slice">
    <div class="figure-caption">Orthogonal XZ cut for comparing the local refinement pattern with the sphere case.</div>
  </div>
</div>

## Boundary patches

<div class="figure-block">
  <img src="{{ '/cases/propeller/images/propeller_patches.png' | relative_url }}" alt="Boundary patches in supplied propeller-labelled case">
  <div class="figure-caption">Six 900-face outer box patches and the 4,368-face object patch named <code>sphere</code>.</div>
</div>

## Geometry-based quality diagnostics

<div class="figure-block">
  <img src="{{ '/cases/propeller/images/propeller_quality.png' | relative_url }}" alt="Supplied propeller-labelled mesh quality distributions">
  <div class="figure-caption">The mesh has a different distribution from the sphere case even though the object boundary is identical.</div>
</div>

| Diagnostic | Median | p95 | p99 |
|---|---:|---:|---:|
| Internal-face non-orthogonality | 0.158° | 25.46° | 87.04° |
| Centroid-line skewness proxy | 0.00053 | 0.1765 | 1.3134 |

In this independent calculation, 2.39% of internal faces exceed 65° non-orthogonality and 1.30% exceed 85°. The 99th-percentile skewness proxy is also higher than in the supplied sphere mesh, which is a concrete indication that the two **volume meshes** differ even though the object surface does not.

## Recommended dataset fix

The supplied case is shown exactly as received. Replace this page and its figures when the intended propeller geometry is available.
