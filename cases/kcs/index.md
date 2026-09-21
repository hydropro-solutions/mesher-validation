---
layout: default
title: KCS Geometry Mesh
description: Geometry-only KCS OpenFOAM mesh inspection with slices, boundary patches, topology, and quality diagnostics.
---

<div class="case-nav"><a href="{{ '/' | relative_url }}">Home</a> / <a href="{{ '/geometry/' | relative_url }}">Geometry meshes</a> / KCS</div>

# KCS hull — geometry-only mesh inspection

<div class="scope-banner">GEOMETRY ONLY · NO CFD RUN OR CFD RESULT IS USED ON THIS PAGE</div>

<div class="download-box">
  <strong>Download source mesh pack:</strong>
  <a class="button button-primary" href="https://drive.google.com/file/d/1EPs5qfkC8DxtvWGVCt7vpBQ5aKtF2_0K/view?usp=sharing">Open KCS / sphere / supplied propeller pack</a>
</div>

<div class="metric-row">
  <div class="metric"><div class="metric-label">Cells</div><div class="metric-value">120,060</div></div>
  <div class="metric"><div class="metric-label">Faces</div><div class="metric-value">382,356</div></div>
  <div class="metric"><div class="metric-label">Object faces</div><div class="metric-value">8,267</div></div>
  <div class="metric"><div class="metric-label">Hex cells</div><div class="metric-value">82.7%</div></div>
</div>

## Mesh summary

| Quantity | Value |
|---|---:|
| Points | 150,973 |
| Internal faces | 364,667 |
| Boundary faces | 17,689 |
| Object patch | `kcs` |
| Object dimensions (x × y × z) | 7.7187 × 0.5097 × 0.7454 |
| Object surface area (triangulated) | 10.6175 |
| Cell types | 99,343 hex · 20,252 polyhedron · 419 wedge · 46 tetra |
| Median equivalent cell length, V^(1/3) | 0.04767 |
| 5th / 95th percentile equivalent cell length | 0.01394 / 0.20304 |

## Hull surface tessellation

<div class="figure-block">
  <img src="{{ '/cases/kcs/images/kcs_surface.png' | relative_url }}" alt="KCS hull surface tessellation">
  <div class="figure-caption">The object boundary patch contains 8,267 faces and 10,927 patch points. This is a surface-mesh view only.</div>
</div>

## Mesh slices

<div class="figure-grid">
  <div class="figure-block">
    <img src="{{ '/cases/kcs/images/kcs_slice_longitudinal.png' | relative_url }}" alt="KCS longitudinal mesh slice">
    <div class="figure-caption">Near-symmetry longitudinal cut. Cell polygons are colored by equivalent cell length; the red contour is the hull intersection.</div>
  </div>
  <div class="figure-block">
    <img src="{{ '/cases/kcs/images/kcs_slice_transverse.png' | relative_url }}" alt="KCS transverse mesh slice detail">
    <div class="figure-caption">Transverse near-hull detail showing local size transition and the half-domain geometry boundary.</div>
  </div>
</div>

The slices show a compact refined region surrounding the hull, with finer cells concentrated against the object boundary and larger cells away from it. The longitudinal view also makes the abruptness of the outer refinement-box transition visible, which is useful for reviewing grading strategy independently of any flow solution.

## Boundary patches

<div class="figure-block">
  <img src="{{ '/cases/kcs/images/kcs_patches.png' | relative_url }}" alt="KCS boundary patch overview">
  <div class="figure-caption">Semi-transparent outer-domain patches with the KCS object patch highlighted.</div>
</div>

| Patch | Faces |
|---|---:|
| `Box0.XMIN` | 130 |
| `Box0.XMAX` | 130 |
| `Box0.YMIN` | 8,187 |
| `Box0.YMAX` | 520 |
| `Box0.ZMIN` | 136 |
| `Box0.ZMAX` | 319 |
| `kcs` | 8,267 |
| `defaultFaces` | 0 |

The high face count on `Box0.YMIN` is consistent with the half-domain/symmetry-side surface intersecting the refined mesh region; the patch table makes this topological asymmetry explicit.

## Geometry-based quality diagnostics

<div class="figure-block">
  <img src="{{ '/cases/kcs/images/kcs_quality.png' | relative_url }}" alt="KCS mesh quality distributions">
  <div class="figure-caption">Cell-size distribution, internal-face non-orthogonality, and centroid-line skewness proxy. The skewness panel displays the lower 99.5% so rare near-singular outliers do not flatten the plot.</div>
</div>

| Diagnostic | Median | p95 | p99 |
|---|---:|---:|---:|
| Internal-face non-orthogonality | 0.00° | 26.04° | 61.47° |
| Centroid-line skewness proxy | 0.0000004 | 0.1463 | 0.4978 |

About 0.92% of internal faces exceed 65° in this independent non-orthogonality calculation, and 0.22% exceed 85°. These values are useful for locating the long tail of the geometric distribution, but they are not OpenFOAM `checkMesh` pass/fail results.

## Reproduce

See [MESH_ANALYSIS.md]({{ '/MESH_ANALYSIS.html' | relative_url }}).
