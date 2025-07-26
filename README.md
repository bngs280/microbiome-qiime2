# 16S QIIME2 Metagenomics Pipeline

![QIIME2](https://img.shields.io/badge/QIIME2-%E2%89%A52022.11-blue)
![Python](https://img.shields.io/badge/Python-3.8%2B-green)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A reproducible pipeline for 16S rRNA microbiome analysis using QIIME2, from raw sequencing data to publication-ready figures.

## Key Features
- ✅ **Denoising**: DADA2 or DeBlur (SNV error correction)
- ✅ **Taxonomy**: SILVA 138.1 & GTDB classification
- ✅ **Diversity**: Faith's PD, Shannon, UniFrac, PCoA
- ✅ **Visualization**: Interactive Emperor plots
- ✅ **Batch Effect Correction**: PERMANOVA + q2-longitudinal

## Quick Start
```bash
# Install QIIME2 (conda required)
wget https://data.qiime2.org/distro/core/qiime2-2023.9-py38-linux-conda.yml
conda env create -n qiime2 --file qiime2-2023.9-py38-linux-conda.yml

# Run pipeline
qiime tools import \
  --type 'SampleData[PairedEndSequencesWithQuality]' \
  --input-path manifest.tsv \
  --output-path demux.qza \
  --input-format PairedEndFastqManifestPhred33
