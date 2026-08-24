---
title: "Quantum ESPRESSO Workflow Cheatsheet"
excerpt: "The standard pw.x pipeline — relax → SCF → NSCF → bands/DOS — with the key variables and convergence checks I use in every calculation."
category: "Tools"
tags: [quantum-espresso, DFT, workflow]
date: 2026-08-24
---

## The pipeline

A typical electronic-structure calculation is a **chain of `pw.x` runs**, each consuming the previous output:

```
relax  →  scf  →  nscf  →  bands.x / dos.x / projwfc.x
(atoms move) (ρ converges) (eigenvalues on dense/paths)  (post-processing)
```

## 1. Structural relaxation

```fortran
&CONTROL
  calculation = 'relax'        ! or 'vc-relax' to also optimize the cell
  prefix      = 'perovskite'
  outdir      = './tmp/'
  pseudo_dir  = './pseudo/'
/
&SYSTEM
  ibrav       = 0              ! use CELL_PARAMETERS when ibrav = 0
  ecutwfc     = 50.0           ! plane-wave cutoff (Ry) — MUST be convergence-tested
  nat         = ...
  ntyp        = ...
/
&ELECTRONS
  conv_thr    = 1.0d-6         ! total-energy convergence (Ry)
  mixing_beta = 0.3
/
ATOMIC_SPECIES ... / ATOMIC_POSITIONS ... / K_POINTS automatic
```

Use `vc-relax` with `cell_dofree` for cell optimization. **Always re-run SCF after relax** on the final geometry.

## 2. SCF — the converged charge density

`calculation = 'scf'` produces the self-consistent $\rho(\mathbf{r})$, total energy, and forces. Everything downstream reuses this density (`restart_mode = 'from_scratch'`, then `'restart'` if needed).

## 3. NSCF — eigenvalues on dense grids or k-paths

```fortran
calculation = 'nscf'
nbnd        =  ...   ! more bands than default for DOS/optics
```

- For **DOS**: `K_POINTS automatic` with a dense grid (e.g. 8×8×8 for conventional cells)
- For **band structure**: `K_POINTS crystal_b` with a high-symmetry path (e.g. `X–Γ–M–R–Γ` for cubic perovskites; generate paths with *SeeK-path* or *XCrySDen*)

## 4. Post-processing

| Tool | Job |
|---|---|
| `bands.x` | reorders/interpolates eigenvalues for band structure plots |
| `dos.x` | total & projected density of states |
| `projwfc.x` | projected DOS, orbital character (atomic projections) |
| `epsilon.x` | dielectric function / optical spectra (IPA) |

## Convergence checklist (do this *before* believing any result)

1. **`ecutwfc`** — increase until total energy changes < ~10 meV/atom
2. **k-grid** — densify until energy/band gap stable
3. **Pseudopotentials** — use a tested library (**SSSP** efficiency/precision); verify the recommended cutoff
4. **`conv_thr`** — tight enough that forces/energies are stable

## Common pitfalls

- **Metallic or small-gap systems** (many perovskites): add smearing — `occupations = 'smearing'`, `smearing = 'gaussian'`, `degauss ~ 0.01–0.02 Ry`; otherwise SCF oscillates
- **Band gap too small?** That's often PBE, not a bug — check against hybrids/experiment before panicking
- **`nbnd` too low** → empty states missing, DOS/BSE-adjacent analysis wrong
- Forgetting that `outdir`/`prefix` must **match** across scf → nscf → post-processing
- Mixing too aggressive (`mixing_beta > 0.4`) → SCF fails to converge on hard systems
