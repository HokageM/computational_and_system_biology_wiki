---
title: E11 — Population Genetics and Multiple Testing
type: exercise
module: 1
tags: [exercise, hardy-weinberg, wright-fisher, phasing, benjamini-hochberg, fdr]
sources: [raw/module1/gsb_3.pdf]
created: 2026-10-21
updated: 2026-10-22
status: solid
---

# E11 — Population Genetics and Multiple Testing

## Task

1. **Sex-specific allele frequencies.** A population starts with two different genotype
   distributions for males and females; the Hardy–Weinberg assumptions otherwise hold.
   a) How many generations until the allele frequencies are equal for male and female?
   b) How many generations until Hardy–Weinberg equilibrium is reached?
2. **Hardy–Weinberg for more than two alleles** `A₁, A₂, A₃`.
   a) List the genotypes. b) Give their equilibrium frequencies.
3. **Wright–Fisher model.** a) How many `A₁` and `A₂` in the 5th generation?
   b) In the 6th? c) What is the probability of that change? d) And of a change from 7
   to 8 copies?
4. **Haplotype phasing.** a) Enumerate the phasings of a given genotype.
   b) Phase a child's genotype against the parents' genotypes.
5. **Benjamini–Hochberg correction** for `α = 0.05` and `M = 10` p-values.

## Approach

Items 1–2 are [[hardy-weinberg-equilibrium]] bookkeeping with a Punnett square — the
[[population-genetics]] arithmetic of the lecture; item 3
uses the binomial transition probability of the [[wright-fisher-model]]; item 4 applies
[[haplotype-phasing]]; item 5 is the step-by-step procedure of
[[multiple-testing-correction]].

## Solution

**1a)** **One generation.** Each offspring receives one gamete from a male and one from a
female, so after a single round of random mating both sexes carry the same allele pool.

**1b)** **Two generations.** HWE requires equal allele frequencies in both sexes
*first* (one generation), and then one further round of random mating to produce the
`p², 2pq, q²` genotype distribution — equal "+1".

In the absence of selection, mutation, genetic drift or other forces, the allele
frequencies `p` and `q` are then **constant between generations**.

**2a)** With three alleles there are **6 genotypes**:

```text
A1A1   A2A2   A3A3        // homozygous
A1A2   A1A3   A2A3        // heterozygous
```

**2b)** Punnett square with allele frequencies `p`, `q`, `r`:

| | `A₁` (p) | `A₂` (q) | `A₃` (r) |
|---|---|---|---|
| **`A₁` (p)** | p² | pq | pr |
| **`A₂` (q)** | pq | q² | qr |
| **`A₃` (r)** | pr | qr | r² |

```text
A1A1 = p²     A1A2 = 2pq     A1A3 = 2pr
A2A2 = q²     A2A3 = 2qr     A3A3 = r²
```

The off-diagonal cells appear twice, hence the factor 2; the six frequencies sum to
`(p + q + r)² = 1`.

**3a)** 5th generation: `#A₁ = 8`, `#A₂ = 2` (a population of `N = 5` diploids,
`2N = 10` alleles).

**3b)** 6th generation: `#A₁ = 8`, `#A₂ = 2` — unchanged.

**3c)** The transition probability is the binomial point probability with `p = 8/10`:

```text
P(8 → 8) = C(10, 8) · (8/10)^8 · (1 - 8/10)^(10-8)
         = 45 · 0.8^8 · 0.2^2 ≈ 0.302
```

**3d)** From 7 copies, `p = 7/10`:

```text
P(7 → 7) = C(10, 7) · (7/10)^7 · (1 - 7/10)^(10-7)
         = 120 · 0.7^7 · 0.3^3 ≈ 0.267
```

Even the "no change" outcome has a probability of only about 30 % — the population is
small, so [[genetic-drift]] is strong.

**4a)** Genotype `A`, `{T,G}`, `{C,A}`, `C`, `G`, `{C,A}`: three heterozygous positions,
so `2³ = 8` labelled phasings, listed as chromosome pairs:

```text
T C C | T C A | T A C | T A A | G C C | G C A | G A C | G A A
G A A | G A C | G C A | G C C | T A A | T A C | T C A | T C C
```

The last four are the first four with the two chromosomes swapped, so there are four
distinct unordered chromosome pairs.

**4b)** Trio phasing:

```text
father: (C,A) (G,G) (C,T) (G,G)
mother: (A,A) (G,A) (T,T) (G,G)
child:  (A,C) (A,G) (T,C) (G,G)
```

At each locus, ask which parent *could* have supplied each allele
(*von wem kam das Allel*): the mother is `A/A` at locus 1 and `T/T` at locus 3, the
father is `G/G` at locus 2. This fixes every heterozygous site:

```text
paternal haplotype: C G C G
maternal haplotype: A A T G
```

**5)** `α = 0.05`, `M = 10`:

| k | p_k | (k/M)·α | significant |
|---|---|---|---|
| 1 | 0.001 | 0.005 | yes |
| 2 | 0.009 | 0.010 | yes |
| 3 | 0.012 | 0.015 | yes |
| 4 | 0.018 | 0.020 | yes |
| 5 | 0.025 | 0.025 | yes |
| 6 | 0.040 | 0.030 | no |
| 7 | 0.070 | 0.035 | no |
| 8 | 0.120 | 0.040 | no |
| 9 | 0.260 | 0.045 | no |
| 10 | 0.350 | 0.050 | no |

`max { k : p_k ≤ (k/M)·α } = 5`, so `H₀` is rejected for the **5 smallest p-values**;
those are the significant results.

```mermaid
flowchart LR
    S["Sorted p-values"] --> C["Compare each p_k with k over M times alpha"]
    C --> K["Largest k that passes: k equals 5"]
    K --> R["Reject H0 for the 5 smallest p-values"]
```
Benjamini–Hochberg in three steps; the cut is made at the largest passing index, not at each test individually.

## Takeaway

Hardy–Weinberg arithmetic is a Punnett square and nothing more, and it generalises to any
number of alleles as `(p + q + r + …)²`. The Wright–Fisher numbers show the other side:
in a population of five, "nothing changed" is itself only a 30 % event. And in
Benjamini–Hochberg the decisive move is step III — once the largest passing index `k` is
found, **all** smaller p-values are rejected, even those that fail their own line.

## Relations

- [[M2E04-k-means-and-transclust]] — the module-2 sheet with a comparable by-hand numeric workflow.

## Sources

- `raw/module1/gsb_3.pdf`, pp. 31–34.
