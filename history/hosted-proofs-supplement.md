# Twin Prime research supplement — primitive three-square counts and divisor-pair parity

admin@cosmosgeek.org · b321014@iiit-bh.ac.in

## Results and verification

**Three-square test.** For prime ℓ > 7 with ℓ ≡ 37 (mod 140), let r₃ᵖʳⁱᵐ count ordered, signed representations by three squares with coordinate gcd one. The first reply derives r₃ᵖʳⁱᵐ(36ℓ²−1) ≡ 48 (mod 96) exactly when 6ℓ−1 and 6ℓ+1 are both prime. Under m ≡ 6 (mod 8), primitive class-number residue 2 (mod 4) first selects two odd prime powers. For m=6ℓ any exponent ≥3 gives a proper factor p+1 or q−1 of 6ℓ with complementary factor greater than 3. Only the small possibility 6 remains, forcing p=5 or q=7, excluded by the chosen residues. The source also exhibits infinitely many centers where a complete four-square trace has residue 2 (mod 4) while the desired trace coordinate vanishes. Its obstruction for an arbitrary fixed trace modulus permits general centers, and does not assert the stronger prime-center restriction there. [Original class-number reply](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6b05e29c-2148-83ee-b4c5-1176ac022aef).

**Finite-cutoff obstruction.** Write an even midpoint as m=2s. In the second reply's square-divisor-corrected expansion, truncate all four row parameters at an integer R≥1 and let L be the least common multiple of j² for odd j≤R. On L consecutive sufficiently large centers the trivial row has odd parity; every nontrivial retained row pairs with its reciprocal, contributing 2L/P for a row period P dividing L. The Chinese remainder theorem supplies arbitrarily high disjoint such intervals where every neighboring odd integer is composite. Thus the true twin count is zero and the omitted rows change the parity. This proves failure for every finite cutoff in that specific expansion. It does not determine the parity of the complete sum on intervals containing twins. [Original divisor-pairing reply](https://chatgpt.com/g/g-p-6af401d0db208191ab9a464770301f0e/c/6b05e53a-f038-83ee-99c9-ad2380de1583).

**Editorial status.** Codex checked the elementary factor exclusions, the full-period pairing and the composite-interval construction. The class-number implication uses classical genus theory, the Rédei criterion, the order class-number formula and Gauss’s three-square formula. The trace evaluations and subsidiary identities below are the original ChatGPT author's derivations; this source edition does not independently certify each analytic or modular-form input. Neither reply establishes infinitely many prime pairs.

## Source replies

The two assistant-authored mathematical replies are reproduced below from the original project conversations. Displayed formulas use their TeX annotations. Formatting and citation labels reflect the rendered replies. User prompts and other messages are excluded.

### 1. Class numbers and primitive three-square coefficients

#### 1. The genus-theory equivalence is correct

Write $m\equiv6\pmod8$, $m>2$, and put

$$
D=m^2-1=(m-1)(m+1).
$$

Then $D\equiv3\pmod8$, and the two factors are odd and coprime.

If $D$ is squarefree, $-D$ is a negative fundamental discriminant. Gauss genus theory gives

$$
\dim_{\mathbb F_2}\mathrm{Cl}(-D)[2]
=\omega(D)-1.
$$

In particular, if $D$ has at least three prime factors, then $4\mid h(-D)$.

Conversely, suppose both endpoints are prime:

$$
p=m-1\equiv5\pmod8,\qquad
q=m+1\equiv7\pmod8.
$$

The prime discriminants of $-D$ are $p$ and $-q$. The relevant Rédei matrix entry is nonzero, since

$$
\left(\frac{-q}{p}\right)
=
\left(\frac{-2}{p}\right)
=-1.
$$

The 2-rank is one and the 4-rank is zero, so the 2-primary class group has order exactly two. This is the standard genus and Rédei rank criterion. 

cambridge.org+1

Therefore the precise equivalence is

$$
\boxed{
m-1,m+1\text{ prime}
\iff
D\text{ squarefree and }h(-D)\equiv2\pmod4.
}
\tag{1}
$$

For these squarefree $D$, the Hurwitz class number equals $h(-D)$. Gauss's three-square formula then gives

$$
r_3(D)=24H(D),
$$

where signs and coordinate order are counted. The factor 24 is the correct normalization for $D\equiv3\pmod8$. 

pure.mpg.de

Thus the proposed class-number detector works. The squarefree requirement, however, is substantive.

#### 2. The conductor calculation gives a stronger primitive detector

Write

$$
D=d f^2,\qquad d\text{ squarefree}.
$$

Because odd squares are one modulo eight, $d\equiv3\pmod8$.

In our particular factorization, each of $m-1,m+1$ has a nontrivial squarefree kernel: their residues are respectively five and seven modulo eight, so neither is a square.

Consequently $d$ has at least two distinct prime factors. In particular, neither of the exceptional unit groups at discriminants $-3,-4$ occurs.

Let $H^{\rm prim}(D)$ count primitive quadratic-form classes with discriminant $-D$, and write

$$
\chi_d(\ell)=\left(\frac{-d}{\ell}\right).
$$

The quadratic-order class-number formula gives

$$
H^{\rm prim}(D)
=h(-d)f\prod_{\ell\mid f}
\left(1-\frac{\chi_d(\ell)}{\ell}\right).
\tag{2}
$$

The corresponding Hurwitz formula, including imprimitive classes, is

$$
H(D)=h(-d)
\prod_{\ell^e\parallel f}
\left[
1+\sum_{j=1}^{e}\ell^{j-1}
(\ell-\chi_d(\ell))
\right].
\tag{3}
$$

These are the usual conductor factors in the Hurwitz class-number formula. 

tandfonline.com

Their parities are different in a useful way.

If $\ell\mid d$, the primitive local factor in (2) is odd; the factor in (3) is odd exactly when $e$ is even.

If $\ell\nmid d$, the primitive local factor is even, whereas the entire Hurwitz local factor in (3) is odd.

It follows that:

$$
\boxed{
H^{\rm prim}(m^2-1)\equiv2\pmod4
\iff
m-1=p^{2a+1},\quad m+1=q^{2b+1}
}
\tag{4}
$$

for distinct primes $p,q$ and nonnegative integers $a,b$.

Here is the remaining 4-rank check. In the two-prime-power case, $p\equiv5\pmod8$ and $q\equiv7\pmod8$. Since $q^{2b+1}\equiv2\pmod p$,

$$
\left(\frac{-q}{p}\right)
=\left(\frac{-2}{p}\right)=-1.
$$

Thus the fundamental core has class number exactly twice an odd integer, and every conductor factor in (2) is odd.

Conversely, residue two in (2) requires exactly two primes in the squarefree core and forbids any conductor prime outside that core. Coprimality of $m-1,m+1$ gives the two separate prime powers in (4).

For the imprimitive Hurwitz count, the exact criterion is broader:

$$
H(m^2-1)\equiv2\pmod4
$$

if and only if

$$
m-1=p^{4a+1}u^2,\qquad
m+1=q^{4b+1}v^2,
\tag{5}
$$

where $p,q$ are distinct primes, $p\nmid u$, $q\nmid v$, and the factorizations satisfy the original coprimality of the two endpoints.

The same Rédei calculation applies because the additional factors at the opposite endpoint are squares.

#### An infinite family of genuine false positives for the imprimitive count

The square contaminants in (5) cannot be dismissed as finitely many exceptions.

Consider the Pell-type equation

$$
7v^2-5u^2=2.
$$

It has the solution $u=v=1$, and the transformation

$$
(u,v)\longmapsto(6u+7v,\;5u+6v)
$$

preserves it. Its determinant is one.

Take a positive power of this transformation that is the identity modulo 35, and iterate that power. This produces infinitely many positive odd solutions with $u,v\equiv1\pmod{35}$.

Set

$$
m=5u^2+1=7v^2-1.
$$

Then $m\equiv6\pmod8$, and

$$
m^2-1=35(uv)^2.
$$

The squarefree core is 35, its class number is twice an odd integer by the Rédei criterion, and its conductor $uv$ is coprime to 35. Formula (3) therefore gives

$$
H(m^2-1)\equiv2\pmod4
$$

throughout this infinite family.

But both $m-1=5u^2$ and $m+1=7v^2$ are composite once $u,v>1$.

Thus nonvanishing modulo four of the unrestricted Hurwitz coefficient at $m^2-1$ does not prove twin-prime infinitude. This is an explicit infinite arithmetic obstruction, not a numerical experiment.

#### 3. A prime-center restriction eliminates even the remaining prime-power contaminants

The primitive three-square count is particularly useful. Let $r_3^{\rm prim}(D)$ count representations with coordinate gcd one. By Möbius inversion of Gauss's three-square identity,

$$
r_3^{\rm prim}(D)
=
\sum_{g^2\mid D}\mu(g)r_3(D/g^2)
=
24H^{\rm prim}(D).
$$

Thus

$$
r_3^{\rm prim}(m^2-1)\equiv48\pmod{96}
$$

detects the two odd prime powers in (4).

Among $m\le X$, the number of possible contaminants with at least one exponent $2a+1\ge3$ is $O(X^{1/3})$. A lower bound substantially larger than that would suffice, but a mere infinitude of nonzero coefficients would not.

There is a way to remove this counting problem entirely, at the cost of restricting the midpoint.

Take

$$
m=6\ell,
$$

where $\ell>7$ is prime and

$$
\ell\equiv1\pmod4,\qquad
\ell\equiv2\pmod5,\qquad
\ell\equiv2\pmod7.
\tag{6}
$$

These are compatible reduced classes, so Dirichlet's theorem supplies infinitely many such $\ell$.

Suppose $m-1=p^{2a+1}$ with $a\ge1$. Then

$$
6\ell=p^{2a+1}+1
=(p+1)(p^{2a}-p^{2a-1}+\cdots-p+1).
$$

Since $p\equiv5\pmod8$, the first factor is even and at least six. It must be one of $6,2\ell,6\ell$.

The first possibility gives $p=5$, excluded by (6). The other two leave a complementary factor of at most three, which is impossible when $a\ge1$.

Likewise, if $m+1=q^{2b+1}$ with $b\ge1$,

$$
6\ell=q^{2b+1}-1
=(q-1)(1+q+\cdots+q^{2b}).
$$

Now $q\equiv7\pmod8$. The possibility $q-1=6$ gives $q=7$, excluded by (6), and the other possibilities again leave too small a complementary factor.

Hence the following exact criterion holds on this restricted prime-center sequence:

$$
\boxed{
H^{\rm prim}(36\ell^2-1)\equiv2\pmod4
\iff
6\ell-1,\ 6\ell+1\text{ both prime}.
}
\tag{7}
$$

This needs no additional squarefree assumption.

It provides a particularly clean sufficient target for the automorphic route: prove the left side of (7) for infinitely many primes $\ell$ satisfying (6).

One must not instead take $m=2\ell$ with a large prime $\ell$. That tempting way to obtain a single prime-square trace index is locally obstructed: one of $2\ell-1,2\ell+1$ is divisible by three. The choice $m=6\ell$ is essential here.

This target is stronger than ordinary twin infinitude, since it additionally prescribes a prime factorization of the midpoint. Its usefulness is the exact removal of the conductor and power contaminants.

#### 4. The square-index trace does give a nonzero residue — but not at the required coordinate

I checked the actual statements in both suggested papers:

[Bringmann–Kane, arXiv:1305.0112, Theorem 1.4](https://arxiv.org/abs/1305.0112?utm_source=chatgpt.com): modularity of congruence-restricted Hurwitz sums, with explicit divisor corrections. Its generating series excludes indices divisible by the prime modulus. The simpler formulas in its final sections specialize to prime indices. 

arxiv.org

[Bringmann–Kane–Pujahari, arXiv:2109.07325, Theorem 1.1](https://arxiv.org/abs/2109.07325?utm_source=chatgpt.com): exact second-moment formulas modulo three, including composite indices divisible by three and the separate square-index terms. These formulas really do apply to $N=9\ell^2$. 

arxiv.org

The second paper therefore allows a concrete test at our contaminant-free midpoint sequence $m=6\ell$.

Define

$$
\mathcal H_{2,1,3}(N)
=
\sum_{\substack{|t|\le2\sqrt N\\t\equiv1\ (3)}}
t^2H(4N-t^2).
$$

Take $N=9\ell^2$, with $\ell>7$ prime. The divisors strictly below $\sqrt N=3\ell$ are

$$
1,\ 3,\ 9,\ \ell.
$$

Substitution into Theorem 1.1(2) gives, after combining its square-index correction with the divisor sums,

$$
\boxed{
\mathcal H_{2,1,3}(9\ell^2)
=
9\ell^2(9\ell^2+8\ell-1)-730-\ell^3.
}
\tag{8}
$$

For $\ell\equiv1\pmod4$, the first term vanishes modulo four, while the remaining terms give

$$
\boxed{
\mathcal H_{2,1,3}(9\ell^2)\equiv1\pmod4.
}
\tag{9}
$$

This is an exact nonzero congruence at infinitely many square indices, obtained from the actual published formula rather than from a conjectural average.

There are no exceptional Hurwitz denominators in this trace: when $t\equiv1\pmod3$,

$$
36\ell^2-t^2\equiv2\pmod3.
$$

It cannot be a square multiple of three or four. All the class numbers in (8) are therefore integers.

Even $t$ contribute zero modulo four because of the factor $t^2$. For odd $t$, that factor is one modulo four. Moreover, for each positive $t$ coprime to three, exactly one of $t,-t$ is one modulo three.

Consequently (9) implies the unweighted odd-trace congruence

$$
\boxed{
\sum_{\substack{0<t<6\ell\\t\ {\rm odd},\ 3\nmid t}}
H(36\ell^2-t^2)
\equiv1\pmod4.
}
\tag{10}
$$

This is a genuine automorphic result at the required square index.

The next task is to determine whether its nonvanishing survives when only the first trace is retained.

#### 5. An independent four-square calculation, including primitive representations

The congruence (10) admits a direct arithmetic check. More importantly, it allows us to test a primitive version of the same trace.

Write $m=2s$, where $s$ is odd, and let $\mathcal R(s)$ count ordered positive odd quadruples

$$
(t,x,y,z),\qquad t^2+x^2+y^2+z^2=4s^2.
$$

Jacobi's four-square theorem gives

$$
r_4(4s^2)=24\sigma(s^2).
$$

The all-even representations contribute $r_4(s^2)=8\sigma(s^2)$. There are no representations with exactly two odd coordinates, by reduction modulo four.

Dividing the remaining all-odd count by the 16 independent sign choices yields the exact identity

$$
\boxed{\mathcal R(s)=\sigma(s^2).}
\tag{11}
$$

For a fixed positive odd first coordinate $t$, Gauss's formula gives exactly $3H(4s^2-t^2)$ ordered positive triples. Hence

$$
3\sum_{\substack{0<t<2s\\t\ {\rm odd}}}
H(4s^2-t^2)=\sigma(s^2).
$$

Now set $s=3\ell$. Modulo three, an odd quadruple representing $36\ell^2$ has either zero or three coordinates not divisible by three.

The quadruples with all coordinates divisible by three contribute $\sigma(\ell^2)$. Among the others, permutation symmetry assigns precisely three quarters to quadruples whose first coordinate is coprime to three.

Therefore

$$
\begin{aligned}
3\sum_{\substack{0<t<6\ell\\t\ {\rm odd},\ 3\nmid t}}
H(36\ell^2-t^2)
&=\frac34\left[\sigma(9\ell^2)-\sigma(\ell^2)\right]\\
&=9(1+\ell+\ell^2).
\end{aligned}
\tag{12}
$$

For $\ell\equiv1\pmod4$, this independently confirms (10).

#### Removing the common four-coordinate gcd

Let $\mathcal R^{\rm prim}(s)$ count the same quadruples with gcd one. Since all coordinates are odd, their common divisor must divide $s$.

Möbius inversion gives

$$
\mathcal R^{\rm prim}(s)
=
\sum_{d\mid s}\mu(d)\sigma((s/d)^2).
$$

At $s=3\ell$,

$$
\boxed{
\mathcal R^{\rm prim}(3\ell)
=12\ell(\ell+1).
}
\tag{13}
$$

Every such quadruple has exactly three coordinates coprime to three.

For a fixed first coordinate $t$, denote the primitive-four-coordinate contribution by $F_m(t)$. Explicitly,

$$
F_m(t)=
3\sum_{d\mid(t,s)}
\mu(d)
H\left(\frac{m^2-t^2}{d^2}\right).
$$

The complete primitive trace is therefore

$$
\boxed{
\sum_{\substack{0<t<6\ell\\t\ {\rm odd},\ 3\nmid t}}
F_{6\ell}(t)
=
9\ell(\ell+1)
\equiv2\pmod4.
}
\tag{14}
$$

This achieves exactly the kind of residue-two congruence we were seeking, now in a primitive representation problem.

Unfortunately, primitivity of all four coordinates is not the same as primitivity of the remaining three.

At $t=1$, the common four-coordinate gcd is automatically one, so

$$
F_m(1)=3H(m^2-1),
$$

not $3H^{\rm prim}(m^2-1)$.

The primitive-three-coordinate quantity required by (7) is obtained by the different inversion

$$
3H^{\rm prim}(m^2-t^2)
=
3\sum_{g^2\mid m^2-t^2}
\mu(g)H\left(\frac{m^2-t^2}{g^2}\right).
$$

These extra divisors need not divide $t$ or $m$. Thus the four-square divisor formula does not automatically evaluate the trace with primitive three-square coefficients.

This is an important limitation of the quaternion/four-square mechanism: multiplicative control of the norm and the common gcd is not yet control of the marked coordinate.

#### 6. A decisive infinite-family test of the trace congruence

The nonzero residue in (14) might still be useful if every term other than $t=1$ were a multiple of four.

That assertion is false, even on the restricted prime-center sequence (6).

Impose the additional congruence

$$
\ell\equiv2\pmod{121}.
\tag{15}
$$

Together with (6), these are compatible reduced residue classes. There are infinitely many such primes $\ell$.

For every one of them,

$$
6\ell-1\equiv11\pmod{121}.
$$

Hence $11$ divides $m-1$ to exactly the first power. But $m-1\equiv5\pmod8$, whereas $11\equiv3\pmod8$. The squarefree kernel of $m-1$ must therefore have another prime factor.

The squarefree kernel of $m+1$ is nontrivial and coprime to that of $m-1$. The fundamental core of $m^2-1$ consequently has at least three distinct prime divisors.

By genus theory,

$$
H(m^2-1)\equiv
H^{\rm prim}(m^2-1)\equiv0\pmod4.
\tag{16}
$$

Nevertheless, the exact trace (14) continues to give residue two.

Subtracting its $t=1$ contribution proves

$$
\boxed{
\sum_{\substack{1<t<6\ell\\t\ {\rm odd},\ 3\nmid t}}
F_{6\ell}(t)
\equiv2\pmod4
}
\tag{17}
$$

for infinitely many actual prime centers with a composite endpoint.

This is a direct arithmetic disproof of the proposed term-isolation argument. All the required nonvanishing can reside in the other traces.

It does not say that primitive three-square coefficients at $t=1$ always vanish. It says that the exact nonzero primitive-four-square trace does not force them to be nonzero.

#### 7. Testing more restrictive congruence classes: every fixed-level filter still contains genuine contaminants

Perhaps the trace modulo three was simply too broad. I tested whether selecting $t\equiv1\pmod M$, with a suitably chosen fixed large $M$, could ensure that all other terms are divisible by four.

There is a general obstruction, even when the unwanted trace discriminant is fundamental and its three-square representations are primitive.

Fix any positive integer $M$, and put

$$
M_0=\operatorname{lcm}(8,M).
$$

Choose a prime $r\equiv3\pmod8$, coprime to $M_0$. Next choose a fixed prime $p\equiv5\pmod8$, with

$$
(p+2,M_0)=1,\qquad p\equiv1\pmod r,\qquad p\nmid M_0r.
$$

These conditions can be imposed by CRT and Dirichlet's theorem. At each odd prime dividing $M_0$, we need only avoid the two residue classes zero and minus two.

Now choose $q$ among the infinitely many primes satisfying

$$
\begin{aligned}
q&\equiv p+2\pmod{2M_0},\\
q&\equiv2\pmod p,\\
q&\equiv2-p+2r\pmod{r^2}.
\end{aligned}
$$

The moduli are coprime, and every prescribed prime-power residue is reduced. Dirichlet's theorem therefore applies.

Set

$$
m=\frac{p+q}{2},
\qquad
t=\frac{q-p}{2}.
$$

For sufficiently large $q$,

$$
t>1,\qquad t\equiv1\pmod{M_0},
\qquad m\equiv6\pmod8.
$$

The unwanted trace discriminant is

$$
m^2-t^2=pq.
$$

It is squarefree, and

$$
\left(\frac{-q}{p}\right)
=\left(\frac{-2}{p}\right)=-1.
$$

Consequently,

$$
\boxed{
H^{\rm prim}(m^2-t^2)
=H(m^2-t^2)
\equiv2\pmod4.
}
\tag{18}
$$

Meanwhile, our congruence modulo $r^2$ gives $r\parallel m-1$. Since $r\equiv3\pmod8$ and $m-1\equiv5\pmod8$, the squarefree core of $m^2-1$ has at least three prime factors. Thus

$$
\boxed{
H^{\rm prim}(m^2-1)
\equiv H(m^2-1)\equiv0\pmod4.
}
\tag{19}
$$

We have proved that for every fixed trace modulus $M$, infinitely many $m\equiv6\pmod8$ contain a genuine, nonzero primitive class-number coefficient at another trace $t\equiv1\pmod M$, while the desired coefficient vanishes.

This does not rule out a signed cancellation identity involving the entire congruence class. It does rule out termwise divisibility of the unwanted traces as a general justification for isolation.

It also defeats a fixed collection of polynomial-moment filters modulo four: taking $t\equiv1\pmod{M_0}$ ensures that all integral polynomial weights have the same residue as at $t=1$. Raising the fixed 2-adic precision simply requires including a larger fixed power of two in $M_0$.

#### 8. A genuinely isolated trace at a growing prime modulus

The previous obstruction leaves one natural repair: let the trace modulus grow with the midpoint so that the progression contains only the desired trace.

This can be implemented within the general Bringmann–Kane framework, with one endpoint already a genuine prime.

Take

$$
p\equiv5\pmod{24}
$$

prime, and put

$$
m=p+1,\qquad N=\frac{(p+1)^2}{4}.
$$

Then $m\equiv6\pmod8$ and $p\nmid N$.

The complete progression $t\equiv1\pmod p$ inside $[-m,m]$ consists of exactly

$$
t=1,\quad 2-m,\quad m.
$$

Their three discriminants are respectively

$$
m^2-1,\qquad4p,\qquad0.
$$

Thus the exact restricted trace is

$$
\boxed{
H_{1,p}(N)
=
H(p(p+2))+H(4p)-\frac1{12}.
}
\tag{20}
$$

The two extra terms are controlled. In fact, $H(4p)=h(-4p)$, and the prime discriminants $-4,p$ give

$$
h(-4p)\equiv2\pmod4
$$

because $(p/2)=-1$.

Equation (20) therefore genuinely isolates the desired Hurwitz coefficient modulo four, apart from an explicit known correction.

This is an improvement over fixed-level averaging: there is no longer an unidentified sum of other nonzero traces.

But the modular-form evaluation becomes the new obstacle.

Bringmann–Kane's Theorem 1.4 applies to each such prime modulus $p$, since $p\nmid N$. It expresses the trace, after its explicit divisor-series correction, as a coefficient of a holomorphic weight-two modular form on

$$
\Gamma_0(p^2)\cap\Gamma_1(p).
$$

Their explicit formulas for fixed moduli $3,5,7$ do not give the coefficient at

$$
N=(p+1)^2/4
$$

for this growing family of levels.

Their Lemma 4.1 requires agreement through $p(p^2-1)/6$ coefficients when identifying a candidate form at this level. That verification mechanism is not a uniform evaluation of the desired coefficient, which occurs at an index of order $p^2$. 

arxiv.org

Thus (20) is a successful exact trace isolation but not a proof of its required residue. In addition, for this one-prime-endpoint sequence, the primitive or squarefree correction remains necessary.

For the contaminant-free sequence $m=6\ell$, choosing a trace modulus exceeding $m+1$ similarly isolates $t=1$. But that again introduces an unbounded modular level. Choosing the prime modulus $\ell$ itself has the additional difficulty that $\ell\mid N=9\ell^2$, outside the coprime-index projection in Bringmann–Kane's Theorem 1.4.

I found no stated result in either paper providing the needed uniform growing-level congruence.

#### 9. Can a Hecke action propagate the isolated coefficient?

There are two different Hecke mechanisms, and neither automatically closes the gap.

#### Half-integral-weight Hecke operators on the three-square series

The operators $T(a^2)$, for primes $a$ away from the level, act on coefficients through indices

$$
D/a^2,\quad D,\quad a^2D.
$$

This is the standard half-integral-weight coefficient action. 

numdam.org

It is well suited to conductor changes because it preserves the squarefree kernel of the index.

But the target sequence is

$$
D=m^2-1.
$$

Multiplying the midpoint by $a$ gives

$$
(am)^2-1
=a^2(m^2-1)+(a^2-1),
$$

not $a^2D$.

So the Hecke relation propagates within a fixed quadratic square class, whereas the required operation must move between the distinct squarefree kernels of consecutive endpoint products.

In fact, a pure square-class propagation can remain forever in the Pell-type false-positive family of Section 2. Such propagation is not an appropriate certificate of ordinary primality.

#### Integral-weight Hecke operators on the square-index trace

After introducing the auxiliary theta series, the corrected trace becomes an integral-weight modular form. Its Hecke operators can control coefficients at prime squares and other multiplicatively structured indices.

But its coefficient is the whole trace.

The exact congruences (9) and (14) show this explicitly: the square-index arithmetic is strong enough to force nonzero aggregate residues, even while the desired marked coefficient vanishes.

For a growing trace modulus, the modular form itself changes with the midpoint. A Hecke recurrence for one fixed form cannot simply be transferred to that changing family.

I also tested the geometric version of this idea. An integral linear isometry of

$$
m^2-x^2-y^2-z^2=1
$$

can propagate individual three-square representations to new midpoints. However, for one fixed linear isometry to take an entire height slice $m=M$ to another fixed height slice independently of the spatial coordinates, its first row must have zero spatial components. The isometry condition then forces its time component to be $1$ or $-1$.

Thus a nontrivial fixed isometry does not produce a uniform bijection between representation counts at increasing midpoints. Generating infinitely many individual representations is easy here; preserving the residue of their total primitive count is the unresolved part.

#### Final assessment

The class-number approach has produced a valid new sufficient criterion with all conductor and prime-power contaminants eliminated:

$$
\boxed{
\begin{gathered}
\ell\text{ prime},\quad
\ell\equiv1\pmod4,\quad
\ell\equiv2\pmod{35},\\
r_3^{\rm prim}(36\ell^2-1)\equiv48\pmod{96}
\\[1mm]
\Longleftrightarrow
6\ell-1,\ 6\ell+1\text{ both prime}.
\end{gathered}}
$$

The two residue conditions modulo five and seven have simply been combined into $\ell\equiv2\pmod{35}$.

The substantive results and limitations are:

Calculation
 | 
Outcome
 | 

Fundamental class-number detector
 | 
Exact
 | 

Primitive conductor correction
 | 
Detects two odd prime powers
 | 

Restricted prime-center sequence
 | 
Removes all remaining power contaminants
 | 

Published second moment at $N=9\ell^2$
 | 
Nonzero residue modulo four
 | 

Independent primitive four-square trace
 | 
Exact residue-two congruence
 | 

Isolation by fixed trace congruences
 | 
Fails on explicit infinite arithmetic families
 | 

Isolation by a growing prime modulus
 | 
Exact, but the required modular coefficient is unevaluated
 | 

Hecke propagation of the isolated coefficient
 | 
No valid transfer established
 | 

I have not proved infinitely many nonzero primitive $t=1$ coefficients. The strongest automorphic calculation reached here forces the required residue in a complete trace, and the infinite family (15)–(17) proves that this residue can be carried entirely by unwanted traces.

The exact remaining research obligation is a nonvanishing theorem for the isolated primitive coefficient at $36\ell^2-1$, not another nonvanishing theorem for its aggregate Hurwitz trace.

All genus, conductor, Pell, primitive representation, and congruence arguments above are unconditional. I inspected the two requested primary texts and the relevant three-square and genus-theory sources. The Bringmann–Kane–Pujahari theorem page was also checked visually; the Bringmann–Kane page-image requests failed, but its mathematical text was accessible. The prime-center restriction, infinite false-positive families and primitive trace calculation are my own derivations.

No sample computation, private-context retrieval, files or manuscript creation was used.

### 2. Root orbits and finite divisor cutoffs

I obtained an exact reciprocal pairing of the aggregated roots, including the squarefree correction. It cancels the complete arithmetic periods and leaves an explicit finite boundary-parity sum.

There is also a rigorous obstruction to one natural way of exploiting that pairing: for any prescribed finite collection of the paired divisor rows, infinitely many disjoint intervals have odd truncated parity but contain no twin primes at all. The omitted rows must supply an odd correction. This holds on actual integers, not on a comparison model.

I have not obtained an independent determination of the complete boundary parity that forces a twin.

#### 1. Quotient the four known roots before counting modulo two

Let $m=n+1\ge4$ be even and put

$$
N=m^2-1=(m-1)(m+1).
$$

The two odd factors $m-1,m+1$ are coprime.

On the roots of

$$
u^2\equiv1\pmod N
$$

act the four maps

$$
u\longmapsto u,\quad -u,\quad mu,\quad -mu.
$$

They form a group of order four, acting freely: every root $u$ is invertible modulo $N$, and neither $m$ nor $-m$ is congruent to $1$ modulo $N$.

Let $C(m)$ be the number of orbits. Then

$$
C(m)=2^{\omega(m-1)+\omega(m+1)-2}.
$$

The orbit of $1$ consists exactly of the four always known roots.

Consequently,

$$
\boxed{
1_{\{m-1,\ m+1\ {\rm prime}\}}
\equiv
\mu^2(m-1)\mu^2(m+1)C(m)\pmod2.
}
\tag{1}
$$

This is your congruence with its factor four removed. The squarefree factor is essential; no prime-power exception is being discarded.

#### A useful alternative description of the quotient

A root modulo an odd integer $v$ specifies a unitary factorization $v=ab$, by assigning each complete prime-power factor of $v$ either to $u-1$ or to $u+1$.

Negation exchanges these two assignments.

Multiplication by $m$ independently exchanges the assignments on $m+1$, because

$$
m\equiv1\pmod{m-1},
\qquad
m\equiv-1\pmod{m+1}.
$$

Thus the orbit space is exactly the set of pairs of unordered unitary factorizations of the two endpoints.

When the endpoints are squarefree, these are simply the ordinary unordered divisor pairs. This description will permit the reciprocal summation without needing to enumerate modular roots.

#### 2. Exchange the root summation using the Pell-type equation

Represent a root by its centered integer value $u$, and let $v$ be the centered representative of $mu\bmod N$. Thus

$$
|u|,|v|\le\frac{N-1}{2}.
$$

Because $m^2\equiv1\pmod N$, the integers

$$
x=\frac{mu-v}{N},\qquad
y=\frac{mv-u}{N}
$$

are well-defined. Solving these equations gives

$$
\boxed{u=mx+y,\qquad v=x+my.}
\tag{2}
$$

This is an exact lattice parametrization of the root action.

Multiplication by $m$ exchanges $x,y$; negation changes both their signs. Moreover,

$$
u^2-v^2=N(x^2-y^2).
$$

The equality $|x|=|y|$ is impossible for a root: it would make $u$ divisible by $m-1$ or $m+1$.

Consequently, every orbit has a unique representative satisfying

$$
0\le x<|y|\le m/2,
$$

with $y>0$ when $x=0$, and the original centered-residue bounds retained.

The root condition becomes

$$
x^2+y^2+2mxy-1=\ell(m^2-1)
\tag{3}
$$

for an integer $\ell$.

The two corresponding Pell parameters are

$$
k=\frac{u^2-1}{m^2-1}=x^2+\ell,
$$

$$
k'=\frac{v^2-1}{m^2-1}=y^2+\ell.
\tag{4}
$$

Thus $k<k'$ for the chosen orbit representative.

The always-known orbit is exactly $x=0,y=1$. All other orbits have $x>0$.

#### The square Pell parameters can be eliminated completely

For a positive centered root, suppose

$$
u^2-1=k(m^2-1).
$$

If $k=0$, then $u=1$. If $k=1$, then $u=m$.

Suppose instead that $k=t^2$, $t\ge2$. Then

$$
(tm-u)(tm+u)=t^2-1.
$$

Both factors are positive integers. But the centered-root bound implies $t<m/2$, so

$$
tm+u>tm>2t^2,
$$

which is impossible.

Therefore:

$$
\boxed{\text{Every nontrivial centered root has nonsquare }k.}
\tag{5}
$$

The exchange of summation consequently reduces the additional roots to generalized Pell equations

$$
u^2-km^2=1-k,\qquad k>1\text{ nonsquare}.
$$

This is a useful exact simplification, but the remaining Pell families do not admit the required parity pairing.

#### 3. Test the natural Pell and Vieta switches

#### Pell translation does not preserve the prime-power correction

If $a^2-kb^2=1$, the ordinary Pell translation is

$$
(u,m)\longmapsto(au+kbm,\;bu+am).
$$

It preserves the equation and, with suitable parity of $a,b$, preserves even $m$.

It does not preserve squarefreeness of $m-1,m+1$.

Here is an exact counterexample to that proposed involution mechanism, rather than a numerical count of prime pairs.

Take

$$
k=21,\qquad (u,m)=(64,14).
$$

We have

$$
64^2-1=21(14^2-1),
$$

and the two endpoints $13,15$ are squarefree.

The Pell unit $55+12\sqrt{21}$ has norm one. Its translation gives

$$
(u',m')=(7048,1538).
$$

Both roots remain in their centered ranges and are the smaller representatives under the four-root action. But

$$
m'+1=1539=3^4\cdot19.
$$

The squarefree filter has changed from one to zero.

Thus pairing adjacent points of a Pell orbit is not a valid cancellation on the filtered root population.

There is a second problem: by (4), the two root representatives belonging to the same four-element orbit generally have different Pell parameters. An independent parity computation on each fixed-$k$ family would not automatically respect the original orbit quotient.

#### Vieta switching in $m$ is not integral

Equation (3), viewed as a quadratic in $m$, suggests the second root

$$
m'=\frac{2xy}{\ell}-m.
$$

This could provide a descent if it were always an admissible even integer.

It is not.

Take the exact lattice state

$$
m=92,\qquad x=17,\qquad y=-44,\qquad \ell=-16.
$$

Then

$$
u=1520,\qquad v=-4031,
$$

and both are roots modulo $92^2-1=8463$. In particular,

$$
1520^2-1=273\cdot8463.
$$

Both original endpoints are squarefree:

$$
91=7\cdot13,\qquad93=3\cdot31.
$$

Nevertheless, the proposed second root is

$$
m'=\frac{-1496}{-16}-92=\frac32.
$$

So the natural Vieta switch is not an integer-valued involution, even on a legitimate squarefree orbit.

These two failures exclude the straightforward Pell translation and Vieta descent. They do not exclude every conceivable pairing of the Pell solutions.

#### 4. A complete reciprocal boundary identity, with exact squarefree inversion

The divisor description from §1 leads to a more promising exchange because it handles the squarefree correction exactly.

Write $m=2j$, and choose integers $2\le U\le V$. Let

$$
\mathcal T(U,V)=
\#\{U\le j\le V:2j-1,\ 2j+1\text{ both prime}\}.
$$

For squarefree endpoints, selecting the smaller factor in each unordered divisor pair gives

$$
\begin{aligned}
\mathcal T(U,V)\equiv
\sum_{j=U}^V&
\mu^2(2j-1)\mu^2(2j+1)\\
&\times
\sum_{\substack{a\mid2j-1\\a^2<2j}}1
\sum_{\substack{c\mid2j+1\\c^2<2j}}1
\pmod2.
\end{aligned}
\tag{6}
$$

The common bound $a^2,c^2<2j$ is valid: the only potential endpoint discrepancies are squares, already killed by the squarefree factors.

Now use the exact inversion

$$
\mu^2(N)=\sum_{e^2\mid N}\mu(e).
$$

Modulo two, this is a sum over squarefree $e$, with coefficient one.

For each choice of odd $a,c$ and odd squarefree $e,f$, set

$$
A=[a,e^2],\qquad C=[c,f^2].
$$

The associated row of (6) requires

$$
A\mid2j-1,\qquad C\mid2j+1.
$$

It is empty unless $(A,C)=1$. Otherwise, writing $P=AC$, its congruence condition is

$$
j\equiv r\pmod P,
$$

where

$$
2r\equiv1\pmod A,\qquad
2r\equiv-1\pmod C.
\tag{7}
$$

Its lower interval endpoint is exactly

$$
K=\max\left(
U,\frac{\max(a^2,c^2)+1}{2}
\right).
$$

All these sums are finite, because $a,c,e,f\le\sqrt{2V+1}$.

#### Pair the reciprocal rows

Exchange the two endpoint tuples:

$$
(a,e)\longleftrightarrow(c,f).
$$

The modulus $P$ and lower endpoint $K$ remain unchanged. The residue changes from $r$ to $-r\bmod P$.

The only fixed row is

$$
a=c=e=f=1,
$$

because any other identical endpoint tuples would give $A=C>1$, contradicting coprimality.

For a nontrivial row, define the binary boundary function

$$
B_P(t;r)=
1_{\{
\min(r,P-r)\le t\bmod P<\max(r,P-r)
\}},
$$

using $1\le r<P$.

Every complete period contains one occurrence of each of the two reciprocal residues, and therefore contributes zero modulo two.

The combined parity of the two rows on $[K,V]$ is exactly

$$
B_P(V;r)+B_P(K-1;r)\pmod2.
$$

We obtain the full identity

$$
\boxed{
\begin{aligned}
\mathcal T(U,V)\equiv{}&
V-U+1\\
&+\sum_{\substack{
\text{nontrivial unordered row pairs}\\
(A,C)=1,\ K\le V}}
\bigl[B_P(V;r)+B_P(K-1;r)\bigr]
\pmod2.
\end{aligned}
}
\tag{8}
$$

This is an exact reciprocal cancellation of the aggregated root count. It retains every square-divisor correction, every moving lower boundary, and both orientations.

No additive-divisor asymptotic has been used.

#### 5. Resolve every one-sided boundary term

Equation (8) can be simplified further. In particular, the rows with one trivial endpoint can be evaluated completely.

First, consider the special square-divisor rows

$$
a=c=f=1,\qquad e>1.
$$

Here $P=e^2$, and the two reciprocal residues are

$$
\frac{P-1}{2},\qquad\frac{P+1}{2}.
$$

Therefore

$$
B_P(t;r)=1_{\{e^2\mid2t+1\}}.
$$

Summing these rows over squarefree $e>1$, their combined boundary parity is precisely

$$
\mu^2(2V+1)+\mu^2(2U-1)\pmod2.
$$

Thus these potentially troublesome square corrections have an exact evaluation. They vanish, for example, when the outer endpoints have the same squarefree status.

#### Complete evaluation of all one-sided rows

Define $P(n)=1_{\{n\text{ prime}\}}$ for odd $n>1$.

The sum of the expanded single-endpoint divisor rows is, by the same exact squarefree inversion,

$$
P(n)\pmod2.
$$

The trivial row contributes one. Thus the combined nontrivial rows on one endpoint contribute $P(n)+1$.

Summing the two possible one-sided terms over the interval gives

$$
\begin{aligned}
&\sum_{j=U}^V
\bigl[P(2j-1)+1+P(2j+1)+1\bigr]\\
&\qquad\equiv P(2U-1)+P(2V+1)\pmod2.
\end{aligned}
$$

Every interior primality indicator occurs twice and cancels.

Let $\mathcal M(U,V)$ denote the boundary sum in (8) restricted to the genuinely mixed rows $A,C>1$.

The complete identity consequently reduces to

$$
\boxed{
\mathcal T(U,V)\equiv
V-U+1+P(2U-1)+P(2V+1)+\mathcal M(U,V)
\pmod2.
}
\tag{9}
$$

This has paid the entire one-sided part, not just a selected family of favorable terms.

For instance, if the two outer endpoints are independently known to be composite and the interval length is odd, it suffices to prove

$$
\mathcal M(U,V)\equiv0\pmod2.
\tag{10}
$$

That would give an odd number of genuine twin pairs.

The next test is whether the reciprocal pairing can force (10).

#### 6. An exact obstruction to closing the mixed rows by complete periods

It is tempting to choose the interval length to be a common multiple of the row moduli. The paired counts would then cancel, leaving the odd contribution of the trivial row.

There is a rigorous reason why that approach cannot be completed using a fixed finite cutoff.

#### Finite-row cancellation theorem

Fix any $R\ge1$, and retain all the rows with

$$
a,c,e,f\le R.
$$

Define the odd integer

$$
L_R=\operatorname{lcm}\{j^2:1\le j\le R,\ j\text{ odd}\}.
$$

For every compatible retained row,

$$
P=[a,e^2][c,f^2]\mid L_R,
$$

because the two bracketed factors are coprime.

Choose an interval $[U,V]$ satisfying

$$
V-U+1=L_R,\qquad U>R^2.
$$

The lower divisor boundaries are now inactive.

Every nontrivial reciprocal row pair contributes exactly

$$
2L_R/P
$$

occurrences, which is even.

Hence the complete truncated expression has parity

$$
\boxed{\mathcal T_R(U,V)\equiv1\pmod2.}
\tag{11}
$$

This is a genuine exact cancellation. It is independent of the position of the interval once its lower endpoint is large enough.

#### Construct arbitrarily high intervals on which the full parity is zero

Choose distinct odd primes $p_0,\ldots,p_{L_R}$, none dividing $L_R$.

By CRT, there are arbitrarily large integers $U$ satisfying

$$
2(U+i)-1\equiv0\pmod{p_i},
\qquad 0\le i\le L_R.
$$

We can additionally prescribe $U$ in any desired residue class modulo $L_R$.

Choose $U$ so large that all the covered integers exceed their assigned prime divisors. Then every integer

$$
2U-1,\ 2U+1,\ldots,2(U+L_R)-1
$$

is composite.

Thus the actual twin count in the interval of $L_R$ successive centers is exactly zero.

Combining this with (11),

$$
\boxed{
\mathcal T(U,V)-\mathcal T_R(U,V)\equiv1\pmod2.
}
\tag{12}
$$

The omitted rows provide an odd correction.

Since both outer endpoints are composite, the fully evaluated one-sided contribution in (9) vanishes. The complete mixed correction has parity one, even though the truncated mixed correction has parity zero.

This proves the following obstruction:

For every finite row cutoff, there are arbitrarily high, pairwise disjoint intervals of odd length on which the complete-period pairing gives the wrong parity unless the omitted arithmetic rows are included.

We may let $R$ increase between successive CRT constructions. Thus the obstruction persists on intervals whose lengths and retained cutoffs both tend to infinity.

If desired, assign two distinct large prime divisors to every covered integer. Then the entire interval contains no pair of prime powers either. The obstruction is not caused merely by the squarefree correction.

This is an exact construction on actual integers, not a model of possible prime behavior.

#### 7. Can we close all row periods by a suitable variable endpoint?

For an interval ending at $V$, the full reciprocal formula contains rows as large as the square-divisor conditions permit.

Even the simple family

$$
a=c=f=1,\qquad e=p\le\sqrt{2V+1}
$$

requires moduli $p^2$.

Consequently, a common period for all relevant rows would be divisible by

$$
\prod_{\substack{p\le\sqrt{2V+1}\\p>2}}p^2.
$$

This exceeds $V$ for every sufficiently large $V$. For example, Chebyshev's elementary lower bound gives a logarithm of order at least $\sqrt V$.

Thus one cannot choose a positive interval of length at most $V$ that is a full common period for every row in the exact inversion.

This does not mean that each row requires a complete period to cancel. Its boundary indicators could cancel for other reasons.

But (12) proves that such additional cancellation cannot be inferred merely by completing increasingly many of the small periods. The remaining mixed boundary sum contains essential arithmetic information.

#### 8. A separate modular-generating-function test

I also tested whether characteristic-two generating identities could determine the missing parity without evaluating the mixed CRT boundaries.

Over $\mathbb F_2$, put

$$
F_{U,V}(z)=
\sum_{j=U}^{V+1}P(2j-1)z^{j-U}.
$$

The exact twin parity is

$$
\boxed{
\mathcal T(U,V)\equiv
[z^1]\bigl(F_{U,V}(z)F_{U,V}(z^{-1})\bigr).
}
\tag{13}
$$

This is the coefficient of the ordered adjacent-pair correlation.

The characteristic-two identity

$$
F(z)^2=F(z^2)
$$

does not evaluate (13). It cancels off-diagonal terms in the ordinary square, whereas the reciprocal product keeps the two directions as different Laurent coefficients.

In particular,

$$
[z^h]\bigl(F(z)F(z^{-1})\bigr)
=
[z^{-h}]\bigl(F(z)F(z^{-1})\bigr).
$$

Evaluating at $z=1$ therefore cancels every nonzero-gap pair and retains only the diagonal prime-count parity.

More generally, reducing modulo $z^M-1$ combines all the Laurent coefficients with exponents congruent modulo $M$. The coefficient for the desired gap then includes all its competing gaps modulo $M$.

Taking $M$ larger than the complete exponent range avoids that aliasing, but requires the original prime polynomial rather than a simpler periodic aggregate.

So the ordinary Frobenius and reciprocal-polynomial identities do not give an independent value of the coefficient in (13). They encounter precisely the same missing adjacent-prime information.

#### Check a related multiplicative pairing

Aebi and Cairns's original paper [A property of twin primes](https://math.colgate.edu/~integers/m7/m7.pdf?utm_source=chatgpt.com) gives another exact root-inversion argument, using the product of invertible quadratic residues modulo $n(n+2)$.

Their Theorem 2 characterizes when this product equals the particular root associated with twins. The characterization still allows one endpoint to be a prime power and the other to have several prime divisors congruent to $3\pmod4$. 

math.colgate.edu

Thus that product pairing does not independently select two ordinary primes either. Even eliminating its prime-power cases would leave the extra composite factorizations on the other endpoint.

#### 9. The precise remaining parity problem

The strongest surviving exact reduction is (9).

For an odd-length interval whose outer endpoints are known to be composite,

$$
\boxed{
\mathcal T(U,V)\equiv1+\mathcal M(U,V)\pmod2.
}
$$

The remaining quantity is explicitly

$$
\mathcal M(U,V)=
\sum_{\substack{
\text{unordered compatible mixed rows}\\
A,C>1,\ K\le V}}
\left[B_{AC}(V;r)+B_{AC}(K-1;r)\right]
\pmod2,
$$

where $r$ is determined by (7), including all square-divisor corrections.

A sufficient advance would be to prove that this quantity is even on arbitrarily high, disjoint odd-length intervals with composite outer endpoints, by an argument not depending on the existence of another twin.

The CRT construction above proves that no such conclusion follows from merely canceling every fixed finite collection of reciprocal rows.

#### Research conclusion

The investigation establishes:

Mechanism
 | 
Result
 | 

Four-root orbit quotient
 | 
Exact, including the genuine-prime filter
 | 

Exchange into Pell equations
 | 
Square $k$ completely removed except for the known roots
 | 

Pell translation and Vieta descent
 | 
Fail to preserve the filtered integer orbit space
 | 

Reciprocal divisor pairing
 | 
Complete exact boundary identity (8)
 | 

All one-sided and corresponding squarefree corrections
 | 
Fully evaluated in (9)
 | 

Finite-period cancellation
 | 
Rigorous obstruction on actual composite intervals
 | 

Independent vanishing of the complete mixed boundary
 | 
Not established
 | 

The most useful result is the combination of (9) and (12). It isolates the essential mixed arithmetic parity and proves that it can compensate the entire favorable trivial-row contribution, even after arbitrarily extensive finite congruence cancellation.

I have not found an involution or an independently evaluable generating identity that controls this complete mixed term on intervals forcing positive twin mass.

The calculations are exact; no proper prime powers were discarded by density, and no smooth divisor asymptotic was interpreted as a congruence. The explicit Pell and Vieta states are counterexamples to the proposed transformations, not numerical evidence about twin-prime abundance.

I chose the lattice parametrization, reciprocal boundary pairing and CRT obstruction independently. No earlier private-context search was performed, and no files or manuscript were created.

The ordinary twin-prime conjecture remains unresolved by this argument. The finite-period repair is ruled out, while a genuinely new cancellation across the complete mixed divisor rows remains a possible—but unproved—route.
