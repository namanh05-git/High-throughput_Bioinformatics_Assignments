# Bioinformatics Course Exercises (R)

Solutions to three exercises from a bioinformatics course, written in R (Jupyter notebooks with
the R kernel). They cover sequence analysis, hidden Markov models, and statistical analysis of
expression and drug response data.

## Contents

| Notebook | Topics |
|---|---|
| `notebooks/ex1_sequence_analysis_orfs_alignment.ipynb` | SARS-CoV-2 genome: sliding-window GC skew, ORF finding, permutation test for ORF length with Bonferroni and Benjamini-Hochberg correction, first-order Markov model to identify the spike-protein ORF, translation, and global and local protein alignment (BLOSUM62) against other coronavirus spike sequences |
| `notebooks/ex2_hmm_viterbi_profile_hmm.ipynb` | Two-state HMM: Viterbi decoding implemented from scratch, sequence scoring, and HMM training; profile HMM of a protein family from a ClustalW multiple sequence alignment; post-hoc consistency correction of predictions on a DAG, evaluated with precision-recall curves |
| `notebooks/ex3_drug_response_and_differential_expression.ipynb` | Random forest prediction of drug combination response (random split vs. held-out cell lines); PCA of gene expression by tissue type; differential expression of TP53-mutant vs. wildtype cell lines with `limma` (empirical Bayes, BH correction) |

## Repository layout

```
.
├── README.md
├── .gitignore
├── data/        # input files go here (not included, see data/README.md)
└── notebooks/
```

## Requirements

R with the [IRkernel](https://irkernel.github.io/) and these packages:

- CRAN: `ape`, `HMM`, `aphid`, `igraph`, `PRROC`, `randomForest`, `ggplot2`, `BiocManager`
- Bioconductor: `Biostrings`, `ORFik`, `pwalign`, `msa`, `limma`, `piano`

## Running

1. Put the course data in `data/` (see [`data/README.md`](data/README.md)).
2. Start Jupyter and open a notebook from inside `notebooks/`, so the relative paths
   (`../data/...`) resolve.

Notes:
- Exercise 1's first cell reinstalls packages on every run (`force=TRUE`); after the first run you can skip it.
- The first cell of exercises 2 and 3 points R at a custom library folder from the course server
  (`/notebooks/Bioinformatics/lib/`). Remove or change those lines on your own machine.
