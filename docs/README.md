# Documentation Index

## Quick Navigation

### Core Theory
1. **[Zero-Residual Polynomials](zero-residual-polys.md)** — Definitions, closed forms, EGF, recurrence, Appell property
2. **[Leibniz Rule](Leibniz%20Rule.md)** — Residue derivation, functional equation symmetry, reflection pairing
3. **[Compact Formula](Compact%20formula.md)** — Compact representations with exercises and computational prompts
4. **[Hierarchy Interdependence Theorem](Hierarchy%20Interdependence%20Theorem.md)** — Derivative interdependence and ODEs

### Advanced Topics
- **[Quadruplet Generating Function](../quad%20upon%20generating%20function.md)** — EGF kernel and coefficient extraction for quadruplet sums

## Notation Reference

### Standard Symbols
- `λ(x) := log x` — preferred notation (older notes may use `L`)
- `ρ` — zero of L-function
- `γ := Im(ρ)` — imaginary part of zero
- `P_k(ρ, λ)` — k-th zero-residue polynomial

### Key Identities

**Exponential Generating Function:**
```
∑_{k≥0} P_k(ρ,λ) t^k/k! = − e^{λt}/(ρ + t)
```

**Linear Recurrence:**
```
ρ P_{k+1} + (k+1) P_k = − λ^{k+1}
```

**Appell Property:**
```
∂_λ P_k = k P_{k-1}
```

**Chain Rule:**
```
∂_x P_k = (k/x) P_{k-1}
```

**Single-Zero ODE:**
```
x d/dx [x^ρ P_k] = − x^ρ λ^k
```

## Pairing Formulas

### Quadruplet (Always Real)
Sum over `{ρ, 1−ρ, ρ̄, 1−ρ̄}`:
```
2 x^{1/2} [A_k(λ) cos(γλ) + B_k(λ) sin(γλ)]
```

### Conjugate Pairing
Simplification when RH holds (not assumed by default).

## Exercise Levels

- **Computational** — Verify identities numerically or symbolically
- **Masters** — Prove structural theorems using given tools
- **PhD** — Extend theory or discover new connections

## Reading Order

### First Time
1. Start with [zero-residual-polys.md](zero-residual-polys.md) for definitions
2. Read [Leibniz Rule.md](Leibniz%20Rule.md) for derivation techniques
3. Work through [Compact formula.md](Compact%20formula.md) exercises

### Deep Dive
1. Study [Hierarchy Interdependence Theorem.md](Hierarchy%20Interdependence%20Theorem.md)
2. Explore quadruplet theory in [quad upon generating function.md](../quad%20upon%20generating%20function.md)

## Related Files

- **[Main README](../README.md)** — Repository overview
- **[Open Questions](../OPEN_QUESTIONS.md)** — Unresolved problems and conjectures
- **[TODO](../TODO.md)** — Implementation and documentation tasks
- **[Contributing Guide](../CONTRIBUTING.md)** — Style and PR guidelines
