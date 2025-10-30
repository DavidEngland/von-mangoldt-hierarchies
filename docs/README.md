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

# docs/ — Rendering conventions and troubleshooting

This document explains how the Markdown in `/docs` is formatted and how to preview it reliably.

Conventions used in these notes
- Inline math: `$...$`
- Display math: `$$ ... $$` (preferred)
- Use fenced code blocks for examples:
  ```python
  # use triple backticks and specify language when possible
  ```
- If your renderer supports it, use fenced math blocks with `math` language:
  ```math
  $$ \sum_{n\ge1} \frac{\Lambda(n)}{n^s} $$
  ```

Recommended previewers
- VS Code: "Markdown Preview Enhanced" or "Markdown+Math"
- GitHub web UI: supports basic `$...$` in READMEs only in limited contexts; complex LaTeX may not render.
- Jupyter / nbviewer: good for notebooks containing LaTeX.

Troubleshooting common issues
1. Nothing renders as math:
   - Install and enable the math preview extension.
   - Reload the editor preview.
2. Partial rendering or stray characters:
   - Search for unclosed fences: ````` ``` ````` without matching closing.
   - Remove stray HTML comments from inside code fences.
3. File preview broken or empty:
   - Check the file name for special characters (e.g., `#`). Some previewers mis-handle such names. Consider renaming to remove `#`.
4. Long LaTeX blocks slow the preview:
   - Use smaller example snippets or an external TeX renderer for edits.

Quick local validation (manual)
- Run a lightweight check:
  - Search for "```" occurrences and confirm even count.
  - Search for "$$" occurrences and confirm pairs.
  - Ensure no triple-fence appears inside another triple-fence.

If you want, I can add a small validation script (Python) to the repo that scans all `.md` files for unclosed fences, unmatched `$$`, and filenames with unsafe characters.
