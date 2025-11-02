# Compact formulas for P_k(ρ, L) — cheat sheet + problems

Notation
- L := log x; u := 1/ρ; E_k(z) := ∑_{j=0}^k z^j/j!.

Core identities (simple zero ρ)
- Truncated exponential:  P_k = (−1)^{k+1} k!/ρ^{k+1} · E_k(−Lρ).
- Falling-factorial (Horner in L):  P_k = −(1/ρ) ∑_{j=0}^k (−1)^j (k)↓j · L^{k−j}/ρ^{j}.
- EGF in k:  ∑_{k≥0} P_k t^k/k! = − e^{Lt}/(ρ + t).
- Linear recurrence:  ρ P_{k+1} + (k+1) P_k = − L^{k+1}.
- Appell: ∂_L P_k = k P_{k−1}; chain rule: ∂_x P_k = (k/x) P_{k−1}.

Pairing kernels (ρ = β + iγ)
- Conjugate pair (RH implications): x^ρ P_k + x^{ρ̄} P_k(ρ̄,L) = 2 x^{1/2} Re(e^{iγL} P_k(ρ,L)).
- Quadruplet kernel (EGF): ∑_{σ∈Q(ρ)} x^σ ∑ P_k(σ,L) t^k/k! = −∑_{σ∈Q} e^{(σ+t)L}/(σ+t).

Masters — worked minis
- Show the top term is −L^k/ρ from the falling-factorial form (j=0 term).
- k=2 via E_2(−Lρ): P_2 = −L^2/ρ + 2L/ρ^2 − 2/ρ^3.
- Verify ρP_1 + P_0 = −L.

PhD — short derivations
- Derive the EGF and the recurrence from (ρ+t)∑ P_k t^k/k! + e^{Lt} = 0.
- Prove Appell: ∂_L P_k = k P_{k−1}.
- Write the quadruplet EGF and extract S_k(L) by k-th derivative at t=0.

Computational prompts (pseudo-code only)
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
  S = sum_{Im(rho)>0} 2*x^(1/2) * Re( exp(i*gamma*L) * P_k(rho,L) )
  ```