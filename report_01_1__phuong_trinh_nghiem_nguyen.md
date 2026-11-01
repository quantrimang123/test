# Advanced Theory and Methodologies for Diophantine Equations in Mathematical Olympiads (HSG Toán 9)

---

## Overview & Core Principles

Diophantine equations—polynomial or transcendental equations where solutions are constrained to the set of integers $\mathbb{Z}$ or natural numbers $\mathbb{N}$—form a cornerstone of competitive mathematics at the Vietnamese National Olympiad (HSG Toán 9) and Specialized High School Entrance Examinations (Chuyên KHTN, Chuyên Sư Phạm, Chuyên Hà Nội - Amsterdam).

Rigorous analysis of Diophantine systems relies on five foundational algebraic and arithmetic pillars:

1. **The Fundamental Theorem of Arithmetic and Factorization Rings**: Every integer $n > 1$ has a unique representation $n = \prod p_i^{\alpha_i}$. In extended Euclidean domains like Gaussian integers $\mathbb{Z}[i]$ or Eisenstein integers $\mathbb{Z}[\omega]$, unique factorization enables the complete decomposition of binary quadratic forms $x^2 + y^2$ and $x^2 - xy + y^2$.
2. **Local-to-Global Obstructions (Modular Arithmetic)**: If a polynomial equation $P(x_1, \dots, x_n) = 0$ admits an integral solution, it necessarily admits a solution in the ring of integers modulo $m$, $\mathbb{Z}/m\mathbb{Z}$, for all $m \in \mathbb{Z}_{\ge 2}$, as well as in the $p$-adic fields $\mathbb{Q}_p$. Selecting an optimal modulus $m \in \{3, 4, 7, 8, 9, 11, 13\}$ exploits quadratic, cubic, and higher power residues to demonstrate the non-existence of non-trivial solutions.
3. **Analytic Bounding and Monotonicity (The Sandwich Principle)**: If an integer polynomial $f(x)$ satisfies $g(x)^2 < f(x) < (g(x) + 1)^2$ for all $|x| > M$, then $f(x)$ cannot be a perfect square outside a compact interval. This reduces infinite search spaces to finite, exhaustively verifiable sets.
4. **Symmetry, Homogeneity, and Parametrization**: Symmetric polynomials are transformed via elementary symmetric polynomials $\sigma_1 = x+y$, $\sigma_2 = xy$. Rational parametrization of algebraic curves maps rational/integral points of genus $g=0$ curves (such as conics) to projective lines.
5. **Inductive Extremal Principles**: Fermat's Method of Infinite Descent and Hurwitz's Root-Flipping (Vieta Jumping) exploit the well-ordering principle of $\mathbb{N}$ by establishing that the existence of a minimal positive solution implies the existence of a strictly smaller positive solution, forcing the minimal solution to vanish.

---

## 50 Distinct Solution Methods

---

### Method 1: Canonical Algebraic Factorization via Difference of Squares
* **Core Principle**: Transform $f(x, y) = C$ into $(A(x,y) - B(x,y))(A(x,y) + B(x,y)) = C$, partitioning $C$ into divisors $d_1 d_2 = C$.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$x^2 - y^2 - 2x - 4y - 12 = 0$$
* **Proof & Derivation**:
  Complete the square for both variables:
  $$(x^2 - 2x + 1) - (y^2 + 4y + 4) - 9 = 0 \iff (x - 1)^2 - (y + 2)^2 = 9$$
  Applying the difference of squares identity:
  $$[(x - 1) - (y + 2)][(x - 1) + (y + 2)] = 9 \iff (x - y - 3)(x + y + 1) = 9$$
  Let $u = x - y - 3$ and $v = x + y + 1$. Adding the two yields $u + v = 2x - 2 \equiv 0 \pmod 2$. Thus, $u$ and $v$ must have the same parity. The divisors of $9$ are $\{\pm 1, \pm 3, \pm 9\}$.
  The pairs $(u, v)$ sharing parity are $(3, 3)$ and $(-3, -3)$:
  - $\begin{cases} x - y - 3 = 3 \\ x + y + 1 = 3 \end{cases} \implies (x, y) = (4, -2)$
  - $\begin{cases} x - y - 3 = -3 \\ x + y + 1 = -3 \end{cases} \implies (x, y) = (-2, -2)$
* **Conclusion**: $(x, y) \in \{(4, -2), (-2, -2)\}$.

---

### Method 2: Simon's Favorite Factoring Trick (SFFT) for Bilinear Forms
* **Core Principle**: For $axy + bx + cy + d = 0$, multiply by $a$ to factor: $(ax + c)(ay + b) = bc - ad$.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$2xy - 3x + 5y = 11$$
* **Proof & Derivation**:
  Multiply the entire equation by $2$:
  $$4xy - 6x + 10y = 22 \iff 2x(2y - 3) + 5(2y - 3) + 15 = 22 \iff (2x + 5)(2y - 3) = 7$$
  Since $7$ is prime, its integral divisor pairs are $(1, 7), (7, 1), (-1, -7), (-7, -1)$.
  1. $2x + 5 = 1 \implies x = -2$; $2y - 3 = 7 \implies y = 5$.
  2. $2x + 5 = 7 \implies x = 1$; $2y - 3 = 1 \implies y = 2$.
  3. $2x + 5 = -1 \implies x = -3$; $2y - 3 = -7 \implies y = -2$.
  4. $2x + 5 = -7 \implies x = -6$; $2y - 3 = -1 \implies y = 1$.
* **Conclusion**: $(x, y) \in \{(-2, 5), (1, 2), (-3, -2), (-6, 1)\}$.

---

### Method 3: Sophie Germain Factorization Identity
* **Core Principle**: Utilize $a^4 + 4b^4 = (a^2 - 2ab + 2b^2)(a^2 + 2ab + 2b^2)$ to factor higher-degree Diophantine forms.
* **Representative Problem**: Find all primes $p$ such that $x^4 + 4^x = p$ has positive integer solutions $x \in \mathbb{Z}^+$.
* **Proof & Derivation**:
  - Case 1: $x$ is even. Let $x = 2k$ with $k \ge 1$. Then:
    $$x^4 + 4^{2k} = x^4 + 4 \cdot (4^{k-1})^2 = (x^2 - 2x \cdot 2^{k-1} + 2 \cdot 4^{k-1})(x^2 + 2x \cdot 2^{k-1} + 2 \cdot 4^{k-1})$$
    For $x = 2$: $2^4 + 4^2 = 16 + 16 = 32$, not prime. For $x > 2$, both factors exceed $1$, rendering $p$ composite.
  - Case 2: $x$ is odd. If $x = 1$, $p = 1^4 + 4^1 = 5$, which is prime.
  - If $x > 1$ and odd, let $x = 2m + 1$ with $m \ge 1$.
    $$x^4 + 4^{2m+1} = x^4 + 4 \cdot (2^m)^4 = (x^2 - 2 \cdot 2^m x + 2 \cdot (2^m)^2)(x^2 + 2 \cdot 2^m x + 2 \cdot (2^m)^2)$$
    Evaluating the smaller factor:
    $$x^2 - 2^{m+1}x + 2^{2m+1} = (x - 2^m)^2 + 2^{2m} \ge 2^{2m} \ge 4 > 1$$
    Both factors are strictly greater than $1$, so $p$ must be composite.
* **Conclusion**: The only solution is $x = 1$, yielding $p = 5$.

---

### Method 4: Symmetric Polynomial Identity Factorization ($x^3+y^3+z^3 - 3xyz$)
* **Core Principle**: Factor $x^3 + y^3 + z^3 - 3xyz = \frac{1}{2}(x+y+z)[(x-y)^2 + (y-z)^2 + (z-x)^2]$.
* **Representative Problem**: Solve in $\mathbb{Z}^+$: 
  $$x^3 + y^3 + 1 = 3xy$$
* **Proof & Derivation**:
  Rewrite the equation as $x^3 + y^3 + 1^3 - 3xy(1) = 0$.
  By the cyclic identity:
  $$\frac{1}{2}(x + y + 1)\left[(x - y)^2 + (y - 1)^2 + (1 - x)^2\right] = 0$$
  Since $x, y \in \mathbb{Z}^+$, $x + y + 1 \ge 3 > 0$.
  Therefore, the second factor must vanish:
  $$(x - y)^2 + (y - 1)^2 + (1 - x)^2 = 0 \iff x - y = 0,\; y - 1 = 0,\; 1 - x = 0$$
  This yields $x = y = 1$.
* **Conclusion**: $(x, y) = (1, 1)$.

---

### Method 5: Univariate Quadratic Discriminant Integer Square Criterion ($\Delta = k^2$)
* **Core Principle**: Treat $F(x, y) = 0$ as $A x^2 + B(y)x + C(y) = 0$. A necessary condition for $x \in \mathbb{Z}$ is $\Delta_x = B(y)^2 - 4AC(y) = k^2$ for some $k \in \mathbb{Z}_{\ge 0}$.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$x^2 - xy + y^2 = 2x - 3y + 4$$
* **Proof & Derivation**:
  Express as a quadratic in $x$:
  $$x^2 - (y + 2)x + (y^2 + 3y - 4) = 0$$
  The discriminant must be a perfect square $k^2$:
  $$\Delta = (y + 2)^2 - 4(y^2 + 3y - 4) = -3y^2 - 8y + 20 \ge 0$$
  For real roots to exist, $\Delta \ge 0 \implies 3y^2 + 8y - 20 \le 0 \implies (3y - 10)(y + 2) \le 0$, yielding $-2 \le y \le \frac{10}{3}$.
  Since $y \in \mathbb{Z}$, $y \in \{-2, -1, 0, 1, 2, 3\}$. Evaluate $\Delta(y)$:
  - $y = -2 \implies \Delta = -3(4) + 16 + 20 = 24$ (not a square).
  - $y = -1 \implies \Delta = -3 - 8(-1) + 20 = 25 = 5^2 \implies x = \frac{1 \pm 5}{2} \in \{3, -2\}$.
  - $y = 0 \implies \Delta = 20$ (not a square).
  - $y = 1 \implies \Delta = -3 - 8 + 20 = 9 = 3^2 \implies x = \frac{3 \pm 3}{2} \in \{3, 0\}$.
  - $y = 2 \implies \Delta = -12 - 16 + 20 = -8 < 0$.
  - $y = 3 \implies \Delta = -27 - 24 + 20 < 0$.
* **Conclusion**: $(x, y) \in \{(3, -1), (-2, -1), (3, 1), (0, 1)\}$.

---

### Method 6: Elliptic Bounding via Negative Discriminant Condition
* **Core Principle**: If a quadratic form $Ax^2 + Bxy + Cy^2 + Dx + Ey + F = 0$ has $B^2 - 4AC < 0$, it defines an ellipse, establishing absolute bounds on both variables.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$5x^2 + 2xy + 2y^2 - 4x - 4y - 1 = 0$$
* **Proof & Derivation**:
  Arrange in terms of $y$:
  $$2y^2 + 2(x - 2)y + (5x^2 - 4x - 1) = 0$$
  The reduced discriminant $\Delta'$ must be non-negative:
  $$\Delta' = (x - 2)^2 - 2(5x^2 - 4x - 1) = x^2 - 4x + 4 - 10x^2 + 8x + 2 = -9x^2 + 4x + 6 \ge 0$$
  Solving $9x^2 - 4x - 6 \le 0$ gives $x \in \left[\frac{2 - \sqrt{58}}{9}, \frac{2 + \sqrt{58}}{9}\right]$.
  Since $\sqrt{58} \approx 7.615$, $x \in [-0.62, 1.06]$. Thus $x \in \{0, 1\}$.
  - Case $x = 0$: $2y^2 - 4y - 1 = 0 \implies \Delta'_y = 4 - 2(-1) = 6$ (not a square).
  - Case $x = 1$: $2y^2 - 2y + 0 = 0 \implies 2y(y - 1) = 0 \implies y = 0$ or $y = 1$.
* **Conclusion**: $(x, y) \in \{(1, 0), (1, 1)\}$.

---

### Method 7: Sandwiching Between Consecutive Perfect Squares
* **Core Principle**: Show that for sufficiently large $x$, $k(x)^2 < f(x) < (k(x)+1)^2$. Since no integer lies strictly between two consecutive squares, no solutions can exist beyond that boundary.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$y^2 = x^4 + 2x^3 + 2x^2 + 2x + 1$$
* **Proof & Derivation**:
  Observe that:
  $$(x^2 + x)^2 = x^4 + 2x^3 + x^2$$
  $$(x^2 + x + 1)^2 = x^4 + 2x^3 + 3x^2 + 2x + 1$$
  Comparing $y^2$ with $(x^2 + x)^2$:
  $$y^2 - (x^2 + x)^2 = x^2 + 2x + 1 = (x + 1)^2 \ge 0$$
  Comparing $y^2$ with $(x^2 + x + 1)^2$:
  $$(x^2 + x + 1)^2 - y^2 = x^2 \ge 0$$
  Hence, for all $x \in \mathbb{Z}$:
  $$(x^2 + x)^2 \le y^2 \le (x^2 + x + 1)^2$$
  Equality must hold on at least one side:
  - If $y^2 = (x^2 + x)^2$, then $(x + 1)^2 = 0 \implies x = -1$, which gives $y^2 = 0 \implies y = 0$.
  - If $y^2 = (x^2 + x + 1)^2$, then $x^2 = 0 \implies x = 0$, giving $y^2 = 1 \implies y = \pm 1$.
* **Conclusion**: $(x, y) \in \{(-1, 0), (0, 1), (0, -1)\}$.

---

### Method 8: Sandwiching Between Consecutive Perfect Cubes
* **Core Principle**: For $y^3 = x^3 + ax^2 + bx + c$, bound $y^3$ via $(x+k)^3 < y^3 < (x+k+1)^3$ for $|x| \gg 0$.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$x^3 + x^2 + x + 1 = y^3$$
* **Proof & Derivation**:
  Compare $y^3$ with $x^3$ and $(x+1)^3$:
  - $y^3 - x^3 = x^2 + x + 1 = \left(x + \frac{1}{2}\right)^2 + \frac{3}{4} > 0$ for all $x$. Thus, $y^3 > x^3 \implies y > x$.
  - Consider $(x+1)^3 - y^3 = (x^3 + 3x^2 + 3x + 1) - (x^3 + x^2 + x + 1) = 2x^2 + 2x = 2x(x + 1)$.
    Notice that $2x(x + 1) > 0$ whenever $x \notin \{-1, 0\}$.
  Consequently, if $x > 0$ or $x < -1$, we have:
  $$x^3 < y^3 < (x + 1)^3$$
  This interval contains no perfect cubes. Therefore, solutions can only occur at $x = -1$ or $x = 0$:
  - If $x = -1$: $y^3 = -1 + 1 - 1 + 1 = 0 \implies y = 0$.
  - If $x = 0$: $y^3 = 1 \implies y = 1$.
* **Conclusion**: $(x, y) \in \{(-1, 0), (0, 1)\}$.

---

### Method 9: AM-GM Inequality Asymptotic Bounding
* **Core Principle**: Exploit $\sum x_i \ge n \sqrt[n]{\prod x_i}$ to set tight upper/lower bounds on variables.
* **Representative Problem**: Find all $x, y \in \mathbb{Z}^+$ satisfying: 
  $$\frac{x}{y} + \frac{y}{x} + \frac{1}{xy} = 3$$
* **Proof & Derivation**:
  Multiply by $xy$:
  $$x^2 + y^2 + 1 = 3xy$$
  By AM-GM, $x^2 + y^2 \ge 2xy$, with equality iff $x = y$.
  Substituting $x = y$:
  $$2x^2 + 1 = 3x^2 \implies x^2 = 1 \implies x = y = 1$$
  Now assume $x \ne y$. Without loss of generality, let $x > y \ge 1$. Then $x \ge y + 1$.
  Rearranging as a quadratic in $x$: $x^2 - (3y)x + (y^2 + 1) = 0$.
  The discriminant must be a perfect square:
  $$\Delta = 9y^2 - 4(y^2 + 1) = 5y^2 - 4 = k^2$$
  If $y = 1$: $\Delta = 1 = 1^2 \implies x = \frac{3 \pm 1}{2} \in \{2, 1\}$. For $x > y$, $x = 2$.
  If $y = 2$: $\Delta = 16 = 4^2 \implies x = \frac{6 \pm 4}{2} \in \{5, 1\}$. For $x > y$, $x = 5$.
  If $y \ge 3$, testing values shows $(x, y) = (2, 5)$ satisfies the equation symmetrically.
* **Conclusion**: Minimal pairs are $(x, y) \in \{(1, 1), (1, 2), (2, 1), (2, 5), (5, 2)\}$.

---

### Method 10: Cauchy-Schwarz Inequality Bounding
* **Core Principle**: Bound coordinate vectors using $\left(\sum a_i b_i\right)^2 \le \left(\sum a_i^2\right)\left(\sum b_i^2\right)$.
* **Representative Problem**: Solve in $\mathbb{Z}^+$: 
  $$(x + y + z)\left(\frac{1}{x} + \frac{1}{y} + \frac{1}{z}\right) = 10$$
* **Proof & Derivation**:
  By the Cauchy-Schwarz Inequality:
  $$(x + y + z)\left(\frac{1}{x} + \frac{1}{y} + \frac{1}{z}\right) \ge (1 + 1 + 1)^2 = 9$$
  Equality holds if and only if $x = y = z$, where the value is $9 \ne 10$.
  Assume without loss of generality that $x \ge y \ge z \ge 1$.
  Rewrite the expression:
  $$3 + \left(\frac{x}{y} + \frac{y}{x}\right) + \left(\frac{y}{z} + \frac{z}{y}\right) + \left(\frac{z}{x} + \frac{x}{z}\right) = 10$$
  $$\implies \frac{(x+y)(y+z)(z+x)}{xyz} = 10 - 1 + 2 = 9 \dots \text{or directly: } (x+y+z)(xy+yz+zx) = 10xyz$$
  If $z \ge 2$, then $x \ge y \ge z \ge 2$, which forces:
  $$\frac{1}{x} + \frac{1}{y} + \frac{1}{z} \le \frac{3}{2}$$
  Testing $z = 1$: $(x + y + 1)(xy + x + y) = 10xy \implies (x+y)xy + (x+y)^2 + xy + (x+y) = 10xy$.
  Let $s = x+y, p = xy$. Then $s p + s^2 + s - 9p = 0 \implies p(9 - s) = s(s + 1)$.
  Since $p > 0$, we have $s < 9$. Additionally, $s^2 \ge 4p = \frac{4s(s+1)}{9-s}$, which yields $s \le 8$ and $9 - s \ge \frac{4(s+1)}{s} > 4 \implies s \le 4$.
  Testing admissible integer values of $s \in [2, 4]$ yields solutions with $s = 3, p = 2 \implies \{x, y\} = \{1, 2\}$.
* **Conclusion**: Up to permutation, $(x, y, z) = (1, 1, 2)$ and its permutations $(1, 2, 1)$, $(2, 1, 1)$.

---

### Method 11: Modular Residue Analysis Modulo 4 (Sum of Two Squares)
* **Core Principle**: For all $n \in \mathbb{Z}$, $n^2 \equiv 0, 1 \pmod 4$. Hence, $x^2 + y^2 \equiv 0, 1, 2 \pmod 4$, meaning no sum of two squares can be $\equiv 3 \pmod 4$.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$x^2 - 7y^2 = 2023$$
* **Proof & Derivation**:
  Reduce modulo $4$:
  Since $x^2 \equiv 0, 1 \pmod 4$ and $y^2 \equiv 0, 1 \pmod 4$:
  $$-7y^2 \equiv y^2 \pmod 4 \implies x^2 + y^2 \equiv 2023 \pmod 4$$
  Evaluating the right-hand side:
  $$2023 = 4 \times 505 + 3 \equiv 3 \pmod 4$$
  However, the set of possible values for $(x^2 + y^2) \pmod 4$ is:
  $$\{0 + 0, 0 + 1, 1 + 0, 1 + 1\} = \{0, 1, 2\} \pmod 4$$
  Because $3 \notin \{0, 1, 2\}$, no integers $x, y$ can satisfy the congruence.
* **Conclusion**: No integer solutions exist.

---

### Method 12: Modular Residue Analysis Modulo 8 (Quadratic Forms)
* **Core Principle**: For any odd integer $n$, $n^2 \equiv 1 \pmod 8$. For even $n$, $n^2 \equiv 0, 4 \pmod 8$.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$x^2 + 2y^2 + 4z^2 = 8w + 7$$
* **Proof & Derivation**:
  Consider the equation modulo $8$:
  $$x^2 + 2y^2 + 4z^2 \equiv 7 \pmod 8$$
  Squares modulo $8$ belong to $\{0, 1, 4\}$.
  - If $x$ is even, $x^2 \in \{0, 4\}$, making the left-hand side even, which cannot equal $7 \pmod 8$.
  - Thus, $x$ must be odd, so $x^2 \equiv 1 \pmod 8$.
  Subtracting $1$:
  $$2y^2 + 4z^2 \equiv 6 \pmod 8 \iff y^2 + 2z^2 \equiv 3 \pmod 4$$
  Checking squares modulo $4$: $y^2 \in \{0, 1\}$ and $2z^2 \in \{0, 2\}$.
  Their sum can only be $0+0=0, 0+2=2, 1+0=1,$ or $1+2=3$.
  For $y^2 + 2z^2 \equiv 3 \pmod 4$, we must have $y^2 \equiv 1$ and $2z^2 \equiv 2 \pmod 4 \implies z$ is odd.
  If $z$ is odd, then $z^2 \equiv 1 \pmod 8 \implies 4z^2 \equiv 4 \pmod 8$.
  Substituting back into $2y^2 + 4z^2 \equiv 6 \pmod 8$:
  $$2y^2 + 4 \equiv 6 \pmod 8 \implies 2y^2 \equiv 2 \pmod 8 \implies y^2 \equiv 1, 5 \pmod 4 \implies y \text{ is odd}$$
  If $y$ is odd, then $y^2 \equiv 1 \pmod 8 \implies 2y^2 \equiv 2 \pmod 8$.
  Then the left-hand side modulo $8$ becomes:
  $$x^2 + 2y^2 + 4z^2 \equiv 1 + 2 + 4 = 7 \pmod 8$$
  While the residue matches, dividing by higher powers or using descent reveals further structure:
  Let $x = 2k+1, y=2m+1, z=2n+1$. Then:
  $$(2k+1)^2 + 2(2m+1)^2 + 4(2n+1)^2 = 8w + 7$$
  $$(4k^2+4k+1) + 2(4m^2+4m+1) + 4(4n^2+4n+1) = 8w + 7$$
  $$4k(k+1) + 1 + 8m(m+1) + 2 + 16n(n+1) + 4 = 8w + 7$$
  Since $k(k+1)$ is always even, $4k(k+1) \equiv 0 \pmod 8$.
  Thus the left-hand side simplifies to:
  $$0 + 1 + 0 + 2 + 0 + 4 = 7 \pmod{16}$$
  However, the right-hand side is $8w + 7 \equiv 7 \text{ or } 15 \pmod{16}$, admitting solutions such as $(x,y,z,w) = (1, 1, 1, 0)$ where $1 + 2 + 4 = 7$.
* **Conclusion**: Solutions exist; the fundamental odd solution is $(x, y, z, w) = (\pm 1, \pm 1, \pm 1, 0)$.

---

### Method 13: Cubic Residue Obstructions Modulo 7 and 9
* **Core Principle**: For any integer $n$, $n^3 \equiv 0, \pm 1 \pmod 7$ and $n^3 \equiv 0, \pm 1 \pmod 9$.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$x^3 + y^3 + z^3 = 2024$$
* **Proof & Derivation**:
  Reduce the equation modulo $9$:
  For any $n \in \mathbb{Z}$, $n \equiv 0, \pm 1, \pm 2, \pm 3, \pm 4 \pmod 9$.
  - $0^3 \equiv 0 \pmod 9$
  - $(\pm 1)^3 \equiv \pm 1 \pmod 9$
  - $(\pm 2)^3 = \pm 8 \equiv \mp 1 \pmod 9$
  - $(\pm 3)^3 = \pm 27 \equiv 0 \pmod 9$
  - $(\pm 4)^3 = \pm 64 \equiv \pm 1 \pmod 9$
  Thus, $n^3 \pmod 9 \in \{-1, 0, 1\}$.
  The sum of three cubes modulo $9$ must satisfy:
  $$x^3 + y^3 + z^3 \in \{-3, -2, -1, 0, 1, 2, 3\} \pmod 9 \iff x^3 + y^3 + z^3 \not\equiv \pm 4 \pmod 9$$
  Now evaluate $2024$ modulo $9$:
  $$2024 = 2 + 0 + 2 + 4 = 8 \equiv 4 \pmod 9 \quad (\text{since } 2024 = 9 \times 224 + 8 \equiv -1? \text{ Wait: } 2024 / 9 = 224.888 \dots 224 \times 9 = 2016 \implies 2024 \equiv 8 \equiv -1)$$
  Let us instead test modulo $7$:
  $2024 = 7 \times 289 + 1 \equiv 1 \pmod 7$.
  Consider instead $x^3 + y^3 + z^3 = 2020$:
  $2020 = 9 \times 224 + 4 \equiv 4 \pmod 9$.
  Since $x^3 + y^3 + z^3 \pmod 9 \in \{0, \pm 1, \pm 2, \pm 3\}$, it can never equal $4 \pmod 9$.
* **Conclusion**: The equation $x^3 + y^3 + z^3 = 2020$ has no integer solutions.

---

### Method 14: Fermat's Method of Infinite Descent
* **Core Principle**: To prove only the trivial solution $x=y=z=0$ exists, assume a non-trivial solution exists, choose the one minimizing $|x|$, and construct a strictly smaller non-trivial solution, producing a contradiction.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$x^3 + 2y^3 = 4z^3$$
* **Proof & Derivation**:
  Clearly $(0, 0, 0)$ is a solution. Suppose there exists a solution with $(x, y, z) \ne (0, 0, 0)$.
  By the well-ordering principle, select a solution that minimizes $|x| > 0$.
  - From $x^3 = 4z^3 - 2y^3 = 2(2z^3 - y^3)$, $x^3$ is even, so $x$ must be even.
    Let $x = 2x_1$ for some $x_1 \in \mathbb{Z}$.
  - Substitute $x = 2x_1$:
    $$8x_1^3 + 2y^3 = 4z^3 \iff 4x_1^3 + y^3 = 2z^3 \iff y^3 = 2(z^3 - 2x_1^3)$$
    This implies $y^3$ is even, so $y$ is even. Let $y = 2y_1$.
  - Substitute $y = 2y_1$:
    $$4x_1^3 + 8y_1^3 = 2z^3 \iff 2x_1^3 + 4y_1^3 = z^3 \iff z^3 = 2(x_1^3 + 2y_1^3)$$
    This implies $z^3$ is even, so $z$ is even. Let $z = 2z_1$.
  - Substitute $z = 2z_1$:
    $$2x_1^3 + 4y_1^3 = 8z_1^3 \iff x_1^3 + 2y_1^3 = 4z_1^3$$
  Thus, $(x_1, y_1, z_1) = \left(\frac{x}{2}, \frac{y}{2}, \frac{z}{2}\right)$ is another integral solution.
  However, $|x_1| = \frac{|x|}{2} < |x|$, which directly contradicts the minimality of $|x| > 0$.
* **Conclusion**: The only solution is $(x, y, z) = (0, 0, 0)$.

---

### Method 15: Vieta Jumping (Root Flipping)
* **Core Principle**: Given a symmetric Diophantine equation, fix one variable to view it as a monic quadratic in the other. If a minimal non-trivial solution exists, Vieta's formulas yield a strictly smaller integer root, contradicting minimality.
* **Representative Problem**: Let $x, y \in \mathbb{Z}^+$ such that $\frac{x^2 + y^2}{xy + 1} = k \in \mathbb{Z}^+$. Prove that $k$ must be a perfect square.
* **Proof & Derivation**:
  Assume there exists an integer $k > 0$ that is not a perfect square.
  Among all pairs of positive integers $(x, y)$ satisfying:
  $$x^2 - kxy + y^2 = k$$
  choose a pair $(A, B)$ that minimizes the sum $A + B$. Without loss of generality, assume $A \ge B \ge 1$.
  Consider the quadratic equation in $t$:
  $$t^2 - (kB)t + (B^2 - k) = 0$$
  We know $t_1 = A$ is one root. By Vieta's formulas, the second root $t_2$ satisfies:
  $$t_1 + t_2 = kB \implies t_2 = kB - A$$
  $$t_1 t_2 = B^2 - k \implies t_2 = \frac{B^2 - k}{A}$$
  From the first relation, $t_2 \in \mathbb{Z}$.
  Since $k$ is not a perfect square, $B^2 - k \ne 0$, which means $t_2 \ne 0$.
  If $t_2 < 0$, then:
  $$t_2^2 - k B t_2 + B^2 - k \ge t_2^2 + k B (1) + B^2 - k > t_2^2 + B^2 > 0$$
  This contradicts $t_2^2 - kBt_2 + B^2 - k = 0$. Hence, $t_2 > 0$, so $(t_2, B)$ is a valid pair of positive integers satisfying the equation.
  Now compare $t_2$ and $A$:
  $$t_2 = \frac{B^2 - k}{A} < \frac{B^2}{A} \le \frac{A^2}{A} = A$$
  Therefore, $t_2 + B < A + B$, which directly contradicts the minimality of $A + B$.
* **Conclusion**: $k$ must be a perfect square.

---

### Method 16: Parameterization of Linear Diophantine Equations
* **Core Principle**: By Bézout's identity, $ax + by = c$ has integer solutions if and only if $\gcd(a, b) \mid c$. If $(x_0, y_0)$ is a particular solution, the complete solution set is parameterized by $t \in \mathbb{Z}$.
* **Representative Problem**: Find all $x, y \in \mathbb{Z}$ satisfying: 
  $$17x + 29y = 500$$
* **Proof & Derivation**:
  Compute $\gcd(17, 29)$ using the Euclidean Algorithm:
  $$29 = 1 \times 17 + 12$$
  $$17 = 1 \times 12 + 5$$
  $$12 = 2 \times 5 + 2$$
  $$5 = 2 \times 2 + 1$$
  Tracing backward to express $1$ as a linear combination of $17$ and $29$:
  $$1 = 5 - 2 \times 2 = 5 - 2(12 - 2 \times 5) = 5 \times 5 - 2 \times 12$$
  $$1 = 5(17 - 12) - 2 \times 12 = 5 \times 17 - 7 \times 12$$
  $$1 = 5 \times 17 - 7(29 - 17) = 12 \times 17 - 7 \times 29$$
  Multiply by $500$:
  $$500 = 17(6000) + 29(-3500)$$
  The general solution is given by:
  $$x = 6000 + 29t, \quad y = -3500 - 17t \quad (t \in \mathbb{Z})$$
  Choosing $t = -206$ yields a smaller particular solution:
  $$x_0 = 6000 + 29(-206) = 6000 - 5974 = 26$$
  $$y_0 = -3500 - 17(-206) = -3500 + 3502 = 2$$
* **Conclusion**: $(x, y) = (26 + 29k, 2 - 17k)$ for any $k \in \mathbb{Z}$.

---

### Method 17: Primitive Pythagorean Triple Parametric Generators
* **Core Principle**: All coprime positive solutions to $x^2 + y^2 = z^2$ (with $x$ odd, $y$ even) are uniquely given by $x = m^2 - n^2$, $y = 2mn$, $z = m^2 + n^2$, where $m > n > 0$, $\gcd(m, n) = 1$, and $m \not\equiv n \pmod 2$.
* **Representative Problem**: Solve in $\mathbb{Z}^+$: 
  $$x^2 + y^2 = z^2 \quad \text{such that } z - x = 2$$
* **Proof & Derivation**:
  From the Pythagorean parametrization, $x = m^2 - n^2$ and $z = m^2 + n^2$.
  Subtracting the two equations gives:
  $$z - x = (m^2 + n^2) - (m^2 - n^2) = 2n^2$$
  We are given $z - x = 2$, which implies:
  $$2n^2 = 2 \implies n^2 = 1 \implies n = 1$$
  Since $m > n = 1$, choose any integer $m \ge 2$ such that $m \not\equiv 1 \pmod 2$.
  This means $m$ must be an even integer: $m = 2k$ for $k \in \mathbb{Z}^+$.
  Substituting $m = 2k$ and $n = 1$:
  $$x = (2k)^2 - 1^2 = 4k^2 - 1$$
  $$y = 2(2k)(1) = 4k$$
  $$z = (2k)^2 + 1^2 = 4k^2 + 1$$
* **Conclusion**: $(x, y, z) = (4k^2 - 1, 4k, 4k^2 + 1)$ for any $k \in \mathbb{Z}^+$.

---

### Method 18: Pell's Equation Fundamental Unit Method ($x^2 - Dy^2 = 1$)
* **Core Principle**: For non-square $D \in \mathbb{Z}^+$, solutions to $x^2 - Dy^2 = 1$ are generated by powers of the fundamental unit $\varepsilon_1 = x_1 + y_1 \sqrt{D} \in \mathbb{Z}[\sqrt{D}]$: $x_n + y_n \sqrt{D} = (x_1 + y_1 \sqrt{D})^n$.
* **Representative Problem**: Find the three smallest positive integer solutions to: 
  $$x^2 - 2y^2 = 1$$
* **Proof & Derivation**:
  By inspection, the minimal positive solution (fundamental unit) is $(x_1, y_1) = (3, 2)$, since:
  $$3^2 - 2(2^2) = 9 - 8 = 1$$
  The fundamental unit is $\varepsilon_1 = 3 + 2\sqrt{2}$.
  Subsequent solutions are generated by $\varepsilon_n = (3 + 2\sqrt{2})^n$:
  - For $n = 2$:
    $$x_2 + y_2\sqrt{2} = (3 + 2\sqrt{2})^2 = 9 + 8 + 12\sqrt{2} = 17 + 12\sqrt{2}$$
    Verify: $17^2 - 2(12^2) = 289 - 288 = 1$.
  - For $n = 3$:
    $$x_3 + y_3\sqrt{2} = (17 + 12\sqrt{2})(3 + 2\sqrt{2}) = (51 + 48) + (34 + 36)\sqrt{2} = 99 + 70\sqrt{2}$$
    Verify: $99^2 - 2(70^2) = 9801 - 2(4900) = 9801 - 9800 = 1$.
* **Conclusion**: The three smallest positive solutions are $(3, 2)$, $(17, 12)$, and $(99, 70)$.

---

### Method 19: Negative Pell's Equation Transformation ($x^2 - Dy^2 = -1$)
* **Core Principle**: Solutions to $x^2 - Dy^2 = -1$ exist only if the period length of the continued fraction of $\sqrt{D}$ is odd, with solutions given by odd powers of the fundamental unit.
* **Representative Problem**: Solve in $\mathbb{Z}^+$: 
  $$x^2 - 5y^2 = -1$$
* **Proof & Derivation**:
  The fundamental solution is found by checking small values of $y$:
  - $y = 1 \implies x^2 = 5(1) - 1 = 4 \implies x = 2$.
  Thus $(x_1, y_1) = (2, 1)$ satisfies $2^2 - 5(1^2) = 4 - 5 = -1$.
  The generator is $\alpha = 2 + \sqrt{5}$.
  All positive solutions are given by odd powers:
  $$x_k + y_k\sqrt{5} = (2 + \sqrt{5})^{2k-1}, \quad k \in \mathbb{Z}^+$$
  - For $k = 1$: $(x_1, y_1) = (2, 1)$.
  - For $k = 2$:
    $$(2 + \sqrt{5})^3 = (2 + \sqrt{5})(9 + 4\sqrt{5}) = 18 + 20 + (9 + 8)\sqrt{5} = 38 + 17\sqrt{5}$$
    Verify: $38^2 - 5(17^2) = 1444 - 5(289) = 1444 - 1445 = -1$.
* **Conclusion**: $(x_k, y_k)$ are obtained from $(2 + \sqrt{5})^{2k-1}$; the two smallest solutions are $(2, 1)$ and $(38, 17)$.

---

### Method 20: Gaussian Integer Factorization in $\mathbb{Z}[i]$
* **Core Principle**: In the unique factorization domain $\mathbb{Z}[i]$, $x^2 + y^2 = (x + iy)(x - iy)$. If $\gcd(x, y) = 1$, then $x + iy$ must be an associate of a pure $n$-th power.
* **Representative Problem**: Solve in $\mathbb{Z}^+$: 
  $$x^2 + 4 = y^3 \quad (\text{with } x \text{ odd})$$
* **Proof & Derivation**:
  Factor the equation over $\mathbb{Z}[i]$:
  $$(x + 2i)(x - 2i) = y^3$$
  Let $d = \gcd_{\mathbb{Z}[i]}(x + 2i, x - 2i)$. Then $d$ divides their difference:
  $$(x + 2i) - (x - 2i) = 4i = (1+i)^4 i$$
  Since $x$ is odd, $x^2 + 4 \equiv 1 + 4 = 5 \pmod 8$, so $y$ must be odd.
  Thus $1+i$ cannot divide $y$, which means $\gcd(x + 2i, x - 2i) = 1$.
  Because $\mathbb{Z}[i]$ is a UFD and its only units are $\pm 1, \pm i$ (all of which are cubes), $x + 2i$ must be a cube of some Gaussian integer $a + bi$:
  $$x + 2i = (a + bi)^3 = a(a^2 - 3b^2) + b(3a^2 - b^2)i$$
  Equating real and imaginary components:
  $$x = a(a^2 - 3b^2)$$
  $$2 = b(3a^2 - b^2)$$
  Since $b \in \mathbb{Z}$ divides $2$, we have $b \in \{\pm 1, \pm 2\}$:
  - If $b = 1$: $3a^2 - 1 = 2 \implies 3a^2 = 3 \implies a^2 = 1 \implies a = \pm 1$.
    Then $x = (\pm 1)(1 - 3) = \mp 2$, which contradicts the assumption that $x$ is odd.
  - If $b = 2$: $3a^2 - 4 = 1 \implies 3a^2 = 5$ (no integer solution).
  - If $b = -1$: $3a^2 - 1 = -2 \implies 3a^2 = -1$ (no solution).
  - If $b = -2$: $3a^2 - 4 = -1 \implies 3a^2 = 3 \implies a^2 = 1 \implies a = \pm 1$.
    Then $x = (\pm 1)(1 - 3(4)) = \pm 1(-11) = \mp 11$.
  Taking positive $x$: $x = 11$.
  Then $y^3 = 11^2 + 4 = 121 + 4 = 125 \implies y = 5$.
* **Conclusion**: $(x, y) = (11, 5)$.

---

### Method 21: Eisenstein Integer Factorization in $\mathbb{Z}[\omega]$
* **Core Principle**: Factor $x^2 - xy + y^2 = (x + \omega y)(x + \omega^2 y)$ in $\mathbb{Z}[\omega]$, where $\omega = e^{2\pi i / 3} = \frac{-1 + \sqrt{3}i}{2}$.
* **Representative Problem**: Solve in $\mathbb{Z}^+$: 
  $$x^2 - xy + y^2 = 7$$
* **Proof & Derivation**:
  In $\mathbb{Z}[\omega]$, the algebraic norm is $N(a + b\omega) = a^2 - ab + b^2$.
  Since $7 \equiv 1 \pmod 3$, $7$ splits in $\mathbb{Z}[\omega]$ as:
  $$7 = (3 + \omega)(3 + \omega^2) = (3 + \omega)(2 - \omega)$$
  The full set of units in $\mathbb{Z}[\omega]$ is $\{\pm 1, \pm \omega, \pm \omega^2\}$.
  Multiplying $3 + \omega$ by each unit yields all elements of norm $7$:
  1. $1 \cdot (3 + \omega) \implies (x, y) = (3, -1)$ (not positive)
  2. $-1 \cdot (3 + \omega) \implies (-3, 1)$
  3. $\omega(3 + \omega) = 3\omega + \omega^2 = 3\omega - 1 - \omega = -1 + 2\omega \implies (x, y) = (-1, -2)$
  4. $-\omega(3 + \omega) = 1 - 2\omega \implies (x, y) = (1, 2)$
  5. $\omega^2(3+\omega) = (-1-\omega)(3+\omega) = -3 - 4\omega - \omega^2 = -2 - 3\omega \implies (x, y) = (-2, 3)$
  6. $-\omega^2(3+\omega) = 2 + 3\omega \implies (x, y) = (2, 3)$
  Testing pairs in $\mathbb{Z}^+$:
  - For $(2, 3)$: $2^2 - 2(3) + 3^2 = 4 - 6 + 9 = 7$.
  - By symmetry, $(3, 2)$ also satisfies $9 - 6 + 4 = 7$.
* **Conclusion**: $(x, y) \in \{(2, 3), (3, 2)\}$.

---

### Method 22: Lifting the Exponent Lemma (LTE) for Odd Primes
* **Core Principle**: For an odd prime $p$, if $p \mid (x - y)$ and $p \nmid xy$, then:
  $$v_p(x^n - y^n) = v_p(x - y) + v_p(n)$$
* **Representative Problem**: Find all natural numbers $n$ such that: 
  $$2^n + 1 = 3^k \quad \text{for some } k \in \mathbb{Z}^+$$
* **Proof & Derivation**:
  Rewrite as $3^k - 1^k = 2^n$ (or apply LTE directly to $2^n - (-1)^n$ with $p = 3$).
  - If $n$ is even, $2^n \equiv 1 \pmod 3 \implies 2^n + 1 \equiv 2 \pmod 3$.
    This cannot be a power of $3$ unless $3^k = 2$, which is impossible.
  - Thus $n$ must be odd, so we can write:
    $$2^n + 1 = 2^n - (-1)^n$$
  Since $3 \mid (2 - (-1)) = 3$ and $3 \nmid 2 \cdot (-1)$, apply LTE with $p = 3$:
  $$v_3(2^n + 1) = v_3(2 - (-1)) + v_3(n) = 1 + v_3(n)$$
  We are given $2^n + 1 = 3^k$, which means:
  $$k = 1 + v_3(n)$$
  Since $3^{v_3(n)} \le n$, it follows that:
  $$2^n + 1 = 3^{1 + v_3(n)} = 3 \cdot 3^{v_3(n)} \le 3n$$
  We now analyze the inequality $2^n + 1 \le 3n$ for odd $n$:
  - If $n = 1$: $2^1 + 1 = 3 \le 3(1) = 3$ (equality holds, yielding $k = 1$).
  - If $n = 3$: $2^3 + 1 = 9 \le 3(3) = 9$ (equality holds, yielding $k = 2$).
  - For $n \ge 5$, an easy induction shows $2^n + 1 > 3n$:
    Base case $n=5$: $2^5 + 1 = 33 > 15$.
* **Conclusion**: $n \in \{1, 3\}$.

---

### Method 23: Lifting the Exponent Lemma (LTE) for $p = 2$
* **Core Principle**: For even $n$ and odd integers $x, y$:
  $$v_2(x^n - y^n) = v_2(x - y) + v_2(x + y) + v_2(n) - 1$$
* **Representative Problem**: Solve in $\mathbb{Z}^+$: 
  $$x^n - 1 = 2^k \quad \text{with } n \ge 2, x \text{ odd}$$
* **Proof & Derivation**:
  Since $x$ is odd and $x \ge 3$, $x - 1 \ge 2$ divides $x^n - 1 = 2^k$.
  Thus $x - 1 = 2^a$ for some $a \ge 1$.
  - If $n$ is odd:
    $$x^n - 1 = (x - 1)(x^{n-1} + \dots + 1)$$
    The second factor has $n$ odd terms, making it odd.
    Since it divides $2^k$, it must equal $1$:
    $$x^{n-1} + \dots + 1 = 1 \implies n = 1 \quad (\text{contradicting } n \ge 2)$$
  - Thus $n$ must be even. Apply the base-$2$ LTE:
    $$v_2(x^n - 1) = v_2(x - 1) + v_2(x + 1) + v_2(n) - 1$$
    Notice that $\gcd(x - 1, x + 1) = 2$.
    Since both are powers of $2$, we must have $\{x - 1, x + 1\} = \{2, 4\} \implies x = 3$.
  Substituting $x = 3$:
  $$3^n - 1 = 2^k$$
  Apply LTE to $3^n - 1$:
  $$v_2(3^n - 1) = v_2(3 - 1) + v_2(3 + 1) + v_2(n) - 1 = 1 + 2 + v_2(n) - 1 = v_2(n) + 2$$
  On the other hand, $3^n - 1 = 2^{v_2(3^n - 1)} = 2^{v_2(n) + 2} = 4 \cdot 2^{v_2(n)} \le 4n$.
  Solving $3^n - 1 \le 4n$ for even $n$:
  - If $n = 2$: $3^2 - 1 = 8 \le 4(2) = 8$ (equality holds, yielding $k = 3$).
  - For even $n \ge 4$: $3^4 - 1 = 80 > 16$, and by induction $3^n - 1 > 4n$.
* **Conclusion**: $(x, n, k) = (3, 2, 3)$.

---

### Method 24: Zsigmondy's Theorem Application
* **Core Principle**: For coprime $a > b \ge 1$, $a^n - b^n$ has at least one primitive prime factor not dividing $a^k - b^k$ for any $k < n$, with the sole exceptions being $2^6 - 1^6$ and $a+b = 2^k$ with $n = 2$.
* **Representative Problem**: Find all $a, b, n \in \mathbb{Z}^+$ with $n \ge 2$ such that: 
  $$a^n - b^n = 3^5$$
* **Proof & Derivation**:
  Here $a^n - b^n = 243 = 3^5$.
  The only prime factor of $a^n - b^n$ is $p = 3$.
  By Zsigmondy's Theorem, $a^n - b^n$ must have a primitive prime factor unless $(a, b, n)$ is an exceptional case:
  1. If a primitive prime divisor $P$ exists, then $P \mid (a^n - b^n) \implies P = 3$.
     Because $P$ is primitive, $3$ cannot divide $a^k - b^k$ for any $k < n$.
     In particular, for $k = 1$, $3 \nmid (a - b)$.
     However, since $n \ge 2$, $a - b$ divides $a^n - b^n = 3^5$, which forces $a - b = 3^m$ for some $m \ge 0$.
     If $m \ge 1$, then $3 \mid (a - b)$, contradicting the primitivity of $3$.
     Thus we must have $a - b = 1$.
  2. If $a - b = 1$:
     $$a^n - (a - 1)^n = 243$$
     - For $n = 2$: $a^2 - (a-1)^2 = 2a - 1 = 243 \implies 2a = 244 \implies a = 122$, so $b = 121$.
     - For $n = 3$: $a^3 - (a-1)^3 = 3a^2 - 3a + 1 = 243 \implies 3a(a-1) = 242$.
       Since $3 \nmid 242$, this yields no integer solution.
     - For $n \ge 4$: $a^n - (a-1)^n > n a^{n-1}$. For $a \ge 2$, testing small values quickly shows $a=2 \implies 2^n - 1 = 243$ (no solution, since $244$ is not a power of $2$). For $a \ge 3$ and $n \ge 5$, $a^n - (a-1)^n > 5 \cdot 2^4 = 80$, and for $a=3, n=5 \implies 3^5 - 2^5 = 243 - 32 = 211 \ne 243$.
* **Conclusion**: $(a, b, n) = (122, 121, 2)$.

---

### Method 25: The Extremal Principle (Well-Ordering on Minimal Non-Zero Element)
* **Core Principle**: Assume the existence of solutions, select the solution minimizing an appropriate positive metric (e.g., $x+y+z$ or $\max(x,y,z)$), and deduce a contradiction.
* **Representative Problem**: Prove that the following system has no solutions in $\mathbb{Z}^+$: 
  $$x^2 + y^2 = 3(z^2 + w^2)$$
* **Proof & Derivation**:
  Suppose the solution set in $\mathbb{Z}^+$ is non-empty.
  Choose a solution $(x_0, y_0, z_0, w_0)$ that minimizes $x^2 + y^2$.
  Reducing modulo $3$:
  $$x_0^2 + y_0^2 \equiv 0 \pmod 3$$
  The quadratic residues modulo $3$ are $\{0, 1\}$.
  A sum of two squares is $0 \pmod 3$ if and only if both squares are $0 \pmod 3$:
  $$x_0 \equiv 0 \pmod 3 \quad \text{and} \quad y_0 \equiv 0 \pmod 3$$
  Let $x_0 = 3x_1$ and $y_0 = 3y_1$ for $x_1, y_1 \in \mathbb{Z}^+$.
  Substitute these into the equation:
  $$(3x_1)^2 + (3y_1)^2 = 3(z_0^2 + w_0^2) \iff 9x_1^2 + 9y_1^2 = 3(z_0^2 + w_0^2)$$
  Divide by $3$:
  $$z_0^2 + w_0^2 = 3(x_1^2 + y_1^2)$$
  By the exact same reasoning modulo $3$, we must have:
  $$z_0 = 3z_1 \quad \text{and} \quad w_0 = 3w_1 \quad (z_1, w_1 \in \mathbb{Z}^+)$$
  Substitute these back:
  $$(3z_1)^2 + (3w_1)^2 = 3(x_1^2 + y_1^2) \iff 9z_1^2 + 9w_1^2 = 3(x_1^2 + y_1^2) \iff x_1^2 + y_1^2 = 3(z_1^2 + w_1^2)$$
  Thus $(x_1, y_1, z_1, w_1)$ is another positive integer solution.
  However:
  $$x_1^2 + y_1^2 = \frac{x_0^2 + y_0^2}{9} < x_0^2 + y_0^2$$
  This directly contradicts the minimality of $x_0^2 + y_0^2$.
* **Conclusion**: No solutions exist in $\mathbb{Z}^+$.

---

### Method 26: Convexity and Monotonicity Squeeze
* **Core Principle**: Exploit strict convexity or monotonicity to bound variables, showing that the function exceeds target values outside a narrow range.
* **Representative Problem**: Solve in $\mathbb{Z}^+$: 
  $$3^x + 4^x = 5^x$$
* **Proof & Derivation**:
  Divide the equation by $5^x$:
  $$f(x) = \left(\frac{3}{5}\right)^x + \left(\frac{4}{5}\right)^x = 1$$
  Notice that $g(t) = c^t$ is strictly decreasing for any $0 < c < 1$.
  Since both $\frac{3}{5} < 1$ and $\frac{4}{5} < 1$, the function $f(x)$ is strictly decreasing on $\mathbb{R}^+$.
  Therefore, $f(x) = 1$ can have at most one real solution.
  Evaluating $f(x)$ at small integers:
  - For $x = 1$: $f(1) = \frac{3}{5} + \frac{4}{5} = \frac{7}{5} > 1$.
  - For $x = 2$: $f(2) = \left(\frac{3}{5}\right)^2 + \left(\frac{4}{5}\right)^2 = \frac{9 + 16}{25} = 1$.
  - For $x \ge 3$: Since $f$ is strictly decreasing, $f(x) < f(2) = 1$.
* **Conclusion**: The unique solution is $x = 2$.

---

### Method 27: Base-$p$ Expansion and Digit Representation Constraints
* **Core Principle**: Represent unknowns in base $p$ to decouple complicated arithmetic systems into independent relations on digits.
* **Representative Problem**: Find all $n \in \mathbb{Z}^+$ such that: 
  $$n \cdot 2^{n-1} + 1 = m^2 \quad \text{for some } m \in \mathbb{Z}^+$$
* **Proof & Derivation**:
  Rearrange the equation:
  $$n \cdot 2^{n-1} = m^2 - 1 = (m - 1)(m + 1)$$
  The factors $(m - 1)$ and $(m + 1)$ are two integers differing by $2$, so $\gcd(m - 1, m + 1) \in \{1, 2\}$.
  - If $n = 1$: $1 \cdot 2^0 + 1 = 2 = m^2$ (no integer solution).
  - If $n = 2$: $2 \cdot 2^1 + 1 = 5 = m^2$ (no integer solution).
  - If $n = 3$: $3 \cdot 2^2 + 1 = 13 = m^2$ (no integer solution).
  - If $n = 4$: $4 \cdot 2^3 + 1 = 33 = m^2$ (no integer solution).
  - If $n = 5$: $5 \cdot 2^4 + 1 = 81 = 9^2 \implies m = 9$.
  For $n > 5$:
  Since $(m-1)(m+1)$ is divisible by $2^{n-1}$ with $n \ge 6$, one of the two factors must carry almost the entire power of $2$:
  $$m \pm 1 = k \cdot 2^{n-2}$$
  Then $m \ge 2^{n-2} - 1$.
  Squaring both sides gives $m^2 > 2^{2n-4}$.
  For $n \ge 6$, $2^{2n-4} > n \cdot 2^{n-1} + 1$, so no further solutions can exist.
* **Conclusion**: The only solution is $n = 5$ (with $m = 9$).

---

### Method 28: Binomial Modulo Prime-Power Expansion
* **Core Principle**: Expand $(1 + a)^p$ and evaluate modulo prime powers $p^2, p^3$ to constrain the exponent.
* **Representative Problem**: Solve in $\mathbb{Z}^+$: 
  $$(x + 1)^p - x^p = p^2 \quad \text{where } p \text{ is prime}$$
* **Proof & Derivation**:
  Expand the left-hand side using the Binomial Theorem:
  $$(x + 1)^p - x^p = \sum_{k=1}^p \binom{p}{k} x^{p-k} = p x^{p-1} + \binom{p}{2} x^{p-2} + \dots + p x + 1 = p^2$$
  - For $p = 2$:
    $$(x + 1)^2 - x^2 = 2x + 1 = 2^2 = 4 \implies 2x = 3 \quad (\text{no integer solution})$$
  - For $p > 2$ ($p$ is an odd prime):
    Modulo $p$, every intermediate binomial coefficient $\binom{p}{k}$ is $0 \pmod p$.
    Thus:
    $$p^2 = (x+1)^p - x^p \equiv 1 \pmod p \implies p^2 \equiv 1 \pmod p \implies 0 \equiv 1 \pmod p$$
    This is an immediate contradiction.
* **Conclusion**: No solutions exist for any prime $p$.

---

### Method 29: Parity Alternation along Finite Chains
* **Core Principle**: Track the parity across iterative recurrence relations or coupled equations to force variables into contradictory cycles.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$\begin{cases} x + y = z^2 \\ y + z = x^2 \\ z + x = y^2 \end{cases}$$
* **Proof & Derivation**:
  Subtracting pairs of equations:
  $$(x + y) - (y + z) = z^2 - x^2 \iff x - z = (z - x)(z + x) \iff (x - z)(x + z + 1) = 0$$
  By cyclic symmetry, we also obtain:
  $$(y - x)(y + x + 1) = 0 \quad \text{and} \quad (z - y)(z + y + 1) = 0$$
  This yields two main cases:
  - Case 1: $x = y = z$.
    The system collapses to $2x = x^2 \implies x(x - 2) = 0$.
    Thus $x = y = z = 0$ or $x = y = z = 2$.
  - Case 2: Two variables are distinct. Without loss of generality, let $x \ne z \implies x + z = -1$.
    From $x + z = y^2$, we get $y^2 = -1$, which is impossible for $y \in \mathbb{Z}$.
  Thus no other cases yield real solutions.
* **Conclusion**: $(x, y, z) \in \{(0, 0, 0), (2, 2, 2)\}$.

---

### Method 30: System Decoupling via Elementary Symmetric Polynomials
* **Core Principle**: Convert cyclic equations into elementary symmetric polynomials $\sigma_1 = x+y+z$, $\sigma_2 = xy+yz+zx$, $\sigma_3 = xyz$, then recover variables as roots of a single cubic.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$\begin{cases} x + y + z = 3 \\ x^2 + y^2 + z^2 = 9 \\ x^3 + y^3 + z^3 = 27 \end{cases}$$
* **Proof & Derivation**:
  Let $\sigma_1 = x+y+z = 3$.
  Using Newton's sums:
  $$\sigma_1^2 = x^2 + y^2 + z^2 + 2\sigma_2 \implies 9 = 9 + 2\sigma_2 \implies \sigma_2 = 0$$
  Next, for the sum of cubes:
  $$x^3 + y^3 + z^3 - 3\sigma_3 = \sigma_1(x^2 + y^2 + z^2 - \sigma_2)$$
  $$27 - 3\sigma_3 = 3(9 - 0) = 27 \implies 3\sigma_3 = 0 \implies \sigma_3 = 0$$
  Thus, $x, y, z$ are the roots of the cubic equation:
  $$t^3 - \sigma_1 t^2 + \sigma_2 t - \sigma_3 = 0 \iff t^3 - 3t^2 = 0 \iff t^2(t - 3) = 0$$
  The roots are $t = 0$ (with multiplicity $2$) and $t = 3$ (with multiplicity $1$).
* **Conclusion**: All permutations of $(3, 0, 0)$: $(3, 0, 0), (0, 3, 0), (0, 0, 3)$.

---

### Method 31: Chinese Remainder Theorem (CRT) Incongruence Sieve
* **Core Principle**: Combine distinct prime congruences using CRT to construct a composite modulus that eliminates all possible solution candidates.
* **Representative Problem**: Prove that $x^2 - 10y^2 = 3$ has no integer solutions.
* **Proof & Derivation**:
  Reduce the equation modulo $5$:
  $$x^2 \equiv 3 \pmod 5$$
  The set of quadratic residues modulo $5$ is:
  $$\mathcal{QR}_5 = \{0^2, 1^2, 2^2\} \pmod 5 = \{0, 1, 4\} \pmod 5$$
  Since $3 \notin \{0, 1, 4\}$, $x^2 \equiv 3 \pmod 5$ has no integer solutions.
  Because no integer $x$ can satisfy the congruence modulo $5$, the original Diophantine equation cannot hold for any pair of integers $(x, y)$.
* **Conclusion**: No integer solutions exist.

---

### Method 32: Rational Parametrization of Conics
* **Core Principle**: Given a rational point $P_0$ on a second-degree curve $Q(x,y) = 0$, intersect the curve with lines of rational slope $y - y_0 = t(x - x_0)$ to generate all rational points, then clear denominators to find all integral solutions.
* **Representative Problem**: Find all rational solutions $(x, y) \in \mathbb{Q}^2$ to: 
  $$x^2 + 3y^2 = 1$$
* **Proof & Derivation**:
  A known base point is $P_0 = (-1, 0)$.
  Consider a line through $P_0$ with rational slope $t \in \mathbb{Q}$:
  $$y = t(x + 1)$$
  Substitute this into the equation of the ellipse:
  $$x^2 + 3t^2(x + 1)^2 = 1 \iff (x^2 - 1) + 3t^2(x + 1)^2 = 0$$
  Factor out $(x + 1)$:
  $$(x + 1)\left[(x - 1) + 3t^2(x + 1)\right] = 0$$
  For the second intersection point $x \ne -1$:
  $$(3t^2 + 1)x + (3t^2 - 1) = 0 \implies x = \frac{1 - 3t^2}{1 + 3t^2}$$
  Substitute $x$ back to find $y$:
  $$y = t\left(\frac{1 - 3t^2}{1 + 3t^2} + 1\right) = t\left(\frac{2}{1 + 3t^2}\right) = \frac{2t}{1 + 3t^2}$$
* **Conclusion**: $(x, y) = \left(\frac{1 - 3t^2}{1 + 3t^2}, \frac{2t}{1 + 3t^2}\right)$ for $t \in \mathbb{Q}$, along with the point $(-1, 0)$.

---

### Method 33: Coordinate Rotation and Diagonalization
* **Core Principle**: Eliminate cross terms $Bxy$ in a quadratic equation by rotating coordinates: $x = u+v, y = u-v$.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$x^2 + xy + y^2 = 3$$
* **Proof & Derivation**:
  Apply the substitution $x = u + v$, $y = u - v$:
  $$(u + v)^2 + (u + v)(u - v) + (u - v)^2 = 3$$
  $$(u^2 + 2uv + v^2) + (u^2 - v^2) + (u^2 - 2uv + v^2) = 3$$
  $$3u^2 + v^2 = 3$$
  Since $u, v \in \frac{1}{2}\mathbb{Z}$ and $3u^2 \le 3$, we have $u^2 \le 1$:
  - If $u = 0$, then $v^2 = 3$, which has no rational solutions.
  - If $u^2 = 1 \implies u = \pm 1$, then $v^2 = 0 \implies v = 0$.
    This gives $(x, y) = (1, 1)$ or $(-1, -1)$.
  - If $2u, 2v$ are odd integers, set $u = \pm \frac{1}{2}$:
    $$3\left(\frac{1}{4}\right) + v^2 = 3 \implies v^2 = \frac{9}{4} \implies v = \pm \frac{3}{2}$$
    This yields:
    - $(u, v) = \left(\frac{1}{2}, \frac{3}{2}\right) \implies (x, y) = (2, -1)$
    - $(u, v) = \left(\frac{1}{2}, -\frac{3}{2}\right) \implies (x, y) = (-1, 2)$
    - $(u, v) = \left(-\frac{1}{2}, \frac{3}{2}\right) \implies (x, y) = (1, -2)$
    - $(u, v) = \left(-\frac{1}{2}, -\frac{3}{2}\right) \implies (x, y) = (-2, 1)$
* **Conclusion**: $(x, y) \in \{(1, 1), (-1, -1), (2, -1), (-1, 2), (1, -2), (-2, 1)\}$.

---

### Method 34: Continued Fraction Expansion for Best Rational Approximations
* **Core Principle**: Rational solutions to quadratic forms $|x^2 - D y^2| < \sqrt{D}$ correspond to convergents $\frac{p_n}{q_n}$ of the simple continued fraction of $\sqrt{D}$.
* **Representative Problem**: Find the fundamental positive integer solution to: 
  $$x^2 - 7y^2 = 1$$
* **Proof & Derivation**:
  Compute the continued fraction of $\sqrt{7}$:
  - $\lfloor\sqrt{7}\rfloor = 2$, $\sqrt{7} = 2 + (\sqrt{7} - 2) = 2 + \frac{1}{x_1}$, where $x_1 = \frac{\sqrt{7}+2}{3}$.
  - $\lfloor x_1 \rfloor = 1$, $x_1 = 1 + \frac{\sqrt{7}-1}{3} = 1 + \frac{1}{x_2}$, where $x_2 = \frac{\sqrt{7}+1}{2}$.
  - $\lfloor x_2 \rfloor = 1$, $x_2 = 1 + \frac{\sqrt{7}-1}{2} = 1 + \frac{1}{x_3}$, where $x_3 = \frac{\sqrt{7}+1}{3}$.
  - $\lfloor x_3 \rfloor = 1$, $x_3 = 1 + \frac{\sqrt{7}-2}{3} = 1 + \frac{1}{x_4}$, where $x_4 = \sqrt{7}+2$.
  - $\lfloor x_4 \rfloor = 4$, period closes.
  Thus, $\sqrt{7} = [2; \overline{1, 1, 1, 4}]$.
  The period length is $k = 4$ (even). The fundamental solution corresponds to convergent $p_{3}/q_{3}$:
  - $C_0 = \frac{2}{1}$
  - $C_1 = 2 + \frac{1}{1} = \frac{3}{1}$
  - $C_2 = 2 + \frac{1}{1 + 1/1} = \frac{5}{2}$
  - $C_3 = 2 + \frac{1}{1 + \frac{1}{1 + 1/1}} = \frac{8}{3}$
  Test $(x, y) = (8, 3)$:
  $$8^2 - 7(3^2) = 64 - 7(9) = 64 - 63 = 1$$
* **Conclusion**: The fundamental solution is $(x, y) = (8, 3)$.

---

### Method 35: Fractional Part and Floor Function Reductions
* **Core Principle**: Decompose real variables into integer and fractional parts $x = \lfloor x \rfloor + \{x\}$, then use $0 \le \{x\} < 1$ to force discrete solutions.
* **Representative Problem**: Solve for $x \in \mathbb{R}$: 
  $$\lfloor x \rfloor^2 = x^2 - 3$$
* **Proof & Derivation**:
  Let $n = \lfloor x \rfloor \in \mathbb{Z}$ and $\alpha = \{x\} \in [0, 1)$, so $x = n + \alpha$.
  Substitute into the equation:
  $$n^2 = (n + \alpha)^2 - 3 \iff n^2 = n^2 + 2n\alpha + \alpha^2 - 3 \iff 2n\alpha + \alpha^2 = 3$$
  Since $0 \le \alpha < 1$:
  $$0 \le 2n\alpha + \alpha^2 < 2n(1) + 1^2 = 2n + 1$$
  Therefore, we must have:
  $$3 < 2n + 1 \implies 2n > 2 \implies n > 1 \implies n \ge 2$$
  Now express $\alpha$ by solving the quadratic $\alpha^2 + 2n\alpha - 3 = 0$:
  $$\alpha = -n + \sqrt{n^2 + 3} \quad (\text{taking the positive root since } \alpha \ge 0)$$
  We require $\alpha < 1$:
  $$-n + \sqrt{n^2 + 3} < 1 \iff \sqrt{n^2 + 3} < n + 1 \iff n^2 + 3 < n^2 + 2n + 1 \iff 2n > 2 \iff n > 1$$
  This condition holds for all integers $n \ge 2$.
  However, for $x$ to be consistent with the original problem over the integers, setting $x \in \mathbb{Z}$ requires $\alpha = 0$, which would yield $3 = 0$ (impossible).
  Thus $x$ must be irrational, with solutions $x = \sqrt{n^2 + 3}$ for each $n \in \mathbb{Z}_{\ge 2}$ such that $\lfloor \sqrt{n^2+3} \rfloor = n$.
  Since $n^2 < n^2 + 3 < (n+1)^2$ holds for all $n \ge 2$, every integer $n \ge 2$ gives a valid solution.
* **Conclusion**: $x = \sqrt{n^2 + 3}$ for any integer $n \ge 2$.

---

### Method 36: Congruence via Euler's Totient and Fermat's Little Theorem
* **Core Principle**: If $p$ is prime and $p \nmid a$, then $a^{p-1} \equiv 1 \pmod p$. More generally, $a^{\phi(m)} \equiv 1 \pmod m$.
* **Representative Problem**: Find all primes $p, q$ such that: 
  $$p^q + q^p \equiv 0 \pmod{p + q}$$
* **Proof & Derivation**:
  By symmetry, assume $p \le q$.
  - If $p = q$: $p^p + p^p = 2p^p$, which is divisible by $p + p = 2p$.
    This condition holds for every prime $p$.
  - Now assume $p < q$. Since $p$ and $q$ are primes, $\gcd(p, p+q) = \gcd(p, q) = 1$.
  By the given congruence:
  $$p^q + q^p \equiv 0 \pmod{p+q}$$
  Since $q \equiv -p \pmod{p+q}$, we have:
  $$q^p \equiv (-p)^p \pmod{p+q}$$
  Substituting this in gives:
  $$p^q + (-p)^p \equiv 0 \pmod{p+q}$$
  - If $p$ is odd, then $(-p)^p = -p^p$, which implies:
    $$p^q - p^p \equiv 0 \pmod{p+q} \implies p^p(p^{q-p} - 1) \equiv 0 \pmod{p+q}$$
    Since $\gcd(p^p, p+q) = 1$, we must have $p+q \mid p^{q-p} - 1$.
    However, $p^{q-p} - 1 < p^q$, and analyzing orders via Fermat's Little Theorem shows this forces $p = 2$.
  - If $p = 2$: $2+q \mid 2^q + q^2$.
    Using $q \equiv -2 \pmod{q+2}$, this becomes $2^q + (-2)^2 = 2^q + 4 \equiv 0 \pmod{q+2}$.
    - For $q = 3$: $2+3 = 5$, and $2^3 + 4 = 12$, not divisible by $5$.
    - For $q \ge 5$: $2^q + 4 < 2(q+2)$ fails; a residue check shows no odd prime $q$ satisfies this.
* **Conclusion**: All pairs of identical primes $(p, p)$.

---

### Method 37: Quadratic Reciprocity Law and the Legendre Symbol
* **Core Principle**: For distinct odd primes $p, q$: $\left(\frac{p}{q}\right)\left(\frac{q}{p}\right) = (-1)^{\frac{p-1}{2}\frac{q-1}{2}}$.
* **Representative Problem**: Prove that $y^2 = x^3 - 5$ has no integer solutions for $x$ even.
* **Proof & Derivation**:
  Assume $x$ is even. Then $x^3 \equiv 0 \pmod 8$, so:
  $$y^2 = x^3 - 5 \equiv -5 \equiv 3 \pmod 8$$
  Squares can only be $0, 1, 4 \pmod 8$.
  Since $3 \notin \{0, 1, 4\}$, $y^2 \equiv 3 \pmod 8$ is impossible.
* **Conclusion**: No integer solutions exist with $x$ even.

---

### Method 38: Runge's Method for Compact Algebraic Curves
* **Core Principle**: If an algebraic curve $F(x, y) = 0$ of degree $d$ satisfies Runge's condition (its leading homogeneous part factors into coprime polynomials over $\mathbb{Q}$), all integer solutions must lie within an effectively computable bounded region.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$y^2 = x(x+1)(x+2)(x+3) + 1$$
* **Proof & Derivation**:
  Group the factors symmetrically:
  $$x(x+3) = x^2 + 3x$$
  $$(x+1)(x+2) = x^2 + 3x + 2$$
  Let $u = x^2 + 3x$. The equation becomes:
  $$y^2 = u(u + 2) + 1 = u^2 + 2u + 1 = (u + 1)^2$$
  Thus:
  $$y = \pm (u + 1) = \pm (x^2 + 3x + 1)$$
  Since $x^2 + 3x + 1$ is an integer for every integer $x$, this identity holds unconditionally.
* **Conclusion**: $(x, \pm (x^2 + 3x + 1))$ for all $x \in \mathbb{Z}$.

---

### Method 39: Invariant and Monovariant Principles in Integer Sequences
* **Core Principle**: Map a system of equations onto an iterative transition rule, then use an invariant quantity (such as parity or a conserved quadratic form) to show the target state is unreachable.
* **Representative Problem**: Determine if there exist integers $a, b, c, d$ satisfying:
  $$a^2 + b^2 + c^2 + d^2 = 7 \times 4^k \quad (k \in \mathbb{Z}^+)$$
* **Proof & Derivation**:
  Apply induction on $k \ge 1$:
  - Base case $k = 1$: $a^2 + b^2 + c^2 + d^2 = 28$.
    Modulo $8$: The sum of four squares can only produce residues in $\{0, 1, 2, 3, 4, 5, 6, 7\} \pmod 8$.
    Notice that $28 \equiv 4 \pmod 8$.
    For the sum of four squares to be $\equiv 4 \pmod 8$, either all four numbers are odd ($1+1+1+1=4$) or all four are even ($4+0+0+0 = 4$).
    - If all are odd: $a = 2a_1+1, \dots \implies \sum (2a_i+1)^2 = 4\sum a_i(a_i+1) + 4 \equiv 4 \pmod{16}$.
      However, $28 \equiv 12 \pmod{16}$, so they cannot all be odd.
    - Thus all four must be even. Let $a = 2a', b = 2b', c = 2c', d = 2d'$.
  Substituting these in:
  $$4(a'^2 + b'^2 + c'^2 + d'^2) = 7 \times 4^k \iff a'^2 + b'^2 + c'^2 + d'^2 = 7 \times 4^{k-1}$$
  By infinite descent, repeatedly dividing by $4$ eventually reduces the equation to:
  $$a_k^2 + b_k^2 + c_k^2 + d_k^2 = 7$$
  The possible squares are $0, 1, 4$.
  The maximum possible sum of four squares from $\{0, 1, 4\}$ that equals $7$ requires $4 + 1 + 1 + 1 = 7$.
  This produces valid base solutions, such as $(\pm 2, \pm 1, \pm 1, \pm 1)$.
  Reversing the substitution gives $(a, b, c, d) = 2^{k-1}(\pm 2, \pm 1, \pm 1, \pm 1)$.
* **Conclusion**: Solutions exist: $(a, b, c, d) = 2^{k-1}(\pm 2, \pm 1, \pm 1, \pm 1)$ and its permutations.

---

### Method 40: Discriminant Method with Sum-of-Squares Decomposition
* **Core Principle**: Rewrite an equation as a sum of squares equal to zero: $\sum_{i=1}^k A_i(x_1, \dots, x_n)^2 = 0 \iff A_i = 0$ for all $i$.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$2x^2 + 2y^2 - 2xy - 2x - 2y + 2 = 0$$
* **Proof & Derivation**:
  Multiply the entire equation by $2$:
  $$4x^2 + 4y^2 - 4xy - 4x - 4y + 4 = 0$$
  Regroup terms as a sum of squares:
  $$(x^2 - 2xy + y^2) + (x^2 - 2x + 1) + (y^2 - 2y + 1) + (2x^2 + 2y^2 - 2x - 2y + 2 - \dots)$$
  More cleanly:
  $$(x - y)^2 + (x - 1)^2 + (y - 1)^2 = 0$$
  Verify the expansion:
  $$(x^2 - 2xy + y^2) + (x^2 - 2x + 1) + (y^2 - 2y + 1) = 2x^2 - 2xy + 2y^2 - 2x - 2y + 2$$
  This matches the original equation exactly.
  Because each squared term must be non-negative, the sum can only be $0$ if every term vanishes simultaneously:
  $$\begin{cases} x - y = 0 \\ x - 1 = 0 \\ y - 1 = 0 \end{cases} \implies x = y = 1$$
* **Conclusion**: $(x, y) = (1, 1)$.

---

### Method 41: Tangent Line Arithmetic on Elliptic Curves
* **Core Principle**: Given an integer or rational point $P$ on a Weierstrass curve $y^2 = x^3 + Ax + B$, the tangent line at $P$ intersects the curve at a third rational point $2P$.
* **Representative Problem**: Find a non-trivial rational solution $(x, y) \in \mathbb{Q}^2$ to: 
  $$y^2 = x^3 - 2$$
  given the known integer solution $P = (3, 5)$.
* **Proof & Derivation**:
  Differentiate implicitly to find the slope of the tangent line at $P(3, 5)$:
  $$2y \frac{dy}{dx} = 3x^2 \implies m = \frac{3x_0^2}{2y_0} = \frac{3(3^2)}{2(5)} = \frac{27}{10}$$
  The tangent line at $P$ has equation:
  $$y - 5 = \frac{27}{10}(x - 3) \implies y = \frac{27}{10}x - \frac{81}{10} + \frac{50}{10} = \frac{27}{10}x - \frac{31}{10}$$
  Substitute this into the curve equation $y^2 = x^3 - 2$:
  $$\left(\frac{27}{10}x - \frac{31}{10}\right)^2 = x^3 - 2 \iff x^3 - \frac{729}{100}x^2 + \dots = 0$$
  By Vieta's formulas, the sum of the three roots of this cubic is the coefficient of $x^2$:
  $$x_1 + x_2 + x_3 = m^2 = \frac{729}{100}$$
  Since the line is tangent to the curve at $P(3, 5)$, $x = 3$ is a double root ($x_1 = x_2 = 3$):
  $$3 + 3 + x_3 = \frac{729}{100} \implies x_3 = \frac{729}{100} - 6 = \frac{129}{100}$$
  Find the corresponding $y$-coordinate:
  $$y_3 = \frac{27}{10}\left(\frac{129}{100}\right) - \frac{31}{10} = \frac{3483}{1000} - \frac{3100}{1000} = \frac{383}{1000}$$
  Reflecting across the $x$-axis gives $2P = \left(\frac{129}{100}, -\frac{383}{1000}\right)$.
* **Conclusion**: A non-trivial rational solution is $(x, y) = \left(\frac{129}{100}, -\frac{383}{1000}\right)$.

---

### Method 42: Dominant Root Asymptotics for High-Degree Equations
* **Core Principle**: For $y^n = x^n + a x^{n-1} + \dots$, compute the asymptotic expansion of $y$ to constrain $y - x$ to a small finite set of integers.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$y^4 = x^4 + 4x^3 + 7x^2 + 6x + 2$$
* **Proof & Derivation**:
  Complete the square inside the quartic:
  $$(x^2 + 2x + 1)^2 = (x^2 + 2x + 1)(x^2 + 2x + 1) = x^4 + 4x^3 + 6x^2 + 4x + 1$$
  $$(x^2 + 2x + 2)^2 = x^4 + 4x^3 + 8x^2 + 8x + 4$$
  Compare $y^4$ with these bounding polynomials:
  - $y^4 - (x^2 + 2x + 1)^2 = x^2 + 2x + 1 = (x + 1)^2 \ge 0$.
  - $(x^2 + 2x + 2)^2 - y^4 = x^2 + 2x + 2 = (x + 1)^2 + 1 > 0$ for all $x \in \mathbb{R}$.
  Thus, for all $x$:
  $$(x^2 + 2x + 1)^2 \le y^4 < (x^2 + 2x + 2)^2$$
  Since $y^2$ is an integer, the only way an integer square can fall in the interval $[A^2, (A+1)^2)$ is if it equals the lower bound:
  $$y^2 = x^2 + 2x + 1 = (x + 1)^2$$
  This forces the difference to vanish:
  $$(x + 1)^2 = 0 \implies x = -1$$
  Substitute $x = -1$ back into the original equation:
  $$y^4 = 1 - 4 + 7 - 6 + 2 = 0 \implies y = 0$$
* **Conclusion**: The only solution is $(x, y) = (-1, 0)$.

---

### Method 43: Bézout Factor Matching for Bilinear Fractions
* **Core Principle**: Convert fractions $\frac{1}{x} + \frac{1}{y} = \frac{1}{p}$ into $p(x+y) = xy \iff (x-p)(y-p) = p^2$.
* **Representative Problem**: Find the number of positive integer solutions $(x, y) \in (\mathbb{Z}^+)^2$ to: 
  $$\frac{1}{x} + \frac{1}{y} = \frac{1}{2024}$$
* **Proof & Derivation**:
  Clear denominators:
  $$2024(x + y) = xy \iff xy - 2024x - 2024y = 0 \iff (x - 2024)(y - 2024) = 2024^2$$
  Because $x, y > 0$ and $\frac{1}{x} < \frac{1}{2024}$, we must have $x > 2024$, which means $x - 2024 > 0$.
  Therefore, each positive factor of $2024^2$ uniquely determines a valid solution pair $(x, y)$.
  Find the prime factorization of $2024$:
  $$2024 = 8 \times 253 = 2^3 \times 11 \times 23$$
  Squaring gives:
  $$2024^2 = 2^6 \times 11^2 \times 23^2$$
  The number of positive divisors is:
  $$d(2024^2) = (6 + 1)(2 + 1)(2 + 1) = 7 \times 3 \times 3 = 63$$
* **Conclusion**: There are $63$ solutions.

---

### Method 44: Floor Function Multiplicity (Legendre's Formula)
* **Core Principle**: Use Legendre's formula $v_p(n!) = \sum_{k=1}^\infty \left\lfloor \frac{n}{p^k} \right\rfloor$ to establish $p$-adic valuations of factorials.
* **Representative Problem**: Find all $n \in \mathbb{Z}^+$ such that: 
  $$n! = 2^a \cdot 3^b \quad (\text{where } a, b \in \mathbb{Z}^+)$$
* **Proof & Derivation**:
  The prime factors of $n!$ are precisely all primes $p \le n$.
  For $n!$ to have only $2$ and $3$ as prime factors, no prime $p \ge 5$ can divide $n!$.
  This requires:
  $$n < 5$$
  Test all candidates $n \in \{1, 2, 3, 4\}$:
  - $n = 1$: $1! = 1 = 2^0 \cdot 3^0$ ($a = 0, b = 0 \notin \mathbb{Z}^+$).
  - $n = 2$: $2! = 2 = 2^1 \cdot 3^0$ ($b = 0 \notin \mathbb{Z}^+$).
  - $n = 3$: $3! = 6 = 2^1 \cdot 3^1$ ($a = 1, b = 1 \in \mathbb{Z}^+$).
  - $n = 4$: $4! = 24 = 2^3 \cdot 3^1$ ($a = 3, b = 1 \in \mathbb{Z}^+$).
* **Conclusion**: $n \in \{3, 4\}$.

---

### Method 45: Linear Combinations and $\gcd$ Invariance
* **Core Principle**: Exploit $\gcd(A, B) = \gcd(A - kB, B)$ to show that coupled terms cannot share prime factors beyond an easily bounded set.
* **Representative Problem**: Find all $n \in \mathbb{Z}^+$ such that $\frac{21n + 4}{14n + 3}$ is reducible.
* **Proof & Derivation**:
  Compute the greatest common divisor using the Euclidean Algorithm:
  $$\gcd(21n + 4, 14n + 3) = \gcd((21n + 4) - (14n + 3), 14n + 3) = \gcd(7n + 1, 14n + 3)$$
  Now eliminate $n$:
  $$\gcd(7n + 1, (14n + 3) - 2(7n + 1)) = \gcd(7n + 1, 1) = 1$$
  Since the greatest common divisor of the numerator and denominator is $1$ for every $n \in \mathbb{Z}^+$, the fraction cannot be simplified by any factor $d > 1$.
* **Conclusion**: No such $n$ exists; the fraction is irreducible for all $n \in \mathbb{Z}^+$.

---

### Method 46: Bounding via the Triangle Inequality
* **Core Principle**: For complex numbers or Euclidean distances, $|z_1 + z_2| \le |z_1| + |z_2|$ gives tight bounds when equality holds.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$\sqrt{x^2 + y^2} + \sqrt{(x-3)^2 + (y-4)^2} = 5$$
* **Proof & Derivation**:
  In the Cartesian plane $\mathbb{R}^2$, let $P = (x, y)$, $O = (0, 0)$, and $A = (3, 4)$.
  The left-hand side is the sum of Euclidean distances:
  $$OP + PA = 5$$
  The distance between $O$ and $A$ is:
  $$OA = \sqrt{3^2 + 4^2} = 5$$
  By the Triangle Inequality:
  $$OP + PA \ge OA = 5$$
  Equality holds if and only if $P(x, y)$ lies on the line segment connecting $O(0, 0)$ to $A(3, 4)$.
  The line segment $OA$ is parameterized by:
  $$y = \frac{4}{3}x \quad \text{for } 0 \le x \le 3$$
  For $y$ to be an integer, $3$ must divide $x$.
  The only integers in the interval $[0, 3]$ divisible by $3$ are $x = 0$ and $x = 3$:
  - If $x = 0$: $y = 0$.
  - If $x = 3$: $y = 4$.
* **Conclusion**: $(x, y) \in \{(0, 0), (3, 4)\}$.

---

### Method 47: Disjoint Residue Classes via Quadratic Non-Residues
* **Core Principle**: Evaluate both sides of an equation modulo an odd prime $p$ where the left-hand side is quadratic and the right-hand side belongs exclusively to quadratic non-residues.
* **Representative Problem**: Solve in $\mathbb{Z}$: 
  $$x^2 = 7y + 3$$
* **Proof & Derivation**:
  Reduce the equation modulo $7$:
  $$x^2 \equiv 3 \pmod 7$$
  The set of quadratic residues modulo $7$ is:
  $$\mathcal{QR}_7 = \{0^2, 1^2, 2^2, 3^2\} \pmod 7 = \{0, 1, 4, 2\} \pmod 7$$
  Comparing sets:
  $$3 \notin \{0, 1, 2, 4\}$$
  Thus $3$ is a quadratic non-residue modulo $7$.
  Because $x^2 \pmod 7$ can never equal $3$, no integer $x$ can satisfy the equation.
* **Conclusion**: No integer solutions exist.

---

### Method 48: Pick's Theorem for Planar Lattice Polygons
* **Core Principle**: The area of any lattice polygon is given by $\mathcal{A} = I + \frac{B}{2} - 1$, where $I$ is the number of strictly interior lattice points and $B$ is the number of boundary lattice points.
* **Representative Problem**: Find the number of strictly interior lattice points $I$ in the triangle bounded by the coordinate axes and the line $3x + 5y = 30$.
* **Proof & Derivation**:
  The vertices of the triangle are $O(0, 0)$, $A(10, 0)$, and $B(0, 6)$.
  The area of this right triangle is:
  $$\mathcal{A} = \frac{1}{2} \times 10 \times 6 = 30$$
  Count the boundary lattice points $B$:
  - On the segment from $(0, 0)$ to $(10, 0)$: $11$ points.
  - On the segment from $(0, 0)$ to $(0, 6)$: $7$ points.
  - On the hypotenuse $3x + 5y = 30$:
    Since $\gcd(3, 5) = 1$, the number of segments is $\gcd(10 - 0, 0 - 6) = \gcd(10, -6) = 2$.
    The boundary points on the hypotenuse are $(0, 6)$, $(5, 3)$, and $(10, 0)$ ($3$ points).
  Summing boundary points and subtracting the three duplicated vertices:
  $$B = 11 + 7 + 3 - 3 = 18$$
  Apply Pick's Theorem to solve for $I$:
  $$\mathcal{A} = I + \frac{B}{2} - 1 \implies 30 = I + \frac{18}{2} - 1 \implies 30 = I + 8 \implies I = 22$$
* **Conclusion**: $I = 22$ interior lattice points.

---

### Method 49: Hyperbolic Coordinate Asymptote Bounding
* **Core Principle**: For equations of the form $x^2 - d y^2 = c$, view the equation as a hyperbola with asymptotes $x = \pm \sqrt{d}y$. The distance between the curve and its asymptotes approaches zero, restricting possible integer solutions.
* **Representative Problem**: Solve in $\mathbb{Z}^+$: 
  $$x^2 - 3xy + 2y^2 = 7$$
* **Proof & Derivation**:
  Factor the left-hand side directly:
  $$x^2 - 3xy + 2y^2 = (x - y)(x - 2y) = 7$$
  Since $7$ is prime, its divisor pairs in $\mathbb{Z}$ are:
  $$(1, 7), (7, 1), (-1, -7), (-7, -1)$$
  Set up each system:
  1. $\begin{cases} x - y = 1 \\ x - 2y = 7 \end{cases} \implies (x - y) - (x - 2y) = y = 1 - 7 = -6 \implies x = -5$ (not positive).
  2. $\begin{cases} x - y = 7 \\ x - 2y = 1 \end{cases} \implies y = 7 - 1 = 6 \implies x = 7 + 6 = 13 \in \mathbb{Z}^+$.
  3. $\begin{cases} x - y = -1 \\ x - 2y = -7 \end{cases} \implies y = -1 - (-7) = 6 \implies x = -1 + 6 = 5 \in \mathbb{Z}^+$.
  4. $\begin{cases} x - y = -7 \\ x - 2y = -1 \end{cases} \implies y = -7 - (-1) = -6$ (not positive).
* **Conclusion**: $(x, y) \in \{(13, 6), (5, 6)\}$.

---

### Method 50: Functional Fixed-Point Iteration on Diophantine Polynomials
* **Core Principle**: For compositions $P(P(x)) = x$, integer solutions must satisfy $P(x) = x$ or form two-cycles where $(P(x) - x)$ divides differences symmetrically.
* **Representative Problem**: Find all integer solutions to $P(P(x)) = x$ for $P(t) = t^2 - 2$.
* **Proof & Derivation**:
  Compute the polynomial composition:
  $$P(P(x)) - x = (x^2 - 2)^2 - 2 - x = x^4 - 4x^2 - x + 2$$
  Notice that any fixed point of $P(x)$ (where $P(x) = x$) also satisfies $P(P(x)) = x$.
  The fixed points satisfy:
  $$x^2 - 2 = x \iff x^2 - x - 2 = 0 \iff (x - 2)(x + 1) = 0$$
  This gives the fixed points $x = 2$ and $x = -1$.
  Therefore, $(x - 2)(x + 1) = x^2 - x - 2$ must divide $P(P(x)) - x$.
  Perform polynomial long division:
  $$\frac{x^4 - 4x^2 - x + 2}{x^2 - x - 2} = x^2 + x - 1$$
  Any additional solutions must satisfy the quotient equation:
  $$x^2 + x - 1 = 0$$
  The roots of this quadratic are:
  $$x = \frac{-1 \pm \sqrt{1 - 4(1)(-1)}}{2} = \frac{-1 \pm \sqrt{5}}{2}$$
  Neither root is an integer.
* **Conclusion**: The only integer solutions are $x \in \{-1, 2\}$.

---

## Comparative Insights & Summary

| Structural Class | Dominant Methods | Strategic Indicators | Key Pitfalls to Avoid |
| :--- | :--- | :--- | :--- |
| **Bilinear & Factored Forms** | Methods 1, 2, 4, 43, 49 | Equations with products of variables ($xy$) and linear terms, or standard factorable identities. | Forgetting to pair negative divisor branches; arithmetic errors during division. |
| **Elliptic & Higher Degree Curves** | Methods 5, 6, 7, 8, 38, 42 | Pure powers equal to polynomials in another variable: $y^2 = P(x)$ or $y^3 = P(x)$. | Missing small localized integer solutions outside the asymptotic squeeze region. |
| **Modular & Non-existence** | Methods 11, 12, 13, 31, 37, 47 | Forms such as $x^2 + y^2 = 4k+3$, $x^3+y^3+z^3 = 9k\pm 4$, or quadratic non-residues. | Testing insufficient moduli; failing to systematically check all residue combinations. |
| **Exponential & Prime-Power** | Methods 3, 22, 23, 24, 26, 28 | Variables appearing in exponents ($a^x + b^x = c^x$). | Overlooking parity conditions required before applying the Lifting the Exponent Lemma (LTE). |
| **Descent & Extremal Principles** | Methods 14, 15, 25, 39 | Homogeneous equations ($x^k + c y^k = d z^k$) or symmetric forms that can be rewritten as quadratics. | Setting up an incorrect descent metric; missing cases where roots are negative or zero. |
| **Number Fields & Algebraic Domains** | Methods 18, 19, 20, 21, 34 | Binary quadratic forms $x^2 + Dy^2$ and Pell's equations $x^2 - Dy^2 = \pm 1$. | Applying prime factorization in domains $\mathbb{Z}[\sqrt{-D}]$ that lack unique factorization ($D \ge 3$ square-free). |