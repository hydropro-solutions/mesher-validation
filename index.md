---
layout: default
title: Home
description: CFD validation cases generated using HydroPro's automated 3D meshing technology.
---

<section class="hero">
  <h1>HydroPro Mesher Validation</h1>
  <p>
    CFD validation cases using HydroPro's automated 3D meshing technology.
    The cases document mesh characteristics, CFD results, and agreement with reference data
    on representative marine-hydrodynamics and external-flow problems.
  </p>
  <div class="hero-actions">
    <a class="button button-primary" href="{{ '/cases/dtc/' | relative_url }}">Explore DTC validation</a>
    <a class="button button-secondary" href="{{ '/cases/ahmed25/' | relative_url }}">Explore Ahmed 25° validation</a>
  </div>
</section>

## Validation Cases

<div class="card-grid">
  <article class="case-card">
    <img src="{{ '/cases/dtc/images/dtc_midship_slice.png' | relative_url }}" alt="DTC midship slice">
    <div class="case-card-body">
      <h3>Duisburg Test Case (DTC)</h3>
      <p>Free-surface ship-resistance simulation using OpenFOAM, including hull boundary layers, wave generation, and resistance prediction.</p>
      <div class="metric-row">
        <div class="metric">
          <div class="metric-label">Cells</div>
          <div class="metric-value">278,418</div>
        </div>
        <div class="metric">
          <div class="metric-label">Difference vs experiment</div>
          <div class="metric-value">+1.21%</div>
        </div>
      </div>
      <p>
        <a class="button button-primary" href="{{ '/cases/dtc/' | relative_url }}">View case</a>
        <a class="button button-secondary" href="https://drive.google.com/file/d/1Cgaiaj46WVoRbSKlV5YIN5G0zRu3pDMk/view?usp=sharing">Download case</a>
      </p>
    </div>
  </article>

  <article class="case-card">
    <img src="{{ '/cases/ahmed25/images/ahmed_slice_symmetry_y0.png' | relative_url }}" alt="Ahmed body symmetry-plane slice">
    <div class="case-card-body">
      <h3>Ahmed Body — 25° Slant</h3>
      <p>Steady external-flow RANS validation on the 25° Ahmed body at 40 m/s, evaluating separation, wake structure, and aerodynamic force prediction.</p>
      <div class="metric-row">
        <div class="metric">
          <div class="metric-label">Cells</div>
          <div class="metric-value">2,082,880</div>
        </div>
        <div class="metric">
          <div class="metric-label">Difference vs reference</div>
          <div class="metric-value">-2.18%</div>
        </div>
      </div>
      <p>
        <a class="button button-primary" href="{{ '/cases/ahmed25/' | relative_url }}">View case</a>
        <a class="button button-secondary" href="https://drive.google.com/file/d/1D6JRIJXeYbrt8wvAJRpOY3rBzG_ywE7a/view?usp=sharing">Download case</a>
      </p>
    </div>
  </article>
</div>

## Validation approach

The validation campaign focuses on quantities that matter directly for CFD applications:

- mesh quality and robustness;
- boundary-layer treatment;
- solver compatibility;
- force prediction;
- free-surface and wake resolution;
- computational mesh size;
- repeatability on different geometry classes.

## About HydroPro

HydroPro works on marine hydrodynamics, complex CFD simulation, and engineering software.

This validation site presents results obtained with HydroPro's automated 3D meshing technology across marine-hydrodynamics and external-flow applications.
