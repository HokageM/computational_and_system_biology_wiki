---
title: Suffix Array
type: method
module: both
tags: [suffix-array, lcp, skip-array, index, string-matching]
sources: [raw/module1/gsb_3.pdf, raw/module2/csb_4.pdf]
created: 2026-10-21
updated: 2026-10-22
status: solid
---

# Suffix Array

## Problem

**Input:** a string `S[0..n−1]` terminated by a sentinel `$`.
**Output:** three flat arrays that encode the same information as a [[suffix-tree]] but
in a fraction of the memory:

- **`suf`** — the start indices of all suffixes, sorted lexicographically.
- **`lcp`** — the length of the longest common prefix of two adjacent suffixes.
- **`skp`** — the *skip* array: for each entry, where to jump when a branch is abandoned.

## Idea

A suffix tree traversed depth-first visits the suffixes in lexicographic order. Writing
down that order as a list of start indices gives `suf`; the internal nodes of the tree
are exactly the positions where two neighbouring suffixes share a prefix, which is what
`lcp` records; and `skp` encodes the "go back up to the parent" move of the tree walk.
Together they replace node pointers by array indices.

**Sorting convention used in the notes:** the sentinel `$` sorts **after** every letter,
so at equal prefix the **longer** suffix comes first (`ermometer$` before `er$`) and the
bare `$` is the last entry.

**Definitions**

```text
lcp[0] = 0
lcp[i] = | LCP( S_suf[i-1] , S_suf[i] ) |      // common prefix with the previous suffix
skp[i] = min { j > i : lcp[j] < lcp[i] }       // n if no such j exists
```

## Pseudocode

```text
BUILD-SUFFIX-ARRAY(S):
  S ← S · "$"
  n ← |S|
  suf ← [0, 1, …, n-1]
  SORT suf by the suffix S[suf[i]..n-1], lexicographically      // (i) $ counts as the largest symbol
  lcp[0] ← 0
  for i ← 1 to n-1:                                            // (ii) longest common prefixes
    lcp[i] ← LENGTH-OF-COMMON-PREFIX( S[suf[i-1]..], S[suf[i]..] )
  for i ← 0 to n-1:                                            // (iii) skip targets
    j ← i + 1
    while j < n and lcp[j] ≥ lcp[i]: j ← j + 1
    skp[i] ← j                                                 // = n when the scan runs off the end
  return suf, lcp, skp

SEARCH(S, suf, P):
  // the suffixes sharing prefix P form one contiguous block of suf
  lo ← BINARY-SEARCH-LOWER(suf, P)
  hi ← BINARY-SEARCH-UPPER(suf, P)
  return { suf[i] : lo ≤ i ≤ hi }          // all start positions of P in S
```

`skp` is what makes a scan over the array behave like a tree traversal: when the shared
prefix of depth `lcp[i]` can no longer lead to a hit — for example because a
[[position-weight-matrix]] prefix score has fallen below the intermediate threshold —
the whole block of suffixes sharing that prefix is skipped by jumping to `skp[i]`.

## Worked example

`S = banana$`, `n = 7`. Suffixes sorted with `$` as the largest symbol:

| i | suf[i] | S_suf[i] | lcp[i] | skp[i] |
|---|---|---|---|---|
| 0 | 1 | `anana$` | 0 | 7 |
| 1 | 3 | `ana$` | 3 | 2 |
| 2 | 5 | `a$` | 1 | 3 |
| 3 | 0 | `banana$` | 0 | 7 |
| 4 | 2 | `nana$` | 0 | 7 |
| 5 | 4 | `na$` | 2 | 6 |
| 6 | 6 | `$` | 0 | 7 |

Reading the table: `lcp[1] = 3` because `anana$` and `ana$` share `ana`; `skp[1] = 2`
because index 2 is the next entry with a smaller `lcp`. The pairs with `lcp ≥ 2` —
indices 1 and 5 — mark the repeated substrings `ana` and `na`, exactly the internal nodes
of the corresponding suffix tree.

```mermaid
flowchart LR
    T["Text with sentinel"] --> ST["Suffix tree"]
    ST -->|"depth-first traversal"| SUF["suf: sorted suffix start indices"]
    SUF --> LCP["lcp: shared prefix with the previous suffix"]
    LCP --> SKP["skp: index of the next smaller lcp"]
    SKP --> USE["Binary-search queries and pruned motif scans"]
```
The three arrays are the depth-first order of the suffix tree plus the depth information its nodes carried.

## Complexity

- **Construction** by generic comparison sorting of suffixes: `O(n² log n)` in the worst
  case, or `O(n²)` when derived from the `O(n²)` suffix-tree construction of the notes;
  specialised algorithms achieve `O(n)`.
- **Space:** three integer arrays of length `n` — roughly an order of magnitude less than
  a suffix tree, which is the whole point.
- **Search:** `O(|P| · log n)` by binary search, or `O(|P|)` with the `lcp` array used to
  avoid re-comparing known prefixes.

See [[algorithmic-complexity]].

## Variants & pitfalls

- The **sorting convention** for `$` must be fixed before anything else; swapping it
  reverses the order of suffixes that are prefixes of one another and changes every
  `lcp`.
- `skp[i] = n` (one past the end) is the legitimate "nothing left to skip to" value and
  must be handled explicitly.
- A suffix array alone cannot answer all suffix-tree queries in the same time bounds;
  `lcp` plus `skp` is what restores the tree structure.
- In practice the **enhanced suffix array** (suffix array + `lcp` + child table) replaces
  the suffix tree in genome indexes entirely.

## Relations

- [[suffix-tree]] — the structure this array flattens; a DFS of the tree yields `suf`.
- [[position-weight-matrix]] — motif scans prune whole suffix blocks via `skp`.
- [[string-matching]] — the factor-search paradigm.
- [[algorithmic-complexity]] — memory versus time trade-off against the suffix tree.
- [[knuth-morris-pratt]] — preprocesses the pattern instead of the text this array
  indexes.
- [[boyer-moore-string-search]] — the other online matcher that preprocesses the pattern,
  so its tables must be rebuilt for every new pattern.
- [[mirna-target-prediction]] — the indexing machinery behind scanning a transcriptome for seed matches.

## Appears in

- [[L08-exact-string-matching]]
- [[L13-suffix-trees-and-arrays]]
- [[E10-suffix-trees-and-arrays]]
- [[M2L09-non-coding-rnas]] — module 2 uses such an index for genome-wide miRNA seed search.

## Sources

- `raw/module1/gsb_3.pdf`, pp. 15, 18–19.
- `raw/module2/csb_4.pdf`, pp. 4–5 — genome-wide seed matching.
