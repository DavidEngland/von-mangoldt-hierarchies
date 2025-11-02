# Quadruplet pairing via the EGF of P_k

Notation (important)
- L := log x is the logarithm of x (not an L-function). In all EGF formulas with parameter t, e^{Lt} = x^{t}.
- Zeros: ρ = β + iγ; the quadruplet is Q(ρ) := {ρ, 1−ρ, ρ̄, 1−ρ̄}.

Setup
- For a simple zero ρ, the P_k EGF in k is
  $$
  G_{\rho}(t,L)\;:=\;\sum_{k\ge0}\frac{P_k(\rho,L)}{k!}\,t^k
  \;=\;-\frac{e^{Lt}}{\rho+t},\qquad L=\log x.
  $$

Quadruplet EGF (summed over k with x^σ)
- Define the quadruplet kernel
  $$
  S_{\mathrm{quad}}(t;L)\;:=\;\sum_{\sigma\in Q(\rho)} x^{\sigma}G_{\sigma}(t,L)
  \;=\;-\sum_{\sigma\in Q(\rho)} \frac{e^{(\sigma+t)L}}{\sigma+t}.
  $$
- For real L and t, S_quad(t;L) is real-valued (by the conjugation/reflection symmetry).

Harmonic decomposition (general β=Re ρ, γ=Im ρ)
- Factor the universal scale:
  $$
  S_{\mathrm{quad}}(t;L)\;=\;-\,2\,e^{(\tfrac{1}{2}+t)L}\,\Big[
  C^+_{t,\rho}(L)\,\cos(\gamma L)\;+\;C^-_{t,\rho}(L)\,\sin(\gamma L)\Big],
  $$
  where
  $$
  C^+_{t,\rho}(L)=\Re\!\Big(\frac{e^{(\beta-\tfrac12)L}}{\rho+t}+\frac{e^{-(\beta-\tfrac12)L}}{1-\rho+t}\Big),\quad
  C^-_{t,\rho}(L)=\Im\!\Big(\frac{e^{(\beta-\tfrac12)L}}{\rho+t}-\frac{e^{-(\beta-\tfrac12)L}}{1-\rho+t}\Big).
  $$
- Mild bounds (fixed k via coefficient extraction at t=0): for real L and |t| small,
  $$
  |C^{\pm}_{t,\rho}(L)| \;\ll\; e^{|\beta-\tfrac12|L}\left(\frac{1}{|\rho+t|}+\frac{1}{|1-\rho+t|}\right).
  $$

Implications if RH holds (β=1/2)
- If RH holds, then 1−ρ=ρ̄ and (for real t) (1−ρ+t)=(ρ̄+t), hence
  $$
  S_{\mathrm{quad}}(t;L)\;=\;-\,4\,e^{(\tfrac{1}{2}+t)L}\,\Re\!\Big(\frac{e^{i\gamma L}}{\rho+t}\Big).
  $$
- At t=0 this collapses to the familiar pair-sum:
  $$
  S_{\mathrm{quad}}(0;L)=\sum_{\sigma\in Q(\rho)} x^{\sigma}P_0(\sigma)
  \;=\;-4\,x^{1/2}\,\Re\!\big(e^{i\gamma L}/\rho\big).
  $$

Coefficient extraction in k
- By definition,
  $$
  S_{\mathrm{quad}}(t;L)=\sum_{k\ge0}\frac{t^k}{k!}\,S_k(L),
  \qquad
  S_k(L):=\sum_{\sigma\in Q(\rho)} x^{\sigma}\,P_k(\sigma,L).
  $$
- Hence
  $$
  S_k(L)=\left.\frac{d^k}{dt^k}\,S_{\mathrm{quad}}(t;L)\right|_{t=0}.
  $$
  In practice, differentiate the compact form −∑ e^{(σ+t)L}/(σ+t) at t=0; if RH holds, use the one-line simplification above.

Aggregated recurrence (from the single-zero recurrence)
- For each σ,
  $
  \sigma\,P_{k+1}(\sigma,L) + (k+1)\,P_k(\sigma,L) = -L^{k+1}.
  $
- Summing over Q(ρ):
  $$
  \boxed{\;\sum_{\sigma\in Q(\rho)}\sigma\,P_{k+1}(\sigma,L) \;+\; (k+1)\,S_k(L)
  \;=\; -\,4\,L^{k+1}\;.}
  $$
  This gives a linear relation between S_k and the σ‑weighted sum at level k+1.

Practical algorithm (pairing-first evaluation)
- Inputs: L = log x (real), k_max, a zero ρ and its quadruplet Q(ρ).
- Steps:
  1) Build S_quad(t;L) via the kernel −∑ e^{(σ+t)L}/(σ+t) (real for real L,t).
  2) Differentiate at t=0 up to order k_max (automatic differentiation is convenient) to get S_k(L).
  3) Alternatively, iterate the aggregated recurrence while maintaining the auxiliary sum U_{k+1}:=∑_{σ∈Q} σ P_{k+1}(σ,L).
- Stability:
  - Always pair conjugates; if RH holds, the conjugate pair {ρ,ρ̄} suffices.
  - The x^{1/2} factor exhibits the natural oscillation scale; the remaining envelopes are degree‑k polynomials in L.

Small‑t expansion (quick series)
- Using $e^{(\sigma+t)L}/(\sigma+t)=\sum_{m\ge0}\frac{L^m}{m!}(\sigma+t)^{m-1}$ and expanding $(\sigma+t)^{m-1}$ at t=0 yields
  $$
  S_{\mathrm{quad}}(t;L)
  = -\sum_{\sigma\in Q(\rho)} \sum_{m\ge0}\frac{L^m}{m!}
  \sum_{r=0}^{m-1}\binom{m-1}{r}\sigma^{\,m-1-r}\,t^{\,r},
  $$
  so the coefficient of $t^k$ gives $S_k(L)$ as a finite linear combination of symmetric sums in σ (hence β,γ) times powers of L.

Numerical use (practical)
- To evaluate {S_k(L)} up to k_max:
  - Differentiate the compact EGF (or RH simplification) at t=0.
  - Or iterate the aggregated recurrence; track U_{k+1} if needed for stability checks.
- Realness: For real L,t, S_quad and all S_k(L) are real by construction.
