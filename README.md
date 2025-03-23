
# Human Variant Calling & Annotation Pipeline

This is a comprehensive Bash pipeline for processing human whole-genome sequencing (WGS) data, including quality control, alignment, variant calling, and variant annotation.

---

## Tools Used

- **FastQC** – Quality control checks on raw FASTQ files  
- **MultiQC** – Aggregates FastQC reports  
- **BWA** – Aligns reads to the human reference genome  
- **Samtools** – Converts and indexes BAM files  
- **Picard** – Sorts BAM files and marks PCR duplicates  
- **GATK** – Performs indel realignment, base recalibration, and variant calling  
- **Annovar** – Annotates variants using multiple databases

---

## Input Requirements

1. `list.txt` – A file with one sample name per line (no extensions).
2. Paired-end FASTQ files for each sample (e.g., `sample_R1.fastq.gz`, `sample_R2.fastq.gz`).
3. Human reference genome (`human_g1k_v37.fa`) and known variant sites.
4. Annovar and the `humandb/` directory with annotation databases.

---

## How to Run

Make sure your script is executable:

```bash
chmod +x variant_pipeline.sh
```

Run the script from your working directory:

```bash
./variant_pipeline.sh
```

Ensure the directory contains `list.txt` and all required FASTQ files.

---

## Output

For each sample, this pipeline generates:

- Aligned, sorted, deduplicated, and indexed BAM files
- VCF files with called variants
- Annovar `.avinput` and `.csv` annotation outputs
- QC reports and summary via MultiQC

---

## Annovar Annotation Databases

The script uses the following Annovar databases:

- `refGene`, `cytoBand`, `snp138`, `esp6500siv2_all`
- `1000g2015aug` (AFR, EAS, EUR), `avsift`, `clinvar`
- `dbnsfp30a`, `exac03`, `icgc21`, `caddgt20`, `gnomad`

Ensure all databases are downloaded in `~/annovar/humandb/`.

---

## Quote to Remember

> **"Bioinformatics is not something you are taught, it’s a way of life."**

---

## Author

**Gerald Mboowa**   
 Email: ...@gmail.com 

---

## License

This script is provided under the **MIT License**.
