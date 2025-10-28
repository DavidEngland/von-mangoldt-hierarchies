# Von Mangoldt Hierarchies and Explicit Formulas

A research repository investigating the derivatives of the logarithmic derivative of the Riemann zeta function and their connections to prime number theory.

## 🎯 Quick Start

**New to this research?** Start with:
1. [Student Recruitment Post](student_recruitment_post.md) - Overview and motivation
2. [Von Mangoldt Hierarchies Guide](von%20Mangoldt%20hierarchies.md) - Core mathematical definitions
3. [Handoff for Graduate Students](Handoff_for_grad_student.md) - Practical implementation guide

## 📊 Research Overview

This repository explores the **von Mangoldt hierarchies** $\Lambda_k(n)$ defined by:

$$(-1)^k\frac{d^k}{ds^k}\!\left(-\frac{\zeta'(s)}{\zeta(s)}\right) = \sum_{n\ge1}\frac{\Lambda_k(n)}{n^s}$$

These functions generalize the classical von Mangoldt function and reveal deep connections between:
- Prime distribution and explicit formulas
- Stieltjes constants and their generating functions  
- Cumulant structures in analytic number theory
- Zeros of $\zeta(s)$ and prime oscillations

### Key Results

- **Explicit Formula**: $\Lambda_k(p^r) = (\log p)^{k+1}r^k$ for prime powers
- **Partial Sums**: $\Psi_k(x) = \sum_{n\le x}\Lambda_k(n)$ with residue expansions
- **Stieltjes Connection**: Coefficients involve Stieltjes constants $\gamma_m$

## 📁 Repository Structure

### Core Theory
- [`Von Mangoldt Hierarchies and Stieltjes Constants.md`](Von%20Mangoldt%20Hierarchies%20and%20Stieltjes%20Constants%20in%20Explicit%20Formulas.md) - Main theoretical exposition
- [`von Mangoldt hierarchies.md`](von%20Mangoldt%20hierarchies.md) - Detailed mathematical framework
- [`Notes on von Mangoldt Hierarchies.md`](Notes%20on%20von%20Mangoldt%20Hierarchies.md) - Research notes and cumulant connections

### Lecture Materials
- [`Analytic_Hierarchies_Stieltjes.md`](Analytic_Hierarchies_Stieltjes.md) - Graduate lecture series
- [`Stieltjes_Mellin_Lectures.md`](Stieltjes_Mellin_Lectures.md) - Specialized lectures
- [`Lambert.md`](Lambert.md) - Course on Lambert series and arithmetic functions

### Computational Resources
- [`Handoff_for_grad_student.md`](Handoff_for_grad_student.md) - Implementation guide
- [`g_function_notes.md`](g_function_notes.md) - Special functions for zeta zeros

### Related Topics
- [`Gauss diGamma.md`](Gauss%20diGamma.md) - Digamma function lecture plan
- [`Gauss diGamma Fourier.md`](Gauss%20diGamma%20Fourier.md) - Fourier perspective
- [`Generalized von Mangoldt function.md`](Generalized%20von%20Mangoldt%20function.md) - Extended framework
- [`Bell-Dirichelt.md`](Bell-Dirichelt.md) - Bell polynomials and multiplicative structures

## 🚀 Getting Started

### Prerequisites
- Graduate-level complex analysis and analytic number theory
- Familiarity with Dirichlet series and explicit formulas
- Programming experience (Python recommended with `mpmath`)

### Quick Implementation
```python
# Computing Λ_k(p^r) for prime powers
def lambda_k(p, r, k):
    """Compute Λ_k(p^r)"""
    return (log(p)**(k+1)) * (r**k)

# Example: Λ_2(8) = Λ_2(2^3) = (log 2)^3 * 3^2
result = lambda_k(2, 3, 2)  # = (log 2)^3 * 9
```

## 🔬 Current Research

### Active Projects
1. **Numerical Verification**: Computing $\Psi_k(x)$ and comparing with explicit formulas
2. **Error Term Analysis**: Sharp bounds under RH for oscillatory components
3. **Computational Methods**: Stable algorithms for large $k$ and $x$

### Recent Results
- Derived explicit polynomial forms for $P_k(\rho, \log x)$ at simple zeros
- Established Bell polynomial connections for cumulant-moment conversions
- Implemented high-precision computation of $\Psi_k(x)$ via prime-power enumeration

## 👥 Research Team

- **David England** (Principal Investigator) - Theoretical development
- **Graduate Researchers** - Computational implementation and verification

## 📝 Contributing

This is an active research repository. Key areas for contribution:
- Numerical computation and verification
- Error term improvements
- Extension to L-functions and modular forms
- Computational optimization

## 📚 References

### Primary Sources
- Titchmarsh, E.C. *The Theory of the Riemann Zeta-Function*
- Iwaniec, H. & Kowalski, E. *Analytic Number Theory*
- Knessl, C. & Coffey, M. "Asymptotic formula for Stieltjes constants" (2011)

### Related Work
- Montgomery, H.L. & Vaughan, R.C. *Multiplicative Number Theory I*
- Edwards, H.M. *Riemann's Zeta Function*

## 📄 License

Academic research materials for educational and research use.

---

*Last updated: October 2025*