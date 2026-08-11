# Hierarchy Interdependence Theorem — structure and practice

Setup
- L := log x, Ψ_k(x) := ∑_{n≤x} Λ_k(n), and for each simple zero ρ,
  the oscillatory contribution is x^ρ P_k(ρ,L), deg_L P_k ≤ k.

Key identities (per zero)
- Appell lowering in L:
  $$
  \frac{\partial}{\partial L}P_k(\rho,L)=k\,P_{k-1}(\rho,L).
  $$
- k-recursion (equivalently):
  $$
  \rho\,P_k(\rho,L)+k\,P_{k-1}(\rho,L)=-\,L^k.
  $$

Theorem (Interdependence operator on zero contributions)
For fixed ρ and L=log x,
$$
\frac{\partial}{\partial L}\Big[x^{\rho}P_k(\rho,L)\Big]
= x^{\rho}\Big(\rho\,P_k(\rho,L)+k\,P_{k-1}(\rho,L)\Big)
= -\,x^{\rho}\,L^{k}.
$$
Hence a single differentiation in L converts the k-th zero term to a pure polynomial mode −x^ρ L^k.

Consequences
- Summing over zeros (formal level),
  $$
  \frac{\partial}{\partial L}\left[\sum_{\rho} x^{\rho}P_k(\rho,L)\right]
  = -\sum_{\rho} x^{\rho} L^k.
  $$
- Pairing (if RH holds, or use quadruplets in general) gives purely real right-hand sides in terms of cos(γL), sin(γL) with polynomial envelopes in L.
- Main term interdependence: differentiate the known main term
  $$
  M_k(x)=xL^k - \sum_{m=0}^{k}\binom{k}{m}\gamma_m\,xL^{k-m}
  $$
  to relate M_k' to M_{k-1} plus explicit polynomials in L (exercise below).

Masters — examples
1) Verify the identity for k=1 directly:
- From P_1=−L/ρ+1/ρ^2 and P_0=−1/ρ,
  ρP_1+1·P_0 = −L.

2) Show ∂_L[x^ρ P_2]=−x^ρ L^2 by explicit differentiation of P_2.

PhD — short proof
- Differentiate x^ρ P_k w.r.t. L:
  ∂_L(x^ρ P_k) = x^ρ(ρP_k + ∂_L P_k).
  Use Appell (∂_L P_k = k P_{k-1}) and the linear recurrence
  (ρP_k + k P_{k-1} = −L^k).

Computational prompts (no code; pseudo-code ok)
- Prompt A (Differentiate a truncated zero sum across k)
  ```
  // input: k, zeros {rho_j}, L
  // compute S_k(L) = sum_j x^{rho_j} P_k(rho_j, L)
  S = 0
  for each rho in zeros:
      S += x^(rho) * P_k(rho, L)
  // interdependence derivative
  dS_dL = - sum_j x^(rho_j) * L^k
  // verify numerically: finite-difference S ≈ dS_dL
  ```

- Prompt B (Bootstrap P_{k} from P_{k-1} across all zeros with one pass)
  ```
  // input: L, zeros, P_{k-1} already computed
  // use: rho*P_k + k*P_{k-1} = -L^k  => P_k = ( -L^k - k*P_{k-1} ) / rho
  for each rho:
      Pk[rho] = ( -L^k - k * Pkm1[rho] ) / rho
  ```

- Prompt C (Reuse a zero-sum table across k)
  ```
  // store for each rho: P0[rho] = -1/rho
  for k in 1..Kmax:
      for each rho:
          Pk[rho] = ( -L^k - k * P_{k-1}[rho] ) / rho
      S_k(L) = sum_rho x^(rho) * Pk[rho]     // pair conjugates or use quadruplets
  ```

Exercises (Masters → PhD)
- M1. Show that the interdependence identity forces deg_L P_k ≤ k (by induction).
- M2. Under conjugate pairing (β=1/2), write ∂_L of the paired term explicitly in cos/sin and confirm it equals −2x^{1/2}L^k cos(γL) after taking real parts of e^{iγL}.
- P1. Prove that for the quadruplet sum S_quad,k(L) the derivative in L yields a real combination of cos(γL), sin(γL) weighted by L^k with envelopes constant in k.
- P2. Using the EGF −e^{Lt}/(ρ+t), derive the entire interdependence family in one line by differentiating w.r.t. L under the sum and equating coefficients of t^k.
- P3. Show how to propagate main terms M_k by differentiation in L and identify the exact polynomial correction required to match M_{k-1}.

---

## 📜 Hierarchy Interdependence Theorem — ∂_L and ∂_x forms

Setup
- L := log x; O_k(ρ,x) := x^{\rho} P_k(ρ,L).
- Appell: ∂_L P_k = k P_{k-1}; recurrence: ρ P_k + k P_{k-1} = −L^k.

Theorem (∂_L operator on the zero term)
$$
\frac{\partial}{\partial L}\big[x^{\rho}P_k(\rho,L)\big]
= x^{\rho}\,\big(\rho P_k(\rho,L)+k P_{k-1}(\rho,L)\big)
= -\,x^{\rho}\,L^k.
$$

Chain rule in x (dL/dx = 1/x)
- ∂_x P_k = (1/x)∂_L P_k = (k/x) P_{k-1}.
- Single‑zero ODE:
  $$
  x\,\frac{d}{dx}\big[x^{\rho}P_k(\rho,L)\big] \;=\; -\,x^{\rho}\,L^k.
  $$

Zero‑sum consequence
- For S_k(x):=∑_ρ x^{\rho}P_k(ρ,L), one has x dS_k/dx = −∑_ρ x^{\rho} L^k (pair in conjugates/quadruplets to keep it real).

Prompts (no code)
- March in L:
  ```
  // d/dL [x^rho P_k] = - x^rho L^k
  T_next = T - h * x^rho * L^k
  ```
- Build P_k from P_{k-1}:
  ```
  Pk = ( -L^k - k*P_{k-1} ) / rho
  ```
- Quadruplet extraction:
  ```
  S_k(L) = d^k/dt^k [ - sum_{σ∈Q(ρ)} e^{(σ+t)L}/(σ+t) ] at t=0
  ```

## Why Appell lowering underpins interdependence

- Appell property (lowering): ∂_λ P_k(ρ,λ) = k P_{k-1}(ρ,λ) with λ := log x.
- Together with the k-recursion ρ P_k + k P_{k-1} = −λ^k, it yields
  ∂_λ[x^ρ P_k] = x^ρ(ρ P_k + k P_{k-1}) = −x^ρ λ^k
  and, via dλ/dx = 1/x, the x-ODE x d/dx[x^ρ P_k] = −x^ρ λ^k.

Necessity (informal): If for all ρ and λ the identity ∂_λ[x^ρ P_k] = −x^ρ λ^k holds with P_k polynomial in λ of degree ≤ k and P_0 constant in λ, then comparing λ-degrees forces ∂_λ P_k = k P_{k-1} and a linear relation ρ P_k + k P_{k-1} = −λ^k. Thus the Appell lowering is the backbone of (and essentially equivalent to) the interdependence identities used throughout.

Notation
- We prefer λ := log x to avoid collision with “L-function.” In older notes L ≡ λ.