---
layout: default
title: Home
description: Geometry-first validation and inspection of meshes generated with HydroPro's automated 3D meshing technology.
---

<section class="hero">
  <span class="scope-pill">Geometry-first mesh validation</span>
  <h1>HydroPro Mesher Validation</h1>
  <p>
    Reproducible inspection of OpenFOAM meshes generated with HydroPro's automated 3D meshing technology.
    The new KCS, sphere, and supplied <code>propeller</code> cases are <strong>geometry-only</strong>:
    no CFD solution or solver-result claims are made from them.
  </p>
  <div class="hero-actions">
    <a class="button button-primary" href="{{ '/geometry/' | relative_url }}">Explore geometry meshes</a>
    <a class="button button-secondary" href="https://drive.google.com/file/d/1EPs5qfkC8DxtvWGVCt7vpBQ5aKtF2_0K/view?usp=sharing">Download mesh pack</a>
  </div>
</section>

## Geometry-only benchmark cases

<div class="card-grid">
  <article class="case-card">
    <img src="{{ '/cases/kcs/images/kcs_slice_longitudinal.png' | relative_url }}" alt="KCS longitudinal mesh slice colored by equivalent cell length">
    <div class="case-card-body">
      <div class="scope-line">GEOMETRY ONLY · NO CFD RUN</div>
      <h3>KCS hull</h3>
      <p>Half-domain ship mesh with hull-surface inspection, patch topology, longitudinal/transverse cuts, and geometry-based face diagnostics.</p>
      <div class="metric-row">
        <div class="metric"><div class="metric-label">Cells</div><div class="metric-value">120,060</div></div>
        <div class="metric"><div class="metric-label">Object faces</div><div class="metric-value">8,267</div></div>
      </div>
      <p><a class="button button-primary" href="{{ '/cases/kcs/' | relative_url }}">Inspect KCS mesh</a></p>
    </div>
  </article>

  <article class="case-card">
    <img src="{{ '/cases/sphere/images/sphere_slice_xy.png' | relative_url }}" alt="Sphere mesh center-plane slice colored by equivalent cell length">
    <div class="case-card-body">
      <div class="scope-line">GEOMETRY ONLY · NO CFD RUN</div>
      <h3>Sphere</h3>
      <p>Spherical object in a cubic domain, including surface tessellation, boundary patches, orthogonal cuts, cell-size distribution, and face-alignment statistics.</p>
      <div class="metric-row">
        <div class="metric"><div class="metric-label">Cells</div><div class="metric-value">52,280</div></div>
        <div class="metric"><div class="metric-label">Object faces</div><div class="metric-value">4,368</div></div>
      </div>
      <p><a class="button button-primary" href="{{ '/cases/sphere/' | relative_url }}">Inspect sphere mesh</a></p>
    </div>
  </article>

  <article class="case-card">
    <img src="{{ '/cases/propeller/images/propeller_slice_xy.png' | relative_url }}" alt="Supplied propeller-labelled case mesh slice">
    <div class="case-card-body">
      <div class="scope-line warning-line">DATA-INTEGRITY FLAG</div>
      <h3>Supplied <code>propeller</code> directory</h3>
      <p>The volume mesh contains 55,362 cells, but the supplied object patch is named <code>sphere</code> and its surface coordinates exactly match the sphere case. The repository reports this rather than mislabeling the geometry.</p>
      <div class="metric-row">
        <div class="metric"><div class="metric-label">Cells</div><div class="metric-value">55,362</div></div>
        <div class="metric"><div class="metric-label">Object patch</div><div class="metric-value"><code>sphere</code></div></div>
      </div>
      <p><a class="button button-primary" href="{{ '/cases/propeller/' | relative_url }}">Inspect supplied case</a></p>
    </div>
  </article>
</div>

## What the geometry analysis checks

The geometry analysis covers mesh topology, boundary-patch composition, cell-type mix, cell-volume statistics, equivalent cell length, object-surface dimensions and area, internal-face alignment, and a centroid-line skewness proxy. It also checks for duplicate or mislabeled object geometry.

<div class="notice notice-info">
  <strong>Mesh diagnostics:</strong> definitions and limitations are documented in <a href="{{ '/MESH_ANALYSIS.html' | relative_url }}">the analysis methodology</a>. These geometry checks are not a replacement for OpenFOAM <code>checkMesh</code>.
</div>

## Legacy CFD-result pages

The original DTC and Ahmed 25° pages are retained separately because they include solver-result validation. They are not mixed with the new geometry-only benchmark claims.

<div class="card-grid compact-cards">
  <article class="case-card">
    <img src="{{ '/cases/dtc/images/dtc_midship_slice.png' | relative_url }}" alt="DTC CFD validation image">
    <div class="case-card-body"><h3>DTC CFD validation</h3><p>Legacy free-surface resistance validation page.</p><a class="button button-secondary" href="{{ '/cases/dtc/' | relative_url }}">View legacy CFD page</a></div>
  </article>
  <article class="case-card">
    <img src="{{ '/cases/ahmed25/images/ahmed_slice_symmetry_y0.png' | relative_url }}" alt="Ahmed body CFD validation image">
    <div class="case-card-body"><h3>Ahmed 25° CFD validation</h3><p>Legacy steady RANS validation page.</p><a class="button button-secondary" href="{{ '/cases/ahmed25/' | relative_url }}">View legacy CFD page</a></div>
  </article>
</div>
