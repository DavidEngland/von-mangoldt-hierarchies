# Compact formulas for P_k(ρ, λ) — cheat sheet + problems

Notation
- λ(x) := log x (preferred; older notes use L ≡ λ). E_k(z) := ∑_{j=0}^k z^j/j!.

Universal zero polynomials (simple zero ρ, any L-function)
- Truncated exponential:  P_k = (−1)^{k+1} k!/ρ^{k+1} · E_k(−λρ).
- Falling-factorial:      P_k = −(1/ρ) ∑_{j=0}^k (−1)^j (k)↓j · λ^{k−j}/ρ^{j}.
- EGF in k:               ∑_{k≥0} P_k t^k/k! = − e^{λ t}/(ρ + t).
- Recurrence:             ρ P_{k+1} + (k+1) P_k = − λ^{k+1}.
- Appell lowering:        ∂_λ P_k = k P_{k−1}.

Main terms (ζ vs. general L)
- ζ: M_k(x)=x λ^k − ∑_{m≤k} binom(k,m) γ_m x λ^{k−m}.
- General L with a simple pole at 1: replace γ_m by c_m(L) from −L′/L(1+u)=1/u+∑ c_m(L) u^m; if L is entire at 1, the x·poly(λ) main term vanishes.

Core identities (simple zero ρ)
- Truncated exponential:
  $$
  P_k(\rho,L)=(-1)^{k+1}\frac{k!}{\rho^{k+1}}\,E_k(-L\rho).
  $$
- Falling‑factorial (Horner in L):
  $$
  P_k(\rho,L)=-\frac{1}{\rho}\sum_{j=0}^k(-1)^j\frac{(k)^{\underline{j}}}{\rho^j}L^{k-j}.
  $$
- EGF (in k):
  $$
  \sum_{k\ge0}\frac{P_k(\rho,L)}{k!}t^k=-\frac{e^{Lt}}{\rho+t},\quad e^{Lt}=x^t.
  $$
- Linear recurrence:
  $$
  \rho P_{k+1} + (k+1)P_k = -L^{k+1}.
  $$

Pairing (ρ=β+iγ)
- Practical (ρ,1−ρ):
  $$
  x^{\rho}P_k(\rho,L)+x^{1-\rho}P_k(1-\rho,L)
  = 2x^{1/2}\Big[C^+_{k,\rho}\cos(\gamma L)+C^-_{k,\rho}\sin(\gamma L)\Big],
  $$
  with $C^{\pm}_{k,\rho}$ from the Practical Pairing note.

Masters — quick checks
- Top term: from falling‑factorial, j=0 gives −L^k/ρ.
- k=2 via E_2: P_2= −L^2/ρ + 2L/ρ^2 − 2/ρ^3.
- Verify ρP_1+P_0=−L.

PhD — short derivations
- Derive EGF from truncated exponential form.
- Prove the recurrence from (ρ+t)∑ P_k t^k/k! + e^{Lt}=0.
- Extract S_k(L) by differentiating the quadruplet kernel at t=0.

Computational prompts (pseudo‑code)
- Horner via truncated exponential:
  ```
  z = -L*rho
  t = 1/k!
  E = t
  for m = k-1..0: t = t*z + 1/m!
  Pk = (-1)^(k+1) * k! * E / rho^(k+1)
  ```
- Recurrence sweep:
  ```
  P0 = -1/rho
  for k=0..K-1:
      Pnext = ( -L^(k+1) - (k+1)*Pk ) / rho
  ```
- Paired zero sum (RH implications):
  ```
  S = sum_{Im(rho)>0} 2*x^(1/2)*Re( exp(i*gamma*L) * P_k(rho,L) )
  ```

## Main term and Stieltjes constants γ_m (what are they?)

- In the explicit formula for Ψ_k(x), the main term is
  $$
  M_k(x)\;=\;x\,L^k\;-\;\sum_{m=0}^{k}\binom{k}{m}\,\gamma_m\,x\,L^{\,k-m},
  \qquad L=\log x.
  $$
- Here γ_m are the Stieltjes constants, defined by the Laurent expansion of ζ(s) at s=1:
  $$
  \zeta(1+u)\;=\;\frac{1}{u}\;+\;\sum_{m\ge 0}\frac{(-1)^m\,\gamma_m}{m!}\,u^m,
  \qquad \gamma_0=\gamma\ \text{(Euler–Mascheroni)}.
  $$
  Equivalently,
  $$
  \gamma_m\;=\;\lim_{N\to\infty}\left(\sum_{n=1}^N\frac{(\log n)^m}{n}\;-\;\frac{(\log N)^{m+1}}{m+1}\right).
  $$
- They encode the smooth (pole-at-1) part of ζ and enter M_k(x) via the binomial combination above.