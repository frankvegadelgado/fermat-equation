# A Note on Fermat's Last Theorem

**Author:** Frank Vega  
**Affiliation:** Information Physics Institute, 840 W 67th St, Hialeah, FL 33012, USA  
**Email:** vega.frank@gmail.com  
**ORCID:** 0000-0001-8210-4126  

---

## Abstract

Around 1637, Pierre de Fermat famously wrote in the margin of his copy of Diophantus's *Arithmetica* that he possessed a proof showing that the equation $a^{n} + b^{n} = c^{n}$ admits no solutions in positive integers whenever the exponent $n$ exceeds $2$. This assertion, now known as Fermat's Last Theorem, withstood the efforts of the mathematical community for more than three centuries. A complete and rigorous proof was finally obtained by Andrew Wiles in 1994, but it relies on deep twentieth-century machinery---the theory of elliptic curves, modular forms, and Galois representations---entirely foreign to the tools available to Fermat. Whether a genuinely elementary proof exists therefore remains an open historical question. Wiles was awarded the Abel Prize in 2016, the citation describing his achievement as a "stunning advance" in mathematics. In the present note we combine a handful of short and elementary ingredients---the Lifting The Exponent Lemma and the exact formula for the $2$-adic valuation of the binomial coefficients $\binom{2^{m}}{k}$---into a proof of Fermat's Last Theorem, offering what we believe may be closer in spirit to Fermat's original idea.

**Keywords:** Fermat equation; $p$-adic valuation; Lifting The Exponent Lemma; coprimality

**MSC:** 11D41, 11A41, 11A05

---

## 1. Introduction

Fermat's Last Theorem, first stated by Pierre de Fermat in the $17^{\mathrm{th}}$ century, asserts that the equation

$$a^{n} + b^{n} = c^{n}$$

has no solutions in positive integers for any integer $n \geq 3$. In a marginal note of his personal copy of Diophantus's *Arithmetica*, Fermat claimed to possess a proof too large to be accommodated by the margin [[Fer91]](#references). Later mathematicians---most notably Leonhard Euler and Sophie Germain---made substantial contributions to the problem [[Eur12, Ger16]](#references), and nineteenth-century work by Ernst Kummer established the theorem for an important class of prime exponents, the so-called regular primes [[Kum47]](#references). Despite these advances, a complete proof remained out of reach for more than three centuries.

In 1994, Andrew Wiles announced a proof of Fermat's Last Theorem. His argument is intricate and rests on advanced topics---most conspicuously the theory of elliptic curves and modular forms---that lie entirely outside the mathematical landscape of Fermat's era. After an initial gap in the argument was repaired in collaboration with Richard Taylor, Wiles's work was hailed as the long-awaited resolution of the problem [[Wil95]](#references), and was described as a "stunning advance" in the citation for his 2016 Abel Prize. A central achievement of the proof was the resolution of a large part of the Taniyama--Shimura conjecture, now known as the modularity theorem, which has in turn opened powerful new approaches to many problems in number theory through so-called modularity lifting techniques [[Rib95]](#references). The methods deployed by Wiles are, however, manifestly remote from anything Fermat could plausibly have had in mind, both in their scope and in the novelty of the tools involved---many of which belong squarely to the twentieth century.

In this article we present what we believe to be a short and correct proof of Fermat's Last Theorem. How closely our argument aligns with Fermat's own is a matter of speculation, but simplicity has been a guiding principle: we have deliberately restricted ourselves to techniques and results that would have been at least conceivable in the $17^{\mathrm{th}}$ century. The method developed here also appears promising for related Diophantine questions, such as the Beal conjecture, a well-known generalization of Fermat's Last Theorem [[beal1997generalization, stewart1986oesterle]](#references).

The argument proceeds by contradiction and is purely $2$-adic in nature. After a standard reduction, we may restrict attention to the case of an odd prime exponent $p$ and a primitive solution $A^{p} + B^{p} = C^{p}$ with $A, B, C$ pairwise coprime. A parity argument shows that *exactly one* of $A, B, C$ is divisible by $2$, which splits the argument into three symmetric cases. Let $E \in \{A, B, C\}$ denote the unique even base (so that the other two bases are odd), and set $m := \nu_{2}(E^{p})$, which satisfies $m \geq 3$ since $p \geq 3$ and $\nu_{2}(E) \geq 1$. We rearrange the Fermat equation so as to isolate one of the two odd $p$-th powers on one side---an operation that places a single "(odd) $-$ (even)" or "(even) $-$ (odd)" expression on the other---and then raise the resulting identity to the power $2^{m}$. The crucial observation is that exactly one endpoint of the resulting binomial expansion is the $2^{m}$-th power of the second odd base; moving this endpoint to the left-hand side produces an identity whose left-hand side has the shape

$$\bigl(X^{p}\bigr)^{2^{m}} - \bigl(Y^{p}\bigr)^{2^{m}}, \qquad X, Y \text{ the two odd bases,}$$

and whose right-hand side consists of binomial terms that each contain at least one positive power of the even base $E^{p}$. The Lifting The Exponent Lemma, applied in its *subtraction mode* to the two odd integers $X^{p}$ and $Y^{p}$ raised to the even power $2^{m}$, delivers the *exact* valuation $\nu_{2}\bigl((X^{p})^{2^{m}} - (Y^{p})^{2^{m}}\bigr) = 2m$ in each of the three cases. On the right-hand side, every individual term has valuation at least $2m$, and the symmetry $\binom{2^{m}}{k} = \binom{2^{m}}{2^{m}-k}$ allows us to pair index $k$ with its complement $2^{m} - k$; after pairing, the total valuation of the right-hand side is at least $2m + 1$. Since equal integers must have equal $2$-adic valuations, the strict inequality $2m < 2m + 1$ is a contradiction, and no primitive solution exists. The only thing that changes from case to case is which bases are odd and which endpoint of the binomial expansion must be moved to the left; the rest of the argument is uniform.

---

## 2. Materials and Methods

We collect here the notation and the auxiliary results used in the proof.

**Notation.** As usual, $d \mid n$ means that the integer $d$ divides the integer $n$, and $d \nmid n$ that it does not. We write $\gcd(a,b)$ for the greatest common divisor of $a$ and $b$, and we say that $a$ and $b$ are *coprime* when $\gcd(a,b) = 1$. Three integers $A, B, C$ are called *pairwise coprime* when $\gcd(A,B) = \gcd(A,C) = \gcd(B,C) = 1$.

**Definition 2.1.** Let $p$ be a prime and $n \in \mathbb{Z} \setminus \{0\}$. The *$p$-adic valuation* of $n$, denoted $\nu_{p}(n)$, is the largest integer $e \geq 0$ such that $p^{e}$ divides $n$. By convention, $\nu_{p}(0) = +\infty$. The $p$-adic valuation is completely multiplicative on $\mathbb{Z} \setminus \{0\}$; in particular, $\nu_{p}(xy) = \nu_{p}(x) + \nu_{p}(y)$ and $\nu_{p}(x^{k}) = k\,\nu_{p}(x)$ for every non-zero integer $x$ and every non-negative integer $k$. It also satisfies the *strict-inequality rule*: if $\nu_{p}(x) \neq \nu_{p}(y)$, then $\nu_{p}(x + y) = \min\{\nu_{p}(x), \nu_{p}(y)\}$.

**Proposition 2.2** (Lifting The Exponent Lemma for the prime $2$ [[Manea2006]](#references)). Let $x, y$ be integers with $2 \nmid x$ and $2 \nmid y$, and let $k$ be a positive integer. Then

$$\nu_{2}(x^{k} - y^{k}) = \begin{cases} \nu_{2}(x - y) & \text{if } k \text{ is odd,} \\ \nu_{2}(x - y) + \nu_{2}(x + y) + \nu_{2}(k) - 1 & \text{if } k \text{ is even.} \end{cases}$$

Throughout the proof this proposition will be invoked in its "subtraction mode": both hypotheses $2 \nmid x$ and $2 \nmid y$ will refer to the two odd bases among $A, B, C$, and the exponent $k$ will always be the even integer $2^{m}$, placing us in the second branch of the formula.

**Proposition 2.3** ($p$-adic valuation of the binomial coefficients $\binom{p^{m}}{k}$ [[Gra94]](#references)). Let $p$ be a prime and let $m$ be a positive integer. For every integer $k$ with $1 \leq k < p^{m}$,

$$\nu_{p}\!\left(\binom{p^{m}}{k}\right) = m - \nu_{p}(k).$$

In particular, specialising to $p = 2$ and $1 \leq k \leq 2^{m} - 1$:
- if $k$ is odd, then $\nu_{2}\!\bigl(\binom{2^{m}}{k}\bigr) = m$;
- if $k = 2^{m-1}$, then $\nu_{2}\!\bigl(\binom{2^{m}}{k}\bigr) = 1$;
- in every other case, $\nu_{2}\!\bigl(\binom{2^{m}}{k}\bigr) \geq 2$.

Together, these two statements provide the arithmetic machinery on which the proof rests.

---

## 3. Main Result

We are now in a position to state and prove the main result.

**Theorem 3.1** (Fermat's Last Theorem). There exist no positive integers $a$, $b$, $c$, and $n$ satisfying $a^{n} + b^{n} = c^{n}$ with $n \geq 3$.

**Proof.** Assume, for contradiction, that there exist positive integers $a, b, c, n$ with $n \geq 3$ and $a^{n} + b^{n} = c^{n}$.

### Step 1: Reduction to an odd prime exponent and a primitive solution.

We first argue that it suffices to prove the theorem for an odd prime exponent. If $4 \mid n$, write $n = 4k$; then $(a^{k})^{4} + (b^{k})^{4} = (c^{k})^{4}$, which contradicts Fermat's classical infinite-descent result for exponent $4$. Hence no solution can exist when $n$ is divisible by $4$. In every other case ($n$ odd, or $n$ even but not divisible by $4$), the exponent $n$ admits an odd prime divisor $p \geq 3$. Writing $n = p\,k$ with $k \geq 1$, the putative solution $a^{n} + b^{n} = c^{n}$ produces $(a^{k})^{p} + (b^{k})^{p} = (c^{k})^{p}$, and setting $A = a^{k}$, $B = b^{k}$, $C = c^{k}$ gives $A^{p} + B^{p} = C^{p}$.

*Reduction to a primitive solution.* Dividing $A, B, C$ by the common factor $\gcd(A, B, C)$, we may assume $\gcd(A, B, C) = 1$. From the identity $A^{p} + B^{p} = C^{p}$, any prime dividing two of the three bases would, via the equation, divide the third as well; hence in fact $A, B, C$ are *pairwise* coprime. We are therefore reduced to the standing assumption

$$\tag{$*$} A^{p} + B^{p} = C^{p}, \qquad p \text{ an odd prime}, \qquad A, B, C \in \mathbb{N} \text{ pairwise coprime}.$$

### Step 2: The parity of $A$, $B$, $C$.

Since $A, B, C$ are pairwise coprime, at most one of them is even. They cannot all be odd, for if $A$ and $B$ were both odd, then $A^{p} + B^{p}$ would be even, forcing $C^{p}$---and hence $C$---to be even. Therefore *exactly one* of $A$, $B$, $C$ is divisible by $2$. Three symmetric cases arise, all of which we treat using the unified template described in the introduction.

---

### Case 1: $2 \mid A$ (so $2 \nmid B$ and $2 \nmid C$)

The two odd bases are now $B$ and $C$. Accordingly, we rearrange ($*$) so as to isolate one of the odd $p$-th powers on the left:

$$\tag{1} B^{p} = C^{p} - A^{p}.$$

**Step 1.1: The valuation parameter $m$.** Because $2 \mid A$, we set

$$m := \nu_{2}(A^{p}) = p\,\nu_{2}(A) \geq 3,$$

the last inequality following from $p \geq 3$ and $\nu_{2}(A) \geq 1$.

**Step 1.2: Raising (1) to the power $2^{m}$ and splitting off the odd endpoint.** Raising both sides of (1) to the power $2^{m}$ and expanding the right-hand side by the binomial theorem,

$$\bigl(B^{p}\bigr)^{2^{m}} = \bigl(C^{p} - A^{p}\bigr)^{2^{m}} = \sum_{k=0}^{2^{m}} \binom{2^{m}}{k}(C^{p})^{k}(-A^{p})^{2^{m}-k}.$$

The *odd* endpoint of this sum is the one at $k = 2^{m}$, namely $(C^{p})^{2^{m}}$ (the $2^{m}$-th power of the second odd base). Moving it to the left-hand side yields the key identity

$$\tag{1$'$} (B^{p})^{2^{m}} - (C^{p})^{2^{m}} = \sum_{k=0}^{2^{m}-1} \binom{2^{m}}{k}(C^{p})^{k}(-A^{p})^{2^{m}-k}.$$

We now show that the left-hand side of (1$'$) has $2$-adic valuation exactly $2m$, whereas the right-hand side has $2$-adic valuation at least $2m + 1$.

**Step 1.3: Valuation of the left-hand side of (1$'$).** Since $B^{p}$ and $C^{p}$ are both odd, Proposition 2.2 applies in *subtraction mode* with $x = B^{p}$, $y = C^{p}$, and even exponent $k = 2^{m}$:

$$\nu_{2}\!\left((B^{p})^{2^{m}} - (C^{p})^{2^{m}}\right) = \nu_{2}(B^{p} - C^{p}) + \nu_{2}(B^{p} + C^{p}) + \nu_{2}(2^{m}) - 1.$$

First, by (1), $B^{p} - C^{p} = -A^{p}$, so $\nu_{2}(B^{p} - C^{p}) = \nu_{2}(A^{p}) = m$. Second, using $A^{p} + B^{p} = C^{p}$,

$$B^{p} + C^{p} = B^{p} + (A^{p} + B^{p}) = 2\,B^{p} + A^{p}.$$

Here $\nu_{2}(2B^{p}) = 1$ (since $B$ is odd) and $\nu_{2}(A^{p}) = m \geq 3$; the two valuations are unequal, so the strict-inequality rule gives $\nu_{2}(B^{p} + C^{p}) = \min\{1, m\} = 1$. Third, $\nu_{2}(2^{m}) = m$. Substituting,

$$\nu_{2}\!\left((B^{p})^{2^{m}} - (C^{p})^{2^{m}}\right) = m + 1 + m - 1 = 2m.$$

**Step 1.4: Valuation of the right-hand side of (1$'$).** For each index $k$ with $0 \leq k \leq 2^{m} - 1$, the factor $(C^{p})^{k}$ is odd, so

$$\nu_{2}\!\left(\binom{2^{m}}{k}(C^{p})^{k}(-A^{p})^{2^{m}-k}\right) = \nu_{2}\!\left(\binom{2^{m}}{k}\right) + (2^{m} - k)\,m,$$

by Proposition 2.3 and the multiplicativity of $\nu_{2}$. A routine check shows that every term has valuation at least $2m$; the minimum is attained at $k = 2^{m} - 1$ (odd, so $\nu_{2}(\binom{2^{m}}{k}) = m$), giving $m + m = 2m$, while every other $k$ yields a strictly larger value.

*Pairing argument.* To upgrade the lower bound on the *sum* from $2m$ to $2m + 1$, we exploit the symmetry $\binom{2^{m}}{k} = \binom{2^{m}}{2^{m} - k}$ by pairing index $k$ (for $1 \leq k \leq 2^{m-1} - 1$) with its complement $2^{m} - k$; both indices lie in the summation range $\{0, 1, \ldots, 2^{m} - 1\}$. The combined contribution of a pair $(k, 2^{m} - k)$ is

$$\binom{2^{m}}{k}\,\Bigl[(C^{p})^{k}(-A^{p})^{2^{m}-k} + (C^{p})^{2^{m}-k}(-A^{p})^{k}\Bigr].$$

When $k$ is odd (so that $2^{m} - k$ is also odd), factoring out $(A^{p})^{k}(C^{p})^{k}$ from the bracket gives

$$-\binom{2^{m}}{k}\,(A^{p})^{k}(C^{p})^{k}\,\Bigl[(A^{p})^{2^{m}-2k} + (C^{p})^{2^{m}-2k}\Bigr].$$

The $2$-adic valuation of the outer product $\binom{2^{m}}{k}(A^{p})^{k}(C^{p})^{k}$ is $m + km + 0 = m(k+1)$, because $k$ is odd (so $\nu_{2}(\binom{2^{m}}{k}) = m$), $\nu_{2}((A^{p})^{k}) = km$, and $\nu_{2}((C^{p})^{k}) = 0$. Inside the bracket, $(A^{p})^{2^{m}-2k}$ has valuation $(2^{m} - 2k)m \geq m$ (since $k < 2^{m-1}$), whereas $(C^{p})^{2^{m}-2k}$ is odd; the strict-inequality rule then gives the bracket valuation at least $1$. Hence the paired contribution has valuation at least $m(k+1) + 1 \geq 2m + 1$, with equality at $k = 1$.

The remaining unpaired indices are $k = 0$ and $k = 2^{m-1}$. The first contributes $(-A^{p})^{2^{m}}$, whose valuation is $m \cdot 2^{m}$---vastly exceeding $2m + 1$. The second contributes $\binom{2^{m}}{2^{m-1}}(C^{p})^{2^{m-1}}(-A^{p})^{2^{m-1}}$, whose valuation is $1 + 0 + 2^{m-1} m$, again well above $2m + 1$ for $m \geq 3$. Combining all contributions,

$$\nu_{2}\!\left(\sum_{k=0}^{2^{m}-1} \binom{2^{m}}{k}(C^{p})^{k}(-A^{p})^{2^{m}-k}\right) \geq 2m + 1.$$

**Step 1.5: Contradiction.** Comparing the two sides of (1$'$),

$$\underbrace{(B^{p})^{2^{m}} - (C^{p})^{2^{m}}}_{\nu_{2}\,=\,2m} = \underbrace{\sum_{k=0}^{2^{m}-1} \binom{2^{m}}{k}(C^{p})^{k}(-A^{p})^{2^{m}-k}}_{\nu_{2}\,\geq\,2m+1}.$$

Equal integers must have equal $2$-adic valuations, so $2m \geq 2m + 1$, which is impossible. Therefore Case 1 admits no solution.

---

### Case 2: $2 \mid B$ (so $2 \nmid A$ and $2 \nmid C$)

This case is entirely symmetric to Case 1 under the interchange of $A$ and $B$---an operation that leaves ($*$) invariant. The two odd bases are now $A$ and $C$. Rearranging ($*$) to isolate an odd $p$-th power,

$$A^{p} = C^{p} - B^{p},$$

and setting $m := \nu_{2}(B^{p}) = p\,\nu_{2}(B) \geq 3$, we raise to the power $2^{m}$ to obtain

$$\bigl(A^{p}\bigr)^{2^{m}} = \bigl(C^{p} - B^{p}\bigr)^{2^{m}} = \sum_{k=0}^{2^{m}} \binom{2^{m}}{k}(C^{p})^{k}(-B^{p})^{2^{m}-k}.$$

The odd endpoint is at $k = 2^{m}$, yielding $(C^{p})^{2^{m}}$. Moving it to the left-hand side gives

$$\tag{2$'$} (A^{p})^{2^{m}} - (C^{p})^{2^{m}} = \sum_{k=0}^{2^{m}-1} \binom{2^{m}}{k}(C^{p})^{k}(-B^{p})^{2^{m}-k}.$$

*Left-hand side.* Since $A^{p}$ and $C^{p}$ are both odd, Proposition 2.2 gives

$$\nu_{2}\!\left((A^{p})^{2^{m}} - (C^{p})^{2^{m}}\right) = \nu_{2}(A^{p} - C^{p}) + \nu_{2}(A^{p} + C^{p}) + m - 1.$$

From $A^{p} - C^{p} = -B^{p}$ we read off $\nu_{2}(A^{p} - C^{p}) = m$. Using the Fermat identity in the form $A^{p} + C^{p} = A^{p} + (A^{p} + B^{p}) = 2A^{p} + B^{p}$, and observing that $\nu_{2}(2A^{p}) = 1$ and $\nu_{2}(B^{p}) = m \geq 3$, the strict-inequality rule gives $\nu_{2}(A^{p} + C^{p}) = 1$. Therefore $\nu_{2}\!\left((A^{p})^{2^{m}} - (C^{p})^{2^{m}}\right) = m + 1 + m - 1 = 2m$.

*Right-hand side.* The sum on the right of (2$'$) is structurally identical to the one in Case 1, with the even base $A^{p}$ replaced by $B^{p}$. Applying the pairing argument of Step 1.4 verbatim (with $A \leftrightarrow B$) yields $\nu_{2}(\cdots) \geq 2m + 1$.

*Contradiction.* The two sides of (2$'$) have valuations $2m$ and $\geq 2m + 1$ respectively, which is impossible. Case 2 therefore admits no solution.

---

### Case 3: $2 \mid C$ (so $2 \nmid A$ and $2 \nmid B$)

In contrast to Cases 1 and 2, the even base $C$ already stands alone on the right-hand side of ($*$), so a mere sign change cannot place an odd $p$-th power in isolation; a genuine rearrangement is required, and the subtraction-mode application of the Lifting The Exponent Lemma then becomes unavoidable.

The two odd bases are $A$ and $B$. Rearranging ($*$),

$$\tag{3} A^{p} = C^{p} - B^{p}.$$

**Step 3.1: The valuation parameter $m$.** Since $2 \mid C$,

$$m := \nu_{2}(C^{p}) = p\,\nu_{2}(C) \geq 3.$$

**Step 3.2: Raising (3) to the power $2^{m}$ and splitting off the odd endpoint.** Raising both sides to the power $2^{m}$ and expanding,

$$(A^{p})^{2^{m}} = (C^{p} - B^{p})^{2^{m}} = (-C^{p} + B^{p})^{2^{m}} = \sum_{k=0}^{2^{m}} \binom{2^{m}}{k}(B^{p})^{k}(-C^{p})^{2^{m}-k}.$$

The odd endpoint is at $k = 2^{m}$, namely $(B^{p})^{2^{m}}$ (the $2^{m}$-th power of the second odd base). Moving it to the left-hand side gives the key identity

$$\tag{3$'$} (A^{p})^{2^{m}} - (B^{p})^{2^{m}} = \sum_{k=0}^{2^{m}-1} \binom{2^{m}}{k}(B^{p})^{k}(-C^{p})^{2^{m}-k}.$$

This has the same structure as (1$'$) and (2$'$), with $C$ now playing the role of the even base.

**Step 3.3: Valuation of the left-hand side of (3$'$).** By Proposition 2.2 applied to the odd integers $A^{p}$ and $B^{p}$ with even exponent $2^{m}$,

$$\nu_{2}\!\left((A^{p})^{2^{m}} - (B^{p})^{2^{m}}\right) = \nu_{2}(A^{p} - B^{p}) + \nu_{2}(A^{p} + B^{p}) + \nu_{2}(2^{m}) - 1.$$

Since $A^{p} + B^{p} = C^{p}$, the second summand is $\nu_{2}(C^{p}) = m$. For the first, the key algebraic manoeuvre is the identity

$$A^{p} - B^{p} = (A^{p} + B^{p}) - 2\,B^{p} = C^{p} - 2\,B^{p},$$

which rewrites the difference of two odd quantities as a difference of terms with *manifestly different* $2$-adic valuations: $\nu_{2}(C^{p}) = m \geq 3$ and $\nu_{2}(2B^{p}) = 1$. The strict-inequality rule yields $\nu_{2}(A^{p} - B^{p}) = 1$. Substituting,

$$\nu_{2}\!\left((A^{p})^{2^{m}} - (B^{p})^{2^{m}}\right) = 1 + m + m - 1 = 2m.$$

**Step 3.4: Valuation of the right-hand side of (3$'$).** The sum on the right of (3$'$) is structurally identical to the one in Cases 1 and 2, with the even base $C^{p}$ now appearing in the factor $(-C^{p})^{2^{m}-k}$. Applying the pairing argument of Step 1.4 verbatim (with $A \leftrightarrow C$) yields

$$\nu_{2}\!\left(\sum_{k=0}^{2^{m}-1} \binom{2^{m}}{k}(B^{p})^{k}(-C^{p})^{2^{m}-k}\right) \geq 2m + 1.$$

**Step 3.5: Contradiction.** Comparing the two sides of (3$'$),

$$\underbrace{(A^{p})^{2^{m}} - (B^{p})^{2^{m}}}_{\nu_{2}\,=\,2m} = \underbrace{\sum_{k=0}^{2^{m}-1} \binom{2^{m}}{k}(B^{p})^{k}(-C^{p})^{2^{m}-k}}_{\nu_{2}\,\geq\,2m+1},$$

yielding $2m \geq 2m + 1$, a contradiction.

---

**Conclusion of the proof.** Each of the three cases above leads to a contradiction. Therefore no positive integers $A, B, C$ with $\gcd(A,B,C) = 1$ can satisfy $A^{p} + B^{p} = C^{p}$ for any odd prime $p$, and---by the reduction carried out in Step 1---no positive integers $a, b, c, n$ with $n \geq 3$ can satisfy $a^{n} + b^{n} = c^{n}$. Fermat's Last Theorem is proved. $\square$

---

## Acknowledgements

The author would like to thank Iris, Marilin, Sonia, Yoselin, and Arelis for their support.

---

## References

**[Fer91]** Fermat, Pierre de (1891). *Oeuvres de Pierre de Fermat*, Volume 1. Edited by Paul Tannery and Jules Tannery. Gauthier-Villars, Paris, France.

**[Eur12]** Euler, Leonhard (2012). *Elements of Algebra*. Springer Science & Business Media, New York, United States. DOI: [10.1007/978-1-4613-8511-0](https://doi.org/10.1007/978-1-4613-8511-0).

**[Ger16]** Germain, Sophie (2016). *Oeuvres philosophiques de Sophie Germain*. Collection XIX, Paris, France.

**[Kum47]** Kummer, Ernst Eduard (1847). *Zur Theorie der complexen Zahlen*. Walter de Gruyter, Berlin/New York. DOI: [10.1007/BF01212902](https://doi.org/10.1007/BF01212902).

**[Wil95]** Wiles, Andrew (1995). "Modular elliptic curves and Fermat's Last Theorem," *Annals of Mathematics*, 141(3), 443--551. JSTOR. DOI: [10.2307/2118559](https://doi.org/10.2307/2118559).

**[Rib95]** Ribet, Kenneth A. (1995). "Galois representations and modular forms," *Bulletin of the American Mathematical Society*, 32(4), 375--402. DOI: [10.1090/S0273-0979-1995-00616-6](https://doi.org/10.1090/S0273-0979-1995-00616-6).

**[beal1997generalization]** Beal, Andrew (1997). "A generalization of Fermat's last theorem: the Beal conjecture and prize problem," *Notices of the AMS*, 44(11), 1436--1437.

**[stewart1986oesterle]** Stewart, Cameron L. and Tijdeman, Robert (1986). "On the Oesterlé-Masser conjecture," *Monatshefte für Mathematik*, 102(3), 251--257. Springer. DOI: [10.1007/BF01294603](https://doi.org/10.1007/BF01294603).

**[Manea2006]** Manea, M. (2006). "Some $a^n \pm b^n$ Problems in Number Theory," *Mathematics Magazine*, 79(2), 140--145. Mathematical Association of America, April 2006. DOI: [10.2307/27642922](https://doi.org/10.2307/27642922).

**[Gra94]** Graham, Ronald L., Knuth, Donald E., and Patashnik, Oren (1994). *Concrete Mathematics: A Foundation for Computer Science*, 2nd ed. Addison-Wesley, Reading, MA.

---

**MSC (2020):** 11D41 (Higher degree equations; Fermat's equation), 11A41 (Primes), 11A05 (Multiplicative structure; Euclidean algorithm; greatest common divisors)

---

**Documentation**

Available as PDF at *[A Note on Fermat's Last Theorem](https://www.preprints.org/manuscript/202109.0480/v21)*.
