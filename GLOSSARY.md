# Glossary (minimal)

- Λ(n): von Mangoldt function; log p if n = p^k, else 0.
- Λ_k(n): hierarchy via $(-1)^k d^k/ds^k[-\zeta'/\zeta] = \sum \Lambda_k(n) n^{-s}$.
- Ψ_k(x): partial sums $\sum_{n\le x}\Lambda_k(n)$.
- ρ: nontrivial zero of an L-function (simple, unless stated).
- P_k(ρ, L): zero–residue polynomial (degree k) in $L=\log x$.
- γ_n: Stieltjes constants (Laurent coefficients at s=1).

# Mathematical Glossary

## Core Functions and Constants

| Symbol | Name | Definition | Notes |
|--------|------|------------|-------|
| $\Lambda(n)$ | von Mangoldt function | $\log p$ if $n=p^k$, else $0$ | Classical arithmetic function |
| $\Lambda_k(n)$ | von Mangoldt hierarchy | $(\log p)^{k+1}r^k$ if $n=p^r$ | Higher-order generalizations |
| $\Psi(x)$ | Chebyshev function | $\sum_{n\le x}\Lambda(n)$ | Prime counting with weights |
| $\Psi_k(x)$ | Generalized Chebyshev | $\sum_{n\le x}\Lambda_k(n)$ | Higher-order partial sums |
| $\gamma_m$ | Stieltjes constants | Laurent coefficients of $\zeta(s)$ at $s=1$ | $\gamma_0 = \gamma$ (Euler's constant) |
| $\zeta(s)$ | Riemann zeta function | $\sum_{n=1}^\infty n^{-s}$ | Fundamental L-function |
| $\psi(z)$ | Digamma function | $\Gamma'(z)/\Gamma(z)$ | Logarithmic derivative of Gamma |

## Key Identities

### Dirichlet Series
$$-\frac{\zeta'(s)}{\zeta(s)} = \sum_{n\ge1}\frac{\Lambda(n)}{n^s}$$

### von Mangoldt Hierarchy
$$(-1)^k\frac{d^k}{ds^k}\!\left(-\frac{\zeta'(s)}{\zeta(s)}\right) = \sum_{n\ge1}\frac{\Lambda_k(n)}{n^s}$$

### Stieltjes Generating Function
$$G(t) = \sum_{n=0}^\infty\frac{\gamma_n}{n!}t^n = \zeta(1-t)+\frac{1}{t}$$

### Explicit Formula Structure
$$\Psi_k(x) = M_k(x) + \sum_\rho x^\rho P_k(\rho,\log x) + O(1)$$

where:
- $M_k(x)$ = main term involving Stieltjes constants
- $\rho$ = nontrivial zeros of $\zeta(s)$
- $P_k(\rho,\log x)$ = polynomial in $\log x$

## Notation Conventions

| Context | Notation | Meaning |
|---------|----------|---------|
| Prime powers | $p^r$ | Prime $p$ to power $r$ |
| Complex variable | $s = \sigma + it$ | Standard in zeta theory |
| Zeros | $\rho = \beta + i\gamma$ | Nontrivial zeros of $\zeta(s)$ |
| Asymptotic | $f(x) \sim g(x)$ | $\lim_{x\to\infty} f(x)/g(x) = 1$ |
| Big O | $f(x) = O(g(x))$ | $|f(x)| \le C|g(x)|$ for some $C$ |

## Research Terminology

- **Hierarchy**: The family $\{\Lambda_k(n)\}_{k\ge0}$ of generalized von Mangoldt functions
- **Cumulant interpretation**: Viewing $\gamma_m$ as cumulants of a log-weighted prime measure
- **Residue expansion**: Expression obtained by shifting contours and computing residues
- **Main term**: Leading asymptotic contribution (polynomial in $\log x$)
- **Oscillatory term**: Contributions from nontrivial zeros (involving $x^\rho$)
- **Zero-free region**: Region in complex plane where $\zeta(s) \neq 0$

## Computational Terms

- **Prime-power enumeration**: Efficient algorithm computing sums over $p^r \le x$
- **Truncated zero sum**: Finite approximation using first $N$ zeros
- **High precision arithmetic**: Using libraries like `mpmath` for arbitrary precision
- **Conjugate pairing**: Summing $\rho$ and $\bar{\rho}$ together for real results
