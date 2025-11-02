## 🔢 Derivation of the Recurrence Relation

The recurrence relation for $P_k(\rho, L)$ is derived by starting with the Exponential Generating Function (EGF):
$$
G(t, L) = \sum_{k\ge0}\frac{P_k(\rho,L)}{k!}\,t^k \;=\; -\,\frac{e^{Lt}}{\rho+t}
$$

### Step 1: Multiply by $(\rho+t)$

Multiply both sides by $(\rho+t)$:
$$
(\rho+t) \sum_{k=0}^{\infty} \frac{P_k(\rho,L)}{k!}\,t^k \;=\; -e^{Lt}
$$

### Step 2: Expand the Left-Hand Side (LHS)

Expand the two parts of the LHS:
$$
\text{LHS} = \rho \sum_{k=0}^{\infty} \frac{P_k(\rho,L)}{k!}\,t^k \;+\; \sum_{k=0}^{\infty} \frac{P_k(\rho,L)}{k!}\,t^{k+1}
$$
Shift the index in the second sum by setting $j=k+1$ (so $k=j-1$):
$$
\text{LHS} = \rho \sum_{k=0}^{\infty} \frac{P_k(\rho,L)}{k!}\,t^k \;+\; \sum_{j=1}^{\infty} \frac{P_{j-1}(\rho,L)}{(j-1)!}\,t^j
$$
To make the powers of $t$ match, pull out the $k=0$ term from the first sum and rename $j$ back to $k$:
$$
\text{LHS} = \rho \frac{P_0(\rho,L)}{0!} + \rho \sum_{k=1}^{\infty} \frac{P_k(\rho,L)}{k!}\,t^k \;+\; \sum_{k=1}^{\infty} \frac{P_{k-1}(\rho,L)}{(k-1)!}\,t^k
$$
Since $\frac{1}{(k-1)!} = \frac{k}{k!}$, we can combine the sums for $k \ge 1$:
$$
\text{LHS} = \rho P_0(\rho,L) + \sum_{k=1}^{\infty} \left( \rho \frac{P_k(\rho,L)}{k!} + k \frac{P_{k-1}(\rho,L)}{k!} \right) t^k
$$
$$
\text{LHS} = \rho P_0(\rho,L) + \sum_{k=1}^{\infty} \frac{1}{k!} \left( \rho P_k(\rho,L) + k P_{k-1}(\rho,L) \right) t^k
$$

### Step 3: Expand the Right-Hand Side (RHS)

Expand the RHS using the Taylor series for $e^{Lt}$:
$$
\text{RHS} = -e^{Lt} = -\sum_{k=0}^{\infty} \frac{(Lt)^k}{k!} = -1 - \sum_{k=1}^{\infty} \frac{L^k}{k!} t^k
$$

### Step 4: Equate Coefficients

Equate the coefficients of $t^k$ for the LHS and RHS.

#### Case $k=0$ (Constant term):
$$
\rho P_0(\rho,L) = -1
$$
This confirms the initial value $P_0(\rho,L) = -1/\rho$.

#### Case $k \ge 1$:
Equate the coefficients of $t^k$:
$$
\frac{1}{k!} \left( \rho P_k(\rho,L) + k P_{k-1}(\rho,L) \right) = -\frac{L^k}{k!}
$$
Multiply by $k!$ and rearrange:
$$
\rho P_k(\rho,L) + k P_{k-1}(\rho,L) = -L^k
$$
Replace $k$ with $k+1$ to find the recurrence for $P_{k+1}$:
$$
\rho P_{k+1}(\rho,L) + (k+1) P_{k}(\rho,L) = -L^{k+1}
$$

### Derivative in x via chain rule

With L = log x and O_k(ρ,x) := x^{\rho} P_k(ρ,L),
- ∂_x P_k(ρ,L) = (k/x) P_{k-1}(ρ,L),
- Product rule + recurrence give the compact ODE
  $$
  \boxed{\,x\,\frac{d}{dx}\,O_k(\rho,x) \;=\; -\,x^{\rho}\,L^k\,.}
  $$
Thus stepping in L (i.e., x → x e^{h}) advances O_k by
  $$
  O_k(L+h) \approx O_k(L) - h\,x^{\rho}\,L^k,
  $$
with higher-order corrections obtainable by standard ODE integrators in L.

Practical note
- Use this ODE to propagate the summed oscillation in L across a grid, pairing conjugates (or quadruplets) to keep the evolution real and stable.

## 📦 The Final Recurrence Relation

The correct recurrence relation for the zero-residue polynomials is:
$$
\boxed{\;P_{k+1}(\rho,L) \;=\; -\,\frac{k+1}{\rho}\,P_{k}(\rho,L) \;-\; \frac{L^{k+1}}{\rho}\;} \quad \text{for } k \ge 0
$$

This linear recurrence, combined with the initial condition $P_0(\rho, L) = -1/\rho$, allows for fast iterative computation of the polynomials:

* **Example for $k=0$ (finding $P_1$):**
    $$P_1(\rho,L) = -\frac{1}{\rho}P_0(\rho,L) - \frac{L}{\rho} = -\frac{1}{\rho}\left(-\frac{1}{\rho}\right) - \frac{L}{\rho} = \frac{1}{\rho^2} - \frac{L}{\rho}$$ (Matches the known $P_1$)

* **Example for $k=1$ (finding $P_2$):**
    $$P_2(\rho,L) = -\frac{2}{\rho}P_1(\rho,L) - \frac{L^2}{\rho} = -\frac{2}{\rho}\left(\frac{1}{\rho^2} - \frac{L}{\rho}\right) - \frac{L^2}{\rho} = -\frac{2}{\rho^3} + \frac{2L}{\rho^2} - \frac{L^2}{\rho}$$ (Matches the known $P_2$)

This recurrence provides the simplest and most numerically stable way to compute the sequence of polynomials $P_k$ in practical applications.