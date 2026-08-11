# Well‑known L-functions — quick facts, hierarchies, and P_k links

How hierarchies and P_k generalize
- Given an L-function with Dirichlet series L(s)=∑_{n≥1} a(n) n^{−s}, Euler product ∏_p ∏_{j=1}^d (1 − α_{p,j} p^{−s})^{−1}, conductor Q and completed form Λ(s)=Q^{s/2}G(s)L(s) satisfying Λ(s)=ε Λ(1−s):
  - Generalized von Mangoldt (prime powers): Λ_L(p^r) = (∑_{j} α_{p,j}^{\,r}) log p, and Λ_L(n)=0 if n is not a prime power.
  - Hierarchies: for k≥0,
    (-1)^k d^k/ds^k[−L′/L(s)] = ∑_{n≥1} Λ_{k,L}(n) n^{−s}, with
    Λ_{k,L}(p^r) = (∑_{j} α_{p,j}^{\,r}) (log p)^{k+1} r^k.
  - Main term M_{k,L}(x) comes from the pole at s=1 only (if present): write −L′/L(1+u)=1/u+∑_{m≥0} c_m(L) u^m, then
    M_{k,L}(x)= x (log x)^k − ∑_{m=0}^k binom(k,m) c_m(L) x (log x)^{k−m}.
    If L is entire at s=1, M_{k,L}(x)=0 (up to archimedean background if you absorb Γ-factors).
  - Zero terms are universal: each simple zero ρ contributes x^{ρ} P_k(ρ, log x) with
    ∑_{k≥0} P_k(ρ, L) t^k/k! = − e^{Lt}/(ρ + t) and recurrence ρ P_{k+1} + (k+1) P_k = −L^{k+1}.
  - Pairing: with completed Λ(s)=εΛ(1−s), zeros occur in {ρ, 1−ρ, ρ̄, 1−ρ̄}. Quadruplet sum yields a real contribution; under GRH and self-duality, conjugate pairing around 1/2 gives x^{1/2} scaling (hyperbolic weights collapse).

Below, d = degree, Q = conductor, ε = root number, G(s) = Γ-factor(s).

---

Riemann zeta ζ(s)
- Data: d=1, Q=1; pole at s=1; completed Λ(s)=π^{−s/2} Γ(s/2) ζ(s), ε=1.
- Hierarchy: Λ_k(n)=Λ(n)(log n)^k, Λ_k(p^r)=(log p)^{k+1} r^k.
- Main term: M_k(x)=xL^k − ∑_{m≤k} binom(k,m) γ_m x L^{k−m} (γ_m Stieltjes).
- P_k and pairing: universal P_k; conjugate/quadruplet pairing as in notes; under RH amplitude ~ x^{1/2}.

Dirichlet L(s, χ) (primitive character modulo q)
- Data: d=1, Q=q; entire except principal where a ζ‑factor contributes the pole; Λ(s,χ) = (q/π)^{(s+κ)/2} Γ((s+κ)/2) L(s,χ), κ∈{0,1}, ε(χ) on unit circle.
- Hierarchy:
  - Λ_{k,χ}(p^r)=χ(p)^r (log p)^{k+1} r^k for p∤q; local modifications at p|q.
- Main term:
  - χ non‑principal: no pole at 1 ⇒ M_{k,L}(x)=0 (up to Γ‑background if included).
  - χ principal: −L′/L inherits 1/u with c_m depending on q ⇒ same binomial main term with c_m(χ).
- P_k and pairing: zeros satisfy ρ ↔ 1−ρ under completion; if χ real, self‑dual pairing; otherwise use ρ ↔ 1−ρ̄. Under GRH, x^{1/2} scaling.

Dedekind zeta ζ_K(s) for number field K
- Data: d = [K:ℚ], Q = |D_K| (discriminant); simple pole at s=1; Γ‑factors per real/complex embeddings; ε=1.
- Hierarchy: Λ_{k,ζ_K}(p^r)= (∑_{𝔭|p} f_{𝔭} 1_{N𝔭^r=p^{rf_{𝔭}}}) (log p)^{k+1} r^k; abstractly via local Satake parameters α_{p,j}.
- Main term: same binomial structure with c_m(ζ_K) from −ζ′_K/ζ_K(1+u).
- P_k and pairing: universal at simple zeros; quadruplet pairing via completion; GRH(K) ⇒ x^{1/2}.

Hecke L(s, χ_K) (Grössencharacters)
- Data: d=1 over K; Q depends on conductor and D_K; entire; ε on unit circle.
- Hierarchy/Main/P_k: as for Dirichlet, with local Satake α_{p,j}=χ_K(𝔭); no pole at 1 unless trivial component.

Holomorphic newform L(s,f) (weight k, level N)
- Data: d=2, Q=N; entire; Λ(s,f)=N^{s/2} (2π)^{−(s+(k−1)/2)} Γ(s+(k−1)/2) L(s,f); ε=±1 (sign).
- Hierarchy: Λ_{k,f}(p^r) = a_{p^r} (log p)^{k+1} r^k with a_{p^r}=α_p^r+β_p^r, α_pβ_p=ε(p)p^{k−1} (good primes).
- Main term: no pole at 1 ⇒ M_{k,L}(x)=0 (after completion; archimedean background lives in Γ if included).
- P_k and pairing: universal; central point 1/2 after completion; sign ε controls spectral symmetry; under GRH, x^{1/2}.

Maass form L(s,f) (level N, Laplace eigenvalue 1/4+t_f^2)
- Data: d=2; entire; Γ_ℝ factors Γ((s+it_f)/2)Γ((s−it_f)/2); ε=±1.
- Hierarchy/Main/P_k: as holomorphic newforms; no pole at 1; universal P_k; x^{1/2} under GRH.

Rankin–Selberg L(s, f×g)
- Data: d=4 (GL(2)×GL(2)); entire (except diagonal poles for f=g at s=1); conductor ≍ N_f^2 N_g^2; ε of modulus 1.
- Hierarchy: Λ_{k,f×g}(p^r)=(α_p^r+β_p^r)(α′_p{}^{\,r}+β′_p{}^{\,r})(log p)^{k+1} r^k at good p.
- Main term: pole at s=1 only in diagonal (f=g) ⇒ M_{k,L}(x) present there with c_m(f×f).
- P_k, pairing: universal; degree 4 zero set; GRH ⇒ x^{1/2}.

Symmetric power L(s, Sym^m f)
- Data: d=m+1; entire for small m (m≤4 proven); conductor ~ N^{m+1}; ε on unit circle.
- Hierarchy: Λ_{k,Sym^m f}(p^r)= (∑_{j=0}^m α_p^{r(m−j)} β_p^{r j}) (log p)^{k+1} r^k.
- Main term: entire ⇒ no pole at 1 (aside from exceptional cases); universal P_k; GRH ⇒ x^{1/2}.

Artin L(s, ρ) (Galois representation ρ)
- Data: degree d=dim ρ; conductor Q(ρ); entire unless ρ contains the trivial rep; ε a root of unity.
- Hierarchy: Λ_{k,ρ}(p^r)= (Tr ρ(Frob_p^r)) (log p)^{k+1} r^k (unramified p).
- Main term: trivial component ⇒ pole at 1 with c_m from −L′/L(1+u); otherwise none. Universal P_k; GRH(ρ) ⇒ x^{1/2}.

Hasse–Weil L(E,s) of an elliptic curve E/ℚ
- Data: d=2; entire; conductor N_E; ε=±1; equals L(s,f_E) for the modular form attached to E.
- Hierarchy/Main/P_k: as holomorphic newform.

Dedekind ζ of quadratic field and Dirichlet β(s)=L(s, χ_{−4})
- Special cases of Dirichlet/Hecke: β(s) (d=1, Q=4), entire; hierarchy via χ_{−4}; no pole at 1; P_k universal.

Automorphic L(s, π) on GL(n,ℚ)
- Data: d=n; conductor Q(π); completed Λ(s,π)=Q^{s/2} ∏_{j=1}^n Γ_ℝ(s+μ_j) L(s,π), ε(π).
- Hierarchy (prime powers): Λ_{k,π}(p^r)= (∑_{j=1}^n α_{p,j}^{\,r}) (log p)^{k+1} r^k (unramified p).
- Main term: pole at 1 iff π contains trivial component; c_m(π) from −L′/L(1+u); else zero. Universal P_k and pairing; GRH(π) ⇒ x^{1/2}.

Hasse–Weil L of varieties (curves, motives)
- Data: degree = rank of motive; conductor from bad reduction; expected analytic continuation and functional equation (proved in many cases).
- Hierarchy/Main/P_k: same template using local Frobenius traces; main term only when a pole at 1 is present; universal P_k.

Epstein zeta (quadratic forms) — zeta‑type, not standard L in Selberg class
- Data: meromorphic with simple pole at 1; functional equation; Euler product typically absent.
- Hierarchy: defined via −ζ′/ζ analogues if Euler product is available; otherwise treat via spectral expansion; P_k usage limited.

---

Pairing and x^{1/2} scaling (all above)
- Conjugate/quadruplet pairing:
  - Completed symmetry gives zeros in {ρ, 1−ρ, ρ̄, 1−ρ̄}. A quadruplet block contributes
    2 x^{1/2}[C^+(L) cos(γL) + C^−(L) sin(γL)], with hyperbolic weights x^{±(β−1/2)} off the line.
  - Under GRH (β=1/2) the hyperbolic weights collapse to 1, leaving pure x^{1/2} oscillations modulated by P_k.
- Universality of P_k:
  - P_k(ρ,L) depends only on (ρ, L=log x); it is independent of the L-function family. All arithmetic enters only through the zero set {ρ} and the main-term coefficients c_m(L) at s=1 (if any).

Minimal recipes (students)
- To construct Λ_{k,L}: read local Satake parameters α_{p,j}; set Λ_{k,L}(p^r)=(∑_j α_{p,j}^{\,r})(log p)^{k+1} r^k; zero elsewhere.
- To build Ψ_{k,L}(x):
  - Main term: include only if L has a simple pole at 1; use c_m(L) in M_{k,L}(x).
  - Zero sum: use universal P_k with the zero set of L; pair conjugates/quadruplets; under GRH, expect x^{1/2}.
