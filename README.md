# Von Mangoldt Hierarchies and Explicit Formulas

A research repository for investigating the derivatives of the logarithmic derivative of the Riemann zeta function and their connections to prime number theory.

## Overview

This repository contains research materials, notes, and computational tools for studying the **von Mangoldt hierarchies** $\Lambda_k(n)$ defined by:

$$(-1)^k\frac{d^k}{ds^k}\!\left(-\frac{\zeta'(s)}{\zeta(s)}\right) = \sum_{n\ge1}\frac{\Lambda_k(n)}{n^s}$$

These functions generalize the classical von Mangoldt function $\Lambda(n)$ and provide deeper insights into:
- Prime distribution and explicit formulas
- Stieltjes constants and their generating functions  
- Cumulant structures in analytic number theory
- Connections between zeros of $\zeta(s)$ and prime oscillations

## Key Research Areas

### 1. Von Mangoldt Hierarchies
- **Definition**: $\Lambda_k(p^r) = (\log p)^{k+1}r^k$ for prime powers
- **Partial Sums**: $\Psi_k(x) = \sum_{n\le x}\Lambda_k(n)$
- **Explicit Formulas**: Residue expansions involving Stieltjes constants

### 2. Stieltjes Constants
- **Laurent Expansion**: Coefficients of $\zeta(s)$ near $s=1$
- **Generating Function**: $G(t) = \zeta(1-t) + 1/t$
- **Cumulant Interpretation**: Connection to prime distribution moments

### 3. Computational Methods
- High-precision evaluation of $\Psi_k(x)$
- Zero-sum approximations using Riemann zeta zeros
- Numerical verification of explicit formula predictions

## Repository Structure

```
├── docs/                           # Research papers and lecture notes
│   ├── Von Mangoldt Hierarchies.md # Main theoretical exposition
│   ├── Stieltjes_Mellin_Lectures.md# Lecture materials
│   └── Analytic_Hierarchies.tex   # LaTeX version for publication
├── notebooks/                      # Computational experiments
├── src/                           # Code for computing hierarchies
├── data/                          # Zeta zeros and precomputed values
└── references/                    # Related papers and resources
```

## Getting Started

### Prerequisites
- Python with `mpmath` for high-precision arithmetic
- Knowledge of analytic number theory and complex analysis
- Familiarity with Dirichlet series and explicit formulas

### Quick Example
Computing the first few von Mangoldt hierarchy values:
```python
# For n = p^r (prime power):
# Λ_k(p^r) = (log p)^(k+1) * r^k

def lambda_k(p, r, k):
    """Compute Λ_k(p^r) for prime p, exponent r, hierarchy level k"""
    return (log(p)**(k+1)) * (r**k)
```

## Current Research Questions

1. **Explicit Formula Verification**: Numerical confirmation of residue expansions for $\Psi_k(x)$
2. **Error Term Analysis**: Sharp bounds under RH for oscillatory components
3. **Stieltjes-Zero Connection**: How nontrivial zeros determine $\gamma_n$ asymptotics
4. **Computational Efficiency**: Stable algorithms for large $k$ and $x$

## Recent Results

- Derived explicit polynomial forms for $P_k(\rho, \log x)$ at simple zeros
- Established Bell polynomial connections for cumulant-moment conversions
- Implemented high-precision computation of $\Psi_k(x)$ via prime-power enumeration

## Collaboration

This is an active research project between:
- **David England** (Advisor) - Theoretical development and guidance
- **Graduate Student** (Researcher) - Computational implementation and verification

## Contributing

Internal research repository. For questions about the mathematics or computational methods, please contact the research team.

## References

- Titchmarsh, E.C. *The Theory of the Riemann Zeta-Function*
- Iwaniec, H. & Kowalski, E. *Analytic Number Theory*
- Knessl, C. & Coffey, M. "Asymptotic formula for Stieltjes constants" (2011)

## License

Research materials for academic use.