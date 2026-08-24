---
title: "DFT Foundations: What Kohn–Sham Equations Actually Solve"
excerpt: "A compact reference on the Hohenberg–Kohn theorems, the Kohn–Sham construction, and what the eigenvalues do (and don't) mean."
category: "Theory"
tags: [DFT, density-functional-theory, kohn-sham]
date: 2026-08-24
---

## The problem DFT solves

Many-body quantum mechanics is intractable: an electron gas in a crystal has a wavefunction that depends on the coordinates of *all* electrons simultaneously. **Density Functional Theory (DFT)** replaces that impossible problem with a tractable one: instead of the full many-body wavefunction $\Psi(\mathbf{r}_1, \dots, \mathbf{r}_N)$, everything about the ground state is determined by the **electron density** $\rho(\mathbf{r})$ — a function of just *one* spatial variable.

## Hohenberg–Kohn theorems (1964)

1. **Ground-state density determines the external potential.** Two different potentials cannot produce the same ground-state density (for non-degenerate ground states). Since the density fixes the potential, it fixes the Hamiltonian and hence *all* ground-state properties: $E_0 = E[\rho_0]$.
2. **The variational principle.** For any trial density $\tilde{\rho} \geq 0$ with $\int \tilde{\rho}\, d\mathbf{r} = N$: $E[\tilde{\rho}] \geq E[\rho_0]$. Minimizing the energy functional over densities gives the exact ground state.

The catch: the *exact* functional $E[\rho]$ is unknown.

## The Kohn–Sham construction (1965)

Kohn–Sham (KS) maps the interacting system onto a fictitious **non-interacting** system with the same density:

$$E[\rho] = T_s[\rho] + \int v_{\text{ext}}(\mathbf{r})\, \rho(\mathbf{r})\, d\mathbf{r} + E_H[\rho] + E_{xc}[\rho]$$

where $T_s$ is the kinetic energy of the non-interacting system, $E_H$ is the classical Hartree (electron–electron repulsion), and **$E_{xc}$ absorbs everything unknown** — exchange, correlation, and the kinetic-energy correction.

The resulting single-particle equations are solved self-consistently:

$$\left[-\frac{1}{2}\nabla^2 + v_{\text{ext}}(\mathbf{r}) + v_H(\mathbf{r}) + v_{xc}(\mathbf{r})\right] \psi_i(\mathbf{r}) = \varepsilon_i\, \psi_i(\mathbf{r})$$

**SCF loop:** guess $\rho$ → build the potential → solve KS equations → get new $\rho$ → repeat until converged.

## The exchange–correlation ladder

| Rung | Functionals | Idea |
|---|---|---|
| 1 | **LDA** | $E_{xc}$ from uniform electron gas; local in $\rho$ |
| 2 | **GGA** (PBE) | adds dependence on $\|\nabla \rho\|$ |
| 3 | Meta-GGA | adds kinetic-energy density |
| 4 | Hybrids (PBE0, HSE06) | mixes exact (HF-like) exchange |
| 5 | RPA / double hybrids | full non-local correlation |

Solid-state work (including most perovskite studies) uses **PBE** as the workhorse; hybrid functionals improve band gaps but cost far more.

## What the KS eigenvalues mean — and don't

- KS eigenvalues $\varepsilon_i$ are **Lagrange multipliers** of the minimization, not physical excitation energies.
- In practice: the **valence band maximum** is usually decent, and band structures from DFT are qualitatively reliable, but **PBE systematically underestimates band gaps** by 30–50% (the band-gap problem). For perovskites, this matters a lot — gap corrections often need hybrids, DFT+U, or scissor operators.
- The one *rigorous* eigenvalue: the highest occupied $\varepsilon_{\text{HOMO}}$ equals minus the ionization energy (exact DFT, Perdew–Levy).

## References

- Hohenberg & Kohn, *Phys. Rev.* **136**, B864 (1964)
- Kohn & Sham, *Phys. Rev.* **140**, A1133 (1965)
- Sholl & Steckel, *Density-Functional Theory: A Practical Introduction* (2009)
- Martin, *Electronic Structure: Basic Theory and Practical Methods* (2020)
