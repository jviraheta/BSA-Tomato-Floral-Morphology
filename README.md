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

# Key Results

| Parameter | Spenn-ch02 (Primary) | Spenn-ch05 (Secondary) |
|---|---|---|
| Peak SNP position | 49,548,378 bp | 57,626,400 bp |
| Peak ΔSNP-index | +0.308 | −0.293 |
| G' statistic | 14.27 | 11.65 |
| REF allele | T | A |
| ALT allele | G | C |
| ALT freq. — High bulk | 0.438 | 0.596 |
| ALT freq. — Low bulk | 0.115 | 0.889 |
| Nearest gene | MYB67 (Sopen02g026690) | Hypothetical protein |
| Distance to gene | 3,996 bp upstream | Within region |
| Exceeds 90% CI | Yes | No (approaching) |

The primary QTL on Spenn-ch02 contains MYB67, an R2R3-MYB transcription factor with established roles in petal epidermal cell morphology. The peak SNP falls in the proximal promoter region, suggesting promoter-region variation may drive differential MYB67 expression between the two species.

# Tools & Dependencies
| Tool | Version | Use |
|---|---|---|
|BWA-MEM | 4.x | SNP calling |
| SAMtools | 1.x | BSA / ΔSNP-index analysis |
| QTLseqr | 2.x | Variant visualization |
| IGV | 4.x | Statistical analysis and plotting |
