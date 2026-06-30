# RNA-seq Preprocessing Pipeline using HISAT2

## Project Overview

This project demonstrates a complete RNA-seq preprocessing workflow using publicly available sequencing data. The pipeline starts from raw paired-end FASTQ files and performs quality control, read trimming, genome alignment, BAM processing, and gene-level quantification.

The workflow was implemented on Ubuntu (WSL2) using widely adopted bioinformatics tools and follows best practices for RNA-seq preprocessing.

---

## Workflow

```text
Raw FASTQ Files
        │
        ▼
Quality Control (FastQC)
        │
        ▼
Read Trimming (fastp)
        │
        ▼
Genome Alignment (HISAT2)
        │
        ▼
SAM to BAM Conversion (SAMtools)
        │
        ▼
Sorting & Indexing BAM (SAMtools)
        │
        ▼
Gene Quantification (featureCounts)
```

---

## Tools Used

| Tool | Purpose |
|------|---------|
| Linux (Ubuntu WSL2) | Bioinformatics environment |
| SRA Toolkit | Download sequencing data |
| FastQC | Raw read quality assessment |
| MultiQC | Aggregate quality reports |
| fastp | Adapter removal and quality trimming |
| HISAT2 | RNA-seq read alignment |
| SAMtools | BAM file processing |
| featureCounts | Gene-level read counting |

---

## Software Versions

- Ubuntu 24.04 (WSL2)
- HISAT2
- SAMtools
- FastQC
- MultiQC
- fastp
- featureCounts (Subread)

---

## Project Structure

```text
RNAseq-Cancer-Pipeline/
│
├── alignment/
├── bam/
├── counts/
├── figures/
├── qc/
├── raw_data/
├── reference/
├── results/
├── scripts/
├── trimmed_reads/
├── README.md
└── .gitignore
```

---

## Input Data

- Public paired-end RNA-seq FASTQ files
- Human reference genome (GRCh38)
- Gene annotation (GTF)

---

## Pipeline Steps

### 1. Download RNA-seq Data

Sequencing reads were downloaded using the SRA Toolkit.

---

### 2. Quality Assessment

Raw sequencing quality was evaluated using FastQC.

Outputs:

- HTML reports
- ZIP reports

---

### 3. Read Trimming

Low-quality bases and adapter sequences were removed using fastp.

Outputs:

- Trimmed FASTQ files
- HTML report
- JSON report

---

### 4. Genome Alignment

Trimmed reads were aligned against the Human GRCh38 reference genome using HISAT2.

Output:

- SAM alignment file

---

### 5. BAM Processing

SAMtools was used to:

- Convert SAM → BAM
- Sort BAM
- Index BAM

Outputs:

- Sorted BAM
- BAM Index (.bai)

---

### 6. Gene Quantification

featureCounts assigned aligned reads to annotated genes.

Outputs:

- gene_counts.txt
- gene_counts.txt.summary

---

# Alignment Statistics

| Metric | Result |
|---------|--------|
| Total Reads | 16,249,153 |
| Overall Mapping Rate | **91.95%** |
| Primary Mapping Rate | **90.63%** |
| Properly Paired Reads | **83.95%** |

The high mapping rate indicates successful alignment against the human reference genome.

---

# Output Files

- Sorted BAM file
- BAM index
- Gene count matrix
- FastQC reports
- fastp reports
- Alignment statistics

---

## Skills Demonstrated

- Linux command line
- Bash scripting
- RNA-seq preprocessing
- FASTQ quality assessment
- Adapter trimming
- Genome alignment
- BAM file manipulation
- Gene quantification
- Bioinformatics workflow management

---

## Applications

This preprocessing workflow provides the required inputs for downstream analyses such as:

- Differential Gene Expression (DESeq2)
- edgeR
- limma-voom
- Functional Enrichment Analysis
- GO Analysis
- KEGG Pathway Analysis

---

## Future Improvements

Future versions of this project will include:

- Multiple biological replicates
- Differential expression analysis using DESeq2
- Volcano plots
- PCA visualization
- Heatmaps
- Gene Ontology enrichment
- KEGG pathway analysis
- Workflow automation using Bash

---

## References

Kim D, Langmead B, Salzberg SL.

**HISAT2: graph-based alignment of next-generation sequencing reads to a population of genomes.**

Nature Biotechnology.

---

Liao Y, Smyth GK, Shi W.

**featureCounts: an efficient general-purpose program for assigning sequence reads to genomic features.**

Bioinformatics.

---

Andrews S.

**FastQC: A Quality Control Tool for High Throughput Sequence Data.**

---

Chen S, Zhou Y, Chen Y, Gu J.

**fastp: an ultra-fast all-in-one FASTQ preprocessor.**

Bioinformatics.

---

## Author

**Mehwish**

Bioinformatics | RNA-seq Analysis | Linux | R | Python | NGS

GitHub: https://github.com/Mehwish55
