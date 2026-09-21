---
layout: default
title: Mesh Analysis Methodology
description: Reproducible geometry-only OpenFOAM mesh analysis methodology and limitations.
---

# Geometry-only mesh analysis methodology

The `kcs`, `sphere`, and `propeller` package is treated as a **geometry/mesh validation set**. No CFD-result claims are made from these cases.

## Reproduce the analysis

Download and extract the geometry pack, then run:

```bash
```

The published figures summarize surface views, boundary-patch structure, geometric mesh slices, and mesh-quality distributions for each case.

## Reported quantities

- topology: cells, points, faces, internal faces, boundary faces and patch face counts;
- cell-type mix from VTK's OpenFOAM reader;
- object-patch dimensions and triangulated surface area;
- cell-volume statistics and equivalent cell length, defined as `V^(1/3)`;
- internal-face non-orthogonality, computed from each face area vector and the line joining adjacent cell centers;
- a centroid-line skewness proxy, defined as the offset between the face centroid and the cell-center-line/face-plane intersection, normalized by adjacent cell-center distance;
- exact boundary-surface coordinate signatures, used to detect duplicate object surfaces across cases.

## Important limitation

The non-orthogonality and skewness statistics are independent geometry diagnostics. They are **not a byte-for-byte reimplementation of OpenFOAM `checkMesh`**, and should not be interpreted as OpenFOAM pass/fail thresholds. The skewness proxy can become numerically very large for nearly parallel center-lines and face planes, so the report emphasizes its median, 95th and 99th percentiles rather than the absolute maximum.

## Data-integrity finding

The supplied case directory named `propeller` currently exposes an object boundary patch named `sphere`. Its object-surface point coordinates have the same signature as the supplied `sphere` case. The two volume meshes are not identical—the cell counts and local refinement differ—but the object boundary geometry is the same spherical surface in the supplied files. The website reports this explicitly so a mislabeled benchmark is not presented as a propeller geometry.
