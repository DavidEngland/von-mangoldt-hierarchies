# Von Mangoldt Hierarchies — Research Notes

What this repo contains
- Zero–residue polynomials P_k(ρ, L) with EGF and linear recurrence in k
- Explicit formula structure for Ψ_k(x) with main terms (Stieltjes constants) + zero sums
- Pairing/reflection identities (conjugate, reflection, quadruplet)
- Masters/PhD-ready examples, exercises, and computational prompts (no code required)
- A standalone HTML tool to generate tables of P_k

Notation and key identities
- λ(x) := log x (preferred; older notes use L ≡ λ). In EGFs, e^{λ t} = x^{t}.
- EGF (in k): ∑ P_k(ρ,λ) t^k/k! = − e^{λ t}/(ρ + t).
- Linear recurrence: ρ P_{k+1} + (k+1) P_k = − L^{k+1}.
- Appell property: ∂_L P_k = k P_{k-1}.
- Chain rule: ∂_x P_k = (k/x) P_{k-1}.
- Single-zero ODE: x d/dx [x^ρ P_k] = − x^ρ L^k.

Pairing and reflection (oscillatory sums)
- Quadruplet (always real): sum over {ρ, 1−ρ, ρ̄, 1−ρ̄} gives 2 x^{1/2}[A_k(L) cos(γL) + B_k(L) sin(γL)].
- Conjugate pairing is a simplification if RH holds (not assumed by default).

Start here (core docs)
- See docs/README.md for the index, notation, and quick references.
- docs/zero-residual-polys.md — definitions, closed forms, EGF, recurrence, Bernoulli/Euler Appell connections.
- docs/Leibniz Rule.md — residue derivation of P_k via Leibniz, functional-equation symmetry, reflection pairing.
- docs/Compact formula.md — compact formulas + Masters/PhD exercises and computational prompts.
- docs/Hierarchy Interdependence Theorem.md — ∂_L and ∂_x interdependence; ODEs for zero terms.
- quad upon generating function.md — quadruplet EGF kernel and coefficient extraction.

Tools
- tools/pk_table.html — standalone browser page to compute and render P_k tables; supports CSV/LaTeX.

Conventions and rendering
- Inline math: $...$, display math: $$ ... $$.
- Prefer filenames without spaces or ‘#’.
- Use a previewer supporting MathJax/KaTeX (e.g., VS Code “Markdown Preview Enhanced”).

Contributing
- See CONTRIBUTING.md for style, math conventions, and PR checklist.

General L-functions
- P_k(ρ,·) is universal at simple zeros (depends only on ρ and λ).
- Main-term coefficients “γ_m” generalize to c_m(L) from −L′/L(1+u) at s=1 (or from the completed L if you absorb Γ-factors). If L has no pole at 1, the x·poly(λ) main term vanishes.