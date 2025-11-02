# Quadruplet pairing and practical pairing (general L-functions → zeta)

Scope and setup
- Let L(s) be a standard L-function (Dirichlet series with Euler product, analytic continuation, and a functional equation) with completed form
  Λ(s) = Q(s) L(s),  and symmetry  Λ(s) = ε Λ(1−s),
  where Q(s) is a product of Γ-factors and powers of π, and |ε|=1 is the root number.
- Zeros are symmetric with respect to reflection and conjugation: if ρ is a (simple) zero, then 1−ρ, ρ̄, and 1−ρ̄ are also zeros.
- For each simple zero σ, the zero-residue contribution in explicit formulas has the form x^{σ} P_k(σ, L) with L := log x and deg_L P_k ≤ k (P_k depends on the local data at σ but is universal in L).

Definition (quadruplet and practical pairing)
- The quadruplet attached to a zero ρ is Q(ρ) := { ρ, 1−ρ, ρ̄, 1−ρ̄ }.
- The k-th oscillatory contribution paired over the quadruplet is
  S_quad,k(L) := ∑_{σ∈Q(ρ)} x^{σ} P_k(σ, L).

Basic facts (no RH assumed)
- Real-valuedness: For real x>1 and real L, S_quad,k(L) is real. This follows from the conjugation/reflection symmetry and the functional equation: the quadruplet sum is invariant under complex conjugation.
- Harmonic decomposition: Writing ρ = β + iγ and defining
  A(L) := x^{β-1/2} P_k(ρ, L),   B(L) := x^{-(β-1/2)} P_k(1−ρ, L),
  one has the identity
  S_quad,k(L) = 2 x^{1/2} [ A_k(L) cos(γ L) + B_k(L) sin(γ L) ],
  with real polynomials (in L) given by
  A_k(L) = Re( A(L) + B(L) ),    B_k(L) = Im( A(L) − B(L) ).
  In particular, the oscillatory carrier is trigonometric in γ L and the envelope is a degree-≤k polynomial in L, scaled by x^{1/2} and hyperbolic weights x^{±(β−1/2)} through A, B. No hypothesis on β is required.

Justification (functional-equation symmetry)
- The completed functional equation Λ(s)=εΛ(1−s) implies zero symmetry {ρ,1−ρ}, and complex conjugation adds {ρ̄,1−ρ̄}. For real x and real L=log x, the map σ ↦ (x^{σ} P_k(σ,L)) respects conjugation by pairing σ with σ̄ and reflection by pairing σ with 1−σ; adding the full quadruplet cancels all imaginary parts, hence S_quad,k(L)∈ℝ.
- The cos/sin form follows by writing x^{β±iγ} = x^{β} (cos(γL) ± i sin(γL)) with β shifted to 1/2 via the factors A(L), B(L) above.

EGF viewpoint (all k at once)
- The exponential generating function (in k) at σ is G_σ(t;L) = ∑_{k≥0} P_k(σ,L) t^k/k! = − e^{Lt}/(σ+t).
- Summing over the quadruplet produces the real kernel
  S_quad(t;L) := ∑_{σ∈Q(ρ)} x^{σ} G_σ(t;L) = − ∑_{σ∈Q(ρ)} e^{(σ+t)L}/(σ+t),
  whose k-th derivative at t=0 yields S_quad,k(L). This is numerically stable and keeps the symmetry manifest.

Practical recipe (no RH)
1) For each zero ρ with Im(ρ)>0, form the quadruplet Q(ρ).
2) Compute P_k(ρ,L) and P_k(1−ρ,L) (and their conjugates via conjugation).
3) Build A(L)=x^{β-1/2}P_k(ρ,L), B(L)=x^{-(β-1/2)}P_k(1−ρ,L), then
   A_k(L)=Re(A+B), B_k(L)=Im(A−B),
   and add 2 x^{1/2}[ A_k(L) cos(γL) + B_k(L) sin(γL) ] to the sum.
4) Repeat over a truncation set of zeros; this yields a real-valued, numerically stable approximation to the oscillatory component.

Specialization to ζ(s)
- For the Riemann zeta function, Q(s)=π^{−s/2} Γ(s/2) and ε=1; the zero symmetry (ρ,1−ρ,ρ̄,1−ρ̄) and all statements above hold verbatim.
- In terms of S_quad(t;L), the ζ-kernel is
  S_quad(t;L) = − ∑_{σ∈{ρ,1−ρ,ρ̄,1−ρ̄}} e^{(σ+t)L}/(σ+t),
  with coefficients at t^k/k! equal to the paired contributions ∑_{σ∈Q(ρ)} x^{σ} P_k(σ,L).

Why this pairing is “practical”
- Reality by construction: no spurious imaginary parts, independent of where zeros lie.
- Stability: pairing opposite phases reduces cancellation error in finite truncations.
- Structure: exhibits an x^{1/2}-scaled, degree-≤k polynomial envelope times pure cos/sin(γL), clarifying amplitude growth in L and the effect of Re(ρ)=β via the hyperbolic weights embedded in A, B.

Note
- Nothing here assumes or mentions the Riemann Hypothesis. The quadruplet pairing uses only the functional-equation symmetry and complex conjugation, which hold in the standard L-function framework (and specifically for ζ(s)).
