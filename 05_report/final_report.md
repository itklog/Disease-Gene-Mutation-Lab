# From Gene Mutation to Disease: Investigating How DNA Sequence Changes Affect Protein Products and Human Phenotypes

## Disease Background
Amyotrophic Lateral Sclerosis (ALS) is a progressive neurodegenerative disorder characterized by the selective loss of motor neurons in the brain and spinal cord, leading to muscle weakness, paralysis, and eventual respiratory failure. Familial ALS accounts for ~10% of cases, with pathogenic variants in *SOD1* being one of the most common genetic causes. Mutations in *SOD1* lead to toxic gain-of-function effects, including protein misfolding, aggregation, and oxidative stress.

## Gene and Normal Protein Function
The *SOD1* gene encodes Cu/Zn superoxide dismutase, a cytosolic antioxidant enzyme that catalyzes the conversion of superoxide radicals into hydrogen peroxide and oxygen. Normal SOD1 function is critical for protecting motor neurons from oxidative damage and maintaining cellular redox balance. The protein is a homodimer of 154 amino acids, stabilized by metal cofactors and disulfide bonds.

## Documented Mutation
- **Gene:** *SOD1*  
- **Reference Transcript Accession:** NM_000454.5  
- **Reference Protein Accession:** NP_000445.1  
- **Variant Notation:** c.272A>C  
- **Nucleotide Change:** Adenine → Cytosine at position 272  
- **Protein Change:** p.Asp91Ala  
- **Mutation Type:** Missense variant  
- **Clinical Interpretation:** Pathogenic; associated with familial ALS through toxic gain-of-function mechanisms (misfolding, aggregation).  
- **Literature Reference:** Benatar et al., 2025; Berdyński et al., 2022; ClinVar Variation ID: 14766  

## Hypothesis
The `c.272A>C` substitution alters codon 91, replacing aspartic acid with alanine. This change removes a negatively charged residue, potentially destabilizing local protein interactions and impairing SOD1 folding. The predicted outcome is increased misfolding and aggregation, contributing to motor neuron toxicity in ALS.

## Methods
1. Retrieved WT CDS (NM_000454.5) and protein (NP_000445.1) from NCBI.  
2. Verified WT translation using EMBOSS Transeq.  
3. Engineered documented variant `c.272A>C` and an artificial missense variant (codon 8 GTG→GAG, Val→Glu).  
4. Translated both mutants with Transeq and performed pairwise alignments.  
5. Managed workflow in Galaxy (`Ansag_SOD1_Gene_Mutation_Lab`) and version-controlled on GitHub.  

## Results

### Wild-Type Control Parameters

| Parameter              | Predicted Protein (Transeq) | Reference Protein |
|------------------------|-----------------------------|------------------|
| CDS Length             | 462 bp                      | 462 bp           |
| Protein Length         | 154 aa                      | 154 aa           |
| Start Codon            | ATG (Position 1–3)          | ATG (Position 1–3) |
| Stop Codon             | TGA (Position 463–465)      | TGA (Position 463–465) |
| Reading Frame          | Frame 1                     | Frame 1          |
| First 10 Amino Acids   | (Insert your Transeq output) | (Insert reference sequence) |
| Last 10 Amino Acids    | (Insert your Transeq output) | (Insert reference sequence) |

### SOD1 Sequence and Protein Comparison
| Comparison Point           | Wild-Type SOD1 | Documented Mutation (c.272A>C) | Artificial Mutation (codon 8 GTG→GAG) |
|----------------------------|----------------|--------------------------------|--------------------------------------|
| CDS length                 | 462 nt         | 462 nt                         | 462 nt                               |
| Protein length             | 154 aa         | 154 aa                         | 154 aa                               |
| Mutation type              | —              | Missense (Asp→Ala at position 91) | Missense (Val→Glu at position 8)     |
| Reading frame change       | None           | None                           | None                                 |
| Premature stop codon       | Absent         | Absent                         | Absent                               |
| Amino acids affected       | None           | 1 substitution                  | 1 substitution                       |
| Expected functional consequence | Normal folding and function | Possible destabilization of SOD1 structure and function | Local destabilization due to charge introduction |

## WT vs Mutant Protein Comparison
- WT: intact 154-aa protein with normal folding and antioxidant function.  
- Documented mutant: Asp91Ala substitution may destabilize local structure, impairing folding and increasing aggregation risk.  
- Artificial mutant: Val8Glu substitution introduces a charged residue, potentially destabilizing the N-terminal region.  

## Artificial Mutation Experiment
The codon 8 GTG→GAG substitution (Val→Glu) introduced a negative charge into the N-terminal region. Translation yielded a full-length protein but with altered physicochemical properties, suggesting possible folding/stability issues.

### Molecular Interpretation

SOD1 Gene  
   ↓ Mutation (c.272A>C → Asp91Ala OR codon 8 GTG→GAG → Val8Glu)  
   ↓ Protein (missense substitutions in 154-aa SOD1)  
   ↓ Cellular Effect (possible misfolding, aggregation, altered stability)  
   ↓ Phenotype (motor neuron stress and degeneration in ALS — requires further validation)

## Limitations
- Computational translation and alignment cannot replicate in vivo folding, aggregation, or toxic gain-of-function effects of SOD1.  
- No functional assays (e.g., enzymatic activity, aggregation studies) were performed to validate predicted consequences.  
- The study does not include patient or model organism data to correlate mutations with ALS phenotypes.  
- Structural modeling was not conducted, limiting visualization of how substitutions destabilize protein domains.

## Conclusion
The `c.272A>C` missense mutation in *SOD1* results in an amino acid substitution that may influence protein stability and folding. The artificial mutation at codon 8 similarly highlights how substitutions can alter local structure. While these in‑silico analyses suggest possible impacts on SOD1 function, the actual biological and clinical consequences remain uncertain. Further experimental studies, including biochemical assays, structural modeling, and patient or model organism investigations, are required to validate these predictions and fully understand their role in ALS pathogenesis.


## References
- Benatar, M., Robertson, J., & Andersen, P. M. (2025). *Amyotrophic lateral sclerosis caused by SOD1 variants: from genetic discovery to disease prevention.* The Lancet Neurology, 24(1), 77–86.  
- Berdyński, M., Miszta, P., Safranow, K., Andersen, P. M., Morita, M., Filipek, S., Żekanowski, C., & Kuźma-Kozakiewicz, M. (2022). *SOD1 mutations associated with amyotrophic lateral sclerosis: analysis of variant severity.* Scientific Reports, 12(1), 103.  
- NCBI ClinVar: NM_000454.5(SOD1):c.272A>C (p.Asp91Ala) [Variation ID: 14766].  
- Nishiyama, A., Niihori, T., Suzuki, N., Izumi, R., Akiyama, T., Kato, M., ... & Aoki, M. (2024). *Updated genetic analysis of Japanese familial ALS patients carrying SOD1 variants revealed phenotypic differences for common variants.* Neurology: Genetics, 10(6), e200196.  
