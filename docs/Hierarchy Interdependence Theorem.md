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

## Chain rule in x (L = log x): ODEs and practical use

Since L = log x, we have dL/dx = 1/x and therefore
- ∂_L P_k(ρ,L) = k P_{k-1}(ρ,L)  (Appell property),
- ∂_x P_k(ρ,L) = (1/x) ∂_L P_k(ρ,L) = (k/x) P_{k-1}(ρ,L).

For the full zero term O_k(ρ,x) := x^ρ P_k(ρ,L), the product rule and the k–recurrence give
- d/dx [x^ρ P_k(ρ,L)]
  = ρ x^{ρ-1} P_k(ρ,L) + x^ρ (k/x) P_{k-1}(ρ,L)
  = x^{ρ-1}[ρ P_k + k P_{k-1}]
  = - x^{ρ-1} L^k,
- equivalently, the compact ODE
  $$
  \boxed{\,x\,\frac{d}{dx}\big[x^{\rho}P_k(\rho,L)\big] \;=\; -\,x^{\rho}\,L^k\,.}
  $$

Consequences (sum over zeros)
- Let S_k(x) := ∑_ρ x^ρ P_k(ρ, L). Then
  $$
  \boxed{\,x\,\frac{d}{dx} S_k(x) \;=\; - \sum_{\rho} x^{\rho} L^k\,.}
  $$
  Under conjugate or quadruplet pairing this is a real ODE in x with right-hand side x^{1/2} times trigonometric polynomials in L.

Second derivative (optional)
- From x d/dx[x^ρ P_k] = −x^ρ L^k one gets
  $$
  x^2\,\frac{d^2}{dx^2}\big[x^{\rho}P_k\big]
  = -\,x^{\rho}\big(\rho\,L^k + k\,L^{k-1}\big).
  $$

Implementation prompts (no code)
- March in x using the ODE (single zero):
  ```
  // inputs: rho, k, x0, L0=log x0, initial T0 = x0^rho * P_k(rho, L0)
  // step x -> x * exp(h), i.e., L -> L + h
  for steps:
      // RHS at current (x,L): R = - x^rho * L^k
      T_next = T + h * R            // since x d/dx T = d/dL T; step in L by h
      L += h;  x = exp(L);  T = T_next
  ```
- March the summed oscillation (paired zeros or quadruplets):
  ```
  // S_k(L) = sum x^rho P_k(rho,L)
  // ODE: d/dL S_k = - sum x^rho L^k
  for steps in L:
      RHS = - sum_over_pairs [ 2 * x^(1/2) * Re( e^{i gamma L} * L^k ) ]   // RH implications; otherwise use quadruplets
      S_k_next = S_k + h * RHS
  ```
- Mixed derivatives:
  ```
  // use: ∂_x P_k = (k/x) P_{k-1}, and ∂_L P_k = k P_{k-1}
  // convert any needed ∂_x to ∂_L via ∂_x = (1/x) ∂_L
  ```