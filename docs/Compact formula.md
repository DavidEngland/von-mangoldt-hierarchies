# Compact formulas for P_k(ρ,L) — cheat sheet + prompts

Notation
- L := log x; u := 1/ρ; E_k(z) := ∑_{j=0}^k z^j/j!.
- No RH is assumed by default; RH consequences are noted explicitly when relevant.

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