---
title: De Bruijn Assembly
type: method
module: 1
tags: [assembly, de-bruijn, k-mer, eulerian]
sources: [raw/module1/gsb_part1.pdf]
created: 2026-10-21
updated: 2026-10-22
status: solid
---

# De Bruijn Assembly

## Problem

**Input**: a large set of short reads.
**Output**: a reconstructed sequence, obtained **without** computing pairwise alignments
between reads.

## Idea

Chop every read into *k*-mers. Each *k*-mer becomes an **edge** joining its prefix
(k−1)-mer to its suffix (k−1)-mer, giving a [[de-bruijn-graph]]. Reconstructing the
sequence then means walking the graph so that **every edge is used exactly once** — an
**Eulerian path**. Unlike the Hamiltonian formulation behind [[greedy-assembly]], this is
solvable in polynomial time.

## Pseudocode

```text
BUILD-DE-BRUIJN(R, k):
  // R = reads, k = k-mer length
  V ← ∅; E ← ∅; count ← empty map
  for each read r in R:
    for i ← 1 to |r| - k + 1:
      m ← r[i .. i+k-1]                     // a k-mer
      count[m] ← count[m] + 1
      u ← m[1 .. k-1]                       // prefix (k-1)-mer
      v ← m[2 .. k]                         // suffix (k-1)-mer
      V ← V ∪ {u, v}
      E ← E ∪ {(u, v, label = m)}           // edge multiplicity = count[m]
  return (V, E, count)

EULERIAN-PATH(V, E):
  // Hierholzer: an Eulerian path exists if at most one vertex has
  // outdeg - indeg = 1 and at most one has indeg - outdeg = 1
  s ← vertex with outdeg - indeg = 1, else any vertex with outdeg > 0
  stack ← [s]; path ← []
  while stack not empty:
    u ← TOP(stack)
    if u has an unused outgoing edge e = (u, v):
      MARK-USED(e)
      PUSH(stack, v)
    else:
      PUSH(path, POP(stack))
  return REVERSE(path)

DE-BRUIJN-ASSEMBLY(R, k):
  (V, E, count) ← BUILD-DE-BRUIJN(R, k)
  REMOVE-SPURS(V, E)                        // short dead ends = read-end errors
  POP-BUBBLES(V, E)                         // keep the better-supported branch
  P ← EULERIAN-PATH(V, E)
  S ← P[1]
  for i ← 2 to |P|:
    S ← S + LAST-CHARACTER(P[i])            // each step adds exactly one base
  return S
```

## Worked example

5-mers `ACGGC, CGGCG, CGTGA, GACGT, GCGTG, GGCGT, GTGAC, TGACG` decompose into the
4-mers `ACGG(1), CGGC(2), GGCG(2), GCGT(2), CGTG(2), GTGA(2), TGAC(2), GACG(2), ACGT(1)`.
Reading them as edges over 3-mer nodes gives the chain

`ACG → CGG → GGC → GCG → CGT → GTG → TGA → GAC → ACG`

whose Eulerian traversal reconstructs **`GACGGCGTGACGT`**. Counts greater than 1 mark the
repeated traversal of the cycle. The full derivation, including a bubble example, is in
[[E03-de-bruijn-assembly]].

## Complexity

- Building the graph is linear in the total read length: `O(Σ|r|)`.
- Hierholzer's algorithm finds an Eulerian path in `O(|V| + |E|)` — **polynomial**,
  versus the NP-hard Hamiltonian formulation (see [[algorithmic-complexity]]).
- Memory is dominated by storing all distinct (k−1)-mers.

## Variants & pitfalls

- **Advantages (from the notes)**: no explicit alignment computation is needed, so it is
  fast; the problem is far less complex and runs in polynomial time.
- **Disadvantage**: the Eulerian path is usually **not unique** — many traversals are
  consistent with the same *k*-mer set, so the reconstruction is ambiguous.
- **Artifacts** to clean before traversal: spurs (read-end errors), bubbles (true
  variants, mid-read errors, or PCR artifacts), cycles (repeats), and frayed ropes
  (repeated elements).
- The choice of *k* trades resolution of repeats (larger *k*) against tolerance of
  sequencing errors and low coverage (smaller *k*).

## Diagram

```mermaid
flowchart LR
    R["Short reads"] --> K["Chop into k-mers"]
    K --> G["De Bruijn graph: k-mer as edge, prefix and suffix as nodes"]
    G --> CL["Remove spurs and pop bubbles"]
    CL --> EP["Eulerian path: every edge used exactly once"]
    EP --> S["Contig: one base added per step"]
```
From reads to sequence without any pairwise alignment: the assembly is a walk that uses every edge of the graph once.

## Relations

- [[de-bruijn-graph]] — the underlying data structure.
- [[greedy-assembly]] — the overlap-graph alternative it replaces.
- [[hamiltonian-and-eulerian-paths]] — the graph-theoretic contrast this method exploits:
  visiting every edge once is polynomial, visiting every node once is NP-hard.
- [[shotgun-sequencing]] — the shear-and-read step that supplies the reads being chopped
  into *k*-mers.
- [[dna-mutation]] — duplications and other repeat-creating mutations are what produce
  the cycles and frayed ropes in the graph.
- [[next-generation-sequencing]] — produces the short reads this method targets.
- [[algorithmic-complexity]] — the Eulerian vs Hamiltonian complexity argument.
- Appears in [[L04-genome-assembly]] and [[E03-de-bruijn-assembly]].

- [[travelling-salesman-problem]] — the weighted Hamiltonian problem that the Eulerian reformulation sidesteps.

## Sources

- `raw/module1/gsb_part1.pdf`, pp. 19–23.
