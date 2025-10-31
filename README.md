# Von Mangoldt Hierarchies — Research Notes

Purpose
- Investigate derivatives of the logarithmic derivative of the Riemann zeta function and their connections to prime number theory (von Mangoldt hierarchies, explicit formulas, Stieltjes constants).

Quick start
- Read docs/zero-residual-polys.md for the zero-residue polynomials P_k(ρ, log x).
- See L-functions.md for the modular/L-function extension.
- Open tools/pk_table.html in a browser to generate P_k tables interactively.

Math rendering conventions
- Inline math: `$...$`
- Display math: `$$ ... $$`
- Use a previewer that supports MathJax/KaTeX (e.g., VS Code “Markdown Preview Enhanced”).
- Avoid filenames containing `#` (see docs/# L-Functions and Modular Forms.md deprecation note).

Repository tips
- Pair conjugate zeros when summing oscillatory terms.
- Use the recurrence `ρ P_{k+1} + (k+1) P_k = - L^{k+1}` for stable P_k generation.