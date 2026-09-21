---
layout: default
title: Home
description: Geometry-first validation and inspection of meshes generated with HydroPro's automated 3D meshing technology.
---

<section class="hero">
  <span class="scope-pill">Geometry-first mesh validation</span>
  <h1>HydroPro Mesher Validation</h1>
  <p>Inspection of OpenFOAM meshes generated with HydroPro's automated 3D meshing technology. KCS, sphere, and propeller are presented as <strong>geometry-only mesh cases</strong>; no CFD runs or CFD-result claims are used.</p>
  <div class="hero-actions">
    <a class="button button-primary" href="{{ '/geometry/' | relative_url }}">Explore geometry meshes</a>
    <a class="button button-secondary" href="{{ '/downloads/geometry-meshes.zip' | relative_url }}">Download geometry meshes</a>
  </div>
</section>

## Geometry-only benchmark cases

<div class="card-grid">
  <article class="case-card">
    <img src="{{ '/cases/kcs/images/kcs_slice_longitudinal.png' | relative_url }}" alt="KCS crinkle-style longitudinal mesh view">
    <div class="case-card-body"><div class="scope-line">GEOMETRY ONLY · NO CFD RUN</div><h3>KCS hull</h3><p>Half-domain KCS mesh with full-hull mirrored surface visualization, crinkle-style mesh sections, boundary topology, and quality diagnostics.</p><div class="metric-row"><div class="metric"><div class="metric-label">Cells</div><div class="metric-value">120,060</div></div><div class="metric"><div class="metric-label">Hull faces</div><div class="metric-value">8,267</div></div></div><p><a class="button button-primary" href="{{ '/cases/kcs/' | relative_url }}">Inspect KCS mesh</a></p></div>
  </article>
  <article class="case-card">
    <img src="{{ '/cases/sphere/images/sphere_slice_xy.png' | relative_url }}" alt="Sphere crinkle-style center mesh view">
    <div class="case-card-body"><div class="scope-line">GEOMETRY ONLY · NO CFD RUN</div><h3>Sphere</h3><p>Sphere mesh with object tessellation, orthogonal crinkle-style views, patch topology, and mesh-quality distributions.</p><div class="metric-row"><div class="metric"><div class="metric-label">Cells</div><div class="metric-value">52,280</div></div><div class="metric"><div class="metric-label">Object faces</div><div class="metric-value">4,368</div></div></div><p><a class="button button-primary" href="{{ '/cases/sphere/' | relative_url }}">Inspect sphere mesh</a></p></div>
  </article>
  <article class="case-card">
    <img src="{{ '/cases/propeller/images/propeller_slice_xy.png' | relative_url }}" alt="Propeller crinkle-style mesh view">
    <div class="case-card-body"><div class="scope-line">GEOMETRY ONLY · NO CFD RUN</div><h3>Propeller</h3><p>Three-blade propeller mesh with 62,590 object-patch faces, detailed near-blade refinement views, patch inspection, and geometry diagnostics.</p><div class="metric-row"><div class="metric"><div class="metric-label">Cells</div><div class="metric-value">369,006</div></div><div class="metric"><div class="metric-label">Propeller faces</div><div class="metric-value">62,590</div></div></div><p><a class="button button-primary" href="{{ '/cases/propeller/' | relative_url }}">Inspect propeller mesh</a></p></div>
  </article>
</div>

## What the geometry analysis checks

The geometry analysis covers topology and patch counts, object-surface tessellation, crinkle-style refinement views, cell-size distributions, internal-face alignment, and a centroid-line skewness proxy.

<div class="notice notice-info"><strong>Visualization:</strong> crinkle-style sections preserve the original intersected mesh cells rather than replacing them with a flat planar triangulation. See <a href="{{ '/MESH_ANALYSIS.html' | relative_url }}">the analysis methodology</a>.</div>
