# Von Mangoldt Hierarchies — Research Notes

## What This Repository Contains

- **Zero–residue polynomials** P_k(ρ, L) with EGF and linear recurrence in k
- **Explicit formula structure** for Ψ_k(x) with main terms (Stieltjes constants) + zero sums
- **Pairing/reflection identities** (conjugate, reflection, quadruplet)
- **Masters/PhD-ready examples, exercises**, and computational prompts (no code required)
- **Standalone HTML tool** to generate tables of P_k

---

## Quick Start

1. **Read the docs:** Start with [docs/README.md](docs/README.md) for navigation and quick references
2. **Try the tool:** Open `tools/pk_table.html` in your browser to compute P_k tables
3. **Explore exercises:** See [docs/Compact formula.md](docs/Compact%20formula.md) for computational prompts

---

## Key Identities (Quick Reference)

### Notation
- `λ(x) := log x` (preferred; older notes use L ≡ λ). In EGFs, e^{λ t} = x^{t}.

### Core Formulas
- **EGF** (in k): `∑ P_k(ρ,λ) t^k/k! = − e^{λ t}/(ρ + t)`
- **Linear recurrence:** `ρ P_{k+1} + (k+1) P_k = − λ^{k+1}`
- **Appell property:** `∂_λ P_k = k P_{k-1}`
- **Chain rule:** `∂_x P_k = (k/x) P_{k-1}`
- **Single-zero ODE:** `x d/dx [x^ρ P_k] = − x^ρ λ^k`

### Pairing and Reflection (Oscillatory Sums)
- **Quadruplet** (always real): Sum over {ρ, 1−ρ, ρ̄, 1−ρ̄} gives `2 x^{1/2}[A_k(λ) cos(γλ) + B_k(λ) sin(γλ)]`
- **Conjugate pairing** is a simplification if RH holds (not assumed by default)

---

## Documentation Structure

### Core Theory
1. [docs/zero-residual-polys.md](docs/zero-residual-polys.md) — Definitions, closed forms, EGF, recurrence, Bernoulli/Euler Appell connections
2. [docs/Leibniz Rule.md](docs/Leibniz%20Rule.md) — Residue derivation of P_k via Leibniz, functional-equation symmetry, reflection pairing
3. [docs/Compact formula.md](docs/Compact%20formula.md) — Compact formulas + Masters/PhD exercises and computational prompts
4. [docs/Hierarchy Interdependence Theorem.md](docs/Hierarchy%20Interdependence%20Theorem.md) — ∂_λ and ∂_x interdependence; ODEs for zero terms

### Advanced Topics
- [quad upon generating function.md](quad%20upon%20generating%20function.md) — Quadruplet EGF kernel and coefficient extraction

### Navigation
- **[docs/README.md](docs/README.md)** — Full documentation index with notation reference
- **[OPEN_QUESTIONS.md](OPEN_QUESTIONS.md)** — Unresolved problems and research directions
- **[TODO.md](TODO.md)** — Implementation tasks and documentation improvements

---

## Tools

### pk_table.html
**Location:** `tools/pk_table.html`

**Features:**
- Compute P_k tables for given zeros
- Export to CSV and LaTeX
- Standalone (runs entirely in browser)

**Usage:** Open in any modern browser (Chrome, Firefox, Safari)

---

## General L-Functions

- P_k(ρ,·) is **universal at simple zeros** (depends only on ρ and λ)
- Main-term coefficients "γ_m" generalize to c_m(λ) from −L′/L(1+u) at s=1
  - (or from the completed L if you absorb Γ-factors)
- If L has **no pole at 1**, the `x·poly(λ)` main term vanishes

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for:
- Style and math conventions
- Pull request checklist
- Citation guidelines

---

## Rendering and Conventions

- **Inline math:** `$...$`
- **Display math:** `$$ ... $$`
- **Filenames:** Prefer no spaces or '#' characters (to be standardized)
- **Previewer:** Use MathJax/KaTeX support (e.g., VS Code "Markdown Preview Enhanced")

---

## Status and Roadmap

### Current Focus
- Organizing documentation structure
- Adding worked examples and exercises
- Enhancing HTML tools with visualization

### Next Steps
See [TODO.md](TODO.md) for detailed task list and [OPEN_QUESTIONS.md](OPEN_QUESTIONS.md) for research directions.

---

**Maintainer:** David England  
**License:** TBD (see TODO.md)  
**Last Updated:** 2024