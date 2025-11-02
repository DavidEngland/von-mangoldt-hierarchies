# Compact formulas for P_k(ρ,L) — cheat sheet + problem set

Notation
- L := log x, ρ a simple zero, u := 1/ρ, E_k(z) := ∑_{j=0}^k z^j/j!.

Core identities (simple zero)
- Truncated exponential
  $$
  P_k(\rho,L)=(-1)^{k+1}\frac{k!}{\rho^{k+1}}\,E_k(-L\rho).
  $$
- Falling-factorial (Horner in L)
  $$
  P_k(\rho,L)=-\frac{1}{\rho}\sum_{j=0}^k(-1)^j\frac{(k)^{\underline{j}}}{\rho^j}L^{k-j}.
  $$
- EGF in k
  $$
  \sum_{k\ge0}\frac{P_k(\rho,L)}{k!}\,t^k=-\frac{e^{Lt}}{\rho+t}.
  $$
- Linear recurrence (in k)
  $$
  \rho P_{k+1}(\rho,L)+(k+1)P_k(\rho,L)=-L^{k+1}.
  $$

Pairing kernels (notation: ρ=β+iγ)
- Conjugate pair (β=1/2) contribution
  $$
  x^\rho P_k(\rho,L)+x^{\bar\rho}P_k(\bar\rho,L)=2x^{1/2}\,\Re\!\big(e^{i\gamma L}P_k(\rho,L)\big).
  $$
- Reflection–conjugation quadruplet Q(ρ) EGF
  $$
  \sum_{\sigma\in Q(\rho)}x^\sigma\!\sum_{k\ge0}\frac{P_k(\sigma,L)}{k!}t^k
  =-\sum_{\sigma\in Q(\rho)}\frac{e^{(\sigma+t)L}}{\sigma+t}.
  $$

Masters — worked mini examples
1) Show the top term is −L^k/ρ:
- From the falling-factorial form, the j=0 term equals −(1/ρ)L^k.

2) Quick check (k=2):
- Expand E_2(−Lρ)=1−Lρ+(Lρ)^2/2 and scale by (−1)^{3}2!/ρ^3 to get
  $$
  P_2=-\frac{L^2}{\rho}+\frac{2L}{\rho^2}-\frac{2}{\rho^3}.
  $$

3) Verify the recurrence for k=0:
- Check ρP_1+1·P_0=−L → P_1=−L/ρ−P_0/ρ=−L/ρ+1/ρ^2.

PhD — short derivations
A) Derive the EGF:
- Start from P_k truncated exponential form; sum over k, swap sums, recognize (ρ+t)^{-1}e^{Lt}.

B) Prove the linear recurrence:
- Multiply the EGF by (ρ+t) and equate coefficients.

C) Appell property:
- Show ∂_L P_k = k P_{k-1} from any of the three forms above.

Computational prompts (no code; pseudo-code ok)
- Prompt 1 (Coefficients via truncated exponential)
  Goal: given (ρ, L, k), compute P_k robustly.
  Pseudocode:
  ```
  // input: rho, L, k
  z = -L * rho
  t = 1.0 / k!           // precompute descending 1/j! if needed
  E = t
  for m from k-1 down to 0:
      t = t * z + 1/m!
  Pk = (-1)^(k+1) * k! * E / rho^(k+1)
  ```

- Prompt 2 (Horner in L with falling factorials)
  ```
  // input: rho, L, k
  a0 = -1/rho
  p  = a0
  factdown = 1            // (k)↓0
  for j in 1..k:
      factdown = factdown * (k - j + 1)
      aj = -(-1)^j * factdown / rho^(j+1)
      p  = p * L + aj
  return p
  ```

- Prompt 3 (Table for a list of zeros with conjugate pairing)
  ```
  // input: zeros R = [rho_1,...,rho_N], L, k
  sum = 0
  for r in R with Im(r) > 0:
      Pk = P_k(r, L)         // from Prompt 1
      term = 2 * x^(Re(r)) * Re( exp(i*Im(r)*L) * Pk )
      sum += term
  return x^(1/2) * sum        // if RH; else use quadruplet pairing
  ```

- Prompt 4 (EGF-based moment sweep over k)
  ```
  // input: rho, L, Kmax
  // Build all P_k from the recurrence
  P0 = -1/rho
  P = [P0]
  for k in 0..Kmax-1:
      Pnext = ( -L^(k+1) - (k+1)*P[k] ) / rho
      append Pnext to P
  return P
  ```

Project ideas (Masters → PhD)
- Masters: build a CSV table of coefficients of L^j in P_k up to k=8 for a fixed ρ; verify symmetry patterns numerically.
- PhD: numerically verify the quadruplet EGF identity and extract S_k(L) = ∑_{σ∈Q(ρ)} x^σ P_k(σ,L) via t-derivatives at 0; compare with recurrence aggregation.