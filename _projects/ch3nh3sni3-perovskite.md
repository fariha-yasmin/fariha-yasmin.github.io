---
title: "First-Principles Investigation of Electrical and Optical Properties of CH₃NH₃SnI₃ Perovskite with Machine Learning-Based Property Prediction"
excerpt: "DFT calculations (Quantum ESPRESSO) on the tin-based perovskite CH₃NH₃SnI₃, device-level simulation in SCAPS-1D, and ML-based property prediction — integrated in one workflow."
layout: single
tags: [DFT, perovskites, machine-learning, photovoltaics]
date: 2026-08-24
---

## Overview

This project combines **first-principles calculations**, **device-level simulation**, and **machine learning** to study CH<sub>3</sub>NH<sub>3</sub>SnI<sub>3</sub> — a lead-free, tin-based halide perovskite of interest for **photovoltaic and optoelectronic applications**.

The central question: what are the fundamental electrical and optical properties of this material, and can ML models trained on computed data predict such properties efficiently for related systems?

## Components

### 1. First-principles calculations (Quantum ESPRESSO)

- Structural relaxation of the CH<sub>3</sub>NH<sub>3</sub>SnI<sub>3</sub> unit cell
- Self-consistent field (SCF) calculation for the converged charge density
- Non-self-consistent field (NSCF) calculations along high-symmetry k-paths and dense grids
- **Electronic band structure** and **density of states** — identifying band gap and band-edge character
- **Optical properties** — absorption and dielectric response

### 2. Device-level simulation (SCAPS-1D)

- Translating material parameters (band gap, absorption, dielectric constants) into thin-film solar cell device behavior
- Studying how the computed material properties affect photovoltaic performance

### 3. Machine learning property prediction

- Training ML models (scikit-learn) on computed/curated material property data
- Predicting target properties for candidate materials as a fast screen ahead of full DFT campaigns

## Tools Used

- Quantum ESPRESSO (`pw.x`, `bands.x`, `dos.x`), SSSP pseudopotentials
- SCAPS-1D
- Python (NumPy, Pandas, scikit-learn, Xarray)
- VESTA for structure visualization

## Status

*In progress — results and figures will be added as they become available.*
