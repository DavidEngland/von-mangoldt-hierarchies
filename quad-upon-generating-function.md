# Quadruplet pairing via the EGF of P_k

Notation
- L := log x (not an L-function). In all EGFs, e^{Lt} = x^{t}.
- ρ = β + iγ, Q(ρ) := {ρ, 1−ρ, ρ̄, 1−ρ̄}.

Single‑zero EGF (in k)
$$
\sum_{k\ge0}\frac{P_k(\sigma,L)}{k!}\,t^k \;=\; -\frac{e^{Lt}}{\sigma+t}.
$$

Quadruplet kernel (real for real L,t)
$$
S_{\mathrm{quad}}(t;L)
:= \sum_{\sigma\in Q(\rho)} x^{\sigma} \sum_{k\ge0}\frac{P_k(\sigma,L)}{k!}t^k
= -\sum_{\sigma\in Q(\rho)} \frac{e^{(\sigma+t)L}}{\sigma+t}.
$$

Harmonic decomposition (general β,γ)
- Factor e^{(\frac12+t)L} and write
$$
S_{\mathrm{quad}}(t;L)
= -\,2\,e^{(\tfrac12+t)L}\Big[ C^+_{t,\rho}(L)\cos(\gamma L)+C^-_{t,\rho}(L)\sin(\gamma L)\Big],
$$
with
$$
C^+_{t,\rho}(L)=\Re\!\Big(\frac{e^{(\beta-\tfrac12)L}}{\rho+t}+\frac{e^{-(\beta-\tfrac12)L}}{1-\rho+t}\Big),\quad
C^-_{t,\rho}(L)=\Im\!\Big(\frac{e^{(\beta-\tfrac12)L}}{\rho+t}-\frac{e^{-(\beta-\tfrac12)L}}{1-\rho+t}\Big).
$$

Coefficient extraction
- Define S_k(L):=∑_{σ∈Q} x^{σ} P_k(σ,L). Then
$$
S_{\mathrm{quad}}(t;L)=\sum_{k\ge0}\frac{t^k}{k!}\,S_k(L)
\;\Rightarrow\;
S_k(L)=\left.\frac{d^k}{dt^k}S_{\mathrm{quad}}(t;L)\right|_{t=0}.
$$
- Practical: differentiate the closed form −∑ e^{(\sigma+t)L}/(σ+t) at t=0.

Aggregated recurrence
- For each σ: σ P_{k+1}+(k+1)P_k=−L^{k+1}. Summing over Q(ρ),
$$
\sum_{\sigma\in Q(\rho)} \sigma\,P_{k+1}(\sigma,L) + (k+1)\,S_k(L) \;=\; -\,4\,L^{k+1}.
$$
