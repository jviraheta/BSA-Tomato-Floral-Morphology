# Bulk Segregant Analysis of Floral Morphology in Solanum pennellii × Solanum pimpinellifolium F2 Population
This project uses bulk segregant analysis (BSA) to identify genomic regions controlling petal fusion differences between two wild tomato species: Solanum pennellii (narrow, spindly petals) and Solanum pimpinellifolium (broader, fused petals).
An F2 population of 109 plants was phenotyped for petal fusion ratio, and the 20 most extreme individuals were selected for paired-end Illumina whole-genome sequencing. ΔSNP-index analysis identified two candidate QTL, with the primary locus on Spenn-ch02 implicating an R2R3-MYB transcription factor (MYB67) in petal epidermal cell development.
# Methods Summary
1. Phenotyping

109 F2 plants grown in greenhouse and phenotyped for petal fusion ratio (middle-to-middle width / tip-to-tip diameter)
20 most extreme individuals selected for bulk construction (11 low/spindly, 9 high/webbed)

2. Sequencing & Alignment

Paired-end Illumina whole-genome sequencing of both bulks
Alignment to S. pennellii reference genome using BWA-MEM
Read group addition, duplicate marking and removal

3. SNP Calling (GATK Pipeline)

SNP calling with GATK HaplotypeCaller in GVCF mode, parallelized across 12 chromosomes
Joint genotyping of per-chromosome GVCFs
Filtering: total depth 100-400x, minimum sample depth 40x, genotype quality = 99
Retained 26,919 high-confidence SNPs from 22,116,620 raw candidates (~0.1%)

4. Bulk Segregant Analysis

ΔSNP-index analysis in QTLseqr (R) using a 2 Mb sliding window
Confidence intervals estimated by simulation (10,000 replications, F2 population structure)

5. Candidate Gene Analysis

Candidate regions visualized in IGV
Genome annotation accessed via Sol Genomics Network (SGN) JBrowse
Gene distance calculations performed at peak SNP positions
