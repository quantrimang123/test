# Advanced Diophantine Equations for Gifted Students

## Overview & Core Principles

Diophantine equations are polynomial equations where solutions are sought only among integers. The study of these equations forms a fundamental cornerstone of number theory, demanding a blend of algebraic manipulation, number-theoretic insights, and logical deduction. For gifted students preparing for National Mathematics Olympiads, mastering diverse approaches to Diophantine equations is paramount.

The core principles underlying the solution of Diophantine equations include:

1.  **The Fundamental Theorem of Arithmetic (Unique Prime Factorization)**: Every integer greater than 1 can be represented uniquely as a product of prime numbers. This allows for analysis of factors, divisibility, and prime powers.
2.  **Modular Arithmetic**: Analyzing equations modulo a specific integer $n$ can reveal crucial properties of potential solutions or demonstrate the absence of solutions.
3.  **Algebraic Identities and Transformations**: Proficient use of algebraic identities (e.g., difference of squares, sum/difference of cubes, completing the square) can transform complex equations into more manageable forms, often leading to factorized expressions or sums of squares.
4.  **Inequalities and Bounding Arguments**: Leveraging inequalities can restrict the search space for integer solutions, often reducing an infinite set of possibilities to a finite, testable collection.
5.  **Principle of Extreme Value and Infinite Descent**: These powerful proof techniques are frequently employed to demonstrate the non-existence of non-trivial solutions or to prove that only trivial solutions exist. They rely on assuming a solution with a minimal (or maximal) property and deriving a contradiction by constructing an even "smaller" solution.
6.  **Parity and Divisibility**: Simple considerations of even/odd numbers or divisibility by small integers (like 3 or 4) can often yield significant deductions.

This document will present a selection of master problems and demonstrate exactly 15 distinct, rigorous solution methods, encouraging a multifaceted approach to problem-solving.

## 15 Distinct Solution Methods

We will illustrate these methods using the following representative Diophantine equations:

*   **Problem A:** Find all integer solutions $(x, y)$ to $xy + 3x - 2y = 11$.
*   **Problem B:** Find all integer solutions $(x, y)$ to $x^2 + y^2 - 4x - 6y + 13 = 0$.
*   **Problem C:** Find all integer solutions $(x, y)$ to $x^2 - 4xy + 5y^2 = 16$.
*   **Problem D:** Find all non-negative integer solutions $(x, y, z)$ to $x^2 + y^2 = 3z^2$.
*   **Problem E:** Find all integer solutions $(x, y)$ to $x^3 - y^3 = 91$.

---

### Method 1: Factoring by Grouping (for Problem A)

This method involves algebraically manipulating the equation to express it as a product of linear terms equaling an integer constant. This transforms the problem into analyzing factors of a fixed integer.

**Problem A:** Find all integer solutions $(x, y)$ to $xy + 3x - 2y = 11$.

**Solution:**
We aim to factor the left-hand side into the form $(x+a)(y+b)$.
Observe the terms $xy + 3x - 2y$. We can group terms involving $x$: $x(y+3)$. To complete the factorization, we need a term $-2(y+3)$.
$$xy + 3x - 2y = 11$$
$$x(y+3) - 2y = 11$$
To introduce the $y+3$ factor in the second term, we add and subtract $2 \times 3 = 6$:
$$x(y+3) - 2(y+3) + 6 = 11$$
$$(x-2)(y+3) = 11 - 6$$
$$(x-2)(y+3) = 5$$
Since $x$ and $y$ are integers, $x-2$ and $y+3$ must also be integers. They are factors of $5$.
The integer factors of $5$ are $(1, 5), (5, 1), (-1, -5), (-5, -1)$.
We set up a system for each pair:
1.  $x-2 = 1 \implies x = 3$
    $y+3 = 5 \implies y = 2$
    Solution: $(3, 2)$
2.  $x-2 = 5 \implies x = 7$
    $y+3 = 1 \implies y = -2$
    Solution: $(7, -2)$
3.  $x-2 = -1 \implies x = 1$
    $y+3 = -5 \implies y = -8$
    Solution: $(1, -8)$
4.  $x-2 = -5 \implies x = -3$
    $y+3 = -1 \implies y = -4$
    Solution: $(-3, -4)$

Thus, the integer solutions are $(3, 2), (7, -2), (1, -8), (-3, -4)$.

---

### Method 2: Completing the Square (for Problem B)

This technique transforms a quadratic Diophantine equation into a sum of squares, which is particularly effective when the sum is equal to zero or a small positive integer.

**Problem B:** Find all integer solutions $(x, y)$ to $x^2 + y^2 - 4x - 6y + 13 = 0$.

**Solution:**
We regroup terms and complete the square for $x$ and $y$ independently.
$$ (x^2 - 4x) + (y^2 - 6y) + 13 = 0 $$
To complete the square for $x^2 - 4x$, we add $(4/2)^2 = 4$.
To complete the square for $y^2 - 6y$, we add $(6/2)^2 = 9$.
$$ (x^2 - 4x + 4) + (y^2 - 6y + 9) + 13 - 4 - 9 = 0 $$
$$ (x-2)^2 + (y-3)^2 + 0 = 0 $$
$$ (x-2)^2 + (y-3)^2 = 0 $$
Since $x$ and $y$ are integers, $(x-2)$ and $(y-3)$ are integers. The square of any real number is non-negative. For the sum of two non-negative terms to be zero, both terms must individually be zero.
Therefore:
$$ (x-2)^2 = 0 \implies x-2 = 0 \implies x = 2 $$
$$ (y-3)^2 = 0 \implies y-3 = 0 \implies y = 3 $$
The unique integer solution is $(2, 3)$.

---

### Method 3: Bounds by Inequalities (for Problem B)

This method utilizes the properties of inequalities (such as non-negativity of squares) to establish bounds for the variables, thereby limiting the search space to a finite number of cases.

**Problem B:** Find all integer solutions $(x, y)$ to $x^2 + y^2 - 4x - 6y + 13 = 0$.

**Solution:**
As derived in Method 2, the equation can be rewritten as:
$$ (x-2)^2 + (y-3)^2 = 0 $$
Since $x, y \in \mathbb{Z}$, $(x-2) \in \mathbb{Z}$ and $(y-3) \in \mathbb{Z}$.
We know that for any real number $a$, $a^2 \ge 0$.
Thus, $(x-2)^2 \ge 0$ and $(y-3)^2 \ge 0$.
The equation states that the sum of these two non-negative terms is $0$. The only way for this to occur is if both terms are simultaneously $0$.
$$(x-2)^2 = 0 \quad \text{and} \quad (y-3)^2 = 0$$
From $(x-2)^2 = 0$, we have $x-2 = 0$, which implies $x = 2$.
From $(y-3)^2 = 0$, we have $y-3 = 0$, which implies $y = 3$.
Therefore, the only integer solution is $(2, 3)$. This method explicitly highlights the use of the non-negativity property as a bounding technique.

---

### Method 4: Modulo Arithmetic (for Problem D)

Modular arithmetic is a powerful tool to constrain possible values or prove the non-existence of solutions by analyzing the equation's behavior modulo certain integers (often primes or composite numbers related to coefficients).

**Problem D:** Find all non-negative integer solutions $(x, y, z)$ to $x^2 + y^2 = 3z^2$.

**Solution:**
We analyze the equation modulo $3$.
The squares modulo $3$ are:
$0^2 \equiv 0 \pmod 3$
$1^2 \equiv 1 \pmod 3$
$2^2 \equiv 4 \equiv 1 \pmod 3$
So, for any integer $k$, $k^2 \pmod 3$ can only be $0$ or $1$.
The equation is $x^2 + y^2 = 3z^2$.
Taking this equation modulo $3$:
$$ x^2 + y^2 \equiv 3z^2 \pmod 3 $$
$$ x^2 + y^2 \equiv 0 \pmod 3 $$
Given that $x^2, y^2 \in \{0, 1\} \pmod 3$, for their sum to be $0 \pmod 3$, the only possibility is that both $x^2 \equiv 0 \pmod 3$ and $y^2 \equiv 0 \pmod 3$.
If $x^2 \equiv 0 \pmod 3$, then $x$ must be a multiple of $3$, i.e., $x \equiv 0 \pmod 3$.
If $y^2 \equiv 0 \pmod 3$, then $y$ must be a multiple of $3$, i.e., $y \equiv 0 \pmod 3$.
So, $x$ and $y$ must both be divisible by $3$.

---

### Method 5: Parity Analysis (for Problem D, extension of Method 4)

Parity analysis focuses on whether variables are even or odd, or more generally, their divisibility by 2 (or other small primes). It is a special case of modular arithmetic but is often distinct in application, leading to specific deductions.

**Problem D:** Find all non-negative integer solutions $(x, y, z)$ to $x^2 + y^2 = 3z^2$.

**Solution:**
From Method 4, we established that $x \equiv 0 \pmod 3$ and $y \equiv 0 \pmod 3$.
Let $x = 3x_1$ and $y = 3y_1$ for some non-negative integers $x_1, y_1$.
Substitute these into the original equation:
$$ (3x_1)^2 + (3y_1)^2 = 3z^2 $$
$$ 9x_1^2 + 9y_1^2 = 3z^2 $$
Dividing by $3$:
$$ 3x_1^2 + 3y_1^2 = z^2 $$
This equation implies that $z^2$ must be divisible by $3$. If $z^2$ is divisible by $3$, then $z$ itself must be divisible by $3$.
Let $z = 3z_1$ for some non-negative integer $z_1$.
Substitute this back:
$$ 3x_1^2 + 3y_1^2 = (3z_1)^2 $$
$$ 3x_1^2 + 3y_1^2 = 9z_1^2 $$
Dividing by $3$:
$$ x_1^2 + y_1^2 = 3z_1^2 $$
This shows that if $(x, y, z)$ is a solution, then $(x/3, y/3, z/3)$ is also a solution. This is a crucial step towards Method 7. The parity/divisibility analysis here specifically shows that all components must be multiples of 3.

---

### Method 6: Discriminant Method (for Problem C)

When a Diophantine equation can be rearranged into a quadratic form with respect to one variable, the discriminant of that quadratic must be a perfect square for integer solutions to exist.

**Problem C:** Find all integer solutions $(x, y)$ to $x^2 - 4xy + 5y^2 = 16$.

**Solution:**
Treat the equation as a quadratic in $x$:
$$ x^2 - (4y)x + (5y^2 - 16) = 0 $$
For $x$ to be an integer, the discriminant $D$ of this quadratic equation must be a perfect square. Let $D = k^2$ for some non-negative integer $k$.
$$ D = (-4y)^2 - 4(1)(5y^2 - 16) $$
$$ D = 16y^2 - 20y^2 + 64 $$
$$ D = 64 - 4y^2 $$
So, we require $64 - 4y^2 = k^2$.
$$ 4(16 - y^2) = k^2 $$
This implies that $4(16 - y^2)$ must be a perfect square. Since $4$ is a perfect square, $16 - y^2$ must also be a perfect square. Let $16 - y^2 = m^2$ for some non-negative integer $m$.
$$ y^2 + m^2 = 16 $$
Since $y$ is an integer, $y^2 \ge 0$. Also, $m^2 \ge 0$.
The possible integer values for $y$ such that $y^2 \le 16$ are $y \in \{-4, -3, -2, -1, 0, 1, 2, 3, 4\}$.
We test these values:
*   If $y=0$, $m^2 = 16 \implies m=4$.
*   If $y=\pm 1$, $m^2 = 15$ (not a perfect square).
*   If $y=\pm 2$, $m^2 = 12$ (not a perfect square).
*   If $y=\pm 3$, $m^2 = 7$ (not a perfect square).
*   If $y=\pm 4$, $m^2 = 0 \implies m=0$.

So, possible values for $y$ are $0, \pm 4$.

Case 1: $y = 0$.
$x^2 - 4x(0) + 5(0)^2 = 16 \implies x^2 = 16 \implies x = \pm 4$.
Solutions: $(4, 0), (-4, 0)$.

Case 2: $y = 4$.
$x^2 - 4x(4) + 5(4)^2 = 16 \implies x^2 - 16x + 80 = 16 \implies x^2 - 16x + 64 = 0$.
$(x-8)^2 = 0 \implies x = 8$.
Solution: $(8, 4)$.

Case 3: $y = -4$.
$x^2 - 4x(-4) + 5(-4)^2 = 16 \implies x^2 + 16x + 80 = 16 \implies x^2 + 16x + 64 = 0$.
$(x+8)^2 = 0 \implies x = -8$.
Solution: $(-8, -4)$.

The integer solutions are $(4, 0), (-4, 0), (8, 4), (-8, -4)$.

---

### Method 7: Method of Infinite Descent (for Problem D)

This powerful proof technique, often attributed to Fermat, is used to show that no non-trivial solutions exist or that only a specific trivial solution exists. It works by assuming a minimal non-trivial solution and then constructing an even "smaller" non-trivial solution, leading to a contradiction.

**Problem D:** Find all non-negative integer solutions $(x, y, z)$ to $x^2 + y^2 = 3z^2$.

**Solution:**
We seek non-negative integer solutions. The trivial solution $(0, 0, 0)$ is clearly valid.
Assume there exists a non-trivial solution $(x, y, z)$ where at least one of $x, y, z$ is non-zero.
From Method 4 and 5, we know that if $(x, y, z)$ is a solution, then $x, y, z$ must all be divisible by $3$.
Let $x = 3x_1$, $y = 3y_1$, and $z = 3z_1$ for some non-negative integers $x_1, y_1, z_1$.
Substitute these into the original equation:
$$ (3x_1)^2 + (3y_1)^2 = 3(3z_1)^2 $$
$$ 9x_1^2 + 9y_1^2 = 3(9z_1^2) $$
$$ 9x_1^2 + 9y_1^2 = 27z_1^2 $$
Divide the entire equation by $9$:
$$ x_1^2 + y_1^2 = 3z_1^2 $$
This implies that if $(x, y, z)$ is a solution, then $(x_1, y_1, z_1) = (x/3, y/3, z/3)$ is also a solution.
If $(x, y, z)$ is a non-trivial solution (i.e., not all zeros), then $(x_1, y_1, z_1)$ is also a non-trivial solution, and $z_1 = z/3 < z$ (assuming $z > 0$).
We can repeat this process indefinitely, generating an infinite sequence of non-negative integer solutions: $(x, y, z) \to (x_1, y_1, z_1) \to (x_2, y_2, z_2) \to \dots$ where $z > z_1 > z_2 > \dots \ge 0$.
However, a strictly decreasing sequence of non-negative integers must terminate. This can only happen if the sequence reaches $0$.
The only way for this infinite descent to terminate is if $z=0$. If $z=0$, then $x^2 + y^2 = 0$. Since $x, y$ are integers, this implies $x=0$ and $y=0$.
Thus, the only non-negative integer solution is $(0, 0, 0)$.

---

### Method 8: Factoring using Algebraic Identities and Systems (for Problem E)

This method applies algebraic identities (like sum/difference of cubes, difference of squares) to factor equations into multiple expressions, which then form a system of equations based on factors of a constant.

**Problem E:** Find all integer solutions $(x, y)$ to $x^3 - y^3 = 91$.

**Solution:**
We use the algebraic identity for the difference of cubes: $a^3 - b^3 = (a-b)(a^2+ab+b^2)$.
So, the equation becomes:
$$ (x-y)(x^2+xy+y^2) = 91 $$
Let $A = x-y$ and $B = x^2+xy+y^2$. Then $AB = 91$.
We need to find integer factors of $91$. The prime factorization of $91$ is $7 \times 13$.
The integer factor pairs of $91$ are:
$(1, 91), (7, 13), (13, 7), (91, 1), (-1, -91), (-7, -13), (-13, -7), (-91, -1)$.

Now, we analyze the term $B = x^2+xy+y^2$. We can rewrite this term:
$$ B = x^2+xy+y^2 = (x-y/2)^2 + 3y^2/4 $$
Since $y^2 \ge 0$, we have $B \ge 0$. In fact, $B > 0$ unless $x=0$ and $y=0$, in which case $x^3-y^3=0 \ne 91$.
Therefore, $B$ must be a positive integer. This eliminates the negative factor pairs for $B$.
This leaves us with four cases:

Case 1: $A=1, B=91$.
$x-y = 1 \implies x = y+1$.
Substitute $x$ into $B$:
$(y+1)^2 + (y+1)y + y^2 = 91$
$y^2+2y+1 + y^2+y + y^2 = 91$
$3y^2+3y+1 = 91$
$3y^2+3y-90 = 0$
$y^2+y-30 = 0$
$(y+6)(y-5) = 0$
So, $y=5$ or $y=-6$.
If $y=5$, then $x=y+1=6$. Solution: $(6, 5)$.
If $y=-6$, then $x=y+1=-5$. Solution: $(-5, -6)$.

Case 2: $A=7, B=13$.
$x-y = 7 \implies x = y+7$.
Substitute $x$ into $B$:
$(y+7)^2 + (y+7)y + y^2 = 13$
$y^2+14y+49 + y^2+7y + y^2 = 13$
$3y^2+21y+49 = 13$
$3y^2+21y+36 = 0$
$y^2+7y+12 = 0$
$(y+3)(y+4) = 0$
So, $y=-3$ or $y=-4$.
If $y=-3$, then $x=y+7=4$. Solution: $(4, -3)$.
If $y=-4$, then $x=y+7=3$. Solution: $(3, -4)$.

Case 3: $A=13, B=7$.
$x-y = 13 \implies x = y+13$.
Substitute $x$ into $B$:
$(y+13)^2 + (y+13)y + y^2 = 7$
$y^2+26y+169 + y^2+13y + y^2 = 7$
$3y^2+39y+169 = 7$
$3y^2+39y+162 = 0$
$y^2+13y+54 = 0$
Discriminant $D = 13^2 - 4(1)(54) = 169 - 216 = -47 < 0$. No real solutions for $y$, thus no integer solutions.

Case 4: $A=91, B=1$.
$x-y = 91 \implies x = y+91$.
Substitute $x$ into $B$:
$(y+91)^2 + (y+91)y + y^2 = 1$
$3y^2 + 3(91)y + 91^2 = 1$
$3y^2 + 273y + 8281 = 1$
$3y^2 + 273y + 8280 = 0$
$y^2 + 91y + 2760 = 0$
Discriminant $D = 91^2 - 4(1)(2760) = 8281 - 11040 = -2759 < 0$. No real solutions for $y$, thus no integer solutions.

The integer solutions are $(6, 5), (-5, -6), (4, -3), (3, -4)$.

---

### Method 9: Casework based on Factors (for Problem A)

This method is a systematic way to explore all possibilities after an equation has been factored into the form $A \cdot B = k$. It involves listing all factor pairs of $k$ and solving the resulting systems.

**Problem A:** Find all integer solutions $(x, y)$ to $xy + 3x - 2y = 11$.

**Solution:**
From Method 1, we transformed the equation into $(x-2)(y+3) = 5$.
Let $P = x-2$ and $Q = y+3$. Since $x,y$ are integers, $P,Q$ must be integers.
We need to find all integer pairs $(P, Q)$ such that $P \cdot Q = 5$.
The integer factor pairs of $5$ are:
1.  $(P, Q) = (1, 5)$
2.  $(P, Q) = (5, 1)$
3.  $(P, Q) = (-1, -5)$
4.  $(P, Q) = (-5, -1)$

Now we set up and solve for $x$ and $y$ for each case:
1.  $x-2 = 1 \implies x = 3$
    $y+3 = 5 \implies y = 2$
    Solution: $(3, 2)$
2.  $x-2 = 5 \implies x = 7$
    $y+3 = 1 \implies y = -2$
    Solution: $(7, -2)$
3.  $x-2 = -1 \implies x = 1$
    $y+3 = -5 \implies y = -8$
    Solution: $(1, -8)$
4.  $x-2 = -5 \implies x = -3$
    $y+3 = -1 \implies y = -4$
    Solution: $(-3, -4)$

This systematic casework ensures all solutions derived from the factored form are found.

---

### Method 10: Using Divisibility Properties (for Problem A)

This method leverages properties of divisibility directly on the original equation or a partially rearranged form, often leading to constraints on variables or allowing for substitution.

**Problem A:** Find all integer solutions $(x, y)$ to $xy + 3x - 2y = 11$.

**Solution:**
Rearrange the equation to isolate one variable's factor:
$$ y(x-2) + 3x = 11 $$
We can deduce that $x-2$ must divide $3x-11$ (if $x-2 \ne 0$).
$$ y(x-2) = 11 - 3x $$
Since $y$ is an integer, $x-2$ must be a divisor of $11-3x$.
Let $k = x-2$. Then $x = k+2$.
$$ k \text{ divides } 11 - 3(k+2) $$
$$ k \text{ divides } 11 - 3k - 6 $$
$$ k \text{ divides } 5 - 3k $$
Since $k$ clearly divides $3k$, if $k$ divides $5-3k$, then $k$ must also divide $(5-3k) + 3k$.
$$ k \text{ divides } 5 $$
So, $x-2$ must be a divisor of $5$.
The divisors of $5$ are $\pm 1, \pm 5$.
1.  $x-2 = 1 \implies x = 3$. Substitute into $y(x-2) = 11-3x \implies y(1) = 11-3(3) \implies y = 2$. Solution: $(3, 2)$.
2.  $x-2 = -1 \implies x = 1$. Substitute into $y(x-2) = 11-3x \implies y(-1) = 11-3(1) \implies -y = 8 \implies y = -8$. Solution: $(1, -8)$.
3.  $x-2 = 5 \implies x = 7$. Substitute into $y(x-2) = 11-3x \implies y(5) = 11-3(7) \implies 5y = -10 \implies y = -2$. Solution: $(7, -2)$.
4.  $x-2 = -5 \implies x = -3$. Substitute into $y(x-2) = 11-3x \implies y(-5) = 11-3(-3) \implies -5y = 20 \implies y = -4$. Solution: $(-3, -4)$.
This method effectively utilizes the divisibility property $A|B \implies A|(B+CA)$ to reduce the expression to a constant divisor.

---

### Method 11: Rearrangement to Sum of Squares (for Problem C)

This method involves creatively rearranging terms, often through completing the square for a part of the expression, to obtain a sum of squares equal to a constant. This can simplify bounding arguments significantly.

**Problem C:** Find all integer solutions $(x, y)$ to $x^2 - 4xy + 5y^2 = 16$.

**Solution:**
We observe that the expression $x^2 - 4xy + 4y^2$ is a perfect square.
$$ x^2 - 4xy + 4y^2 + y^2 = 16 $$
$$ (x-2y)^2 + y^2 = 16 $$
Let $A = x-2y$. Then the equation becomes $A^2 + y^2 = 16$.
Since $A$ and $y$ are integers, $A^2$ and $y^2$ are non-negative integer perfect squares.
We need to find pairs of perfect squares that sum to $16$.
Possible perfect squares are $0, 1, 4, 9, 16$.
1.  If $y^2 = 0$, then $y = 0$.
    $A^2 = 16 \implies A = \pm 4$.
    If $A=4$, then $x-2y = 4 \implies x-2(0) = 4 \implies x = 4$. Solution: $(4, 0)$.
    If $A=-4$, then $x-2y = -4 \implies x-2(0) = -4 \implies x = -4$. Solution: $(-4, 0)$.
2.  If $y^2 = 1$, then $y = \pm 1$.
    $A^2 = 16-1 = 15$ (not a perfect square). No solutions here.
3.  If $y^2 = 4$, then $y = \pm 2$.
    $A^2 = 16-4 = 12$ (not a perfect square). No solutions here.
4.  If $y^2 = 9$, then $y = \pm 3$.
    $A^2 = 16-9 = 7$ (not a perfect square). No solutions here.
5.  If $y^2 = 16$, then $y = \pm 4$.
    $A^2 = 16-16 = 0 \implies A = 0$.
    If $y=4$, then $x-2y = 0 \implies x-2(4) = 0 \implies x = 8$. Solution: $(8, 4)$.
    If $y=-4$, then $x-2y = 0 \implies x-2(-4) = 0 \implies x = -8$. Solution: $(-8, -4)$.

The integer solutions are $(4, 0), (-4, 0), (8, 4), (-8, -4)$. This method effectively uses a partial completion of the square to simplify the structure.

---

### Method 12: Extreme Value Principle (for Problem D)

The Extreme Value Principle (or Principle of Minimal Element) is a formal proof technique often used in number theory. It states that any non-empty set of positive integers has a smallest element. It's closely related to infinite descent but focuses on contradicting the minimality assumption directly.

**Problem D:** Find all non-negative integer solutions $(x, y, z)$ to $x^2 + y^2 = 3z^2$.

**Solution:**
We are looking for non-negative integer solutions. The solution $(0, 0, 0)$ is trivial.
Assume there exists at least one non-trivial solution $(x, y, z)$ where not all components are zero.
Consider the set $S = \{z \in \mathbb{N}_0 \mid \exists x,y \in \mathbb{N}_0 \text{ such that } x^2+y^2=3z^2 \text{ and } (x,y,z) \ne (0,0,0)\}$.
Since we assume non-trivial solutions exist, $S$ is non-empty. By the Principle of Minimal Element, $S$ must have a smallest element, let's call it $z_0$.
Let $(x_0, y_0, z_0)$ be a solution with this minimal positive $z_0$.
From Method 4, analyzing the equation modulo $3$: $x_0^2 + y_0^2 \equiv 0 \pmod 3$. This implies $x_0 \equiv 0 \pmod 3$ and $y_0 \equiv 0 \pmod 3$.
So, $x_0 = 3x_1$ and $y_0 = 3y_1$ for some non-negative integers $x_1, y_1$.
Substitute these into the equation for $(x_0, y_0, z_0)$:
$$ (3x_1)^2 + (3y_1)^2 = 3z_0^2 $$
$$ 9x_1^2 + 9y_1^2 = 3z_0^2 $$
$$ 3(x_1^2 + y_1^2) = z_0^2 $$
This implies $z_0^2$ must be divisible by $3$. If $z_0^2$ is divisible by $3$, then $z_0$ must also be divisible by $3$.
So, $z_0 = 3z_1$ for some non-negative integer $z_1$.
Substitute this back:
$$ 3(x_1^2 + y_1^2) = (3z_1)^2 $$
$$ 3(x_1^2 + y_1^2) = 9z_1^2 $$
$$ x_1^2 + y_1^2 = 3z_1^2 $$
Thus, $(x_1, y_1, z_1)$ is also a solution to the original equation.
Furthermore, since $z_0 = 3z_1$ and $z_0 > 0$, we have $z_1 = z_0/3 < z_0$.
This means $z_1$ is a smaller non-negative integer in $S$. But we assumed $z_0$ was the *smallest* element in $S$. This is a contradiction.
The only way to avoid this contradiction is if our initial assumption that $S$ is non-empty is false. Therefore, there are no non-trivial solutions. The only solution is $(0, 0, 0)$.

---

### Method 13: Graphical Interpretation (for Problem B)

For equations involving two variables, a graphical interpretation can provide intuition and help visualize the integer points on the curve or surface defined by the equation. While not a standalone proof, it can guide the solution process or confirm the nature of solutions.

**Problem B:** Find all integer solutions $(x, y)$ to $x^2 + y^2 - 4x - 6y + 13 = 0$.

**Solution:**
From Method 2, we transformed the equation into $(x-2)^2 + (y-3)^2 = 0$.
In Cartesian coordinates, an equation of the form $(x-h)^2 + (y-k)^2 = r^2$ represents a circle centered at $(h, k)$ with radius $r$.
In this case, $(h, k) = (2, 3)$ and $r^2 = 0$, which means $r=0$.
A circle with radius $0$ is a degenerate circle that consists of a single point, its center.
Therefore, the only point that satisfies this equation is $(x, y) = (2, 3)$.
Since this point has integer coordinates, $(2, 3)$ is the unique integer solution.
This geometric perspective provides an immediate understanding of why there is only one solution and directly identifies it.

---

### Method 14: Approximation and Bounding using Square Roots (for Problem C)

This method involves isolating squared terms and then using square root properties to establish numerical bounds on variables, reducing the infinite search space to a finite, manageable range.

**Problem C:** Find all integer solutions $(x, y)$ to $x^2 - 4xy + 5y^2 = 16$.

**Solution:**
From Method 11, we transformed the equation to $(x-2y)^2 + y^2 = 16$.
Let $A = x-2y$. So, $A^2 + y^2 = 16$.
Since $A$ and $y$ are integers, $A^2 \ge 0$ and $y^2 \ge 0$.
From $y^2 = 16 - A^2$, we must have $y^2 \le 16$.
Taking the square root of both sides, $ \sqrt{y^2} \le \sqrt{16} $, which implies $|y| \le 4$.
Since $y$ is an integer, $y$ can only take values in the set $\{-4, -3, -2, -1, 0, 1, 2, 3, 4\}$.
We systematically test these values:
*   If $y=0$: $A^2 + 0^2 = 16 \implies A^2 = 16 \implies A = \pm 4$.
    If $A=4$: $x-2(0) = 4 \implies x=4$. Solution: $(4,0)$.
    If $A=-4$: $x-2(0) = -4 \implies x=-4$. Solution: $(-4,0)$.
*   If $y=\pm 1$: $A^2 + (\pm 1)^2 = 16 \implies A^2+1=16 \implies A^2=15$. No integer $A$.
*   If $y=\pm 2$: $A^2 + (\pm 2)^2 = 16 \implies A^2+4=16 \implies A^2=12$. No integer $A$.
*   If $y=\pm 3$: $A^2 + (\pm 3)^2 = 16 \implies A^2+9=16 \implies A^2=7$. No integer $A$.
*   If $y=\pm 4$: $A^2 + (\pm 4)^2 = 16 \implies A^2+16=16 \implies A^2=0 \implies A=0$.
    If $y=4$: $x-2(4) = 0 \implies x=8$. Solution: $(8,4)$.
    If $y=-4$: $x-2(-4) = 0 \implies x=-8$. Solution: $(-8,-4)$.

This method systematically uses the boundedness property derived from the square root to enumerate all possible integer values for $y$, thereby completing the solution.

---

### Method 15: Transformation to a Standard Form (for Problem C)

This method involves introducing new variables to transform the given Diophantine equation into a more recognizable or simpler standard form, which might have known solutions or easier analysis.

**Problem C:** Find all integer solutions $(x, y)$ to $x^2 - 4xy + 5y^2 = 16$.

**Solution:**
From Method 11, we cleverly transformed the equation to $(x-2y)^2 + y^2 = 16$.
Now, let's introduce new integer variables to simplify this form.
Let $X = x-2y$ and $Y = y$.
With this substitution, the equation becomes:
$$ X^2 + Y^2 = 16 $$
This is a standard Diophantine equation representing points on a circle centered at the origin with radius $4$. We need to find integer coordinates $(X, Y)$ that lie on this circle.
We list integer pairs $(X, Y)$ whose squares sum to $16$:
Since $X^2 \ge 0$ and $Y^2 \ge 0$, we must have $X^2 \le 16$ and $Y^2 \le 16$.
This implies $|X| \le 4$ and $|Y| \le 4$.
Possible perfect squares for $X^2$ and $Y^2$ are $0, 1, 4, 9, 16$.
The only pairs $(X^2, Y^2)$ that sum to $16$ are:
1.  $(X^2, Y^2) = (0, 16) \implies X = 0, Y = \pm 4$.
2.  $(X^2, Y^2) = (16, 0) \implies X = \pm 4, Y = 0$.

Now, we convert these solutions $(X, Y)$ back to $(x, y)$ using the transformation $Y=y$ and $X=x-2y$:
*   If $(X, Y) = (0, 4)$: $y=4$. $x-2(4)=0 \implies x=8$. Solution: $(8, 4)$.
*   If $(X, Y) = (0, -4)$: $y=-4$. $x-2(-4)=0 \implies x=-8$. Solution: $(-8, -4)$.
*   If $(X, Y) = (4, 0)$: $y=0$. $x-2(0)=4 \implies x=4$. Solution: $(4, 0)$.
*   If $(X, Y) = (-4, 0)$: $y=0$. $x-2(0)=-4 \implies x=-4$. Solution: $(-4, 0)$.

The integer solutions are $(8, 4), (-8, -4), (4, 0), (-4, 0)$. This method clearly distinguishes the act of defining new variables for simplification.

---

## Comparative Insights & Summary

Mastering Diophantine equations for Olympiads requires flexibility and strategic thinking in choosing the most efficient method. Here's a brief guide:

*   **Factoring-based methods (1, 9, 10, 8)** are generally the first line of attack for polynomial equations. If an equation can be factored into a product equaling a constant, a finite set of possibilities emerges. Method 1 (grouping) is for simple linear factors, Method 8 for advanced algebraic identities leading to systems. Method 9 (casework) is a systematic follow-up to factoring. Method 10 (divisibility) offers an alternative path to constraint derivation without full factorization.
*   **Quadratic forms and sums of squares (2, 3, 11, 14, 15)** are frequently encountered. Method 2 (completing the square) is direct for $A^2+B^2=0$. Method 11 (rearrangement to sum of squares) and Method 15 (transformation to standard form like $X^2+Y^2=k$) are powerful for general quadratic Diophantine equations, converting them into forms amenable to bounding. Method 14 (bounding with square roots) is the analytical step for these forms, and Method 3 (bounds by non-negativity) is the underlying principle.
*   **Discriminant method (6)** is invaluable when one variable can be seen as a root of a quadratic equation in terms of the other. It reduces the problem to checking if a specific expression is a perfect square.
*   **Number theoretic methods (4, 5, 7, 12)** are crucial for equations where algebraic manipulation is difficult or insufficient. Method 4 (modulo arithmetic) and Method 5 (parity) are excellent for quickly narrowing down possibilities or proving non-existence. Method 7 (infinite descent) and Method 12 (extreme value principle) are sophisticated proof techniques, typically used for homogeneous equations to prove that only trivial solutions exist.
*   **Graphical interpretation (13)**, while not a rigorous proof method on its own, offers a quick visual understanding of the solution set and can inform other methods, especially for equations representing conic sections.

In summary, a strong Olympiad competitor will not rely on a single approach but rather cultivate a rich toolkit of methods. The ability to recognize the structure of an equation and select the most appropriate method, or even combine several, is the hallmark of a master problem solver. Iterative practice across diverse problems, applying these distinct perspectives, is key to developing this expertise.