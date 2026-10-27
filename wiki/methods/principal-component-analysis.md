---
title: Principal Component Analysis
type: method
module: both
tags: [pca, dimensionality-reduction, unsupervised, quality-control, mds]
sources: [raw/module1/gsb_3.pdf, raw/module2/csb_4.pdf]
created: 2026-10-21
updated: 2026-10-22
status: solid
---

# Principal Component Analysis

## Problem

**Input:** a matrix of `n` possibly correlated variables measured on many samples
(e.g. genes × samples), scaled/normalized beforehand
([[data-normalization]]).
**Output:** a small number of uncorrelated new variables — the **principal components
(PCs)** — that capture most of the variance, usually plotted as PC1 against PC2.

What it is used for, per the notes:

- Reduce **dimensions / complexity** so the data can be visualized in 2D or 3D.
- Visualize the **most dominant signal** in the data.
- Detect biologically important signal.
- **Quality control** — spot experimental artifacts, e.g. a [[batch-effect]].
- Identify **outliers**.

## Idea

PCA is a statistical algorithm that transforms possibly correlated variables into
**uncorrelated linear combinations**. Formally it is an **orthogonal linear
transformation** into a new coordinate system chosen so that the **greatest variance**
lies on the first coordinate, the second greatest on the second coordinate, and so on.
The new axes are the **eigenvectors** of the data's covariance matrix; the first
component is the most dominant signal.

Each component is a weighted sum of the original variables:

```text
t_1 = a_11 · x_1 + a_12 · x_2 + … + a_1n · x_n
…
t_n = a_n1 · x_1 + a_n2 · x_2 + … + a_nn · x_n
```

PCA is one of the techniques used for **unsupervised learning** problems: no labels are
used in computing the projection.

## Pseudocode

```text
PCA(X, k):
  // X: samples × variables matrix, k: number of components wanted
  X ← NORMALIZE(X)                       // centre each variable, scale to unit variance
  C ← COVARIANCE(X)                      // n × n covariance matrix of the variables
  (λ, V) ← EIGEN(C)                      // eigenvalues λ_i and eigenvectors v_i
  order ← SORT-DESCENDING-BY(λ)          // greatest variance first
  A ← [ V[order[1]], …, V[order[k]] ]    // loading matrix, k eigenvectors as columns
  T ← X · A                              // scores: coordinates in the new system
  for i ← 1 to k:
    explained[i] ← λ[order[i]] / Σ_j λ[j]   // fraction of variance captured by PC i
  return T, A, explained

PCA-PLOT(T):
  plot column T[·,1] against column T[·,2]   // first PC versus second PC
```

Removing a batch effect reduces to identifying the component `i` whose scores track the
batch and subtracting its contribution `T[·,i] · A[·,i]ᵀ` from `X`.

## Worked example

Suppose an expression experiment with 20,000 genes is run on two days, ten samples each,
and both days contain five healthy and five diseased individuals. Plotting PC1 against
PC2:

- If the samples split along **PC1** by *day*, PC1 carries the batch effect — the
  dominant signal is technical, not biological.
- If they split along PC1 by *disease status*, the dominant signal is biological.
- A single sample far away from every cluster is an **outlier**.

The experiment was designed so that the day is not confounded with disease status;
otherwise the two interpretations could not be separated at all ([[batch-effect]]).

```mermaid
flowchart LR
    X["Data matrix: samples by variables"] --> C["Center and scale each variable"]
    C --> COV["Covariance matrix"]
    COV --> EIG["Eigenvectors and eigenvalues"]
    EIG --> ORD["Order components by variance explained"]
    ORD --> PROJ["Project samples onto PC1 and PC2"]
    PROJ --> USE["Visualise signal, spot outliers, detect batch effects"]
```
PCA in one line: centre, diagonalise the covariance, keep the highest-variance directions.

## Complexity

Computing the `n × n` covariance matrix of `m` samples costs `O(m·n²)`; the eigenvalue
decomposition costs `O(n³)` ([[algorithmic-complexity]]). For wide omics matrices the
truncated SVD is used instead, which produces only the leading `k` components.

## Variants & pitfalls

**PCA versus MDS** (multidimensional scaling), as contrasted in the notes:

| | input | output |
|---|---|---|
| **PCA** | scaled (normalized) vectors in `n`-dimensional space | projection onto the directions of greatest variance |
| **MDS** | pairwise **distances** between data points | a 2D/3D projection in which the distances between points are preserved |

Pitfalls:

- PCA on **unscaled** data lets the variable with the largest units dominate every
  component — always normalize first.
- The first component is the most *dominant* signal, not necessarily the most
  *interesting* one; it is frequently technical.
- Components are only interpretable up to sign and rotation within equal eigenvalues.

## Relations

- [[data-normalization]] — required preprocessing; PCA consumes standardized vectors.
- [[batch-effect]] — PCA is both the diagnostic and the removal tool.
- [[population-genetics]] — PCA on genotypes is the standard correction for population
  structure in a [[genome-wide-association-study]].
- [[descriptive-statistics]] — covariance, the quantity PCA diagonalises.
- [[microarray-expression-analysis]], [[rna-seq]] — the data matrices PCA is applied to.
- [[snp]] — PCA on SNP genotypes is what exposes and corrects population structure.
- [[z-score]] — the standardized values PCA consumes.

- [[enrichment-analysis]] — PCA is a quality-control step before the differential expression that enrichment consumes.
- [[machine-learning]] — PCA is the standard unsupervised method of that taxonomy, as clustering is the other.
- [[cluster-analysis]], [[k-means]] — PCA is commonly run first, and the clusters are then drawn in its first two components.
- [[support-vector-machine]], [[random-forest]] — supervised counterparts that use the labels PCA ignores.
- [[t-sne]], [[umap]] — the non-linear successors; in practice PCA runs first and they embed its output.
- [[autoencoder]] — a non-linear PCA with a reusable encoder.
- [[single-cell-analysis-workflow]], [[single-cell-rna-seq]], [[highly-variable-genes]] — PCA is step 5 of the single-cell pipeline, with the number of components chosen at the elbow.
- [[rna-interference]] — visual analytics of screening data is one of the listed RNAi bioinformatics tasks.

## Appears in

- [[L06-expression-profiling]]
- [[L11-normalization-pca-and-batch-effects]]
- [[L14-population-genetics]]
- [[E09-binding-sites-pwm-and-pca]]
- [[M2L03-machine-learning-and-classification]]
- [[M2L04-clustering]]
- [[M2E07-single-cell-rna-seq-and-dimensionality-reduction]] — the linear step that precedes t-SNE/UMAP in the single-cell pipeline.
- [[M2L06-deep-learning]] — the linear benchmark that an autoencoder generalises non-linearly.
- [[M2L07-single-cell-rna-seq]] — module 2 uses PCA as the linear pre-step of the single-cell embedding.

## Sources

- `raw/module1/gsb_3.pdf`, pp. 3–4, 12.

- `raw/module2/csb_4.pdf`, p. 3 — visual analytics in the RNAi screening analysis stack.
