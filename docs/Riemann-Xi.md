# The Riemann Xi-function: symmetry, products, and zero sums (chapter draft)

Audience and aim
- Bright undergraduates and early graduate students.
- A self-contained on-ramp to using the completed/xi-function to simplify functional equations, zero pairing, and sums/products over zeros; connects directly to explicit formulas and the Stieltjes-constant conventions used elsewhere in this repo.

Motivation (why Xi/ξ?)
- ζ(s) has a pole at s=1 and a non-symmetric functional equation. By absorbing the Γ-factor (and a power of π), the completed zeta becomes an entire, symmetric function with all nontrivial zeros:
  - Standard completed form
    ξ(s) := ½ s(s−1) π^{-s/2} Γ(s/2) ζ(s)
    (entire, order 1), and the “Xi-function” Ξ(s) often denotes the same object (notation varies).
  - Functional equation (perfect symmetry): ξ(s) = ξ(1−s).
- Payoff in this repo: when you differentiate logs, Γ/ψ terms complicate zero sums for −ζ′/ζ; passing to ξ aggregates the Γ-factor, simplifying identities for sums over zeros and making pairing transparent.

## 1) Definitions and core properties

- Completed zeta (meromorphic): Λ*(s) := π^{−s/2} Γ(s/2) ζ(s).
- Xi/ξ (entire, order 1):
  - ξ(s) := ½ s(s−1) Λ*(s) = ½ s(s−1) π^{−s/2} Γ(s/2) ζ(s).
  - Functional equation: ξ(s) = ξ(1−s).
  - Critical-line symmetry: ξ(½+it) ∈ ℝ and ξ(½+it) = ξ(½−it).
- Zeros: ξ(s) vanishes exactly at the nontrivial zeros ρ of ζ(s) (the trivial zeros are canceled by Γ(s/2) and the s(s−1) factor).

Hadamard product (canonical)
- ξ(s) is an entire function of order 1 and genus 1, hence
  ξ(s) = e^{A+Bs} ∏_ρ (1 − s/ρ) e^{s/ρ},
  where the product runs over nontrivial zeros ρ (including conjugates), and A,B are real constants.
- Taking the logarithmic derivative,
  − ξ′(s)/ξ(s) = −B + Σ_ρ 1/(s−ρ),
  where the additive constant −B drops out upon taking higher derivatives or when matching coefficients of (s−s0)^k for k≥1.

Remarks
- Many references write ξ without the exponential factor by using symmetric grouping; the e^{As+Bs^0} ambiguity is harmless for identities involving powers of (s−s0) with degree ≥1.
- In this repo we abusively write Xi(s) and ξ(s) interchangeably (Ξ is common in physics literature). The properties claimed above refer to ξ.

## 2) Functional equation: clean symmetry

- Start from θ(x) = Σ_{n∈ℤ} e^{−π n^2 x} and Poisson summation; derive the theta transformation x^{−1/2}θ(x^{−1}) = θ(x).
- Mellin-transform θ(x)−1 and change variables; one obtains the completed ζ factor Λ*(s) and the symmetric identity
  Λ*(s) = Λ*(1−s).
- Multiplying by ½ s(s−1) removes the pole/zero at s=1,0, yielding ξ(s) = ξ(1−s).
- Consequences: ξ(½+it) is real and even in t; zeros are symmetric with respect to the line Re(s)=½ and the real axis.

## 3) Products and simplified sums over zeros

- Zero quadruplets for ζ: {ρ, 1−ρ, ρ̄, 1−ρ̄} collapse to conjugate pairs for ξ because of the built-in symmetry. Under RH (β=Re ρ=½), quadruplets reduce to {½±iγ}.
- Log-derivative (clean pole sum):
  − ξ′/ξ(s) = −B + Σ_ρ 1/(s−ρ).
  This is the simplest place to form “power sums of zeros” by expanding at a point s0 (usually s0=½ or s0=1):
  − ξ′/ξ(s0+u) = −B + Σ_ρ 1/(u − (ρ−s0)).
  Expand in powers of u to obtain symmetric sums Σ_ρ (ρ−s0)^{−k}; convergence is in the paired/regularized sense.

Connection to Stieltjes constants and explicit formulas
- In −ζ′/ζ, Γ/ψ terms are explicit passengers. This repo records how those terms contribute background constants in Stieltjes-constant identities (e.g., the k=1 caveat). Passing to ξ absorbs Γ, and the sums over zeros appear in their cleanest form in −ξ′/ξ.
- Heuristic dictionary:
  - For k≥2, identities like γ_k = (k−1)! [1 − (1−2^{−k})ζ(k) − S_k] (in this repo’s convention) arise after accounting for Γ/ψ and constant terms; the “pure zeros” piece corresponds to ξ and its −ξ′/ξ expansion.
  - Working with ξ makes symmetric pairing and critical-line specialization algebraically transparent.

## 4) Critical-line pairing and x^{1/2} scaling

- For explicit formulas with x^s kernels, pairing (ρ,1−ρ) yields
  x^{ρ}P_k(ρ,log x) + x^{1−ρ}P_k(1−ρ,log x)
  = 2 x^{1/2}[ C^+_{k,ρ}(L) cos(γL) + C^-_{k,ρ}(L) sin(γL) ],
  where L=log x and C^± are explicit polynomials (see pairing notes in this repo).
- Under RH (β=½), the hyperbolic weights x^{±(β−½)} collapse to 1, leaving a clean x^{1/2}-scaled oscillation modulated by log-polynomials. This is the “square-root barrier” familiar from RH-level error terms.

## 5) Worked examples (short, self-contained)

Example 1 (Reality and evenness on the critical line)
- Show that ξ(½+it) ∈ ℝ and ξ(½+it) = ξ(½−it).
  Sketch: Using ξ(s)=ξ(1−s) and real coefficients in the Taylor series at s=½, we have ξ(½+it) = ξ(½−it) = ξ(½+it)̄. Hence the value is real and even in t.

Example 2 (First nontrivial coefficient in a local expansion)
- Expand −ξ′/ξ(s) at s=½:
  −ξ′/ξ(½+u) = −B + Σ_ρ 1/(u − (ρ−½)).
  The u^1 coefficient (after pairing) is Σ_ρ (ρ−½)^{−2}, interpreted symmetrically. This is the cleanest “power sum” over critical shifts; compare with the ζ/ψ versions where Γ/ψ contribute constants.

Example 3 (Product form to zero sums)
- From the Hadamard product,
  log ξ(s) = A + Bs + Σ_ρ [ log(1 − s/ρ) + s/ρ ].
  Taylor expand at s=½; the coefficient of (s−½)^k for k≥1 is a signed polynomial in Σ_ρ (ρ−½)^{−m}, m≤k. This is the ξ-analogue of the Stieltjes-constant expansions recorded earlier.

## 6) Exercises (with brief hints)

1) Functional equation via θ (core)
- Prove Λ*(s)=Λ*(1−s) using θ(x)=Σ e^{−π n^2 x} and Poisson summation; then define ξ(s)=½ s(s−1)Λ*(s).
  Hint: Mellin-transform θ(x)−1 and change variables x↦1/x.

2) Evenness and reality of ξ(½+it)
- Show ξ(½+it)=ξ(½−it) and ξ(½+it)∈ℝ.
  Hint: Combine ξ(s)=ξ(1−s) with complex conjugation symmetry.

3) Hadamard product and log-derivative
- Starting from ξ(s)=e^{A+Bs}∏_ρ (1−s/ρ) e^{s/ρ}, differentiate log ξ(s) to obtain −ξ′/ξ(s)=−B+Σ_ρ 1/(s−ρ).
  Hint: The exponentials cancel in pairs when forming the derivative.

4) Power sums around the center (½)
- Expand −ξ′/ξ(½+u) and identify the u^k coefficient (k≥1) with Σ_ρ (ρ−½)^{−(k+1)}.
  Hint: Use the expansion 1/(u−a)=−Σ_{m≥0} u^m a^{−(m+1)} valid in a symmetric/pairwise sense.

5) Quadruplet/conjugate collapse under RH
- Show that for sums like (1−ρ)^{−k} the quadruplet {ρ,1−ρ,ρ̄,1−ρ̄} reduces to a doubled conjugate pair when β=½.
  Hint: Pair real parts; use polar decompositions and cos(kθ) as in the pairing section of this repo.

6) Optional: Li/Keiper coefficients (pointer)
- Define λ_n := Σ_ρ [1 − (1 − 1/ρ)^n] and show (using the product for ξ) that {λ_n} are coefficients of −d/ds log ξ(s) at s=1.
  Hint: Expand log(1 − s/ρ) at s=1 and compare with the combinatorial polynomial in n; see standard references on Li’s criterion.

## 7) Practical notes (computation)

- Evaluating ξ(s): ξ(s) = ½ s(s−1) π^{−s/2} Γ(s/2) ζ(s). For numerical work, prefer working with log Γ and log ζ to stabilize magnitude and phase; on the critical line, ξ(½+it) is real.
- Zero sums: Always form symmetric (conjugate/quadruplet) sums; for k≥2, tails decay quickly. Under RH, use conjugate pairing only.

## 8) How this connects to the rest of the repo

- In “Power sums of zeros and Stieltjes constants,” Γ/ψ terms appear explicitly when working with −ζ′/ζ. Rewriting those identities via ξ streamlines the zero-sum side: constants and Γ-terms get absorbed into ξ, and only symmetric zero sums remain. The k=1 caveat in the ζ/ψ setting manifests as the additive constant −B in −ξ′/ξ; for k≥2, clean power-sum identities follow directly.
- In “Practical pairing” and “Hyperbolic weights,” the x^{1/2} scale and the disappearance of hyperbolic weights under RH match the ξ-centered symmetry; use this file when you want the shortest route from symmetry to oscillations.

---

Textbook chapter: The Riemann Xi-function (Ξ/ξ), symmetry, and zero sums

Learning objectives
- Understand the completed zeta and Xi/ξ definitions and the symmetric functional equation.
- Use the Hadamard product and log-derivative to form clean zero sums.
- Apply conjugate/quadruplet pairing and x^{1/2} scaling; connect to von Mangoldt hierarchies Λ_k and P_k(ρ,λ).
- Work simple numeric examples and establish practice habits for stable zero-sum evaluation.

Prerequisites
- Dirichlet series, Euler products; basic complex analysis; Mellin transform basics; explicit formulas for ζ.

1) Motivation and definition
- Completed zeta and ξ:
  - Λ*(s) := π^{−s/2} Γ(s/2) ζ(s); ξ(s) := ½ s(s−1) Λ*(s).
  - Functional equation: ξ(s) = ξ(1−s); symmetry about Re(s)=½.
- Zeros: ξ(s) entire; zeros are exactly nontrivial zeros of ζ(s); trivial zeros absorbed by the Γ and s(s−1) factors.

2) Hadamard product and log-derivative
- Hadamard form (order 1):
  ξ(s) = e^{A+Bs} ∏_ρ (1 − s/ρ) e^{s/ρ}.
- Log-derivative:
  − ξ′/ξ(s) = −B + Σ_ρ 1/(s−ρ).
  Expanding at s0=½ gives symmetric power sums Σ_ρ (ρ−½)^{−k} in a clean, Γ-free setting.

3) Zero pairing and x^{1/2} scaling
- For explicit-formula kernels x^s, pairing (ρ,1−ρ) yields:
  x^{ρ}P_k(ρ,λ) + x^{1−ρ}P_k(1−ρ,λ) = 2 x^{1/2}[ C^+ cos(γλ) + C^- sin(γλ) ], λ=log x.
- Under RH (β=½), hyperbolic weights collapse (x^{±(β−½)}→1): amplitude ∼ x^{1/2}.

4) Link to Λ_k and the log-damping P_k
- Hierarchy (ζ-side): (−1)^k d^k/ds^k[−ζ′/ζ] ↔ Λ_k; Mellin inversion gives Ψ_k(x).
- Local (zero) model and EGF:
  Σ_{k≥0} P_k(ρ,λ) t^k/k! = − e^{λ t}/(ρ+t),
  with recurrence ρ P_{k+1} + (k+1) P_k = − λ^{k+1}, Appell ∂_λ P_k = k P_{k−1}.
- In practice: compute x^{ρ}P_k(ρ,λ), sum in conjugate/quadruplet pairs.

5) Simplified sums and products (rule-of-thumb)
- Work on the ξ-side to avoid Γ/ψ terms when forming pure zero power sums.
- Use ζ-side when main terms (Stieltjes constants) are needed; ψ/Γ terms supply smooth backgrounds and trivial-zero cancellations.

Worked examples

Example A (Pairing at k=1, first zero; RH-typical)
- Data: ρ=½+iγ, γ≈14.1347; x=10^3, λ=log x≈6.90776.
- P_1(ρ,λ)= −λ/ρ + 1/ρ^2. Compute z := 2 x^{1/2} Re(e^{iγλ} P_1(ρ,λ)).
- Outcome: z ≈ −3.068×10^1 (matches earlier numeric in repo). Good test of pipeline and pairing.

Example B (Quadruplet block for power sums S_k)
- For ρ=β+iγ, write 1−ρ=r_- e^{−iθ_-}, ρ=r_+ e^{iθ_+}.
- Quadruplet block for (1−ρ)^{−k} and ρ^{−k}:
  2[ r_-^{−k} cos(kθ_-) + r_+^{−k} cos(kθ_+) ].
- This is the simplest real form for power sums entering the ζ→ξ translation.

Example C (Local EGF check up to k=2)
- Expand −e^{λ t}/(ρ+t) to O(t^2) and match coefficients:
  P_0= −1/ρ; P_1= −λ/ρ + 1/ρ^2; P_2= −λ^2/ρ + 2λ/ρ^2 − 2/ρ^3.

Exercises (with short hints)

Conceptual
1) Show ξ(½+it)∈ℝ and even in t.
   Hint: combine ξ(s)=ξ(1−s) with conjugation symmetry and real Taylor coefficients at s=½.
2) Explain why Γ/ψ terms disappear when forming −ξ′/ξ but reappear in −ζ′/ζ.
   Hint: completion absorbs Γ; ζ-side keeps Γ explicit.

Computational
3) Using ρ≈½+i 14.1347, compute 2 x^{1/2} Re(e^{iγλ} P_1) at x=10^3; compare to Example A.
   Hint: pair conjugates; use ≥50 dps to avoid cancellation.
4) For k=2 and β≠½, evaluate the quadruplet block 2[ r_-^{−2} cos(2θ_-) + r_+^{−2} cos(2θ_+) ] numerically for a mocked β=0.49, γ as above.

Proof/derivation
5) Derive the recurrence ρ P_{k+1} + (k+1) P_k = − λ^{k+1} from the EGF by multiplying both sides by (ρ+t) and comparing t^{k+1}.
6) Expand −ξ′/ξ(½+u) to identify the u^m coefficient as the symmetric power sum Σ_ρ (ρ−½)^{−(m+1)} (paired sense).

Deliverables (students)
- Hand in numeric outputs for Exercises 3–4 with a short log of precision and pairing strategy.
- One-page derivation for Exercise 5 or 6.

Further reading
- Titchmarsh (ξ, functional equation, products); Edwards (historical ξ); Iwaniec–Kowalski (completed L-functions framework).

---

Lesson plan (90–120 minutes)

Audience
- Bright undergraduates and early grads; aim to connect symmetry/ξ with your Λ_k/P_k machinery.

Learning goals (observable)
- State and use ξ(s)=ξ(1−s); write the Hadamard product and log-derivative.
- Execute a paired evaluation of a small zero-sum term at k=1 using P_k.
- Explain x^{1/2} scaling and hyperbolic weights collapse under RH.

Structure and timing
- 0–10 min: Motivation and definitions (Λ*, ξ, symmetry).
- 10–25 min: Hadamard product; −ξ′/ξ(s)=−B+Σ 1/(s−ρ).
- 25–45 min: Pairing and x^{1/2} scaling; derive conjugate/quadruplet formulas.
- 45–65 min: Link to Λ_k and P_k; EGF and recurrence; micro-derivation of P_1,P_2.
- 65–85 min: Worked example walk-through (Example A). Live computation notes: precision, pairing, stability.
- 85–100 min: Guided practice: students compute Example C coefficients; quick checks in pairs.
- 100–120 min (optional): Power sums (Example B) and ζ↔ξ comparison; Q&A.

In-class materials
- One-page handout: definitions, ξ symmetry, Hadamard, EGF for P_k, recurrence, Example A data.
- Calculator/Notebook with arbitrary precision (mpmath/Julia/Mathematica acceptable).

Assessment (lightweight)
- Exit ticket: write down the recurrence for P_k and explain, in one sentence, why x^{1/2} appears after pairing.
- Optional graded: Exercise 3 numeric replication with brief notes on stability.

Instructor tips
- Emphasize “work on ξ when you want pure zero sums; work on ζ when you need main terms (Stieltjes constants).”
- Keep the pairing algebra visual; draw the (ρ,1−ρ,ρ̄,1−ρ̄) block and indicate which terms collapse under RH.
- Encourage pairwise summation of conjugates and increasing-γ order to reduce cancellation.

---

## 🌌 $\Xi(s)$: Simplified Sums and Symmetry
# (retained summary; see chapter above for the full development)

Riemann's $\Xi(s)$ is an entire function whose zeros, $\rho$, are exactly the non-trivial zeros of $\zeta(s)$. Its functional equation $\Xi(s) = \Xi(1-s)$ simplifies the analytic structure.

### 1. Zero Pairing and Symmetry

Since $\Xi(s) = $\Xi(1-s)$, if $\rho$ is a zero, then $1-\rho$ is a zero. As $\Xi(s)$ has real coefficients in its Taylor expansion, zeros also come in conjugate pairs $\rho$ and $\bar{\rho}$.

* **The Quadruplet Collapse:** Because the zeros of $\Xi(s)$ are constrained to the critical strip, and are conjectured to satisfy the RH ($\rho = 1/2 + i\gamma$), the four theoretical zeros $\{\rho, \bar{\rho}, 1-\rho, 1-\bar{\rho}\}$ **always collapse** into a single conjugate pair $\{\rho, \bar{\rho}\}$, since $1-\rho = \bar{\rho}$.
* **Simplified Pairing:** For $\Xi(s)$, the analysis of the oscillation only requires the **conjugate pair** $(\rho, \bar{\rho})$, which ensures the oscillation is real and centered precisely on the $x^{1/2}$ amplitude.

### 2. Sums over Zeros (Analogous to Stieltjes Constants)

For $\Xi(s)$, the analogy to the Stieltjes constants arises from the factorization of the entire function $\Xi(s)$ into its Hadamard product over its zeros $\rho$:

$$\Xi(s) = \Xi(0) \prod_{\rho} \left(1 - \frac{s}{\rho}\right)$$

Taking the logarithmic derivative and expanding around $s=1/2$ (the point of symmetry) gives constants that are closely related to the sum over the zeros:

$$-\frac{\Xi'(s)}{\Xi(s)} = \sum_{\rho} \frac{1}{s-\rho}$$

Expanding this logarithm near $s=1/2$ yields coefficients that are $\Xi$-analogues of the Stieltjes constants $\gamma_n$. These coefficients involve known mathematical constants (like $\log(2\pi)$ and the logarithm of the $\Gamma$-function's product term) mixed with **sums over powers of the zeros $\rho$**:

$$\sum_{\rho} \frac{1}{\rho^n}$$

These sums are **known to be expressible** in terms of $\log(2\pi)$, $\gamma_0$, and other fundamental constants, similar to how the Stieltjes constants relate to $\zeta(s)$'s pole structure.

---

## 📉 Hyperbolic Weights and Oscillation Expansions

The key difference when analyzing $\Xi(s)$ is the **disappearance of the hyperbolic weights** for the zero analysis.

### Hyperbolic Weights Vanish (under RH)

Recall the hyperbolic weights $x^{\pm(\beta - 1/2)}$ appear when analyzing the reflection pair $(\rho, 1-\rho)$ **off the critical line ($\beta \ne 1/2$)**:

$$\mathcal{O}(\rho, 1-\rho) \propto x^{1/2} \left[ x^{\beta-1/2} P_k(\rho, \mathcal{L}) \pm x^{-(\beta-1/2)} P_k(1-\rho, \mathcal{L}) \right]$$

Since the zeros of $\Xi(s)$ are conjectured to satisfy the RH ($\mathbf{\beta = 1/2}$), the hyperbolic weights disappear: $x^{\pm(\beta - 1/2)} = x^0 = 1$.

* **Result:** The oscillation is perfectly centered on $x^{1/2}$, and the oscillation's magnitude is controlled solely by the **Log-Damping Polynomials** $P_k(\rho, \mathcal{L})$ applied to the critical line zeros:
    $$\mathcal{O}(\rho, \bar{\rho}) \propto 2 x^{1/2} \operatorname{Re}\left[ e^{i\gamma \mathcal{L}} P_k(\rho, \mathcal{L}) \right]$$

The oscillation is a clean $x^{1/2}$ wave modulated by polynomials in $\mathcal{L}$, confirming that under RH, the prime distribution is **governed by the square root of $x$**.
