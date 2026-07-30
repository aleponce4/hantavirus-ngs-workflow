# Hantavirus NGS Analysis Workflow (Legacy Prototype)

> [!CAUTION]
> **Archived Legacy Prototype**: This repository represents an early, unmaintained first-generation Bash pipeline prototype. It has been superseded by the production containerized Nextflow DSL2 pipeline **[viral-intrahost-variant-workflow](https://github.com/aleponce4/viral-intrahost-variant-workflow)**.
> This repository is preserved as an archived read-only record for historical project tracking and must not be used for production data processing.

---

## Overview

Workflow for processing Hantavirus Illumina sequencing data including quality control, mapping, variant calling, consensus generation, and basic visualization. Developed to standardize analysis of segmented viral genomes (L, M, and S segments) in early research studies.

### Workflow Structure

Major components:

- Read QC and adapter trimming  
- Primer trimming  
- Reference alignment  
- Variant calling  
- Consensus generation  
- Coverage analysis  
- Primer evaluation  

---

## Installation & Historical Setup

### Requirements

- Conda or Miniconda  
- Git  

### Setup

Clone repository:

```bash
git clone https://github.com/aleponce4/hantavirus-ngs-workflow.git
cd hantavirus-ngs-workflow
```

Run setup script:

```bash
./setup.sh
```

---

## Input Data Conventions

Expected directory structure:

### FASTQ files

Place paired-end reads in:

```text
data/raw_reads/
```

Naming convention:

```text
SAMPLE_R1.fastq.gz
SAMPLE_R2.fastq.gz
```

### Reference sequences

Organize references by genome segment:

```text
data/references/
  L_segment/
  M_segment/
  S_segment/
```

Each segment directory expects a FASTA reference sequence and matching GFF3 annotation file.

---

## ⚠️ Legacy Limitations & Operational Warnings

- **Superseded Architecture:** This pipeline is unmaintained and lacks the containerization, automated unit testing, schema validation, and reproducible provenance of `viral-intrahost-variant-workflow`.
- **Parameter Consumption Note:** The prototype wrapper scripts (`run_pipeline.sh`) process raw inputs present in `data/raw_reads/` directly; individual sample CLI arguments passed to `run_pipeline.sh` are not parsed.
- **Directory Cleanup Safeguard:** Legacy execution scripts contain hardcoded workspace cleanup routines under `results/`. Reviewers and users are advised to consult `viral-intrahost-variant-workflow` for maintained viral genomics pipelines.

---

## License

This legacy archive is provided under the [MIT License](LICENSE).
