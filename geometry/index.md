---
layout: default
title: Geometry Meshes
description: Geometry-only OpenFOAM mesh cases for KCS, sphere, and the supplied propeller-labelled directory.
---

<div class="case-nav"><a href="{{ '/' | relative_url }}">Home</a> / Geometry meshes</div>

# Geometry-only mesh inspection

<div class="download-box">
  <strong>Mesh pack:</strong>
  <a class="button button-primary" href="https://drive.google.com/file/d/1EPs5qfkC8DxtvWGVCt7vpBQ5aKtF2_0K/view?usp=sharing">Download KCS + sphere + supplied propeller-labelled cases</a>
  <div class="small-note">Compressed archive analyzed here: 24,203,653 bytes · SHA-256 <code>5eaacf2d031e3df1d9a649c0b8f8b847e085d9f109d60b43b88e9344904df5f3</code></div>
</div>

These three cases are treated strictly as mesh/geometry data. The analysis does not use CFD solution fields or infer solver performance.

| Case | Cells | Faces | Object patch | Hex cells | Non-orthogonality p95 / p99 |
|---|---:|---:|---|---:|---:|
| [KCS]({{ '/cases/kcs/' | relative_url }}) | 120,060 | 382,356 | `kcs` | 82.7% | 26.04° / 61.47° |
| [Sphere]({{ '/cases/sphere/' | relative_url }}) | 52,280 | 166,196 | `sphere` | 75.9% | 25.24° / 71.34° |
| [Supplied `propeller` directory]({{ '/cases/propeller/' | relative_url }}) | 55,362 | 176,533 | `sphere` | 74.3% | 25.46° / 87.04° |

<div class="notice notice-warning">
  <strong>Supplied-case integrity note:</strong> the <code>propeller</code> directory does not currently contain a distinct propeller object surface. Its object boundary is named <code>sphere</code>, has 4,368 faces, and has the same surface-coordinate signature as the sphere case. The volume mesh differs from the sphere case, so both directories are retained and analyzed independently.
</div>

## Analysis outputs

Each case page contains an object-surface rendering, a boundary-patch view, geometric mesh slices, and mesh-quality distributions.

The face-angle and skewness quantities are geometry diagnostics. They are not claimed to be identical to OpenFOAM `checkMesh`; see [the methodology]({{ '/MESH_ANALYSIS.html' | relative_url }}) for definitions and limitations.
