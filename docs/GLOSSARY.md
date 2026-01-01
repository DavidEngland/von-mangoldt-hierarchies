# Glossary of Symbols

## Primary Notation

### Variables and Functions
| Symbol | Meaning | Notes |
|--------|---------|-------|
| `λ` | log x | Preferred notation (modern) |
| `L` | log x | Older notation; equivalent to λ |
| `x` | Real variable | Usually x > 1 |
| `s` | Complex variable | Standard in L-function theory |
| `ρ` | Zero of L-function | Usually written ρ = β + iγ |
| `β` | Real part of ρ | Re(ρ) |
| `γ` | Imaginary part of ρ | Im(ρ) |
| `ρ̄` | Complex conjugate | ρ̄ = β − iγ |

### Polynomials and Sequences
| Symbol | Meaning | Definition |
|--------|---------|------------|
| `P_k(ρ, λ)` | k-th zero-residue polynomial | See recurrence or EGF |
| `A_k(λ)` | Cosine coefficient (quadruplet) | Real polynomial in λ |
| `B_k(λ)` | Sine coefficient (quadruplet) | Real polynomial in λ |
| `Ψ_k(x)` | k-th von Mangoldt hierarchy function | Explicit formula sum |
| `γ_m` | Stieltjes constants | For Riemann ζ |
| `c_m(λ)` | Generalized Stieltjes constants | For general L-functions |

### Operators
| Symbol | Meaning | Notes |
|--------|---------|-------|
| `∂_λ` | Partial derivative w.r.t. λ | ∂/∂λ |
| `∂_x` | Partial derivative w.r.t. x | ∂/∂x |
| `d/dx` | Total derivative | Standard calculus |
| `Res_{s=ρ}` | Residue at s = ρ | Complex analysis |

## Special Constants and Functions

### Number-Theoretic
| Symbol | Meaning | Context |
|--------|---------|---------|
| `Λ(n)` | von Mangoldt function | Λ(p^k) = log p |
| `ζ(s)` | Riemann zeta function | ∑ 1/n^s |
| `L(s, χ)` | Dirichlet L-function | Character χ |
| `ξ(s)` | Completed zeta function | Satisfies ξ(s) = ξ(1−s) |

### Polynomial Families
| Symbol | Meaning | Relation |
|--------|---------|----------|
| `B_n(x)` | Bernoulli polynomials | Appell sequence |
| `E_n(x)` | Euler polynomials | Appell sequence |

## Pairing Notation

### Sets of Zeros
| Symbol | Meaning | Cardinality |
|--------|---------|-------------|
| `{ρ, ρ̄}` | Conjugate pair | 2 (or 1 if γ = 0) |
| `{ρ, 1−ρ}` | Reflection pair | 2 (or 1 if β = 1/2) |
| `{ρ, ρ̄, 1−ρ, 1−ρ̄}` | Quadruplet | 4 (or fewer if symmetries) |

### Pairing Results
| Expression | Meaning | Properties |
|------------|---------|------------|
| `x^ρ P_k + x^ρ̄ P̄_k` | Conjugate pairing | Real-valued |
| `x^ρ P_k + x^{1−ρ} Q_k` | Reflection pairing | Uses functional equation |
| `2x^{1/2}[A cos(γλ) + B sin(γλ)]` | Quadruplet pairing | Always real |

## Subscripts and Indices

| Convention | Meaning | Example |
|------------|---------|---------|
| `k` | Hierarchy level | P_k, Ψ_k |
| `n` | Summation index | ∑_{n=1}^∞ |
| `m` | Stieltjes index | γ_m, c_m |
| `j` | Zero index | ρ_j (j-th zero) |

## Greek Letters Reference

| Letter | Common Use | Pronunciation |
|--------|------------|---------------|
| `γ` | Imaginary part of ρ; Euler's constant | gamma |
| `ρ` | Zero of L-function | rho |
| `λ` | Logarithm (log x) | lambda |
| `ψ` | Chebyshev function | psi |
| `Ψ` | Hierarchy function | capital psi |
| `ζ` | Riemann zeta | zeta |
| `χ` | Dirichlet character | chi |
| `ξ` | Completed zeta | xi |

## Notation Variants

### Historical vs. Modern
| Old | New | Note |
|-----|-----|------|
| `L` | `λ` | λ preferred in new docs |
| `log x` | `λ(x)` | Functional notation |
| `P_k(ρ, L)` | `P_k(ρ, λ)` | Argument notation |

### Document-Specific
Some older documents in this repository may use `L` instead of `λ`. They are equivalent:
- `P_k(ρ, L) = P_k(ρ, λ)` where `L = λ = log x`

## Asymptotic Notation

| Symbol | Meaning | Example |
|--------|---------|---------|
| `O(·)` | Big-O | f = O(g) |
| `o(·)` | Little-o | f = o(g) |
| `∼` | Asymptotic to | f ∼ g as x → ∞ |
| `≪` | Much less than (Vinogradov) | f ≪ g |

## Conventions

### Summation
- **Zeros:** Sum over non-trivial zeros unless stated
- **Convergence:** Sums over zeros typically need analytic continuation or pairing
- **Ordering:** Zeros ordered by imaginary part γ_1 < γ_2 < ...

### Integration
- **Contours:** Standard conventions for inverse Mellin/Perron
- **Branch cuts:** log branch: −π < arg(·) ≤ π

---

**See Also:**
- [docs/README.md](README.md) — Full documentation index
- [Main README](../README.md) — Quick reference section
