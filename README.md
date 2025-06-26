# Structural and Small Variant Detection from Contigs
# contig-variant-pipeline

A reproducible pipeline for identifying structural and small variants in de novo contigs relative to a reference genome, with optional annotation using snpEff.

---

## Project Structure
contig-variant-pipeline/
├── 01_StructuralVariants/
│   └── ptg000272l_example/
│       ├── example_ref.fasta
│       ├── ptg000272l.fasta
│       └── (nucmer output files)
├── 02_SmallVariants/
│   └── example/
│       ├── ref.fasta
│       ├── contig.fasta
│       └── (VCF and annotation)
├── scripts/
│   ├── run_nucmer.sh
│   ├── run_assemblytics.sh
│   ├── run_minimap2_smallvar.sh
│   └── run_snpeff_annotation.sh
---

# How to Run

### Structural Variant Detection

bash scripts/run_nucmer.sh ref.fasta contig.fasta output_prefix
bash scripts/run_assemblytics.sh output_prefix.delta output_dir

# Small Variant Calling + Annotation
bash scripts/run_minimap2_smallvar.sh ref.fasta contig.fasta output.vcf
bash scripts/run_snpeff_annotation.sh output.vcf

Reference
	•	Reference genome: MaizeGDB Zm-B73-REFERENCE-NAM-5.0
	•	snpEff: https://pcingola.github.io/SnpEff/
