---
title: "Research"
permalink: /research/
layout: single
author_profile: true
---

## Overview

I work in **computational materials science**, using **first-principles (ab initio) methods** — chiefly Density Functional Theory — to understand how the atomic and electronic structure of materials determines their properties, with a focus on **perovskite materials**.

Rather than fitting to experiment, the approach is to solve the electronic structure problem directly: build the crystal, relax the structure, and compute band structures, densities of states, and optical response from the ground-state density.

## Research Areas

### 1. Inorganic perovskites for photovoltaics & optoelectronics

Perovskites (ABX₃) are remarkably tunable — composition, octahedral tilting, and strain all reshape the band edges. I compute **band structures, densities of states, and optical properties** of tin-based and inorganic perovskites (currently CH<sub>3</sub>NH<sub>3</sub>SnI<sub>3</sub>) to understand what makes them promising for **solar cells and optoelectronic devices**, and how device-level behavior (SCAPS-1D) connects back to the atomistic picture.

### 2. Optical & electrical properties from first principles

Connecting electronic structure to optical response — absorption and the dielectric function computed within the independent-particle approximation, with an eye toward where electron–hole (excitonic) effects become essential.

### 3. Machine learning for materials

Using ML models (scikit-learn) to predict material properties and complement first-principles calculations — screening promising candidates faster than full DFT campaigns can.

### 3. Computational methods & workflow

First-principles calculations live or die by their convergence and reproducibility. I care about doing this properly: systematic **convergence testing**, validated pseudopotentials (SSSP), scripted and version-controlled workflows, and honest error assessment.

## Methods & Tools

| | |
|---|---|
| **Theory** | Density Functional Theory, plane-wave pseudopotential method |
| **Codes** | Quantum ESPRESSO (`pw.x`, `bands.x`, `dos.x`, `projwfc.x`, `epsilon.x`), SCAPS-1D |
| **Machine learning** | Python — NumPy, Pandas, scikit-learn, Xarray |
| **Pseudopotentials** | SSSP efficiency/precision libraries |
| **Workflow** | Linux/Shell, Git & GitHub, VESTA, LaTeX, Google Cloud Platform |

## Typical Workflow

1. Build & relax the structure (`relax` / `vc-relax`)
2. Self-consistent field calculation → converged charge density
3. Non-self-consistent runs: band paths (high-symmetry k-points), dense grids for DOS
4. Post-processing & analysis: orbital character, optical response
5. Documentation — every calculation scripted, versioned, and written up

See the [Notes](/notes/) section for the cheatsheets and theory reference notes behind this workflow, and [Projects](/projects/) for concrete calculations.

## Future Directions

- Machine-learning-based property prediction integrated with DFT campaigns
- Defect states and doping effects in perovskite lattices
- Beyond-PBE band gaps: hybrid functionals, DFT+U, and comparison across rungs of the XC ladder
- Excitonic and many-body corrections to optical spectra
