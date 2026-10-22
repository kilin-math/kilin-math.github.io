---
layout: post
title: "A coprime double sum with only one pole"
date: 2026-10-22 14:00:00 +0800
categories: numbers
---

Here is a small puzzle. Why is

$
\sum_{\substack{m,n\geq1\cr (m,n)=1}}\frac{1}{(m^2+1)(n^2+1)}=1\,?
$

In fact, a parameter gives the slightly surprising identity

$
\boxed{\displaystyle \sum_{\substack{m,n\geq1\cr (m,n)=1}}\frac{1}{(m^2-r)(n^2-r)}=\frac{5-3r}{2(1-r)^2}.} \qquad\text{(1)}
$

It holds for every real $r<1$, and indeed for every complex $r$ which is not a positive integer square. The summands have poles at all integer squares, but the answer has a pole only at $r=1$. Where did all the others go?

We give two proofs: one by Euler's convolution of even zeta values, the other by telescoping on coprime pairs. The latter is a generating-function version of a construction of Don Zagier.

## First proof: Euler's convolution

For $\Re s,\Re t>1$, separating the greatest common divisor in the product $\zeta(s)\zeta(t)$ gives

$
\sum_{\substack{m,n\geq1\cr (m,n)=1}}\frac{1}{m^s n^t}=\frac{\zeta(s)\zeta(t)}{\zeta(s+t)}. \qquad\text{(2)}
$

Write $S(r)$ for the left side of (1). For $\lvert r\rvert<1$, geometric expansion and (2) give

$
S(r)=\sum_{h\geq0}r^h\sum_{j=0}^{h}\frac{\zeta(2j+2)\zeta(2h-2j+2)}{\zeta(2h+4)}.
$

Now Euler's convolution formula says that

$
\sum_{j=1}^{N-1}\zeta(2j)\zeta(2N-2j)=\left(N+\frac12\right)\zeta(2N)\qquad(N\geq2). \qquad\text{(3)}
$

With $N=h+2$, this turns the double sum into

$
S(r)=\sum_{h\geq0}\left(h+\frac52\right)r^h=\frac{5-3r}{2(1-r)^2}.
$

Both sides are holomorphic away from the positive integer squares. The identity theorem proves (1) throughout that domain. We shall prove (3) below, following Zagier.

## Second proof: a Stern--Brocot telescoping

The rational function

$
H_r(m,n)=\frac{2m^2+2n^2+mn-3r}{2mn(m^2-r)(n^2-r)} \qquad\text{(4)}
$

has the remarkable property

$
\boxed{\displaystyle H_r(m,n)-H_r(m+n,n)-H_r(m,m+n)=\frac{1}{(m^2-r)(n^2-r)}.} \qquad\text{(5)}
$

For a quick verification, split $H_r=T_r+I_r$, where

$
T_r(m,n)=\frac{1}{mn}\left(\frac{1}{m^2-r}+\frac{1}{n^2-r}\right),\qquad I_r(m,n)=\frac{mn+r}{2mn(m^2-r)(n^2-r)}.
$

Put $u=m+n$ and $\Delta F(m,n)=F(m,n)-F(u,n)-F(m,u)$. Then

$
\Delta T_r=\frac{m^2+mn+n^2-3r}{(m^2-r)(n^2-r)(u^2-r)},\qquad \Delta I_r=\frac{mn+2r}{(m^2-r)(n^2-r)(u^2-r)}.
$

Their sum is $1/((m^2-r)(n^2-r))$, as claimed.

Every coprime pair other than $(1,1)$ has exactly one parent, obtained by subtracting the smaller coordinate from the larger. Thus the two maps

$
(m,n)\longmapsto(m+n,n),\qquad (m,n)\longmapsto(m,m+n)
$

enumerate all coprime positive pairs except $(1,1)$. Summing (5) ought to leave only $H_r(1,1)$, which is precisely the right side of (1).

Here is the small convergence detail. Let $Q_N$ be the coprime pairs with $1\leq m,n\leq N$. Cancellation gives

$
\sum_{(m,n)\in Q_N}\Delta H_r(m,n)=H_r(1,1)-\sum_{\substack{(m,n)\in Q_N\cr m+n>N}}\bigl(H_r(m+n,n)+H_r(m,m+n)\bigr).
$

For fixed $r$ away from the positive squares,

$
\lvert H_r(x,y)\rvert\ll_r\frac{1}{xy^3}+\frac{1}{x^2y^2}+\frac{1}{x^3y}\qquad(x,y\geq1).
$

For each $n\leq N$, at most $n$ values of $m\leq N$ have $m+n>N$. The displayed bound makes the entire boundary sum $O_r(N^{-1})$. The summand in (1) is absolutely summable, so (5) telescopes rigorously to $S(r)=H_r(1,1)$.

## Zagier's identity

Zagier [1994, pp. 498--499] starts with the rational functions, for even $k\geq4$,

$
f_k(m,n)=\frac{1}{mn^{k-1}}+\frac12\sum_{j=2}^{k-2}\frac{1}{m^j n^{k-j}}+\frac{1}{m^{k-1}n}. \qquad\text{(6)}
$

His key observation is

$
\boxed{\displaystyle \Delta f_k(m,n)=\sum_{\substack{2\leq j\leq k-2\cr j\ \mathrm{even}}}\frac{1}{m^j n^{k-j}}.} \qquad\text{(7)}
$

In fact, our rational function (4) is nothing but the generating function of all these $f_k$:

$
\boxed{\displaystyle H_r(m,n)=\sum_{h\geq0}r^h f_{2h+4}(m,n).} \qquad\text{(8)}
$

To see this, sum the two endpoint terms of (6) geometrically; they give $T_r$. The middle terms give $I_r$, by taking the even-degree part of a product of two geometric series. Explicitly,

$
\frac12\sum_{h\geq0}r^h\sum_{j=2}^{2h+2}\frac{1}{m^j n^{2h+4-j}}=\frac{mn+r}{2mn(m^2-r)(n^2-r)}.
$

Apply $\Delta$ to (8), use (5), and compare coefficients of $r^h$ in

$
\frac{1}{(m^2-r)(n^2-r)}=\sum_{h\geq0}r^h\sum_{j=0}^{h}\frac{1}{m^{2j+2}n^{2h-2j+2}}.
$

This proves (7), including the algebraic verification omitted in Zagier's short account (and supplied by a different argument in Choi [2009]).

To obtain Euler's formula, sum (7) over all positive $m,n$. The two child maps now cover all pairs *off the diagonal*, so that

$
\sum_{m,n\geq1}\Delta f_k(m,n)=\sum_{n\geq1}f_k(n,n)=\frac{k+1}{2}\zeta(k).
$

As above, take finite square cutoffs first: $f_k$ satisfies the same type of bound as $H_r$, and the boundary error tends to zero. The right side of (7), summed over all pairs, is $\sum_{2\leq j\leq k-2,\ j\ \mathrm{even}}\zeta(j)\zeta(k-j)$. Therefore

$
\boxed{\displaystyle \sum_{\substack{2\leq j\leq k-2\cr j\ \mathrm{even}}}\zeta(j)\zeta(k-j)=\frac{k+1}{2}\zeta(k)\qquad(k\geq4\ \mathrm{even}).}
$

This is Euler's formula (3). Zagier's summation over *all* pairs leaves the diagonal; summation over *coprime* pairs leaves just its first point $(1,1)$.

## Where have the poles gone?

There is an unexpectedly simple answer. For every integer $k\geq2$,

$
\boxed{\displaystyle \sum_{\substack{n\geq1\cr (n,k)=1}}\frac{1}{n^2-k^2}=0.} \qquad\text{(9)}
$

Indeed,

$
\frac{1}{n^2-k^2}=\frac{1}{2k}\left(\frac{1}{n-k}-\frac{1}{n+k}\right).
$

Since coprimality with $k$ is unchanged by translating an integer by $k$, shifting the two sums (first with a finite cutoff) reduces their difference to

$
\frac{1}{2k}\sum_{\substack{-k<t<k\cr (t,k)=1}}\frac1t=0,
$

by pairing $t$ with $-t$; the cutoff error is $O_k(N^{-1})$. The residue of the double sum at $r=k^2$ is $-2$ times the left side of (9), so it vanishes. Thus the apparent singularities at $4,9,16,\ldots$ are removable. The original summands are undefined there, of course, but the sum has a finite analytic continuation.

Two more consequences are worth recording. By symmetry, the diagonal contributes only $(m,n)=(1,1)$, and so (1) gives the even simpler identity

$
\boxed{\displaystyle \sum_{\substack{1\leq m<n\cr (m,n)=1}}\frac{1}{(m^2-r)(n^2-r)}=\frac{3}{4(1-r)}.} \qquad\text{(10)}
$

Also, restricting to pairs of *fixed* greatest common divisor $d$, rather than to coprime pairs, amounts to replacing $(m,n)$ by $(dm,dn)$:

$
\sum_{\substack{m,n\geq1\cr (m,n)=d}}\frac{1}{(m^2-r)(n^2-r)}=\frac{5d^2-3r}{2d^2(d^2-r)^2}. \qquad\text{(11)}
$

## The cotangent behind the sum

Put $A(r)=\sum_{n\geq1}(n^2-r)^{-1}$. The classical partial-fraction expansion of the cotangent is

$
\pi\cot(\pi z)=\frac1z+\sum_{n\geq1}\frac{2z}{z^2-n^2}=\frac1z-2zA(z^2).
$

Now $p(z)=\pi\cot(\pi z)$ satisfies $p'(z)=-\pi^2-p(z)^2$. Substituting $p(z)=z^{-1}-2zA(z^2)$, with $r=z^2$, we obtain

$
-\frac1{z^2}-2A(r)-4rA'(r)=-\pi^2-\left(\frac1z-2zA(r)\right)^2,
$

or simply

$
\boxed{\displaystyle A(r)^2=A'(r)+\frac{3}{2r}\bigl(A(r)-\zeta(2)\bigr).} \qquad\text{(12)}
$

But (12) is also what we get by *forgetting coprimality*. Indeed, grouping all positive pairs by their greatest common divisor and using (1),

$
\begin{aligned} A(r)^2&=\sum_{d\geq1}\frac1{d^4}S\!\left(\frac{r}{d^2}\right)\\&=\sum_{d\geq1}\frac{5d^2-3r}{2d^2(d^2-r)^2}\\&=\sum_{d\geq1}\left[\frac1{(d^2-r)^2}+\frac{3}{2r}\left(\frac1{d^2-r}-\frac1{d^2}\right)\right],\end{aligned}
$

which is exactly (12). Conversely, Mobius inversion gives $S(r)=\sum_{d\geq1}\mu(d)d^{-4}A(r/d^2)^2$. Thus (1) is the **coprime version of the cotangent Riccati equation**.

Finally, expanding $A(r)=\sum_{j\geq0}\zeta(2j+2)r^j$ and comparing coefficients in (12) gives

$
\sum_{j=0}^h\zeta(2j+2)\zeta(2h-2j+2)=\left(h+\frac52\right)\zeta(2h+4),
$

which is just Euler's formula (3).

A natural question is what happens with two different parameters $r$ and $s$. Then the coefficient of $r^i s^j$ is

$
\frac{\zeta(2i+2)\zeta(2j+2)}{\zeta(2i+2j+4)},
$

and it is only on the diagonal $r=s$ that Euler's convolution immediately collapses all coefficients of a given total degree.

## References

1. **L. Euler.** The convolution recurrence for even zeta values; see [DLMF 25.6.16](https://dlmf.nist.gov/25.6.E16). The cotangent partial-fraction formula is [DLMF 4.22.3](https://dlmf.nist.gov/4.22.E3).
2. **D. Zagier.** [*Values of Zeta Functions and Their Applications*](https://people.mpim-bonn.mpg.de/zagier/files/scanned/ValuesofZetaFunsAndApplications/fulltext.pdf), *First European Congress of Mathematics*, Vol. II, Progress in Mathematics **120**, Birkhauser, 1994, 497--512, especially pp. 498--499.
3. **J. Choi.** [*Several Results Associated with the Riemann Zeta Function*](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART001375712), *Journal of the Chungcheong Mathematical Society* **22** (2009), 467--480, Section 2.
