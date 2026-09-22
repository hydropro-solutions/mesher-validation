---
layout: default
title: Mesh Analysis Methodology
description: Geometry-only OpenFOAM mesh inspection methodology and visualization notes. 
---

# Geometry-only mesh analysis methodology

The KCS, sphere, and propeller cases are treated strictly as **geometry and mesh data**. No CFD solution fields, convergence histories, forces, or solver-result claims are used on these pages.

## Visualizations

The surface figures show the supplied object boundary tessellation. The mesh-section figures are **crinkle-style views**: cells intersecting the reference plane are retained with their original cell faces instead of creating a smooth planar cutter. This makes local refinement and topology transitions visible without inventing a new triangulated slice.

The supplied KCS case is a half-domain mesh about `y = 0`. For the KCS **surface and object-patch figures only**, the hull patch is mirrored about `y = 0` so visitors can inspect the complete hull shape. Cell, face, point, and patch counts remain those of the original supplied half-domain mesh.

## Reported quantities

The pages report mesh topology counts, boundary-patch face counts, object bounds and surface area, cell-volume/equivalent-length distributions, internal-face non-orthogonality, and a centroid-line skewness proxy.

Equivalent cell length is `V^(1/3)`. The non-orthogonality and skewness values are independent geometry diagnostics computed from the mesh connectivity and geometry; they are not presented as OpenFOAM `checkMesh` pass/fail results.

## Downloadable dataset

The repository includes a geometry-only ZIP containing only the OpenFOAM mesh topology needed for inspection: `points`, `faces`, `owner`, `neighbour`, and `boundary`, plus an empty `foam.foam` marker for each case. It contains no CFD run results.
