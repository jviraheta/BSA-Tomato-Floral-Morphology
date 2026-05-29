# Results Summary
## Bulk Segregant Analysis of Floral Morphology in Wild Tomato
### *Solanum pennellii* × *Solanum pimpinellifolium* F2 Population

---

## 1. Phenotypic Distribution

- **109 F2 plants** phenotyped for petal fusion ratio (middle-to-middle / tip-to-tip)
- Fusion ratios ranged from **0.29** (most spindly) to **0.55** (most webbed)
- Continuous variation consistent with quantitative genetic control
- **20 most extreme individuals** selected for sequencing:
  - Low bulk (spindly): n = 11 (fusion ratio ≤ 0.32)
  - High bulk (webbed): n = 9 (fusion ratio ≥ 0.53)

<img width="827" height="462" alt="Screenshot 2026-05-28 at 11 02 47 PM" src="https://github.com/user-attachments/assets/1b719f0b-eb92-4e0f-a71e-382f7aa61580" />

---

## 2. SNP Filtering and Coverage

- **22,116,620** raw SNP candidates called by GATK HaplotypeCaller
- **26,919** high-confidence SNPs retained after filtering (~0.1%)
- Filtering criteria: total depth 100–400x, minimum sample depth 40x, genotype quality = 99
- SNP density broadly uniform across all 12 chromosomes
- Highest density on Spenn-ch01 (5,522 SNPs), consistent with largest chromosome size

<img width="872" height="592" alt="Screenshot 2026-05-28 at 11 07 04 PM" src="https://github.com/user-attachments/assets/3d6f90c0-ad82-46fc-b845-6fc5163486f6" />


---

## 3. QTL Detection

Genome-wide ΔSNP-index analysis identified **two candidate regions** with elevated signal:

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

> Neither region exceeded the 95% or 99% confidence thresholds, likely due to small bulk sizes. Both approached the 90% CI threshold (ΔSNP-index = ±0.304).

<img width="773" height="520" alt="Screenshot 2026-05-28 at 11 06 36 PM" src="https://github.com/user-attachments/assets/bc2dd20b-3b77-4550-8f24-a3b8160cbf86" />


---

## 4. Candidate QTL Regions

<img width="790" height="559" alt="Screenshot 2026-05-28 at 11 07 23 PM" src="https://github.com/user-attachments/assets/c6dc3db0-d7ac-4a28-bb6f-534defb16307" />

### Primary QTL — Spenn-ch02 (~49.5 Mb)
- Elevated ΔSNP-index spanning ~47–51 Mb
- Peak single-SNP ΔSNP-index of **+0.323** — highest value across the entire genome
- ALT allele strongly enriched in high (webbed) bulk vs low (spindly) bulk
- Peak SNP located **3,996 bp upstream** of *Sopen02g026690* (MYB67)

### Secondary QTL — Spenn-ch05 (~57.6 Mb)
- Negative ΔSNP-index indicates ALT allele enriched in low (spindly) bulk
- Opposite direction to Spenn-ch02 locus — consistent with segregation in F2 populations
- Nearest genes annotated as hypothetical proteins — causal gene undetermined

---

## 5. Candidate Gene: MYB67

- **Gene:** Sopen02g026690 — R2R3-MYB transcription factor (MYB67)
- **Location:** Spenn-ch02, transcription start site at ~49,552,374 bp
- **Peak SNP distance:** 3,996 bp upstream (proximal promoter region)
- **Biological relevance:** R2R3-MYB transcription factors regulate petal epidermal cell morphology in plants. MIXTA and MIXTA-like proteins directly control petal surface texture and shape.
- **Proposed mechanism:** Promoter-region variation at this SNP may alter MYB67 expression level or tissue specificity in petal tissue, driving the observed petal fusion difference between the two species.

---

## 6. Limitations

- Small bulk sizes (n = 11, n = 9) reduced statistical power — bulk sizes of 20–30 recommended for reliable QTL detection
- 2 Mb sliding window limits fine-mapping resolution
- Spenn-ch05 candidate gene remains unidentified (hypothetical proteins only)

---

## 7. Future Directions

- Sequence parental lines to identify causal variant
- Measure MYB67 expression in developing petals of both species
- CRISPR-Cas9 knockout of MYB67 in *S. pennellii* to directly test function
- Repeat with larger mapping population to improve statistical power and narrow QTL intervals
