---
layout: default
title: Sphere Geometry Mesh
description: Geometry-only sphere OpenFOAM mesh inspection with slices, boundary patches, topology, and quality diagnostics.
---

<div class="case-nav"><a href="{{ '/' | relative_url }}">Home</a> / <a href="{{ '/geometry/' | relative_url }}">Geometry meshes</a> / Sphere</div>

# Sphere — geometry-only mesh inspection

<div class="scope-banner">GEOMETRY ONLY · NO CFD RUN OR CFD RESULT IS USED ON THIS PAGE</div>

<div class="download-box">
  <strong>Download source mesh pack:</strong>
  <a class="button button-primary" href="https://drive.google.com/file/d/1EPs5qfkC8DxtvWGVCt7vpBQ5aKtF2_0K/view?usp=sharing">Open KCS / sphere / supplied propeller pack</a>
</div>

<div class="metric-row">
  <div class="metric"><div class="metric-label">Cells</div><div class="metric-value">52,280</div></div>
  <div class="metric"><div class="metric-label">Faces</div><div class="metric-value">166,196</div></div>
  <div class="metric"><div class="metric-label">Object faces</div><div class="metric-value">4,368</div></div>
  <div class="metric"><div class="metric-label">Hex cells</div><div class="metric-value">75.9%</div></div>
</div>

## Mesh summary

| Quantity | Value |
|---|---:|
| Points | 69,972 |
| Internal faces | 156,428 |
| Boundary faces | 9,768 |
| Object patch | `sphere` |
| Object bounding dimensions | 0.99838 × 0.99306 × 0.99997 |
| Object surface area (triangulated) | 3.10780 |
| Cell types | 39,680 hex · 11,408 polyhedron · 1,192 wedge |
| Median equivalent cell length, V^(1/3) | 0.03407 |
| 5th / 95th percentile equivalent cell length | 0.01245 / 0.06667 |

The object bounds are consistent with a nominal diameter of approximately 1 in a `[-1, 1]^3` cubic domain. The triangulated surface area is slightly below π, as expected for the supplied faceted approximation to a radius-0.5 sphere.

## Surface and orthogonal slices

<div class="figure-block">
  <img src="{{ '/cases/sphere/images/sphere_surface.png' | relative_url }}" alt="Sphere object surface mesh">
  <div class="figure-caption">Object-patch tessellation for the supplied sphere geometry.</div>
</div>

<div class="figure-grid">
  <div class="figure-block">
    <img src="{{ '/cases/sphere/images/sphere_slice_xy.png' | relative_url }}" alt="Sphere XY center-plane mesh slice">
    <div class="figure-caption">Center-plane XY cut colored by equivalent cell length. The concentric refinement band and transition to the background mesh are directly visible.</div>
  </div>
  <div class="figure-block">
    <img src="{{ '/cases/sphere/images/sphere_slice_xz.png' | relative_url }}" alt="Sphere XZ center-plane mesh slice">
    <div class="figure-caption">Orthogonal XZ cut used as a symmetry/consistency check on the 3D refinement pattern.</div>
  </div>
</div>

The two center cuts show broadly symmetric refinement around the spherical boundary. The fine layer adjacent to the surface transitions through an intermediate region before reaching the uniform outer-domain scale.

## Boundary patches

<div class="figure-block">
  <img src="{{ '/cases/sphere/images/sphere_patches.png' | relative_url }}" alt="Sphere boundary patch overview">
  <div class="figure-caption">Six outer box patches plus the spherical object patch.</div>
</div>

Each of the six outer box patches contains 900 faces; the `sphere` patch contains 4,368 faces. This gives 9,768 boundary faces in total.

## Geometry-based quality diagnostics

<div class="figure-block">
  <img src="{{ '/cases/sphere/images/sphere_quality.png' | relative_url }}" alt="Sphere mesh quality distributions">
  <div class="figure-caption">Cell-size, internal-face non-orthogonality, and centroid-line skewness-proxy distributions.</div>
</div>

| Diagnostic | Median | p95 | p99 |
|---|---:|---:|---:|
| Internal-face non-orthogonality | 0.067° | 25.24° | 71.34° |
| Centroid-line skewness proxy | 0.00019 | 0.1422 | 0.5003 |

About 1.18% of internal faces exceed 65° in this independent non-orthogonality calculation and about 0.52% exceed 85°. The long tail is concentrated in a small part of the face population; use the raw JSON for exact values.

## Reproduce

See [MESH_ANALYSIS.md]({{ '/MESH_ANALYSIS.html' | relative_url }}).
