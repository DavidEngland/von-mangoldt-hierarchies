# L-Functions and Modular Forms in the Context of von Mangoldt Hierarchies

**Level:** Advanced Graduate (Analytic Number Theory)  
**Duration:** 3-4 lectures (90 minutes each)  
**Prerequisites:** Complex analysis, basic modular forms, Dirichlet characters, von Mangoldt hierarchies

---

## 📚 Learning Objectives

By the end of this module, students will:
1. Understand how L-functions generalize the Riemann zeta function
2. Connect modular forms to arithmetic functions via their L-series
3. Extend von Mangoldt hierarchies to L-functions and character twists
4. Apply explicit formulas to L-functions with modular form coefficients
5. Explore computational aspects and current research directions

---

## 🎯 Lecture 1: From Zeta to L-Functions — Generalizing von Mangoldt

### 1.1 Review: The Classical Setup

**The Riemann Zeta Function:**
$$\zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^s} = \prod_p \left(1 - p^{-s}\right)^{-1}$$

**Von Mangoldt Function and Its Hierarchy:**
$$-\frac{\zeta'(s)}{\zeta(s)} = \sum_{n=1}^{\infty} \frac{\Lambda(n)}{n^s}$$

$$(-1)^k \frac{d^k}{ds^k}\left(-\frac{\zeta'(s)}{\zeta(s)}\right) = \sum_{n=1}^{\infty} \frac{\Lambda_k(n)}{n^s}$$

### 1.2 Dirichlet L-Functions

**Definition:** For a Dirichlet character $\chi$ modulo $q$:
$$L(s, \chi) = \sum_{n=1}^{\infty} \frac{\chi(n)}{n^s} = \prod_p \left(1 - \chi(p)p^{-s}\right)^{-1}$$

**Generalized von Mangoldt Function:**
$$\Lambda_{\chi}(n) = \begin{cases}
\chi(p)\log p & \text{if } n = p^k \\
0 & \text{otherwise}
\end{cases}$$

**Key Identity:**
$$-\frac{L'(s,\chi)}{L(s,\chi)} = \sum_{n=1}^{\infty} \frac{\Lambda_{\chi}(n)}{n^s}$$

### 1.3 Character Hierarchies

**Definition:** For integer $k \geq 0$:
$$(-1)^k \frac{d^k}{ds^k}\left(-\frac{L'(s,\chi)}{L(s,\chi)}\right) = \sum_{n=1}^{\infty} \frac{\Lambda_{k,\chi}(n)}{n^s}$$

**Explicit Formula:**
$$\Lambda_{k,\chi}(p^r) = \chi(p)(\log p)^{k+1} r^k$$

### 💡 Key Insight
The character $\chi$ acts as a "twist" that preserves the logarithmic structure while introducing modular arithmetic constraints.

### 🧠 Exercises (Lecture 1)

1. **Character Verification:** For the character $\chi$ modulo 4 with $\chi(1)=1, \chi(3)=-1$, compute $\Lambda_{\chi}(n)$ for $n \leq 20$.

2. **Euler Product:** Show that if $\chi$ is primitive, then
   $$L(s,\chi) = \prod_p \left(1 - \chi(p)p^{-s}\right)^{-1}$$
   converges for $\Re(s) > 1$.

3. **Functional Equation Sketch:** State (without proof) the functional equation for $L(s,\chi)$ and identify the gamma factors.

---

## 🎯 Lecture 2: Modular Forms and Their L-Series

### 2.1 Modular Forms Primer

**Definition:** A modular form $f$ of weight $k$ for $\Gamma_0(N)$ satisfies:
$$f\left(\frac{az+b}{cz+d}\right) = (cz+d)^k f(z)$$
for all $\begin{pmatrix} a & b \\ c & d \end{pmatrix} \in \Gamma_0(N)$.

**Fourier Expansion:**
$$f(z) = \sum_{n=1}^{\infty} a_n e^{2\pi i nz}$$

### 2.2 L-Series of Modular Forms

**Definition:** For a normalized eigenform $f$ with Fourier coefficients $a_n$:
$$L(s,f) = \sum_{n=1}^{\infty} \frac{a_n}{n^s}$$

**Euler Product:** For newforms:
$$L(s,f) = \prod_p L_p(s,f)^{-1}$$
where $L_p(s,f) = 1 - a_p p^{-s} + \epsilon(p) p^{k-1-2s}$ with $\epsilon(p)$ depending on the level.

### 2.3 Modular von Mangoldt Functions

**Definition:** Associated to a newform $f$:
$$\Lambda_f(n) = \begin{cases}
a_p \log p & \text{if } n = p^m, p \nmid N \\
b_{p,m} \log p & \text{if } n = p^m, p \mid N \\
0 & \text{otherwise}
\end{cases}$$

where $b_{p,m}$ comes from the local factor at bad primes.

**Generating Series:**
$$-\frac{L'(s,f)}{L(s,f)} = \sum_{n=1}^{\infty} \frac{\Lambda_f(n)}{n^s}$$

### 2.4 Modular Hierarchies

**Definition:**
$$(-1)^k \frac{d^k}{ds^k}\left(-\frac{L'(s,f)}{L(s,f)}\right) = \sum_{n=1}^{\infty} \frac{\Lambda_{k,f}(n)}{n^s}$$

**Prime Power Formula:**
$$\Lambda_{k,f}(p^r) = a_p (\log p)^{k+1} r^k \quad \text{(good primes)}$$

### 💡 Key Insight
The Hecke eigenvalues $a_p$ play the same role as $\chi(p)$ in Dirichlet L-functions, but now carry deep arithmetic information from modular forms.

### 🧠 Exercises (Lecture 2)

1. **Ramanujan Delta:** For $\Delta(z) = q \prod_{n=1}^{\infty}(1-q^n)^{24}$ with $q = e^{2\pi i z}$, identify the first few Fourier coefficients and write the first terms of $L(s,\Delta)$.

2. **Bad Primes:** Explain why the Euler product for $L(s,f)$ requires modification at primes dividing the level $N$.

3. **Functional Equation:** State the functional equation for $L(s,f)$ where $f$ is a newform of weight $k$ and level $N$.

---

## 🎯 Lecture 3: Explicit Formulas for L-Functions

### 3.1 General Framework

**Mellin Inversion:** For L-functions $L(s)$ with suitable properties:
$$\Psi_L(x) := \sum_{n \leq x} \Lambda_L(n) = \frac{1}{2\pi i} \int_{c-i\infty}^{c+i\infty} -\frac{L'(s)}{L(s)} \frac{x^s}{s} ds$$

### 3.2 Contribution from Poles and Zeros

**Main Terms:** From poles of $L(s)$:
- For primitive characters: residue at $s=1$ (if $\chi$ is principal)
- For modular forms: typically no pole at $s=1$

**Oscillatory Terms:** From zeros $\rho$ of $L(s)$:
$$\sum_{\rho} \frac{x^{\rho}}{\rho}$$

### 3.3 Character L-Function Explicit Formula

**For primitive $\chi \neq \chi_0$:**
$$\Psi_{\chi}(x) = -\sum_{\rho} \frac{x^{\rho}}{\rho} + O(\log x)$$

**Generalized Riemann Hypothesis (GRH):** All non-trivial zeros have $\Re(\rho) = 1/2$.

### 3.4 Modular Form Explicit Formula

**For newform $f$ of weight $k \geq 2$:**
$$\Psi_f(x) = -\sum_{\rho} \frac{x^{\rho}}{\rho} + \delta_f x^{k-1} + O(x^{(k-1)/2+\epsilon})$$

where $\delta_f$ accounts for the pole at $s=k$ (if it exists).

### 3.5 Hierarchical Explicit Formulas

**For the $k$-th hierarchy:**
$$\Psi_{k,L}(x) = M_{k,L}(x) + \sum_{\rho} x^{\rho} P_k(\rho, \log x) + O(\text{error})$$

where:
- $M_{k,L}(x)$ involves residues at poles
- $P_k(\rho, \log x)$ are polynomials in $\log x$ of degree $\leq k$

### 💡 Key Insight
The explicit formulas reveal how the arithmetic of L-functions (through their zeros) controls the distribution of weighted prime sums.

### 🧠 Exercises (Lecture 3)

1. **Character Explicit Formula:** For $\chi$ the non-principal character mod 3, write out the explicit formula for $\Psi_{\chi}(x)$ including the contribution from the first few zeros.

2. **Polynomial Factors:** For the hierarchy $k=1$, derive the explicit form of $P_1(\rho, \log x)$ for a simple zero $\rho$.

3. **Error Term Analysis:** Under GRH, what is the expected size of the error term in $\Psi_f(x)$ for a weight 2 newform?

---

## 🎯 Lecture 4: Advanced Topics and Research Directions

### 4.1 Rankin-Selberg L-Functions

**Definition:** For two modular forms $f$ and $g$:
$$L(s, f \times g) = \sum_{n=1}^{\infty} \frac{a_n b_n}{n^s}$$

**Hierarchy Extension:**
$$\Lambda_{k, f \times g}(p^r) = a_p b_p (\log p)^{k+1} r^k$$

### 4.2 Symmetric Power L-Functions

**Definition:** For a modular form $f$:
$$L(s, \text{Sym}^m f) = \prod_p \det(I - \text{Sym}^m(\rho_p) p^{-s})^{-1}$$

**Research Question:** How do hierarchies behave under symmetric power operations?

### 4.3 Automorphic L-Functions

**General Framework:** For automorphic representations $\pi$ of $GL_n$:
$$L(s, \pi) = \prod_v L_v(s, \pi_v)$$

**Langlands Program Connection:** The von Mangoldt hierarchies provide a computational tool for studying automorphic L-functions.

### 4.4 Computational Aspects

**Numerical Challenges:**
1. Computing Hecke eigenvalues $a_p$ for large primes
2. Locating zeros of L-functions accurately
3. Evaluating truncated explicit formulas

**Algorithms:**
- Modular symbols for computing $a_p$
- Rigorous zero-finding methods
- High-precision arithmetic for explicit formulas

### 4.5 Open Problems and Research Directions

| Area | Problem | Significance |
|------|---------|--------------|
| **Analytic** | Prove GRH for Dirichlet L-functions | Would give optimal error bounds for $\Psi_{\chi}(x)$ |
| **Computational** | Efficient computation of $\Psi_{k,f}(x)$ for large $k$ | Applications to moment calculations |
| **Arithmetic** | Study correlations between different L-function hierarchies | Deep connections to automorphic forms |
| **Statistical** | Distribution of values $\Lambda_{k,f}(n)$ | Random matrix theory predictions |

### 💡 Research Insight
The hierarchies provide a unified framework for studying the fine-scale distribution of primes across different L-functions, with potential applications to the Langlands program.

### 🧠 Exercises (Lecture 4)

1. **Rankin-Selberg:** For the Ramanujan delta function $\Delta$, write the first few terms of $L(s, \Delta \times \Delta)$.

2. **Symmetric Square:** Describe the Euler factors of $L(s, \text{Sym}^2 f)$ for an elliptic modular form $f$.

3. **Research Proposal:** Choose one of the open problems and outline a potential approach to making progress.

---

## 🔬 Laboratory Exercises and Computational Projects

### Project 1: Character L-Function Hierarchies
**Objective:** Compute $\Psi_{k,\chi}(x)$ for various characters and compare with explicit formula predictions.

**Tools:** SageMath, Pari/GP
```python
# Sample code structure
def lambda_k_chi(n, k, chi):
    """Compute Lambda_k for character chi"""
    # Implementation for prime powers
    pass

def psi_k_chi(x, k, chi):
    """Compute partial sum"""
    return sum(lambda_k_chi(n, k, chi) for n in range(1, x+1))
```

### Project 2: Modular Form L-Series
**Objective:** Study the hierarchy structure for small weight modular forms.

**Tasks:**
1. Compute Hecke eigenvalues for forms of weight 2 and level 11
2. Implement $\Lambda_{k,f}$ for $k = 0, 1, 2$
3. Compare numerical values with theoretical predictions

### Project 3: Zero Contributions
**Objective:** Visualize how zeros of L-functions affect the oscillatory terms.

**Approach:**
1. Use known zeros of Dirichlet L-functions
2. Compute truncated zero sums
3. Plot $\Psi_{k,L}(x) - M_{k,L}(x)$ to observe oscillations

---

## 📖 Recommended References

### Core Texts
- **Iwaniec & Kowalski:** *Analytic Number Theory* (Chapters on L-functions)
- **Bump:** *Automorphic Forms and Representations* 
- **Miyake:** *Modular Forms*
- **Davenport:** *Multiplicative Number Theory I*

### Research Papers
- **Hoffstein & Lockhart:** "Coefficients of Maass forms and the Siegel zero"
- **Booker & Strömbergsson:** "Numerical computations with the trace formula"
- **Farmer:** "Long mollifiers of the Riemann zeta-function"

### Computational Resources
- **SageMath:** Modular forms database and L-function computations
- **LMFDB:** L-functions and Modular Forms Database
- **Pari/GP:** High-precision arithmetic and number theory functions

---

## 🎯 Assessment and Evaluation

### Problem Sets (40%)
- Weekly exercises covering theory and computation
- Mix of proof-based and numerical problems

### Computational Project (30%)
- Choose one of the laboratory projects
- Submit code, numerical results, and analysis

### Research Presentation (20%)
- 20-minute presentation on current research in the area
- Could focus on recent papers or open problems

### Final Exam (10%)
- Theoretical questions on key concepts
- Short computational exercises

---

## 🔮 Advanced Topics for Independent Study

### Galois Representations
- Connection between L-functions and Galois representations
- How hierarchies reflect Galois-theoretic structure

### Special Values
- Critical values of L-functions and their arithmetic significance
- BSD conjecture and its computational verification

### Random Matrix Theory
- Moment calculations and their connection to random matrix ensembles
- Statistical properties of zero spacings

### Langlands Correspondence
- Functoriality and its impact on L-function hierarchies
- Automorphic representations and their L-functions

---

## 💭 Pedagogical Notes

### Key Conceptual Hurdles
1. **Abstract vs. Concrete:** Students often struggle with the abstract definition of L-functions. Use specific examples (quadratic characters, small level modular forms) early and often.

2. **Analytic Continuation:** The passage from convergent Dirichlet series to meromorphic functions is subtle. Emphasize the role of functional equations.

3. **Computational Complexity:** Modern L-function computations require sophisticated algorithms. Balance theoretical understanding with practical limitations.

### Teaching Strategies
- **Start Concrete:** Begin each topic with explicit examples before generalizing
- **Visual Aids:** Use plots of L-functions and their zeros to build intuition
- **Connect to Known Results:** Relate new concepts to familiar objects like $\zeta(s)$
- **Encourage Computation:** Have students implement basic algorithms to develop understanding

### Common Misconceptions
- **"All L-functions have Euler products":** True only for nice cases; bad primes require care
- **"Zeros determine everything":** Poles and residues also carry important arithmetic information
- **"GRH implies everything":** Many results require additional hypotheses beyond GRH
