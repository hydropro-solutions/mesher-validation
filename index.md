---
layout: default
title: Home
description: HydroPro mesher validation covering geometry-only mesh inspection and CFD validation cases.
---

<section class="hero">
  <span class="scope-pill">Mesh validation · geometry inspection · CFD validation</span>
  <h1>HydroPro Mesher Validation</h1>
  <p>
    Validation and inspection of meshes generated with HydroPro's automated 3D meshing technology.
    Geometry-only cases are kept separate from CFD-result validation cases so the scope of each result is explicit.
  </p>
  <div class="hero-actions">
    <a class="button button-primary" href="{{ '/geometry/' | relative_url }}">Explore geometry meshes</a>
    <a class="button button-secondary" href="{{ '/cases/dtc/' | relative_url }}">DTC CFD validation</a>
    <a class="button button-secondary" href="{{ '/cases/ahmed25/' | relative_url }}">Ahmed 25° CFD validation</a>
  </div>
</section>

## Geometry-only benchmark cases

<div class="card-grid">
  <article class="case-card">
    <img src="{{ '/cases/kcs/images/kcs_slice_longitudinal.png' | relative_url }}" alt="KCS crinkle-style longitudinal mesh view">
    <div class="case-card-body">
      <div class="scope-line">GEOMETRY ONLY · NO CFD RUN</div>
      <h3>KCS hull</h3>
      <p>Half-domain KCS mesh with full-hull mirrored surface visualization, crinkle-style mesh sections, boundary topology, and mesh diagnostics.</p>
      <div class="metric-row"><div class="metric"><div class="metric-label">Cells</div><div class="metric-value">120,060</div></div><div class="metric"><div class="metric-label">Hull faces</div><div class="metric-value">8,267</div></div></div>
      <p><a class="button button-primary" href="{{ '/cases/kcs/' | relative_url }}">Inspect KCS mesh</a></p>
    </div>
  </article>

  <article class="case-card">
    <img src="{{ '/cases/sphere/images/sphere_slice_xy.png' | relative_url }}" alt="Sphere crinkle-style center mesh view">
    <div class="case-card-body">
      <div class="scope-line">GEOMETRY ONLY · NO CFD RUN</div>
      <h3>Sphere</h3>
      <p>Sphere mesh with object tessellation, orthogonal crinkle-style views, patch topology, and mesh-quality distributions.</p>
      <div class="metric-row"><div class="metric"><div class="metric-label">Cells</div><div class="metric-value">52,280</div></div><div class="metric"><div class="metric-label">Object faces</div><div class="metric-value">4,368</div></div></div>
      <p><a class="button button-primary" href="{{ '/cases/sphere/' | relative_url }}">Inspect sphere mesh</a></p>
    </div>
  </article>

  <article class="case-card">
    <img src="{{ '/cases/propeller/images/propeller_slice_xy.png' | relative_url }}" alt="Propeller crinkle-style mesh view">
    <div class="case-card-body">
      <div class="scope-line">GEOMETRY ONLY · NO CFD RUN</div>
      <h3>Propeller</h3>
      <p>Three-blade propeller mesh with detailed near-blade refinement views, patch inspection, and geometry diagnostics.</p>
      <div class="metric-row"><div class="metric"><div class="metric-label">Cells</div><div class="metric-value">369,006</div></div><div class="metric"><div class="metric-label">Propeller faces</div><div class="metric-value">62,590</div></div></div>
      <p><a class="button button-primary" href="{{ '/cases/propeller/' | relative_url }}">Inspect propeller mesh</a></p>
    </div>
  </article>
</div>

<div class="download-box">
  <strong>Geometry meshes:</strong>
  <a class="button button-primary" href="{{ '/downloads/geometry-meshes.zip' | relative_url }}">Download KCS + sphere + propeller</a>
  <div class="small-note">OpenFOAM mesh topology only; no CFD solution fields or solver results.</div>
</div>

## CFD validation cases

<div class="card-grid">
  <article class="case-card">
    <img src="{{ '/cases/dtc/images/dtc_midship_slice.png' | relative_url }}" alt="DTC midship slice">
    <div class="case-card-body">
      <div class="scope-line">CFD VALIDATION</div>
      <h3>Duisburg Test Case (DTC)</h3>
      <p>Free-surface ship-resistance simulation using OpenFOAM, including hull boundary layers, wave generation, and resistance prediction.</p>
      <div class="metric-row"><div class="metric"><div class="metric-label">Cells</div><div class="metric-value">278,418</div></div><div class="metric"><div class="metric-label">Difference vs experiment</div><div class="metric-value">+1.21%</div></div></div>
      <p>
        <a class="button button-primary" href="{{ '/cases/dtc/' | relative_url }}">View DTC case</a>
        <a class="button button-secondary" href="https://drive.google.com/file/d/1Cgaiaj46WVoRbSKlV5YIN5G0zRu3pDMk/view?usp=sharing">Download DTC case</a>
      </p>
    </div>
  </article>

  <article class="case-card">
    <img src="{{ '/cases/ahmed25/images/ahmed_slice_symmetry_y0.png' | relative_url }}" alt="Ahmed body symmetry-plane slice">
    <div class="case-card-body">
      <div class="scope-line">CFD VALIDATION</div>
      <h3>Ahmed Body — 25° Slant</h3>
      <p>Steady external-flow RANS validation on the 25° Ahmed body at 40 m/s, evaluating separation, wake structure, and aerodynamic force prediction.</p>
      <div class="metric-row"><div class="metric"><div class="metric-label">Cells</div><div class="metric-value">2,082,880</div></div><div class="metric"><div class="metric-label">Difference vs reference</div><div class="metric-value">-2.18%</div></div></div>
      <p>
        <a class="button button-primary" href="{{ '/cases/ahmed25/' | relative_url }}">View Ahmed case</a>
        <a class="button button-secondary" href="https://drive.google.com/file/d/1D6JRIJXeYbrt8wvAJRpOY3rBzG_ywE7a/view?usp=sharing">Download Ahmed case</a>
      </p>
    </div>
  </article>
</div>

## Validation scope

The geometry-only pages inspect mesh topology, boundary patches, surface tessellation, refinement structure, and geometry-based quality diagnostics. The DTC and Ahmed pages retain the existing CFD validation results and their reference comparisons.
