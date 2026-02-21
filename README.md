# A Note on Fermat's Last Theorem

**Author:** Frank Vega  
**Affiliation:** Information Physics Institute, 840 W 67th St, Hialeah, FL 33012, USA  
**Email:** vega.frank@gmail.com  
**ORCID:** 0000-0001-8210-4126  

--- 

## Abstract

Around 1637, Pierre de Fermat famously wrote in the margin of a book that he had a proof showing the equation $a^n + b^n = c^n$ has no positive integer solutions for exponents $n$ greater than 2. This statement, now known as Fermat's Last Theorem, remained unproven for centuries despite the efforts of countless mathematicians. Andrew Wiles's work in 1994 finally provided a rigorous proof of Fermat's Last Theorem. However, Wiles's proof relied on advanced mathematical techniques far beyond the scope of Fermat's time, raising questions about whether Fermat could have truly possessed a proof using only the methods available to him. Wiles's achievement was widely celebrated, and he was awarded the Abel Prize in 2016; the citation described his proof as a "stunning advance" in mathematics. Combining short and elementary tools, we prove the *Beal conjecture*, a well-known generalization of Fermat's Last Theorem. The present work potentially offers a solution closer in spirit to Fermat's original idea.

**Keywords:** Generalized Fermat equation; p-adic valuation; Lifting The Exponent Lemma; coprimality

**MSC:** 11D41, 11A41, 11A05, 11A07

---

## 1. Introduction

Fermat's Last Theorem, first stated by Pierre de Fermat in the $17^{\mathrm{th}}$ century, asserts that the equation

$$
a^{n} + b^{n} = c^{n}
$$

has no solutions in positive integers whenever $n \in \mathbb{N}$ is greater than 2. In a margin note left on his personal copy of Diophantus's *Arithmetica*, Fermat claimed to have a proof which the margin was too small to contain [[Fer91]](#References). Later mathematicians such as Leonhard Euler and Sophie Germain made significant contributions to the study of the problem [[Eur12, Ger16]](#References), and $20^{\mathrm{th}}$-century work by Ernst Kummer established the theorem for a specific class of prime exponents [[Kum47]](#References). A complete solution, however, remained elusive for more than three centuries.

Finally, in 1994, Andrew Wiles announced a proof of Fermat's Last Theorem. His argument was complex and multifaceted, drawing on advanced topics such as the theory of elliptic curves, which lay entirely beyond the mathematical landscape of Fermat's time. After some initial gaps were repaired, Wiles's work was hailed as the long-awaited resolution of the problem [[Wil95]](#References) and described as a "stunning advance" in the citation for his Abel Prize in 2016. The proof also established much of the Taniyama—Shimura conjecture, subsequently known as the modularity theorem, and opened up powerful new approaches to numerous other problems via modularity lifting techniques [[Rib95]](#References). The techniques employed by Wiles are ostensibly remote from any proof Fermat could have had in mind, in terms of scope, complexity, and the novelty of the tools involved—many of which were only developed in the $20^{\mathrm{th}}$ century.

In 1993, Andrew Beal, an American amateur mathematician and banker, formulated a conjecture while exploring generalizations of Fermat's Last Theorem. Beal first publicly presented the conjecture together with a prize of \$5,000 for a proof or counterexample. This prize has since been raised several times and is currently held by the American Mathematical Society (AMS) at \$1,000,000. The *Beal conjecture* states that if

$$
A^{x} + B^{y} = C^{z},
$$

where $A$, $B$, $C$, $x$, $y$, $z$ are positive integers with $x, y, z > 2$, then $A$, $B$, and $C$ must share a common prime factor. Equivalently, there are no solutions to the above equation with $A$, $B$, and $C$ pairwise coprime [[BE97]](#References). Fermat's Last Theorem arises as the special case $x = y = z$.

The argument is by contradiction. Assuming $A^x + B^y = C^z$ holds with $\gcd(A,B,C) = 1$ and $x, y, z > 2$, the three bases $A$, $B$, $C$ are pairwise coprime, so at most one of them is divisible by an odd prime $p$. We treat three symmetric cases depending on which base is divisible by $p$. In each case, we let $m$ denote the p-adic valuation of the divisible term and raise both sides of an appropriately rearranged equation to the power $p^m$. On the one hand, the p-adic valuation of the resulting left-hand side equals $m \cdot p^m$, which is greater than $1$. On the other hand, an explicit analysis of the binomial expansion of the right-hand side—using a precise formula for the p-adic valuation of central binomial coefficients—shows that the valuation of the right-hand side is equal to $1$. This discrepancy yields a contradiction in every case, completing the proof. The same argument immediately yields Fermat's Last Theorem as a corollary.

Recent years have witnessed significant computational progress in tackling the Beal conjecture. Peter Norvig, a Google research director, carried out an exhaustive search for counterexamples and ruled out their existence for $x, y, z \le 7$ and $A, B, C \le 250{,}000$, as well as for $x, y, z \le 100$ and $A, B, C \le 10{,}000$ [[PN17]](#References). Our proof goes further by showing that no counterexample can exist for *any* values of the parameters.

---

## 2. Background and Ancillary Results

We collect here all notation and auxiliary results needed for the proof.

**Notation.** As usual, $d \mid n$ means that the integer $d$ divides the integer $n$, and $d \nmid n$ means that $d$ does not divide $n$. We write $\gcd(a, b)$ for the greatest common divisor of $a$ and $b$.

**Definition 2.1.** Let $p$ be a prime and $n \in \mathbb{Z} \setminus \\{0\\}$. The $p$-adic valuation, denoted $v_p(n)$, is the highest integer $e \geq 0$ such that $p^e$ divides $n$. By convention, $v_p(0) = +\infty$.

**Proposition 2.2** (Lifting The Exponent Lemma for odd primes [[Manea2006]](#References)). Let $p$ be an odd prime and let $x,y$ be integers such that $p \nmid x$ and $p \nmid y$.

1. If $p \mid (x - y)$, then for every positive integer $k$,
$$\nu_p(x^k - y^k) = \nu_p(x - y) + \nu_p(k).$$

2. If $p \mid (x + y)$ and $k$ is odd, then
$$\nu_p(x^k + y^k) = \nu_p(x + y) + \nu_p(k).$$

**Proposition 2.3** (p-adic valuation of binomial coefficients [[Gra94]](#References)). Let $p$ be a prime number and $m$ be a positive integer. For any integer $k$ such that $1 \leq k < p^m$, the $p$-adic valuation of the binomial coefficient $\binom{p^m}{k}$ is given by:

$$\nu_p \left( \binom{p^m}{k} \right) = m - \nu_p(k).$$

In particular:
- If $\nu_p(k) < m-1$ (i.e., $k \ne p^{m-1}$), then $\nu_p\left(\tbinom{p^m}{k}\right) \ge 2$.
- If $\nu_p(k) = m-1$ (i.e., $k = p^{m-1}$, the unique such index), then $\nu_p\left(\tbinom{p^m}{p^{m-1}}\right) = 1$.

These statements together provide the arithmetic machinery used in the proof.

---

## 3. Main Result

We are now ready to state and prove the main result.

**Theorem 3.1** (Beal Conjecture). Let $A$, $B$, $C$, $x$, $y$, $z$ be positive integers with $x, y, z > 2$. If

$$A^x + B^y = C^z,$$

then $A$, $B$, and $C$ have a common prime factor. Equivalently, there are no solutions to the equation above with $\gcd(A, B, C) = 1$.

**Proof.** Suppose, for contradiction, that there exist positive integers $A$, $B$, $C$, $x$, $y$, $z$ with $x, y, z > 2$, $\gcd(A, B, C) = 1$, and

$$(*) \qquad A^x + B^y = C^z.$$

Since $\gcd(A, B, C) = 1$, the three integers $A$, $B$, $C$ are pairwise coprime. Suppose that $p$ is an odd prime with $p \mid ABC$. In particular, at most one of them can be divisible by $p$ (if two were both divisible by $p$, their gcd would be divisible by $p$, contradicting coprimality). We consider the three symmetric cases.

### Case 1: $p \mid C$ (so $p \nmid A$ and $p \nmid B$)

**Step 1: Setting the valuation parameter.**
Since $p \mid C$, $C^z$ is divisible by $p$. Write

$$m = \nu_p(C^z) \ge 3.$$

(The lower bound $m \ge 3$ follows from $z \ge 3$ and $\nu_p(C) \ge 1$, giving $\nu_p(C^z) = z\,\nu_p(C) \ge 3$.)

**Step 2: Raising both sides to the power $p^m$.**
Starting from $A^x + B^y = C^z$, raise both sides to the power $p^m$:

$$(1) \qquad \left(C^z\right)^{p^m} = \left(A^x + B^y\right)^{p^m}.$$

**Left-hand side valuation.** By definition of $m = \nu_p(C^z)$, we can write $C^z = p^m \cdot Q$ where $Q$ is an integer and $p \nmid Q$. Therefore

$$\left(C^z\right)^{p^m} = p^{m \cdot p^m} \cdot Q^{p^m}, \qquad p \nmid Q,$$

so

$$(L) \qquad \nu_p\left(\left(C^z\right)^{p^m}\right) = m \cdot p^m.$$

**Step 3: Expanding the right-hand side via the binomial theorem.**
Since $p \nmid A^x$ and $p \nmid B^y$ (as $p \nmid A$ and $p \nmid B$), the binomial expansion gives

$$\left(A^x + B^y\right)^{p^m} = \sum_{k=0}^{p^m} \binom{p^m}{k} \left(A^x\right)^k \left(B^y\right)^{p^m - k}.$$

We analyze the p-adic valuation of each term separately.

*Endpoint terms* ($k = 0$ and $k = p^m$).

$$k = 0\colon\quad \left(B^y\right)^{p^m}, \qquad k = p^m\colon\quad \left(A^x\right)^{p^m}.$$

Both $p \nmid A^x$, $p \nmid B^y$ and $p \mid A^x + B^y$, so by Proposition 2.2,

$$\nu_p\left(\left(A^x\right)^{p^m} + \left(B^y\right)^{p^m}\right) = \nu_p\left(A^x +B^y\right) + \nu_p\left(p^m\right) = \nu_p\left(C^{z}\right) + m = 2m.$$

*Interior terms* ($1 \le k \le p^m - 1$).
For each such $k$, since $p \nmid A^x$ and $p \nmid B^y$, the only p-power factor comes from the binomial coefficient, so

$$\nu_p\left(\binom{p^m}{k}\left(A^x\right)^k\left(B^y\right)^{p^m-k}\right) = \nu_p\left(\binom{p^m}{k}\right) = m - \nu_p(k),$$

by Proposition 2.3. Among all interior indices $k$:
- For $\nu_p(k) \le m - 2$ (i.e., $k \ne p^{m-1}$): the valuation is $m - \nu_p(k) \ge 2$.
- For $\nu_p(k) = m - 1$ (i.e., $k = p^{m-1}$, which is the unique such index): the valuation is $m - (m-1) = 1$.

Hence there is exactly one interior term of valuation 1, namely the term with $k = p^{m-1}$:

$$T_{\mathrm{mid}} = \binom{p^m}{p^{m-1}} \left(A^x\right)^{p^{m-1}} \left(B^y\right)^{p^m - p^{m-1}}.$$

All other interior terms have valuation at least 2.

**Step 4: Computing the total valuation of the right-hand side.**
We isolate the three contributions:

$$\left(A^x + B^y\right)^{p^m} = \underbrace{\left(A^x\right)^{p^m} + \left(B^y\right)^{p^m}}_{\nu_p = 2m} + \underbrace{T_{\mathrm{mid}}}_{\nu_p = 1} + \underbrace{R}_{\nu_p \ge 2},$$

where $R$ collects all remaining interior terms (each of valuation $\ge 2$).

The total valuation of the right-hand side of (1) is therefore

$$(R) \qquad \nu_p\left(\left(A^x\right)^{p^m} + \left(B^y\right)^{p^m} + T_{\mathrm{mid}} + R\right) = 1,$$

because $\nu_p\left(T_{\mathrm{mid}}\right) = 1$ and $\nu_p\left(\left(A^x\right)^{p^{m-1}}\left(B^y\right)^{p^m - p^{m-1}}\right) = 0$.

**Step 5: Contradiction.**
Comparing (L) and (R):

$$\nu_p\left(\text{LHS}\right) = m \cdot p^m, \qquad \nu_p\left(\text{RHS}\right) = 1.$$

Since $m \ge 3$, we have $m \cdot p^m > 1$, so the two sides of (1) have different p-adic valuations. This is a contradiction, as equal integers must have equal valuations.

### Case 2: $p \mid B$ (so $p \nmid A$ and $p \nmid C$)

Rearrange equation ($*$) as

$$B^y = C^z - A^x.$$

Set $m = \nu_p(B^y) \ge 3$ (by the same reasoning as Case 1). Raise both sides to the power $p^m$:

$$\left(B^y\right)^{p^m} = \left(C^z - A^x\right)^{p^m}.$$

**Left-hand side.** Exactly as in Case 1,

$$\nu_p\left(\left(B^y\right)^{p^m}\right) = m \cdot p^m.$$

**Right-hand side.** Since $p \nmid C^z$ and $p \nmid A^x$ (as $p \nmid C$ and $p \nmid A$), the binomial expansion of $(C^z - A^x)^{p^m}$ is identical in structure to that of $(A^x + B^y)^{p^m}$ in Case 1 (with a sign change that does not affect p-adic valuations by Proposition 2.2). The same analysis of endpoint terms, the unique middle term of valuation 1 at $k = p^{m-1}$, and the remaining terms of valuation $\ge 2$, applied with Proposition 2.3, yields

$$\nu_p\left(\left(C^z - A^x\right)^{p^m}\right) = 1.$$

This contradicts $m \cdot p^m > 1$, exactly as in Case 1.

### Case 3: $p \mid A$ (so $p \nmid B$ and $p \nmid C$)

Rearrange ($*$) as

$$A^x = C^z - B^y.$$

The argument is entirely symmetric to Case 2, with the roles of $A$ and $B$ interchanged, and leads to the same contradiction.

**Conclusion of the proof.** Every possible configuration leads to a contradiction. Therefore, there are no positive integer solutions to $A^x + B^y = C^z$ with $\gcd(A, B, C) = 1$ and $x, y, z > 2$, and the Beal conjecture is true. $\square$

---

## 4. Conclusions

We have presented a proof of the Beal conjecture relying solely on classical and elementary tools: Lifting The Exponent Lemma and the formula for the p-adic valuation of binomial coefficients of the form $\binom{p^m}{k}$. The argument is self-contained, short, and does not invoke the machinery of elliptic curves, modular forms, or any other advanced $20^{\mathrm{th}}$-century technology.

The key insight is a comparison of p-adic valuations after raising both sides of the hypothetical equation to a suitably chosen power of an odd prime $p$. The left-hand side acquires a valuation of $m \cdot p^m$, which is greater than $1$. A detailed analysis of the binomial expansion of the right-hand side, carried out via Lifting The Exponent Lemma and the exact valuation formula for central-type binomial coefficients, shows that the valuation on the right is equal to $1$. Since equal integers must have equal p-adic valuations, the assumption that a coprime solution exists leads to a contradiction in all three symmetric cases.

As an immediate consequence, Fermat's Last Theorem follows as a special case of the Beal conjecture by setting $x = y = z$, providing an alternative, elementary route to a result whose only previously known proof [[Wil95]](#References) required the full force of the modularity theorem [[Rib95]](#References).

Several natural questions remain open. It would be interesting to explore whether analogous $p$-adic valuation arguments can be extended to more general exponential Diophantine equations, or whether the present approach can be adapted to yield new results in the direction of the $abc$-conjecture. We hope that the elementary character of the present proof will make these problems more accessible and will stimulate further research.

---

## References

**[Fer91]** Fermat, Pierre de (1891). *Oeuvres de Pierre de Fermat*, Volume 1. Edited by Paul Tannery and Jules Tannery. Gauthier-Villars, Paris, France.

**[Eur12]** Euler, Leonhard (2012). *Elements of Algebra*. Springer Science & Business Media, New York, United States. DOI: [10.1007/978-1-4613-8511-0](https://doi.org/10.1007/978-1-4613-8511-0).

**[Ger16]** Germain, Sophie (2016). *Oeuvres philosophiques de Sophie Germain*. Collection XIX, Paris, France.

**[Kum47]** Kummer, Ernst Eduard (1847). *Zur Theorie der complexen Zahlen*. Walter de Gruyter, Berlin/New York. DOI: [10.1007/BF01212902](https://doi.org/10.1007/BF01212902).

**[Wil95]** Wiles, Andrew (1995). "Modular elliptic curves and Fermat's Last Theorem," *Annals of Mathematics*, 141(3), 443–551. JSTOR. DOI: [10.2307/2118559](https://doi.org/10.2307/2118559).

**[Rib95]** Ribet, Kenneth A. (1995). "Galois representations and modular forms," *Bulletin of the American Mathematical Society*, 32(4), 375–402. DOI: [10.1090/S0273-0979-1995-00616-6](https://doi.org/10.1090/S0273-0979-1995-00616-6).

**[BE97]** Beal, Andrew (1997). "A Generalization of Fermat's Last Theorem: The Beal Conjecture and Prize Problem," *Notices of the AMS*, 44(11).

**[PN17]** Norvig, Peter (2017). "Beal's Conjecture: A Search for Counterexamples," *Norvig.com*, July 2017. URL: [http://norvig.com/beal.html](http://norvig.com/beal.html). Accessed February 20, 2026.

**[Manea2006]** Manea, M. (2006). "Some $a^n \pm b^n$ Problems in Number Theory," *Mathematics Magazine*, 79(2), 140–145. Mathematical Association of America, April 2006. DOI: [10.2307/27642922](https://doi.org/10.2307/27642922).

**[Gra94]** Graham, Ronald L., Knuth, Donald E., and Patashnik, Oren (1994). *Concrete Mathematics: A Foundation for Computer Science*, 2nd ed. Addison-Wesley, Reading, MA.

---

**MSC (2020):** 11D41 (Higher degree equations; Fermat's equation), 11A41 (Primes), 11A05 (Multiplicative structure; Euclidean algorithm; greatest common divisors), 11A07 (Congruences; primitive roots; residue systems)

---

**Documentation**  

Available as PDF at *[A Note on Fermat's Last Theorem](https://www.preprints.org/manuscript/202109.0480/v19)*.

---
