# Hosted Twin Prime research responses

Private research snapshot. Captured 25 November 2026 from the 13 conversations listed in the Twin Prime Conjecture — Research project. This preserves substantive assistant replies recovered from the visible conversation pages, with mathematics transcribed from their displayed TeX. It is not an account export. User messages, progress indicators, and binary attachments are omitted. These replies contain working arguments, superseded claims, and open questions. The separate historical archive preserves original source files and earlier manuscripts.

## Confirm Twin Prime Proof Rules

[Original conversation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6b05e29c-2148-83ee-b4c5-1176ac022aef)

### Recovered response 1

1. Exact isolation of the cofactor-one term

Let

$$
L=\log X,\qquad
J_X=\int_X^{2X}\frac{dt}{\log t},
$$

and define the logarithmically weighted twin-prime count

$$
T_X=\sum_{\substack{X<p\le 2X\\
p,\ p+2\ \mathrm{prime}}}\log(p+2).
$$

The objective is to prove $T_X>0$ for an unbounded sequence of $X$.

Consider the product

$$
\mathcal P_X=\prod_{\substack{X<p\le2X\\p\ \mathrm{prime}}}(p+2).
$$

There is a slightly sharper version of the proposed largest-prime-factor criterion. Since $p+2$ is odd, any nonunit cofactor of a prime divisor is at least three. Consequently,

$$
\boxed{
T_X=
\sum_{\substack{q>(2X+2)/3\\q\ \mathrm{prime}}}
v_q(\mathcal P_X)\log q
}
$$

for sufficiently large $X$.

Thus a prime divisor exceeding $(2X+2)/3$, rather than $X+2$, already suffices.

More generally, define

$$
H_X(Y)=
\sum_{\substack{X<p\le2X\\p\ \mathrm{prime}}}
\sum_{\substack{q\mid p+2\\q>Y\\q\ \mathrm{prime}}}
\log q.
$$

For $Y>\sqrt{2X+2}$, each contributing integer has exactly one prime divisor exceeding $Y$. Writing $p+2=kq$ gives the exact decomposition

$$
H_X(Y)=T_X+
\sum_{\substack{3\le k\le(2X+2)/Y\\k\ \mathrm{odd}}}
\ \sum_{\substack{q>Y,\ q\ \mathrm{prime}\\
X<kq-2\le2X\\kq-2\ \mathrm{prime}}}
\log q,
$$

provided $Y\le X+2$.

Every term in the second sum is a genuine prime pair of the form $q,kq-2$, but it need not be a twin-prime pair.

This identifies the precise quantity that must be removed. A lower bound for $H_X(Y)$ alone cannot establish the result.

2. A cofactor weight whose complete mean can be evaluated

A direct cancellation of the odd cofactors would use the identity

$$
\sum_{d\mid k}\mu(d)=\mathbf1_{k=1}.
$$

The difficulty is that opening this complete divisor sum can produce moduli almost as large as $X$. Instead, I tested a truncated version for which the entire logarithmic mean is accessible.

Fix constants $h,\delta>0$ satisfying

$$
h+\delta<\frac12.
$$

Choose a smooth function $f$ with values in $[0,1]$, equal to one on $[0,1/2]$ and zero on $[1,\infty)$. Put

$$
a_d=\mu(d)f\left(\frac{\log d}{\delta L}\right),
\qquad
A_\delta(k)=\sum_{d\mid k}a_d.
$$

This weight has three important exact properties:

-

$A_\delta(1)=1$.

-

$A_\delta(k)=0$ when $1<k\le X^{\delta/2}$.

-

$A_\delta(k)=1$ whenever every prime factor of $k$ exceeds $X^\delta$.

Define

$$
S_{h,\delta}(X)=
\sum_{\substack{X<p\le2X\\p\ \mathrm{prime}}}
\sum_{\substack{q\mid p+2,\ q>X^h\\q\ \mathrm{prime}}}
(\log q)A_\delta\left(\frac{p+2}{q}\right).
$$

Here all qualifying prime divisors are included, not just the largest. This modification allows an exact convolution calculation.

Write

$$
K_0=2\prod_{\ell>2,\ \ell\ \mathrm{prime}}
\left(1-\frac1{(\ell-1)^2}\right).
$$

Proposition. For every fixed admissible $h,\delta,f$,

$$
\boxed{S_{h,\delta}(X)=K_0J_X+o(J_X).}
\tag{1}
$$

This is unconditional.

Proof

First include every prime-power marker $r$, weighted by the von Mangoldt function. The identity $\sum_{r\mid m}\Lambda(r)=\log m$ gives

$$
\begin{aligned}
\sum_{r\mid N}\Lambda(r)A_\delta(N/r)
&=\sum_{d\mid N}a_d
  \sum_{r\mid N/d}\Lambda(r)\\
&=\sum_{d\mid N}a_d\log(N/d).
\end{aligned}
$$

Apply this with $N=p+2$. The maximal Bombieri–Vinogradov theorem evaluates the resulting prime-progression sums because $d\le X^\delta$. It also permits removal of the markers $r\le X^h$, since their opened moduli satisfy

$$
dr\le X^{h+\delta}.
$$

This has a fixed power margin below $X^{1/2}$. The combined coefficient multiplicity at a modulus $m$ costs at most $\sum_{r\mid m}\Lambda(r)=\log m$, which can be absorbed by taking a stronger logarithmic error estimate. The classical distribution theorem originates in Bombieri's On the large sieve.

cambridge.org+1

For completeness, the two arithmetic moments determining the main term are

$$
\sum_{d\ \mathrm{odd}}\frac{a_d}{\varphi(d)}=o(L^{-1}),
$$

$$
\sum_{d\ \mathrm{odd}}
\frac{a_d\log d}{\varphi(d)}
=-K_0+o(1).
$$

They follow from the Dirichlet series

$$
\sum_{d\ \mathrm{odd}}
\frac{\mu(d)}{\varphi(d)d^s}
=\frac{E(s)}{\zeta(1+s)},
$$

where

$$
E(s)=
\frac1{1-2^{-1-s}}
\prod_{\ell>2}
\frac{1-\ell^{-s}/(\ell-1)}
     {1-\ell^{-1-s}}.
$$

The product is absolutely convergent near $s=0$, and $E(0)=K_0$. Its zero-order moment therefore vanishes, while the logarithmic moment is $-K_0$. The classical Möbius summatory estimate and partial summation justify truncation by the flat smooth function $f$, with errors smaller than every fixed inverse power of $L$.

It remains to check that removing the low prime-power markers does not introduce a new main term. For $r=\ell^j$, with $\ell$ odd,

$$
\sum_{d\ \mathrm{odd}}\frac{a_d}{\varphi(dr)}
=
\frac1{\varphi(r)}
\left(
\sum_d\frac{a_d}{\varphi(d)}
-\frac1\ell
\sum_{\ell\mid d}\frac{a_d}{\varphi(d)}
\right),
$$

where the $d$-sums are over odd integers.

This accounts for shared prime factors; treating $\varphi(dr)$ as always multiplicative would be incorrect.

For $\ell\le X^{\delta/4}$, the second sum is arbitrarily logarithmically small after writing $d=\ell e$ and removing the Euler factor at $\ell$. The removed factor has uniformly bounded absolute coefficient norm in a fixed neighborhood of $s=0$, and the translated cutoff is still flat through $e\le X^{\delta/4}$.

For larger $\ell$, its contribution inside the parentheses is bounded by

$$
O\left(\frac{L}{\ell(\ell-1)}\right).
$$

Since $\sum_{r\le X^h}\Lambda(r)/\varphi(r)=O(L)$, the complete low-marker principal contribution is $o(J_X)$.

Finally, proper prime powers $r=\ell^j>X^h$, $j\ge2$, can be removed at cost $o(J_X)$. Their number up to $t$ is $O(\sqrt t\log t)$; summing their divisibility incidences and using the standard divisor bound gives a power saving for fixed $h>0$.

This proves (1).

3. The resulting sufficient inequality for twin primes

Separate the unit explicitly:

$$
S_{h,\delta}(X)=T_X+C_{h,\delta}(X),
$$

where

$$
C_{h,\delta}(X)=
\sum_{\substack{X<p\le2X\\p\ \mathrm{prime}}}
\sum_{\substack{q\mid p+2,\ q>X^h\\
q\ \mathrm{prime},\ k=(p+2)/q\ge3}}
(\log q)A_\delta(k).
$$

It follows that

$$
\boxed{
T_X=K_0J_X-C_{h,\delta}(X)+o(J_X).
}
\tag{2}
$$

In particular, the concrete sufficient implication is

$$
\liminf_{X\to\infty}
\frac{C_{h,\delta}(X)}{K_0J_X}<1
\quad\Longrightarrow\quad
\text{infinitely many twin primes}.
$$

The cofactor-one coefficient is exactly one. There is no almost-prime substitution in this implication.

The remaining task is a one-sided bound on the actual signed nonunit contribution.

4. Returning to the actual largest prime factor

The multiple-marker issue in (1) can also be removed with a controlled error.

Take

$$
h=\frac12-\varepsilon,\qquad
\delta=\frac{\varepsilon}{4},
$$

where $0<\varepsilon<1/50$ is fixed before $X\to\infty$.

Let $P^+(N)$ denote the largest prime factor of $N$, and put

$$
\mathcal L_\varepsilon(X)=
\sum_{\substack{X<p\le2X,\ p\ \mathrm{prime}\\
P^+(p+2)>X^h}}
\log P^+(p+2)\,
A_\delta\left(\frac{p+2}{P^+(p+2)}\right).
$$

I obtain the following largest-factor version of (1):

$$
\boxed{
\limsup_{X\to\infty}
\left|
\frac{\mathcal L_\varepsilon(X)}{K_0J_X}-1
\right|
\ll_f \varepsilon.
}
\tag{3}
$$

The implied constant is independent of sufficiently small fixed $\varepsilon$.

Proof of the multiple-marker error

Because $h>1/3$, there can be at most two distinct prime divisors above $X^h$.

If there are two, write

$$
p+2=mq_1q_2,\qquad X^h<q_1<q_2.
$$

Then

$$
m\le3X^{2\varepsilon},
$$

and both marked cofactors have the identical weight $A_\delta(m)$: neither large prime can occur in a divisor below $X^\delta$.

Removing the smaller marker therefore costs at most

$$
\sum_{\substack{mq_1q_2-2\ \mathrm{prime}\\
X<mq_1q_2-2\le2X\\
X^h<q_1<q_2,\ q_1,q_2\ \mathrm{prime}}}
(\log q_1)|A_\delta(m)|.
$$

For fixed $m,q_1$, upper-bound sieve the two forms

$$
t,\qquad mq_1t-2.
$$

The uniform two-form upper bound is

$$
\ll
\frac{X D(mq_1)}{mq_1L^2},
\qquad
D(v)=\prod_{\substack{\ell\mid v\\\ell>2}}
\frac{\ell-1}{\ell-2}.
$$

The sieve bound applies uniformly here because the variable $t=q_2$ has available scale at least $X^h$ on every nonempty row. At an odd prime dividing $mq_1$, there is one forbidden residue rather than two; the factor $D(mq_1)$ accounts for precisely this change.

Consequently, the error is bounded by

$$
\ll \frac XL
\left(\sum_{m\le3X^{2\varepsilon}}
\frac{|A_\delta(m)|D(m)}m\right)
\left(\sum_{X^h<q_1\le\sqrt{2X+2}}
\frac{D(q_1)}{q_1}\right).
\tag{4}
$$

The second factor tends to

$$
\log\left(\frac{1/2}{1/2-\varepsilon}\right)
=O(\varepsilon).
$$

For the first factor, extend $f$ smoothly to a compactly supported function on the real line. Fourier inversion gives

$$
A_\delta(m)=\frac1{2\pi}
\int_{\mathbb R}\widehat f(t)
\prod_{\ell\mid m}
\left(1-e^{it\log\ell/(\delta L)}\right)\,dt.
$$

The product is over all distinct prime divisors of $m$, including those exceeding $X^\delta$.

Opening the positive harmonic sum into an Euler product bounds its integrand by

$$
\prod_{3\le\ell\le3X^{2\varepsilon}}
\left(
1+
\frac{\min(2,|t|\log\ell/(\delta L))}
{\ell-2}
\right).
$$

Split the primes at $\exp(\delta L/\max(1,|t|))$. The logarithm of this product is $O(1+\log(2+|t|))$, uniformly in sufficiently large $X$, since $2\varepsilon/\delta=8$.

The rapid decay of $\widehat f$ therefore bounds the first factor in (4) by a constant depending only on $f$.

This proves that the multiple-marker error is $O_f(\varepsilon J_X)+o(J_X)$, establishing (3).

Thus the known positive main term can be transferred to a statistic involving only the actual largest prime factor, with an arbitrarily small limiting error. The composite cofactors, however, still have to be controlled.

5. Testing the composite cancellation on actual shifted primes

The next question is whether the nonunit contributions in (2) or (3) can simply be bounded from above by their positive terms.

They cannot be treated that way. There is an explicit, substantial positive composite contribution.

Set $z=X^\delta$, and define the roughness indicator

$$
R_z(N)=\mathbf1_{P^-(N)>z},
$$

where $P^-(N)$ is the least prime divisor of $N$.

On this set, $A_\delta(N/q)=1$ for every prime marker $q$. Denote the restriction of $S_{h,\delta}$ to this set by $S^{\mathrm{rough}}_{h,\delta}$.

Choose a sieve level $D=X^\theta$ with

$$
\delta<h,\qquad h+\theta<\frac12,
\qquad s=\frac{\theta}{\delta}.
$$

The linear sieve has local density $1/(\ell-1)$ at odd primes and product

$$
V(z)=\prod_{2<\ell\le z}
\left(1-\frac1{\ell-1}\right)
\sim\frac{K_0e^{-\gamma}}{\delta L}.
$$

Write $f_{\rm lin},F_{\rm lin}$ for the lower and upper linear-sieve functions. Their explicit formulas include

$$
f_{\rm lin}(3)=\frac{2e^\gamma\log2}{3},
\qquad
F_{\rm lin}(3)=\frac{2e^\gamma}{3}.
$$

These are the classical functions stated, for example, in Matomäki and Zuniga-Alterman's Weighted sieves with switching, equations (2.4)–(2.5) and Lemma 2.5.

Cambridge Core

The lower sieve gives

$$
\sum_p R_z(p+2)
\ge J_XV(z)(f_{\rm lin}(s)+o(1)).
$$

Now subtract the logarithmic mass of prime divisors in $(z,X^h]$.

For each such prime divisor $q$, open the roughness sieve with divisors $d\le D$. Since $q>z$, these divisors are coprime to $q$. The progression modulus is $qd\le X^{h+\theta}$, so Bombieri–Vinogradov applies.

The upper sieve consequently gives

$$
\begin{aligned}
&\sum_p R_z(p+2)
\sum_{\substack{z<q\le X^h\\q\mid p+2}}\log q\\
&\quad\le J_XV(z)L(h-\delta)
       (F_{\rm lin}(s)+o(1)).
\end{aligned}
$$

Here and below, prime-divisor markers $q$ are genuine primes. The factor $h-\delta$ follows from

$$
\sum_{z<q\le X^h}\frac{\log q}{q-1}
=(h-\delta)L+O(1).
$$

Repeated prime factors on the rough set cost $o(J_X)$, since their bases exceed $X^\delta$ and the number of affected integers is $O(X^{1-\delta}+\sqrt X)$.

Subtracting the low logarithmic mass from the complete logarithm yields

$$
\boxed{
\liminf_{X\to\infty}
\frac{S^{\mathrm{rough}}_{h,\delta}(X)}{K_0J_X}
\ge
\frac{e^{-\gamma}}{\delta}
\left[f_{\rm lin}(s)-(h-\delta)F_{\rm lin}(s)\right].
}
\tag{5}
$$

Explicit arithmetic test

Take

$$
h=0.49,\qquad \delta=0.002,\qquad\theta=0.006.
$$

All the modulus conditions hold, since $h+\theta=0.496$, and $s=3$.

The right side of (5) becomes

$$
\frac{2}{0.006}
(\log2-0.488)
=68.38239\ldots.
$$

For comparison, the upper linear sieve at level $X^{0.49}$, sifting through $X^{0.2}$, gives

$$
\limsup_{X\to\infty}
\frac{T_X}{K_0J_X}
\le\frac{2}{0.49}
=4.08163\ldots.
$$

Therefore the contribution from actual composite $p+2$ on the rough set satisfies

$$
\boxed{
\liminf_{X\to\infty}
\frac{C^{\mathrm{rough}}_{h,\delta}(X)}
{K_0J_X}>64.
}
\tag{6}
$$

Yet the entire inclusive weighted sum has limiting normalized value one.

This establishes that large compensating negative contributions are genuinely present outside the rough set. They cannot be discarded.

The phenomenon also survives the restriction to the actual largest prime factor in Section 4. Taking $h=1/2-\varepsilon$, $\delta=\varepsilon/4$, and $\theta=3\delta$, the lower bound in (5) grows proportionally to $1/\varepsilon$, whereas the multiple-marker correction tends to zero.

6. Changing the weight: cancel the large composite mass by a difference

The preceding failure suggests using a signed difference of two prime-factor cutoffs.

Take fixed values

$$
h_1=\frac14,\qquad h_2=\frac{49}{100},
\qquad \theta=\frac1{200}.
$$

Let $\delta$ be sufficiently small and fixed before taking $X\to\infty$.

The same upper and lower sieve calculation gives a sharper two-sided formula:

$$
\frac{S^{\mathrm{rough}}_{h,\delta}(X)}{K_0J_X}
=
\frac{e^{-\gamma}}{\delta}(1-h+\delta)
+O_\theta(\delta)+o_{X\to\infty}(1).
\tag{7}
$$

The error is small on the required additive scale, not merely relative to the large $1/\delta$ main term.

To check this, the standard linear-sieve inequalities give $f_{\rm lin}\le1\le F_{\rm lin}$. Their differential equations imply, on setting

$$
G(s)=s(F_{\rm lin}(s)-f_{\rm lin}(s)),
$$

that

$$
G'(s)=-\frac{G(s-1)}{s-1}.
$$

Since $G$ is nonnegative and decreasing for $s>3$,

$$
G'(s)\le-\frac{G(s)}{s-1}
\qquad(s>4).
$$

Hence $F_{\rm lin}(s)-f_{\rm lin}(s)=O(s^{-2})$. Inserting $s=\theta/\delta$ into the preceding sieve estimates gives the $O_\theta(\delta)$ error in (7).

First cancellation

Choose

$$
c_\delta=\frac{1-h_2+\delta}{1-h_1+\delta},
$$

and consider

$$
\mathcal D_\delta
=S_{h_2,\delta}-c_\delta S_{h_1,\delta}.
$$

The large rough contribution cancels by (7):

$$
\mathcal D_\delta^{\mathrm{rough}}
=O_\theta(\delta K_0J_X)+o(J_X).
$$

But the full mean from (1) is

$$
\mathcal D_\delta
=(1-c_\delta)K_0J_X+o(J_X),
$$

where

$$
1-c_\delta\longrightarrow0.32.
$$

Thus almost all of the surviving positive main term is now carried by the nonrough integers. Every one of those integers $p+2$ is composite for sufficiently large $X$.

The difference cancels the large mass, but leaves its positive reserve on the wrong population.

Second cancellation: deliberately remove the nonrough mean

A better choice is

$$
c_\delta^*=
\frac{1-h_2+\delta-\delta e^\gamma}
     {1-h_1+\delta-\delta e^\gamma}.
$$

Define

$$
\mathcal D_\delta^*
=S_{h_2,\delta}-c_\delta^*S_{h_1,\delta}.
$$

This time the coefficient is chosen to satisfy

$$
1-h_2+\delta-c_\delta^*(1-h_1+\delta)
=\delta e^\gamma(1-c_\delta^*).
$$

Consequently,

$$
\boxed{
\mathcal D_\delta^{*,\mathrm{rough}}
=(1-c_\delta^*)K_0J_X
+O_\theta(\delta K_0J_X)+o(J_X).
}
\tag{8}
$$

The complete nonrough signed contribution is only $O_\theta(\delta J_X)+o(J_X)$.

This is a useful improvement: the small-factor part has been removed at a controlled additive cost, and the positive inclusive main term survives on the rough population.

On a twin prime, the coefficient is exactly $1-c_\delta^*$, which tends to $0.32$.

The next sufficient inequality is therefore an upper bound for the composite-only portion of (8), separated from $0.32K_0J_X$ by a fixed positive margin as $\delta\downarrow0$.

7. Challenging the repaired weight with an actual tagged-prime calculation

I tested whether this repaired difference has a favorable sign on the rough composite population.

Choose the additional prime-factor band

$$
a=0.001,\qquad b=0.002,
$$

and assume $0<\delta<a$. Define

$$
B(N)=\sum_{\substack{X^a<r\le X^b\\r\mid N,\ r\ \mathrm{prime}}}1.
$$

Every integer in this tagged population is composite. In particular, no twin-prime contribution enters this calculation.

We can evaluate the tagged version of (7), because the largest progression modulus now has exponent at most

$$
h_2+b+\theta=0.497<\frac12.
$$

Exact treatment of the shared prime

When a tagged prime $r$ is also a low logarithmic marker $q$, it must be counted separately. The modulus is $rd$, not $r^2d$.

For distinct $r,q$, the modulus is $rqd$, with all three factors coprime because $d$ contains only primes at most $z$.

The relevant prime sums are

$$
\sum_{X^a<r\le X^b}\frac1{r-1}
=\log(b/a)+o(1),
$$

$$
\sum_{X^a<r\le X^b}\frac{\log r}{r-1}
=(b-a)L+O(1).
$$

The second expression supplies the same-prime correction. When summing the distinct-prime progression errors, a modulus has at most two ordered representations of its two large prime factors. Thus the multiplicities cost only a bounded factor and a logarithm.

Applying the same sieve estimates to the tagged logarithmic sum gives

$$
\begin{aligned}
&\frac1{K_0J_X}
\sum_p R_z(p+2)B(p+2)
\sum_{\substack{q>X^h\\q\mid p+2}}\log q\\
&\quad=
\frac{e^{-\gamma}}{\delta}
\left[(1-h+\delta)\log(b/a)-(b-a)\right]\\
&\qquad+O_\theta(\delta)+o_{X\to\infty}(1).
\end{aligned}
\tag{9}
$$

The term $-(b-a)$ is essential. It records the logarithmic mass already assigned to the tagged small prime.

Apply the repaired difference

For a rough integer $N$, put

$$
W_\delta(N)=
\sum_{\substack{q>X^{h_2}\\q\mid N}}\log q
-c_\delta^*
\sum_{\substack{q>X^{h_1}\\q\mid N}}\log q.
$$

Subtract the two formulas (9), retaining the shared-prime correction. The result is

$$
\boxed{
\begin{aligned}
&\frac{\sum_p R_z(p+2)B(p+2)W_\delta(p+2)}
{K_0J_X}\\
&=(1-c_\delta^*)
\left[
\log2-\frac{0.001e^{-\gamma}}{\delta}
\right]
+O_\theta(\delta)+o_{X\to\infty}(1).
\end{aligned}
}
\tag{10}
$$

This is a negative quantity of order $1/\delta$ as $\delta\downarrow0$.

It is a statement about actual shifted primes, without an assumption of statistical independence between their prime factors.

Furthermore,

$$
B(N)\le\frac{\log N}{aL}\le\frac2a
$$

for large $X$. Thus (10) implies an unconditional lower bound of order $J_X/\delta$ for the negative variation of the repaired weight on rough composites.

Since its complete signed mean is only $O(J_X)$, and the twin contribution is also $O(J_X)$, its positive composite variation must likewise have order at least $J_X/\delta$.

Both signs survive on actual composite integers, at a scale much larger than the required twin-prime reserve.

This does not disprove a signed cancellation estimate. It proves that the repaired weight cannot be handled by simply retaining the positive terms, or by asserting that its large rough contributions cancel individually.

8. What happens with differences between dilated intervals?

The tagged calculation extends to any fixed finite linear combination of the preceding weights on intervals

$$
(\alpha_iX,\beta_iX].
$$

Use common factor cutoffs, or fixed dilations of those cutoffs, and bounded coefficients $u_i$.

Write

$$
U=\sum_i u_i(\beta_i-\alpha_i).
$$

The complete inclusive normalized mean is $U+o(1)$. The corresponding rough principal term is

$$
\frac{e^{-\gamma}}{\delta}
\sum_i u_i(\beta_i-\alpha_i)(1-h_i+\delta).
$$

If this is tuned to remain bounded while $U>0$, the tagged calculation introduces the additional term

$$
-\frac{e^{-\gamma}}{\delta}(b-a)U.
$$

It cannot be canceled merely by the same choice of dilated intervals.

Subject to the stated fixed modulus margins, the calculation therefore applies to interval differences as well as differences of prime-factor cutoffs. It does not exclude more general arithmetic-dependent weights.

There is also an exact cancellation available when the largest-factor threshold is genuinely linear in $X$.

Fix $0<c\le1$, and let $K$ be an integer exceeding $3/c$. Put

$$
M_K=\prod_{\substack{3\le r\le K\\r\ \mathrm{prime}}}r.
$$

If $q>cX$ divides $p+2$, its cofactor is bounded by $K$ for all sufficiently large $X$. Every odd nonunit cofactor then has a prime divisor in $M_K$.

Consequently,

$$
\boxed{
T_X=
\sum_{\substack{X<p\le2X,\ p\ \mathrm{prime}\\
(p+2,M_K)=1}}
\sum_{\substack{q>cX\\q\mid p+2,\ q\ \mathrm{prime}}}
\log q.
}
\tag{11}
$$

This eliminates every bounded odd nonunit cofactor exactly.

The difficulty with this last construction is not the cancellation: it is obtaining a positive lower bound for the remaining linear-size prime-factor sum. Prime distribution in fixed residue classes evaluates the complete logarithmic mass with the coprimality condition, but does not evaluate the part with $q>cX$. Subtracting the small prime factors by Bombieri–Vinogradov leaves an uncontrolled intermediate range.

9. Strongest surviving proof obligation

The strongest largest-factor estimate obtained here is (3). Define its composite remainder by

$$
C_\varepsilon^{\max}(X)
=
\sum_{\substack{X<p\le2X,\ p\ \mathrm{prime}\\
p+2\ \mathrm{composite}\\
q=P^+(p+2)>X^{1/2-\varepsilon}}}
(\log q)A_{\varepsilon/4}\left(\frac{p+2}{q}\right).
$$

Then

$$
T_X=K_0J_X-C_\varepsilon^{\max}(X)
+O_f(\varepsilon J_X)+o(J_X).
$$

A precise sufficient target is

$$
\boxed{
\liminf_{\varepsilon\downarrow0}
\liminf_{X\to\infty}
\frac{C_\varepsilon^{\max}(X)}{K_0J_X}<1.
}
\tag{12}
$$

The order of limits ensures that a sufficiently small fixed $\varepsilon$ can be selected first, after which a strict positive lower bound for $T_X$ holds on an unbounded sequence.

Alternatively, the repaired difference (8) reduces the question to a signed composite sum entirely on the rough population.

Neither strict inequality has been established. The largest-factor reduction, the controlled multiple-marker error, and the tagged composite calculation are unconditional partial results. The latter identifies why the natural difference constructions still require genuinely new signed arithmetic cancellation.

I chose these weights and cutoffs to permit rigorous progression estimates and then tested their composite contributions separately. I have not obtained an independent external verification or a complete proof of twin-prime infinitude. No private-material retrieval, file creation or external contact was used in this assignment.

---

### Recovered response 2

Second-reader verdict

The pseudoprime note is a substantially better candidate for a standalone publication than the cofactor-cutoff and signed-sieve work in this chat.

I verified the directly comparable published result:

Florian Luca, Dimbinaina Ralaivaosaona and Jorge Jiménez Urroz, On pseudoprime RSA moduli, Afrika Matematika 36, article 118 (2025), published 10 June 2025.

Their Theorem 3.1 establishes

$$
Q_2(X)\ll\frac{X^{4/5}}{(\log X)^{2/5}},
$$

for base-2 pseudoprimes that are products of two primes, without a balanced-factor restriction.

Springer Nature Link

Published paper — DOI 10.1007/s13370-025-01338-1

The proposed bound,

$$
Q_2(X)\ll\frac{X^{3/4}}{(\log X)^{5/4}},
$$

would improve this by a factor of

$$
X^{1/20}(\log X)^{17/20}.
$$

That is a genuine power-saving improvement, not merely a refinement of a logarithmic factor.

Priority against the wider literature and correctness of the two-sieve argument need to be assessed separately.

1. Prior literature and exact scope

The relevant counting function is

$$
Q_2(X)=\#\{n=rs\le X:
r,s\text{ odd primes},\
2^{n-1}\equiv1\pmod n\}.
$$

The important distinction is that neither prime is required to lie in a prescribed interval relative to the other.

Published result
 |
Bound or conclusion
 |
Comparison
 |

Szymiczek (1967), Theorem 1
 |
$Q_2(X)\gg\log X$
 |
Lower bound
 |

Pomerance (1981)
 |
$X^{1-o(1)}$ upper bound for all pseudoprimes
 |
Weaker upper bound
 |

Granville–Pomerance (2002), §8
 |
Galway's conjectured order $\sqrt X/\log^2 X$
 |
Conjectural
 |

Dieulefait–Jiménez Urroz (2010)
 |
$O(z^2/\log^3 z)$, factors in $(z,2z]$
 |
Restricted and weaker
 |

Luca–Ralaivaosaona–Jiménez Urroz (2025), Theorem 3.1
 |
$O(X^{4/5}/\log^{2/5}X)$
 |
Direct benchmark
 |

Li–Pomerance (2026)
 |
General pseudoprime upper bound uniform in the base
 |
Does not supersede the two-factor result
 |

Proposed note
 |
$O(X^{3/4}/\log^{5/4}X)$
 |
Improves the strongest directly comparable published bound found
 |

Primary sources checked

K. Szymiczek — On Pseudoprimes Which Are Products of Distinct Primes (1967).
American Mathematical Monthly, 74, 35–37. Theorem 1 establishes a logarithmic lower bound for pseudoprimes with exactly two distinct prime factors. This confirms that the counting problem has a substantial history, but does not establish a competing upper bound.

math.stonybrook.edu

Original article

Carl Pomerance — On the Distribution of Pseudoprimes (1981).
Mathematics of Computation, 37, 587–593. The result applies to all base-2 Fermat pseudoprimes:

$$
P_2(X)\le X\exp\left(
-\frac{\log X\log\log\log X}
{2\log\log X}\right).
$$

It also extends to arbitrary fixed bases. Its upper bound is asymptotically larger than either of the two-factor power-saving estimates.

math.dartmouth.edu

Author-hosted original paper

Andrew Granville and Carl Pomerance — Two Contradictory Conjectures Concerning Carmichael Numbers (2002).
Section 8 discusses Galway's conjecture specifically for two-prime base-2 pseudoprimes. It predicts

$$
Q_2(X)\sim C\frac{\sqrt X}{(\log X)^2},
$$

for an explicit positive constant $C$. This is a conjecture, not an established upper bound. It also demonstrates that the gcd parameterization underlying the proposed note has older antecedents.

math.dartmouth.edu+1

Original published paper

Shuguang Li and Carl Pomerance — Fermat Pseudoprimes (2026).
Acta Arithmetica, 222, 191–196, published online 29 December 2025. This important later result extends the general pseudoprime upper bound uniformly to bases $2\le a\le X$, without requiring coprimality to the base. It does not give a stronger two-factor power-saving estimate.

impan.pl+2

Published article · Author manuscript

Novák literature. I specifically investigated this lead. The directly accessible relevant primary paper was A. B. Kalmynin's On Novák numbers (2018). It studies integers satisfying $N\mid 2^N+1$, a different arithmetic population. Its results do not supersede the proposed theorem. I could not identify a separate Novák publication establishing a stronger bound for the exact requested counting function.

mathnet.ru

Published paper

I also checked later fixed-base pseudoprime literature, including the 2026 paper On the Asymptotic Density of Fermat Pseudoprimes to a Fixed Base. It provides an elementary sparsity argument, not a stronger competing two-factor estimate.

Literature conclusion: the 2025 Theorem 3.1 remains the strongest directly comparable published upper bound I located. This is a bounded priority assessment, not an exhaustive certification that no other result exists.

2. Independent mathematical check of the proposed improvement

I reconstructed the argument independently from the mechanism supplied in your assignment.

Small gcd: genuine improvement over the published proof

For distinct primes $r<s$, put

$$
m=\gcd(r-1,s-1).
$$

The pseudoprime condition implies

$$
r\mid2^m-1,\qquad s\mid2^m-1,
\qquad r,s\equiv1\pmod m.
$$

For each fixed $m$, let $t(m)$ count primes satisfying these conditions. Since their product divides $2^m-1$, and every such prime is at least $m+1$,

$$
(m+1)^{t(m)}\le2^m-1.
$$

Therefore

$$
t(m)\le\frac{m\log2}{\log(m+1)}.
$$

The contribution from $m\le Y$ is bounded by

$$
\sum_{m\le Y}t(m)^2
\ll\frac{Y^3}{(\log Y)^2}.
\tag{1}
$$

The published 2025 proof instead pools the primes of order at most $Y$ before counting pairs, obtaining $O(Y^4/\log^2Y)$.

Springer Nature Link

Retaining the common gcd throughout the counting is the first decisive improvement.

Large gcd: verification of the second Brun–Titchmarsh application

Write

$$
r=am+1,\qquad s=bm+1,\qquad a\le b.
$$

Necessarily,

$$
ab\le\frac X{m^2},
\qquad a\le\frac{\sqrt X}{m}.
$$

For $Y<m\le X^{2/5}$, the first application of Brun–Titchmarsh, counting possible $b$ for fixed $a,m$, gives

$$
\#\{b:\text{ admissible}\}
\ll\frac{X}{am\varphi(m)\log X}.
$$

The denominator has a uniform logarithmic margin because

$$
\frac{X}{am^2}\ge X^{1/10}.
$$

Now restrict $m$ to a dyadic block $M<m\le2M$. The resulting count is at most

$$
\frac{CX}{M^2\log X}
\sum_{a\le\sqrt X/M}\frac1a
\sum_{\substack{M<m\le2M\\am+1\ \mathrm{prime}}}
\frac m{\varphi(m)}.
\tag{2}
$$

The crucial uniform estimate is

$$
\boxed{
\sum_{\substack{M<m\le2M\\am+1\ \mathrm{prime}}}
\frac m{\varphi(m)}
\ll\frac a{\varphi(a)}\frac M{\log M}.
}
\tag{3}
$$

To verify it, expand

$$
\frac m{\varphi(m)}
=\sum_{d\mid m}\frac{\mu^2(d)}{\varphi(d)}.
$$

For $d\le\sqrt M$, apply Brun–Titchmarsh to the progression $1\bmod ad$. Use

$$
\varphi(ad)\ge\varphi(a)\varphi(d)
$$

and the convergent series $\sum_d1/\varphi(d)^2$.

For $d>\sqrt M$, simply count multiples of $d$. Their complete weighted contribution is

$$
\ll M\sum_{d>\sqrt M}\frac1{d\varphi(d)}
\ll\sqrt M.
$$

This proves (3), uniformly in $a$, including $a=1$.

Substituting into (2), and using

$$
\sum_{a\le A}\frac1{\varphi(a)}\ll\log(2A),
$$

gives, for the required polynomial-size $M$,

$$
\#\{\text{admissible pairs in the block}\}
\ll\frac{X}{M\log X}.
$$

Summing the dyadic blocks geometrically gives

$$
Q_2(X;Y<m\le X^{2/5})
\ll\frac X{Y\log X}.
\tag{4}
$$

The remaining range $m>X^{2/5}$ is bounded by elementary divisor counting:

$$
\ll X^{3/5}\log X.
$$

Thus it does not affect the desired final estimate.

Final optimization

Combining the complete ranges,

$$
Q_2(X)\ll
\frac{Y^3}{(\log Y)^2}
+\frac X{Y\log X}
+X^{3/5}\log X.
$$

The correct balancing choice is

$$
Y=X^{1/4}(\log X)^{1/4}.
$$

Both main terms then have order

$$
\boxed{
Q_2(X)\ll
\frac{X^{3/4}}{(\log X)^{5/4}}.
}
$$

Prime squares, if included in the definition, contribute at most $O(\sqrt X)$, which is negligible.

Mathematical verdict: the reconstructed argument is valid. I found no missing factor-size range or logarithmic loss in this reconstruction.

3. Mathematical significance and novelty

The contribution should be characterized precisely:

-

Not new: the common-gcd parameterization and its connection to multiplicative orders.

-

Genuine improvement: counting small-gcd pairs separately for each $m$, rather than pooling primes across all small orders.

-

Additional improvement: the weighted second Brun–Titchmarsh estimate, which supplies the stronger logarithmic saving.

The small-gcd improvement alone, combined with the 2025 paper's large-gcd estimate, would already give

$$
Q_2(X)\ll\frac{X^{3/4}}{(\log X)^{1/2}}.
$$

The second sieve improves that logarithmic denominator to exponent $5/4$.

There is also a straightforward extension to every fixed integer base $B\ge2$, for Fermat pseudoprimes coprime to $B$: replace $2^m-1$ by $B^m-1$. The implied constant can depend on $B$. Uniformity in a growing base is not established by this argument.

For balanced RSA moduli with both factors in $(z,2z]$, the proposed theorem also implies

$$
O_B\left(\frac{z^{3/2}}{(\log z)^{5/4}}\right),
$$

improving the power exponent in the 2025 paper's Theorem 2.1.

This is a meaningful, elementary improvement in a published number-theoretic counting problem. It is not a resolution of Galway's conjecture, a general primality-testing breakthrough, or a proof concerning twin primes.

4. Comparison with the twin-prime research

Assessment
 |
Pseudoprime note
 |
Cofactor-cutoff and signed-sieve research
 |

Complete unconditional target estimate
 |
Yes, in the reconstructed proof
 |
No
 |

Direct published benchmark improved
 |
Yes
 |
Not established
 |

Main mathematical contribution
 |
Power-saving counting bound
 |
Exact reductions and obstacles to signed cancellation
 |

Length and ease of verification
 |
Short and independently reconstructible
 |
More extensive
 |

Standalone publication potential
 |
Good candidate
 |
Lower at present
 |

My cofactor-cutoff calculations establish useful inclusive means and identify genuine positive and negative composite contributions. But the decisive composite upper bound remains missing. Those calculations do not prove twin-prime infinitude or an independently established improvement on the strongest published twin-prime results.

The pseudoprime note, by contrast, delivers its complete stated theorem.

5. Recommendation to the owner

Retain and prioritize the pseudoprime paper candidate.

Mathematical correctness

Positive reconstruction

Improvement over 2025 theorem

Confirmed

Absolute literature priority

Not certified

Standalone research value

Substantial enough for a short note

I recommend presenting it as an improved upper bound for semiprime Fermat pseudoprimes, explicitly crediting the 2025 theorem and the earlier gcd construction. I would not claim that it is the first result on the problem, or that absolute priority for the improved exponent has been established.

Review limitation: I could not retrieve the complete standalone proposed manuscript from the available project material. Consequently, my positive mathematical assessment applies to the independently reconstructed argument above, not to every line of the existing manuscript. The weighted estimate (3), the large-gcd endpoint and the prime-square convention should be checked against that actual text before submission.

No additional paper was drafted, no files were changed, and no external parties were contacted.

---

## Show research records

[Original conversation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6af40271-3984-8323-be2f-6636ab3bcca6)

### Recovered response 1

I tested the genuine positive rank-three branch against Friedlander–Iwaniec’s asymptotic sieve, Pascadi’s modern dispersion results, and a separate linear-sieve calculation on the actual shifted integers.

The results are saved in the same Twin Primes.md file. The persistent copy was updated and reopened.

Download updated Twin Primes.md · Open persistent working file

What the tests establish

1. Friedlander–Iwaniec does not directly close this branch. In a concrete rank-three factor box, the Möbius sign is constant. Its required bilinear cancellation therefore fails for the corresponding triple-supported sequence when that sequence has mass. I also proved positive mass for a shifted-prime rough relaxation, establishing that this particular obstruction is not merely an empty-support example. The relaxation does not preserve the exact factor-count condition on $M+2$.

Annals of Mathematics

2. The contemporary dispersion theorems have specific support mismatches. Pascadi’s triply well-factorable modulus weights cannot represent the natural $rs$ modulus in the tested box. Maynard’s two-factor modulus conditions fit, but his theorem concerns primes in progressions, not the additional coupled prime-factor and $G_2(M+2)$ conditions.

3. A different mechanism gives a rigorous bound on the actual coupled sum. A linear upper sieve, with Bombieri–Vinogradov controlling the progression errors, yields the following normalized upper bounds.

arxiv.org

Contribution
 |
Upper bound
 |

Fixed rank-three box, $r\in[X^{0.125},X^{0.1305}]$, $s\in[X^{0.200},X^{0.202}]$
 |
0.005998387
 |

Entire positive rank-three branch
 |
8.559861
 |

Required upper bound for the whole signed $R_X$
 |
0.21805
 |

The local bound is genuine, but it does not improve the complete bound. The negative rank-two contribution, the other rank-three boxes, and the positive portions of ranks four through seven must still be accounted for together. I have not treated the unshifted $0.6114186\ldots$ benchmark as evidence of a twin-prime saving.

The full twin-prime conjecture remains unproved. The file now preserves the exact source hypotheses, exponent checks, coefficient formulas, a finite reproducibility test, and the outstanding one-sided arithmetic estimate.

Twin Primes.mdDocumentOpen file

---

### Recovered response 2

I’ve completed the nine-page standalone manuscript, including theorem statements, complete proofs using stated classical sieve inputs, references, and editable author and email fields.

Editable LaTeX

Full source, including proofs and bibliography

Download manuscript.tex

Compiled PDF

Nine pages, rendered and checked

Download manuscript.pdf

Mathematical content

The manuscript establishes:

-

Exact rank-two and rank-three formulas: every squarefree two-prime product has negative long-divisor weight; the only positive three-prime case has two smaller primes individually below $D$, their product above $D$, and weight $\log p$.

-

Unshifted weighted asymptotic: $(0.6114186198092624\ldots+o(1))X$, with a complete prime-number-theorem derivation and dilogarithm evaluation.

-

Actual shifted upper bound: at the specified factor box, the normalized contribution retaining the exact $M+2$ factor gate is at most $0.005998386331\ldots$.

-

Positive shifted roughness result: a lower bound on a larger family where $M+2$ has no prime factor below $X^{1/21}$.

-

Asymptotic-sieve limitation: an explicit nonempty rough family for which the required Friedlander–Iwaniec bilinear cancellation fails.

The manuscript distinguishes the ordinary $X$-scale asymptotic from the coupled $X/\log X$-scale estimates. Its main classical inputs are the Opera de Cribro linear-sieve framework and the established prime-distribution theorems.

annals.math.princeton.edu+1

Scope: The paper does not prove the twin-prime conjecture. The signed contribution from the other factor ranks remains uncontrolled. I have not claimed novelty, independent external validation, or a publishable priority result.

The original research files remain unchanged. Nothing has been published or submitted.

twin_primes_long_divisor_manuscript.texFileOpen filetwin_primes_long_divisor_manuscript.pdfPDFOpen file

---

### Recovered response 3

Selection decision

My recommendation is §308CO: the near-critical fractional von Mangoldt moment on actual shifted primes. It is the strongest candidate from this research month for a potentially useful independent theorem.

I do not recommend public promotion yet. The result has a substantial internal proof, but its most delicate uniform estimates have not received an independent, line-by-line mathematical audit, and priority over existing literature is not established.

The November 19–20 signed three-prime result is more elementary and easier to verify, but considerably less likely to interest an outside number theorist.

1. The selected result: §308CO

Define

$$
Q_\alpha(m)=\sum_{d\mid m}\mu(d)
\left(\frac{\log(m/d)}{\log m}\right)^\alpha.
$$

At $\alpha=1$, this is $\Lambda(m)/\log m$, the prime-power detector.

Let $L=\log X$, $H=\log\log X$, and sum over actual primes $X<p\le2X$, excluding prime-power values of $p+2$. Section 308CO claims the unconditional limits

$$
\frac{L^2}{2C_2X}
\sum_p |Q_{1+c/H}(p+2)|
\longrightarrow 1-e^{-c},
$$

and

$$
\frac{L^2}{2C_2X}
\sum_p |Q_{1-c/H}(p+2)|
\longrightarrow e^c-1
\qquad(c>0\text{ fixed}).
$$

These are sharp transition constants for a real order moving toward one, not ordinary fixed-order moment estimates. The section also derives a subsequential signed Laplace law and positive-order approximants with composite absolute mass $(1-e^{-1})^k$.

The nearest published work I identified is Sieve Weights and Their Smoothings, by Granville, Koukoulopoulos and Maynard (2021), which establishes moments of smoothed Möbius divisor sums on integers. It does not state these moving-real-order limits on the genuine shifted-prime sequence.

dms.umontreal.ca+1
 Lichtman's published work on Möbius averages over shifted primes is also relevant, but concerns different quantifiers and statistics.

doi.org

Independent utility: a quantitative transition law for prime-detecting divisor weights, applicable to sieve design and shifted-prime factor statistics even if the twin-prime conjecture remains open.

Proof-completeness judgment: the finite-difference Mellin identity and sign rule are directly checkable. The crucial uniform positive mean of the moving multiplicative weight, the square-power deletion, and domination across the entire Mellin range require a fresh independent audit. I found no demonstrated contradiction, but that is not enough to certify the theorem.

2. Comparison across the other candidates

Candidate
 |
Closest published mathematics and genuinely different content
 |
Decision
 |

§308GN — Rough neighbors
 |
Classical shifted-prime large-factor sieves and Bombieri–Vinogradov. The record goes further by claiming simultaneous large prime factors on two rough neighbors of a genuine prime, with a narrow exponent above $1/2$.
 |
Interesting possible independent lemma, but a narrow range and considerable sieve bookkeeping. Second-tier candidate.
 |

§308DJ — Liouville signs of short differences
 |
Green–Tao, Linear equations in primes, Appendix D, and Tao–Teräväinen's quantitative correlation framework.

arxiv.org
 The claimed extension permits arbitrary sparse vertex weights and averaged differences $d\le R$, provided $R/(\log X)^j\to\infty$.
 |
Potentially independently useful, especially for sparse prime-supported sets. However, it does not cover fixed $d=1$, and the elaborate weighted Cauchy/majorant argument needs independent verification and a prior-art check.
 |

§§308CF–CG, 308CY–CZ — Divisor switching
 |
Friedlander–Iwaniec's Asymptotic sieve for primes, and later bilinear/dispersion estimates. The special determinant-two reductions and controlled regions are different applications.
 |
Mathematically substantial, but the surviving signed determinant is still the original prime-pair difficulty. Not a standalone breakthrough.
 |

§§308LR–LU — Two-sided physical bounds
 |
Classical weighted sieves, Maynard's distribution theorem and Pascadi's factorizable-modulus estimates. Gives the internally checked $3.04808378$ lower for twins plus weighted composites.
 |
A useful research checkpoint. It is not a twin-count theorem because the necessary upper on composites is missing.
 |

November 19–20 — Signed three-prime sector
 |
Möbius inversion, the prime number theorem, Mertens' formula and standard linear-sieve upper bounds. Exact sign classification and the $0.6114186198\ldots$ unshifted mass are correct in the checked scope.
 |
The cleanest self-contained manuscript material, but likely too elementary and too limited for a persuasive originality claim. The coupled bounds do not improve the global target.
 |

The distinction that matters is that §308CO offers a new type of asymptotic statement with explicit constants. The three-prime work mainly identifies where an existing convolution weight changes sign. The divisor-switching work gives sophisticated representations, but still needs the full unknown correlation.

3. Separate comparison: base-2 pseudoprimes

I verified the exact published benchmark. Theorem 3.1 of Luca, Ralaivaosaona and Jiménez Urroz, On pseudoprime RSA moduli, Afrika Matematika 36, article 118 (2025), proves

$$
\#\{n\le X:n=pq,\ n\text{ base-2 pseudoprime}\}
\ll \frac{X^{4/5}}{(\log X)^{2/5}}.
$$

Springer Nature Link

The separately reported improvement

$$
O\!\left(\frac{X^{3/4}}{(\log X)^{5/4}}\right)
$$

would be strictly stronger, by a factor

$$
X^{1/20}(\log X)^{17/20}
$$

in the comparison of the old bound with the new one.

If it has a complete correct proof, it could be more immediately publishable than §308CO. It concerns an independently defined counting problem and improves an identified published exponent.

However, that derivation belongs to another chat. I could verify the 2025 published theorem but did not obtain or inspect a complete proof of the claimed improvement. It must therefore remain an unverified candidate, not a certified result or an accomplishment of this older twin-prime research.

4. What I actually consulted

I reopened the complete consolidated twin-prime-research-state.txt archive (version 93, approximately 11.2 MB), searched its section index and inspected the mathematical arguments in §§308CO–CR, 308GN, 308DJ, 308CF–CG, 308CY–CZ and the later signed-rank reductions §§308LQ–LU.

I also reviewed the current Twin Primes.md handoff and the opening theorem statements of the November 25 standalone long-divisor LaTeX manuscript. For older history, I used the archive's mathematical map and selected dependencies; I did not re-audit every proof in the entire month-long notebook.

For external comparison, I inspected the published Granville–Koukoulopoulos–Maynard and Luca–Ralaivaosaona–Jiménez Urroz records, plus the relevant Friedlander–Iwaniec and Tao–Teräväinen source statements. This was a focused comparison, not an exhaustive novelty search.

Final recommendation

Preserve §308CO as the one priority for independent specialist review. Require verification of its full moving-parameter uniformity and an exact literature comparison before calling it a new theorem suitable for public release.

Do not promote the November signed three-prime manuscript as the month's principal discovery, and do not claim the twin-prime conjecture has been solved.

The project provenance should remain explicit: DEEPAK KUMAR, project coordinator, admin@cosmosgeek.org. Mathematical derivations and drafting were substantially AI-generated; coordination does not establish personal authorship of those proofs. No contact or submission has been made.

---

## Confirm Research Rules

[Original conversation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6b05db68-6484-83ec-8ff0-d7524eba45ba)

### Recovered response 1

Goal confirmed: Develop an unconditional, rigorous proof that infinitely many ordinary primes $p$ satisfy $p+2$ prime.

I will follow these working rules:

-

Briefly map the mathematical territory and select one distinct research lane with the greatest direct potential.

-

Pursue substantive proof attempts, challenge each critical inference, and change approaches when necessary.

-

Distinguish proved results, conditional deductions, conjectures and failed arguments.

-

Use only public primary sources, minimizing tools and scratch work.

-

Do not access local or project files, download or install anything, or send external messages.

-

If workers are available, provide the rules and obtain their confirmation before assigning research.

-

Maintain one coherent mathematical output here, avoiding routine interruptions and unsupported completion claims.

Ready for the research assignment.

---

### Recovered response 2

1. The primitive-norm reduction is valid

The proposed route uses a genuine advantage of the half-dimensional sieve: one entire family of prime divisors can be excluded at a lower sieve cost than excluding all prime divisors simultaneously. The question is whether that advantage survives the second sieve.

Put

$$
n=p-2,\qquad \chi(q)=\left(\frac{-8}{q}\right),
$$

and divide the odd primes into

$$
\mathcal P_+=\{q:q\equiv1,3\pmod8\},
\qquad
\mathcal P_-=\{q:q\equiv5,7\pmod8\}.
$$

These are respectively the split and inert primes in $\mathbb Q(\sqrt{-2})$.

Exact elementary result. An odd positive integer $n$ has a primitive representation

$$
n=x^2+2y^2,\qquad \gcd(x,y)=1,
$$

if and only if every prime divisor of $n$ belongs to $\mathcal P_+$.

For necessity, an inert prime dividing $x^2+2y^2$ must divide both $x$ and $y$. For sufficiency, the ring $\mathbb Z[\sqrt{-2}]$ is norm-Euclidean: rounding the two rational coordinates gives a norm error at most $1/4+2/4<1$. It is therefore a unique factorization domain. For each split prime power dividing $n$, choose only one of the two conjugate prime elements. Their product has norm $n$, and no rational prime divides both its coordinates.

This gives an exact characterization of the distinct integer norms, not just a count of their representations.

Fuchs, Hsu, Rickards, Schindler and Stange's arXiv:2504.20289, Theorem 1.1, applies with $A=2$, $B=1$, $D=-8$. In particular,

$$
\#\{p\le X:p\text{ prime},\
p-2=x^2+2y^2\text{ primitively}\}
\asymp \frac{X}{(\log X)^{3/2}}.
$$

Their theorem uses a characteristic function of representability, so repeated representations are not counted as different integers. The paper was subsequently published in Acta Arithmetica 222 (2026), pp. 371–391.

math.ucdavis.edu+1

This is a rigorous starting population. It is not yet a population of twin primes.

2. Why switching works for the inert primes

Begin with the distinct-integer sequence

$$
\mathcal A_X=
\{X/2<n\le X:n+2\text{ prime},\ \chi(n)=1\}.
$$

For an odd squarefree integer $n$,

$$
\chi(n)=(-1)^{\omega_-(n)},
$$

where $\omega_-(n)$ counts its inert prime divisors. Thus every element of the squarefree part of $\mathcal A_X$ has an even number of inert prime factors.

Choose $z_-=X^\alpha$, with $1/3<\alpha<1/2$, and exclude inert primes below $z_-$. Any surviving integer which is not a primitive norm necessarily has the form

$$
n=q_1q_2m,
$$

where $q_1<q_2$ are inert primes exceeding $z_-$, and

$$
m\le X^{1-2\alpha}
$$

has only split prime factors. The factorization is unique. The unit $m=1$ must be included.

This is exactly the structural advantage behind Iwaniec's switching: the unwanted prime divisors occur in pairs, leaving a comparatively short complementary factor.

Fuchs et al., §§3.4–3.5, use a distribution level essentially $X^{1/2}/(\log X)^U$, followed by subtraction of the surviving large inert-prime pairs. Their argument chooses the half-dimensional sieve parameter sufficiently close to its lower-bound threshold $s=1$.

math.ucdavis.edu+2

There is no corresponding requirement that the number of split prime factors be even or odd. That difference becomes decisive in the second sieve.

3. The two sieve levels cannot be allocated independently

For an odd squarefree modulus $d$, let $\mathcal A_{X,d}$ denote the elements of $\mathcal A_X$ divisible by $d$. Put

$$
J=\int_{X/2+2}^{X+2}\frac{dt}{\log t}.
$$

The prime progression main term is

$$
|\mathcal A_{X,d}|=\frac{J}{2\varphi(d)}+r_d.
$$

Indeed, the restriction $\chi(n)=1$ corresponds to $p\equiv3,5\pmod8$, and $d\mid n$ corresponds to $p\equiv2\pmod d$. Both resulting CRT classes are reduced.

Bombieri–Vinogradov controls the summed remainders for moduli below $X^{1/2}/(\log X)^B$. Each of the two prime families separately gives sieve dimension $1/2$.

Suppose we use inert and split cutoffs

$$
z_-=X^\alpha,\qquad z_+=X^\beta
$$

and sieve levels

$$
D_-=X^u,\qquad D_+=X^v.
$$

The two sets of sieve divisors are coprime, but opening their weights produces the modulus $d_-d_+$. Consequently the available level requires

$$
u+v<\frac12
\tag{1}
$$

with fixed positive slack.

This is not two independent applications of Bombieri–Vinogradov, each with level $1/2$.

The correct vector-sieve lower coefficient is

$$
\begin{aligned}
\mathcal L(s_-,s_+)
={}&f_{1/2}(s_-)F_{1/2}(s_+)\\
&+F_{1/2}(s_-)f_{1/2}(s_+)\\
&-F_{1/2}(s_-)F_{1/2}(s_+),
\end{aligned}
\tag{2}
$$

where $s_-=u/\alpha$, $s_+=v/\beta$.

This follows from the pointwise vector-sieve inequality, and does not require assuming statistical independence of the two sieved populations. Nath and Xie's primary paper arXiv:2501.16723, Lemma 3.6 and Proposition 3.10, provides the relevant beta-sieve framework.

arxiv.org+1

The half-dimensional lower function vanishes for $s\le1$. For $1<s\le2$, Iwaniec's formulas give

$$
\frac{f_{1/2}(s)}{F_{1/2}(s)}
=\operatorname{arsinh}\sqrt{s-1}.
$$

matwbn.icm.edu.pl

Therefore a positive coefficient in (2) requires both $u>\alpha$ and $v>\beta$, together with a stronger combined inequality.

Sieve requirement
 |
Exponent requirement
 |

Available combined BV level
 |
$u+v<1/2$
 |

Positive inert lower sieve
 |
$u>\alpha$
 |

Positive split lower sieve
 |
$v>\beta$
 |

Remove split composites directly
 |
$\beta\ge1/2$
 |

Leave at most two inert factors
 |
$\alpha>1/4$
 |

The direct scheme would require a combined distribution exponent exceeding $3/4$ merely to enter the positive range of both lower sieve functions. Even that is not sufficient for positivity of (2).

There is a stronger numerical obstruction for the choice $\alpha\ge1/3,\ \beta=1/2$. Even if one hypothetically had distribution up to exponent $1$, the vector lower coefficient could not become positive. In that range $s_-,s_+\le2$, and positivity would require

$$
\begin{aligned}
1
&<\operatorname{arsinh}\sqrt{u/\alpha-1}
+\operatorname{arsinh}\sqrt{v/\beta-1}\\
&\le \sqrt{(u+v-\alpha-\beta)
(1/\alpha+1/\beta)}\\
&\le\sqrt{5/6}<1,
\end{aligned}
$$

a contradiction.

This disproves the straightforward two-half-dimensional lower-sieve strategy at these cutoffs. It does not disprove a different switching argument or a new parity-sensitive distribution theorem.

4. A genuine arithmetic result: the second sieve can remove polynomially small split primes

Rather than abandon the switching idea at the failed level calculation, I tested whether the two sieves can be combined at a smaller split cutoff. This gives a rigorous result on actual primes, including an unavoidable composite contribution.

Proposition. There exists a fixed $\beta>0$ such that, for every sufficiently large $X$, there are

$$
\gg_\beta \frac{X}{(\log X)^2}
$$

distinct squarefree composite integers $n\in(X/2,X]$ satisfying all of the following:

-

$n+2$ is prime.

-

Every prime divisor of $n$ is split in $\mathbb Q(\sqrt{-2})$.

-

Every prime divisor of $n$ exceeds $X^\beta$.

-

Exactly one prime divisor $r$ lies in $(X^\beta,X^{2\beta}]$; every other prime divisor exceeds $X^{3\beta}$.

Thus these are genuinely primitive norms, with bounded factor count, at the scale of the desired twin-prime lower bound. They are nevertheless composite.

Proof

Write $L=\log X$. Choose a sufficiently small fixed $\delta>0$, and set

$$
\alpha=\frac{1-\delta}{2},\qquad
u=\frac12-\frac{\delta}{4},\qquad
v=\frac{\delta}{8}.
$$

Choose $\beta>0$ sufficiently small afterwards.

Tag a genuine split prime $r\in(X^\beta,X^{2\beta}]$, and write $n=rm$. Apply the inert sieve through $X^\alpha$ and the split sieve through $X^{3\beta}$ to $m$, at levels $X^u,X^v$, respectively.

The opened moduli are $8rd_-d_+$. They have exponent at most

$$
2\beta+u+v=\frac12-\frac{\delta}{8}+2\beta.
$$

Taking $\beta<\delta/32$ leaves strict Bombieri–Vinogradov room, even after tagging $r$.

For fixed $r$, the progression main term is

$$
\frac{J}{2\varphi(r)}g_r(d),
\qquad
g_r(d)=\frac{\varphi(r)}{\varphi(rd)}.
$$

For squarefree $d$, the local value is $1/(\ell-1)$ except at $\ell=r$, where it is $1/r$. This retains shared factors correctly.

For a given opened modulus and $r$, the split/inert decomposition is unique. The possible tags $r$ cost at most a divisor multiplicity, absorbed by the logarithmic precision of Bombieri–Vinogradov.

First estimate: a positive mixed-sieve lower bound.

Here

$$
s_-=\frac{u}{\alpha}
=1+\frac{\delta}{2(1-\delta)}.
$$

The explicit half-dimensional lower function gives

$$
f_{1/2}(s_-)\asymp\sqrt{\delta}.
$$

Meanwhile $s_+=v/(3\beta)$ can be made arbitrarily large by decreasing $\beta$ after fixing $\delta$. Both $F_{1/2}(s_+)$ and $f_{1/2}(s_+)$ tend to one.

Thus we may choose $\beta$ so that the coefficient in (2) is at least

$$
\frac12f_{1/2}(s_-)\gg\sqrt{\delta}.
$$

Mertens' theorem in the two prime families gives

$$
V_-(X^\alpha)V_+(X^{3\beta})
\asymp\frac{1}{L\sqrt{\alpha\,3\beta}}.
$$

Since

$$
\sum_{\substack{X^\beta<r\le X^{2\beta}\\r\in\mathcal P_+}}
\frac1{\varphi(r)}
\longrightarrow \frac12\log2,
$$

the total doubly sifted, tagged population is at least

$$
c\sqrt{\frac{\delta}{\beta}}\frac{X}{L^2}
\tag{3}
$$

for an absolute positive $c$, once $X$ is sufficiently large for the fixed parameters.

The tag $r$ is unique: every other surviving split prime exceeds $X^{3\beta}$, while every surviving inert prime exceeds $X^\alpha$. Removing nonsquarefree integers costs only $O(X^{1-\beta})$, which is negligible.

Second estimate: remove the remaining inert pairs.

Any retained nonnorm must now have the unique factorization

$$
n=rq_1q_2h,
$$

where $q_1<q_2$ are inert primes greater than $X^\alpha$, and $h$ is a product of split primes exceeding $X^{3\beta}$. In particular,

$$
h\le\frac{X^\delta}{r}.
$$

Fix $r,q_1,h$. The remaining conditions include simultaneous primality of

$$
q_2,\qquad rhq_1q_2+2.
$$

The standard two-linear-form upper sieve, on the variable $q_2$, gives

$$
\ll \frac{X}{rhq_1L^2}.
$$

The bound is uniform here: the variable has available length at least $X^\alpha$ on every nonempty row, and the additional singular factors from primes dividing $rhq_1$ are $1+o(1)$, uniformly for fixed $\beta$, because all such primes exceed $X^\beta$.

Summing these bounds gives

$$
\begin{aligned}
E_-
&\ll \frac{X}{L^2}
\sum_r\frac1r
\sum_{\substack{X^\alpha<q_1\le\sqrt X\\q_1\in\mathcal P_-}}\frac1{q_1}
\sum_{\substack{h\le X^\delta\\
q\mid h\Rightarrow q\in\mathcal P_+,\ q>X^{3\beta}}}
\frac1h.
\end{aligned}
$$

The three harmonic factors satisfy, respectively,

$$
O(1),\qquad O(\delta),\qquad
O\!\left(\sqrt{\frac{\delta}{\beta}}\right).
$$

The last bound follows by enlarging the sum to the corresponding positive Euler product. It includes $h=1$.

Consequently,

$$
E_-\le C\frac{\delta^{3/2}}{\sqrt\beta}
\frac{X}{L^2}
\tag{4}
$$

with absolute $C$, in the stipulated order of parameter choices.

Subtracting (4) from (3) leaves at least

$$
(c-C\delta)\sqrt{\frac{\delta}{\beta}}
\frac{X}{L^2}.
$$

Choose $\delta$ sufficiently small and then fix $\beta$ as above. This is positive. All remaining integers are primitive norms, and they are composite because $r\le X^{2\beta}<n$. This proves the proposition.

What this establishes

The inert switching genuinely survives the addition of a second, polynomial-scale split sieve. Its debit is smaller than the positive lower bound by a factor $O(\delta)$.

However, the resulting rough primitive-norm population has an actual composite part of order at least $X/L^2$. This is not hypothetical contamination or a representation-counting artifact. It is an arithmetic population on the precise shift $n+2$.

The next operation therefore has to distinguish these composites from primes at their full main scale.

5. Representation multiplicity cannot be used as a substitute for the integer count

There is an additional obstruction which can be proved using the preceding argument.

For an odd primitive norm $n>1$, the number of primitive ordered signed representations is exactly

$$
r_{\mathrm{prim}}(n)=2^{\omega(n)+1}.
$$

Each distinct split prime gives two conjugate choices in the unique factorization, and the ring has two units. Therefore a prime has four representations, a squarefree semiprime has eight, and a squarefree product of three primes has sixteen.

A natural attempt would be to detect primes using a polynomial in the representation count.

Set

$$
R(n)=\frac{r_{\mathrm{prim}}(n)}2,
\qquad
W(n)=\frac{4R(n)-R(n)^2}{4}.
$$

On primitive squarefree norms, $W$ equals one on primes, zero on semiprimes, and is at most $-8$ on integers with three or more prime factors. It is consequently a valid pointwise prime minorant.

But its mean is negative for sufficiently small fixed roughness cutoff.

To prove this, modify the preceding proposition by tagging two genuine split primes:

$$
X^\beta<r_1\le X^{2\beta},
\qquad
X^{2\beta}<r_2\le X^{3\beta},
$$

and sift their residual factor through $X^{4\beta}$ in the split family.

The total opened modulus now has exponent at most

$$
5\beta+u+v.
$$

For sufficiently small $\beta$, this still lies below $1/2$ with fixed slack. The two tag harmonic sums tend to positive constants. The same mixed-sieve calculation and inert-pair subtraction give at least

$$
c'\sqrt{\frac{\delta}{\beta}}\frac{X}{L^2}
$$

distinct genuine shifted-prime primitive norms with at least three prime factors. Here $\delta$ is fixed first, and $c'>0$ can be chosen independently of sufficiently small $\beta$.

The ordinary upper-bound sieve gives an absolute upper $C_0X/L^2$ for the number of twin primes. Hence

$$
\sum_{\substack{n\in\mathcal A_X\\
n\text{ squarefree primitive norm}\\
P^-(n)>X^\beta}}W(n)
\le
\left(C_0-8c'\sqrt{\frac{\delta}{\beta}}\right)
\frac{X}{L^2}
<0
$$

for sufficiently small fixed $\beta$ and all sufficiently large $X$.

The same construction works with any fixed number of disjoint small-prime tags. Consequently, any fixed polynomial in $R$ that is one at $R=2$ and nonpositive at every composite value $R=2^j,\ j\ge2$, has negative mean when the roughness exponent is sufficiently small: its leading coefficient must be negative, and sufficiently high ranks occur in the actual source in the required quantity.

This rules out a concrete class of representation-moment shortcuts. It does not rule out a parameter-dependent prime detector together with genuinely new estimates for its mean.

6. Switching the split-prime factors: a matching-order upper bound

Define the squarefree rough primitive-norm count $S_\beta(X)$, and decompose it exactly as

$$
S_\beta(X)=T_+(X)+C_\beta(X),
$$

where $T_+(X)$ counts genuine twin pairs whose smaller prime belongs to $\mathcal P_+$, and $C_\beta(X)$ counts the composite norms.

Using the least split prime factor gives the exact Buchstab decomposition

$$
C_\beta(X)=
\sum_{\substack{X^\beta<q\le\sqrt X\\q\in\mathcal P_+}}
\ \sum_{\substack{X/2<qm\le X\\
m>1,\ P^-(m)>q\\
m\text{ squarefree primitive norm}}}
\mathbf1_{\{qm+2\text{ prime}\}}.
\tag{5}
$$

There is no multiplicity in this identity.

One can obtain a substantially sharper upper bound than simply discarding all restrictions on the complementary factor $m$.

Fix $q$, put $Y=X/q$, and take $z=Y^{1/K}$, where $K$ is a sufficiently large absolute constant. Upper-sieve the variable $m$ simultaneously for:

-

primality of $qm+2$;

-

absence of inert divisors through $z$;

-

absence of split divisors through $\min(q,z)$.

At an odd prime $\ell\ne q$, there is one forbidden root for $qm+2$, with one additional, distinct forbidden root whenever the corresponding norm or roughness restriction applies. The exceptional prime $q$ costs only a bounded local factor.

The sieve dimension is at most two, and the residue-class counting remainder at level $Y^{1/2}$ is $O(Y^{1/2}\log Y)$. The upper-bound sieve and Mertens products therefore give the uniform row estimate

$$
\ll
\frac{X}{qL^{3/2}\sqrt{\log q}}.
$$

Summing over genuine split primes, using

$$
\sum_{q>X^\beta}\frac1{q\sqrt{\log q}}
\ll\frac1{\sqrt{\beta L}},
$$

proves

$$
C_\beta(X)\ll
\frac{X}{\sqrt\beta L^2}.
\tag{6}
$$

Together with the actual lower bound of §4, this gives the following two-sided order estimate.

Established in this calculation

$$
C_\beta(X)\asymp
\frac{X}{\sqrt\beta(\log X)^2}.
$$

Uniform implied constants for sufficiently small fixed $\beta>0$, with the limit $X\to\infty$ taken first.

In particular,

$$
\limsup_{X\to\infty}\frac{T_+(X)}{S_\beta(X)}
=O(\sqrt\beta).
$$

So the leading mass of this two-stage sieve, as the split cutoff exponent tends to zero, is genuinely carried by composites.

A portion of the large-factor remainder can be eliminated

If the least split prime satisfies $q>X^a$ for fixed $a>1/3$, every remaining squarefree composite in (5) is a semiprime. The complementary factor $m$ must itself be prime.

The two-linear-form upper sieve then gives

$$
C_a(X)\ll
\log\frac1{2a}\,\frac{X}{L^2},
$$

in the limiting upper-bound sense. More sharply, for any fixed $B>0$, the entire balanced collar

$$
\frac{\sqrt X}{L^B}<q\le\sqrt X
$$

has count

$$
O_B\!\left(\frac{X\log L}{L^3}\right)
=o(X/L^2).
$$

This is a legitimate use of complementary-factor switching: the near-square semiprime sector is negligible at the twin-prime scale. But the unbalanced sector and the products of three or more split primes remain.

7. The exact large-split-modulus remainder

The preceding switch concerns actual prime factors $q$. Switching composite sieve moduli is a different operation, and it is important not to confuse the two.

Let $b(n)$ indicate odd primitive norms, and let $\mathcal N_X$ denote the squarefree primitive norms in $\mathcal A_X$.

Write

$$
P_+(z)=\prod_{\substack{q\le z\\q\in\mathcal P_+}}q.
$$

Complete inclusion-exclusion gives

$$
T_+(X)=
\sum_{n\in\mathcal N_X}
\sum_{\substack{d\mid n\\d\mid P_+(\sqrt X)}}\mu(d).
$$

Split the inner sum at $D=X^\theta$. The large-divisor part, after switching to $m=n/d$, is exactly

$$
\boxed{
E_{>D}=
\sum_{\substack{m\le X/D\\b(m)=1\\\mu^2(m)=1}}
\ \sum_{\substack{d>D,\ d\mid P_+(\sqrt X)\\
(d,m)=1,\ X/2<dm\le X}}
\mu(d)\mathbf1_{\{dm+2\text{ prime}\}}.
}
\tag{7}
$$

All the factors in this expression are retained, including the unit $m=1$.

The difficulty is now explicit: switching shortens the complementary factor but does not remove the Möbius sign on the large split divisor.

Both $d$ and $m$ have quadratic character $+1$. This supplies no information about whether $\mu(d)$ is positive or negative.

There is also a second level obstruction. For a complementary factor $m\asymp X^\gamma$, the free norm variable $d$ has scale $Y\asymp X/m$. An additional divisor modulus $e$ produces the actual prime progression modulus $me$.

Ordinary Bombieri–Vinogradov therefore allows, at best in the averaged calculation,

$$
D_{\mathrm{new}}\le\frac{X^{1/2-\varepsilon}}m.
$$

Relative to the cutoff needed for primality of $d$,

$$
\frac{D_{\mathrm{new}}}{\sqrt Y}
\ll\frac{X^{-\varepsilon}}{\sqrt m}.
$$

This is below the positive half-dimensional lower-sieve threshold for sifting through $\sqrt Y$, even if membership of $d$ in the primitive-norm semigroup were supplied for free.

Nor can one substitute Fuchs et al. with $B=m$: the uniform sieve application in their Proposition 3.7 has a polylogarithmic parameter restriction, whereas $m$ in (7) can have polynomial size. Their result also does not estimate the signed, smooth-divisor sum in (7).

math.ucdavis.edu

Thus the remaining problem is a signed arithmetic estimate on (7), not another application of the established primitive-norm counting theorem.

8. A rigorous parity countermodel for the proposed sieve information

There is a stronger way to test whether improved divisor distribution alone could rescue the method.

Proposition. There exists an explicit nonnegative reference sequence which satisfies the split-residue restriction and the expected divisor main terms, with arbitrarily strong logarithmic accuracy up to every fixed distribution exponent less than one, yet assigns zero weight to every prime.

This is an information counterexample, not a counterexample to the twin-prime conjecture.

Construction

Let $\lambda(n)=(-1)^{\Omega(n)}$ be the Liouville function. Define

$$
w(n)=\prod_{\substack{q\mid n\\q>2}}
\frac{q-1}{q-2},
\qquad
H=\prod_{q>2}\left(1+\frac1{q(q-2)}\right).
$$

On $X/2<n\le X$, put

$$
a_X(n)=
\frac{2w(n)}{H\log(n+2)}
\mathbf1_{\{\chi(n)=1\}}(1+\lambda(n)).
$$

This weight is nonnegative. For every prime $n$, it vanishes because $\lambda(n)=-1$.

Nevertheless, for every fixed $\varepsilon,A>0$, uniformly over odd $d\le X^{1-\varepsilon}$,

$$
\boxed{
\sum_{d\mid n}a_X(n)
=
\frac{J}{2\varphi(d)}
+O_{\varepsilon,A}\left(\frac{X}{dL^A}\right).
}
\tag{8}
$$

These are precisely the unsieved divisor main terms from §3.

Proof of the distribution claim

Write $w=1*h$, where $h$ is multiplicative, supported on odd squarefree integers, and

$$
h(q)=\frac1{q-2}.
$$

The series $\sum h(r)/\sqrt r$ converges.

For $n=dm$,

$$
w(dm)=w(d)
\sum_{\substack{r\mid m\\(r,d)=1}}h(r).
$$

Put

$$
H_d=\prod_{q\nmid2d}
\left(1+\frac1{q(q-2)}\right).
$$

Expanding the divisor sum and counting odd multiples gives, uniformly in $d$,

$$
\sum_{\substack{m\le Y\\m\text{ odd}}}
\frac{w(dm)}{w(d)}
=
\frac{YH_d}{2}+O(\sqrt Y).
$$

The same sum twisted by any of $\chi(m)$, $\lambda(m)$, or $\chi(m)\lambda(m)$ is

$$
O_A(Y/\log^A Y).
$$

For the character alone this follows from its bounded partial sums. For the Liouville twists, use the classical fixed-character Möbius estimates and

$$
\lambda(n)=\sum_{k^2\mid n}\mu(n/k^2),
$$

then expand the absolutely convergent $h$-convolution. Splitting the convolution at $\sqrt Y$ makes the estimates uniform in the excluded factors of $d$.

Expand

$$
\mathbf1_{\{\chi(dm)=1\}}(1+\lambda(dm))
$$

on odd $m$. All three twisted terms have negligible means. Partial summation incorporates the factor $1/\log(dm+2)$.

Finally, the exact local identity

$$
\frac{w(d)H_d}{dH}=\frac1{\varphi(d)}
$$

gives (8).

The squarefree restriction also survives

For odd squarefree $d\le X^{1-\varepsilon}$, squarefree inversion applied to (8) yields

$$
\sum_{d\mid n}\mu^2(n)a_X(n)
=
\frac{J}{2d}
\prod_{\substack{q>2\\q\nmid d}}
\left(1-\frac1{q(q-1)}\right)
+O_{\varepsilon,A}\left(\frac{X}{dL^A}\right).
\tag{9}
$$

For completeness, truncate the square-divisor variable at $K=X^{\varepsilon/4}$. The opened modulus $[d,k^2]$ remains below $X^{1-\varepsilon/2}$.

For squarefree $k$, write $k=ab$, where $a\mid d$ and $(b,d)=1$. Then

$$
[d,k^2]=dab^2.
$$

The discarded reciprocal tail is bounded by

$$
\sum_{\substack{a\mid d,\ b\ge1\\ab>K}}
\frac1{ab^2}
\le
K^{-1/2}\prod_{q\mid d}(1+q^{-1/2})
\sum_{b\ge1}b^{-3/2}
=X^{-\varepsilon/8+o(1)}.
$$

This justifies the truncation, with enough room for arbitrary logarithmic precision. The Euler factors of the remaining complete squarefree main term give (9).

The model therefore retains the squarefree divisor main terms as well as the even-inert-factor restriction. Its squarefree primitive norms have positive mass of order $X/L^{3/2}$: applying the half-dimensional lower sieve and the inert-pair switching calculation gives this, with the switched prime-variable count replaced by ordinary prime counting and the model's $1/L$ weight.

But every primitive norm receiving positive weight has even split-factor parity. No prime receives any weight.

The model does not impose actual primality of $n+2$. That is exactly the distinction which a successful new arithmetic estimate must exploit.

Research verdict

The investigation establishes considerably more than the observation that there is a parity barrier.

Proposed operation
 |
Result
 |

Distinct primitive-norm counting
 |
Valid
 |

Inert-pair switching
 |
Valid, including after a small polynomial split sieve
 |

Two independent half-dimensional sieves
 |
Invalid level allocation
 |

Polynomially rough primitive norms
 |
Unconditional lower and upper bounds of matching order
 |

Negligible composite contamination
 |
Disproved for sufficiently small fixed roughness exponent
 |

Near-balanced split semiprime switching
 |
Negligible collar proved
 |

Fixed polynomial representation-moment minorants
 |
Negative mean at sufficiently small roughness cutoffs
 |

Complete signed large-split-divisor switching
 |
Unresolved
 |

Infinitely many genuine twin primes
 |
Not established
 |

The strongest surviving quantitative result of this lane is the actual composite count

$$
C_\beta(X)\asymp
\frac{X}{\sqrt\beta(\log X)^2}
$$

in the stated ordered limits. The half-dimensional sieve advantage is real, but it does not make the remaining composite contribution negligible.

The next decisive mathematical obligation is to exploit actual primality of $dm+2$ to control the signed switched expression (7), together with the corresponding short-divisor contribution, at additive accuracy $X/(\log X)^2$. Neither the quadratic character, primitive representability, divisor distribution alone, nor representation multiplicity determines this term.

Verification and limitations: I inspected the Fuchs et al. preprint, Iwaniec's 1976 half-dimensional sieve theorem, and Nath–Xie's beta-sieve framework. The original 1972 Iwaniec PDF could not be retrieved successfully; I therefore derived the switching bounds directly rather than relying on its precise numerical constants. The new deductions are internally checked, without independent worker validation or a novelty claim. No local or project files were accessed or modified, and no external messages were sent.

The straightforward second-sieve strategy is disproved within its specified level and information constraints. A fundamentally stronger switching argument remains possible, but the required prime-sensitive estimate has not been proved.

---

### Recovered response 3

The strongest manuscript-ready extraction is the exact large-order equivalence, the reduction of Fermat congruences to the shorter exponent $k=(n-1)/q$ on composites, and a power-saving counting bound that requires only a single sufficiently large shared prime-power divisor—not the full Fermat congruence.

Here is standalone, compilable TeX, with author and email left blank.

LaTeX

\documentclass[11pt]{article}
\usepackage{amsmath,amssymb,amsthm}

\newtheorem{proposition}{Proposition}
\newtheorem{corollary}{Corollary}
\newtheorem{remark}{Remark}

\title{Large Prime Divisors of Fermat Congruences
and Semiprime Pseudoprimes}
\author{}
% Email:
\date{}

\begin{document}
\maketitle

\section{Large-order certificates and shared prime divisors}

\begin{proposition}[Exact large-order criterion]
Let $n>2$ be an integer and suppose
\[
n-1=kq,
\qquad q\ \text{prime},\qquad q>\sqrt n.
\]
Then the following conditions are equivalent:
\begin{enumerate}
\item $n$ is prime;
\item $(\mathbb Z/n\mathbb Z)^\times$ contains an
      element of order $q$;
\item there exists $a\not\equiv1\pmod n$ such that
      $a^q\equiv1\pmod n$;
\item $q\mid\varphi(n)$.
\end{enumerate}

Moreover, if $n$ is composite, then for every integer
$a$,
\[
\gcd(n,a^{n-1}-1)=\gcd(n,a^k-1).
\tag{1}
\]
In particular,
\[
a^{n-1}\equiv1\pmod n
\quad\Longleftrightarrow\quad
a^k\equiv1\pmod n.
\tag{2}
\]
\end{proposition}

\begin{proof}
If $n$ is prime, the multiplicative group modulo $n$
is cyclic of order $kq$, so conditions 2--4 follow.
Conditions 2 and 3 are equivalent because $q$ is prime.

Suppose $q\mid\varphi(n)$. Since
\[
\varphi(n)=\prod_{r^e\parallel n}r^{e-1}(r-1)
\]
and $q\nmid n$, some prime divisor $r$ of $n$
satisfies $r\equiv1\pmod q$.
Write $n=rm$. Since $n\equiv1\pmod q$,
we have $m\equiv1\pmod q$. But
\[
1\le m=\frac nr<\frac nq<q.
\]
Consequently $m=1$ and $n=r$ is prime.
Lagrange's theorem gives the implication from
condition 2 to condition 4, completing the equivalence.

Now suppose $n$ is composite. The preceding argument
shows that $q\nmid\varphi(n)$ and, more specifically,
\[
q\nmid\varphi(r^j)
\]
for every prime power $r^j\mid n$.

If $r^j\mid a^{kq}-1$, the multiplicative order
of $a$ modulo $r^j$ divides both $kq$ and
$\varphi(r^j)$. Since the latter is coprime to $q$,
that order divides $k$. Hence
\[
r^j\mid a^{kq}-1
\quad\Longleftrightarrow\quad
r^j\mid a^k-1.
\]
Applying this equivalence to every prime-power
divisor of $n$ proves (1), and therefore (2).
\end{proof}

The large-order criterion requires no additional
condition $\gcd(a-1,n)=1$. Under the stated size
hypothesis, the existence of a nontrivial $q$-th root
already forces primality.

\begin{proposition}[Single shared prime divisor]
Let $n=rm$, where $r$ is an odd prime.
Then
\[
r\mid 2^{n-1}-1
\quad\Longleftrightarrow\quad
r\mid 2^{m-1}-1.
\tag{3}
\]
If, additionally, $n$ is composite and
$n-1=kq$ with $q>\sqrt n$ prime, these conditions
are equivalent to
\[
r\mid 2^{\gcd(k,m-1)}-1.
\tag{4}
\]

More generally, for any prime power $r^e\mid n$,
writing $n=r^e m$, and any integer $a$ coprime to $r$,
one has
\[
r^e\mid a^{n-1}-1
\quad\Longleftrightarrow\quad
r^e\mid a^{\gcd(r-1,m-1)}-1.
\tag{5}
\]
\end{proposition}

\begin{proof}
Put $t=\operatorname{ord}_r(2)$. Since $t\mid r-1$,
we have
\[
n-1=rm-1\equiv m-1\pmod t,
\]
which proves (3).

Under the additional large-$q$ hypothesis,
Proposition 1 shows that $q\nmid r-1$.
Thus
\[
t\mid n-1=kq
\quad\Longleftrightarrow\quad t\mid k.
\]
Together with (3), this proves (4).

For (5), put $u=\operatorname{ord}_{r^e}(a)$.
Since $u\mid\varphi(r^e)$, the required equivalence
follows from
\[
\begin{aligned}
\gcd(n-1,\varphi(r^e))
&=\gcd(n-1,r^{e-1}(r-1))\\
&=\gcd(n-1,r-1)\\
&=\gcd(m-1,r-1).
\end{aligned}
\]
Here the second equality uses $r\nmid n-1$,
and the third uses $r^e\equiv1\pmod{r-1}$.
\end{proof}

\section{A power-saving counting bound}

\begin{corollary}[Large shared prime-power factors]
Fix an integer $a\ge2$ and real numbers
\[
\frac12<\theta<1,\qquad 1-\theta<\delta\le1.
\]
Let $N_{a,\theta,\delta}(X)$ count composite integers
$X<n\le2X$ satisfying both:
\begin{enumerate}
\item $n-1=kq$ for some prime $q>X^\theta$;
\item $\gcd(n,a^{n-1}-1)$ has a prime-power
      divisor at least $X^\delta$.
\end{enumerate}
Then
\[
N_{a,\theta,\delta}(X)
\ll_{a,\theta,\delta}
\frac{X^{2-\theta-\delta}+X^{2-2\theta}}
     {\log X}.
\tag{6}
\]
In particular, this count is
$o(X/\log X)$.
\end{corollary}

\begin{proof}
For sufficiently large $X$, the hypothesis
$q>X^\theta$ implies $q>\sqrt n$. By (1), the
prime-power divisor in condition 2 also divides
$a^k-1$.

Moreover,
\[
k\le K:=2X^{1-\theta}.
\]

Fix $k$. For each prime $r$, let $s_r$ be the
smallest power of $r$ that is at least $X^\delta$.
Retain only those $s_r$ which divide $a^k-1$.
These retained prime powers are pairwise coprime.
Their number is therefore at most
\[
\frac{\log(a^k-1)}{\delta\log X}
\le\frac{k\log a}{\delta\log X}.
\]

Every counted integer $n$ is divisible by at least
one retained $s_r$. Since $n=kq+1$, this requires
\[
kq\equiv-1\pmod{s_r}.
\]
If $(k,s_r)>1$, there are no solutions.
Otherwise $q$ lies in a single residue class
modulo $s_r$.

Even without imposing primality on $q$, the number
of such $q$ with $X<kq+1\le2X$ is
\[
O\left(\frac{X}{ks_r}+1\right)
=O\left(\frac{X^{1-\delta}}k+1\right).
\]

Summing over the retained prime powers and then
over $k\le K$ gives
\[
\begin{aligned}
N_{a,\theta,\delta}(X)
&\ll_{a,\delta}
\frac1{\log X}
\sum_{k\le K}(X^{1-\delta}+k)\\
&\ll_{a,\delta}
\frac{KX^{1-\delta}+K^2}{\log X}.
\end{aligned}
\]
Substituting the value of $K$ proves (6).
Both exponents in its numerator are strictly
less than one.
\end{proof}

\begin{corollary}[Semiprime Fermat pseudoprimes]
Fix $a\ge2$ and $1/2<\theta<1$.
The number of composite semiprimes $n\in(X,2X]$
satisfying
\[
P^+(n-1)>X^\theta,
\qquad a^{n-1}\equiv1\pmod n
\]
is
\[
O_{a,\theta}\left(
\frac{X^{3/2-\theta}}{\log X}
\right),
\]
where $P^+(m)$ denotes the largest prime divisor
of $m$.

In particular, for base $2$ and $\theta=3/5$,
the bound is
\[
O\left(\frac{X^{9/10}}{\log X}\right).
\]
\end{corollary}

\begin{proof}
Every semiprime $n>X$ has a prime divisor at least
$\sqrt X$. The full Fermat congruence therefore
implies the shared-factor condition of Corollary 1
with $\delta=1/2$.
Since $\theta>1/2$,
\[
2-2\theta<3/2-\theta.
\]
The conclusion follows from (6).
\end{proof}

\begin{remark}
The counting argument actually requires only
one sufficiently large prime-power divisor shared
by $n$ and $a^{n-1}-1$. It does not require the
full Fermat congruence.

More generally, for composite Fermat pseudoprimes
having at most $R$ distinct prime factors, the
same argument applies with $\delta=1/R$, provided
$\theta>\max(1/2,1-1/R)$, by selecting a largest
full prime-power factor of $n$.
\end{remark}

\section{Scope and limitations}

The two primes in these arguments play different roles:
\[
q\mid n-1,\qquad r\mid n.
\]
They are necessarily distinct. The prime $q$ provides
the large-order certificate and the exponent reduction;
the prime $r$ is a potential shared factor of $n$
and the Fermat expression.

All counting bounds above remain valid on imposing
the additional condition that $n-2$ is prime.
However, an upper bound for composite Fermat
pseudoprimes does not supply a lower bound for
successful Fermat tests on that shifted-prime
sequence. No infinitude of twin primes follows
from these results alone.

\end{document}

Editorial and verification notes: Proposition 1 and the counting estimate come directly from the preceding research. The shared-prime-power formulation strengthens their presentation through exact elementary order and gcd identities. The counting proof deliberately retains the weaker single-shared-factor hypothesis, since requiring the complete Fermat congruence is unnecessary.

The mathematics is self-contained and internally checked. Independent review and literature-priority assessment remain outstanding; no novelty claim or twin-prime solution should be attached to this contribution.

---

### Recovered response 4

1. What an exceptional character supplies that an ordinary character does not

The Heath-Brown argument, and its quantitative refinement by Matomäki–Merikoski, use more than the existence of a real multiplicative character. A sufficiently exceptional character approximates the value $-1$ on prime arguments over a substantial numerical range. This permits replacing a Möbius coefficient by a character coefficient while controlling the resulting error.

Matomäki–Merikoski explicitly develop this replacement in their 2023 paper, beginning with the approximation

$$
\Lambda=\mu*\log\approx\chi*\log.
$$

Their error estimates depend essentially on the exceptional-zero hypothesis. I will not assume that hypothesis here.

oup.silverchair-cdn.com+1

Write the shifted Chen candidate as $n=p+2$, where $p$ is prime and $n$ is either prime or semiprime.

For a real character $\chi$, the desired behavior is

$$
\chi(n)=
\begin{cases}
-1,&n\text{ prime},\\
+1,&n=rs,\quad r,s\text{ prime}.
\end{cases}
$$

An ordinary character does not have this property.

There is also an exact collapse of the polynomial construction in the question. For any $F\in\mathbb Z[T]$,

$$
\left(\frac{F(p)}n\right)
=
\left(\frac{F(-2)}n\right),
$$

including the zero-symbol cases. This holds for composite odd $n$ as a Jacobi-symbol identity, not just for prime $n$.

Reversing the direction of reciprocity does not automatically fix it. For an odd prime $r\mid p+2$,

$$
\left(\frac rp\right)
=
(-1)^{\frac{r-1}{2}\frac{p-1}{2}}
\left(\frac{-2}{r}\right).
$$

The dependence on the other prime factor has disappeared, apart from the elementary residue-class sign.

A genuinely different symbol must therefore depend on the complementary factor $s=(p+2)/r$, not merely on the known prime $p$.

2. A cross-factor character family that really does suppress semiprime false positives

There is an unconditional construction that passes every sufficiently large prime and passes only a power-saving number of the polynomially rough composites. It uses the actual complementary factor, so it avoids the polynomial-collapse obstruction.

Fix $0<\alpha<1/2$. For a squarefree integer $n\in(X,2X]$ with least prime factor $r>X^\alpha$, write

$$
n=rs,\qquad r=P^-(n).
$$

For a positive integer $J<r$, define the filter

$$
G_J(n)=
\prod_{j=0}^{J-1}
\mathbf1_{\left\{
\left(\frac{(1+j)(s+j)}r\right)=1
\right\}}.
\tag{1}
$$

All zero-symbol cases are rejected.

Prime contribution. If $n$ is prime, then $r=n,\ s=1$. Every symbol in (1) has a nonzero square numerator. Consequently,

$$
G_J(n)=1.
$$

Composite contribution. For a fixed possible least prime factor $r$, let

$$
A_r=\left\{b\in\mathbb F_r:
\left(\frac{(1+j)(b+j)}r\right)=1
\text{ for }0\le j<J\right\}.
$$

By expanding the product of the $J$ quadratic-character projectors and applying the classical Weil character-sum bound to each nonempty subset of the distinct linear factors,

$$
\boxed{|A_r|=2^{-J}r+O(J\sqrt r).}
\tag{2}
$$

The implied constant can be taken absolute. Indeed, each nonempty subset contributes a character sum bounded by its degree minus one times $\sqrt r$, and the normalization $2^{-J}$ compensates for the number of subsets. The at most $J$ exceptional zero-symbol residues cost $O(J)$.

This uses the standard complete character-sum theorem originating in Weil's work, not an exceptional-character assumption.

pubmed.ncbi.nlm.nih.gov

A uniform false-positive bound

For a composite $n$, its least prime factor satisfies $r\le\sqrt{2X}$. The interval for $s$ has length $X/r$, which is at least $r/2$.

Each residue class modulo $r$ therefore occurs $O(X/r^2)$ times in that interval. From (2), the number of passing integers on this row is

$$
\ll \frac Xr
\left(2^{-J}+\frac{J}{\sqrt r}\right).
$$

Summing over the possible least prime factors gives

$$
\begin{aligned}
&\#\{X<n\le2X:n\text{ composite},\
P^-(n)>X^\alpha,\ G_J(n)=1\}\\
&\qquad\ll_\alpha
2^{-J}X+JX^{1-\alpha/2}.
\end{aligned}
\tag{3}
$$

Here the prime harmonic sum over $X^\alpha<r\le\sqrt{2X}$ is bounded at fixed $\alpha$. The second term follows even by summing $r^{-3/2}$ over all integers exceeding $X^\alpha$.

Take

$$
J=\left\lceil\frac{\alpha\log X}{2\log2}\right\rceil.
$$

Then $J<r$ throughout the rough population for sufficiently large $X$, and (3) becomes

$$
\boxed{
\#\{\text{passing rough composites}\}
\ll_\alpha X^{1-\alpha/2}\log X.
}
\tag{4}
$$

This counts all rough composite integers, so it is also an upper bound for the false positives satisfying the additional condition that $n-2$ is prime.

In particular, this family suppresses the semiprime false positives to $o(X/\log^2X)$, strictly below any fixed positive Chen lower-bound coefficient.

However, the Chen lower bound applies to the unfiltered population. Establishing that a positive portion of that population passes (1) is a different mathematical obligation. The false-positive bound alone cannot establish it.

3. A fixed-size family also gives a small false-positive coefficient at the Chen scale

The preceding construction used $J$ growing with $X$. I checked that one can instead fix a sufficiently large $J$ permanently and still obtain the required small coefficient by exploiting the actual primality conditions.

Proposition. For every fixed $0<\alpha<1/2$, there is a constant $K_\alpha$, independent of $J$, such that

$$
\limsup_{X\to\infty}
\frac{\log^2 X}{X}
\sum_{\substack{X<rs\le2X\\
X^\alpha<r<s\\
r,s,rs-2\text{ prime}}}
G_J(rs)
\le K_\alpha 2^{-J}.
\tag{5}
$$

In particular, a finite family of cross-factor symbols suffices to make the retained semiprime count smaller than any specified positive Chen coefficient.

Proof

Put $\rho_r=|A_r|/r$ and define the centered residue weight

$$
g_r(b)=\mathbf1_{A_r}(b)-\rho_r.
$$

We first need a uniform estimate on incomplete sums of this weight; counting only complete periods would not suffice after opening the sieve divisors.

For $h\bmod r$, define

$$
C_r(h)=\sum_{b\bmod r}g_r(b)g_r(b+h).
$$

Unless $h$ belongs to the at most $2J-1$ differences of the $J$ shifts, the two sets of linear factors in the character expansion are disjoint. Applying the same Weil estimate to their union gives

$$
C_r(h)\ll J\sqrt r.
$$

For the exceptional differences, use $|C_r(h)|\le r$.

Writing $\widehat g_r$ for the normalized additive Fourier transform, it follows that

$$
|\widehat g_r(u)|^2
\le \frac1{r^2}\sum_{h\bmod r}|C_r(h)|
\ll \frac J{\sqrt r}.
$$

Additive completion therefore gives, on every interval $I$ and every progression step $d$ coprime to $r$,

$$
\left|\sum_{t\in I}g_r(a+dt)\right|
\ll \sqrt J\,r^{3/4}\log r.
\tag{6}
$$

Complete periods contribute zero, so this bound does not depend on the interval length.

Now fix $r$ and upper-sieve the two linear forms

$$
s,\qquad rs-2
$$

on the interval of length at most $X/r$, retaining the residue restriction $s\bmod r\in A_r$.

Choose the sieve level $D=X^{1/16}$ and cutoff

$$
z=X^{\min(\alpha/2,\,1/160)}.
$$

Every sieve prime is smaller than $r$. For an odd sieve prime there are two distinct forbidden residues; at 2 there is one. Thus the sieve dimension is two.

For each squarefree sieve modulus $d$, with $\nu(d)$ forbidden residue classes, (6) gives the exact local main term

$$
\rho_r\frac{|I|\nu(d)}d
$$

with error

$$
O\!\left(\nu(d)
[1+\sqrt J\,r^{3/4}\log r]\right).
$$

The standard upper-bound sieve has bounded coefficients at this level-to-cutoff ratio. Its main term is at most

$$
K'_\alpha \rho_r\frac{X}{r\log^2X}.
$$

The total remainder, summed over all $r\le\sqrt{2X}$, is

$$
\ll \sqrt J\,D X^{7/8}(\log X)^C
=
\sqrt J\,X^{15/16}(\log X)^C.
$$

This is negligible at the Chen scale for each fixed $J$. Finally, substitute

$$
\rho_r=2^{-J}+O(Jr^{-1/2})
$$

and use the bounded prime harmonic sum over $X^\alpha<r\le\sqrt{2X}$. This proves (5). Prime squares, if included, cost $O(\sqrt X)$. $\square$

This bound genuinely includes the simultaneous primality of $r,s,rs-2$. It is not just a random model for factor residues.

For comparison, Green–Tao's Restriction theory of the Selberg sieve, with applications, Theorem 6.1, records the unconditional lower bound of order $X/\log^2X$ for Chen primes with polynomially large prime factors. In fact, the roughness stated there is stronger than the $X^{1/10}$ cutoff needed for the calculations below.

arxiv.org

Consequently, if $c_{\mathrm{Ch}}>0$ is a valid Chen lower-bound coefficient for the chosen interval and roughness, we can choose a fixed $J$ with

$$
K_\alpha 2^{-J}<\frac{c_{\mathrm{Ch}}}{10}.
$$

The false-positive side of the proposed construction is therefore solved. The remaining question is whether the lower sieve can retain a sufficiently large coefficient after this restriction.

4. An unconditional distribution estimate on actual shifted primes

I next tested the lower-sieve side directly, rather than assuming that the character patterns remain equidistributed after restricting to Chen primes.

A useful polynomial range survives. In this range, the cross-factor symbols can be inserted into genuine prime progression sums, with a power-saving error.

Set

$$
\mathcal R=
\{r\text{ prime}:X^{0.101}<r\le X^{0.102}\},
\qquad D=X^{0.21}.
$$

Retain the centered weight $g_r$ from §3. Define

$$
E(r,d)=
\sum_{\substack{X-2<t\le2X-2\\t\equiv-2\pmod{rd}}}
\Lambda(t)\,
g_r\!\left(\frac{t+2}{r}\right).
$$

Proposition. For every fixed $J$,

$$
\boxed{
\sum_{r\in\mathcal R}
\sum_{\substack{d\le D\\d\text{ squarefree}\\(d,2r)=1}}
|E(r,d)|
\ll_J X^{0.995}.
}
\tag{7}
$$

The same assertion holds for any of the $2^J$ specified nonzero sign patterns, centered at its own exact residue density.

Proof: the conductor calculation

The significant point is that the symbol $((t+2)/r\,/\,r)$ is periodic in $t$ modulo $r^2$, not merely modulo $r$.

Define

$$
F_r(t)=
\mathbf1_{t\equiv-2\pmod r}
g_r\!\left(\frac{t+2}{r}\right).
$$

Expand it in multiplicative characters modulo $r^2$. The coefficient of $\chi$ is

$$
c_{\chi,r}
=
\frac1{\varphi(r^2)}
\sum_{b\bmod r}
g_r(b)\overline{\chi(-2+rb)}.
$$

The subgroup $1+r\mathbb Z/r^2\mathbb Z$ is additively isomorphic to $\mathbb F_r$. Hence the restriction of $\chi$ to the coset $-2+rb$ is a constant times an additive character in $b$.

If $\chi$ is induced from modulus $r$, this additive character is trivial, and the coefficient vanishes because $g_r$ is centered.

Every nonzero coefficient therefore belongs to a primitive character of conductor $r^2$. Moreover, the Fourier estimate proved in §3 gives

$$
|c_{\chi,r}|
\ll \sqrt J\,r^{-5/4}.
\tag{8}
$$

This explicit coefficient saving is important. A bound using only the number of permitted residue classes would be weaker.

Expand the additional congruence modulo $d$ by multiplicative characters. Because $(d,r)=1$, the resulting primitive conductors have the form

$$
r^2 f,\qquad f\mid d.
$$

The conductor determines $r$ uniquely, since $f$ is squarefree and coprime to $r$.

The total coefficient cost of inducing from $f$ to the possible $d$'s is bounded by

$$
\sum_{\substack{d\le D\\f\mid d\\d\text{ squarefree}}}
\frac1{\varphi(d)}
\ll \frac{\log X}{\varphi(f)}.
$$

The discrepancy between an induced character and its primitive character involves only prime powers whose bases divide $d$. Summing these discrepancies costs $O(R^2D(\log X)^C)$ for $r\asymp R$, negligible in the range in question.

Now apply Vaughan's primitive-character mean-value estimate, in the explicit form given by Akbary–Hambrook, Theorem 1.2 of arXiv:1309.2730:

$$
\sum_{q\le Q}\frac q{\varphi(q)}
\sum_{\chi\bmod q}^{*}
\max_{y\le2X}|\psi(y,\chi)|
\ll
\left(X+X^{1/2}Q^2+
X^{2/3}Q^{3/2}+X^{5/6}Q\right)
(\log X)^C.
$$

No exceptional-zero assumption is required.

arxiv.org

Dyadically grouping $r\asymp R,\ f\asymp F$, the relevant conductor bound is $Q\asymp R^2F$, and the coefficient prefactor is $O_J(R^{-5/4}F^{-1}(\log X)^C)$.

After summing the dyadic ranges, this gives

$$
\begin{aligned}
\ll_J(\log X)^C\bigg[
&\frac{X}{R^{5/4}}
+X^{5/6}R^{3/4}\\
&+X^{2/3}R^{7/4}D^{1/2}
+X^{1/2}R^{11/4}D
+R^2D
\bigg].
\end{aligned}
$$

The exponent ledger is:

Contribution
 |
Largest exponent of $X$
 |

First
 |
0.87375
 |

Second
 |
0.90984
 |

Third
 |
0.95017
 |

Fourth
 |
0.99050
 |

Induced-character correction
 |
0.41400
 |

All have strict power-saving margins. Absorbing the fixed logarithmic factors proves (7). $\square$

This is an actual arithmetic estimate, involving the von Mangoldt function at the required shift, not merely finite-field equidistribution.

5. What the estimate proves after a lower sieve

The available level in (7) is large enough to perform a genuine lower sieve on the complementary factor, at a cutoff overlapping the ordinary Chen roughness range.

Take

$$
z=X^{0.104}.
$$

For each $r\in\mathcal R$, write $n=p+2=rs$, and sieve $s$ through $z$, temporarily excluding $r$ itself from the sieve primes.

The opened progression moduli are $rd$, and their local density is $1/\varphi(d)$ for odd $d$ coprime to $r$. Ordinary Bombieri–Vinogradov controls the uncentered main term, since

$$
rd\le X^{0.312}.
$$

The multiplicity of any such modulus coming from the possible tags $r$ is bounded absolutely: every tag exceeds $X^{0.101}$.

Equation (7) controls the additional cross-factor residue weight for any bounded sieve coefficients on these rows.

The linear lower-sieve parameter is

$$
s_0=\frac{\log D}{\log z}
=\frac{105}{52}>2.
$$

Thus its lower function is strictly positive.

Write

$$
K_0=2\prod_{\ell>2}
\left(1-\frac1{(\ell-1)^2}\right).
$$

The local sieve product is asymptotic to

$$
\frac{K_0e^{-\gamma}}{0.104\log X},
$$

and the harmonic mass of the tagged primes tends to

$$
\sum_{r\in\mathcal R}\frac1{r-1}
\longrightarrow\log\frac{102}{101}.
$$

Removing proper prime powers from the original von Mangoldt sum, and removing squareful $n$, costs $o(X/\log^2X)$ in counting units. After these removals, every retained $n$ has exactly one prime factor in $\mathcal R$, since every other factor exceeds $z$.

We obtain the following unconditional conclusion.

Theorem. For every fixed sign pattern of length $J$, the number of distinct squarefree composites $n\in(X,2X]$ for which

-

$n-2$ is prime;

-

$X^{0.101}<P^-(n)\le X^{0.102}$;

-

every other prime factor exceeds $X^{0.104}$;

-

the complementary factor realizes the specified cross-character pattern,

is at least

$$
\left(c_*2^{-J}+o_J(1)\right)
\frac{X}{\log^2X},
$$

where the following explicit constant is positive:

$$
c_*=
\frac{2K_0}{0.21}
\log\frac{53}{52}
\log\frac{102}{101}>0.
\tag{9}
$$

The constant follows from the standard formula

$$
f_{\rm lin}(s_0)=
\frac{2e^\gamma}{s_0}\log(s_0-1).
$$

The necessary linear-sieve framework also appears in Grimmelt–Teräväinen's arXiv:2508.16400, §3, where the Chen construction uses a roughness cutoff $N^{1/10}$.

arxiv.org

Interpretation

This proves that every fixed pattern occurs abundantly on the actual shifted-prime source before its final restriction to at most two prime factors.

It does not prove that these composites are semiprimes. They may have additional prime factors.

That distinction cannot be removed by citing Chen's theorem again: a Chen-type theorem applied to the complementary factor $s$ would generally allow $s$ to have two prime factors, making $n=rs$ a product of three.

6. Why the final restriction still fails

There are two precise obstructions.

A. The complementary-prime sieve runs out of level

On a tagged row $r\asymp X^a$, the complementary integer has size

$$
Y\asymp X^{1-a}.
$$

To make $s$ prime by a lower linear sieve, one must sift through $\sqrt Y$, with a positive lower-sieve parameter exceeding two. That requires a distribution level exceeding $Y$.

The available estimate in §4 instead has the restrictive term

$$
X^{1/2}R^{11/4}D.
$$

Its power-saving condition is

$$
\boxed{
\frac{\log D}{\log X}
<
\frac12-\frac{11a}{4}.
}
$$

At $a=0.102$, this gives a maximum exponent of $0.2195$, before taking any additional margins. The working choice $0.21$ is within that range.

For primality of the complementary factor, however, the required exponent exceeds $1-a=0.898$.

The actual lower-sieve parameter at the primality cutoff would be only approximately $0.47$, far below the required value two.

This is a specific, quantified failure of the attempted second lower sieve. It is not an assertion that no stronger distribution theorem could exist.

B. Normalizing the character filter restores its false-positive weight

For each fixed $r$, the passing set has density

$$
\rho_r=2^{-J}+o(1).
$$

Suppose a nonnegative residue weight $W_r$ vanishes outside the passing set but is intended to preserve the ordinary local main term:

$$
\frac1r\sum_{b\bmod r}W_r(b)=1.
$$

Then necessarily

$$
\|W_r\|_\infty\ge\frac1{\rho_r},
\qquad
\frac1r\sum_{b\bmod r}W_r(b)^2
\ge\frac1{\rho_r}.
$$

Both inequalities follow immediately from the support size and Cauchy–Schwarz.

The cheapest constant-on-support choice is

$$
W_r(b)=\rho_r^{-1}\mathbf1_{A_r}(b).
$$

Its surviving coefficients are of order $2^J$. That factor compensates for the $2^{-J}$ false-positive reduction.

There is a corresponding signed-weight obstruction. Suppose a residue weight has average $b_0>0$, is nonpositive outside $A_r$, and is bounded above by $M$ inside it. Then

$$
b_0\le \rho_r M.
$$

Consequently $M\ge b_0/\rho_r$. A locally centered modification of a positive Chen coefficient cannot make almost all composite residues nonpositive while keeping the remaining coefficients uniformly small.

This explains exactly why a family of ordinary candidate-dependent characters does not automatically reproduce the exceptional-character method.

7. The remaining fixed-gap inequality

Let $T_X$ count genuine twins on the chosen dyad, and $C_X$ count the squarefree rough semiprime neighbors. Chen's theorem supplies

$$
T_X+C_X\ge
(c_{\mathrm{Ch}}+o(1))
\frac{X}{\log^2X}.
$$

Let $C_{J,X}$ count the semiprimes passing the new filter. Its complete filtered population is exactly

$$
F_{J,X}=T_X+C_{J,X}.
$$

The result in §3 gives

$$
C_{J,X}\le
(K_\alpha2^{-J}+o(1))
\frac{X}{\log^2X}.
$$

Choose a fixed $J$ making this coefficient less than $c_{\mathrm{Ch}}/10$.

It would now suffice to prove

$$
F_{J,X}\ge
\frac{c_{\mathrm{Ch}}}{5}
\frac{X}{\log^2X}
$$

on unbounded dyadic intervals.

But the available Chen lower bound does not prove this. Even hypothetical exact equidistribution of all character patterns on the actual semiprime population would only give

$$
F_{J,X}
=
2^{-J}(T_X+C_X)
+(1-2^{-J})T_X
+o(X/\log^2X).
$$

Without information on $T_X$, this provides a lower coefficient $2^{-J}c_{\mathrm{Ch}}$, reducing the known lower bound by precisely the same factor used to reduce semiprime contamination.

With the growing family of §2, the relationship becomes stronger:

$$
F_{J,X}=T_X+
O_\alpha(X^{1-\alpha/2}\log X).
$$

A main-scale lower bound for this filtered count would prove a main-scale twin-prime lower bound. Establishing that lower is the remaining arithmetic problem, not a consequence of the small false-positive count.

Research verdict

The cross-factor construction survives the initial mathematical tests substantially better than the polynomial or simple reciprocity substitutions.

Proof obligation
 |
Outcome
 |

Avoid the polynomial-collapse obstruction
 |
Achieved
 |

Preserve every genuine prime neighbor
 |
Exact
 |

Reduce semiprime false positives below the Chen coefficient
 |
Proved
 |

Obtain a power-saving bound on all rough composite false positives
 |
Proved
 |

Control actual shifted-prime character sums with sieve divisors
 |
Proved in the stated polynomial range
 |

Establish every fixed pattern on actual rough composite neighbors
 |
Proved
 |

Preserve a sufficiently large Chen lower bound after filtering
 |
Unproved
 |

The strongest new prime-sensitive result is (7), because it controls the actual shifted-prime sequence with the genuine cross-factor dependence, including the square conductor and the sieve-divisor cost.

The most promising remaining direction within this lane is a parity-sensitive estimate for the full switched Chen contribution, retaining the cross-character weight and controlling its complementary prime factor. An improvement confined to the initial divisor rows, or another reduction of the false-positive upper bound, would not by itself close the argument.

Verification and decisions: I chose the least-prime-factor/complementary-factor symbols to avoid the reciprocity collapse, and the explicit exponent range to make every term of Vaughan's estimate power-saving. These deductions have been internally checked, but not independently worker-reviewed or assessed for novelty. No Siegel zero was assumed, no local or project files were accessed, and no new manuscript was created.

The twin-prime conjecture remains unresolved by this route.

---

### Recovered response 5

1. The graph hypothesis really does force many nondegenerate four-cycles

Write $L=\log X$, and assume for contradiction that there are only finitely many twin primes.

Using the rough version of Chen's lower bound stipulated in the assignment, the graph has at least

$$
c_{\mathrm{Ch}}\frac{X}{L^2}
$$

edges $r\!-\!s$, where $r<s$ are primes, $r,s\ge X^{1/8}$, $X/2<rs\le X$, and $rs-2$ is prime. Removing prime squares costs only $O(\sqrt X)$.

Removing the balanced factors is legitimate. For fixed $r$, the upper-bound sieve on the two forms

$$
s,\qquad rs-2
$$

gives $O(X/(rL^2))$ possible neighbors, uniformly over the allowed range of $r$.

Thus the number of edges with $X^{1/2-\eta}<r\le\sqrt X$ is at most

$$
\left(C\log\frac{1/2}{1/2-\eta}+o(1)\right)
\frac{X}{L^2}
=O(\eta)\frac{X}{L^2}.
$$

Fixing sufficiently small $\eta>0$, we retain a positive Chen-scale lower bound entirely on the unbalanced factors.

Partition those factors into dyadic boxes $r\asymp R,\ s\asymp S$, with $RS\asymp X$. There are $O(L)$ relevant boxes. At least one contains

$$
E\gg \frac{X}{L^3}
$$

edges.

Let $U,V$ be the numbers of prime vertices in its two intervals. The prime number theorem gives

$$
U\asymp\frac R L,\qquad V\asymp\frac S L.
$$

If $A$ is its bipartite adjacency matrix, the ordered four-cycle count, initially allowing repeated vertices, satisfies

$$
\begin{aligned}
\operatorname{tr}((AA^{\mathsf T})^2)
&=\sum_{r_1,r_2}
\left(\sum_s A_{r_1s}A_{r_2s}\right)^2\\
&\ge \frac{E^4}{U^2V^2}
\gg\frac{X^2}{L^8}.
\end{aligned}
\tag{1}
$$

This is two applications of Cauchy–Schwarz.

The repeated-vertex contribution is at most $UV^2+U^2V$, which is $o(X^2/L^8)$, since both factor ranges have polynomial length.

Therefore the finiteness hypothesis forces

$$
\boxed{
\#\{\text{nondegenerate ordered four-cycles}\}
\gg\frac{X^2}{L^8}
}
\tag{2}
$$

in at least one unbalanced factor box.

These are genuine configurations of four distinct ordinary primes

$$
p_{ij}=r_i s_j-2
$$

satisfying

$$
(p_{11}+2)(p_{22}+2)
=(p_{12}+2)(p_{21}+2).
$$

The question is whether the arithmetic upper bound can contradict (2).

2. Exact four-cycle local densities: the correlation has the opposite sign from the hoped-for obstruction

It is essential to count the eight simultaneous prime conditions: the four factor primes and the four labels.

For an odd prime $\ell$, condition on all four factor variables being units modulo $\ell$. Put $m=\ell-1$.

For a single edge, the conditional local survival probability is

$$
A_\ell=1-\frac1m.
$$

For four edges forming a rectangle, the conditions are

$$
r_i s_j\not\equiv2\pmod\ell
\qquad(i,j\in\{1,2\}).
$$

There are two cases.

If $r_1=r_2\bmod\ell$, which occurs with probability $1/m$, each $s_j$ has one forbidden unit residue. Otherwise each has two forbidden unit residues. Hence the exact conditional four-cycle density is

$$
B_\ell=
\frac1m\left(1-\frac1m\right)^2
+
\left(1-\frac1m\right)
\left(1-\frac2m\right)^2.
$$

Simplifying,

$$
B_\ell=1-\frac4m+\frac6{m^2}-\frac3{m^3},
$$

and consequently

$$
\boxed{
\frac{B_\ell}{A_\ell^4}
=1+\frac1{(\ell-2)^3}.
}
\tag{3}
$$

In particular, the four-edge survival probability is strictly greater than the fourth power of the single-edge survival probability.

At $\ell=3$, for instance, the edge condition becomes $r=s\bmod3$. The graph splits into two permitted residue blocks. Four independent edges would have survival probability $1/16$, whereas the actual rectangle survives with probability $1/8$.

Let

$$
K_0=2\prod_{\ell>2}
\left(1-\frac1{(\ell-1)^2}\right)
$$

be the usual twin-prime singular series. The full eight-form singular series for these rectangles is

$$
\boxed{
\mathfrak S_4
=K_0^4
\prod_{\ell>2}
\left(1+\frac1{(\ell-2)^3}\right).
}
\tag{4}
$$

The extra Euler product converges and is strictly greater than two.

This is an exact local calculation, not a conjectural assertion of independence between the four labels. The local correlations actually favor multiplicative rectangles.

3. A rigorous arithmetic upper bound matches the graph lower bound

The multivariable upper-bound sieve gives

$$
\boxed{
C_4(R,S)\ll
\mathfrak S_4\frac{R^2S^2}{L^8}
\asymp \frac{X^2}{L^8}.
}
\tag{5}
$$

Here is the remainder calculation needed to justify applying that sieve.

Consider the polynomial in four variables

$$
\mathcal F=
r_1r_2s_1s_2
\prod_{i,j=1}^2(r_i s_j-2).
$$

For a prime $\ell$, the proportion of residue tuples on which $\ell\nmid\mathcal F$ is

$$
\sigma_\ell=
\begin{cases}
2^{-4},&\ell=2,\\
(1-\ell^{-1})^4 B_\ell,&\ell>2.
\end{cases}
$$

Therefore the sieve density $g(\ell)=1-\sigma_\ell$ satisfies

$$
g(\ell)=\frac8\ell+O(\ell^{-2}).
$$

For a squarefree modulus $d$, let $g(d)$ be its multiplicative extension. Over the rectangular integer box, CRT gives the divisor count

$$
\mathcal V g(d)
+
O\!\left(
\frac{\mathcal V}{M_{\min}}\,d g(d)
\right),
$$

where $\mathcal V\asymp R^2S^2$ is the box volume and $M_{\min}\asymp\min(R,S)$.

Take the sieve level $D=M_{\min}^{1/2}$. Since $dg(d)\le C^{\omega(d)}$ for an absolute constant $C$, the total divisor remainder is bounded by

$$
\ll
\frac{\mathcal V D}{M_{\min}}
(\log D)^C
=o(\mathcal V/L^8).
$$

A fixed-dimension upper sieve with cutoff $z=D^{1/u}$, for sufficiently large fixed $u$, has main product

$$
\prod_{\ell\le z}(1-g(\ell))
\sim
\frac{e^{-8\gamma}\mathfrak S_4}
{(\log z)^8}.
$$

Because the factor ranges have fixed polynomial lower bounds, $\log z\asymp L$. This proves (5).

The proof follows the multivariable sieve mechanism used by Ford, Luca and Pomerance in The image of Carmichael's $\lambda$-function, §5, with the local factors recomputed here for the four shifted products.

arxiv.org

Combining (2) and (5), the proposed multiplicative-energy contradiction fails at the level of powers of $X$ and logarithms. Both bounds have exactly the same order.

4. The complete multiplicative energy has matching bounds, including interactions between boxes

The single-box estimate can be strengthened to the entire unbalanced Chen population.

Let $\mathcal B_X$ be the set of retained semiprime endpoints $rs$. Under the finite-twins hypothesis,

$$
E:=|\mathcal B_X|\asymp X/L^2.
$$

Define its multiplicative energy by

$$
\mathcal E_\times(\mathcal B_X)
=
\#\{(a,b,c,d)\in\mathcal B_X^4:ab=cd\}.
$$

Unique factorization gives the exact identity

$$
\mathcal E_\times(\mathcal B_X)
=2E^2-E+2C_4^{\mathrm{ord}},
\tag{6}
$$

where $C_4^{\mathrm{ord}}$ counts ordered nondegenerate rectangles throughout the unbalanced graph.

Indeed, any nontrivial equality between two products of squarefree semiprimes must arise from two different pairings of four distinct prime factors. These pairings form a four-cycle. The factor two accounts for the two choices of which diagonal pairing occurs on the left of the equality.

Global upper bound. Every rectangle satisfies

$$
\frac12<\frac{r_1}{r_2}<2,
\qquad
\frac12<\frac{s_1}{s_2}<2.
$$

This follows from the common product window $X/2<r_i s_j\le X$.

Thus rectangles cannot connect widely separated factor scales. Covering all rectangles requires only $O(L)$ enlarged dyadic boxes, so (5) gives

$$
C_4^{\mathrm{ord}}\ll X^2/L^7.
$$

Global lower bound. Partition the edges into $M=O(L)$ disjoint factor boxes, with edge counts $E_i$. Each box has at most $O(X/L^2)$ possible pairs of prime vertices. Applying (1) inside every box and then Hölder's inequality gives

$$
\begin{aligned}
C_4^{\mathrm{ord}}
&\gg \frac{L^4}{X^2}\sum_i E_i^4
-o(X^2/L^7)\\
&\gg \frac{L^4E^4}{X^2M^3}
-o(X^2/L^7)\\
&\gg X^2/L^7.
\end{aligned}
$$

Consequently, under the stated contradiction hypothesis,

$$
\boxed{
\mathcal E_\times(\mathcal B_X)
=2E^2-E+\Theta(X^2/L^7).
}
\tag{7}
$$

The nontrivial multiplicative energy is smaller than the trivial energy by a factor of order $L^{-3}$.

This establishes the matching orders for the entire population, not merely a favorable box. There is no additional logarithmic gain from combining the boxes.

The rough Chen input used here is also explicitly stated with cutoff $X^{1/8}$ in §3 of Tao's exposition of Chen's theorem.

What's new

5. Compatibility even at leading order

To test whether a sharper numerical comparison could repair the argument, consider a rectangular factor box entirely within the product window, containing $U,V$ prime vertices.

The natural prime-pattern main terms would be

$$
E\sim K_0\frac{UV}{L},
$$

and

$$
C_4^{\mathrm{ord}}
\sim\mathfrak S_4\frac{U^2V^2}{L^4}.
$$

These are predictions, not established asymptotics for actual prime labels.

Substituting the predicted edge count into the exact graph lower bound yields

$$
C_4^{\mathrm{ord}}
\ge (K_0^4+o(1))\frac{U^2V^2}{L^4}.
$$

But by (4),

$$
\mathfrak S_4>K_0^4.
$$

Thus even the predicted sharp arithmetic main term is compatible with the graph inequality.

A rigorous comparison model

This compatibility can be realized without assuming any prime-tuple conjecture.

Use the actual prime factor vertices. Fix $z$, and permit an edge only when

$$
rs-2\not\equiv0\pmod\ell
\quad\text{for every prime }\ell\le z.
$$

Independently retain each permitted edge with probability

$$
\frac1L\prod_{\ell\le z}(1-\ell^{-1})^{-1}.
$$

For fixed $z$, the prime number theorem in fixed progressions gives the exact asymptotic residue distributions of the vertices. The expected edge and rectangle counts therefore have precisely the truncated Euler factors computed in §2.

Their relative variances tend to zero. For rectangles, two indicator products are independent unless the rectangles share an edge. The number of ordered pairs sharing an edge is

$$
O(U^3V^3),
$$

while the square of the expected rectangle count has order $U^4V^4/L^8$. The relative variance is therefore

$$
O_z(L^8/(UV))=o(1).
$$

Taking $X\to\infty$ first and then $z\to\infty$, or using a sufficiently slow diagonal choice of $z$, realizes the stated leading constants simultaneously.

Every selected endpoint $rs$ is composite.

This is a comparison model for the graph information and local prime densities; its labels are not asserted to be actual primes. It shows why those pieces of information alone cannot exclude a population consisting entirely of composite endpoints.

The obstruction extends beyond four-cycles. For an even cycle of length $2k$, transforming the right-hand residues by $s\mapsto2/s$ turns the local condition into proper coloring of the cycle with $m=\ell-1$ colors.

Its conditional local density is exactly

$$
\frac{(m-1)^{2k}+(m-1)}{m^{2k}}.
$$

Relative to $2k$ independent edges, the correction factor is

$$
1+\frac1{(\ell-2)^{2k-1}}>1.
$$

Thus every fixed even-cycle length exhibits the same favorable local correlation. Counting more fixed cycles does not reverse the discrepancy.

6. Change of mechanism: growing common-neighbor sets and Gallagher's larger sieve

I next abandoned the fixed-cycle count and tested whether the graph forces a sufficiently large simultaneous prime constellation to contradict the larger sieve.

This allows the number of prime conditions to grow with $X$, rather than remaining fixed.

Proposition. Under the finite-twins hypothesis, fix $0<\kappa<1/16$, and put

$$
k=\left\lfloor\frac{\kappa L}{\log L}\right\rfloor.
$$

There exist $k$ distinct genuine small-factor primes $r_1,\ldots,r_k$, all in the same residue class modulo every prime at most $4k+10$, and a common-neighbor set $\mathcal S$ of large-factor primes satisfying

$$
|\mathcal S|\ge S X^{-\kappa+o(1)},
\tag{8}
$$

such that every one of the numbers

$$
s,\quad r_1s-2,\quad\ldots,\quad r_ks-2
$$

is prime for every $s\in\mathcal S$.

Proof

Use the dense box obtained in §1, with graph density

$$
\delta=\frac E{UV}\gg L^{-1}.
$$

Set $T=4k+10$ and

$$
Q_0=\prod_{\ell\le T}\ell=X^{o(1)}.
$$

Partition the $U$ small prime vertices by their residue classes modulo $Q_0$.

Discard every class containing fewer than $\delta U/(4Q_0)$ vertices. This deletes at most $\delta UV/4=E/4$ edges.

Some remaining class has size

$$
U'\ge\frac{\delta U}{4Q_0}
$$

and edge density at least $\delta/2$.

At least $\delta V/4$ right vertices then have at least $\delta U'/4$ neighbors in this class. Since $U'$ has polynomial size and $k$ is logarithmic, each such vertex is adjacent to at least $(\delta U'/8)^k$ ordered distinct $k$-tuples, for sufficiently large $X$.

Averaging over the possible tuples shows that some tuple has at least

$$
\frac{\delta V}{4}\left(\frac{\delta}{8}\right)^k
$$

common neighbors. Using $V\asymp S/L$ proves (8). $\square$

This is stronger structural information than merely the existence of many four-cycles.

Can the larger sieve exclude this constellation?

For the chosen tuple, let $\nu_\ell$ be the number of forbidden residue classes for the simultaneous prime forms in $s$, and write $v_\ell=\ell-\nu_\ell$.

For every odd $\ell\le T$, all $r_i$ are congruent to the same nonzero residue, so

$$
\nu_\ell=2.
$$

For $\ell>T$, we only know

$$
\nu_\ell\le k+1.
$$

The constellation is therefore admissible at every prime. Its growing number of forms does not introduce a local obstruction.

Moreover,

$$
\begin{aligned}
\sum_\ell \log\ell
\left(\frac1{v_\ell}-\frac1\ell\right)
&\ll 1+k\sum_{\ell>T}\frac{\log\ell}{\ell^2}\\
&\ll 1+\frac{k}{T}\\
&\ll1.
\end{aligned}
\tag{9}
$$

Here and below we use primes smaller than the candidate values, so a prime being equal to the sieving prime does not cause an erroneous exclusion.

Gallagher's larger sieve gives, for any finite set $\mathcal P$ of such primes,

$$
|\mathcal S|
\le
\frac{W-\log S}
{\displaystyle\sum_{\ell\in\mathcal P}
\frac{\log\ell}{v_\ell}-\log S},
\qquad
W=\sum_{\ell\in\mathcal P}\log\ell,
\tag{10}
$$

when the denominator is positive.

For any choice of $\mathcal P$, splitting its primes at $W$ and applying Mertens' estimate gives

$$
\sum_{\ell\in\mathcal P}\frac{\log\ell}{\ell}
\le\log W+O(1).
$$

By (9), the denominator in (10) is consequently at most

$$
\log(W/S)+C
$$

with absolute $C$.

A positive denominator requires $W\ge e^{-C}S$. In that range, the numerical upper bound furnished by (10) is necessarily at least a constant times $S$, because

$$
\frac{W}{\log(W/S)+C}\gg S.
$$

The larger-sieve bound derived from the available residue restrictions cannot even yield a power saving over $S$. It therefore cannot contradict the required common-neighbor lower bound $S X^{-\kappa+o(1)}$.

The ordinary local sieve product also has the compatible exponent

For a polynomial cutoff $z=X^\xi$, the same exact forbidden-residue counts give

$$
\prod_{\ell\le z}\left(1-\frac{\nu_\ell}{\ell}\right)
\gg
\frac1{(\log T)^2}
\exp\left(
-(k+1)\sum_{T<\ell\le z}\frac1\ell
-O\left(k^2\sum_{\ell>T}\ell^{-2}\right)
\right).
$$

By Mertens' theorem,

$$
\boxed{
\prod_{\ell\le z}\left(1-\frac{\nu_\ell}{\ell}\right)
\ge X^{-\kappa+o(1)}.
}
\tag{11}
$$

This is a local product estimate, not an assertion that the actual simultaneous prime count has that asymptotic.

Nevertheless, it quantifies why merely increasing the constellation size does not create the proposed contradiction: congruence coalescence preserves enough local density to match the exponent of the graph lower bound.

To improve this mechanism, one would need information about the residues actually occupied by the common-neighbor primes, beyond those excluded by the simultaneous primality conditions.

7. Can multiplicative cancellation across cycles generate a twin?

There is an exact algebraic obstruction, independent of counting estimates.

For a connected bipartite component with prime vertex sets $\mathcal L,\mathcal R$, represent each shifted label $rs=p+2$ by its prime-exponent vector

$$
e_r+e_s.
$$

The integer lattice generated by all these edge vectors is precisely

$$
\left\{
x\in\mathbb Z^{\mathcal L\cup\mathcal R}:
\sum_{r\in\mathcal L}x_r
=
\sum_{s\in\mathcal R}x_s
\right\}.
\tag{12}
$$

To prove the reverse inclusion, alternating sums along even paths generate differences between any two vertices on the same side. Together with one edge vector, these generate every vector satisfying the displayed equality.

No individual prime-exponent vector lies in this lattice.

Even when components from different scales are combined, every edge has even total exponent sum. Therefore every integer obtained solely by multiplying and dividing these composite shifted labels has even Liouville parity.

No multiplicative combination of such edges can itself equal a prime.

Introducing the individual factor primes as additional generators removes that algebraic obstruction, but does not establish that any generated prime has a prime neighbor two below it.

An explicit actual-prime counterexample to automatic twin generation

The following rectangle consists entirely of genuine primes.

$r\backslash s$
 |
$983$
 |
$1223$
 |

$233$
 |
$229037$
 |
$284957$
 |

$263$
 |
$258527$
 |
$321647$
 |

Each entry is $rs-2$. All eight vertex and label primes were checked by exact trial division.

All four vertices are $23\bmod30$. Their neighbors two below are divisible by $3$, and their neighbors two above are divisible by $5$.

All four labels are $17\bmod30$. Their neighbors two below are divisible by $15$, and their neighbors two above are the composite products $rs$.

Thus none of the eight primes participates in a twin pair, despite the exact nondegenerate multiplicative rectangle and all eight primality conditions.

This does not refute an asymptotic contradiction using additional arithmetic information. It does refute any universal algebraic implication from the existence of such a rectangle to a twin among its vertices or labels.

Research conclusion

The multiplicative-relation approach has now produced three substantial, precisely scoped results:

-

The complete nontrivial multiplicative energy of the unbalanced Chen endpoints is $\Theta(X^2/\log^7X)$ under the finite-twins hypothesis.

-

The exact four-cycle local correction is $\prod_{\ell>2}(1+(\ell-2)^{-3})$, which favors rather than suppresses rectangles. The graph lower bound and the arithmetic main-term model are compatible even in leading order.

-

Growing common-neighbor constellations with $k\asymp\log X/\log\log X$ can be forced, but their congruence structure defeats the attempted larger-sieve contradiction.

The remaining opportunity would require a genuinely new additive–multiplicative correlation estimate connecting the composite product graph to prime values at its unit-factor boundary. Multiplicative energy, additional fixed cycles, larger admissible constellations and multiplicative cancellation do not supply that connection.

I would not invest further in counting larger versions of the same rectangles without a new arithmetic mechanism.

Verification and limitations: The local density calculations, global energy bounds, growing-tuple argument and lattice obstruction are internally derived. The finite example was independently checked computationally by trial division, not by an independent research worker. The comparison model is deliberately distinguished from actual prime labels. I have not established an optimal numerical upper constant for the actual rectangle count or ruled out every stronger arithmetic estimate. No project files were accessed or created, and no manuscript was produced.

The proposed contradiction has not established infinitude of twin primes.

---

## Confirm Twin Prime Proof

[Original conversation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6b05e53a-f038-83ee-99c9-ad2380de1583)

### Recovered response 1

1. Result of the external-prime-factor approach

The external-padding idea preserves the Möbius sign, but I found a stronger obstruction than the original auxiliary weights vanishing on primes: padding and subsequently switching prime factors can leave the Cauchy–Schwarz energy confined to the original integers, even when arbitrarily many auxiliary factors are introduced.

There is also a promising way to formulate the alternative hyperbola approach so that the prime endpoint vanishes exactly and only a selective, one-sided parity estimate is needed.

Source limitation: I confirmed the November 19, 2026 revision of Lü–Wang–Wu, arXiv:2610.20242v2, but its full text could not be retrieved. I could inspect the relevant determinant and auxiliary-weight arguments in the authors' October 14 v1 manuscript, including Sections 2.3 and 4.1–4.2. I therefore distinguish the following independent mathematical derivations from any unverified extension of v2.

arxiv.cnoctave.top+2

The original determinant and its padded replacement

Write $t=uv+2$ and $t'=rs+2$. With genuine selected divisors $a\mid t$ and $b\mid t'$, equality of the switched quotients gives

$$
\frac{uv+2}{a}=\frac{rs+2}{b}
$$

and therefore

$$
buv-ars=2(a-b).
\tag{1}
$$

The original proof uses this nontrivial determinant relation together with arithmetic restrictions on the selected primes.

Now introduce external squarefree factors $D_1,D_2$, coprime to their respective original integers. The proposed replacement gives

$$
\frac{D_1(uv+2)}a
=
\frac{D_2(rs+2)}b,
$$

hence

$$
bD_1uv-aD_2rs
=2(aD_2-bD_1).
\tag{2}
$$

Superficially, (2) looks sufficiently similar to (1). However, its arithmetic structure is different.

Let $\mathcal B$ be the union of the auxiliary prime blocks. Define

$$
C_{\mathcal B}(n)
=
\frac{n}{\displaystyle\prod_{q\in\mathcal B}q^{v_q(n)}}.
$$

This removes every prime-power factor belonging to the auxiliary blocks.

Whenever both $D$ and $a$ are composed entirely of primes in $\mathcal B$, and $a\mid Dt$, we have the exact invariant

$$
\boxed{
C_{\mathcal B}(Dt/a)=C_{\mathcal B}(t).
}
\tag{3}
$$

In particular, if $t$ has no prime factor in the blocks, its original value survives in the quotient.

Suppose $t,t'\in(X,2X+2]$ and $t$ is block-free. Equality of the padded quotients forces $C_{\mathcal B}(t')=t$. But $t'=t\ell$, where every prime factor of $\ell$ belongs to the blocks. If $\ell>1$, then $t'>2X+2$ for sufficiently large $X$.

Consequently,

$$
t=t'.
\tag{4}
$$

This remains true even if the second original integer is initially allowed to contain block primes.

For these block-free inputs, write $D_1=ae$ and $D_2=bf$. Equation (2) reduces to

$$
euv-frs=2(f-e).
$$

By (4), equality of the quotients also forces $e=f$. The effective determinant is therefore zero.

The fresh labels have not generated new arithmetic connections between distinct original integers.

2. Repair attempt: insert several primes in every block

One possible repair is to attach multiple external primes per block, then switch only some of them. This introduces many possible residual products $e=D/a$, rather than always returning the original integer.

The invariant (3) survives this modification. More importantly, there is an exact energy obstruction that accounts for all multiplicities.

Let $c_t$ be an original coefficient on a dyadic interval. Suppose that, after inserting and removing auxiliary primes, the new coefficient at a quotient $h$ is $F(h)$.

For a squarefree, block-free integer $t$, preservation of its original Möbius contribution requires

$$
\sum_e\mu(e)F(te)=c_t.
\tag{5}
$$

Indeed, $\mu(te)=\mu(t)\mu(e)$. Arbitrarily complicated multiplicities, selection probabilities and compensating signs can all be included in $F$.

Different block-free integers $t$ have disjoint quotient fibers by (3).

Let $H$ be the number of squarefree quotients on which $F$ is nonzero. Triangle and Cauchy–Schwarz inequalities give

$$
\begin{aligned}
\sum_{\substack{t\ \mathrm{squarefree}\\
t\ \mathrm{block\text{-}free}}}|c_t|
&\leq \sum_{\mu(h)\ne0}|F(h)|\\
&\leq
\sqrt{H\sum_{\mu(h)\ne0}|F(h)|^2}.
\end{aligned}
\tag{6}
$$

Thus padding can redistribute the original coefficient among more quotients, but the corresponding increase in quotient multiplicity offsets any reduction of its squared norm.

This is not merely a failure of one choice of padding probabilities. It holds for arbitrary coefficient-preserving allocations satisfying (5), including signed allocations and repeated selection procedures.

An arithmetic witness at the required scale

The obstruction in (6) occurs on genuine arithmetic inputs to a Vaughan Type II decomposition, not just an artificially chosen coefficient vector.

Take fixed $0<a<b<1/2$, for example $a=1/5,\ b=3/10$, and the coefficient

$$
c_t=
\sum_{\substack{uv=t-2\\X^a<u\le X^b\\v>V}}
\mu(u)R_Z(u)c_V(v)R_Z(v),
$$

where

$$
c_V(v)=\sum_{\substack{k\mid v\\k>V}}\Lambda(k)
$$

and the cutoffs satisfy $V<X^a$ and $Z=X^{o(1)}$. These are compatible Vaughan-type coefficients; I am not assuming they are v2's particular cutoff choices.

Consider the integers

$$
t=uv+2,\qquad X<uv\le2X,
$$

where $u,v$ are both genuine primes, $X^a<u\le X^b$, and $t$ is squarefree and block-free.

Since $v>X^{1-b}>u$, the factorization in this coefficient is unique. Hence

$$
c_t=-\log v.
\tag{7}
$$

I obtain unconditionally

$$
\boxed{
\sum_{\substack{t\ \mathrm{squarefree}\\
t\ \mathrm{block\text{-}free}}}|c_t|
\gg_{a,b,\mathcal B}X,
}
\tag{8}
$$

where the implied constant is uniform in $X$ when the number of source-style blocks and their exponents are fixed.

Derivation. Fix a genuine prime $u\in(X^a,X^b]$. For a block prime $q$, excluding $q\mid uv+2$ excludes precisely one reduced residue class for $v$ modulo $q$. Its prime-density cost is $1/(q-1)$.

Also exclude $q^2\mid uv+2$ for odd primes $q\le L^4$, where $L=\log X$. These cost $1/\varphi(q^2)$. For the subpower blocks used in v1, the two sets of primes are disjoint for large $X$.

Their total reciprocal-density cost is bounded:

$$
\sum_{q\in\mathcal B}\frac1{q-1}
+
\sum_{q>2}\frac1{\varphi(q^2)}
=O_K(1).
$$

The associated product of surviving densities is bounded below by a positive constant depending on the fixed number $K$ of blocks.

Apply inclusion–exclusion truncated at a sufficiently large fixed odd order. The products of the retained moduli are all $X^{o(1)}$. Bombieri–Vinogradov at the prime-variable scale $X/u\ge X^{1-b}$ controls the sum of progression errors uniformly in $u$. The omitted density terms are bounded by the tail of an exponential series, and the truncation order can be fixed to make that tail smaller than half the surviving density.

What's new

It follows that

$$
\sum_{\substack{X/u<v\le2X/u\\
v\ \mathrm{prime}\\
\text{retained restrictions}}}
\log v\gg_K \frac Xu.
$$

Summing over $u$ gives

$$
\gg_K X
\sum_{\substack{X^a<u\le X^b\\u\ \mathrm{prime}}}\frac1u
\sim c_KX\log(b/a).
$$

Finally, large square factors can be removed: the number of integers in the target interval divisible by a square $q^2$, with $q>L^4$, is

$$
O\left(\frac{X}{L^4}+\sqrt X\right).
$$

Because the selected semiprime factorizations are unique, removing these integers costs only $o(X)$ in logarithmic weight.

This proves (8).

Combining (6) and (8), every coefficient-preserving padding construction of the indicated kind satisfies

$$
\sqrt{H\sum_{\mu(h)\ne0}|F(h)|^2}
\gg X.
\tag{9}
$$

This rules out an $o(X)$ bound from that Cauchy–Schwarz quantity alone, and in particular rules out a uniform arbitrary-logarithmic-saving estimate of this kind.

It also survives approximate coefficient preservation if the total absolute recovery error on these fibers is $o(X)$.

Scope: this does not contradict Lü–Wang–Wu's original marked estimates. Their genuine marks do not include these block-free witnesses. Nor does (9) show that the actual signed Möbius sum is large. It establishes that the proposed external padding cannot create the needed cancellation through the quotient-energy mechanism alone.

3. Can the changed shift be repaired?

There are two natural repairs.

Retain the padded shift. Writing

$$
D(uv+2)=(Du)v+2D
$$

preserves a bilinear product but replaces the fixed shift $2$ by the variable shift $2D$. Even if $D=X^{o(1)}$, uniformity in these shifts requires additional arguments.

More fundamentally, the determinant degeneracy above remains exact.

Restore the shift to two. Writing

$$
D(uv+2)=\bigl(Duv+2(D-1)\bigr)+2
$$

restores the shift but loses the original factorization. For a nonunit subpower $D$ and polynomially large $u$,

$$
u\nmid 2(D-1).
$$

Thus the original $u$-row cannot be retained as a divisor of the transformed base integer. The same problem affects the other polynomially large factor.

The changed base integer might admit a different factorization, but transferring the original Möbius and Vaughan coefficients to that factorization would require a new arithmetic identity.

Neither repair closes the argument.

4. A selective parity criterion with the prime endpoint removed exactly

The second idea in your assignment admits a cleaner sufficient implication.

Here the short part of the argument can be evaluated unconditionally, including the squarefree restrictions and their shared factors.

Define

$$
\mathfrak S
=
2\prod_{q>2}
\left(1-\frac1{(q-1)^2}\right),
$$

where the product is over primes, and let

$$
T(X)=
\sum_{\substack{X<p\le2X\\p,\ p+2\ \mathrm{prime}}}
\log p\log(p+2).
$$

Fix $0<\theta<1/2$, and set $D=X^\theta$.

Because $\mu^2(n)\Lambda(n)$ equals $\log n$ on primes and vanishes on every composite, the exact convolution identity gives

$$
T(X)=
\sum_{X<p\le2X}
\log p\,\mu^2(p+2)
\sum_{dm=p+2}\mu(d)\log m.
\tag{10}
$$

Split the inner sum at $d=D$:

$$
T(X)=I_D(X)+R_D(X).
$$

The short-divisor part is

$$
I_D(X)=
\sum_{X<p\le2X}\log p\,\mu^2(p+2)
\sum_{\substack{d\mid p+2\\d\le D}}
\mu(d)\log\frac{p+2}{d}.
$$

The long-divisor part can be written as

$$
R_D(X)=
\sum_{\substack{X<p\le2X\\m\mid p+2\\
1<m<(p+2)/D}}
\log p\,\mu^2(p+2)
\mu\left(\frac{p+2}{m}\right)\log m.
\tag{11}
$$

The unit $m=1$ is absent because its coefficient is exactly zero.

In particular, $R_D(X)$ vanishes on every genuine twin pair in the interval.

Unconditional evaluation of the short part

I obtain

$$
\boxed{I_D(X)=\mathfrak S X+o(X).}
\tag{12}
$$

Here is the proof.

Put

$$
A_2=\prod_{q>2}\left(1-\frac1{q(q-1)}\right)
$$

and, for odd squarefree $d$, define the multiplicative local density $g$ by

$$
g(q)=
\frac{1/q}{1-1/[q(q-1)]}.
$$

The squarefree prime-progression density for $d\mid p+2$ is then $A_2g(d)$.

To see the local factor, requiring $q\mid p+2$ but $q^2\nmid p+2$ costs

$$
\frac1{\varphi(q)}-\frac1{\varphi(q^2)}
=\frac1q.
$$

This accounts for the overlap between the squarefree condition and the divisor $d$; treating them as independent would give an incorrect constant.

Expand the squarefree indicator:

$$
\mu^2(p+2)=\sum_{e^2\mid p+2}\mu(e).
$$

Truncate at $e\le E=L^{20}$. The discarded contribution is bounded by

$$
O\left(
L^2\sum_{n\le3X}\tau(n)
\sum_{\substack{e>E\\e^2\mid n}}1
\right).
$$

Writing the second inner sum as $\rho_E(n)$, we have

$$
\sum_{n\le3X}\rho_E(n)^2
\le
3X\sum_{e,f>E}\frac1{[e,f]^2}
\ll \frac XE.
$$

The last estimate follows by writing $e=ga,f=gb$, splitting the sum at $g=E$, and bounding the reciprocal-square tails. Together with

$$
\sum_{n\le3X}\tau(n)^2\ll XL^3,
$$

Cauchy–Schwarz gives a truncation error

$$
O\left(XL^{7/2}E^{-1/2}\right)=o(X).
$$

For the retained terms the progression moduli are exactly

$$
[d,e^2]\le DE^2=X^\theta L^{40}.
$$

This remains strictly below the square-root distribution level. Their multiplicities are divisor-bounded, which can be absorbed using divisor moments and Bombieri–Vinogradov with sufficiently strong fixed logarithmic precision.

Restoring the full principal squarefree sum is also justified: for squarefree $d,e$,

$$
\frac1{\varphi([d,e^2])}
=
\frac1{\varphi(e^2)\varphi(d/(d,e))}.
$$

Consequently the principal tail summed over $d\le D,e>E$ is

$$
\ll \log(2D)
\sum_{e>E}\frac{\tau(e)}{\varphi(e^2)}
\ll \frac{\log(2D)}{\sqrt E}.
$$

Partial summation now gives

$$
\begin{aligned}
I_D(X)
={}&A_2\sum_{\substack{d\le D\\d\ \mathrm{odd}}}
\mu(d)g(d)
\int_X^{2X}\log\frac{t+2}{d}\,dt\\
&+o(X).
\end{aligned}
\tag{13}
$$

It remains to calculate the two Möbius moments. Introduce

$$
F(s)=A_2\prod_{q>2}(1-g(q)q^{-s}).
$$

Factor out $\zeta(1+s)^{-1}$. The remaining Euler product converges around $s=0$, and

$$
F(0)=0.
$$

Moreover,

$$
\begin{aligned}
F'(0)
&=2A_2\prod_{q>2}
\frac{1-g(q)}{1-1/q}\\
&=2\prod_{q>2}\frac{q(q-2)}{(q-1)^2}\\
&=\mathfrak S.
\end{aligned}
$$

These Euler identities yield the requisite truncated moments with sufficiently small errors, not merely formal identities at the boundary of convergence.

For justification, the coefficients $\mu(d)d g(d)$, restricted to odd $d$, are the convolution of $\mu$ with a multiplicative function whose absolute Dirichlet series converges at $1/2$. At odd prime powers, the latter function has value $1-qg(q)=O(q^{-2})$. Classical quantitative Möbius cancellation and partial summation therefore give

$$
A_2\sum_{d\le D,\ d\ \mathrm{odd}}\mu(d)g(d)
=o(1/L)
$$

and

$$
A_2\sum_{d\le D,\ d\ \mathrm{odd}}
\mu(d)g(d)\log d
=-\mathfrak S+o(1).
$$

Substitution into (13) proves (12).

5. The precise remaining estimate

We now have the unconditional reduction

$$
\boxed{
T(X)=\mathfrak S X+R_D(X)+o(X).
}
\tag{14}
$$

Sufficient implication. It is enough to prove, for some fixed $\eta>0$,

$$
\boxed{
R_D(X)\ge-(\mathfrak S-\eta)X
}
\tag{15}
$$

along an unbounded sequence of $X$.

Equation (14) would then give $T(X)\ge \eta X/2$ on sufficiently large members of that sequence. This forces an actual twin pair beyond every prescribed bound.

Notice that full cancellation $R_D(X)=o(X)$ is unnecessary.

For squarefree $n$,

$$
\mu(n/m)=\mu(n)\mu(m).
$$

Therefore the missing expression is equivalently

$$
R_D(X)=
\sum_{X<p\le2X}
\log p\,\mu(p+2)H_D(p+2),
$$

where

$$
H_D(n)=
\sum_{\substack{m\mid n\\1<m<n/D}}
\mu(m)\log m.
\tag{16}
$$

Nonsquarefree integers automatically contribute zero through $\mu(p+2)$.

This is a selective parity correlation: it measures the association of the Möbius sign with a particular truncated divisor statistic.

The distinction matters because Lü–Wang–Wu's headline cancellation estimate does not give cancellation against $H_D$.

The cofactor-switching version

Rearranging (11) instead gives

$$
R_D(X)=
\sum_{\substack{2\le m\le(2X+2)/D\\m\ \mathrm{odd}}}
\mu^2(m)\log m\,B_X(m),
$$

where

$$
B_X(m)=
\sum_{\substack{d>D,\ (d,m)=1\\
X<md-2\le2X\\md-2\ \mathrm{prime}}}
\mu(d)\log(md-2).
\tag{17}
$$

There is a limited but useful algebraic repair here.

For a fixed $m$, opening the prime coefficient through Vaughan and switching genuine auxiliary divisors $a,b$ of the long cofactor produces

$$
\frac{uv+2}{ma}=\frac{rs+2}{mb}.
$$

The common $m$ cancels, leaving precisely determinant (1). Thus the original determinant geometry need not be abandoned for a fixed cofactor. The additional congruence and coprimality restrictions still require verification in the analytic estimates.

For two different cofactors $m_1,m_2$, however, the relation becomes

$$
bm_2uv-am_1rs=2(am_1-bm_2).
$$

The effective labels now contain the potentially polynomial-sized cofactors. The original subpower-label and shared-factor estimates cannot simply be transferred.

This suggests working directly on (17), exploiting the exact $\log m$ coefficient, rather than padding the target integer.

One quantitatively sufficient, though stronger than necessary, estimate would be

$$
|B_X(m)|
\le
\varepsilon(X)\frac{X}{\varphi(m)L^2},
\qquad \varepsilon(X)\longrightarrow0,
$$

uniformly over the retained squarefree odd cofactors. Indeed,

$$
\sum_{m\le 3X/D}\frac{\log m}{\varphi(m)}
\ll L^2,
$$

so this would give $R_D(X)=o(X)$.

The better research target is the one-sided aggregate (15), rather than demanding this stronger uniform estimate.

6. Research verdict

Two concrete results survive the calculation:

Result
 |
Status
 |

External-prime padding preserves Möbius signs
 |
Proved
 |

Padding preserves the block-free core and cannot create cross-core quotient collisions
 |
Proved
 |

Multiplicity-adjusted energy obstruction on Vaughan-type arithmetic inputs
 |
Proved
 |

Squarefree hyperbola short main $\mathfrak S X+o(X)$
 |
Proved using classical inputs
 |

Fixed-cofactor determinant preservation
 |
Proved algebraically
 |

Selective parity bound (15)
 |
Unproved
 |

Infinitely many twin primes
 |
Not established
 |

The most useful next mathematical direction is genuine internal factor switching on the long cofactor in (17), with the short cofactor retained as an arithmetic variable. Its advantage is that the unit coefficient vanishes and the required final inequality is only one-sided.

The external-padding obstruction is exact; overcoming it would require a mechanism that uses the actual Möbius signs across different block-free cores, not merely more auxiliary labels.

I have not independently verified the revised v2 analytic proof because its full text was inaccessible. I used no private research records, wrote no files, and contacted no third parties. The derivations above are independent calculations, with no claim of established novelty or a completed twin-prime proof.

---

### Recovered response 2

1. Evaluate the signed first moment before applying Cauchy–Schwarz

The small-resultant observation is correct. I tested it in a genuine midpoint bank, keeping the complete signed hyperbola coefficient rather than estimating its individual divisor terms.

The calculation below establishes two things: the entire nonrough contribution can be priced to arbitrarily small additive error, and the remaining rough contribution has substantial positive off-diagonal energy despite the pairwise coprimality of its four endpoints.

This does not establish the desired strict twin-prime lower bound, but it identifies more precisely where a new arithmetic saving is required.

Put $L=\log X$. Restrict the bank temporarily to genuine primes

$$
\mathcal B_R=\{r:R<r\le2R\},
\qquad R=\exp(L^{1/10}),
$$

and normalize by

$$
S_R=\sum_{r\in\mathcal B_R}\frac1{r-2}
\sim\frac{\log2}{\log R}.
$$

The dyadic restriction is necessary for meaningful common-$j$ switching: two labels contributing at the same $j$, with both midpoints in $(X,2X]$, must be comparable in size.

Let $\vartheta(n)=1_{n\text{ prime}}\log n$. Choose a sufficiently small fixed $\delta>0$, set $D=X^\delta$, and define

$$
B_D(n)=
\sum_{\substack{d\mid n\\d\le D}}
\mu(d)\log(n/d).
$$

The exact signed long-divisor coefficient is

$$
C_D(n)=\Lambda(n)-B_D(n).
$$

This retains every term of the hyperbola decomposition, including its signs. In particular, $C_D(n)=0$ on primes $n>D$.

Define the weighted prime-pair sum

$$
T_R=
\frac1{S_R}\sum_{r\in\mathcal B_R}
\sum_{X<rj\le2X}
\vartheta(rj-1)\Lambda(rj+1).
$$

As in the preceding calculation, the short-divisor main term is

$$
\frac1{S_R}\sum_{r,j}
\vartheta(rj-1)B_D(rj+1)
=\mathfrak S X+o(X),
$$

where

$$
\mathfrak S=
2\prod_{q>2}\left(1-\frac1{(q-1)^2}\right).
$$

This remains valid for the present dyadic bank even though $S_R\to0$: its reciprocal is only $O(L^{1/10})$, which is absorbed by the arbitrary logarithmic precision of Bombieri–Vinogradov.

Consequently, the complete signed remainder satisfies

$$
T_R=\mathfrak S X+\mathcal R_R+o(X).
\tag{1}
$$

Exact separation at the roughness boundary

Let

$$
A_R=
\frac1{S_R}\sum_{r,j}
\vartheta(rj-1)\log(rj+1)
1_{\{P^-(rj+1)>D\}}.
$$

On this rough population, $B_D(rj+1)=\log(rj+1)$ exactly. On the complementary population, $\Lambda(rj+1)$ is zero except for proper prime powers.

Those prime powers have negligible weighted mass: the bank multiplicity is at most $O(L)$, there are $O(\sqrt X L)$ proper powers in the interval, and $S_R^{-1}$ is polylogarithmic.

Therefore the signed remainder splits as

$$
\boxed{
\begin{aligned}
\mathcal R_{\rm rough}&=T_R-A_R+o(X),\\
\mathcal R_{\rm nonrough}&=A_R-\mathfrak S X+o(X).
\end{aligned}
}
\tag{2}
$$

These are complete signed identities. In particular, the second line does not require knowing the twin count.

This separation avoids attempting to estimate the numerous positive and negative nonrough divisor terms individually.

2. A complete signed evaluation of the nonrough region

The quantity $A_R$ admits the following arbitrarily accurate evaluation in the ordered limits $X\to\infty$, followed by $\delta\downarrow0$:

$$
\boxed{
\frac{A_R}{X}
=
\frac{\mathfrak S e^{-\gamma}}{\delta}
+O\left(\frac{\epsilon_\delta}{\delta}\right)
+o_\delta(1),
\qquad
\frac{\epsilon_\delta}{\delta}\longrightarrow0.
}
\tag{3}
$$

Here $\gamma$ is Euler's constant. The final term tends to zero as $X\to\infty$ with $\delta$ fixed.

The error can be taken exponentially small in $\delta^{-1}\log(1/\delta)$.

Proof and distribution level

For fixed $r$, write $p=rj-1$. The roughness condition excludes $p\equiv-2\pmod q$ for each odd prime $q\le D$, except $q=r$, which is already impossible.

The local sieve density on the prime source is

$$
g(q)=\frac1{q-1}.
$$

Partition the sieving primes into blocks

$$
D^{2^{-(i+1)}}<q\le D^{2^{-i}}.
$$

Each block has bounded total $g(q)$, uniformly in $X$. Truncate its inclusion–exclusion at consecutive even and odd orders $K+2i$ and $K+2i+1$.

If $U_i,L_i$ are these upper and lower polynomials, and $J_i$ is the exact block-survivor indicator, then

$$
\prod_iU_i-\sum_i(U_i-L_i)\prod_{h\ne i}U_h
\le\prod_iJ_i\le\prod_iU_i.
$$

The total relative principal error is bounded by

$$
\epsilon_K
\ll
\sum_{i\ge0}
\frac{C^{K+2i+1}}{(K+2i+1)!}
\le \exp(-cK\log K)
$$

for sufficiently large $K$.

All opened divisor moduli have size at most

$$
D^{2K+6}.
$$

Choose $K$ even and of size $1/(20\delta)$. The full progression modulus, including $r$, is then at most

$$
rD^{2K+6}
\le X^{1/10+6\delta+o(1)}.
$$

This leaves substantial Bombieri–Vinogradov margin. The modulus multiplicities are divisor-bounded, with an additional $O(\log L)$ factor from the lower polynomial; the usual divisor-moment Cauchy bound absorbs these losses.

The principal density is

$$
\prod_{\substack{3\le q\le D\\q\ne r}}
\left(1-\frac1{q-1}\right)
=
\frac{\mathfrak S e^{-\gamma}}{\delta L}
\frac{r-1}{r-2}(1+o_\delta(1)).
$$

Multiplying by the prime progression denominator $1/(r-1)$, the endpoint logarithm $L+O(1)$, and summing over $r$, gives (3).

All parameters are fixed before the limit in $X$. No moving-polynomial-cutoff uniformity is assumed.

Combining (2) and (3), I obtain

$$
\boxed{
\frac{\mathcal R_{\rm nonrough}}X
=
\frac{\mathfrak S e^{-\gamma}}{\delta}
-\mathfrak S
+O\left(\frac{\epsilon_\delta}{\delta}\right)
+o_\delta(1).
}
\tag{4}
$$

For any prescribed additive tolerance, choose $\delta$ sufficiently small and then let $X$ grow.

This is an evaluation of the whole signed nonrough first moment, not an estimate of its absolute variation.

It also shows why the rough component cannot simply be estimated by a relative-error argument: its leading magnitude grows like $X/\delta$, whereas the twin-prime reserve needed after cancellation is only a fixed multiple of $X$.

3. The off-diagonal energy is genuinely present on pairwise-coprime endpoints

Define the recombined, nonnegative rough-composite coefficient

$$
G_r(j)=
\vartheta(rj-1)
\bigl[\log(rj+1)-\Lambda(rj+1)\bigr]
1_{\{P^-(rj+1)>D\}},
$$

with the original window $X<rj\le2X$ understood.

This is exactly the negative of the signed rough hyperbola coefficient. It is zero on genuine twin pairs and positive on composite right endpoints.

For sufficiently large $X$, whenever $G_r(j)G_s(j)>0$ with $r\ne s$, all four integers

$$
rj-1,\quad rj+1,\quad sj-1,\quad sj+1
$$

are pairwise coprime.

Indeed, the cross gcds divide $r-s$ or $r+s$; any prime dividing these resultants is at most $4R<D$. The same-label gcds divide $2$, and the endpoints are odd.

Thus the following estimates concern precisely the coprime arithmetic population in your proposed argument.

First moment

The elementary two-form upper sieve gives

$$
0\le T_R\ll X
$$

with an absolute constant independent of $\delta$. The bound follows by sieving $rj-1,rj+1$ through a sufficiently small fixed polynomial cutoff, uniformly for $r\in\mathcal B_R$. The exceptional local factor at the prime $r$ is bounded.

By (3), taking $\delta$ sufficiently small ensures $A_R$ is much larger than this upper bound.

Therefore

$$
\begin{aligned}
G&:=\sum_{r,j}G_r(j)\\
&=S_R(A_R-T_R)+o(XS_R)\\
&\asymp_\delta \frac{X}{\log R}.
\end{aligned}
\tag{5}
$$

The positive lower bound here is unconditional. It is not derived by assuming that there are finitely many twins.

Diagonal

Put

$$
E_{\rm diag}=\sum_{r,j}G_r(j)^2.
$$

On every nonzero term, the first endpoint is prime and the second composite. Even if the second endpoint is a proper prime power, its von Mangoldt weight is at most half its logarithm.

Consequently, every nonzero $G_r(j)$ is between two fixed positive multiples of $L^2$. By (5),

$$
\boxed{
E_{\rm diag}\asymp_\delta
\frac{XL^2}{\log R}.
}
\tag{6}
$$

Off-diagonal

Let

$$
g(j)=\sum_{r\in\mathcal B_R}G_r(j).
$$

All nonzero $g(j)$ lie in

$$
\frac{X}{2R}<j\le\frac{2X}{R}.
$$

There are $O(X/R)$ such integers. Cauchy–Schwarz, now applied after the signed first-moment recombination, gives

$$
\sum_jg(j)^2
\gg_\delta \frac{XR}{(\log R)^2}.
$$

Subtracting the exact diagonal estimate (6),

$$
\boxed{
E_{\rm off}:=
\sum_j\sum_{\substack{r,s\in\mathcal B_R\\r\ne s}}
G_r(j)G_s(j)
\gg_\delta \frac{XR}{(\log R)^2}.
}
\tag{7}
$$

The diagonal is smaller by a factor of order

$$
\frac{L^2\log R}{R}=o(1).
$$

Every term in (7) comes from four pairwise-coprime endpoints. This is a positive lower bound for the actual signed rough-remainder cross products, because both signed row coefficients are negative.

Coprimality has not generated cancellation.

Matching upper bound

The order of magnitude in (7) is also an upper bound.

For fixed distinct $r,s$, upper-sieve the four forms $rj\pm1,sj\pm1$. At every prime $q\ge5$ not dividing $rs(r-s)(r+s)$, there are exactly four forbidden residues. At exceptional primes there are two.

The same elementary block upper sieve used above therefore gives the uniform bound

$$
\#\{\text{four rough endpoints}\}
\ll_\delta
\frac{X}{RL^4}f(r-s)f(r+s),
$$

where

$$
f(n)=\prod_{\substack{q\mid n\\q\ge5}}
(1+10/q).
$$

The factor $10$ is sufficient because the ratio of the two-root and four-root local densities is

$$
\frac{q-2}{q-4}\le1+\frac{10}{q}.
$$

To average these factors, expand

$$
f(n)^2=\sum_{d\mid n}h(d),
$$

where $h$ is supported on squarefree integers with

$$
h(q)=20/q+100/q^2.
$$

For $d\le R^{1/3}$, Bombieri–Vinogradov at scale $R$, applied to the prime label $s$ in the reduced residue classes $s\equiv\pm r\pmod d$, controls the average. The main Euler series

$$
\sum_d\frac{h(d)}{\varphi(d)}
$$

converges, and $h(d)$ is uniformly bounded. For $d>R^{1/3}$, the divisor tail on each nonzero integer $r\pm s=O(R)$ is $R^{-1/3+o(1)}$.

It follows that

$$
\sum_{r\ne s}f(r-s)f(r+s)
\ll \frac{R^2}{(\log R)^2}.
$$

Multiplying the four-form count by the bound $G_rG_s\ll L^4$ proves

$$
\boxed{
E_{\rm off}\asymp_\delta
\frac{XR}{(\log R)^2}.
}
\tag{8}
$$

No asymptotic for four prime forms, and no independence assumption, enters this argument.

4. A strict quantitative obstruction to the uncentered energy method

The preceding estimates show that a logarithmic saving on the complete off-diagonal is impossible. I then tested whether its correct-order constant might nevertheless suffice for a strict twin lower bound.

There is an additional local obstruction, even after restricting to $6\mid j$.

Every nonzero $G_r(j)$ has $6\mid j$. Let $J_6$ be the number of multiples of six in the common quotient interval $(X/(2R),2X/R]$.

Consider the portion with $5\mid j$.

For the actual rough first moment $A_R$, imposing $5\mid j$ replaces the prime progression modulus $r$ by $5r$ and removes the need to sieve the right endpoint at $5$.

The net density factor is exactly

$$
\frac1{\varphi(5)}
\left(1-\frac1{\varphi(5)}\right)^{-1}
=\frac13.
$$

Thus the same signed-first-moment calculation proves

$$
A_R[5\mid j]
=\frac13 A_R+
O\left(\frac{\epsilon_\delta}{\delta}X\right)
+o_\delta(X).
$$

Since $T_R\ll X$ but $A_R\asymp X/\delta$, the fraction $u$ of the actual rough-composite mass $G$ lying on $5\mid j$ satisfies

$$
u=\frac13+O(\delta+\epsilon_\delta)+o_\delta(1).
\tag{9}
$$

Only one fifth of the eligible quotient positions are divisible by five.

Applying Cauchy–Schwarz separately to the two classes gives

$$
\begin{aligned}
\frac{J_6\sum_jg(j)^2}{G^2}
&\ge5u^2+\frac54(1-u)^2+o(1)\\
&=1+\frac{25}{4}(u-1/5)^2+o(1).
\end{aligned}
$$

By (9), this is at least

$$
\boxed{
\frac{10}{9}-O(\delta+\epsilon_\delta)-o_\delta(1).
}
\tag{10}
$$

This extra factor is a lower bound on the actual energy, not a loss introduced by a crude estimate.

Propagation to the twin count

The uncentered common-$j$ method would give the lower bound

$$
T_R\ge
A_R-\frac{\sqrt{J_6\sum_jg(j)^2}}{S_R}+o(X).
\tag{11}
$$

But (10), together with $T_R/A_R=O(\delta)$, implies that, for sufficiently small fixed $\delta$,

$$
\frac{\sqrt{J_6\sum_jg(j)^2}}{S_R}
\ge (1+c)A_R
$$

for an absolute $c>0$.

For example, any fixed $c<\sqrt{10/9}-1$ works once $\delta$ is sufficiently small.

Even knowing the exact uncentered energy would therefore not make (11) positive.

Moreover, the diagonal's contribution to the normalized Cauchy budget is only

$$
\frac{\sqrt{J_6E_{\rm diag}}}{S_R}
\asymp_\delta
XL\sqrt{\frac{\log R}{R}}
=o(X).
$$

The excess resides in the genuine off-diagonal, not in a diagonal term that can be isolated and discarded.

Repair using local-density weights

The factor $10/9$ can be addressed by using the correct relative local weights at five:

$$
v(j)=
\begin{cases}
5/3,&5\mid j,\\
5/6,&5\nmid j.
\end{cases}
$$

Apply weighted Cauchy–Schwarz with $\sum v(j)$ and $\sum g(j)^2/v(j)$.

However, the same argument at seven survives this repair. More generally, for any fixed positive periodic weight $v$ with period $M$, choose a prime $q\ge5$ not dividing $6M$.

By CRT, a fraction $1/q+o(1)$ of the total weight $v$ is on $q\mid j$. But the arithmetic rough-composite mass fraction is

$$
\frac1{q-2}+O_q(\delta+\epsilon_\delta)+o_\delta(1).
$$

Weighted Cauchy–Schwarz therefore has a squared excess factor at least

$$
\boxed{
1+\frac{4}{(q-1)(q-2)^2}
-O_q(\delta+\epsilon_\delta)-o_\delta(1).
}
\tag{12}
$$

For every fixed periodic local correction, taking $\delta$ sufficiently small again makes the uncentered Cauchy budget exceed $A_R$.

This does not exclude growing-period corrections or a genuinely centered signed energy argument. It does rule out a fixed finite collection of local corrections as a repair of this particular uncentered method.

5. A more promising repair: compute the complete signed principal term

Instead of estimating the uncentered energy, I tested the signed first moment against the uniform divisibility principal term, retaining the polynomial roughness restriction.

For $n\asymp X$, define

$$
M_\delta(n)=
\sum_{\substack{d\le n\\P^-(d)>D}}
\frac{\mu(d)}d\log(n/d),
\qquad D=X^\delta.
$$

The divisor $d=1$ is included.

On $D$-rough integers, the exact difference between the genuine von Mangoldt coefficient and this principal term is

$$
\Lambda(n)-M_\delta(n)=
\sum_{\substack{d\le n\\P^-(d)>D}}
\mu(d)\log(n/d)
\left(1_{d\mid n}-\frac1d\right).
\tag{13}
$$

New calculation: the full principal term can be evaluated, including the alternating signs of every factor rank. It predicts the correct positive twin-prime main term.

Evaluation of the alternating integral

Mertens' prime harmonic theorem gives, uniformly for $n\in[X,2X+1]$,

$$
\frac{M_\delta(n)}L
=J(\delta)+o_\delta(1),
$$

where

$$
J(\delta)=
\sum_{k=0}^{\lfloor1/\delta\rfloor}
\frac{(-1)^k}{k!}
\int_{\substack{x_i\ge\delta\\\sum x_i\le1}}
\left(1-\sum_i x_i\right)
\prod_i\frac{dx_i}{x_i}.
$$

The $k=0$ term is one. This is the full signed integral, not an absolute-value approximation.

The number of prime factors is bounded at fixed $\delta$, and repeated-prime diagonals have vanishing harmonic mass. These facts justify the limiting integral.

Replace the upper simplex boundary $1$ by $t$, and denote the resulting function by $J_\delta(t)$. Its Laplace transform is

$$
\int_0^\infty e^{-st}J_\delta(t)\,dt
=
\frac1{s^2}
\exp\left(-\int_\delta^\infty\frac{e^{-su}}u\,du\right).
$$

Using the elementary exponential-integral identity, this becomes

$$
\frac{e^\gamma\delta}{s}
\exp\left(\int_0^\delta
\frac{e^{-su}-1}{u}\,du\right).
$$

The exponential factor is the Laplace transform of a nonnegative random variable $Z_\delta$. One explicit construction uses independent Poisson point processes on the intervals

$$
(\delta2^{-i-1},\delta2^{-i}],
$$

each with intensity measure $du/u$, and sums all their point locations.

The sum converges almost surely because its expectation is $\delta$.

Uniqueness of Laplace transforms gives the exact integral identity

$$
\boxed{
J(\delta)=e^\gamma\delta\,
\mathbb P(Z_\delta\le1).
}
\tag{14}
$$

Exponential Markov bounds, with parameter $\log(1/\delta)/(2\delta)$, give

$$
\mathbb P(Z_\delta>1)
\le \exp\left(-c\delta^{-1}\log(1/\delta)\right)
$$

for sufficiently small $\delta$.

Consequently,

$$
J(\delta)=e^\gamma\delta(1-o_\delta(1)).
$$

Combining this with (3),

$$
\boxed{
\frac1{S_R}\sum_{r,j}
\vartheta(rj-1)
1_{\{P^-(rj+1)>D\}}M_\delta(rj+1)
=
\mathfrak S X+o_\delta(X)+o_{X;\delta}(X).
}
\tag{15}
$$

The notation distinguishes the error made small by choosing $\delta$ from the error tending to zero in $X$ afterward.

Thus the complete signed principal term does have the right value. The question is whether the true divisibility discrepancies in (13) can cancel that positive term.

A genuine portion of the discrepancy can be removed

I can control the entire range $d\le X^{1/3}$ in (13), including the roughness restriction.

For $D$-rough $d$, the prime-source congruences are

$$
p\equiv-1\pmod r,\qquad
p\equiv-2\pmod d.
$$

The rough sieve introduces another divisor $e\le D^{2K+6}$, coprime to $d$. Hence the complete progression modulus is bounded by

$$
rde\le
X^{1/3+1/10+6\delta+o(1)}
<X^{1/2}
$$

for sufficiently small $\delta$.

Bombieri–Vinogradov therefore prices the opened congruences. This uses its classical averaged distribution theorem, not an unproved extension to large moduli.

londmathsoc.onlinelibrary.wiley.com

The roughness sieve has relative error $O(\epsilon_\delta)$. Summing that error with the signed divisor coefficients costs at most

$$
\sum_{\substack{d\le X^{1/3}\\P^-(d)>D}}
\frac{|\mu(d)|}{\varphi(d)}
\ll \delta^{-1},
$$

by the finite Euler product. Moreover, replacing $1/\varphi(d)$ by $1/d$ has negligible relative error, since every prime factor of $d$ exceeds $D$.

Consequently the full contribution from $d\le X^{1/3}$ to the signed discrepancy (13), in the normalized midpoint sum, is

$$
O\left(\frac{\epsilon_\delta}{\delta^2}X\right)
+o_{X;\delta}(X).
\tag{16}
$$

This tends to zero relative to $X$ in the stated ordered limits.

The resulting precise sufficient target is now

$$
\begin{aligned}
\Delta_{\rm long}(X)=\frac1{S_R}
\sum_{r,j}&\vartheta(rj-1)
1_{\{P^-(rj+1)>D\}}\\
{}\times&
\sum_{\substack{X^{1/3}<d\le rj+1\\P^-(d)>D}}
\mu(d)\log\frac{rj+1}{d}
\left(1_{d\mid rj+1}-\frac1d\right).
\end{aligned}
$$

The preceding unconditional calculations yield

$$
\boxed{
T_R=\mathfrak S X+\Delta_{\rm long}(X)
+o_\delta(X)+o_{X;\delta}(X).
}
\tag{17}
$$

Proving, for some fixed $\eta>0$,

$$
\Delta_{\rm long}(X)\ge-(\mathfrak S-\eta)X
$$

along an unbounded sequence would suffice, after selecting $\delta$ with errors smaller than the reserve.

This is the signed first-moment target with its complete principal term and the accessible modulus range already accounted for.

6. Testing reciprocal switching on the remaining long divisors

For distinct labels $r,s$, open genuine divisor equations

$$
rj+1=dk,\qquad sj+1=e\ell.
$$

On the rough support, $(d,e)=1$, and the determinant is

$$
sdk-re\ell=s-r.
$$

Solving for $k$ gives the compatible congruences

$$
k\equiv\bar d\pmod r,
\qquad
k\equiv(s-r)\overline{sd}\pmod e.
$$

The combined modulus is $re$. Equivalently, the common quotient $j$ is in one residue class modulo $de$.

This gives an exact reciprocal-phase representation. Writing $\mathrm e_q(a)=\exp(2\pi ia/q)$, the CRT phase in the $k$-variable is

$$
\mathrm e_r(h\overline{de})\,
\mathrm e_e\bigl(h(s-r)\overline{rsd}\bigr).
\tag{18}
$$

The small resultant is genuinely useful here: the numerator $s-r$ is subpower, and the first factor has subpower modulus.

However, the denominator of the second factor remains the long divisor $e$.

Quantitative test against an established reciprocal-sum theorem

I checked Theorem 1 of Bettin–Chandee, Trilinear forms with Kloosterman fractions, including its coefficient and frequency dependence.

arxiv.org

First test the simpler problem with a smooth common-$j$ window and bounded, separate divisor coefficients, omitting the prime-supported endpoint weights.

For $d\asymp M,\ e\asymp N$, write $J\asymp X/R$ for the quotient length. Poisson summation has prefactor $J/(MN)$ and effective nonzero-frequency length

$$
H\asymp MN/J
$$

when $MN\ge J$.

The three coefficient norms have sizes at most $\sqrt M,\sqrt N,\sqrt H$. The subpower factors in (18) can be handled by residue splitting and the sparse row $rsd$, at cost $X^{o(1)}$.

The resulting nonzero-frequency bound is

$$
X^\varepsilon
\left[
J^{3/20}(MN)^{7/10}(M+N)^{1/4}
+
(MN)^{7/8}(M+N)^{1/8}
\right].
\tag{19}
$$

On the balanced scale $M=N=X^a$, its two exponents in $X$ are

$$
\frac3{20}+\frac{33a}{20},
\qquad
\frac{15a}{8}.
$$

Long-divisor exponent $a$
 |
First exponent
 |
Second exponent
 |

0.50
 |
0.975
 |
0.9375
 |

0.51
 |
0.9915
 |
0.95625
 |

0.60
 |
1.14
 |
1.125
 |

0.85
 |
1.5525
 |
1.59375
 |

This gives a genuine power saving in the simplified smooth problem for

$$
\frac12\le a<\frac{17}{33}.
$$

It does not cover the larger-divisor range.

More importantly, (19) cannot be transferred directly to the actual prime-supported correlation. Its coefficients after Fourier expansion include the exponential sums of

$$
\vartheta(rj-1)\vartheta(sj-1)
$$

with the two roughness restrictions. They are not the separate coefficient vectors required by the trilinear theorem.

The large-lcm range occurs on actual arithmetic inputs

This is not merely an inconvenient possible parameter range.

Using the earlier prime-progression lower sieve, select a genuine prime factor

$$
X^{1/10}<k\le X^{3/20}
$$

of the rough, squarefree composite endpoint $rj+1$.

The selected prime progression has modulus $rk$, and the rough sieve retains the same level margin. The total number of these witnessed rows is

$$
\gg_\delta \frac{X}{L^2\log R}.
$$

The bounded multiplicity of the selected factor is harmless.

Cauchy–Schwarz on the common $j$-positions, followed by removal of the diagonal, therefore gives

$$
\gg_\delta\frac{XR}{L^4(\log R)^2}
$$

ordered distinct-label coincidences of such actual rows.

For each coincidence choose the corresponding genuine long cofactors $d,e$. They satisfy

$$
d,e>X^{17/20},\qquad (d,e)=1,
$$

and hence

$$
\boxed{[d,e]=de>X^{17/10}.}
$$

The quotient interval has length only $X^{1-o(1)}$.

Thus the small resultant removes shared factors but leaves a modulus vastly larger than the available interval. The zero-frequency progression approximation alone is not adequate here.

These witnessed long-divisor terms have Möbius signs that must still be recombined. Their occurrence is not a lower bound for their net signed contribution.

7. What has advanced, and what remains

The strongest new result is the complete signed principal-term evaluation (14)–(17). It removes the small-modulus discrepancy through $X^{1/3}$ while retaining genuine midpoint labels, genuine shifted primes and polynomial roughness.

There is also a rigorous obstruction to the proposed uncentered common-quotient energy method: its off-diagonal has the exact order of magnitude in (8), its diagonal is negligible, and even a single uncorrected local prime produces a definite excess over the energy budget needed for positivity.

The remaining candidate is a centered reciprocal estimate for the signed long-divisor discrepancy in (17), rather than a saving on the complete rough-composite energy. The small determinant could assist such an estimate, but the actual prime-supported Fourier coefficients and the large-lcm range remain uncontrolled.

I selected the dyadic bank, small fixed roughness exponent and reciprocal test ranges independently. The unweighted reciprocal saving is not claimed for the original prime-supported sum. I did not obtain the strict lower bound in (17), so the ordinary twin-prime conjecture remains unresolved by this calculation.

No private records or files were inspected or written, and no paper-release work or third-party contact was undertaken.

---

### Recovered response 3

1. The Jacobi representation is exact and gives a sufficient parity test

Your identity is correct. More significantly, its second moment has an exact prime-versus-semiprime sign distinction, which survives averaging over a polynomial number of shifts.

I have derived that distinction below. The difficulty is that the corresponding character-sum energy has a much larger diagonal, and quadratic reciprocity exposes a substantial square-numerator degeneracy.

Let

$$
\mathcal C_X=
\{X<n\le2X:\ n-2\text{ prime},\
\mu^2(n)=1,\ \Omega(n)\le2,\
P^-(n)>X^{1/8}\}.
$$

Write $N=|\mathcal C_X|$, and let $T$ be the number of genuine twin pairs in this set.

The Chen lower bound supplies $N\gg X/\log^2X$, and the standard upper sieve supplies the corresponding upper bound. For the roughness hypothesis, one may use the stronger Chen-prime input stated in Theorem 6.1 of Green and Tao's Restriction theory of the Selberg sieve, with applications, which uses least-prime-factor exponent $3/11$. Removing square endpoints costs $O(\sqrt X)$.

numdam.org

Choose

$$
H=\left\lfloor\frac12X^{1/8}\right\rfloor
$$

and, for $n\in\mathcal C_X$, define

$$
K_n(u,h)=\left(\frac{u(u+h)}n\right).
$$

For an odd prime $q$ and $h\not\equiv0\pmod q$,

$$
\sum_{u\bmod q}\left(\frac{u(u+h)}q\right)=-1.
$$

One elementary proof counts solutions of $y^2=u(u+h)$. After completing the square, the equation becomes a product of two variables equal to $h^2$, giving $q-1$ solutions.

If $q\mid h$, the sum is instead $q-1$. CRT therefore gives, for every odd squarefree $n$,

$$
\sum_{u\bmod n}K_n(u,h)
=
\prod_{\substack{q\mid n\\q\mid h}}(q-1)
\prod_{\substack{q\mid n\\q\nmid h}}(-1)
=c_n(h).
$$

All $1\le h\le H$ are coprime to every $n\in\mathcal C_X$. Hence

$$
\boxed{
\mathcal J_X:=
\frac1H\sum_{n\in\mathcal C_X}
\sum_{h=1}^H\sum_{u\bmod n}K_n(u,h)
=N-2T.
}
\tag{1}
$$

The exact sufficient target is

$$
\mathcal J_X\le(1-\eta)N
$$

for some fixed $\eta>0$ along an unbounded sequence of $X$. It would imply

$$
T\ge\frac{\eta N}{2}
\gg_\eta\frac{X}{\log^2X}.
$$

A negative signed first moment would be stronger than necessary: it would establish that more than half of this Chen population consists of genuine twin pairs.

2. Exact off-diagonal calculation: the two ranks really are different

Let $\chi_q$ denote the Legendre character at an odd prime $q$. For any integers $h,k$, including zero or nonunit residues, one has

$$
\boxed{
\sum_{u\bmod q}K_q(u,h)K_q(u,k)
=
q\,1_{h\equiv k\pmod q}
-1-\chi_q(hk).
}
\tag{2}
$$

To prove this, multiply the characters:

$$
K_q(u,h)K_q(u,k)
=
1_{u\ne0}\chi_q((u+h)(u+k)).
$$

The complete quadratic character sum on the right, before excluding $u=0$, is $q-1$ when the two roots coincide, and $-1$ otherwise. Excluding zero subtracts precisely $\chi_q(hk)$.

CRT now gives the complete Gram matrix at every squarefree $n$:

$$
\sum_{u\bmod n}K_n(u,h)K_n(u,k)
=
\prod_{q\mid n}
\bigl(q1_{h\equiv k\pmod q}-1-\chi_q(hk)\bigr).
\tag{3}
$$

On the original short-shift range, distinct $h,k\in[1,H]$ remain distinct and nonzero modulo every factor of $n$.

Consequently:

Endpoint $n$
 |
Diagonal $h=k$
 |
Off-diagonal $h\ne k$
 |

Prime $q$
 |
$q-2$
 |
$-1-\chi_q(hk)\le0$
 |

Semiprime $rs$
 |
$(r-2)(s-2)$
 |
$(1+\chi_r(hk))(1+\chi_s(hk))\ge0$
 |

This is an exact distinction on the actual endpoints, not a statistical independence assumption.

Can weighting the shifts overcome the diagonal?

Allow arbitrary real weights $w_h$, even depending on $n$, with

$$
\sum_{h=1}^H w_h=1.
$$

Define

$$
F_n(u)=\sum_{h=1}^H w_hK_n(u,h).
$$

The complete first moment is still $\mu(n)$.

For prime $n=q$, (2) gives

$$
\sum_{u\bmod q}F_q(u)^2
=
q\sum_h w_h^2
-1-\left|\sum_h w_h\chi_q(h)\right|^2.
$$

Therefore, by Cauchy–Schwarz,

$$
\sum_{u\bmod q}F_q(u)^2
\ge\frac qH-2.
\tag{4}
$$

For $n=rs$, expanding (3) gives

$$
\begin{aligned}
\sum_{u\bmod n}F_n(u)^2
={}&(n-2r-2s)\sum_h w_h^2+1\\
&+\left|\sum_h w_h\chi_r(h)\right|^2\\
&+\left|\sum_h w_h\chi_s(h)\right|^2\\
&+\left|\sum_h w_h\chi_n(h)\right|^2.
\end{aligned}
$$

Since $r,s>X^{1/8}$,

$$
\sum_{u\bmod n}F_n(u)^2
\ge
\left(1-O(X^{-1/8})\right)\frac nH+1.
\tag{5}
$$

Uniform shift weights attain the order $n/H$ in both cases.

Thus no signed reweighting of the short shifts that preserves the complete first moment can reduce the individual row energy below order $n/H$.

Averaging over the shifts does buy a factor $H$ compared with a single shift, but it cannot buy more through shift weights alone.

3. The precise cross-endpoint energy budget

Take the uniform shift average

$$
F_n(u)=\frac1H\sum_{h=1}^H K_n(u,h),
$$

and extend each row by zero outside $0\le u<n$. Put

$$
F(u)=\sum_{n\in\mathcal C_X}F_n(u).
$$

Then (1) becomes

$$
\mathcal J_X=\sum_{0\le u<2X}F(u).
$$

The diagonal of the physical second moment is, by (4)–(5),

$$
\boxed{
E_{\rm diag}
=
\sum_{n\in\mathcal C_X}\sum_{u<n}|F_n(u)|^2
\asymp\frac{NX}{H}.
}
\tag{6}
$$

Let $E_{\rm off}$ denote the actual cross-endpoint contribution, retaining its signs. Cauchy–Schwarz gives

$$
|\mathcal J_X|^2
\le2X(E_{\rm diag}+E_{\rm off}).
$$

To deduce the strict bound $\mathcal J_X\le(1-\eta)N$ through this absolute-value inequality, the required energy budget is

$$
E_{\rm diag}+E_{\rm off}
\le\frac{(1-\eta)^2N^2}{2X}.
\tag{7}
$$

The ratio of this budget to the diagonal is

$$
\asymp\frac{HN}{X^2}
\asymp\frac{H}{X\log^2X}.
$$

At $H\asymp X^{1/8}$, this is of order

$$
\boxed{\frac{X^{-7/8}}{\log^2X}.}
$$

In other words, merely obtaining cancellation of the off-diagonal to a size smaller than the diagonal would not suffice. One would need a specifically negative off-diagonal that cancels essentially the entire diagonal, with the displayed relative precision.

The diagonal-only Cauchy budget is of order

$$
\sqrt{X E_{\rm diag}}
\asymp X\sqrt{N/H},
$$

which exceeds the desired first-moment scale $N$ by a factor of order $X^{7/16}\log X$.

Complete cross-endpoint correlations can also be evaluated exactly

For distinct coprime $n,m\in\mathcal C_X$, CRT gives, for every permitted pair of shifts,

$$
\frac1{nm}\sum_{u\bmod nm}K_n(u,h)K_m(u,k)
=
\frac{\mu(n)\mu(m)}{nm}.
$$

Accordingly, the centered functions

$$
\widetilde F_n(u)=F_n(u)-\frac{\mu(n)}n
$$

have exactly zero cross-covariance on the complete joint period.

There is also a controlled formula for shared prime factors. Distinct noncoprime Chen endpoints necessarily have the form

$$
n=qa,\qquad m=qb
$$

with three distinct primes $q,a,b$. Using (2) at the shared prime gives

$$
\begin{aligned}
\mathbb E_{u\bmod[n,m]}
\widetilde F_n(u)\widetilde F_m(u)
={}&
\frac{q^2/H-q(1+t_q^2)-1}{nm},\\
t_q={}&\frac1H\sum_{h\le H}\chi_q(h).
\end{aligned}
\tag{8}
$$

The total absolute shared-factor contribution is small on the complete period.

Indeed, if $C_q$ counts the actual Chen endpoints divisible by $q$, then $C_q\le2X/q$. For a shared factor, its other prime factor exceeds $z=X^{1/8}$, so $q\le2X/z$. Hence

$$
\sum_q q^2 C_q(C_q-1)
\le 2X\sum_q qC_q
\ll \frac{NX^2}{z}.
$$

Combining this with (8), the total centered shared-factor covariance is

$$
O\left(\frac{N}{Hz}\right).
$$

The centered diagonal on the complete period is of order $N/H$.

This verifies that shared prime factors are not the main obstruction in the complete-period model.

But the complete cross-period for coprime $n,m$ has length $nm\asymp X^2$, whereas the physical common-$u$ interval has length only $O(X)$. Complete-period orthogonality does not establish the negative physical off-diagonal required in (7).

4. Quadratic reciprocity exposes a large, exact positive degeneracy

Before applying reciprocity or the quadratic large sieve, the square numerator $u(u+h)$ must be treated separately.

I obtain an explicit asymptotic for its complete contribution:

$$
\boxed{
Q(H)=
\#\{(u,h):u\ge1,\ 1\le h\le H,\ u(u+h)\text{ is a square}\}
=
\frac{3}{4\pi^2}H(\log H)^2+O(H\log H).
}
\tag{9}
$$

Every one of these pairs contributes $+1$ on every actual Chen endpoint in $\mathcal C_X$.

Derivation

If $u(u+h)$ is a square, there are unique integers $a,b,d$, with $a$ squarefree and $b,d\ge1$, such that

$$
u=ab^2,\qquad u+h=a(b+d)^2.
$$

Thus

$$
h=ad(2b+d)\le H.
$$

The exact count is

$$
Q(H)=
\sum_{a\le H}\mu^2(a)
\sum_{d\le\sqrt{H/a}}
\left\lfloor\frac{H/(ad)-d}{2}\right\rfloor.
$$

The inner sum is

$$
\frac{H}{4a}\log(H/a)+O(H/a).
$$

The elementary squarefree harmonic estimate gives

$$
\sum_{a\le H}\frac{\mu^2(a)}a\log(H/a)
=
\frac3{\pi^2}(\log H)^2+O(\log H),
$$

which proves (9).

Moreover, every such pair satisfies

$$
u\le\frac{H^2}{4}<X
$$

and all prime factors of $ab(b+d)$ are at most $H$. Since every prime factor of a Chen endpoint exceeds $2H$, the square numerator is coprime to $n$. Its Jacobi symbol is exactly one.

There is no coprimality exception or variable-period boundary error in this calculation.

What this does to the signed first moment

Let $\mathcal J_{\rm ns}$ be the unnormalized character sum over the positive nonsquare numerators, retaining the full original $u,h,n$ ranges.

Equation (1) now gives exactly

$$
\boxed{
\mathcal J_{\rm ns}
=-NQ(H)+H(N-2T).
}
\tag{10}
$$

Consequently, there is already an unconditional negative signed first moment on nonsquare numerators:

$$
\mathcal J_{\rm ns}
=
-\left(\frac3{4\pi^2}+o(1)\right)
NH(\log H)^2.
$$

This is substantial negative cancellation on the genuine prime-supported Chen population. But it compensates the large positive square contribution.

The estimate sufficient for twins is not merely negativity, or even the correct leading negative asymptotic. It is

$$
\boxed{
\mathcal J_{\rm ns}
\le -NQ(H)+(1-\eta)HN.
}
\tag{11}
$$

The square term must be canceled to additive precision $O(HN)$, approximately a relative $1/(\log H)^2$ precision on this negative population.

This is a concrete arithmetic degeneracy of the proposed two-variable amplifier, rather than a generic invocation of the parity barrier.

5. Testing the quadratic large sieve on the actual opened coefficients

Write

$$
u(u+h)=a b^2
$$

with $a$ squarefree. The exact reduction is

$$
K_n(u,h)
=
1_{(b,n)=1}\left(\frac an\right).
$$

The coprimality mask cannot be omitted in the long numerator range.

There are also substantial repeated columns besides the square class. For every $1\le d\le H$,

$$
K_n(du,dh)=K_n(u,h)
$$

whenever the shifted variables remain inside their allowed ranges. This follows because $d$ is a unit modulo $n$.

Thus many different pairs of free variables give identical quadratic-character tests. They are not independent samples.

I checked Heath-Brown's A mean value estimate for real character sums, specifically Theorem 1 and Corollary 2. The latter explicitly accommodates nonsquarefree numerator coefficients, with square-product collisions retained in its energy.

ora.ox.ac.uk

To test its strength without a variable-endpoint complication, restrict to the genuine common rectangle

$$
X/4<u\le X/2,\qquad 1\le h\le H.
$$

Define the nonnegative multiplicities

$$
b_v=\#\{(u,h)\text{ in this rectangle}:u(u+h)=v\}.
$$

The numerator scale is $M\asymp X^2$, and the character conductor scale is $X$.

Corollary 2, followed by Cauchy–Schwarz over the actual Chen moduli, gives the bound

$$
\left|
\sum_{n\in\mathcal C_X}\sum_v
b_v\left(\frac vn\right)
\right|
\ll_\epsilon
X^\epsilon
\sqrt{N(X+M)
\sum_{v w=\square}b_vb_w}.
\tag{12}
$$

This is a legitimate application: every $n\in\mathcal C_X$ is odd and squarefree, so its Jacobi character is primitive.

But the square-product energy includes the ordinary diagonal, and therefore

$$
\sum_{vw=\square}b_vb_w
\ge\sum_v b_v^2
\ge\sum_v b_v
\asymp XH.
$$

Even using only this minimum energy, the right-hand budget in (12) has size at least

$$
X^{3/2}\sqrt{NH}.
$$

The signal required for the whole signed sum is $HN$. Their ratio is of order at least

$$
\boxed{
\frac{X\log X}{\sqrt H}.
}
\tag{13}
$$

At $H\asymp X^{1/8}$, this grows as $X^{15/16}\log X$.

This test does not involve dropping the coprimality mask: Corollary 2 handles the original Jacobi symbols directly. The rectangle also contains no square numerators, since all those in (9) have $u\le H^2/4$.

Removing the principal square degeneracy alone therefore does not repair the available quadratic large-sieve bound. The remaining scale mismatch is already enormous.

6. A diagonal-free repair using square shifts

There is a way to remove the entire within-endpoint diagonal exactly, rather than attempting to estimate it.

Choose the shifts

$$
\mathcal H=\{1^2,2^2,\ldots,\lfloor\sqrt H\rfloor^2\}.
$$

For any distinct $h,k\in\mathcal H$, every local character satisfies $\chi_q(hk)=1$. Formula (3) becomes

$$
\sum_{u\bmod n}K_n(u,h)K_n(u,k)
=(-2)^{\omega(n)}.
$$

Thus, writing $B=|\mathcal H|$,

$$
\boxed{
\frac1{B(B-1)}
\sum_{n\in\mathcal C_X}
\sum_{\substack{h,k\in\mathcal H\\h\ne k}}
\sum_{u\bmod n}K_n(u,h)K_n(u,k)
=4N-6T.
}
\tag{14}
$$

This gives a genuine diagonal-free sufficient criterion: an upper bound strictly below $4N$, by a fixed proportion of $N$, proves infinitely many twins.

However, opening this repaired statistic gives

$$
K_n(u,h)K_n(u,k)
=
1_{(u,n)=1}
\left(\frac{(u+h)(u+k)}n\right).
$$

Removing the coprimality mask by divisor inversion shows exactly what remains:

$$
\begin{aligned}
\sum_{u\bmod n}K_n(u,h)K_n(u,k)
&=\sum_{d\mid n}\mu(d)
\sum_{\substack{u\bmod n\\d\mid u}}
\left(\frac{(u+h)(u+k)}n\right)\\
&=\sum_{d\mid n}\mu(d)\mu(n/d)\\
&=2^{\omega(n)}\mu(n).
\end{aligned}
$$

Each divisor contributes with the same Möbius sign. There is no internal cancellation among these opened divisor terms.

The repair successfully removes the diagonal, but estimating the resulting cross-endpoint signed sum still requires distinguishing the actual parity classes.

7. A stronger repair: deliberately permit nonunit shifts

The most promising further modification I found is to extend the shift interval substantially. Instead of requiring every shift to be coprime to $n$, use the exceptional nonunit shifts to cancel the positive semiprime contribution.

Set

$$
L=\log X,\qquad
K=\left\lfloor\frac{\sqrt X}{L^2}\right\rfloor,
$$

and define

$$
D_K(n)=\frac1K\sum_{h=1}^K c_n(h).
$$

For a prime $n\in(X,2X]$, every shift is nonzero modulo $n$, so

$$
D_K(n)=-1.
$$

For a squarefree semiprime $n=ab$, with primes $a<b$, we always have $b>\sqrt X>K$. Therefore

$$
c_n(h)=1-a1_{a\mid h},
$$

and consequently

$$
\boxed{
D_K(ab)=1-\frac aK\left\lfloor\frac Ka\right\rfloor.
}
\tag{15}
$$

In particular,

$$
0\le D_K(ab)<a/K.
$$

When $a\le K/L^2$, the positive semiprime contribution is at most $L^{-2}$.

It remains to price the actual exceptional semiprimes with

$$
\frac{\sqrt X}{2L^4}<a\le\sqrt{2X}.
$$

Unconditional removal of the nearly balanced exception

Fix such a genuine prime $a$. Both $b$ and $ab-2$ must be prime, with $b\asymp X/a$.

The two-dimensional upper sieve gives

$$
\#\{b:X<ab\le2X,\ b,\ ab-2\text{ prime}\}
\ll\frac{X}{aL^2}
$$

uniformly over this band.

The uniformity follows directly from the local root counts: at odd sieving primes other than $a$, the two linear forms have two distinct roots. Sieve through a sufficiently small fixed power of $X/a$, which lies below $a$ throughout this band. The ordinary Selberg denominator is of order $\log^2(X/a)$, and its interval remainder is power-small.

By partial summation over prime $a$,

$$
\sum_{\sqrt X/(2L^4)<a\le\sqrt{2X}}\frac1a
\ll\frac{\log L}{L}.
$$

Hence the entire exceptional semiprime population has size

$$
O\left(\frac{X\log L}{L^3}\right).
$$

It follows unconditionally that

$$
\boxed{
\frac1K
\sum_{n\in\mathcal C_X}
\sum_{h=1}^K\sum_{u\bmod n}
\left(\frac{u(u+h)}n\right)
=
-T+O\left(\frac{X\log\log X}{\log^3X}\right).
}
\tag{16}
$$

This is a useful improvement of the original amplifier. The short-shift version gives the difference between semiprime and prime counts. The extended-shift version removes the semiprime main term altogether, leaving the negative of the actual twin count, up to a proved smaller-order error.

8. An equivalent character-energy deficit that would prove twins

The preceding repair also admits an exact triangularly averaged formulation.

Define

$$
V_K(n)=
\sum_{u\bmod n}
\left|\sum_{v=1}^{K}\chi_n(u+v)\right|^2.
$$

Expanding the square and using the complete Jacobi correlation,

$$
V_K(n)
=
K\varphi(n)+
2\sum_{h=1}^{K-1}(K-h)c_n(h).
$$

For primes $n$, the second term equals $-K(K-1)$.

For semiprimes $n=ab$, with $b>K$, write $K=ma+t$, where $0\le t<a$. An exact summation gives

$$
\frac{V_K(ab)-K\varphi(ab)}{K(K-1)}
=
\frac{K(a-1)-t(a-t)}{K(K-1)}.
$$

This expression is nonnegative, at most one, and is $O(a/K)$ when $a\le K$.

The same nearly balanced exception estimate therefore proves

$$
\boxed{
\sum_{n\in\mathcal C_X}V_K(n)
=
K\sum_{n\in\mathcal C_X}\varphi(n)
-K(K-1)T
+
O\left(
\frac{K^2X\log\log X}{\log^3X}
\right).
}
\tag{17}
$$

A sufficient new arithmetic estimate is consequently

$$
\boxed{
\sum_{n\in\mathcal C_X}V_K(n)
\le
K\sum_{n\in\mathcal C_X}\varphi(n)
-cK^2\frac{X}{L^2}
}
\tag{18}
$$

for some fixed $c>0$ along an unbounded sequence.

Substitution into (17) would give

$$
T\gg_c\frac X{\log^2X}.
$$

Comparison with the diagonal

The exact diagonal has order $KXN$, while the desired deficit has order $K^2N$. The required relative saving is

$$
\frac KX\asymp\frac1{\sqrt X L^2}.
$$

This is a better scale than the original short-shift energy test, but still extremely demanding. In particular, replacing $\varphi(n)$ by $n$ is not justified at this precision. The resulting error on semiprimes can be much larger than the proposed deficit.

The diagonal must remain exactly $K\sum\varphi(n)$.

Research verdict

The Jacobi approach has produced several substantive, checkable results:

Calculation
 |
Outcome
 |

Complete short-shift parity amplifier
 |
Exact
 |

Prime/semiprime off-diagonal distinction
 |
Exact
 |

Optimal order of shift-only diagonal energy
 |
Proved
 |

Square-numerator degeneracy
 |
Explicitly evaluated
 |

Direct quadratic large-sieve application
 |
Insufficient at the required scale
 |

Extended nonunit-shift semiprime cancellation
 |
Proved
 |

Strict character-energy deficit (18)
 |
Unproved
 |

The strongest surviving direction is now (18): a deficit in the complete short-character-sum energy, averaged over genuine squarefree Chen endpoints. The extended shifts eliminate the semiprime main contribution unconditionally, so a sufficiently strong negative deficit would force actual twin primes.

I chose the shift extension and nearly balanced cutoff independently. The proof of the elementary identities and reductions is complete at their stated scope; the required signed arithmetic estimate is not. I have not established an unconditional proof of the twin-prime conjecture.

No private research files were inspected or written, and no paper preparation or third-party contact was undertaken.

---

### Recovered response 4

The boundary scaling is mathematically useful. I have proved a localization result for your normal family: every limiting function is determined by shifted primes whose factorization consists of a small squarefree part and one genuinely prime large cofactor. Contributions with two or more large factors disappear uniformly on compact $w$-sets.

I also obtain an actual arithmetic lower bound for tagged adjacent ranks. The decisive issue is whether that lower bound can be made to survive the boundary normalization, rather than losing one factor of $\log\log X$.

I agree with your correction concerning the four-frequency deficit. Transferring shift mass from $1$ to $2$ preserves the complete Ramanujan trace on every odd endpoint while changing the selected-frequency contribution. That route does not establish positivity of the twin count.

1. Normality and the exact analytic sufficiency test

Write

$$
L=\log X,\qquad \lambda=\log\log X,
$$

and let

$$
A_k(X)=
\#\left\{
\frac X2<p\le X:
p+2\text{ squarefree},\ \omega(p+2)=k
\right\},
$$

where $p$ is always prime.

Then your polynomial is

$$
F_X(w)=\sum_{j\ge0}b_j(X)w^j,
\qquad
b_j(X)=\frac{L^2 A_{j+1}(X)}{X\lambda^j}.
$$

In particular,

$$
F_X(0)=\frac{L^2}{X}A_1(X)
$$

is exactly the normalized twin-prime count, not a count including prime powers.

I checked Corollary 1 of Ford's original Hardy–Ramanujan type inequality for shifted primes and sifted sets. Its bound is uniform in the factor rank, and applies to our shift $a=2$ without the adjustment required for odd shifts.

arxiv.org

It gives absolute constants $C,C_0$ such that

$$
0\le b_j(X)\le
\frac{C}{j!}\left(1+\frac{C_0}{\lambda}\right)^j.
\tag{1}
$$

Consequently,

$$
|F_X(w)|\le
C\exp\left(\left(1+\frac{C_0}{\lambda}\right)|w|\right).
$$

Thus the family is normal on the entire complex plane. Every subsequential limit is entire, with nonnegative coefficients bounded by $C/j!$.

What sign information would actually suffice?

For fixed real $w>0$,

$$
F_X(0)\ge
F_X(w)-C(e^w-1)-o(1).
\tag{2}
$$

A stronger prime-sensitive test uses the negative activity:

$$
F_X(-w)=
-\frac{L^2}{X}
\sum_{\substack{X/2<p\le X\\p+2\text{ squarefree}}}
\mu(p+2)
\left(\frac w\lambda\right)^{\omega(p+2)-1}.
$$

All odd-degree coefficients now enter negatively. Hence

$$
\boxed{
F_X(0)\ge
F_X(-w)-C(\cosh w-1)-o(1).
}
\tag{3}
$$

This improves the contamination budget from $O(w)$ to $O(w^2)$.

Therefore, at any sufficiently small fixed $w>0$, a proved lower bound

$$
F_X(-w)>C(\cosh w-1)+\eta
$$

with $\eta>0$ on an unbounded sequence would force infinitely many twins.

Mere positivity of $F_X(-w)$, however, is insufficient: the first surviving contribution could come from integers with three distinct prime factors.

2. A stronger use of Ford's small-prime theorem

Choose the moving cutoff

$$
U=\lambda^2,\qquad
y=X^{1/U}.
$$

For a squarefree shifted integer $n=p+2$, split its factors into

$$
d=\prod_{\substack{q\mid n\\q\le y}}q,
\qquad m=n/d,
$$

and write

$$
K_y(n)=\omega(d),\qquad R_y(n)=\omega(m).
$$

The exact small-factor model is particularly informative here because it can be evaluated at the boundary activity $w/\lambda$, not just at the usual Erdős–Kac scale.

I checked Theorem 1 of Ford's Poisson approximation of prime divisors of shifted primes. Ordinary Bombieri–Vinogradov supplies its hypothesis $Z(1/2)$, and its total-variation error is

$$
O_A\left(e^{-\alpha U\log U}+L^{-A}\right)
$$

for fixed $0<\alpha<1/2$ and arbitrary fixed $A$. At our cutoff this is smaller than every fixed negative power of $L$.

arxiv.org

The theorem applies to the cumulative prime populations at $X$ and $X/2$; subtracting them gives the required dyadic result.

For an odd prime $q\le y$, its model probabilities of valuations zero and one are

$$
v_0(q)=1-\frac1{q-1},
\qquad v_1(q)=\frac1q.
$$

Define

$$
V_y=\prod_{3\le q\le y}v_0(q),
\qquad
\rho(q)=\frac{v_1(q)}{v_0(q)}
=\frac{q-1}{q(q-2)}.
$$

Mertens' theorem gives

$$
V_y\sim\frac{2C_2 e^{-\gamma}U}{L},
$$

where

$$
C_2=\prod_{q>2}
\left(1-\frac1{(q-1)^2}\right).
$$

Also,

$$
\sum_{3\le q\le y}\rho(q)
=\lambda-\log U+O(1),
\qquad
\sum_q\rho(q)^2<\infty.
$$

The probability generating function of the squarefree small-factor part is consequently

$$
V_y\prod_{3\le q\le y}
\left(1+\frac w\lambda\rho(q)\right)
=V_y(e^w+o(1)),
$$

uniformly on compact complex $w$-sets.

The squarefree restriction on factors above $y$ costs at most

$$
O(X/y+\sqrt X)
$$

integers, which is negligible at every logarithmic scale under consideration.

Combining these facts with the prime number theorem proves the following actual shifted-prime asymptotic:

$$
\boxed{
\frac{L^2}{UX}
\sum_{\substack{X/2<p\le X\\p+2\text{ squarefree}}}
\left(\frac w\lambda\right)^{K_y(p+2)}
\longrightarrow
C_2e^{-\gamma}e^w.
}
\tag{4}
$$

This convergence is locally uniform in the complex plane.

Importantly, (4) makes no assertion about independence of the remaining cofactor.

3. Localization of the entire normal family to prime cofactors

Here is the stronger arithmetic consequence.

Define

$$
G_X(w)=\frac{L^2}{X}
\sum_{\substack{X/2<p\le X\\p+2\text{ squarefree}\\R_y(p+2)=1}}
\left(\frac w\lambda\right)^{K_y(p+2)}.
$$

On this population the remaining cofactor $m$ is a genuine prime.

Proved estimate: for every fixed $W>0$,

$$
\boxed{
\sup_{|w|\le W}|F_X(w)-G_X(w)|
\ll_W\frac{\log\lambda}{\lambda}.
}
\tag{5}
$$

Thus the two families have exactly the same subsequential entire limits.

Proof

First consider integers with $j+1$ distinct prime factors and at least two factors exceeding $y$.

Remove their largest prime factor $q$, writing $n=bq$. Then $b$ has exactly $j$ distinct factors, at least one exceeding $y$, and

$$
q\ge(X/2)^{1/(j+1)}.
$$

For a fixed odd $b$, an ordinary two-form upper sieve for

$$
q,\qquad bq-2
$$

gives

$$
\#\{q\text{ satisfying the required conditions}\}
\ll
\frac{X}{b\log^2(2X/b)}
\prod_{\substack{r\mid b\\r>2}}\frac{r-1}{r-2}.
$$

The uniform dependence on $b$ is the same upper-sieve input used in Ford's proof of Corollary 3.

arxiv.org

Because $q$ is the largest factor,

$$
\log(2X/b)\gg\frac L{j+1}.
$$

Using the reciprocal prime weight $\rho(r)$ defined above, the total harmonic mass of possible $b$'s is bounded by

$$
\left(\sum_{y<r\le X+2}\rho(r)\right)
\frac{\left(\sum_{r\le X+2}\rho(r)\right)^{j-1}}{(j-1)!}.
$$

The first parenthesis is $\log U+O(1)$, while the second prime sum is $\lambda+O(1)$.

Consequently,

$$
\begin{aligned}
&\#\left\{
X/2<p\le X:
p+2\text{ squarefree},\
\omega(p+2)=j+1,\
R_y(p+2)\ge2
\right\}\\
&\hspace{12mm}\ll
\frac X{L^2}(j+1)^2
(\log U+1)\frac{(\lambda+C_0)^{j-1}}{(j-1)!}.
\end{aligned}
\tag{6}
$$

After multiplying by the boundary weights and summing over $j\ge1$, the exponential series gives

$$
\frac{L^2}{X}
\sum_{R_y(n)\ge2}
\left|\frac w\lambda\right|^{\omega(n)-1}
\ll_W\frac{\log U+1}{\lambda}.
$$

Finally, if $R_y(n)=0$, all prime factors are at most $y$, so $n>X/2$ forces

$$
\omega(n)\ge U(1-o(1)).
$$

The factorial upper bound (1) makes that entire contribution smaller than every fixed negative power of $\lambda$.

Since $\log U=2\log\lambda$, this proves (5).

The significance is that the unknown limiting coefficients cannot be recovered merely from the small-prime marginal in (4). They measure the actual probability that the omitted portion of the factorization is prime.

4. The first unknown conditional intensity

The coefficient version of (4) gives, for every fixed $j\ge0$,

$$
\#\{p\in(X/2,X]:p+2\text{ squarefree},\ K_y(p+2)=j\}
\sim
\frac{C_2e^{-\gamma}UX}{L^2}\frac{\lambda^j}{j!}.
\tag{7}
$$

Let $\pi_{X,j}$ be the actual conditional probability that $R_y=1$ on this population.

Combining (5)–(7) gives

$$
\boxed{
b_j(X)=
\frac{C_2e^{-\gamma}}{j!}
U\pi_{X,j}+o_j(1).
}
\tag{8}
$$

The uniform coefficient bound implies $\pi_{X,j}=O_j(1/U)$.

Thus prime completion is a rare event, occurring on at most the $1/U$ scale even after conditioning on a fixed number of small factors.

Ford's theorem determines the denominator of this conditional probability to ample precision. It does not determine its numerator.

The first unknown intensity is

$$
U\pi_{X,0}.
$$

A positive lower bound for this intensity on an unbounded sequence would settle the conjecture.

I next tested whether an actual adjacent-rank lower sieve could force such an intensity, rather than assigning all its positive contribution to composite cofactors.

5. An unconditional tagged low-rank lower bound

I checked Timofeev's original 1995 article, The Hardy–Ramanujan and Halász inequalities for shifted primes. Its Theorem 3 gives the adjacent-rank lower bounds, and its equation (16) arises from a Chen sieve with small multiplicative tags.

mathnet.ru

Rather than silently extending its cumulative count to squarefree dyadic populations, I reconstructed the following restricted tagged calculation.

For fixed $j\ge0$, let $\mathcal D_j$ consist of squarefree products of exactly $j$ primes in

$$
L^{10}<r\le y.
$$

Include $d=1$ when $j=0$. These tags satisfy

$$
d\le y^j=X^{o(1)},
\qquad
\sum_{d\in\mathcal D_j}\frac1d
\sim\frac{\lambda^j}{j!}.
\tag{9}
$$

For every tag write

$$
p+2=dm,\qquad T_d=\frac{X+2}{d}.
$$

Let $P_j(X)$ count the resulting actual shifted primes for which $m$ is prime, and let $Q_j(X)$ count those for which $m$ is squarefree semiprime with both factors exceeding $T_d^{1/8}$.

I obtain an absolute $c>0$ such that, for every fixed $j$,

$$
\boxed{
P_j(X)+Q_j(X)
\ge c\frac{X}{L^2}\frac{\lambda^j}{j!}
}
\tag{10}
$$

for sufficiently large $X$, depending on $j$.

These are genuine shifted integers. Moreover, the small part of $p+2$ is exactly $d$, so there is no multiple counting across the tags.

Proof of the positive lower bound

Put

$$
z=T_d^{1/8},\qquad Y=T_d^{1/3}.
$$

On $z$-rough, squarefree $m$, use the Chen weight

$$
W_d(m)=1-\frac12\sum_{\substack{z\le q<Y\\q\mid m}}1
-\frac12\,1_{\mathcal E_d}(m),
$$

where $\mathcal E_d$ consists of products of three primes with exactly one factor below $Y$.

This weight satisfies

$$
W_d(m)\le1_{\{\Omega(m)\le2\}}.
$$

Indeed, a squarefree triple with two small factors already loses at least one through the first subtraction. A triple with exactly one small factor loses the remaining half through the second subtraction. Any product of at least four prime factors has at least two factors below $Y$.

Squareful exceptions among the $z$-rough $m$'s cost $O(T_d/z)$ for each tag, which is negligible after summation over $d$.

Fix a distribution exponent $\theta<1/2$, sufficiently close to $1/2$, and use direct sieve level $X^\theta/d$.

The progression moduli for the original prime variable are $de$, or $dqe$ when opening the first subtraction. Their maximum is $X^\theta$. Ordinary Bombieri–Vinogradov therefore controls the aggregated errors.

The shared factors between $d$ and $e$ are retained through the exact local density

$$
g_d(r)=\frac{\varphi(d)}{\varphi(dr)}.
$$

At primes dividing $d$, this equals $1/r$, rather than $1/(r-1)$. Because the tags have fixed rank and every tag prime exceeds $L^{10}$, the associated singular-product changes are uniformly $1+o(1)$.

The multiplicities of opened moduli are divisor-bounded. The weighted remainder estimates follow from Bombieri–Vinogradov by Cauchy–Schwarz and the standard reciprocal divisor moments.

I use the standard linear sieve functions, with their precise ranges as stated in equations (2.4)–(2.5) of Matomäki and Zuniga-Alterman's Weighted sieves with switching.

Cambridge Core

In units of

$$
\frac{2C_2X}{2dL^2},
$$

the direct lower sieve has coefficient

$$
8e^{-\gamma}f(8\theta)
=\frac2\theta\log(8\theta-1).
$$

The first subtraction has upper coefficient

$$
\int_{1/8}^{1/3}\frac{dt}{t(\theta-t)}.
$$

Here the remaining sieve level after selecting $q=T_d^t$ is $X^\theta/(dq)$, which gives the displayed $\theta-t$ denominator.

The switched triple subtraction

For the second subtraction, sieve the actual prime condition

$$
dq_1q_2q_3-2\text{ prime},
$$

where

$$
z\le q_1<Y,\qquad Y\le q_2\le q_3.
$$

The ordinary triple-product count in the required interval is

$$
\frac{T_d}{2\log T_d}(I+o(1)),
$$

with

$$
I=\int_{1/8}^{1/3}
\frac{\log(2-3t)}{t(1-t)}\,dt.
\tag{11}
$$

To obtain this integral, first integrate the second factor exponent from $1/3$ to $(1-t)/2$; the third factor is then priced by the prime number theorem. All three prime variables have polynomial size. The angular boundary strips have arbitrarily small limiting mass.

The convolution Bombieri–Vinogradov estimate applies at level $T_d^\theta$. For the specific source here, group $q_1q_2$ into one bounded coefficient and keep $q_3$ as the prime variable. Both grouped lengths are polynomial, and the prime variable satisfies the required nonprincipal Siegel–Walfisz estimates. The maximal convolution estimate in Timofeev's Lemma 2 is an applicable classical form of this input. The ordering of $q_2,q_3$ can alternatively be handled by counting both orientations and dividing by two, with a negligible repeated-factor boundary.

For each fixed $d$, the progression residue is $2\bar d$ modulo a modulus coprime to $2d$. The maximum over reduced residue classes in the convolution estimate makes this uniform in $d$.

The resulting error is $O_A(T_d/L^A)$ per tag, not $O_A(X/L^A)$ per tag. Summation is therefore controlled by (9).

The principal coprimality exclusion is also harmless here: a prime factor of a triple product is at least $z$, so imposing divisibility by any such factor costs $O(T_d/z)$ before the reciprocal-modulus summation.

Upper-sieving the switched prime through $T_d^{1/4}$ gives the coefficient

$$
4e^{-\gamma}F(4\theta)=\frac2\theta.
$$

Including the factor $1/2$ in the original Chen weight, the switched subtraction consequently costs at most $I/\theta$.

Check the sign of the complete lower bound

The surviving coefficient tends, as $\theta\uparrow1/2$, to

$$
4\log3-2\log6-2I
=
2\left(\log\frac32-I\right).
$$

This is strictly positive, with an elementary certificate.

Using $\log(1+u)\le u-u^2/2+u^3/3$,

$$
\begin{aligned}
I
&\le
\frac{175}{128}
+\frac56\log\frac83
+\frac{20}{3}\log\frac{16}{21}\\
&<\frac{769}{1920}.
\end{aligned}
$$

The last inequality follows from $\log(8/3)<1$ and $\log(21/16)>27/100$.

On the other hand,

$$
\log\frac32\ge\frac{77}{192}
=\frac{770}{1920}.
$$

Hence the limiting coefficient exceeds $1/960$. By continuity, a sufficiently close fixed $\theta<1/2$ retains a positive margin greater than $1/1920$.

Summing over the genuine tags and using (9) proves (10). For example, $c=2C_2/10000$ is a conservative admissible constant.

No independence between the small tag and the remaining cofactor has been used.

6. Propagate the actual lower bound into the boundary function

The contribution of the preceding tagged population to $F_X(w)$, for fixed $w>0$, is

$$
\frac{L^2}{X}
\sum_{j\ge0}
\left(\frac w\lambda\right)^j
\left[P_j(X)+\frac w\lambda Q_j(X)\right].
$$

For every fixed finite collection of ranks, (10) applies simultaneously.

Since $w/\lambda<1$,

$$
P_j+\frac w\lambda Q_j
\ge
\frac w\lambda(P_j+Q_j).
$$

Therefore, first summing through a fixed rank $J$, then taking $X\to\infty$, and finally $J\to\infty$, proves

$$
\boxed{
\liminf_{X\to\infty}\lambda F_X(w)
\ge cwe^w,\qquad w>0.
}
\tag{12}
$$

This is a positive lower bound on the actual boundary statistic, derived from genuine tagged factorizations.

But it is one factor of $\lambda$ too small to establish a nonzero normal-family limit, much less a positive constant coefficient.

Can the semiprime contribution be removed?

I tested subtracting an upper bound for $Q_j$ using the same switched distribution theorem.

The ordinary semiprime angular integral is

$$
\int_{1/8}^{1/2}\frac{dt}{t(1-t)}
=\log7.
$$

The switched upper sieve consequently gives, in the same limiting units as the tagged Chen lower,

$$
\limsup
\frac{2L^2j!}{2C_2X\lambda^j}Q_j(X)
\le4\log7.
$$

The lower coefficient for $P_j+Q_j$ approaches

$$
2\left(\log\frac32-I\right).
$$

For orientation, these two coefficients are approximately $7.784$ and $0.0848$, respectively.

The available semiprime upper bound is about ninety times the inclusive lower bound. Thus ordinary subtraction cannot force a positive $P_j$, even with the genuine tags and complete switched calculation.

This is the first failed arithmetic inequality, with both contributions measured in the same units.

7. A discriminating test of the interpolation proposal

There is a particularly simple analytic countermodel showing why the adjacent-rank lower bounds cannot themselves force the constant term.

Consider the polynomials

$$
E_\lambda(w)=
D\sum_{j=1}^{\lfloor\lambda^2\rfloor}
\frac{1-e^{-j/\lambda}}{j!}w^j,
$$

where $D>0$ is fixed.

Their coefficients are nonnegative, obey the factorial Hardy–Ramanujan envelope, and have zero constant term.

Moreover, for every fixed $b>0$, and uniformly for $1\le k\le b\lambda$,

$$
\frac{\lambda(1-e^{-k/\lambda})}{k!}
\ge
\frac{1-e^{-b}}{b(k-1)!}.
$$

Thus these coefficients are compatible with the order of magnitude of every adjacent-rank lower bound in Timofeev's stated range. Indeed, the larger rank alone can pay each adjacent-rank lower bound.

Nevertheless,

$$
\boxed{E_\lambda(w)\longrightarrow0}
$$

locally uniformly on the entire complex plane.

The same model has

$$
E_\lambda(\lambda)
\sim D(1-e^{-1})e^\lambda,
$$

which has the correct order for the normalized total population, since $e^\lambda=L$. Also,

$$
E_\lambda(-\lambda)=O(e^{-\lambda}),
$$

so even global Möbius sign balance is compatible with this vanishing boundary limit.

Adding a fixed positive multiple of $w^2$ produces another model with a nonzero limit and positive values at both $w$ and $-w$, but still zero constant term. Its contribution at the global activity scale is negligible relative to $e^\lambda$.

These are coefficient-information countermodels, not claimed distributions of genuine shifted primes. Their purpose is precise: normality, nonnegative coefficients, adjacent-rank lower bounds, global sign balance, and even positivity at a fixed negative activity do not, in these forms, imply $F(0)>0$.

8. The next arithmetic inequality worth attempting

The small-factor theorem and the localization estimate together reduce the problem to a conditional prime-completion bias.

Let

$$
M_X(w)=
\sum_{\substack{X/2<p\le X\\p+2\text{ squarefree}}}
\left(\frac w\lambda\right)^{K_y(p+2)}.
$$

For fixed positive $w$, define the probability measure proportional to these weights.

The exact asymptotic (4) and localization (5) give

$$
\boxed{
F_X(w)=
(C_2e^{-\gamma}+o(1))Ue^w
\mathbb P_w(R_y=1)
+O_w\left(\frac{\log\lambda}{\lambda}\right).
}
\tag{13}
$$

Thus a positive fixed-$w$ lower bound requires a prime-completion probability of order $1/U$. To prove twins from it, one also needs a sufficiently strong lower bound relative to the analytic contamination budget in (2) or (3).

The actual tagged lower sieve establishes the corresponding scale for prime or semiprime completion, but does not separate them.

The most useful unresolved quantity is therefore

$$
U\pi_{X,j},
$$

especially at $j=0$, together with its dependence on $j$ under the boundary activity. A valid arithmetic comparison linking prime completion across successive small-core ranks could be useful. Ford's marginal total-variation theorem alone does not provide such a comparison.

Research outcome: the normal-family localization (5), the exact small-core boundary asymptotic (4), and the tagged low-rank lower bound (10) are established at their stated scope. The attempted positive lower at the decisive constant scale still fails because the semiprime completion can absorb the available lower bound.

I chose the moving cutoff, tag range and sieve parameters independently. I inspected the public primary source text, although the page-image rendering of Timofeev's article was unavailable. No private records were consulted, no files or papers were created, and no unconditional twin-prime proof has been obtained.

---

### Recovered response 5

Your common kernel is an exact prime projector. Removing the Chen factor-count restriction is a genuine improvement.

I obtained an unconditional negative contribution from a growing family of primitive frequencies, of order $X/\log\log X$, substantially larger than the twin-prime signal we need. However, completing a natural companion family cancels that leading deficit and leaves a positive contribution of order $X/\log X$.

The calculation below establishes both signs on the actual shifted-prime source, without assuming Lü–Wang–Wu's theorem.

1. Fix the exact kernel and required deficit

Write $L=\log X$, $B=2X/3$, and

$$
\mathcal P_X=\{n:X<n\le2X,\ n-2\text{ prime}\},
\qquad N_X=|\mathcal P_X|\sim X/L.
$$

Use your shift weights multiplied by $L$. Explicitly,

$$
w_1=L-\sum_{r\le B}\frac{\log r}{r},
$$

and, for each prime $r\le B$,

$$
w_{r^j}=
\begin{cases}
(1-1/r)\dfrac{\log r}{r^j},&1\le j<J_r,\\[4pt]
\dfrac{\log r}{r^{J_r}},&j=J_r,
\end{cases}
$$

where $J_r=\lfloor\log(2X)/\log r\rfloor$.

These weights are nonnegative for large $X$, sum to $L$, and satisfy the useful estimates

$$
w_1=O(1),\qquad
\sum_h w_hh\ll X,
\tag{1}
$$

and

$$
\sum_{h}\left|
w_h-1_{\{h\le B,\ h\text{ prime}\}}\frac{\log h}{h}
\right|\ll1.
\tag{2}
$$

For (1), primes $r>\sqrt{2X}$ contribute $\log r$ each to the first moment. All smaller prime labels contribute at most $J_r\log r\le\log(2X)$ each. For (2), the geometric redistribution from a prime $r$ to its proper powers has total mass at most $\log r/r^2$, whose sum converges.

The classical harmonic prime sum also gives

$$
w_1=\log(3/2)+\gamma+
\sum_r\frac{\log r}{r(r-1)}+o(1)>0.
$$

Define the real primitive-frequency kernel

$$
W_X(\alpha)=\sum_h w_h\cos(2\pi h\alpha).
$$

Your exact identity gives

$$
\mathcal S_X
:=
\sum_{n\in\mathcal P_X}
\sum_{\substack{a\bmod n\\(a,n)=1}}
W_X(a/n)
=
-LT_X+
\sum_{\substack{n\in\mathcal P_X\\n\text{ composite}}}
\mu(n)\log(X/n),
\tag{3}
$$

where $T_X$ is the number of actual twin pairs in this dyad.

There is no squarefree restriction in (3). The representation uses primitive additive frequencies, not an imprimitive Jacobi character at nonsquarefree moduli.

The November 19 revision of Lü–Wang–Wu states the shifted-prime Möbius cancellation needed to make the correction in (3) negligible. Its author abstract is accessible, but I could not retrieve the complete revised proof; I therefore continue to treat its conclusion as a conditional input.

arxiv.cnoctave.top

Assuming that conclusion, partial summation gives

$$
\mathcal S_X=-LT_X+o(N_X).
\tag{4}
$$

In particular, the sufficient negative deficit is

$$
\boxed{\mathcal S_X\le-cN_X}
\tag{5}
$$

on an unbounded sequence, for any fixed $c>0$.

The results in the next sections are unconditional.

2. A genuine negative deficit from four primitive frequencies

Consider the frequencies with numerators

$$
1,\quad -1,\quad \overline2,\quad-\overline2
\pmod n.
$$

They are distinct primitive frequencies for every odd $n\in\mathcal P_X$ at large $X$.

Since $\overline2=(n+1)/2$,

$$
\cos(2\pi h\overline2/n)
=(-1)^h\cos(\pi h/n).
$$

Thus their exact total contribution at $n$ is

$$
F_{1,2}(n)
=
2\sum_h w_h
\left[
\cos(2\pi h/n)+(-1)^h\cos(\pi h/n)
\right].
$$

The even shifts are precisely the powers of two. Their total weight is $\log2/2$, and dominated convergence evaluates their contribution inside the outer factor two as $\log2+o(1)$.

For odd shifts, the relevant difference is

$$
\cos(2\pi h/n)-\cos(\pi h/n).
$$

The discrepancy between the geometric weights and the simpler prime weights in this difference is $o(1)$, uniformly for $X<n\le2X$. To justify this, first retain finitely many prime powers, for which the difference tends to zero; then use the summable bound underlying (2).

The prime number theorem consequently gives

$$
F_{1,2}(n)
=
2\left[
\log2-
\int_0^{B/n}
\frac{\cos(\pi u)-\cos(2\pi u)}u\,du
\right]+o(1).
\tag{6}
$$

This is uniform across the entire dyad.

A rigorous negative constant

For $0\le u\le2/3$,

$$
\cos(\pi u)-\cos(2\pi u)
=
2\sin(3\pi u/2)\sin(\pi u/2)\ge0.
$$

For $v\le4/9$, put $A=3\pi/2$ and $C=\pi/2$. The elementary bound $\sin t\ge t-t^3/6$ gives

$$
\int_0^v\frac{\cos(\pi u)-\cos(2\pi u)}u\,du
\ge
ACv^2-\frac{AC(A^2+C^2)}{12}v^4
+\frac{A^3C^3}{108}v^6.
$$

The right side exceeds $0.89$ at $v=4/9$, and exceeds $0.63$ at $v=1/3$. Both inequalities can be checked using $3.14159<\pi<3.14160$.

For the first half of the dyad, $B/n\ge4/9$; for the second half, $B/n\ge1/3$. Each half contains $(1/2+o(1))N_X$ shifted primes.

Using $\log2<0.694$ in (6),

$$
\boxed{
\sum_{n\in\mathcal P_X}F_{1,2}(n)
\le-0.13N_X
}
\tag{7}
$$

for all sufficiently large $X$.

For orientation, direct integration gives the sharper limiting coefficient approximately $-0.55308954$.

This is an independent negative deficit at the scale required by (5). It is not yet a deficit of the complete primitive-frequency sum: all other primitive frequencies remain to be included.

In fact, the bound in (7) can be strengthened enough to make the four-frequency deficit sufficient without using Lü–Wang–Wu, provided its complement can be shown nonpositive.

Expanding the integral in (6) gives

$$
\begin{aligned}
I&=\int_1^2\int_0^{2/(3t)}
\frac{\cos(\pi u)-\cos(2\pi u)}u\,du\,dt\\
&=\sum_{k\ge1}
\frac{(-1)^{k+1}(4^k-1)(2\pi/3)^{2k}
(1-2^{1-2k})}
{2k(2k)!(2k-1)}.
\end{aligned}
$$

The alternating terms decrease in magnitude. The first four terms give the rigorous lower bound $I>0.965$. Hence

$$
\boxed{
\sum_{n\in\mathcal P_X}F_{1,2}(n)
\le-0.54N_X.
}
\tag{8}
$$

Meanwhile, the correction in your common-kernel identity satisfies unconditionally

$$
\sum_{n\in\mathcal P_X}\mu(n)\log(X/n)
\ge-(2\log2-1+o(1))N_X,
$$

by the prime number theorem, since

$$
\int_1^2\log t\,dt=2\log2-1<0.387.
$$

Therefore a full-kernel deficit of $0.54N_X$ would already prove twins unconditionally.

The obstacle is obtaining that deficit after including the remaining frequencies.

3. Prime inverse denominators: a much larger negative contribution

I next tested a growing family, using reciprocity and prime distribution in residue classes.

Choose

$$
A=L^{40},
\qquad
\mathcal L=\{\ell:A<\ell\le2A,\ \ell\text{ prime}\}.
$$

For a positive integer $a<X/2$, define its two-frequency contribution

$$
P_a(X)=
2\sum_{\substack{n\in\mathcal P_X\\(a,n)=1}}
W_X(\bar a/n),
$$

where $\bar a$ is the inverse of $a$ modulo $n$.

The factor two includes the distinct negative frequency as well.

Reciprocity calculation

For $(a,n)=1$, additive reciprocity gives

$$
\frac{\bar a}{n}
\equiv
-\frac{\bar n}{a}+\frac1{an}\pmod1.
$$

By (1),

$$
\left|
W_X(\bar a/n)-W_X(-\bar n/a)
\right|
\ll\frac1a.
\tag{9}
$$

This is useful because the prime $p=n-2$ can now be distributed in residue classes modulo $a$.

For $a=\ell$, its possible $n$-classes are all classes except $2$; the primitivity restriction additionally excludes zero.

Define

$$
C_\ell(h)=
\frac1{\ell-1}
\sum_{\substack{b\bmod\ell\\b\ne0,2}}
e_\ell(-h\bar b),
\qquad e_q(t)=e^{2\pi it/q}.
$$

Inverting the nonzero residues gives the exact principal coefficient

$$
\boxed{
C_\ell(h)=
\frac{c_\ell(h)-e_\ell(-h\bar2)}
{\ell-1}.
}
\tag{10}
$$

The excluded residue $b=2$ is essential: it is precisely the condition that $n-2$ is a large prime.

The Siegel–Walfisz theorem applies uniformly because $\ell\le2L^{40}$. The number of opened classes and the kernel weight $L$ cause only fixed powers of $L$, absorbed by choosing sufficient logarithmic precision.

Consequently,

$$
P_\ell(X)=
\frac{2N_X}{\ell-1}
\left[-L+\log\ell-W_X(\bar2/\ell)\right]
+\mathcal E_\ell,
\tag{11}
$$

where

$$
\sum_{\ell\in\mathcal L}|\mathcal E_\ell|=o(N_X).
$$

Here the term $-L+\log\ell$ follows exactly from the shift mass at powers of $\ell$. No approximate evaluation of that mass is needed.

Evaluation of the remaining Fourier term

The required uniform estimate is

$$
\boxed{
W_X(\bar2/\ell)=-\log\ell+o(\log\ell).
}
\tag{12}
$$

I checked this using the classical prime exponential-sum estimate, as presented in Theorem 17.1 of Montgomery and Vaughan's Multiplicative Number Theory II. It bounds the rational-frequency sum at reduced denominator $q$ by

$$
\left|\sum_{m\le t}\Lambda(m)e(am/q)\right|
\ll
\left(\frac t{\sqrt q}+t^{4/5}+\sqrt{tq}\right)
\log^5(2t).
$$

The displayed logarithmic exponent is a harmless weakening of their stated estimate.

personal.science.psu.edu

To apply it, fix $\epsilon>0$ and divide the genuine prime labels into three ranges.

For $r\le\ell^{1-\epsilon}$, odd primes satisfy

$$
\cos(2\pi r\bar2/\ell)
=-\cos(\pi r/\ell)=-1+o(1)
$$

uniformly. Their harmonic logarithmic weight is

$$
(1-\epsilon)\log\ell+O(1).
$$

For $\ell^{1-\epsilon}<r\le\ell^{1+\epsilon}$, the total absolute weight is at most

$$
2\epsilon\log\ell+O(1).
$$

For $r>\ell^{1+\epsilon}$, partial summation of the exponential-sum estimate gives a bound

$$
\ll
\frac{L^6}{\sqrt\ell}
+\ell^{-(1+\epsilon)/5}(\log\ell)^5
+\ell^{-\epsilon/2}(\log\ell)^5
+o(1).
$$

This tends to zero uniformly for $\ell\asymp L^{40}$. The passage from von Mangoldt weights to genuine primes costs a negligible proper-power tail in this last range.

Finally, (2) handles the geometric redistribution at bounded cost.

Taking $X\to\infty$ first and then $\epsilon\downarrow0$ proves (12).

Substituting into (11),

$$
P_\ell(X)=
\frac{2N_X}{\ell-1}
\left[-L+2\log\ell+o(\log\ell)\right]
+\mathcal E_\ell.
$$

Mertens' theorem for prime reciprocals now gives

$$
\boxed{
\sum_{\ell\in\mathcal L}P_\ell(X)
\sim
-\frac{2\log2}{\log A}\,LN_X.
}
\tag{13}
$$

This is an unconditional negative contribution of order

$$
-\frac{X}{\log\log X}
$$

on all genuine shifted-prime endpoints. It is larger than the required twin-sensitive scale by a factor tending to infinity.

4. The companion moduli $2\ell$ reverse the conclusion

Before using (13), it is necessary to include the closely related inverse denominators $2\ell$.

Because every original endpoint $n$ is odd, CRT gives

$$
C_{2\ell}(h)=(-1)^h C_\ell(h\bar2).
\tag{14}
$$

In particular,

$$
C_\ell(h)+C_{2\ell}(h)
=
\frac{
(1+(-1)^h)c_\ell(h)
-e_\ell(-h\bar2)
-(-1)^he_\ell(-h\bar4)}
{\ell-1}.
\tag{15}
$$

This exhibits an exact degeneracy: the entire Ramanujan principal term cancels for every odd shift.

The even shifts are powers of two and have bounded total weight. Their Ramanujan sums at the odd prime $\ell$ are all $-1$. Their remaining contribution to (15) is therefore $O(1/\ell)$.

The decisive calculation for the odd shifts is

$$
\boxed{
W_X(\bar4/\ell)=o(\log\ell).
}
\tag{16}
$$

Its proof uses the same three ranges as (12). For the small-prime range, write

$$
\bar4=\frac{1+c\ell}{4},
\qquad c\in\{1,3\}.
$$

For odd $r$,

$$
\cos(2\pi r\bar4/\ell)=O(r/\ell),
$$

because the constant phase is an odd multiple of $\pi/2$. The intermediate and large ranges are controlled exactly as before.

Equations (12), (15) and (16) consequently give

$$
P_\ell(X)+P_{2\ell}(X)
=
\frac{2N_X}{\ell-1}
\left[\log\ell+o(\log\ell)\right]
+\mathcal E'_\ell,
$$

with summed error $o(N_X)$.

Thus

$$
\boxed{
\sum_{\ell\in\mathcal L}
\bigl(P_\ell(X)+P_{2\ell}(X)\bigr)
=
(2\log2+o(1))N_X.
}
\tag{17}
$$

The resulting contribution is positive, at precisely the scale needed to decide the twin-prime count.

This positive secondary term is not an upper-sieve artefact. It arises from the actual excluded residue $n=2\bmod\ell$, together with the prime exponential sums in (12) and (16).

Enlarging the prime-label bank

The preceding estimates hold uniformly for $A<\ell\le A^2$ as well.

Using this larger bank gives

$$
\sum_{\substack{A<\ell\le A^2\\\ell\text{ prime}}}
P_\ell(X)
\sim-2\log2\,X.
$$

But completing the twice-prime companions gives instead

$$
\boxed{
\sum_{\substack{A<\ell\le A^2\\\ell\text{ prime}}}
(P_\ell(X)+P_{2\ell}(X))
\sim2N_X\log A.
}
\tag{18}
$$

Thus increasing the bank amplifies the positive compensation after the leading cancellation. It does not amplify a surviving negative signal.

5. Repair attempt: complete the higher powers of two

I tested whether the positive contribution in (17) disappears upon including the additional inverse denominators

$$
4\ell,\ 8\ell,\ 16\ell,\ldots
$$

through any fixed polylogarithmic range.

For $k\ge2$, CRT and uniform distribution of the genuine primes in the permitted residue classes give

$$
C_{2^k\ell}(h)
=
\frac{c_{2^k}(h)}{\varphi(2^k)}
C_\ell(h\overline{2^k}).
$$

The first factor vanishes unless $2^{k-1}\mid h$.

Consequently, only the genuine even shifts $h=2^j$, with $j\ge k-1$, remain. For these shifts, (10) implies

$$
|C_\ell(h\overline{2^k})|
\le\frac2{\ell-1}.
$$

The geometric tail of the shift distribution gives

$$
\sum_{j\ge k-1}w_{2^j}\ll2^{-k}.
$$

Therefore

$$
\left|\sum_h w_h C_{2^k\ell}(h)\right|
\ll\frac{2^{-k}}{\ell}.
$$

Summing over the prime bank and all $k\ge2$ for which $2^k\le L^C$, where $C$ is any fixed constant, yields

$$
\boxed{
\sum_{\ell\in\mathcal L}
\sum_{\substack{k\ge2\\2^k\le L^C}}
P_{2^k\ell}(X)=o(N_X).
}
\tag{19}
$$

The reciprocity errors are summable because

$$
\sum_{\ell\in\mathcal L}\sum_{k\ge2}
\frac{N_X}{2^k\ell}
\ll\frac{N_X}{\log A}.
$$

Siegel–Walfisz remains applicable to every retained modulus.

Hence the positive term $2\log2\,N_X$ survives this natural completion. I have not extended (19) to arbitrary polynomial or larger powers of two.

6. A quantitative obstruction from the full primitive-frequency variation

There is a separate obstruction to controlling the remaining frequencies by absolute values or a standard energy estimate.

It can be proved directly on your complete kernel and the genuine shifted-prime source.

Put

$$
\Phi_X=\sum_{n\in\mathcal P_X}\varphi(n).
$$

Then

$$
\Phi_X\asymp XN_X.
\tag{20}
$$

For a quick proof of the lower bound, use

$$
\frac{\varphi(n)}n\ge
1-\sum_{q\mid n}\frac1q.
$$

On the shifted-prime population, Bombieri–Vinogradov evaluates the contribution of primes $q\le X^{1/4}$, giving the mean

$$
\sum_{q>2}\frac1{q(q-1)}+o(1)<\frac12.
$$

The contribution from larger prime divisors is uniformly $O(X^{-1/4})$, because there are at most four such divisors for large $X$.

This proves (20).

Limiting distribution of the kernel

The Fourier coefficients of $W_X$ converge individually to

$$
w_1^\infty=
\log(3/2)+\gamma+
\sum_r\frac{\log r}{r(r-1)}
$$

and

$$
w_{r^j}^\infty=(1-1/r)\frac{\log r}{r^j}.
$$

They define a nonzero, mean-zero function $W_\infty$ in $L^2([0,1])$.

Moreover, uniformly in $X$,

$$
\sum_{h>H}w_h^2
\le
\sum_{h>H}\frac{\Lambda(h)^2}{h^2}
\longrightarrow0.
\tag{21}
$$

For a fixed finite Fourier truncation, the empirical distribution over the primitive fractions of the actual $n$'s tends to the uniform distribution on the circle. Indeed, every fixed nonzero Fourier mode has normalized average

$$
\frac{\sum_{n\in\mathcal P_X}c_n(k)}{\Phi_X}
=o(1).
$$

For fixed $k\ne0$, the numerator is $O_k(N_X)$, using the elementary divisor formula for Ramanujan sums.

The tail can be controlled without assuming that the primitive frequencies are independent. On the full residue grid modulo $n$, Fourier orthogonality gives

$$
\sum_{a\bmod n}
\left|
\sum_{h>H}w_h\cos(2\pi ha/n)
\right|^2
\ll n\sum_{h>H}w_h^2.
$$

Here $h\le2X<2n$, so every residue frequency has bounded multiplicity, including the negative-frequency aliases.

Restricting to primitive residues only decreases this nonnegative quantity. Equations (20)–(21) then justify removing the truncation in mean square.

It follows that

$$
\boxed{
\frac1{\Phi_X}
\sum_{n\in\mathcal P_X}\sum_a^*
W_X(a/n)^2
\longrightarrow
\int_0^1W_\infty(\alpha)^2\,d\alpha>0.
}
\tag{22}
$$

Likewise, by the same truncation argument in $L^1$,

$$
\boxed{
\frac1{\Phi_X}
\sum_{n\in\mathcal P_X}\sum_a^*
|W_X(a/n)|
\longrightarrow
\int_0^1|W_\infty(\alpha)|\,d\alpha>0.
}
\tag{23}
$$

Since the limiting function has mean zero, the positive and negative masses individually satisfy

$$
\sum_{n,a}^*(W_X(a/n))_+
\asymp XN_X,
$$

$$
\sum_{n,a}^*(-W_X(a/n))_+
\asymp XN_X.
$$

This is an arithmetic result on the actual primitive frequencies, rather than a hypothetical random model.

Comparison with the required deficit

The positive and negative masses are each of order

$$
\frac{X^2}{\log X}.
$$

Their required difference is of order

$$
\frac X{\log X}.
$$

Therefore an argument estimating those two masses separately needs relative precision of order $1/X$, with a controlled sign.

The ordinary Cauchy–Schwarz budget from (22) is

$$
\sqrt{\Phi_X\sum_{n,a}^*W_X(a/n)^2}
\asymp XN_X,
$$

which exceeds the desired deficit by a factor of order $X$.

The exact common-kernel identity has eliminated composite contributions after complete signed summation, but it has not eliminated this large positive and negative spectral variation.

7. An exact test of whether the four-frequency deficit is intrinsically prime-sensitive

There is one additional diagnostic worth preserving.

For every odd $n$,

$$
c_n(1)=c_n(2)=\mu(n).
$$

Consequently, transferring a fixed positive weight $b$ from $h=1$ to $h=2$ leaves the complete primitive-frequency trace unchanged at every original endpoint.

The weights remain nonnegative, for example with $b=1/2$, because $w_1^\infty>1/2$.

But the four-frequency contribution changes by

$$
4b+O_b(X^{-2})
$$

at each $n$.

Thus the unconditional negative coefficient approximately $-0.55309$ from Section 2 can be changed to a positive coefficient approximately $1.44691$, while leaving the complete twin-prime identity exactly unchanged.

This does not invalidate the negative calculation. It demonstrates why the sign of that local deficit, by itself, is not evidence about primality.

8. The exact remaining obligation

Using the dyadic prime inverse-denominator bank and including the four small frequencies, let $R_X$ denote the contribution of every remaining primitive frequency.

The computations above establish

$$
\mathcal S_X
=
(2\log2-0.55308954\ldots+o(1))N_X+R_X.
$$

The coefficient is approximately $0.83320482$.

Accordingly, the following strict upper bound would suffice unconditionally:

$$
\boxed{
R_X\le-(1.22+\eta)N_X
}
\tag{24}
$$

for some fixed $\eta>0$ along an unbounded sequence. The constant $1.22$ safely exceeds the positive priced contribution plus the worst possible Möbius correction.

If Lü–Wang–Wu's stated cancellation theorem is valid, the sufficient threshold improves to

$$
R_X\le-(0.834+\eta)N_X.
$$

Neither bound has been established.

The genuine advance here is the evaluation of the growing prime inverse-denominator block and its compensating companions, including the secondary term at the exact twin-sensitive scale. It confirms that large negative spectral sectors exist unconditionally but that their natural completions cannot be omitted.

I chose the polylogarithmic inverse-denominator ranges and the higher-power completion independently. The calculations do not rely on the Chen filter, private research records or an unverified extension of v2. The remaining blocker is a one-sided estimate for the complete complementary primitive-frequency sum, not the construction of the prime projector itself.

No full twin-prime proof, paper preparation, file writing or third-party contact is claimed.

---

## Twin Prime Proof Attempt

[Original conversation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6b05cc9f-5a88-83ec-aa5a-bc3efa98591d)

### Recovered response 1

Research lane: gap-two Fourier filtering of the zeta mean square

The most promising result of this investigation is that Lee's particular window produces a strictly positive zero-diagonal contribution of order $X$, after cancelling the much larger $X\log X$ term. This gives a concrete one-sided inequality to attack on the remaining zero pairs.

However, the off-diagonal contribution has not been controlled. The calculation below also establishes why substituting the universal sine-kernel pair-correlation model at the required precision would be invalid.

1. Exact arithmetic target

I inspected the Fourier detector in §4 of Gou–Wang–Xu, arXiv:2611.18825 and the two-window construction in §3 of Lee, arXiv:2610.32672v2. Their Fourier identities are unconditional; their asymptotic evaluations require additional hypotheses.

borowiecki.dev+1

Fix a nonnegative, nonzero smooth function $W$ compactly supported in $(1,1.02)$. Define

$$
P_X(t)=\sum_n
\frac{\Lambda(n)}{n^{1/2+it}}W(n/X),
\qquad T=2\pi X.
$$

Let $r$ be a real Schwartz function of the appropriate Fourier support, and put

$$
H=\widehat{r^2},\qquad
g_\pm(v)=r(v)^2(1\pm\cos(4\pi v)).
$$

Both time windows are nonnegative. Set

$$
I_\pm(X)=\int_0^\infty
g_\pm(t/T)|P_X(t)|^2\,dt.
$$

The signed difference satisfies the exact identity

$$
\begin{aligned}
I_+(X)-I_-(X)
={}&T\sum_n
\frac{\Lambda(n)\Lambda(n+2)}
{\sqrt{n(n+2)}}\\
&\quad\times W(n/X)W((n+2)/X)\\
&\quad\times H\left(X\log(1+2/n)-2\right).
\end{aligned}
$$

The Fourier support excludes every other integer gap, and the common diagonal cancels exactly.

Consequently, an unconditional bound

$$
\boxed{I_+(X)-I_-(X)\ge cX}
$$

for some fixed $c>0$ along an unbounded sequence of $X$ would prove infinitely many twin primes. Contributions involving proper prime powers are $O(\sqrt X\log^2 X)=o(X)$.

Mere nonnegativity is insufficient because it follows from the arithmetic identity itself.

The common diagonal of the two windows is of order $X\log X$. Thus separate leading-order mean-square estimates, even if correct, need substantially greater precision to establish the required strict difference.

2. An unconditional reduction to a signed sum over zeros

This removes the need to assume RH merely to obtain a spectral formulation.

Write each nontrivial zero as $\rho=\beta+i\gamma$, counted with multiplicity, and put $a_\rho=\beta-\tfrac12$. Define

$$
g(v)=r(v)^2\cos(4\pi v),
\qquad I_g=\frac{I_+-I_-}{2}.
$$

For two zeros, let

$$
d=\gamma-\gamma',\qquad
m=\frac{\gamma+\gamma'}2,
$$

and

$$
A_{\rho,\rho'}(d)
=2\pi\int_0^\infty
W(u)^2u^{a_\rho+a_{\rho'}+id}\frac{du}{u}.
$$

Proved reduction, without RH or a ratios hypothesis:

$$
\begin{aligned}
I_g(X)=\frac12\sum_{\rho,\rho'}
&X^{a_\rho+a_{\rho'}}
e^{id\log X}
g(m/T)A_{\rho,\rho'}(d)\\
&+O_{W,g}(X^{3/5}\log^C X)
\end{aligned}
\tag{1}
$$

for a fixed constant $C$. The sum includes both positive and negative zero ordinates.

Derivation. The standard explicit formula gives

$$
P_X(t)=
X^{1/2-it}\widetilde W(1/2-it)
-\sum_\rho X^{\rho-1/2-it}
\widetilde W(\rho-1/2-it)
+E_X(t),
$$

where $E_X$ is the trivial-zero contribution and

$$
\widetilde W(s)=\int_0^\infty W(u)u^{s-1}\,du.
$$

The pole and trivial-zero terms contribute $o(1)$ to the filtered integral, using rapid Mellin decay and $g(v)=O(v^2)$ at zero.

Expanding the zero contribution, freeze the time window at the midpoint of each pair:

$$
g(t/T)\longrightarrow g(m/T).
$$

Parseval's identity then produces precisely the kernel $A_{\rho,\rho'}(d)$.

The error from freezing the window is bounded by

$$
\frac{C_K}{T}\sum_\rho
X^{2a_\rho}
(1+|\gamma|/T)^{-K}
\log(2+|\gamma|).
$$

Here one uses the uniform Schwartz bounds on the Mellin transforms, the zero count in unit intervals, and

$$
X^{a_\rho+a_{\rho'}}
\le \frac{X^{2a_\rho}+X^{2a_{\rho'}}}{2}.
$$

For $\beta\le3/4$, this error is $O(X^{1/2}\log^2 X)$. For $\beta>3/4$, Ingham's unconditional density estimate

$$
N(3/4,U)\ll U^{3/5}\log^5 U
$$

gives $O(X^{3/5}\log^C X)$ after summing dyadic heights.

arxiv.org

Thus the spectral conversion itself has an error smaller than the required arithmetic scale. The missing estimate is on the actual weighted zero-pair sum in (1), not on the conversion error.

3. A strictly positive contribution from the zero diagonal

There is a useful sign property of Lee's original window.

Take

$$
r(v)=\sin(\pi v/5)k(v),
$$

where $b=\widehat k$ is even, nonnegative, smooth and supported in $(-1/40,1/40)$. Put $K=b*b$ and $\delta=1/5$. Then

$$
H(y)=\frac12K(y)-\frac14K(y-\delta)
-\frac14K(y+\delta).
$$

Define

$$
L_g=\int_0^\infty g(v)\log v\,dv,
\qquad
C_W=\int_0^\infty W(u)^2\frac{du}{u}.
$$

The cosine transform of the logarithm gives

$$
L_g=-\frac14\int_{\mathbb R}
\frac{H(y)}{2+y}\,dy.
$$

Substituting the expression for $H$ and simplifying yields

$$
\boxed{
L_g=\frac{\delta^2}{8}
\int_{\mathbb R}
\frac{K(y)}
{(2+y)((2+y)^2-\delta^2)}\,dy>0.
}
\tag{2}
$$

Every denominator is positive on the support of $K$.

Now use the Riemann–von Mangoldt zero-counting formula. Since $\int_0^\infty g(v)\,dv=0$,

$$
2\pi C_W\sum_{\gamma>0}g(\gamma/T)
=T C_W L_g+O(\log T).
$$

This identifies a strictly positive arithmetic-scale contribution.

Without RH, the actual zero diagonal contains additional weights. Using the functional-equation symmetry $\beta\leftrightarrow1-\beta$, its exact decomposition is

$$
D_{\rm zero}=T C_W L_g+E_\beta+O(\log T),
$$

where

$$
\begin{aligned}
E_\beta=2\pi\sum_{\substack{\beta>1/2\\\gamma>0}}
g(\gamma/T)\int_0^\infty W(u)^2
\big[
&(Xu)^{2\beta-1}\\
+&(Xu)^{1-2\beta}-2
\big]\frac{du}{u}.
\end{aligned}
$$

The bracket is nonnegative. However, the time weight changes sign, so $E_\beta$ is not necessarily nonnegative.

Under RH, $E_\beta=0$. Unconditionally, it must be retained.

4. Extracting a genuine positive off-diagonal contribution

I tested whether the off-diagonal sum could itself supply a positive reserve using only zero counting and functional-equation symmetry.

A positive off-diagonal family can indeed be proved to exist unconditionally. Unfortunately, an equally large negative family also exists.

Choose a fixed interval $[a,b]\subset(0,\infty)$ on which $g\ge\eta>0$. Consider zeros with

$$
aT\le\gamma\le bT,\qquad \beta\ge\tfrac12.
$$

Functional-equation symmetry and the zero-counting formula give at least

$$
N\ge
\left(\frac{b-a}{4\pi}+o(1)\right)T\log T
$$

such zero labels.

Partition their ordinates into intervals of length $200/\log X$. Within each interval, partition the phases

$$
\gamma\log X\pmod{2\pi}
$$

into six equal arcs.

If the resulting cell populations are $n_j$, Cauchy–Schwarz gives

$$
\sum_j n_j(n_j-1)
\ge \frac{N^2}{\#\text{cells}}-N
\gg T\log T.
$$

Every ordered pair so obtained satisfies

$$
|d|\le\frac{200}{\log X},
\qquad \cos(d\log X)\ge\frac12.
$$

Consequently, for sufficiently large $X$,

$$
\operatorname{Re}
\left(e^{id\log X}A_{\rho,\rho'}(d)\right)
\ge \frac{2\pi}{3}C_W.
$$

Also $X^{a_\rho+a_{\rho'}}\ge1$ on these pairs. Their contribution is therefore positive and of magnitude

$$
\gg_{W,g}X\log X.
$$

Repeating the identical construction in an interval where $g\le-\eta'<0$ gives a negative contribution of magnitude $\gg_{W,g}X\log X$.

This is a calculation on the actual zeta zeros, not on a statistical comparison model. Multiplicities are retained in both families.

It establishes that the off-diagonal sum has substantial variation of both signs. Discarding its negative terms, or taking absolute values, cannot produce the required lower bound at scale $X$.

5. Where Montgomery's Fourier frequency actually falls

Under RH, the kernel in (1) simplifies to

$$
e^{id\log X}A(d)
=2\pi\int W(u)^2e^{id\log(Xu)}\frac{du}{u}.
$$

Using the conventional normalized zero spacing

$$
s=\frac{d\log T}{2\pi},
$$

the Fourier frequency is

$$
\alpha(u)=\frac{\log(Xu)}{\log T}.
$$

Since $T=2\pi X$,

$$
\boxed{
\alpha(u)=1-\frac{\log(2\pi/u)}{\log T}.
}
$$

For $1<u<1.02$, the Fourier support lies just below $1$, at distance $O(1/\log T)$, with width $O(1/\log T)$.

This distinction matters: it is not a fixed compact subinterval of the interior Montgomery range.

Montgomery's theorem, including the endpoint extension, supplies leading normalized pair-correlation information under RH. Its ordinary error scale is $o(T\log T)$, whereas the signed detector needs an error smaller than $T$.

public.websites.umich.edu+1

The shrinking Fourier interval does not automatically improve the error: its Fourier density increases proportionally to $\log T$, so its total mass stays fixed.

At a local height $t=Tv$, the normalization using the local zero density instead gives

$$
\alpha_{\rm local}(u,v)
=\frac{\log(Xu)}{\log(Xv)}.
$$

It exceeds $1$ whenever $u>v$. Thus localizing in the time variable also encounters the transition across the critical frequency.

6. A different window exposes a failure of the universal sine-kernel shortcut

I tested whether sufficiently accurate local sine-kernel statistics might nevertheless predict a strictly positive signed mean.

This produces a decisive countercheck.

Consider the usual local sine-kernel comparison at zero density

$$
\rho(t)=\frac1{2\pi}\log\frac{t}{2\pi}.
$$

Its off-diagonal pair density is

$$
\rho(t)^2
\left[
1-\left(\frac{\sin(\pi\rho(t)d)}
{\pi\rho(t)d}\right)^2
\right].
$$

Combining its Fourier transform with the zero diagonal gives the following model prediction for our detector:

$$
\frac{I_g^{\rm model}(X)}{T}
\longrightarrow
\int W(u)^2\frac{du}{u}
\int_0^\infty
g(v)\min(\log v,\log u)\,dv.
\tag{3}
$$

The calculation uses the triangular Fourier transform of the squared sinc function. Because $\int g=0$, the inner expression becomes

$$
\int_0^u g(v)\log(v/u)\,dv.
$$

Now choose a different valid Fourier window,

$$
g_{\epsilon,h}(v)
=v^2k(\epsilon v)^2\cos(2\pi hv),
$$

where $k$ has compactly supported smooth Fourier transform and $k(0)>0$.

For fixed sufficiently small $\epsilon>0$, this still isolates the single gap $h$, after choosing the spatial support of $W$ sufficiently close to $1$.

At $u=1$, the inner expression in (3), as $\epsilon\downarrow0$, tends to

$$
k(0)^2\int_0^1v^2\cos(2\pi hv)\log v\,dv.
$$

With $A=2\pi h$, direct integration by parts gives

$$
\int_0^1v^2\cos(Av)\log v\,dv
=\frac1{A^2}+\frac{2\operatorname{Si}(A)}{A^3}>0.
$$

Here

$$
\operatorname{Si}(A)=\int_0^A\frac{\sin t}{t}\,dt,
$$

which is positive at every positive integer multiple of $2\pi$.

By continuity, the model therefore predicts a strictly positive contribution of order $X$ for both $h=2$ and $h=1$.

But the actual gap-one detector satisfies

$$
I_{g_{\epsilon,1}}(X)=o(X)
$$

unconditionally: sufficiently large consecutive integers cannot both be ordinary primes, and proper prime powers have negligible contribution.

This establishes a precise failure of the proposed statistical replacement. The universal sine-kernel approximation, if extrapolated to this detector with an $o(X)$ error, would give a false answer even for gap one.

It does not refute ordinary pair-correlation statistics. It shows that arithmetic-dependent corrections at the next order are indispensable.

7. Dyadic averaging and the functional equation

Averaging over $Y<X<2Y$ preserves the exact arithmetic detector. In the zero-pair expression, a fixed pair acquires the multiplier

$$
\int_1^2
v^{a_\rho+a_{\rho'}+id}
g\left(\frac{m}{2\pi Yv}\right)\frac{dv}{v}.
$$

For the closely spaced zero pairs used above,

$$
|d|\ll1/\log Y,
$$

and hence

$$
v^{id}=1+O(1/\log Y)
$$

uniformly throughout the averaging interval.

Thus ordinary dyadic averaging does not provide an oscillatory cancellation mechanism for these pairs. Moreover, the gap-one failure of the sine-kernel replacement survives the same dyadic averaging at order $Y$.

The functional equation also supplies no additional independent main term in the exact Mellin calculation. On shifting the logarithmic derivative to the left, its reflected Dirichlet-series contribution contains the inverse Mellin weight

$$
W\left(\frac1{Xn}\right)=0.
$$

The remaining archimedean and residue terms reconstruct the explicit formula already used in (1). They do not remove the signed zero-pair remainder.

Exact remaining proof obligation

Let $O_X$ denote the complete off-diagonal sum in (1), including multiplicities. The unconditional calculation gives

$$
\boxed{
I_g(X)=T C_WL_g+E_\beta+O_X+o(X).
}
$$

The constant $C_WL_g$ is strictly positive by (2).

It would therefore suffice to establish, along an unbounded sequence,

$$
\boxed{
E_\beta+O_X\ge-\frac12T C_WL_g.
}
$$

This is the specific one-sided spectral estimate worth pursuing instead of assuming the full ratios conjecture.

Research verdict: the unconditional spectral conversion, positive diagonal baseline, positive and negative off-diagonal families, and gap-one countercheck survive the calculation. The final strict signed inequality remains unproved. In particular, neither RH alone nor the leading pair-correlation statistics justify dropping $E_\beta+O_X$.

I chose the explicit-formula and alternative-window tests within the assigned lane. No project files, other chats, downloads, installations or external messages were used. Direct arXiv retrieval and PDF screenshot access failed; the relevant author-text passages were available through public mirrors. The new derivations have not received an independent mathematical audit, and no complete twin-prime proof is claimed.

---

### Recovered response 2

Maynard cluster route: a quantitative obstruction and a parity-sensitive repair

The first calculation gives a rigorous limitation: adding arbitrarily many auxiliary translates to a Maynard tuple cannot, by itself, force a twin-prime pair through the usual weighted prime-count lower bound.

There is a more targeted repair using Liouville weights. It yields an explicit inequality involving only a selected pair's weighted parity and prime–parity correlations, rather than the full collection of distribution conjectures in Pintz's theorem. I have not proved that inequality for the actual integers.

1. The forbidden pattern inside an admissible tuple

Let $\mathcal H=\{h_1,\ldots,h_k\}$ be a fixed admissible tuple of distinct integer translates. Write

$$
P_i(n)=1_{\mathbb P}(n+h_i).
$$

Connect vertices $i,j$ whenever $|h_i-h_j|=2$.

Lemma. This graph is necessarily a matching together with isolated vertices.

Indeed, two incident edges would require three translates

$$
h,\quad h+2,\quad h+4.
$$

They occupy every residue class modulo 3, contradicting admissibility.

Suppose, for contradiction, that only finitely many twin primes exist. For all sufficiently large $n$,

$$
P_i(n)+P_j(n)\le1
$$

on every edge.

If the matching contains $r$ pairs, with $k-2r$ additional translates, the total number of primes can still be as large as

$$
\sum_{i=1}^kP_i(n)\le k-r.
$$

In particular, for $k=2r$, a cluster containing $r$ primes is entirely consistent with the absence of twins.

More generally, for arbitrary nonnegative coefficients $c_i$, the exact combinatorial ceiling is

$$
\boxed{
\sum_i c_iP_i(n)
\le
\sum_{\{i,j\}\in E}\max(c_i,c_j)
+\sum_{i\text{ isolated}}c_i.
}
\tag{1}
$$

Changing the relative importance of the endpoints therefore does not remove the forbidden-pattern obstruction. A successful proof needs a weighted arithmetic mean exceeding this ceiling, or a different observable.

2. A stronger obstruction from the Maynard variational problem

Let $w_X(n)\ge0$ be an ordinary Maynard–Selberg weight, with simplex-supported function $F$, cutoff $R=X^\rho$, and $\rho<\theta/2$, where $\theta$ is the available prime distribution exponent.

Normalize the weight to a probability measure, writing

$$
\mathbb E_w f=
\frac{\sum_{X<n\le2X}w_X(n)f(n)}
{\sum_{X<n\le2X}w_X(n)}.
$$

Maynard's Proposition 4.1 gives

$$
\mathbb E_w P_i
=\rho\frac{J_i(F)}{I(F)}+o(1),
$$

where

$$
I(F)=\int F^2,\qquad
J_i(F)=\int\left(\int F\,dt_i\right)^2dt_{\ne i}.
$$

The support condition is $\sum_i t_i\le1$.

arxiv.org

For any selected pair of coordinates $i,j$, independently of the number of auxiliary coordinates, one has

$$
\boxed{J_i(F)+J_j(F)\le2\log2\,I(F).}
\tag{2}
$$

Proof. Freeze all other coordinates and put $s=1-\sum_{\ell\ne i,j}t_\ell$. The remaining domain is the triangle $x+y\le s$.

Weighted Cauchy–Schwarz gives

$$
\left(\int_0^{s-y}F(x,y)\,dx\right)^2
\le
\log2\int_0^{s-y}
(s-y+x)F(x,y)^2\,dx.
$$

The analogous inequality in $y$ has multiplier $s-x+y$. Adding the two multipliers gives $2s\le2$. Integration over the frozen coordinates proves (2).

It follows that

$$
\mathbb E_w(P_i+P_j)
\le2\rho\log2+o(1).
$$

Distribution input
 |
Upper bound for the pair's mean prime count
 |

Ordinary Bombieri–Vinogradov, $\theta=1/2$
 |
$0.346574+o(1)$
 |

Elliott–Halberstam, $\theta=1$
 |
$0.693148+o(1)$
 |

Required to contradict absence of twins directly
 |
Greater than $1$
 |

Combining (2) with the individual bound $J_i\le I$ for isolated vertices proves that no nonnegative linear score of the form (1) can attain the necessary mean through these ordinary simplex-supported weights.

This is a rigorous statement about this variational framework, not an impossibility theorem for every generalized sieve weight.

3. What the exact Polymath8b parity argument establishes

I inspected §8, equations (142)–(148), and Remark 8.1 of Polymath8b, arXiv:1407.4897v4.

For the admissible triple $\{0,2,6\}$, the authors consider the nonnegative multiplier

$$
\begin{aligned}
\omega(n)
&=(1-\lambda(n)\lambda(n+2))
(1-\lambda(n+2)\lambda(n+6))\\
&=1-\lambda(n)\lambda(n+2)
-\lambda(n+2)\lambda(n+6)\\
&\qquad+\lambda(n)\lambda(n+6).
\end{aligned}
$$

It vanishes whenever either of the two forbidden simultaneous-primality patterns occurs. For twins alone the multiplier is simply $1-\lambda(n)\lambda(n+2)$.

Their argument is that the conjecturally available linear progression estimates should persist under this reweighting, while the desired prime pattern disappears. They explicitly describe the general transfer argument as heuristic. They do not prove that all possible new sieve inputs are powerless.

arxiv.org+1

For our disjoint-pair tuple, the corresponding multiplier is

$$
\omega_E(n)=
\prod_{\{i,j\}\in E}(1-\lambda_i(n)\lambda_j(n)),
$$

where $\lambda_i(n)=\lambda(n+h_i)$.

It annihilates every twin-containing configuration. Its expansion, however, contains Liouville products of orders up to $2r$. Ordinary two-point cancellation does not justify transferring all the required arithmetic progression estimates.

4. The optimal elementary Liouville repair

For one selected pair, write

$$
\begin{aligned}
A&=\mathbb E_w(P_i+P_j),\\
B&=\mathbb E_w(P_i\lambda_j+P_j\lambda_i),\\
C&=\mathbb E_w(\lambda_i+\lambda_j),\\
D&=\mathbb E_w(\lambda_i\lambda_j).
\end{aligned}
$$

Instead of suppressing equal parities, select both endpoints having odd factor parity using the nonnegative multiplier

$$
V=(1-\lambda_i)(1-\lambda_j).
$$

Because $\lambda_i=-1$ whenever $P_i=1$,

$$
\mathbb E_w[V(P_i+P_j)]=2(A-B),
\qquad
\mathbb E_w V=1-C+D.
$$

Absence of twins implies the following exact inequality:

$$
\boxed{2(A-B)\le1-C+D.}
\tag{3}
$$

Thus a strict violation of (3) on an unbounded sequence would suffice.

The obstruction is quantitative. Even assuming perfect weighted parity cancellation $B=C=D=0$, one still needs $A>1/2$. At the ordinary Bombieri–Vinogradov level, (2) gives only $A\le0.346574+o(1)$.

With $C,D=o(1)$, a sufficient mixed prime–Liouville estimate would have to give

$$
B<A-\frac12.
$$

Even at the most favorable variational upper bound this requires a negative bias exceeding $0.153426$ in normalized units. Ordinary cancellation $B=o(1)$ is not enough.

In Pintz, arXiv:1004.1067, §§2–3, the parity filter is precisely $V$. His hypotheses control primes, Liouville, the shifted Liouville pair, and both prime-supported shifted Liouville sequences in progressions.

For the simplest two-coordinate GPY weight, perfect cancellation leads to the threshold $\theta>3/4$. Optimizing a linear combination of its two profiles instead gives the condition

$$
\theta\left(\frac43+3u+\frac95u^2\right)
>
1+2u+\frac32u^2.
$$

The maximizing parameter is

$$
u=\frac{\sqrt{34}-2}{9},
$$

and the resulting sufficient distribution exponent is $0.7231$, as stated in §3.

arxiv.org+1

This independently confirms the barrier encountered in (3): ordinary BV-level distribution, even augmented by perfect cancellation of these particular signed moments, does not reach the required score.

5. Exact countermodel for the proposed cluster inference

There is a finite probability construction showing that the obstruction is not merely a weak numerical optimization.

Suppose the desired prime marginals in a pair are $p_i,p_j$, with

$$
p_i+p_j\le\frac12.
$$

Choose the two Liouville signs independently and uniformly. Conditional on both signs being negative, choose endpoint $i$ to be prime with probability $2p_i$, endpoint $j$ with probability $2p_j$, and neither otherwise. These choices are mutually exclusive.

When only one sign is negative, choose that endpoint with its corresponding probability $2p_i$ or $2p_j$.

This construction has all of the following properties:

-

The prescribed prime marginals are reproduced exactly.

-

The Liouville signs are independent and unbiased.

-

Every mixed moment involving one prime indicator and any nonempty product of other Liouville signs vanishes.

-

The probability of simultaneous primality is zero.

Taking independent copies across the matching gives the same conclusion for arbitrarily many pairs, including all higher-order pure sign moments.

At the BV level the bound (2) ensures that these countermodel probabilities are feasible.

This is an information countermodel, not an arithmetic counterexample involving actual primes. Its significance is that additional parity equidistribution alone, without a stronger prime-sensitive statistic, cannot force the forbidden pattern from the known cluster means.

6. A different repair: a signed Jordan detector supported by Chen's theorem

The preceding obstruction suggests changing the arithmetic observable rather than adding more translates.

Take just the pair $\{0,2\}$, write $L=\log X$, and fix

$$
\rho=\frac1{20},\qquad R=X^\rho.
$$

Use the normalized two-coordinate GPY–Selberg weight

$$
w_R(n)=
\left[
\sum_{\substack{d\mid n(n+2)\\d\le R}}
\mu(d)
\left(\frac{\log(R/d)}{\log R}\right)^2
\right]^2.
$$

It equals one whenever both endpoints have no prime factor at most $R$.

Set

$$
K_0=2\prod_{p>2}
\left(1-\frac1{(p-1)^2}\right).
$$

The ordinary GPY mean, which is unconditional at this cutoff, gives

$$
\sum_{X<p\le2X}w_R(p)
=
\left(\frac{4K_0}{3\rho}+o(1)\right)
\frac{X}{L^2}.
\tag{4}
$$

Here and below, a summation variable $p$ denotes a genuine prime. This follows from the $k=2,\ell=0$ specialization of Lemma 2 in Pintz's paper.

arxiv.org

For a fixed small positive $c$, put $\sigma=c/L$ and introduce the multiplicative detector

$$
\begin{aligned}
A_\sigma(m)
&=\sum_{d\mid m}\mu(d)(m/d)^{-\sigma}\\
&=m^{-\sigma}\prod_{q\mid m}(1-q^\sigma).
\end{aligned}
\tag{5}
$$

On squarefree integers this equals the Liouville function multiplied by the Jordan-type weight

$$
\prod_{q\mid m}(1-q^{-\sigma}).
$$

Using (5) rather than that expression directly has the advantage that prime powers and repeated factors remain covered by an exact convolution identity.

Define the full signed statistic

$$
\boxed{
M_c(X)=\sum_{X<p\le2X}w_R(p)A_{c/L}(p+2).
}
\tag{6}
$$

For every sufficiently small fixed $c>0$,

$$
\boxed{
\liminf_{X\to\infty}\frac{L^2}{X}M_c(X)\le0
}
\tag{7}
$$

would imply infinitely many twin primes.

Unlike (3), this asks for a nonpositive signed correlation rather than a large negative bias in an unweighted Liouville statistic.

Proof. The quantitative rough version of Chen's theorem supplies a constant $\kappa>0$ such that, for sufficiently large $X$,

$$
\#\left\{
\begin{array}{l}
X<p\le2X,\ p\text{ prime},\\
\Omega(p+2)\le2,\\
P^-(p+2)>X^{1/8}
\end{array}
\right\}
\ge\kappa\frac{X}{L^2}.
$$

The classical proof is given by Halberstam; the dyadic rough version is explicitly derived in Tao's exposition of Chen's theorem.

numdam.org+1

Suppose there are only finitely many twins. After removing negligible prime-square exceptions, these Chen neighbors are products $ab$ of two distinct primes exceeding $X^{1/8}$.

On this population, $w_R(p)=1$, and

$$
A_\sigma(ab)
=(1-a^{-\sigma})(1-b^{-\sigma})
\ge(1-e^{-c/8})^2
\ge\frac{c^2}{256}
$$

for $0<c\le1$.

Every integer with an even number of distinct prime factors contributes nonnegatively to (6).

A negative composite contribution, apart from proper prime powers, requires at least three distinct prime factors. By the arithmetic–geometric mean inequality applied to their logarithms,

$$
|A_\sigma(m)|
\le
\left(\frac{\sigma\log m}{3}\right)^3
=
\frac{c^3}{27}(1+o(1)).
$$

Proper prime powers contribute $o(X/L^2)$.

Consequently, using (4),

$$
\frac{L^2}{X}M_c(X)
\ge
\frac{\kappa c^2}{256}
-\frac{4K_0}{81\rho}c^3
+o(1).
\tag{8}
$$

For sufficiently small fixed $c$, the right-hand side is strictly positive. This contradicts (7).

This establishes the claimed implication unconditionally. The inequality (7) itself remains to be proved.

7. An unconditional negative main term for the new statistic

The following calculation addresses part of (7) directly.

Split the convolution in (5) at

$$
D=X^{1/5}.
$$

Write

$$
M_c=M_{\mathrm{short}}+M_{\mathrm{long}},
$$

where

$$
M_{\mathrm{short}}
=
\sum_{X<p\le2X}w_R(p)(p+2)^{-\sigma}
\sum_{\substack{q\mid p+2\\q\le D}}\mu(q)q^\sigma.
$$

All opened moduli in this sum are at most

$$
R^2D=X^{3/10}.
$$

Thus the entire short part lies comfortably within ordinary Bombieri–Vinogradov.

Put

$$
a_d=\mu(d)
\left(\frac{\log(R/d)}{\log R}\right)^2
$$

for $d\le R$, and zero otherwise. Define the finite coefficient

$$
\mathcal B_X(c)=
\sum_{\substack{d,e\le R\\d,e\text{ odd}}}
a_da_e
\prod_{q\mid[d,e]}
\frac{1-q^\sigma}{q-1-q^\sigma}.
$$

Proved estimate:

$$
\boxed{
M_{\mathrm{short}}
=
-K_0ce^{-c}\mathcal B_X(c)
\frac{X}{L^2}
+o_c(X/L^2).
}
\tag{9}
$$

Moreover,

$$
\mathcal B_X(c)
=
1+\frac7{15}\rho c
+O((\rho c)^2)+o_X(1).
\tag{10}
$$

In particular, for sufficiently small fixed $c$, the short part is strictly negative at the required arithmetic scale.

For a prime $p>X$, every divisor at most $R$ of $p(p+2)$ divides $p+2$. Expanding the square and applying BV therefore gives

$$
M_{\mathrm{short}}
=
J_\sigma(X)
\sum_{\substack{d,e\le R\\d,e\text{ odd}}}
a_da_e
\sum_{\substack{q\le D\\q\text{ odd}}}
\frac{\mu(q)q^\sigma}{\varphi([d,e,q])}
+O_A(X/L^A),
$$

where

$$
J_\sigma(X)=\int_X^{2X}
\frac{(t+2)^{-\sigma}}{\log t}\,dt
\sim e^{-c}\frac XL.
$$

There is no coprimality assumption between $d,e,q$. Each opened modulus has multiplicity at most $7^{\omega(m)}$, which is absorbed by divisor moments and BV at sufficiently high logarithmic precision.

Let $\ell=[d,e]$ and factor $q=q_1q_2$, with $q_1\mid\ell$ and $(q_2,\ell)=1$. The relevant coprime Dirichlet series is

$$
\sum_{\substack{n\ge1\\(n,2\ell)=1}}
\frac{\mu(n)n}{\varphi(n)n^s}
=\frac{E_\ell(s)}{\zeta(s)}.
$$

Its Euler factors give

$$
E_\ell(s)=E_1(s)
\prod_{p\mid\ell}
\left(1-\frac{p^{1-s}}{p-1}\right)^{-1},
\qquad E_1(1)=K_0.
$$

The required uniform truncation statement is

$$
\sum_{\substack{n\le Y\\(n,2\ell)=1}}
\frac{\mu(n)n^\sigma}{\varphi(n)}
=
\frac{E_\ell(1-\sigma)}{\zeta(1-\sigma)}
+O_A(L^{-A})
\tag{11}
$$

for $X^{1/10}\le Y\le D$ and $\ell\le R^2$.

To justify (11), expand $E_\ell$ into its absolutely convergent Dirichlet series at real part $1/2$, and convolve with $\mu$. The excluded-prime factors have absolute norm at most $\exp(O(\sqrt L))$ there and polylogarithmic norm at $1-\sigma$.

For the Möbius convolution with argument at least $\sqrt Y$, the classical Mertens estimate permits Taylor expansion in $\sigma=c/L$ to any fixed order, with error of arbitrary logarithmic precision. The coefficients are the convergent logarithmic moments of $\mu(n)/n$, namely the Taylor coefficients of $1/\zeta(1-\sigma)$. The complementary convolution tail is power-small.

The application is uniform because

$$
D/q_1\ge D/R^2=X^{1/10}.
$$

Summing the retained $q_1$ gives the exact factor

$$
\prod_{p\mid\ell}(1-p^\sigma).
$$

Combining this with $1/\varphi(\ell)$ gives precisely the denominator $p-1-p^\sigma$ in $\mathcal B_X(c)$. Using

$$
\frac1{\zeta(1-\sigma)}
=-\sigma+O(\sigma^2)
$$

proves (9).

For (10), the term $d=e=1$ is one. The total absolute contribution from $\ell$ containing at least two distinct primes is $O((\rho c)^2)$, by comparison with

$$
\prod_{p\le R,\ p>2}
\left(1+3\frac{p^\sigma-1}{p-1-p^\sigma}\right).
$$

For $\ell=p$, writing $u=\log p/\log R$, the combined coefficient from its three divisor assignments is $-2(1-u)^2+(1-u)^4$.

Mertens' prime harmonic formula then evaluates the first-order contribution as

$$
\rho c\int_0^1
\left[2(1-u)^2-(1-u)^4\right]du
=\frac7{15}\rho c.
$$

This proves the stated expansion.

8. Testing the remaining long part

The exact complementary expression is

$$
M_{\mathrm{long}}
=
\sum_{\substack{qt-2\text{ prime}\\
X<qt-2\le2X\\q>D}}
\mu(q)t^{-\sigma}w_R(qt-2).
\tag{12}
$$

The unit $t=1$ remains included.

I tested whether the negative short main could be combined with an elementary sign estimate for (12). The following two actual arithmetic populations rule out that shortcut.

Negative long-tail population. Require every prime factor of $m=p+2$ to exceed $D$. The classical lower linear sieve gives $\gg X/L^2$ such primes $p$, since the available sieve ratio is $0.49/0.20>2$.

On this population $w_R(p)=1$, and the short divisor sum is just $m^{-\sigma}$. Since

$$
|A_\sigma(m)|\le1-m^{-\sigma},
$$

the long contribution at each such integer is at most

$$
1-2m^{-\sigma},
$$

which is bounded above by a negative constant for sufficiently small $c$.

Positive long-tail population. Require

$$
p+2=av,\qquad
X^{0.06}<a<X^{0.07},
$$

where $a$ is prime and every prime factor of $v$ exceeds $D$.

This population also has size $\gg X/L^2$, unconditionally. To see this, sift the actual primes $p\equiv-2\pmod a$ with residual level $X^{0.41}$. The total opened modulus is at most $X^{0.48}$, and the sieve ratio is $0.41/0.20=2.05>2$. Sum over $a$ using its positive harmonic mass. Repeated-$a$ exceptions cost a power saving.

Again $w_R(p)=1$. The complete short sum is now

$$
m^{-\sigma}(1-a^\sigma),
$$

which is negative with magnitude $\gg c$. Meanwhile $|A_\sigma(m)|=O(c^2)$, because $m$ has at least two distinct prime factors. Hence the long contribution is positive and $\gg c$ for sufficiently small fixed $c$.

Both populations consist of actual shifted primes; no independent-factor model was assumed.

These estimates establish substantial variation of opposite signs in the long part. They do not establish the net signed upper required by (7).

There is also an exact cancellation check at $c=0$: the complete convolution $A_0(m)$ vanishes for every $m>1$. Thus the zeroth-order short and long means cancel identically. Counting large positive or negative populations without controlling their complement cannot settle the small-$c$ signed inequality.

9. Can the current two-point correlation results finish the repair?

I checked the stated scope of the September 2026 manuscript Ordinary two-point correlations of multiplicative functions.

Its quantitative Liouville result treats fixed affine forms and fixed progression moduli, with a power-of-logarithm saving. Its general bounded multiplicative-function theorem is qualitative.

github.com+1

Even granting those results in full, three mathematical mismatches remain:

-

The Selberg-weight expansion involves polynomially growing moduli, not fixed progressions.

-

The long sum (12) contains genuine prime support $qt-2$, which is not a bounded multiplicative function of $q$.

-

The prime-sensitive parameter $\sigma=c/\log X$ moves with $X$, and the required signed precision is $X/\log^2 X$, not merely $o(X)$.

Taking $\sigma$ fixed does not repair the third point. For a product of two or three polynomial-sized primes, $|A_\sigma(m)|$ then tends to one, destroying the small-parameter separation between semiprimes and higher-rank composites used in (8).

There is a further concrete test of the sparse-support problem. Delete from the prime sequence every prime $p$ for which $p+2$ is prime. Brun's upper bound shows that this removes only $O(X/L^2)$ primes in a dyad. Every unweighted prime-supported correlation of a bounded function known to accuracy $o(X/L)$ can survive that deletion, while all twin pairs disappear.

For (6), however, every deleted twin has weight $w_R(p)=1$ and detector value of order $-c$. The potentially invisible change is exactly at the decisive $X/L^2$ scale.

This is not a counterexample to a stronger progression theorem. It demonstrates why qualitative cancellation on shifted primes, even if available, cannot automatically provide the needed weighted estimate.

Precise surviving research target

The strongest repair from this lane is the signed statistic (6), with its unconditional short-divisor evaluation (9).

For a sufficiently small fixed $c>0$, it would suffice to prove, along unbounded dyadic scales,

$$
\boxed{
M_{\mathrm{long}}(X)
\le
\left[
K_0ce^{-c}\mathcal B_X(c)+o(1)
\right]\frac{X}{L^2}.
}
$$

This genuinely changes the required inputs from Pintz's common distribution exponent above $0.7231$: ordinary BV and Chen's theorem already supply the other components. The remaining input is one specific signed prime-supported convolution estimate, including all complementary factors.

Status: the combinatorial obstruction, variational bound, parity countermodel, Jordan implication, and short-divisor calculation have been derived. The full long-divisor inequality is unproved, so twin-prime infinitude has not been established.

I chose the smaller GPY cutoff and signed Jordan convolution to replace the unsuccessful cluster-score strategy. No local files, project files, other chats, downloads or installations were used. Polymath's relevant PDF pages were inspected directly; Pintz's PDF text was accessible, although its page screenshots failed. The recent shifted-prime Möbius preprint could not be reopened, so I have not assumed its claims. The new calculations have not undergone independent agent or external verification, and no novelty claim is made.

---

### Recovered response 3

Section 7 audit — Moreno Borrallo's claimed proof

Verdict: the argument inspected does not establish the twin-prime conjecture. The critical unresolved step is the transition from an explicitly constructed local density to a negligible centered remainder on the genuine one-prime stratum.

I found an exact formula identifying the missing contribution. It cannot be removed by the short-variable switching argument of Proposition 7.16. I also distinguish this problem from a separate inconsistency in the normalization of the conserved density.

I inspected the author-uploaded text of A Parity-Sensitive Liouville Decomposition for Binary Prime Correlations, particularly Definitions 7.5 and 7.7, Propositions 7.6, 7.14, 7.16 and 7.21, Lemmas 7.17–7.19, and equations (62)–(66). ResearchGate's publication identifier now also resolves to a differently titled manuscript, so the audit refers specifically to the indexed version containing the requested Section 7 statements.

researchgate.net+2

1. The actual one-prime row

Specialize to $T=2,\ \varepsilon=+1$, and write

$$
z=X^{\beta_0},
\qquad
\beta_0=\frac{57}{224}-10^{-3}.
$$

Use a nonnegative smooth window $W(n/X)$ in the interior of the paper's top-aligned interval. Put

$$
\omega_W=\int W(u)\,du>0,\qquad
L=\log X.
$$

For this audit, define $N_j(X)$ to be the weighted count of integers $n$ satisfying

$$
P^-(n)>z,\qquad \Omega(n)=j,\qquad n+2\text{ prime}.
$$

Here the weight is $W(n/X)$, and $\Omega$ counts prime factors with multiplicity.

The exact rough-support decomposition is

$$
\begin{aligned}
R_z&=N_1+N_2+N_3,\\
L_z&=-N_1+N_2-N_3,\\
T_{3,z}&=N_3.
\end{aligned}
$$

Consequently,

$$
\frac{R_z-L_z}{2}-T_{3,z}=N_1.
$$

This identity is correct. The term $N_1$ is precisely the genuine twin-prime count in the chosen window.

The important distinction is that the ordinary prime density

$$
\sum_p W(p/X)\sim\frac{\omega_W X}{L}
$$

is established by the prime number theorem, whereas

$$
N_1(X)=\sum_p W(p/X)1_{\mathbb P}(p+2)
$$

is the unknown binary prime correlation.

2. Lemmas 7.17 and 7.19: the exact point of separation

Lemma 7.17, equation (63), evaluates the subtracted model $Z$ as

$$
Z=
\left[-I_1(\beta_0)+I_2(\beta_0)
-I_3(\beta_0)+o(1)\right]
\frac{\omega_W X}{L^2},
$$

with

$$
I_1=1,\qquad
I_2=\log\frac{1-\beta_0}{\beta_0}.
$$

Lemma 7.19 then discards the negative triprime component to obtain

$$
c_\lambda^{\mathrm{loc},+}
=-1+\log\frac{1-\beta_0}{\beta_0}.
$$

These are legitimate ordinary rough-integer comparison constants. The calculation of $I_2$ is not itself problematic.

The difficulty is the use of the prime model from Definition 7.5. In the proof of Lemma 7.17, the author approximates the model attached to a rough integer $n$, with conductor $K\mid n$, by

$$
\frac{K}{\varphi(K)}
\frac{W(n/X)}{L}.
$$

The factor $K/\varphi(K)=1+O(X^{-\beta_0})$ is indeed valid when $K$ is rough and $K\ll X$.

researchgate.net

But this evaluates only the model. It does not evaluate the conditional primality of $n+2$.

On the one-prime stratum, $K\mid p$ forces $K=1$ or $K=p$. In either case, under the single-window convention of Lemma 7.17, the negative model contribution is

$$
Z_1=-\frac{\omega_W X}{L^2}
+o(X/L^2).
$$

The actual negative contribution is $-N_1(X)$.

Therefore the centered one-prime contribution is necessarily

$$
\boxed{
E_1(X)=
\frac{\omega_W X}{L^2}
-N_1(X)+o(X/L^2).
}
\tag{A}
$$

This is the missing term.

In particular, if only finitely many twin primes exist,

$$
E_1(X)\sim\frac{\omega_W X}{L^2}>0.
$$

It is then of precisely the scale the paper must control, rather than an arbitrarily logarithmically small error.

I do not identify the evaluation of the artificial model alone with a circular assumption of twin primes. The unjustified transfer would be to establish its value and then remove (A) without a valid arithmetic estimate. That is the distinction that must be preserved throughout the audit.

3. Proposition 7.16 does not cover the genuine one-prime row

Proposition 7.16 asserts arbitrary logarithmic savings for four exceptional classes, relying on Lemmas 7.12–7.13 and Proposition 7.14.

The short-live switching argument in Proposition 7.14 requires retained exterior cofactors with exponents satisfying

$$
\rho,\sigma\ge\beta_0-o(1),
\qquad
\rho+\sigma+\gamma+\ell=1+o(1).
$$

These hypotheses are essential to the subsequent complementary-modulus calculation in Lemma 7.15.

researchgate.net+1

But for a genuine prime $n=p$, any factorization

$$
p=rsc\ell
$$

has exactly one nonunit factor.

In particular, there cannot be two exterior factors $r,s\ge z$. The prime row cannot be put inside the retained two-exterior-cofactor switching argument.

There are only two relevant alternatives.

Alternative A: retain $K=p$, with live variable $\ell=1$.

The prime terminal is $p+2$. The progression modulus is of size $X$, and its live interval contains only a bounded number of integers.

The prediction $K/\varphi(K)$ does not give an unconditional asymptotic for this short progression. Switching the prime factor into the live variable produces Alternative B.

Alternative B: retain $K=1$, with live variable $p$.

The actual sum is now

$$
-\sum_p W(p/X)\Lambda(p+2).
$$

The progression modulus has disappeared, but the live coefficient is supported on genuine primes.

This is not the unweighted prime number theorem.

Indeed, exact character orthogonality for a weighted progression gives

$$
\begin{aligned}
&\sum_{\substack{m\in J\\m\equiv a\pmod K}}
b(m)\Lambda(m)\\
&=\frac1{\varphi(K)}
\sum_{\chi\bmod K}\overline{\chi(a)}
\sum_{m\in J}b(m)\Lambda(m)\chi(m).
\end{aligned}
$$

The actual principal-character term is

$$
\frac1{\varphi(K)}
\sum_{\substack{m\in J\\(m,K)=1}}
b(m)\Lambda(m).
$$

It is not automatically an independently computable smooth density.

For $K=1$ and

$$
b(m)=1_{\mathbb P}(m-2)W((m-2)/X),
$$

the principal-character term is the entire prime-pair correlation.

Conclusion for Proposition 7.16: reducing the conductor does not remove the prime-supported coefficient. The one-prime row must remain in the unseparated branch of Definition 7.7, with its own estimate. Proposition 7.16 cannot supply that estimate through the stated retained-cofactor argument.

4. An unconditional counterexample to the proposed density transfer

The problem with the local mean can be exhibited within the actual gap-two problem, without assuming that twins are finite.

Restrict the one-prime row to primes

$$
p\equiv1\pmod3.
$$

Then $3\mid p+2$. For sufficiently large $p$, there are no simultaneous prime pairs on this restricted row.

Thus

$$
\sum_{\substack{p\equiv1\pmod3}}
W(p/X)1_{\mathbb P}(p+2)=0.
$$

On the other hand, the model used in Lemma 7.17 gives

$$
-\sum_{\substack{p\equiv1\pmod3}}
\frac{p}{\varphi(p)}
\frac{W(p/X)}{\log(p+2)}
=
-\left(\frac{\omega_W}{2}+o(1)\right)
\frac{X}{L^2}.
$$

This follows from the ordinary prime number theorem modulo 3.

Hence the actual centered contribution on this subrow is

$$
\boxed{
E_{1,\,1\bmod3}(X)
=
\left(\frac{\omega_W}{2}+o(1)\right)
\frac{X}{L^2}.
}
\tag{B}
$$

It is not negligible.

This is a rigorous counterexample to a subrow-wise negligible-error inference from the rough conductor's Euler factors. It does not establish that the unrestricted centered sum cannot exhibit cancellation between the two residue classes.

That cancellation would itself require genuine prime-pair information.

5. Proposition 7.21: what can actually be conserved?

Equation (64) of Proposition 7.21 gives the sum of the cellular local-density terms as

$$
\sum_{R,S}LD^{\mathrm{res}}_{R,S}
=
\left(\omega_W c_\lambda^{\mathrm{loc},+}+o(1)\right)
\mathfrak S(2)\frac{X}{L^2},
$$

where

$$
\mathfrak S(2)=
2\prod_{q>2}\left(1-\frac1{(q-1)^2}\right)
>1.32.
$$

Equation (65) additionally asserts arbitrary logarithmic savings for the cellular centered sums.

researchgate.net

There are two separate issues.

Normalization. Lemma 7.17 and Remark 7.18 explicitly omit the singular series from the computed model. After discarding the negative cubic contribution, their model has coefficient $c_\lambda^{\mathrm{loc},+}$, not $\mathfrak S(2)c_\lambda^{\mathrm{loc},+}$.

If equation (64) is conserving that same model after the stated discard, the difference is

$$
\omega_W
\big(\mathfrak S(2)-1\big)
c_\lambda^{\mathrm{loc},+}\frac{X}{L^2}.
$$

This is a nonvanishing main-scale difference, not an endpoint error.

The numerical coefficient $c_\lambda^{\mathrm{loc},+}$ is approximately $0.08022$. Multiplying it by the singular series is permissible for an upper bound, because the coefficient is positive and the singular series exceeds one. It is not justified as an equality merely by partitioning the cells.

The one-sided enlargement in Proposition 7.22 is therefore repairable as an inequality. It does not repair the missing centered estimate.

Window conservation. There is another literal bookkeeping issue. Definition 7.5 places $W$ inside the model $M_K$, and Proposition 7.6 displays an additional outer factor $W$. If these are the same window, the subtracted term contains $W^2$, rather than $W$.

Splitting a window into two identical half-weight pieces preserves its linear mass, but changes the quadratic mass:

$$
W=\frac W2+\frac W2,
\qquad
\left(\frac W2\right)^2+
\left(\frac W2\right)^2=\frac{W^2}{2}.
$$

Thus literal quadratic weighting cannot have the asserted partition-of-unity conservation.

Removing the duplicate window factor repairs this algebraic problem. I have used the repaired, single-window convention in (A) and (B), so the main objection survives that correction.

Independent repair attempt

6. Recover the correct principal density on the genuine prime row

Instead of assigning the artificial model $K/\varphi(K)$ separately to each rough integer, I attempted an actual divisor opening of the affine prime.

Choose a fixed cutoff

$$
D=X^{1/10}.
$$

The exact identity

$$
\Lambda(p+2)
=\sum_{d\mid p+2}\mu(d)\log\frac{p+2}{d}
$$

gives

$$
N_1(X)=U_D(X)+V_D(X)+O(\sqrt X),
\tag{C}
$$

where

$$
U_D(X)=
\sum_p W(p/X)
\sum_{\substack{d\mid p+2\\d\le D}}
\mu(d)
\frac{\log((p+2)/d)}{\log(p+2)}
$$

and

$$
V_D(X)=
\sum_p W(p/X)
\sum_{\substack{d\mid p+2\\d>D}}
\mu(d)
\frac{\log((p+2)/d)}{\log(p+2)}.
$$

The error in (C) removes proper prime powers of $p+2$. They number $O(\sqrt X)$, and their divided von Mangoldt weights are bounded.

Unlike the original local-density transfer, the entire short part is accessible to ordinary Bombieri–Vinogradov.

Define

$$
S_0(D)=\sum_{\substack{d\le D\\d\text{ odd}}}
\frac{\mu(d)}{\varphi(d)}
$$

and

$$
S_1(D)=\sum_{\substack{d\le D\\d\text{ odd}}}
\frac{\mu(d)\log d}{\varphi(d)}.
$$

The relevant Dirichlet series is

$$
\begin{aligned}
F(s)
&=\sum_{d\text{ odd}}
\frac{\mu(d)}{\varphi(d)d^s}\\
&=\frac{H(s)}{\zeta(1+s)},
\end{aligned}
$$

where

$$
H(s)=
\frac1{1-2^{-1-s}}
\prod_{q>2}
\frac{1-q^{-s}/(q-1)}
{1-q^{-1-s}}.
$$

At zero,

$$
H(0)=\mathfrak S(2).
$$

Consequently,

$$
F(0)=0,\qquad F'(0)=\mathfrak S(2).
$$

The classical Möbius summatory estimate and the absolutely convergent auxiliary Euler product justify the truncated logarithmic moments, giving, for every fixed $A>0$,

$$
S_0(D)\ll_A L^{-A},
$$

$$
S_1(D)=-\mathfrak S(2)+O_A(L^{-A}).
$$

For completeness, the convergence argument expands $H(s)$ into its absolutely convergent Dirichlet series in a neighborhood of zero, convolves with $\mu(n)/n$, and splits the auxiliary convolution at $\sqrt D$. The short part uses the classical logarithmic Möbius moments; the remaining absolutely convergent tail is power-small.

Applying BV with partial summation to $U_D$ now yields

$$
\begin{aligned}
U_D
={}&S_0(D)\int
\frac{W(t/X)}{\log t}\,dt\\
&-S_1(D)\int
\frac{W(t/X)}{\log t\log(t+2)}\,dt
+o(X/L^2).
\end{aligned}
$$

Therefore

$$
\boxed{
U_D(X)=
\left(\mathfrak S(2)\omega_W+o(1)\right)
\frac{X}{L^2}.
}
\tag{D}
$$

This is a legitimate unconditional principal-term calculation on the actual prime-supported sequence. It also produces the correct twin singular series.

Combining (C) and (D) gives the repaired equality

$$
\boxed{
N_1(X)=
\mathfrak S(2)\omega_W\frac{X}{L^2}
+V_D(X)+o(X/L^2).
}
\tag{E}
$$

The price of the repair is the complete long-divisor sum $V_D$. It cannot be discarded.

7. Attempt to control the repaired remainder by its sign

I tested whether the new remainder might have a favorable pointwise sign after restricting to the actual prime support.

It does not. Both signs occur with substantial mass.

For composite $m=p+2$ that is not a prime power, the complete divisor sum vanishes. Hence its long-divisor contribution is exactly the negative of its short-divisor contribution.

Consider two disjoint families.

Negative family. Require

$$
m=av,\qquad
X^{0.055}<a<X^{0.06},
$$

where $a$ is prime and all prime factors of $v$ exceed $D$. Exclude repeated $a$.

The only short divisors are $1,a$. Thus the long-divisor coefficient is

$$
-\frac{\log a}{\log m},
$$

which is bounded above by a fixed negative constant.

Positive family. Require

$$
m=abv,
$$

where $a,b$ are distinct primes in the same exponent interval and every prime factor of $v$ exceeds $D$.

Since $ab>X^{0.11}>D$, the only short divisors are $1,a,b$. Consequently, the long-divisor coefficient is

$$
1-\frac{\log(ab)}{\log m},
$$

which exceeds a fixed positive constant.

Both families have unconditionally $\gg X/L^2$ representatives with $p=m-2$ genuinely prime.

To establish this, fix the selected prime factors and apply the lower linear sieve to the remaining roughness condition. In the two-factor family, use residual sieve level $X^{0.35}$. The complete opened moduli have size at most

$$
X^{0.12+0.35}=X^{0.47},
$$

comfortably within BV. The sieve ratio is $3.5>2$, so its lower coefficient is positive. The selected prime factors have positive harmonic mass. The one-factor family has still more modulus room.

The polynomial-sized repeated-factor exceptions are negligible. Divisor multiplicities in the summed progression errors are absorbed by taking sufficiently strong logarithmic precision in BV.

It follows that the repaired remainder has both positive and negative contributions of order $X/L^2$.

This rules out simply discarding one sign and declaring the repaired principal term sufficient. The net signed estimate is still missing.

Final assessment of the assigned section

Statement
 |
Audit result
 |

Rough Liouville projector
 |
Correct exact identity
 |

Ordinary $I_1,I_2,I_3$ densities
 |
Valid comparison quantities
 |

Lemma 7.17
 |
Model evaluation is distinguishable from actual prime-pair evaluation; its complete partition and weighting require justification
 |

Proposition 7.16
 |
Retained short-live switching does not cover the genuine prime unit-cofactor row
 |

Lemma 7.19
 |
Its coefficient is valid for the specified ordinary comparison, not an independently established prime-pair conditional density
 |

Proposition 7.21
 |
Normalization and conservation problems under the stated identification; negligible centered remainder not established by conservation
 |

Independent repair
 |
Correct principal term proved, with an essential signed long-divisor remainder
 |

The decisive surviving obligation is to establish, for some $\delta>0$ along unbounded scales,

$$
\boxed{
V_D(X)\ge
-\big(\mathfrak S(2)-\delta\big)
\omega_W\frac{X}{L^2}.
}
$$

By (E), this would prove infinitely many ordinary twin primes. I have not established it.

Verification limits: I accessed the author-uploaded indexed mathematical text, not a locally downloaded PDF. I could inspect the requested proposition statements and substantial surrounding proofs, but not recover every line of Proposition 7.21's proof or the complete downstream Proposition 9.5 derivation. Therefore this is a specific Section 7 gap diagnosis, not a comprehensive refutation of every later argument or manuscript version. No independent agent review was performed. No local files, project files, downloads or external messages were used.

The substantive finding is that repairing the local-density equality exposes, rather than resolves, the original prime-sensitive arithmetic remainder.

---

## Confirm research rules

[Original conversation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6b05c0cd-cd2c-83ee-9cec-f42c2c5a6f54)

### Recovered response 1

1. The exact parity target

Put $z=X^\alpha$, where $1/5<\alpha<1/3$, and let $n=p+h$, with $h=\pm2$.

For sufficiently large $X$, every $z$-rough $n$ in the specified interval has at most four prime factors, counted with multiplicity. Nonsquarefree exceptions number at most $O(X^{1-\alpha})$, negligible at the expected twin-prime scale.

On the remaining squarefree integers:

Number of prime factors
 |
$\mu(n)$
 |
Type
 |

1
 |
−1
 |
Desired prime
 |

2
 |
+1
 |
Semiprime
 |

3
 |
−1
 |
Triple prime product
 |

4
 |
+1
 |
Four-prime product
 |

Writing $C_j(X)$ for the count in each row, the rough odd-parity mass is exactly $C_1+C_3$. Consequently, a sufficiently strong lower bound for odd parity, together with a smaller upper bound for triple products, would prove ordinary twin primes.

The critical requirement is cancellation or a one-sided inequality on polynomially rough shifted primes, not merely on unrestricted shifted primes.

2. External padding: exact obstruction

Source limitation: I could verify the v2 bibliographic record, dated 19 November 2026, but its full HTML and PDF were inaccessible. The original v1 determinant and operator argument was accessible. The following obstruction is an independent algebraic calculation and does not depend on any unverified v2 estimate.

arxiv.cnoctave.top+1

Write the Type II variables as $uv+h$ and $rs+h$.

With genuine internal marks $a\mid uv+h$ and $b\mid rs+h$, the common-cofactor equation is

$$
\frac{uv+h}{a}=\frac{rs+h}{b},
$$

giving

$$
buv-ars=h(a-b).
$$

The nonzero right-hand side for distinct marks permits the determinant geometry used by Lü–Wang–Wu.

Now replace the internal marks by external squarefree products $A,B$ of bank primes below $z$. The padded cross equation becomes

$$
A(uv+h)=B(rs+h),
$$

or

$$
Auv-Brs=h(B-A).
$$

Superficially, this retains the determinant structure. However, both $uv+h$ and $rs+h$ are $z$-rough.

Put $g=(A,B)$. The cross equation requires

$$
\frac{B}{g}\mid uv+h,
\qquad
\frac{A}{g}\mid rs+h.
$$

Every prime dividing either of these divisors is below $z$. Roughness therefore forces

$$
\boxed{A=B,\qquad uv=rs.}
$$

This holds whether $A$ is fixed, independently randomized, or chosen from many disjoint prime banks.

The surviving second moment

Let $F(t)$ denote the complete bilinear coefficient at the rough integer $t$, and let $w_A$ be external padding weights with $\sum_A w_A=1$.

Define

$$
H(m)=\sum_{At=m}w_A\mu(A)F(t).
$$

Multiplicativity gives the desired identity

$$
\sum_m\mu(m)H(m)=\sum_t\mu(t)F(t).
$$

But unique recovery of the small-prime part gives the exact energy identity

$$
\boxed{
\sum_m|H(m)|^2
=
\left(\sum_A|w_A|^2\right)
\sum_t|F(t)|^2.
}
$$

There is no arithmetic mixing between distinct external marks.

For $N$ possible marks, the padded support also increases by a factor $N$. Since

$$
N\sum_A|w_A|^2\ge1,
$$

the apparent second-moment saving is completely lost when Cauchy–Schwarz is used to recover the original sum.

Uniform random padding attains equality, not an improvement.

3. Attempted repair: allowing genuine large-factor exchanges

Suppose the bank primes are instead allowed to exceed $z$, imposing $(A,t)=1$ to preserve Möbius multiplicativity.

For probability weights $w_A$, define

$$
c(t)=\sum_{(A,t)=1}w_A.
$$

Normalize each admissible contribution by $c(t)>0$. The resulting padded sum still equals the original Möbius sum.

The full second moment now contains genuine off-diagonal terms. With $g=(A,B)$, these have the form

$$
\sum_{A\ne B}w_Aw_B\mu(A)\mu(B)
\sum_k
\frac{F((B/g)k)\overline{F((A/g)k)}}
{c((B/g)k)c((A/g)k)},
$$

with the original roughness, interval and coprimality conditions retained.

This repairs the algebraic diagonal collapse only by exchanging actual prime factors of the rough integers.

There are two important limitations:

-

At most four bank labels can change, because the rough integer has at most four prime factors.

-

If every bank prime is smaller than $X/2-2$, a prime $t$ in the target interval cannot participate in any distinct-mark exchange. Its contribution remains isolated.

Thus the paper's small-prime averaging mechanism is not recovered. Moving to polynomial-size banks introduces new arithmetic correlations rather than supplying the missing estimate.

4. Selberg identity: an exact triple-annihilating detector

This part produces a more useful result.

Selberg's identity is

$$
\Lambda_2(n)
=(\mu*\log^2)(n)
=\Lambda(n)\log n+(\Lambda*\Lambda)(n).
$$

For squarefree $n$, its normalized values are

Factorization
 |
$\Lambda_2(n)/\log^2 n$
 |

Prime
 |
$1$
 |

Semiprime with log shares $a,b$
 |
$2ab\le 1/2$
 |

Three or more primes
 |
$0$
 |

Consequently,

$$
\frac{\Lambda_2(n)}{\log^2 n}
-\frac{1+\mu(n)}4
\le \mathbf1_{\mathbb P}(n).
$$

This is a valid pointwise minorant on squarefree integers, but its mean is not immediately accessible.

A stronger repair is to fold the divisor sum at the square root. Define

$$
W(n)=\sum_{d\mid n}\mu(d)
\left(1-\frac{2\log d}{\log n}\right)_+.
$$

When $n$ is squarefree and $\mu(n)=-1$, pairing complementary divisors gives exactly

$$
W(n)=\frac{\Lambda_2(n)}{\log^2 n}.
$$

Indeed, their combined normalized logarithmic weight is

$$
(1-x)^2-x^2=1-2x,
\qquad x=\frac{\log d}{\log n}.
$$

Therefore $W=1$ on primes and $W=0$ on every squarefree odd-rank composite.

Now square this detector:

$$
V(n)=W(n)^2.
$$

We obtain the exact identity

$$
\boxed{
\mathbf1_{\mathbb P}(n)
=\frac{\mu^2(n)-\mu(n)}2 V(n)
}
$$

for every integer $n>1$.

Unlike using $\Lambda_2$ directly, this squared detector retains positive weight on four-prime products. That makes it possible to prove a positive unsigned mean without first proving a stronger rough version of Chen's theorem.

5. Unconditional positive unsigned mean

Choose the admissible exponent

$$
\alpha=\frac{201}{1000}.
$$

Let

$$
K_0=2\prod_{q>2}\left(1-\frac1{(q-1)^2}\right),
\qquad
B_X=\frac{K_0X}{2\log^2 X}.
$$

Define

$$
U_X=\sum_{\substack{X/2<p\le X\\
p\ {\rm prime},\ P^-(p+h)>X^\alpha}}
\mu^2(p+h)V(p+h).
$$

Proved bound, using established sieve theorems:

$$
\boxed{\liminf_{X\to\infty}\frac{U_X}{B_X}
\ge 0.0576.}
$$

Here is the derivation.

Lower bound for the total rough population

Use the lower linear sieve at distribution exponent $\theta=0.57$, strictly below $4/7$.

This application is justified by Bombieri–Friedlander–Iwaniec, Theorem 10, together with the well-factorable lower-sieve weights. Both upper and lower weights are covered by the formulation in Lichtman's paper, Theorem 2.10.

archive.ymsc.tsinghua.edu.cn+1

Since $2<\theta/\alpha<4$, the lower-sieve coefficient gives

$$
\liminf\frac{C_1+C_2+C_3+C_4}{B_X}
\ge
\frac2\theta
\log\left(\frac{\theta}{\alpha}-1\right)
>2.12.
$$

Squareful exceptions are negligible.

Upper bound for the triple population

Switch to the sequence of products of three distinct primes exceeding $X^\alpha$, and upper-sieve their shifted values.

The Bombieri–Vinogradov theorem for products of primes permits distribution exponent $0.49$; see Liu–Park–Song, Theorem 3.2. Here the prime-factor ranges are polynomial, and the physical product length is of order $X$.

Springer Nature Link

Sift through $X^{1/6}$. Every prime factor of the product exceeds the sieve cutoff, so the principal progression density is $1/\varphi(d)$ for the odd sieve moduli.

The resulting bound is

$$
\limsup\frac{C_3}{B_X}
\le \frac{2}{0.49}I_3,
$$

where the ordinary three-prime angular mass is

$$
I_3=
\frac12
\int_\alpha^{1-2\alpha}
\frac1u
\log\left(\frac{1-\alpha-u}{\alpha}\right)\,du.
$$

The factor $1/2$ follows by marking one genuine prime with its logarithmic share and counting the other two without ordering.

Since $\alpha>1/5$,

$$
I_3\le\frac12\int_1^3\frac{\log(4-u)}u\,du.
$$

The concavity inequality

$$
\log(4-u)\le\log2+\frac{2-u}{2}
$$

gives

$$
I_3\le
\frac{(1+\log2)\log3-1}{2}.
$$

Hence

$$
\limsup\frac{C_3}{B_X}<1.76.
$$

Combining the two sieve bounds,

$$
\liminf\frac{C_1+C_2+C_4}{B_X}
\ge 0.36.
$$

Uniform positivity of the squared detector

For semiprimes, writing $a$ for the smaller logarithmic prime share,

$$
W(n)=2a\ge 2\alpha-o(1).
$$

For four-prime products, write the ordered shares as

$$
a\le b\le c\le d,\qquad a+b+c+d=1.
$$

All individual shares are below $1/2$ at the chosen roughness exponent. Pairing complementary two-factor divisors gives

$$
W(n)=-\min(4a,\,2-4d).
$$

Since

$$
a\ge\alpha-o(1),\qquad
d\le1-3\alpha+o(1),
$$

we obtain

$$
|W(n)|\ge
\min(4\alpha,12\alpha-2)-o(1).
$$

The semiprime lower bound tends to $0.402$, and the four-prime lower bound tends to $0.412$. Thus on every retained rank other than three,

$$
V(n)\ge0.16
$$

for sufficiently large $X$.

This proves

$$
\liminf\frac{U_X}{B_X}
\ge0.16(2.12-1.76)=0.0576.
$$

6. The precise remaining parity estimate

Define the signed weighted sum

$$
E_X=
\sum_{\substack{X/2<p\le X\\
p\ {\rm prime},\ P^-(p+h)>X^{0.201}}}
\mu(p+h)W(p+h)^2.
$$

If $T_X$ counts ordinary twin pairs in this interval, the pointwise identity proves exactly

$$
\boxed{2T_X=U_X-E_X.}
$$

The unconditional lower bound above therefore establishes the following sufficient criterion for the twin-prime conjecture:

$$
\boxed{
\liminf_{X\to\infty}\frac{E_X}{B_X}
\le0.057.
}
$$

In particular, proving $E_X=o(X/\log^2 X)$ would suffice. A full asymptotic is unnecessary.

The exact divisor-expanded form of the remaining term is

$$
E_X=
\sum_{d,e\le\sqrt{X+2}}\mu(d)\mu(e)
\sum_{\substack{X/2<p\le X,\ p\ {\rm prime}\\
P^-(p+h)>X^{0.201}\\
[d,e]\mid p+h}}
\mu(p+h)w_d(p+h)w_e(p+h),
$$

where

$$
w_d(n)=\left(1-\frac{2\log d}{\log n}\right)_+.
$$

All three-prime contamination has been eliminated. The unsigned mass is rigorously bounded below. The remaining obligation is the upper bound for this single signed arithmetic statistic.

Research verdict

The external-small-mark proposal fails by an exact second-moment factorization, not merely by an insufficient numerical estimate. Enlarging the banks restores exchanges only through genuine large divisors.

The Selberg repair is productive: it supplies a triple-annihilating weight with a strictly positive unconditional unsigned mean and an explicit sufficient parity threshold for ordinary twin primes.

The signed estimate $E_X/B_X\le0.057$ in liminf remains unproved. If there were only finitely many twins, the established identities would force its liminf to be at least $0.0576$.

I selected the roughness exponent, sieve levels and squared detector independently. The v2 proof body remained inaccessible, so no claim is made that its technical estimates cover this new weight. No project-file tools, local scratch files, downloads or external communications were used, and no independent worker verification was performed.

---

### Recovered response 2

1. A successful calculation: the unsigned two-site moment

The folded weight has an independently evaluable two-site correlation. In the notation of your question, put

$$
P(n)=\mathbf1_{\mathbb P}(n)\log n,\qquad
K=2C_2,
$$

and let $I=(X/2,X]$, of length $Y=X/2$.

The exact pointwise identity is

$$
A(n)-B(n)=2P(n).
$$

I obtain the following asymptotic, including the moving cutoffs and the squarefree gates:

$$
\boxed{\sum_{n\in I}A(n)A(n+2)=4KY+o(X).}
$$

This uses a genuine arithmetic estimate for the CRT errors, not the prime-pair identity. It does not require a twin-prime hypothesis.

Squarefree gates and CRT errors

Write

$$
H(n)=2\sum_{d\mid n}\mu(d)
\log_+\frac{\sqrt n}{d}.
$$

Expand the squarefree gate as

$$
\mu^2(n)=\sum_{a^2\mid n}\mu(a).
$$

Truncate both square-divisor variables at $Q=X^{1/1000}$. The discarded terms contribute $O(X^{1-1/1000+o(1)})$: the number of large-square incidences is $O(X/Q+\sqrt X)$, and all remaining divisor multiplicities and logarithmic weights are $X^{o(1)}$.

For fixed retained $a,b$, the actual congruence moduli become

$$
D=[d,a^2],\qquad E=[e,b^2].
$$

They satisfy $D,E\ll X^{0.502}$. These moduli are generally not squarefree.

Fortunately, the Bettin–Chandee Kloosterman-fraction theorem applies to arbitrary integer coefficient sequences and coprime integer arguments, without requiring squarefree moduli.

arxiv.org+1

A compatible CRT pair must have $g=(D,E)\mid2$. Write $D=gm$, $E=gr$. The residue class for $n=Dk$ is determined by

$$
k\equiv-\frac2g\overline m\pmod r.
$$

Thus the floor discrepancies at an interval endpoint $T$ have phases

$$
e\left(\frac{2h}{g}\frac{\overline m}{r}
+\frac{hT}{gmr}\right).
$$

The second term is essential: omitting it would replace the actual interval count by a different one.

Split into dyadic blocks $m\asymp M,\ r\asymp N$.

-

If $MN\le X^{0.99}$, the trivial floor-error sum is $O(X^{0.99+o(1)})$ for each fixed $a,b$.

-

Otherwise, use the Vaaler sawtooth approximation through frequencies $1\le |h|\le X^{0.01}$.

On the latter blocks the perturbation factor in Bettin–Chandee, Remark 1, is

$$
\left(1+\frac{|h|X}{MN}\right)^{1/2}
\ll X^{0.01}.
$$

With a single frequency, their bound is at most

$$
X^{o(1)}
(MN)^{1/2}X^{0.01}
\left[(MN)^{7/20}(M+N)^{1/4}
+(MN)^{3/8}(M+N)^{1/8}\right].
$$

At the largest permitted block, the first term has exponent $0.9889$, and the second is smaller. Summing the Fourier coefficients costs only logarithms. The zero-frequency approximation error is at most $X^{1.004-0.01+o(1)}$.

After summing the $Q^2$ square-divisor pairs, the total error remains power-saving. The coefficients created by grouping $d$ into $[d,a^2]$ are divisor-bounded, which is absorbed in $X^{o(1)}$.

The moving cutoffs cause no additional power loss. Indeed,

$$
H(n)=2\int_1^{\sqrt n}
\left(\sum_{\substack{d\mid n\\d\le u}}\mu(d)\right)
\frac{du}{u}.
$$

Use this representation on both sides. For fixed integration variables $u,v$, the interval is simply restricted by $n\ge u^2$ and $n+2\ge v^2$. The CRT estimate above is uniform in these endpoints. Integration costs $O(\log^2 X)$.

The principal term

The full squarefree density can now be restored in the CRT main term. For example,

$$
\sum_{d\le\sqrt X}\frac1{[d,a^2]}
\ll \frac{\tau(a^2)\log X}{a^2},
$$

so extending the truncated square-divisor sums to infinity costs $o(X)$, even after the logarithmic weights.

Let $\rho(d,e)$ be the density of integers satisfying both divisibility requirements and both squarefree gates. Its signed double Dirichlet series is

$$
F(s,t)=\sum_{d,e}
\frac{\mu(d)\mu(e)\rho(d,e)}{d^s e^t}.
$$

At an odd prime $q$, the local factor is

$$
1-\frac2{q^2}
-\frac{q-1}{q^2}(q^{-s}+q^{-t}).
$$

At $2$, it is $1/2$, since two integers at distance two cannot both be even and squarefree.

Consequently,

$$
F(s,t)=
\frac{G(s,t)}{\zeta(1+s)\zeta(1+t)},
$$

where $G$ has an absolutely convergent double Dirichlet series in a neighborhood of $(0,0)$. Its value there is

$$
G(0,0)
=2\prod_{q>2}\frac{1-2/q}{(1-1/q)^2}
=K.
$$

To evaluate the two logarithmic ramps, convolve the coefficients of $G$ with the coefficients of the two inverse zeta functions. The classical Mertens consequence of the prime number theorem,

$$
\sum_{m\le R}\frac{\mu(m)}m\log(R/m)\longrightarrow1,
$$

is bounded uniformly in $R$. Absolute convergence of the coefficients of $G$ therefore permits dominated convergence in both variables, uniformly for the two moving square-root cutoffs.

Each folded ramp has a factor two. The resulting local main term is $4G(0,0)=4K$, proving the asserted $AA$ asymptotic.

2. Checking the mixed prime moments

The squarefree gate also has the correct principal constant in the mixed calculation.

Conditional on $n$ being prime, the local factor at an odd prime $q$ for the divisor expansion of $A(n+2)$ is

$$
1-\frac1{q(q-1)}-\frac{q^{-s}}q.
$$

After extracting $1/\zeta(1+s)$, the remaining Euler product has value $K$ at zero. The logarithmic ramp therefore gives $2K$.

There is a useful technical point in controlling the squarefree gate near the square-root boundary. Truncate its square-divisor variable at $(\log X)^{40}$. In the modulus

$$
D=[d,a^2],
$$

both $d$ and $a$ are squarefree, so $a$ is uniquely determined by the primes occurring to exponent two in $D$. The multiplicity of $d$ is at most $2^{\omega(a)}$.

This permits the following treatment using Bombieri–Vinogradov below the square-root collar and the fixed-residue mean-value theorem of Bombieri–Friedlander–Iwaniec, Primes in Arithmetic Progressions to Large Moduli II, inside that collar. The latter gives a dyadic modulus error of order $X(\log\log X)^{O(1)}/\log^2 X$ for square-root moduli enlarged by fixed logarithmic powers.

The exceptional coefficients exceeding $(\log X)^{1/2}$ are harmless by Brun–Titchmarsh and the convergence, for every fixed $j$, of

$$
\sum_a\frac{\tau(a)^j}{\varphi(a^2)}.
$$

The remaining coefficient loss and the logarithmic integration together still leave an $o(X)$ error.

Thus the standard fixed-residue theorem supplies the mixed estimates stated in your question:

$$
\sum_{n\in I}P(n)A(n+2)=2KY+o(X),
$$

$$
\sum_{n\in I}A(n)P(n+2)=2KY+o(X).
$$

The original BFI II full text was inaccessible during this check; I have used its classical mean-value theorem rather than claiming a fresh audit of its proof. Original paper.

3. The remaining signed correlation

Define

$$
T_X=\sum_{n\in I}P(n)P(n+2).
$$

Expanding the exact pointwise relation and using the independently evaluated moments gives

$$
\boxed{
\sum_{n\in I}B(n)B(n+2)
=-4KY+4T_X+o(X).
}
$$

The sufficient one-sided estimate is therefore

$$
\limsup_{X\to\infty}
\frac1Y\sum_{n\in I}B(n)B(n+2)>-4K.
$$

An $o(X)$ estimate would establish the full weighted Hardy–Littlewood asymptotic, but that strength is unnecessary.

For the second attack, introduce the composite-only coefficient

$$
C(n)=A(n)-P(n)=B(n)+P(n).
$$

It vanishes on primes, nonsquarefree integers and squarefree odd-rank composites. Only squarefree even-rank composites remain.

The computed moments imply

$$
\boxed{
\sum_{n\in I}C(n)C(n+2)=T_X+o(X).
}
$$

This is a particularly clean reformulation: a positive signed correlation on composite pairs alone would force infinitely many twin primes. It is an identity-derived criterion, not yet an independent lower bound.

4. Mellin attack: an independently controlled frequency region

Put $L=\log(2X)$ and $x_q=\log q/L$. Define the multiplicative function

$$
f_z(n)=\mu^2(n)
\prod_{q\mid n}-(e^{zx_q}-e^{-zx_q}).
$$

Mellin inversion gives, for $a>0$,

$$
\frac{B(n)}L
=\frac1{2\pi}
\int_{\mathbb R}
\frac{f_{a+iu}(n)}{(a+iu)^2}\,du.
$$

The crucial feature appears when moving the contour to the imaginary axis.

The residue contribution at zero is precisely the negative prime term. Equivalently, using the Fourier representation of the absolute-value function gives the exact formula

$$
\boxed{
\frac{B(n)}L
=-\frac{P(n)}L
-\frac1{2\pi}\int_{\mathbb R}
\frac{\operatorname{Re}f_{iu}(n)}{u^2}\,du.
}
$$

On odd-rank squarefree integers the product $f_{iu}(n)$ is purely imaginary. On even ranks it is real. Thus the integral is exactly $C(n)/L$.

An arithmetic majorant at the correct scale

Define the nonnegative squarefree multiplicative function

$$
g_X(n)=\mu^2(n)\prod_{q\mid n}
\min\left(1,\frac{\log q}{L}\right).
$$

Its harmonic Euler product is bounded uniformly:

$$
\sum_{m\le 2X}\frac{g_X(m)}m
\le
\exp\left(\sum_{q\le2X}\frac{\log q}{qL}\right)
\ll1.
$$

The Nair–Tenenbaum upper bound applied to the two linear forms $n,n+2$ consequently gives

$$
\boxed{
\sum_{n\in I}g_X(n)g_X(n+2)
\ll\frac{X}{L^2}.
}
\tag{1}
$$

Its uniformity hypotheses hold because the functions are nonnegative, multiplicative and bounded by one, with fixed polynomial forms.

tenenb.perso.math.cnrs.fr+1

This reaches the required absolute scale, although not the required cancellation.

Low-frequency positivity

For $0<\eta\le1/4$, define

$$
C_\eta(n)=
-\frac{L}{2\pi}\int_{-\eta}^{\eta}
\frac{\operatorname{Re}f_{iu}(n)}{u^2}\,du.
$$

For a squarefree semiprime $n=qr$,

$$
\frac{C_\eta(n)}L
=\frac4\pi\int_0^\eta
\frac{\sin(ux_q)\sin(ux_r)}{u^2}\,du
\ge0.
$$

More precisely,

$$
\frac{C_\eta(n)}L
=\frac{4\eta}{\pi}x_qx_r
+O(\eta^3x_qx_r).
$$

For every even rank $k\ge4$, the elementary bound

$$
|f_{iu}(n)|\le(2|u|)^k g_X(n)
$$

gives

$$
|C_\eta(n)|\ll L\eta^3g_X(n).
$$

This estimate is uniform over all higher ranks, including unbounded ones.

Combining these inequalities with (1), I obtain the independent arithmetic estimate

$$
\begin{aligned}
\sum_{n\in I}C_\eta(n)C_\eta(n+2)
={}&\frac{16\eta^2L^2}{\pi^2}
\sum_{\substack{n\in I\\
n,n+2\text{ squarefree semiprimes}}}
g_X(n)g_X(n+2)\\
&+O(\eta^4X).
\end{aligned}
$$

In particular,

$$
\boxed{
\sum_{n\in I}C_\eta(n)C_\eta(n+2)
\ge-O(\eta^4X).
}
$$

If $B_\eta=-P+C_\eta$, the mixed terms are bounded absolutely by $O(\eta X)$, again using (1). Consequently,

$$
\boxed{
\sum_{n\in I}B_\eta(n)B_\eta(n+2)
\ge T_X-O(\eta X).
}
\tag{2}
$$

This is a genuine one-sided bound for a portion of the Mellin integral, obtained without using the twin-prime identity.

5. Why ordinary Elliott does not yet close the estimate

For a fixed bounded frequency $u$, the function

$$
f_{iu}(n)n^{-2|u|/L}
$$

is multiplicative and bounded by one. Indeed, its local modulus satisfies

$$
2|\sin(ux_q)|e^{-2|u|x_q}\le1.
$$

It is also strongly nonpretentious, since its local values at primes with $\log q=o(L)$ are small in absolute value, independently of any character twist.

I checked the scope of the September 2026 ordinary two-point correlations manuscript. Its corrected Elliott theorem is qualitative for fixed one-bounded multiplicative functions; its quantitative logarithmic saving is stated separately for Liouville correlations. Neither statement directly provides the required estimate for these $X$-dependent functions at scale $X/L^2$.

GitHub+1

There is a substantive reason not to assume that stronger rate from nonpretentiousness alone.

The positive majorant $g_X$ above is itself strongly nonpretentious. Nevertheless,

$$
\sum_{n\in I}g_X(n)g_X(n+2)
\gg\frac{X}{L^2}.
$$

To prove this, sift both integers through $X^\delta$ for a sufficiently small fixed $\delta>0$. The dimension-two lower sieve supplies $\gg_\delta X/L^2$ survivors. Removing squareful exceptions is negligible. Each remaining integer has a bounded number of prime factors, each with logarithmic share at least $\delta/2$, so its $g_X$ weight is bounded below by a positive constant.

Thus even extremely strong nonpretentiousness is compatible with a correlation of precisely the size that needs to be resolved.

There is also a sharper check involving the actual Mellin functions. For sufficiently small fixed complex $z,w$, expansion at zero and (1) give

$$
\sum_{n\in I}f_z(n)f_w(n+2)
=
\frac{4zw}{L^2}T_X
+
O\left(
|zw|(|z|+|w|)\frac{X}{L^2}
\right).
$$

The error follows because every composite contributes at least two powers of its Mellin parameter.

A blanket cancellation theorem of order $o(X/L^2)$ at every sufficiently small fixed positive pair $z,w$ would therefore force $T_X=o(X)$, by subsequently letting the parameters tend to zero. That would contradict the predicted Hardy–Littlewood main term.

The desired cancellation must be an integrated signed phenomenon, not indiscriminate cancellation at every Mellin frequency.

6. Covariance positivity: an explicit obstruction

I tested whether the independently established moments and positive-semidefinite covariance constraints could force a strict improvement.

They cannot, without additional arithmetic information.

Consider the following stationary three-state probability model, with a large parameter $L$. At each site let $(P,C)$ take the values

State
 |
$P$
 |
$C$
 |
Probability
 |

Prime state
 |
$L$
 |
$0$
 |
$1/L$
 |

Composite state
 |
$0$
 |
$L/2$
 |
$2/L$
 |

Other
 |
$0$
 |
$0$
 |
$1-3/L$
 |

Choose a symmetric adjacent-state distribution in which prime–prime and composite–composite transitions have probability zero, while each orientation of prime–composite has probability $4K/L^2$. Complete the remaining probabilities using transitions to the other state.

For sufficiently large $L$, this defines a stationary reversible Markov chain.

Setting $A=P+C$ and $B=C-P$, its adjacent moments are exactly

$$
\begin{aligned}
\mathbb E[A_0A_1]&=4K,\\
\mathbb E[P_0A_1]
=\mathbb E[A_0P_1]&=2K,\\
\mathbb E[B_0B_1]&=-4K,\\
\mathbb E[P_0P_1]&=0.
\end{aligned}
$$

Every genuine Gram matrix of this process is positive semidefinite.

This is not a model of actual integer factorizations. It is a rigorous obstruction to deriving the strict signed margin solely from the computed moments, pointwise identities and generic covariance positivity.

7. The exact surviving high-frequency term

Define

$$
D_\eta(n)=C(n)-C_\eta(n)
=-\frac{L}{2\pi}
\int_{|u|>\eta}
\frac{\operatorname{Re}f_{iu}(n)}{u^2}\,du.
$$

The complete uncontrolled remainder is

$$
\begin{aligned}
\mathcal R_\eta(X)=\sum_{n\in I}\big[
&D_\eta(n)D_\eta(n+2)\\
+{}&D_\eta(n)B_\eta(n+2)\\
+{}&B_\eta(n)D_\eta(n+2)
\big].
\end{aligned}
$$

By (2), a sufficient estimate, for some fixed sufficiently small $\eta>0$, is

$$
\limsup_{X\to\infty}
\frac{\mathcal R_\eta(X)}Y
>-4K+O(\eta),
$$

where the positive margin must dominate the absolute constant in (2).

The high-frequency remainder cannot simply be discarded. In fact, the mixed prime moment gives

$$
\sum_{n\in I}P(n)D_\eta(n+2)
=2KY-T_X+O(\eta X)+o(X).
$$

Under a finite-twins hypothesis this is a nonzero main-scale term. The high-frequency composite correlation must compensate for it.

Research conclusion

The strongest result of this pass is the independent evaluation

$$
\boxed{\sum_{n\in I}A(n)A(n+2)=4KY+o(X),}
$$

with the moving square-root cutoffs, composite CRT moduli and squarefree gates included.

The second step produced an independent low-frequency lower bound with an $O(\eta^4X)$ composite-correlation deficit. It also established why generic Elliott cancellation and covariance positivity cannot supply the remaining estimate without additional arithmetic.

The decisive missing result is now a lower bound for the high-frequency signed remainder, or equivalently a strict positive mean for the complete composite-only correlation $C(n)C(n+2)$.

No complete twin-prime proof has emerged. I independently selected the CRT truncation parameters and Mellin decomposition; neither the new derivations nor their novelty have received independent external verification. No project files, scratch files, installations, downloads or external communications were used.

---

### Recovered response 3

1. A finite obstruction to factor-share corrections

I found an obstruction that is stronger than the restriction for a single continuous kernel. Allowing arbitrary dependence on the individual prime-factor shares of a divisor does not remove the obstruction below support exponent $2/3$. It persists even if corrections of every divisor rank are allowed.

Here is the precise statement and proof.

For a squarefree integer with normalized prime logarithms $x_1,\ldots,x_r$, write the proposed normalized weight in the general form

$$
W(x_1,\ldots,x_r)=
\sum_{S\subseteq[r]}(-1)^{|S|}
k\big((x_i)_{i\in S}\big).
$$

Assume that $k(\varnothing)=1$, that $k$ is symmetric in its arguments, and that

$$
k(x_1,\ldots,x_j)=0
\quad\text{if }\sum_i x_i>\theta,
\qquad \theta<\frac23.
$$

Unlike the original folded kernel, $k$ need not be a function of the sum alone.

We want $W=1$ on primes, $W=0$ on odd-rank composites, and $W\ge0$ on even-rank composites. This would give the desired nonnegative composite partner while preserving the Möbius parity identity.

The six-share test

Use shares that are multiples of $1/6$, writing a partition such as $(3,2,1)$ for the actual shares $(1/2,1/3,1/6)$.

The support restriction leaves only six potentially nonzero coefficients on these configurations:

$$
\begin{aligned}
a&=k(1/6),& b&=k(1/3),& c&=k(1/2),\\
d&=k(1/6,1/6),&
e&=k(1/6,1/3),&
f&=k(1/6,1/6,1/6).
\end{aligned}
$$

All coefficients involving a total share of at least $4/6$ vanish.

The exact divisor expansions are

Partition
 |
Rank
 |
Weight $W$
 |

$(4,1,1)$
 |
3
 |
$1-2a+d$
 |

$(3,2,1)$
 |
3
 |
$1-a-b-c+e$
 |

$(2,2,2)$
 |
3
 |
$1-3b$
 |

$(2,1,1,1,1)$
 |
5
 |
$1-b-4a+6d+4e-4f$
 |

$(3,1,1,1)$
 |
4
 |
$1-c-3a+3d-f$
 |

$(2,2,1,1)$
 |
4
 |
$1-2b-2a+d+4e$
 |

$(1,1,1,1,1,1)$
 |
6
 |
$1-6a+15d-20f$
 |

Write $W_\lambda$ for the weight on partition $\lambda$.

Eliminating all six coefficients yields the following exact identity:

$$
\boxed{
\begin{aligned}
&W_{111111}+9W_{2211}+8W_{3111}\\
&=7W_{21111}+8W_{321}
+6W_{411}+W_{222}-4.
\end{aligned}}
\tag{1}
$$

This identity is independent of the choice of factor-share kernels.

If the triple weights and the rank-five weight vanish, its right-hand side is $-4$. Consequently,

$$
\boxed{
\min(W_{111111},W_{2211},W_{3111})
\le-\frac29.
}
$$

At least one four-prime or six-prime configuration must have a strictly negative weight.

Conversely, if all triples vanish and all even-rank weights are nonnegative, (1) forces

$$
\boxed{W_{21111}\ge\frac47.}
$$

Thus repairing the even-rank signs necessarily introduces a substantial positive odd-rank composite contribution.

This is an exact obstruction, not a failure to find suitable numerical coefficients.

Robustness and the precise cost of escaping it

The obstruction is not an artifact of equal prime logarithms.

Take six distinct positive shares close to $1/6$, summing to one. Group them into blocks of the sizes in the table, and average over all permutations of the six labels. Choose the neighborhood small enough that every union of four labels has total share greater than $\theta$.

Each coefficient appearing in the table is then replaced by its average over the corresponding block type. The same identity (1) holds exactly.

For continuous kernels, these open angular regions are realizable asymptotically by distinct genuine prime factors. Thus the obstruction is relevant to ordinary squarefree integers, not just a formal configuration with repeated prime labels.

There is also an exact formula for what a longer-divisor repair must supply. Allow support through an exponent between $2/3$ and $5/6$, and write

$$
k_{31}=k(1/2,1/6),
$$

with analogous notation for the other block types of total share $2/3$. Then the right-hand side of (1) acquires the additional term

$$
6k_4+16k_{31}+6k_{22}
+24k_{211}+8k_{1111}.
$$

If all odd composites are annihilated and all even composites have nonnegative weights, necessarily

$$
\boxed{
6k_4+16k_{31}+6k_{22}
+24k_{211}+8k_{1111}\ge4.
}
\tag{2}
$$

The long-divisor correction is therefore not optional or infinitesimal. Some coefficient at total share $2/3$ must carry a definite amount of the repair.

This includes the proposed two-variable correction and any higher-order correction that remains a linear sum over short divisors.

2. Checking the proposed least-factor recursion

There are two materially different ways to use the least factor as a tag.

If the tag is the least prime factor of the divisor $d$, it is already part of the individual factor-share information allowed in $k$. The preceding obstruction applies unchanged.

If the tag is the actual least prime factor of $n$, the weight uses information outside the selected divisor. This is a genuine enlargement of the class.

However, opening this condition gives the exact identity

$$
\mathbf1_{q=P^-(n)}
=
\mathbf1_{q\mid n}
\sum_{\substack{e\mid n\\P^+(e)<q}}\mu(e),
$$

with the unit included.

A recursive divisor coefficient indexed by $d\mid n/q$ therefore introduces moduli of the form

$$
q[d,e].
$$

There is no general short-support restriction on these moduli. If the complete recursion can be recombined into a divisor kernel supported below $2/3$, identity (1) rules it out. If it cannot, the additional long-divisor contribution must actually be estimated.

The currently available fixed-residue results do not automatically supply that transfer. Maynard's convenient-factor theorem reaches certain moduli of size $X^{11/21}$, while his well-factorable theorem reaches $X^{3/5-\varepsilon}$ under stronger coefficient assumptions. Neither directly covers the mandatory general correction at exponent $2/3$.

arxiv.org+1

For comparison, the original folded kernel gives $W_{2211}=-2/3$ and $W_{111111}=2$. Its rank-six weight is not universally positive either: on the shares

$$
(0.48,0.16,0.16,0.16,0.02,0.02)
$$

the exact weight is $-0.08$.

Thus repairing only quadruples would not suffice.

3. A stronger obstruction: the three transferable main terms

I then relaxed the odd-rank annihilation requirement entirely. Could we tolerate positive odd composites, retune the three main terms, and still obtain a useful nonnegative partner?

There is a rigorous obstruction here too.

Let $A(n)=\mu^2(n)(\log n)W(n)$, assume $A(n)\ge P(n)$ everywhere, and put $C=A-P$. Define the ordinary odd-composite mass

$$
O_X=
\sum_{\substack{n\in I,\ n\text{ composite}\\\mu(n)=-1}}
\nu(n)A(n),
$$

where

$$
\nu(n)=\mathbf1_{n\text{ odd}}
\prod_{q\mid n,\ q>2}\frac{q-1}{q-2}.
$$

As before, $K=2C_2$ and $Y=|I|$.

For this analytic argument, assume fixed proper-divisor support $\theta<1$, divisor-bounded coefficients and logarithmic Lipschitz bounds sufficient for partial summation. These include the natural smooth factor-share corrections under consideration.

Theorem. If the three moments are successfully evaluated by their ordinary CRT divisor-density principal terms, then

$$
\boxed{
\begin{aligned}
\sum_{n\in I}P(n)A(n+2)&=2KY+2KO_X+o(X),\\
\sum_{n\in I}A(n)P(n+2)&=2KY+2KO_X+o(X),
\end{aligned}}
\tag{3}
$$

and

$$
\boxed{
\begin{aligned}
\sum_{n\in I}\big[
&A(n)A(n+2)\\
&-P(n)A(n+2)-A(n)P(n+2)
\big]\ge4KO_X+o(X).
\end{aligned}}
\tag{4}
$$

The arithmetic transfer of those principal terms is a hypothesis here. The inequality between the principal terms is proved below.

Independent parity balance

For any fixed integer $r\le 2X$, proper-divisor support gives

$$
\sum_{\substack{n\in I\\(n,r)=1}}
\nu(n)\mu(n)A(n)=o(X),
$$

uniformly in $r$, with arbitrary logarithmic saving.

To see this, open the divisor weight and write $n=dm$. The signed inner coefficient is a coprime-restricted Möbius function multiplied by

$$
\prod_{q\mid m}\frac{q-1}{q-2}.
$$

The free variable has polynomial length $m\gg X^{1-\theta}$. Its weighted Möbius sum is controlled by classical Mertens cancellation. Indeed, the multiplicative modification has an absolutely convergent convolution with Möbius at exponent $1/2$, since its local correction is

$$
-\frac1{q-2}\sum_{j\ge1}q^{-js}.
$$

The additional coprimality restrictions have Euler-product cost at most

$$
\exp\left(O\left(\frac{\sqrt{\log X}}{\log\log X}\right)\right),
$$

which is absorbed by the classical exponential Mertens saving.

Summing over $d$ costs only fixed logarithmic powers.

Consequently, even-composite mass balances prime mass plus odd-composite mass. In particular,

$$
\boxed{\sum_{n\in I}\nu(n)A(n)=2Y+2O_X+o(X).}
\tag{5}
$$

This is an independently evaluated one-site signed mean, not a twin-prime identity.

A positive reference measure with no twins

Partition $I$ into intervals $J$ of length $H\asymp X/\log^D X$, for a sufficiently large fixed $D$.

On two independently chosen integers $n,m\in J$, define the nonnegative bilinear reference form

$$
\begin{aligned}
\mathcal Q_J(F,G)=\frac K H
\sum_{\substack{n,m\in J\\(n,m)=1}}
&\nu(n)\nu(m)F(n)G(m)\\
&\cdot[1-\mu(n)\mu(m)].
\end{aligned}
$$

Its decisive property is

$$
\mathcal Q_J(P,P)=0
$$

exactly: every prime–prime pair is deleted by the parity multiplier.

Nevertheless, this reference reproduces all three short-divisor principal terms.

At an odd prime $q$, the local factor

$$
\frac{q(q-2)}{(q-1)^2}
\left(\frac{q-1}{q-2}\right)^{
\mathbf1_{q\mid n}+\mathbf1_{q\mid m}}
\mathbf1_{q\nmid(n,m)}
$$

converts independent divisibility densities into the correct gap-two divisibility densities.

Specifically, the resulting probabilities of simultaneous divisibility by $q^i,q^j$ are zero when both exponents are positive and $q^{-i}$ when only $i$ is positive. The factor at two restricts both squarefree integers to be odd.

This comparison includes prime powers in the opened squarefree gates.

For completeness, the principal-term comparison can be justified without a conjectural independence assumption:

-

Freeze the divisor coefficients on $J$. The logarithmic Lipschitz bounds and ordinary divisor moments make the total freezing error $o(X)$.

-

Expand the two squarefree gates, the two factors $\nu$, and the coprimality indicator. Truncate their five auxiliary variables at $R=X^\delta$, where $5\delta<1-\theta$.

-

The discarded independent-pair terms are power-saving, using square-divisor incidence, the convergent Euler products for the $\nu$ expansions, and $\sum_{k>R}k^{-2}\ll R^{-1}$.

-

Replace the two independent interval counts by their divisor densities. After division by $H$, their total floor error is $X^{\theta+5\delta+o(1)}=o(X)$.

-

Restore the full principal Euler products. In their absolute expansions, every auxiliary-variable prime incidence costs $O(q^{-2})$, including when it shares a prime with a selected divisor. A positive power moment controls the truncation tails.

Finally, inserting the opposite-parity multiplier changes these principal terms by $o(X)$, by the uniform signed mean established above.

For the mixed moment, the ordinary prime number theorem inside $J$, excluding primes dividing the other integer, yields

$$
\mathcal Q_J(P,A)
=K\sum_{m\in J}\nu(m)A(m)+o(H).
$$

Equation (5) now proves (3).

The one-sided inequality

Because $C\ge0$, the reference correlation is nonnegative.

More strongly, for every odd-composite $n$, the uniform parity balance gives

$$
\sum_{\substack{m\in J,\ (m,n)=1\\\mu(m)=+1}}
\nu(m)A(m)\ge H-o(H).
$$

The right-hand side is supplied by the prime contribution in the opposite parity class. All other contributions are nonnegative.

On these opposite-parity pairs the reference multiplier equals two. Counting both orientations therefore gives

$$
\boxed{
\mathcal Q_J(C,C)
\ge4K
\sum_{\substack{n\in J,\ n\text{ composite}\\\mu(n)=-1}}
\nu(n)A(n)-o(H).
}
$$

But

$$
\mathcal Q_J(C,C)=
\mathcal Q_J(A,A)-\mathcal Q_J(P,A)-\mathcal Q_J(A,P),
$$

because the reference prime–prime term is exactly zero.

Summing proves (4).

This reference is not a model asserted to describe actual neighboring integers. It is an explicit positive measure reproducing the principal terms of the proposed method, and it demonstrates what those principal terms alone cannot establish.

4. Combining the two obstructions

For any fixed continuous factor-share kernel supported below $2/3$, nonnegativity of every even-rank weight forces, by (1),

$$
7W_{21111}+8W_{321}+6W_{411}+W_{222}\ge4.
$$

At least one of these odd-composite weights is therefore at least $2/11$.

Continuity gives a fixed open angular region of positive weight. Ordinary prime-product counting using the prime number theorem gives $\gg X/\log X$ genuine squarefree composites in that region on every sufficiently large dyadic interval.

After multiplying by the logarithmic weight,

$$
\boxed{O_X\gg_k X.}
$$

The implied constant can depend on the fixed kernel.

Together with (3)–(4), this proves that even permitting positive odd composites does not repair the intended method:

-

The mixed principal terms necessarily increase above their original $2KY$ values.

-

The combined unsigned principal term minus the two mixed principal terms has a strictly positive main-scale contribution.

-

Positivity of the new composite correlation cannot be credited to twin primes.

The exact surviving arithmetic obligation becomes

$$
\boxed{
T_X=
\sum_{n\in I}C(n)C(n+2)
-\sum_J\mathcal Q_J(C,C)
+o(X).
}
$$

A positive excess over the reference correlation would prove twins. Ordinary nonnegativity of $C$ cannot establish that excess.

Research verdict

This pass establishes two substantial limitations of the proposed repair:

-

Finite algebraic obstruction: no divisor kernel supported below exponent $2/3$, even with arbitrary individual factor-share dependence and all divisor ranks, can simultaneously annihilate odd composites and remain nonnegative on even composites.

-

Principal-term obstruction: allowing odd-composite leakage instead creates an unavoidable positive main-scale reference correlation. Retuning the three transferable moments does not remove it.

The next mathematically distinct route would need either the long-divisor correction quantified in (2), with genuinely stronger distribution estimates, or an arithmetic estimate distinguishing actual adjacent composite factorizations from the opposite-parity reference measure.

Neither has been proved here. I selected the six-share obstruction and the reference measure independently; their novelty and correctness have not received independent external review. The general three-moment transfer remains conditional on establishing the required arithmetic error estimates for the chosen coefficients.

No project files, scratch files, downloads, installations, external communications or research workers were used.

---

## Prime Pair Proof Plan

[Original conversation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6b05a5b8-4b10-83ee-8424-479e8e612538)

### Recovered response 1

1. The direction of the inequality is essential

I inspected Alpöge's original remarks, particularly timeline items 1–5 and 8–15, and the Rubinstein exposition, particularly §§I.1–I.4.3 and III.5.

The transferable idea is to identify an obstruction with the correct sign before constructing the arithmetic object. The Riemann-hypothesis argument needs an upper bound for a centered prime sum. For a nonzero integer $\Delta$, the inequality

$$
\sum_\ell v_\ell(\Delta)\log\ell
=\log|\Delta|
$$

naturally supplies upper bounds on contributions from selected primes. Alpöge's construction replaces ordinary factorial divisibility with a much more sophisticated multiplicity mechanism.

alpo.ge+1

In the exposition, the relevant local estimate is (III.83), whose principal term is

$$
\sum_{\substack{h\ge1\\h\text{ odd}}}
\left(\frac{A}{\ell^h}-w_h\right)_+.
$$

The remaining terms include explicit orbit, capacity and logarithmic losses. This inequality has specific hypotheses on the theta kernels and their integral structures; it is not a general divisibility inequality for arbitrary determinants.

math.uwaterloo.ca+1

For twin primes, the correct sign suggests bounding the complement.

Let

$$
\begin{aligned}
\mathcal P_X&=\{p\text{ prime}:X<p\le2X\},\\
\mathcal C_X&=\{p\in\mathcal P_X:p+2\text{ composite}\},\\
\mathcal T_X&=\{p\in\mathcal P_X:p+2\text{ prime}\}.
\end{aligned}
$$

An upper bound

$$
\#\mathcal C_X<\#\mathcal P_X
$$

on an unbounded sequence of scales would force the desired conclusion.

The crucial difference from the RH application is that the new local divisibility must distinguish the arithmetic of $p+2$, not merely the primality or residue class of $p$.

2. A genuine extra divisor under the no-twins hypothesis

There is an elementary construction in which the desired local divisibility really does occur.

Put

$$
Q=\prod_{p\in\mathcal P_X}p,\qquad
A=\prod_{p\in\mathcal P_X}(p+2),\qquad
D=A-Q.
$$

For sufficiently large $X$, every prime $p\in\mathcal P_X$ dividing $A$ must equal one of the factors $r+2$. Indeed, the factors are odd and smaller than $3p$.

Consequently,

$$
\gcd(D,Q)=\gcd(A,Q)
=\prod_{\substack{r,r+2\in\mathcal P_X}}(r+2).
\tag{1}
$$

This detects precisely the twins with both endpoints inside the interval.

The prime number theorem and partial summation give

$$
\log Q=(1+o(1))X,
$$

and

$$
\log(A/Q)
=\sum_{p\in\mathcal P_X}\log(1+2/p)
=\frac{2\log2+o(1)}{\log X}.
$$

Hence

$$
0<D<Q,\qquad
D=\frac{2\log2+o(1)}{\log X}\,Q.
\tag{2}
$$

The archimedean comparison is genuine: $D$ is a positive integer strictly smaller than $Q$.

Turning the absence of twins into divisibility

Let

$$
M=\operatorname{lcm}_{p\in\mathcal P_X}(p-1),
\qquad
\Delta=D^M-1.
$$

For each $p\in\mathcal P_X$:

-

If $p\mid D$, then $v_p(\Delta)=0$.

-

If $p\nmid D$, Fermat's theorem gives $p\mid\Delta$.

Thus the product of all complement primes divides $\Delta$. Under the hypothesis of no twins in the interval,

$$
\boxed{Q\mid\Delta.}
\tag{3}
$$

This is a valid extra-divisor mechanism, rather than an assumed consequence of compositeness.

The local valuations can also be calculated. For complement primes, the lifting-the-exponent identity gives

$$
v_p(\Delta)
=v_p(D^{p-1}-1)+v_p(M).
$$

In this dyadic interval $v_p(M)=0$: no other prime $r\in\mathcal P_X$ can satisfy $p\mid r-1$. The only possible positive multiple would give $r=p+1$, which is even.

Therefore

$$
v_p(\Delta)=v_p(D^{p-1}-1)\ge1.
\tag{4}
$$

There is no automatic second unit of multiplicity.

The real size budget

Unfortunately,

$$
\log|\Delta|=M\log D+O(D^{-M})
=(1+o(1))MX.
$$

The necessary divisibility under finite twins has logarithmic size only $(1+o(1))X$.

Moreover, $M$ grows faster than every fixed power of $X$. Otherwise, all the $\asymp X/\log X$ distinct integers $p-1$ would be divisors of an integer $M\le X^C$, contradicting the elementary bound $\tau(M)=M^{o(1)}$.

Thus the first genuinely valid local mechanism has an overwhelmingly excessive height cost.

A cyclotomic repair avoids the full exponent $M$. Take

$$
F_X(T)=
\prod_{\substack{d:\ d\mid p-1\\
\text{for some }p\in\mathcal P_X}}\Phi_d(T).
$$

Every complement prime divides $F_X(D)$, since its multiplicative order divides $p-1$. But the degree is still at least $\max_{p\in\mathcal P_X}(p-1)>X-1$. The height cost remains at least of order $X^2$.

Precise surviving problem: find a shared unit-detection mechanism retaining (3), but whose real size is below $Q$. Neither taking higher powers nor ordinary cyclotomic factorization supplies it.

A concrete check also rules out automatic higher multiplicity. Take the prime collection $\{23,31,37\}$, whose three successors $25,33,39$ are composite. Here

$$
Q=26381,\quad A=32175,\quad D=5794,\quad M=1980.
$$

Direct modular exponentiation gives

$$
D^{22}\equiv116=1+5\cdot23\pmod{23^2}.
$$

Since $23\nmid1980/22$, it follows that

$$
v_{23}(D^{1980}-1)=1.
$$

The additional divisibility is real, but a second unit of valuation cannot be inferred simply from compositeness of all the shifted factors.

3. A stronger construction: the shifted Cauchy determinant

This construction substantially reduces the height-versus-divisibility mismatch and produces an exact signed local statistic.

Let $N=\#\mathcal P_X$, and write the primes as

$$
p_1<\cdots<p_N,\qquad a_i=\frac{p_i-1}{2}.
$$

Set $H=\lceil X/2\rceil+1$.

Under the no-twins hypothesis, no two $a_i$ differ by one. Consequently the matrix

$$
C_{ij}=\frac1{1+a_i-a_j}
$$

is well defined.

The Cauchy determinant identity gives

$$
R:=\det C
=\prod_{i<j}
\frac{(a_j-a_i)^2}{(a_j-a_i)^2-1}.
\tag{5}
$$

In particular, $R>1$ when $N\ge2$.

Archimedean size

Let

$$
r(k)=\#\{(i,j):a_j-a_i=k\}.
$$

Since $r(k)\le N$, and $r(1)=0$ under the no-twins hypothesis,

$$
\begin{aligned}
0\le\log R
&=\sum_{k\ge2}r(k)
  \log\frac{k^2}{k^2-1}\\
&\le N\sum_{k\ge2}\log\frac{k^2}{k^2-1}\\
&=N\log2.
\end{aligned}
\tag{6}
$$

The last equality follows from the telescoping product

$$
\prod_{k=2}^{K}\frac{k^2}{k^2-1}
=\frac{2K}{K+1}.
$$

Unlike the Fermat construction, this determinant has a genuinely small logarithmic size after its denominators have been accounted for.

Exact local prime valuations

For an integer modulus $m\ge2$, define

$$
n_m(b)=\#\{i:a_i\equiv b\pmod m\}
$$

and the nonnegative integer

$$
E_m=\frac12\sum_{b\bmod m}
\bigl(n_m(b)-n_m(b+1)\bigr)^2.
$$

Expanding the square gives the exact identity

$$
\begin{aligned}
E_m-N
=\sum_{k\ge1}r(k)\bigl(
&2\mathbf1_{m\mid k}\\
&-\mathbf1_{m\mid k-1}
-\mathbf1_{m\mid k+1}
\bigr).
\end{aligned}
\tag{7}
$$

Under the no-twins hypothesis, the term $k=1$ vanishes. Taking valuations in (5) therefore yields

$$
\boxed{
v_\ell(R)=
\sum_{\ell^h\le H}(E_{\ell^h}-N).
}
\tag{8}
$$

This holds for every prime $\ell$, including $2$.

The important feature is the signed difference between ordinary residue collisions and collisions displaced by one.

A nonzero integer with these valuations

Define

$$
b_H=\operatorname{lcm}(1,\ldots,H),
\qquad
\Delta_X=\det\left[
\frac{b_H}{1+a_i-a_j}
\right]_{i,j=1}^N.
$$

Every entry is integral under the no-twins hypothesis: its nonzero denominator has absolute value at most $H$.

Since

$$
\Delta_X=b_H^N R,
$$

equation (8) gives the exact one-prime formula

$$
\boxed{
v_\ell(\Delta_X)=
\sum_{\ell^h\le H}E_{\ell^h}.
}
\tag{9}
$$

The complete logarithmic size budget is

$$
\boxed{
\log|\Delta_X|
=N\psi(H)+\log R
\le N\psi(H)+N\log2.
}
\tag{10}
$$

Here $\psi(H)=\sum_{m\le H}\Lambda(m)=\log b_H$.

This is a concrete integer determinant with independently calculated local valuations, nonvanishing and archimedean height.

4. The resulting upper-bound criterion for the complement

The residue energies $E_m$ are defined even when twins exist, although the preceding Cauchy matrix then has singular denominators.

Let

$$
T=r(1)
$$

count the twins with both endpoints in $\mathcal P_X$, and put

$$
\mathcal E_X=\sum_{m\le H}\Lambda(m)E_m.
$$

Summing (7) over prime powers gives the unconditional identity

$$
\boxed{
\mathcal E_X
=N\psi(H)-T\bigl(\psi(H)+\log2\bigr)+S_X,
}
\tag{11}
$$

where

$$
S_X=\sum_{k\ge2}r(k)\log\frac{k^2}{k^2-1},
\qquad 0\le S_X\le N\log2.
$$

The $k=1$ term must be treated separately: every modulus divides zero, while the other shifted argument equals two. These give precisely the two terms multiplying $T$.

Consequently, for the complement count $N-T$,

$$
\boxed{
N-T\le
\frac{\mathcal E_X+N\log2}{\psi(H)}.
}
\tag{12}
$$

This is an upper bound in the required direction. Counting internal twin endpoints rather than all twin starts changes the original dyadic count by at most one at the upper boundary.

In particular, proving

$$
\mathcal E_X\le N\psi(H)-cN^2
\tag{13}
$$

for some fixed $c>0$ on an unbounded sequence would imply

$$
T\ge \frac{cN^2}{\psi(H)+\log2}
\gg_c\frac{X}{(\log X)^2}.
$$

The question is whether the individual nonnegative residue energies can be estimated sharply enough to establish (13).

5. An unconditional evaluation through almost-linear moduli

A substantial part of this calculation can be completed.

Put $L=\log X$, and choose

$$
Y=\frac{X}{L^B}
$$

with a sufficiently large fixed $B$.

Proved estimate:

$$
\boxed{
\sum_{m\le Y}\Lambda(m)(E_m-N)
=(C_*+o(1))N^2,
}
\tag{14}
$$

where

$$
C_*=\sum_{\ell>2}
\frac{\ell\log\ell}{(\ell-1)^3}>0.
$$

In particular,

$$
C_*\ge\frac{3\log3}{8}>0.4119.
$$

Proof

For $m=\ell^h$ with $\ell$ odd, the uniform reduced-residue comparison population is

$$
n_m^*(b)=
\frac{N}{\varphi(m)}
\mathbf1_{\ell\nmid 2b+1}.
$$

There are exactly $\ell^{h-1}$ forbidden positions, with two neighboring transitions per position. Therefore its energy is exactly

$$
E_m^*=
\frac{N^2}{\ell^{h-1}(\ell-1)^2}.
\tag{15}
$$

For $m=2^h$, the comparison population is uniform over all $2^h$ classes, because $a_i$ corresponds to an odd residue of $p_i$ modulo $2^{h+1}$. Hence $E_{2^h}^*=0$.

To control the discrepancy, use Theorem 0(a), equation (2.2), of the original Bombieri–Friedlander–Iwaniec 1986 paper.

This is a mean-square progression theorem extending to moduli of size $X/L^B$, under its Siegel–Walfisz hypothesis (A2).

archive.ymsc.tsinghua.edu.cn+1

The prime indicator on $(X,2X]$ satisfies that hypothesis. Extra coprimality restrictions remove at most the number of prime divisors of the additional integer, absorbed by the permitted divisor-factor loss. The squared coefficient norm is $N$.

Thus, choosing $B$ sufficiently large,

$$
\sum_{m\le Y}\Lambda(m)
\sum_{b\bmod m}|n_m(b)-n_m^*(b)|^2
=o(N^2).
\tag{16}
$$

For the powers of two, apply the theorem at modulus $2m$, which remains within the allowed range after adjusting $B$.

The discrete difference operator has squared norm at most four. Expanding the energy of $n_m^*+(n_m-n_m^*)$, then applying Cauchy–Schwarz to (16), gives

$$
\sum_{m\le Y}\Lambda(m)(E_m-E_m^*)
=o(N^2).
$$

Finally,

$$
\begin{aligned}
\sum_{m\le Y}\Lambda(m)E_m^*
&=(C_*+o(1))N^2,\\
N\psi(Y)&=o(N^2).
\end{aligned}
$$

The first follows by summing (15) and using convergence of the resulting prime series. The second uses $B>1$ and $N\sim X/L$. This proves (14).

Consequence

Small and intermediate moduli contribute a positive constant times $N^2$.

Therefore they do not themselves establish the desired complement upper bound. The larger prime moduli must produce a compensating negative contribution, with a strictly additional negative reserve if twins are to be forced.

6. Exact accounting of the remaining large-prime terms

First, proper prime powers above $Y$ are negligible.

Each residue class modulo $m>Y$ contains $O(L^B)$ possible $a_i$. Consequently,

$$
E_m\le\sum_b n_m(b)^2\ll NL^B.
$$

The total contribution from powers $\ell^h>Y$ with $h\ge2$ is bounded in absolute value by

$$
O\!\left(NL^B\sqrt X\,L^2\right)=o(N^2).
$$

Thus only genuine prime moduli $\ell\in(Y,H]$ remain.

Define the complete nonzero-gap contribution

$$
\begin{aligned}
V_X=\sum_{Y<\ell\le H}\log\ell
\sum_{j\ge1}\bigl(
2r(j\ell)-r(j\ell-1)-r(j\ell+1)
\bigr),
\end{aligned}
\tag{17}
$$

where the outer sum runs over primes. All $j$ outside the possible difference range contribute zero; the surviving $j$ are $O(L^B)$.

For these moduli, the exact expansion is

$$
E_\ell-N
=-T+
\sum_{j\ge1}
\bigl(2r(j\ell)-r(j\ell-1)-r(j\ell+1)\bigr).
\tag{18}
$$

Combining the complete identity (11) with (14) and the proper-prime-power bound proves

$$
\boxed{
V_X=-C_*N^2+o(N^2).
}
\tag{19}
$$

Indeed, the omitted contribution $T\vartheta(Y)$ is $o(N^2)$, even using only $T\le N$.

This is an unconditional evaluation of the entire signed nonzero-gap combination in (17). It includes both shifted branches and their exact coefficients.

The consequence is decisive for this attempted repair: the nonzero-gap large-prime contribution cancels precisely the positive constant obtained from smaller moduli. It does not leave a reserve that can be credited toward twin primes.

The surviving term is

$$
-T\sum_{Y<\ell\le H}\log\ell.
$$

Dropping it would discard the exact arithmetic quantity the construction was intended to detect.

Testing a prime-moduli large-sieve repair

I inspected Theorem 2 of Iwaniec's The large sieve with prime moduli.

For the present prime-supported coefficients, its rough-support hypothesis is satisfied. Fourier inversion gives, for odd prime $\ell$,

$$
E_\ell=
\frac1\ell\sum_{s=1}^{\ell-1}
\left(1-\cos\frac{4\pi s}{\ell}\right)
\left|\sum_{p\in\mathcal P_X}
e\!\left(\frac{sp}{\ell}\right)\right|^2.
$$

Applying Iwaniec's theorem on dyadic modulus intervals and using the bounded Fourier multiplier yields

$$
\sum_{Y<\ell\le H}\log\ell\,E_\ell
\ll HN.
$$

The theorem applies because the modulus scale is at least $X/L^B$, and the prime-supported coefficients avoid the required small primes.

ems.press

However, its absolute constant does not establish a leading coefficient of one followed by a negative correction of size $N^2$.

The required improvement is an additive $X^2/L^2$ correction to a quantity of order $X^2/L$. The published large-sieve estimate does not resolve this correction.

7. Testing the multiplicity mechanism

Alpöge's construction gains multiplicity through iterated arithmetic maps. I tested the corresponding elementary operation on the Cauchy determinant: replace each interpolation point by $u$ confluent derivative rows and columns.

For $0\le i,j<u$, use the normalized derivative entries

$$
\frac{(-1)^{i+j}\binom{i+j}{i}}
{(1+a_r-a_s)^{i+j+1}}.
$$

The confluent Cauchy determinant formula, obtained by coalescing $u$ distinct points at each original point, gives the determinant $R^{u^2}$.

To make the matrix integral, multiply derivative row $i$ by $b_H^{i+1}$, and derivative column $j$ by $b_H^j$. The determinant acquires the factor $b_H^{Nu^2}$.

The resulting integer determinant is therefore exactly

$$
\boxed{
\Delta_X^{(u)}=\Delta_X^{u^2}.
}
$$

In particular,

$$
v_\ell(\Delta_X^{(u)})
=u^2v_\ell(\Delta_X)
$$

and

$$
\log|\Delta_X^{(u)}|
=u^2\log|\Delta_X|.
$$

This multiplicity operation gives no relative gain whatsoever. Divisibility, denominator cost and archimedean size all scale by the identical factor.

It cannot reproduce the economical multiplicity amplification needed from the Alpöge–Claude construction.

8. The exact remaining required fact

The strongest surviving reduction from this investigation is the following one-sided criterion.

For some fixed $c>0$, prove on an unbounded sequence that

$$
\boxed{
\sum_{\substack{X/L^B<\ell\le H\\\ell\ \mathrm{prime}}}
\log\ell\,(E_\ell-N)
\le -(C_*+c)N^2.
}
\tag{20}
$$

Everything outside this sum has been accounted for at the required $o(N^2)$ precision.

Condition (20) would establish a positive main-scale twin-prime lower bound. Conversely, the exact identities show that it requires genuinely new information about the shifted covariance at near-linear prime moduli. It is not supplied by the ordinary progression mean-square theorem, the prime-moduli large sieve, or an evaluation of all nonzero-gap terms.

Research verdict: the shifted Cauchy determinant is a valid arithmetic construction with exact local valuations and a controlled real size. The Fermat construction supplies genuine additional divisibility under absence of twins, but at excessive height. Neither construction currently establishes the required strict inequality.

I independently derived and algebraically checked these constructions and selected their parameters. No separate external or subagent validation is asserted. The two requested PDFs were accessible as indexed mathematical text; their screenshot retrieval failed. The additional primary-source theorem statements were inspected, and the Iwaniec theorem's PDF page was retrieved successfully. No local notes, files, downloads, installations or external messages were used.

The unconditional twin-prime conjecture remains unresolved by this argument.

---

### Recovered response 2

1. Exact rational-twist extraction

The rational-frequency mechanism works unconditionally. In fact, the common-multiple contamination disappears exactly for the logarithmic derivative, rather than merely being bounded.

Let

$$
F(s)=-\frac{\zeta'(s)}{\zeta(s)}
=\sum_{a\ge1}\frac{\Lambda(a)}{a^s},
\qquad \Re s>1.
$$

For odd $n>1$, put

$$
r_n=\frac{n+2}{n}.
$$

Since $\gcd(n,n+2)=1$, the rational number $r_n$ is reduced.

Absolute convergence gives the exact limiting Fourier coefficient

$$
\begin{aligned}
I_\sigma(n)
&=\lim_{T\to\infty}
\frac1T\int_T^{2T}
r_n^{it}|F(\sigma+it)|^2\,dt\\
&=\sum_{\substack{a,b\ge1\\a/b=r_n}}
\frac{\Lambda(a)\Lambda(b)}{(ab)^\sigma}.
\end{aligned}
$$

Every resonant pair has

$$
a=(n+2)d,\qquad b=nd
$$

for some positive integer $d$.

If $d>1$ and both Mangoldt coefficients are nonzero, then $a,b$ must be powers of the same prime, because they share a prime divisor of $d$. Their reduced ratio would therefore have numerator or denominator one. But both $n$ and $n+2$ exceed one.

Consequently only $d=1$ can contribute:

$$
\boxed{
I_\sigma(n)=
\frac{\Lambda(n)\Lambda(n+2)}
{[n(n+2)]^\sigma}.
}
\tag{1}
$$

No Riemann-hypothesis assumption is involved.

The ordinary diagonal $a=b$ is also excluded automatically because $r_n\ne1$.

Define

$$
S(X)=\sum_{\substack{X<n\le2X\\n\text{ odd}}}
\Lambda(n)\Lambda(n+2).
$$

Proper prime powers contribute at most $O(\sqrt X\log^2X)$, since the number of proper powers up to $2X+2$ is $O(\sqrt X)$.

Hence an unconditional lower bound $S(X)\ge cX$, with any fixed $c>0$ on unbounded scales, would imply

$$
\#\{X<p\le2X:p,p+2\text{ prime}\}
\gg_c \frac{X}{\log^2X}.
$$

The question is whether the zeta representation supplies such a lower bound independently, rather than simply encoding $S(X)$.

2. A finite-height estimate with all near-resonances controlled

The limiting identity can be made quantitative at heights just above $X^2$, even using the full, untruncated logarithmic derivative.

Choose a fixed nonnegative smooth function $w$, supported in $(1,2)$, with integral one. Take $\sigma=2$, and define

$$
\mathcal I(X,T)=
\frac1T\int_{\mathbb R}
w(t/T)|F(2+it)|^2
\sum_{\substack{X<n\le2X\\n\text{ odd}}}
[n(n+2)]^2r_n^{it}\,dt.
$$

Proved estimate. Uniformly for $T\ge X^2$,

$$
\boxed{
\mathcal I(X,T)=S(X)
+O_w\left(
X\left(\frac{X^2}{T}\right)^3
(\log(2T))^2
\right).
}
\tag{2}
$$

In particular, $T=X^2(\log X)^2$ suffices to make the error $o(X)$.

Proof of the error bound

For each $n$, expansion of the integral produces the Fourier factor

$$
\widehat w\left(T\log\frac{r_nb}{a}\right),
$$

using the Fourier convention with exponential $e^{iut}$.

The exact resonance is already evaluated in (1). For all other terms, write

$$
h=na-(n+2)b\ne0.
$$

When $a,b\asymp B$,

$$
\left|\log\frac{r_nb}{a}\right|
\gg\frac{|h|}{XB}.
$$

For each fixed $h$, the coprimality of $n,n+2$ restricts $b$ to one residue class modulo $n$. There are consequently $O(1+B/X)$ candidate pairs in this dyadic block.

Rapid Fourier decay gives, for every fixed $A>1$,

$$
\sum_{h\ne0}
\left(1+\frac{T|h|}{XB}\right)^{-A}
\ll_A
\begin{cases}
(XB/T)^A,&XB\le T,\\
XB/T,&XB>T.
\end{cases}
$$

Multiplying by $O(B^{-4}\log^2(2B))$ for the two Mangoldt-weighted coefficients and summing over blocks gives the following per-twist error:

$$
O_w\left(\frac{X^2}{T^3}\log^2(2T)\right).
$$

For completeness, blocks with $B<X$ contribute at most $O_w(X^{-4}(X^2/T)^A\log^2X)$ when $A>4$. The blocks between $X$ and $T/X$, and those above $T/X$, are both dominated by the transition scale $B\asymp T/X$. Noncomparable $a,b$ have a Fourier argument bounded away from zero before multiplication by $T$; absolute convergence makes their contribution $O_w(T^{-A})$.

Finally, the outer factor is $O(X^4)$, and there are $O(X)$ twists. This proves (2).

This is a genuine quantitative extraction of the target. No long common-multiple tail, diagonal contribution, or unpriced nearby rational frequency remains.

3. An unconditional Landau–Gonek zero-average analogue

I also obtained a corresponding finite-height identity over the actual nontrivial zeta zeros, without RH.

Let

$$
D_X(s)=
\sum_{\substack{X<a\le2X+2\\a\text{ odd}}}
\frac{\Lambda(a)}{a^s},
$$

and denote by $N_T$ the number of zeros $\rho=\beta+i\gamma$ with $T<\gamma\le2T$, counted with multiplicity.

Define

$$
\mathcal Z(X,T)=
\frac1{N_T}
\sum_{T<\gamma\le2T}
D_X(\rho)D_X(1-\rho)
\sum_{\substack{X<n\le2X\\n\text{ odd}}}
n\,r_n^\rho.
$$

Then

$$
\boxed{
\mathcal Z(X,T)=S(X)
+O\left(\frac{X^3(\log X)^3}{T}\right).
}
\tag{3}
$$

For example, $T=X^2(\log X)^5$ gives an error $O(X/(\log X)^2)$.

Exact treatment of the zero-sum main terms

Expanding both Dirichlet polynomials gives the frequency

$$
y=\frac{(n+2)b}{na}
$$

with coefficient $n\Lambda(a)\Lambda(b)/b$.

The frequency $y=1$ occurs only at $a=n+2,\ b=n$, on the nonzero Mangoldt support. Its zero sum is exactly $N_T$, yielding the required $S(X)$.

For $y\ne1$, apply the uniform Landau–Gonek formula. In its unconditional form, for $u>1$,

$$
\sum_{0<\gamma\le T}u^\rho
=-\frac{T}{2\pi}\Lambda(u)+E(u,T),
$$

where $\Lambda(u)=0$ unless $u$ is an integral prime power, and the error tracks both the distance from prime powers and the distance from $1$. For $u<1$, the functional equation gives the reciprocal version. The precise statements are reproduced as Theorem 2 and Corollary 2.1 in the primary paper of Durkan–Hughes–Pearce-Crump.

arxiv.org

Here $y$ lies in a bounded neighborhood of $[1/2,2]$. The only possible nonunit prime-power frequency or reciprocal frequency would be $2$ or $1/2$.

Both are excluded, since $a,b,n,n+2$ are odd.

Thus all Landau main terms outside the desired resonance vanish.

Summing the Landau errors

For sufficiently large $X$, the cited formula gives an upper bound of the form

$$
\left|\sum_{T<\gamma\le2T}y^\rho\right|
\ll
\log(2T)\left(
1+\frac1{|y-1|}
+\frac1{|y-2|}
+\frac1{|2y-1|}
\right).
$$

Each reciprocal distance has numerator $O(X^2)$ after the rational expression for $y$ is inserted.

The corresponding nonzero integer denominators are

$$
(n+2)b-na,\quad
(n+2)b-2na,\quad
2(n+2)b-na.
$$

For each prescribed value of any one of these integers, the associated linear Diophantine equation has $O(1)$ solutions in the two dyadic intervals. This uses $\gcd(n,n+2)=1$ and the bounded additional coefficients.

Summing their reciprocal absolute values therefore costs only $O(\log X)$ for each fixed $n$.

After inserting $n\Lambda(a)\Lambda(b)/b\ll(\log X)^2$, the aggregate error over $n,a,b$ is

$$
O\left(X^3(\log X)^3\log(2T)\right).
$$

Division by $N_T\asymp T\log T$ proves (3).

This gives a rigorous spectral reformulation in precisely the high-height regime proposed. It does not rely on treating $\rho$ as $1/2+i\gamma$. Off RH, the product $D_X(\rho)D_X(1-\rho)$ must remain as written.

4. A resonator test with its complete quadratic term

I tested a resonator constructed from precisely the proposed rational frequencies. Its second-order term can also be evaluated, including the additional resonances caused by prime powers.

Write

$$
\begin{aligned}
P(t)&=D_X(1/2+it),\\
R(t)&=\sum_{\substack{X<n\le2X\\n\text{ odd}}}r_n^{it},\\
V&=\sum_{\substack{X<a\le2X+2\\a\text{ odd}}}
\frac{\Lambda(a)^2}{a}\sim(\log2)\log X,\\
C&=\sum_{\substack{X<n\le2X\\n\text{ odd}}}
\frac{\Lambda(n)\Lambda(n+2)}{\sqrt{n(n+2)}}.
\end{aligned}
$$

Let $M$ be the number of rational twists, so $M\sim X/2$. Denote the infinite-height mean by angle brackets.

The linear term is exactly

$$
\langle |P|^2R\rangle=C.
$$

The potentially useful independent input is the quadratic term. I obtain

$$
\boxed{
\langle |P|^2|R|^2\rangle=MV+E,
\qquad 0\le E\ll(\log X)^4.
}
\tag{4}
$$

If $P$ is restricted to genuine primes rather than prime powers, then $E=0$ exactly.

Proof of the off-diagonal bound

For distinct odd $n,m$ in the dyad,

$$
\frac{r_n}{r_m}
=\frac{(n+2)m}{n(m+2)}.
$$

Put $g=\gcd(n,m)$ and $h=\gcd(n+2,m+2)$. Its reduced form is

$$
\frac{((n+2)/h)(m/g)}
{(n/g)((m+2)/h)}.
$$

All four displayed factors exceed one: distinct integers in the same dyadic interval cannot divide one another.

Both the reduced numerator and denominator are consequently composite. Such a frequency cannot equal a ratio of two distinct primes, or a ratio of powers of the same prime.

For a resonance on the full Mangoldt support, both reduced integers must therefore be proper prime powers of distinct bases. The common-multiple argument from Section 1 again excludes additional multiples.

For a fixed such pair $a,b$, the resonance equation is

$$
a n(m+2)=b m(n+2).
$$

Writing $d=a-b\ne0$, this becomes

$$
(dn-2b)(dm+2a)=-4ab.
$$

There are at most $2\tau(4ab)$ possible pairs $n,m$. Since $a,b$ are prime powers of size $O(X)$,

$$
\tau(4ab)\ll(\log X)^2.
$$

There are $O(X)$ ordered pairs of proper prime powers in the dyad, each with coefficient at most $O((\log X)^2/X)$. This gives $E\ll(\log X)^4$, as claimed.

The ordinary resonance $n=m$ gives exactly $MV$.

Consequence for the positive resonator

For every real $\lambda$,

$$
\boxed{
\langle |P|^2|1+\lambda R|^2\rangle
=V+2\lambda C+\lambda^2(MV+E).
}
\tag{5}
$$

This calculation also holds at finite height $T=X^6$, with arbitrarily small power errors for the three coefficients after smooth averaging. Indeed, each nonresonant frequency in the quadratic expansion has numerator and denominator $O(X^3)$, so its logarithmic distance from zero is at least a constant times $X^{-3}$.

Nonnegativity of (5) yields only

$$
C^2\le V(MV+E),
$$

an upper bound, not a positive lower bound.

The resonator does not generate a new positive main term: the sole linear coefficient is the sought twin correlation.

There is nevertheless a precise variational formulation. The optimal reduction of the mean-square value below $V$ is

$$
V-\min_{\lambda\in\mathbb R}
\langle |P|^2|1+\lambda R|^2\rangle
=\frac{C^2}{MV+E}.
$$

An independently established reduction of at least $c/(X\log X)$, for fixed $c>0$ on unbounded scales, would force $C\gg1$, and hence a main-scale twin lower bound. No such reduction has been proved.

5. Why known positive twisted zeta moments do not transfer

Theorem 1 of Bettin–Chandee–Radziwiłł, The mean square of the product of the Riemann zeta function with Dirichlet polynomials, supplies a particularly relevant positive twisted main term.

By polarizing their mean-square formula, for $T=X^6$ and odd $n\in(X,2X]$, one obtains

$$
\begin{aligned}
&\frac1T\int w(t/T)r_n^{it}
|\zeta(1/2+it)|^2\,dt\\
&\quad=
\frac{\log\!\left(\frac{T}{2\pi n(n+2)}\right)+c_w}
{\sqrt{n(n+2)}}+O_w(X^{-2}),
\end{aligned}
\tag{6}
$$

where $c_w=2\gamma+\int w(u)\log u\,du$, and $\gamma$ here denotes Euler's constant.

The error follows from their theorem's explicit estimate after multiplying by $\sqrt{n(n+2)}/T$. The length of the two-term twisting polynomial is $O(X)$, comfortably within their admissible range.

math.mcgill.ca

This gives a genuinely positive main term of order $(\log X)/X$ for every such rational twist, even when $n$ and $n+2$ are composite.

However, this positivity does not survive the operation required to extract logarithmic derivatives.

Exact cancellation under differentiation of zeta ratios

For $\sigma>1$ and sufficiently small complex $\alpha$, write

$$
\frac{\zeta(s+\alpha)}{\zeta(s)}
=\sum_{m\ge1}\frac{c_\alpha(m)}{m^s}.
$$

The Euler factors give

$$
c_\alpha(m)=
m^{-\alpha}\prod_{p\mid m}(1-p^\alpha).
$$

Thus $c_\alpha(m)$ vanishes at $\alpha=0$ to order exactly $\omega(m)$, the number of distinct prime divisors of $m>1$.

In particular,

$$
c'_0(m)=-\Lambda(m).
$$

The limiting rationally twisted average of two independent zeta ratios is exactly

$$
J_{\alpha,\beta}(n)=
\sum_{d\ge1}
\frac{c_\alpha((n+2)d)c_\beta(nd)}
{[n(n+2)d^2]^\sigma}.
$$

Absolute convergence in a neighborhood of $(0,0)$ justifies termwise differentiation.

Consequently,

$$
\boxed{
\left.
\frac{\partial^2 J_{\alpha,\beta}(n)}
{\partial\alpha\,\partial\beta}
\right|_{\alpha=\beta=0}
=
\frac{\Lambda(n)\Lambda(n+2)}
{[n(n+2)]^\sigma}.
}
\tag{7}
$$

Every common multiple with $d>1$ disappears.

This identifies exactly where the known positive zeta main term loses its usefulness. Introducing the reciprocal zeta factors and differentiating eliminates the composite contributions, but also eliminates the positive main term whenever the desired prime-power pair is absent.

A twisted-ratios calculation therefore needs a new estimate for the mixed derivative in (7). Positivity of the undifferentiated zeta moment does not establish it.

6. Functional-equation repair: an independent arithmetic main term

There is another relevant approach in the January 2026 primary preprint of Durkan–Hughes–Pearce-Crump, arXiv:2601.18025.

Its Theorem 5 studies

$$
\sum_{T<\gamma\le2T}\chi(\rho)x^\rho,
$$

where

$$
\zeta(s)=\chi(s)\zeta(1-s).
$$

For bounded $x\ge1$, its stated formula reduces to

$$
\sum_{T<\gamma\le2T}\chi(\rho)x^\rho
=
-x\sum_{T/(2\pi x)<j\le T/(\pi x)}
\Lambda(j)e^{2\pi ixj}
+O(\sqrt T\log^2T).
\tag{8}
$$

I checked the precise statement and its applicable range; I have not independently audited the entire proof of this new preprint.

arxiv.org

Unlike the ordinary Landau main term, (8) involves an additive prime sum. This creates a genuine alternative opportunity.

Take $x=r_n$ and choose $T=e^X$, which is permitted by the proposed high-height regime. Then

$$
e^{2\pi ir_nj}=e^{4\pi ij/n}.
$$

Since $n\le2X$ and $\log T=X$, the classical Siegel–Walfisz theorem applies uniformly to these residue classes.

Summing their main terms gives the Ramanujan sum

$$
\sum_{\substack{v\bmod n\\(v,n)=1}}
e^{4\pi iv/n}=\mu(n).
$$

The contribution from prime powers whose bases divide $n$ is $O(X\log X)$, negligible at this height.

Using arbitrary fixed logarithmic precision in Siegel–Walfisz therefore gives, for every fixed $A>0$,

$$
\boxed{
-\frac{2\pi\varphi(n)}{T}
\sum_{T<\gamma\le2T}\chi(\rho)r_n^\rho
=
\mu(n)+O_A(X^{-A}).
}
\tag{9}
$$

The error is uniform over the required odd integers $n$.

Using instead the reduced rational number

$$
x=\frac{2n}{n+2}>1
$$

gives the corresponding formula with $\mu(n+2)$.

What this repair achieves

The functional-equation twist retrieves the two Möbius values with very high accuracy. Unlike the logarithmic-derivative twist, it supplies an independently evaluable arithmetic main term through prime distribution in progressions.

But the arithmetic information is different:

$$
\mu(n),\quad \mu(n+2)
$$

rather than

$$
\Lambda(n),\quad\Lambda(n+2).
$$

In particular, Möbius value $-1$ cannot distinguish a prime from a squarefree product of three distinct primes.

Multiplying the two recovered spectral expressions gives a shifted Möbius correlation, not a twin-prime count. Imposing a sufficiently strong roughness condition would repair this distinction, but no positive lower bound for the required jointly rough, doubly negative Möbius population follows from (9).

7. A rigorous obstruction to using untwisted higher moments

I tested whether arbitrarily precise ordinary moments, combined with positivity of the resonator, might force its missing linear term.

The following countermodel shows that fixed-order untwisted moments cannot do this by themselves, even for polynomials supported on genuine primes.

Let

$$
P_0(t)=\sum_{X<p\le2X+2}
\frac{\log p}{\sqrt p}\,p^{-it}.
$$

Delete every prime $p$ in this interval for which $p-2$ is also a prime in the interval.

The remaining support contains no gap-two pair.

The deleted population is $o(X/\log X)$. To verify this without a twin-prime conjecture, fix a finite set of odd primes $\ell$, apply the prime number theorem in residue classes modulo their product, and observe that the fraction of eligible prime residues is

$$
\prod_\ell\left(1-\frac1{\ell-1}\right).
$$

Taking the dyadic limit first and then enlarging the finite prime set makes this product tend to zero.

Now rescale all remaining coefficients by a common factor $1+o(1)$, obtaining $P_*(t)$, so that

$$
\langle |P_*|^2\rangle
=\langle |P_0|^2\rangle=V_0.
$$

Here $V_0\asymp\log X$.

Higher-moment comparison

For any prime-supported polynomial

$$
P(t)=\sum_p c_p p^{-it},
\qquad V_P=\sum_p|c_p|^2,
$$

unique factorization gives, for fixed integer $k\ge2$,

$$
\langle |P|^{2k}\rangle
=
k!V_P^k+
O_k\left(V_P^{k-2}\sum_p|c_p|^4\right).
$$

Indeed, terms involving $k$ distinct prime labels agree exactly with the corresponding expansion of $k!V_P^k$. The remaining terms are bounded by charging a repeated label among the $k$ positions.

For both $P_0$ and $P_*$,

$$
\sum_p|c_p|^4\ll\frac{(\log X)^3}{X}.
$$

Therefore

$$
\boxed{
\langle |P_*|^{2k}\rangle-
\langle |P_0|^{2k}\rangle
=
O_k\left(\frac{(\log X)^{k+1}}X\right).
}
\tag{10}
$$

Their ordinary second moments agree exactly, and every fixed higher moment agrees with an error tending to zero.

Yet

$$
\boxed{\langle |P_*|^2R\rangle=0.}
$$

Their quadratic rational-resonator terms also agree exactly, since both have prime-only support and the same $V_0$.

This model does not replace the actual zeta function. It establishes the narrower obstruction that even extremely precise untwisted moments, the correct diagonal, genuine prime support and positive quadratic-resonator identities do not force the adjacent-prime coefficient.

8. Exact remaining proof obligation

The strongest independently derived results of this lane are:

Calculation
 |
Outcome
 |

Full logarithmic-derivative twist
 |
Exact prime-power pair extraction
 |

Finite continuous-height average
 |
Error $o(X)$ at $T=X^2\log^2X$
 |

Average over actual zeta zeros
 |
Error $o(X)$ at $T=X^2\log^5X$, without RH
 |

Quadratic rational resonator
 |
Complete diagonal and proper-power remainder
 |

Positive ordinary zeta twist
 |
Main term does not distinguish primes
 |

Functional-equation twist
 |
Recovers Möbius values using the stated preprint theorem
 |

Untwisted higher moments
 |
Explicit obstruction to extracting the target
 |

A sufficient new estimate is

$$
\boxed{
\Re\mathcal Z(X,X^2\log^5X)\ge cX
}
$$

for any fixed $c>0$ on an unbounded sequence.

Alternatively, it suffices to establish independently that the quadratic resonator in (5) improves upon its unperturbed mean-square value by at least

$$
\frac{c}{X\log X}.
$$

Both would imply infinitely many ordinary twin primes, with all prime-power contamination negligible.

The decisive finding is that height resolution is not the remaining obstacle. The rational frequencies can be resolved at the proposed heights with sufficient uniform accuracy. The unresolved issue is an independent positive lower bound for their combined coefficient.

I independently selected the smooth averaging argument, the odd-support Landau–Gonek calculation, the rational-resonator factorization and the prime-deletion moment test. These derivations were checked algebraically; no separate external validation or novelty claim is made. The functional-equation application retains its stated preprint dependency.

Only public mathematical sources were consulted. No project files, local notebooks, downloads or external messages were used.

No unconditional twin-prime lower bound has been established in this lane.

---

### Recovered response 3

1. The precise prime-producing sieve input

Work on $x/2<t\le x$, and put

$$
a_t=\Lambda(t+2),\qquad w_t=a_t-b_t.
$$

The required two-coefficient estimate is

$$
\boxed{
\left|
\sum_{\substack{m\asymp M,\ n\asymp N\\x/2<mn\le x}}
\alpha_m\beta_n w_{mn}
\right|
\ll_A \frac{x}{(\log x)^A},
\qquad MN\asymp x,
}
\tag{II}
$$

uniformly for divisor-bounded coefficients

$$
|\alpha_m|\le\tau(m)^B,\qquad
|\beta_n|\le\tau(n)^B,
$$

where $B$ is fixed.

This is the strong bilinear hypothesis used in prime-producing sieves, not just an estimate for a particular Möbius-weighted sum.

Ford and Maynard's On the theory of prime-producing sieves, Theorem 2.2, gives a precise criterion for when Type I and Type II information determines the prime mass of a sequence. For example, Type I through exponent $2/3$ together with Type II on $[1/3,2/3]$ is sufficient, subject to their growth condition.

arxiv.org

For the present sequence, the resulting prime mass is

$$
\sum_{x/2<p\le x}\Lambda(p+2).
$$

After removing proper prime powers, a positive main-scale lower bound for this quantity proves ordinary twin primes.

2. A comparison model for which Type II is already false

Matching the ordinary divisor-density main terms is not enough. Consider the superficially natural multiplicative comparison

$$
b_t^{(0)}
=K_0\mathbf1_{2\nmid t}
\prod_{\substack{\ell\mid t\\\ell>2}}
\frac{\ell-1}{\ell-2},
$$

where

$$
K_0=2\prod_{\ell>2}
\left(1-\frac1{(\ell-1)^2}\right).
$$

This model has the appropriate reduced-class divisor densities in the mean. But it has forgotten which residue classes make $t+2$ composite.

Take both coefficient rows supported on genuine primes:

$$
\alpha_m=\mathbf1_{\{m\text{ prime},\ m\equiv1\bmod3\}},
$$

$$
\beta_n=\mathbf1_{\{n\text{ prime},\ n\equiv1\bmod3\}}.
$$

Choose fixed-proportion rectangles contained in the product dyad, with $M,N$ both of polynomial size.

Then $mn+2\equiv0\bmod3$. Hence $\Lambda(mn+2)=0$, except when $mn+2$ is a power of three. There are only $O(\log x)$ possible powers, each with at most $x^{o(1)}$ representations.

On the other hand, $b_{mn}^{(0)}\ge K_0$. The prime number theorem in fixed progressions gives

$$
\boxed{
\sum_{m,n}\alpha_m\beta_n
(a_{mn}-b_{mn}^{(0)})
\le -c\frac{x}{(\log x)^2}
}
$$

for some fixed $c>0$ and all sufficiently large $x$.

Thus (II) is false for this comparison whenever the required precision exceeds two logarithmic powers.

This counterexample uses the actual shifted von Mangoldt function and two genuine prime-supported coefficient rows. It is not an artificial parity model.

3. Correcting the local comparison

Write $L=\log x$. Choose the subpower cutoff

$$
z=\exp(L^{9/20}),
\qquad
V(z)=\prod_{\ell\le z}(1-\ell^{-1}),
$$

and define

$$
\boxed{
b_t=\frac{\mathbf1_{\{P^-(t+2)>z\}}}{V(z)}.
}
\tag{1}
$$

Here $P^-(u)$ is the least prime divisor of $u$.

This is the appropriate Cramér-type comparison: it retains the actual small-prime obstructions on the shifted integer.

The normalization matters. In particular, it makes the unrestricted average of $b_t$ asymptotic to one.

Established Type I estimate

For every fixed $\delta,A,B>0$,

$$
\boxed{
\sum_{q\le x^{1/2-\delta}}\tau(q)^B
\max_J
\left|
\sum_{\substack{t\in J\\q\mid t}}
(a_t-b_t)
\right|
\ll_{A,B,\delta}\frac{x}{L^A},
}
\tag{2}
$$

where $J$ ranges over intervals contained in $(x/2,x]$.

For $a_t$, this follows from the maximal Bombieri–Vinogradov theorem. When $q$ is odd, the main term is $|J|/\varphi(q)$. When $q$ is even, only powers of two can contribute to $\Lambda(t+2)$; their total divisor-weighted contribution is $x^{o(1)}$.

For $b_t$, the Chinese remainder theorem gives the local main term, for odd $q$,

$$
\frac{|J|}{q}
\prod_{\substack{\ell\mid q\\\ell\le z}}
(1-\ell^{-1})^{-1}.
$$

To justify this without counting over the enormous complete presieving period, truncate inclusion–exclusion after $R=\lceil C\log L\rceil$ prime labels.

Every retained divisor has size at most

$$
z^{R+1}=x^{o(1)}.
$$

The truncation error is bounded using the factorial tail

$$
\frac{(\sum_{\ell\le z}\ell^{-1})^{R+1}}{(R+1)!},
$$

which is smaller than any prescribed negative power of $L$ when $C$ is sufficiently large. The total CRT floor error is $x^{o(1)}$ per $q$.

Finally,

$$
\prod_{\substack{\ell\mid q\\\ell>z}}
(1-\ell^{-1})^{-1}
=1+O(L/z).
$$

This is negligible at every fixed logarithmic precision. Summing the divisor-weighted errors proves (2). The usual weighted extension of Bombieri–Vinogradov follows by Cauchy–Schwarz and divisor moments.

Why not retain a fixed polylogarithmic cutoff?

There is another genuine uniformity obstruction.

Suppose instead that $z=L^C$, with $C$ fixed, and demand (II) for arbitrarily large $A$ using that same model.

Choose a prime $\ell\in(z,2z)$, and restrict the two prime rows to

$$
m\equiv1\pmod\ell,\qquad
n\equiv-2\pmod\ell.
$$

Then $mn+2$ is divisible by $\ell$, but this obstruction is invisible to the presieve.

Siegel–Walfisz and the small-prime inclusion–exclusion calculation give comparison mass of order

$$
\frac{x}{\ell^2L^2}\asymp\frac{x}{L^{2C+2}}.
$$

The actual Mangoldt mass is negligible, since it comes only from powers of $\ell$.

Thus a fixed polylogarithmic cutoff fails the requested arbitrary-logarithmic uniformity for sufficiently large $A$.

One must either choose $C$ after the requested precision or use a subpower cutoff as in (1).

4. What the recent dilation estimates actually provide

Walsh: reconstruction from occupied prime-factor banks

I inspected the original manuscript Shifted convolutions of divisor functions, arXiv:2610.40439, particularly Proposition 4.1, Corollary 4.4 and Section 4.4.

Walsh uses banks of primes contained in

$$
[\exp(L^{1/8}),\exp(L^{1/4})]
$$

and

$$
[\exp(L^{1/3}),\exp(L^{2/5})].
$$

The reconstruction requires sufficiently many banks containing exactly one distinct prime divisor of each shifted integer. The exceptional-set estimate is derived for fixed-order divisor-function weights, using an enveloping measure.

arxiv.cnoctave.top+1

If $m,n$ are primes of fixed polynomial size, then

$$
\omega_{\mathcal B}(mn)=0
$$

for every such bank $\mathcal B$.

Consequently, the entire prime-by-prime coefficient test belongs to the exceptional population. Walsh's arbitrary-logarithmic savings for the reconstructed typical contribution do not bound this population at the required scale.

Lü–Wang–Wu and the Poisson–Dirichlet estimate

In the accessible original text of Lü–Wang–Wu, arXiv:2610.20242v1, the auxiliary weight is

$$
\mathcal W(u)=
\prod_{i=1}^K
\frac{\rho^{\omega_i(u)-1}\omega_i(u)}{V_i},
$$

where $\omega_i$ counts prime divisors in the corresponding subpower bank.

This weight vanishes unless every bank supplies a divisor. The determinant calculation exploits the ability to extract products of those divisors.

arxiv.t3mt.com

The Poisson–Dirichlet machinery has a particularly relevant extension in Hu–Lü–Wang–Wu's November preprint, On the higher-order Titchmarsh divisor problem.

I inspected Lemma 4.1 directly. It concerns a fixed nonzero shift $h$, and a coefficient of the specific form

$$
\alpha_m=m^{it}
\left(
\mathbf1_{\{m\text{ prime}\}}-
\frac{\mathbf1_{\{P^-(m)>Z\}}}{V(Z)\log m}
\right).
$$

Its second coefficient is supported on $Z$-rough integers. The asserted conclusion is cancellation in

$$
\sum_{m,n}
\alpha_m\beta_n
F(mn+h)\mathcal W(mn+h),
$$

where $F$ is bounded and invariant under multiplication by the selected bank primes.

arxiv.cnoctave.top

This is a significant bilinear estimate, but it differs from (II) in three essential ways:

-

The first coefficient has a prescribed centered prime-indicator form.

-

The shifted argument carries the mandatory divisor mark $\mathcal W$.

-

The remaining shifted function must satisfy a dilation-invariance hypothesis.

None of these conditions automatically disappears when one requests arbitrary two-coefficient uniformity.

Lichtman's improvement

Lichtman's 20 November preprint announces the bound

$$
\sum_{p\le x}\mu(p+2)
\ll_\varepsilon
\frac{\pi(x)}{L^{1/2-\varepsilon}},
$$

using an exact partition of prime intervals and arbitrary-logarithmic cancellation after excluding exceptional integers.

arxiv.org

The full manuscript did not load in this investigation, so I cannot certify a stronger Type II statement from its proof. The published abstract alone does not establish uniformity for the two arbitrary coefficient rows in (II).

5. A sharper obstruction: the marked estimate can become vacuous

For the comparison (1), every bank in the inspected Walsh and Lü–Wang–Wu constructions lies below $z$.

Consider inserting a mandatory bank mark into the desired discrepancy:

$$
\sum_{m,n}
\alpha_m\beta_n
\mathcal W(mn+2)(a_{mn}-b_{mn}).
\tag{3}
$$

Whenever $\mathcal W(mn+2)\ne0$, a prime below $z$ divides $mn+2$.

Therefore

$$
b_{mn}=0.
$$

Also, $a_{mn}=0$ unless $mn+2$ is a proper prime power.

The number of proper powers up to $x+2$ is $O(\sqrt x)$. Their factorizations into $mn$ have total divisor-bounded multiplicity $x^{o(1)}$.

Hence, for any bounded or fixed polylogarithmically bounded mark,

$$
\boxed{
(3)=O(x^{1/2+o(1)}).
}
\tag{4}
$$

This holds for arbitrary divisor-bounded coefficients.

The marked discrepancy is therefore already negligible for elementary reasons. Its cancellation does not measure the unmarked prime-producing discrepancy.

Marking $mn$ rather than $mn+2$ does not repair this: when both coefficient rows are supported on polynomial-sized primes, all those marks vanish identically.

What happens to the determinant calculation without the marks?

The marked argument produces equations of the form

$$
mn+h=A u,\qquad rs+h=B u,
$$

where $A,B$ are products of selected bank primes.

Eliminating $u$ gives

$$
Bmn-Ars=h(A-B).
$$

On the empty-bank population, the natural choices are $A=B=1$. The determinant relation collapses to

$$
mn=rs.
$$

For prime-supported rows in disjoint size intervals, unique factorization forces $m=r,\ n=s$. Thus the squared convolution norm is exactly

$$
\sum_t\left|
\sum_{mn=t}\alpha_m\beta_n
\right|^2
=
\left(\sum_m|\alpha_m|^2\right)
\left(\sum_n|\beta_n|^2\right).
$$

There is no additional prime-product averaging left to produce cancellation.

This identifies a specific failed step in the proposed extension: deleting the banks deletes the distinct dilation products that power the determinant argument.

6. A genuine partial Type II theorem

There is nevertheless a substantial class of coefficient rows for which the corrected comparison works unconditionally.

The following result covers arbitrary numerical dependence on the complete small-prime part of the longer variable, including multiplicities.

Theorem. Fix positive constants $\delta,\kappa$, with $\kappa<1$, and suppose

$$
x^\delta\le M\le x^{1/2-\delta},
\qquad MN\asymp x.
$$

Put $y=\exp(L^\kappa)$, and define the complete small-prime record

$$
n_y=\prod_{\ell\le y}\ell^{v_\ell(n)}.
$$

Let $\alpha_m$ be arbitrary divisor-bounded coefficients, and let

$$
\beta_n=G_x(n_y),
\qquad |G_x(u)|\le L^C,
$$

on the longer dyadic interval.

Then, for every fixed $A>0$,

$$
\boxed{
\sum_{\substack{m\asymp M,\ n\asymp N\\x/2<mn\le x}}
\alpha_mG_x(n_y)(a_{mn}-b_{mn})
\ll_{A,B,C,\delta,\kappa}\frac{x}{L^A}.
}
\tag{5}
$$

The function $G_x$ need not be multiplicative, smooth or independent of $x$.

Proof

On the set of $y$-smooth integers, define

$$
c(d)=\sum_{e\mid d}\mu(d/e)G_x(e).
$$

Möbius inversion gives the exact identity

$$
G_x(n_y)=
\sum_{\substack{d\mid n\\P^+(d)\le y}}c(d).
$$

Since only squarefree values of $d/e$ contribute,

$$
|c(d)|\le L^C2^{\omega(d)}.
$$

Choose

$$
D=x^{\delta/2}.
$$

First truncate the expansion to $d\le D$. The absolute discarded mass on $n\asymp N$ is bounded by

$$
2NL^C
\sum_{\substack{d>D\\P^+(d)\le y}}
\frac{2^{\omega(d)}}d.
$$

With $s=1/\log y$, Rankin's inequality gives

$$
\begin{aligned}
\sum_{\substack{d>D\\P^+(d)\le y}}
\frac{2^{\omega(d)}}d
&\le
D^{-s}
\prod_{\ell\le y}
\left(1+\frac{2}{\ell^{1-s}-1}\right)\\
&\ll
L^{O(1)}
\exp\left(-\frac{\delta}{2}L^{1-\kappa}\right).
\end{aligned}
$$

This beats every fixed logarithmic power.

Because $|a_t-b_t|\ll L$, and the divisor-bounded $m$-row has total absolute mass at most $ML^{O_B(1)}$, the complete discarded contribution is $O_A(x/L^A)$.

Now open the retained expansion and put $n=dk$. The modulus is

$$
q=md\le2MD\le x^{1/2-\delta/3}
$$

for sufficiently large $x$.

For each $m,d$, the $k$-sum has an interval restriction, including the original product dyad. Grouping by $q=md$ costs at most

$$
\sum_{d\mid q}|\alpha_{q/d}c(d)|
\le L^C\tau(q)^{B+2}.
$$

Apply the already proved Type I estimate (2), with the necessary extra logarithmic precision.

This proves (5).

Scope of the result

The theorem includes, without further work:

-

Arbitrary restrictions on the divisibility records in all the subpower banks.

-

Exact exclusion of selected small primes.

-

Complete valuation-dependent weights, not just squarefree masks.

-

Arbitrary coefficients on the shorter row, including genuine prime-supported coefficients.

Slowly varying additional factors on the longer row can be included by partial summation.

This is an actual estimate for the required discrepancy, not merely a calculation for the comparison sequence. Its limitation is that primality of the longer variable is not a function of its subpower small-prime record.

7. The prime-by-prime test after the repair

Let $m$ be a prime of polynomial size and $J_m\subseteq[N,2N]$ the interval allowed by the product cutoff.

The corrected model satisfies

$$
\boxed{
\sum_{\substack{n\in J_m\\n\text{ prime}}}b_{mn}
=
K_0\int_{J_m}\frac{du}{\log u}
+O_A(N/L^A),
}
\tag{6}
$$

uniformly in such $m$.

To prove this, expand the presieve by truncated inclusion–exclusion. For odd $\ell\le z$, the forbidden residue of $n$ modulo $\ell$ is reduced, because $m>z$.

Bombieri–Vinogradov at the scale $N$ evaluates the retained progression sums; their moduli are $z^{O(\log L)}=x^{o(1)}$.

The local factor is

$$
\frac{1-1/(\ell-1)}{1-1/\ell}
=
1-\frac1{(\ell-1)^2}.
$$

At two, the factor is two. Their product tends to $K_0$, with a tail smaller than every fixed negative power of $L$.

Thus the corrected reference has the right prime-by-prime main term.

Replace the longer prime indicator by its own rough approximation

Define

$$
c_z(n)=
\frac{\mathbf1_{\{P^-(n)>z\}}}{V(z)\log n}.
$$

A direct two-form CRT calculation gives

$$
\boxed{
\sum_{n\in J_m}c_z(n)b_{mn}
=
K_0\int_{J_m}\frac{du}{\log u}
+O_A(N/L^A).
}
\tag{7}
$$

At odd primes below $z$, the two forms $n$ and $mn+2$ exclude two distinct residue classes. At two, they exclude one class. These are precisely the twin-prime singular factors.

Subtracting (6) and (7),

$$
\sum_{n\in J_m}
\left(\mathbf1_{\{n\text{ prime}\}}-c_z(n)\right)b_{mn}
\ll_A N/L^A.
\tag{8}
$$

Meanwhile, Theorem (5), followed by partial summation for $1/\log n$, proves

$$
\sum_{m,n}\alpha_m c_z(n)(a_{mn}-b_{mn})
\ll_A x/L^A
$$

whenever the shorter row lies below $x^{1/2-\delta}$.

Combining these estimates gives the reduction

$$
\boxed{
\begin{aligned}
&\sum_{\substack{m,n\\n\text{ prime}}}
\alpha_m(a_{mn}-b_{mn})\\
&\quad=
\sum_{m,n}\alpha_m
\left(\mathbf1_{\{n\text{ prime}\}}-c_z(n)\right)
\Lambda(mn+2)
+O_A(x/L^A),
\end{aligned}
}
\tag{9}
$$

for arbitrary divisor-bounded, prime-supported $\alpha_m$ in the shorter range.

All comparison terms have been evaluated.

The remaining sum is a single centered prime-indicator estimate against the genuine shifted-prime weight, with no mandatory banks.

This is exactly the type of extension one would want from the Poisson–Dirichlet machinery. But its existing marked theorem does not cover it.

8. Testing whether the distribution of the prime factors can remove that remainder

A prime $n$ of polynomial size has

$$
n_y=1.
$$

Every $y$-rough composite has the same record.

The rough population in a fixed dyadic interval has cardinality asymptotic to $NV(y)$, whereas the prime population has cardinality of order $N/\log N$. Their ratio tends to infinity:

$$
\frac{NV(y)}{N/\log N}
\asymp\frac{\log N}{\log y}
\asymp L^{1-\kappa}.
$$

Consequently, no function of $n_y$ alone can approximate the prime indicator with negligible absolute error at the prime-counting scale.

Indeed, on the empty-record fiber, such a function is a constant $c$. If that fiber contains $P$ primes and $Q$ composites, then

$$
P|1-c|+Q|c|\ge P
$$

whenever $Q\ge P$.

Thus the best possible absolute approximation on this fiber still loses the entire prime population.

The same issue limits a direct inference from a Poisson–Dirichlet distribution law. Even granting the corresponding law for $p-2$, convergence of normalized prime-factor sizes would not determine the much smaller mass supported on exactly two polynomial-sized prime factors.

For example, the actual mass

$$
\sum_{\substack{m\asymp M,\ n\asymp N\\m,n\text{ prime}}}
\Lambda(mn+2)
$$

is at most $O(x/L)$ by the prime number theorem and the trivial bound $\Lambda\le L$. Deleting this entire population changes any bounded normalized factor-distribution statistic by $o(1)$.

Yet its predicted mass from (6) is of order $x/L^2$, which the Type II estimate must resolve.

Hence qualitative convergence of the factor distribution cannot supply the missing quantitative estimate.

9. The exact one-sided input that would prove twins

The full arbitrary-coefficient Type II hypothesis is stronger than necessary. Using the corrected model, one can isolate a single signed bilinear remainder through Vaughan's identity.

Take

$$
U=V=x^{0.24},
\qquad
\beta_V(n)=\sum_{\substack{d\mid n\\d>V}}\Lambda(d).
$$

Then

$$
0\le\beta_V(n)\le\log n.
$$

Vaughan's identity and the proved Type I estimate give

$$
\sum_{x/2<t\le x}\Lambda(t)w_t
=
R_x+O_A(x/L^A),
$$

where

$$
\boxed{
R_x=
\sum_{\substack{m>U,\ n>V\\x/2<mn\le x}}
\mu(m)\beta_V(n)
\left[
\Lambda(mn+2)-
\frac{\mathbf1_{\{P^-(mn+2)>z\}}}{V(z)}
\right].
}
\tag{10}
$$

The two short branches of Vaughan's identity use moduli at most

$$
UV=x^{0.48},
$$

strictly inside the proved Type I range.

The comparison prime mass is

$$
\sum_{x/2<t\le x}\Lambda(t)b_t
=\frac{K_0x}{2}+o(x),
$$

by the prime-only reference calculation and partial summation.

Proper prime powers on either side of the shifted correlation cost $O(\sqrt xL^2)$. Therefore

$$
\boxed{
\sum_{\substack{x/2<p\le x\\p,\ p+2\text{ prime}}}
\log p\log(p+2)
=
\frac{K_0x}{2}+R_x+o(x).
}
\tag{11}
$$

It follows that the one-sided bound

$$
\boxed{
R_x\ge-\frac{K_0x}{4}
}
\tag{12}
$$

on any unbounded sequence of scales would prove infinitely many ordinary twins.

No arbitrary-coefficient asymptotic is needed if this particular scalar can be controlled.

Independent-lane verdict

Proof obligation
 |
Result
 |

Naive multiplicative comparison
 |
Disproved for the actual prime-supported bilinear test
 |

Corrected presieved comparison
 |
Constructed and normalized
 |

Type I below the square root
 |
Proved
 |

Type II with arbitrary complete small-prime-record weights on the longer variable
 |
Proved
 |

Prime-by-prime comparison main term
 |
Evaluated
 |

Mandatory-bank removal
 |
Explicit support and approximation obstructions
 |

Unmarked centered-prime bilinear estimate (9)
 |
Unproved
 |

One-sided Vaughan remainder bound (12)
 |
Unproved
 |

The most useful surviving advance is Theorem (5): the full small-prime record, including powers and arbitrary dependence on its numerical value, can be handled with arbitrary logarithmic savings. That isolates the missing information in the large-prime factors rather than in the complexity of the bank weights.

The next decisive mathematical input must control the empty-bank contribution on the genuine shifted-prime source, particularly the centered-prime expression in (9) or the actual signed scalar (10).

I selected the subpower comparison and complete-record inversion independently. These partial estimates rely on classical Bombieri–Vinogradov, prime distribution and elementary divisor bounds, rather than the unverified portions of the recent preprints. Walsh's manuscript, the accessible Lü–Wang–Wu version and the fixed-shift extension in Hu–Lü–Wang–Wu were inspected. The newest Lü–Wang–Wu revision and Lichtman's full text could not be retrieved in this investigation; no stronger theorem has been attributed to them. Some PDF screenshot requests also failed.

No project files, old notebooks, downloads, installations or external messages were used. No external independent validation or novelty claim is asserted.

The unconditional twin-prime conjecture is not yet proved by this lane.

---

### Recovered response 4

1. Exact normalization and the fourth-moment target

Put $L=\log X$, $z=\exp(L^{1/4})$, and

$$
V(z)=\prod_{\ell\le z}(1-1/\ell).
$$

On a rectangular box $r,s\asymp M$, $u,v\asymp N$, with $MN\asymp X$, define

$$
A_{ru}=\Lambda(ru+2),\qquad
B_{ru}=\frac{\mathbf1_{\{P^-(ru+2)>z\}}}{V(z)}.
$$

Assume throughout that both lengths are polynomial:

$$
X^\delta\le M\le\sqrt X,\qquad MN\asymp X
$$

for fixed $\delta>0$.

For a matrix $F$, use the normalized box norm

$$
\|F\|_\square^4
=\mathbb E_{r,s,u,v}
F_{ru}\overline{F_{su}}F_{sv}\overline{F_{rv}},
$$

where each average is over its actual integer interval.

For real $F$, this is

$$
\|F\|_\square^4
=\mathbb E_{r,s}
\left(\mathbb E_u F_{ru}F_{su}\right)^2.
$$

The required estimate is

$$
\boxed{\|A\|_\square^4\le c+O_A(L^{-A}).}
\tag{1}
$$

Here and below, the constant in $O_A$ may depend on the fixed polynomial length margin.

The exact local constant

For an odd prime $\ell$, let $\nu_\ell(r,s)$ be the number of distinct forbidden residues of $u$ arising from

$$
ru+2\equiv0,\qquad su+2\equiv0\pmod\ell.
$$

There are three cases:

$\nu_\ell$
 |
Number of row pairs modulo $\ell$
 |

$0$
 |
$1$
 |

$1$
 |
$3(\ell-1)$
 |

$2$
 |
$(\ell-1)(\ell-2)$
 |

Conditionally on the rows, the two columns are independent in the residue model. The probability that all four forms avoid divisibility by $\ell$ is therefore

$$
\begin{aligned}
d_\ell
&=\frac{
1+3(\ell-1)(1-1/\ell)^2+
(\ell-1)(\ell-2)(1-2/\ell)^2
}{\ell^2}\\
&=1-\frac4\ell+\frac{10}{\ell^2}
-\frac{11}{\ell^3}+\frac5{\ell^4}.
\end{aligned}
$$

At two, all four variables must be odd, giving probability $1/16$, which is canceled exactly by the fourth power of the normalization.

Consequently,

$$
\boxed{
c=\prod_{\ell>2}
\left(
1+\frac{4\ell^2-7\ell+4}{(\ell-1)^4}
\right).
}
\tag{2}
$$

This converges absolutely to a finite positive constant.

The model satisfies, unconditionally,

$$
\|B\|_\square^4=c+O_A(L^{-A}).
\tag{3}
$$

To justify the growing presieve, truncate inclusion–exclusion over the four forms after $C_A\log L$ prime labels. Each retained modulus is

$$
z^{O_A(\log L)}=X^{o(1)}.
$$

The probability of divisibility of at least one form by $\ell$ is at most $4/\ell$. The first omitted factorial tail is therefore smaller than any prescribed negative power of $L$. The CRT counting errors over the four polynomial-length intervals cost only $X^{-\delta+o(1)}$ after normalization. Finally, the Euler-product tail beyond $z$ is $O(1/z)$.

Thus the comparison constant is established at the precision required in (1).

2. The mixed term can be evaluated, including the balanced endpoint

Define

$$
\mathcal M=
\mathbb E_{r,s,u,v}
A_{ru}B_{su}B_{sv}B_{rv}.
$$

I obtain the unconditional estimate

$$
\boxed{\mathcal M=c+O_A(L^{-A})}
\tag{4}
$$

throughout the polynomial range above, including $M\asymp\sqrt X$.

The useful point is that averaging the other two variables first produces divisor-linear weights rather than arbitrary progression residue classes.

Conditional local calculation

First remove proper prime powers from $A_{ru}$. There are $O(\sqrt X)$ proper powers in its numerical range, and each admits $X^{o(1)}$ representations as $ru+2$. Their normalized contribution, even with the three model weights, is $X^{-1/2+o(1)}$.

Thus $ru+2$ is a genuine prime, and $r,u$ are odd.

Fix $r,u$. For an odd prime $\ell\le z$, write

$$
i=\mathbf1_{\ell\mid r},\qquad
j=\mathbf1_{\ell\mid u}.
$$

Since $ru+2\not\equiv0\bmod\ell$, the number of pairs $(s,v)\bmod\ell$ for which the other three forms are nonzero is exactly

$$
\ell^2-3\ell+4+(\ell-2)(i+j)+ij.
\tag{5}
$$

Indeed, the conditions on $su+2$ and $rv+2$ remove up to two coordinate lines. The remaining forbidden hyperbola $sv=-2$ intersects each existing line once, and those two intersections cannot coincide because $ru\ne-2\bmod\ell$.

After normalization, the conditional local factor is a constant times

$$
1+a_\ell i+a_\ell j+b_\ell ij,
$$

where

$$
a_\ell=\frac{\ell-2}{\ell^2-3\ell+4},
\qquad
b_\ell=\frac1{\ell^2-3\ell+4}.
$$

At two, the conditional model mean contributes a factor two.

The same truncated inclusion–exclusion argument used in Section 1 evaluates the conditional average over $s,v$, uniformly in the fixed $r,u$, with arbitrary logarithmic precision.

Thus the mixed moment reduces to sums weighted by

$$
G_z(r,u)
=
\prod_{2<\ell\le z}
\left(
1+a_\ell\mathbf1_{\ell\mid r}
+a_\ell\mathbf1_{\ell\mid u}
+b_\ell\mathbf1_{\ell\mid r,\ \ell\mid u}
\right).
$$

The constant omitted here is bounded above and below uniformly in $z$.

Divisor expansion and endpoint theorem

Expand

$$
G_z(r,u)=\sum_{d\mid r,\ e\mid u}\lambda(d,e),
$$

where the coefficients are nonnegative and supported on squarefree $z$-smooth labels.

Their total absolute mass is bounded by a fixed power of $L$, because

$$
\sum_{\ell\le z}(2a_\ell+b_\ell)\ll\log L.
$$

Truncating the expansion to at most $C_A\log L$ prime labels gives arbitrary logarithmic accuracy, and every retained $de$ is $X^{o(1)}$.

For each retained pair, put $r=dr'$, $u=eu'$. The actual prime progression now has modulus

$$
q=de\,r'
$$

and fixed residue $2$.

This is exactly where the endpoint can be handled by Theorem 9 of Bombieri–Friedlander–Iwaniec, 1986. It gives arbitrary logarithmic cancellation for an unweighted inner modulus sum with an additional small factor, provided the total modulus remains below $X/L^C$. The authors' 2019 corrections leave its theorem statement unchanged.

archive.ymsc.tsinghua.edu.cn+1

Here

$$
de=X^{o(1)},\qquad
de\,r'\ll \sqrt X\,X^{o(1)},
$$

so both restrictions have ample room.

For clarity, the moving progression endpoints can be handled by partitioning the $r'$-interval into $L^C$ pieces, freezing the physical endpoints on each piece, and bounding the intervening thin strips using positivity and the same theorem. Increasing the requested logarithmic precision absorbs the number of pieces.

The progression main term for $B_{de\,r'u'}$ is the identical one, by small-prime inclusion–exclusion. The factor arising from primes of $de\,r'$ exceeding $z$ differs from one by $O(L/z)$.

Consequently, in this complete divisor-linear average, $A_{ru}$ can be replaced by $B_{ru}$ with arbitrary logarithmic accuracy. Equation (3) then proves (4).

This proof does not require an absolute progression estimate at every modulus near $\sqrt X$. It uses the signed, unweighted inner modulus average for which the BFI theorem actually applies.

3. Verification of the uniform-convexity implication

The proposed deduction from (1) and (4) is valid.

The normalized box norm is a rescaled Schatten-4 matrix norm. Its four-linear Hölder inequality gives

$$
|\mathcal M(A+B,B,B,B)|
\le\|A+B\|_\square\|B\|_\square^3.
$$

Using (3) and (4),

$$
\|A+B\|_\square\ge2c^{1/4}-O_A(L^{-A}).
$$

The Schatten-4 inequality

$$
\|A+B\|_\square^4+\|A-B\|_\square^4
\le8\bigl(\|A\|_\square^4+\|B\|_\square^4\bigr)
$$

then gives

$$
\boxed{\|A-B\|_\square^4\ll_A L^{-A}}
$$

if (1) holds.

This inequality follows directly by expanding the two fourth powers as matrix traces and applying Hilbert–Schmidt Cauchy–Schwarz to the cross terms.

Finally,

$$
\left|\mathbb E_{r,u}\alpha_r\beta_u(A_{ru}-B_{ru})\right|
\le
\|\alpha\|_2\|\beta\|_2\|A-B\|_\square.
$$

For divisor-bounded coefficients, the two $L^2$ norms cost only fixed logarithmic powers. Thus arbitrary-logarithmic precision in (1) would indeed imply the desired uniform Type II estimate.

The mixed moment and the convexity step are no longer missing inputs. The genuine four-prime upper bound remains the critical one.

4. Primitive row ratios and removal of all diagonals

The diagonals in the four-prime moment can be removed completely at the requested logarithmic precision.

First, a proper prime power in any of the four cells contributes a total normalized error

$$
O(X^{-1/2+o(1)}).
$$

Indeed, there are $O(\sqrt X)$ proper powers in the physical range, each has $X^{o(1)}$ possible divisor representations, and the other row and column have $O(X)$ choices.

The ordinary row and column diagonals $r=s$ or $u=v$ cost

$$
O\left(L^4\left(\frac1M+\frac1N\right)\right).
$$

There are also cross diagonals, such as $ru=sv$, which require separate treatment.

Write

$$
r=ga,\qquad s=gb,\qquad (a,b)=1.
$$

Then $ru=sv$ forces $u=bh,\ v=ah$. For $j=\max(a,b)$, there are $O(j)$ choices of the primitive pair, $O(M/j)$ choices of $g$, and $O(N/j)$ choices of $h$.

Summation gives $O(MN\log M)$ cross-diagonal quadruples. Their normalized contribution is

$$
O(L^5/X).
$$

The other cross diagonal is identical.

Moreover, removing

$$
\gcd(r,s)>D
\quad\text{or}\quad
\gcd(u,v)>D
$$

costs $O(L^4/D)$. Taking $D=L^{A+6}$ gives the desired negligible error.

Thus we may work with distinct genuine shifted primes, distinct rows and columns, and small common factors.

What fixing the primitive ratio actually leaves

For each primitive pair $a,b$ and common factor $g$, define

$$
Y_{a,b,g}(u)
=\Lambda(gau+2)\Lambda(gbu+2).
$$

After deleting the column diagonal, its contribution is exactly

$$
\boxed{
\left(\sum_uY_{a,b,g}(u)\right)^2
-\sum_uY_{a,b,g}(u)^2.
}
\tag{5}
$$

The second term is negligible globally. But the first term remains the square of a genuine two-prime count along the variable slopes $ga,gb$.

Divisor switching does not remove this square.

Indeed, putting $x=gu,\ y=gv$, the four primes become

$$
ax+2,\quad bx+2,\quad ay+2,\quad by+2.
$$

The switched representation carries the exact multiplicity

$$
D_{a,b}(x,y)
=
\#\{g\mid(x,y):
ga,gb\asymp M,\ x/g,y/g\asymp N\}.
$$

The primitive ratio $a:b$ is unique, but $g$ is not. Even after the gcd restrictions above,

$$
\gcd(x,y)\le D^2,
$$

and the multiplicity is bounded by a divisor function rather than identically one.

This distinguishes the usable divisor-switching identity from an unjustified assertion that primitive-ratio uniqueness eliminates every off-diagonal term.

5. A stronger reduction to the variance of two-prime counts

Below the balanced endpoint, another part of the fourth-moment calculation can be completed.

Define the row covariance matrices

$$
\begin{aligned}
K_A(r,s)&=\mathbb E_u A_{ru}A_{su},\\
K_B(r,s)&=\mathbb E_u B_{ru}B_{su},\\
K_{AB}(r,s)&=\mathbb E_u A_{ru}B_{su}.
\end{aligned}
$$

Suppose $M\le X^{1/2-\delta}$ for fixed $\delta>0$.

Then

$$
\boxed{
\mathbb E_{r,s}|K_{AB}(r,s)-K_B(r,s)|
\ll_A L^{-A}.
}
\tag{6}
$$

To prove this, expand the presieve on $su+2$ using the same truncated inclusion–exclusion as before. Its retained divisor labels satisfy

$$
d\le z^{O_A(\log L)}=X^{o(1)}.
$$

For each fixed $r,s,d$, the condition $d\mid su+2$, when nonempty, selects a residue class of $u\bmod d$. Consequently $ru+2$ lies in a single progression modulo $rd$.

The modulus satisfies

$$
rd\le X^{1/2-\delta/2}
$$

for sufficiently large $X$.

Bombieri–Vinogradov, including its maximum over reduced residue classes, evaluates the actual prime contribution. Grouping repeated moduli costs only a fixed divisor power. The sum over the additional row $s$ contributes a factor $O(M)$, canceled by normalization.

Nonprimitive progressions contain no genuine primes of the required size; their proper powers have already been paid. The model has precisely the same local restrictions, with a relative error $O(L/z)$ from prime divisors of $r$ exceeding the presieve cutoff.

The inclusion–exclusion tail remains negligible after multiplication by $\Lambda\le L+O(1)$.

This proves (6).

Since all covariance matrices are bounded by $O(L^2)$, (6) also holds in mean square with arbitrary logarithmic precision. Expanding the box norm of $A-B$ therefore gives

$$
\boxed{
\|A-B\|_\square^4
=
\mathbb E_{r,s}\bigl(K_A(r,s)-K_B(r,s)\bigr)^2
+O_A(L^{-A}).
}
\tag{7}
$$

This is a useful exact localization of the missing information.

For distinct odd rows, write

$$
\mathfrak S(r,s)=
\prod_\ell
\frac{1-\nu_\ell(r,s)/\ell}{(1-1/\ell)^2},
$$

and set it to zero if either row is even. The presieve calculation gives

$$
K_B(r,s)=\mathfrak S(r,s)+O_A(L^{-A})
$$

uniformly off the row diagonal.

Indeed, all exceptional odd primes divide $rs(r-s)$. Their contribution beyond $z$ changes the product by only $O(L/z)$.

Consequently, below the square root, the required fourth-moment estimate is equivalent to

$$
\boxed{
\mathbb E_{r\ne s}
\left|
\frac1{|\mathcal U|}
\sum_{u\in\mathcal U}
\Lambda(ru+2)\Lambda(su+2)
-\mathfrak S(r,s)
\right|^2
\ll_A L^{-A}.
}
\tag{8}
$$

All diagonal, model and mixed-column contributions have been accounted for.

At the balanced endpoint, the earlier global one-prime mixed moment remains established. I have not extended the stronger absolute mixed-column estimate (6) to that endpoint.

6. Two actual upper bounds obtained by sieving the slopes

Although I could not obtain the sharp constant $c$, the entire four-prime moment admits explicit unconditional upper bounds.

A. Sieve both forms after fixing the rows

For fixed distinct odd $r,s$, apply the dimension-two Selberg upper sieve to

$$
ru+2,\qquad su+2.
$$

The standard upper-bound constant is $8$ relative to the corresponding singular series. One primary exposition of the optimal Selberg denominator is Theorem 30 of Tao's sieve notes.

What's new

Here the application is uniform in the growing slopes.

In detail, choose the Selberg divisor cutoff

$$
R=N^{1/2}/L^C.
$$

The progression counting errors are $R^2L^{O(1)}$, negligible for sufficiently large $C$. The optimal denominator satisfies

$$
G(R)=
(1+o(1))
\frac{(\log R)^2}{2\mathfrak S(r,s)}.
$$

Uniformity follows by factoring its Dirichlet series into the dimension-two zeta factor and an absolutely convergent correction. The exceptional local corrections are supported on primes dividing $2rs(r-s)$; their absolute Euler products, including fixed logarithmic moments, cost only powers of $\log L$. This is negligible relative to the polynomial growth of $\log R$.

Multiplication by the Mangoldt weights gives

$$
K_A(r,s)
\le
(8+o(1))
\left(\frac{L}{\log N}\right)^2
\mathfrak S(r,s)
$$

for the genuine prime part.

Since the squared singular-series average is $c+O_A(L^{-A})$, this proves

$$
\boxed{
\|A\|_\square^4
\le
(64+o(1))
\left(\frac{L}{\log N}\right)^4c.
}
\tag{9}
$$

This bound includes the balanced endpoint, but its constant there is $1024c$, not $c$.

B. Average the slopes before paying the second primality condition

A better bound in part of the unbalanced range uses $\Lambda(ru+2)$ as the source sequence and sieves only $su+2$.

Write $M=X^\alpha$, with fixed $0<\alpha<1/2$.

For fixed distinct odd rows, an odd prime $\ell$ is active in the second sieve when

$$
\ell\nmid s(r-s).
$$

Its conditional density in the prime source is

$$
g_\ell=
\frac{\varphi(r)}{\varphi(r\ell)}
=
\begin{cases}
1/\ell,&\ell\mid r,\\
1/(\ell-1),&\ell\nmid r.
\end{cases}
$$

For the inactive primes the density is zero. At two the source already requires $u$ odd.

These densities satisfy the exact identity

$$
\frac r{\varphi(r)}
\prod_\ell\frac{1-g_\ell}{1-1/\ell}
=
\mathfrak S(r,s).
$$

Choose the sieve level

$$
D=X^{1/2-\alpha-\eta}
$$

with fixed $\eta>0$. The progression moduli $rd$, $d\le D$, lie below the Bombieri–Vinogradov boundary with fixed slack.

Applying the dimension-one Selberg upper sieve on this source gives

$$
K_A(r,s)
\le
\left(\frac{2}{1/2-\alpha-\eta}+o(1)\right)
\mathfrak S(r,s)+e_{rs},
$$

where $e_{rs}\ge0$ and

$$
\mathbb E_{r,s}e_{rs}\ll_A L^{-A}.
$$

The error follows by summing the divisor-weighted progression discrepancies over the rows and sieve labels. The maximum over residue classes permits the variable slopes. Squaring the inequality is legitimate after using the trivial $O(L^2)$ upper bound to absorb the exceptional errors.

Combining this with (9), and taking $\eta\downarrow0$ after the dyadic limit, gives

$$
\boxed{
\limsup_{X\to\infty}\frac{\|A\|_\square^4}{c}
\le
\min\left\{
\frac{64}{(1-\alpha)^4},
\frac4{(1/2-\alpha)^2}
\right\}.
}
\tag{10}
$$

For example, at $\alpha=0.24$, this improves the available factor to less than $59.18$.

The averaging of variable slopes has therefore produced a genuine improvement. It does not produce the asymptotically sharp constant required by uniform convexity.

The remaining problem is to evaluate the off-diagonal variance in (8), rather than merely upper-bound each of its two-prime populations by a fixed-factor sieve majorant.

7. Direct attack on the weaker Vaughan remainder

I then changed direction to the one-sided scalar, which does not require the entire four-prime asymptotic.

Use the physical interval $X/2<t\le X$, and write

$$
K_0=2\prod_{\ell>2}
\left(1-\frac1{(\ell-1)^2}\right),
\qquad
B_0=\frac{K_0X}{2}.
$$

Let

$$
b_t=\frac{\mathbf1_{\{P^-(t+2)>z\}}}{V(z)},
\qquad w_t=\Lambda(t+2)-b_t.
$$

Take $U=V=X^{0.24}$ in Vaughan's identity and put

$$
\beta_V(n)=\sum_{\substack{k\mid n\\k>V}}\Lambda(k).
$$

The short branches are controlled by Type I through moduli $UV=X^{0.48}$. Consequently,

$$
\sum_{\substack{X/2<p\le X\\p,\ p+2\ {\rm prime}}}
\log p\log(p+2)
=B_0+R+o(X),
\tag{11}
$$

where

$$
R=
\sum_{\substack{m>U,\ n>V\\X/2<mn\le X}}
\mu(m)\beta_V(n)w_{mn}.
$$

The comparison prime mass $B_0+o(X)$ follows by opening the subpower presieve on the actual prime $p$. Proper powers on either side cost $O(\sqrt X L^2)$.

Remove another complete range of Möbius rows

Use

$$
\beta_V(n)=\log n-\sum_{\substack{k\mid n\\k\le V}}\Lambda(k).
$$

On the complete sector $m\le X^{0.259}$, the first term uses moduli $m$, and the second uses moduli

$$
mk\le X^{0.259+0.24}=X^{0.499}.
$$

Thus ordinary Type I, with fixed slack, removes the entire sector at arbitrary logarithmic precision.

Define the remaining numerical coefficient

$$
K(t)=
\sum_{\substack{m\mid t\\m>X^{0.259}}}
\mu(m)\beta_V(t/m).
$$

Then

$$
R=\sum_{X/2<t\le X}K(t)w_t+O_A(X/L^A).
$$

A complete giant-prime sector collapses to semiprimes

Suppose $t=qv$, where $q>X^{0.741}$ is prime. Necessarily

$$
v<X^{0.259},\qquad q\nmid v.
$$

Every retained divisor $m$ must contain $q$. Thus

$$
\begin{aligned}
K(qv)
&=-\sum_{d\mid v}\mu(d)\beta_V(v/d)\\
&=-\Lambda(v)\mathbf1_{\{v>V\}}.
\end{aligned}
\tag{12}
$$

The second identity is exact Möbius inversion.

This is a substantial simplification: the entire giant-prime sector vanishes except when the complementary factor is a prime power above $V$.

Proper powers $v=p^j$, $j\ge2$, cost

$$
O(XV^{-1/2+o(1)})
$$

up to logarithmic factors, by their reciprocal tail.

Let $R_G$ be this complete sector of $R$. Equation (12) yields

$$
\begin{aligned}
R_G={}&-
\sum_{\substack{p,q\ {\rm prime}\\
p>X^{0.24},\ q>X^{0.741}\\X/2<pq\le X}}
\log p\,\Lambda(pq+2)\\
&+
\sum_{\substack{p,q\ {\rm prime}\\
p>X^{0.24},\ q>X^{0.741}\\X/2<pq\le X}}
\log p\,b_{pq}
+o(X).
\end{aligned}
\tag{13}
$$

Unlike an unsigned estimate of the original convolution, this retains its exact sign and its compensating comparison term.

Price both terms

Write $t=\log p/L$.

The reference sum in (13) equals

$$
B_0\int_{0.24}^{0.259}\frac{dt}{1-t}+o(X)
=
B_0\log\frac{0.76}{0.741}+o(X).
$$

For this calculation, fix the genuine prime $p$, open the presieve on $pq+2$, and apply prime distribution in the resulting subpower moduli at the scale $X/p$. The local constant is $K_0(1+o(1))$, uniformly in the selected $p$.

The actual prime contribution in (13) has the upper bound

$$
8B_0\int_{0.24}^{0.259}\frac{dt}{(1-t)^2}+o(X).
$$

This follows by applying the dimension-two Selberg upper sieve to $q,pq+2$ for each fixed $p$.

The endpoint collar $X^{0.259}/2<p\le X^{0.259}$, where the lower cutoff $q>X^{0.741}$ truncates the product interval, contributes $o(X)$. Its prime harmonic mass is $O(1/L)$, and the same uniform sieve bounds apply.

Therefore

$$
\begin{aligned}
R_G\ge -B_0\left[
8\left(\frac1{0.741}-\frac1{0.76}\right)
-\log\frac{0.76}{0.741}
\right]+o(X).
\end{aligned}
$$

Using the elementary lower bound

$$
\log\frac{0.76}{0.741}
\ge\frac{0.019}{0.76},
$$

the bracket is strictly less than $0.245$.

Established one-sided bound:

$$
\boxed{R_G\ge-0.245B_0+o(X).}
\tag{14}
$$

Let $R_{\rm rest}$ denote the remaining signed sum, retaining exactly $t$ with no prime factor exceeding $X^{0.741}$.

It now suffices to prove

$$
\boxed{
R_{\rm rest}\ge-0.75B_0
}
\tag{15}
$$

on an unbounded sequence.

Equations (11) and (14) would then give a weighted twin-prime lower bound of at least $(0.005+o(1))B_0$.

This is a proved payment of an entire arithmetic sector, not just another expression for its unknown contribution.

8. A separate divisor-switching extension beyond the square root

The previous giant-prime calculation uses fixed cutoffs $U=V=X^{0.24}$. I also tested a different representation, which must not be combined numerically with (14).

Retune to

$$
U=X^{0.488},\qquad V=X^{0.01}.
$$

Their product is $X^{0.498}$, so the initial Type I argument remains valid.

Maynard's Primes in arithmetic progressions to large moduli I, Theorem 1.1, supplies a fixed-residue distribution theorem for two modulus factors with exponent caps $q_1,q_2$ satisfying, with fixed slack,

$$
q_1+2q_2<1,\qquad
12q_1+7q_2<4,\qquad
20q_1+19q_2<10.
$$

I checked these inequalities against the actual theorem statement.

arxiv.org+1

Opening $\beta_V$ as before permits the following complete removals.

First: all $m\le X^{0.494}$. The modulus factors have caps $(0.01,0.494)$, giving

$$
0.998<1,\qquad
3.578<4,\qquad
9.586<10.
$$

Second: all $X^{0.494}<m\le X^{0.505}$ for which $m$ possesses a divisor

$$
X^{0.04}\le d\le X^{0.045}.
$$

Choose one such divisor deterministically, before applying the progression estimate. Factor the full modulus as

$$
mk=d\left(\frac md k\right).
$$

The two caps are $(0.045,0.475)$, giving

$$
0.995<1,\qquad
3.865<4,\qquad
9.925<10.
$$

Repeated moduli have only divisor-bounded multiplicity, absorbed by the weighted version of the absolute estimate. Moving physical endpoints are handled by partial summation and a logarithmic mesh, requesting sufficient extra precision. The reference progression means agree by the subpower presieve calculation.

Thus this alternative representation retains only

$$
\boxed{
m>X^{0.494},
\qquad
\left[
m>X^{0.505}
\ \text{or}\
m\text{ has no divisor in }[X^{0.04},X^{0.045}]
\right].
}
\tag{16}
$$

All removed terms together cost $O_A(X/L^A)$.

Why the remaining semiprimes matter

The convenient-divisor switching cannot remove a genuine prime row $m$.

For the squarefree semiprime portion of this retuned remainder, the normalized reference magnitude can be evaluated exactly. Put $a=0.494,\ b=0.01$. The smaller prime contributes the first orientation, and when both primes exceed $X^a$, both orientations survive.

The resulting magnitude is

$$
\begin{aligned}
\int_b^a\frac{dt}{1-t}
+\int_a^{1/2}\frac{dt}{t(1-t)}
&=\log\frac{1-b}{a}\\
&=\log\frac{0.99}{0.494}.
\end{aligned}
$$

This is approximately $0.695$ in units of $B_0$.

The direct two-form upper sieve gives the actual magnitude allowance

$$
8B_0
\left(
2-\frac1{1-b}
+\log\frac{1-a}{a}
\right)+o(X),
$$

which is greater than $8B_0$.

Consequently, even after the significant modulus-range improvement (16), paying the negative semiprime population by the ordinary upper sieve is insufficient. A much sharper upper bound or a separately established positive compensation is necessary.

This is a quantitative failure of that particular strategy, not a lower bound asserting that the actual negative population must be this large.

9. A genuine positive contribution in another signed representation

To test whether positive compensation can be obtained rather than estimated heuristically, I investigated one additional retuning.

Take $U=X^{0.24}, V=X^{0.12}$, and remove $m\le X^{0.25}$ by Type I. Write

$$
K'(t)=
\sum_{\substack{m\mid t\\m>X^{0.25}}}
\mu(m)\beta_{X^{0.12}}(t/m).
$$

Consider

$$
t=rsv,
$$

with distinct genuine primes in the disjoint windows

$$
X^{0.1251}<r\le X^{0.1255},
\qquad
X^{0.1256}<s\le X^{0.126},
$$

and require $P^-(v)>X^{0.126}$.

Every prime factor of $t$ exceeds $X^{0.12}$, so $\beta_V(t/m)=\log(t/m)$. After the negligible squareful exclusions, the divisors of $t$ below $X^{0.25}$ are exactly the unit and individual eligible prime factors: no product of two such factors lies below the cutoff.

If $j\ge2$ is their number, Möbius inversion gives

$$
K'(t)=(j-1)\log t-\sum_{\substack{p\mid t\\p\le X^{0.25}}}\log p.
$$

Hence, on this whole selected family,

$$
K'(t)\ge0.747L
$$

for sufficiently large $X$.

An actual lower sieve on the selected family

The relevant prime source is

$$
\Lambda(rsv+2).
$$

Sift $v$ through $X^{0.126}$, using a lower linear sieve at level

$$
D=X^{0.269}.
$$

Its sifting parameter exceeds two:

$$
s_{\rm lin}=\frac{0.269}{0.126}>2.
$$

The analytic issue is distributing the actual modulus $rsd$ for the lower-sieve divisors $d$.

The standard lower Rosser support, as described in Iwaniec's original linear-sieve paper, has the required ordered-prefix inequalities.

bibliotekanauki.pl

In the present case these imply an elementary two-bin factorization

$$
d=d_1d_2,\qquad
d_1\le X^{0.047},\quad d_2\le X^{0.222}.
$$

To verify it, insert the ordered prime factors into these two bins. If a new prime could fit into neither, the product of the already inserted factors times the square of that prime would exceed $D$, contradicting the support inequality.

Therefore the physical modulus factors as

$$
rsd=d_1(rs d_2)
$$

with caps $(0.047,0.4735)$. Maynard's three inequalities become

$$
0.994<1,\qquad
3.8785<4,\qquad
9.9365<10.
$$

All have fixed positive slack.

The actual prime distribution theorem thus applies to the complete lower-sieve expansion. The tags $r,s$ are unique because their windows are disjoint and the residual $v$ is rougher than either. Shared prime factors in the opened modulus change its local density by only a polynomially small relative error, since the tagged primes exceed $X^{0.1251}$.

Writing

$$
H_*=
\log\frac{0.1255}{0.1251}
\log\frac{0.126}{0.1256},
$$

the lower linear-sieve function yields

$$
\sum_{\text{selected }t}\Lambda(t+2)
\ge
\frac{B_0}{L}
H_*\frac{2}{0.269}
\log\left(\frac{0.269}{0.126}-1\right)
+o(X/L).
$$

This is strictly positive. In particular,

$$
\boxed{
\sum_{\text{selected }t}K'(t)\Lambda(t+2)
\ge
(6\cdot10^{-6}+o(1))B_0.
}
\tag{17}
$$

The displayed conservative constant follows using $\log(1+x)\ge x/(1+x)$ in each of the three logarithms.

This is a genuine favorable signed contribution on the actual prime source, obtained without assuming any twin-prime correlation.

However, it belongs to this separately retuned Vaughan representation, and (17) prices the $\Lambda$-part of that representation. Its corresponding model contribution and the entire complementary population must still be accounted for before crediting it toward a lower bound for the full remainder. I have not added it to either (14) or (16).

10. Research outcome

Proof obligation
 |
Result
 |

Normalized four-form model constant $c$
 |
Established
 |

Mixed one-prime/three-model moment, including balance
 |
Established
 |

Uniform-convexity implication
 |
Established
 |

Ordinary and cross diagonals
 |
Completely removed
 |

Primitive-ratio multiplicity
 |
Exact accounting
 |

Mixed column covariances below balance
 |
Established
 |

Sharp actual four-prime upper bound
 |
Unproved
 |

Two explicit full fourth-moment upper bounds
 |
Established
 |

Giant-prime sector of the Vaughan remainder
 |
Lower bound $-0.245B_0+o(X)$
 |

Alternative fixed-residue removal beyond balance
 |
Established in (16)
 |

Actual positive signed population
 |
Established in the distinct retuning (17)
 |

The two remaining proof obligations that would advance the full target are now particularly concrete:

$$
\|A\|_\square^4\le c+O_A(L^{-A}),
$$

or, for the original signed representation after paying its giant-prime sector,

$$
R_{\rm rest}\ge-0.75B_0
$$

on an unbounded sequence.

The primitive-ratio and divisor-switching calculations show exactly why merely eliminating multiplicative-energy diagonals does not prove the first estimate. The surviving off-diagonal quantity is the variance of genuine two-prime counts along growing affine slopes.

The one-sided route has nevertheless made a substantive arithmetic advance: a complete giant-prime sector has been evaluated and bounded within a fixed fraction of the available main term. The complementary signed budget is not yet controlled.

I selected the sieve levels, factorability splits and alternative Vaughan cutoffs independently. The numerical budgets and local identities were checked algebraically. The primary theorem statements were inspected; some PDF screenshot requests failed, particularly for the older sieve paper. The new applications have not received separate external or subagent validation. No project files, notebooks, downloads, installations or external messages were used.

No unconditional positive lower bound for ordinary twin primes has yet been established by this investigation.

---

## Proof readiness confirmation

[Original conversation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6b0518bf-1c20-83e8-828d-6ce455694164)

### Recovered response 1

1. The endpoint derivative and its Euler product

For $m>1$, define

$$
P_m(w)=\prod_{r\mid m,\ r\ {\rm prime}}(1-r^{-w}),
\qquad w\ge0.
$$

The exact derivative is

$$
\boxed{P_m'(0)=\Lambda(m).}
$$

Indeed, if $m=r^a$, there is one factor and its derivative at zero is $\log r$. If $m$ has two or more distinct prime factors, the product has a zero of order at least two.

Put

$$
L=\log X,\qquad J_X=\int_X^{2X}\frac{dt}{\log t},
$$

and average over genuine primes:

$$
A_X(w)=\frac1{J_X}
\sum_{X<p\le2X}P_{p+2}(w).
$$

Writing $T_X$ for the number of genuine twins in this dyad, we have

$$
A_X'(0)
=\frac{L}{J_X}T_X
+O\left(\frac{T_X+\sqrt X L}{J_X}\right).
\tag{1}
$$

The $O(\sqrt X L)$ term accounts for all proper prime powers. Thus

$$
\limsup_{X\to\infty}A_X'(0)>0
$$

would establish twin-prime infinitude.

The fixed-parameter mean

Expanding the product gives

$$
P_m(w)=\sum_{d\mid m}\mu(d)d^{-w}.
$$

For every fixed $w>0$, prime distribution in progressions and truncation of this absolutely summable mean yield

$$
\boxed{
A_X(w)\longrightarrow
E(w):=
\prod_{r>2}
\left(1-\frac{r^{-w}}{r-1}\right).
}
\tag{2}
$$

The exclusion of the prime two is necessary because $p+2$ is odd for all sufficiently large $p$.

Factoring the Euler product,

$$
E(w)=\frac{H(w)}{\zeta(1+w)},
$$

where

$$
H(w)=
\frac1{1-2^{-1-w}}
\prod_{r>2}
\frac{1-r^{-w}/(r-1)}{1-r^{-1-w}}.
$$

The second product converges near zero, and

$$
H(0)=2C_2,\qquad
C_2=\prod_{r>2}
\left(1-\frac1{(r-1)^2}\right).
$$

Therefore

$$
\boxed{E(w)=2C_2w+O(w^2).}
\tag{3}
$$

This gives a strictly positive derivative of the limiting Euler product. But exchanging that derivative with the limit in (2) is precisely the unproved step.

2. Curvature: why a direct concavity argument fails

Write $a_r=\log r$. For $w>0$,

$$
\frac{P_m''(w)}{P_m(w)}
=
\left(\sum_{r\mid m}
\frac{a_r}{e^{a_rw}-1}\right)^2
-
\sum_{r\mid m}
\frac{a_r^2e^{a_rw}}{(e^{a_rw}-1)^2}.
$$

At the endpoint, this gives the exact identity

$$
P_m''(0)=
\begin{cases}
-(\log r)^2,&m=r^a,\\
2\log r\log s,&m=r^as^b,\ r\ne s,\\
0,&\omega(m)\ge3.
\end{cases}
\tag{4}
$$

Thus the semiprime-type contributions have the opposite curvature from the prime-power contributions.

In particular, $P_m$ is not a Bernstein function when $m$ has at least two distinct prime factors: it is convex sufficiently close to zero, whereas a Bernstein function must be concave.

The product is log-concave on $w>0$, since

$$
(\log P_m)''(w)
=
-\sum_{r\mid m}
\frac{a_r^2e^{a_rw}}{(e^{a_rw}-1)^2}<0.
$$

But log-concavity cannot detect the desired endpoint. A function with a double or higher-order zero, such as $w^2$, can also be log-concave.

Neither of these curvature properties yields a positive lower bound for $P_m'(0)$ on composites.

3. A genuine two-radius minorant

There is a useful pointwise construction that does give the desired sign on every composite, except that prime powers must be treated as usual.

Put

$$
L_*=\log(2X+2),\qquad w=\frac c{L_*},
\qquad
R(c)=(1+e^{-c/2})^2.
$$

Define

$$
M_c(m)=R(c)P_m(w)-P_m(2w).
$$

For every $m\le2X+2$ having at least two distinct prime factors,

$$
\boxed{M_c(m)\le0.}
\tag{5}
$$

To prove this, note the exact identity

$$
\frac{P_m(2w)}{P_m(w)}
=\prod_{r\mid m}(1+r^{-w}).
$$

Choose any two distinct prime factors $r,s$, and put $x=\log r/L_*$, $y=\log s/L_*$. Then $x+y\le1$.

The function

$$
t\longmapsto\log(1+e^{-ct})
$$

is convex and decreasing. Hence

$$
(1+e^{-cx})(1+e^{-cy})
\ge(1+e^{-c/2})^2.
$$

Every additional factor in the product is at least one. This proves (5).

On a genuine prime $m\asymp X$,

$$
M_c(m)\longrightarrow
2e^{-c/2}(1-e^{-c})>0
$$

for every fixed $c>0$.

Moreover, for every integer $m>1$,

$$
\boxed{
\frac{M_c(m)}{R(c)w}\le\Lambda(m).
}
\tag{6}
$$

This follows from (5) when $m$ has multiple distinct factors, and from $P_{r^a}(w)\le w\log r$ on prime powers.

Consequently, this is a valid minorant assembled from just two positive parameter values. It retains ordinary primality rather than merely detecting bounded factor count.

What mean estimate would make it work?

Introduce the scaled analytic family

$$
B_X(c)=L_*A_X(c/L_*).
$$

The minorant gives the unconditional inequality

$$
\boxed{
A_X'(0)\ge
\frac{R(c)B_X(c)-B_X(2c)}{R(c)c}.
}
\tag{7}
$$

If the fixed-parameter Euler approximation could be extended sufficiently accurately to these moving parameters, it would predict

$$
B_X(c)\sim 2C_2c.
$$

The right side of (7) would then be positive whenever

$$
R(c)>2,
$$

equivalently

$$
0<c<2\log(1+\sqrt2).
$$

In particular, $c=1$ would suffice.

The pointwise minorant succeeds. The outstanding task is its arithmetic mean. The fixed-$w$ limit (2) does not justify substituting $w=c/L_*$.

4. A uniform endpoint estimate on actual shifted primes

I obtained a stronger, unconditional control of the passage to the derivative.

Proposition. There is an absolute constant $C$ such that, uniformly for all sufficiently large $X$ and $0<c\le1$,

$$
\boxed{
\left|
\frac{B_X(c)}c-A_X'(0)
\right|\le Cc.
}
\tag{8}
$$

This estimates the complete composite contamination, including every factor-count rank.

Proof

Define the nonnegative multiplicative weight

$$
g_X(m)=
\prod_{r\mid m}
\min\left(1,\frac{\log r}{L_*}\right).
$$

I first claim

$$
\boxed{
\sum_{X<p\le2X}g_X(p+2)
\ll\frac{X}{L^2}.
}
\tag{9}
$$

Use the Nair–Tenenbaum multivariable upper-bound theorem on the two linear polynomials $n,n+2$, with multiplicative weights

$$
f_X(n)=\mathbf1_{\{P^-(n)>X^{1/10}\}},
\qquad g_X(n+2).
$$

The original theorem's statement is reproduced as Theorem 1 in Henriot's Nair–Tenenbaum bounds uniform with respect to the discriminant. Its hypotheses permit these $X$-dependent functions because both have uniformly bounded coprime growth. The polynomials have fixed discriminant four and no fixed prime divisor.

arxiv.org

The sieve product is $O(L^{-2})$. The two remaining harmonic Euler products are bounded because

$$
\sum_{X^{1/10}<r\le X}\frac1{r-1}\ll1,
$$

and

$$
\sum_{r\le X}\frac{\log r}{L_*(r-1)}\ll1.
$$

Every genuine prime $p\in(X,2X]$ satisfies $f_X(p)=1$. This proves (9).

Now put $x_r=\log r/L_*$ for $r\mid m$.

If $\omega(m)\ge2$, then

$$
0\le\frac{P_m(c/L_*)}{c}
\le c^{\omega(m)-1}\prod_{r\mid m}x_r
\le c\,g_X(m).
$$

The endpoint derivative is zero on these integers.

If $m=r^a$, then

$$
0\le x_r-\frac{1-e^{-cx_r}}c
\le\frac c2x_r^2
\le\frac c2g_X(m).
$$

Thus, on every integer under consideration,

$$
\left|
\frac{P_m(c/L_*)}{c}
-\frac{\Lambda(m)}{L_*}
\right|
\le c\,g_X(m).
$$

Sum over genuine primes $p$, multiply by $L_*/J_X$, and apply (9). Since $L_*/J_X\asymp L^2/X$, this proves (8). ∎

The consequence is particularly clean. A lower bound

$$
\boxed{
B_X(c_X)\ge\varepsilon c_X,
\qquad c_X\to0^+,
}
\tag{10}
$$

on an unbounded sequence of scales, for any fixed $\varepsilon>0$, would prove infinitely many twins.

The analytic endpoint error is now completely priced. The missing estimate is the linear-sized lower bound in (10).

5. How far toward zero can the Euler product actually be proved?

A useful repair of the fixed-parameter approximation is to apply a randomized sieve to the positive product, rather than truncate its Möbius expansion by absolute values.

This gives a genuine moving-parameter theorem, although it stops short of the endpoint range required by (7).

Proposition. There are absolute constants $b>0$ and $c_0>0$ such that, uniformly for $c_0\le c\le L_*$,

$$
\boxed{
A_X(c/L_*)
=
E(c/L_*)
\left(1+O(e^{-b\sqrt{c\log c}})\right)
+O_A(L^{-A})
}
\tag{11}
$$

for every fixed $A>0$.

Proof

Write $w=c/L_*$. Set the available sieve level to $D=X^{1/3}$, and truncate the product at $z=D^{1/s}$:

$$
P_m^{\le z}(w)=
\prod_{\substack{r\mid m\\r\le z}}
(1-r^{-w}).
$$

Choose standard upper and lower fundamental-lemma sieve coefficients $\lambda_d^\pm$, supported on squarefree $d\le D$ with prime factors at most $z$.

For each prime divisor $r\le z$ of $m$, independently select it with probability $r^{-w}$. The probability that no factor is selected is exactly $P_m^{\le z}(w)$.

Applying the pointwise sieve inequalities to the product of the selected primes, then taking expectations, gives

$$
\sum_{d\mid m}\lambda_d^-d^{-w}
\le P_m^{\le z}(w)
\le\sum_{d\mid m}\lambda_d^+d^{-w}.
$$

Thus randomization preserves both sieve directions exactly.

Bombieri–Vinogradov applies to the actual prime progressions $p\equiv-2\pmod d$, since $d\le X^{1/3}$ and the coefficients have absolute value at most one.

The fundamental lemma applies with local density

$$
g_w(r)=\frac{r^{-w}}{r-1}
\quad(r>2),\qquad g_w(2)=0.
$$

These densities are bounded above by the usual dimension-one densities $1/(r-1)$, so the required product-growth bounds are uniform in $w$. I checked the coefficient support and error form in Ford's Theorem 3.6, which includes its proof.

ford126.web.illinois.edu

Consequently,

$$
\frac1{J_X}\sum_{X<p\le2X}P_{p+2}^{\le z}(w)
=
E_z(w)(1+O(e^{-a s\log s}))
+O_A(L^{-A}),
$$

where $a>0$ is absolute, $s$ is sufficiently large, and

$$
E_z(w)=\prod_{2<r\le z}
\left(1-\frac{r^{-w}}{r-1}\right).
$$

The discarded large prime factors are controlled pointwise:

$$
0\le P_m^{\le z}(w)-P_m(w)
\le P_m^{\le z}(w)
\frac{L_*}{\log z}e^{-w\log z}.
$$

The omitted Euler-product tail is also controlled:

$$
\log\frac{E_z(w)}{E(w)}
\ll
\sum_{r>z}\frac{r^{-w}}r
\ll\frac{e^{-w\log z}}{w\log z}.
$$

The last estimate follows from the elementary prime-counting upper bound and partial summation, uniformly for $0<w\le1$.

Finally, choose

$$
s\asymp\sqrt{\frac c{\log c}}.
$$

Both $s\log s$ and $w\log z\asymp c/s$ are then of order $\sqrt{c\log c}$. All the discarded factors and sieve errors are absorbed into (11). ∎

The resulting parameter separation

In particular, whenever

$$
c_X\to\infty,\qquad c_X=o(\log X),
$$

we obtain the unconditional asymptotic

$$
\frac{A_X(c_X/L_*)}{c_X/L_*}\longrightarrow 2C_2.
$$

Thus the Euler-product slope can be recovered at parameters tending to zero, provided they satisfy $w\log X\to\infty$.

However, the uniform derivative estimate (8) requires the opposite regime, $w\log X\to0$, to make its error vanish.

This is now a precise quantitative separation between the two proved estimates, rather than merely a warning about interchanging limits.

The two-radius minorant needs a bounded parameter $c$ below $2\log(1+\sqrt2)$. The available sieve approximation (11) becomes accurate for large $c$, where $R(c)$ tends to one and its predicted minorant mean is negative.

6. Can a weaker unconditional lower bound reach the endpoint?

I tested a direct roughness lower bound, avoiding any assumption of the Euler-product asymptotic in the transition region.

Choose a sufficiently small fixed $\delta>0$, and consider the actual primes $p\in(X,2X]$ satisfying

$$
P^-(p+2)>X^\delta.
$$

Bombieri–Vinogradov and the lower fundamental lemma give

$$
\#\{X<p\le2X:P^-(p+2)>X^\delta\}
\gg_\delta \frac{X}{L^2}.
$$

Here one can take the distribution level $D=X^{1/3}$ and choose $\delta$ sufficiently small that the fundamental-lemma relative error is less than one-half.

On this population, every prime factor of $p+2$ has normalized logarithm at least $\delta/2$ for sufficiently large $X$. The number of distinct prime factors is at most the fixed integer

$$
K=\left\lceil\frac2\delta\right\rceil.
$$

Consequently,

$$
P_{p+2}(c/L_*)
\ge(1-e^{-c\delta/2})^K.
$$

Summing yields the unconditional lower bound

$$
\boxed{B_X(c)\gg_\delta c^K,\qquad 0<c\le1.}
\tag{12}
$$

This proves positivity of the actual generating mean even at arbitrarily small positive parameters.

However, after division by $c$, the lower bound is of order $c^{K-1}$. It cannot dominate the $O(c)$ endpoint error in (8).

The distinction is decisive: positive generating-function mass is established, but a sufficiently large linear term is not.

7. An obstruction covering arbitrarily many positive parameter values

I next tested whether a more elaborate linear combination could escape the problem encountered by the two-radius minorant.

There is an exact integral comparison that identifies the limitation.

The ordinary angular calculation

Represent the logarithmic proportions of the distinct prime factors by

$$
x_1+\cdots+x_k=1,\qquad x_i>0.
$$

Define

$$
I_k(c)=\frac1{k!}
\int_{\substack{x_i>0\\\sum x_i=1}}
\prod_{i=1}^k
\frac{1-e^{-cx_i}}{x_i}\,
dx_1\cdots dx_{k-1}.
$$

These are nonnegative integrals. The prime contribution is $I_1(c)=1-e^{-c}$.

All ranks can be summed exactly.

Set

$$
g_c(t)=\frac{1-e^{-ct}}t.
$$

Its Laplace transform is

$$
\int_0^\infty e^{-st}g_c(t)\,dt
=\log\frac{s+c}{s}.
$$

The convolution expansion therefore gives

$$
\mathcal L\left(
\sum_{k\ge1}\frac{g_c^{*k}}{k!}
\right)(s)
=
\exp\left(\log\frac{s+c}{s}\right)-1
=\frac cs.
$$

Evaluating the inverted density at total logarithmic proportion one proves

$$
\boxed{\sum_{k\ge1}I_k(c)=c.}
\tag{13}
$$

The same calculation with an alternating sign gives

$$
\mathcal L\left(
\sum_{k\ge1}\frac{(-1)^kg_c^{*k}}{k!}
\right)(s)
=
-\frac c{s+c}.
$$

Hence

$$
\boxed{
2\sum_{\substack{k\ge2\\k\ {\rm even}}}I_k(c)
=c(1-e^{-c}).
}
\tag{14}
$$

All interchanges are justified by the elementary bound $g_c(t)\le c$, which gives absolute convergence of the convolution series on compact intervals.

A positive comparison with no primes

Equations (13) and (14) produce two analytic functions:

$$
B_{\rm ord}(c)=2C_2c,
$$

and

$$
B_{\rm even}(c)=2C_2c(1-e^{-c}).
$$

The second is realized by a nonnegative angular measure supported entirely on composite factor configurations of even rank.

It satisfies

$$
B_{\rm even}'(0)=0,
$$

while

$$
B_{\rm even}(c)
=
2C_2c+O(ce^{-c})
$$

as $c\to\infty$.

Thus it reproduces the large-$c$ Euler-product slope with an error exponentially smaller than the error currently established in (11).

This is an information comparison, not a claim that actual shifted primes have this distribution.

It demonstrates why positivity, analytic regularity and the available large-parameter estimate cannot by themselves force a positive endpoint derivative.

Consequence for several-radius minorants

Consider an arbitrary finite combination

$$
M(x_1,\ldots,x_k)
=
\sum_{j=1}^N b_j
\prod_{i=1}^k(1-e^{-c_jx_i}),
\qquad c_j>0.
$$

Suppose it is nonpositive on every composite configuration $k\ge2$.

Integrating against the positive even-rank comparison and using (14) gives the necessary inequality

$$
\sum_j b_jc_j(1-e^{-c_j})\le0.
$$

Equivalently,

$$
\boxed{
\sum_j b_jc_j
\le
\sum_j b_jc_je^{-c_j}
\le
\sum_j|b_j|c_je^{-c_j}.
}
\tag{15}
$$

This applies in particular to limiting pointwise minorants valid on all composite integers in a dyad. Every fixed positive angular tuple can be approximated by distinct genuine prime factors whose product lies in that dyad, using the prime number theorem.

The consequence is quantitative. When all the parameters $c_j$ are large, the predicted positive Euler-product mean of any such finite minorant is at most exponentially small relative to its weighted coefficient norm.

The certified approximation errors in (11) are larger than that allowance. Therefore those estimates alone cannot establish positivity of the minorant by increasing the number of large-radius evaluations.

A successful several-radius minorant still needs new information in the bounded-$c$ transition region, or substantially sharper signed control of its combined arithmetic error.

8. A second positive-kernel repair: raising the product to a high power

One can alternatively eliminate composites using a completely nonnegative kernel.

Fix $w_0>0$, independently of $X$. Every composite $m\le2X+2$, including a proper prime power, has a prime divisor at most $\sqrt{2X+2}$. Consequently,

$$
P_m(w_0)\le1-(2X+2)^{-w_0/2}.
$$

For a genuine prime $m>X$,

$$
P_m(w_0)\ge1-X^{-w_0}.
$$

Choose

$$
k_X=
\left\lceil
A(2X+2)^{w_0/2}\log\log X
\right\rceil,
\qquad A>1.
$$

Then every composite satisfies

$$
P_m(w_0)^{k_X}\le(\log X)^{-A},
$$

whereas uniformly on genuine primes,

$$
P_m(w_0)^{k_X}=1-o(1).
$$

It follows unconditionally that

$$
\boxed{
\sum_{X<p\le2X}P_{p+2}(w_0)^{k_X}
=
T_X+o(X/\log^2X).
}
\tag{16}
$$

Here the classical twin upper bound, or the weighted upper estimate (9), prices the small multiplicative error on the prime contribution.

This is a particularly clean positive detector: it eliminates all composite ranks and proper prime powers without any signed subtraction.

But its arithmetic mean has a new scale problem.

The kernel can be interpreted as a randomized sieve with local exclusion probabilities

$$
b_X(r)=1-(1-r^{-w_0})^{k_X}.
$$

For every fixed $\varepsilon>0$, these probabilities tend uniformly to one on primes

$$
r\le X^{1/2-\varepsilon}.
$$

Indeed, $k_Xr^{-w_0}\to\infty$ uniformly in that range.

Thus the high-power detector behaves like a sieve extending almost to the square-root primality boundary.

The ordinary lower linear sieve on shifted primes, at Bombieri–Vinogradov level, has no positive lower coefficient at this sifting depth. The kernel has repaired composite contamination, but not the missing lower-bound estimate.

Proving a sufficiently large mean of (16) would establish twins; the available fixed-power mean theorems do not evaluate this growing-power kernel.

Final research verdict

The strongest independently supported conclusions are the uniform endpoint control

$$
\left|
\frac{L_*A_X(c/L_*)}{c}-A_X'(0)
\right|\ll c,
$$

and the moving-parameter Euler-product approximation (11).

Together, they identify exactly where the proof stops: the transition between $w\log X\to\infty$, where the Euler-product mean is accessible, and $w\log X\to0$, where its value reliably determines the prime-sensitive derivative.

The explicit two-radius minorant gives a concrete remaining inequality. At $c=1$, it is enough to prove, on arbitrarily large scales,

$$
\boxed{
\sum_{X<p\le2X}
\left[
(1+e^{-1/2})^2P_{p+2}(1/L_*)
-
P_{p+2}(2/L_*)
\right]
\gg\frac{X}{\log^B X}
}
$$

for any fixed $B>0$, with a positive implied constant.

Every integer with multiple distinct prime factors contributes nonpositively. Proper prime powers contribute only $O(\sqrt X)$, which cannot account for the displayed lower bound.

This criterion therefore requires much less than a complete twin-prime asymptotic. It would force a genuine twin on arbitrarily large dyadic intervals.

I have not established this final inequality. The minorant itself is proved, but its required positive mean remains unresolved. The even-rank angular comparison establishes why the currently available positive-parameter information cannot supply that mean through a purely analytic or Tauberian argument.

---

### Recovered response 2

1. The mechanism that must be transferred

I inspected Sawin–Shusterman's arXiv:1808.04001v2, especially Section 3 and the proof of Theorem 6.3. The result was subsequently published in the Annals of Mathematics.

Their method has two distinct algebraic ingredients.

For a monic polynomial $f$ over a finite field of odd characteristic, Pellet's formula states

$$
\mu(f)=(-1)^{\deg f}\chi(\operatorname{Disc}f),
$$

where $\chi$ is the quadratic character, extended by zero.

The underlying reason is that Frobenius permutes the roots of $f$, with one cycle for each irreducible factor. Its sign detects the parity of the factor count.

The second ingredient is the identity

$$
(r+s^\ell)'=r'
$$

in characteristic $\ell$. Thus a large family of varying polynomials has a fixed derivative. The resultant defining the discriminant can then be interpreted, through quadratic reciprocity, as a character with a conductor independent of the varying parameter.

More generally, Lemma 3.2 uses

$$
D=M^2\left(g+\frac aM\right)'
$$

on the progression $a+Mg$. Fixing $g'$ fixes $D$, allowing character-sum cancellation within the corresponding family.

arxiv.org+1

This gives a precise transfer requirement: we need an integer analogue that both detects the parity of the integer's own prime factors and permits cancellation with a suitably controlled conductor.

An auxiliary polynomial whose discriminant has a quadratic character is not enough unless that character actually detects integer factorization.

There is, however, an exact integer analogue of the parity identity worth testing.

2. An exact integer discriminant certificate

A promising substitute is the cyclotomic polynomial $\Phi_n(T)$, rather than a digit encoding of $n$.

For every odd integer $n>1$, put

$$
D_n=\operatorname{Disc}\Phi_n.
$$

I obtain the following exact squareclass identity:

$$
\boxed{
D_n\equiv
\begin{cases}
(-1)^{(r-1)/2}r,&n=r^a,\ r\text{ prime},\\
1,&\omega(n)\ge2
\end{cases}
\quad\bmod(\mathbb Q^\times)^2.
}
\tag{1}
$$

In particular, for odd squarefree $n>1$,

$$
\boxed{
n\text{ is prime}\quad\Longleftrightarrow\quad
D_n\text{ is not a rational square}.
}
\tag{2}
$$

Unlike irreducibility of an auxiliary polynomial, this certificate detects primality of the ordinary integer itself.

Proof

The cyclotomic discriminant formula is

$$
D_n=
(-1)^{\varphi(n)/2}
\frac{n^{\varphi(n)}}
{\displaystyle\prod_{r\mid n,\ r\ {\rm prime}}
r^{\varphi(n)/(r-1)}}.
\tag{3}
$$

It can be derived directly by differentiating

$$
\Phi_n(T)=\prod_{d\mid n}(T^d-1)^{\mu(n/d)}
$$

at the primitive $n$-th roots of unity and multiplying the resulting derivatives. The required norm factors are $\Phi_{n/d}(1)^{\varphi(n)/\varphi(n/d)}$; here $\Phi_k(1)$ equals the prime base when $k$ is a prime power, and one otherwise.

If $n$ has at least two distinct odd prime factors, then $\varphi(n)$ is divisible by four. Moreover, every $\varphi(n)/(r-1)$ is even, because another odd prime contributes an even factor.

Thus (3) is a positive square.

If $n=r^a$, the exponent of $r$ in (3) is

$$
r^{a-1}\bigl(a(r-1)-1\bigr),
$$

which is odd. Its sign is $(-1)^{(r-1)/2}$. This proves (1).

The Frobenius interpretation also survives

For a prime $s\nmid n$, Frobenius acts on the primitive $n$-th roots by

$$
\zeta\longmapsto\zeta^s.
$$

All its cycles have length $\operatorname{ord}_n(s)$. Its sign is therefore

$$
(-1)^{\varphi(n)/\operatorname{ord}_n(s)}
=\left(\frac{D_n}{s}\right)
$$

for odd $s$.

When $n$ has multiple distinct prime factors, the two-adic valuation of the group order exceeds that of every element order. Hence every such permutation is even.

For prime-power $n$, this sign can be negative.

This is an exact arithmetic counterpart of the permutation-sign mechanism underlying Pellet's formula.

Where the conductor argument fails

The raw discriminant is enormous:

$$
\log|D_n|
=\varphi(n)\left(
\log n-\sum_{r\mid n}\frac{\log r}{r-1}
\right)
\ge\frac12\varphi(n)\log n.
$$

The degree $\varphi(n)$ itself is $\gg n/\log\log n$.

After removing square factors, the quadratic character has conductor one when $n$ has multiple distinct factors, and conductor $r$ when $n=r^a$.

Thus the squareclass reduction gives an exact certificate, but not a fixed conductor shared by a large arithmetic family. It is precisely the unknown prime-power property that determines whether the character is principal.

For example, for genuine primes $p\equiv1\pmod4$, the identity gives

$$
\frac{1-\operatorname{sgn}D_{p+2}}2
=
\mathbf1_{\{p+2\text{ is a prime power}\}}.
$$

Consequently,

$$
\sum_{\substack{X<p\le2X\\p\equiv1\ (4)}}
(1-\operatorname{sgn}D_{p+2})
=
2T_{1\to3}(X)+O(\sqrt X),
$$

where $T_{1\to3}(X)$ counts twins with lower prime congruent to one modulo four.

A lower bound exceeding the proper-prime-power allowance would prove twins. I have not found an unconditional distribution theorem for these varying cyclotomic discriminants that supplies it.

The algebraic detector works exactly; the required analytic averaging does not follow from it.

3. Why a p-adic analogue cannot directly freeze the derivative

The essential polynomial-space operation in Sawin–Shusterman is not just a derivative that vanishes. It is an additive operation with vanishing derivative, producing large translated families.

In positive characteristic, the Frobenius map supplies both properties. Over integer residue rings, they impose substantially different restrictions.

Proposition: the mixed-characteristic obstruction

Let $\ell$ be a prime, $k\ge2$, and

$$
R=\mathbb Z/\ell^k\mathbb Z.
$$

Suppose a polynomial $F(T)\in R[T]$ satisfies the formal identities

$$
F(U+V)=F(U)+F(V),\qquad F'(T)=0.
$$

Then necessarily

$$
\boxed{
F(T)=\ell^{k-1}\sum_{j\ge1}b_jT^{\ell^j}.
}
\tag{4}
$$

In particular, on scalar residue classes,

$$
|\operatorname{im}F|\le\ell.
$$

Proof. Write $F(T)=\sum a_dT^d$. Formal additivity requires

$$
a_d\binom di=0\pmod{\ell^k}
$$

for every $1\le i<d$.

If $d\ge2$ is not a power of $\ell$, some interior binomial coefficient is nonzero modulo $\ell$. Indeed, write $d=\ell^bu$, with $\ell\nmid u$ and $u>1$. The coefficient of $T^{\ell^b}$ in

$$
(1+T)^d\equiv(1+T^{\ell^b})^u\pmod\ell
$$

is $u$, a unit.

Therefore $a_d=0$.

If $d=\ell^j$, all interior binomial coefficients are divisible by $\ell$, but

$$
v_\ell\binom{\ell^j}{\ell^{j-1}}=1.
$$

Thus $a_d$ must be divisible by $\ell^{k-1}$. Finally, $F'=0$ eliminates the linear coefficient. This proves (4). ∎

Consequently, increasing the p-adic precision does not produce an increasingly large scalar translated family of the required kind. The nonlinear additive variations with zero derivative remain confined to the last residue digit.

There is a related obstruction modulo a composite squarefree integer $n$: a monomial $T^d$, with $d>1$, cannot be formally additive modulo every prime dividing $n$. Its exponent would have to be a power of each distinct prime simultaneously.

One can construct separate Frobenius maps using the CRT decomposition of $\mathbb Z/n\mathbb Z$, but that construction requires precisely the prime-factor decomposition one is trying to detect.

This rules out the literal formal Frobenius transfer. It does not rule out all methods involving p-adic analysis.

4. Quantitative obstruction to a frozen-conductor parity identity

I tested whether one could bypass formal additivity and directly represent integer Möbius parity by a residue-dependent character on large fibers.

The following result rules out a substantial version of that proposal.

Fix

$$
0<\alpha<a<b<\frac12,
\qquad
0<\theta<\frac{1-b}{2}.
$$

Let $Q\le X^\theta$.

Proposition. Apart from $O_A(Q/\log^A X)$ moduli $q\in[Q,2Q]$, every reduced residue class modulo $q$ contains both

$$
\gg\frac{X}{\varphi(q)\log X}
$$

primes in $(X,2X]$, and

$$
\gg_{\alpha,a,b}\frac{X}{\varphi(q)\log X}
$$

squarefree semiprimes in $(X,2X]$ whose prime factors both exceed $X^\alpha$.

This follows unconditionally from Bombieri–Vinogradov.

Proof of the semiprime assertion

Consider

$$
n=rs,\qquad X^a<r\le X^b,
\qquad X/r<s\le2X/r,
$$

with $r,s$ prime.

Since $b<1/2$, the smaller factor is uniquely $r$, and every such product is squarefree and $X^\alpha$-rough.

For $(h,q)=1$, the progression $rs\equiv h\pmod q$ becomes

$$
s\equiv hr^{-1}\pmod q,
$$

with $(r,q)=1$.

The scale of the second prime is at least $X^{1-b}$. The strict inequality on $\theta$ therefore permits Bombieri–Vinogradov at this scale, with arbitrary logarithmic precision.

Summing the progression errors first over moduli and then over $r$ costs only

$$
\sum_{X^a<r\le X^b}\frac1r\ll_{a,b}1.
$$

The total error is consequently $O_A(X/\log^A X)$.

The principal term in a reduced class is

$$
\frac1{\varphi(q)}
\sum_{\substack{X^a<r\le X^b\\(r,q)=1}}
\int_{X/r}^{2X/r}\frac{dt}{\log t}
\asymp_{a,b}\frac{X}{\varphi(q)\log X}.
$$

The removal of $r\mid q$ changes this main term negligibly, since every such $r$ exceeds $X^a$.

Markov's inequality now gives the exceptional-modulus estimate. The corresponding assertion for primes follows directly from Bombieri–Vinogradov at scale $X$. The relevant classical distribution statement is also recorded explicitly in Pascadi's published Smooth numbers in arithmetic progressions to large moduli.

doi.org

Consequence for character encodings

Let $G_q$ be any complex-valued $q$-periodic function.

Primes have Möbius value $-1$, and the squarefree semiprimes just constructed have Möbius value $+1$. On every good reduced residue class, the triangle inequality

$$
|G_q(h)-1|+|G_q(h)+1|\ge2
$$

therefore forces a substantial approximation error.

Summing over classes gives

$$
\boxed{
\sum_{\substack{X<n\le2X\\
P^-(n)>X^\alpha\\
n\ {\rm squarefree}\\
\omega(n)\le2}}
|\mu(n)-G_q(n)|
\gg_{\alpha,a,b}\frac{X}{\log X}
}
\tag{5}
$$

for all the good moduli.

For fixed moduli, the analogous statement follows from the prime number theorem in progressions.

Thus a frozen periodic character cannot reproduce integer Möbius parity even on the thin, polynomially rough population consisting exclusively of primes and semiprimes.

This is a genuine distinction from the polynomial derivative fibers. Its scope is periodic approximation on ordinary integers; it does not establish the corresponding lower bound after requiring $n-2$ to be prime.

That additional requirement is exactly where the twin-prime arithmetic enters.

5. A more promising substitute: an exact integer Pellet-type character sum

There is another identity which detects factor parity exactly, without using an integer polynomial's irreducibility.

For odd $n$, write

$$
J(n)=\sum_{t\bmod n}
\left(\frac{t(t+1)}n\right),
$$

where the symbol is the Jacobi symbol.

For odd squarefree $n$,

$$
\boxed{J(n)=\mu(n).}
\tag{6}
$$

Proof

For an odd prime $r$,

$$
\sum_{t\bmod r}
\left(\frac{t(t+1)}r\right)=-1.
$$

This follows by counting solutions of

$$
u^2=t(t+1).
$$

After completing the square,

$$
(2t+1-2u)(2t+1+2u)=1.
$$

There are exactly $r-1$ solutions, whereas the original quadratic-character expression counts $r$ plus the character sum.

The CRT now factors the complete sum into the product of these local sums:

$$
J(n)=\prod_{r\mid n}(-1)=\mu(n)
$$

when $n$ is squarefree.

For arbitrary odd $n$, the exact extension is

$$
J(n)=
\prod_{r^e\parallel n}
r^{e-1}
\begin{cases}
-1,&e\text{ odd},\\
r-2,&e\text{ even}.
\end{cases}
$$

Consequently,

$$
\boxed{\mu(n)=\mu^2(n)J(n)}
\tag{7}
$$

holds on every odd integer.

This identity has the desired connection to a resultant: $4t(t+1)$ is the discriminant of

$$
F_t(U)=U^2-t(t+1),
$$

whose derivative $2U$ is independent of $t$.

Thus we have found a family with a fixed derivative whose complete quadratic-character sum records the parity of the ordinary integer's factors.

The exact fixed-gap-two correlation

Because $n$ and $n+2$ are coprime when $n$ is odd,

$$
\boxed{
\mu(n)\mu(n+2)
=
\mu^2(n(n+2))
\sum_{t\bmod n(n+2)}
\left(\frac{t(t+1)}{n(n+2)}\right).
}
\tag{8}
$$

This is an exact parity-sensitive identity at the ordinary shift two.

Unlike Sawin–Shusterman's formula, however, it expresses parity through a complete auxiliary character sum, rather than the value of one fixed-conductor character.

For $n\asymp X$, the auxiliary modulus in (8) is of order $X^2$. Its complete sum has absolute value one on the squarefree support.

The normalization is therefore critical: an error merely small relative to the modulus is nowhere near enough to recover parity.

6. Can the complete character sum be shortened?

I tested two ways of recovering (6) without its full modulus-length sum.

A. Freeze the reciprocal characters using congruences

For a fixed $t\ge1$, quadratic reciprocity expresses

$$
n\longmapsto\left(\frac{t(t+1)}n\right)
$$

on odd $n$ as a real character with modulus dividing $4t(t+1)$.

Consider trying to freeze all these character values for $1\le t\le H$ by a common CRT modulus.

For every odd prime $r\le H+1$, choose $t=r-1$. Then

$$
t(t+1)=r(r-1),
$$

and its squarefree part contains $r$.

Thus any common period for these character functions must be divisible by every odd prime up to $H+1$.

Its size is consequently at least

$$
\boxed{
\exp((1+o(1))H).
}
\tag{9}
$$

To retain many integers in a single progression at height $X$, this direct construction permits only $H=O(\log X)$.

That is far shorter than the complete sum of length $n\asymp X$ in (6), let alone the length $n(n+2)\asymp X^2$ in (8).

B. A short weighted average, allowing signed coefficients

There is also a quantitative obstruction to treating a short auxiliary sample as an accurate substitute for the complete Jacobi sum.

Take a large odd prime $r$ and define

$$
f_r(t)=\left(\frac{t(t+1)}r\right).
$$

For distinct residues $a_1,\ldots,a_H$ and arbitrary complex coefficients $c_j$ satisfying $\sum c_j=1$, put

$$
Y(u)=r\sum_{j=1}^H c_jf_r(u+a_j).
$$

Average over uniformly distributed $u\bmod r$. The exact complete-sum identity gives

$$
\mathbb E_uY(u)=-1.
$$

Thus $Y$ is an unbiased estimator of the genuine Möbius value.

Nevertheless, uniformly for $H=o(\sqrt r)$,

$$
\boxed{
\mathbb E_u|Y(u)+1|^2
\ge
(1-o(1))\frac{r^2}{H}.
}
\tag{10}
$$

Proof. The centered diagonal covariance of $f_r$ is

$$
1-\frac2r-\frac1{r^2}.
$$

For a nonzero shift $h$, the uncentered covariance is

$$
\frac1r\sum_{t\bmod r}
\left(\frac{t(t+1)(t+h)(t+h+1)}r\right).
$$

The polynomial is not a square modulo $r$. At $h=\pm1$, the repeated root can be removed, costing only a bounded correction. Otherwise the polynomial has four distinct roots.

Weil's character-sum bound therefore gives $O(r^{-1/2})$ for every off-diagonal covariance. The primary source is Weil's On Some Exponential Sums.

pmc.ncbi.nlm.nih.gov

It follows that

$$
\mathbb E|Y+1|^2
\ge
r^2\left(1-O(H/\sqrt r)\right)
\sum_j|c_j|^2.
$$

Since $\sum c_j=1$, Cauchy–Schwarz gives $\sum|c_j|^2\ge1/H$, proving (10).

This establishes a substantial mean-square obstruction even on genuine prime moduli, where the required parity value is exactly $-1$.

The estimate does not rule out a specially chosen arithmetic auxiliary set or cancellation across varying moduli. It does rule out obtaining a uniformly accurate parity detector through short translated linear sampling, even when signed coefficients are allowed.

7. Carrying the mechanism through to an actual twin-prime criterion

The exact character representation can nevertheless be combined with an established positive lower sieve.

I checked Halberstam's 1975 primary paper A proof of Chen's theorem, including its actual weighted sieve on pages 282–283 and the estimates in Sections 2–4.

Let $z=X^{1/10}$, $y=X^{1/3}$. On squarefree integers $3\le n<X$, define

$$
W_X(n)=
\mathbf1_{\{P^-(n)\ge z\}}
\left(1-\frac12 A(n)-\frac12 B(n)\right),
$$

where

$$
A(n)=
\#\{r\mid n:r\text{ prime},\ z\le r<y\},
$$

and

$$
B(n)=
\#\{n=rst:r,s,t\text{ prime},\
z\le r<y\le s<t\}.
$$

Set $W_X(n)=0$ on nonsquarefree integers.

Halberstam's weighted calculation gives, with a safe rounding of his stated coefficient,

$$
\boxed{
\sum_{\substack{p\text{ prime}\\p+2<X}}
W_X(p+2)
\ge0.68C_2\frac{X}{\log^2X}
}
\tag{11}
$$

for sufficiently large $X$. The full squarefree restriction costs only $O(X^{9/10})$, since every excluded square has a prime base at least $X^{1/10}$. The weights are uniformly bounded on the rough support.

numdam.org

The essential pointwise property is that $W_X(n)\le0$ whenever $n$ has three or more distinct prime factors. For example, a triple with just one factor below $y$ receives both half-unit penalties. A higher rank must have at least two factors below $y$.

Now apply the parity projector

$$
\frac{1-J(n)}2
$$

on the squarefree support.

For primes it equals one. For semiprimes it equals zero. On higher odd ranks, its multiplier $W_X(n)$ is nonpositive.

Therefore

$$
\mathbf1_{\{n\text{ prime}\}}
\ge
\frac12W_X(n)(1-J(n)).
$$

Summing over actual shifted primes gives the unconditional inequality

$$
\boxed{
2T(X)\ge
0.68C_2\frac{X}{\log^2X}
-
\mathcal J(X),
}
\tag{12}
$$

where $T(X)$ counts ordinary twin pairs with upper endpoint below $X$, and

$$
\mathcal J(X)=
\sum_{\substack{p\text{ prime}\\p+2<X}}
W_X(p+2)
\sum_{t\bmod p+2}
\left(\frac{t(t+1)}{p+2}\right).
$$

Thus it would suffice to establish

$$
\boxed{
\liminf_{X\to\infty}
\frac{\log^2X}{X}\mathcal J(X)
<0.68C_2.
}
\tag{13}
$$

No unproved full prime-pair asymptotic enters this implication. Nor is a separate prime-power correction required, since the weight is already squarefree.

This is a precise one-sided character-sum estimate whose proof would give ordinary twins.

The remaining difficulty is that the available character bounds concern the auxiliary variable for individual moduli, while (13) requires cancellation across the actual shifted-prime moduli, with the complete signed Chen weight retained.

The square-root size of ordinary incomplete-character-sum bounds cannot supply the required constant-sized average of the complete parity sums.

Research conclusion

The investigation produces two exact integer analogues of the function-field mechanism:

-

The cyclotomic discriminant squareclass detects ordinary primality on squarefree integers.

-

The complete quadratic Jacobi sum detects ordinary Möbius parity, including an exact fixed-gap-two correlation identity.

The attempted analytic transfers encounter three independently checkable limitations: formal p-adic derivative freezing gives only small scalar families; fixed-conductor periodic encodings cannot distinguish rough primes from rough semiprimes; and short auxiliary character sampling has an explicit large mean-square error.

The strongest surviving proof obligation is (13). Its positive unsigned sieve contribution is already established, and its parity projection is exact. What remains unproved is the strict one-sided estimate for the complete character sums on the actual shifted-prime sequence.

No unconditional proof of infinitely many ordinary twin primes has resulted. The calculations identify precisely which part of the Sawin–Shusterman mechanism transfers to integers and which additional arithmetic estimate would still be necessary.

---

### Recovered response 3

1. Genus theory gives an exact twin-prime certificate

Write

$$
d_m=m^2-1=(m-1)(m+1),\qquad
D_m=4d_m,
$$

where $m>2$ is even.

Assume initially that $d_m$ is squarefree. Since $d_m\equiv3\pmod4$, $D_m$ is the fundamental discriminant of the real quadratic field

$$
K_m=\mathbb Q(\sqrt{d_m}).
$$

Let $C_m=\operatorname{Cl}^+(K_m)$ denote its narrow class group. Gauss genus theory gives

$$
\dim_{\mathbb F_2}(C_m/C_m^2)
=\omega(D_m)-1=\omega(d_m).
$$

Here $\omega$ counts distinct prime factors. I checked the narrow-class convention in Fouvry–Klüners, On the 4-rank of class groups of quadratic number fields.

math.uni-paderborn.de

The two factors $m-1,m+1$ are coprime odd integers greater than one. Consequently, the minimum possible narrow 2-rank is two, and

$$
\boxed{
\operatorname{rk}_2 C_m=2
\quad\Longleftrightarrow\quad
m-1,\ m+1\text{ are both prime}.
}
\tag{1}
$$

This is an exact certificate for ordinary gap two, not an almost-prime statement.

The squarefree condition must be retained: replacing a nonfundamental discriminant by its fundamental part can discard prime factors of even multiplicity and produce false positives.

2. What the prime geodesic theorem actually counts

The fundamental totally positive unit of $K_m$, on this squarefree family, is

$$
\epsilon_m=m+\sqrt{m^2-1}.
$$

Indeed, the Pell equation $x^2-d_my^2=1$ has the solution $(m,1)$, and every positive solution with $y\ge2$ gives a larger unit. A norm-minus-one unit is impossible, since $d_m\equiv3\pmod4$ has a prime divisor congruent to three modulo four.

The trace is therefore exactly $2m$, and the regulator is $\log\epsilon_m\asymp\log m$.

The conductor terms

Soundararajan–Young's The Prime Geodesic Theorem, Section 2, gives the exact class-number expression

$$
\Psi_\Gamma(x)
=
\sum_{3\le t\le\sqrt{x}+1/\sqrt{x}}
\ \sum_{\substack{\Delta u^2=t^2-4\\
\Delta\ {\rm discriminant}}}
h^+(\Delta)\log\epsilon_\Delta^2.
$$

Here $h^+(\Delta)$ is the narrow class number of the quadratic order of discriminant $\Delta$, and $\epsilon_\Delta$ is its fundamental totally positive unit.

The class-number formula is

$$
h^+(\Delta)\log\epsilon_\Delta
=\sqrt\Delta\,L(1,\chi_\Delta).
$$

Equivalently, the full trace weight is

$$
2\sqrt{t^2-4}\,\mathscr L(1,t^2-4),
$$

where $\mathscr L$ is the Zagier $L$-series.

arxiv.org

Writing $\delta=t^2-4=Df^2$, with $D$ fundamental, its exact conductor decomposition is

$$
\boxed{
\mathscr L(1,Df^2)
=
L(1,\chi_D)
\sum_{u\mid f}\frac1u
\prod_{\ell\mid f/u}
\left(1-\frac{\chi_D(\ell)}{\ell}\right).
}
\tag{2}
$$

Thus a trace with nonfundamental discriminant contributes through multiple quadratic orders. These terms cannot be identified with a single field class number.

For the squarefree family in (1), however, $f=1$, and there is only one contribution:

$$
\boxed{
G(m)=2h^+(D_m)\log\epsilon_m
=4\sqrt{m^2-1}\,L(1,\chi_{D_m}).
}
\tag{3}
$$

This exact identification is useful. It removes the conductor ambiguity on the target family.

But the prime geodesic theorem counts primitive conjugacy classes, not integers with prime factors. Its main term measures the size of the class groups, not the minimum possible number of genera.

For example, the matrix

$$
\begin{pmatrix}
m&m^2-1\\
1&m
\end{pmatrix}
$$

has determinant one and trace $2m$ for every integer $m\ge2$. Its primitive-form discriminant is $4(m^2-1)$. The fundamental unit of that order is $m+\sqrt{m^2-1}$, so it supplies a primitive hyperbolic class regardless of the primality of $m-1$ and $m+1$.

3. Congruence localization is available, but does not count genera

Chatzakos–Harcos–Kaneko's published 2024 theorem, The Prime Geodesic Theorem in Arithmetic Progressions, gives a useful refinement.

For an odd prime $\ell$, its Theorem 1.1 states

$$
\Psi_\Gamma(x;\ell,a)
=c_\ell(a)x+
O_{\ell,\varepsilon}(x^{3/4+\vartheta/2+\varepsilon}),
$$

where $\vartheta$ is an admissible quadratic Dirichlet subconvexity exponent, and

$$
c_\ell(a)=
\begin{cases}
1/(\ell-1),&
\left(\frac{a^2-4}{\ell}\right)=1,\\
1/(\ell+1),&
\left(\frac{a^2-4}{\ell}\right)=-1,\\
\ell/(\ell^2-1),&
\ell\mid a^2-4.
\end{cases}
$$

The error constant is independent of $\ell$ in the first two cases. The ramified case has a separate dependence on $\ell$.

users.renyi.hu

At our trace scale $t\asymp M$, geodesic norms are of order $M^2$. Thus the quoted uniform error has size $M^{3/2+\vartheta+2\varepsilon}$, whereas the individual residue-class main term is of size $M^2/\ell$.

This does not provide localization to individual traces, or distribution at the composite moduli needed to sift both $m-1$ and $m+1$ to their square-root primality boundaries.

There is also a more fundamental issue: the local factor records splitting and ramification at $\ell$, not the number of distinct ramified primes in the entire discriminant.

One can prescribe any fixed finite collection of such local conditions while leaving arbitrarily many additional prime factors in $m^2-1$.

I therefore tested a stronger repair: remove the nonfundamental discriminants completely and evaluate the average on precisely the squarefree family where the genus certificate is valid.

4. A conductor-free trace average — independently derived

Let $Q$ be a fixed even integer, and let $a$ be an even residue satisfying

$$
(a^2-1,Q)=1.
$$

This allows us to prescribe, for example, $m\equiv0\pmod6$, together with admissibility conditions at any fixed collection of other primes.

Define

$$
\mathcal F_{Q,a}(M)=
\{M<m\le2M:m\equiv a\pmod Q,\
\mu^2(m^2-1)=1\}.
$$

Proposition. There is an explicit positive constant $\mathfrak A_{Q,a}$ such that

$$
\boxed{
\sum_{m\in\mathcal F_{Q,a}(M)}
L(1,\chi_{D_m})
=
\frac{\mathfrak A_{Q,a}}Q M
+O_Q(M^{99/100}),
}
\tag{4}
$$

where

$$
\begin{aligned}
\mathfrak A_{Q,a}
={}&
\prod_{\substack{\ell\mid Q\\\ell>2}}
\left(1-
\frac{1}{\ell}\left(\frac{a^2-1}{\ell}\right)
\right)^{-1}\\
&\times
\prod_{\substack{\ell\nmid Q\\\ell>2}}
\left(
1-\frac2{\ell^2}
-\frac{2}{\ell(\ell^2-1)}
\right).
\end{aligned}
$$

Every factor is positive, and the infinite product converges absolutely.

This calculation does not assume a prime-pair conjecture or use a nonfundamental class-number contribution.

Proof: truncate the $L$-function at a permissible length

Put

$$
Y=M^{4/5},\qquad A=M^{1/20}.
$$

On the squarefree support, $\chi_{D_m}$ is primitive with conductor of order $M^2$.

Burgess's character-sum bound with parameter two gives

$$
\sum_{n\le N}\chi_{D_m}(n)
\ll_\varepsilon
N^{1/2}D_m^{3/16+\varepsilon}.
$$

This version permits the composite conductors used here. The original result is in Burgess's work on character sums and $L$-series; the precise bound and conductor conditions also appear in equation (1) of Heath-Brown's primary paper Burgess's Bounds for Character Sums.

academic.oup.com+1

Partial summation therefore yields

$$
L(1,\chi_{D_m})
=
\sum_{n\le Y}\frac{\chi_{D_m}(n)}n
+
O_\varepsilon(M^{-1/40+\varepsilon}),
\tag{5}
$$

uniformly over the squarefree family.

The error exponent follows from $M^{3/8}Y^{-1/2}=M^{-1/40}$.

Proof: retain the squarefree restriction

Because $m$ is even, the two odd integers $m-1,m+1$ are coprime. Thus

$$
\mu^2(m^2-1)
=
\left(\sum_{r^2\mid m-1}\mu(r)\right)
\left(\sum_{s^2\mid m+1}\mu(s)\right).
$$

Truncate both sums at $A$.

The number of integers affected by an omitted square divisor is

$$
\ll
\sum_{A<r\le\sqrt{2M+1}}
\left(\frac M{r^2}+1\right)
\ll M/A+\sqrt M.
$$

Using the usual divisor bound to control the truncated coefficients, and the harmonic bound $O(\log Y)$ for the truncated $L$-series, the resulting total error is

$$
O_\varepsilon(M^{19/20+\varepsilon}).
$$

The approximation (5) was applied before replacing the squarefree indicator. This avoids applying a primitive-character estimate to an imprimitive discriminant.

Proof: evaluate the complete periodic means

For odd $n$, the truncated character is

$$
\chi_{4(m^2-1)}(n)=
\left(\frac{m^2-1}{n}\right).
$$

After imposing $r^2\mid m-1$, $s^2\mid m+1$ and the fixed progression modulo $Q$, the variable $m$ runs through one progression of modulus $Qr^2s^2$, provided the conditions are compatible.

The Jacobi-symbol sequence along this progression has period dividing $n$. Its complete-period replacement costs $O(n)$.

After division by $n$, summation over $n\le Y$ and $r,s\le A$, this error is

$$
O(A^2Y)=O(M^{9/10}).
$$

For a prime $\ell\nmid Qrs$, the local means are

$$
\kappa(\ell^j)=
\begin{cases}
-1/\ell,&j\text{ odd},\\
1-2/\ell,&j\text{ even},\ j\ge2.
\end{cases}
$$

The odd-exponent identity follows from

$$
\sum_{u\bmod\ell}
\left(\frac{u^2-1}{\ell}\right)=-1;
$$

the even-exponent mean simply excludes $u=\pm1$.

If $\ell\mid rs$, the character vanishes whenever $\ell\mid n$.

It follows that the complete local factor, including the two squarefree exclusions, is

$$
1-\frac2{\ell^2}
+\sum_{j\ge1}\frac{\kappa(\ell^j)}{\ell^j}
=
1-\frac2{\ell^2}
-\frac2{\ell(\ell^2-1)}.
$$

For $\ell\mid Q$, the character is fixed and nonzero, giving the geometric-series factor in $\mathfrak A_{Q,a}$. The prime two contributes one.

Finally, the series of absolute local coefficients converges even with $n^{-1}$ replaced by $n^{-3/4}$. The omitted $n>Y$ terms therefore cost a power saving. Extending the absolutely convergent square-divisor sums beyond $A$ costs $O(M/A)$.

Combining these errors with (5) proves (4). ∎

Consequence for the actual fundamental geodesic weight

The argument is uniform for interval endpoints between $M$ and $2M$. Partial summation and (3) now give

$$
\boxed{
\sum_{m\in\mathcal F_{Q,a}(M)}
G(m)
=
\frac{6\mathfrak A_{Q,a}}Q M^2
+O_Q(M^{199/100}).
}
\tag{6}
$$

Thus the entire fundamental-discriminant part of the desired family has a positive, independently evaluated class-number main term.

The remaining question is whether this positive mass forces the minimum genus rank.

It does not follow from (6), as the next calculation demonstrates.

5. Why the conductor-free average still does not force minimal rank

Write

$$
r(m)=\dim_{\mathbb F_2}(C_m/C_m^2).
$$

On our squarefree family, $r(m)=\omega(m-1)+\omega(m+1)$.

Tenenbaum's published theorem on joint local laws for the number of prime factors gives, for fixed positive integers $i,j$,

$$
\#\{M<m\le2M:
\omega(m-1)=i,\ \omega(m+1)=j\}
\ll
\frac{M}{\log^2 M}
\frac{(\log\log M)^{i+j-2}}{(i-1)!(j-1)!}.
$$

The two distinct linear polynomials satisfy the theorem's hypotheses, including its fixed-divisor condition.

tenenb.perso.math.cnrs.fr

For every fixed $K\ge2$, this yields

$$
\#\{m\in\mathcal F_{Q,a}(M):r(m)\le K\}
\ll_K
\frac{M(\log\log M)^{K-2}}{\log^2 M}.
$$

The elementary uniform upper bound $L(1,\chi_{D_m})\ll\log M$, combined with (3), therefore proves

$$
\boxed{
\sum_{\substack{m\in\mathcal F_{Q,a}(M)\\r(m)\le K}}
G(m)
\ll_K
\frac{M^2(\log\log M)^{K-2}}{\log M}
=o(M^2).
}
\tag{7}
$$

Consequently,

$$
\sum_{\substack{m\in\mathcal F_{Q,a}(M)\\r(m)>K}}
G(m)
\sim \frac{6\mathfrak A_{Q,a}}Q M^2
$$

for every fixed $K$.

The entire leading class-number main term survives after deleting not merely all twins, but every discriminant of any fixed bounded narrow 2-rank.

This is an unconditional result about the actual discriminants. It is stronger than an abstract warning that an average might be dominated by composites.

It does not assert that deleting those ranks preserves the power-saving error in (6).

Fixed congruences cannot repair this obstruction

For any fixed admissible progression $m\equiv a\pmod Q$, choose distinct fresh odd primes $s_1,\ldots,s_k$ and impose

$$
m\equiv1+s_i\pmod{s_i^2}
\qquad(1\le i\le k).
$$

Each $s_i$ then divides $m-1$ exactly once.

These conditions are compatible by CRT. The elementary squarefree sieve on the remaining primes gives a positive density of squarefree $m^2-1$ in the resulting fixed progression: each remaining odd prime excludes two classes modulo its square, and

$$
\prod_{\ell>2}(1-2/\ell^2)>0.
$$

The omitted large-square tail is $O(M/z+\sqrt M)$ after sieving through a fixed bound $z$, so the density statement follows by first letting $M$ grow and then $z$ grow.

Hence arbitrarily high genus rank remains possible inside every such fixed local restriction.

The required localization must control prime factors at growing scales, not just the splitting behavior at a finite list of places.

6. Test an involution and an inverse-genus weight

Conjugation on the narrow ideal class group acts by inversion:

$$
[c]\longmapsto[c]^{-1}.
$$

Indeed, an ideal multiplied by its conjugate is generated by its positive rational norm.

The number of fixed classes is exactly

$$
|\operatorname{Fix}(\iota_m)|=|C_m[2]|=2^{r(m)}.
$$

Thus the permutation trace of this involution is an exact genus detector. But the prime geodesic trace in (3) counts all $h^+(D_m)$ classes, not just these fixed classes.

I tested the following one-sided minorant, which attempts to correct this mismatch:

$$
U(m)=\frac8{|C_m[2]|}-1.
$$

Its values are

$$
U(m)=
\begin{cases}
1,&r(m)=2,\\
0,&r(m)=3,\\
<0,&r(m)\ge4.
\end{cases}
$$

Therefore

$$
\sum_{m\in\mathcal F_{Q,a}(M)}G(m)U(m)>0
$$

would force a genuine twin.

Unfortunately, the mean has the opposite sign.

From (6)–(7), for every fixed $K$,

$$
\frac{\sum_{m\in\mathcal F_{Q,a}(M)}
G(m)\,2^{-r(m)}}
{\sum_{m\in\mathcal F_{Q,a}(M)}G(m)}
\le o_K(1)+2^{-K}.
$$

First let $M\to\infty$, then $K\to\infty$. It follows that

$$
\boxed{
\sum_{m\in\mathcal F_{Q,a}(M)}
G(m)U(m)
\sim-\frac{6\mathfrak A_{Q,a}}Q M^2.
}
\tag{8}
$$

The inverse-genus minorant is valid pointwise but fails decisively on averaging.

Minimal rank is also not the same as one class per genus

Kopp and Lagarias's recent manuscript Unit-generated orders of real quadratic fields I: Class number bounds studies precisely the discriminant families $n^2-4$ and $n^2+4$.

Their Theorem 3.3 derives class-group growth

$$
h(n^2-4)=n^{1+o(1)},
$$

and their Corollary 1.7 establishes finiteness of unit-generated quadratic orders having one narrow class per genus.

gskopp.com+1

In our squarefree family the same growth follows directly from the class-number formula, the explicit regulator, and Siegel's lower bound for $L(1,\chi)$.

Meanwhile,

$$
|C_m[2]|=2^{\omega(m^2-1)}=m^{o(1)}.
$$

Consequently,

$$
\frac{|C_m|}{|C_m[2]|}=m^{1+o(1)}.
$$

Even a genuine twin-prime discriminant of minimal rank has increasingly many classes per genus. Trying to force the inversion involution to fix every class would impose a condition much stronger than the desired minimal rank, and one which cannot hold at arbitrarily large traces in this family.

7. A stronger repair: an exact class-number congruence modulo eight

The most promising additional connection I obtained is that, on two fixed congruence classes of $m$, the minimal-rank condition can be detected using the class number itself, rather than the separately computed genus count.

Proposition. Suppose $m>2$ is even, $m^2-1$ is squarefree, and

$$
m\equiv4\ \text{or}\ 6\pmod8.
$$

Then

$$
\boxed{
h^+(D_m)\equiv4\pmod8
\quad\Longleftrightarrow\quad
m-1,\ m+1\text{ are both prime}.
}
\tag{9}
$$

This is an exact unconditional class-number divisibility certificate.

Proof: the composite direction

If either $m-1$ or $m+1$ is composite, squarefreeness and coprimality imply

$$
r(m)\ge3.
$$

Genus theory then gives

$$
8\mid |C_m[2]|\mid h^+(D_m).
$$

Thus the displayed congruence cannot hold.

Proof: the prime direction

Suppose

$$
p=m-1,\qquad q=m+1
$$

are both prime.

The discriminant has three prime-discriminant factors

$$
D_m=(-4)p^*q^*,
\qquad
p^*=(-1)^{(p-1)/2}p,
\quad
q^*=(-1)^{(q-1)/2}q.
$$

The narrow 2-rank is exactly two. To prove that the class number is four modulo eight, it remains to establish that the narrow 4-rank is zero.

I checked the Rédei-matrix convention and its rank formula in Section 2.2, Theorem 2.2 of Koymans–Pagano–Sofos, Elliptic fibrations and $3\cdot2^k$.

pure.mpg.de

With rows indexed by $2,p,q$ and columns by $-4,p^*,q^*$, the off-diagonal entry is the additive version of the appropriate quadratic symbol: $+1$ becomes zero and $-1$ becomes one. Diagonal entries make every row sum zero.

The exact matrices are:

$$
R_4=
\begin{pmatrix}
0&1&1\\
1&0&1\\
0&1&1
\end{pmatrix},
\qquad m\equiv4\pmod8,
$$

and

$$
R_6=
\begin{pmatrix}
1&1&0\\
0&1&1\\
1&1&0
\end{pmatrix},
\qquad m\equiv6\pmod8.
$$

For example, when $m\equiv4\pmod8$, we have $p\equiv3$, $q\equiv5\pmod8$, and

$$
\left(\frac{-4}{p}\right)=-1,
\qquad
\left(\frac qp\right)=\left(\frac2p\right)=-1,
\qquad
\left(\frac{-p}{q}\right)=-1.
$$

These determine the last two rows; the first follows from the Kronecker symbols at two.

For $m\equiv6\pmod8$, the same calculation uses $p\equiv5$, $q\equiv7\pmod8$, and $p=q-2$.

Both matrices have rank two over $\mathbb F_2$. Rédei's formula therefore gives

$$
\operatorname{rk}_4 C_m
=3-1-\operatorname{rank}R_m=0.
$$

A finite abelian group of 2-rank two and 4-rank zero has 2-primary subgroup exactly

$$
C_2\times C_2.
$$

Hence $v_2(h^+(D_m))=2$, proving the prime direction of (9). ∎

For completeness, the other two even residue classes $m\equiv0,2\pmod8$ give Rédei matrices of rank one when both endpoints are prime. Their narrow 4-rank is one, so their class numbers are divisible by eight. They cannot be included in (9).

Since the norm-minus-one equation is insoluble on this family, $h^+(D_m)=2h(D_m)$, where $h$ is the ordinary class number. Thus (9) can equivalently be stated using

$$
h(D_m)\equiv2\pmod4.
$$

This refinement of the genus certificate is the strongest exact divisibility connection obtained here. I make no claim of literature novelty.

8. Can the class-number trace formula detect that congruence?

To remove the local obstruction modulo three, restrict to

$$
\mathcal F_M^*=
\left\{
\begin{array}{l}
M<m\le2M,\quad m\equiv0\pmod3,\\
m\equiv4\text{ or }6\pmod8,\quad
\mu^2(m^2-1)=1
\end{array}
\right\}.
$$

Equation (9) gives the exact identity

$$
\boxed{
\sum_{m\in\mathcal F_M^*}
\left(1-(-1)^{h^+(D_m)/4}\right)
=
2T_*(M),
}
\tag{10}
$$

where $T_*(M)$ counts the genuine twins with centers in the indicated residue classes.

Consequently, it would suffice to prove

$$
\boxed{
\limsup_{M\to\infty}
\frac{\log^2 M}{M}
\sum_{m\in\mathcal F_M^*}
\left(1-(-1)^{h^+(D_m)/4}\right)>0.
}
\tag{11}
$$

Even mere positivity on infinitely many disjoint dyadic intervals would suffice.

The important change is that the missing statistic now depends only on a congruence of the narrow class number. No separate enumeration of ambiguous ideal classes is required.

However, the inspected prime geodesic and Zagier $L$-series estimates evaluate real-valued class-number weights. They do not evaluate the phase $(-1)^{h^+/4}$.

A quantitative test of the available precision

To make this distinction rigorous, consider the numerical comparison obtained by replacing each narrow class number in the squarefree family by

$$
\widetilde h(m)
=8\left\lceil\frac{h^+(D_m)}8\right\rceil.
$$

Every comparison value is divisible by eight. Because genus theory already gives $4\mid h^+(D_m)$, the change is either zero or four.

The corresponding geodesic weight changes by at most

$$
8\log\epsilon_m=O(\log M)
$$

per trace. Over an entire dyadic interval, the change is therefore

$$
\boxed{O(M\log M).}
\tag{12}
$$

This is smaller than the error in the independently established conductor-free average (6). It is also smaller than the global prime geodesic error allowances at the norm scale $x\asymp M^2$, even the conjectural global allowance $O(x^{1/2+\varepsilon})$.

The same bound holds if we sum over a fixed congruence-restricted subfamily.

Thus the known size and progression averages cannot distinguish, at their certified precision, the true class-number values from numerical values having no desired residue modulo eight.

This is an information comparison, not a construction of alternative quadratic fields or class groups. It does not preserve every exact spectral identity. It establishes the specific limitation of the available average estimates.

A successful trace-formula repair would need arithmetic information that controls class-number divisibility itself, rather than merely a more accurate leading average of class-number magnitudes.

Final research verdict

Three useful unconditional connections survive:

-

The minimal narrow 2-rank is exactly the ordinary twin-prime condition on the squarefree discriminant family.

-

The entire fundamental-discriminant geodesic weight admits an explicit positive mean, with the conductor terms removed and a power-saving error. Nevertheless, every fixed bounded-rank sector contributes negligibly to its leading term.

-

For squarefree $m^2-1$ and $m\equiv4,6\pmod8$, the exact equivalence

$$
\boxed{
h^+\!\left(4(m^2-1)\right)\equiv4\pmod8
\iff m-1,\ m+1\text{ prime}
}
$$

provides a more selective class-number certificate than genus theory alone.

The inverse-genus lower-bound attempt fails by the proved negative asymptotic (8). The class-number congruence repair leads to the precise missing estimate (11).

I have not established that estimate or an unconditional proof of infinitely many twin primes. The remaining obstacle is a lower bound for a specific class-number residue on this thin discriminant family, not the ordinary prime geodesic main term, the regulator, or an omitted conductor contribution.

---

### Recovered response 4

1. The imaginary quadratic certificate is exact

Let $m>2$ be even, let $d=m^2-1$ be squarefree, and let $\ell\equiv1\pmod4$ be prime with $\ell\nmid d$. Put

$$
D=-\ell(m^2-1),\qquad
h(D)=|\operatorname{Cl}(\mathbb Q(\sqrt D))|.
$$

Since $d\equiv3\pmod4$, the integer $D$ is a negative fundamental discriminant. In particular, there is no quadratic-order conductor to remove.

Gauss genus theory gives

$$
\operatorname{rk}_2\operatorname{Cl}(\mathbb Q(\sqrt D))
=\omega(D)-1
=\omega(m-1)+\omega(m+1).
$$

Both $m-1$ and $m+1$ are coprime odd integers greater than one. Hence

$$
\boxed{
h(-\ell(m^2-1))\equiv4\pmod8
\ \Longrightarrow\
m-1,\ m+1\text{ are prime}.
}
\tag{1}
$$

Indeed, if either neighbor were composite, squarefreeness would give at least three distinct prime factors in their product. Genus theory would then force $8\mid h(D)$.

The important distinction from ordinary class-number indivisibility is that we are seeking exactly $v_2(h(D))=2$, not merely a class number whose odd-primary part has some specified behavior. Genus theory supplies the necessary minimal rank automatically if this exact valuation can be established.

link.springer.com

2. The converse holds after choosing the auxiliary prime

There is a particularly useful strengthening of (1): every genuine twin-prime pair admits auxiliary primes producing the required class-number residue.

Suppose $p=m-1$ and $q=m+1$ are both prime. Define the additive Legendre symbols

$$
x=\left[\frac qp\right],\qquad
y=\left[\frac{\ell}{p}\right],\qquad
z=\left[\frac{\ell}{q}\right],
$$

where brackets assign zero to a quadratic residue and one to a nonresidue.

Since exactly one of $p,q$ is congruent to three modulo four, and $\ell\equiv1\pmod4$, quadratic reciprocity makes the Rédei matrix symmetric:

$$
R=
\begin{pmatrix}
x+y&x&y\\
x&x+z&z\\
y&z&y+z
\end{pmatrix}.
$$

I checked the convention and rank formula in Section 2.2, Theorem 2.2 of Koymans–Pagano–Sofos, Elliptic fibrations and $3\cdot2^k$.

pure.mpg.de

The class group has 2-rank two, and its 4-rank is

$$
r_4=2-\operatorname{rank}_{\mathbb F_2}R.
$$

The matrix has rank two precisely when at least two of $x,y,z$ equal one. For example, a principal $2\times2$ minor has determinant

$$
xy+xz+yz.
$$

Consequently,

$$
\boxed{
h(-\ell pq)\equiv4\pmod8
\iff xy+xz+yz=1
\quad\text{in }\mathbb F_2.
}
\tag{2}
$$

In particular, choosing

$$
\left(\frac{\ell}{p}\right)
=
\left(\frac{\ell}{q}\right)=-1,
\qquad \ell\equiv1\pmod4,
$$

always suffices.

These conditions define reduced residue classes modulo $4pq$. Dirichlet's theorem therefore supplies infinitely many auxiliary primes.

Exact auxiliary densities

Since $q=p+2$,

$$
\left(\frac qp\right)=\left(\frac2p\right).
$$

The prime number theorem in fixed arithmetic progressions now gives the following exact limiting proportions.

Twin center $m\bmod8$
 |
Required condition
 |
Proportion among auxiliary primes $\ell\equiv1\bmod4$
 |

$0,2$
 |
Both auxiliary symbols are nonresidues
 |
$1/4$
 |

$4,6$
 |
At least one auxiliary symbol is a nonresidue
 |
$3/4$
 |

Thus there is no further intrinsic 4-rank obstruction once the two neighbors are prime.

There is also a polynomial bound on the size of a suitable auxiliary prime. Let $A$ be an admissible absolute exponent in Linnik's theorem. Among the reduced classes modulo $4pq$, there are

$$
\frac{(p-1)(q-1)}4
$$

classes imposing both nonresidue conditions and $\ell\equiv1\pmod4$.

At least one of their least positive representatives is therefore $\gg m^2$. Applying Linnik's theorem to that class yields, for every sufficiently large twin center,

$$
\boxed{
2m<\ell\ll m^{2A},
\qquad
h(-\ell(m^2-1))\equiv4\pmod8.
}
\tag{3}
$$

The Linnik input is unconditional; a primary reference is Xylouris's On the least prime in an arithmetic progression and estimates for the zeros of Dirichlet $L$-functions.

impan.pl

Together, (1)–(3) give an exact equivalence:

The twin-prime conjecture holds if and only if the desired class-number nonvanishing occurs for unbounded centers $m$, even with the auxiliary prime restricted to polynomial size in $m$.

This resolves the algebraic implication in both directions. The unresolved issue is obtaining those unbounded centers.

3. Published nonvanishing results: the actual hypotheses

I examined the primary results most relevant to progression-restricted class-number indivisibility.

Result
 |
Established input
 |
Why it does not supply the required implication
 |

Wiles, On class groups of imaginary quadratic fields (2015), Theorem 0.0.1
 |
Existence with specified local conditions and class number indivisible by an odd prime
 |
Does not establish exact 2-adic valuation two
 |

Beckwith, Indivisibility of class numbers of imaginary quadratic fields (2017), Theorem 1.1 and Corollary 1.2
 |
Quantitative indivisibility with prescribed local conditions; lower bound of order $\sqrt X/\log X$
 |
The divisibility prime is odd, and the remaining discriminant factor has no required quadratic-polynomial shape
 |

Ono–Skinner, Fourier coefficients of half-integral weight modular forms modulo $\ell$
 |
Squarefree-index nonvanishing for suitable eigenforms, outside a finite set of coefficient primes
 |
Cannot assume that two lies outside the exceptional set, or that dividing the required coefficients by four produces an eligible eigenform
 |

Beckwith–Raum–Richter, Hurwitz congruences (2020), Theorem 0.1
 |
Restrictions on identically vanishing progressions modulo primes greater than three
 |
Not a nonvanishing theorem modulo eight
 |

Beckwith–Raum–Richter, specified split primes (2024)
 |
Removes important restrictions on prescribed split primes in odd-primary indivisibility results
 |
Still an odd-prime theorem, not exact 2-adic valuation
 |

Fouvry–Klüners, 4-rank distribution, Theorem 6
 |
Moments over negative odd fundamental discriminants
 |
Does not force the simultaneous minimum 2-rank on the proposed discriminant family
 |

ora.ox.ac.uk+5

The exceptional-prime distinction in Ono–Skinner is essential. A theorem valid for all but finitely many coefficient primes cannot be specialized to the particular prime two without additional verification.

Likewise, Beckwith's quantitative theorem constructs discriminants involving a prescribed prime and a bounded auxiliary factor. Its conclusion does not require that factor to be $m^2-1$.

I found no applicable published theorem among the inspected sources guaranteeing $h(D)\equiv4\pmod8$ on the actual family with unbounded $m$. This is a statement about the inspected results, not an exhaustive assertion about every publication on class-number congruences.

Some source HTML and PDF image retrievals failed. I used the available theorem text and author publication records for these scope checks; I do not claim to have independently audited the complete modular-form proofs.

4. A decisive obstruction: infinitely many discriminants can come from one twin

Allowing the auxiliary prime to vary creates a serious multiplicity problem.

Define $N(X)$ to count distinct fundamental discriminants satisfying

$$
\begin{gathered}
D=-\ell(m^2-1),\qquad |D|\le X,\\
m>2\text{ even},\quad \mu^2(m^2-1)=1,\\
\ell>2m,\quad \ell\equiv1\pmod4\text{ prime},\\
h(D)\equiv4\pmod8.
\end{gathered}
$$

The extra condition $\ell>2m$ makes the representation unique: the auxiliary prime is the largest prime divisor of $|D|$, and the other two are the twin endpoints.

I obtain the following unconditional asymptotic, despite the unresolved twin-prime conjecture.

Proposition.

$$
\boxed{
N(X)\sim \kappa\frac X{\log X},
}
\tag{4}
$$

where

$$
\kappa=
\sum_{\substack{m>2\text{ even}\\m-1,m+1\text{ prime}}}
\frac{\delta_m}{m^2-1},
\qquad
\delta_m=
\begin{cases}
1/8,&m\equiv0,2\pmod8,\\
3/8,&m\equiv4,6\pmod8.
\end{cases}
$$

The series converges absolutely and is strictly positive.

Proof

For each fixed genuine twin center $m$, the auxiliary densities established in Section 2 give

$$
N_m(X)\sim
\delta_m\frac{X}{(m^2-1)\log X}.
$$

To justify summing these asymptotics, fix a center cutoff $B$. The contribution from $m>B$ is at most

$$
\sum_{m>B}\pi\left(\frac X{m^2-1}\right).
$$

For $B<m\le X^{1/4}$, the elementary prime-counting upper bound gives

$$
\sum_{B<m\le X^{1/4}}
\pi\left(\frac X{m^2-1}\right)
\ll \frac X{B\log X}.
$$

For $m>X^{1/4}$, use $\pi(t)\le t$, obtaining

$$
\sum_{m>X^{1/4}}\pi\left(\frac X{m^2-1}\right)
\ll X^{3/4}.
$$

Thus the normalized tail is $O(1/B)+o(1)$. First apply the fixed-center asymptotics through $B$, then let $B\to\infty$.

This proves (4).

The already known twin pair $(3,5)$, with $m=4$, contributes

$$
\frac{3}{8\cdot15}=\frac1{40}
$$

to $\kappa$. In particular, $\kappa\ge1/40$. ∎

This result identifies exactly why even a strong global nonvanishing theorem on the requested family would be insufficient. The family already contains $\gg X/\log X$ nonvanishing discriminants, unconditionally, generated by known twin centers.

Its asymptotic is compatible with there being only finitely many twin primes.

An argument must either restrict the centers directly or impose a relation such as the polynomial auxiliary bound (3), which prevents indefinitely reusing finitely many centers.

5. Hurwitz coefficients introduce a second multiplicity problem

For positive $N$ such that $-N$ is fundamental and $N>4$,

$$
H(N)=h(-N),
$$

in the usual Hurwitz normalization.

For nonfundamental discriminants, the precise formula is

$$
H(Nf^2)
=
h(-N)
\sum_{d\mid f}\mu(d)\chi_{-N}(d)\sigma_1(f/d).
\tag{5}
$$

I checked this normalization in Beckwith's equation (2.1), together with Beckwith–Raum–Richter's Hecke-factorization formula.

link.springer.com+1

In particular, for an odd prime $s\nmid N$,

$$
H(Ns^2)
=
h(-N)\bigl(1+s-\chi_{-N}(s)\bigr).
$$

The multiplier is odd. Consequently,

$$
h(-N)\equiv4\pmod8
\quad\Longrightarrow\quad
H(Ns^2)\equiv4\pmod8.
\tag{6}
$$

Thus a single nonvanishing fundamental discriminant can generate infinitely many nonvanishing Hurwitz coefficients without changing its underlying quadratic field.

For any fixed progression modulus $A$, taking $s\equiv1\pmod A$ even preserves the original coefficient-index residue:

$$
Ns^2\equiv N\pmod A.
$$

Therefore, an infinitude statement for nonzero Hurwitz coefficients in a progression does not automatically produce infinitely many fundamental discriminants. And even producing infinitely many fundamental discriminants does not solve the center-multiplicity problem in Section 4.

Both filters must be retained.

The weight-three-halves formulation

On the squarefree residue class $N\equiv3\pmod8$, Gauss's three-square formula gives

$$
r_3(N)=24h(-N).
$$

Hence on that class,

$$
h(-N)\equiv4\pmod8
\iff
r_3(N)\equiv96\pmod{192}.
$$

This is an exact modular-coefficient formulation of the desired certificate.

However, the relevant indices must still satisfy

$$
N=\ell(m^2-1).
$$

Ordinary progression sieving of a weight-three-halves form does not impose this polynomial-index condition. Also, the complementary class $N\equiv7\pmod8$ has $r_3(N)=0$ regardless of its class number, so the three-square form cannot cover the whole family.

6. Substantive repair attempt: impose square congruences and vary all prime factors

The natural repair is to impose

$$
\frac{|D|}{\ell}+1\equiv a^2\pmod Q
$$

for a large collection of local moduli, hoping that a class number nonzero modulo eight will force the expression to be an actual square.

I tested this using genuine fundamental discriminants, not a numerical comparison sequence.

Proposition: plentiful false positives survive every fixed admissible congruence filter

Fix an integer $Q$ divisible by four and residues $a,b$ satisfying

$$
a\text{ even},\qquad
(a^2-1,Q)=1,\qquad
(b,Q)=1,\qquad
b\equiv1\pmod4.
$$

Let $Y=M^B$, where $B\ge4$ is fixed.

Then there are

$$
\boxed{
\gg_{Q,a,b,B}
\frac{M^2Y}{(\log M)^2\log Y}
}
\tag{7}
$$

distinct negative fundamental discriminants of the form

$$
D=-\ell rs
$$

satisfying all the following conditions:

$$
\begin{gathered}
M<r<1.2M,\qquad 1.6M<s<2M,\\
Y<\ell\le2Y,\qquad r,s,\ell\text{ prime},\\
r\equiv a-1,\quad s\equiv a+1,\quad
\ell\equiv b\pmod Q,\\
h(D)\equiv4\pmod8.
\end{gathered}
$$

In particular,

$$
rs+1\equiv a^2\pmod Q.
$$

Nevertheless, none of these discriminants belongs to the desired family.

Proof

The prime number theorem in the two fixed progressions supplies

$$
\gg_{Q,a}\frac{M^2}{(\log M)^2}
$$

pairs $(r,s)$ in the indicated disjoint intervals.

Because their congruence classes modulo four are opposite, $-\ell rs$ is fundamental.

It remains to find many suitable auxiliary primes uniformly for almost all these pairs.

Put

$$
\mathcal L=
\{\ell:Y<\ell\le2Y,\ \ell\text{ prime},\
\ell\equiv b\pmod Q\},
$$

so $|\mathcal L|\asymp_QY/\log Y$.

For each pair $(r,s)$, consider the three primitive quadratic characters

$$
\chi_r(\ell)=\left(\frac{\ell}{r}\right),\qquad
\chi_s(\ell)=\left(\frac{\ell}{s}\right),\qquad
\chi_{rs}=\chi_r\chi_s.
$$

All their conductors are at most $4M^2$.

The classical multiplicative large sieve, applied with coefficients $\mathbf1_{\mathcal L}$, gives

$$
\sum_{q\le4M^2}
\frac q{\varphi(q)}
\sum_{\chi\bmod q}^{*}
\left|\sum_{\ell\in\mathcal L}\chi(\ell)\right|^2
\ll (Y+M^4)|\mathcal L|.
$$

This is the standard primitive-character inequality, stated as Theorem 19.16 in Montgomery–Vaughan's large-sieve treatment.

personal.science.psu.edu

Because $Y\ge M^4$, there are at most $O_Q(\log Y)$ primitive characters satisfying

$$
\left|\sum_{\ell\in\mathcal L}\chi(\ell)\right|
>\frac{|\mathcal L|}{10}.
$$

A bad single-prime character excludes at most $O(M/\log M)$ pairs. A bad character of conductor $rs$ excludes at most one pair, since the factor intervals are disjoint.

Thus the number of excluded pairs is negligible relative to $M^2/\log^2M$.

For every remaining pair, the number of auxiliary primes having both Legendre symbols equal to $-1$ is exactly

$$
\frac14\sum_{\ell\in\mathcal L}
(1-\chi_r(\ell))(1-\chi_s(\ell)).
$$

The three character estimates give a lower bound of

$$
\frac{7}{40}|\mathcal L|.
$$

By the Rédei calculation in Section 2, every resulting discriminant has class number congruent to four modulo eight. Multiplication by the number of good pairs proves (7).

The discriminants are distinct because their three prime factors occupy separate intervals.

Finally, none contains any pair of prime factors differing by two: $r,s$ are separated by at least $0.4M$, and the auxiliary prime is much larger.

If $rs+1$ were a square, then

$$
rs=(m-1)(m+1)
$$

for an even integer $m$. Since $rs$ has exactly two prime factors, these would have to be $r,s$, contradicting their separation.

This proves the proposition. ∎

What this rules out

The construction preserves the exact desired class-number residue, squarefreeness, fundamental discriminant status, fixed congruence restrictions, polynomial-sized prime factors, and a simultaneously varying auxiliary prime.

It nevertheless contains no target discriminants.

Moreover, its population has an extra factor of order $M$ compared with the conjectural population where the two smaller prime factors differ by two.

Thus even quite strong nonvanishing results with balanced prime-factor restrictions would not automatically detect the required polynomial shape.

7. The quantitative exceptional-set requirement

Consider the actual two-scale target statistic

$$
\mathcal N(M,Y)=
\#\left\{
\begin{array}{l}
M<m\le2M,\ m\text{ even},\ \mu^2(m^2-1)=1,\\
Y<\ell\le2Y,\ \ell\equiv1\pmod4\text{ prime},\\
h(-\ell(m^2-1))\equiv4\pmod8
\end{array}
\right\}.
$$

Take $Y=M^B$, with fixed $B\ge4$.

By (1), the standard twin-prime upper sieve gives

$$
\mathcal N(M,Y)
\ll
\frac{MY}{(\log M)^2\log Y}.
\tag{8}
$$

At discriminant height $X\asymp M^{B+2}$, this is

$$
\boxed{
\mathcal N(M,Y)
\ll_B
\frac{X^{1-1/(B+2)}}{(\log X)^3}.
}
\tag{9}
$$

Even before imposing nonvanishing, the entire target family has cardinality only $O(MY/\log Y)$.

Consequently, an exceptional set of size

$$
O_A(X/\log^A X)
$$

for every fixed $A$ could contain the entire two-scale family. Arbitrary logarithmic savings over all discriminants are not enough to remove this problem.

The logarithmically saving moment estimates in the inspected 4-rank distribution results operate on the much larger ambient family. They do not establish the necessary relative nonvanishing on the set in (9).

A power-saving exceptional-set estimate of sufficiently strong exponent would at least address the size comparison, but it would also need to concern the correct joint condition: minimal 2-rank and vanishing 4-rank. A 4-rank-zero theorem alone does not establish $v_2(h)=2$.

8. The precise surviving dependency

The auxiliary averaging itself can be controlled to a useful extent.

Let $T(M)$ be the number of actual twin centers in $(M,2M]$, and retain $Y=M^B$, $B\ge4$.

The same multiplicative-large-sieve argument used in Section 6 shows that, except for $O_B(\log M)$ possible genuine twin centers, each such center has

$$
\gg_B Y/\log Y
$$

auxiliary primes giving $h(D)\equiv4\pmod8$.

Here a bad single-prime character affects at most a bounded number of twin centers, and a bad product character affects at most one.

Thus

$$
\mathcal N(M,Y)
\gg_B
\frac{Y}{\log Y}
\bigl(T(M)-O_B(\log M)\bigr)_+.
$$

Together with the elementary upper bound

$$
\mathcal N(M,Y)\le T(M)\pi(2Y),
$$

this confirms that, away from a small exceptional collection of centers, auxiliary averaging does not introduce another substantial obstruction.

But it does not create the missing centers.

A particularly clean sufficient statement would be

$$
\boxed{
\mathcal N(M,M^B)>0
\quad\text{for an unbounded sequence of }M.
}
\tag{10}
$$

A stronger quantitative version would be

$$
\limsup_{M\to\infty}
\frac{(\log M)^3}{M^{B+1}}\,
\mathcal N(M,M^B)>0.
$$

Either would prove ordinary twin-prime infinitude. Neither is supplied by the inspected class-number nonvanishing theorems.

Final research verdict

The strongest checked connection is the exact equivalence

$$
\boxed{
\begin{aligned}
&m-1,m+1\text{ both prime}\\
&\quad\Longleftrightarrow\
\exists\,\ell\equiv1\pmod4\text{ prime},\
\ell\nmid m^2-1,\\
&\hspace{37mm}
\mu^2(m^2-1)=1,\
h(-\ell(m^2-1))\equiv4\pmod8.
\end{aligned}
}
$$

The auxiliary prime may be bounded polynomially in $m$.

The investigation also establishes two substantive limitations:

-

The full nonvanishing discriminant family already has an unconditional positive $X/\log X$-scale asymptotic, which can be generated by repeatedly using known twin centers.

-

Exact class-number nonvanishing, squarefreeness, balanced prime factors and arbitrary fixed admissible congruence filters coexist with a much larger population containing no pair of prime factors at distance two.

The remaining missing theorem is nonvanishing modulo eight localized to the actual squarefree polynomial cofactor $m^2-1$, with $m$ unbounded. Neither global class-number distribution nor progression-level modular nonvanishing provides that localization.

I have proved the arithmetic equivalence and tested the varying-auxiliary repair, but have not established the necessary localized nonvanishing or an unconditional proof of the twin-prime conjecture.

---

## Acknowledge Proof Goal

[Original conversation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6b0511be-72ac-83ee-908d-fa223d13b529)

### Recovered response 1

I’ve read and accept the working rules and exact goal.

Sole goal: An unconditional, rigorous proof that infinitely many ordinary primes $p$ have $p+2$ prime.

Target map: Prioritize approaches that genuinely establish infinitely many gap-2 pairs, including parity-breaking sieve estimates, fixed-shift prime correlations, and rigorous arithmetic constructions. Conditional results, bounded gaps, and finite computations do not suffice.

I confirm that I will:

-

Work only on my assigned distinct mathematical lane.

-

Accept claims only after checking their supporting arguments.

-

Distinguish established results from conjectures and failed attempts.

-

Use this chat as the sole output, with minimal tools.

-

Create no files, leave existing notebooks closed, and preserve all prior work.

-

Consult public primary sources when necessary, without downloads, installations, private-data access, or external messages.

-

Change mathematical direction when an approach fails.

Rules confirmed. Ready for the mathematical assignment.

---

### Recovered response 2

The descent formulation is valid with your corrected stopping rule. I proved that every fixed generation is harmonically thin, established a stronger dichotomy for the entire generated set, and ruled out two natural methods of obtaining the necessary uniform bound.

The remaining obstruction is controlling generation growth. A complete unconditional proof of twin-prime infinitude has not emerged from this lane.

1. Multiplicative residue classes: an obstruction

Fix $B\ge5$. Let $S$ be a proposed survivor set of odd primes exceeding $B$, and let $E$ be its complement among odd primes.

Consider an even modulus $m$ and a set of reduced residue classes

$$
R\subseteq G=(\mathbb Z/m\mathbb Z)^\times.
$$

Suppose membership in $S$, for primes above $B$ coprime to $m$, is determined by membership in $R$.

The natural purely multiplicative residue certificate would require:

$$
\boxed{
\begin{gathered}
n\text{ composite},\qquad
q\mid n\Rightarrow q\in E,\\
(n-2,m)=1
\quad\Longrightarrow\quad
n-2\bmod m\notin R.
\end{gathered}}
\tag{1}
$$

This would establish the desired closure on the reduced residue classes without needing additional information about the primality of $n-2$.

Proposition. If every odd prime dividing $m$ lies outside $S$, condition (1) forces $R=\varnothing$.

Proof. Let $U$ be the multiplicative monoid modulo $m$ generated by the residues of primes in $E$, including the empty product.

First, there exists a prime in $E$ coprime to $m$. If $3\nmid m$, take $3$. Otherwise choose $j\ge2$ such that

$$
3^j\equiv1\pmod{m/3^{v_3(m)}}.
$$

Then $3^j-2$ is coprime to $m$. By (1), its residue lies outside $R$. Dirichlet's theorem therefore supplies a prime exceeding $B$ in this excluded residue class.

Using a suitable power of this excluded unit prime, every element of $U$ can be represented by a composite product of primes in $E$. Consequently,

$$
t\in U,\quad t-2\in G
\quad\Longrightarrow\quad t-2\in U.
\tag{2}
$$

Here we used Dirichlet's theorem again to ensure that every reduced class outside $R$ has a representative in $E$.

Taking $t=1$ gives $-1\in U$. Thus $U$ is closed under negation.

Now induct on positive odd integers $n$.

-

If $n=1$, its residue belongs to $U$.

-

If $n$ is coprime to $m$, the induction hypothesis gives $n-2\in U$. Negating and applying (2) gives $-n\in U$, hence $n\in U$.

-

Otherwise, some odd prime $r\mid(n,m)$ belongs to $E$. The induction hypothesis applies to $n/r$, so multiplication by $r$ gives $n\in U$.

Therefore every odd residue belongs to $U$.

For any $a\in G$, the residue $a+2$ consequently has a composite representative whose prime factors belong to $E$. Condition (1) excludes $a$ from $R$.

Hence $R=\varnothing$. $\square$

Can primes dividing the modulus escape this obstruction?

They can escape the residue argument, but only by retaining the central primality obligation.

Suppose some modulus prime belongs to $S$, and let $r_*$ be the least such prime. The preceding induction still proves that every positive odd integer below $r_*$ has its residue in $U$.

It follows from (1) that every prime below $r_*-2$ belongs to $E$.

If $r_*+2$ were composite, each of its prime divisors $q$ would satisfy

$$
q\le\frac{r_*+2}{3}<r_*-2.
$$

Thus every child of $r_*$ would lie outside $S$, violating the corrected closure condition.

Consequently,

$$
\boxed{r_*+2\text{ must be prime}.}
$$

Allowing exceptional modulus primes therefore transfers the missing proof to the least included modulus prime.

This rules out the purely residue-based certificate (1). It does not rule out periodic constructions using additional arithmetic information about actual primes.

2. Every fixed generation is extremely thin

Define

$$
A_0=\{p\le B:p\text{ is an odd prime}\}
$$

and

$$
A_{k+1}=A_k\cup
\left\{
\begin{array}{l}
p>B:p\text{ prime},\ p+2\text{ composite},\\
q\mid p+2\Rightarrow q\in A_k
\end{array}
\right\}.
$$

Write

$$
A_\infty=\bigcup_{k\ge0}A_k.
$$

The complement of $A_\infty$ is precisely the largest possible survivor set satisfying your corrected condition.

Theorem. For every fixed generation $k$ and every real $s>0$,

$$
Z_k(s):=\sum_{p\in A_k}\frac1{p^s}<\infty.
\tag{3}
$$

This is substantially stronger than harmonic thinness.

Proof. The assertion is immediate for $A_0$. Suppose it holds for $A_k$.

Let $\mathcal M_k$ be the multiplicative monoid generated by $A_k$. Its Dirichlet series converges:

$$
\sum_{n\in\mathcal M_k}n^{-s}
=
\prod_{q\in A_k}(1-q^{-s})^{-1}
<\infty.
$$

Every newly generated prime has the form $p=n-2$, where $n\in\mathcal M_k$ is odd and composite.

Such an $n$ is at least $9$, so

$$
(n-2)^{-s}\le(9/7)^s n^{-s}.
$$

By monotonicity of the generation operator, one obtains the bound

$$
\begin{aligned}
Z_{k+1}(s)\le Z_0(s)
+\left(\frac97\right)^s
\left[
\prod_{q\in A_k}(1-q^{-s})^{-1}
-1-Z_k(s)
\right].
\end{aligned}
\tag{4}
$$

The right-hand side is finite. Induction proves (3). $\square$

In particular, for every fixed $k$ and every $\varepsilon>0$,

$$
\boxed{
\#(A_k\cap[1,x])
=O_{B,k,\varepsilon}(x^\varepsilon).
}
\tag{5}
$$

Every fixed generation therefore contains a vanishing proportion of the primes, with a much stronger bound than ordinary density zero.

The problem is that the constant in (5) depends on $k$.

3. A sharp generation-growth dichotomy

Write

$$
H_k=\sum_{p\in A_k}\frac1p.
$$

Suppose, temporarily, that there are no twin-prime starters exceeding $B$.

Every prime $p>B$ then has composite $p+2$, whose prime factors satisfy

$$
q-1\le\frac{p-1}{3}.
$$

Define

$$
Y_k=1+3^k(B-1).
$$

By induction,

$$
\boxed{\{p\le Y_k:p\text{ odd prime}\}\subseteq A_k.}
\tag{6}
$$

Indeed, if $p\le Y_{k+1}=3Y_k-2$, all prime factors of its composite neighbor $p+2$ are at most $Y_k$.

Mertens' theorem for primes now implies

$$
H_k\ge\log\log Y_k+M_{\rm odd}+o(1),
$$

where $M_{\rm odd}$ is the odd-prime Mertens constant. Hence

$$
\boxed{
H_k\ge
\log k+\log\log3+M_{\rm odd}+o(1).
}
\tag{7}
$$

This proves that a uniform harmonic bound is more than is necessary.

A sufficient generation-growth estimate is merely

$$
\boxed{
\liminf_{k\to\infty}\frac{H_k}{\log k}<1.
}
\tag{8}
$$

This would force a twin-prime pair above the arbitrary threshold $B$.

The converse: one omitted prime forces uniform harmonic thinness

There is also a rigorous converse.

Suppose $q\notin A_\infty$. Every sufficiently large prime

$$
r\equiv-2\pmod q
$$

must also lie outside $A_\infty$, since $q\mid r+2$.

Thus, if $p>B$ belongs to $A_\infty$, its neighbor $p+2$ cannot be divisible by any sufficiently large prime in the progression $-2\bmod q$.

This imposes an additional forbidden residue on a positive proportion of prime moduli.

The resulting counting estimate can be established directly by truncated inclusion-exclusion. At each small prime $r$, forbid the residue $0$ for $p$, and additionally forbid $-2$ whenever $r$ is in the excluded progression.

Let $\nu(r)$ be the number of forbidden residues. Mertens' theorem in the fixed progression gives

$$
\prod_{r\le z}
\left(1-\frac{\nu(r)}r\right)
\ll_q
(\log z)^{-1-\delta},
\qquad
\delta=\frac1{q-1}.
\tag{9}
$$

Choose a fixed

$$
\frac1{1+\delta}<a<1,
\qquad
z=\exp((\log x)^a).
$$

Truncate inclusion-exclusion at an even order $K$ of sufficiently large constant multiple of $\log\log x$.

The total CRT counting error is at most

$$
(K+1)(2z)^K=x^{o(1)}.
$$

The tail of the principal inclusion-exclusion expansion is bounded by

$$
\sum_{j>K}\frac1{j!}
\left(\sum_{r\le z}\frac{\nu(r)}r\right)^j
\ll(\log x)^{-10},
$$

by choosing the constant in $K$ sufficiently large.

Consequently, on dyadic intervals,

$$
\#\bigl(A_\infty\cap(x/2,x]\bigr)
\ll_{B,q}
\frac{x}{(\log x)^{a(1+\delta)}}.
\tag{10}
$$

Since $a(1+\delta)>1$, summing over dyadic intervals proves

$$
\sum_{p\in A_\infty}\frac1p<\infty.
\tag{11}
$$

Combining these arguments establishes the following equivalence.

For every fixed $B\ge5$, the four statements are equivalent:

-

There exists a twin-prime starter exceeding $B$.

-

$A_\infty$ omits an odd prime.

-

$\sup_k H_k<\infty$.

-

$\displaystyle\liminf_{k\to\infty}H_k/\log k<1.$

This is the strongest verified result from this descent lane. The union is either harmonically summable or has generation growth at least logarithmic.

The argument establishing (11), however, requires a genuinely omitted prime. Its constant depends on that prime, so it cannot be used to establish properness without further arithmetic input.

4. Why the elementary Euler-product recurrence does not close

Equation (4) might suggest finding an invariant upper bound $M$ for $H_k$.

Even the optimistically reduced scalar majorant

$$
H_0+e^M-1-M
$$

cannot certify such a bound for $B\ge5$.

Indeed, a fixed-point majorization would require

$$
H_0+e^M-1-M\le M.
$$

But

$$
e^M-1-M\ge\frac{M^2}{2},
$$

so necessarily

$$
H_0\le M-\frac{M^2}{2}\le\frac12.
$$

Already

$$
H_0\ge\frac13+\frac15=\frac8{15}>\frac12.
$$

Thus the unrestricted multiplicative-monoid estimate cannot supply an invariant harmonic bound.

This is a failure of that majorant, not a lower bound on the actual generation growth. A successful argument would have to exploit the additional restriction that $n-2$ is prime.

5. A convergent-measure and mass-transport attempt

For a composite neighbor $p+2$, assign each prime child $q$ the transition weight

$$
P(p,q)=
\frac{v_q(p+2)\log q}{\log(p+2)}.
$$

The multiplicities are retained, and

$$
\sum_qP(p,q)=1.
$$

Kill the transition at primes at most $B$ and at successful twin-prime starters.

Use the harmonic measure $\mu(p)=1/p$, and define the incoming mass

$$
I(q)=\sum_p\frac{P(p,q)}p.
$$

For each fixed $q$, this column converges. To verify this, split into dyadic ranges $p\asymp X$ and prime powers $q^j\mid p+2$. Brun–Titchmarsh handles $q^j\le\sqrt X$, contributing $O_q((\log X)^{-2})$ per dyad. Integer counting handles the remaining powers with a summable error.

Every generated prime outside $A_0$ sends all of its mass into the preceding generation. Therefore

$$
H_{k+1}-H_0
\le\sum_{q\in A_k}I(q).
\tag{12}
$$

A uniform column contraction

$$
I(q)\le\frac{1-\eta}{q},
\qquad q>B,
\tag{13}
$$

for some fixed $\eta>0$, would prove a uniform harmonic bound through (12).

However, (13) is impossible.

For any $X>B$, all children of a composite-neighbor prime $p\le X$ lie below $X$. Thus

$$
\sum_{q\le X}I(q)
\ge
\sum_{\substack{B<p\le X\\p+2\ {\rm composite}}}\frac1p.
\tag{14}
$$

By Brun's convergence theorem for twin-prime reciprocals, the right-hand side is

$$
\log\log X-O_B(1).
$$

Under (13), the left-hand side would instead be at most

$$
(1-\eta)\log\log X+O_B(1),
$$

a contradiction.

The same obstruction applies to any choice of transition probabilities supported on the smaller prime children, provided their sum is one at every composite-neighbor prime.

Even a nonuniform contraction with nonnegative deficits whose total diverges is impossible, since (14) gives

$$
\sum_{q\le X}\left(\frac1q-I(q)\right)
\le H_0+
\sum_{\substack{p>B\\p+2\ {\rm prime}}}\frac1p
=O_B(1).
$$

For a summable positive measure $w$, the exact conservation identity is

$$
\begin{aligned}
&\sum_{q>B}\bigl(w(q)-I_w(q)\bigr)
-\sum_{q\le B}I_w(q)\\
&\qquad=
\sum_{\substack{p>B\\p+2\ {\rm prime}}}w(p),
\end{aligned}
$$

where $I_w(q)=\sum_p w(p)P(p,q)$.

Consequently, obtaining a nonnegative incoming-mass deficit is insufficient by itself: the mass entering the initial finite set must also be accounted for.

6. Size-dependent sets and the Pratt-tree control

A natural size-dependent candidate uses the first generation $d(p)$ containing $p$, with $d(p)=\infty$ for omitted primes.

For generated primes, descent gives the unconditional bound

$$
d(p)\le
\left\lceil
\frac{\log((p-1)/(B-1))}{\log3}
\right\rceil,
\qquad p>B.
\tag{15}
$$

Thus defining a survivor set by exceeding this height bound simply recovers $A_\infty^c$. It supplies no independent construction of a survivor.

There is also a decisive control using Pratt trees for $p-1$.

Start with $C_0=\{2,3\}$, and adjoin every prime $p>3$ for which all prime divisors of $p-1$ belong to the preceding generation.

Exactly the Euler-product argument of Section 2 proves

$$
\sum_{p\in C_k}p^{-s}<\infty
$$

for every fixed $k$ and every $s>0$.

Nevertheless, strong induction on primes proves

$$
\bigcup_{k\ge0}C_k=\{\text{all primes}\}.
$$

Therefore fixed-generation thinness, even simultaneously at every positive Dirichlet exponent, does not imply that the union is thin.

The distinction in the twin-prime problem is the possibility of a successful terminal prime above $B$. The Pratt-tree analogy does not establish the existence of such a terminal.

Precise surviving research target

The descent approach reduces the full problem to a specific uniform estimate on recursively generated primes:

$$
\boxed{
\liminf_{k\to\infty}
\frac{\displaystyle\sum_{p\in A_k}p^{-1}}
{\log k}<1
\qquad\text{for every fixed }B\ge5.
}
$$

For example, an eventual increment bound

$$
H_{k+1}-H_k\le\frac{c}{k+1},
\qquad c<1,
$$

would suffice.

Unlike the unrestricted Euler-product majorization and the universal mass-transport contraction, this estimate concerns the actual successive generations. Neither of the proved obstructions rules it out.

It remains unproved. Establishing it for arbitrary $B$ would complete the unconditional twin-prime proof by descent.

---

### Recovered response 3

1. Exact frontier decomposition

Write $G_k$ for the cumulative generated set, $F_k=G_k\setminus G_{k-1}$ for its new frontier, and

$$
H_k=\sum_{p\in G_k}\frac1p,\qquad
h_k=H_k-H_{k-1}.
$$

For any set of primes $A$, let $\mathcal M(A)$ be the integers whose prime factors all belong to $A$, including $1$.

Every prime in $F_{k+1}$, for $k\ge1$, has the unique decomposition

$$
p+2=ab,\qquad
a\in\mathcal M(G_{k-1}),\quad
b\in\mathcal M(F_k),\quad b>1.
$$

The product $ab$ must be composite, and $p>B$. This separates the frontier into two genuinely different contributions:

-

Single frontier factor: $b=q\in F_k$, with $a>1$.

-

Multiple frontier factors: $\Omega(b)\ge2$, including repeated copies of the same prime.

In particular, the case $a=1,\ b=q$ is excluded. It is a successful twin-prime terminal, not a generated prime.

Put

$$
E_k=\prod_{q\in G_k}(1-q^{-1})^{-1},
\qquad
V_k=\prod_{q\in F_k}(1-q^{-1})^{-1}.
$$

The multiple-frontier contribution satisfies the unconditional bound

$$
h_{k+1}^{(\ge2)}
\le \frac97 E_{k-1}(V_k-1-h_k).
\tag{1}
$$

If $F_k$ is nonempty and $L_k=\min F_k$, this gives

$$
h_{k+1}^{(\ge2)}
\ll e^{H_k}\left(h_k^2+\frac{h_k}{L_k}\right).
\tag{2}
$$

The second term explicitly retains repeated prime factors. The elementary descent inequality gives

$$
L_k>1+3^{k-1}(B-1).
$$

At the critical growth regime $H_k=\log k+O(1)$, $h_k=O(1/k)$, bound (2) is only $O(1/k)$. Thus treating multiple frontier factors by the unrestricted Euler product consumes an entire harmonic-scale increment. It cannot simply be declared negligible.

2. The actual two-generation sieve

Consider the single-frontier contribution

$$
p=mq-2,\qquad q\in F_k,\qquad
1<m\in\mathcal M(G_{k-1}).
$$

Put $A=G_{k-1}$. Since $q$ is generated, every prime factor of $q+2$ belongs to $A$.

For a sieving prime $\ell\ge5$, the forbidden residues of $q$ are exactly

$$
\begin{aligned}
q&\equiv0\pmod\ell,\\
q&\equiv2m^{-1}\pmod\ell
&&(\ell\nmid m),\\
q&\equiv-2\pmod\ell
&&(\ell\notin A).
\end{aligned}
$$

Consequently, the number of distinct forbidden roots is

Condition
 |
Forbidden roots
 |

$\ell\in A,\ \ell\mid m$
 |
1
 |

$\ell\in A,\ \ell\nmid m$
 |
2
 |

$\ell\notin A,\ \ell\mid m+1$
 |
2
 |

$\ell\notin A,\ \ell\nmid m+1$
 |
3
 |

Here $\ell\notin A$ implies $\ell\nmid m$, because the cofactor is supported entirely on $A$.

The coincidence at $\ell\mid m+1$ is essential. Counting three distinct roots there would produce an invalid extra saving. The primes $2,3$ are treated separately; $3\in A$, so no forbidden third root can be imposed at $3$.

Define

$$
D_3(n)=
\prod_{\substack{\ell\mid n\\\ell\ge5}}
\left(1+\frac1{\ell-3}\right).
$$

The standard upper-bound sieve, with uniform CRT remainder bounds, now gives

$$
\#\{Q<q\le2Q:
q\in F_k,\ mq-2\text{ prime}\}
\ll
\frac{Qe^{H_{k-1}}D_3(m(m+1))}
{(\log Q)^3}.
\tag{3}
$$

This is a genuine use of the additional restrictions on $q+2$, rather than treating $q$ as an arbitrary prime. The applicable sieve framework is Ford's upper-bound sieve and fundamental lemma.

ford126.web.illinois.edu+1

The exceptional-factor cost can be averaged without an additional logarithmic loss:

$$
\sum_{m\le M}\frac{D_3(m(m+1))}{m}
\ll \log(2M).
\tag{4}
$$

Indeed, expand $D_3$ over squarefree divisors. The congruence $d\mid m(m+1)$ has $2^{\omega(d)}$ roots modulo $d$. The principal Euler product converges, since each nonconstant local contribution is $O(\ell^{-2})$. The accumulated floor error is $O((\log M)^C)$, and partial summation gives (4).

Summing (3) over the child $q\ge L_k$ and the exact cofactors $m\le M$, we obtain

$$
h_{k+1}^{(1,\ m\le M)}
\ll
\frac{e^{H_{k-1}}\log(2M)}
{(\log L_k)^2}.
\tag{5}
$$

For the complementary cofactors $m>M$, reverse the sieve variable. Fix $q\in F_k$, and sieve $m$ for both $qm-2$ prime and membership in $\mathcal M(A)$. At each prime outside $A$, the residue $m=0$ is forbidden, in addition to the primality root when it exists.

This gives

$$
\sum_{\substack{m>M,\ m\in\mathcal M(A)\\
qm-2\ {\rm prime}}}
\frac1{qm-2}
\ll
\frac{e^{H_{k-1}}}{q\log M}.
\tag{6}
$$

Combining both parts,

$$
\boxed{
h_{k+1}^{(1)}
\ll e^{H_{k-1}}
\left(
\frac{\log(2M)}{(\log L_k)^2}
+\frac{h_k}{\log M}
\right).
}
\tag{7}
$$

Optimizing the cutoff, when $\sqrt{h_k}\log L_k\ge1$, yields

$$
h_{k+1}^{(1)}
\ll
\frac{e^{H_{k-1}}\sqrt{h_k}}
{\log L_k}.
\tag{8}
$$

This improvement does not yet give contraction. At $H_{k-1}=\log k+O(1)$, $h_k\asymp1/k$, and using the guaranteed $\log L_k\gg_B k$, its upper allowance is $O(k^{-1/2})$, rather than the needed $O(k^{-1})$ with a sufficiently small coefficient.

Thus the additional forbidden root from $q+2$ produces real arithmetic savings, but the elementary small/large-cofactor split cannot certify the necessary sign at the critical scale.

3. A distinct repair: bilinear sieving of multiple frontier factors

The unrestricted bound (2) loses too much because it ignores primality of the parent after selecting two frontier factors. A multiplicative large-sieve argument recovers a logarithmic saving, even for arbitrary subsets of the prime children.

Bilinear lemma. Let $\mathcal Q,\mathcal R$ be arbitrary sets of primes in $(Q,2Q]$ and $(R,2R]$, respectively. Put $M=\min(Q,R)$, and let $a$ be any positive odd integer. For every fixed $A>0$,

$$
\begin{aligned}
&\#\{(q,r)\in\mathcal Q\times\mathcal R:
aqr-2\text{ prime}\}\\
&\quad\ll_A
D_2(a)|\mathcal Q||\mathcal R|
\frac{\log\log M}{\log M}
+\frac{QR}{(\log M)^A},
\end{aligned}
\tag{9}
$$

where

$$
D_2(a)=\prod_{\substack{\ell\mid a\\\ell>2}}
\left(1+\frac1{\ell-2}\right).
$$

Importantly, the estimate is uniform in $a$. The cofactor need not be bounded in size.

Proof

Take a sieve level $D=M^{1/4}$, and sieve using primes

$$
(\log M)^C<\ell\le M^{1/16},
\qquad \ell\nmid a,
$$

with $C$ sufficiently large in terms of $A$.

For a squarefree sieve modulus $d\le D$, the divisibility condition is

$$
qr\equiv2a^{-1}\pmod d.
$$

Both prime variables are coprime to $d$, because they exceed $D$. Character orthogonality gives the principal term

$$
\frac{|\mathcal Q||\mathcal R|}{\varphi(d)}
$$

and a remainder $r_d$ involving nonprincipal characters.

Every such character has primitive conductor exceeding $(\log M)^C$. Grouping by primitive conductor $f$, and using

$$
\sum_{\substack{d\le D\\f\mid d}}
\frac1{\varphi(d)}
\ll\frac{\log D}{\varphi(f)},
$$

reduces the remainder estimate to dyadic conductor sums.

By Cauchy–Schwarz and the multiplicative large sieve,

$$
\begin{aligned}
&\sum_{f\asymp T}\frac1{\varphi(f)}
\sum_{\chi\bmod f}^{*}
\left|\sum_{q\in\mathcal Q}\chi(q)\right|
\left|\sum_{r\in\mathcal R}\chi(r)\right|\\
&\quad\ll
\frac{\sqrt{(Q+T^2)(R+T^2)
|\mathcal Q||\mathcal R|}}{T}.
\end{aligned}
$$

Since $T^2\le D^2=M^{1/2}$, this is $O(QR/T)$. The multiplicative inequality here follows from the additive large sieve by primitive Gauss sums and character orthogonality; the underlying primary reference is Montgomery and Vaughan's The Large Sieve.

doi.org

Summing conductors therefore gives

$$
\sum_{d\le D}|r_d|
\ll\frac{QR\log D}{(\log M)^C},
$$

where the sum is restricted to the selected sieve moduli.

The principal upper-sieve product is

$$
\prod_{\substack{(\log M)^C<\ell\le M^{1/16}\\
\ell\nmid a}}
\left(1-\frac1{\ell-1}\right)
\ll_A
D_2(a)\frac{\log\log M}{\log M}.
$$

Choosing $C>A+2$ proves (9). No Siegel–Walfisz assumption on either frontier subset is needed. $\square$

Application to the actual recursion

If $p+2$ contains at least two frontier prime factors, counted with multiplicity, write

$$
p+2=aqr,\qquad q,r\in F_k,\quad
a\in\mathcal M(G_k).
$$

All such parents are covered by the ordered pair sum. Repeated factors $q=r$ are included; no squarefree reduction is made.

For an arbitrary truncation $T$, the original one-variable sieve gives

$$
\sum_{\substack{q\in F_k\\q>T}}\frac1q
\ll\frac{e^{H_{k-1}}}{\log T}.
$$

For $q,r\le T$, apply (9) on dyadic boxes and sum over the actual multiplicative monoid of cofactors. The exceptional-factor sum is harmless:

$$
\sum_{a\in\mathcal M(G_k)}\frac{D_2(a)}a
\ll e^{H_k}.
$$

Indeed, its Euler product differs from $E_k$ by an absolutely bounded factor.

Using $\log L_k\gg_B k$ yields the following unconditional bound, for $k$ sufficiently large:

$$
\boxed{
h_{k+1}^{(\ge2)}
\ll_{A,B}e^{H_k}
\left[
\frac{h_k^2\log k}{k}
+\frac{(\log T)^2}{k^A}
+\frac{h_ke^{H_{k-1}}}{\log T}
\right].
}
\tag{10}
$$

This is stronger than (2) in an important regime.

Suppose one could independently establish the near-critical bounds

$$
H_k\le\log k+O_B(1),
\qquad h_k=O_B(k^{-1}).
\tag{11}
$$

Take $T=\exp(k^4)$ and $A=12$. Equation (10) then gives

$$
h_{k+1}^{(\ge2)}
\ll_B\frac{\log k}{k^2}.
$$

Consequently,

$$
\boxed{
\sum_{k\ge1}h_{k+1}^{(\ge2)}<\infty
\quad\text{under (11).}
}
\tag{12}
$$

This is a genuine improvement in the arithmetic estimate. At the critical growth scale, the multiple-frontier contribution is summable rather than merely $O(1/k)$.

The hypotheses (11), however, have not been established for the actual recursion. They are not being assumed unconditionally.

4. Removing small cofactors cumulatively

There is a separate unconditional saving which does not require (11).

Fix $0<\alpha<1$. Consider every prime pair

$$
q,\ mq-2,
\qquad
m\ge3,\quad m\text{ odd},
$$

satisfying

$$
\log m\le(\log q)^\alpha.
$$

Then

$$
\boxed{
\sum_{\substack{q,\ mq-2\ {\rm prime}\\
m\ge3\ {\rm odd}\\
\log m\le(\log q)^\alpha}}
\frac1{mq-2}<\infty.
}
\tag{13}
$$

To prove this, fix $m$. The two-linear-form upper sieve and partial summation give

$$
\sum_{\substack{q\ge U\\q,\ mq-2\ {\rm prime}}}
\frac1{mq-2}
\ll\frac{D_2(m)}{m\log U}.
$$

The condition in (13) permits

$$
U=\exp((\log m)^{1/\alpha}).
$$

Thus the complete sum is bounded by a constant multiple of

$$
\sum_{m\ge3}
\frac{D_2(m)}
{m(\log m)^{1/\alpha}},
$$

which converges because $1/\alpha>1$ and

$$
\sum_{m\le x}D_2(m)\ll x.
$$

The latter bound follows directly by divisor expansion.

In particular, all single-frontier transitions having subpower logarithmic cofactors carry only finite total harmonic mass over every generation combined.

The same argument proves that transitions whose cofactors use only any fixed finite set of primes are summable. This includes arbitrary powers and products of the base primes, not just a bounded list of small numerical cofactors.

A stronger cumulative inequality

Let $0<\eta\le1$. For generations $1\le k\le K$, separate single-frontier transitions according to $m\le q^\eta$ or $m>q^\eta$.

For the first part, split the child variable at

$$
Z=\exp(e^{H_{K-1}}).
$$

Below $Z$, the ordinary two-form sieve bounds the harmonic contribution of a dyadic child interval by $O(\eta/\log Q)$.

Above $Z$, use the extra restrictions on $q+2$ from (3), with the larger set $G_{K-1}$. The corresponding contribution is

$$
O\left(\frac{\eta e^{H_{K-1}}}{(\log Q)^2}\right).
$$

Summing both ranges proves

$$
\sum_{k=1}^K
h_{k+1}^{(1,\ m\le q^\eta)}
\ll \eta(1+H_{K-1}).
\tag{14}
$$

The implied constant is independent of $K,\eta$.

For $m>q^\eta$, use (6) with a child-dependent cutoff. Define

$$
\mathcal L_K=
\sum_{k=1}^K e^{H_{k-1}}
\sum_{q\in F_k}\frac1{q\log q}.
$$

Then the entire single-frontier contribution satisfies

$$
\boxed{
\sum_{k=1}^K h_{k+1}^{(1)}
\ll
\eta(1+H_{K-1})
+\frac{\mathcal L_K}{\eta}.
}
\tag{15}
$$

This incorporates both the arithmetic of consecutive frontiers and their actual numerical sizes.

It permits the contribution of relatively small cofactors to be made an arbitrarily small proportion of the cumulative harmonic mass. What remains is the size-weighted frontier quantity $\mathcal L_K$.

5. Why numerical growth of the frontier does not automatically repair (15)

One might hope that $\mathcal L_K=o(H_K)$ simply because successive frontier primes become large. That inference is unjustified.

In fact, under the hypothetical absence of twins above $B$, one can prove

$$
\mathcal L_K\gg_B\log K,
\tag{16}
$$

using the given bounded-increment estimate $h_k\le C$.

Proof. Under the no-twin hypothesis, every odd prime at most

$$
Y_K=1+3^K(B-1)
$$

belongs to $G_K$.

Order the primes in $(B,Y_K]$ by their first generation of appearance. Within each generation choose any ordering. For such a prime $q$, let $s(q)$ be the sum of reciprocals of the preceding primes in this ordering.

If $q\in F_k$, then

$$
s(q)\le H_{k-1}-H_0+C.
$$

Consequently,

$$
\mathcal L_K
\ge e^{H_0-C}
\sum_{B<q\le Y_K}
\frac{e^{s(q)}}{q\log q}.
$$

Associate to each prime an interval of length $1/q$ beginning at $s(q)$. The resulting expression is comparable, with absolute constants, to the integral of $e^t/\log q$ over these consecutive intervals.

By the rearrangement inequality, that integral is minimized by ordering the primes numerically increasingly: the decreasing weights $1/\log q$ are paired with the increasing function $e^t$.

In that ordering, Mertens' theorem gives

$$
s(q)=\log\log q+O_B(1),
$$

so $e^{s(q)}/\log q\gg_B1$. Hence

$$
\mathcal L_K
\gg_B\sum_{B<q\le Y_K}\frac1q
\gg_B\log K.
$$

$\square$

Thus, under the no-twin alternative and the near-critical regime $H_K=\log K+O(1)$, the remaining quantity in (15) is not negligible relative to $H_K$.

This does not preclude a stronger arithmetic estimate with favorable constants. It establishes why the coarse numerical growth of the frontier cannot supply the missing contraction by itself.

6. Exact cumulative check on local exclusion coefficients

There is also a precise obstruction to obtaining contraction simply by multiplying the additional local exclusions at every generation.

Consider an odd sieving prime $\ell$, an allowed cofactor prime set $A$, and a child residue $q\not\equiv0\pmod\ell$.

In the ordinary local harmonic model for the cofactor $m$:

-

If $\ell\in A$, include every valuation $e\ge0$ with normalized weight $(1-1/\ell)\ell^{-e}$, distributing units uniformly.

-

If $\ell\notin A$, only valuation zero is allowed, with units distributed uniformly.

These are explicitly defined local comparison laws, not assumptions about the distribution of the actual frontier.

For an allowed prime $\ell$, the resulting residue of $m$ is uniform over all $\ell$ residues. Hence the probability that $mq-2$ survives is

$$
1-\frac1\ell.
$$

For an excluded prime, it is

$$
1-\frac1{\ell-1}.
$$

After normalization by ordinary primality survival $1-1/\ell$, the exact local coefficient is therefore

$$
c_\ell(A)=
\begin{cases}
1,&\ell\in A,\\[2mm]
1-\dfrac1{(\ell-1)^2},&\ell\notin A.
\end{cases}
\tag{17}
$$

This calculation retains all powers of the small prime. In particular, the base prime $3$ does not create an extra normalized contraction.

For consecutive single-frontier edges

$$
q=nr-2,\qquad p=mq-2,
$$

the local survival coefficients multiply in this comparison law, because each new unit child permutes the allowed multiplier residues. Root coincidences are thus accounted for by conditioning rather than treating the forbidden roots as independent.

Under the hypothetical absence of twins above $B$, the old sets contain every odd prime up to $Y_j$. Therefore

$$
\begin{aligned}
-\log\prod_{j=0}^{K}
\prod_{\substack{\ell>2\\\ell\notin G_j}}
c_\ell(G_j)
&\ll\sum_{j=0}^{K}\sum_{\ell>Y_j}\frac1{\ell^2}\\
&\ll\sum_{j=0}^\infty\frac1{Y_j}\\
&\ll\frac1B.
\end{aligned}
$$

Consequently, uniformly in depth,

$$
\boxed{
\prod_{j=0}^{K}
\prod_{\substack{\ell>2\\\ell\notin G_j}}
c_\ell(G_j)
\ge \exp(-C/B)>0.
}
\tag{18}
$$

The cumulative normalized local defect is finite, not divergent.

Thus multiplying these averaged local exclusion coefficients alone cannot give a contraction whose product tends to zero. An argument involving the actual joint distribution of the frontier and its cofactors would have to supply additional information.

7. A critical coefficient calculation for single-frontier propagation

The remaining single-frontier problem has a particularly revealing ordinary comparison.

Retain all odd primes up to $y$ as allowed cofactor factors, including their powers. Consider the comparison coefficient

$$
C_y(q)=
2\sum_{\substack{m>1,\ m\ {\rm odd}\\
P^+(m)\le y}}
\frac1{m\log(mq)}.
\tag{19}
$$

This inserts the ordinary prime-frequency weight $2/\log(mq)$ among odd integers. It is not asserted to bound actual primality of $mq-2$.

For fixed $\beta>0$, suppose

$$
\frac{\log q}{\log y}\longrightarrow\beta.
$$

Then

$$
C_y(q)\longrightarrow
e^\gamma\int_0^\infty e^{-\beta t}f(t)\,dt,
\tag{20}
$$

where

$$
f(t)=
\exp\left(\int_0^1
\frac{e^{-tx}-1}{x}\,dx\right).
$$

To verify (20), use the integral representation of $1/\log(mq)$ and the exact Euler product

$$
\sum_{\substack{m\ {\rm odd}\\P^+(m)\le y}}
m^{-1-s}
=
\prod_{3\le\ell\le y}
(1-\ell^{-1-s})^{-1}.
$$

After substituting $s=t/\log y$, Mertens' theorem and partial summation give

$$
\frac1{\log y}
\prod_{3\le\ell\le y}
(1-\ell^{-1-t/\log y})^{-1}
\longrightarrow \frac{e^\gamma}{2}f(t).
$$

The prime-power terms in the ratio of the Euler products converge absolutely, and dominated convergence applies because $\beta>0$. The excluded unit $m=1$ costs exactly $2/\log q$.

Now

$$
(tf(t))'=e^{-t}f(t),
\qquad
\lim_{t\to\infty}tf(t)=e^{-\gamma}.
$$

It follows that

$$
e^\gamma\int_0^\infty e^{-t}f(t)\,dt=1.
$$

Therefore the comparison coefficient has the exact critical value

$$
\boxed{
\lim_{\log q/\log y\to1}C_y(q)=1.
}
\tag{21}
$$

For $\beta>1$, the limiting coefficient is strictly below one; for $0<\beta<1$, it is strictly above one.

This reveals the difficulty of the proposed single-frontier contraction. At comparable logarithmic scales, even the ordinary prime-frequency comparison is neutral at leading order. Extra old primes increase the positive cofactor comparison, while obtaining a strict arithmetic saving requires more than replacing prime counts by ordinary local densities.

No actual frontier distribution near this critical scale has been presumed in this calculation.

Surviving conclusion

The strongest new result is (10): bilinear large-sieve control of the multiple-frontier contribution, uniform in the remaining cofactor and retaining repeated prime factors. In the near-critical regime (11), this contribution becomes summable.

The single-frontier contribution remains the decisive obstacle. Its exact remaining form is

$$
\sum_{q\in F_k}
\sum_{\substack{m>1\\m\in\mathcal M(G_{k-1})}}
\frac{\mathbf1_{\{mq-2\ {\rm prime}\}}}{mq-2}.
$$

We have now obtained a cumulative summable removal of sufficiently small cofactors, a tunable cumulative bound for relatively small cofactors, and a precise calculation showing why normalized local exclusions do not by themselves accumulate into a sufficient defect.

The most valuable next mathematical attack is a relative, frontier-sensitive upper bound on the surviving single-frontier sum, particularly where the logarithmic size of the child is comparable to the effective logarithmic scale of the older cofactor monoid. An absolute upper sieve loses the coefficient precisely where contraction is required.

The arithmetic developed here narrows that obligation, but does not establish it. A twin-prime starter above arbitrary $B$ has not yet been proved to exist.

---

## Twin Prime Proof Plan

[Original conversation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6b031ca6-ca70-83e8-ac1b-3b25967b0674)

### Recovered response 1

1. The inverse transfer leaves exactly one undetermined signed correlation

I reconstructed the lag-two Fourier projection using Lee’s plus/minus setup and the prime–mollifier identities established in this chat. The underlying paper proves a prime-pair asymptotic conditional on a uniform two-over-two zeta-ratios formula, not from the Fourier projection alone.

arxiv.cnoctave.top

Let

$$
P(n)=\log n\,\mathbf1_{\{n\text{ prime}\}},\qquad
a_D(n)=\sum_{\substack{d\mid n\\d\le D}}\mu(d)\log(n/d),
\qquad C_D(n)=a_D(n)-P(n).
$$

Take $D=x^\alpha$, $0<\alpha<1/2$, and let $\mathcal B_x(f,g)$ be the symmetric signed lag-two form, with Lee’s nonnegative gap kernel $K_x(n)\asymp x^{-1}$ on the chosen support.

Define

$$
T_x=\mathcal B_x(P,P),\qquad
c_W=2C_2\int_0^\infty
\frac{W(u)^2}{u}H(2/u-2)\,du>0.
$$

The short-divisor calculation and Bombieri–Vinogradov give

$$
\mathcal B_x(a_D,a_D)=c_W+o(1),
\qquad
\mathcal B_x(P,a_D)=c_W+o(1).
\tag{1}
$$

Because $a_D(p)=P(p)$ for every prime in the support, $C_D$ vanishes identically on primes. Expanding (1) therefore yields

$$
\boxed{\mathcal B_x(P,C_D)=c_W-T_x+o(1)}
\tag{2}
$$

and

$$
\boxed{
\mathcal B_x(C_D,C_D)=T_x-c_W+o(1).
}
\tag{3}
$$

The second quantity is supported only on composite–composite pairs. No prime–composite or prime-power contribution is hidden in it.

Under finite twin support, $T_x=0$ for every sufficiently large $x$. Hence the arithmetic that has actually been evaluated permits

$$
\boxed{
\mathcal B_x(C_D,C_D)=-c_W+o(1).
}
\tag{4}
$$

The critical question is whether there is an independent inequality excluding this negative value. The mixed-transfer calculation alone gives none.

2. A stronger obstruction: every fixed short reciprocal-mollifier length gives the same residual

I tested whether a second mollifier piece, or a change of length, could improve the composite–composite sign.

Take two fixed exponents

$$
0<\alpha,\beta<\tfrac12,\qquad
D_1=x^\alpha,\quad D_2=x^\beta.
$$

Because $D_1D_2=o(x)$, the two-divisor CRT calculation still applies. The one-prime Bombieri–Vinogradov calculation also applies separately to both lengths. Consequently,

$$
\begin{aligned}
\mathcal B_x(a_{D_1},a_{D_2})&=c_W+o(1),\\
\mathcal B_x(P,a_{D_1})&=c_W+o(1),\\
\mathcal B_x(P,a_{D_2})&=c_W+o(1).
\end{aligned}
$$

Expanding with $C_{D_i}=a_{D_i}-P$ gives the stronger cross-length identity

$$
\boxed{
\mathcal B_x(C_{D_1},C_{D_2})
=T_x-c_W+o(1).
}
\tag{5}
$$

This has two immediate consequences.

If $V=a_{D_2}-a_{D_1}$ is an added divisor band below the square-root threshold, then

$$
\boxed{
\mathcal B_x(V,V)=o(1),
\qquad
\mathcal B_x(C_{D_1},V)=o(1).
}
\tag{6}
$$

Likewise, for any fixed finite linear combination

$$
a=\sum_{j=1}^J w_j a_{x^{\alpha_j}},
\qquad 0<\alpha_j<\tfrac12,\quad\sum_jw_j=1,
$$

we still have

$$
\boxed{
\mathcal B_x(a-P,a-P)=T_x-c_W+o(1).
}
\tag{7}
$$

So neither varying the length nor using two bounded-coefficient short pieces changes the leading signed error. Their added divisor bands are asymptotically null for this lag-two bilinear form.

This is an unconditional invariance statement for fixed lengths; it does not cover arbitrarily growing coefficients or two long pieces whose length product reaches $x$.

The conclusion is stronger than a failure of Cauchy–Schwarz: within the whole short-mollifier range accessible to the existing divisor estimates, the missing residual has the same leading value.

3. Its positive norms are too large to recover that value by Cauchy–Schwarz

This obstruction can be quantified independently of the twin-prime hypothesis.

Choose $0<\beta<\beta+\delta<\min(\alpha,1/2)$. Consider distinct semiprimes

$$
n=rs\asymp x,\qquad
x^\beta<r<x^{\beta+\delta},\quad s\asymp x/r,
$$

with $r,s$ prime.

Then $r<D<s$, and exactly

$$
a_D(rs)=\log r,\qquad C_D(rs)=\log r.
$$

The prime number theorem gives $\gg_{\alpha,W}x/\log x$ such semiprimes in a subinterval on which $W$ is nonzero. Hence

$$
\boxed{
\sum_n\frac{W(n/x)^2C_D(n)^2}{n}
\gg_{\alpha,W}\log x.
}
\tag{8}
$$

In Lee's plus/minus norms, their sum retains the diagonal and therefore has size at least

$$
I_+(C_D)+I_-(C_D)\gg T\log x.
$$

But the signed difference we must determine has size $O(T)$.

Thus estimating the two positive norms separately would require cancellation to relative precision better than $1/\log x$ in their difference. The ordinary mean-value theorem or a bound on either norm does not provide that information.

There are also genuine composite–composite pairs with negative contributions. For example, with $D=6$,

$$
285=3\cdot5\cdot19,\qquad287=7\cdot41,
$$

and

$$
a_6(285)=-\log19,\qquad a_6(287)=\log287.
$$

Their product is negative. This is a finite sign check, not an asymptotic lower bound, but it rules out the proposed pointwise positivity of the complete composite residual.

4. Combining every rough and nonrough composite term removes the apparent positive margin

I also tested the strongest available elementary positivity: retaining every pair in which both composites are $D$-rough.

Set

$$
H_D(n)=\log n\,\mathbf1_{\{P^-(n)>D\}},\qquad
L_D(n)=a_D(n)-H_D(n).
$$

Every prime in the support is $D$-rough. Consequently,

$$
C_D=(H_D-P)+L_D.
$$

Write

$$
Q_x=\mathcal B_x(H_D,H_D),\qquad
M_x=\mathcal B_x(P,H_D).
$$

The complete rough–rough composite contribution is

$$
\mathcal R_x
=\mathcal B_x(H_D-P,H_D-P)
=Q_x-2M_x+T_x\ge0.
\tag{8}
$$

Now combine all remaining composite–composite terms, including their negative cross products:

$$
\mathcal N_x
=2\mathcal B_x(H_D-P,L_D)+\mathcal B_x(L_D,L_D).
$$

Using (1), with no absolute values, gives

$$
\boxed{
\mathcal N_x=-c_W-Q_x+2M_x+o(1).
}
\tag{9}
$$

Thus

$$
\boxed{
\mathcal R_x+\mathcal N_x=T_x-c_W+o(1).
}
\tag{10}
$$

This is the complete signed accounting. The positive rough–rough contribution does not leave an uncharged reserve; its corresponding negative amount occurs in the combined nonrough term.

The effect can be quantified. For sufficiently small fixed $\alpha>0$, standard fundamental-lemma sieve estimates and the upper sieve for a prime with a rough neighbor give

$$
Q_x\gg_W\alpha^{-2},
\qquad
M_x\ll_W\alpha^{-1}.
$$

Therefore

$$
\mathcal N_x
\le-c_W-c_W'\alpha^{-2}+O_W(\alpha^{-1})+o(1).
\tag{11}
$$

For small fixed $\alpha$, the nonrough complementary contribution is unconditionally strongly negative. This is an actual arithmetic cancellation, not merely a hypothetical possibility under finite twins.

The elementary union-bound alternative would require

$$
2M_x-Q_x>0,
$$

because (8) would then give $T_x>0$. But the same sieve estimates establish

$$
2M_x-Q_x<0
$$

for sufficiently small fixed $\alpha$.

So the available rough-pair positivity and one-prime distribution estimates do not produce the needed strict inequality. They already account for each other with the wrong sign.

5. Positivity of Lee’s two norms imposes no additional contradiction

There is a useful adversarial check against trying to extract a sign from the fact that $I_+$ and $I_-$ are individually nonnegative.

Under finite twins, the limiting signed bilinear form on the two coefficient sequences $(P,C_D)$ has matrix

$$
\boxed{
\begin{pmatrix}
0&c_W\\
c_W&-c_W
\end{pmatrix}.
}
\tag{12}
$$

This reproduces every evaluated relationship:

$$
\begin{aligned}
\mathcal B_x(P,P)&=0,\\
\mathcal B_x(P,P+C_D)&=c_W,\\
\mathcal B_x(P+C_D,P+C_D)&=c_W.
\end{aligned}
$$

There is no conflict with positivity of the original norms. For example, if $A$ denotes the matrix in (12), then for sufficiently large $L>0$,

$$
G_+=LI+\tfrac12A,\qquad
G_-=LI-\tfrac12A
$$

are both positive semidefinite, yet

$$
G_+-G_-=A.
$$

This is an abstract consistency test, not a replacement for the actual integer sequences. It establishes that the known signed moments together with positivity of both Fourier norms do not logically force a positive prime-pair difference.

The actual residual diagonal energy is large enough to permit precisely this behavior, as (8) shows.

6. The unresolved term is the complete long–long divisor correlation

Return to the original von Mangoldt coefficients and define

$$
r_D(n)=\Lambda(n)-a_D(n)
=\sum_{\substack{d\mid n\\d>D}}\mu(d)\log(n/d).
$$

Proper prime powers contribute $o(1)$ to these fixed-gap forms, so

$$
\mathcal B_x(r_D,r_D)
=\mathcal B_x(C_D,C_D)+o(1).
$$

Opening both residual divisor sums gives

$$
\boxed{
\begin{aligned}
\mathcal B_x(r_D,r_D)
=\sum_{n\asymp x}K_x(n)
&\sum_{\substack{d\mid n\\d>D}}
\sum_{\substack{e\mid n+2\\e>D}}\\
&\mu(d)\mu(e)
\log\frac nd\log\frac{n+2}{e}.
\end{aligned}}
\tag{13}
$$

This is the first genuinely uncontrolled arithmetic quantity.

The two divisor congruences are compatible only when $(d,e)\mid2$. For many relevant pairs, however, their combined modulus $[d,e]$ is at least comparable with $x$, and can greatly exceed it.

The short–short calculation succeeds because its modulus is $o(x)$. The prime–short calculation succeeds because Bombieri–Vinogradov controls its single modulus below $x^{1/2-\varepsilon}$.

Neither argument controls (13). Its large divisors correspond to complementary cofactors satisfying the determinant-two relation

$$
e\ell-dk=2,
$$

with both Möbius signs retained. The relevant slopes and cofactors grow with $x$. A standard mean-value theorem for the unweighted Möbius correlation, or an estimate applied separately to each progression, does not give the required additive $o(1)$ control of this combined signed sum.

This is not merely a technical error term in the mollifier calculation. Under finite twin support, (13) must have the main term

$$
\boxed{-c_W+o(1).}
$$

Thus a proof that it is $o(1)$, or even strictly greater than $-c_W$ by a fixed positive amount, would require genuinely new fixed-shift arithmetic information.

The cumulative version does not escape this obstruction

Take unbounded geometrically separated scales $x_j$, using the same fixed smoothing. Summing (3) gives

$$
\sum_{j\le J}T_{x_j}
=
c_WJ+
\sum_{j\le J}\mathcal B_{x_j}(C_{D_j},C_{D_j})
+o(J).
\tag{14}
$$

If twins are finite, the left side is eventually constant (indeed, zero on all sufficiently large selected windows), so the cumulative composite residual has slope exactly $-c_W$.

No independent estimate checked here rules out that slope. The cross-length invariance (5) shows that altering the short mollifier pieces does not change it.

Final verdict

The arithmetic transfer succeeds through every part accessible to short-divisor CRT and one-prime Bombieri–Vinogradov estimates.

It establishes a positive mollified difference, evaluates both genuine-prime cross forms, and proves that changes among fixed short mollifier lengths have asymptotically zero signed effect. The full inverse calculation nevertheless leaves

$$
\boxed{
\mathcal B_x(C_D,C_D)=T_x-c_W+o(1),
}
$$

with no independent strict lower bound on the left.

The rough–rough positivity does not close the inequality: the complete nonrough contribution is provably negative enough to compensate it. The positive Fourier norms do not supply an additional sign constraint. The unresolved long–long Möbius divisor correlation can have exactly the negative main term required by finite twin support without contradicting any of the established estimates.

The first failed implication is therefore the attempted passage from evaluated prime–mollifier mixed moments to a favorable one-sided bound for their composite–composite residual. It is not justified by Lee’s Fourier identity, Bombieri–Vinogradov, the available sieve bounds, or standard norm inequalities.

No strictly positive genuine-prime gap-two difference on an unbounded sequence, and no unbounded cumulative prime-only difference, has been established.

I am ending this particular inverse-mollifier attempt at that exact obstruction, rather than presenting another mollifier or equivalent detector as a solution. The stronger prime-conductor ratios input remains a separate, unverified mathematical route and has not been assumed here.

---

## Confirm Twin Prime Proof Plan

[Original conversation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6b031ca7-26c8-83ee-a2e0-f4f6cf51888d)

### Recovered response 1

1. An exact positive moment that suppresses every semiprime

There is a useful algebraic construction from Bombieri’s generalized von Mangoldt function

$$
\Lambda_k(n)=\sum_{d\mid n}\mu(d)\log^k(n/d).
$$

Set

$$
R(n)=\frac{\Lambda_2(n)}{(\log n)^2},\qquad n>1.
$$

Using Bombieri’s identity

$$
\Lambda_2=\Lambda\log+\Lambda*\Lambda,
$$

one obtains, with no squarefreeness assumption,

$$
\boxed{
R(n)=
\begin{cases}
(2a-1)/a^2,&n=q^a,\\[3pt]
\dfrac{2\log q\log r}{(a\log q+b\log r)^2},
&n=q^ar^b,\quad q\ne r,\\[8pt]
0,&\omega(n)\ge3.
\end{cases}}
\tag{1}
$$

Here $\omega$ counts distinct prime factors. These cases show that $0\le R(n)\le1$, with the sharper distinctions

$$
\boxed{
R(q)=1,\qquad
R(q^a)\le\frac34\ (a\ge2),\qquad
R(n)\le\frac12\quad(\omega(n)\ge2).
}
\tag{2}
$$

In particular, for a squarefree semiprime $n=qr$, writing $t=\log q/\log n$,

$$
R(n)=2t(1-t)\le\frac12.
$$

Thus $R(n)^j$ gives weight exactly $1$ to a prime, at most $2^{-j}$ to every integer having at least two distinct prime factors, and at most $(3/4)^j$ to proper prime powers.

Define the genuine-prime-supported moment

$$
\mathcal M_j(X)=
\sum_{\substack{X<p\le2X\\p\text{ prime}}}
(\log p)R(p+2)^j.
$$

Let

$$
\mathcal T(X)=
\sum_{\substack{X<p\le2X\\p,p+2\text{ prime}}}\log p.
$$

The prime-number theorem and the elementary bound $O(\sqrt X)$ for proper prime powers in a dyadic interval give the unconditional estimate

$$
\boxed{
0\le\mathcal M_j(X)-\mathcal T(X)
\ll X2^{-j}+\sqrt X\log X(3/4)^j,
}
\tag{3}
$$

uniformly over all positive integers $j$.

In particular, choosing $j=\lceil2\log X\rceil$ makes the right-hand side $o(1)$. Therefore

$$
\boxed{
\mathcal M_{\lceil2\log X\rceil}(X)
=\mathcal T(X)+o(1).
}
\tag{4}
$$

This is a rigorous exponentially accurate nonnegative prime projector on the actual shifted-prime source. It does not, by itself, establish a positive lower bound for the moment; that is the remaining analytic task.

2. Bombieri's sieve gives a stronger, uniform contamination bound

The estimate (3) can be improved substantially at the natural twin-prime scale.

I verified the relevant primary input in Bombieri's On twin almost primes, especially §2, equation (2.7). Its $k=1$ case is an upper-bound sieve for two affine prime forms. Replacing the shift $+2$ by $-2$ leaves the local root counts unchanged.

matwbn.icm.edu.pl

For odd $a$, put

$$
\Phi(a)=\prod_{\substack{\ell\mid a\\\ell>2}}\frac{\ell-1}{\ell-2}.
$$

The two-form upper sieve gives, uniformly when $T\ge\sqrt X$ and $aT\asymp X$,

$$
\sum_{b\le T}\Lambda(b)\Lambda(ab-2)
\ll \Phi(a)\,T\frac{\log X}{\log T}.
$$

Using

$$
\Lambda_2(n)=\Lambda(n)\log n+(\Lambda*\Lambda)(n),
$$

splitting the convolution at $a\le\sqrt n$, and applying the usual twin-prime upper sieve to the first term, yields

$$
\boxed{
\sum_{\substack{X<p\le2X\\p\text{ prime}}}
(\log p)\Lambda_2(p+2)
\ll X\log X.
}
\tag{5}
$$

The convolution estimate uses

$$
\sum_{a\le\sqrt{2X}}\frac{\Lambda(a)\Phi(a)}a
\ll\log X.
$$

No asymptotic for twin primes, Elliott–Halberstam conjecture, or unproved Type II estimate is used.

Consequently,

$$
\sum_{X<p\le2X}(\log p)R(p+2)
\ll\frac X{\log X}.
$$

For integers with at least two distinct prime factors, $R^j\le2^{1-j}R$. This sharpens (3) to

$$
\boxed{
0\le\mathcal M_j(X)-\mathcal T(X)
\ll
2^{1-j}\frac X{\log X}
+\sqrt X\log X(3/4)^j,
}
\tag{6}
$$

with an absolute implied constant independent of $j$.

In particular, for any integer-valued $j(X)\to\infty$,

$$
\boxed{
\mathcal M_{j(X)}(X)
=\mathcal T(X)+o\left(\frac X{\log X}\right).
}
\tag{7}
$$

This is a genuine unconditional analytic approximation to the weighted twin-prime count, with composite contamination smaller than the predicted Hardy–Littlewood scale.

It is not yet a forcing inequality: the right side could be $o(X/\log X)$, and no independent positive lower bound for the left side at a growing exponent has been established.

3. Chen's theorem supplies a positive moment—but below the discrimination threshold

There is an important independent lower bound to test.

Bienvenu, Shao and Teräväinen, A transference principle for systems of linear equations, and applications to almost twin primes, Proposition 5.2, prove a weighted Chen theorem in which every prime factor of $p+2$ exceeds $X^{1/10-o(1)}$. Its nilsequence formulation permits a fixed smooth dyadic localization.

msp.org

Therefore there is a constant $c>0$ such that, for all sufficiently large $X$, at least

$$
c\frac X{\log^2X}
$$

primes $p\in(X,2X]$ have $p+2$ prime or semiprime, with all prime factors exceeding $X^{1/10-o(1)}$.

For a squarefree semiprime in that population, put $t=\log q/\log(p+2)$, with $q$ the smaller factor. Then

$$
t\ge\frac1{10}-o(1),\qquad
R(p+2)=2t(1-t)\ge\frac9{50}-o(1).
$$

Prime squares have $R=3/4$, and actual primes have $R=1$. Hence, for every fixed $j$,

$$
\boxed{
\mathcal M_j(X)\gg_j\frac X{\log X}.
}
\tag{8}
$$

Combining this with (5) establishes

$$
\boxed{
\mathcal M_j(X)\asymp_j\frac X{\log X}
\qquad\text{for every fixed }j\ge1.
}
\tag{9}
$$

This is an unconditional positive moment theorem on the actual shifted-prime source.

Unfortunately, it does not prove twins. The Chen lower bound provides a coefficient proportional to $(9/50)^j$, while the possible composite contamination in (6) decreases only as $2^{-j}$. Their ratio contains

$$
\left(\frac{9}{25}\right)^j\longrightarrow0.
$$

Thus increasing $j$ makes the available positive Chen contribution shrink faster than the composite allowance we need it to beat.

The first missing inference is therefore quite precise: the established positive moment at each fixed degree does not give a growing-degree lower bound above the permitted semiprime contribution.

4. The critical near-balanced semiprimes can be priced more sharply

The maximum value $R(qr)=1/2$ occurs when the two prime factors have equal logarithmic sizes. This suggests concentrating on the nearly balanced region.

Bombieri's two-form upper bound gives, for each fixed $j$, an absolute constant $C$ such that

$$
\boxed{
\limsup_{X\to\infty}
\frac{\log X}{X}
\sum_{\substack{X<p\le2X\\
p+2=qr,\ q<r\text{ prime}}}
(\log p)R(p+2)^j
\le C I_j,
}
\tag{10}
$$

where

$$
I_j=
\int_0^{1/2}
\frac{[2t(1-t)]^j}{t(1-t)^2}\,dt.
$$

To derive this, fix the smaller prime $q$, sieve the two forms $r$ and $qr-2$, then sum $1/q$ over the prime $q$. The logarithmic variable $t=\log q/\log X$ produces $dt/t$. The denominator $(1-t)^2$ comes from the two prime conditions in the complementary variable. The repeated-prime-factor terms are $o_j(X/\log X)$ by the same sieve, splitting their repeated base into small and large ranges.

Laplace's method at $t=1/2$ gives the exact asymptotic

$$
\boxed{
I_j\sim\frac{2\sqrt\pi}{\sqrt j}\,2^{-j}
\qquad(j\to\infty).
}
\tag{11}
$$

This improves the crude $2^{-j}$ bound by a factor $j^{-1/2}$, for fixed-degree sieve estimates followed by the degree limit.

There is a useful quantitative test of whether balancing can repair the argument. Suppose we had an independent lower bound

$$
\#\left\{
\begin{array}{l}
X<p\le2X,\ p\text{ prime},\\
p+2\text{ prime or }qr,\quad
X^{1/2-\eta}\le q\le r
\end{array}
\right\}
\ge c_\eta\frac X{\log^2X}.
$$

It would contribute at least, asymptotically,

$$
c_\eta\,2^{-j}(1-4\eta^2)^j\frac X{\log X}
$$

to $\mathcal M_j$.

To exceed the global semiprime bound (10), we would need

$$
\boxed{
c_\eta(1-4\eta^2)^j>\frac{C'}{\sqrt j}
}
\tag{12}
$$

with a suitably specified sieve constant $C'$.

Optimizing the comparison around $j\asymp\eta^{-2}$ shows that it would require a lower coefficient at least of order $C'\eta$.

The verified Chen theorem does not supply this near-balanced lower bound with the necessary constant. Its factor condition $q\ge X^{1/10-o(1)}$ is much broader. We cannot silently concentrate its positive mass near $\sqrt X$.

This is the critical factor-interval obstruction, even after exploiting the optimal Gaussian-shaped suppression in (11).

5. The $\Lambda_3$ cancellation works pointwise but creates a signed three-factor term

There is a second, strikingly exact construction. The Dirichlet-convolution identities give

$$
\boxed{
3(\log n)\Lambda_2(n)-2\Lambda_3(n)
=
\Lambda(n)(\log n)^2-2(\Lambda*\Lambda*\Lambda)(n).
}
\tag{13}
$$

For a prime, this equals $(\log n)^3$. For every squarefree semiprime, it equals zero regardless of how balanced its factors are. For a product $n=qrs$ of three distinct primes it equals

$$
-12\log q\log r\log s<0.
$$

For an integer having four or more distinct prime factors, it vanishes.

Thus the semiprime contribution is eliminated perfectly, rather than merely suppressed.

But summing (13) on the actual shifted-prime source gives

$$
\begin{aligned}
&\sum_{\substack{X<p\le2X\\p\text{ prime}}}
(\log p)\left[
3\log(p+2)\Lambda_2(p+2)-2\Lambda_3(p+2)
\right]\\
&\quad=
\sum_{\substack{X<p\le2X\\p\text{ prime}}}
(\log p)\Lambda(p+2)\log^2(p+2)\\
&\qquad-
2\sum_{\substack{X<p\le2X\\p\text{ prime}}}
(\log p)(\Lambda*\Lambda*\Lambda)(p+2).
\end{aligned}
\tag{14}
$$

The first term is the desired twin-prime correlation, with negligible prime-power contamination. The second is a nonnegative, genuinely shifted three-prime-factor correlation, subtracted with coefficient two.

To prove twins through this identity, we would need to establish a positive lower bound for the difference. That has not been obtained.

Why Bombieri's asymptotic sieve does not settle the sign

I checked the precise quantifiers in Bombieri's original Theorems 1 and 2 and Ford's On Bombieri's asymptotic sieve.

Bombieri unconditionally establishes

$$
\sum_{n\le X}\Lambda(n+2)\Lambda_k(n)
=
2C_2X(\log X)^{k-1}
\left[k+O\!\left(k^{4/3}2^{-k/3}\right)\right],
$$

with an absolute implied constant. For $k=2,3$, the error is at the same order as the main term, so this is not an asymptotic precise enough to evaluate (14). Under the unproved full level-one distribution hypothesis, Bombieri obtains the corresponding asymptotics for $k\ge2$.

matwbn.icm.edu.pl+1

Even conditionally granting those stronger asymptotics, the leading terms in our combination cancel:

$$
3(\log X)\,[4C_2X\log X]
-
2[6C_2X(\log X)^2]=0.
$$

The shift sign $-2$ has the same local constants, but adapting the published $+2$ result does not create a positive remainder.

Hence the asymptotic sieve supplies neither the required positive sign nor a lower-order estimate distinguishing the two sides of (14). Ford's result further shows that a fixed distribution exponent below one is insufficient, in general, to determine even individual generalized von Mangoldt asymptotics. That is a limitation of distribution-only methods, not an impossibility theorem for the particular shifted-prime sequence.

6. The strongest unconditional result and the unresolved forcing inequality

The two attempts yield complementary conclusions.

The signed degree-three combination annihilates all semiprimes exactly, but leaves a negative shifted three-factor correlation of the same potentially decisive scale.

The nonlinear $\Lambda_2$ moment remains nonnegative and suppresses all semiprimes exponentially. It has the unconditional approximation

$$
\mathcal M_{j(X)}(X)
=\mathcal T(X)+o(X/\log X)
\quad\text{whenever }j(X)\to\infty,
$$

and even an $o(1)$ error for $j(X)=\lceil2\log X\rceil$. However, the available positive lower bound from Chen's theorem becomes too small as $j$ grows.

The sharpest clean sufficient criterion emerging from this investigation is:

$$
\boxed{
\limsup_{X\to\infty}
\frac{\log X}{X}\,
\mathcal M_{j(X)}(X)>0
\quad\text{for some }j(X)\to\infty
\ \Longrightarrow\
\text{infinitely many ordinary twins}.
}
\tag{15}
$$

This implication is unconditional and follows from (7). It would actually imply a quantitative positive twin density on a subsequence. For an arbitrarily sparse infinitude result, one could instead use the absolutely accurate $j(X)=\lceil2\log X\rceil$ moment and prove that it stays bounded away from zero on arbitrarily large scales.

Neither lower bound is supplied by the checked primary sources. The missing mathematical input is a growing-degree one-sided moment estimate for the actual pair of forms $p,p+2$, or a signed bound on the triple convolution in (14). The known Chen lower bound and the available semiprime upper sieve do not cross the necessary threshold.

Thus the high-moment construction gives a rigorous prime-selecting approximation and a precise, independently checked obstacle at the balanced-semiprime interval, but it does not yet force infinitely many genuine twin primes.

---

### Recovered response 2

1. A genuine two-factor obstruction inside the Carmichael–Lucas construction

The two norm-group divisibilities are correct. For $D=-3$,

$$
\chi(r)=-1\quad(r\equiv2\bmod3),\qquad
\chi(s)=1\quad(s\equiv1\bmod3).
$$

If $N=rs$, then

$$
r+1\mid N+1\iff r+1\mid s-1,
$$

and

$$
s-1\mid N+1\iff s-1\mid r+1.
$$

Therefore

$$
\boxed{r+1=s-1,\qquad s=r+2.}
$$

This characterization applies to primes greater than $3$, with $r\equiv2\bmod3$ and $s\equiv1\bmod3$. The exceptional twin pair $3,5$ is excluded because $3$ ramifies in $\mathbb Q(\sqrt{-3})$.

There is a stronger identity worth retaining:

$$
\boxed{N+1=(r+1)^2.}
$$

For a squarefree product of exactly two odd primes, the converse also holds: if $rs+1=t^2$, then

$$
rs=(t-1)(t+1).
$$

Since $t-1,t+1$ are odd and coprime, unique factorization forces them to be $r,s$. Thus the desired two-factor construction is equivalent to finding a semiprime $N$ for which $N+1$ is a square.

That additional constraint is not supplied by ordinary Carmichael–Lucas divisibility.

2. Wright's actual prime pool is one-sided

I inspected Thomas Wright's primary paper, There are infinitely many elliptic Carmichael numbers, including its prime-pool construction and subgroup argument.

His proof constructs an auxiliary squarefree product $L$ and finds a common parameter $k$ for which many divisors $d\mid L$ satisfy

$$
\boxed{r_d=d\alpha k-1\text{ prime},}
$$

where

$$
\alpha=8\cdot3\cdot7\cdot11\cdot19\cdot43\cdot67\cdot163.
$$

The primes also satisfy quadratic-nonresidue conditions modulo the primes composing $L$. In particular, because $3\mid\alpha$,

$$
r_d\equiv2\pmod3.
$$

They are exactly the inert-sign primes needed on the $r$-side. But the proof establishes no primality of the companion numbers

$$
\boxed{s_d=d\alpha k+1.}
$$

Wright's Lemma 6.2 supplies many one-sided primes. His Theorem 8.1 then uses a subgroup theorem in

$$
G=(\mathbb Z/L\mathbb Z)^\times\times\{\pm1\}
$$

to select a subset of the $r_d$ whose product $N$ satisfies

$$
N\equiv-1\pmod{L},\qquad N\equiv-1\pmod{\alpha k}.
$$

Hence each selected $r_d+1$ divides $N+1$. This is how the Lucas–Carmichael condition is obtained.

arxiv.org+1

The subgroup theorem chooses a product of many primes, not a matching pair of the forms $d\alpha k\pm1$. Furthermore, all selected primes have the negative sign, and their number must be odd. A two-factor product drawn exclusively from that pool cannot furnish the required mixed-sign certificate.

The quadratic-nonresidue condition does not sieve the companion prime

There is a concrete arithmetic reason that Wright's extra character conditions cannot establish primality of $s_d$.

Every auxiliary prime $\ell\mid L$ satisfies $\ell\equiv7\pmod8$, so

$$
\left(\frac{-2}{\ell}\right)=-1.
$$

For $\ell\nmid d$, the residue

$$
r_d\equiv-2\pmod\ell
$$

is therefore allowed by Wright's quadratic-nonresidue restriction. But that residue makes

$$
s_d=r_d+2\equiv0\pmod\ell.
$$

Thus the nonresidue condition does not even exclude divisibility of the proposed upper prime by the unused factors of $L$.

For $\ell\mid d$, the companion is automatically $1\bmod\ell$, but that protects it against only those particular primes. Nothing in the construction excludes all other possible prime divisors.

The first missing prime input is therefore precise: prove that at least one of Wright's many one-sided primes has $r_d+2$ prime, with the same $d$ and the same $k$. Wright's published abundance result does not imply it.

3. A common parameter $k$ is still insufficient: the labels must coincide

The classical AGP construction and Wright's earlier paper, Infinitely many Carmichael numbers in arithmetic progressions, provide the complementary plus-sign prime pools. Their proofs establish suitable common parameters within their own constructions, not a shared parameter across the positive- and negative-sign constructions.

doi.org+1

Suppose we strengthen the setup by granting a common parameter $t=\alpha k$, and define

$$
A_t=\{d\mid L:dt-1\text{ prime}\},\qquad
B_t=\{d\mid L:dt+1\text{ prime}\}.
$$

Then the desired event is exactly

$$
\boxed{A_t\cap B_t\ne\varnothing.}
$$

The ordinary pigeonhole bound is

$$
|A_t\cap B_t|\ge |A_t|+|B_t|-\tau(L).
$$

Wright's argument provides no lower bound making the right side positive.

This remains a problem even if both signs have many prime values. For a squarefree $L$, there are $2^{\omega(L)}$ available divisor labels, while the subgroup construction needs only a much smaller prime pool. The two prime-label sets can therefore be disjoint without violating the separate abundance statements.

Why averaging over the common parameter does not repair this

Consider the simultaneous multiplicity count

$$
\sum_{t\in\mathcal K}|A_t||B_t|
=
\sum_{t\in\mathcal K}\sum_{d,e\mid L}
\mathbf1_{\{dt-1\text{ prime}\}}
\mathbf1_{\{et+1\text{ prime}\}}.
$$

It separates into

$$
\boxed{
\underbrace{\sum_t\sum_{d\mid L}
\mathbf1_{\{dt-1,\ dt+1\text{ prime}\}}}_{\text{desired diagonal}}
+
\underbrace{\sum_t\sum_{\substack{d,e\mid L\\d\ne e}}
\mathbf1_{\{dt-1,\ et+1\text{ prime}\}}}_{\text{different-label contamination}}.
}
\tag{3}
$$

The different-label part cannot be excluded by congruence.

For a prime $\ell\nmid de$, the roots of the two linear forms modulo $\ell$ coincide precisely when

$$
d+e\equiv0\pmod\ell.
$$

Otherwise they exclude two residue classes. If $\ell$ divides exactly one of $d,e$, there is one excluded class; if it divides both, there is none. Thus each off-diagonal pair is locally admissible at every odd prime $\ell\ge5$. The required parity and mod-$3$ restrictions are handled by $t=\alpha k$.

A positive count of simultaneous plus- and minus-sign primes at different labels therefore does not establish twins. Their separation is

$$
(et+1)-(dt-1)=(e-d)t+2.
$$

It equals two only when $e=d$.

This is the exact discriminating calculation. More averaging over $k$, stronger separate prime counts, or a common-parameter multiplicity theorem would still need to isolate the diagonal $d=e$ from the off-diagonal pairs.

No lower bound for that diagonal follows from the checked AGP-type results.

4. The subgroup argument cannot shorten a long product to two factors

Wright's group theorem guarantees a subproduct with a prescribed residue in a finite multiplicative group. It does not impose that the subproduct contain exactly two primes.

This distinction is essential rather than technical.

For instance, in the abstract group $C_3\times C_2$, three elements each equal to $(g,-1)$, where $g$ has order three, multiply to $(1,-1)$. No two of them do. Adding any number of elements of the opposite-sign type $(g,+1)$ does not automatically create a mixed pair with product $(1,-1)$.

Thus even a rich prime pool and a successful prescribed-product theorem need not contain a successful two-element subproduct.

There is also an exact arithmetic explanation.

Suppose a longer squarefree number has the form

$$
N=rsT,
$$

where $r$ is inert and $s$ is split. The two relevant divisibilities become

$$
\boxed{
sT\equiv1\pmod{r+1},\qquad
rT\equiv-1\pmod{s-1}.
}
\tag{4}
$$

The extra product $T$ is a modular compensator. It allows these congruences to hold even when $r+1\ne s-1$.

To delete all the other factors while preserving the two conditions, one would need, for example,

$$
T\equiv1\pmod{\operatorname{lcm}(r+1,s-1)}.
$$

Then (4) would indeed give $r+1=s-1$ and twins. But no subgroup theorem used in Wright's construction asserts that the product of all the unwanted factors is $1$ modulo these two growing, prime-dependent moduli.

Subgroup extraction proves that some collection of factors has a prescribed product. It does not permit an arbitrary designated pair to remain after every other factor is removed.

5. Carlip–Somer supplies an especially sharp comparison

The primary Carlip–Somer, Primitive Lucas d-pseudoprimes and Carmichael–Lucas numbers is directly relevant.

Their Theorem 6.5 proves that, for each fixed $d$, there are only finitely many Lucas $d$-pseudoprimes with exactly two distinct prime factors.

The proof identifies the same mixed-sign phenomenon. Apart from finitely many exceptional cases, the two-prime configuration must have opposite signatures and its prime factors must differ by two.

impan.pl

There is no contradiction with an infinitude of twins: for the mixed twin pair $r,s=r+2$, the corresponding primitive Lucas index is

$$
\boxed{
d=\frac{N+1}{\operatorname{lcm}(r+1,s-1)}
=r+1.
}
$$

Thus the index necessarily grows with the twin primes. Fixed-$d$ infinitude is the wrong target.

Their three-factor construction does not force two-factor twins

Algorithm 7.2 constructs candidates with

$$
p_2=p_1+1+k,\qquad
p_3=\frac{p_1(p_2-1)+p_2}{k},
$$

requiring all three numbers to be prime. Its signature is $(-1,1,1)$, and its resulting product satisfies the Carmichael–Lucas condition.

When $k\equiv1\pmod6$, the paper's residue calculation gives

$$
p_1\equiv2\pmod3,\qquad
p_2,p_3\equiv1\pmod3,
$$

so this branch has precisely the fixed $D=-3$ signature of interest.

impan.pl+1

But

$$
p_2-p_1=k+1.
$$

For $k>1$, the first two primes are not twins. To force difference two, one must specialize to $k=1$, when the algorithm requires

$$
p_1,\qquad p_1+2,\qquad p_1^2+2p_1+2
$$

all to be prime.

That specialization already assumes the simultaneous primality of $p_1,p_1+2$.

Moreover, Carlip and Somer explicitly present the infinitude of their three-factor constructions as conjectural, conditional on Schinzel–Sierpiński Hypothesis H—not as a proved theorem. Their unconditional theorems certify the outputs when the required prime inputs exist.

impan.pl

Consequently, this paper provides no independent forcing argument that can supply even the desired two-prime subproduct, let alone infinitely many such products.

6. The strongest possible repair using these prime pools

The appropriate constructive target is a matched-label lower bound:

$$
\boxed{
\sum_{k\in\mathcal K}\sum_{d\mid L}
\theta(\alpha dk-1)\theta(\alpha dk+1)>0,
}
\tag{5}
$$

where $\theta(u)=(\log u)\mathbf1_{\{u\text{ prime}\}}$.

A positive value at unbounded $\alpha dk$ would genuinely prove unbounded ordinary twin primes.

I tested whether either source can provide (5) by three successive deductions.

First, Wright gives a large negative-sign prime pool for some $k$, but no positive-sign count for that same $k$.

Second, even granting both one-sided counts for the same $k$, the available cardinality bounds do not force a common divisor $d$.

Third, even granting an unbounded number of simultaneous plus- and minus-sign primes at that $k$, the different-label terms in (3) remain. The group product conditions do not distinguish them from the diagonal.

A two-dimensional upper sieve can bound the matched-label population, but no proved lower sieve or product-group theorem gives it a strictly positive lower bound. The obstruction is not a missing local congruence: for $t$ divisible by $\alpha$, the two forms $dt-1,dt+1$ are locally admissible.

One could attempt to force a close pair via a bounded-gap prime theorem. But the two primes from different labels are separated by at least $t-2$. If $t$ exceeds a fixed bounded-gap constant, a close pair would have to come from the same label. The difficulty is that the available prime-cluster theorems do not guarantee two primes within one designated two-form block. They can select prime values from different blocks, whose separation grows with $t$.

This repair therefore returns to (5), without an independent positive estimate.

Final mathematical assessment

The proposed two-prime mixed-sign criterion is correct, and the primary sources give two genuinely different constructions:

-

Wright proves infinitely many long Lucas–Carmichael products using abundant primes of the negative form $dk-1$.

-

Carlip–Somer gives algorithms for mixed-sign three-prime Lucas–Carmichael products, but does not prove their infinitude.

The obstacle is sharper than the observation that those products have too many factors.

The exact missing arithmetic input is simultaneous primality of $dk-1$ and $dk+1$ for the same divisor $d$ and the same parameter $k$. Neither many one-sided primes, nor a common parameter, nor subgroup products modulo $L$, nor three-factor Lucas divisibility forces that matching.

The product-shortening congruences (4) show why: additional factors can compensate for two primes that are not twins. Removing those factors requires a new condition not supplied by either construction.

No unconditional infinite matched-label family has been obtained, so the proposed Lucas–Carmichael route has not established infinitely many ordinary twin primes. The full target remains open at the precise lower-bound obligation (5).

---

### Recovered response 3

1. The new two-sign residue count is correct

This repair genuinely strengthens Wright's one-sided prime pool. It does not merely impose an incompatible extra condition.

Let

$$
t=\alpha dk,\qquad r=t-1,\qquad s=t+1,
$$

where $d\mid L$, $(k,L)=1$, and

$$
\alpha=8\cdot3\cdot7\cdot11\cdot19\cdot43\cdot67\cdot163.
$$

Wright chooses the primes $q\mid L$ with $q\equiv-1\pmod{4\alpha}$. In particular, $q\equiv7\pmod8$, so $\chi_q(-1)=-1$ and $\chi_q(2)=1$. This is the setup of his Lemmas 5.1 and 6.2.

arxiv.org

For $q\mid d$, $t\equiv0\pmod q$, giving automatically

$$
\chi_q(t-1)=-1,\qquad \chi_q(t+1)=1.
$$

For $q\nmid d$, $t\ne0\pmod q$. The exact number of admissible residues is

$$
\begin{aligned}
A_q
&=\frac14\sum_{t\in\mathbb F_q\setminus\{0,\pm1\}}
(1-\chi_q(t-1))(1+\chi_q(t+1))\\
&=\boxed{\frac{q-5-2\chi_q(2)}4}.
\end{aligned}
$$

The character sums used here are $\sum_t\chi_q(t^2-1)=-1$, together with the exclusions of $0,\pm1$.

On Wright's actual modulus family,

$$
\boxed{A_q=\frac{q-7}{4},\qquad
\rho_q=\frac{A_q}{q-1}=\frac{q-7}{4(q-1)}.}
$$

The zero residue is deliberately excluded when $q\nmid d$; otherwise it would allow $q\mid k$.

The correct multiplicative pool factor

At a prime $q\nmid d$, the local prime-progression density is $\rho_q$. At $q\mid d$, the condition $k\ne0\pmod q$, combined with the prime-progression normalization, contributes a factor $1$.

Thus, after summing the possible divisor labels $d\mid L$, the local density product is

$$
\boxed{
\prod_{q\mid L}(1+\rho_q)
=
\prod_{q\mid L}\frac{5q-11}{4(q-1)}.
}
\tag{1}
$$

Since Wright's selected primes $q$ grow and satisfy $\sum_{q\mid L}1/q=o(1)$,

$$
\boxed{
\prod_{q\mid L}(1+\rho_q)
=(1+o(1))\left(\frac54\right)^{\omega(L)}.
}
\tag{2}
$$

This confirms your claimed exponential base $5/4$. Wright's original one-sign pool has base $3/2$, so the added sign reduces but does not eliminate the exponential supply of divisor labels.

Wright's progression proof uses an exceptional-modulus theorem of Alford–Granville–Pomerance, followed by Brun–Titchmarsh to remove the labels with $(k,L)>1$. These are exactly the places where the revised residue count must be inserted; simply multiplying his final numerical bound by $2^{-\omega(L)}$ would not be a sufficient proof.

arxiv.org+2

2. A stronger CRT test: exponentially many candidates can all have composite companions

There is a decisive way to test the new condition against Wright's actual construction. We can retain both quadratic signs and prove the existence of a large common-$k$ prime pool whose companions are all composite.

The construction uses only prime-distribution inputs already present in Wright's proof.

Impose one additional fixed congruence

Observe that

$$
\alpha\equiv1\pmod5.
$$

Modify Wright's auxiliary-prime selection by requiring

$$
\boxed{
q\equiv-1\pmod{4\alpha},
\qquad q\equiv1\pmod5.
}
\tag{3}
$$

These are compatible reduced congruences. Wright's Lemma 5.1 is proved using Bombieri–Vinogradov with an arbitrary fixed admissible progression. The same proof works with the fixed modulus $20\alpha$ in place of $4\alpha$, so the pool of auxiliary primes remains large:

$$
|\mathcal Q|\gg\frac{y^\vartheta}{\log y}
$$

for Wright's fixed admissible parameter $1<\vartheta<2$, retaining the required smoothness of $q-1$.

arxiv.org

Form $L$ from these primes, discarding the bounded number needed to avoid Alford–Granville–Pomerance exceptional moduli. One further large prime may be discarded to ensure the harmless fixed factor $5$ fits the progression-modulus range. This changes $\omega(L)$ by at most a bounded amount.

Every divisor $d\mid L$ now satisfies

$$
\boxed{d\equiv1\pmod5.}
$$

Impose the additional condition

$$
r=\alpha dk-1\equiv3\pmod5.
$$

Because $\alpha d\equiv1\pmod5$, this is equivalent to

$$
\boxed{k\equiv4\pmod5.}
$$

But for every such $k$ and every $d\mid L$,

$$
\boxed{
s=\alpha dk+1\equiv0\pmod5.
}
\tag{4}
$$

Since $s>5$, every companion is composite.

The question is whether such a $k$ can still have many prime values $r$, satisfying both of your quadratic-character signs. The answer is yes.

Adapt Wright's progression count

For $q\nmid d$, use the $A_q=(q-7)/4$ admissible residues computed in §1. At $q\mid d$, the signs are automatic.

Apply the Alford–Granville–Pomerance progression lower bound to the resulting reduced classes modulo $5\alpha L$. For each $d\mid L$, it gives a prime count bounded below by a fixed multiple of

$$
\frac{x^{1-B/2}}{\varphi(5\alpha)\log x}
\prod_{q\mid d}\frac q{q-1}
\prod_{\substack{q\mid L\\q\nmid d}}\rho_q,
\qquad 0<B<5/12,
\tag{5}
$$

where $x$ is Wright's large scale parameter.

The condition $(k,L)=1$ requires one further check. For $q\mid d$, failure means

$$
q^2\mid r+1.
$$

Brun–Titchmarsh bounds these primes in lifted progressions modulo $5\alpha Lq$. Relative to (5), their total cost is

$$
O_B\left(\sum_{q\mid L}\frac1q\right)=o(1).
$$

For $q\nmid d$, coprimality of $k$ is already enforced by $t\ne0\pmod q$. This retains Wright's original exceptional-modulus and coprimality safeguards.

Summing (5) over $d\mid L$ gives the product

$$
\begin{aligned}
\prod_{q\mid L}\left(\frac q{q-1}+\rho_q\right)
&=\prod_{q\mid L}\frac{5q-7}{4(q-1)}\\
&=(1+o(1))\left(\frac54\right)^{\omega(L)}.
\end{aligned}
$$

Averaging over the possible $k$'s therefore proves the following adapted prime-pool statement:

$$
\boxed{
\begin{gathered}
\text{For arbitrarily large Wright-type }L,\text{ there exists }k\equiv4\pmod5,\\
(k,L)=1,\quad
\#\left\{d\mid L:
\begin{array}{l}
r=\alpha dk-1\text{ prime},\\
\chi_q(r)=-1,\ \chi_q(r+2)=1\quad(q\mid L)
\end{array}\right\}\\
\gg_\alpha
\frac{(5/4)^{\omega(L)}}{\log x}.
\end{gathered}
}
\tag{6}
$$

The right-hand side grows without bound in Wright's parameter range.

Yet every one of those prime values has composite companion $r+2$, by (4).

This is not a hypothetical parity model. It is an adaptation of the actual AGP/Wright prime-progression construction, with one fixed CRT constraint added and all the original prime values retained.

It does not show that other choices of $k$ lack twins. It proves the more relevant point: exponentially many one-sided primes, for one common parameter $k$, satisfying both quadratic signatures at every $q\mid L$, do not force even one prime companion among that pool.

3. The semiprime signature comparison gives no saving

Suppose

$$
s=t+1=uv
$$

with distinct primes $u,v$ not dividing $L$.

For every $q\mid L$, the new condition says

$$
\chi_q(uv)=1.
$$

Therefore

$$
\boxed{\chi_q(u)=\chi_q(v).}
\tag{7}
$$

Your proposed consequence is correct. But it does not imply that either factor has the positive signature individually.

Indeed, fix any nonzero quadratic-residue value $s\bmod q$. As $u$ ranges through $\mathbb F_q^\times$, the condition $v=su^{-1}$ gives:

Signatures of $(u,v)$
 |
Number of ordered residue pairs
 |

$(+1,+1)$
 |
$(q-1)/2$
 |

$(-1,-1)$
 |
$(q-1)/2$
 |

Opposite signs
 |
0
 |

Exactly the same conclusion holds when $q\mid d$, where $s\equiv1\pmod q$.

Thus the two-factor restriction is already entirely accounted for by $\chi_q(s)=1$.

For comparison, among independently chosen reduced residue classes:

$$
\begin{aligned}
\Pr(\chi_q(s)=1\mid s\text{ a single prime residue})&=\frac12,\\
\Pr(\chi_q(uv)=1\mid u,v\text{ prime residues})&=\frac12.
\end{aligned}
$$

Across all primes $q\mid L$, both have normalized local signature mass

$$
\boxed{2^{-\omega(L)}.}
$$

There are $2^{\omega(L)}$ possible common signature vectors for the pair $(u,v)$. Requiring those signatures to agree does not make the semiprime locally rarer than the single prime.

These are exact finite-field density calculations, not an assertion that shifted primes and semiprimes are globally equidistributed. The missing global comparison cannot be inferred from them.

The fixed factor $5$ is invisible to all the new signatures

The construction in §2 has an additional useful property. Since every $q\mid L$ satisfies $q\equiv1\pmod5$, quadratic reciprocity gives

$$
\boxed{\left(\frac5q\right)=\left(\frac q5\right)=1.}
$$

For every composite companion $s=5u$ in that construction,

$$
\chi_q(s)=1
\quad\Longrightarrow\quad
\boxed{\chi_q(u)=1}
$$

for every $q\mid L$.

So the auxiliary character conditions cannot even distinguish a number satisfying all the positive signatures from that same number multiplied by the fixed prime $5$.

This supplies an explicit arithmetic obstruction to trying to turn the common positive signatures into a primality certificate.

4. Why increasing the number of auxiliary primes does not eliminate that obstruction

One might hope that sufficiently many character conditions would make it impossible for two distinct prime factors to share the same signature vector.

Wright's parameter sizes do not support that inference.

His construction has

$$
\omega(L)\asymp\frac{\log x}{\log\log x}
$$

up to fixed construction-dependent constants. Consequently,

$$
2^{\omega(L)}=x^{o(1)}.
$$

Meanwhile, the range of possible prime factors below $\sqrt x$ contains on the order of

$$
\frac{\sqrt x}{\log x}
$$

primes.

There are far more potential prime factors than character-signature vectors. Even a distribution theorem placing those primes reasonably evenly among signatures would leave many primes sharing each signature.

More importantly, the fixed-factor construction of §2 remains valid for arbitrarily large $L$. Adding more quadratic-character tests does not remove the invisible factor $5$, because the selected auxiliary primes have been chosen so that $5$ is a quadratic residue at every one of them.

This rules out a straightforward signature-uniqueness forcing argument.

5. The remaining arithmetic requirement

Define the strengthened Wright pool

$$
\mathcal D(k)=
\left\{d\mid L:
\begin{array}{l}
\alpha dk-1\text{ prime},\\
\chi_q(\alpha dk-1)=-1,\\
\chi_q(\alpha dk+1)=1\quad\forall q\mid L
\end{array}
\right\}.
$$

The adapted progression theorem proves that some $k$ has

$$
|\mathcal D(k)|
\gg\frac{(5/4)^{\omega(L)}}{\log x}.
$$

But establishing twins requires the genuinely different lower bound

$$
\boxed{
\sum_{d\in\mathcal D(k)}
(\log(\alpha dk+1))
\mathbf1_{\{\alpha dk+1\text{ prime}\}}>0
}
\tag{8}
$$

for arbitrarily large parameters.

The construction with $k\equiv4\pmod5$ shows that even an exponentially large $\mathcal D(k)$ may make the entire left side exactly zero.

Wright's subgroup argument cannot repair this. It selects a long product of the already-known primes $\alpha dk-1$ having a prescribed multiplicative residue. The character conditions on $\alpha dk+1$ do not transform that long product into a new prime or guarantee a two-prime subproduct. Wright's group theorem controls product residues, not the number of prime factors of a companion integer.

arxiv.org

An attempt to exclude the fixed factor $5$ would only remove one example. To guarantee that a companion is prime, one ultimately needs to exclude every possible prime divisor up to its square root. The quadratic-signature restrictions do not do this, and the checked AGP/Wright progression results do not supply the necessary positive lower sieve for the two simultaneous prime forms.

Final verdict

The first part of the repair succeeds. The exact local residue count is

$$
\frac{q-5-2\chi_q(2)}4,
$$

and, with Wright's actual auxiliary primes, the modified common-parameter pool retains exponential base $5/4$.

The proposed semiprime suppression fails. Two prime factors with identical quadratic signatures have the same normalized positive-sign local density as one prime. There is no surviving local-density gain that favors a prime companion.

The strongest independent challenge is constructive: by imposing $q\equiv1\pmod5$ on the auxiliary primes and $k\equiv4\pmod5$, the same Wright–AGP mechanism produces an exponentially large common-$k$ prime pool satisfying both requested quadratic signatures while every companion $\alpha dk+1$ is composite.

Therefore, the additional signs can be incorporated successfully into the prime-pool construction, but the existing subgroup and progression theorems still do not establish (8).

The full twin-prime infinitude theorem has not been proved by this repair. The exact missing step is a positive matched-prime lower bound, not the supply of common parameters or local quadratic signatures.

---

### Recovered response 4

1. The automorphic input is genuinely stronger than ordinary residue information, but its exact scope matters

For $K=\mathbb Q(\sqrt{-23})$, let $\psi$ be a nontrivial character of its class group $C_3$. The associated weight-one theta newform has level $23$, nebentypus $\chi_{-23}$, and real Hecke eigenvalues $\lambda(n)$. Its coefficients at unramified rational primes are exactly as proposed.

Prime splitting types and coefficients

Type of prime $\ell\ne23$
 |
$\lambda(\ell)$
 |
Number of integral ideals of norm $\ell$, $a_K(\ell)$
 |

Inert
 |
0
 |
0
 |

Principal split
 |
2
 |
2
 |

Nonprincipal split
 |
−1
 |
2
 |

The key distinction is nonabelian class-field information: the two split-prime types are not separated by an ordinary congruence class.

I checked the two primary analytic statements.

Assing–Blomer–Li, Theorem 1.3 proves a power-saving estimate for a fixed cuspidal newform,

$$
\sum_{X<p\le2X}\Lambda(p)\lambda(p+2)\ll_\phi X^{1-\delta},
$$

in its stated newform setting, with polynomial conductor dependence. The shift $+2$ is admissible.

arxiv.org

Blomer–Grimmelt–Li–Rydin Myerson, Theorem 3.3 has the stronger divisor-sensitive shape

$$
\sum_{\substack{p\equiv-2\pmod d}}
\Lambda(p)\lambda\left(\frac{p+2}{d}\right)G(p)
\ll P^A X^{1-\eta},
$$

where, in this specialization,

$$
P\asymp d(1+|\mu_\phi|)N_\phi Z,
$$

and $G$ has the specified smoothness parameter $Z$.

Springer Nature Link

There is a scope qualification: the published BGLM §3 explicitly sets up its newforms with level divisible by $4$ and character $\chi_{-4}$, whereas the proposed form has level $23$ and character $\chi_{-23}$. Their discussion allows extensions to other fixed quadratic forms, but the quoted theorem cannot simply be substituted with level $23$ without establishing that extension.

pure.mpg.de

Even granting that fixed-field extension, the estimate has effective conductor cost $d^A$. Summing the individual estimates over all $d\le X^\kappa$ costs at most

$$
X^{1-\eta+(A+1)\kappa+o(1)}.
$$

It retains a power saving only when $(A+1)\kappa<\eta$. The exponent is not arbitrary, and this is not distribution at the full square-root factor scale.

The substantive question is therefore whether such cancellation, even in this favorable form, can make a nonnegative ideal-representation weight favor primes over semiprimes.

2. A positive ideal-representation main term exists—and composites carry essentially all of it

Let

$$
a_K(n)=\sum_{d\mid n}\chi_{-23}(d).
$$

This is the number of integral ideals of norm $n$ in $\mathcal O_K$, so $a_K(n)\ge0$.

Assing–Blomer–Li's Theorem 2.2 applies directly to $1*\chi_{-23}$, with the actual shift $+2$. It gives, for every fixed $A>0$,

$$
\boxed{
\sum_{X<p\le2X}\theta(p)a_K(p+2)
=C_{23}X+O_A(X/\log^A X),
}
\tag{1}
$$

where $\theta(p)=\log p$ on genuine primes and

$$
\begin{aligned}
C_{23}
&=\frac{21}{22}L(1,\chi_{-23})c(\chi_{-23},2)>0,\\
c(\chi,2)
&=\frac12\prod_{\ell>2}
\left(1+\frac{\chi(\ell)}{\ell(\ell-1)}\right).
\end{aligned}
$$

The factor $21/22$ comes from the two complementary divisor orientations in Theorem 2.2; retaining it matters.

arxiv.org

A genuine twin with $p+2\ne23$ contributes exactly $2\theta(p)$ to this sum. By the classical twin-prime upper sieve, the total contribution of genuine twins is at most $O(X/\log X)$.

It follows unconditionally that

$$
\boxed{
\sum_{\substack{X<p\le2X\\p+2\text{ composite}}}
\theta(p)a_K(p+2)
=C_{23}X+o(X).
}
\tag{2}
$$

So an entire positive main term from a genuine ideal-representation count is already known to come from composite shifted integers. This is a concrete failure of the simplest route from positive quadratic-form representations to twin primes.

The class-group projection makes the issue sharper. Let $a_0(n)$ count ideals of norm $n$ in the principal class and $a_1(n)$ count those in either specified nonprincipal class. Complex conjugation gives equal counts in the two nonprincipal classes, and

$$
\boxed{
a_0(n)=\frac{a_K(n)+2\lambda(n)}3,\qquad
a_1(n)=\frac{a_K(n)-\lambda(n)}3.
}
\tag{3}
$$

Both are nonnegative integers. A power-saving shifted-prime estimate for $\lambda(p+2)$, when applicable, changes the positive leading coefficient into $C_{23}/3$ for each class; it does not create a prime-supported main term. The composite contribution in (2) is too large.

3. Exact prime–semiprime coefficients expose a linear-separation obstruction

The following table is obtained by multiplying ideal-class characters, not by a statistical model. It applies to distinct unramified split primes; entries are ordered by their classes in $C_3$.

Factorization of $n$
 |
$a_K(n)$
 |
$\lambda(n)$
 |
$a_0(n)$
 |
$a_1(n)$
 |

Principal split prime
 |
2
 |
2
 |
2
 |
0
 |

Nonprincipal split prime
 |
2
 |
−1
 |
0
 |
1
 |

Two principal split primes
 |
4
 |
4
 |
4
 |
0
 |

Principal × nonprincipal split primes
 |
4
 |
−2
 |
0
 |
2
 |

Two nonprincipal split primes
 |
4
 |
1
 |
2
 |
1
 |

Contains an inert prime to exponent one
 |
0
 |
0
 |
0
 |
0
 |

The decisive equalities are

$$
\begin{aligned}
(a_K,\lambda)(r_1r_2)
&=2(a_K,\lambda)(r_1)
&&\text{when both primes are principal split},\\
(a_K,\lambda)(r_1r_2)
&=2(a_K,\lambda)(r_2)
&&\text{when one is principal and one nonprincipal split}.
\end{aligned}
$$

These imply a useful impossibility theorem.

Linear-separation lemma. No affine function

$$
L(n)=c+\alpha a_K(n)+\beta\lambda(n)
$$

can be positive on either selected split-prime type, nonpositive on every squarefree semiprime type, and nonpositive on the inert semiprime type.

Proof. Inert semiprimes have $a_K=\lambda=0$, so $c\le0$. If a split prime has $L>0$, write $v=\alpha a_K+\beta\lambda$ at that prime. Then $v>-c\ge0$. Choose the corresponding semiprime whose coefficient vector is twice the prime vector. Its value is

$$
c+2v>c-2c=-c\ge0,
$$

contradicting nonpositivity. The same argument works for either split-prime class.

Since every linear combination of the two ideal-class counts $a_0,a_1$ is also a linear combination of $a_K,\lambda$, no first-moment linear class-character weight supplies a pointwise twin-prime minorant on the full prime-or-semiprime population.

This is stronger than insufficient analytic precision: even perfect first-moment estimates for these two automorphic coefficients cannot produce such a sign separator.

4. The nonlinear repair has an exact favorable sign

There is nevertheless a different arithmetic possibility. The total ideal-norm count $a_K$ itself distinguishes a split prime from a product of two distinct split primes:

$$
a_K(\ell)=2,\qquad a_K(\ell_1\ell_2)=4.
$$

Define

$$
\boxed{\mathcal W(n)=3a_K(n)-a_K(n)^2.}
\tag{4}
$$

For squarefree $n$ with at most two prime factors, coprime to $23$,

$$
\mathcal W(n)=
\begin{cases}
+2,&n\text{ is a split prime},\\
-4,&n\text{ is a product of two split primes},\\
0,&\text{any factor is inert}.
\end{cases}
\tag{5}
$$

Choose the actual cutoff $z=(2X+2)^{1/3}$. On primes $p\in(X,2X]$ with $P^-(p+2)>z$, the only exceptions to (5) are prime squares. Their total contribution to the $\theta(p)$-weighted sum is $O(\sqrt X\log X)$.

Thus, after excluding $23\mid p+2$, the exact signed prime-supported sum is

$$
\boxed{
\begin{aligned}
\mathcal D_X
&=\sum_{\substack{X<p\le2X\\
P^-(p+2)>z\\(p+2,23)=1}}
\theta(p)\mathcal W(p+2)\\
&=2T_{\mathrm{split}}(X)-4S_{\mathrm{split,split}}(X)
+O(\sqrt X\log X),
\end{aligned}
}
\tag{6}
$$

where $T_{\mathrm{split}}$ is the weighted genuine-twin count with split upper prime and $S_{\mathrm{split,split}}$ counts shifted products of two distinct split primes.

This is an exact one-sided separator: positivity of $\mathcal D_X$ at a sufficiently large scale would force genuine twins. But it is quadratic in the ideal-norm representation count, whereas the cited cusp-form estimates are linear in $\lambda$. Evaluating that quadratic term is a different analytic problem.

5. The precise nonlinear cost is a four-character divisor correlation

The nonlinear repair in (4) has an exact Dirichlet-series description:

$$
\boxed{
\sum_{n\ge1}\frac{a_K(n)^2}{n^s}
=
\frac{\zeta(s)^2L(s,\chi_{-23})^2}
{\zeta(2s)(1+23^{-s})},
\qquad \Re s>1.
}
\tag{7}
$$

This follows directly from the prime-power coefficients. At a split prime the local generating function is $(1+x)/(1-x)^3$; at an inert prime it is $1/(1-x^2)$; the final factor corrects the ramified prime $23$.

It has a double pole at $s=1$. In particular, the ordinary-integer mean satisfies

$$
\sum_{n\le X}a_K(n)^2
\sim
\frac{23L(1,\chi_{-23})^2}{24\zeta(2)}X\log X.
$$

This is an established consequence of the Euler product, not an estimate on shifted primes.

For squarefree $n$ coprime to $23$, one gets the stronger exact convolution identities

$$
\boxed{
a_K(n)^2=(a_K*a_K)(n),\qquad
\lambda(n)^2=(a_K*\lambda)(n).
}
\tag{8}
$$

The second identity holds because, at each unramified rational prime,

$$
\lambda(\ell)^2=a_K(\ell)+\lambda(\ell),
$$

and all three functions are multiplicative at coprime arguments.

For a split semiprime $n=qr$, equation (8) opens to

$$
\boxed{
\lambda(qr)^2
=a_K(qr)+\lambda(qr)
+a_K(q)\lambda(r)+a_K(r)\lambda(q).
}
\tag{9}
$$

The last two terms are the genuine composite cross-divisor contributions. They can be positive or negative. Applying the prime identity $\lambda(\ell)^2=a_K(\ell)+\lambda(\ell)$ directly to a semiprime would omit them.

Now compare (8) with BGLM Theorem 3.3. Expanding the shifted convolution produces terms of the form

$$
\sum_{\substack{X<p\le2X\\d\mid p+2}}
\theta(p)\,a_K(d)\,
\lambda\left(\frac{p+2}{d}\right).
$$

For sufficiently small $d$, the cusp coefficient has a power-saving estimate in the applicable automorphic setting.

But if

$$
p+2=qr,\qquad q,r>X^{1/3},
$$

the proper divisors $q,r$ themselves exceed $X^{1/3}$. A conductor range $d\le X^\kappa$ with a small $\kappa$ sees none of these divisors. It retains only the $d=1$ term and misses precisely the terms responsible for distinguishing the two-factor product.

Thus the missing analytic quantity is not another individual Hecke coefficient. It is a large-divisor convolution over the balanced semiprime region. The quoted fixed-cusp power savings do not evaluate it.

6. The nonnegative ideal-norm sieve has effective dimension one, not one-half

I also checked the proposed positive-majorant sieve at the local level.

Fix an unramified prime $\ell>2$. Among genuine outer primes $p$, the local densities for $v_\ell(p+2)$ are

$$
\Pr(v_\ell(p+2)=0)=\frac{\ell-2}{\ell-1},
\qquad
\Pr(v_\ell(p+2)=e)=\ell^{-e}\quad(e\ge1).
$$

For split $\ell$, the ideal-norm coefficient is $a_K(\ell^e)=e+1$. Therefore the normalized local fraction of the $a_K$-weighted mass supported on $\ell\mid p+2$ is

$$
\boxed{
g_K(\ell)=\frac{2\ell-1}{\ell^2-\ell+1}
=\frac2\ell+O(\ell^{-2}).
}
$$

For inert $\ell$, $a_K(\ell^{2e+1})=0$ and $a_K(\ell^{2e})=1$, giving

$$
\boxed{
g_K(\ell)=\frac1{\ell^2-\ell-1}
=O(\ell^{-2}).
}
$$

Split primes have reciprocal-prime density one-half, so

$$
\sum_{\substack{\ell\le z\\\ell\text{ split}}}g_K(\ell)
=\log\log z+O(1).
$$

Therefore the ideal-norm-weighted source has sieve dimension one. The factor $2$ from the two prime ideals above each split rational prime exactly offsets the density-one-half restriction on split primes.

This calculation describes the correct local sieve model; it does not assert an unproved global equidistribution theorem for all growing moduli.

The consequence is still decisive for the direct lower sieve. At a cutoff $z\asymp X^{1/3}$, a dimension-one lower linear sieve needs level

$$
D>z^2\asymp X^{2/3}.
$$

Bombieri–Vinogradov supplies only level $X^{1/2-o(1)}$ on the underlying rational-prime source. The cusp-form bound with polynomial conductor dependence does not replace this missing level for the nonnegative Eisenstein/ideal-norm weight.

So the anticipated half-dimensional advantage does not survive the multiplicity of ideal representations.

7. Chen's positive lower bound does not overcome the class-group obstruction

The strongest relevant positive input is the Chen-prime lower bound in Bienvenu–Shao–Teräväinen, Proposition 5.2: there are $\gg X/\log^2X$ primes $p\asymp X$ for which $p+2$ is prime or semiprime, with every prime factor exceeding $X^{1/10-o(1)}$.

utupub.fi

I tested whether this positivity, together with ideal-norm counts and a hypothetically perfect cuspidal cancellation estimate, could force a twin.

Let $T_0,T_1$ be weighted counts of shifted primes $p+2$ in the principal and nonprincipal split classes. Let $S_{00},S_{01},S_{11}$ count the three corresponding types of products of two split primes.

The class-group table gives

$$
\begin{aligned}
\sum\theta(p)a_K(p+2)
&=2(T_0+T_1)+4(S_{00}+S_{01}+S_{11}),\\
\sum\theta(p)\lambda(p+2)
&=2T_0-T_1+4S_{00}-2S_{01}+S_{11}.
\end{aligned}
\tag{10}
$$

There is an exact obstruction to the proposed inference. Set

$$
T_0=T_1=S_{11}=0,\qquad
S_{00}=t,\quad S_{01}=2t,\quad t>0.
$$

Then the norm-count moment is $12t>0$, while the cusp moment is exactly zero. Moreover, the principal and nonprincipal ideal-class moments are equal and positive.

This is an algebraic feasibility test, not a claim that actual shifted primes realize these proportions. It proves that even perfectly evaluated linear class-character first moments, together with a positive Chen population, do not logically exclude the all-composite alternative.

The critical semiprime upper bound

The split-semiprime contribution can be bounded unconditionally. Write

$$
p+2=qr,\qquad
X^{1/3}<q\le r,\qquad q,r\text{ prime}.
$$

For fixed $q$, apply the upper-bound sieve to

$$
r,\qquad qr-2.
$$

The determinant is $2$, and the local factor for primes dividing $q$ is $(\ell-1)/(\ell-2)$. Summing over $q$ gives

$$
\boxed{
S_{\mathrm{split,split}}(X)\ll\frac X{\log X}.
}
\tag{11}
$$

The logarithmic factor-size integral is

$$
\int_{1/3}^{1/2}\frac{dt}{t(1-t)^2}
=\frac12+\log2.
$$

Restricting both factors to split classes cannot increase this bound.

But $X/\log X$ is also the natural scale of the weighted twin-prime count. Equation (11) supplies no $o(X/\log X)$ contamination estimate, nor a strict constant comparison with an independent lower bound.

This is the hardest factor interval for the proposed automorphic approach. Its nontrivial divisors are larger than the permitted small-conductor range, and its semiprime contribution remains at the decisive scale.

8. The missing forcing inequality and final verdict

The investigation produces an exact, class-group-sensitive sign test:

$$
\mathcal D_X
=
2T_{\mathrm{split}}(X)-4S_{\mathrm{split,split}}(X)
+O(\sqrt X\log X).
$$

To turn it into a proof, one would need an independently established positive lower bound for $\mathcal D_X$ on arbitrarily large scales.

The cited automorphic theorems do not supply that bound:

-

ABL evaluates the positive two-character Eisenstein convolution $a_K=1*\chi_{-23}$, but its order-$X$ main is already carried by composites.

-

The shifted cusp estimate controls a linear coefficient $\lambda$, not the quadratic norm-count term $a_K^2$.

-

BGLM supplies polynomial-conductor power savings for divisor-sensitive cusp sums in its stated setting, not the required large-divisor four-character convolution at $d\asymp X^{1/3}$ or beyond.

-

Chen's lower bound supplies prime-or-semiprime mass, but no strict class-sensitive inequality separating the two outcomes.

The precise missing analytic estimate is a one-sided shifted-prime lower bound for the nonlinear class-group statistic, retaining the products of two split primes with their full negative coefficient. Merely improving the power saving for a single cusp-form coefficient would not establish it.

My strongest independently established results from this attempt are the exact class-group convolution identities (3) and (8), the linear-separation impossibility lemma, the positive shifted Eisenstein asymptotic (1), and the exact signed prime-versus-semiprime decomposition (6).

Final verdict: The $K=\mathbb Q(\sqrt{-23})$ approach supplies genuine factor-sensitive information beyond Dirichlet characters, but no checked primary theorem turns it into a strict positive twin-prime lower bound. The original unconditional infinitude target remains unproved by this route.

---

## Twin prime proof planning

[Original conversation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6b031c45-7ab0-83e8-b305-61b653af4a75)

### Recovered response 1

Two-stage half-dimensional sieve: verification and cofactor bound

The proposed unconditional first stage is valid. Both sieves can be combined within the ordinary Bombieri–Vinogradov range, and the resulting positive lower bound counts genuine primes $p$, not modeled integers.

The remaining question is whether the composite cofactors $u>1$ can be bounded below that positive main term. The semiprime part alone has an explicit upper constant, but the complete cofactor population is substantially larger.

1. Exact factorization after the first sieve

Let

$$
z=(2X+2)^{1/3},\qquad y=X^\varepsilon,
$$

and define

$$
\mathcal S_\varepsilon(X)=
\left\{
X<p\le2X:
\begin{array}{l}
p\text{ prime},\ p\equiv1\pmod4,\\
\ell\mid p+2,\ \ell\equiv3\pmod4\Rightarrow\ell>z,\\
\ell\mid p+2,\ \ell\equiv1\pmod4\Rightarrow\ell>y
\end{array}
\right\}.
$$

Because $p+2\equiv3\pmod4$, its number of $3\bmod4$ prime factors, counted with multiplicity, is odd.

Three such factors would give

$$
p+2>z^3=2X+2,
$$

which is impossible. Therefore every member of the source has a unique factorization

$$
\boxed{
p+2=ru,\quad
r>z\text{ prime},\ r\equiv3\pmod4,
\quad
\ell\mid u\Rightarrow\ell\equiv1\pmod4,\ \ell>y.
}
\tag{1}
$$

The cases are exactly $u=1$, giving genuine twins; $u$ prime, giving semiprime neighbors; and $u$ composite, giving at least three prime factors of $p+2$, counted with multiplicity.

2. The combined lower sieve

For a squarefree odd divisor $d$, the required prime progression is

$$
p\equiv1\pmod4,\qquad p\equiv-2\pmod d.
$$

It is reduced, and the prime number theorem gives the local density

$$
g(d)=\frac1{\varphi(d)}
$$

relative to primes $p\equiv1\pmod4$.

Take separate half-dimensional lower and upper weights for the $3\bmod4$ and $1\bmod4$ prime sets, at levels

$$
D_3=X^{0.4},\qquad D_1=X^{0.05}.
$$

The first sifting ratio is

$$
s_3=\frac{\log D_3}{\log z}=\frac65+o(1).
$$

The second is

$$
s_1=\frac{\log D_1}{\log y}=\frac{0.05}{\varepsilon}.
$$

Iwaniec's half-dimensional sieve has $f_{1/2}(s)>0$ for $s>1$. For $1\le s\le2$, its exact normalization is

$$
\begin{aligned}
f_{1/2}(s)&=
\sqrt{\frac{e^\gamma}{\pi s}}
\int_1^s\frac{dt}{\sqrt{t(t-1)}},\\
F_{1/2}(s)&=2\sqrt{\frac{e^\gamma}{\pi s}}.
\end{aligned}
$$

These formulas are from Iwaniec's original The Half Dimensional Sieve, Theorem 1.

matwbn.icm.edu.pl

Let $R_3,R_1$ be the two exact roughness indicators, with sieve bounds $L_i\le R_i\le U_i$. The proposed product minorant is pointwise valid:

$$
\boxed{
R_3R_1\ge L_3U_1-U_3(U_1-L_1).
}
\tag{2}
$$

All opened moduli are products $d_3d_1\le X^{0.45}$. Since the two prime classes are disjoint, their sieve-weight products have no hidden multiple representations. Ordinary weighted Bombieri–Vinogradov, applied to moduli $4d_3d_1$, gives an error smaller than $X/\log^A X$ for every prescribed fixed $A$, after accounting for the fixed divisor-weight losses.

The main terms of the two half-dimensional sieve bounds give

$$
\boxed{
\begin{aligned}
|\mathcal S_\varepsilon(X)|
\ge\bigl(c_\varepsilon+o_\varepsilon(1)\bigr)
\frac{X}{(\log X)^2},\\
c_\varepsilon=
C_2e^{-\gamma}\sqrt{\frac3\varepsilon}
\Big[
f_{1/2}(s_3)f_{1/2}(s_1)
-\big(F_{1/2}(s_3)-f_{1/2}(s_3)\big)
\big(F_{1/2}(s_1)-f_{1/2}(s_1)\big)
\Big],
\end{aligned}}
\tag{3}
$$

where

$$
C_2=\prod_{\ell>2}\left(1-\frac1{(\ell-1)^2}\right).
$$

As $\varepsilon\downarrow0$, both $f_{1/2}(s_1)$ and $F_{1/2}(s_1)$ tend to $1$. Consequently,

$$
\boxed{
c_\varepsilon\sim
C_2e^{-\gamma}\sqrt{\frac3\varepsilon}
f_{1/2}(6/5)>0.
}
\tag{4}
$$

This proves the claimed unconditional first-stage lower bound for every sufficiently small fixed $\varepsilon>0$.

It does not yet distinguish $u=1$ from the composite cofactors in (1).

3. The semiprime cofactor has an explicit upper constant

Let $N_{2,\varepsilon}(X)$ count members of $\mathcal S_\varepsilon(X)$ with

$$
p+2=rs,\qquad
r>z,\ r\equiv3\pmod4,\qquad
s>y,\ s\equiv1\pmod4,
$$

where $r,s$ are primes.

Fix $s$. The remaining conditions are

$$
r\equiv3\pmod4,\qquad
r\text{ prime},\qquad sr-2\text{ prime}.
$$

Writing $r=4t+3$, the two prime-valued forms become

$$
4t+3,\qquad 4st+3s-2.
$$

At each odd prime $\ell\ne s$, they exclude two distinct residue classes; at $\ell=s$, they exclude one.

An elementary Selberg upper sieve gives, uniformly for $s\ge X^\varepsilon$ and $R=X/s\ge X^{1/3+o(1)}$,

$$
\boxed{
\#\{R<r\le2R:r\equiv3\ (4),\
r,\ sr-2\text{ prime}\}
\le(8C_2+o_\varepsilon(1))
\frac{R}{(\log R)^2}\frac{s-1}{s-2}.
}
\tag{5}
$$

For completeness, its Selberg denominator is

$$
G_s(Z)=
\sum_{\substack{d\le Z\\d\ {\rm odd,\ squarefree}}}
\prod_{\ell\mid d}\frac{\nu_s(\ell)}{\ell-\nu_s(\ell)}
\sim
\frac{(\log Z)^2}{8C_2}\frac{s-2}{s-1},
$$

with $\nu_s(\ell)=2$ except $\nu_s(s)=1$. Taking $Z=R^{1/2}/(\log R)^B$ and $B$ sufficiently large makes the Selberg remainder negligible compared with $R/\log^2R$. This uses the standard Selberg quadratic upper-bound sieve, not an unproved prime-pair asymptotic.

Sum (5) over the genuine primes $s\equiv1\pmod4$, with

$$
X^\varepsilon<s\le(2X+2)/z.
$$

The prime number theorem in that progression yields

$$
\boxed{
N_{2,\varepsilon}(X)
\le
\left(4C_2 I_\varepsilon+o_\varepsilon(1)\right)
\frac{X}{(\log X)^2},
}
\tag{6}
$$

where the entire angular constant is

$$
\begin{aligned}
I_\varepsilon
&=\int_\varepsilon^{2/3}
\frac{d\beta}{\beta(1-\beta)^2}\\
&=\boxed{
\log\frac{2(1-\varepsilon)}{\varepsilon}
+3-\frac1{1-\varepsilon}.
}
\end{aligned}
\tag{7}
$$

This includes the region where $s$ exceeds $\sqrt X$; there is no symmetry factor of $1/2$, because the $3\bmod4$ factor $r$ is uniquely identified.

As $\varepsilon\downarrow0$,

$$
4C_2I_\varepsilon
=
4C_2\bigl(\log(1/\varepsilon)+O(1)\bigr).
$$

By comparison, the proved source lower constant in (4) grows like $1/\sqrt\varepsilon$.

The semiprime upper bound alone is therefore too small to account for the entire guaranteed source when $\varepsilon$ is sufficiently small. But that does not force twins: cofactors containing two or more permitted $1\bmod4$ prime factors have not yet been charged.

4. Upper bound for the entire composite cofactor population

The semiprime estimate is not sufficient. We must charge every

$$
u>1,\qquad
\ell\mid u\Longrightarrow
\ell\equiv1\pmod4,\quad \ell>X^\varepsilon.
$$

This can also be done unconditionally, using the same two-linear-form sieve.

For a fixed $u$, count primes $r\equiv3\pmod4$ for which $ru-2$ is prime. The local singular-series correction is

$$
\mathfrak s(u)=
\prod_{\ell\mid u}\frac{\ell-1}{\ell-2}.
$$

Since $u\le(2X+2)/z$, and every prime factor of $u$ exceeds $X^\varepsilon$,

$$
\omega(u)\le\frac{2}{3\varepsilon}+o(1),
\qquad
\mathfrak s(u)=1+o_\varepsilon(1)
$$

uniformly.

Thus (5) gives

$$
\boxed{
N_{\mathrm{comp},\varepsilon}(X)
\le
(8C_2+o_\varepsilon(1))X
\sum_{\substack{1<u\le(2X+2)/z\\
\ell\mid u\Rightarrow\ell\equiv1(4),\ \ell>X^\varepsilon}}
\frac1{u\log^2(X/u)}.
}
\tag{8}
$$

Unlike a semiprime-only bound, this includes cofactors with arbitrarily many permitted factors, subject to the size restriction.

Evaluating the complete harmonic cofactor constant

For fixed $\varepsilon$, at most $\lfloor2/(3\varepsilon)\rfloor$ prime factors can occur. Repeated prime factors have negligible harmonic mass, so the prime number theorem modulo $4$ evaluates the sum in (8).

Define

$$
\boxed{
H_\varepsilon=
\sum_{j\ge1}\frac1{2^j j!}
\int_{\substack{\beta_1,\ldots,\beta_j\ge\varepsilon\\
\beta_1+\cdots+\beta_j\le2/3}}
\frac{d\beta_1\cdots d\beta_j}
{\beta_1\cdots\beta_j
(1-\beta_1-\cdots-\beta_j)^2}.
}
\tag{9}
$$

The factor $2^{-j}$ comes from restricting every cofactor prime to $1\bmod4$, and $j!$ removes ordering multiplicity.

Then

$$
\boxed{
N_{\mathrm{comp},\varepsilon}(X)
\le
\left(8C_2H_\varepsilon+o_\varepsilon(1)\right)
\frac{X}{(\log X)^2}.
}
\tag{10}
$$

The $j=1$ part is exactly $H_\varepsilon^{(1)}=I_\varepsilon/2$, recovering the semiprime constant (6).

The full constant is much larger than the semiprime constant

The size of $H_\varepsilon$ can be calculated analytically as $\varepsilon\downarrow0$.

Let $\sigma_\varepsilon$ be the positive measure whose Laplace transform is

$$
\int_0^\infty e^{-sv}\,d\sigma_\varepsilon(v)
=
\exp\left(
\frac12\int_\varepsilon^\infty\frac{e^{-st}}t\,dt
\right).
$$

Its convolution expansion is precisely the measure underlying (9), including the atom at zero corresponding to $u=1$.

For fixed $s>0$,

$$
\int_\varepsilon^\infty\frac{e^{-st}}t\,dt
=-\gamma-\log(s\varepsilon)+o(1).
$$

Consequently,

$$
\sqrt\varepsilon\,d\sigma_\varepsilon(v)
\longrightarrow
\frac{e^{-\gamma/2}}{\sqrt\pi}\,
v^{-1/2}\,dv
$$

weakly on bounded intervals.

Therefore

$$
\boxed{
H_\varepsilon\sim
\frac{e^{-\gamma/2}}{\sqrt{\pi\varepsilon}}
\int_0^{2/3}\frac{dv}{\sqrt v(1-v)^2}.
}
\tag{11}
$$

The integral has the exact value

$$
\boxed{
\int_0^{2/3}\frac{dv}{\sqrt v(1-v)^2}
=
\sqrt6+\operatorname{arctanh}\sqrt{\frac23}.
}
\tag{12}
$$

Thus the complete composite upper allowance is of order

$$
\boxed{\frac{X}{\sqrt\varepsilon\,(\log X)^2},}
$$

not merely $X\log(1/\varepsilon)/\log^2X$.

This is the same dependence on $\varepsilon$ as the positive source lower bound.

5. The constants do not leave a positive twin-prime margin

Write

$$
J_0=\int_1^{6/5}\frac{dt}{\sqrt{t(t-1)}}
=\log\frac{7+2\sqrt6}{5}
$$

and

$$
I_0=\sqrt6+\operatorname{arctanh}\sqrt{\frac23}.
$$

From (4),

$$
c_\varepsilon\sim
\frac{C_2e^{-\gamma}\sqrt3}{\sqrt\varepsilon}
\sqrt{\frac{e^\gamma}{\pi(6/5)}}\,J_0.
$$

From (10)–(12), the complete composite upper constant is asymptotic to

$$
\frac{8C_2e^{-\gamma/2}}{\sqrt{\pi\varepsilon}}I_0.
$$

Their ratio is exactly

$$
\boxed{
\frac{8C_2H_\varepsilon}{c_\varepsilon}
\longrightarrow
8\sqrt{\frac25}\frac{I_0}{J_0}>1.
}
\tag{13}
$$

The strict inequality follows directly from the integral expressions, without numerical approximation.

In fact, using

$$
I_0>2\sqrt{\frac23},
\qquad
J_0<\frac2{\sqrt5},
$$

gives the explicit lower bound

$$
\boxed{
8\sqrt{\frac25}\frac{I_0}{J_0}
>\frac{16}{\sqrt3}.
}
\tag{14}
$$

Hence the available switched upper sieve permits a composite-cofactor contribution more than nine times the guaranteed source lower constant, in the small-$\varepsilon$ limit.

This is an allowance, not a claim that actual composites attain that upper bound.

The lower-bound subtraction consequently gives only

$$
\boxed{
\begin{aligned}
N_{\mathrm{twins},\varepsilon}(X)
&=|\mathcal S_\varepsilon(X)|
-N_{\mathrm{comp},\varepsilon}(X)\\
&\ge
\left(c_\varepsilon-8C_2H_\varepsilon
+o_\varepsilon(1)\right)
\frac X{\log^2X},
\end{aligned}}
\tag{15}
$$

whose displayed leading coefficient is negative for all sufficiently small fixed $\varepsilon$.

Taking a smaller presieving exponent does not repair the loss. It increases the guaranteed source and the available composite allowance at the same $1/\sqrt\varepsilon$ order.

6. Exact outcome

The unconditional part of the construction is established:

$$
\boxed{
|\mathcal S_\varepsilon(X)|
\gg_\varepsilon\frac X{\log^2X}
}
$$

for all sufficiently small fixed $\varepsilon$. Every member has precisely one $3\bmod4$ prime factor larger than the cube-root cutoff, and its remaining cofactor is composed exclusively of $1\bmod4$ primes exceeding $X^\varepsilon$.

The semiprime cofactor costs at most

$$
\boxed{
\left[
4C_2\left(
\log\frac{2(1-\varepsilon)}{\varepsilon}
+3-\frac1{1-\varepsilon}
\right)
+o_\varepsilon(1)
\right]\frac X{\log^2X}.
}
$$

But the complete composite cofactor upper bound has the much larger constant $8C_2H_\varepsilon$. Its higher-rank terms are not negligible and cannot be omitted.

Decision: The direct two-stage half-dimensional sieve succeeds as an unconditional prime-supported construction, but the proposed complementary-factor upper sieve does not establish $u=1$. The precise failure is the full composite-cofactor constant in (9)–(14), not the semiprime region alone.

No strict positive remainder for genuine twin primes is obtained. This attempt therefore stops at its demonstrated cofactor bound, without treating its positive almost-prime population as a proof of twin-prime infinitude.

---

### Recovered response 2

Cubic-residue minorant: pointwise proof and analytic test

The proposed minorant is valid on the squarefree rough source. It equals $1$ for a prime $n=p-2$, equals $0$ for a semiprime, and is nonpositive for every remaining factorization.

The difficulty is not the minorant's sign. Its squared cubic-character sum has a principal diagonal that cancels the entire positive unit term on semiprimes and exceeds it on three- and four-factor integers. This happens even in the correctly conditioned cubic-residue model.

1. Exact pointwise classification

Let $K=\mathbb Q(\omega)$, with $\omega^3=1$, $\omega\ne1$. For a rational prime $p\equiv1\pmod3$, choose $\pi$ with $N\pi=p$, and put

$$
n=p-2,\qquad c=\chi_\pi(-2)\ne1.
$$

Because $n\equiv-2\pmod\pi$,

$$
\boxed{\chi_\pi(n)=c\in\{\omega,\omega^2\}.}
\tag{1}
$$

Choose $1/5<\alpha<1/4$ and $z=X^\alpha$. Suppose $n\in(X-2,2X-2]$ is squarefree and $P^-(n)>z$.

For sufficiently large $X$, $n$ has at most four prime factors. Define

$$
\mathcal D(n)=\{d:d\mid n,\ 1<d<\sqrt n\},
\qquad
M_\pi(n)=\sum_{d\in\mathcal D(n)}\mu(d)\chi_\pi(d).
$$

There are four possibilities.

One prime factor. The divisor set is empty, so $M_\pi(n)=0$ and $1-|M_\pi(n)|^2=1$.

Two prime factors. Exactly the smaller prime belongs to $\mathcal D(n)$, so $M_\pi(n)=-\chi_\pi(d)$ and

$$
\boxed{1-|M_\pi(n)|^2=0.}
$$

Three prime factors. Write $n=abc$, with $a<b<c$, and put $x=\chi_\pi(a)$, $y=\chi_\pi(b)$, $w=\chi_\pi(c)$.

If $c<\sqrt n$, all three prime factors occur in $\mathcal D(n)$, but none of their pair products does. Thus

$$
M_\pi(n)=-(x+y+w).
$$

Three cube roots of unity sum to zero only when they are $1,\omega,\omega^2$, whose product is $1$. This contradicts $xyw=c\ne1$. More strongly, the character constraint forces two roots to be equal and the third different, so

$$
\boxed{|M_\pi(n)|^2=3,\qquad1-|M_\pi(n)|^2=-2.}
\tag{2}
$$

If $c>\sqrt n$, the retained divisors are $a,b,ab$, giving

$$
M_\pi(n)=xy-x-y.
$$

The equation $xy=x+y$ is impossible for cube roots of unity. Checking the three algebraic possibilities for the unordered pair $\{x,y\}$, up to the conjugate cases, gives

$$
\boxed{|M_\pi(n)|^2\in\{1,4,7\}.}
\tag{3}
$$

Thus the minorant is respectively $0,-3$, or $-6$.

Four prime factors. Write $n=abcd$. All four individual prime factors are smaller than $\sqrt n$, because $\alpha>1/5$. Among the six pair products, exactly three are smaller than $\sqrt n$, one from each complementary pair.

Hence $M_\pi(n)$ has four negative singleton terms and three positive pair terms.

In the Eisenstein integer ring, reduce modulo the prime ideal $(1-\omega)$. Every cube root of unity becomes $1$, so

$$
\boxed{
M_\pi(n)\equiv-4+3=-1\pmod{1-\omega}.
}
\tag{4}
$$

Therefore $M_\pi(n)\ne0$. Moreover its algebraic norm satisfies

$$
|M_\pi(n)|^2\equiv1\pmod3,
$$

so

$$
\boxed{1-|M_\pi(n)|^2\in\{0,-3,-6,\ldots\}.}
\tag{5}
$$

We have proved the proposed pointwise implication:

$$
\boxed{
1-|M_\pi(p-2)|^2
\le\mathbf1_{\{p-2\text{ prime}\}}
}
\tag{6}
$$

on the squarefree, $X^\alpha$-rough source with $\chi_\pi(-2)\ne1$.

The minorant is independent of the choice between $\pi$ and $\bar\pi$: conjugation conjugates every cubic character value and leaves its squared absolute value unchanged.

2. Removing squareful contamination

This step is unconditional.

If $n=p-2$ is $z$-rough and not squarefree, some prime $\ell>z$ satisfies $\ell^2\mid n$. The number of possible integers $n$ in the dyadic interval is at most

$$
\begin{aligned}
\sum_{z<\ell\le\sqrt{2X}}
\left(\frac{2X}{\ell^2}+1\right)
&\ll\frac Xz+\sqrt X\\
&=\boxed{O(X^{1-\alpha}+\sqrt X)}.
\end{aligned}
\tag{7}
$$

Because $\Omega(n)\le4$ throughout the rough source for large $X$, we also have $\tau(n)\le16$ and

$$
|1-|M_\pi(n)|^2|\le257.
$$

Thus deleting all squareful $n$ costs

$$
\boxed{
O(X^{1-\alpha}+\sqrt X)
=o(X/\log^A X)
}
\tag{8}
$$

for every fixed $A>0$, even before restricting to the upper primes $p$.

There is no additional ramification error at $2$ or $3$: $n=p-2$ is odd and $n\equiv2\pmod3$. Also $p>n$, so none of the divisors of $n$ is divisible by $\pi$.

3. The exact diagonal and the signed off-diagonal sum

Let $\mathcal P_\alpha(X)$ be the genuine rational primes $p\in(X,2X]$ satisfying

$$
p\equiv1\pmod3,\qquad
\chi_\pi(-2)\ne1,\qquad
\mu^2(p-2)=1,\qquad
P^-(p-2)>X^\alpha.
$$

Define

$$
\mathcal S_\alpha(X)=
\sum_{p\in\mathcal P_\alpha(X)}
\left(1-|M_\pi(p-2)|^2\right).
$$

A positive value would prove at least one genuine twin pair in the interval. Positivity on unbounded scales would prove the conjecture.

Expand the square exactly:

$$
|M_\pi(n)|^2=
\sum_{d,e\in\mathcal D(n)}
\mu(d)\mu(e)\chi_\pi(d)\overline{\chi_\pi(e)}.
$$

For squarefree $n$ with $r=\omega(n)$, complementary divisors occur in pairs across $\sqrt n$. Consequently,

$$
\boxed{|\mathcal D(n)|=2^{r-1}-1.}
\tag{9}
$$

This is the full principal $d=e$ contribution.

Principal diagonal by factor rank

$\omega(n)$
 |
Number of diagonal terms
 |
Constant $1$ minus diagonal
 |

1
 |
0
 |
+1
 |

2
 |
1
 |
0
 |

3
 |
3
 |
−2
 |

4
 |
7
 |
−6
 |

For $d\ne e$, put $g=(d,e)$, $d=gd_1$, $e=ge_1$. Squarefreeness gives

$$
\boxed{
\mu(d)\mu(e)\chi_\pi(d)\overline{\chi_\pi(e)}
=
\mu(d_1)\mu(e_1)
\chi_\pi(d_1)\overline{\chi_\pi(e_1)}.
}
\tag{10}
$$

Thus common prime factors cancel from both the Möbius sign and the cubic phase. They do not disappear from the divisibility condition.

Let $\mathfrak O_\alpha(X)$ denote the complete sum over $d\ne e$, including both orientations. Then

$$
\boxed{
\mathcal S_\alpha(X)
=
N_1(X)-2N_3(X)-6N_4(X)
-\mathfrak O_\alpha(X),
}
\tag{11}
$$

where $N_r(X)$ counts members of $\mathcal P_\alpha(X)$ having exactly $r$ prime factors in $p-2$.

This identity is exact. The semiprime contribution has already canceled completely between the leading $1$ and the diagonal.

4. What genuine norm-fibre distribution can estimate

For $d,e\mid p-2$, put $L=[d,e]$. The divisibility condition becomes

$$
\boxed{N\pi=p\equiv2\pmod L.}
\tag{12}
$$

Because $L\mid p-2$, it is odd and coprime to $3$. The congruence is therefore reduced. The condition $\chi_\pi(-2)\ne1$ is a cubic splitting condition in the Kummer extension

$$
K(\sqrt[3]{2})/K.
$$

For each fixed $L$, Chebotarev gives the prime distribution

$$
\boxed{
\sum_{\substack{X<p\le2X\\
p\equiv1\ (3),\ p\equiv2\ (L)\\
\chi_\pi(-2)\ne1}}\log p
\sim\frac{X}{3\varphi(L)}.
}
\tag{13}
$$

The $1/3$ accounts for the split rational primes and the two nonidentity cubic Frobenius classes. This statement concerns the unrestricted prime-conductor population in a fixed norm progression.

But the actual terms in (11) require much more.

For $d,e\in\mathcal D(p-2)$, every prime factor of $d,e$ exceeds $X^\alpha$. In particular, for distinct $d,e$,

$$
\boxed{
L=[d,e]\ge X^{2\alpha}.
}
\tag{14}
$$

The modulus therefore grows at least as fast as $X^{0.4+o(1)}$, and can be of order $X$.

The relevant off-diagonal term is

$$
\boxed{
\begin{aligned}
\mathfrak O_\alpha(X)
=2\operatorname{Re}
\sum_{\substack{d<e\\d,e\text{ odd squarefree}}}
\mu(d)\mu(e)
\sum_{\substack{X<p\le2X\\
p\equiv1\ (3),\ \chi_\pi(-2)\ne1\\
p\equiv2\ ([d,e])\\
e^2<p-2\\
\mu^2(p-2)=1,\ P^-(p-2)>X^\alpha}}
\chi_\pi(d)\overline{\chi_\pi(e)}.
\end{aligned}}
\tag{15}
$$

The extra bound $e^2<p-2$ is the exact short-divisor condition; $d<e$ makes the corresponding condition for $d$ automatic.

For fixed $d,e$, cubic reciprocity relates the phase to a fixed cubic Hecke-character problem. But here the character varies with $d,e$, and the norm modulus varies simultaneously through $X^{2\alpha}\le L\ll X$. The roughness and squarefree conditions also remain attached to the complementary cofactor $(p-2)/L$.

A prime-ideal theorem at fixed conductor does not give the necessary average over this growing family. Even granting square-root cancellation in individual progression sums would not control the aggregate without a further large-sieve or Type II estimate.

The inspected primary source, Merikoski's A cubic analogue of the Friedlander–Iwaniec spin over primes, proves equidistribution of a particular cubic spin $[s/r]_3$ over prime ideals of $\mathbb Z[\zeta_{12}]$, with a power-saving bound. Its coefficients and prime family are different from the coupled symbols in (15); its theorem contains neither the growing norm-progressions $N\pi\equiv2\pmod L$ nor the rough shifted cofactor.

arxiv.org

It cannot be applied as an estimate for $\mathfrak O_\alpha(X)$.

5. The correct conditional cubic-residue model gives no positive excess

There is a second, more decisive test: suppose we grant the strongest natural cubic equidistribution model, rather than trying to prove it.

For a fixed squarefree factorization

$$
n=\ell_1\cdots\ell_r,
$$

write $x_j=\chi_\pi(\ell_j)$. Model these as uniformly distributed cube roots of unity, subject to the exact constraint

$$
\boxed{x_1\cdots x_r=c,\qquad c\in\{\omega,\omega^2\}.}
\tag{16}
$$

This is a formal conditioned residue-fibre model, not a theorem about the actual moving prime factors.

For two distinct proper divisors $d,e$, the character product

$$
\chi_\pi(d)\overline{\chi_\pi(e)}
$$

corresponds to a nonzero exponent vector in $(\mathbb Z/3\mathbb Z)^r$. Averaging over the configurations (16) kills this product unless its exponent vector is constant in every coordinate.

But a constant nonzero vector would require $d=n,e=1$, or the reverse. Neither divisor belongs to $\mathcal D(n)$.

Therefore

$$
\boxed{
\mathbb E\!\left[
\chi_\pi(d)\overline{\chi_\pi(e)}
\mid x_1\cdots x_r=c
\right]=0
\qquad(d\ne e).
}
\tag{17}
$$

The entire off-diagonal average vanishes, while the diagonal survives.

Thus the conditioned model predicts

$$
\boxed{
\mathbb E\bigl[1-|M_\pi(n)|^2\mid\omega(n)=r,c\bigr]
=
2-2^{r-1}.
}
\tag{18}
$$

Explicitly, the predicted values by rank are

$$
\boxed{1,\quad0,\quad-2,\quad-6.}
$$

So perfect cubic-character equidistribution would leave the averaged minorant at

$$
\boxed{
N_1-2N_3-6N_4,
}
\tag{19}
$$

not at the positive size of the whole rough source.

This is the sharp principal-term obstruction.

Semiprimes supply zero, regardless of their number. Three-factor and four-factor composites supply a negative contribution. Only genuine primes $n=p-2$ supply a positive contribution.

There is no independent positive excess in this residue-fibre model unless

$$
N_1>2N_3+6N_4.
$$

Such a bound would already imply infinitely many twins. It does not follow from cubic equidistribution or from a positive rough-source count.

The obstruction is especially explicit in the balanced three-factor sector: equation (2) gives the value $-2$ pointwise. Even perfect off-diagonal cancellation cannot improve it.

6. The exact failed analytic step

The proposed cubic mechanism has successfully produced a prime-only minorant. It has not produced a prime-producing lower bound.

The two necessary advances would be simultaneous: control the complete signed off-diagonal correlation (15), with moduli reaching order $X$, and show that its contribution improves the negative diagonal ledger (11) enough to leave a strictly positive remainder.

The published cubic-spin estimate does not provide the first advance. More importantly, the strongest natural equidistribution model for those off-diagonal terms does not provide the second: it leaves the diagonal values $0,-2,-6$ on the composite ranks.

The exact mathematical reason to stop is therefore not merely inadequate character-sum uniformity. It is that the principal diagonal consumes the entire positive $1$ on every semiprime, and more than consumes it on higher factor ranks. The proposed cubic phases enforce the nonvanishing required for the minorant, but averaging them naturally destroys the very off-diagonal information that would be needed to improve its sign.

No unconditional positive value of $\mathcal S_\alpha(X)$ on unbounded scales has been established, so this attempt does not prove the existence of infinitely many ordinary integer twin primes.

---

### Recovered response 3

Signed cubic repair: exact factor-rank analysis

The proposed cubic correction works exactly on semiprimes and balanced three-factor integers. It fails to be a pointwise twin-prime minorant on the full $X^{1/4-\varepsilon}$-rough source: unbalanced triples can contribute $+5$, and four-factor integers can contribute $+45$.

There is, however, an exact cubic resonance worth checking. The terms with $d_1d_2d_3=n$ have a deterministic character value $w=\chi_\pi(-2)$, and their coefficient can be computed without any equidistribution assumption.

1. The exceptional factor configurations

Put

$$
n=p-2,\qquad
\alpha=\frac14-\varepsilon,\qquad
\chi=\chi_\pi,\qquad
w=\chi(n)\in\{\omega,\omega^2\}.
$$

Assume $n$ is squarefree and $P^-(n)>X^\alpha$. For sufficiently small fixed $\varepsilon>0$, it has at most four prime factors.

Let

$$
M=\sum_{\substack{d\mid n\\1<d<\sqrt n}}\mu(d)\chi(d),
\qquad
G=1+\frac23\operatorname{Re}M^3-\frac13|M|^2.
$$

For prime $n$, $M=0$, giving $G=1$. For semiprime $n$, $M=-\chi(d)$ for the smaller prime factor $d$, giving $M^3=-1$, $|M|^2=1$, and $G=0$.

For a balanced triple $n=abc$, with all three primes below $\sqrt n$, write

$$
x=\chi(a),\quad y=\chi(b),\quad z=\chi(c).
$$

Because $xyz=w\ne1$, the three phases consist of two equal cube roots and one different root. Thus

$$
M=-(x+y+z),\qquad |M|^2=3,\qquad
\operatorname{Re}M^3=0,
$$

and again $G=0$.

Unbalanced triples

Suppose $a,b<\sqrt n<c$, so $ab<\sqrt n$. The retained divisors are $a,b,ab$, giving

$$
\boxed{M=xy-x-y.}
\tag{1}
$$

This has the complete algebraic classification

$$
\boxed{
G=
\begin{cases}
5,&\{x,y\}=\{\omega,\omega^2\},\\
-8,&x=y\in\{\omega,\omega^2\},\\
0,&x=1\text{ or }y=1.
\end{cases}}
\tag{2}
$$

Every case is compatible with the imposed product constraint $xyz=w\ne1$, by taking $z=w/(xy)$.

Therefore $G$ can be positive on a composite three-factor integer. A separate arithmetic theorem would be needed to exclude the positive phase pattern from the actual shifted-prime family; cubic multiplicativity does not exclude it.

Four factors

Write $n=abcd$, with $a<b<c<d$. The short divisors consist of four individual primes and exactly three pair products.

The selected pairs are

$$
ab,\quad ac,\quad
\begin{cases}
ad,&ad<bc,\\
bc,&bc<ad.
\end{cases}
$$

Consider the first region, $ad<bc$. Set

$$
\chi(a)=\omega,\qquad
\chi(b)=\chi(c)=\chi(d)=\omega^2.
$$

Their product is $w=\omega\ne1$, while

$$
M=3-\omega-3\omega^2=6+2\omega.
$$

Direct algebra gives

$$
|M|^2=28,\qquad \operatorname{Re}M^3=80,
$$

and hence

$$
\boxed{G=45.}
\tag{3}
$$

The angular condition $ad<bc$ is feasible for arbitrarily small fixed $\varepsilon>0$.

This is an algebraically admissible configuration, not a demonstrated actual prime factorization with these phase values. It suffices to show that the proposed pointwise minorant has not been proved from the stated character constraint.

There is a useful compensating size bound: as $\varepsilon\downarrow0$, the unbalanced three-factor region has logarithmic angular area $O(\varepsilon^2)$, while the four-factor region has three-dimensional angular volume $O(\varepsilon^3)$.

2. Exact cubic resonance and its sign

For each squarefree $n=\ell_1\cdots\ell_r$, write $x_j=\chi(\ell_j)$. The exact constraint is

$$
x_1\cdots x_r=w\ne1.
$$

Expand

$$
M^3=
\sum_{d_1,d_2,d_3\in\mathcal D(n)}
\mu(d_1)\mu(d_2)\mu(d_3)
\chi(d_1d_2d_3),
$$

where $\mathcal D(n)=\{d\mid n:1<d<\sqrt n\}$.

Two classes of terms have a character value determined without knowing the individual $x_j$.

All three divisors equal. Since $n$ is squarefree,

$$
\mu(d)^3\chi(d)^3=\mu(d).
$$

Their contribution to $\frac23\operatorname{Re}M^3$ is exactly

$$
\boxed{\frac23\sum_{d\in\mathcal D(n)}\mu(d).}
\tag{4}
$$

Three divisors partition $n$. If $d_1d_2d_3=n$, their prime supports are disjoint, and

$$
\mu(d_1)\mu(d_2)\mu(d_3)\chi(d_1d_2d_3)
=\mu(n)w.
$$

Because $\operatorname{Re}w=-1/2$, each ordered triple contributes

$$
\boxed{-\frac13\mu(n)}
\tag{5}
$$

to $G$.

The full multiplicities are:

Factorization
 |
Ordered triples with $d_1d_2d_3=n$
 |
Total contribution to $G$
 |

Semiprime
 |
0
 |
0
 |

Balanced triple
 |
6
 |
$+2$
 |

Unbalanced triple
 |
0
 |
0
 |

Four factors
 |
18
 |
$-6$
 |

For a balanced triple, the six triples are the permutations of its three prime factors. For four factors, select one of the three permitted short two-prime divisors, then assign it and the two remaining singleton primes to the three ordered slots: $3\cdot3!=18$.

The sign is therefore exact:

$$
\boxed{
\text{Balanced three-factor resonance}=+2,\qquad
\text{Four-factor resonance}=-6.
}
\tag{6}
$$

The positive $+2$ is a genuine arithmetic phase from $n=p-2$; it is not a generic diagonal term. But it is offset by another exact term in the same moment.

3. The principal terms cancel the balanced-triple gain

Consider the formal model in which $x_1,\ldots,x_r$ are uniform cube roots of unity, subject to $\prod_jx_j=w$. This model is useful for determining which character terms could contribute a principal main term. It is not being asserted as an equidistribution theorem for actual primes.

The orthogonality relation is

$$
\mathbb E_w\prod_jx_j^{e_j}
=
\begin{cases}
w^a,&e_j\equiv a\pmod3\text{ for every }j,\\
0,&\text{otherwise}.
\end{cases}
\tag{7}
$$

For the square moment, only $d=e$ survives. For the cubic moment, on the present rank-one-through-four divisor configurations, only the all-equal and full-partition terms survive. The possible condition $d_1d_2d_3=n^2$ cannot occur: it would require more prime-factor incidences than three short divisors can supply.

It follows that

$$
\boxed{
\mathbb E_wG
=
1-\frac{|\mathcal D(n)|}{3}
+\frac23\sum_{d\in\mathcal D(n)}\mu(d)
-\frac{\mu(n)}3
\#\{(d_1,d_2,d_3)\in\mathcal D(n)^3:d_1d_2d_3=n\}.
}
\tag{8}
$$

Complete principal-term ledger

Factorization
 |
$1-\lvert\mathcal D\rvert/3$
 |
All-equal cubic
 |
Full-partition cubic
 |
Total
 |

Prime
 |
1
 |
0
 |
0
 |
1
 |

Semiprime
 |
$2/3$
 |
$-2/3$
 |
0
 |
0
 |

Balanced triple
 |
0
 |
$-2$
 |
$+2$
 |
0
 |

Unbalanced triple
 |
0
 |
$-2/3$
 |
0
 |
$-2/3$
 |

Four factors
 |
$-4/3$
 |
$-2/3$
 |
$-6$
 |
$-8$
 |

In particular,

$$
\boxed{
\text{Balanced triple:}\quad
1-\frac33+\frac23(-3)+\frac23\operatorname{Re}(-6w)
=0.
}
\tag{9}
$$

This cancellation is pointwise, as proved in §1. It does not require averaging characters.

Therefore an independent lower bound for the resonant balanced-triple count would not yield a positive twin-prime signal. Its positive coefficient $+2$ is canceled exactly by the all-equal cubic contribution $-2$.

The four-factor resonance has the opposite sign and makes the principal model more negative.

4. What the full moment reduces to on actual primes

Let $\mathcal P_\alpha(X)$ consist of the genuine primes $p\in(X,2X]$ satisfying the cubic condition, with $n=p-2$ squarefree and $X^\alpha$-rough.

Separate the population into primes $n$, semiprimes, balanced triples, unbalanced triples, and four-factor integers. Denote their counts by $N_1,N_2,N_{3,b},N_{3,u},N_4$.

The pointwise calculations give the exact decomposition

$$
\boxed{
\sum_{p\in\mathcal P_\alpha(X)}G_\pi(p-2)
=
N_1(X)+
\sum_{\substack{p\in\mathcal P_\alpha(X)\\
n\text{ unbalanced triple or four-factor}}}
G_\pi(n).
}
\tag{10}
$$

There is no contribution from semiprimes or balanced triples—not merely an asymptotic cancellation.

The principal-term calculation in §3 can instead be written as

$$
\boxed{
\sum_{p\in\mathcal P_\alpha(X)}G_\pi(p-2)
=
N_1-\frac23N_{3,u}-8N_4+\mathcal E_{\mathrm{cubic}}(X),
}
\tag{11}
$$

where $\mathcal E_{\mathrm{cubic}}$ is the complete nonresonant cubic-character remainder. This is an exact decomposition by subtracting the explicitly determined character-neutral terms; it does not assume that the remainder averages to zero.

For genuinely uniform conditioned phases, the formal prediction would be

$$
\mathbb E\,\mathcal E_{\mathrm{cubic}}=0.
$$

But then the modeled main would still contain the unknown positive quantity $N_1$, opposed by the negative exceptional contributions. Cubic-character equidistribution alone supplies no independent positive main term.

An unconditional bound for the exceptional configurations

There is one useful quantitative result that can be proved without estimating the cubic symbols.

For every sufficiently small fixed $\varepsilon>0$, a standard two-linear-form Selberg upper sieve gives

$$
\boxed{
N_{3,u}(X)\ll
\varepsilon^2\frac{X}{(\log X)^2},
\qquad
N_4(X)\ll
\varepsilon^3\frac{X}{(\log X)^2}.
}
\tag{12}
$$

Here is the argument with the factor-size restrictions retained.

For an unbalanced triple $n=abc$, with $a\le b<c$ and $c>\sqrt n$, let

$$
u=\frac{\log a}{\log X},\qquad
v=\frac{\log b}{\log X}.
$$

Then

$$
u,v\ge\frac14-\varepsilon,\qquad u+v<\frac12+o(1).
$$

This region has area $O(\varepsilon^2)$. Fixing the primes $a,b$, we upper-sieve the two forms

$$
c,\qquad abc+2.
$$

Their singular series is uniformly bounded, since $a,b>X^\alpha$. The sieve gives

$$
\#\{c:c,\ abc+2\text{ prime},\ abc\asymp X\}
\ll\frac{X}{ab(\log X)^2}.
$$

Summing $1/(ab)$ over the permitted prime-factor region proves the first bound.

For four factors, every logarithmic share belongs to

$$
\left[\frac14-\varepsilon,\frac14+3\varepsilon+o(1)\right].
$$

The permitted three-dimensional simplex has volume $O(\varepsilon^3)$. Fix three prime factors and apply the same two-linear-form upper sieve to the fourth prime and $p=abcd+2$. This proves the second bound.

The cubic condition $w\ne1$ can only decrease these counts.

Because $|M|\le7$, the four-factor contribution has a bounded absolute weight. Together with (2), equation (12) therefore establishes

$$
\boxed{
\left|
\sum_{p\in\mathcal P_\alpha(X)}G_\pi(p-2)-N_1(X)
\right|
\ll
\varepsilon^2\frac{X}{(\log X)^2}.
}
\tag{13}
$$

This is unconditional.

Squareful rough integers can also be removed. Their number is at most

$$
\sum_{\ell>X^\alpha,\ \ell^2\ll X}
\left(\frac{2X}{\ell^2}+1\right)
\ll X^{1-\alpha}+\sqrt X
=o\left(\frac{X}{(\log X)^A}\right)
$$

for every fixed $A>0$. The bounded factor rank makes their total possible moment contribution negligible at the scale in (13).

Equation (13) is the strongest positive development in this calculation: the cubic moment differs from the actual twin-prime count by only a controlled $O(\varepsilon^2X/\log^2X)$ exceptional term.

It does not establish a positive lower bound for the cubic moment.

5. Why the available prime-ideal estimates do not evaluate the remainder

A nonresonant term in the cube expansion has the form

$$
\chi_\pi(d_1d_2d_3),
$$

with each $d_i$ a nontrivial short divisor of $n=N\pi-2$.

Let

$$
L=\operatorname{lcm}(d_1,d_2,d_3).
$$

The norm condition is exactly

$$
\boxed{N\pi\equiv2\pmod L.}
\tag{14}
$$

If $L$ is a proper divisor of $n$, roughness gives

$$
\boxed{L\le\frac n{P^-(n)}\ll X^{1-\alpha}.}
\tag{15}
$$

At $\alpha=1/4-\varepsilon$, this permits moduli as large as $X^{3/4+\varepsilon}$.

Other nonresonant terms have $L=n$, so their norm congruence is no restriction at all beyond the original identity $N\pi=n+2$.

For instance, in the four-factor star configuration, the three short divisors

$$
ab,\quad ac,\quad ad
$$

have lcm $n=abcd$, while

$$
\chi_\pi((ab)(ac)(ad))
=\chi_\pi(a^3bcd)
=\frac{w}{\chi_\pi(a)}.
$$

This is a genuinely nonconstant cubic phase, even though the lcm is the full shifted neighbor.

To estimate it, one must average over actual configurations

$$
\boxed{
p=abcd+2,\qquad p,a,b,c,d\text{ prime},
}
\tag{16}
$$

retaining the factor-size restrictions and the cubic symbol. Ordinary prime distribution in residue classes does not evaluate this correlation.

For balanced triples, the full-partition resonance similarly leads to

$$
\boxed{
p=abc+2,\qquad p,a,b,c\text{ prime},
}
\tag{17}
$$

with $a,b,c$ in prescribed macroscopic ranges.

Even independently establishing a lower asymptotic for (17) would not create a gain in the proposed moment: its resonant coefficient $+2$ is canceled exactly as in (9).

Applicability of the published estimates

I checked Jori Merikoski's primary paper, A cubic analogue of the Friedlander–Iwaniec spin over primes.

Its Theorem 1 proves

$$
\sum_{N\mathfrak p\le X}[\mathfrak p]_3
\ll X^{1-1/143},
$$

for its specific cubic spin on prime ideals of $\mathbb Q(\zeta_{12})$. Its Type II estimate concerns arbitrary divisor-bounded coefficients multiplying that spin, with the particular ideal-factorization structure in the paper.

doi.org+1

Neither theorem supplies cancellation for the moving symbols $\chi_\pi(d_1d_2d_3)$ under (14), especially when the lcm reaches $n$.

I also checked the primary Matomäki–Zuniga Alterman, Weighted sieves with switching. Its prime–$P_3$ result counts a prime together with an integer having at most three prime factors under its stated distribution hypotheses. It does not count the exact balanced configurations (17), nor the cubic-weighted five-prime configurations (16).

cambridge.org

Thus neither source provides the required nonresonant cubic average or an independent positive lower for $\sum G$.

6. Final sign comparison

The proposed repair has produced two rigorous results:

$$
\boxed{
\begin{aligned}
G_\pi(n)&=1&&\text{when }n\text{ is prime},\\
G_\pi(n)&=0&&\text{when }n\text{ is semiprime or a balanced triple}.
\end{aligned}}
$$

It also produces an exact positive cubic resonance $+2$ on balanced triples. But that resonance cancels with the $-2$ all-equal divisor contribution, before any averaging.

For four-factor integers the full-partition resonance is $-6$, and the total character-neutral contribution is $-8$. The remaining nonresonant terms have no proved favorable sign.

Most sharply, equation (13) shows that the full cubic moment is already within $O(\varepsilon^2X/\log^2X)$ of the genuine twin-prime count. Hence any useful independent positive excess must resolve that same fixed-gap arithmetic, rather than merely demonstrate cubic cancellation on the large semiprime and balanced-triple populations.

The first unsupported step is an independent lower estimate for the full cubic moment exceeding its exceptional-composite allowance. The exact resonance does not provide one, and the available cubic-spin and switched-sieve theorems do not estimate the coupled norm-fibre terms that remain.

No such positive excess has been proved. The signed cubic repair therefore does not establish infinitely many ordinary twin primes.

---

### Recovered response 4

Apollonian curvature transfer: local obstructions

The proposed transfer encounters a stronger obstruction than the usual parity restriction: ordinary twin primes greater than $3$ cannot both occur as odd curvatures anywhere in the same primitive integral Apollonian packing. Moreover, the proposed doubled even curvatures $2p,2(p+2)$ cannot belong to a single integral Descartes quadruple for any ordinary twin-prime lower member $p>3$.

These are exact local impossibility statements, independent of sieve estimates.

1. How Sarnak actually produces two primes

Sarnak's 2007 letter to Lagarias gives the underlying two-stage construction. Fix a circle of curvature $a$. The subgroup fixing that circle produces other curvatures among primitive values of a shifted positive-definite binary quadratic form

$$
A\xi^2+2B\xi\eta+C\eta^2-a,
\qquad B^2-AC=-a^2.
$$

Iwaniec's theorem supplies infinitely many prime values for this form. Sarnak then fixes one such prime curvature $p$, applies the subgroup fixing the $p$-circle, and produces infinitely many further prime curvatures tangent to it.

web.math.princeton.edu

Thus the two prime curvatures are produced successively, with the first fixed during the second application. Their numerical difference is unrestricted.

Sarnak's 2011 exposition states the resulting theorem as infinitely many tangent pairs of prime curvatures, calling them Apollonian twin primes. This terminology means tangency, not difference $2$.

ias.edu

2. All odd curvatures have the same residue modulo $4$

An integral Descartes quadruple $(a,b,c,d)$ satisfies

$$
2(a^2+b^2+c^2+d^2)=(a+b+c+d)^2.
$$

For a primitive quadruple, a modulo-$4$ calculation forces an even number of odd coordinates. Four odd coordinates are impossible modulo $16$: the left side would be $8\pmod{16}$, whereas $8$ is not a square modulo $16$. Hence there are exactly two odd coordinates.

Label them $a,b$, with $c,d$ even.

Modulo $16$, the Descartes equation becomes

$$
(a+b+c+d)^2
\equiv4+2c^2+2d^2\pmod{16}.
$$

If $c,d$ belonged to different even residue classes modulo $4$, the right side would be $12\pmod{16}$, impossible for a square.

Therefore $c\equiv d\pmod4$, and $c+d\equiv0\pmod4$. The equation then forces

$$
a+b\equiv2\pmod4,
$$

so

$$
\boxed{a\equiv b\pmod4.}
\tag{1}
$$

The Apollonian reflections replace one curvature $x_i$ by twice the sum of the other three minus $x_i$. They preserve each coordinate's residue modulo $4$, using the congruences just established.

Consequently, all odd curvatures throughout a given primitive integral packing occupy one fixed residue class modulo $4$.

But ordinary twin primes $p,p+2$, with $p>3$, occupy opposite odd residue classes modulo $4$. Therefore they cannot both occur as curvatures in that packing—even if the corresponding circles are not tangent.

This proves that changing to another primitive integral packing does not remove the odd-curvature obstruction.

3. The doubled-even repair has a local obstruction at $3$

Suppose an integral Descartes quadruple contains

$$
c=2p,\qquad d=2(p+2)=2p+4,
$$

with remaining curvatures $a,b$.

An exact rearrangement of the Descartes equation gives

$$
(a-b)^2+(c-d)^2=2(a+b)(c+d).
$$

Therefore

$$
\boxed{(a-b)^2+16=8(p+1)(a+b).}
\tag{2}
$$

Every ordinary twin-prime lower member $p>3$ satisfies

$$
p\equiv5\pmod6,
$$

because otherwise $p+2$ is divisible by $3$.

Hence $3\mid p+1$. Reducing (2) modulo $3$ forces

$$
(a-b)^2\equiv-1\equiv2\pmod3,
$$

which is impossible.

Thus

$$
\boxed{
p,p+2\text{ prime},\ p>3
\ \Longrightarrow\
( a,b,2p,2p+4 )
\text{ cannot satisfy the Descartes equation}.
}
\tag{3}
$$

This does not depend on primitivity, positivity of all four curvatures, or membership in a particular Apollonian group orbit. The entire proposed doubled-curvature slice is locally empty for ordinary twins.

4. The difference stabilizer gives a quadratic form with a zero local prime-pair density

There is a more geometric interpretation of the same obstruction, which directly tests the suggested arithmetic subgroup.

In a primitive quadruple, $a,b$ are the two odd curvatures. Since they agree modulo $4$, write

$$
a=v+2u,\qquad b=v-2u,
$$

with $u\in\mathbb Z$, $v$ odd.

Equation (2) becomes

$$
\boxed{u^2+1=(p+1)v.}
\tag{4}
$$

Equivalently, the integral binary quadratic form

$$
F(S,T)=(p+1)S^2+2uST+vT^2
$$

has discriminant

$$
\boxed{\Delta_F=4u^2-4(p+1)v=-4.}
\tag{5}
$$

It is positive definite, primitive, and belongs to the unique proper equivalence class of positive-definite binary quadratic forms of discriminant $-4$.

Consequently, there exist coprime integers $x,y$ such that

$$
\boxed{p+1=x^2+y^2,\qquad (x,y)=1.}
\tag{6}
$$

This is the quadratic-form structure of the fixed-difference surface. The full integral orthogonal stabilizer acts through the arithmetic symmetry of unimodular binary quadratic forms, but any Apollonian subgroup acting within it remains subject to (6).

Now reduce (6) modulo $3$. Squares are $0,1\pmod3$. Their sum can be $0\pmod3$ only if both $x$ and $y$ are divisible by $3$, contradicting coprimality.

Therefore

$$
p+1\not\equiv0\pmod3.
$$

The two desired normalized curvature values are

$$
p=(x^2+y^2)-1,\qquad
p+2=(x^2+y^2)+1.
$$

Since a primitive sum of two squares is $1$ or $2\pmod3$, one of these two values is necessarily divisible by $3$.

Thus the simultaneous shifted-binary-form prime problem generated by this stabilizer has zero local density at $3$. Its singular series is zero, so no prime-producing theorem can give an unbounded family with both values prime.

This is a stronger conclusion than failure of a particular sieve estimate: the required integer points themselves are absent for ordinary twin primes.

5. Why the arithmetic subgroup does not repair the obstruction

The subgroup generated by the two Descartes reflections that change $a$ and $b$ while fixing $c,d$ acts on $u=(a-b)/4$ by

$$
u\longmapsto-u+2(p+1),
\qquad
u\longmapsto-u-2(p+1).
$$

Their compositions give

$$
\boxed{u\longmapsto u\pm4(p+1).}
\tag{7}
$$

These are genuine infinite arithmetic orbits on the quadratic-form surface. But they hold $p$ fixed. They vary the remaining two curvatures, not the desired twin-prime pair.

Allowing $p$ to vary while stabilizing the difference $d-c=4$ leads back to equation (6),

$$
p+1=x^2+y^2,\qquad (x,y)=1.
$$

The mod-$3$ obstruction applies to every point on that surface. Passing to a larger arithmetic stabilizer or restricting to an Apollonian subgroup cannot remove it.

There is also a useful generalization for any fixed integer scaling $s$. Suppose two curvatures are

$$
sp,\qquad s(p+2).
$$

For an ordinary twin-prime lower member $p>3$:

-

If $s$ is odd, the two curvatures are odd and differ by $2s\equiv2\pmod4$, contradicting (1).

-

If $s$ is even but $3\nmid s$, the Descartes equation modulo $3$ gives the same nonresidue obstruction as (3).

Therefore the two local obstructions leave only scalings divisible by $6$ as possible candidates.

But when $6\mid s$, both $sp$ and $s(p+2)$ are composite curvature values. Sarnak's theorem guaranteeing prime curvatures no longer supplies primality of their quotients by $s$. A new theorem about two simultaneously prime normalized curvatures with a fixed difference would be required.

This is the precise limitation of the scaling repair.

6. Different packings and coordinate changes

Changing the initial primitive integral Descartes quadruple does not help with odd curvatures: the global mod-$4$ argument holds in every primitive integral packing.

An integral coordinate transformation preserving the Descartes quadratic form also preserves the fact that its transformed quadruples satisfy the same equation. It therefore cannot evade either the odd-curvature congruence or the doubled-even mod-$3$ obstruction.

An arbitrary coordinate change that does not preserve the Descartes form may define new linear combinations of curvatures. But Sarnak's prime-curvature theorem does not assert that these new linear forms simultaneously take prime values. One cannot transfer the theorem to them without proving an additional prime-producing result.

The independent prime-producing input is lost precisely where one attempts to turn two unrestricted prime curvatures into two ordinary primes separated by $2$.

Final mathematical verdict

The source-backed construction of infinitely many tangent prime-curvature pairs is valid, but the desired fixed-gap transfer fails for a definitive local reason:

$$
\boxed{
\begin{gathered}
\text{Odd curvatures in one primitive integral packing}\\
\text{are all congruent modulo }4,
\end{gathered}}
$$

while

$$
\boxed{
\begin{gathered}
\text{Even curvatures }2p,\ 2(p+2)
\text{ in one Descartes quadruple}\\
\text{are impossible for every ordinary twin pair }p>3.
\end{gathered}}
$$

The difference-$4$ arithmetic stabilizer reduces to a discriminant-$-4$ binary quadratic form. Its simultaneous shifted-prime problem has an identically vanishing local factor at $3$. This is not a failure of sieve strength; the required configurations do not exist.

The only remaining scaling class, multiples of $6$, no longer lies within Sarnak's established prime-curvature theorem.

Decision: The proposed Apollonian transfer cannot prove infinitely many ordinary integer twin primes using the stated unconditional theorem. No alternative packing or primitive Descartes coordinate change preserves an applicable independent prime-producing input that resolves the fixed gap $2$.

---

### Recovered response 5

Signed Apollonian slice: exact prime gap

The proposed construction is correct. For every odd prime $p\ge5$, the signed Descartes quadruple is primitive, its tangent form has discriminant $-4p^2$, and its least positive tangent prime is either $p+2$ or at least $2p^2+p+8$.

The gap is unconditional. The problem is whether an existing prime-producing theorem can place a tangent prime below that threshold for infinitely many growing anchors $p$.

1. Verifying the signed root

Set

$$
T=\frac{(p+1)^2}{2},
\qquad
(a,b,c,d)=(-p,p+2,T,T).
$$

Since $p$ is odd, $T$ is an even integer. The quadruple is primitive because

$$
\gcd(p,p+2)=1.
$$

Descartes' equation is equivalent to

$$
(a-b)^2+(c-d)^2=2(a+b)(c+d).
$$

For this root, both sides equal $4(p+1)^2$, so the Descartes equation holds exactly.

Sarnak's tangent parametrization, as stated in Proposition 1.2 of Fuchs–Hsu–Rickards–Schindler–Stange, gives the curvatures tangent to a circle of curvature $a$ as primitive values of

$$
(b+a)x^2+(a+b+d-c)xy+(d+a)y^2-a.
$$

Substituting $a=-p$ yields

$$
\boxed{
q_p(x,y)
=p+2x^2+2xy+\frac{p^2+1}{2}y^2
=p+\frac{(2x+y)^2+p^2y^2}{2},
\quad (x,y)=1.
}
\tag{1}
$$

Replacing $x$ by $-x$ gives the proposed minus-sign version, with the same primitive values. The underlying quadratic form is primitive, positive definite, and has discriminant

$$
\boxed{\Delta=-4p^2.}
$$

This matches the actual source parametrization.

math.ucdavis.edu

2. The least-prime gap, with no missing primitive cases

If $y=0$, primitivity forces $x=\pm1$, giving exactly

$$
q_p(x,0)=p+2.
$$

If $y$ is odd, both $2x+y$ and $py$ are odd. Their squares are $1\pmod8$, so

$$
q_p(x,y)\equiv p+1\pmod2.
$$

Thus $q_p(x,y)$ is even. Moreover,

$$
q_p(x,y)\ge p+\frac{p^2+1}{2}>2
$$

for $p\ge5$. None of these values is prime.

If $y=2z$, then

$$
\boxed{
q_p(x,2z)=p+2(x+z)^2+2p^2z^2.
}
\tag{2}
$$

Primitivity forces $x$ to be odd.

For $|z|=1$, the integer $x+z$ is even. If it is zero, the curvature is

$$
p+2p^2=p(2p+1),
$$

which is composite. Otherwise $|x+z|\ge2$, so

$$
q_p(x,2z)\ge2p^2+p+8.
$$

For $|z|\ge2$,

$$
q_p(x,2z)\ge p+8p^2>2p^2+p+8.
$$

These cases exhaust all coprime integer pairs $(x,y)$. Therefore:

$$
\boxed{
\begin{gathered}
\text{If }p+2\text{ is prime, it is the least positive}\\
\text{prime curvature tangent to }-p;\\[2pt]
\text{if }p+2\text{ is composite, every such prime}\\
\text{curvature is at least }2p^2+p+8.
\end{gathered}}
\tag{3}
$$

No exceptional small primes occur for $p\ge5$. Equality at the lower bound is a possible primitive curvature value, not a guarantee that this value is prime.

There is also a small strengthening in the only residue class relevant to unbounded twin primes. If $p\equiv2\pmod3$, then for $|z|=1$,

$$
q_p(x,2z)\equiv1+2(x+z)^2\pmod3.
$$

A noncomposite curvature requires $3\mid x+z$; since $x+z$ is even and nonzero, its absolute value is at least $6$. The other $z$-ranges are already larger. Hence

$$
\boxed{
p\equiv2\pmod3,\ p\ge5
\quad\Longrightarrow\quad
\text{every non-root tangent prime}\ge2p^2+p+72.
}
\tag{4}
$$

This strengthens the gap but does not provide a prime within it.

3. All integral completions give the same quadratic-form class

There is an exact answer to the proposed class-equivalence repair.

Keep the two curvatures

$$
a=-p,\qquad b=p+2
$$

fixed, but allow the other two curvatures $c,d$ to vary through every integral Descartes completion.

Descartes' equation becomes

$$
4(p+1)^2+(d-c)^2=4(c+d).
$$

Integrality forces $4\mid d-c$. Writing $d-c=4h$, we obtain

$$
\boxed{
c=T+2h(h-1),\qquad
d=T+2h(h+1),\qquad h\in\mathbb Z.
}
\tag{5}
$$

There are no other integral completions of this fixed pair.

Substituting into Sarnak's tangent form gives

$$
\begin{aligned}
f_h(x,y)
={}&2x^2+(2+4h)xy\\
&+\left(\frac{p^2+1}{2}+2h(h+1)\right)y^2.
\end{aligned}
$$

But this is exactly

$$
\boxed{f_h(x,y)=f_0(x+hy,y).}
\tag{6}
$$

The substitution

$$
(x,y)\longmapsto(x+hy,y)
$$

has determinant $1$ and is a bijection on primitive integer pairs.

Therefore all integral completions with the curvatures $-p,p+2$ fixed represent exactly the same multiset of tangent curvatures. They belong to one proper equivalence class of binary quadratic forms, not a growing collection of independent classes.

Summing their representation counts would count the same tangent primes repeatedly. It would provide neither additional distinct primes nor independent arithmetic conditions.

Other form classes of discriminant $-4p^2$ exist, but accessing them requires changing the geometric data, not merely completing this fixed pair. Their prime values are not automatically prime curvatures on the specified signed slice.

4. What Theorem 1.3 actually guarantees

I inspected the original arXiv v1 source of Fuchs, Hsu, Rickards, Schindler and Stange, Primes represented by shifted quadratic forms: on primitivity and congruence classes.

Their Theorem 1.3 gives a lower bound for prime values of a fixed shifted Apollonian form, including primitive representations and qualifying arithmetic progressions. The relevant lower-bound assertion is part (2).

math.ucdavis.edu

Our form satisfies its fixed-form arithmetic conditions:

$$
f_p(x,y)=2x^2+2xy+\frac{p^2+1}{2}y^2.
$$

Although its displayed leading coefficient $2$ is not coprime to $2\Delta$, interchanging the variables gives the leading coefficient

$$
\frac{p^2+1}{2},
$$

which is odd and coprime to $8p^2$. Moreover $\Delta=-4p^2\equiv4\pmod8$, so the excluded discriminant condition does not arise.

Taking progression modulus $1$, the theorem therefore supplies, for each fixed prime $p$,

$$
\boxed{
\#\{q\le B:q\text{ prime},\
q=p+f_p(x,y),\ (x,y)=1\}
\gg_p\frac{B}{(\log B)^{3/2}}
}
\tag{7}
$$

as $B\to\infty$.

This proves that each signed anchor has infinitely many positive tangent prime curvatures. It says nothing about their least value relative to $p^2$.

The precise growing-discriminant caveat

The authors explicitly note that their theorem treats a fixed discriminant. They contrast this with a Bourgain–Fuchs theorem permitting discriminants of polylogarithmic size and state that adapting their result to growing discriminants requires additional work. Their genus-to-form transfer also incurs class-number dependence when the discriminant grows.

math.ucdavis.edu+1

Here,

$$
|\Delta|=4p^2.
$$

The desired cutoff is also of size $p^2$. Thus $|\Delta|\asymp B$, not merely $|\Delta|\le(\log B)^A$.

The fixed-$p$ theorem cannot be used uniformly in this regime.

5. A stronger quantitative obstruction to uniform transfer

The failure is not just that the theorem's constants are unspecified. Its lower-bound scale is mathematically impossible uniformly when $B\asymp p^2$.

Fix $C>2$ and let $B=Cp^2$.

Every prime curvature below $B$ has $y=2z$, because odd $y$ gives an even composite curvature. Equation (2) implies

$$
2p^2z^2\le B,\qquad
2(x+z)^2\le B.
$$

Therefore

$$
|z|\le\sqrt{C/2},
\qquad
|x+z|\le p\sqrt{C/2}.
$$

There are only $O_C(1)$ possible $z$ and $O_C(p)$ possible $x$. Hence the number of distinct positive prime curvatures below $Cp^2$ satisfies the unconditional geometric bound

$$
\boxed{
\#\{q\le Cp^2:q\text{ prime tangent curvature}\}
=O_C(p).
}
\tag{8}
$$

A uniform version of (7), with an absolute positive lower constant at $B=Cp^2$, would instead give

$$
\gg_C\frac{p^2}{(\log p)^{3/2}},
$$

which is asymptotically larger than $p$. Such a uniform theorem is impossible.

Even more sharply, for

$$
p+2<B<2p^2+p+8,
$$

there is at most one positive tangent prime, namely $p+2$.

This shows that fixed-form prime-production asymptotics cannot be transferred to the critical range by making their constants merely uniform in $p$. The form itself becomes too sparse there.

A useful theorem at that scale would have to be of a different type—for example, an existence result for the first prime value rather than the fixed-form asymptotic (7).

6. The exact quantifier failure

Define the least positive tangent prime curvature

$$
L(p)=\min\{q:q\text{ prime},\
q=p+f_p(x,y),\ (x,y)=1\}.
$$

Theorem 1.3 guarantees $L(p)<\infty$ for every fixed prime anchor $p$.

Our gap theorem proves

$$
\boxed{
L(p)<2p^2+p+8
\iff
p+2\text{ is prime}.
}
\tag{9}
$$

Consequently, proving

$$
L(p)<2p^2+p+8
$$

for infinitely many unbounded primes $p$ would solve the twin-prime conjecture.

But the source proves only

$$
\forall p\text{ prime},\quad L(p)<\infty.
$$

It supplies no estimate that forces $L(p)$ into the interval in (9) while $p\to\infty$.

The class-equivalent completions cannot improve this because of (6). They generate precisely the same prime-value set.

Final verdict

The signed-root construction passes every requested algebraic check. The complete least-prime gap is proved, including primitivity, the exceptional composite value $p(2p+1)$, and all parity cases.

The family of integral completions is also completely classified: every completion is related to the original quadratic form by a unimodular shear. There are no additional independent form classes on this fixed pair of curvatures.

The first unsupported step is the proposed uniform first-prime bound at $B\asymp p^2$. The cited shifted-forms theorem is asymptotic for a fixed discriminant; its growing-discriminant caveat is explicit, and its $B/(\log B)^{3/2}$ lower-bound scale cannot hold uniformly at this critical height.

Thus the geometric gap is a rigorous equivalence to the desired twin-prime condition, but no applicable independent theorem forces the first tangent prime into that gap for infinitely many growing anchors.

No unconditional proof of infinitely many ordinary twin primes follows from this signed Apollonian slice.

---

## Paper Extraction Plan

[Original conversation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6af7fd52-87a8-83ee-952d-ea2ca54d783b)

### Recovered response 1

I’ve read the project rules and the paper goal. I’ll wait here for the exact source pointers and assignment before starting work or briefing reviewers.

I understand this is a finite paper-extraction task. Once you provide the sources, I’ll map the results, proof dependencies, and prior literature before selecting a claim. I’ll use distinct proof and novelty reviewers, give each the rules and goal first, and wait for their confirmation before assigning work. If the evidence supports a paper, I’ll prepare one coherent manuscript with an essential verification appendix under separate draft filenames, preserving the original research and sources.

The draft will credit DEEPAK KUMAR (admin@cosmosgeek.org) as research coordinator and contact, with final authorship pending. It will identify the actual model used and describe its substantive contributions to the research and writing.

---

### Recovered response 2

Verdict: put the semiprime pseudoprime bound in front of a specialist first

The strongest immediate candidate for public mathematical attention is the unconditional bound

$$
\boxed{
\#\{n\le X:n=pq,\ p,q\text{ prime},\
2^{n-1}\equiv1\pmod n\}
\ll \frac{X^{3/4}}{(\log X)^{5/4}}.
}
$$

This improves the published unrestricted bound $O(X^{4/5}/(\log X)^{2/5})$ in Luca–Ralaivaosaona–Jiménez Urroz, On pseudoprime RSA moduli (2025), Theorem 3.1. Their Theorem 2.1 has a different scope: balanced prime factors.

Springer Nature Link+1

The improvement has a short, independently reconstructible mathematical argument:

1. For distinct prime factors $p,q$, put $g=\gcd(p-1,q-1)$. The pseudoprime condition forces both $p$ and $q$ to divide $2^g-1$. For $g\le Y$, each such prime is at least $g+1$, so $2^g-1$ has at most $O(g/\log g)$ eligible distinct prime divisors. This gives $O(Y^3/\log^2Y)$ pairs.

2. For $g>Y$, write $p=ag+1,\ q=bg+1$. Since $abg^2\le X$, a uniform two-linear-form upper sieve and an averaged singular-series estimate give
\[
#{g>Y}\ll \frac{X}{Y\log X}.
\]
The singular-series average is bounded over dyadic coefficient boxes using the bounded moments of $n/\varphi(n)$, including the dependence on $a-b$. The coincident-factor case $p=q$ costs at most $\sqrt X$.

3. Choosing $Y=X^{1/4}(\log X)^{1/4}$ balances the two estimates and gives the displayed theorem.

This is a genuine exponent improvement for a well-defined arithmetic population, not a reformulation of twin primes. I have not found a primary source already stating the $3/4$ bound, but a specialist must check priority and the complete uniform sieve argument before a novelty claim.

§308DJ: stronger combinatorial statement, but less certain novelty

I reopened the original §308DJ argument and the six-page draft. The central result is substantially more specific than a theorem merely producing short prime gaps.

For $L=\log X$, every fixed $\delta>0$, every subset $A\subseteq\mathbb P\cap(X,2X]$ with $|A|\ge\delta X/L$, and every $R/L\to\infty$, $R\le X/100$, it claims

$$
N_\pm(A,R)=\left(\frac12+o_\delta(1)\right)N(A,R),
\qquad
N(A,R)\asymp_\delta\frac{XR}{L^2},
$$

where the sign is $\lambda((q-p)/2)$ and $p<q$ are selected primes.

The larger theorem permits arbitrary endpoint weights on one or two polynomially rough translates. Its scale is $R/L^j\to\infty$, with $j=1,2$. For each fixed $k$, all $2^{\binom{k}{2}}$ Liouville-sign assignments to the edges of a local $k$-tuple are equidistributed under the specified window sampling.

Short-scale proof audit

The claimed argument has a coherent route through the difficult logarithmic window:

-

Green–Tao Appendix D, Theorem D.3, controls fixed moments of the smooth sieve majorant, including coincident translates after merging their multiplicities.

-

The collision error is $O_k(\sum_{c<b}(L^j/R)^{b-c})$. It vanishes even when $R/L^j$ diverges arbitrarily slowly.

-

The averaged singular series can be truncated to a fixed primorial. The resulting finite residue masks separate by vertex.

-

Two Cauchy–Schwarz applications reduce the signed correlation to a four-cycle. Davenport’s uniform Möbius exponential-sum bound, extended to Liouville by $\lambda(n)=\sum_{d^2\mid n}\mu(n/d^2)$, gives the required vanishing operator norm.

The key quantifiers appear compatible with the primary Green–Tao theorem: bounded scaled affine coefficients, a sufficiently small fixed sieve exponent, and an exceptional-prime error averaged over the vertex indices. I found no concrete break in this chain in the reopened proof. That is a scoped mathematical audit, not formal verification or an external referee verdict.

annals.math.princeton.edu+1

The boundary examples are substantive. The draft constructs a positive-density prime subset at $R=\lfloor4\log X\rfloor$ whose counted pairs all have the same Liouville sign. The later §308DK gives a corresponding arbitrary-selection obstruction for doubly rough composite rows when $R=o((\log X)^2)$. These match the two asserted threshold scales rather than merely supplying numerical examples.

Is it already a corollary?

The closest sources do not state this conclusion:

Primary result
 |
Scope compared with §308DJ
 |

Shao, Narrow arithmetic progressions in the primes (2017)
 |
Produces $k$-term progressions in arbitrary dense prime subsets with difference $O((\log X)^{(k-1)2^{k-2}})$. No conclusion about Liouville signs on all short pairs.

doi.org+1

 |

Shao, Narrower arithmetic progressions in the primes (November 2026)
 |
Improves the exponent to $k2^{k-3}+\varepsilon$, still for $k\ge3$ progressions, not uniform sign frequencies on selected pairs or complete edge patterns.

arxiv.org+1

 |

Green–Tao, Appendix D; Green–Tao Selberg-sieve restriction theory
 |
Supplies indispensable sieve-correlation and Fourier machinery, but not the displayed Liouville-sign conclusion by itself. The four-cycle reduction and short-scale collision accounting must still be made.

annals.math.princeton.edu+1

 |

The Rivat–Sárközy–Stewart sumset work is also close in theme, but its logarithmic savings in the difference-variable scale do not directly overcome the $1/\log X$ endpoint density when $R$ is only slightly larger than $\log X$.

Thus §308DJ is not a direct corollary of the inspected theorem statements. Whether specialists would regard its combination of existing machinery as a new theorem of publishable novelty remains unverified.

Where §308CO ranks

§308CO establishes, in the saved argument, a sharp unconditional absolute leakage calculation for the fractional divisor detector $Q_\alpha$, with $\alpha=1+c/\log\log X$:

$$
\text{composite absolute mass}\longrightarrow 1-e^{-c}
$$

in the specified normalized shifted-prime units. It also obtains a subsequential signed Laplace representation with an unknown bounded density.

The calculation is mathematically useful, but that density is not identified and the required prime-sensitive signed lower bound remains absent. Its immediate standalone impact is narrower than either the pseudoprime exponent improvement or the short-difference sign theorem.

Final ranking

Rank
 |
Result
 |
Assessment
 |

1
 |
Base-2 semiprime pseudoprimes, exponent $3/4$
 |
Send to a number-theory specialist first. Explicit improvement over a directly comparable published theorem, with a short sieve argument that can be audited independently. Novelty still requires a priority check.
 |

2
 |
§308DJ and §308DK
 |
Strongest claim about arbitrary prime subsets and short-scale sign structure. Proof survives this targeted continuity check; likely interesting, but the distinction between a new theorem and an accessible synthesis of established methods needs specialist judgment.
 |

3
 |
§308CO
 |
Substantial technical calculation; not presently the strongest independent public result.
 |

My decision: lead with the $3/4$ pseudoprime bound, giving the specialist the complete small-gcd/large-gcd argument and the exact 2025 comparison. Present §308DJ as the second candidate for a separate analytic-number-theory novelty assessment. Do not lead with another twin-prime reduction or claim that any of these results proves infinitely many twin primes.

---

### Recovered response 3

I selected §308DJ and completed one six-page manuscript, Liouville signs of short differences in sets of primes. The saved TeX matched the source on readback, and I verified all six pages of the saved PDF, including the proof, verification appendix, and references.

Read the manuscript — twin-prime-paper-draft.pdf · Open the source — twin-prime-paper-draft.tex

The result. Choose any fixed positive proportion of the primes between \(X\) and \(2X\). Among all selected pairs \(p<q\) with \(q-p\le 2R\), count the prime factors of \((q-p)/2\), including multiplicity. As \(X\) grows, the count is even for half the pairs and odd for half, provided \(R/\log X\to\infty\) and \(R\le X/100\). The ratio can grow arbitrarily slowly, and the conclusion holds uniformly over the choice of primes. For fixed-size tuples counted in translated windows, the paper also proves that every assignment of signs to the pairwise half-differences occurs with the same limiting frequency.

Why the scale matters. At \(R=\lfloor4\log X\rfloor\), one can select a positive proportion of the primes so that every counted pair has the same sign. There are still \(\gg X/\log X\) such pairs. This counterexample was derived and independently checked during extraction. It explains exactly where an arbitrary selection can defeat sign balance; the behavior of the full, unselected prime set at that width is a separate question.

Why this paper was selected. The requested shifted-prime audit in §308G.5 survived checks of the squarefree expansion, moving boundaries, genuinely free inner modulus, summed errors, and Euler factor \(2C_2\). Fiorilli’s Theorem 1.4 already supplies the outer range \(gk\le X^{1/10-\varepsilon}\). Every genuine twin atom has \(k=n\) and lies outside that corner. Section 308DJ gives a standalone conclusion about ordinary prime pairs. Its contribution is sign balance under arbitrary endpoint selection at this short scale. The draft credits Green–Tao and Shao for the sieve and collision estimates, and compares the result with earlier work on the parity of prime-factor counts in sumsets. arxiv.org

Separate AI proof and prior-art reviewers read the finished manuscript. They found no proof defect and no reviewed theorem giving the same conclusion at this scale. External peer review and a definitive priority determination remain outstanding. The theorem averages over many differences and leaves the twin-prime conjecture unresolved. The draft identifies GPT-6 Astra Pro’s substantive mathematical and writing contributions and credits DEEPAK KUMAR (admin@cosmosgeek.org) as research coordinator and contact, with human authorship pending.


---

## Fixed factor counts and the remaining twin-prime case — subsequent hosted review

These are working deductions under Propositions 4.2 and 5.3 of [Lü–Wang–Wu v2](https://arxiv.org/html/2610.20242v2). The two readers checked the implication from those propositions. The zero-forced-factor case remains unresolved. The independent reader supplied a multiplicity estimate missing from the first account.

### Derivation from the proof researcher

[Conversation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e-twin-prime-conjecture-research/c/6b05e53a-f038-83ee-99c9-ad2380de1583)

1. Audit verdict: the v2 statements suffice for the marked theorem

Using your transcription of v2, including its definition of $Q_Y$ in (4.7), the prime-cofactor transfer passes the proof audit.

The required logarithmic precision can also be reduced: a bound $Q_Y\ll xY(\log x)^{-4}$ suffices for the asymptotic main term. There is no circular dependence of the required precision on the number of banks $K$.

I attempted to reopen the v2 manuscript, including its PDF and alternative arXiv endpoints; the full text remains inaccessible through my browser. Accordingly, the following verifies the deduction from the precise propositions you supplied, not the underlying proofs of those propositions.

There is a new obstruction at the empty-tag endpoint as well: I can calculate substantial contributions of both signs on actual unmarked Vaughan rows whose cofactors avoid every possible selected bank.

2. Fix all logarithmic losses before choosing $K$

Retain the previous definitions

$$
L=\log x,\qquad Z=\exp(L^{0.24}),
\qquad U_0=V_0=x^{1/5}.
$$

For the $K$ disjoint banks, put

$$
\mathcal A=\{r_1\cdots r_K:r_i\in\mathcal P_i\},
\qquad
\mathcal V=\prod_{i=1}^K
\sum_{r\in\mathcal P_i}\frac1r.
$$

The cofactor weight is

$$
f(h)=\Lambda(h)-\frac{R_Z(h)}{V(Z)},
\qquad
V(Z)=\prod_{q\le Z}(1-1/q),
$$

and the marked weight on the original Vaughan variable is

$$
F(t)=\frac1{\mathcal V}
\sum_{\substack{a\in\mathcal A\\a\mid t+2}}
f((t+2)/a).
$$

Two uniform norm bounds

For $t\asymp x$,

$$
\boxed{|F(t)|\ll_K L.}
\tag{1}
$$

Here is the complete uniqueness check behind this bound.

If $(t+2)/a$ is $Z$-rough, the tag $a$ must be exactly the full small-prime part of $t+2$. There is at most one such tag.

If $(t+2)/a$ is a prime power, there is again at most one tag. Two different cofactor prime bases would force a prime power of size $x^{1-o(1)}$ to divide a subpower tag. If the bases agree, any difference in their exponents would change the number of prime factors in the squarefree tags, contradicting the fixed rank $K$.

Thus at most one tag contributes to each of the two components of $f$. Also,

$$
\mathcal V\longrightarrow(\log2)^K>0
$$

for fixed bank exponents. Its reciprocal affects the implied constant, not the logarithmic exponent.

The sharper bound needed for Type II is

$$
\boxed{
\sum_{h\le H}|f(h)|^2\ll HL,
\qquad H\asymp x/Y.
}
\tag{2}
$$

Indeed,

$$
\sum_{h\le H}\Lambda(h)^2
\le \log H\sum_{h\le H}\Lambda(h)
\ll HL
$$

by Chebyshev's bound. Furthermore,

$$
\sum_{h\le H}
\left|\frac{R_Z(h)}{V(Z)}\right|^2
\le \frac{H}{V(Z)^2}
\ll H L^{0.48}.
$$

Both estimates are uniform over the subpower tag scales, and neither incurs a logarithmic exponent depending on $K$.

3. Type I: exact Vaughan decomposition and local factors

The identity to use is

$$
\begin{aligned}
\Lambda={}&
\mu_{\le U_0}*\log
-\mu_{\le U_0}*1*\Lambda_{\le V_0}\\
&+\Lambda_{\le V_0}
+\mu_{>U_0}*1*\Lambda_{>V_0}.
\end{aligned}
$$

Multiplying by $R_Z(t)$ is legitimate because the original primes in the dyad exceed $Z$. On the von Mangoldt source, the only changed values are proper prime powers, whose total contribution against (1) is power-small.

The factor $R_Z(t)$ splits exactly across every convolution factor. In the second Type I term, grouping the short variables into $d$ gives

$$
d\le x^{2/5},\qquad
\left|(\mu_{\le U_0}*\Lambda_{\le V_0})(d)\right|
\le\log d.
$$

The term $\Lambda_{\le V_0}(t)$ vanishes on the original interval.

Open the remaining inner roughness condition by Bonferroni truncation at order $R=\lceil C_A\log L\rceil$. Separate parity, and write $b$ for an opened divisor composed of odd primes at most $Z$.

Every retained modulus satisfies

$$
b\le Z^{R+1}=x^{o(1)}.
$$

The absolute error from this opening, using (1), is bounded by

$$
\ll_K L^2\left[
xL\frac{(\sum_{3\le q\le Z}1/q)^{R+1}}{(R+1)!}
+x^{2/5}Z^{R+1}
\right].
$$

Since the reciprocal prime sum is $O(\log L)$, the error is $O_{A,K}(xL^{-A})$ after choosing $C_A$.

Check the actual progression

For each tag $a$, the equation is

$$
ah-2=dk.
$$

The conditions $b\mid k$ and $k$ odd impose one residue class on $h$ modulo $2db$.

If $(a,db)>1$, there is no solution. Otherwise the class is reduced: all factors of $db$ are odd, and the numerator determining the class is congruent to $2$ modulo $db$.

The progression scale and modulus satisfy

$$
H_a=x/a=x^{1-o(1)},
\qquad
2db\le x^{2/5+o(1)}.
$$

There is therefore a fixed power margin for ordinary maximal Bombieri–Vinogradov.

For the rough approximant, direct inclusion–exclusion on the same reduced class gives principal density

$$
\frac1{2db}
\prod_{\substack{q\mid 2db\\q\le Z}}
(1-1/q)^{-1}.
$$

Because every factor of $d$ exceeds $Z$, this is

$$
\frac1{\varphi(2db)}
\prod_{q\mid d}(1-1/q).
$$

Its relative difference from the von Mangoldt principal is

$$
O(L/Z),
$$

uniformly in the entire short-divisor range.

This is the precise local-factor comparison. No independence of the cofactor is required.

Check the summed errors

The decomposition of $2db$ is unique because $d$ is $Z$-rough and $b$ is supported on primes at most $Z$. For each fixed tag, the progression errors cost

$$
O_A\bigl((x/a)L^{-A}\bigr)
$$

after requesting sufficient logarithmic precision and using partial summation for the first Type I logarithm.

The rough-reference floor errors total $x^{2/5+o(1)}$ after summing all the opened variables and tags.

Finally,

$$
\frac1{\mathcal V}\sum_{a\in\mathcal A}\frac1a=1
$$

exactly.

Hence both complete Type I contributions are $O_{A,K}(xL^{-A})$.

This part of the bridge is unconditional and its logarithmic losses have fixed exponents independent of $K$.

4. Type II: remove the hyperbolic cutoff without modifying the Möbius row

This is where the clarified v2 hypotheses improve the previous audit.

We need not assume Proposition 5.3 allows arbitrary truncation of its Möbius coefficient inside a dyad. The common Mellin phases suffice.

Step A: choose the smoothing before $K$

Set

$$
\varepsilon=L^{-6}.
$$

Choose a smooth function $W_\varepsilon(v)$ approximating the indicator of $0<v\le\log2$, with transition intervals of width $\varepsilon$.

Replace

$$
1_{x<mn\le2x}
$$

by

$$
W_\varepsilon(\log(mn/x)).
$$

The difference is supported on two intervals of length $O(\varepsilon x)$.

The Type II coefficient is bounded by $L$ per factorization, and (1) bounds the marked weight by $O_K(L)$. The elementary interval divisor estimate

$$
\sum_{u<t\le u+H}\tau(t)
\ll H\log x+\sqrt x
$$

for $t\asymp x$ therefore gives the complete smoothing error

$$
\boxed{
E_{\rm boundary}\ll_K
xL^{-3}+\sqrt x\,L^2=o(x).
}
\tag{3}
$$

The logarithmic exponent is independent of $K$.

Step B: preserve the exact coefficient hypotheses

Partition $m>U_0$ and $n>V_0$ into dyadic intervals starting at those cutoffs. Only $O(L)$ pairs of dyads have products intersecting the smoothed support.

This last count is $O(L)$, not $O(L^2)$: for each $m$-dyad, only boundedly many $n$-dyads have $MN\asymp x$.

On every such rectangle, Mellin inversion introduces precisely the coefficient phases

$$
\alpha_m=\mu(m)R_Z(m)m^{iv},
$$

$$
\beta_n=c_{V_0}(n)R_Z(n)n^{iv}.
$$

Thus we can fix

$$
\delta=\frac1{10},\qquad C=2.
$$

Every ambient dyadic length exceeds $x^\delta$, and the prescribed coefficient bounds hold independently of $K$.

The Mellin transform satisfies

$$
|\widehat W_\varepsilon(v)|
\ll
\min\left(1,\frac1{|v|},
\frac1{\varepsilon |v|^2}\right).
$$

This follows from the bounded total variation and the $O(\varepsilon^{-1})$ integral of its second derivative. In particular,

$$
\int_{\mathbb R}|\widehat W_\varepsilon(v)|\,dv
\ll\log L.
\tag{4}
$$

If a truncation of the Mellin integral is needed, taking $|v|\le L^{15}$ leaves a tail of size $O(L^{-9})$. The crude absolute Type II bound over all the retained rectangles is $O_K(xL^3)$, so the discarded Mellin tail contributes $O_K(xL^{-6})$.

This calculation uses the common-phase uniformity in the v2 statements you supplied. In particular, it requires uniformity over the retained phase range, not merely a separate estimate for each fixed $v$.

Step C: apply the two v2 energy propositions

Write the dyadically localized switched coefficient as

$$
\mathcal F_Y(h)=
\frac1{\mathcal V}
\sum_{\substack{mn+2=ah\\a\in\mathcal A}}
\eta(a/Y)\alpha_m\beta_n.
$$

Here $\eta$ is a fixed admissible smooth dyadic cutoff.

The energy in v2 equation (4.7) is

$$
Q_Y=\sum_h|\mathcal F_Y(h)|^2.
$$

Your supplied Proposition 4.2, followed by Proposition 5.3 with the same admissible parameters, gives

$$
Q_Y\ll_D xY L^{-D}.
$$

There is no need to insert the cofactor weight $f$ into either proposition.

By (2),

$$
\begin{aligned}
\left|\sum_h f(h)\mathcal F_Y(h)\right|
&\le
\left(\sum_{h\ll x/Y}|f(h)|^2\right)^{1/2}
Q_Y^{1/2}\\
&\ll x L^{(1-D)/2}.
\end{aligned}
\tag{5}
$$

All tag products satisfy

$$
\log a\le2K L^{0.2}.
$$

Consequently, a fixed smooth dyadic partition of the tag-product range has $O_K(L^{0.2})$ nonempty pieces.

Combining (4), (5), the $O(L)$ ambient rectangle count, and the tag-product partition gives

$$
\boxed{
|T_3(F)|
\ll_K xL^{17/10-D/2}\log L+o(x).
}
\tag{6}
$$

Taking $D=4$ makes this

$$
O_K(xL^{-3/10}\log L)+o(x)=o(x).
$$

Parameter-order conclusion

The valid order of choices is:

Fix the Vaughan cutoffs, $\delta,C$, and smoothing exponent $6$.

Request energy precision $D=4$, including the common Mellin phases.

Choose the common admissible $A_0,K$ furnished by the two propositions.

Fix the ordered bank exponents and let $x\to\infty$.

The crucial estimates are (1) and (2): neither has a logarithmic exponent growing with $K$.

Thus there is no circular choice of $K$.

The improved precision requirement may reduce the number of banks needed in the authors' quantitative proof. But without their explicit dependence of $K$ on $A_0,D,C,\delta$, it does not establish any particular smaller numerical value of $K$.

5. Finish the main-term calculation

The preceding Type I and Type II estimates establish, from the supplied propositions,

$$
\frac1{\mathcal V}
\sum_{a\in\mathcal A}
\sum_{\substack{x<p\le2x\\a\mid p+2}}
(\log p)
\left[
\Lambda((p+2)/a)
-\frac{R_Z((p+2)/a)}{V(Z)}
\right]
=o(x).
\tag{7}
$$

Proper prime powers in the original source contribute negligibly by (1).

The rough-reference term is unconditional. For each tag $a$, the conditional divisor density is

$$
g_a(q)=\frac{\varphi(a)}{\varphi(aq)}
=
\begin{cases}
1/q,&q\mid a,\\
1/(q-1),&q\nmid a.
\end{cases}
$$

Thus its principal factor is

$$
\frac1{V(Z)}
\prod_{3\le q\le Z}(1-g_a(q))
=
\mathfrak S_Z
\prod_{q\mid a}
\frac{(q-1)^2}{q(q-2)},
$$

where

$$
\mathfrak S_Z=
2\prod_{3\le q\le Z}
\left(1-\frac1{(q-1)^2}\right).
$$

The extra factors tend to one uniformly over the tags for fixed $K$. The same holds for $\varphi(a)/a$, since their least prime factor tends to infinity.

Opening the roughness sieve uses only subpower moduli, and its reciprocal factorial remainder is arbitrarily logarithmically small.

Therefore the complete normalized reference term is

$$
\mathfrak S x+o(x).
$$

Substituting into (7),

$$
\sum_{a\in\mathcal A}
\sum_{\substack{x<p\le2x\\a\mid p+2}}
(\log p)\Lambda((p+2)/a)
\sim\mathfrak S x\mathcal V.
$$

Proper cofactor prime powers cost $x^{1/2+o(1)}L^2$, using the subpower number of possible tags.

On every remaining term, both prime logarithms are $(1+o(1))L$. This proves the claimed genuine prime-cofactor asymptotic:

$$
\boxed{
\#\{x<p\le2x:p+2=r_1\cdots r_Kq,\
r_i\in\mathcal P_i,\ q\text{ prime}\}
\sim
\mathfrak S(\log2)^K\frac{x}{L^2}.
}
\tag{8}
$$

The edition clarification also resolves the quantifier needed for integrating the bank exponents: the same $K$ can be chosen independently of every fixed ordered exponent tuple.

Fatou's lemma, followed by the exact bank-membership interval length $\log2/\log\log x$, therefore gives the previously proposed individual-rank consequence:

$$
\boxed{
\liminf_{X\to\infty}
\frac{\log^2X\,A_{K+1}(X)}
{X(\log\log X)^K}
\ge C_2\frac{0.1^K}{K!}.
}
\tag{9}
$$

No uniform convergence near overlapping exponent tuples is needed.

The deduction of (8)–(9) is complete, given Propositions 4.2 and 5.3 as supplied. There is no additional unproved Type I, smoothing, or integration step in this deduction.

6. Attempt to reduce the number of forced factors

I tested whether the $K$-bank estimate can be used as an operator estimate with only $k<K$ retained banks.

Let $\mathcal A_k$ denote the products from the retained banks and $\mathcal B$ the products from the omitted banks. For a cofactor function $g$, define

$$
\mathcal D_{\mathcal B}g(h)
=
\frac1{\mathcal V_{\mathcal B}}
\sum_{\substack{b\in\mathcal B\\b\mid h}}g(h/b).
$$

There is an exact operator identity:

$$
\text{\(K\)-bank functional at \(g\)}
=
\text{\(k\)-bank functional at }
\mathcal D_{\mathcal B}g.
\tag{10}
$$

Thus reducing the number of forced factors by this mechanism would require recovering $f$ from the range of the omitted-bank operator.

But for every $Z$-rough $h$,

$$
\mathcal D_{\mathcal B}g(h)=0
$$

regardless of $g$. Every omitted-bank product has at least one prime factor below $Z$.

The desired weight

$$
f(h)=\Lambda(h)-R_Z(h)/V(Z)
$$

does not vanish there.

Averaging over bank positions, allowing signed combinations, or increasing the number of available banks does not remove this exact support restriction.

The question is whether the omitted $Z$-rough population might nevertheless be negligible in the actual signed Vaughan pairing.

It is not negligible in absolute variation, as the following new calculation shows.

7. An unconditional, signed obstruction on the actual empty-tag rows

Define the complete unmarked Type II coefficient

$$
C(t)=
\sum_{\substack{mn=t\\m>U_0}}
\mu(m)R_Z(m)c_{V_0}(n)R_Z(n).
$$

I calculate two disjoint arithmetic families on which the exact contribution $C(t)f(t+2)$, restricted to rough composite cofactors, has opposite signs and magnitude comparable to $x$.

These are genuine terms of the original Vaughan identity, not invented reference coefficients.

Family A: a negative Vaughan coefficient

Take

$$
t=rs,\qquad
x^{1/4}<r\le x^{1/3},\qquad
x/r<s\le2x/r,
$$

where $r,s$ are prime.

Both factors exceed $U_0=V_0$. The only nonzero decompositions in the complete coefficient are the two orientations, giving

$$
C(rs)=-\log s-\log r=-\log t.
\tag{11}
$$

For each fixed $r$, sieve the genuine prime variable $s$ by the condition $P^-(rs+2)>Z$.

Truncated inclusion–exclusion and Bombieri–Vinogradov at scale $x/r$ give uniformly

$$
\frac1{V(Z)}
\sum_{\substack{x/r<s\le2x/r\\s\text{ prime}}}
\log s\,R_Z(rs+2)
=
(\mathfrak S+o(1))\frac xr.
\tag{12}
$$

Indeed, every odd sieving prime $q\le Z$ excludes one reduced class for $s$, because $r>Z$. The opened moduli are subpower, and their principal product divided by $V(Z)$ tends to $\mathfrak S$.

On the relevant dyad,

$$
\frac{\log t}{\log s}
=
\frac1{1-\log r/L}+O(1/L).
$$

Summing (12) over genuine prime $r$, Mertens' theorem gives

$$
\sum_{\text{Family A}}
\log t\,\frac{R_Z(t+2)}{V(Z)}
\sim
\mathfrak S x
\int_{1/4}^{1/3}\frac{du}{u(1-u)}.
$$

The integral is exactly $\log(3/2)$.

Remove all prime and prime-power cofactors

For fixed $r$, a two-form upper sieve for $s,rs+2$ gives

$$
\#\{s\text{ prime}:rs+2\text{ prime}\}
\ll\frac{x}{rL^2}.
$$

This bound is uniform in $r$. One can obtain it directly by upper-sieving the two forms through $x^\kappa$ for a sufficiently small fixed $\kappa>0$. All odd sieving primes are below $r$, and the two forms have distinct forbidden classes. The blockwise Bonferroni sieve has a bounded relative principal error and a power-small floor error, with its opened modulus level chosen below $x^{1/2}$.

The contribution of these prime cofactors to the preceding reference sum is consequently

$$
O\left(\frac{x\log Z}{L}\right)=o(x).
$$

Proper prime-power cofactors are also negligible: each numerical $t$ has at most one representation in this family.

Therefore, on the actual rough composite non-prime-power cofactors, where $f(t+2)=-1/V(Z)$, we have proved

$$
\boxed{
\sum_{\substack{t\in\text{Family A}\\
R_Z(t+2)=1,\ \Lambda(t+2)=0}}
C(t)f(t+2)
\sim
+\mathfrak S x\log(3/2).
}
\tag{13}
$$

The contribution is strictly positive.

Family B: a positive Vaughan coefficient

Now take

$$
t=rsq,
$$

where all three factors are genuine primes and

$$
x^{0.11}<r\le x^{0.12},
\qquad
x^{0.13}<s\le x^{0.14},
\qquad
x<rsq\le2x.
$$

Here $r,s<U_0$, but $rs>U_0$, and $q>V_0$.

The only nonzero Type II factorization is $m=rs,n=q$. Thus

$$
C(rsq)=+\log q.
\tag{14}
$$

For each fixed pair $r,s$, apply exactly the sieve calculation (12) to the genuine prime variable $q$, with coefficient $rs$ in place of $r$.

The cofactor scale is at least $x^{0.74}$; every selected factor exceeds $Z$; the opened congruences have the same local factors and remain within Bombieri–Vinogradov.

Summing gives

$$
\sum_{\text{Family B}}
\log q\,\frac{R_Z(t+2)}{V(Z)}
\sim
\mathfrak S x
\log\frac{12}{11}\log\frac{14}{13}.
$$

Removing prime and proper prime-power cofactors again costs $o(x)$, using the uniform two-form upper sieve and unique factorization in the specified ranges.

Consequently,

$$
\boxed{
\sum_{\substack{t\in\text{Family B}\\
R_Z(t+2)=1,\ \Lambda(t+2)=0}}
C(t)f(t+2)
\sim
-\mathfrak S x
\log\frac{12}{11}\log\frac{14}{13}.
}
\tag{15}
$$

This contribution is strictly negative.

What these two calculations establish

Every cofactor contributing to (13) or (15) avoids all possible banks in the specified exponent range.

Therefore no combination of the forced-factor operators in (10) sees these terms.

Yet the omitted signed pairing has both positive and negative variations of order at least $x$. This proves that deleting the unmarked complement cannot be justified by an absolute-error argument at the required main-term scale.

It does not prove that its net signed contribution has either sign. That is the remaining arithmetic issue.

8. Check the empty-tag energy and propagate to the twin count

The first family also strengthens the energy obstruction for the full recombined unmarked coefficient.

From (13), since $|C(t)|\asymp L$ on that family,

$$
\boxed{
\sum_{\substack{x<t\le2x\\R_Z(t+2)=1}}
|C(t)|^2
\gg xLV(Z)
\asymp\frac{xL}{\log Z}.
}
\tag{16}
$$

This is a lower bound on the actual coefficient, after complete recombination.

Even on a single admissible ambient rectangle $M\asymp x^{1/3},N\asymp x^{2/3}$, the prime-by-prime witness gives

$$
Q_{\rm empty,\ rough}\gg\frac{x}{\log Z}.
$$

Thus the needed $xL^{-4}$ empty-tag energy estimate is false for these genuine rows. It is not simply missing from the statements of the propositions.

For the full unmarked cofactor weight, its squared norm is at least of order $xL$, because of its values at genuine primes. The ordinary Cauchy–Schwarz budget using (16) is therefore at least of order

$$
\frac{xL}{\sqrt{\log Z}}
=xL^{0.88}.
$$

This is much larger than $x$.

Nevertheless, the unconditional Type I calculation still works with $a=1$. The reference principal is then $\mathfrak S x+o(x)$. Consequently the exact remaining obligation for ordinary twins is

$$
\sum_{\substack{x<p\le2x\\p+2\text{ prime}}}
\log p\log(p+2)
=
\mathfrak S x+
\sum_{x<t\le2x}C(t)f(t+2)+o(x).
$$

It would suffice to prove

$$
\boxed{
\sum_{x<t\le2x}C(t)f(t+2)
\ge-(\mathfrak S-\eta)x
}
\tag{17}
$$

for some fixed $\eta>0$ along an unbounded sequence.

The independently evaluated opposite-sign families in (13) and (15) belong to this exact sum. Neither can be omitted or credited twice.

Conclusion

The proof audit establishes three distinct outcomes.

Question

Result

Does the prime-minus-rough cofactor replacement follow from the supplied v2 propositions?

Yes.

Is the choice of $K$ circular?

No. Energy precision $D=4$ suffices, with all logarithmic losses fixed beforehand.

Can the forced factors be removed using the same energy or a negligible mark-removal error?

No by those mechanisms. The empty-tag energy and actual omitted signed variations are too large.

The genuine prime-cofactor asymptotic and positive individual Ford coefficient survive as rigorous consequences of the supplied v2 propositions. Independent validation of those propositions' proofs remains outside this deduction.

The new unconditional result is the explicit calculation of the two opposite-sign, bank-free populations in (13)–(15). It pinpoints what any successful reduction to the empty tag must control: the signed cancellation on arithmetic rows that every positive-rank bank operator entirely misses.

I chose the smoothing parameters, reduced precision requirement and witness intervals independently. No private records were inspected, no files or manuscripts were produced, and the strict inequality (17) remains unproved.

### Independent proof review

[Conversation](https://chatgpt.com/c/6b05f83f-e2ac-83ee-972e-14d9c933ff41)

Independent review verdict

The deduction of (9) survives my examination as a consequence of the stated v2 energy propositions. I have not found a fatal error in the transfer from the marked Type II estimate to an individual fixed-rank lower bound for actual shifted primes $p+2$.

Importantly, I was able to access the actual Lü–Wang–Wu v2 manuscript, dated 19 November 2026, rather than relying on the earlier transcription. Its definition of $Q_Y$, Proposition 4.2, Proposition 5.3 and the permitted Mellin phases agree with the essential inputs used in the attached derivation. 

arXiv+3

This is a positive audit of the implication, not yet an independent certification of the underlying proofs of those two substantial energy propositions.

1. Adversarial audit of the individual steps

Component

Verdict

Vaughan identity and roughness insertion

Pass

Type I progression and local factors

Pass

Type I summed error estimates

Pass

Type II localization and Mellin phases

Pass

Application of the actual v2 propositions

Pass, subject to their correctness

Choice of $K$ and logarithmic precision

Pass

Rough-reference main term

Pass after explicit multiplicity bookkeeping

Repeated prime factors

Pass

Fatou integration and boundary effects

Pass

Reduction to rank one

Not established

2. Type I: no hidden distribution hypothesis

The essential progression in the attachment is

$$
ah-2=dk,
$$

where $d$ is $Z$-rough. Opening the roughness condition on $k$ introduces an odd squarefree divisor $b\mid k$.

Since $k$ must be odd,

$$
ah\equiv 2+db\pmod{2db}.
$$

If $(a,db)>1$, there is no solution. Otherwise this determines one reduced residue class for $h$.

The important size comparison is

$$
H_a\asymp \frac{x}{a}=x^{1-o(1)},
$$

whereas

$$
2db\leq x^{2/5+o(1)}.
$$

This genuinely lies within the ordinary Bombieri–Vinogradov range at scale $H_a$. There is no concealed use of Elliott–Halberstam.

For the rough-reference weight, the density in this progression is

$$
\frac{1}{2db}
\prod_{\substack{\ell\mid 2db\\\ell\le Z}}
(1-1/\ell)^{-1}.
$$

Since $d$ is $Z$-rough, this equals

$$
\frac{1}{\varphi(2db)}
\prod_{\ell\mid d}(1-1/\ell).
$$

The final product differs from one by $O(L/Z)$. This is sufficiently small to absorb every fixed logarithmic loss.

I also checked the potentially dangerous summation over tags. For each fixed $a$, Bombieri–Vinogradov supplies an error of size

$$
O_A\left(\frac{x}{a}L^{-A}\right),
$$

rather than $O_A(xL^{-A})$. The distinction is essential because there are subexponentially many tags.

The normalization then gives exactly

$$
\frac1{\mathcal V}\sum_{a\in\mathcal A}\frac xa=x.
$$

The Type I estimates therefore survive.

3. Type II: the decisive source comparison

The strongest concern was whether the attachment had silently generalized a result restricted to Möbius-weighted cofactors into an estimate for arbitrary cofactor weights.

The actual equation (4.7) resolves this concern.

The energy is precisely

$$
Q_Y=
\frac{1}{\mathcal V^2}
\sum_{h\ge1}
\left|
\sum_{a\in\mathcal A}\eta(a/Y)
\sum_{mn+2=ah}\alpha_m\beta_n
\right|^2.
$$

There is no Möbius, Liouville or squarefreeness restriction on $h$ in this definition.

Proposition 4.2, on page 18, controls the difference between this energy and its major-arc approximation. Proposition 5.3, on page 63, controls the approximation with the prescribed Möbius row and explicitly permits common Mellin phases. 

arXiv+2

Consequently, assuming those propositions, one can pair the switched coefficient with

$$
f(h)=\Lambda(h)-\frac{R_Z(h)}{V(Z)}
$$

without proving a new Type II theorem.

The norm estimate

$$
\sum_{h\le H}|f(h)|^2\ll HL
$$

is sufficient. In particular,

$$
\sum_{h\le H}\frac{R_Z(h)^2}{V(Z)^2}
\ll HL^{0.48}=o(HL).
$$

Cauchy–Schwarz therefore gives, on each localized piece,

$$
\left|\sum_h f(h)\mathcal F_Y(h)\right|
\ll
\left(\frac{xL}{Y}\right)^{1/2}
\left(xYL^{-D}\right)^{1/2}
=
xL^{(1-D)/2}.
$$

This is the central valid deduction in the attachment.

Boundary localization

The proposed smoothing width $L^{-6}$ is sufficient. Using the elementary short-interval divisor estimate and the pointwise bound on $F$, the boundary error is

$$
O_K(xL^{-3}+\sqrt{x}L^2)=o(x).
$$

The Mellin transform has $L^1$-norm $O(\log L)$. Truncating at $L^{15}$ leaves an error $O_K(xL^{-6})$.

Neither operation changes the required Möbius coefficient into an inadmissible arbitrary sequence.

4. The dependence on $K$ is not circular

The losses in the Type II calculation are as follows.

Source

Loss

Cofactor squared norm

$L^{1/2}$

Ambient dyadic rectangles

$L$

Tag-product dyadic intervals

$O_K(L^{1/5})$

Mellin integration

$\log L$

Energy saving

$L^{-D/2}$

Thus the combined bound is

$$
O_K\left(xL^{17/10-D/2}\log L\right)+o(x).
$$

Taking $D=4$ gives

$$
O_K(xL^{-3/10}\log L)+o(x)=o(x).
$$

The precision requirement can be selected before $K$.

More importantly, the actual Proposition 4.2 explicitly permits the choice of $K$ independently of the fixed bank exponents. This is exactly the quantifier needed later for Fatou's lemma.

Some elementary sieve error constants can depend on $K$. That is harmless: their precision can be increased after $K$ is fixed, without requiring a stronger Type II estimate.

No numerical value of $K$, however, has been established by this audit.

5. One omitted detail in the rough-reference calculation

The closest thing I found to an incomplete step is in Section 5 of the attachment, between (7) and (8).

Merely noting that the opened moduli are subpower does not, by itself, justify summing Bombieri–Vinogradov errors over all tags. Multiple pairs $(a,b)$ can produce the same modulus $ab$.

Fortunately, this has an elementary repair.

If the Bonferroni expansion retains at most $R+1$ primes in $b$, the modulus $ab$ has at most $K+R+1$ distinct prime factors. Its multiplicity as a product of a valid tag and an opened divisor is at most

$$
(K+R+1)^K.
$$

For fixed $K$ and $R=O(\log L)$, this is absorbed by choosing sufficient logarithmic precision in Bombieri–Vinogradov.

The conditional divisor densities are also correct:

$$
g_a(q)=
\begin{cases}
1/q,&q\mid a,\\
1/(q-1),&q\nmid a.
\end{cases}
$$

In particular, when $q\mid a$, the modulus is divisible by $q^2$. The calculation accounts for this rather than mistakenly treating $q$ as a fresh prime divisor.

The normalized reference main term is therefore indeed

$$
\mathfrak S x+o(x),
\qquad
\mathfrak S=
2\prod_{q>2}\left(1-\frac1{(q-1)^2}\right).
$$

This is an omitted justification, not a fatal obstruction.

6. Repeated factors and exact rank

The distinction between

$$
\omega(n)=\#\{\text{distinct prime divisors of }n\}
$$

and

$$
\Omega(n)=\#\{\text{prime divisors counted with multiplicity}\}
$$

must be preserved.

The construction is stronger than necessary because it ultimately counts squarefree shifted primes.

For a fixed ordered exponent tuple, the banks are disjoint for sufficiently large $x$. Therefore the tag

$$
a=r_1\cdots r_K
$$

is squarefree.

After discarding proper prime-power cofactors, the remaining cofactor is a genuine prime satisfying

$$
q=\frac{p+2}{a}=x^{1-o(1)}>Z.
$$

Every bank prime lies below $Z$. Consequently, $q$ cannot equal any of the $r_i$.

Thus every surviving shifted prime satisfies

$$
\mu^2(p+2)=1,\qquad
\omega(p+2)=\Omega(p+2)=K+1.
$$

The discarded proper prime-power cofactors contribute at most $x^{1/2+o(1)}L^2$ to the weighted sum, using the subpower bound on the number of tags. This is negligible.

There is no transition here from a marked count to an unjustified count of numerical integers.

7. Fatou's lemma: independent reconstruction of (9)

This is the part I examined most carefully, since it converts a sparse marked asymptotic into a full-order individual-rank lower bound.

Define the fixed simplex

$$
\Delta_K=
\left\{
\boldsymbol u:
\frac1{10}<u_1<\cdots<u_K<\frac15
\right\}.
$$

Its volume is

$$
|\Delta_K|=\frac{0.1^K}{K!}.
$$

Let $B_x(\boldsymbol u)$ denote the count in (8), defining it to be zero whenever the banks at that particular $x$ overlap.

For each fixed $\boldsymbol u\in\Delta_K$, the banks eventually become disjoint and the marked asymptotic gives

$$
\frac{L^2}{x}B_x(\boldsymbol u)
\longrightarrow
\mathfrak S(\log2)^K.
$$

The functions are measurable and nonnegative. Fatou therefore gives

$$
\liminf_{x\to\infty}
\frac{L^2}{x}
\int_{\Delta_K}B_x(\boldsymbol u)\,d\boldsymbol u
\ge
\mathfrak S(\log2)^K
\frac{0.1^K}{K!}.
$$

Now fix a numerical prime $r$. Its membership in a bank of exponent $u$ is equivalent to

$$
L^u<\log r\leq2L^u.
$$

The corresponding exponent interval has length exactly

$$
w_x=\frac{\log2}{\log L},
$$

before intersection with the permitted exponent range.

For an individual counted $p$, its $K$ small prime factors must occupy the ordered banks in increasing order. The volume of exponent tuples that count this $p$ is consequently at most $w_x^K$.

There is no additional $K!$ multiplicity: the ordering has already fixed the assignment.

Writing

$$
A_j(X)=\#\{p\le X:\omega(p+2)=j\},
$$

we obtain

$$
\int_{\Delta_K}B_x(\boldsymbol u)\,d\boldsymbol u
\le
\left(\frac{\log2}{\log L}\right)^K
\bigl(A_{K+1}(2x)-A_{K+1}(x)\bigr).
$$

Combining these inequalities proves

$$
\boxed{
\liminf_{x\to\infty}
\frac{\log^2 x\,
[A_{K+1}(2x)-A_{K+1}(x)]}
{x(\log\log x)^K}
\ge
\mathfrak S\frac{0.1^K}{K!}.
}
$$

This establishes the attachment's (9), with $X=2x$ and $C_2=\mathfrak S/2$.

Neither uniform convergence near the boundary of the simplex nor an interchange of a signed integral and a limit is required.

A small additional strengthening

The same argument also shows that the factor $C_2$ in (9) is conservative. Summing any fixed finite number of descending dyadic intervals, and then letting their number increase, gives

$$
\boxed{
\liminf_{X\to\infty}
\frac{\log^2X\,A_{K+1}(X)}
{X(\log\log X)^K}
\ge
2C_2\frac{0.1^K}{K!}.
}
$$

This strengthening uses no new analytic estimate. It is simply a consequence of the verified dyadic lower bound. It also holds when $A_{K+1}$ counts only squarefree shifted primes.

8. Comparison with Timofeev and the primary literature

I recovered the original Russian paper of N. M. Timofeev:

The Hardy–Ramanujan and Halasz inequalities for shifted primes, Mathematical Notes 57 (1995), 522–535.

I inspected Theorem 3 on original Russian page 749, rather than relying exclusively on later citations.

Its first lower-bound assertion, in the notation $P_g(m,x)=\#\{p\le x:g(p+2)=m\}$, is

$$
P_g(m,x)+P_g(m+1,x)
\ge
c_6\frac{x(\log\log x)^{m-1}}
{(m-1)!\log^2x}.
$$

The ranges are:

$1\le m\le(2-\delta)\log\log x$ for $g=\Omega$.

$1\le m\le b\log\log x$ for $g=\omega$.

The theorem also contains a separate large-$\Omega$ regime and a restricted-prime-factor result involving three adjacent counts. 

Math-Net.Ru+1

The distinction from the proposed result is substantive.

Result

Count controlled

Chen

At most two prime factors

Timofeev, Theorem 3

Two adjacent ranks

Ford, Corollary 1

Upper bound for an individual rank

Proposed consequence of v2

Positive lower bound for one fixed individual rank

Kevin Ford's author version of A Hardy-Ramanujan type inequality for shifted primes and sifted sets, dated 19 March 2025, explicitly identifies the individual-rank lower bound as unresolved. His Corollary 1 supplies the corresponding upper-bound order. 

ford126.web.illinois.edu+1

There is also a directly relevant primary paper by Eugene K.-S. Ng, A Conditional Resolution of the Parity Problem in Sieve Theory, Journal of Number Theory 40 (1992), 329–335. It establishes a lower bound for exactly two prime factors of $p+2$, but assumes Elliott–Halberstam and an additional strengthened upper estimate for three-prime cofactors. 

ScienceDirect+1

I did not locate an earlier unconditional individual-fixed-rank lower bound of the required order for actual $p+2$. That is a bounded literature finding, not an exhaustive priority determination.

If the v2 energy propositions are correct, the attached result supplies the conjecturally correct order of magnitude for at least one fixed individual rank, by combining its lower bound with Ford's upper bound.

9. Does this give anything about rank one?

No.

The verified existence quantifier is

$$
\exists K\ge1:
\quad
A_{K+1}(X)\gg_K
\frac{X(\log\log X)^K}{\log^2X}.
$$

It is not a statement for every $K\ge0$, and in particular does not permit setting $K=0$.

I also checked the attachment's empty-tag obstruction. Its two families have the stated Vaughan coefficients:

$$
C(rs)=-\log(rs),
\qquad
C(rsq)=+\log q
$$

in the respective prescribed ranges.

Their opposite-sign contributions on rough composite cofactors are of order $x$. They cannot be discarded as an $o(x)$ absolute error.

Moreover, on the unmarked rows the elementary energy lower bound

$$
Q_{\mathrm{empty,rough}}\gg
\frac{x}{\log Z}
=\frac{x}{L^{0.24}}
$$

is incompatible with the desired empty-tag estimate $Q\ll xL^{-4}$.

This rules out the proposed direct extension of the same energy argument to empty tags. It does not rule out a different signed-cancellation argument.

The exact unresolved twin-prime obligation remains the attachment's (17):

$$
\sum_{x<t\le2x}C(t)f(t+2)
\ge-(\mathfrak S-\eta)x
$$

for some fixed $\eta>0$ along an unbounded sequence of $x$.

Final mathematical assessment

The precise surviving claim is:

Assuming Propositions 4.2 and 5.3 of Lü–Wang–Wu, arXiv:2610.20242v2, are correct as stated, there exists a fixed integer $j\ge2$ for which

[The displayed final formula was cut off here. The full single-rank conclusion is stated earlier in this review.]

### Integer moments and the missing absolute normalization

[Conversation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e-twin-prime-conjecture-research/c/6af40271-3984-8323-be2f-6636ab3bcca6)

Result: the integer-order moments do not supply the missing anchor

I found an exact obstruction to the proposed route. Even if every fixed integer-order generalized von Mangoldt mean were known with its conjectured leading constant, those constants would not force the strict lower bound required by §308CO.

This is stronger than the failure of a particular numerical estimate. It follows from an explicit identity showing that all integer orders $k\ge2$ are blind to a particular parity redistribution that eliminates the prime contribution entirely.

1. The precise fractional-order target

Put

$$
L=\log X,\qquad H=\log\log X,\qquad
K_0=2C_2,
$$

and, for $\alpha>0$, define

$$
Q_\alpha(m)=\sum_{d\mid m}\mu(d)
\left(\frac{\log(m/d)}{\log m}\right)^\alpha.
$$

The normalized inclusive mean on actual shifted primes is

$$
I_X(c)=\frac{L^2}{K_0X}
\sum_{\substack{X<P\le2X\\P\ {\rm prime}}}
Q_{1+c/H}(P+2).
$$

Let

$$
\tau_X=\frac{L^2}{K_0X}
\#\{X<P\le2X:P,P+2\ {\rm prime}\}.
$$

The internally proved §308CO absolute-value result states that the composite contribution has limiting absolute mass

$$
E(c)=1-e^{-c}.
$$

For $1<\alpha<2$, a non-prime-power composite $m$ has

$$
\operatorname{sgn}Q_\alpha(m)=(-1)^{\omega(m)}.
$$

Consequently, if $O_X(c)$ denotes the normalized absolute contribution from composites $P+2$ having an odd number of distinct prime factors, then

$$
\boxed{I_X(c)=E(c)+\tau_X-2O_X(c)+o(1).}
\tag{1}
$$

The proper-prime-power contribution is $o(1)$ at this normalization.

Thus the desired strict excess is exactly the requirement

$$
\boxed{\limsup_{X\to\infty}\bigl(\tau_X-2O_X(c)\bigr)>0.}
\tag{2}
$$

It is not enough to evaluate a positive generalized von Mangoldt mean: its contribution from odd-rank composites must also be controlled.

2. An exact integer-moment identity

For a squarefree product of $r$ primes with logarithmic shares $x_1,\ldots,x_r>0$, $\sum x_i=1$, set

$$
q_k(x_1,\ldots,x_r)
=\sum_{S\subseteq\{1,\ldots,r\}}(-1)^{|S|}
\left(1-\sum_{i\in S}x_i\right)^k.
$$

For an integer $k\ge1$, define its ordinary angular mass

$$
a_{k,r}=\frac1{r!}
\int_{\substack{x_i>0\\\sum x_i=1}}
q_k(x_1,\ldots,x_r)
\frac{dx_1\cdots dx_{r-1}}{x_1\cdots x_r}.
$$

The exact generating identity is

$$
\boxed{
\sum_{r=1}^{k}a_{k,r}z^r
=\frac{z(z+1)\cdots(z+k-1)}{(k-1)!}.
}
\tag{3}
$$

To prove it, introduce the Laplace transform in the total exponent and use Frullani's identity:

$$
\int_0^\infty e^{-sx}(e^{-tx}-1)\frac{dx}{x}
=\log\frac{s}{s+t}.
$$

Exponentiating with activity $z$, then differentiating $k$ times in $t$ at zero, gives

$$
\left.(-\partial_t)^k
\left(\frac{s}{s+t}\right)^z\right|_{t=0}
=\frac{z(z+1)\cdots(z+k-1)}{s^k}.
$$

Expanding the exponential by the number of factors and scaling $x_i$ by their sum gives the left side of (3), multiplied by $(k-1)!/s^k$. Finite differences ensure that ranks exceeding $k$ contribute zero.

For every $k\ge2$, substituting $z=1$ and $z=-1$ yields

$$
\sum_r a_{k,r}=k,\qquad
\sum_{r\ {\rm odd}}a_{k,r}
=\sum_{r\ {\rm even}}a_{k,r}=\frac{k}{2}.
\tag{4}
$$

Now change the ordinary angular density by multiplying rank $r$ by

$$
w_r=1+(-1)^r.
$$

This weight is nonnegative, equals zero at rank one, and doubles every even rank. Nevertheless,

$$
\sum_r w_r a_{k,r}=k
\qquad\text{for every fixed }k\ge2.
\tag{5}
$$

The formal comparison has no prime atom, yet it reproduces every fixed integer-order leading moment exactly. It is an angular information model, not a constructed sequence of actual shifted primes. Its role is to test what the moment constants can logically determine.

3. The exact published integer-order theorem, with its errors

Let

$$
\Lambda_k(n)=\sum_{d\mid n}\mu(d)\log^k(n/d),
\qquad Q_k(n)=\frac{\Lambda_k(n)}{(\log n)^k}.
$$

Define

$$
M_{k,X}=\frac{L^2}{K_0X}
\sum_{\substack{X<P\le2X\\P\ {\rm prime}}}Q_k(P+2).
$$

Unconditional input. Bombieri's asymptotic sieve, as recorded precisely by Kevin Ford in On Bombieri's asymptotic sieve, gives for the cumulative shifted-prime generalized von Mangoldt sums

$$
1-c_k+o_k(1)\le
\frac{\sum_{n\le x}\Lambda(n-2)\Lambda_k(n)}
{K_0k\,x(\log x)^{k-1}}
\le1+c_k+o_k(1),
\tag{6}
$$

for every fixed $k\ge2$, with $c_k\to0$ as $k\to\infty$. The orientation $n-2$ has the same fixed-residue sieve inputs as $n+2$. 

ford126.web.illinois.edu+1

The unconditional distribution input is Bombieri–Vinogradov at each fixed level $\nu<1/2$, applied to the primitive class $-2\bmod d$ for odd $d$. The underlying sequence is $a_n=\Lambda(n-2)$, with local density $1/\phi(d)$ for odd $d$ and zero for even $d$, apart from negligible exceptional powers.

Equation (6) is cumulative. Subtracting its upper and lower estimates at $2X$ and $X$, rather than assuming a stronger localized theorem, gives the conservative valid bounds

$$
\boxed{
k(1-3c_k)+o_k(1)\le M_{k,X}
\le k(1+3c_k)+o_k(1).
}
\tag{7}
$$

The denominator conversion costs $O_k(1/L)$ in normalized units, and proper prime powers in the $\Lambda(n-2)$ source cost $o(1)$.

Conditional stronger input. If the shifted-prime remainder hypothesis $R(\nu)$ holds for every fixed $\nu<1$—the relevant Elliott–Halberstam-type hypothesis—Bombieri's theorem gives

$$
\boxed{M_{k,X}=k+o_k(1)\qquad(k\ge2\text{ fixed}).}
\tag{8}
$$

This is not an unconditional consequence of Bombieri–Vinogradov. Ford explicitly distinguishes the best-distribution theorem from the available half-level bounds; Tao's exposition also records that even the complete conditional family leaves the prime contribution undetermined. 

ford126.web.illinois.edu+2

For any fixed coefficients $a_2,\ldots,a_K$, the unconditional estimates propagate to an error no better than

$$
3\sum_{k=2}^{K}|a_k|kc_k+o_K(1)
$$

around $\sum a_kk$. Under the stronger hypothesis this error becomes $o_K(1)$, but only with $K$ fixed. Neither theorem supplies a uniform remainder when $K=K(X)$ grows.

4. A direct test on the actual shifted-prime support

There is a second obstruction, beyond the formal parity comparison.

Rank-escape lemma. Using §308CO's uniform absolute envelope, for every fixed $K\ge2$ and $c>0$,

$$
\boxed{
\frac{L^2}{K_0X}
\sum_{\substack{X<P\le2X\\P\ {\rm prime}\\
m=P+2\ {\rm squarefree}\\2\le\omega(m)\le K}}
|Q_{1+c/H}(m)|\longrightarrow0.
}
\tag{9}
$$

Here is the argument. First, the classical two-linear-form upper sieve gives

$$
\#\{X<P\le2X:P\ {\rm prime},\
P+2\text{ squarefree},\ \omega(P+2)\le K\}
\ll_K \frac{XH^{K-1}}{L^2},
\tag{10}
$$

excluding the prime case.

For a squarefree $m$ with $r\le K$ factors, choose its largest prime $q$, so $m=aq$ and $q\gg X^{1/r}$. Uniformly in $a$, sieve the two forms $q$ and $aq-2$. Their singular correction is bounded by

$$
W(a)=\prod_{\ell\mid a,\ \ell>2}\frac{\ell-1}{\ell-2}.
$$

The sieve bound is $O_K(XW(a)/(aL^2))$. Summing over the possible products $a$ of $r-1$ distinct primes uses

$$
\sum_{\ell\le2X}\frac{W(\ell)}{\ell}
=\log\log X+O(1)
$$

and gives (10), including the exact shift two.

Now let $A_X^{(\le K)}(t)$ denote the normalized sum of the absolute §308CO Mellin integrands over these composite ranks. The integrand has absolute value at most one, so (10) implies, for every fixed $0<v<1$,

$$
\frac{A_X^{(\le K)}(L^v)}{L^v}
\ll_K \frac{H^{K-1}}{L^v}\longrightarrow0.
$$

Section 308CO supplies the uniform dominating bound $A_X(t)\ll t$ for $1\le t\le L$. In its Mellin formula, the regions $t<1$ and $t>L$ contribute $O_c(1/H)$. On writing $t=L^v$, dominated convergence gives (9). Repeated-base contributions are separately negligible by the square-factor estimate already required in §308CO.

Thus the fractional composite absolute mass $1-e^{-c}$ is carried by factor counts escaping every fixed rank. But $Q_k(m)=0$ identically whenever $\omega(m)>k$. This explains on the actual shifted-prime population why a fixed collection of integer-order moments misses the mass responsible for the fractional error.

This rank-escape conclusion uses no new distribution hypothesis beyond the standard upper sieve and the stated §308CO estimates. Its verification status inherits the internal, not externally certified, status of §308CO's uniform Mellin envelope.

5. Why the positive integer-moment hierarchy cannot repair the sign

An exact Poissonization makes the missing information visible, even if orders are allowed to grow.

For $m>1$, write

$$
x_p=\frac{\log p}{\log m},\qquad
b_m=1-\sum_{p\mid m}x_p\ge0.
$$

For integers $j\ge0$, $Q_j(m)$ is the probability that $j$ independent draws, selecting prime base $p$ with probability $x_p$ and a blank with probability $b_m$, have seen every distinct prime base.

Consequently,

$$
\boxed{
e^{-t}\sum_{j=0}^{\infty}\frac{t^j}{j!}Q_j(m)
=\prod_{p\mid m}(1-e^{-tx_p}).
}
\tag{11}
$$

But the signed Mellin integrand of §308CO is

$$
\boxed{
h_{t/\log m}(m)
=(-1)^{\omega(m)}e^{-tb_m}
\prod_{p\mid m}(1-e^{-tx_p}).
}
\tag{12}
$$

The integer-order hierarchy measures a positive coupon-completion probability. The fractional signed moment additionally requires the parity of the complete set of prime bases.

At the relevant scale $t=L^v$, $0<v<1$, the Poisson contribution of any fixed collection $j\le K$ is bounded, after normalizing and summing over the actual prime row, by

$$
O\!\left(L e^{-t}\sum_{j=0}^{K}\frac{t^j}{j!}\right)=o(1).
$$

The full positive Mellin envelope, by contrast, is asymptotic to $t$ in §308CO. Its mass therefore requires growing orders. The positive moving-integer-order result in §308CR is consistent with this, but its last-prime exponential law does not supply the factor-parity sign in (12).

There is also an elementary finite-moment test. Suppose, more strongly than the published results justify, that the unknown bounded density $b(v)$ were constrained by its first $m+1$ ordinary power moments. Set

$$
b_\pm(v)=\pm P_{m+1}(2v-1),
$$

where $P_j$ is the Legendre polynomial. Both satisfy $|b_\pm|\le1$ and have identical moments

$$
\int_0^1v^j b_\pm(v)\,dv=0\qquad(0\le j\le m).
$$

Their Laplace integrals nevertheless differ, because

$$
\int_0^1 e^{-cv}P_n(2v-1)\,dv
=\frac{(-1)^n c^n}{n!}
\int_0^1e^{-cv}v^n(1-v)^n\,dv\ne0.
\tag{13}
$$

For example, with $m=1,c=1$, the integral is $7-19/e\approx0.0102906$. These are admissible bounded signed densities, not proposed models of actual primes. They demonstrate why finitely many generic moment constraints cannot determine the needed Laplace sign.

Conclusion

The attempted strict lower bound did not survive. The strongest consequences are:

The exact polynomial identity (3) proves that every fixed integer-order leading moment, even under the full Elliott–Halberstam hypothesis, is compatible with a zero-prime parity comparison.

The rank-escape lemma (9) shows why those orders miss the dominant near-critical fractional absolute mass on the genuine shifted-prime support.

The Poisson identity (11)–(12) identifies the missing arithmetic information as complete factor parity, rather than the positive coupon-completion statistics.

In §308CO's normalization the remaining decisive inequality is still

$$
\boxed{\limsup_{X\to\infty}\bigl(I_X(c)-(1-e^{-c})\bigr)>0}
$$

for some fixed $c>0$, equivalently (by (1)) to a positive limsup of $\tau_X-2O_X(c)$.

A proved positive one-sided bound here would imply infinitely many ordinary twins. None of the available integer-order means establishes it. The next input would have to be a parity-sensitive estimate on the actual shifted-prime sequence, at the $X/\log^2X$ scale, not another leading integer-order generalized von Mangoldt asymptotic.


---

## A paired Jacobsthal lower sieve on the anchored interval — proof attempt and review

The target is one integer n in (z,z²−2] for which n and n+2 both have no prime factor at most z. This condition would give an ordinary twin pair. The researcher and independent reviewer derived a limitation of the transferred one-residue sieve tree: taking the original compact prime-path occupation theorem as input, its lower bound becomes arbitrarily negative relative to z²/log²z. This statement concerns that particular lower bound. The true survivor count remains unknown. The primary TeX contains the compact occupation statement in `prime-paths.tex` and the fixed terminal window in `stops.tex`. [Original preprint sources](https://github.com/openai/math/tree/main/preprints/A-quadratic-bound-for-Jacobsthals-function-September-25-2026/build/sections).

### Setup and composite cleanup

[Source chat](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e-twin-prime-conjecture-research/c/6b05e29c-2148-83ee-b4c5-1176ac022aef)



1. The target and the relevant Jacobsthal mechanism

Your anchored criterion is exact. Put

$I_z=\{n\in\mathbb Z:z<n\le z^2-2\},\qquad
P(z)=\prod_{p\le z}p.$

If $n\in I_z$ and $\gcd(n(n+2),P(z))=1$, then both $n$ and $n+2$ are prime. A composite integer at most $z^2$ necessarily has a prime factor at most $z$.

Consequently, it suffices to establish a survivor in $I_z$ for arbitrarily large $z$. There is no need to prove a uniform two-residue Jacobsthal theorem.

I recovered the relevant portions of the September 25 manuscript through a TeX rendering of the original paper, including its decreasing-prime tree, positive reference margin, and aligned stopping argument. The original GitHub and raw-file endpoints failed to load directly.

The ordinary theorem is actually stronger than a quadratic bound:

$h(k)\ll\frac{k^2}{(\log\log(3k))^2}.$

Its Theorem 1.2 and Proposition 6.3 obtain positivity from a delicate correction at the critical parameter of the one-dimensional sieve. The other crucial step is the averaged arithmetic estimate at an aligned stopping node, Lemma 10.3 and Proposition 10.5. 

Plectis Atlas+1

I tested these two mechanisms separately. The result is mixed: the arithmetic switching argument has a useful paired extension on certain nodes, but the original positive reference calculation does not transfer.

2. Reconstructing the decreasing-prime tree for the linked pair

Write

$L=\log z,\qquad H=|I_z|,\qquad
w=\frac{L}{(\log L)^2},\qquad
B=\frac{L}{\log w}.$

Define the one- and two-residue local products

$V_1(t)=\prod_{p\le t}(1-1/p),$

$V_2(t)=\frac12\prod_{2<p\le t}(1-2/p).$

In particular, $V_2(t)\asymp(\log t)^{-2}$.

In the original proof, each decreasing tuple of primes specifies one progression. Its product is $d$, its reference progression length is $J_d=Y/d$, and the reference count is $J_dV_1(w)$.

The paired version has to retain an additional label at every selected odd prime:

$\epsilon_p\in\{0,2\},
\qquad n\equiv-\epsilon_p\pmod p.$

For a tuple and its labels, let

$d_0=\prod_{\epsilon_p=0}p,\qquad
d_2=\prod_{\epsilon_p=2}p.$

These products are coprime. Their simultaneous hit conditions are

$d_0\mid n,\qquad d_2\mid n+2.$

They specify one progression modulo $d=d_0d_2$.

Let $N_\nu$ count its members in $I_z$ that avoid both forbidden classes at every prime at most $w$. Let $S_\nu(b)$ additionally impose avoidance at the available primes above $w$, up to the cutoff $b$.

Partitioning deleted integers by their first bad available prime gives the exact identity

$\boxed{
S_\nu(b)=N_\nu-
\sum_{p\ {\rm available}}
\left(S_{\nu+(p,0)}+S_{\nu+(p,2)}\right).
}
\tag{1}$

The two terms for a given odd prime are disjoint. The source's alternating lower-tree construction therefore remains valid after adding these labels, with the same admission rule.

The obstruction appears in its reference evaluation.

The correct reference count per labelled node is

$\mu_\nu=\frac HdV_2(w).$

If admission depends only on the prime sizes, the two labels give identical reference subtrees. Thus the paired reference recursions are

$P_e^{(2)}(r,b)=
1-\sum_p\frac2pP_o^{(2)}(r-x_p,x_p),$

$P_o^{(2)}(r,b)=
1-\sum_{\substack{p\\
r-x_p\ge\max(2x_p,x_p+2)}}
\frac2pP_e^{(2)}(r-x_p,x_p),
\tag{2}$

where $x_p=\log p/\log w$.

Compare this with equation (3.5) of the manuscript, which has $1/p$ in both recursions. This change cannot be removed by exploiting the translation relation between the forbidden classes. It comes from two genuinely disjoint hit branches.

The alternating-tree inequality transfers. Its positive-reference theorem has to be proved again for (2).

3. The specific reference term that breaks the original proof

The ordinary proof uses the classical linear-sieve functions $f,F$. Its continuous reference benchmark at an even node is proportional to

$\frac{f(r/b)}b.$

The differential identity underlying its reference calculation, including equation (6.3) of the manuscript, is

$\frac{d}{db}\left(\frac{f(r/b)}b\right)
=-\frac{F(r/b-1)}{b^2}.$

This matches the ordinary tree's transition measure $dx/x$. 

Plectis Atlas

For the paired tree, the remaining local product instead has size $b^{-2}$, and the transition measure is $2\,dx/x$.

Test the direct replacement

$G(r,b)=b^{-2}f(r/b).$

Writing $s=r/b$, differentiation gives

$\frac{\partial G}{\partial b}
=-\frac{f(s)+F(s-1)}{b^3}.$

But the paired recursion requires the derivative

$-\frac{2F(s-1)}{b^3}.$

The resulting defect is exactly

$\boxed{
\mathcal D(r,b)=
\frac{F(s-1)-f(s)}{b^3}.
}
\tag{3}$

This is not a small quadrature error.

On the full anchored interval,

$r=2B+O(1).$

For $0.9B\le b\le B$, we have $2\le s\le2.23$ for sufficiently large $z$. On this range,

$f(s)=\frac{2e^\gamma}{s}\log(s-1),
\qquad
F(s-1)=\frac{2e^\gamma}{s-1}.$

Their difference is bounded below by a positive absolute constant. Therefore

$\int_{0.9B}^{B}\mathcal D(r,b)\,db
\gg B^{-2}.$

In physical counting units, this costs

$\boxed{
HV_2(w)B^{-2}
\asymp\frac{z^2}{(\log z)^2}.
}
\tag{4}$

That is the entire expected twin-prime scale.

In contrast, the directly transplanted benchmark $B^{-2}f(r/B)$ is only $O(B^{-3})$, since $r/B=2+O(B^{-1})$.

Thus the original reference differential calculation fails at a scale larger than its transplanted root benchmark.

This does not prove that a redesigned two-dimensional reference tree must have negative value. It establishes that the source's Proposition 6.3 cannot be reused without a substantially different evaluation.

An actual arithmetic check of the mixed branches

The doubled transition weight also corresponds to genuine arithmetic mass, not merely a formal defect.

Take primes in two disjoint ranges

$z^{0.60}<p\le z^{0.65},
\qquad
z^{0.25}<q\le z^{0.30}.$

Both selections satisfy the source's two-step admission test on the anchored interval.

Consider the mixed labelled nodes

$p\mid n,\quad q\mid n+2,$

and the opposite orientation. Impose the complete paired avoidance condition at primes at most $w$.

For each orientation, the CRT count is

$\frac{H}{pq}V_2(w)+O(P(w)).$

Since $P(w)=z^{o(1)}$, the total error over these prime pairs is negligible. Summing the two orientations gives

$\begin{aligned}
&(2+o(1))HV_2(w)
\log\frac{0.65}{0.60}
\log\frac{0.30}{0.25}.
\end{aligned}
\tag{5}$

These are actual mixed-endpoint divisor incidences.

Their size is

$\asymp\frac{H}{(\log w)^2},$

larger than the twin-prime scale by a factor of order $B^2$.

They enter the second-level tree with positive signs; the first-level deletions enter with negative signs. They must participate in the full signed calculation. I am not treating (5) as a negative remainder or claiming that it cannot cancel elsewhere.

What it rules out is removing mixed-label branches as a negligible consequence of the translation relation.

4. Rerunning the source's arithmetic switching inequality

There is a more promising outcome for the other half of the proof.

The original Lemma 10.3 fixes a product $q'$ and averages over a large varying prime $p$. The alignment to a common rational allows the source to write the progression as

$Dn-A=pq'm.$

It then uses a prime factor of the short variable $m$, and sieves the varying prime $p$.

The original averaged lower coefficient is $0.39$, exceeding the reference-subtree allowance $0.33$; after accounting for the nonaligning primes, the proof retains $0.34>0.33$. 

Plectis Atlas+1

For the anchored linked pair, an important simplification occurs when all selected primes divide the same endpoint.

Proposition: a paired monochromatic switching estimate

Let $P$ be the smallest selected prime, with $P\to\infty$. Let $q'$ be a squarefree product of primes at least $P$, and let

$\mathcal P=\{p\text{ prime}:R<p\le(1+\xi)R\}$

be a disjoint varying-prime bin, where $\xi>0$ is fixed and small.

Suppose

$J=\frac{H}{Rq'},\qquad
2.03\le\frac{\log J}{\log P}\le2.19,$

$J=z^{o(1)},\qquad
\frac{\log R}{\log P}\longrightarrow\infty.$

Let $T_p^{(2)}$ count the members $n\in I_z$ satisfying

$pq'\mid n,
\qquad
\gcd(n(n+2),P(P^-))=1,$

where $P(P^-)$ denotes the product of primes strictly below $P$.

Then, writing $s=\log J/\log P$,

$\boxed{
\sum_{p\in\mathcal P}T_p^{(2)}
\ge
\left(\frac{e^\gamma}{s(1+\xi)}+o(1)\right)
V_2^{<}(P)\sum_{p\in\mathcal P}\frac{H}{pq'}.
}
\tag{6}$

Here $V_2^{<}$ uses the strict cutoff below $P$.

Proof. Restrict to

$n=pq'm,\qquad
P<m\le J/(1+\xi),$

with $m$ prime.

The first endpoint automatically avoids every prime below $P$. The anchored lower bound causes no difficulty: $pq'\gg H/J=z^{2-o(1)}$, so these integers exceed $z$.

For each fixed $m$, the second condition excludes one reduced residue class for $p$ modulo each odd prime $t<P$:

$p\not\equiv-2\overline{q'm}\pmod t.$

The corresponding sieve product on the prime variable is

$W(P)=\prod_{2<t<P}\left(1-\frac1{t-1}\right)
=\frac{V_2^{<}(P)}{V_1^{<}(P)}.$

Apply the fundamental lemma and Bombieri–Vinogradov to the prime bin, at level $R^{1/3}$. The condition $\log R/\log P\to\infty$ makes the relative sieve error tend to zero. The progression error is uniform in the coefficient $q'm$, because the residue classes are reduced and the maximal distribution bound applies.

For every eligible $m$, the number of surviving tag primes is therefore

$(1+o(1))|\mathcal P|W(P).$

By the prime number theorem, the number of eligible $m$ is

$(1+o(1))\frac{J}{(1+\xi)\log J}.$

Finally,

$V_1^{<}(P)\sim\frac{e^{-\gamma}}{\log P},
\qquad
\sum_{p\in\mathcal P}\frac{H}{pq'}\le J|\mathcal P|.$

Combining these estimates proves (6). The other monochromatic orientation, in which $pq'\mid n+2$, is identical with the shift reversed.

The coefficient $e^\gamma/(2.19(1+\xi))$ exceeds $0.75$ for sufficiently small fixed $\xi$.

This is a successful transfer of the arithmetic mechanism on monochromatic nodes. It does not require two simultaneous primality conditions: $m$ is prime, and the other endpoint is only sieved below $P$.

However, the new paired reference subtree has not been proved to satisfy the original $0.33$ allowance. Nor have all nodes been reduced to this monochromatic situation.

5. Repairing some mixed nodes by asymmetric switching

The linked classes permit a further extension.

Suppose the selected primes other than the varying prime have been divided between the two endpoints:

$q'=AC,
\qquad
pA\mid n,\qquad C\mid n+2,$

with $A,C,p$ pairwise coprime.

The exact switched equation becomes

$n=pAu,\qquad
pAu\equiv-2\pmod C.
\tag{7}$

The cofactor $u$ now has upper scale $CJ$, not $J$.

This difference is crucial, but we can handle it when the opposite-colour product $C$ is sufficiently short.

Assume, in addition to the preceding tag-bin hypotheses, that

$C\le P^a,\qquad C\le(\log R)^M,$

for fixed constants $a,M$. Restrict $u$ to primes in

$P<u\le CJ/(1+\xi),\qquad (u,C)=1.$

For every such $u$, equation (7) prescribes one reduced residue class for $p$ modulo $C$.

Because every prime factor of $C$ is at least $P$, this progression condition is coprime to the small sieve primes. The sieve on $p$ again has product $W(P)$.

The additional modulus $C$ costs at most a fixed power of $\log R$, so it is absorbed by requesting sufficiently strong logarithmic precision from Bombieri–Vinogradov.

The count of eligible tag primes per $u$ is consequently

$(1+o(1))
\frac{|\mathcal P|}{\varphi(C)}W(P).$

The prime number theorem for $u$ supplies

$(1+o(1))
\frac{CJ}{(1+\xi)\log(CJ)}$

choices. Setting $a_C=\log C/\log P$, we obtain the lower coefficient

$\boxed{
\frac{e^\gamma}{(s+a_C)(1+\xi)}
\frac{C}{\varphi(C)}.
}
\tag{8}$

This is in the same normalization as (6).

For example, when $C\le P^2$, the coefficient exceeds $0.39$ for sufficiently small $\xi$.

Thus the switching operation extends even to some mixed nodes. In particular, the requirement that every selected prime align to exactly the same endpoint can be relaxed when the complete opposite-colour product is short.

Where this repair stops

If $C$ grows polynomially in $z$ while $P$ is a fixed power of $w$, then

$a_C=\frac{\log C}{\log P}\longrightarrow\infty.$

Even if one granted ideal prime distribution in the required progressions, the coefficient furnished by the prime-$u$ subfamily in (8) would tend to zero.

There is also an actual distribution obstruction: the residue modulus $C$ may be comparable to, or larger than, the whole varying-prime bin.

Alternatively, solve the congruence (7) for $u$:

$u=u_0+Cj.$

The other endpoint then has the form

$n+2=C(v_0+pAj).$

The variable $j$ has length approximately $J$. At every odd prime below $P$, the conditions that both affine cofactors avoid divisibility exclude two distinct residue classes.

This puts us back into a paired sieve in an interval of length

$J\asymp P^{2.1}.$

It is exactly the local two-residue problem that the switching operation was supposed to resolve.

Consequently, the successful estimates (6) and (8) do not establish the full stopped-subtree comparison. A new treatment of genuinely mixed nodes with a large opposite-colour product is required.

6. Testing an asymmetric cover of the entire anchored interval

There is a natural way to exploit the anchoring more aggressively: finish the first sieve completely, so that every remaining $n$ is already prime, and then sieve $n+2$.

I tested the actual size of the second-stage deletion rather than estimating it by independent probabilities.

Define

$A(w)=
\#\{n\in I_z:n\text{ prime},\ P^-(n+2)>w\}.$

The prime number theorem, fundamental lemma and Bombieri–Vinogradov give

$A(w)\sim
2C_2e^{-\gamma}
\frac{H}{2L\log w}.
\tag{9}$

Here the local prime-sequence divisor density is $1/(p-1)$ at odd primes. The subpower cutoff $w$ leaves ample distribution-level margin.

Let $T(z)$ be the actual number of twin-prime survivors in $I_z$. The classical upper-bound sieve gives

$T(z)\ll H/L^2.$

Now assign every deleted member of $A(w)$ to the least prime factor of $n+2$ in $(w,z]$. The exact total deletion is

$\begin{aligned}
\mathcal C(w,z)
={}&
\sum_{w<q\le z}
\#\{n\in I_z:n\text{ prime},\\
&\hspace{37mm}P^-(n+2)=q\}\\
={}&A(w)-T(z),
\end{aligned}$

where the outer sum is over primes.

It follows unconditionally that

$\boxed{
\mathcal C(w,z)
\sim
2C_2e^{-\gamma}
\frac{H}{2L\log w}.
}
\tag{10}$

This is a genuine size estimate for the actual second-stage cover.

It is larger than the desired twin-prime scale by a factor of order $L/\log w$. A relative estimate $1+o(1)$ for that cover therefore cannot force a survivor.

The anchored interval removes arbitrary progression positions from the first sieve, but it does not remove the critical subtraction in the second. The ordinary Jacobsthal theorem says nothing about the placement of its surviving primes relative to the shifted composite set.

In particular, simply repeating the ordinary result on the translate does not establish a common survivor.

7. A more useful two-stage construction: shrink the final cutoff

I did obtain an unconditional reduction that makes the final composite cleanup substantially cheaper.

Fix $A_0>0$ and put

$z_0=\frac{z}{(\log z)^{A_0}}.$

Let

$S_2(z_0)=
\#\{n\in I_z:P^-(n(n+2))>z_0\}.$

Since $z_0^3>z^2$ eventually, every composite endpoint counted by $S_2(z_0)$ is necessarily a product of two primes.

Moreover, its smaller prime factor $r$ belongs to the narrow range

$z_0<r\le z.$

For fixed such $r$, write the composite endpoint as $rs$. The remaining conditions imply

$s\text{ prime},\qquad
P^-(rs\pm2)>z_0.$

Apply the ordinary two-form upper-bound sieve to $s$ and $rs\pm2$, at a fixed small polynomial cutoff below $z_0$.

The two forms have distinct roots at every odd sieving prime: all those primes are smaller than $r$. Their local factors are therefore uniform in $r$. Since the variable $s$ has available length at most $z^2/r$, with polynomial scale in $z$, the resulting bound is

$\ll\frac{z^2}{rL^2}.$

Sum over the smaller factor. The prime number theorem gives

$\sum_{z_0<r\le z}\frac1r
\ll_{A_0}\frac{\log L}{L}.$

Accounting for a composite at either endpoint yields

$\boxed{
0\le S_2(z_0)-T(z)
\ll_{A_0}
\frac{z^2\log\log z}{(\log z)^3}.
}
\tag{11}$

Prime squares are included in the upper bound, or can be charged separately at cost $O(z)$.

Thus a positive main-scale lower bound for the paired survivors at the slightly smaller cutoff $z_0$ would suffice. The final cleanup would be negligible.

There is a fixed-power version as well. With $z_0=z^{1-\delta}$, for sufficiently small fixed $\delta>0$, the identical argument gives

$S_2(z^{1-\delta})-T(z)
\ll(\delta+o(1))\frac{z^2}{L^2},
\tag{12}$

with a uniform implied constant for small $\delta$.

This provides a potentially useful target for a redesigned two-stage covering theorem. It is weaker than demanding that the full paired sieve work exactly at the square-root cutoff.

But neither the original reference-tree theorem nor the partial switching extensions above produce the necessary lower bound for $S_2(z_0)$. Reducing the cutoff logarithmically does not change the main-order defect in (3).

8. Verdict and the remaining mathematical requirement

Component tested

Result

Anchored survivor criterion

Exact

Alternating-tree lower inequality

Transfers with two labels per prime

Original positive reference margin

Does not transfer; main-order defect (3)

Aligned arithmetic switching

Transfers on monochromatic nodes

Asymmetric mixed-node switching

Transfers when the opposite-colour product is sufficiently short

General mixed-node stopping argument

Unproved

Final cleanup after a logarithmically smaller cutoff

Unconditionally negligible by (11)

The two genuinely useful results from this investigation are the local switching estimates (6)–(8) and the near-square cleanup estimate (11).

They suggest a more focused sufficient target:

$\boxed{
S_2\left(\frac{z}{(\log z)^{A_0}}\right)
\gg\frac{z^2}{(\log z)^2}
}$

along an unbounded sequence of $z$, with fixed $A_0>0$.

The paired reference tree must supply a positive reserve, and its stopping argument must pay the genuinely mixed endpoint configurations without losing that reserve.

A sparse sequence does not repair the demonstrated main-order reference defect or the actual deletion estimate (10); those calculations hold asymptotically throughout the anchored range.

I have not obtained a proof of a survivor for arbitrarily large $z$. The original Jacobsthal breakthrough supplies a valuable switching mechanism, but its one-dimensional reference positivity is precisely the part that cannot be imported into the twin-prime system.

The source-access limitation is that I inspected the relevant original-text rendering rather than the GitHub PDF itself, and did not independently replay its Lean formalization. The paired recursions, differential-defect calculation, restricted switching estimates and two-stage cleanup are my own derivations, not claims made by the original manuscript. No paper or files have been created.



### Full lower tree and omitted positive children



1. The complete monochromatic correction can be reduced to an exact one-endpoint tree count

There is a useful simplification here, but it requires distinguishing the ordinary tree's lower-bound polynomial from the actual number of survivors of that ordinary sieve.

Keep the notation from (12). Put

$H=z^2-z+O(1),\qquad
L=\log z,\qquad
w=\frac{L}{(\log L)^2},\qquad
z_0=\frac{z}{L^{A_0}},
\qquad B=\frac{\log z_0}{\log w}.$

Let $\mathcal T$ be the original unstopped admitted family of unlabelled decreasing-prime paths, including the empty path. Thus $d\in\mathcal T$ is squarefree, with prime factors in $(w,z_0]$. Write

$\lambda_d=\mu(d)\mathbf1_{d\in\mathcal T}.$

I retain the original admission rule: an even child with last exponent $x=\log p/\log w$ is admitted only when its remaining gap is at least $\max(2x,x+2)$. This is the rule in Section 3 of the Jacobsthal manuscript. Its equation (3.7) separately accounts for any subsequent lower-node stops. 

Plectis Atlas

For the present calculation, define

$R(N)=\mathbf1_{(N,P(w))=1},
\qquad
U(N)=\sum_{d\mid N}\lambda_d.$

Define the two exact one-endpoint tree counts, with the identical coefficients $\lambda_d$, by

$J_0=\sum_{n\in I_z}R(n)U(n),
\qquad
J_2=\sum_{n\in I_z}R(n+2)U(n+2).$

Also write

$P_1=\sum_d\frac{\lambda_d}{d},
\qquad
P_2=\sum_d\frac{2^{\omega(d)}\lambda_d}{d}.$

Here the empty product contributes one to each reference polynomial.

The complete paired lower-tree value is

$\mathcal L_2=
\sum_{n\in I_z}R(n)R(n+2)
\sum_{d\mid n(n+2)}\lambda_d.$

For a nonempty outer modulus $d$, its two monochromatic labelings give

$\mathbf1_{d\mid n}+\mathbf1_{d\mid n+2}.$

Counting the empty path just once, the entire monochromatic part is therefore

$\boxed{
\mathcal L_{\rm mono}
=
\sum_{n\in I_z}R(n)R(n+2)
[U(n)+U(n+2)-1].
}
\tag{13}$

Its reference value is exactly

$HV_2(w)(2P_1-1).
\tag{14}$

The mixed-root reference is the complementary quantity

$HV_2(w)(P_2-2P_1+1).$

No monochromatic root, mixed root or empty path has been omitted or counted twice.

A paired comparison with the exact ordinary tree

Put

$W(w)=\frac{V_2(w)}{V_1(w)}
=\prod_{2<p\le w}\left(1-\frac1{p-1}\right).$

For the original unstopped, size-admitted family, I obtain

$\boxed{
\mathcal L_{\rm mono}
=
W(w)(J_0+J_2)-HV_2(w)+o(H/L^2).
}
\tag{15}$

In particular, the complete monochromatic arithmetic correction is

$\boxed{
\mathcal E_{\rm mono}
=
W(w)\left[J_0+J_2-2HV_1(w)P_1\right]
+o(H/L^2).
}
\tag{16}$

This is a comparison of actual counts with identical admission weights, rather than a multiplication of conjectural probabilities.

2. Proof of the comparison at twin-prime precision

It suffices to prove

$\begin{aligned}
&\sum_{n\in I_z}R(n)R(n+2)U(n)\\
&\qquad=W(w)\sum_{n\in I_z}R(n)U(n)+o(H/L^2),
\end{aligned}
\tag{17}$

with the reverse shift handled identically.

In fact, the argument below gives error $O_A(HL^{-A})$ for every fixed $A$, for this comparison.

Small outer moduli

For $d\le z$, the one-endpoint and paired presieve counts are respectively

$\frac Hd V_1(w)+O(P(w)),
\qquad
\frac Hd V_2(w)+O(P(w)).$

These are exact-period counting estimates: $(d,P(w))=1$, and the second presieve has two distinct forbidden classes at every odd small prime.

Since $P(w)=z^{o(1)}$, the total error over these moduli is $z^{1+o(1)}$.

Large outer moduli having only subpower prime factors

Take $R_*=\exp(L^{1/3})$. For the moduli $d>z$ with $P^+(d)\le R_*$, Rankin's inequality gives

$\begin{aligned}
\sum_{\substack{d>z,\ \mu^2(d)=1\\P^+(d)\le R_*}}\frac1d
&\le
e^{-L^{2/3}}
\prod_{p\le R_*}(1+p^{-1+L^{-1/3}})\\
&\ll e^{-L^{2/3}}L^{O(1)}.
\end{aligned}$

Every actual multiple count here is $O(H/d)$: the admitted moduli are smaller than $H$. Thus this range is negligible even before signed cancellation.

The remaining large moduli

Write the outer modulus as $d=pa$, where $p=P^+(d)>R_*$, and write $n=pak$.

Fix $a,k$. The one-endpoint presieve requires $R(k)=1$, since every prime of $d$ exceeds $w$.

The conditions on $p$ are then:

$p$ is prime and larger than every prime factor of $a$;

the endpoint condition places $p$ in an interval;

every original admission inequality imposes an upper bound on $\log p$.

The last assertion follows because $p$ is the first prime of the path; all later exponents are fixed. The admissible values of $p$, in any fixed dyadic bin $p\asymp R_1$, therefore form an interval.

For each odd prime $\ell\le w$, the extra condition $R(pak+2)=1$ excludes precisely one reduced residue class of $p\bmod\ell$:

$p\not\equiv-2\overline{ak}\pmod\ell.$

Apply the fundamental lemma and Bombieri–Vinogradov to this prime interval, with sieve level $R_1^{1/3}$. Its sieve ratio tends to infinity uniformly because

$\frac{\log R_1}{\log w}\ge
\frac{L^{1/3}}{\log w}.$

The resulting count is $W(w)$ times the actual unweighted prime count in the same admitted interval, with error

$O_A(R_1L^{-A})$

for arbitrary fixed $A$. The maximal progression form handles the moving endpoints of that interval.

Finally, sum over $a,k$. Their product is $O(H/R_1)$, so the elementary divisor estimate

$\sum_{ak\le Y}1\ll Y\log(2Y)$

absorbs the number of rows, and the $O(L)$ possible dyadic bins are paid by increasing the requested logarithmic precision. The coefficient is $\mu(pa)=-\mu(a)$ throughout each row.

This proves (17).

The root presieve count is $HV_2(w)+O(P(w))$, giving (15) and (16).

Scope: the comparison applies to the entire size-admitted unstopped family. Arbitrary label-dependent arithmetic stops cannot be inserted into its prime intervals without checking their extra conditions. I handle stops separately below.

3. Evaluating the entire monochromatic correction, not just its favorable subfamily

The comparison (16) makes it possible to go further. Because this is the anchored interval, the one-endpoint counts can be evaluated in the progression coordinate by Buchstab's function.

Let $a_\star=1/100$ be the original admission constant. At an included node put

$r_d=\log_w(H/d)+2-a_\star.$

Let $\omega_B(v)$ denote Buchstab's function, extended by zero for $0<v<1$. Define

$\delta(v)=e^\gamma\omega_B(v)-1.$

On compact gap ranges, the ordinary one-endpoint count $N_d^{(1)}$ satisfies

$\frac{N_d^{(1)}}{(H/d)V_1(w)}-1
=
\delta(r_d-2+a_\star)+o(1),
\tag{18}$

uniformly away from the jump at $r_d-2+a_\star=1$.

Indeed, the progression is simply $n=dk$, with $k$ free of prime factors at most $w$. Its upper length is $(1+o(1))H/d$, and its lower endpoint is below one in the compact-gap region. The usual Buchstab asymptotic applies for $v>1$; for $v<1$, only the unit $k=1$ can survive.

For large gaps, the fundamental lemma gives an exponentially decreasing relative-error bound. Thus the compact occupation and weighted-tail estimates in the ordinary manuscript's Proposition 5.5 justify integration over the entire unlabelled admitted tree. I recovered the relevant occupation formulas and invariant densities in this turn. 

Plectis Atlas

Summing all boundary descendants

The source's occupation law for paths whose exponents exceed two has, after integration over the terminal cutoff, the following densities in the gap variable $r$:

$E_0(r)=\frac{r(r-4)}2\mathbf1_{r\ge4},
\qquad
O_0(r)=\frac{(r-2)^2}2\mathbf1_{r\ge2}.$

The common normalization is $e^\gamma/M_g$, where $M_g>0$ is the manuscript's renewal constant and $M_g\le4e^\gamma$.

These are the densities in units of $B^{-2}$.

Every remaining path is obtained by appending a decreasing tuple of exponents in $(1,2]$ to one of these parent paths. At these exponents, the original even-child admission condition is exactly

$r_{\rm child}\ge x+2.$

I summed all such descendants, retaining their parity and this stronger admission condition.

The resulting signed occupation density, before multiplication by the common normalization, is $-h(r)$, where

$\boxed{
h(r)=
\begin{cases}
b^2+b+2+b\log(2-b)
-\dfrac4b\log\!\left(\dfrac{(2-b)(1+b)}2\right),
 &r=2+b,\ 0<b<1,\\[2mm]
1+\dfrac4{r-2}-(r-2),
 &3\le r<4,\\[2mm]
1,&r\ge4.
\end{cases}}
\tag{19}$

The continuous value at $r=2$ is zero.

Here is the counting calculation underlying this expression.

For $r\ge4$, every appended boundary tuple is admissible. The parent signed density is

$E_0(r)-O_0(r)=-2.$

Summing all descendant lengths gives

$-2\sum_{j\ge0}\frac{(-\log2)^j}{j!}=-1.$

For $3\le r<4$, odd-ending paths are unrestricted, but even-ending paths require their smallest appended exponent to be at most $r-2$. Summing the excluded even-ending paths gives $4/(r-2)-(r-2)$, yielding the middle expression in (19).

For $2<r<3$, there are no even-ending paths. Put $b=r-2$. The complete odd-ending density is

$\begin{aligned}
h(r)={}&\frac{b^2}{2}
+\int_{4-r}^{2}\frac{E_0(r+x)}x\,dx\\
&+\int_1^2\frac{(r+t)^2}{t}
\left(
\frac1t-\frac1{\min(2,t+b)}
\right)dt.
\end{aligned}$

The last integral sums all paths with at least two appended primes. Their last two exponents $s>t$ must satisfy $s-t\le b$; that is precisely the last even-child admission condition. Earlier even-child conditions then hold automatically. Elementary integration gives the first expression in (19).

This calculation includes every admissible boundary descendant, including those producing corrections of the unfavorable sign.

The combined constant

Combining (16), (18) and (19) gives

$\boxed{
\frac{\mathcal E_{\rm mono}}{HV_2(w)/B^2}
\longrightarrow
\frac{2e^\gamma}{M_g}\,\mathfrak C,
}
\tag{20}$

where

$\mathfrak C
=
\int_2^\infty h(r)
\left[1-e^\gamma\omega_B(r-2+a_\star)\right]\,dr.$

This integral is convergent. Its infinite tail can be evaluated without numerically following Buchstab's delay equation to infinity.

Indeed, the Laplace transform of $\omega_B$ satisfies

$1+\int_1^\infty e^{-sv}\omega_B(v)\,dv
=
\exp\left(\int_s^\infty\frac{e^{-t}}t\,dt\right).$

Expanding at zero gives

$\int_0^\infty[1-e^\gamma\omega_B(v)]\,dv
=e^\gamma-1.$

Since $h(r)=1$ for $r\ge4$, this reduces the tail of $\mathfrak C$ to elementary integrals through $v=2.01$. On the relevant finite range,

$\omega_B(v)=
\begin{cases}
0,&v<1,\\
1/v,&1\le v\le2,\\
(1+\log(v-1))/v,&2\le v\le2.01.
\end{cases}$

I obtained the numerical value

$\mathfrak C=1.232751234\ldots.$

I also checked a conservative enclosure by rational Riemann bounds, splitting at the discontinuity and formula changes, using the monotonicity of $h$ on its separate pieces and the convergent logarithm series. With mesh $1/1000$ on the compact gap integrals and $1.781<e^\gamma<1.782$, the enclosure is

$1.2229<\mathfrak C<1.2426.$

Consequently,

$\boxed{
\liminf_{z\to\infty}
\frac{\mathcal E_{\rm mono}}{HV_2(w)/B^2}>0.61.
}
\tag{21}$

This uses $M_g\le4e^\gamma$.

This is the full monochromatic result. The previously priced positive subfamily is included in this constant and must not be added again.

The asymptotic (20) depends on the ordinary manuscript's stated occupation theorem, whose underlying proof I have not independently certified. The paired comparison (15) itself is unconditional and does not use that occupation theorem.

It is now appropriate to turn to the complete mixed-root correction.

4. A decisive obstruction to the full lower-tree bound

While tracing the omitted terms, I found a stronger obstruction than an unestimated mixed-root discrepancy.

Using the original manuscript's occupation theorem, the complete unstopped paired lower-tree value can be shown to become negative by an arbitrarily large multiple of the twin-prime scale.

The obstruction comes from the exact even children rejected by the admission rule. It also survives the ordinary manuscript's stopping rule with fixed terminal-exponent bounds.

This rules out positivity of the particular expression in (12), rather than merely failing to prove its positivity.

Exact omission identity

Let $\mathcal O$ consist of first omitted labelled even children: their parents belong to the admitted tree, but the children fail its admission test.

For $\nu\in\mathcal O$, let $S_\nu$ be the exact count in its progression that avoids both forbidden classes at every prime strictly below its last prime.

Then the least-bad-prime decomposition, iterated throughout the admitted tree, gives

$\boxed{
S_2(z_0)=\mathcal L_2+\Delta_2,
\qquad
\Delta_2=\sum_{\nu\in\mathcal O}S_\nu\ge0.
}
\tag{22}$

The multiplicities here are those of the exact tree expansion. If an integer belongs to several omitted leaves, each occurrence genuinely contributes to the deficit.

This identity follows because every first omitted child has even depth and would enter the full expansion with a positive sign.

The point is now to estimate $\Delta_2$ on the actual arithmetic population, not merely on the independent-residue reference.

A sequence of disjoint omission bands

Fix any constant $b\ge20$, independently of $z$. Take included odd parent paths with gap $r$ and terminal ratio $s$ satisfying

$\frac52b<r<\frac{14}{5}b,
\qquad
\frac{41}{20}<s<\frac{11}{5}.$

Their last prime exponent $r/s$ exceeds $1.1b$.

Append a prime $p=w^x$ with

$b<x<1.1b.$

The child is even and its remaining gap satisfies

$1.4b<r-x<1.8b<2x.$

It therefore fails the original admission rule. Every such child is a first omitted leaf.

For its product $d$, write

$v=\log_w(H/d)=r-x-2+a_\star.$

The chosen margins give

$x<v<2x,
\qquad
xv<1.98b^2.
\tag{23}$

In particular, the progression has room for a genuinely prime cofactor $k>p$.

Use just the monochromatic orientation in which all factors of $d$ divide $n$. The actual integers

$n=dk,\qquad p<k\le(1+o(1))H/d,\qquad k\text{ prime}$

automatically avoid every prime below $p$ on the first endpoint.

We still have to require that $n+2$ avoid every prime below $p$. This additional condition can be counted.

Paying the second endpoint arithmetically

Write $d=Pa$, where $P=P^+(d)$. Restrict first to $P>\exp(L^{1/3})$.

Fix $a,k$. The parent occupation window, original admission constraints, appended-prime range, and anchored endpoint restriction impose interval conditions on $P$. The last prime $p$ is fixed in this row.

For each odd prime $\ell<p$, the second endpoint forbids precisely one reduced residue class for $P$:

$P\not\equiv-2\overline{ak}\pmod\ell.$

All factors of $ak$ exceed or equal $p$, so the inverse is legitimate.

The same maximal Bombieri–Vinogradov and fundamental-lemma argument used in Section 2 applies. Here the sieve limit is at most $w^{1.1b}$, with $b$ fixed, whereas the varying prime has logarithm at least $L^{1/3}$.

The summed error is $o(H/L^2)$ for each fixed $b$. The discarded moduli with no prime factor exceeding $\exp(L^{1/3})$ have negligible harmonic mass by Rankin's argument, since all these omitted products have size $H/w^{O(b)}$.

Thus the second-endpoint sieve multiplies the actual one-endpoint prime-cofactor count by

$W^{<}(p)
=\prod_{2<\ell<p}
\left(1-\frac1{\ell-1}\right)
\sim\frac{2C_2e^{-\gamma}}{x\log w},$

with the claimed aggregate error. This is an application of prime distribution to actual rows, not an independence assumption.

The prime number theorem for $k$, uniformly within the fixed gap margins (23), gives the following contribution to the omission deficit from this band:

$\Delta_{2,b}
=
(1+o(1))
\frac{2C_2e^{-\gamma}H}{(\log w)^2}
\sum_{\text{selected children }d}
\frac1{d\,xv}
+o(H/L^2).
\tag{24}$

The occupation mass pays a uniform positive amount per band

All exponents of the parent paths exceed two. Hence the original and standard admission rules agree on them.

The ordinary compact occupation theorem gives

$\begin{aligned}
&B^2\sum_{\text{selected parents }d'}\frac1{d'}\\
&\quad\longrightarrow
\frac{e^\gamma}{M_g}
\int_{5b/2}^{14b/5}r\,dr
\int_{41/20}^{11/5}(1-s^{-2})\,ds.
\end{aligned}$

The appended prime contributes its harmonic mass $\log(11/10)+o(1)$.

Combining this with $xv<1.98b^2$ in (24), we obtain

$\boxed{
\liminf_{z\to\infty}
\frac{\Delta_{2,b}}{H/L^2}
\ge \kappa_* >0,
}
\tag{25}$

where

$\kappa_*=
\frac{2C_2}{1.98M_g}
\frac{(14/5)^2-(5/2)^2}{2}
\log\frac{11}{10}
\int_{41/20}^{11/5}(1-s^{-2})\,ds.$

Crucially, this constant does not depend on $b$. Using $M_g\le4e^\gamma<8$, even the conservative bound

$\kappa_*>\frac{2C_2}{3000}$

is sufficient.

This is a lower bound for a part of the negative deficit of the complete lower tree. It is not a favorable subfamily being proposed as a substitute for the full lower bound.

Now choose any finite number $N$ of disjoint bands, for example $b_j=20\cdot2^j$. Their last-prime exponent ranges are disjoint, so their omitted leaves are distinct.

Take $z\to\infty$ with all these $N$ bands fixed. Equation (22) gives

$\liminf_{z\to\infty}
\frac{\Delta_2}{H/L^2}
\ge N\kappa_*.$

Since $N$ is arbitrary,

$\boxed{
\frac{\Delta_2}{H/L^2}\longrightarrow+\infty.
}
\tag{26}$

There is no moving-parameter uniformity assumption in this argument. Any prescribed lower bound is obtained by fixing a finite collection of bands first.

On the other hand, the ordinary two-form upper sieve gives $S_2(z_0)=O(H/L^2)$. Consequently (22) proves

$\boxed{
\frac{\mathcal L_2}{H/L^2}\longrightarrow-\infty.
}
\tag{27}$

Thus the precise unstopped lower bound (12) cannot produce a positive survivor, even if twin primes are abundant.

Effect of the original stops

Definition 10.2 and equation (10.5) of the ordinary manuscript restrict its stops to nonempty even nodes whose last exponent is at most a fixed $b_1$. 

Plectis Atlas

Choose every band above $b_1$. All ancestors of its omitted leaves have larger last exponents still. No such ancestor can be stopped by the original rule.

Hence the same divergence of the omission deficit holds after any prefix-free exact stops of this bounded-exponent type, regardless of the extra alignment conditions used to select the stops.

Stops at exponents growing without bound, or a fundamentally different admission rule, are not covered by this obstruction.

5. The exact paired mixed-root boundary calculation

The obstruction above already determines the sign of the complete lower bound. Nevertheless, the root pairing identifies explicitly what upper-endpoint averaging can and cannot remove.

Freeze the original admission weights at the full anchored interval. Choose fixed constants

$0<\alpha<\beta<1$

and vary the upper endpoint over $t\in[\alpha,\beta]$:

$z<n\le tz^2-2.$

Using $n=2j-1$, the exact interval for $j$ is

$A_z<j\le C_z(t),
\qquad
A_z=\frac{z+1}{2},
\quad
C_z(t)=\frac{tz^2-1}{2}.$

The floor counts below automatically handle nonintegral endpoints.

For an outer mixed root, split $d=AC$ into its two nonunit coprime products:

$A\mid2j-1,\qquad C\mid2j+1.$

Open the complete small-prime presieve, and let $a=a_0a_2\mid P_o(w)$ be its labelled divisor. The full modulus is

$q=ad=(a_0A)(a_2C).$

Write $U=a_0A,\ V=a_2C$. The root $r\bmod q$ satisfies

$2r\equiv1\pmod U,\qquad
2r\equiv-1\pmod V.$

Interchanging $U,V$ gives the opposite root $-r\bmod q$.

Their common coefficient is precisely $\mu(q)$ when the original outer path is admitted. The outer mixed condition is retained: both $A,C$ must exceed one. This prevents presieve labels from moving a previously priced monochromatic outer root into the mixed correction.

Both floor terms

Put $\vartheta=r/q\in(0,1)$. For real $u$, define

$\mathcal B(u,\vartheta)
=
\{u-\vartheta\}+\{u+\vartheta\}-1.$

Equivalently,

$\mathcal B(u,\vartheta)
=
2\{u\}
-\mathbf1_{\vartheta\le\{u\}}
-\mathbf1_{1-\vartheta\le\{u\}}.$

The combined count of the two roots is exactly

$\begin{aligned}
&\left\lfloor\frac{C_z(t)-r}{q}\right\rfloor
+\left\lfloor\frac{C_z(t)+r}{q}\right\rfloor\\
&\quad-
\left\lfloor\frac{A_z-r}{q}\right\rfloor
-\left\lfloor\frac{A_z+r}{q}\right\rfloor.
\end{aligned}$

Subtracting the reference count $2(C_z(t)-A_z)/q$ gives the paired discrepancy

$\boxed{
E_{\pm}(q,r;t)
=
\mathcal B(A_z/q,\vartheta)
-\mathcal B(C_z(t)/q,\vartheta).
}
\tag{28}$

Thus the complete signed mixed correction is the sum of (28), with coefficient $\mu(q)$, over the admitted outer mixed paths, all their presieve divisors, and one representative of each opposite-root pair.

This retains the reflection relation exactly. It does not turn the opposite roots into independent random points.

Stopping

For a prefix-free collection of even stops, the exact comparison becomes

$\begin{aligned}
\mathcal L_{2,\mathrm{stop}}-HV_2(w)P_2
={}&
\sum_{\nu\ \mathrm{expanded}}
\mu(d_\nu)(N_\nu-\mu_\nu)\\
&+
\sum_{\nu\ \mathrm{stopped}}
\left[S_\nu-\mu_\nu P_{\nu,2}\right],
\end{aligned}
\tag{29}$

where $\mu_\nu=HV_2(w)/d_\nu$, and $P_{\nu,2}$ is the original paired reference subtree at the stop.

If the exact stopped survivor $S_\nu$ is opened into all its smaller-prime continuations, its boundary terms again have the floor form (28). But those continuations no longer satisfy the original admission restriction: they belong to the exact replacement subtree.

Moreover, opposite roots can be paired without qualification only when their effective expansion coefficients agree. For asymmetric label-dependent stops, the difference of their coefficients must be retained alongside the paired sum.

Neither consideration removes the omitted leaves above the fixed stop window established in Section 4.

6. What smoothing the upper endpoint actually buys

Choose a nonnegative function

$\varphi\in C_c^\infty((\alpha,\beta)),
\qquad
\int\varphi(t)\,dt=1.$

The averaged lower bound remains a valid lower bound for the averaged actual survivor count.

The lower anchored boundary is negligible in the complete sum

Summing the first term of (28) is equivalent to summing the root counts on $0<j\le A_z$, minus their reference densities.

The actual root incidences there are bounded by

$\sum_{1\le j\le A_z}
\tau((2j-1)(2j+1))
=z^{1+o(1)}.$

The corresponding reference contribution is $O(zL^2)$, using

$\sum_q\frac{|\mu(q)|2^{\omega(q)}}q
\le\prod_{p\le z_0}(1+2/p)
\ll L^2$

over the possible squarefree products.

Both are $o(z^2/L^2)$.

Thus the lower anchored endpoint does not supply an additional main-scale correction after the complete mixed-root sum has been formed.

The upper boundary

The opposite-root sawtooth sum has zero mean over a complete period. Its Fourier coefficients contain the factor $2\cos(2\pi h\vartheta)$.

Averaging the upper endpoint gives the exact Fourier expression

$\begin{aligned}
&\int\varphi(t)
\mathcal B(C_z(t)/q,\vartheta)\,dt\\
&\quad=
-\sum_{h\ne0}
\frac{2\cos(2\pi h\vartheta)}{2\pi ih}
e\left(-\frac{h}{2q}\right)
\widehat\varphi\left(-\frac{hz^2}{2q}\right),
\end{aligned}
\tag{30}$

with the convention

$\widehat\varphi(\xi)=\int\varphi(t)e(-\xi t)\,dt.$

For $q\ll z^2$, smoothness gives arbitrary fixed power savings in $q/z^2$.

In particular, every complete signed contribution with

$q\le z^2/w^\kappa,\qquad \kappa>0\text{ fixed},$

becomes negligible at the twin-prime scale. To see this directly, choose a sufficiently large fixed Fourier decay exponent $M$. The summed bound is

$\ll_{\varphi,M}
\frac{z^2L^2}{w^{\kappa(M+1)}}
=o(z^2/L^2).$

This is a smoothing calculation on the actual paired boundary expression, including its Möbius coefficients.

The obstruction that remains

The outer admitted moduli satisfy

$d\le H/w^{a_\star}.$

But the full modulus in (30) is $q=ad$, with $a\mid P_o(w)$. Thus the complete presieve includes moduli comparable to, and larger than, $z^2$.

These moduli do not have a rapidly oscillating upper-endpoint phase.

For example, when $q>\beta z^2$, one has $C_z(t)/q<1/2$ throughout the averaging window. Then

$\begin{aligned}
&\int\varphi(t)\mathcal B(C_z(t)/q,\vartheta)\,dt\\
&\quad=
\frac{2}{q}\int\varphi(t)C_z(t)\,dt\\
&\qquad-
\int\varphi(t)
\mathbf1_{\min(r,q-r)\le C_z(t)}\,dt.
\end{aligned}
\tag{31}$

The first term is explicit. The second asks whether the actual CRT root lies in the relevant anchored region.

Opposite-root pairing has reduced this term to a single root-location condition. It has not produced a sign for its Möbius-weighted sum.

Removing the large presieve multipliers would be particularly damaging at compact-gap nodes: their progression lengths are fixed powers of $w$, so the fundamental lemma does not provide arbitrarily small relative error at the resulting truncated presieve level.

Most decisively, the proof of (26) is uniform over the present fixed averaging window. For an omitted leaf, the logarithmic progression length changes by only $O(1/\log w)$; its prime-cofactor and occupation estimates remain valid.

Therefore

$\boxed{
\frac{
\displaystyle\int\varphi(t)\mathcal L_2(t)\,dt
}{
z^2/L^2
}
\longrightarrow-\infty.
}
\tag{32}$

Averaging the upper endpoint cannot rescue this lower tree. The complete signed result is negative, independently of which long-modulus root terms account for that negativity.

7. Quantitative compensation for the favorable monochromatic constant

Let

$U_z=\frac{HV_2(w)}{B^2}
\sim 2C_2e^{-2\gamma}\frac{H}{L^2}.$

Combining the exact decomposition (22) with the two root corrections gives

$\boxed{
B^2P_2+
\frac{\mathcal E_{\rm mix}}{U_z}
=
\frac{S_2(z_0)-\Delta_2}{U_z}
-
\frac{\mathcal E_{\rm mono}}{U_z}.
}
\tag{33}$

We have evaluated the last term completely in (20); its limiting value exceeds $0.61$.

Let $C_{\rm up}$ be a fixed upper bound for $S_2(z_0)/U_z$ furnished by the classical upper sieve. With any fixed collection of $N$ omission bands, (25) gives the quantitative constraint

$\limsup_{z\to\infty}
\left[
B^2P_2+\frac{\mathcal E_{\rm mix}}{U_z}
\right]
\le
C_{\rm up}
-\frac{Ne^{2\gamma}}{3000}
-0.61.$

Taking successively larger fixed $N$, we conclude

$\boxed{
B^2P_2+\frac{\mathcal E_{\rm mix}}{U_z}
\longrightarrow-\infty.
}
\tag{34}$

This is the compulsory compensation in the complete lower-bound calculation.

It is important not to overinterpret the sign: (34) concerns the paired reference plus the complete mixed correction. It does not assert that the mixed correction by itself is negative; the reference polynomial may also make a large negative contribution.

Either way, the favorable monochromatic constant cannot yield positivity.

8. Precisely where unrestricted inversion restores the twin count

For completeness, consider dropping admission entirely and summing all squarefree outer products. This gives a different, exact sieve identity.

For an integer passing the small presieve, put

$J_i(n)=
\mathbf1_{\text{no prime in }(w,z_0]\text{ divides }n+i},
\qquad i=0,2.$

The full monochromatic polynomial is

$J_0(n)+J_2(n)-1.$

The full mixed polynomial is exactly

$\begin{aligned}
&\left(
\sum_{\substack{A\mid n\\A>1\\p\mid A\Rightarrow w<p\le z_0}}
\mu(A)
\right)
\left(
\sum_{\substack{C\mid n+2\\C>1\\p\mid C\Rightarrow w<p\le z_0}}
\mu(C)
\right)\\
&\qquad=(J_0(n)-1)(J_2(n)-1).
\end{aligned}$

Adding them produces

$J_0+J_2-1+(J_0-1)(J_2-1)=J_0J_2.$

After multiplication by $R(n)R(n+2)$, this is exactly the paired survivor indicator.

This multiplication of the two complete nonunit Möbius sums is the precise step at which unrestricted root inversion restores the unknown twin-prime count.

The full-inversion compensation can also be quantified

Let $S_1^{(0)},S_1^{(2)}$ denote the exact one-endpoint survivor counts through $z_0$.

Each endpoint is prime or semiprime, because $z_0^3>z^2$. For example, with upper endpoint $Y$, the first count is exactly

$S_1^{(0)}
=
\pi(Y)-\pi(z)
+
\sum_{z_0<p\le\sqrt Y}
\left[\pi(Y/p)-\pi(p-1)\right].
\tag{35}$

This includes prime squares. The corresponding formula for the translated endpoint changes only the interval endpoints.

The prime-variable comparison from Section 2, applied separately to primes and to these semiprimes, evaluates the extra small-prime sieve on the other endpoint. For semiprimes, fix the smaller prime and apply the distribution estimate to the larger one.

Hence the unrestricted monochromatic correction satisfies

$\mathcal E_{\rm mono}^{\rm full}
=
W(w)
\left[S_1^{(0)}+S_1^{(2)}-2HV_1(z_0)\right]
+o(H/L^2).$

By the prime number theorem and the narrow semiprime range,

$S_1^{(i)}
=
\frac{H}{2L}
+O\left(\frac{H\log L}{L^2}\right).$

It follows that

$\boxed{
\frac{\mathcal E_{\rm mono}^{\rm full}}{U_z}
=-(2-e^\gamma)B+o(B).
}
\tag{36}$

The coefficient $2-e^\gamma=0.218927\ldots$ is strictly positive.

Thus unrestricted inversion produces a large negative monochromatic correction, unlike the positive constant of the admitted lower tree.

The complete mixed correction must compensate it:

$\boxed{
\frac{\mathcal E_{\rm mix}^{\rm full}}{U_z}
=(2-e^\gamma)B+o(B).
}
\tag{37}$

This follows unconditionally from the ordinary paired upper sieve and the exact full identity.

The leading positive mixed contribution in (37) is therefore already committed to paying the negative term in (36). It is not a twin-prime reserve.

At the decisive finer scale, the identity reads

$HV_2(z_0)
+\mathcal E_{\rm mono}^{\rm full}
+\mathcal E_{\rm mix}^{\rm full}
=
T(z)+O_{A_0}\left(\frac{H\log L}{L^3}\right),
\tag{38}$

by the previous near-square composite cleanup estimate (11).

Estimating the left side strictly positively to the required precision is once again the original twin-prime problem.

9. Final verdict

This investigation changes the status of the proposed transfer substantially.

Component

Result

Exact comparison with the one-endpoint tree using identical weights

Established

Complete monochromatic correction

Evaluated; strictly positive constant in the admitted tree

Opposite-root pairing

Exact boundary formula (28)

Nonnegative smooth upper-endpoint averaging

Does not rescue the full lower bound

Complete omission deficit

Diverges relative to twin-prime scale, by (26)

Original bounded-exponent stopping mechanism

Does not remove this deficit

Unrestricted inversion

Restores the exact twin-prime count

The original admitted-tree construction should now be abandoned as a route to (12). Subject to the ordinary occupation theorem, the obstruction is stronger than a missing mixed-root estimate: the full proposed lower bound itself tends to minus infinity in twin-prime units.

The positive monochromatic correction was genuine, and its complete calculation was worthwhile. But the admission losses occur over arbitrarily many distinct logarithmic exponent bands, each with a fixed positive arithmetic cost. Their cumulative effect overwhelms that correction.

A viable replacement would require a new admission/stopping mechanism that prevents this divergent omission deficit. The ordinary manuscript's fixed terminal-exponent stops cannot do so. This is not an impossibility result for every two-residue Jacobsthal method, nor a disproof of twin-prime infinitude.

Verification scope: the arithmetic comparisons, floor identities, omission identity, and per-band estimates are derived here. The occupation-dependent conclusions use Proposition 5.5 and the invariant densities of the original manuscript as inputs. I inspected its recovered indexed mathematical text, including the precise admission and stopping conditions, but have not independently certified the entire renewal proof. The parameter changes, compact occupation windows, and smoothing construction were my mathematical choices; all band parameters are fixed before taking the relevant limit.

No new manuscript or files have been created.



### Independent check of the omission bands and limiting argument

[Separate research chat](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e-twin-prime-conjecture-research/c/6b05e53a-f038-83ee-99c9-ad2380de1583)



Verdict

The central no-go argument survives my independent mathematical challenge, conditional on the original manuscript's compact prime-path occupation theorem. In particular, I find no missing factor, invalid prime-independence assumption, or improper interchange of limits in the argument that the omission deficit diverges in units of $z^2/\log^2 z$.

There is a useful simplification: the divergence proof does not need the numerical monochromatic correction, the mixed-root Fourier calculation, or an extension of the manuscript's inverse theorem to two forbidden residues. It can be proved using a restricted set of genuine omitted leaves and their exact arithmetic counts.

My source-verification scope is important. I read the attached argument and attempted to open all four specified GitHub source files. The direct endpoints returned cache misses. I recovered the original manuscript's relevant mathematical text through its Plectis Atlas TeX rendering, including the tree rule, harmonic change of measure, invariant occupation densities, prime-occupation argument and stopping definition. I have not independently certified the manuscript's entire renewal and prime-coupling proof. 

Plectis Atlas+3

The following is my reconstruction of the shortest valid route to the claimed obstruction.

1. Does the one-colour occupation theorem embed with identical weights?

Yes. This is the first essential check.

Use the attached argument's parameters

$\begin{gathered}
I_z=\{n:z<n\le z^2-2\},\qquad H=|I_z|,\\
L=\log z,\qquad w=\frac{L}{(\log L)^2},\\
z_0=\frac z{L^{A_0}},\qquad
B=\frac{\log z_0}{\log w}.
\end{gathered}$

The original admission constant is $a_\star=1/100$. For a decreasing prime path with product $d$, define

$r_d=\log_w(H/d)+2-a_\star.$

An even child obtained by appending a prime of exponent $u=\log_w p$ is admitted precisely when

$r_{\rm parent}-u\ge\max(2u,u+2).
\tag{1}$

The original standard paths use only the condition $r_{\rm parent}-u\ge2u$. The two admission rules agree whenever $u\ge2$. This is confirmed by the manuscript's equation (3.1), Lemma 3.1 and its subsequent definition of standard paths. 

Plectis Atlas

Restrict the paired tree to one colour

At every odd selected prime, the paired tree has two possible labels:

$n\equiv0\pmod p,\qquad n\equiv-2\pmod p.$

Restrict every label along a path to the first choice.

There is then an exact bijection between ordinary admitted prime paths and these monochromatic admitted paths. It preserves:

the ordered prime tuple;

its product $d$;

every prefix gap and terminal ratio;

the admission decision at every prefix;

the harmonic weight $1/d$.

The reference progression count in the paired problem differs from the ordinary reference count, because its small-prime density is $V_2(w)$, rather than $V_1(w)$. But the occupation theorem measures the harmonic path weights, not the presieve counts.

Thus that density difference does not alter this embedding.

In particular, there is no factor $2^{\omega(d)}$ to insert when using just one monochromatic orientation. That factor belongs to the complete labelled tree.

Check the starting state

The new root satisfies

$\frac{r_1}{B}
=
\frac{\log_w H+2-a_\star}{B}
\longrightarrow2.$

Although the anchored interval has a different length from the interval in the original theorem, its starting ratio remains in the compact range required by the source's prime-occupation estimates.

The relevant source calculation is the harmonic change of measure (4.17), followed by Lemma 4.4, Proposition 4.5 and Proposition 5.5(iv). The starting normalization is

$\frac{B^2\phi_{\rm e}(r_1/B)}{r_1^2}
\longrightarrow e^\gamma,$

because $\phi_{\rm e}(2)=4e^\gamma$. The invariant odd-state density satisfies

$\frac{\pi_{\rm o}(s)}{\phi_{\rm o}(s)}
=1-s^{-2}.$

Consequently, on a fixed compact odd-state window whose terminal exponents exceed $2$, the occupation input is

$\boxed{
B^2\sum_{d\in\mathcal A}\frac1d
\longrightarrow
\frac{e^\gamma}{M_g}
\iint_{\mathcal A}r(1-s^{-2})\,dr\,ds.
}
\tag{2}$

The manuscript supplies $0<M_g\le4e^\gamma$. 

Plectis Atlas

Audit finding: the weight and starting-state transfer needed for the omitted-parent construction is valid at the stated occupation-theorem scope. There is no need for a two-colour renewal theorem.

2. The exact omission identity is correct

Let $N_\nu$ be the count at an admitted labelled node after applying the complete small-prime presieve through $w$. Let $S_\nu$ additionally avoid all primes strictly below its last selected prime.

Partitioning by the least additional prime hit gives

$S_\nu=N_\nu-\sum_{\nu'\text{ child of }\nu}S_{\nu'}.$

For an odd prime, its two possible hit classes are disjoint. Thus this identity applies unchanged to the paired tree when the children carry their labels.

Expand recursively, retaining every admitted node but leaving each first rejected child unexpanded.

Every rejected child has even depth. Its exact count therefore enters with a positive sign. Hence

$\boxed{
S_2(z_0)=\mathcal L_2+\Delta_2,
\qquad
\Delta_2=\sum_{\nu\text{ first omitted}}S_\nu\ge0.
}
\tag{3}$

This verifies equation (22) of the attachment. 
Pasted text(2).txt

There are two important multiplicity points.

First, a decreasing labelled tuple has a unique prefix history. Thus the same omitted node cannot be reached by two different tree histories.

Second, an integer can contribute to several omitted nodes. These contributions are genuinely separate summands of the expansion. They must not be deduplicated.

The exact deficit in (3) is a sum of node counts, not the cardinality of their union.

3. Verify the omitted band geometry

Fix any constant $b\ge20$, independently of $z$.

Consider admitted odd parents with gap $r$ and terminal ratio $s$ satisfying

$2.5b<r<2.8b,
\qquad
2.05<s<2.2.
\tag{4}$

Their terminal exponent exceeds

$\frac{2.5b}{2.2}>1.13b.$

Append a genuine prime $p=w^u$ with

$b<u<1.1b.
\tag{5}$

It is strictly smaller than the parent's last prime, so the child is a legitimate continuation.

Its new gap satisfies

$1.4b<r-u<1.8b<2u.$

The child fails the admission condition (1), including the weaker standard admission rule.

Write $d$ for the child's product, and put

$v=\log_w(H/d)=r-u-2+a_\star.$

Uniformly throughout these windows,

$v-u>0.3b-2+a_\star>0,$

and

$v<2u,\qquad uv<1.98b^2.
\tag{6}$

These inequalities have fixed positive margins.

They establish the essential arithmetic fact: each selected omitted monochromatic progression has room for a prime cofactor $k>p$, while its coordinate length is smaller than $p^2$.

This confirms the geometric portion of the attachment's per-band construction.

4. The prime-cofactor count survives the full summation

This is the most delicate arithmetic step in the proposed no-go.

Take the monochromatic orientation in which every selected prime divides $n$. For an omitted product $d$, restrict to integers

$n=dk,\qquad k>p,\qquad k\text{ prime},$

where $p$ is the last prime of $d$.

The first endpoint automatically avoids every prime below $p$. We must still impose

$P^-(dk+2)\ge p.$

Counting this second condition independently for each short cofactor would be unjustified. The attachment instead switches to the largest prime factor of $d$. I checked that this switch works, including the aggregate remainder.

Step A: remove products having no sufficiently large prime

Set

$R_*=\exp(L^{1/3}).$

Every selected omitted product satisfies

$d=\frac H{w^v}=z^{2-o(1)}>z,
\qquad d<H.$

Rankin's bound gives

$\begin{aligned}
\sum_{\substack{d>z\\
d\text{ squarefree}\\P^+(d)\le R_*}}\frac1d
&\le
e^{-L^{2/3}}
\prod_{q\le R_*}(1+q^{-1+L^{-1/3}})\\
&\ll e^{-L^{2/3}}L^{O(1)}.
\end{aligned}$

Since the number of multiples of $d<H$ in the interval is $O(H/d)$, the entire discarded arithmetic contribution is

$O_A(HL^{-A})$

for every fixed $A$.

This removal is valid before any signed cancellation. It also removes negligible occupation mass.

Step B: vary the largest prime

For the remaining products, write

$d=Pa,\qquad P=P^+(d)>R_*.$

Fix $a$ and the prime cofactor $k$. The last prime $p$ is now fixed as well.

Within a dyadic interval $P\asymp R_1$, all the following requirements impose interval conditions on $P$:

$P$ exceeds every prime factor of $a$;

the original decreasing path is admitted up to the parent;

the parent belongs to the window (4);

the child satisfies the chosen omission-band restrictions;

$Pak$ lies in $I_z$.

To check the admission statement, note that $P$ is the first path factor. Changing $\log P$ changes every subsequent gap by the same additive amount. Each later admission inequality is therefore a linear upper bound on $\log P$. The parent ratio restriction also gives an interval, because its terminal prime is fixed.

There is no arbitrary subset of primes concealed in this step.

For each odd prime $\ell<p$, every factor of $ak$ is a unit modulo $\ell$. The second endpoint forbids exactly one reduced class:

$P\equiv-2\overline{ak}\pmod\ell.$

At two, no additional restriction is necessary, since both endpoints are odd.

Step C: prove the uniform prime-sieve comparison

For every such admissible interval $J\subseteq[R_1,2R_1]$, the required comparison is

$\begin{aligned}
&\#\{P\in J:P\text{ prime},\ P^-(Pak+2)\ge p\}\\
&\qquad=
W^{<}(p)\#\{P\in J:P\text{ prime}\}
+O_{A,b}(R_1L^{-A}),
\end{aligned}
\tag{7}$

where

$W^{<}(p)=
\prod_{2<\ell<p}\left(1-\frac1{\ell-1}\right).$

This is an absolute interval error, not an assumed relative error for every potentially short interval $J$.

One can establish (7) directly by truncated inclusion–exclusion. Take the truncation order $J_0\asymp C_A\log L$. Because $b$ is fixed,

$p\le w^{1.1b},$

and every opened modulus is bounded by

$p^{J_0+1}
=\exp(O_{A,b}((\log L)^2)).$

On the other hand,

$R_1\gg\exp(L^{1/3}).$

Thus the opened moduli lie well within the classical Bombieri–Vinogradov range at scale $R_1$.

The upper and lower Bonferroni polynomials differ in principal mass by at most the relevant reciprocal factorial tail. Increasing $C_A$ makes this smaller than any fixed inverse power of $L$. Maximal Bombieri–Vinogradov, with sufficiently high logarithmic precision at scale $R_1$, gives the error in (7).

The crucial comparison is

$(\log L)^2=o(L^{1/3}),$

not a claim that the complete small-prime period is itself short.

Step D: sum every remaining factor

For each fixed dyadic interval $P\asymp R_1$,

$ak\ll H/R_1.$

The number of numerical pairs $(a,k)$ is therefore at most

$\sum_{ak\ll H/R_1}1
\ll \frac H{R_1}L.$

Each $a$ determines the remaining decreasing prime tuple uniquely. There is no additional path-ordering multiplicity.

The complete error in this dyadic interval is consequently

$O_{A,b}(HL^{1-A}).$

There are $O(L)$ dyadic intervals. Requesting $A>4$ gives an aggregate error

$o(H/L^2).$

This is precisely the error scale required by the attachment.

Audit finding: the prime-variable comparison survives the full summation. It does not require a uniform relative estimate for an individual short cofactor interval, nor an unaccounted factor for the number of paths.

5. The per-band lower constant is genuinely independent of $b$

After completing the largest-prime comparison, return to the sum over $d$.

Uniformly in the fixed margins (6), the prime number theorem gives

$\#\{k\text{ prime}:p<k\le (z^2-2)/d\}
=
(1+o_b(1))\frac H{d\,v\log w}.$

The lower endpoint $p$ is negligible because $v-u$ is bounded below by a positive constant.

Also, $d>z$, so every counted $dk$ automatically satisfies the lower anchored endpoint.

Mertens' theorem gives, uniformly over the fixed appended-prime band,

$W^{<}(p)
\sim\frac{2C_2e^{-\gamma}}{u\log w},$

where

$C_2=\prod_{\ell>2}
\left(1-\frac1{(\ell-1)^2}\right).$

Let $\Delta_b^{\rm mono}$ denote the selected monochromatic omitted-leaf contribution. We have proved

$\boxed{
\Delta_b^{\rm mono}\ge
(1+o_b(1))
\frac{2C_2e^{-\gamma}H}{(\log w)^2}
\sum_{\text{selected children }d}\frac1{d\,uv}
+o_b(H/L^2).
}
\tag{8}$

I deliberately write this as a lower bound. It is sufficient for the no-go and does not require identifying every additional cofactor or every other colouring of an omitted product.

In fact, the exceptional cofactors $k=1$ and $k=p$ would be negligible here: there are at most $O(H/w^{1.4b-2+a_\star})$ selected numerical products, and $b\ge20$.

Insert the occupation mass

By (2), the selected parents have harmonic mass satisfying

$\begin{aligned}
B^2\sum_{\text{parents }d'}\frac1{d'}
\longrightarrow{}&
\frac{e^\gamma}{M_g}
b^2\frac{2.8^2-2.5^2}{2}\\
&\times\int_{2.05}^{2.2}(1-s^{-2})\,ds.
\end{aligned}$

Every prime in the appended band is available at every selected parent, because the parent's last exponent exceeds $1.13b$.

Its harmonic mass tends to

$\sum_{w^b<p<w^{1.1b}}\frac1p
\longrightarrow\log(1.1).$

Thus no extra ordering restriction reduces this appended-prime sum.

Using $uv<1.98b^2$, together with

$B^2(\log w)^2=(\log z_0)^2\sim L^2,$

we obtain

$\boxed{
\liminf_{z\to\infty}
\frac{\Delta_b^{\rm mono}}{H/L^2}
\ge\kappa_*,
}
\tag{9}$

where

$\kappa_*=
\frac{2C_2}{1.98M_g}
\frac{2.8^2-2.5^2}{2}
\log(1.1)
\int_{2.05}^{2.2}(1-s^{-2})\,ds.$

This is strictly positive and, most importantly, independent of $b$.

The conservative numerical estimate in the attachment is correct. For example,

$\frac{2.8^2-2.5^2}{2}=0.795,$

$\int_{2.05}^{2.2}(1-s^{-2})\,ds>0.11,$

and $\log(1.1)>0.095$, while $M_g<8$. These inequalities give

$\boxed{\kappa_*>\frac{2C_2}{3000}.}$

This independently verifies the constant-scale conclusion of the attachment's equations (24)–(25). 
Pasted text(2).txt

6. The order of limits is valid

Choose a fixed finite collection of bands

$b_j=20\cdot2^j,\qquad 1\le j\le N.$

Their appended-prime exponent intervals are disjoint. Hence the selected omitted leaves are distinct.

Using the nonnegativity of every omitted count, (3) and (9) give

$\liminf_{z\to\infty}
\frac{\Delta_2}{H/L^2}
\ge N\kappa_*.$

Here $N$, and therefore every $b_j$, is fixed before $z$ tends to infinity.

This establishes

$\boxed{
\frac{\Delta_2}{H/L^2}\longrightarrow+\infty.
}
\tag{10}$

There is no assertion that the per-band asymptotic is uniform for $b=b(z)$. None is needed.

For any prescribed large lower bound, choose enough fixed bands to exceed it, then take $z$ beyond the finitely many corresponding asymptotic thresholds.

The standard two-dimensional upper sieve gives

$S_2(z_0)\ll H/L^2.$

For this upper bound, it already suffices to sieve through a small fixed power of $z$, far below $z_0$, with an admissible finite level. The local root counts are one at two and two at every odd prime.

Substituting into (3) proves

$\boxed{
\frac{\mathcal L_2}{z^2/\log^2z}
\longrightarrow-\infty.
}
\tag{11}$

This is the precise no-go. It applies to the actual arithmetic lower-tree expression, not merely to its independent-residue reference polynomial.

7. Do the original inverse theorem and stops provide a repair?

They do not repair this particular deficit.

The source's inverse argument identifies alignment with suitable rationals in its one-residue setting. Its purpose is to locate nodes at which a different arithmetic count can replace the reference subtree. I did not independently verify the full inverse proof or establish a two-residue analogue.

Fortunately, the no-go does not depend on whether such an analogue is possible.

The recovered Definition 10.2 specifies nonempty even stops whose last representative exponent lies in a fixed interval $[b_0,b_1]$, together with additional alignment and admission-margin conditions. 

Plectis Atlas

Choose all omitted bands above $b_1+1$.

Every ancestor of a selected omitted child has last prime exponent greater than the appended exponent $u>b_j$. Thus none can belong to that fixed stopping window.

The representative exponents differ from the true exponents by $o(1)$ for the manuscript's fixed-width prime bins, so the extra margin of one suffices.

An exact stop elsewhere in the tree replaces its entire descendant expansion by the exact survivor count. It removes omissions underneath that stop, but it cannot change the omissions on the surviving branches selected above.

Consequently, for the stopped lower bound,

$S_2(z_0)=\mathcal L_{2,\rm stop}+
\sum_{\substack{\nu\text{ first omitted}\\
\nu\text{ not underneath a stop}}}S_\nu.$

The same band argument proves

$\boxed{
\frac{\mathcal L_{2,\rm stop}}{z^2/\log^2z}
\longrightarrow-\infty
}
\tag{12}$

for any such prefix-free collection of exact stops confined to a fixed terminal-exponent window.

This is stronger than testing the particular alignment conditions in inverse.tex or stops.tex. Even if every proposed paired aligned-stop count were correct, fixed-window stops could not remove the selected deficit.

8. Additional checks on the monochromatic comparison and smoothing

The separate comparison between the ordinary tree and the paired monochromatic terms also survives the arithmetic audit.

For admitted $d\le z$, ordinary periodic counting modulo $P(w)$ gives total error

$O(zP(w))=z^{1+o(1)}.$

For $d>z$ with only prime factors at most $R_*$, the Rankin bound already established makes the contribution negligible.

For the remaining $d=Pa$, fix $a,k$ and vary $P$, exactly as in §4. Now the second-endpoint sieve limit is only $w$. The coefficient $\mu(d)=-\mu(a)$ is constant throughout each prime-variable interval. The same aggregate error proof applies.

Thus the attached monochromatic comparison with identical admission weights,

$\mathcal L_{\rm mono}
=
\frac{V_2(w)}{V_1(w)}(J_0+J_2)
-HV_2(w)+O_A(HL^{-A}),$

is valid at the specified unstopped scope.

I have not separately certified the attachment's numerical Buchstab integral for its favorable monochromatic constant. That constant is unnecessary for establishing (11).

Upper-endpoint averaging cannot repair the deficit

Freeze the tree's admission weights and replace the upper endpoint $z^2-2$ by

$tz^2-2,\qquad t\in[\alpha_0,\beta_0]\subset(0,1).$

The occupation windows remain unchanged.

For each selected omitted product, the available cofactor length changes from $H/d$ to

$(1+o(1))tH/d.$

Its exponent changes by $O(1/\log w)$, uniformly on the fixed averaging interval. The margins in (6) are therefore preserved.

The prime-variable comparison uses maximal interval errors and remains uniform in $t$. Each omitted band retains a normalized contribution bounded below by $\alpha_0\kappa_*+o(1)$.

Hence every nonnegative normalized smoothing of these upper endpoints retains the divergent omission deficit.

This confirms the attachment's conclusion about smoothing without needing to evaluate its entire mixed-root sawtooth expansion.

9. Distinguish the failed lower bound from the actual twin count

There is no negative result here about the true number of twins.

Indeed, the anchored survivor count through $z_0=z/L^{A_0}$ differs from the genuine twin count only by a smaller-order near-square composite contribution.

If an endpoint is composite and survives through $z_0$, it must be a semiprime, since

$z_0^3>z^2$

for sufficiently large $z$.

Its smaller prime factor lies in $(z_0,z]$. For each such prime $p$, an ordinary two-form upper sieve on the larger factor $q$ and the other endpoint $pq\pm2$ gives

$\ll\frac{H}{pL^2}$

possible surviving pairs, uniformly in $p$. The sieve can be run through a fixed small power of $z$; the fact that the other endpoint survives through $z_0$ is more than sufficient.

Since

$\sum_{z_0<p\le z}\frac1p
\ll_{A_0}\frac{\log L}{L},$

the total composite-neighbor contribution is

$O_{A_0}\left(\frac{H\log L}{L^3}\right).$

Therefore, writing $T(z)$ for the genuine anchored twin count,

$\boxed{
S_2(z_0)=T(z)+
O_{A_0}\left(\frac{H\log L}{L^3}\right).
}
\tag{13}$

The lower-tree obstruction can consequently coexist with a twin count of the expected positive order $H/L^2$. It does not distinguish that situation from the possibility of finitely many twins.

10. Final audit decision

Proof obligation

Independent finding

Monochromatic embedding and harmonic weights

Pass

Starting ratio and occupation normalization

Pass at the source theorem's stated scope

Omitted-band geometry

Pass

Uniform prime-cofactor count

Pass

Aggregate interval and remainder costs

Pass

Exact omission identity and multiplicities

Pass

Fixed-band order of limits

Pass

Original fixed-exponent stops

Do not remove the divergence

Entire renewal/prime-coupling theorem

Used as a source input; not independently certified here

Positive full lower bound for twins

Not established

I therefore find no failed implication in the central divergence proof after taking the original compact occupation theorem as an input.

A repair would have to change the admission mechanism or intercept omitted branches over an unbounded range of terminal exponents. Adding more stops within any fixed window, or completing finitely many additional omission bands, cannot suffice. The remaining bands reproduce the same argument.

I did not identify a new admission rule or a growing-exponent stopping mechanism whose complete arithmetic lower bound is provably positive. Exact expansion of all omitted branches would recover the true survivor count, but would not by itself estimate it.

The appropriate conclusion is to reject this particular transferred one-residue lower tree as a route to positivity. That conclusion is considerably stronger than an unestimated mixed-root error, but much narrower than a general impossibility theorem for two-residue Jacobsthal methods.

I used a direct largest-prime sieve reconstruction to check the interval errors and a separate near-square upper sieve to verify the distinction from the twin count. The original GitHub source files remained inaccessible, so the source-dependent part of the verdict retains the verification limitation stated above. No new files or paper were created.




---

## Ordered residues of consecutive primes — a checked corollary and its limit

**Status.** A deduction from existing bounded-gap machinery, independently checked within the normal ChatGPT account. No claim of independent priority or proof of twin-prime infinitude. [Source chat](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6b05e29c-2148-83ee-b4c5-1176ac022aef) · [Independent review](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6af7fd52-87a8-83ee-952d-ea2ca54d783b)

For all but at most five odd prime moduli, **every ordered pair of distinct reduced residues occurs infinitely often among consecutive primes**. Indeed, suppose six distinct prime moduli have a nonrecurring ordered pair each. Index 64 residues by six-bit words in increasing binary order. At coordinate $i$, assign the first prescribed residue to bit 0 and the second to bit 1. The Chinese remainder theorem gives reduced residues modulo the product of the six primes. In every increasing pair of word indices, the most significant differing coordinate changes from 0 to 1. Definition 1.4 and Theorem 1.5 with $m=r=2$ give a strictly increasing pair of indices occurring infinitely often for consecutive primes. Its relevant coordinate contradicts nonrecurrence. [Lau, Theorem 1.5](https://arxiv.org/html/2409.12819v2)

There is also a fixed-gap variant using the earlier consecutive-tuple theorem. Choose 50 distinct six-bit words in order and lift the associated residues to increasing shifts. By CRT the shifts can additionally be zero modulo primes up to 50 outside the six chosen moduli. Take the common leading coefficient to be the product of the six moduli. The forms are admissible, and the leading coefficient is coprime to every shift. The consecutive-tuple construction and the 50-form result give one fixed pair of shifts attained infinitely often by consecutive primes. The lifts can be spaced more than any preassigned $G$ apart. For each $G$ at most five moduli can have a distinct ordered pair lacking a recurring gap greater than $G$. These exceptional sets are nested, so their union also has size at most five. [Banks–Freiberg–Turnage-Butterbaugh](https://arxiv.org/abs/1311.7003) · [Ford, general linear forms](https://www.ford126.web.illinois.edu/wwwpapers/phink.pdf)

The modulus is fixed first. For a residue difference of two, a recurring even gap can be $2+2kq$ with $k\ge1$. In fact the same construction can force arbitrarily large recurring gaps in that residue pair. The bounded gap depends on the modulus and the chosen lifts. Neither recurrence nor the combinatorial selection gives a gap of size two. The identities and earlier publications are the reason this observation is kept as a corollary in the archive.


## Why the two-form semiprime sieve does not supply a positive twin-prime count

Goldston, Graham, Pintz and Yıldırım's Theorem 3 gives infinitely many prescribed gap-two pairs whose endpoints each have at most two prime factors. It allows a prime at one endpoint and a semiprime at the other. Write \(K=(\Lambda*\Lambda)/\log\) pointwise for \(n>1\), and \(G=\Lambda+K\). In the expansion of the two-endpoint product \(\Lambda(n)\Lambda(n+2)=(G-K)(n)(G-K)(n+2)\), a pair with both endpoints genuine squarefree semiprimes contributes zero pointwise. A count of such pairs alone supplies no lower bound for twins.

Two specific ways the project tried to extract a stronger conclusion admit short checks.

* **Covering all possible selected pairs by affine relations.** For \(L_i(t)=a_i t+b_i\), \(a_i>0\), join \(i,j\) when odd positive multipliers \(c,d\) give \(cL_i-dL_j=\pm2\) identically. On an edge \(ca_i=da_j\), hence both slopes have the same 2-adic valuation. Put \(z_i=b_i(a_i/2^{v_2(a_i)})^{-1}\bmod 4\). Multiplying the difference \(z_i-z_j\) by the common odd part of \(ca_i=da_j\) gives \(2\bmod4\). Thus every edge crosses the partition \(\{0,1\}\mid\{2,3\}\) of the \(z_i\). There is no triangle. An unspecified two-out-of-three selection of squarefree semiprimes cannot by itself guarantee an edge in such a diagram.
* **Optimizing the paper's one-polynomial two-form score.** Set \(B=4\), \(F(t)=\int_0^tP(v)\,dv\), \(J_0=\int_0^1(1-t)P(t)^2\,dt\). By Theorems 7–8 and §8 the leading score for two selected squarefree semiprimes is proportional to \(J=(J_1+J_2+J_3)/2-J_0\). At any fixed positive factor cutoff in the range of the formulas, the first two nonnegative integrals are bounded above by
  \[
  \int_0^1\frac{4\,dy}{y(4-y)}\int_0^1 [F(t)-F((t-y)_+)]^2\,dt
  \le 4\log(4/3)J_0.
  \]
  Cauchy–Schwarz bounds the square by \(y\int_{(t-y)_+}^{t}P(v)^2\,dv\), and each \(v\) is integrated over a \(t\)-interval of length at most \(1-v\). The last integral is \(J_3=(\log3)\int_0^1F^2\). With \(\phi=t+t^2/2\), integration by parts gives \(J_0=\int_0^1(1-t)\phi^2((F/\phi)')^2+\int_0^1[2/(1+t/2)]F^2\), with vanishing boundary terms. Hence \(\int F^2\le3J_0/4\). Together \(J\le[2\log(4/3)+(3/8)\log3-1]J_0<-0.0126J_0\) for nonzero \(P\). Trying further fixed polynomials in this score at distribution level \(1/2\) cannot yield positivity. The inequality concerns this score only. It gives no upper bound on the actual number of prime or semiprime pairs.

[Hosted derivation](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e-twin-prime-conjecture-research/c/6b05e53a-f038-83ee-99c9-ad2380de1583) · [Authors' sieve formulas](https://renyi.hu/~pintz/0609615.pdf) · [Published corrigendum concerning Theorem 1](https://doi.org/10.1112/plms/pds053). No claim of publication priority.
