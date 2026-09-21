---
layout: default
title: Duisburg Test Case (DTC)
description: DTC free-surface resistance validation case generated using HydroPro's automated 3D meshing technology.
---

<div class="case-nav"><a href="{{ '/' | relative_url }}">Home</a> / DTC</div>

# Duisburg Test Case (DTC)

<div class="download-box">
  <strong>Download:</strong>
  <a class="button button-primary" href="https://drive.google.com/file/d/1Cgaiaj46WVoRbSKlV5YIN5G0zRu3pDMk/view?usp=sharing">Complete DTC OpenFOAM validation case</a>
</div>

This case presents a free-surface resistance calculation on the Duisburg Test Case (DTC) hull using a mesh generated with HydroPro's automated 3D meshing technology.

<div class="metric-row">
  <div class="metric">
    <div class="metric-label">Mesh cells</div>
    <div class="metric-value">278,418</div>
  </div>
  <div class="metric">
    <div class="metric-label">CFD resistance</div>
    <div class="metric-value">16.108 N</div>
  </div>
  <div class="metric">
    <div class="metric-label">Experiment</div>
    <div class="metric-value">15.915 N</div>
  </div>
  <div class="metric">
    <div class="metric-label">Difference</div>
    <div class="metric-value">+1.21%</div>
  </div>
</div>

## Case summary

| Item | Value |
|---|---|
| Geometry | Duisburg Test Case (DTC) |
| Domain | Half-domain with symmetry plane |
| Inflow speed | 1.668 m/s |
| CFD solver | OpenFOAM `interFoam` |
| OpenFOAM version | 5.x |
| Turbulence model | RANS, k-ω SST |
| Mesh cells | 278,418 |
| Mesh faces | 868,415 |
| Internal faces | 838,323 |
| Hull boundary faces | 10,819 |
| Final simulated time/step | 8000 |

## CFD result

Using the final 2,000 recorded force samples:

| Quantity | Mean |
|---|---:|
| Pressure resistance | 3.690 N |
| Viscous resistance | 12.419 N |
| Total resistance | 16.108 N |

The experimental total-resistance value used for comparison is **15.915 N for the half hull**.

<div class="figure-block">
  <img src="{{ '/cases/dtc/images/dtc_midship_slice.png' | relative_url }}" alt="DTC midship slice">
  <div class="figure-caption">Longitudinal midship cut close to the hull with velocity magnitude on the slice and the ship geometry overlaid.</div>
</div>

<div class="figure-block">
  <img src="{{ '/cases/dtc/images/dtc_wall_layer_cell_height.png' | relative_url }}" alt="DTC wall-layer cell height image">
  <div class="figure-caption">Near-wall cells around the midship region, colored by cell-center-to-hull distance to show the wall-normal spacing distribution.</div>
</div>


## CFD setup source

The underlying DTC CFD setup is based on the DTC tutorial case distributed with OpenFOAM.

## Inspecting the mesh

From the CFD case directory:

```bash
checkMesh
```

For visualization, create or open a `.foam` marker file and inspect the mesh and solution in ParaView.
