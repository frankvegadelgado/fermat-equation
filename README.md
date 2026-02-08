# A Note on Fermat's Last Theorem


**Author:** Frank Vega
**Affiliation:** Information Physics Institute, 840 W 67th St, Hialeah, FL 33012, USA
**Email:** vega.frank@gmail.com
**ORCID:** 0000-0001-8210-4126

---

## Abstract

In 1637, Pierre de Fermat asserted that the equation $a^{n}+b^{n}=c^{n}$ has no positive integer solutions for any exponent $n>2$, famously claiming to possess a proof too large for the margin. Although Andrew Wiles established the full theorem in 1994 using deep methods from algebraic geometry and modular forms, the possibility of a more elementary argument has remained a topic of enduring interest. In this work we give a classical proof of the nonexistence of solutions to the Fermat equation for prime exponents under a natural local constraint: we assume that for an odd prime $p$, any hypothetical primitive solution triple $(a,b,c)$ to $a^p+b^p=c^p$ satisfies $a+b-c<2p$. The proof proceeds by establishing that the difference $\delta = a+b-c$ must satisfy $\delta \ge 2p$, thereby contradicting the hypothesis. This follows from three elementary observations: first, by the binomial theorem, $(a+b)^p > a^p+b^p = c^p$, ensuring $\delta > 0$; second, by Fermat's Little Theorem applied modulo $p$, we have $p \mid \delta$, yielding $\delta \ge p$; third, parity considerations force $2 \mid \delta$, which combined with $\delta \ge p$ gives $\delta \ge 2p$. The argument relies solely on elementary number theory and congruence techniques, remaining close to the arithmetic framework available in Fermat's time.

**Keywords:** Fermat's equation; prime divisors; Fermat's Little Theorem; coprimality; congruences

**MSC:** 11D41, 11A41, 11A05, 11A07

---

## 1. Introduction

Fermat's Last Theorem, first stated by Pierre de Fermat in the $17^{\mathrm{th}}$ century, asserts that the Diophantine equation

$$
a^{n}+b^{n}=c^{n}
$$

has no solutions in positive integers whenever $n>2$. In a margin note left on his copy of Diophantus' *Arithmetica*, Fermat claimed to possess a proof "too large to fit in the margin" [[Fer91]](#References). Over the centuries, mathematicians such as Euler [[Eur12]](#References), Sophie Germain [[Ger16]](#References), and Kummer [[Kum47]](#References) resolved important special cases, yet a complete proof remained elusive.

The modern breakthrough came in 1994, when Andrew Wiles established the full theorem using deep results from the theory of elliptic curves and modular forms [[Wil95]](#References). His work, later strengthened by Ribet and others [[Rib95]](#References), revolutionized modern number theory and relied on sophisticated machinery far removed from the classical arithmetic methods available in Fermat's time.

Despite this achievement, the search for an elementary proof--one relying only on classical number-theoretic tools--has persisted. Such a proof would illuminate the inherent arithmetic structure of the Fermat equation and provide insight into why the equation admits no nontrivial solutions.

In this article we establish an elementary proof of the nonexistence of solutions to the Fermat equation for prime exponents under a natural local restriction. Specifically, we assume that for an odd prime $p$, any hypothetical primitive solution triple $(a,b,c)$ to the equation

$$
a^p+b^p=c^p
$$

satisfies the inequality

$$
a+b-c<2p.
$$

The proof is remarkably direct: we show that the difference $\delta = a+b-c$ must satisfy $\delta \ge 2p$, contradicting the hypothesis. The argument combines three elementary facts. First, the binomial theorem ensures $(a+b)^p > a^p+b^p$, so $\delta > 0$. Second, applying Fermat's Little Theorem modulo $p$ shows $p \mid \delta$, hence $\delta \ge p$. Third, parity considerations reveal that exactly one of $a,b,c$ is even, forcing $2 \mid \delta$. Since $\delta$ is divisible by both $2$ and $p$ (with $p$ odd), we obtain $\delta \ge 2p$, the desired contradiction. This fully elementary argument requires only basic congruence techniques and remains within the classical arithmetic framework.

---

## 2. Main Result

As usual, we write $d \mid n$ to mean that the integer $d$ divides the integer $n$. We denote by $a \equiv b \pmod{n}$ the congruence of $a$ and $b$ modulo $n$ (i.e., $n \mid (a - b)$).

This is the main theorem.

**Theorem 1** (Fermat-type nonexistence under a local constraint). Let $p$ be an odd prime. Suppose there exist positive integers $a,b,c$ such that

$$
a^p + b^p = c^p,\quad a,b,c \in \mathbb{N} \text{ pairwise coprime and } a + b - c < 2p.
$$

Then no such integers $a,b,c$ exist.

**Proof.** Assume, for contradiction, that there exist positive integers $a,b,c$ and an odd prime $p$ such that

$$
a^p + b^p = c^p
\qquad\text{and}\qquad
a + b - c < 2p,
$$

where $a,b,c$ are pairwise coprime.

### Step 1: Establishing $\delta > 0$ via the binomial theorem.

By the binomial theorem, expanding $(a+b)^p$ yields

$$
(a+b)^p = \sum_{k=0}^{p} \binom{p}{k} a^k b^{p-k} = a^p + b^p + \sum_{k=1}^{p-1} \binom{p}{k} a^k b^{p-k}.
$$

Since all terms in the sum $\sum_{k=1}^{p-1} \binom{p}{k} a^k b^{p-k}$ are strictly positive (as $a,b > 0$), we have

$$
(a+b)^p > a^p + b^p.
$$

But $a^p + b^p = c^p$ by hypothesis, so

$$
(a+b)^p > c^p.
$$

Since the function $x \mapsto x^p$ is strictly increasing on positive reals, this inequality implies $a+b > c$. Defining $\delta = a + b - c$, we conclude $\delta > 0$.

### Step 2: Showing $\delta \ge p$ via Fermat's Little Theorem.

We now examine the equation $a^p + b^p = c^p$ modulo $p$. By Fermat's Little Theorem, for any integer $x$, we have $x^p \equiv x \pmod{p}$. Therefore,

$$
a^p \equiv a \pmod{p}, \qquad b^p \equiv b \pmod{p}, \qquad c^p \equiv c \pmod{p}.
$$

Substituting into $a^p + b^p = c^p$:

$$
a + b \equiv c \pmod{p} \implies a + b - c \equiv 0 \pmod{p} \implies p \mid \delta.
$$

Since $\delta > 0$ and $p \mid \delta$, we have $\delta \ge p$.

### Step 3: Deducing $2 \mid \delta$ from parity considerations.

Since $p$ is an odd prime ($p \ge 3$), the exponent $p$ is odd. For any integer $x$, the congruence $x^p \equiv x \pmod{2}$ holds because $x^p - x = x(x^{p-1}-1)$, which is even whether $x$ is even (making the whole product even) or odd (making $x^{p-1}-1$ even). Reducing $a^p + b^p = c^p$ modulo $2$:

$$
a + b \equiv c \pmod{2}.
$$

If $a, b, c$ were all odd, we would have $1 + 1 \equiv 1 \pmod{2}$, i.e., $0 \equiv 1 \pmod{2}$, a contradiction. Thus at least one of $a,b,c$ is even. Since $a,b,c$ are pairwise coprime, at most one can be even (otherwise two would share the common factor $2$). Therefore exactly one of $a,b,c$ is even and the other two are odd. In all cases,

$$
a + b - c \equiv 0 \pmod{2},
$$

yielding $2 \mid \delta$.

### Step 4: Deriving the contradiction $\delta \ge 2p$.

We have established:

* $p \mid \delta$ (from Step 3), so $\delta \ge p$;
* $2 \mid \delta$ (from Step 4);
* $p$ is an odd prime, so $\gcd(2, p) = 1$.

Since $\gcd(2,p) = 1$ and both $2$ and $p$ divide $\delta$, their least common multiple $\text{lcm}(2,p) = 2p$ also divides $\delta$. Thus $\delta \ge 2p$. But this contradicts our hypothesis that $a + b - c = \delta < 2p$.

Consequently, no such $a,b,c$ exist under the stated conditions. This completes the proof of the theorem.


□

---

## 3. Conclusion

While the full proof of Fermat's Last Theorem provided by Andrew Wiles remains one of the crowning achievements of modern mathematics, it relies on the heavy machinery of modular forms and Galois representations. Our result suggests that for specific regions of the integer search space--defined here by the proximity of $a+b$ to $c$--the nonexistence of solutions can be recovered using only the arithmetic tools available in the $17^{\mathrm{th}}$ century. The requirement $a+b-c \ge 2p$ provides a concrete geometric and arithmetic hurdle for any hypothetical counterexample. Future research might investigate whether this lower bound can be further sharpened using higher-order congruences or if the constraint $a+b-c < 2p$ can be relaxed to encompass a larger subset of potential solutions. Ultimately, this proof reaffirms that even within the most complex problems in number theory, elementary methods continue to offer elegant and profound insights.

---

## References

**[Fer91]** Fermat, Pierre de (1891). *Oeuvres de Pierre de Fermat*, Volume 1. Edited by Paul Tannery and Jules Tannery. Gauthier-Villars, Paris, France.

**[Eur12]** Euler, Leonhard (2012). *Elements of Algebra*. Springer Science & Business Media, New York, United States. DOI: [10.1007/978-1-4613-8511-0](https://doi.org/10.1007/978-1-4613-8511-0).

**[Ger16]** Germain, Sophie (2016). *Oeuvres philosophiques de Sophie Germain*. Collection XIX, Paris, France.

**[Kum47]** Kummer, Ernst Eduard (1847). *Zur Theorie der complexen Zahlen*. Walter de Gruyter, Berlin/New York. DOI: [10.1007/BF01212902](https://doi.org/10.1007/BF01212902).

**[Wil95]** Wiles, Andrew (1995). "Modular elliptic curves and Fermat's Last Theorem," *Annals of Mathematics*, 141(3), 443–551. JSTOR. DOI: [10.2307/2118559](https://doi.org/10.2307/2118559).

**[Rib95]** Ribet, Kenneth A. (1995). "Galois representations and modular forms," *Bulletin of the American Mathematical Society*, 32(4), 375–402. DOI: [10.1090/S0273-0979-1995-00616-6](https://doi.org/10.1090/S0273-0979-1995-00616-6).

---

**MSC (2020):** 11D41 (Higher degree equations; Fermat's equation), 11A41 (Primes), 11A05 (Multiplicative structure; Euclidean algorithm; greatest common divisors), 11A07 (Congruences; primitive roots; residue systems)

---

**Documentation**  

Available as PDF at *[A Note on Fermat's Last Theorem](https://www.preprints.org/manuscript/202109.0480/v18)*.

---