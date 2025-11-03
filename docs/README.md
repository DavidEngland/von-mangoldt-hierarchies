# Documentation

This directory contains organized documentation for the von Mangoldt hierarchies research.

## 📁 Organization

### Core Theory (`theory/`)
- Mathematical foundations and definitions
- Proofs and derivations
- Research notes

### Lectures (`lectures/`)
- Course materials and lecture notes
- Graduate-level presentations
- Student exercises

### Computational (`computational/`)
- Implementation guides
- Numerical methods
- Code examples

### Examples (`examples/`)
- Worked examples
- Tutorial materials
- Quick start guides

## 🎯 Recommended Reading Order

1. **Introduction**: Start with the main [README](../README.md)
2. **Core Concepts**: Read [von Mangoldt hierarchies](../von%20Mangoldt%20hierarchies.md)
3. **Implementation**: Follow [Handoff for grad student](../Handoff_for_grad_student.md)
4. **Advanced Theory**: Explore [Notes on von Mangoldt Hierarchies](../Notes%20on%20von%20Mangoldt%20Hierarchies.md)

## 🔧 Contributing to Documentation

When adding new documentation:
- Use clear, descriptive filenames
- Include mathematical notation in LaTeX format
- Provide both theory and computational examples
- Cross-reference related documents

# docs — Conventions and Preview

Conventions
- Inline math: `$...$`; display: `$$ ... $$`.
- Code blocks fenced with triple backticks and a language hint where possible.
- Prefer filenames without spaces or `#` to avoid preview issues.

Recommended preview
- VS Code + “Markdown Preview Enhanced” (MathJax/KaTeX enabled).
- GitHub renders most Markdown but not all math; use local preview for verification.

Checklist
- Ensure every fenced block is closed.
- Check paired `$$`.
- Avoid nested triple fences.

# Documentation index and conventions

Notation sanity
- L := log x (not an L-function). In EGFs with parameter t, e^{Lt} = x^{t}.
- ρ = β + iγ denotes a (simple) zero; Q(ρ) = {ρ, 1−ρ, ρ̄, 1−ρ̄}.
- “No RH assumed” by default; RH is only used to simplify pairings as a consequence.

Core documents
- zero-residual-polys.md — P_k closed forms, EGF, recurrence, Appell links, trivial zeros note.
- Compact formula.md — cheat sheet, examples, and problem prompts (Masters/PhD).
- Hierarchy Interdependence Theorem.md — ∂_L and ∂_x identities; ODEs and prompts.
- ../quad upon generating function.md — quadruplet EGF kernel, harmonic decomposition, coefficient extraction.
- ../Practical Pairing of the Quadruplet of a Simple Zero.md — (ρ,1−ρ) practical pairing.

Rendering
- Inline math: $...$; display: $$ ... $$. Close all fences. Prefer filenames without spaces or ‘#’.

Quick references
- EGF: ∑ P_k(ρ,L) t^k/k! = − e^{Lt}/(ρ + t).
- Recurrence: ρ P_{k+1} + (k+1) P_k = − L^{k+1}.
- Appell: ∂_L P_k = k P_{k-1}; chain rule: ∂_x P_k = (k/x) P_{k-1}.
