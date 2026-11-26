# Twin Prime

All thirteen working papers are available here as PDFs with editable LaTeX. The [research archive](history/twin-prime-research-history-2026-11-25.tar.xz) and [original chat records](history/hosted-research-responses-2026-11-25.md) are preserved in this repository. A [source supplement](history/hosted-proofs-supplement.md) preserves two later mathematical replies on primitive three-square counts and the parity of divisor cutoffs, together with their verification status.

## Featured manuscript — Large prime divisors of Fermat congruences and semiprime pseudoprimes

How many composite numbers built from exactly two primes can pass the base-2 Fermat test? Write $Q_2(X)$ for their count up to $X$, including squares. The manuscript proves

$$Q_2(X)\ll \frac{X^{3/4}}{(\log X)^{5/4}}.$$

For the same count with unrestricted factor sizes, Theorem 3.1 of Luca, Ralaivaosaona and Jiménez Urroz gives $O(X^{4/5}/(\log X)^{2/5})$. The improvement comes from counting possible prime factors separately at each small value of $\gcd(r-1,s-1)$ and retaining both primality conditions for large values. [Published comparison (2025)](https://doi.org/10.1007/s13370-025-01338-1) · [Read the paper](fermat-divisors.pdf) · [Editable proof](fermat-divisors.tex)

This bound controls false positives. Proving that sufficiently many candidates pass the test remains open. The Twin Prime Conjecture is unresolved in this work. The comparison above concerns the cited theorem. Literature priority and independent specialist review remain open.

## A model for prime-tuple counts

For every fixed pattern without a pair two apart, one set can reproduce the predicted Hardy–Littlewood counts in every fixed progression and still contain no pair two apart. The construction identifies which pattern information is insufficient to force twins. [PDF](prime-tuple-model.pdf) · [LaTeX](prime-tuple-model.tex)

## Supporting sieve notes

- **A long-divisor sign classification on three-prime products and an upper sieve for their shift by two.** Bounds a contribution where the neighboring integer satisfies specified factorization conditions. [PDF](shift-two-sieve.pdf) · [LaTeX](shift-two-sieve.tex)
- **The signed contribution of two- and three-prime products to a truncated von Mangoldt convolution.** Computes the signed mean before restrictions on the neighboring integer are applied. [PDF](truncated-divisor-weights.pdf) · [LaTeX](truncated-divisor-weights.tex)

- **Fractional moments for a shifted-prime divisor weight.** For orders tending to one, the normalized absolute composite errors tend to $1-e^{-c}$ and $e^c-1$. The note also treats a signed subsequential limit and fixed factor counts. [PDF](fractional-moments.pdf) · [LaTeX](fractional-moments.tex)
- **Liouville signs on short differences.** Proves a conditional-on-a-dense-subset implication and gives short-window constructions showing where it fails, including a pair of squarefree composite neighbors. [PDF](short-differences.pdf) · [LaTeX](short-differences.tex)
- **Prime-factor shapes and Liouville signs on two rough neighbors.** Adapts the Tao–Teräväinen correlation argument to two rough neighbors and gives independent finite shape tests and Liouville signs outside an exceptional set of scales. [PDF](rough-neighbor-shapes.pdf) · [LaTeX](rough-neighbor-shapes.tex)

- **A folded divisor correlation and the weighted twin count.** The November 14 calculation now gives the weighted squarefree Titchmarsh formula, its range from Fiorilli’s theorem and the explicit twin-prime-constant term before composite cancellation. [PDF](folded-divisor-correlation.pdf) · [LaTeX](folded-divisor-correlation.tex)
- **A uniform negative bound for a two-form semiprime sieve score.** [PDF](two-form-semiprime-score.pdf) · [LaTeX](two-form-semiprime-score.tex)
- **Two-site fractional divisor moments outside exceptional scales.** [PDF](two-site-fractional-moments.pdf) · [LaTeX](two-site-fractional-moments.tex)
- **One- and two-site laws for the last marked prime factor.** [PDF](last-prime-factor.pdf) · [LaTeX](last-prime-factor.tex)
- **Paired Jacobsthal cleanup and a conditional divergence statement.** [PDF](paired-jacobsthal.pdf) · [LaTeX](paired-jacobsthal.tex)

- **Class-number criteria and Pell–Hurwitz false positives.** Includes the ramified-conductor case and a fixed-midpoint auxiliary-prime density. [PDF](class-number-criteria.pdf) · [LaTeX](class-number-criteria.tex)

[admin@cosmosgeek.org](mailto:admin@cosmosgeek.org) · [b321014@iiit-bh.ac.in](mailto:b321014@iiit-bh.ac.in)

The research and drafting involved ChatGPT and Codex. The coordinator is identified for correspondence. These manuscripts are public research drafts.
