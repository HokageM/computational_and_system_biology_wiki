---
title: Highly Variable Genes
type: concept
module: 2
tags: [single-cell, feature-selection, hvg, noise-reduction, dimensionality]
sources: [raw/module2/csb_3.pdf]
created: 2026-10-22
updated: 2026-10-22
status: solid
---

# Highly Variable Genes

## Definition

**Highly variable genes (HVGs)** are the genes whose expression varies across cells by
more than the technical noise at their expression level. Restricting a single-cell
analysis to them is the standard **feature-selection** step of
[[single-cell-analysis-workflow]].

## Why it matters

The exercise asks it directly: *why do we only perform the downstream analysis with
highly variable genes?* Five reasons are given in the notes:

| Reason | Argument |
|---|---|
| **Biological relevance** | a gene expressed at the same level in every cell cannot distinguish cell types; only variation carries information about heterogeneity |
| **Noise reduction** | invariant genes contribute almost nothing but measurement noise and dropout zeros to every distance computation |
| **Computational efficiency** | `20 000` genes down to `1 000–2 000` makes every downstream step an order of magnitude cheaper |
| **Interpretability** | a short, variable gene list is readable; a full matrix is not |
| **Resource optimization** | memory and runtime for matrices with `10⁵–10⁶` cells |

## Details

HVG selection is **unsupervised feature selection**: no labels are used, only the
dispersion of each gene across cells. A naive "take the genes with the largest variance"
rule fails, because in count data the variance grows with the mean — highly expressed
genes are automatically high-variance. Selection is therefore made **relative to the
expected variance at that mean**:

```text
SELECT-HVG(M, n):
  for each gene g:
    μ[g] ← mean expression of g across cells
    σ²[g] ← variance of g across cells
  fit a trend  f(μ)  describing the expected variance at each mean level
  for each gene g:
    score[g] ← σ²[g] / f(μ[g])          // excess variance over the technical trend
  return the n genes with the largest score
```

In the preprocessing layers of the notes, HVG selection is the **"feature selected"**
branch of the *reduced* layer, sitting beside **"dimensionally reduced"**:

```text
1) Measured   → raw | normalized
2) Corrected  → technical correction | biological correction
3) Reduced    → feature selected | dimensionally reduced
```

Feature selection and dimensionality reduction are complementary, not alternatives:
HVG selection **discards genes**, keeping the surviving axes interpretable;
[[principal-component-analysis]], [[t-sne]] and [[umap]] **mix** genes into new
coordinates that are cheaper still but no longer named.

## Diagram

```mermaid
flowchart LR
    A["Normalized count matrix: ~20000 genes"] --> B["Fit variance against mean trend"]
    B --> C["Score each gene by excess variance"]
    C --> D["Keep the top n genes: the HVGs"]
    D --> E["PCA, then t-SNE or UMAP"]
    E --> F["Clustering and cell-type annotation"]
```
HVG selection shrinks the gene axis before any dimensionality reduction is attempted.

## Relations

- [[single-cell-analysis-workflow]] — HVG selection is its feature-selection step.
- [[single-cell-rna-seq]] — the data it is applied to.
- [[principal-component-analysis]], [[t-sne]], [[umap]] — the dimensionality reductions
  that follow it; HVG selection keeps the axes named, these do not.
- [[descriptive-statistics]] — the dispersion measures the selection is built on.
- [[data-normalization]] — HVGs are selected *after* normalisation, otherwise library
  size dominates the variance.
- [[random-forest]] — the supervised counterpart: a two-stage feature selection using
  labels, where HVG selection uses none.
- [[batch-effect]] — a gene that varies mainly between batches will be selected as an
  HVG, which is why correction comes first.

## Appears in

- [[M2L07-single-cell-rna-seq]]
- [[M2E07-single-cell-rna-seq-and-dimensionality-reduction]]

## Sources

- `raw/module2/csb_3.pdf`, p. 15 — the preprocessing layers: measured, corrected,
  reduced (feature selected / dimensionally reduced).
- `raw/module2/csb_3.pdf`, p. 22 — the exercise question about highly variable genes and
  the five reasons: biological relevance, noise reduction, computational efficiency,
  interpretability, resource optimization.
