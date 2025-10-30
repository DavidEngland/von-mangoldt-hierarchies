# von-mangoldt-hierarchies — Repository overview & Markdown preview guide

This repository contains research notes and code for von Mangoldt hierarchies, explicit formulas, Stieltjes constants, and related computations.

Quick purpose
- Research and teaching materials (lecture notes, experiments, notebooks).
- Use this file for instructions on how to preview Markdown (especially math) consistently.

Previewing Markdown and LaTeX (recommended conventions)
- Use inline math with single-dollar signs: `$...$`.
- Use display math with double-dollar signs: `$$ ... $$`.
- If your previewer supports fenced math blocks, use:
  ```math
  \[ ... \]
  ```
  or
  ```math
  $$ ... $$
  ```
- Many Markdown previewers (GitHub, VS Code) do not render LaTeX by default. Recommended options:
  - VS Code: install the "Markdown+Math" or "Markdown Preview Enhanced" extension.
  - For interactive notebooks or web previews, use a renderer that supports MathJax/KaTeX.

Recommended editor setup
1. VS Code + Markdown Preview Enhanced (or Markdown+Math)
2. In Markdown Preview Enhanced settings enable KaTeX or MathJax rendering.
3. For high-precision numeric or LaTeX-heavy work, run snippets in Jupyter / Binder with MathJax enabled.

Common preview problems and fixes
- Unrendered math:
  - Ensure you use `$...$` (inline) or `$$...$$` (display).
  - Check previewer extension is installed and enabled.
- Unclosed code / math fences:
  - Make sure each triple-fence has a matching closing fence (```).
  - Avoid nested triple-fences inside other fences.
- HTML comments (e.g. `<!-- filepath: ... -->`) are OK in Markdown, but if placed inside a fenced code block they will display as literal text; move them above the fence.
- Filenames with special characters:
  - Avoid `#`, `%`, and other special characters in filenames (there is a docs file containing `#` in the name — such names can break some previewers). Rename files if possible.

Quick checklist before committing Markdown:
- [ ] Every code block has a closing fence.
- [ ] Display math uses `$$ ... $$` or a supported fenced math block.
- [ ] No stray backslashes escaping Markdown characters unintentionally.
- [ ] If preview fails, open the Markdown in the recommended previewer/extension.

If you want, I can:
- produce a script to validate Markdown files for unclosed fences and common LaTeX issues, or
- propose a lightweight rename for the problematic docs file whose filename contains `#`.

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