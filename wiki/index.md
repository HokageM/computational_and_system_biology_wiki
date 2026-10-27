---
title: Index
type: overview
module: both
tags: [index]
created: 2026-10-21
updated: 2026-10-22
status: solid
---

# Index

Catalog of every page in this wiki. Updated on every ingest.

## Overview
- [[overview]] — map of both UHH Computational & Systems Biology modules; module 1 complete (L01–L17, E01–E13) and module 2 complete (M2L01–M2L10, M2E01–M2E10). *(both, solid)*

## Lectures

### Module 1
- [[L01-bioinformatics-and-the-cell]] — what bioinformatics is, the three levels of biological information, and the cell and genome it studies. *(module 1, solid)*
- [[L02-gene-expression-and-regulation]] — gene expression, microarrays, the prokaryotic operon and eukaryotic transcriptional control. *(module 1, solid)*
- [[L03-sequencing-and-genomics]] — genomics, Sanger vs NGS, sequencing by synthesis, bias, and the mapping/alignment/assembly vocabulary. *(module 1, solid)*
- [[L04-genome-assembly]] — assembly as a graph problem: overlap graphs, Hamiltonian vs Eulerian paths, and graph artifacts. *(module 1, solid)*
- [[L05-sequence-comparison-and-networks]] — alignment axes, gaps, BLAST and E-values, structural mutations, ChIP-Seq and interaction networks. *(module 1, solid)*
- [[L06-expression-profiling]] — microarray normalisation and RNA-Seq, from fluorescence intensities to count matrices. *(module 1, solid)*
- [[L07-algorithms-and-complexity]] — algorithms, correctness, O/Ω/Θ bounds, dynamic programming and divide and conquer. *(module 1, solid)*
- [[L08-exact-string-matching]] — the exact matching problem, the four search paradigms, KMP and Boyer–Moore compared. *(module 1, solid)*
- [[L09-sequence-alignment-and-homology]] — alignment types, homology vocabulary, Needleman–Wunsch and Smith–Waterman, scoring matrices and the BLAST program family. *(module 1, solid)*
- [[L10-biostatistics-and-statistical-testing]] — data types, descriptive statistics, distributions, hypotheses, errors, p-values and significance levels. *(module 1, solid)*
- [[L11-normalization-pca-and-batch-effects]] — log transform and z-scores, PCA as projection and quality control, and the batch effects normalization cannot remove. *(module 1, solid)*
- [[L12-binding-sites-and-position-weight-matrices]] — transcription-factor binding sites, PWM construction with pseudo-counts, log-odds scoring, thresholds and lookahead scanning. *(both, solid)*
- [[L13-suffix-trees-and-arrays]] — indexing the text instead of the pattern: suffix-tree construction, PWM scoring on the tree, and the suffix array with its lcp and skp columns. *(module 1, solid)*
- [[L14-population-genetics]] — allele frequencies, the Wright–Fisher model and genetic drift, population structure, phasing and the Hardy–Weinberg principle. *(module 1, solid)*
- [[L15-gwas-eqtl-and-multiple-testing]] — SNP coding and linkage, Fisher and Cochran–Armitage tests, quantitative traits and eQTLs, FWER versus FDR. *(module 1, solid)*
- [[L16-epigenetics]] — chromatin and its two mark types, ChIP-Seq with MACS2 peak calling, DNA methylation and bisulfite sequencing, and the EWAS design. *(module 1, solid)*
- [[L17-markov-chains-and-hidden-markov-models]] — Markov chains, hidden Markov models, and the three problems solved by the forward, Baum–Welch and Viterbi algorithms. *(module 1, solid)*

### Module 2
- [[M2L01-enrichment-analysis]] — from differentially expressed genes to biological meaning: gene sets, Gene Ontology, Fisher versus GSEA, and de novo network enrichment. *(module 2, solid)*
- [[M2L02-sequence-motifs-and-motif-discovery]] — sequence motifs, their four representations and the logo, then de novo discovery by EM, MEME and Gibbs sampling. *(module 2, solid)*
- [[M2L03-machine-learning-and-classification]] — learning instead of programming, the defences against overfitting, and three classifiers: decision tree, random forest, SVM. *(module 2, solid)*
- [[M2L04-clustering]] — unsupervised structure discovery: the five clustering families, k-means, TransClust, and evaluation by the F-measure. *(module 2, solid)*
- [[M2L05-network-based-disease-modules]] — GrandForest and BiCoN: machine learning constrained by an interaction network, yielding de novo endophenotypes. *(module 2, solid)*
- [[M2L06-deep-learning]] — machine learning as curve fitting, scaled up: neurons, cost, gradient descent, backpropagation, and the CNN/autoencoder/RNN/GNN/GAN architectures. *(module 2, solid)*
- [[M2L07-single-cell-rna-seq]] — from bulk averages to one cell at a time: droplets, barcodes, UMIs, doublets, and the seven-step analysis workflow ending in t-SNE and UMAP. *(module 2, solid)*
- [[M2L08-molecular-evolution-and-phylogeny]] — trees, tree counting, substitution models, and reconstruction by UPGMA, Neighbor-Joining and maximum parsimony. *(module 2, solid)*
- [[M2L09-non-coding-rnas]] — RNA interference, miRNA and siRNA, CRISPR–Cas9, target prediction, and ceRNA networks inferred by SPONGE. *(module 2, solid)*
- [[M2L10-network-alignment]] — aligning networks instead of sequences: MCES, NP-hardness, CytoMCS by local search and GEDEVO by evolutionary search. *(module 2, solid)*

## Concepts
- [[central-dogma]] — information flow from DNA through mRNA to protein, including splicing and the genetic code. *(both, solid)*
- [[genetic-code]] — mRNA read as non-overlapping triplets from `AUG` to a stop codon, and the redundancy that makes protein comparison more informative than DNA. *(both, solid)*
- [[splicing]] — removal of introns and joining of exons into mature mRNA, and the spliced alignment it forces on RNA-Seq. *(module 1, solid)*
- [[genome-organization]] — chromosomes, genes, exons and introns, and the prokaryote/eukaryote contrast with quantitative figures. *(both, solid)*
- [[gene-regulation]] — operons, promoters, operators and enhancers; positive and negative control of transcription. *(both, solid)*
- [[promoter]] — the RNA-polymerase binding element of a transcription unit, and everything that acts on it: operators, enhancers, transcription factors and methylation. *(module 1, solid)*
- [[dna-mutation]] — deletion, duplication, inversion, insertion and translocation, and what each does depending on where it falls. *(both, solid)*
- [[de-bruijn-graph]] — k-mer graph whose Eulerian traversal reconstructs a sequence, plus its spurs, bubbles, cycles and frayed ropes. *(module 1, solid)*
- [[hamiltonian-and-eulerian-paths]] — nodes-once versus edges-once traversal, the NP-hard/polynomial divide that decides which assembler is usable. *(both, solid)*
- [[interaction-network]] — binary versus co-complex representations of the molecular interactome. *(both, solid)*
- [[epigenetics]] — heritable regulation without sequence change; histone marks, DNA methylation and chromatin state. *(both, solid)*
- [[chromatin]] — the DNA–protein packaging of the genome: nucleosomes, euchromatin versus heterochromatin, interphase and prometaphase. *(module 1, solid)*
- [[histone-modification]] — covalent marks on histone tails, their writers, erasers and readers, and the nucleosome-exchange mechanisms. *(module 1, solid)*
- [[dna-methylation]] — 5-methylcytosine in the CpG context: imprinting, X inactivation, and opposite effects at promoters and in gene bodies. *(module 1, solid)*
- [[cpg-island]] — dense C+G regions at promoters, and the methylated CpG-poor background around them. *(both, solid)*
- [[markov-chain]] — a memoryless, homogeneous state process described by a transition matrix. *(module 1, solid)*
- [[hidden-markov-model]] — states hidden behind emissions; the three problems, profile HMMs and gene prediction. *(module 1, solid)*
- [[maximum-likelihood]] — the "pick the parameters that make the observed data most probable" principle shared by Baum–Welch, EM motif discovery and phylogenetic model fitting. *(both, solid)*
- [[algorithmic-complexity]] — asymptotic bounds, the growth hierarchy, calculation rules, and the polynomial/exponential divide. *(both, solid)*
- [[dynamic-programming]] — the design pattern behind every table-filling algorithm in the module: Bellman's principle, init/fill/traceback, and its four instances here. *(module 1, solid)*
- [[string-matching]] — the exact matching problem and the prefix, suffix and factor search paradigms. *(both, solid)*
- [[homology]] — common ancestry, orthologs versus paralogs, and the identity/conservation/similarity distinction. *(both, solid)*
- [[substitution-matrix]] — scoring residue substitutions, PAM versus BLOSUM, and constant, linear and affine gap penalties. *(both, solid)*
- [[descriptive-statistics]] — data types, central tendency, variability, relative standing, covariance and the z-score. *(both, solid)*
- [[z-score]] — `z = (x − μ)/σ` as both a measure of relative standing and the standardization step of the normalization pipeline. *(module 1, solid)*
- [[probability-distribution]] — the normal and binomial distributions, the central limit theorem and distribution shapes. *(module 1, solid)*
- [[statistical-testing]] — null and alternative hypotheses, type I/II errors, sensitivity and specificity, p-values and significance levels. *(both, solid)*
- [[data-normalization]] — log transform, z-score standardization and outliers, and why normalization cannot remove a batch effect. *(both, solid)*
- [[batch-effect]] — biased measurements from processing circumstances, the confounding they cause, and the design and statistical remedies. *(both, solid)*
- [[transcription-factor-binding-site]] — short degenerate DNA segments bound by transcription factors, and the experimental and in silico ways to find them. *(both, solid)*
- [[population-genetics]] — allele frequencies, genotypes, SNPs, linkage and the population structure that confounds association studies. *(module 1, solid)*
- [[snp]] — the single-base polymorphism as the unit of human variation: genotype coding, linkage, and the multiple-testing burden it creates. *(module 1, solid)*
- [[genetic-drift]] — allele-frequency change from random sampling alone, with fixation and loss as its absorbing states. *(module 1, solid)*
- [[hardy-weinberg-equilibrium]] — the `p²`, `2pq`, `q²` null model of genotype frequencies, its assumptions and its Punnett-square derivation. *(module 1, solid)*
- [[expression-qtl]] — loci whose alleles shift a gene's expression, split into cis and trans, found by one GWAS per gene. *(module 1, solid)*
- [[gene-set]] — a named group of genes sharing a function, process, component or pathway; the unit of enrichment analysis. *(module 2, solid)*
- [[gene-ontology]] — the structured controlled vocabulary of gene function: a DAG of `is a` and `part of` relations over three ontologies. *(module 2, solid)*
- [[sequence-motif]] — a short conserved sequence shared by related sequences and tied to a biological function. *(module 2, solid)*
- [[information-content]] — entropy, information content in bits and relative entropy against a background; the geometry of a sequence logo. *(module 2, solid)*
- [[gene-knockout]] — deactivating a gene to see what changes, and the route from a knocked-out transcription factor to candidate binding sites. *(module 2, solid)*
- [[planted-motif-problem]] — the formal `(l,d)`-motif search problem and its `O(4^l · m · n · d)` brute-force cost. *(module 2, solid)*
- [[travelling-salesman-problem]] — the shortest closed tour visiting every city once: the NP-hard reference problem for metaheuristics. *(module 2, solid)*
- [[machine-learning]] — data plus answers in, rules out; linear versus non-linear problems and the supervised/unsupervised split. *(module 2, solid)*
- [[overfitting]] — a model that explains its training data perfectly and new data badly, and the data splits that expose it. *(module 2, solid)*
- [[node-impurity]] — how mixed the classes at a decision-tree node are, measured by resubstitution error, Gini or entropy, and the goodness of a split. *(module 2, solid)*
- [[cluster-analysis]] — grouping objects without labels so that intra-cluster distance is small and inter-cluster distance large; the five method families. *(module 2, solid)*
- [[f-measure]] — the harmonic mean of precision and recall, applied pairwise to score a clustering against a gold standard. *(module 2, solid)*
- [[endophenotype]] — a measurable intermediate trait closer to the genetics than the phenotype, and what de novo endophenotyping means. *(module 2, solid)*
- [[kaplan-meier-plot]] — probability of an event not yet having occurred, plotted against time; the clinical validation of a discovered subgroup. *(module 2, solid)*
- [[deep-learning]] — machine learning as function fitting, with the features learned rather than designed; the architecture catalogue. *(module 2, solid)*
- [[activation-function]] — the non-linearity that keeps a stack of layers from collapsing into one linear map: sigmoid, binary step, softplus, softmax. *(module 2, solid)*
- [[cost-function]] — one number saying how wrong the network is, taking the parameters as input; MSE, L1, L2 and the local/global minimum problem. *(module 2, solid)*
- [[pooling-layer]] — downsampling a feature map by taking the maximum or the mean of each window. *(module 2, solid)*
- [[dropout]] — randomly deactivating neurons during training so that no neuron can rely on any particular other one. *(module 2, solid)*
- [[bias-variance-tradeoff]] — Andrew Ng's diagnostic: compare human-level, training and dev error to decide whether to fix bias or variance. *(module 2, solid)*
- [[recurrent-neural-network]] — sequence models, attention and transformers; the neural successor to the hidden Markov model. *(module 2, draft)*
- [[graph-neural-network]] — node-, edge- and graph-level prediction on networks, built on the Laplacian `L = D − A`. *(module 2, solid)*
- [[droplet-based-single-cell-methods]] — co-encapsulating cells and barcoded beads, with Poisson loading setting the capture and duplication rates. *(module 2, solid)*
- [[barcode-collision]] — two cells receiving the same barcode; the rate `1 − ((M−1)/M)^(N−1)` and the 100× diversity rule. *(module 2, solid)*
- [[doublet]] — technical, synthetic and biological; detected by the barnyard plot and controlled by loading density. *(module 2, solid)*
- [[unique-molecular-identifier]] — a random tag per molecule, so that PCR duplicates can be collapsed and counts mean molecules. *(module 2, solid)*
- [[highly-variable-genes]] — the feature-selection step of single-cell analysis, with five reasons for discarding the rest. *(module 2, solid)*
- [[single-cell-analysis-workflow]] — the seven steps from quality control to downstream cell-level and gene-level analysis. *(module 2, solid)*
- [[molecular-evolution]] — evolution as mutation with selection, the neutral theory, the molecular clock, gene loss and horizontal transfer. *(module 2, solid)*
- [[phylogenetic-tree]] — OTUs and HTUs, rooted versus unrooted, cladogram versus additive versus ultrametric, and how many trees exist. *(module 2, solid)*
- [[gene-tree-and-species-tree]] — why they need not agree: a gene may duplicate before or after two species diverge. *(module 2, solid)*
- [[evolutionary-distance]] — the unobservable substitution count, why `p = D/L` underestimates it, and the hierarchy of corrections. *(module 2, solid)*
- [[transition-and-transversion]] — purine↔purine and pyrimidine↔pyrimidine versus the cross-class exchanges, and why transitions dominate. *(module 2, solid)*
- [[molecular-clock]] — a constant rate per protein across lineages; the three-point condition and what UPGMA depends on. *(module 2, solid)*
- [[non-coding-rna]] — RNA that regulates instead of coding; the second answer to why identical genomes give different cell types. *(module 2, solid)*
- [[rna-interference]] — sequence-specific post-transcriptional gene silencing, covering both miRNA and siRNA. *(module 2, solid)*
- [[microrna]] — 19–22 nt endogenous regulators: biogenesis via Drosha, Exportin 5 and Dicer, then seed pairing in miRISC. *(module 2, solid)*
- [[small-interfering-rna]] — perfectly complementary small RNAs that direct RISC to cleave their target; not encoded in the genome. *(module 2, solid)*
- [[competing-endogenous-rna]] — genes sharing a miRNA response element titrate the miRNA and so regulate each other in trans. *(module 2, solid)*
- [[mutual-information]] — `I(X;Y)` and its conditional form, and the four reasons it cannot scale to genome-wide ceRNA inference. *(module 2, solid)*
- [[sensitivity-correlation]] — `scor = cor − pcor`, generalised to `mscor` over several miRNAs, with a simulated null model. *(module 2, solid)*
- [[network-alignment]] — the best mapping between the nodes of two or more networks; local versus global, and the NP-hard MCES problem. *(module 2, solid)*
- [[graph-edit-distance]] — the number of edge insertions and deletions needed to turn one graph into another. *(module 2, solid)*
- [[graphlet-degree-signature-distance]] — how dissimilar two nodes' local neighbourhoods are, measured over 15 graphlet orbits. *(module 2, solid)*

## Methods
- [[shotgun-sequencing]] — shear many genome copies, read the fragments, and reconstruct the original from overlaps. *(module 1, solid)*
- [[next-generation-sequencing]] — massively parallel sequencing by synthesis, its pipeline, and its characteristic biases. *(module 1, solid)*
- [[greedy-assembly]] — merge the heaviest overlap repeatedly until one contig remains. *(module 1, solid)*
- [[de-bruijn-assembly]] — build a k-mer graph and assemble by finding an Eulerian path in polynomial time. *(module 1, solid)*
- [[sequence-alignment]] — hub page for alignment: the four alignment types, the dynamic-programming framework, gaps and gap penalties. *(both, solid)*
- [[needleman-wunsch]] — global alignment of two complete sequences by dynamic programming with traceback. *(both, solid)*
- [[smith-waterman]] — optimal local alignment by zero-clamped dynamic programming from the matrix maximum. *(both, solid)*
- [[knuth-morris-pratt]] — linear-time exact string search using a precomputed failure function. *(module 1, solid)*
- [[boyer-moore-string-search]] — right-to-left exact string search combining the bad-character and good-suffix rules. *(module 1, solid)*
- [[qq-plot]] — graphical check of whether two datasets share a distribution, by plotting their quantiles against each other. *(module 1, solid)*
- [[blast]] — heuristic seed-and-extend local alignment search of a database, scored by E-value. *(both, solid)*
- [[chip-seq]] — sequencing of immunoprecipitated chromatin to locate transcription-factor binding sites and histone marks. *(both, solid)*
- [[atac-seq]] — Tn5 tagmentation of nucleosome-free DNA as a direct readout of chromatin accessibility; named but not described in the notes, so supplied beyond them. *(module 1, solid)*
- [[microarray-expression-analysis]] — hybridisation-based expression measurement, with background subtraction, normalisation and testing. *(both, solid)*
- [[rna-seq]] — sequencing-based transcriptomics producing a gene-by-experiment count matrix. *(both, solid)*
- [[boyer-moore-majority-vote]] — linear-time constant-space majority element detection, with its divide-and-conquer alternative. *(module 1, solid)*
- [[principal-component-analysis]] — orthogonal projection onto the directions of greatest variance, for visualisation, quality control and batch removal. *(both, solid)*
- [[position-weight-matrix]] — position-specific nucleotide frequencies scored as log-odds against a background, with pseudo-counts, thresholds and lookahead scanning. *(both, solid)*
- [[suffix-tree]] — all suffixes of a string as root-to-leaf paths, giving `O(|P|)` substring queries and pruned motif scans. *(module 1, solid)*
- [[suffix-array]] — the flattened suffix tree: sorted suffix indices plus the lcp and skp arrays. *(both, solid)*
- [[wright-fisher-model]] — binomial resampling of `2N` gametes per generation, the formal origin of genetic drift. *(module 1, solid)*
- [[haplotype-phasing]] — assigning the alleles of each locus to the two chromosome copies, by enumeration, trios or population data. *(module 1, solid)*
- [[genome-wide-association-study]] — testing hundreds of thousands of SNPs against a phenotype, with coding models, linkage and population-structure correction. *(both, solid)*
- [[multiple-testing-correction]] — Bonferroni for the family-wise error rate and Benjamini–Hochberg for the false discovery rate. *(both, solid)*
- [[peak-calling]] — MACS2: fragment-length estimation, a dynamic local Poisson background, enriched regions and FDR. *(module 1, solid)*
- [[bisulfite-sequencing]] — reading methylation as a C/T difference, and finding maximal differentially methylated regions. *(module 1, solid)*
- [[epigenome-wide-association-study]] — associating genome-wide quantifiable epigenetic marks with a phenotype across individuals. *(module 1, solid)*
- [[forward-algorithm]] — the probability of an observed sequence under an HMM, summed over all state paths by dynamic programming. *(module 1, solid)*
- [[viterbi-algorithm]] — the most probable hidden state path, by a max-recursion in log space with backtracking. *(module 1, solid)*
- [[baum-welch-algorithm]] — EM training of HMM parameters from unlabelled sequences, maximising likelihood or the posterior. *(both, solid)*
- [[enrichment-analysis]] — hub page: the workflow from experimental design to functional groups, and the threshold-versus-whole-distribution split. *(module 2, solid)*
- [[fishers-exact-test]] — exact hypergeometric test of a 2×2 overlap table, without any sampling. *(module 2, solid)*
- [[gene-set-enrichment-analysis]] — the running enrichment score over a ranked gene list, with a permutation null, an empirical p-value and an FDR. *(module 2, solid)*
- [[keypathwayminer]] — de novo network enrichment: maximal connected subnetworks with `K` gene and `L` case exceptions, under the INEs and GLONE models. *(module 2, solid)*
- [[ant-colony-optimization]] — pheromone-guided randomised search for intractable combinatorial problems. *(module 2, solid)*
- [[sequence-logo]] — a motif drawn as stacked letters whose heights come from relative entropy and per-residue contributions. *(both, solid)*
- [[expectation-maximization]] — parameter estimation with incomplete data: complete the data with probabilities, then apply MLE, and repeat. *(module 2, solid)*
- [[em-motif-discovery]] — EM with the motif position as the latent variable, plus MEME's pseudo-counts and start-point search. *(module 2, solid)*
- [[gibbs-sampling]] — the stochastic analogue of EM for motifs: resample one sequence's start position at a time. *(module 2, solid)*
- [[cross-validation]] — hold out one fold at a time so every sample is tested exactly once; leave-one-out as its extreme. *(module 2, solid)*
- [[bootstrapping]] — resampling with replacement to approximate the sampling distribution of a statistic, with the out-of-bag set as a free test set. *(module 2, solid)*
- [[roc-curve]] — true-positive against false-positive rate over every cutoff, summarised by the area under the curve. *(module 2, solid)*
- [[decision-tree]] — top-down induction by repeatedly choosing the split that most reduces node impurity. *(module 2, solid)*
- [[random-forest]] — hundreds of trees on random subsets of features and observations, aggregated, with an out-of-bag error estimate. *(module 2, solid)*
- [[support-vector-machine]] — the separating hyperplane with the widest margin, defined by its support vectors alone. *(module 2, solid)*
- [[k-means]] — assign to the nearest centroid, recompute the centroids, repeat; with the elbow method for choosing `k`. *(module 2, solid)*
- [[transclust]] — weighted transitive graph projection: threshold a similarity graph and pay for every edge flip needed to make it a union of cliques. *(module 2, solid)*
- [[grandforest]] — a random forest grown along the edges of an interaction network, returning a connected disease-gene module. *(module 2, solid)*
- [[bicon]] — ant-driven bi-clustering that splits patients and genes at once under a connected-subnetwork constraint. *(module 2, solid)*
- [[neural-network]] — layers of neurons computing `a¹ = σ(W a⁰ + b)`, trained by forward pass, loss, backward pass and update. *(module 2, solid)*
- [[gradient-descent]] — step downhill along `−η∇C`, in mini-batches, with the learning rate as the decisive knob. *(module 2, solid)*
- [[backpropagation]] — the gradient computed backwards through the layers, via the three levers on a neuron's output. *(module 2, solid)*
- [[convolutional-neural-network]] — translationally equivariant feature detection by kernels, stride and padding, stacked into VGG and ResNet blocks. *(module 2, solid)*
- [[autoencoder]] — encoder, latent representation and decoder trained to reconstruct the input; a non-linear PCA. *(module 2, solid)*
- [[generative-adversarial-network]] — a generator trained against a discriminator, with training instability, mode collapse and difficult evaluation. *(module 2, solid)*
- [[single-cell-rna-seq]] — expression measured one cell at a time, the eleven-point wish list, and the wet-lab plus analysis pipeline. *(module 2, solid)*
- [[t-sne]] — Gaussian neighbour probabilities in high dimensions, t-distributed ones in low, minimising the KL divergence; local structure only. *(module 2, solid)*
- [[umap]] — simplicial complexes, fuzzy spectral embedding and fuzzy cross entropy; preserves global dissimilarities too, and scales better. *(module 2, solid)*
- [[jukes-cantor-model]] — one substitution rate for everything; the rate matrix `Q^JC` and the row-sum/column-sum conservation rules. *(module 2, solid)*
- [[kimura-two-parameter-model]] — separate rates for transitions and transversions, with `d = −½ln(1−2P−Q) − ¼ln(1−2Q)`. *(module 2, solid)*
- [[upgma]] — sequential clustering under a molecular clock, merging the closest pair at height `d_ij/2` into a rooted ultrametric tree. *(module 2, solid)*
- [[neighbor-joining]] — star decomposition minimising `M_ij`, giving unequal branch lengths and an unrooted additive tree without a clock. *(module 2, solid)*
- [[maximum-parsimony]] — the topology needing the fewest character-state changes over the informative alignment columns. *(module 2, solid)*
- [[phylogenetic-tree-reconstruction]] — the four steps — data selection, model, method, evaluation — and the distance- versus alignment-based comparison. *(module 2, solid)*
- [[bootstrap-tree-assessment]] — resample the alignment columns, rebuild, and report a support value per internal branch; plus outgroup rooting. *(module 2, solid)*
- [[crispr-cas9]] — bacterial adaptive immunity turned into programmed genome editing; permanent knock-out with fewer off-targets than RNAi. *(module 2, solid)*
- [[mirna-target-prediction]] — seed pairing, conservation, hybridization energy and accessibility, plus learning from PAR-CLIP and filtering by expression. *(module 2, solid)*
- [[sponge]] — Sparse Partial correlation ON Gene Expression: genome-wide ceRNA network construction from `mscor` against a simulated null. *(module 2, solid)*
- [[cytomcs]] — iterated local search for multiple global network alignment, maximising squared per-edge conservation. *(module 2, solid)*
- [[evolutionary-algorithm]] — population, mutation, crossover and survival of the fittest as a general-purpose metaheuristic. *(module 2, solid)*
- [[gedevo]] — evolutionary minimisation of the graph edit distance, guided by `pairScore` and health-based selection. *(module 2, solid)*

## Exercises

### Module 1
- [[E01-cell-biology-and-gene-expression]] — prokaryote/eukaryote table, central dogma, splicing, and the effect of mutations by location. *(module 1, solid)*
- [[E02-greedy-assembly]] — hand-assembly of six fragments into `ATTTGCGCAGAGACCTAAG` by heaviest-overlap merging. *(module 1, solid)*
- [[E03-de-bruijn-assembly]] — k-mer decomposition, Eulerian reconstruction of `GACGGCGTGACGT`, and bubble identification. *(module 1, solid)*
- [[E04-complexity-and-majority-element]] — Big-O classification, calculation rules, and two majority-element algorithms. *(module 1, solid)*
- [[E05-kmp-string-matching]] — failure functions for two patterns and a traced KMP search finding a match at position 18. *(module 1, solid)*
- [[E06-boyer-moore-string-search]] — bad-character table, two-shift search of `GCAGAGAG`, and the BMH/BM difference. *(module 1, solid)*
- [[E07-alignment-and-homology]] — globin orthologs and paralogs, plus a Needleman–Wunsch alignment with a three-residue gap. *(module 1, solid)*
- [[E08-test-errors-and-z-score]] — confusion matrix, sensitivity/specificity/accuracy of a screening test, a z-score test decision, distribution identification and QQ-plot shapes. *(module 1, solid)*
- [[E09-binding-sites-pwm-and-pca]] — TFBS and PWM definitions, a count matrix with pseudo-counts and a sequence logo, and PCA versus MDS. *(both, solid)*
- [[E10-suffix-trees-and-arrays]] — suffix trees for `banana$`, `ananas$` and `CACGACGAT$`, and the full suffix array of `teethermometer$`. *(module 1, solid)*
- [[E11-population-genetics-and-multiple-testing]] — generations to Hardy–Weinberg, three-allele frequencies, Wright–Fisher transition probabilities, trio phasing and Benjamini–Hochberg. *(module 1, solid)*
- [[E12-epigenetics-and-peak-calling]] — epigenetic terminology, histone-mark nomenclature, MACS2 capabilities and IDR, and the effect of methylation by genomic compartment. *(module 1, solid)*
- [[E13-markov-chains-and-viterbi]] — a first-order transition matrix from dinucleotide probabilities, and a full Viterbi trellis for `C A A`. *(module 1, solid)*

### Module 2
- [[M2E01-enrichment-analysis-and-keypathwayminer]] — GSEA ordering, Fisher for overlaps, the GO DAG, TSP, and INE/GLONE validity on an 11-gene network. *(module 2, solid)*
- [[M2E02-motif-discovery-and-expectation-maximization]] — motif and knock-out definitions, logos, entropy versus relative entropy, and a full EM iteration on five GC-coded sequences. *(module 2, solid)*
- [[M2E03-machine-learning-and-classification]] — overfitting, CV versus bootstrap, random-forest reading, two ROC curves compared, and an SVM solved by hand. *(module 2, solid)*
- [[M2E04-k-means-and-transclust]] — three k-means iterations on five points, then TransClust at `t = 2` with its cost of 11 and `F ≈ 0.61`. *(module 2, solid)*
- [[M2E05-grandforest-and-bicon]] — de novo endophenotyping vocabulary, supervised versus unsupervised analysis, Kaplan–Meier axes, and BiCoN's five parameters. *(module 2, solid)*
- [[M2E06-deep-learning]] — backpropagation/dropout/pooling definitions, a 4×4 max- and average-pooling example, the epoch stages, and a full Keras CNN pipeline. *(module 2, solid)*
- [[M2E07-single-cell-rna-seq-and-dimensionality-reduction]] — capture and duplication rates, barcodes versus UMIs, the first steps of t-SNE and UMAP, and the seven workflow steps. *(module 2, solid)*
- [[M2E08-phylogenetics]] — in-paralogs and co-orthologs, 15 unrooted and 105 rooted trees for 5 taxa, three rate matrices, and a full UPGMA trace on taxa A–F. *(module 2, solid)*
- [[M2E09-non-coding-rnas-and-sponge]] — miRNA versus siRNA, miRBase and miRNA families, MREs and trans regulation, and how SPONGE finds and tests interactions. *(module 2, solid)*
- [[M2E10-network-alignment]] — `g(A) = 23` for CytoMCS, `GED = 3` for GEDEVO, the GDSD formulas, and a full crossover trace. *(module 2, solid)*

## Gaps
- [[open-questions]] — illegible passages, missing topics, things to verify. *(both, draft)*

## Meta
- [[log]] — append-only chronological record of every ingest, query, lint and refactor pass. *(both, solid)*
