---
layout: default
title: Sphere Geometry Mesh
description: Geometry-only sphere OpenFOAM mesh inspection with crinkle slices, patches, and quality diagnostics.
---

<div class="case-nav"><a href="{{ '/' | relative_url }}">Home</a> / <a href="{{ '/geometry/' | relative_url }}">Geometry meshes</a> / Sphere</div>

# Sphere — geometry-only mesh inspection

<div class="scope-banner">GEOMETRY ONLY · NO CFD RUN OR CFD RESULT IS USED ON THIS PAGE</div>
<div class="download-box"><strong>Download source meshes:</strong> <a class="button button-primary" href="{{ '/downloads/geometry-meshes.zip' | relative_url }}">Download geometry-only ZIP</a></div>

<div class="metric-row"><div class="metric"><div class="metric-label">Cells</div><div class="metric-value">52,280</div></div><div class="metric"><div class="metric-label">Faces</div><div class="metric-value">166,196</div></div><div class="metric"><div class="metric-label">Object faces</div><div class="metric-value">4,368</div></div><div class="metric"><div class="metric-label">Boundary faces</div><div class="metric-value">9,768</div></div></div>

## Surface and crinkle-style sections

<div class="figure-block"><img src="{{ '/cases/sphere/images/sphere_surface.png' | relative_url }}" alt="Sphere object surface mesh"><div class="figure-caption">Supplied sphere object-patch tessellation.</div></div>
<div class="figure-grid"><div class="figure-block"><img src="{{ '/cases/sphere/images/sphere_slice_xy.png' | relative_url }}" alt="Sphere XY crinkle mesh section"><div class="figure-caption">XY crinkle view through the center, preserving original intersected cells.</div></div><div class="figure-block"><img src="{{ '/cases/sphere/images/sphere_slice_xz.png' | relative_url }}" alt="Sphere XZ crinkle mesh section"><div class="figure-caption">Orthogonal XZ crinkle view showing the 3D refinement consistency.</div></div></div>

The fine region follows the spherical boundary and transitions through intermediate mesh scales before reaching the background mesh.

## Boundary patches

<div class="figure-block"><img src="{{ '/cases/sphere/images/sphere_patches.png' | relative_url }}" alt="Sphere boundary patch overview"><div class="figure-caption">Six outer box patches plus the spherical object patch.</div></div>

Each outer box patch contains 900 faces; the `sphere` patch contains 4,368 faces.

## Geometry-based quality diagnostics

<div class="figure-block"><img src="{{ '/cases/sphere/images/sphere_quality.png' | relative_url }}" alt="Sphere mesh quality distributions"><div class="figure-caption">Cell-size, internal-face non-orthogonality, and centroid-line skewness-proxy distributions.</div></div>

| Diagnostic | Median | p95 | p99 |
|---|---:|---:|---:|
| Internal-face non-orthogonality | 0.067° | 25.24° | 71.34° |
| Centroid-line skewness proxy | 0.00019 | 0.1422 | 0.5003 |
