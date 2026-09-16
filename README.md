# HydroPro Mesher Validation

CFD validation cases generated using HydroPro's automated 3D meshing technology.

This repository documents the performance of the current HydroPro meshing MVP on representative marine-hydrodynamics and external-flow problems. Each validation case includes the generated mesh, CFD results, comparison data, and a downloadable OpenFOAM case for independent inspection and testing.

---

## Validation Cases

### Duisburg Test Case (DTC)

Free-surface ship-resistance simulation using OpenFOAM.

The DTC case evaluates the generated mesh on a marine free-surface problem involving hull boundary layers, wave generation, and resistance prediction.

**Case summary**

| Parameter | Value |
|---|---:|
| Flow speed | 1.668 m/s |
| Solver | OpenFOAM `interFoam` |
| Turbulence model | k-ω SST |
| Mesh cells | 278,418 |
| Experimental resistance — half hull | 15.915 N |
| CFD resistance | 16.108 N |
| Difference from experiment | +1.21% |

The underlying CFD setup is based on the DTC case available in the OpenFOAM tutorials.

**[View DTC validation details](cases/dtc/)**

**[⬇ Download complete DTC OpenFOAM validation case](https://drive.google.com/file/d/1Cgaiaj46WVoRbSKlV5YIN5G0zRu3pDMk/view?usp=sharing)**

---

### Ahmed Body — 25° Slant

Steady external-flow RANS simulation of the 25° Ahmed body at 40 m/s.

This case provides an additional validation outside marine hydrodynamics and evaluates the mesher on bluff-body flow, separation, wake development, and aerodynamic force prediction.

**Case summary**

| Parameter | Value |
|---|---:|
| Freestream velocity | 40 m/s |
| Solver | OpenFOAM `simpleFoam` |
| Turbulence model | k-ω SST |
| Mesh cells | 2,082,880 |
| Computed Cd | 0.29249 |
| Reference Cd | ≈ 0.299 |
| Difference | -2.18% |
| Computed Cl | 0.33839 |

The CFD setup used as the starting point for this validation is based on the public Ahmed Bluff Body CFD Validation case by Nathan Rooy:

https://github.com/nathanrooy/ahmed-bluff-body-cfd/tree/master/openfoam_rans

The final mesh used for the HydroPro validation was generated using HydroPro's meshing technology.

**[View Ahmed Body validation details](cases/ahmed25/)**

**[⬇ Download complete Ahmed Body OpenFOAM validation case](https://drive.google.com/file/d/1D6JRIJXeYbrt8wvAJRpOY3rBzG_ywE7a/view?usp=sharing)**

---

## Validation Approach

The validation campaign focuses on quantities that matter directly for CFD applications:

- mesh quality and robustness;
- boundary-layer treatment;
- solver compatibility;
- force prediction;
- free-surface and wake resolution;
- computational mesh size;
- repeatability on different geometry classes.

Additional validation cases will be added as the meshing technology develops and is applied to new CFD problems.

---

## Repository Structure

```text
mesher-validation/
├── README.md
├── cases/
│   ├── dtc/
│   │   ├── README.md
│   │   └── images/
│   └── ahmed25/
│       ├── README.md
│       └── images/