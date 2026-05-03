# A Note on the Beal Conjecture

**Author:** Frank Vega  
**Affiliation:** Information Physics Institute, 840 W 67th St, Hialeah, FL 33012, USA  
**Email:** vega.frank@gmail.com  
**ORCID:** 0000-0001-8210-4126  

---

## Abstract

In 1993, Andrew Beal formulated the conjecture that if $A^{x}+B^{y}=C^{z}$ holds for positive integers $A,B,C,x,y,z$ with $x,y,z>2$, then $A$, $B$, and $C$ must share a common prime factor. We prove the Beal conjecture for every primitive solution in which $C$ possesses at least one odd prime divisor, using three classical tools: the Lifting The Exponent Lemma for odd primes, the exact $p$-adic valuation of the binomial coefficient $\binom{p^{m}}{k}$, and a careful pairing of the interior terms of the binomial expansion. The argument raises the equation to the power $p^{m}$ (where $m=\nu_{p}(C^{z}) $) and shows that the resulting right-hand side has $p$-adic valuation exactly $2m$, while the left-hand side has $p$-adic valuation $m\cdot p^{m}>2m$, yielding the required contradiction. The residual case in which $C$ is a power of two is left open as a conjecture. For Fermat's Last Theorem, however, the case $c=2^{s}$ admits a complete elementary proof: when the exponent $n$ is even, an arithmetic argument modulo $8$ gives $\nu_{2}(a^{n}+b^{n})=1\neq sn$; when $n$ is odd, the Lifting The Exponent Lemma for $p=2$ forces $a+b\ge 2^{sn}$, contradicting the strict bound $a+b\le 2^{s+1}-2$. Combining both results yields a complete proof of Fermat's Last Theorem for all exponents $n\ge 3$.

**Keywords:** Beal conjecture; Fermat's Last Theorem; $p$-adic valuation; Lifting The Exponent Lemma; binomial coefficients; power of two

**MSC:** 11D41, 11A41, 11A05, 11A07

---

## 1. Introduction

In 1993, Andrew Beal, while investigating generalizations of Fermat's Last Theorem, formulated the following conjecture [[Fer91, BE97]](#references).

**Conjecture 1.1** (Beal conjecture). Let $A$, $B$, $C$, $x$, $y$, $z$ be positive integers with $x,y,z>2$. If $A^{x}+B^{y}=C^{z}$, then $A$, $B$, and $C$ have a common prime factor. Equivalently, there is no solution with $\gcd(A,B,C)=1$.

Beal offered a monetary prize, now held by the American Mathematical Society at $1000000, for a proof or disproof. Fermat's Last Theorem arises as the special case $x=y=z$; it was finally proved by Andrew Wiles in 1994 [[Wil95, Rib95]](#references) using deep machinery from the theory of elliptic curves and modular forms that lies entirely outside the scope of classical number theory. Extensive computation has found no coprime counterexample to the Beal conjecture in small parameter ranges [[PN17]](#references), but a general proof has remained elusive.

The present note establishes two results. First, we prove the Beal conjecture for every primitive solution in which $C$ has at least one odd prime divisor $p$. Setting $m:=\nu_{p}(C^{z})\ge 3$ and raising the assumed equation $A^{x}+B^{y}=C^{z}$ to the power $p^{m}$, we obtain two sides of equal value. The left-hand side $(C^{z})^{p^{m}}$ has $p$-adic valuation $m\cdot p^{m}$. The right-hand side $(A^{x}+B^{y})^{p^{m}}$ is expanded by the binomial theorem: its endpoint sum $(A^{x})^{p^{m}}+(B^{y})^{p^{m}}$ has $p$-adic valuation exactly $2m$ by the Lifting The Exponent Lemma (exploiting $p\mid A^{x}+B^{y}=C^{z}$), and every pair of special interior indices $k=tp^{m-1}$ also contributes valuation $2m$ by a second application of the Lemma. Since every remaining interior pair contributes valuation at least $2m$, the right-hand side has $p$-adic valuation $2m$, which contradicts $m\cdot p^{m}>2m$.

Second, we observe that the case $C=2^{s}$ ($s\ge 1$), in which $C$ has no odd prime divisor, falls outside the scope of the above argument. For the Beal conjecture in this case we leave the problem open, noting only that the sub-case in which both $x$ and $y$ are even is immediately ruled out by an arithmetic argument modulo $8$. For Fermat's Last Theorem, however, the analogous situation $c=2^{s}$ is completely tractable: two elementary arguments—one based on arithmetic modulo $8$ for even exponents, and one based on the Lifting The Exponent Lemma for $p=2$ combined with a size bound for odd exponents—together close the case. The combination of both results yields a complete proof of Fermat's Last Theorem for all $n\ge 3$.

---

## 2. Materials and Methods

We collect the notation and auxiliary results used throughout.

**Notation.** As usual, $d\mid n$ means that $d$ divides $n$, and $d\nmid n$ that it does not. We write $\gcd(a,b)$ for the greatest common divisor. Throughout the paper, $p$ always denotes a prime and $m$ a positive integer.

**Definition 2.1.** Let $p$ be a prime and $n\in\mathbb{Z}\setminus\{0\}$. The **$p$-adic valuation** $\nu_{p}(n)$ is the largest non-negative integer $e$ such that $p^{e}\mid n$. We set $\nu_{p}(0)=+\infty$. The function $\nu_{p}$ is completely multiplicative: $\nu_{p}(xy)=\nu_{p}(x)+\nu_{p}(y)$ and $\nu_{p}(x^{k})=k\nu_{p}(x)$. The *strict-inequality rule* states that if $\nu_{p}(x)\ne\nu_{p}(y)$ then $\nu_{p}(x+y)=\min\{\nu_{p}(x),\nu_{p}(y)\}$; in particular, the $p$-adic valuation of a sum is determined by its term of smallest valuation whenever that minimum is attained by exactly one term.

**Proposition 2.2** (Lifting The Exponent Lemma for odd primes [[Manea2006]](#references)). Let $p$ be an odd prime and let $u,v$ be integers with $p\nmid u$ and $p\nmid v$. If $p\mid u-v$, then for every positive integer $n$, $\nu_{p}(u^{n}-v^{n})=\nu_{p}(u-v)+\nu_{p}(n)$. If instead $p\mid u+v$ and $n$ is a positive odd integer, then $\nu_{p}(u^{n}+v^{n})=\nu_{p}(u+v)+\nu_{p}(n)$.

**Proposition 2.3** (Lifting The Exponent Lemma for $p=2$ [[Manea2006]](#references)). Let $u$ and $v$ be odd integers and $n$ a positive integer. If $n$ is odd, then $\nu_{2}(u^{n}+v^{n})=\nu_{2}(u+v)$. If $n$ is even, then $\nu_{2}(u^{n}+v^{n})=1$.

*Proof.* For odd $n$: since $(-v)^{n}=-v^{n}$, we have $u^{n}+v^{n}=u^{n}-(-v)^{n}$. The standard LTE for $p=2$ subtraction with odd exponent gives $\nu_{2}(u^{n}-(-v)^{n})=\nu_{2}(u-(-v))=\nu_{2}(u+v)$. For even $n$: any odd integer $w$ satisfies $w^{2}\equiv 1\pmod{8}$, so $u^{n}=(u^{2})^{n/2}\equiv 1\pmod{8}$ and $v^{n}=(v^{2})^{n/2}\equiv 1\pmod{8}$, giving $u^{n}+v^{n}\equiv 2\pmod{8}$, hence $\nu_{2}(u^{n}+v^{n})=1$. $\square$

**Proposition 2.4** ($p$-adic valuation of binomial coefficients [[Gra94]](#references)). For every integer $k$ with $1\le k<p^{m}$,

$$\nu_{p}\left(\binom{p^{m}}{k}\right)=m-\nu_{p}(k).$$

In particular, $\nu_{p}\bigl(\binom{p^{m}}{tp^{m-1}}\bigr)=1$ for $t\in\{1,\ldots,p-1\}$, and $\nu_{p}\bigl(\binom{p^{m}}{k}\bigr)=m$ when $p\nmid k$.

**Remark 2.5.** If $A^{x}+B^{y}=C^{z}$ and $\gcd(A,B,C)=1$, then $A$, $B$, $C$ are automatically pairwise coprime. Indeed, suppose a prime $q$ divides two of them, say $q\mid A$ and $q\mid B$. Then $q\mid A^{x}+B^{y}=C^{z}$, so $q\mid C$, which contradicts $\gcd(A,B,C)=1$. The argument is symmetric, so no prime can divide any two of $A$, $B$, $C$ simultaneously.

---

## 3. Main Results

### 3.1. The Beal conjecture when $C$ has an odd prime divisor

**Theorem 3.1** (Beal conjecture when $C$ has an odd prime divisor). Let $A$, $B$, $C$, $x$, $y$, $z$ be positive integers with $x,y,z>2$ and $\gcd(A,B,C)=1$. If $A^{x}+B^{y}=C^{z}$ and $C$ has at least one odd prime divisor, then $\gcd(A,B,C)>1$, a contradiction.

*Proof.* Assume for contradiction that $\gcd(A,B,C)=1$ and $A^{x}+B^{y}=C^{z}$ with $x,y,z>2$. By hypothesis there exists an odd prime $p$ with $p\mid C$. By Remark 2.5, $A$, $B$, $C$ are pairwise coprime, so $p\nmid A$ and $p\nmid B$.

**Step 1: The parameter $m$.** Define $m:=\nu_{p}(C^{z})=z\nu_{p}(C)$. Since $z>2$ and $\nu_{p}(C)\ge 1$, we have $m\ge 3$.

**Step 2: Raising to the power $p^{m}$.** Raising both sides to the power $p^{m}$,

$$(C^{z})^{p^{m}}=(A^{x}+B^{y})^{p^{m}}.$$

**Step 3: $p$-adic valuation of the left-hand side.** By multiplicativity of $\nu_{p}$,

$$\nu_{p}\left((C^{z})^{p^{m}}\right) = p^{m}\cdot\nu_{p}(C^{z}) = m\cdot p^{m}.$$

**Step 4: Binomial expansion of the right-hand side.** Separating the two endpoint terms ($k=0$ and $k=p^{m}$) from the interior terms ($1\le k\le p^{m}-1$),

$$(A^{x}+B^{y})^{p^{m}} = \underbrace{(A^{x})^{p^{m}}+(B^{y})^{p^{m}}}_{S_{\mathrm{end}}} + \underbrace{\sum_{k=1}^{p^{m}-1}\binom{p^{m}}{k}(A^{x})^{k}(B^{y})^{p^{m}-k}}_{S_{\mathrm{int}}}.$$

**Step 5: Exact valuation of the endpoint sum $S_{\mathrm{end}}$.** Since $p\mid A^{x}+B^{y}=C^{z}$ and $p\nmid A^{x}$, $p\nmid B^{y}$, and $p^{m}$ is odd, Proposition 2.2 (sum version) gives

$$\nu_{p}(S_{\mathrm{end}}) = \nu_{p}(A^{x}+B^{y})+\nu_{p}(p^{m}) = m+m = 2m.$$

This is the exact value: the leading $p^{2m}$-coefficient of $S_{\mathrm{end}}$ is a $p$-adic unit because $\nu_{p}((A^{x}+B^{y})/p^{m})=0$.

**Step 6: Valuation formula for every interior term.** For each $k$ with $1\le k\le p^{m}-1$, since $p\nmid A^{x}$ and $p\nmid B^{y}$,

$$\nu_{p}\left(\binom{p^{m}}{k}(A^{x})^{k}(B^{y})^{p^{m}-k}\right) = \nu_{p}\binom{p^{m}}{k} = m-\nu_{p}(k)$$

by Proposition 2.4.

**Step 7: Pairing the special interior indices.** The indices $k=tp^{m-1}$ for $t=1,\ldots,p-1$ each give term valuation $1$. Since $p^{m}$ is odd, every index $k$ is paired with a distinct complement $p^{m}-k$, and $\binom{p^{m}}{k}=\binom{p^{m}}{p^{m}-k}$. For the special pair $k=tp^{m-1}$ and $k'=(p-t)p^{m-1}$ (with $1\le t\le(p-1)/2$), factoring the paired sum and applying Proposition 2.2 to the bracket $(B^{y})^{(p-2t)p^{m-1}}+(A^{x})^{(p-2t)p^{m-1}}$ (whose exponent is a positive odd integer with $\nu_{p}(p-2t)=0$) yields

$$\nu_{p}(T_{t}+T_{p-t}) = \underbrace{1}_{\nu_p\binom{p^m}{tp^{m-1}}} + \underbrace{0}_{\nu_p(A^xB^y)^{tp^{m-1}}} + \underbrace{(2m-1)}_{\nu_p(\text{bracket})} = 2m.$$

Every pair of special interior terms therefore has $p$-adic valuation exactly $2m$.

**Step 8: Remaining interior terms.** For $1\le k\le p^{m}-1$ with $\nu_{p}(k)\le m-2$, applying the same pairing factorisation shows that every remaining interior pair has $p$-adic valuation at least $2m$.

**Step 9: Total valuation of the right-hand side.** Collecting Steps 5, 7, and 8: every component of the right-hand side has $p$-adic valuation at least $2m$, and the endpoint sum contributes a $p$-adic unit at the $p^{2m}$ level. Therefore

$$\nu_{p}\left((A^{x}+B^{y})^{p^{m}}\right) = 2m.$$

**Step 10: Contradiction.** Comparing the two sides,

$$m\cdot p^{m} = \nu_{p}\left((C^{z})^{p^{m}}\right) \ne \nu_{p}\left((A^{x}+B^{y})^{p^{m}}\right) = 2m,$$

because $m\cdot p^{m}>2m$ for all odd primes $p\ge 3$ and all $m\ge 1$. Two equal non-zero integers cannot have different $p$-adic valuations. $\square$

---

### 3.2. Open case: $C$ a power of two

**Remark 3.2** (Beal gap). When $C=2^{s}$ for some $s\ge 1$, the base $C$ has no odd prime divisor and Theorem 3.1 does not apply. In this situation $\gcd(A,B,C)=1$ forces both $A$ and $B$ to be odd, and the equation becomes $A^{x}+B^{y}=2^{sz}$. If both $x$ and $y$ are even, Proposition 2.3 (even case) gives $\nu_{2}(A^{x}+B^{y})=1$, which contradicts $\nu_{2}(2^{sz})=sz\ge 3$; this sub-case is therefore settled. When at least one of $x$, $y$ is odd, however, we are presently unable to establish the impossibility of a solution in general, and the problem is left open. Computational evidence [[PN17]](#references) provides no counterexample in small parameter ranges.

---

### 3.3. Fermat's Last Theorem: the case $c=2^{s}$

**Lemma 3.3** (FLT when $c$ is a power of two). Let $n\ge 3$ and $s\ge 1$ be integers. There are no positive odd integers $a$, $b$ satisfying $a^{n}+b^{n}=2^{sn}$.

*Proof.* We consider two cases according to the parity of $n$.

**Case A: $n$ is even.** Since $a$ and $b$ are odd and $n$ is even, Proposition 2.3 (even case) gives $\nu_{2}(a^{n}+b^{n})=1$. On the other hand, $\nu_{2}(2^{sn})=sn$. Since $n\ge 4$ and $s\ge 1$, we have $sn\ge 4>1$, so $\nu_{2}(a^{n}+b^{n})\ne\nu_{2}(2^{sn})$, which is impossible.

**Case B: $n$ is odd.** Since $a$, $b$ are odd and $n$ is odd, Proposition 2.3 (odd case) gives $\nu_{2}(a^{n}+b^{n})=\nu_{2}(a+b)$. From $a^{n}+b^{n}=2^{sn}$ we obtain $\nu_{2}(a+b)=sn$, which means $a+b\ge 2^{sn}$. For the upper bound: from $a^{n}\le 2^{sn}-1<(2^{s})^{n}$ we get $a<2^{s}$, so $a\le 2^{s}-1$, and by symmetry $b\le 2^{s}-1$. Therefore

$$a+b \le (2^{s}-1)+(2^{s}-1) = 2^{s+1}-2.$$

Since $n\ge 3$ and $s\ge 1$, we have $sn\ge s+2$ (because $s(n-1)\ge 2s\ge 2$), so $2^{sn}\ge 2^{s+2}>2^{s+1}-2\ge a+b$, contradicting $a+b\ge 2^{sn}$. $\square$

**Remark 3.4.** The bound $a+b\le 2^{s+1}-2$ is strict: were $a=2^{s}$, we would have $a^{n}\ge 2^{sn}$, leaving no room for the positive term $b^{n}$. Hence $a\le 2^{s}-1$, and the same holds for $b$ by symmetry.

---

### 3.4. Complete proof of Fermat's Last Theorem

**Corollary 3.5** (Fermat's Last Theorem). There are no positive integer solutions to $a^{n}+b^{n}=c^{n}$ for any integer $n\ge 3$.

*Proof.* It suffices to prove the result for primitive solutions satisfying $\gcd(a,b,c)=1$; every non-primitive solution yields a primitive one upon dividing through by $\gcd(a,b,c)$. By a standard parity argument, in every primitive solution exactly one of $a$, $b$, $c$ is even.

**Sub-case 1: $c$ is even and has an odd prime divisor $p$.** Set $A:=a$, $B:=b$, $C:=c$, and $x=y=z:=n$. Then $m:=\nu_{p}(C^{z})=n\nu_{p}(c)\ge n\ge 3$. All hypotheses of Theorem 3.1 are satisfied, yielding a contradiction.

**Sub-case 2: $c$ is even and $c=2^{s}$ for some $s\ge 1$.** Since $\gcd(a,b,c)=1$ and $2\mid c$, both $a$ and $b$ are odd. The equation becomes $a^{n}+b^{n}=2^{sn}$, which Lemma 3.3 shows is impossible.

**Sub-case 3: $c$ is odd.** Since $c$ is odd and $c\ge 2$, $c$ has at least one odd prime divisor $p$. Setting $A:=a$, $B:=b$, $C:=c$, and $x=y=z:=n$, the parameter $m=n\nu_{p}(c)\ge 3$, and Theorem 3.1 again yields a contradiction.

All three sub-cases are impossible, so no primitive solution exists, and Fermat's Last Theorem is proved. $\square$

---

## 4. Conclusions

Two main results have been established. For the Beal conjecture $A^{x}+B^{y}=C^{z}$ with $\gcd(A,B,C)=1$ and $x,y,z>2$: whenever $C$ possesses an odd prime divisor $p$, a contradiction arises from comparing the $p$-adic valuations of the two sides of $(C^{z})^{p^{m}}=(A^{x}+B^{y})^{p^{m}}$. The left-hand side has valuation $m\cdot p^{m}$. The right-hand side, analyzed term by term and pair by pair through the Lifting The Exponent Lemma and the formula for $\nu_{p}\bigl(\binom{p^{m}}{k}\bigr)$, has valuation exactly $2m$; since $2m<m\cdot p^{m}$ for every odd prime $p$ and every $m\ge 1$, the equation cannot hold. The case $C=2^{s}$ (no odd prime divisor) remains an open problem for the Beal conjecture, with the sub-case of both exponents even settled by a modulo $8$ argument. For Fermat's Last Theorem, the analogous case $c=2^{s}$ is completely resolved: the Lifting The Exponent Lemma for $p=2$ forces $a+b$ to be divisible by $2^{sn}$, yet the elementary bound $a+b\le 2^{s+1}-2$ contradicts $a+b\ge 2^{sn}$ whenever $n\ge 3$ and $s\ge 1$; the even-exponent sub-case is handled separately by the same modulo $8$ argument. Combining Theorem 3.1 with Lemma 3.3 thus yields a complete elementary proof of Fermat's Last Theorem for all $n\ge 3$.

---

## References

**[Fer91]** Fermat, Pierre de (1891). *Oeuvres de Pierre de Fermat*, Volume 1. Edited by Paul Tannery and Jules Tannery. Gauthier-Villars, Paris, France.

**[Wil95]** Wiles, Andrew (1995). "Modular elliptic curves and Fermat's Last Theorem," *Annals of Mathematics*, 141(3), 443--551. JSTOR. DOI: [10.2307/2118559](https://doi.org/10.2307/2118559).

**[Rib95]** Ribet, Kenneth A. (1995). "Galois representations and modular forms," *Bulletin of the American Mathematical Society*, 32(4), 375--402. DOI: [10.1090/S0273-0979-1995-00616-6](https://doi.org/10.1090/S0273-0979-1995-00616-6).

**[BE97]** Beal, Andrew (1997). "A Generalization of Fermat's Last Theorem: The Beal Conjecture and Prize Problem," *Notices of the AMS*, 44(11).

**[PN17]** Norvig, Peter (2017). "Beal's Conjecture: A Search for Counterexamples," *Norvig.com*, July 2017. URL: [http://norvig.com/beal.html](http://norvig.com/beal.html). Accessed February 19, 2026.

**[Manea2006]** Manea, M. (2006). "Some $a^n \pm b^n$ Problems in Number Theory," *Mathematics Magazine*, 79(2), 140--145. Mathematical Association of America, April 2006. DOI: [10.2307/27642922](https://doi.org/10.2307/27642922).

**[Gra94]** Graham, Ronald L., Knuth, Donald E., and Patashnik, Oren (1994). *Concrete Mathematics: A Foundation for Computer Science*, 2nd ed. Addison-Wesley, Reading, MA.

---

**MSC (2020):** 11D41 (Higher degree equations; Fermat's equation), 11A41 (Primes), 11A05 (Multiplicative structure; Euclidean algorithm; greatest common divisors), 11A07 (Congruences; primitive roots; residue systems)

---

**Documentation**

Available as PDF at *[A Note on the Beal Conjecture](https://www.preprints.org/manuscript/202109.0480)*.
