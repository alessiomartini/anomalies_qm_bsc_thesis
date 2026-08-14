# Scale Anomaly in Quantum Mechanics — BSc Thesis

LaTeX source of the Bachelor's thesis *Anomalies in Quantum Mechanics*, by
Alessio Martini (student no. 867624), Università degli Studi di Milano-Bicocca,
supervised by Noppadol Mekareeya.

The compiled thesis is committed as
[`Tesi_Martini_867624.pdf`](Tesi_Martini_867624.pdf).

## What the thesis is about

An **anomaly** is a symmetry that holds in the classical description of a system
but is broken by quantization. The thesis studies one concrete and fully solvable
instance of this: the breaking of **scale invariance** by the attractive
inverse-square potential

$$V(x) = -\frac{\lambda}{x^2}$$

Classically this potential has no length scale — the Schrödinger equation is
invariant under $x \to a x$. That invariance is exactly what makes the quantum
problem ill-posed: the naive Hamiltonian is not self-adjoint, and the spectrum
it produces is an unbounded, uncountable continuum of bound states with no ground
state, which is unphysical.

The resolution developed here is the **method of self-adjoint extensions**.
Choosing a self-adjoint extension of the Hamiltonian requires fixing a boundary
condition at the origin, and that boundary condition necessarily introduces a
length scale. The scale symmetry present in the classical problem is therefore
broken by the very act of making the quantum theory well defined — a *dimensional
transmutation*, and the mechanism behind the anomaly. The result is a discrete,
bounded-below spectrum with physically meaningful bound states.

## Structure of the document

| Chapter | File under `contents/` | Content |
| --- | --- | --- |
| Preface | `preface.tex` | Scope and motivation |
| Introduction | `introduction.tex` | What an anomaly is |
| — | `symmetry_classification.tex` | Classification of symmetry breakings (explicit, spontaneous, anomalous) |
| Why the $1/x^2$ potential? | `generic_potentials.tex` | The stationary Schrödinger equation for generic potentials |
| — | `peculiarities_potential.tex` | What makes the inverse-square potential special: scale invariance and the fall to the centre |
| The Method | `selfadjoint.tex` | Self-adjoint extensions, deficiency indices, von Neumann's theory |
| Content | `free_particle_half_line.tex` | Worked warm-up: the free particle on the half line |
| — | `particle_xsquared.tex` | The main calculation: the particle in the $1/x^2$ potential |
| — | `conclusion.tex` | Conclusions |
| Analogy from the literature | `delta_potential.tex` | The two-dimensional $\delta$-potential, which exhibits the same anomaly |

Figures are committed as ready-made PDFs (`bessel.pdf`, `potential.pdf`,
`free_boundstate.pdf`, `free_phaseshift.pdf`); the Mathematica notebook that
generated them lives in the companion private repository.

## Repository layout

```
thesis.tex             Master file: document class, packages, page style, \input order
contents/*.tex         One file per chapter or section (see the table above)
bibliography.bib       BibTeX references
title_page.pdf         Title page, included verbatim with \includepdf
cover_press.pdf        Printed cover
STIX2Math.otf          Math font, embedded so the build is reproducible
Tesi_Martini_867624.pdf  The compiled thesis
```

## Building

The document loads `fontspec`, `unicode-math`, `polyglossia` and
`graphicx[xetex]`, with the bundled `STIX2Math.otf` as the math font and
Libertinus for the text, so it must be compiled with **XeLaTeX** — not pdfLaTeX
— and with **biber** as the bibliography backend. Run it from the repository
root so the relative `\input` and font paths resolve:

```bash
xelatex thesis.tex
biber thesis
xelatex thesis.tex
xelatex thesis.tex
```

## Related repositories

- [`bsc-thesis-scale-anomaly-archive`](https://github.com/alessiomartini/bsc-thesis-scale-anomaly-archive)
  — the full working archive: defence slides, draft history, figure notebooks and
  university paperwork.
- [`msc-thesis-non-invertible-symmetries`](https://github.com/alessiomartini/msc-thesis-non-invertible-symmetries)
  — the MSc thesis, which continues the same thread on anomalies into generalized
  and non-invertible symmetries.
