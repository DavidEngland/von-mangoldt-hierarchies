# TODO — Tasks and Improvements

## Documentation

### High Priority
- [ ] Add worked examples to `docs/zero-residual-polys.md`
  - Example: Compute P_0 through P_5 for first ζ zero
  - Example: Verify Appell property numerically
- [ ] Create solution guide for exercises in `docs/Compact formula.md`
- [ ] Add diagrams/visualizations for pairing identities
  - Visual representation of quadruplet {ρ, 1−ρ, ρ̄, 1−ρ̄}
  - Oscillatory sum plots

### Medium Priority
- [ ] Standardize notation across all docs (ensure λ vs L consistency)
- [ ] Add references section to each doc file
- [x] Create glossary of symbols (`docs/GLOSSARY.md`)
- [ ] Expand `CONTRIBUTING.md` with:
  - LaTeX rendering conventions
  - Example PR descriptions
  - Citation style guide

### Low Priority
- [ ] Add historical notes on von Mangoldt functions
- [ ] Create "Further Reading" section with research papers
- [ ] Add appendix with Bernoulli/Euler polynomial background

---

## Tools Enhancement

### pk_table.html improvements
- [ ] Add support for computing A_k, B_k coefficients (quadruplet)
- [ ] Implement arbitrary precision option (beyond JavaScript float64)
- [ ] Add graphical plot output (interactive charts)
- [ ] Export functionality:
  - [x] CSV export (completed)
  - [x] LaTeX export (completed)
  - [ ] JSON export for programmatic use
  - [ ] Mathematica/SageMath format
- [ ] Add input validation and error messages
- [ ] Responsive design for mobile devices
- [ ] Dark mode toggle

### New Tools to Create
- [ ] `tools/zero_sum_visualizer.html` — plot oscillatory sums
- [ ] `tools/recurrence_checker.html` — verify recurrence relation
- [ ] `tools/pairing_identity_verifier.html` — numerical verification of pairings

---

## Examples and Exercises

### Add to Repository
- [ ] `examples/zeta_first_zero.md` — complete walkthrough for ρ₁ ≈ 0.5 + 14.134725i
- [ ] `examples/dirichlet_L.md` — example with Dirichlet L-function
- [ ] `exercises/masters_level.md` — collection of Masters exercises with hints
- [ ] `exercises/phd_level.md` — collection of PhD exercises
- [ ] `solutions/` directory (separate from exercises)

---

## Code Quality (if applicable)

### If Code is Added
- [ ] Set up testing framework (Jest/Mocha for JS tools)
- [ ] Add unit tests for recurrence relation
- [ ] Add integration tests for EGF computation
- [ ] Set up CI/CD pipeline (GitHub Actions)
- [ ] Add code linting (ESLint for JS)

---

## Repository Organization

### File Structure
- [x] Create `docs/README.md` (index)
- [ ] Rename files to remove spaces:
  - `Leibniz Rule.md` → `leibniz-rule.md`
  - `Compact formula.md` → `compact-formula.md`
  - `Hierarchy Interdependence Theorem.md` → `hierarchy-interdependence.md`
  - `quad upon generating function.md` → `quadruplet-egf.md`
- [ ] Move root-level docs to `docs/` directory:
  - `quad upon generating function.md` → `docs/quadruplet-egf.md`

### Metadata
- [x] Add LICENSE file
- [x] Add CITATION.cff for academic citation
- [x] Add .gitignore for common editor files
- [ ] Add tags/releases for version tracking

---

## Outreach and Community

### Publication
- [ ] Write blog post introducing the repository
- [ ] Post to math.stackexchange or MathOverflow (if questions arise)
- [ ] Create arXiv preprint summarizing main results
- [ ] Submit to journal (e.g., Experimental Mathematics)

### Collaboration
- [ ] Add "Good First Issue" labels for newcomers
- [ ] Create discussion forum (GitHub Discussions)
- [ ] Reach out to collaborators at universities

---

## Computational Experiments

### Numerical Investigations
- [ ] Compute P_k for k=0..50, first 100 ζ zeros
- [ ] Verify pairing identities to high precision
- [ ] Investigate coefficient growth empirically
- [ ] Test stability of recurrence for large k
- [ ] Compare main term accuracy for different L-functions

### Data Collection
- [ ] Create database of computed P_k values
- [ ] Store results in `data/` directory
- [ ] Document data format and access methods

---

## Priority Labels

- 🔴 **High Priority** — Blocking or high-impact
- 🟡 **Medium Priority** — Important but not urgent
- 🟢 **Low Priority** — Nice-to-have improvements

---

## Completed Tasks

- [x] Create README.md with overview
- [x] Create pk_table.html tool
- [x] Basic CSV/LaTeX export in tool
- [x] Create CONTRIBUTING.md
- [x] Create OPEN_QUESTIONS.md
- [x] Create TODO.md
- [x] Create docs/README.md
- [x] Add LICENSE file
- [x] Add CITATION.cff for academic citation
- [x] Add .gitignore for common editor files
- [x] Create glossary of symbols (docs/GLOSSARY.md)

---

**Last Updated:** 2024
**Maintainer:** David England
