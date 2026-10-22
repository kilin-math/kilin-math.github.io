---
layout: post
title: "A coprime double sum, Euler's convolution, and Zagier's telescoping"
date: 2026-10-22 14:00:00 +0800
categories: numbers
---

Consider the following identity, valid for every complex number $a$ with $|a|<1$:

$$
\boxed{\displaystyle
\sum_{\substack{m,n\geq 1\\\gcd(m,n)=1}}
\frac{1}{(m^2-a^2)(n^2-a^2)}
=\frac{5-3a^2}{2(1-a^2)^2}.}
\tag{1}
$$

At $a=0$, it says that

$$
\sum_{\substack{m,n\geq1\\\gcd(m,n)=1}}\frac{1}{m^2n^2}
=\frac{\zeta(2)^2}{\zeta(4)}=\frac52.
$$

There are two proofs of (1). The first reduces the sum to a classical convolution formula for even values of the Riemann zeta function. The second telescopes directly on the Stern–Brocot tree of coprime positive pairs. Both are connected to a remarkably simple construction of Don Zagier.

## First proof: coprime Dirichlet series and Euler's convolution

For $\Re s,\Re t>1$, grouping positive integer pairs by their greatest common divisor gives

$$
\zeta(s)\zeta(t)
=\sum_{d=1}^{\infty}d^{-s-t}
  \sum_{\substack{m,n\geq1\\\gcd(m,n)=1}}m^{-s}n^{-t},
$$

hence

$$
\sum_{\substack{m,n\geq1\\\gcd(m,n)=1}}\frac1{m^s n^t}
=\frac{\zeta(s)\zeta(t)}{\zeta(s+t)}.
\tag{2}
$$

Expand each denominator of (1) in a geometric series. Absolute convergence for $|a|<1$ permits rearrangement:

$$
\begin{aligned}
S(a)
&=\sum_{\substack{m,n\geq1\\\gcd(m,n)=1}}
\frac1{m^2n^2}
\sum_{p,q\geq0}\frac{a^{2p+2q}}{m^{2p}n^{2q}}\\
&=\sum_{r=0}^{\infty} a^{2r}
\sum_{j=0}^{r}
\frac{\zeta(2j+2)\zeta(2r-2j+2)}{\zeta(2r+4)}.
\end{aligned}
$$

The classical **Euler convolution formula** is

$$
\boxed{\displaystyle
\sum_{j=1}^{N-1}\zeta(2j)\zeta(2N-2j)
=\left(N+\frac12\right)\zeta(2N),\qquad N\geq2.}
\tag{3}
$$

Applying (3) with $N=r+2$, we obtain

$$
\begin{aligned}
S(a)
&=\sum_{r=0}^{\infty}\left(r+\frac52\right)a^{2r}\\
&=\frac{5}{2(1-a^2)}+\frac{a^2}{(1-a^2)^2}\\
&=\frac{5-3a^2}{2(1-a^2)^2}.
\end{aligned}
$$

A proof of Euler's formula (3), using Zagier's rational functions, is given below. Thus no evaluation of individual zeta values is needed.

## Second proof: telescoping on coprime pairs

Define

$$
H_a(m,n)=
\frac{2m^2+2n^2+mn-3a^2}
{2mn(m^2-a^2)(n^2-a^2)}.
\tag{4}
$$

The key algebraic identity is

$$
\boxed{\displaystyle
H_a(m,n)-H_a(m+n,n)-H_a(m,m+n)
=\frac1{(m^2-a^2)(n^2-a^2)}.}
\tag{5}
$$

Here is a way to verify (5) without expanding one large numerator. Write $t=a^2$ and $H_a=T+I$, where

$$
T(m,n)=\frac1{mn}
\left(\frac1{m^2-t}+\frac1{n^2-t}\right),
\qquad
I(m,n)=\frac{mn+t}{2mn(m^2-t)(n^2-t)}.
$$

For any function $F$, let

$$
\Delta F(m,n)=F(m,n)-F(m+n,n)-F(m,m+n).
$$

Putting $u=m+n$, straightforward common-denominator calculations yield

$$
\Delta T(m,n)
=\frac{m^2+mn+n^2-3t}
{(m^2-t)(n^2-t)(u^2-t)}
$$

and

$$
\Delta I(m,n)
=\frac{mn+2t}
{(m^2-t)(n^2-t)(u^2-t)}.
$$

The two numerators add to
$m^2+2mn+n^2-t=u^2-t$, proving (5).

Every coprime pair $(m,n)$ other than $(1,1)$ has exactly one parent:

$$
(m,n)\longmapsto
\begin{cases}
(m-n,n),&m>n,\\
(m,n-m),&n>m.
\end{cases}
$$

Equivalently, the maps

$$
(m,n)\longmapsto(m+n,n),\qquad
(m,n)\longmapsto(m,m+n)
$$

enumerate all coprime positive pairs except $(1,1)$, each exactly once. Thus the sum of the coboundary in (5) *should* collapse to $H_a(1,1)$.

There is a small convergence issue worth making explicit: $H_a(m,n)$ is **not** absolutely summable over all pairs. For example, $H_a(m,1)$ behaves like a constant times $1/m$. We must telescope over finite sets before taking a limit.

Set

$$
Q_N=\{(m,n):1\leq m,n\leq N,\ \gcd(m,n)=1\}.
$$

Cancellation inside this square gives the exact finite identity

$$
\begin{aligned}
\sum_{(m,n)\in Q_N}\Delta H_a(m,n)
&=H_a(1,1)-E_N,\\
E_N
&=\sum_{\substack{(m,n)\in Q_N\\m+n>N}}
\bigl(H_a(m+n,n)+H_a(m,m+n)\bigr).
\end{aligned}
\tag{6}
$$

For fixed $|a|<1$, there is a constant $C_a$ such that

$$
|H_a(x,y)|\leq C_a
\left(\frac1{xy^3}+\frac1{x^2y^2}+\frac1{x^3y}\right)
\qquad(x,y\geq1).
\tag{7}
$$

For fixed $n\leq N$, there are at most $n$ integers $m\leq N$ satisfying $m+n>N$. As $m+n>N$, equation (7) bounds one half of the error in (6) by

$$
C_a\sum_{n=1}^N n
\left(\frac1{Nn^3}+\frac1{N^2n^2}+\frac1{N^3n}\right)
=O_a(N^{-1}).
$$

The other half is symmetric, so $E_N\to0$. Since the right side of (5) is absolutely summable over positive pairs, we can let $N\to\infty$ in (6):

$$
\sum_{\substack{m,n\geq1\\\gcd(m,n)=1}}
\frac1{(m^2-a^2)(n^2-a^2)}
=H_a(1,1)
=\frac{5-3a^2}{2(1-a^2)^2}.
$$

This proves (1) again, without invoking zeta functions.

## Zagier's identities, and a proof

In [*Values of Zeta Functions and Their Applications*](https://people.mpim-bonn.mpg.de/zagier/files/scanned/ValuesofZetaFunsAndApplications/fulltext.pdf) (1994, pp. 498–499), Don Zagier considers, for every even integer $k\geq4$, the rational function

$$
f_k(m,n)=
\frac1{mn^{k-1}}
+\frac12\sum_{j=2}^{k-2}\frac1{m^j n^{k-j}}
+\frac1{m^{k-1}n}.
\tag{8}
$$

**Zagier's rational identity** is

$$
\boxed{\displaystyle
f_k(m,n)-f_k(m+n,n)-f_k(m,m+n)
=\sum_{\substack{2\leq j\leq k-2\\j\ \mathrm{even}}}
\frac1{m^j n^{k-j}}.}
\tag{9}
$$

Zagier writes down both the explicit function and identity, illustrates the case $k=4$, and states that the higher-weight identities can be checked directly. Junesang Choi later provided a longer verification in [*Several Results Associated with the Riemann Zeta Function*](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART001375712) (2009, §2, equations (2.5)–(2.7)). Here is another complete proof, by generating functions.

### Proof of the rational identity

The rational function $H_a$ in (4) is exactly the generating function of Zagier's potentials:

$$
\boxed{\displaystyle
H_a(m,n)=\sum_{r=0}^{\infty}a^{2r}f_{2r+4}(m,n).}
\tag{10}
$$

Indeed, the two endpoint terms in (8) contribute

$$
\sum_{r\geq0}a^{2r}
\left(\frac1{mn^{2r+3}}+\frac1{m^{2r+3}n}\right)
=\frac1{mn(n^2-a^2)}+\frac1{mn(m^2-a^2)}.
$$

For the remaining terms, use the elementary even-degree projection

$$
\begin{aligned}
&\frac12\sum_{r\geq0}a^{2r}
\sum_{j=2}^{2r+2}\frac1{m^j n^{2r+4-j}}\\
&\qquad=\frac1{4m^2n^2}
\left(
\frac1{(1-a/m)(1-a/n)}
+\frac1{(1+a/m)(1+a/n)}
\right)\\
&\qquad=\frac{mn+a^2}{2mn(m^2-a^2)(n^2-a^2)}.
\end{aligned}
$$

Adding the endpoint contributions gives precisely (4), proving (10). All these expansions converge for $|a|<1$.

Now apply $\Delta$ to (10). The already verified rational identity (5) gives

$$
\begin{aligned}
\sum_{r\geq0}a^{2r}\Delta f_{2r+4}(m,n)
&=\Delta H_a(m,n)\\
&=\frac1{(m^2-a^2)(n^2-a^2)}\\
&=\sum_{r\geq0}a^{2r}
\sum_{j=0}^r
\frac1{m^{2j+2}n^{2r-2j+2}}.
\end{aligned}
$$

Comparing coefficients of $a^{2r}$ proves (9) for every $k=2r+4$. This supplies the algebraic verification that Zagier leaves to the reader, without needing Choi's induction.

### Summing Zagier's identity: Euler's convolution

Summing the right side of (9) over $m,n\geq1$ gives

$$
\sum_{\substack{2\leq j\leq k-2\\j\ \mathrm{even}}}
\zeta(j)\zeta(k-j).
\tag{11}
$$

For the left side, the two substitutions

$$
(m,n)\mapsto(m+n,n),\qquad
(m,n)\mapsto(m,m+n)
$$

cover exactly the positive pairs off the diagonal. Formally, the sum of the coboundary is therefore $\sum_{n\geq1}f_k(n,n)$. As before, this needs a finite-cutoff justification because the individual sums of $f_k$ diverge.

Summing (9) over $1\leq m,n\leq N$, the terms whose images stay inside the square cancel, leaving

$$
\sum_{m,n=1}^N\Delta f_k(m,n)
=\sum_{n=1}^N f_k(n,n)
-\sum_{\substack{1\leq m,n\leq N\\m+n>N}}
\bigl(f_k(m+n,n)+f_k(m,m+n)\bigr).
\tag{12}
$$

Because $k\geq4$, formula (8) implies

$$
0\leq f_k(x,y)\leq C_k
\left(\frac1{xy^3}+\frac1{x^2y^2}+\frac1{x^3y}\right).
$$

The same estimate used in (6)–(7) shows that the error term in (12) is $O_k(N^{-1})$. On the diagonal, every term in (8) equals a constant times $n^{-k}$, giving

$$
f_k(n,n)=\left(2+\frac{k-3}{2}\right)\frac1{n^k}
=\frac{k+1}{2n^k}.
$$

Passing to the limit in (12), we obtain

$$
\boxed{\displaystyle
\sum_{\substack{2\leq j\leq k-2\\j\ \mathrm{even}}}
\zeta(j)\zeta(k-j)
=\frac{k+1}{2}\zeta(k),\qquad k\geq4\ \mathrm{even}.}
\tag{13}
$$

Setting $k=2N$ recovers exactly Euler's formula (3). For instance, the case $k=4$ is

$$
\zeta(2)^2=\frac52\zeta(4),
$$

and, starting with Euler's evaluation $\zeta(2)=\pi^2/6$, identity (13) recursively determines every $\zeta(2N)$.

## A remark on the relationship between the proofs

Zagier's proof of (13) telescopes over **all** positive pairs: the surviving terms lie on the diagonal $(n,n)$. Restricting the same coboundary to **coprime** positive pairs leaves only the root $(1,1)$. This is why the same elementary mechanism evaluates both a convolution of zeta values and the one-parameter coprime double sum (1).

Equation (10) packages Zagier's whole family of rational potentials into a single rational function. It is a convenient reformulation of his construction, not a claim that the original one-parameter identity appears explicitly in his paper.

## References

1. **L. Euler.** Classical convolution and recurrence relations for even zeta values and Bernoulli numbers. The zeta recurrence is recorded in the [NIST Digital Library of Mathematical Functions, §25.6(iii), equation 25.6.16](https://dlmf.nist.gov/25.6.E16).
2. **D. Zagier.** [*Values of Zeta Functions and Their Applications*](https://people.mpim-bonn.mpg.de/zagier/files/scanned/ValuesofZetaFunsAndApplications/fulltext.pdf), in *First European Congress of Mathematics*, Vol. II, Progress in Mathematics **120**, Birkhäuser, 1994, pp. 497–512. See §1, especially pp. 498–499.
3. **J. Choi.** [*Several Results Associated with the Riemann Zeta Function*](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART001375712), *Journal of the Chungcheong Mathematical Society* **22** (2009), no. 3, 467–480. See §2 for a detailed algebraic verification of Zagier's identity.
