---
title: Log
type: overview
module: both
tags: [log]
created: 2026-10-21
updated: 2026-10-22
status: solid
---

# Log

Append-only. Newest entries at the bottom.
Quick timeline: `grep "^## \[" wiki/log.md | tail -5`

## [2026-10-21] refactor | Wiki initialized
- Created `CLAUDE.md` schema, `raw/` and `wiki/` scaffolding
- Created [[index]], [[overview]], [[open-questions]]
- Awaiting first handwritten note scans in `raw/`

## [2026-10-21] ingest | raw/module1/gsb_part1.pdf — Molecular biology foundations, sequencing, genome assembly, expression profiling and algorithmic complexity
- Source: 31 scanned pages, part 1 of 4 of the module 1 (GSB) handwritten summary.
- Created lectures [[L01-bioinformatics-and-the-cell]], [[L02-gene-expression-and-regulation]], [[L03-sequencing-and-genomics]], [[L04-genome-assembly]], [[L05-sequence-comparison-and-networks]], [[L06-expression-profiling]], [[L07-algorithms-and-complexity]]
- Created concepts [[central-dogma]], [[genome-organization]], [[gene-regulation]], [[dna-mutation]], [[de-bruijn-graph]], [[interaction-network]], [[epigenetics]], [[algorithmic-complexity]]
- Created methods [[shotgun-sequencing]], [[next-generation-sequencing]], [[greedy-assembly]], [[de-bruijn-assembly]], [[sequence-alignment]], [[blast]], [[chip-seq]], [[microarray-expression-analysis]], [[rna-seq]], [[boyer-moore-majority-vote]]
- Created exercises [[E01-cell-biology-and-gene-expression]], [[E02-greedy-assembly]], [[E03-de-bruijn-assembly]], [[E04-complexity-and-majority-element]]
- Updated [[index]], [[overview]], [[open-questions]]
- Epigenetics supplemented beyond the notes per `CLAUDE.md` §1, marked with the "Added beyond lecture notes" callout in [[epigenetics]]
- Open question: p. 11 amino-acid sequence under the splicing example not legible; only `AUG` and the presence of a stop codon transcribed
- Open question: p. 17 low-weight overlap-graph edge labels not read with confidence; only the weight-4/3/2 merge edges transcribed
- Open question: p. 28 logarithm base in `3 log₈ n` written ambiguously
- Open question: the "7–9 % functional" human-genome figure on p. 3 is uncited
- Open question: Sanger chemistry, LOESS/RMA normalisation, BLAST scoring matrices, multiple sequence alignment, Eulerian-path selection and the master theorem are referenced but never explained in the notes
- Numbering: parts 2–4 continue at **L08** and **E05**

## [2026-10-21] ingest | raw/module1/gsb_part2.pdf — Exact string matching, sequence alignment and homology, and biostatistics with statistical testing
- Source: 29 scanned pages, part 2 of 4 of the module 1 (GSB) handwritten summary.
- Created lectures [[L08-exact-string-matching]], [[L09-sequence-alignment-and-homology]], [[L10-biostatistics-and-statistical-testing]]
- Created concepts [[string-matching]], [[homology]], [[substitution-matrix]], [[descriptive-statistics]], [[probability-distribution]], [[statistical-testing]]
- Created methods [[knuth-morris-pratt]], [[boyer-moore-string-search]], [[needleman-wunsch]], [[smith-waterman]], [[qq-plot]]
- Created exercises [[E05-kmp-string-matching]], [[E06-boyer-moore-string-search]], [[E07-alignment-and-homology]], [[E08-test-errors-and-z-score]]
- Updated [[sequence-alignment]] into a hub page: four alignment types, pairwise definition, protein-vs-DNA argument, links to the two DP algorithms
- Updated [[blast]] with the BLAST program family table, the G parameter and PAM/BLOSUM scoring
- Updated [[boyer-moore-majority-vote]] with an explicit disambiguation against [[boyer-moore-string-search]]
- Updated [[L05-sequence-comparison-and-networks]], [[L06-expression-profiling]], [[L07-algorithms-and-complexity]], [[algorithmic-complexity]], [[microarray-expression-analysis]], [[rna-seq]], [[next-generation-sequencing]], [[greedy-assembly]], [[central-dogma]], [[genome-organization]], [[gene-regulation]], [[dna-mutation]] with backlinks to the new pages
- Updated [[index]], [[overview]], [[open-questions]]
- Resolved: the part-1 open question on dynamic-programming alignment algorithms — [[needleman-wunsch]] and [[smith-waterman]] are now fully covered, struck through in [[open-questions]]
- Resolved (partly): the part-1 open question on BLAST scoring matrices — PAM/BLOSUM are now in [[substitution-matrix]]; the E-value derivation remains open
- Open question: p. 10 good-suffix table is overwritten and could not be transcribed with confidence
- Open question: p. 26 writes accuracy as `(TP + FN)/n`; the p. 29 example shows the correct `(TP + TN)/n`
- Open question: factor-searching algorithms, semi-global/free-end-gaps initialisation, regression, concrete test statistics and confidence intervals are named but never explained
- Open question: no concrete statistical test and no multiple-testing correction appear anywhere in parts 1–2, although the microarray pipeline depends on both
- Numbering: parts 3–4 continue at **L11** and **E09**

## [2026-10-21] ingest | raw/module1/gsb_3.pdf — Normalization, PCA and batch effects; binding sites and PWMs; suffix trees and arrays; population genetics; GWAS, eQTLs and multiple testing
- Source: 34 scanned pages, part 3 of 4 of the module 1 (GSB) handwritten summary.
- Created lectures [[L11-normalization-pca-and-batch-effects]], [[L12-binding-sites-and-position-weight-matrices]], [[L13-suffix-trees-and-arrays]], [[L14-population-genetics]], [[L15-gwas-eqtl-and-multiple-testing]]
- Created concepts [[data-normalization]], [[batch-effect]], [[transcription-factor-binding-site]], [[population-genetics]], [[genetic-drift]], [[hardy-weinberg-equilibrium]], [[expression-qtl]]
- Created methods [[principal-component-analysis]], [[position-weight-matrix]], [[suffix-tree]], [[suffix-array]], [[wright-fisher-model]], [[haplotype-phasing]], [[genome-wide-association-study]], [[multiple-testing-correction]]
- Created exercises [[E09-binding-sites-pwm-and-pca]], [[E10-suffix-trees-and-arrays]], [[E11-population-genetics-and-multiple-testing]]
- Updated [[E08-test-errors-and-z-score]] with items 3 and 4 of the same sheet: distribution identification (uniform, Poisson, normal, binomial) and the QQ-plot shape table
- Updated [[qq-plot]] with the shape-to-distribution mapping from p. 2
- Updated [[L06-expression-profiling]], [[L08-exact-string-matching]], [[L10-biostatistics-and-statistical-testing]] with the part-3 continuations and strike-through resolutions
- Updated [[descriptive-statistics]], [[probability-distribution]], [[statistical-testing]], [[string-matching]], [[algorithmic-complexity]], [[gene-regulation]], [[dna-mutation]], [[genome-organization]], [[substitution-matrix]], [[chip-seq]], [[microarray-expression-analysis]], [[rna-seq]], [[next-generation-sequencing]], [[knuth-morris-pratt]], [[boyer-moore-string-search]] with backlinks to the new pages
- Updated [[index]], [[overview]], [[open-questions]]
- Resolved: the parts 1–2 open question on **multiple-testing correction** — Bonferroni and Benjamini–Hochberg are now in [[multiple-testing-correction]]; struck through in [[open-questions]], [[L06-expression-profiling]] and [[L10-biostatistics-and-statistical-testing]]
- Resolved: the part-2 open question on **factor-searching algorithms** — [[suffix-tree]] and [[suffix-array]] supply the paradigm; struck through in [[open-questions]] and [[L08-exact-string-matching]]
- Resolved (partly): concrete statistical tests are finally named — Fisher's exact test, the Cochran–Armitage trend test and logistic regression in [[genome-wide-association-study]]; their test statistics are still not given
- Open question: p. 11 PWM exercise sequences and several count-matrix entries are not legible; only the worked pseudo-count value was transcribed
- Open question: p. 15 suffix-array example `lcp` values could not be reconciled with the definition on the same page; the legible `teethermometer$` example was used instead
- Open question: SVD, ComBat and "standardization" are named as batch-correction methods but never described
- Open question: the background score distribution of a PWM is used for thresholding but its computation is never given
- Open question: linear-time suffix-tree construction, natural selection and gene flow, linkage disequilibrium, population-based phasing, Manhattan plots and sequence logos are referenced but not explained
- Open question: p. 20 records "98 % no junk — functionality discovered", which conflicts in emphasis with the part-1 "7–9 % functional" figure
- Numbering: part 4 continues at **L16** and **E12**

## [2026-10-21] ingest | raw/module1/gsb_part4.pdf — epigenetics (chromatin, histone marks, DNA methylation, peak calling, bisulfite-seq, EWAS) and Markov chains / hidden Markov models

- Source: 20 scanned pages, part 4 of 4 — the final part of the module 1 (GSB) handwritten summary. Module 1 is now completely ingested.
- Created lectures [[L16-epigenetics]], [[L17-markov-chains-and-hidden-markov-models]]
- Created concepts [[chromatin]], [[histone-modification]], [[dna-methylation]], [[cpg-island]], [[markov-chain]], [[hidden-markov-model]]
- Created methods [[peak-calling]], [[bisulfite-sequencing]], [[epigenome-wide-association-study]], [[forward-algorithm]], [[viterbi-algorithm]], [[baum-welch-algorithm]]
- Created exercises [[E12-epigenetics-and-peak-calling]] (GSB-Ex 10, pp. 10–12), [[E13-markov-chains-and-viterbi]] (GSB-Ex 11, pp. 19–20)
- Updated [[epigenetics]] — rewritten from a stub-like draft into the hub of the epigenetics cluster, status draft → solid; the "Added beyond lecture notes" callout was cut back to the three items part 4 still does not cover
- Updated [[chip-seq]] with the peak-calling continuation, the German ChIP gloss, the quality-measure pointer and the part-4 lecture/exercise backlinks
- Updated [[gene-regulation]], [[genome-organization]], [[probability-distribution]], [[statistical-testing]], [[multiple-testing-correction]], [[transcription-factor-binding-site]], [[next-generation-sequencing]], [[genome-wide-association-study]], [[batch-effect]], [[sequence-alignment]], [[position-weight-matrix]], [[algorithmic-complexity]], [[needleman-wunsch]], [[blast]], [[L05-sequence-comparison-and-networks]] with backlinks to the new pages and part-4 source lines
- Updated [[index]], [[overview]] (module 1 section rewritten as a complete L01–L17 / E01–E13 map with a new module-structure diagram and an eleventh theme), [[open-questions]]
- Resolved: the long-standing **epigenetics** gap — DNA methylation, chromatin states and imprinting are all covered by the notes themselves now; struck through in [[open-questions]]. Only the functional meaning of individual histone marks and the DNMT1 maintenance mechanism are still supplied from outside the notes.
- Open question: p. 19 dinucleotide probability table is not legible; only the marginals and the two worked transition probabilities were transcribed
- Open question: p. 20 Viterbi trellis is filled in only for the first column; columns 2–3 were derived, not read
- Open question: nucleosome DNA length is given as 146 bp on p. 1 and 160 bp on p. 2
- Open question: CpG islands are described both as promoter-associated and as "constantly methylated", which conflicts with CpG-poor promoters being the methylation-silenced ones
- Open question: the Baum–Welch step is written as plain counting (Viterbi training) rather than expected counts; the backward recursion is never written out
- Open question: no concrete test is named for the per-site DMR comparison; MACS2 fragment-length estimation, ATAC-Seq, the imprinting mechanism and profile-HMM construction from an MSA are referenced but not explained
- Open question: p. 20 attaches emission probabilities to transitions, p. 14–15 attach them to states; both conventions are documented
- Numbering: module 1 ends at **L17** and **E13**; module 2 has not been started

## [2026-10-21] lint | Full wiki health check after module 1 ingest

**Checked** (mechanical, by script over all `wiki/**/*.md`): dead wikilinks, orphan
pages, one-directional links, YAML frontmatter presence and required keys, `index.md`
drift against disk, method pages missing `​```text` pseudocode, pages missing
`## Sources`, unbalanced code fences, unquoted Mermaid labels, `status: stub`, and pages
with no diagram. **Checked** (semantic, by reading): contradictions, duplicated
material, recurring terms without a page, processes lacking a diagram, and the
epigenetics coverage gaps of `CLAUDE.md` §1.

**Found and fixed**
- **Dead links** 0 → 0. **Malformed/missing frontmatter** 0. **Stubs** 0. **Unbalanced
  fences** 0.
- **One-directional links**: 461 → 0 (150 after excluding the catalog hubs
  [[index]]/[[log]]/[[overview]]/[[open-questions]], which legitimately link outward
  only). 231 reciprocal links added across all four folders, each with a one-line
  statement of *how* the pages relate, per `CLAUDE.md` §8.6.
- **Orphan pages**: [[log]] was unreachable — now listed in [[index]] under a new *Meta*
  group and in the [[overview]] *See also*.
- **Mermaid**: 6 unquoted labels in [[overview]] and 15 unquoted edge labels in
  [[L02-gene-expression-and-regulation]], [[E02-greedy-assembly]] and
  [[E03-de-bruijn-assembly]] would have broken rendering in Obsidian; all now quoted.
  107 blocks verified clean.
- **Missing diagrams**: 25 pages had none. Added 18 to method pages (BLAST seed-and-
  extend, MACS2, the DP cell for [[needleman-wunsch]]/[[smith-waterman]], the KMP and
  Boyer–Moore shift loops, the forward and Viterbi trellis cells, the sequencing and
  assembly pipelines, QQ-plot shapes, the majority-vote state machine) and 7 to exercise
  sheets, each with a one-sentence caption.
- **index.md drift**: 8 files on disk were unlisted; all added with summaries and the
  `*(module, status)*` suffix.

**Contradictions reconciled** (both readings kept on the page, standard reading named)
- "98 % no junk" (part 3) versus "7–9 % functional" (part 1) — separated into a
  biochemical-activity claim and a constraint-based estimate, on
  [[L01-bioinformatics-and-the-cell]] and [[population-genetics]].
- CpG islands at promoters versus "constantly methylated" — reconciled on [[cpg-island]],
  now cross-referenced from [[dna-methylation]] and [[L16-epigenetics]].
- Nucleosome DNA 146 bp versus 160 bp — core-wrapped versus core + linker, on
  [[chromatin]].
- Emission-on-transition versus emission-on-state — new § *Two emission conventions* on
  [[hidden-markov-model]], with both recursions written out and pointers from
  [[viterbi-algorithm]] and [[forward-algorithm]].

**Duplication removed** (canonical page kept, other reduced to a summary + wikilink)
- The full DP pseudocode and the `ACGT`/`AGT` worked matrix were on both
  [[sequence-alignment]] and [[needleman-wunsch]] → the hub page now carries only the
  shared recurrence skeleton.
- The BLAST program-family table and the substitution-matrix/gap-penalty tables were
  duplicated on [[L09-sequence-alignment-and-homology]] → reduced to bullets pointing at
  [[blast]] and [[substitution-matrix]].
- The confusion-matrix formulas and α trade-off were duplicated on
  [[L10-biostatistics-and-statistical-testing]] → reduced to bullets pointing at
  [[statistical-testing]].

**Pages created** (8) — terms used across many pages but with no page of their own:
[[dynamic-programming]], [[hamiltonian-and-eulerian-paths]], [[promoter]],
[[genetic-code]], [[splicing]], [[snp]], [[z-score]], and [[atac-seq]].

**Epigenetics supplemented** per `CLAUDE.md` §1, every addition inside an
"Added beyond lecture notes" callout: the **ATAC-Seq assay** ([[atac-seq]], named but
never described in the notes), the **imprinting mechanism** — erasure, establishment at
ICRs by DNMT3A/3B, maintenance by DNMT1, reading by CTCF, plus XIST for X inactivation
([[dna-methylation]]) — and the **candidate per-site DMR tests** (Fisher's exact,
beta-binomial regression, smoothing, then FDR) in [[bisulfite-sequencing]].

**Still open** — [[open-questions]] was pruned of resolved items and reorganised with a
new *Reconciled, but worth checking against the slides* section. Genuinely open:
all ten illegible-handwriting passages; Sanger chemistry, LOESS/RMA, the E-value
extreme-value derivation and PAM/BLOSUM construction, multiple sequence alignment,
Eulerian-path selection, the master theorem, yeast two-hybrid/co-IP, concrete test
statistics and confidence intervals, SVD/ComBat, the PWM background score distribution,
Ukkonen construction, natural selection and gene flow, linkage disequilibrium,
population-based phasing, Manhattan plots and sequence logos, histone-mark inheritance,
the backward recursion, MACS2 fragment-length estimation and profile-HMM construction.
`index.md`, `log.md` and `open-questions.md` intentionally carry no `## Sources`
section — they are catalogs, not content pages.

## [2026-10-22] ingest | raw/module2/csb_1.pdf — Enrichment analysis, KeyPathwayMiner, sequence motifs and motif discovery

First source of **module 2** (CSB). 27 handwritten pages covering two lectures and two
exercises. Module 2 opens its own lecture/exercise namespace (`M2L##` / `M2E##`,
`module: 2`) while sharing `wiki/concepts/` and `wiki/methods/` with module 1.

**Created — lectures (2)**
- [[M2L01-enrichment-analysis]] (pp. 1–9) — the workflow from experimental design to
  functional groups; gene sets, networks and pathways; Gene Ontology; the two-class,
  time-course and linear-model designs; Fisher versus GSEA; de novo network enrichment.
- [[M2L02-sequence-motifs-and-motif-discovery]] (pp. 14–22) — motifs, their four
  representations and the logo; the planted motif problem; EM, MEME and Gibbs sampling.

**Created — exercises (2)**
- [[M2E01-enrichment-analysis-and-keypathwayminer]] (pp. 10–13) — with the full 11×5
  indicator matrix, the derived activity sets for `L = 1` and `L = 3`, and the
  INE/GLONE verdicts.
- [[M2E02-motif-discovery-and-expectation-maximization]] (pp. 23–27) — with the GC
  likelihood table and the complete first EM iteration.

**Created — concepts (7)**
- [[gene-set]], [[gene-ontology]], [[sequence-motif]], [[information-content]],
  [[gene-knockout]], [[planted-motif-problem]], [[travelling-salesman-problem]]

**Created — methods (9)**
- [[enrichment-analysis]], [[fishers-exact-test]], [[gene-set-enrichment-analysis]],
  [[keypathwayminer]], [[ant-colony-optimization]], [[sequence-logo]],
  [[expectation-maximization]], [[em-motif-discovery]], [[gibbs-sampling]]

**Updated — hub files**
- [[overview]] — Module 2 section filled with four numbered strands and a structure
  diagram; three new Themes (*Functional interpretation*, *Latent variables and
  iterative estimation*, *Metaheuristics for intractable search*); Motif models extended.
- [[index]] — 20 new entries; Lectures and Exercises subdivided into Module 1 / Module 2.
- [[open-questions]] — new blocks under all three sections for this source.

**Updated — existing pages (cross-links made bidirectional)**
- Promoted to `module: both`: [[interaction-network]],
  [[transcription-factor-binding-site]], [[statistical-testing]], [[cpg-island]],
  [[hamiltonian-and-eulerian-paths]], [[algorithmic-complexity]],
  [[position-weight-matrix]], [[multiple-testing-correction]],
  [[microarray-expression-analysis]], [[baum-welch-algorithm]], [[rna-seq]].
- Module-2 sections added to [[interaction-network]] (the network as a search space),
  [[transcription-factor-binding-site]] (finding sites de novo),
  [[position-weight-matrix]] (the PCM/PPM/PWM hierarchy),
  [[microarray-expression-analysis]] and [[rna-seq]] (what happens next).
- Reciprocal relation bullets added to [[genome-wide-association-study]],
  [[L12-binding-sites-and-position-weight-matrices]],
  [[E09-binding-sites-pwm-and-pca]], [[batch-effect]], [[data-normalization]],
  [[principal-component-analysis]], [[bisulfite-sequencing]], [[central-dogma]],
  [[chip-seq]], [[de-bruijn-assembly]], [[greedy-assembly]], [[gene-regulation]],
  [[hidden-markov-model]], [[homology]], [[markov-chain]],
  [[probability-distribution]], [[qq-plot]], [[sequence-alignment]],
  [[string-matching]], [[substitution-matrix]].

**Resolved from module 1**
- ~~sequence logo named without any description of its axes or construction~~ — now
  fully constructed in [[sequence-logo]] with [[information-content]].
- ~~not a single concrete test statistic is given~~ — partly resolved:
  [[fishers-exact-test]] gives a complete, usable formula; the t-test and Pearson
  correlation are named as ranking statistics. The Manhattan plot remains undescribed.

**Open questions recorded**
- Illegible: the GLONE `B = 3` versus `4` conflict (p. 13), the unreadable GLONE blob
  memberships, the struck-through wording on p. 10.
- Missing: k-means, Pearson correlation and linear models, the ACO transition and
  pheromone formulae, the ES contribution magnitudes, combinatorial motif approaches,
  pathway scoring, KPM candidate enumeration, and every convergence criterion.
- To verify: the leading minus sign on the p. 16 relative entropy; three arithmetic
  failures in the p. 26 EM iteration (row 5 reuses row 4, row 3 uses rounded
  likelihoods, and the reported `Θ_A¹`/`Θ_B¹` cannot be reproduced); whether the
  p. 5 Fisher p-value is the point probability or the one-sided sum; the p. 12 edge list;
  the missing pseudo-count formula on p. 15.

**Next free module-2 numbers: M2L03 and M2E03.**

## [2026-10-22] ingest | raw/module2/csb_part2.pdf — Machine learning, clustering and network-based disease modules

Part 2 of 4 of the module-2 (CSB) handwritten summary, 25 pages. Three lectures
(α3, α4, α5 in the notes) with their exercise sheets: supervised classification and how
to evaluate it honestly, unsupervised clustering, and the combination of the two under a
network constraint.

**Created — lectures**
- [[M2L03-machine-learning-and-classification]] (pp. 1–8)
- [[M2L04-clustering]] (pp. 12–16)
- [[M2L05-network-based-disease-modules]] (pp. 21–23)

**Created — exercises**
- [[M2E03-machine-learning-and-classification]] (pp. 9–11)
- [[M2E04-k-means-and-transclust]] (pp. 17–20)
- [[M2E05-grandforest-and-bicon]] (pp. 24–25)

**Created — concepts**
- [[machine-learning]], [[overfitting]], [[node-impurity]], [[cluster-analysis]],
  [[f-measure]], [[endophenotype]], [[kaplan-meier-plot]]

**Created — methods**
- [[cross-validation]], [[bootstrapping]], [[roc-curve]], [[decision-tree]],
  [[random-forest]], [[support-vector-machine]], [[k-means]], [[transclust]],
  [[grandforest]], [[bicon]]

**Updated**
- [[index]] — 23 new entries; [[overview]] — Module 2 section extended with items 5–7, a
  second structure diagram, three new themes (supervised learning and honest evaluation,
  unsupervised structure discovery, network-constrained patient stratification), and
  part 2 marked ingested.
- Reciprocal relation and *Appears in* bullets added to [[statistical-testing]],
  [[E08-test-errors-and-z-score]], [[E11-population-genetics-and-multiple-testing]],
  [[M2E01-enrichment-analysis-and-keypathwayminer]], [[M2L01-enrichment-analysis]],
  [[interaction-network]], [[keypathwayminer]], [[ant-colony-optimization]],
  [[algorithmic-complexity]], [[hamiltonian-and-eulerian-paths]],
  [[principal-component-analysis]], [[expectation-maximization]],
  [[information-content]], [[position-weight-matrix]], [[peak-calling]],
  [[multiple-testing-correction]], [[probability-distribution]],
  [[descriptive-statistics]], [[batch-effect]], [[population-genetics]],
  [[expression-qtl]], [[enrichment-analysis]], [[gene-set-enrichment-analysis]],
  [[microarray-expression-analysis]], [[rna-seq]].

**Resolved from part 1**
- ~~k-means is named as the clustering example but never described~~ — now a full method
  page, [[k-means]], with pseudocode, the elbow method and a three-iteration worked
  example.

**Open questions recorded**
- Illegible: the blank k-means distance matrix (p. 17), the scribbled-over left cluster
  and the untranscribed 55-pair enumeration in the TransClust exercise (p. 20), the
  crossed-out word above BiCoN's title (p. 23).
- Missing: neural networks and linear regression (named only); the SVM quadratic
  program, dual, kernels and soft margins; GrandForest's splitting rule and background
  generation; BiCoN's objective function; density-, model- and hierarchical clustering;
  the rule for picking the elbow; convergence criteria for k-means, TransClust and BiCoN.
- To verify: the ROC x-axis labelled `spec` on p. 4 versus FP rate on p. 10; `AUC = 0`
  called "no classifier"; the undefined `k_t` and `u_t` in `Q(t)` on p. 16; the
  TransClust edge weights on p. 19; the undecomposed cost sum on p. 20; the
  lower-variance/larger-bias claim for the bootstrap on p. 3; the OOB numerator on p. 7.

**Next free module-2 numbers: M2L06 and M2E06.**

## [2026-10-22] ingest | raw/module2/csb_3.pdf — Deep learning, single-cell RNA-Seq, molecular evolution and phylogeny

Part 3 of 4 of the module-2 handwritten summary, 39 pages. Three lectures and three
exercises: **M2L06 / M2E06** deep learning (pp. 1–11), **M2L07 / M2E07** single-cell
RNA-Seq (pp. 12–22), **M2L08 / M2E08** molecular evolution and phylogeny (pp. 23–39).

**Created — lectures**
- [[M2L06-deep-learning]], [[M2L07-single-cell-rna-seq]],
  [[M2L08-molecular-evolution-and-phylogeny]]

**Created — exercises**
- [[M2E06-deep-learning]], [[M2E07-single-cell-rna-seq-and-dimensionality-reduction]],
  [[M2E08-phylogenetics]]

**Created — concepts (20)**
- Deep learning: [[deep-learning]], [[activation-function]], [[cost-function]],
  [[pooling-layer]], [[dropout]], [[bias-variance-tradeoff]],
  [[recurrent-neural-network]], [[graph-neural-network]]
- Single cell: [[droplet-based-single-cell-methods]], [[barcode-collision]], [[doublet]],
  [[unique-molecular-identifier]], [[highly-variable-genes]],
  [[single-cell-analysis-workflow]]
- Phylogeny: [[molecular-evolution]], [[phylogenetic-tree]],
  [[gene-tree-and-species-tree]], [[evolutionary-distance]],
  [[transition-and-transversion]], [[molecular-clock]]

**Created — methods (16)**
- [[neural-network]], [[gradient-descent]], [[backpropagation]],
  [[convolutional-neural-network]], [[autoencoder]], [[generative-adversarial-network]]
- [[single-cell-rna-seq]], [[t-sne]], [[umap]]
- [[jukes-cantor-model]], [[kimura-two-parameter-model]], [[upgma]],
  [[neighbor-joining]], [[maximum-parsimony]], [[phylogenetic-tree-reconstruction]],
  [[bootstrap-tree-assessment]]

**Updated**
- [[homology]] — extended with the in-paralog / out-paralog / co-ortholog hierarchy from
  p. 35.
- 57 existing pages given reciprocal `Relations` bullets, `raw/module2/csb_3.pdf` added
  to their frontmatter `sources` and `## Sources`, and `module: both` set where the page
  now genuinely serves both modules: [[machine-learning]], [[overfitting]],
  [[cross-validation]], [[bootstrapping]], [[random-forest]], [[decision-tree]],
  [[support-vector-machine]], [[roc-curve]], [[cluster-analysis]], [[k-means]],
  [[transclust]], [[principal-component-analysis]], [[batch-effect]],
  [[data-normalization]], [[rna-seq]], [[microarray-expression-analysis]],
  [[next-generation-sequencing]], [[splicing]], [[gene-regulation]], [[gene-set]],
  [[enrichment-analysis]], [[endophenotype]], [[grandforest]], [[bicon]],
  [[keypathwayminer]], [[interaction-network]], [[de-bruijn-graph]],
  [[hamiltonian-and-eulerian-paths]], [[travelling-salesman-problem]],
  [[ant-colony-optimization]], [[algorithmic-complexity]], [[dynamic-programming]],
  [[needleman-wunsch]], [[sequence-alignment]], [[blast]], [[substitution-matrix]],
  [[dna-mutation]], [[snp]], [[cpg-island]], [[genetic-drift]], [[population-genetics]],
  [[genome-organization]], [[markov-chain]], [[hidden-markov-model]],
  [[baum-welch-algorithm]], [[viterbi-algorithm]], [[expectation-maximization]],
  [[position-weight-matrix]], [[sequence-motif]], [[sequence-logo]],
  [[information-content]], [[descriptive-statistics]], [[probability-distribution]],
  [[statistical-testing]], [[multiple-testing-correction]],
  [[M2L03-machine-learning-and-classification]].
- [[overview]] — Module 2 extended with items 8–10, a third structure diagram, and four
  new themes (learned representations; resolution of measurement; dimensionality
  reduction and visualization; reconstructing history).
- [[index]], [[open-questions]].

**Open questions resolved**
- ~~Neural networks named but never specified~~ — fully answered by pp. 1–9.
- ~~Linear regression named without a formula~~ — partly answered by p. 1
  (`f(X) = β₀ + β₁X₁ + …`); the least-squares derivation is still missing.

**Open questions recorded**
- Illegible: the inDrops branch of the platform decision tree (p. 15); the overwritten
  GC-bias and transition/transversion matrices (p. 37).
- Missing: faster optimisers than gradient descent (unnamed, p. 5); RNN / attention /
  transformer equations and the GNN message-passing rule (p. 8); diffusion components
  and force-directed layouts (p. 17); the Jukes–Cantor distance formula itself (p. 28);
  minimal evolution, maximum likelihood and Felsenstein (pp. 30, 37); the topology
  search inside maximum parsimony (p. 33).
- To verify: the weight count `= 48` that should be **44** (p. 4); the internal-node row
  of the tree-complexity table (p. 25); the missing mechanism for the transition excess
  (p. 27); the index order in the three-point condition (p. 31); the branch lengths
  derived rather than transcribed in the UPGMA example (p. 39).

**Next free module-2 numbers: M2L09 and M2E09.**

## [2026-10-22] ingest | raw/module2/csb_4.pdf — Non-coding RNAs and network alignment

Part 4 of 4 of the module-2 handwritten summary, 19 pages, and the **last source in the
collection**. Two lectures: non-coding RNAs (pp. 1–9, exercise p. 10) and network
alignment (pp. 11–17, exercise pp. 18–19). Module 2 is now complete at **M2L01–M2L10**
and **M2E01–M2E10**; both modules are fully ingested.

**Created**
- Lectures: [[M2L09-non-coding-rnas]], [[M2L10-network-alignment]].
- Exercises: [[M2E09-non-coding-rnas-and-sponge]], [[M2E10-network-alignment]].
- Concepts: [[non-coding-rna]], [[rna-interference]], [[microrna]],
  [[small-interfering-rna]], [[competing-endogenous-rna]], [[mutual-information]],
  [[sensitivity-correlation]], [[network-alignment]], [[graph-edit-distance]],
  [[graphlet-degree-signature-distance]].
- Methods: [[crispr-cas9]], [[mirna-target-prediction]], [[sponge]], [[cytomcs]],
  [[evolutionary-algorithm]], [[gedevo]].

**Updated**
- Backlinks, `sources` and `updated` on 53 existing pages: [[central-dogma]],
  [[epigenetics]], [[gene-regulation]], [[genome-organization]], [[rna-seq]],
  [[batch-effect]], [[data-normalization]], [[enrichment-analysis]], [[gene-knockout]],
  [[interaction-network]], [[keypathwayminer]], [[microarray-expression-analysis]],
  [[multiple-testing-correction]], [[principal-component-analysis]],
  [[single-cell-analysis-workflow]], [[statistical-testing]], [[t-sne]], [[umap]],
  [[homology]], [[sequence-motif]], [[transcription-factor-binding-site]],
  [[fishers-exact-test]], [[gene-set-enrichment-analysis]], [[information-content]],
  [[descriptive-statistics]], [[algorithmic-complexity]],
  [[hamiltonian-and-eulerian-paths]], [[needleman-wunsch]], [[sequence-alignment]],
  [[smith-waterman]], [[transclust]], [[travelling-salesman-problem]],
  [[evolutionary-distance]], [[substitution-matrix]], [[blast]], [[dna-mutation]],
  [[genetic-code]], [[string-matching]], [[chip-seq]], [[cross-validation]],
  [[machine-learning]], [[position-weight-matrix]], [[roc-curve]], [[suffix-array]],
  [[ant-colony-optimization]], [[k-means]], [[bicon]], [[expectation-maximization]],
  [[molecular-evolution]], [[L16-epigenetics]],
  [[M2L03-machine-learning-and-classification]].
- [[overview]] — Module 2 rewritten to a finished state: items 11–12, a fourth structure
  diagram for M2L09/M2L10, two new themes (regulation carried by RNA; comparing networks
  instead of sequences), and the source list closed out at part 4 of 4.
- [[index]], [[open-questions]].

**Open questions resolved**
- None. Part 4 opens new threads rather than closing earlier ones.

**Open questions recorded**
- Illegible: the final stage of the PAR-CLIP machine-learning pipeline (p. 5); the
  graphlet degree table for orbits 0–14 in exercise 2b (p. 19); the third GEDEVO
  termination criterion, cut off at the page edge (p. 17).
- Missing: the elastic net penalty and fitting procedure (p. 10); methodological detail
  for miRanda, TargetScan, miRcode, miRBase and CLIP-Seq/PAR-CLIP (pp. 4–5, 9); the
  exact mutation rates of GEDEVO's four offspring strategies (p. 17).
- To verify: the coefficients `A`, `B`, `C` of the quadratic solved for `r_BZ` in the
  SPONGE null model (p. 8); the undefined factor `α` in GEDEVO's health decay (p. 17);
  the unspecified regression filter threshold in SPONGE's first step (p. 9).

**All sources ingested. No free module-2 numbers remain to be allocated; the next
lecture would be M2L11 and the next exercise M2E11.**
## [2026-10-22] lint | Full wiki health check after module 2 ingest

First lint pass covering **both** modules together (204 pages). Module 1 had been linted
on 2026-10-21; module 2 had never been linted, and the module 1 ↔ module 2 seam had
never been reviewed as a whole.

**Checked** (mechanically, over `wiki/**/*.md`): dead wikilinks; orphan pages;
one-directional links; YAML frontmatter presence and required keys; `index.md` drift in
both directions; method pages without a `text` pseudocode block; pages without
`## Sources`; unbalanced code fences; Mermaid node labels with unquoted punctuation and
invalid diagram headers; `status: stub`; pages without any diagram; `module:`
frontmatter against the page's own `raw/` citations; and the number of cross-module
bridge links. Semantically: duplication across the two modules, contradictions, missing
term pages, missing bridge links, missing diagrams, epigenetics coverage and stale
`status` values.

**Fixed**
- **100 one-directional links → 0.** 46 pages gained reciprocal bullets; 8 bullets whose
  prose described the wrong side of the relation were rewritten by hand.
- **75 invented source lines removed.** An earlier agent had bulk-added generic
  `- raw/moduleN/x.pdf — module N cross-reference` lines to ~60 pages — a `CLAUDE.md`
  §8.2 violation. All removed, every page's `sources:` frontmatter recomputed from the
  real citations in its `## Sources` body.
- **`module:` frontmatter put on a single rule**: derived from the page's own `raw/`
  citations (module1 only → `1`, module2 only → `2`, both → `both`). Link-based
  rules conflate "taught here" with "forward-referenced from here". 16 pages retagged;
  34 stale `*(module, status)*` suffixes in `index.md` resynced.
- **29 pages gained a Mermaid diagram** with a one-sentence caption (15 ML/phylogeny
  method pages, 14 module-2 exercise and classifier pages). 229 diagrams now validate;
  pages with no diagram: 1 (`open-questions`, intentional).
- **Duplication merged across 7 clusters** — motifs/PWMs, statistical testing vs
  enrichment, dimensionality reduction, networks, HMM vs EM, bulk vs single-cell
  expression, clustering vs classification. One canonical page per topic; the other side
  reduced to a summary plus a pointer, with both modules' lectures aimed at the canonical
  page.
- **Contradiction reconciled**: the PWM log-odds base (module 1 `ln(f/pi)` vs module 2
  `log2(P/pi)`) — documented on [[position-weight-matrix]] as differing by `1/ln 2`,
  rank-identical, with bits as the standard. Four earlier contradictions re-verified as
  still correctly documented.
- **Bridge links 28 → 52 shared concept/method pages**, and 10 → 11 direct cross-module
  lecture links. The two modules now form one connected graph rather than two clusters.
- **1 page created**: [[maximum-likelihood]], the principle shared by
  [[baum-welch-algorithm]], [[em-motif-discovery]] and phylogenetic model fitting.
- **Epigenetics supplemented** per `CLAUDE.md` §1 on 8 pages, every addition inside an
  *Added beyond lecture notes* callout.
- **[[overview]]** gained a *How the two modules relate* section with a seam diagram;
  **[[index]]** resynced and completed; **[[open-questions]]** pruned of resolved items.
- `status`: 3 complete pages lifted `draft → solid`; 0 stubs remain.

**Conventions settled**
- `## See also` is the cross-reference section on lecture and exercise pages (16 pages
  already used it); `## Relations` and `## Appears in` stay as in `CLAUDE.md` §3 for
  concept and method pages.
- `module:` is ground-truthed from `raw/` citations, never from inbound links.

**Still open** — all tracked in [[open-questions]]: illegible passages in the scans
(good-suffix table, graphlet orbit table, GEDEVO's third termination criterion), topics
named but never explained in the notes (Sanger chemistry, LOESS/RMA, master theorem,
multiple sequence alignment, SVM dual, BLAST extreme-value statistics), and undefined
symbols to check against the official slides (GEDEVO's `alpha`, SPONGE's threshold and
quadratic coefficients). `index.md` is the only page with no `raw/` citation, by
design.
