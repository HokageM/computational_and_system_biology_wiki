---
title: Open questions
type: gaps
module: both
tags: [gaps]
created: 2026-10-21
updated: 2026-10-22
status: draft
---

# Open questions

Running list of things the wiki cannot yet answer. Every item names the module and the
`raw/` source it came from. Items fully closed by a later part of the notes or by a lint
pass have been removed; partly-closed items keep a struck-through original with a note on
what is still missing.

> [!note] Epigenetics is no longer listed here
> Per `CLAUDE.md` §1 the epigenetics notes were known to be incomplete. All remaining
> gaps were closed from established domain knowledge during the 2026-10-21 and
> 2026-10-22 lint passes and are marked in place with the *Added beyond lecture notes*
> callout on [[epigenetics]], [[chromatin]], [[histone-modification]],
> [[dna-methylation]], [[cpg-island]], [[atac-seq]], [[bisulfite-sequencing]],
> [[chip-seq]] and [[epigenome-wide-association-study]]. What is marked there is
> background, not examinable lecture content.

## Illegible handwriting

From `raw/module1/gsb_part1.pdf` (part 1 of 4):

- p. 11 — the amino-acid sequence written under the spliced mRNA example is small and
  overwritten; only the start codon `AUG` and the presence of a stop codon could be read
  reliably. The individual residues were **not** transcribed and must not be assumed.
  Recorded in [[E01-cell-biology-and-gene-expression]].
- p. 17 — the overlap graph carries edge weights from 1 to 4, but only the weight-4,
  weight-3 and weight-2 edges actually used in the merge sequence could be read with
  confidence; the individual low-weight edge labels were not transcribed. See
  [[E02-greedy-assembly]].
- p. 28 — in item b) 6) the base of the logarithm in `3 log₈ n` is written ambiguously;
  `log₈` was assumed because the matching right-hand side reads `O(log₈ n)`. Flagged in
  [[E04-complexity-and-majority-element]].

From `raw/module1/gsb_part2.pdf` (part 2 of 4):

- p. 6 — the iteration count in the KMP trace is overwritten; the corrected value **29**
  was taken (an earlier `28` is struck through on the sheet). See
  [[E05-kmp-string-matching]].
- p. 10 — the **good-suffix table** for `ATGATTATGAATGA` is written with several
  corrections on top of each other and could **not** be transcribed with confidence. Only
  the general shape (large shifts for long suffixes, small ones — around 3 and 1 — for
  short suffixes) could be read. The bad-character table on the same page is legible.
  Recorded in [[E06-boyer-moore-string-search]] and
  [[boyer-moore-string-search]].
- p. 26 — the accuracy formula is written as `(TP + FN)/n`, which is a slip of the pen:
  the worked example on p. 29 computes `(35 + 120)/200`, i.e. `(TP + TN)/n`. The correct
  form is used in [[statistical-testing]] and [[E08-test-errors-and-z-score]].

From `raw/module1/gsb_3.pdf` (part 3 of 4):

- p. 11 — the ~18 input sequences of the PWM exercise and several entries of the position
  count matrix are written small and partly overwritten; the individual letters and
  counts could **not** be read with confidence and were therefore **not** reproduced.
  Only the worked entry `f^P = 3 + 0.2·4 = 3.8`, `f = 3.8/22 ≈ 0.172` and the overall
  `C`-rich consensus are reliable. Recorded in [[E09-binding-sites-pwm-and-pca]].
- p. 15 — the small suffix-array example (`acadaccac$` and its neighbours) carries `lcp`
  values that could not be reconciled with the definition given on the same page; the
  [[suffix-array]] page therefore uses the fully legible `teethermometer$` example from
  pp. 18–19 and a self-contained `banana$` example instead.

From `raw/module1/gsb_part4.pdf` (part 4 of 4):

- p. 19 — the **dinucleotide probability table** of the Markov-chain exercise is written
  small and partly overwritten; the individual `P(XY)` entries could **not** be read with
  confidence and were therefore **not** reproduced. Only the derived marginals
  `P(A) = 0.33`, `P(T) = 0.29`, `P(C) = 0.23`, `P(G) = 0.18` and the two computed
  transition probabilities `P(A|A) = 0.27` and `P(A|T) = 0.31` are reliable. Recorded in
  [[E13-markov-chains-and-viterbi]] and [[markov-chain]].
- p. 20 — in the Viterbi trellis only the **first column** is filled in on the sheet;
  the remaining cells are blank. Columns 2 and 3 in
  [[E13-markov-chains-and-viterbi]] are derived here from the model probabilities given
  on the same page, not transcribed.

From `raw/module2/csb_1.pdf` (part 1 of 4):

- p. 13 — the per-node zero counts written beside the GLONE figures give **B = 3**, but
  the indicator matrix on p. 12 reads `B = 0 0 0 0 1`, i.e. **4** zeros. The written
  counts total 26, the matrix 27. Both readings are stated in
  [[M2E01-enrichment-analysis-and-keypathwayminer]]; the matrix is treated as
  authoritative.
- p. 13 — the exact **node membership** of the three hand-drawn GLONE candidate
  subnetworks could **not** be determined reliably (the blobs overlap the graph
  drawing). Only the reported sums (10, 14, 9 for `L = 10`; 20, 18, 13 for `L = 15`) and
  the corresponding verdicts are reproduced.
- p. 10 — the struck-through alternative answer in item 1c) reads "(or GSEA Enrichment
  Test)"; the strike-through is clear but the parenthetical wording is small. See
  [[M2E01-enrichment-analysis-and-keypathwayminer]].

From `raw/module2/csb_part2.pdf` (part 2 of 4):

- p. 17 — the `5 × 5` **distance matrix** of the k-means exercise is drawn but only the
  **zero diagonal** is filled in; the off-diagonal entries are blank on the sheet. The
  distances quoted in [[M2E04-k-means-and-transclust]] were recomputed from the five
  given points, not transcribed.
- p. 20 — in the TransClust clustering drawing, the left-hand group is **scribbled over**
  and its exact membership (around nodes `0`, `1`, `2`) could **not** be read with
  confidence. Only the two clearly drawn triangles `{3,5,6}` and `{4,7,9}` and the
  singletons `{8}` and `{10}` are reproduced in [[M2E04-k-means-and-transclust]].
- p. 20 — the full 55-pair TP/TN/FN/FP enumeration is written in a dense column; the
  individual pair labels were **not** transcribed cell by cell. Only the stated final
  value `F ≈ 0.6133` and the rule itself are reproduced. See [[f-measure]].
- p. 23 — a word above "Network constraint bi-clustering" is crossed out in blue and is
  illegible. Noted in [[M2L05-network-based-disease-modules]].

From `raw/module2/csb_3.pdf` (part 3 of 4):

- p. 15 — the **platform decision tree** is drawn compactly and the branch leading to
  *"common sensitivity → inDrops"* could not be placed with certainty relative to the
  neighbouring branches. The Mermaid diagram in [[single-cell-rna-seq]] reproduces the
  readable structure and flags the uncertain branch in its caption.
- p. 37 — the **GC-biased substitution matrix** and the **transition/transversion
  matrix** are both partly written over. The entries reproduced in
  [[M2E08-phylogenetics]] are self-consistent reconstructions satisfying the stated
  row-sum rule; the exact off-diagonal values of the GC variant are **not** confirmed.

From `raw/module2/csb_4.pdf` (part 4 of 4):

- p. 5 — the **final stage label of the PAR-CLIP machine-learning pipeline** is not
  legible. The readable stages (feature extraction and analysis, feature selection,
  scoring, coding/3′ UTR targets, independent testing) are reproduced in
  [[mirna-target-prediction]]; the last box is omitted rather than guessed.
- p. 19 — the **graphlet degree table for orbits 0–14** in exercise 2b is overwritten and
  struck through. Only `d₀(u) = 4` and `d₀(v) = 1` can be read with confidence, so
  [[M2E10-network-alignment]] computes the orbit-0 term only and states the general
  formula instead of a numeric GDSD.
- p. 17 — the **third termination criterion of [[gedevo]]** ("when the fitness of the
  best solution did not improve for …") runs off the edge of the page; the missing number
  of generations is not recoverable.

## Missing topics

- **Sanger sequencing** is named as the Human Genome Project technology in
  [[L03-sequencing-and-genomics]] but its chain-termination chemistry is never explained.
- **LOESS** and **RMA** are listed as normalisation methods in
  [[L06-expression-profiling]] without any description of how they work.
- ~~**BLAST E-value statistics**~~ **Partly resolved by
  part 2**: PAM and BLOSUM are introduced in [[substitution-matrix]] and the BLAST
  program family in [[L09-sequence-alignment-and-homology]]. Still missing: the
  derivation of the E-value's extreme-value statistics, and how the PAM/BLOSUM matrices
  themselves are constructed from substitution frequencies.
- **Multiple sequence alignment** is named as an axis in [[sequence-alignment]] but no
  algorithm for it is given — part 2 covers only pairwise alignment.
- **Eulerian path selection**: [[de-bruijn-assembly]] notes that the path is usually not
  unique, but the notes do not say how an assembler chooses among the candidates.
- **The master theorem** for divide-and-conquer recurrences is not covered in
  [[L07-algorithms-and-complexity]]; only the `O(n log n)` result is stated.
- **Yeast two-hybrid / co-immunoprecipitation**: [[interaction-network]] distinguishes
  binary from co-complex data, but the underlying experiments are not described.
- **Microarray statistical testing**: [[microarray-expression-analysis]] mentions
  "statistical testing" as a pipeline stage without naming a test or a
  multiple-testing correction. Part 2 supplies the general framework in
  [[statistical-testing]], but **no concrete test** (t-test, Wilcoxon, ANOVA …) is named
  anywhere in the notes. **Multiple-testing correction resolved by part 3**:
  Bonferroni and Benjamini–Hochberg appear in
  [[multiple-testing-correction]], and Fisher's exact test, the Cochran–Armitage trend
  test and logistic regression are named for GWAS in
  [[genome-wide-association-study]]. **Concrete tests named by
  `raw/module2/csb_1.pdf`**: the **t-test** is given as the ranking statistic of a
  two-class design and **Pearson correlation** for a quantitative phenotype
  ([[enrichment-analysis]]), though neither statistic is written out.

From `raw/module1/gsb_part2.pdf` (part 2 of 4):

- **BDM/BNDM** factor-search automata are named but never described; the factor-search
  machinery itself is now covered by [[suffix-tree]] and [[suffix-array]] in
  [[L13-suffix-trees-and-arrays]].
- **Semi-global and free-end-gaps alignment** are named as alignment types in
  [[L09-sequence-alignment-and-homology]] without the corresponding initialisation and
  traceback rules; those given on this wiki's [[needleman-wunsch]] page are inferred from
  the global case.
- **Regression** is mentioned once on p. 19 as the route from data to correlation with a
  clinical outcome, but no regression model is described. Part 3 names **logistic
  regression** and **linear models** for GWAS
  ([[genome-wide-association-study]]) but still gives no model equation.
- ~~**Test statistics** are described only abstractly~~ **Partly resolved by
  `raw/module2/csb_1.pdf`**: [[fishers-exact-test]] is the first test in these notes
  given with a complete, usable formula — the hypergeometric probability of a 2×2 table
  — and module 2 additionally names the **t-test** and **Pearson correlation** as
  ranking statistics. Still missing: the statistics of the t-test, the Wilcoxon test and
  the Cochran–Armitage trend test.
- **Confidence intervals** are implied by "confidence level `1 − α`" on p. 28 but never
  defined.

From `raw/module1/gsb_3.pdf` (part 3 of 4):

- **Batch-effect correction methods**: **SVD**, **ComBat** and "standardization" are
  listed in [[batch-effect]] as statistical approaches, but none of them is described.
  Only the PCA route ("subtract the component representing the batch effect") is
  explained at all.
- **The background score distribution** `λ_B(X)` of a
  [[position-weight-matrix]] is used to set the threshold, but the notes never say how it
  is computed (exact dynamic programming, simulation, or an approximation).
- **Linear-time suffix-tree construction** (Ukkonen) is not covered; only the `O(n²)`
  incremental construction of [[suffix-tree]] is given, and the role of the `skp` array
  inside an actual search is only sketched.
- **Natural selection** and **gene flow** are named in [[population-genetics]] as two of
  the four evolutionary forces, but neither is modelled; only drift and the
  Hardy–Weinberg null model are developed.
- **Linkage disequilibrium** is used informally ("SNPs in proximity are correlated") in
  [[genome-wide-association-study]] but never quantified, so the notes do not say how the
  "one SNP per region of strong linkage" is actually chosen.
- **Population-based phasing algorithms** are implied by "genotype data for a large
  number of individuals" in [[haplotype-phasing]], but only enumeration and trio phasing
  are shown.
- ~~**Manhattan plot** and **sequence logo** are named as the standard visualisations~~
  **Sequence logo resolved by `raw/module2/csb_1.pdf`**: [[sequence-logo]] gives the
  full construction — stack height from the relative entropy, letter height from each
  residue's contribution — with [[information-content]] supplying the entropy
  machinery. Still missing: the axes and construction of the **Manhattan plot**
  ([[genome-wide-association-study]]). Originally raised from
  [[E09-binding-sites-pwm-and-pca]].

From `raw/module1/gsb_part4.pdf` (part 4 of 4):

- **How histone marks are inherited** across replication is raised explicitly in the
  notes (p. 4: a newly formed nucleosome is unmodified) and left unanswered. Noted in
  [[histone-modification]].
- **The backward recursion** of the forward–backward algorithm is never written out; only
  the forward trellis is drawn and the name "forward–backward" is used. The backward pass
  in [[forward-algorithm]] is the standard formulation, not a transcription.
- **Fragment-length estimation** in MACS2 ([[peak-calling]]) is stated as "estimate `d`"
  without the cross-correlation procedure that produces it.
- **Profile-HMM construction** from a multiple alignment is sketched as an architecture
  ([[hidden-markov-model]]) but the mapping from alignment columns to match states, and
  the treatment of gap-rich columns, is not given.

From `raw/module2/csb_1.pdf` (part 1 of 4):

- **k-means** is named as the clustering method for time-course enrichment designs
  ([[enrichment-analysis]]) but is never described — no objective function, no
  initialisation, no stopping rule.
- **Pearson correlation** and **linear models** are named as alternative ranking
  statistics for GSEA and for "other designs", with no formula for either.
- **The ant transition probability.** The notes state that there is "a probability that
  an ant `s` at vertex `u` moves to vertex `v`" and that successful ants "update the
  pheromone value", but neither the transition formula nor the update and evaporation
  rules are written out. The forms used in [[ant-colony-optimization]] are the standard
  ACO ones, not transcriptions.
- **The ES-score contribution magnitudes.** [[gene-set-enrichment-analysis]] records
  only that a present gene gives a *positive* and an absent gene a *negative*
  contribution; the actual weights are not given, so the balance condition used on that
  page is explicitly marked as derived.
- **Combinatorial approaches** to motif discovery are listed on p. 18 as one of the
  three method families alongside brute force and statistical approaches, but no
  combinatorial algorithm is described. See [[planted-motif-problem]].
- **Pathway scoring.** Pathways are named as one of the three functional groupings and
  as something that can be "scored exploiting gene expression and topology", but no
  pathway-scoring method is given — in contrast to gene sets (GSEA) and networks
  (KeyPathwayMiner).
- **How KeyPathwayMiner enumerates candidates.** The models define what a valid solution
  is; the notes point at [[ant-colony-optimization]] but do not describe how an ant's
  walk is turned into a candidate subnetwork or how maximality is enforced during the
  search.
- **Convergence criteria.** Every iterative method in this source —
  [[expectation-maximization]], [[em-motif-discovery]], [[gibbs-sampling]],
  [[ant-colony-optimization]] — ends with "repeat until convergence" without a stated
  criterion. **Part 2 adds to the list**: [[k-means]], [[transclust]], [[bicon]].
- ~~**Linear regression** is named on p. 1 as the other linear method beside the
  [[support-vector-machine]], but it has no derivation or formula in the notes.~~
  **Partly resolved by `raw/module2/csb_3.pdf` p. 1**: linear and multiple linear
  regression are written as `f(X) = β₀ + β₁X₁ + β₂X₂ + …` and used as the entry point to
  [[deep-learning]]. Still missing: the least-squares derivation of the coefficients.
- **The SVM optimisation.** p. 8 gives `f(x) = sign(wᵀx + b)`, the signed distance
  `r = (wᵀx_i + b)/‖w‖` and the margin `ρ`, and states that maximising the margin gives a
  PAC guarantee — but the **constrained quadratic program**, its **dual**, the
  **kernel trick** and **soft margins** are not written out. The QP in
  [[support-vector-machine]] is the standard form, explicitly marked as such.
- **Non-linear SVMs** are described only as "map the training set to a higher-dimensional
  feature space"; no kernel function is named.
- **The GrandForest splitting rule.** p. 21 shows a network being unrolled into a tree,
  but how a node's candidate features are restricted to network neighbours — and how the
  root is chosen — is not specified. See [[grandforest]].
- **GrandForest's background generation** (step 1 of the unsupervised pipeline) is named
  but never defined; nor is the "recursive clustering on computed pathways" on p. 22.
- **BiCoN's objective function** is described in words ("maximizes the expression
  differences of these two gene sets between two subgroups of patients") but is never
  written as a formula. See [[bicon]].
- **Density-based and model-based clustering** are listed on p. 12 as two of the five
  families but no algorithm (DBSCAN, Gaussian mixture, …) is given for either; only
  prototype-based ([[k-means]]) and graph-based ([[transclust]]) are developed. See
  [[cluster-analysis]] and [[M2L04-clustering]].
- **Hierarchical clustering** is likewise named as a family with no linkage criterion or
  dendrogram construction described.
- **The elbow method** is drawn with the SSE on the y-axis, but no rule for *choosing*
  the elbow point is stated. See [[k-means]].

From `raw/module2/csb_3.pdf` (part 3 of 4):

- **Faster optimisers than plain gradient descent** are referred to on p. 5 but none is
  named (no Adam, RMSProp, momentum). See [[gradient-descent]].
- **RNNs, attention and transformers** (p. 8) are listed with their purpose but no
  equations, no recurrence and no attention formula. [[recurrent-neural-network]] is
  therefore `status: draft`.
- **Graph neural networks** (p. 8) are given only by their three prediction levels and
  the Laplacian `L = D − A`; no message-passing rule or spectral convolution is derived.
  [[graph-neural-network]] is `status: draft`.
- **Diffusion components** and **force-directed graph layouts** are named on p. 17 as
  visualization options alongside t-SNE and UMAP, but neither is developed. See
  [[single-cell-analysis-workflow]].
- **The Jukes–Cantor distance formula** itself is not written out on p. 28 — only the
  rate matrix `Q^JC` and the Poisson correction `d_P = −ln(1−p)`. The standard
  `d = −¾ ln(1 − 4p/3)` is given in [[jukes-cantor-model]] and explicitly marked as not
  transcribed from the notes.
- **Minimal evolution** and **maximum likelihood** are named on p. 30 as further
  reconstruction methods, and **Felsenstein** on p. 37 as a further substitution model
  (explicitly "not presented"), but none of the three is developed. See
  [[phylogenetic-tree-reconstruction]], [[neighbor-joining]] and [[maximum-parsimony]].
- **The topology search inside maximum parsimony** is not described: the notes say "all
  possible topologies" without branch-and-bound or heuristic search. The Fitch scoring
  pass in [[maximum-parsimony]] is standard content, not transcribed.
- **Elastic net regression** is named in [[M2E09-non-coding-rnas-and-sponge]] (p. 10) as
  the model SPONGE uses to confirm gene–miRNA interactions, but neither the penalty term
  nor the fitting procedure is written down. [[sponge]] describes its role, not its
  derivation.
- **miRanda, TargetScan, miRcode, miRBase and CLIP-Seq/PAR-CLIP** are all named on
  pp. 4–5 and 9 as tools or data sources without any methodological detail. Only their
  function is recorded, in [[mirna-target-prediction]] and [[sponge]].
- **The four offspring-generation strategies of [[gedevo]]** (p. 17) are described in one
  line each; the exact mutation rates beyond "1 % of good pairs" and "a random number of
  bad pairs" are not specified. See [[M2L10-network-alignment]].

## To verify

- p. 28, item 1a): the computation `T(10⁶) = 2000 ms` uses `log₁₀`. With `log₂` the
  answer would differ; the notes are not explicit about the base. See
  [[E04-complexity-and-majority-element]].
- p. 7 gene-length range "1148 bp – 37.7 kb" — it is unclear whether this is the average
  gene length range or a min/max over the genome.
- [[E02-greedy-assembly]] — the final 19 bp contig `ATTTGCGCAGAGACCTAAG` matches the
  notes; the position table reconstructed for the last two fragments should be
  double-checked against the original sheet.

From `raw/module1/gsb_part2.pdf` (part 2 of 4):

- p. 10 — the bad-character shifts `A = 3`, `T = 2`, `G = 1` only follow from
  `len(P) − index − 1` if the **last** pattern position is excluded from the table. That
  convention (the Horspool convention) was assumed in
  [[boyer-moore-string-search]]; the notes do not state it explicitly.
- p. 14 — the Needleman–Wunsch matrix for `YCTYSRFTVF` / `YRTYTVF` was not fully
  legible cell by cell; the initialisation row and the final alignment
  `YCTYSRFTVF / YRTY---TVF` were read directly, the intermediate cells were not
  verified. See [[E07-alignment-and-homology]].
- p. 19–20 — the two sample groups are labelled `LC` and `CC` without the abbreviations
  ever being expanded; they are treated here simply as two conditions.
- p. 26 — the sensitivity/specificity/accuracy block gives no numerical example; the
  values were checked against the exercise on p. 29 instead.

From `raw/module1/gsb_3.pdf` (part 3 of 4):

- pp. 18–19 — the `teethermometer$` suffix array was transcribed cell by cell and
  re-derived independently in [[E10-suffix-trees-and-arrays]]; both agree, but the
  sorting convention (the sentinel `$` ranking **after** every letter, so the longer
  suffix comes first at an equal prefix) is only implicit in the notes and was inferred
  from the resulting order.
- p. 26 — the case/control contingency table `23 / 41 / 351` versus `104 / 208 / 103` is
  reproduced as read; the row totals happen to be equal (415 each), which may be
  coincidental or may indicate a transcription slip. See
  [[genome-wide-association-study]].
- pp. 31–32 — the Wright–Fisher exercise does not state the population size explicitly;
  `N = 5` (so `2N = 10` alleles) was inferred from the allele counts `8 + 2 = 10` used in
  the binomial computation. See [[E11-population-genetics-and-multiple-testing]].

From `raw/module1/gsb_part4.pdf` (part 4 of 4):

- p. 16 — the Baum–Welch step is described as plain **counting** of transitions and of
  symbols aligned to a state, which is Viterbi training rather than EM. The
  expected-count formulation used in [[baum-welch-algorithm]] is the standard EM version
  and should be checked against the lecture slides.
- p. 19 — the four marginals derived from the dinucleotide table sum to **1.03**
  (`0.33 + 0.29 + 0.23 + 0.18`), so at least one value is rounded or misread. See
  [[E13-markov-chains-and-viterbi]].

From `raw/module2/csb_1.pdf` (part 1 of 4):

- p. 16 — the **relative entropy** is written with a leading minus sign,
  `H(P_i ‖ π) = −Σ_j P_ij log₂(P_ij/π_j)`, which is the **negative** of the standard
  Kullback–Leibler divergence. With that sign a strongly conserved column would get a
  *negative* stack height in a [[sequence-logo]]. The standard (positive) form is used on
  [[information-content]] and [[sequence-logo]], with the discrepancy noted there.
- p. 26 — **the EM iteration does not close arithmetically.** Three separate problems,
  all documented on [[M2E02-motif-discovery-and-expectation-maximization]]:
  (i) row 5 of the responsibility table reuses row 4's weighted head counts
  (`5.8562 / 1.144`) although Seq 5 has only **3** heads, so the values should be
  `2.511 / 0.49`; (ii) row 3 uses the **rounded** likelihoods `0.001 / 0.04`, giving a
  responsibility of `0.0243` where the exact binomial values give `0.0376`;
  (iii) the reported `Θ_A¹ = 0.674` and `Θ_B¹ = 0.303` **cannot be reproduced** from the
  sheet's own table — recomputation gives `≈ 0.631 / 0.708` as written, or
  `≈ 0.449 / 0.687` with row 5 corrected. The *procedure* is correct; the numbers are
  not. Worth checking against the official solution.
- p. 5 — the Fisher p-value is written as
  `(a+b)!(a+c)!(c+d)!(b+d)! / (n! a! b! c! d!)`. This is the standard hypergeometric
  point probability, but the notes do not say whether the reported enrichment p-value is
  this single term or the one-sided **sum** over all tables at least as extreme. The
  summed, one-sided form is used on [[fishers-exact-test]], with the distinction stated
  there.
- p. 12 — the indicator matrix was read cell by cell at 600 DPI and reconciled against
  the derived activity columns for `L ≤ 1` and `L ≤ 3`; the two agree. The edge list of
  the graph (A–D, B–D, C–D, D–E, D–F, E–F, E–H, E–I, F–I, F–G, H–I, I–K, I–J) should
  nonetheless be double-checked against the original sheet. See
  [[M2E01-enrichment-analysis-and-keypathwayminer]].
- p. 15 — the **pseudo-count** is named as part of the PWM definition but no formula is
  given on that page; [[position-weight-matrix]] uses the module-1 form
  `f = (c_j + β·π_j) / (Σc + β)`.

From `raw/module2/csb_part2.pdf` (part 2 of 4):

- p. 4 versus p. 10 — the **ROC x-axis**. The lecture page labels it `spec`, the exercise
  page uses the **FP rate** (`= 1 − specificity`). The standard convention, and the one
  used on [[roc-curve]], is FP rate on x and TP rate on y; the lecture's label is most
  likely shorthand. Worth confirming against the slides.
- p. 4 — `AUC = 0` is written as "no classifier". A classifier with `AUC = 0` is in fact
  a **perfectly inverted** classifier; `AUC = 0.5` is the coin toss. Both readings are
  stated on [[roc-curve]].
- p. 16 — the quality function `Q(t) = 2·k_t·(1 − u_t) / (k_t + (1 − u_t))` is written
  without defining `k_t` and `u_t`; they are glossed only as "clusters in peak" and
  "unspecific items". The harmonic-mean *form* is unambiguous, the operands are not. See
  [[f-measure]].
- p. 19 — the TransClust similarity graph was read edge by edge; the weights used in
  [[M2E04-k-means-and-transclust]] (`0–1 = 5`, `1–2 = 3`, `1–5 = 4`, `5–3 = 9`,
  `5–6 = 3`, `6–3 = 8`, `3–4 = 4`, `4–7 = 8`, `7–8 = 2`, `7–9 = 3`, `4–9 = 5`,
  `4–10 = 10`) should be double-checked against the original matrix.
- p. 20 — the cost sum is written as `(2+1) + 0 + 3 + (3+2) = 11`, but which edge flip
  each term corresponds to is not annotated. The total is reproduced; the decomposition
  is not interpreted.
- p. 3 — bootstrapping is characterised as having **lower variance but larger bias** than
  cross-validation. This is the usual statement for the simple bootstrap error estimate;
  worth confirming that the lecture means the `.632` correction or the plain version.
  See [[bootstrapping]].
- p. 7 — the out-of-bag error is written as `#false predicted / #out of bag`. The
  Loud/Drunk → Victory example beneath it is too small to confirm the numerator; only
  the formula is reproduced in [[random-forest]].

From `raw/module2/csb_3.pdf` (part 3 of 4):

- p. 4 — the weight count for a `3 → 4 → 4 → 4` network is written
  `3·4 + 4·4 + 4·4 = 12 + 16 + 16 = 48`, but that sum is **44**. [[neural-network]]
  reproduces the three products and states **44**, flagging the discrepancy inline.
- p. 25 — the internal-node row of the tree-complexity table appears to read `n−1` under
  *unrooted* and `n−2` under *rooted*, which contradicts the node-count row on the same
  page (`2n−2` unrooted, `2n−1` rooted). [[phylogenetic-tree]] gives the self-consistent
  standard values (`n−2` unrooted, `n−1` rooted) and flags the reading.
- p. 27 — "transitions are more common" is recorded as a fact with **no mechanism**. The
  chemical explanation offered in [[transition-and-transversion]] is marked there as not
  being course content.
- p. 31 — the three-point condition is written `d_ij ≤ d_ik = d_kj`. The index order of
  the two equal terms was read as given; the substantive claim (the two larger of the
  three pairwise distances are equal) is unambiguous either way. See [[molecular-clock]].
- p. 39 — the UPGMA worked example gives the merge order and the matrix updates, but the
  **branch lengths are not written out** on the sheet. Those reported in [[upgma]] and
  [[M2E08-phylogenetics]] were derived from the merge heights and verified against the
  ultrametric property.
- pp. 21–22 — the exercise answers are terse keyword lists. The expanded reasoning in
  [[M2E07-single-cell-rna-seq-and-dimensionality-reduction]] (especially the Scanpy
  thresholding rationale) elaborates the keywords rather than transcribing sentences.
- `raw/module2/csb_4.pdf`, p. 8 — the SPONGE null model solves a **quadratic**
  `(−B ± √(B² − 4AC)) / (2A)` for `r_BZ`, but the coefficients `A`, `B` and `C` are not
  written out and the discriminant notation is partly ambiguous. [[sponge]] and
  [[sensitivity-correlation]] state the constraint the quadratic enforces (`mscor = 0`
  under H₀) rather than reproducing unverified coefficients.
- `raw/module2/csb_4.pdf`, p. 17 — the factor **`α`** in GEDEVO's health-decay formula
  `H_i(t+1) = H_i(t) − (r_i − 0.1) × 0.9 × α` is never defined in the notes. It is
  reproduced verbatim in [[gedevo]] and flagged there.
- `raw/module2/csb_4.pdf`, p. 9 — the regression filter threshold in SPONGE's first step
  is written only as `|·| > threshold`; no value is given. See [[M2L09-non-coding-rnas]].

## Reconciled, but worth checking against the slides
Four contradictions were resolved during the 2026-10-21 lint pass and a fifth during the
2026-10-22 cross-module pass. Both readings are stated on the relevant pages, so nothing
is silently picked; only confirmation against the official slides is still outstanding.

- **PWM log-odds base: `ln(f/π)` (module 1, `raw/module1/gsb_3.pdf`) versus
  `log₂(P/π)` (module 2, `raw/module2/csb_1.pdf`).** Reconciled in
  [[position-weight-matrix]] and [[sequence-motif]]: the two scores differ only by the
  constant factor `1/ln 2`, so they rank sites identically and any threshold transfers by
  rescaling. Bits (`log₂`) are the standard convention and are what
  [[information-content]] and [[sequence-logo]] assume.
- **"98 % no junk" (part 3, p. 20) versus "7–9 % functional" (part 1, p. 3).** Reconciled
  in [[L01-bioinformatics-and-the-cell]] and [[population-genetics]] as two different
  claims: a *constraint-based* estimate (7–9 % under purifying selection) versus a
  *biochemical-activity* claim in the ENCODE sense (most of the genome does something).
  Still unverified: which of the two the lecture intends as *the* functional fraction,
  and the source of the 7–9 % figure.
- **CpG islands at promoters versus "constantly methylated" (part 4, p. 8 vs p. 12).**
  Reconciled in [[cpg-island]], with a cross-reference from [[dna-methylation]]:
  promoter islands are normally **un**methylated, and "constantly methylated" is read as
  "stably maintained through mitosis". Marked as added beyond the notes.
- **Nucleosome DNA length 146 bp (p. 1) versus 160 bp (p. 2).** Reconciled in
  [[chromatin]] as *core-wrapped* (146/147 bp) versus *core + linker* nucleosome repeat
  length (~160–200 bp); 147 bp is the standard single figure. Marked as added beyond the
  notes.
- **Emission on the transition (p. 20) versus emission on the state (pp. 14–15).** Both
  conventions are now documented side by side in [[hidden-markov-model]]
  § *Two emission conventions*, with the recursion written out for each and a note that
  the state-emission form is the bioinformatics standard. [[viterbi-algorithm]] and
  [[forward-algorithm]] point at it from their worked examples.
