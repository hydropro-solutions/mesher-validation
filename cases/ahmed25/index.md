---
layout: default
title: Ahmed Body 25°
description: Ahmed body steady RANS validation case generated using HydroPro's automated 3D meshing technology.
---

<div class="case-nav"><a href="{{ '/' | relative_url }}">Home</a> / Ahmed 25°</div>

# Ahmed Body — 25° Slant

<div class="download-box">
  <strong>Download:</strong>
  <a class="button button-primary" href="https://drive.google.com/file/d/1D6JRIJXeYbrt8wvAJRpOY3rBzG_ywE7a/view?usp=sharing">Complete Ahmed Body OpenFOAM validation case</a>
</div>

This case presents a steady RANS simulation of the 25° Ahmed body at 40 m/s using a mesh generated with HydroPro's automated 3D meshing technology.

<div class="metric-row">
  <div class="metric">
    <div class="metric-label">Mesh cells</div>
    <div class="metric-value">2,082,880</div>
  </div>
  <div class="metric">
    <div class="metric-label">Cd</div>
    <div class="metric-value">0.29249</div>
  </div>
  <div class="metric">
    <div class="metric-label">Reference Cd</div>
    <div class="metric-value">≈ 0.299</div>
  </div>
  <div class="metric">
    <div class="metric-label">Difference</div>
    <div class="metric-value">-2.18%</div>
  </div>
</div>

## Case summary

| Item | Value |
|---|---|
| Geometry | Ahmed body, 25° rear slant |
| Freestream speed | 40 m/s |
| CFD solver | OpenFOAM `simpleFoam` |
| OpenFOAM version | 7 |
| Turbulence model | RANS, k-ω SST |
| Reference area | 0.115032 m² |
| Reference length | 0.470 m |
| Mesh cells | 2,082,880 |
| Mesh faces | 6,401,687 |
| Internal faces | 6,275,652 |
| Ahmed-body wall faces | 107,461 |
| Final iteration | 500 |

## Base validation case

The Ahmed-body solver setup used as the starting point for this validation was obtained from Nathan Rooy's public Ahmed Bluff Body CFD Validation repository:

<https://github.com/nathanrooy/ahmed-bluff-body-cfd/tree/master/openfoam_rans>

## CFD result

At iteration 500:

| Coefficient | Value |
|---|---:|
| Cm | 0.102888 |
| Cd | 0.292490 |
| Cl | 0.338394 |
| Cl(front) | 0.272085 |
| Cl(rear) | 0.066309 |

<div class="figure-block">
  <img src="{{ '/cases/ahmed25/images/ahmed_slice_symmetry_y0.png' | relative_url }}" alt="Ahmed symmetry-plane velocity slice">
  <div class="figure-caption">Velocity magnitude on the symmetry plane, highlighting the wake structure behind the body.</div>
</div>

<div class="figure-block">
  <img src="{{ '/cases/ahmed25/images/ahmed_slice_horizontal_zmid.png' | relative_url }}" alt="Ahmed horizontal velocity slice">
  <div class="figure-caption">Horizontal velocity slice around the body and in the near wake.</div>
</div>

## Inspecting the mesh

From the CFD case directory:

```bash
checkMesh
```

For visualization, create or open a `.foam` marker file and inspect the mesh and solution in ParaView.
