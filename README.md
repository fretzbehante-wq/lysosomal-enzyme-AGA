# Exploring Lysosomal Enzymes Using NCBI and R
## Gene and Enzyme Information: AGA

- **Gene Name:** Aspartylglucosaminidase
- **Enzyme Name:** N(4)-(beta-N-acetylglucosaminyl)-L-asparaginase
- **Gene Symbol:** AGA
- **NCBI Protein Accession:** [NP_000018.2](https://www.ncbi.nlm.nih.gov/protein/NP_000018.2)
- **What It Breaks Down:** The enzyme breaks the bond between N-acetylglucosamine (GlcNAc) and asparagine in glycoprotein-derived oligosaccharides during lysosomal degradation.
- **Normal Function:** AGA encodes an enzyme that helps cells break down glycoproteins in lysosomes by removing asparagine from N-linked sugar chains. This process supports the normal recycling and degradation of glycoproteins.

## Analysis Workflow

1. **Data setup and validation**
   - Defines the target gene as AGA and the protein accession as NP_000018.2.
   - Checks whether the required R packages, rentrez and ggplot2, are installed.
   - Creates the project directories: data/, results/, and figures/.

2. **Data download**
   - Retrieves the protein FASTA sequence from NCBI using rentrez::entrez_fetch().
   - Checks the downloaded sequence and saves the raw record as data/AGA.fasta.

3. **Sequence Composition Analysis**
   - Calculates the total protein length and the absolute and percentage frequencies of the 20 standard amino acids.
   - Saves the protein length, amino acid counts, and percentages in the results/ directory.

4. **Motif Prediction**
   - Scans the protein sequence for potential N-linked glycosylation motifs following the pattern N-X-S/T, where X is any amino acid except proline (P).
   - Saves the motif positions in results/AGA_motif_positions.csv.
   - These are predicted sequence motifs and are not confirmed glycosylation sites.

5. **Visualization and Reporting**
   - Creates an amino acid composition bar chart and saves it as figures/AGA_amino_acid_composition.png.
   - Creates a linear coordinate plot of potential N-glycosylation motifs and saves it as figures/AGA_potential_N_glycosylation.png.
   - Prints a summary of the protein length, amino acid composition, and detected motifs in the R console.

### Amino Acid Composition

<img width="2400" height="1350" alt="AGA_amino_acid_composition" src="https://github.com/user-attachments/assets/a8cc9ce5-6712-4ecd-9cc3-05e123d689b2" />

**Figure 1:** A bar plot showing the frequency of each standard amino acid in the AGA protein sequence. The most abundant amino acid will be identified from the calculated composition results.

### Potential N-Glycosylation Motifs

<img width="2400" height="990" alt="AGA_potential_N_glycosylation" src="https://github.com/user-attachments/assets/04e2c81c-313b-4b57-a5c9-a69ecd8cd694" />

**Figure 2:** A linear coordinate plot showing the locations of predicted N-linked glycosylation consensus motifs (`N-X-S/T`, where `X` is not proline) along the AGA protein sequence. The total number and exact positions are reported by the analysis.

## Questions and Answers

1. **What does your enzyme normally break down inside lysosomes?**

   AGA helps break down glycoproteins by cleaving the bond between N-acetylglucosamine and asparagine in N-linked oligosaccharides. This reaction is one of the final steps in the lysosomal degradation of certain glycoproteins.

2. **What is the total length of your protein, and which amino acids are most common?**

   The protein length and amino acid frequencies are determined from the downloaded NCBI protein sequence. The most abundant amino acid is identified by comparing the calculated counts of all 20 standard amino acids.

3. **How many potential N-glycosylation motifs did you find, and where are they located?**

   The number and positions of potential N-glycosylation motifs are determined by scanning the AGA sequence for the pattern `N-X-S/T`, excluding motifs where X is proline. The exact number and residue positions are provided in `results/AGA_motif_positions.csv`.

4. **Why can glycosylation matter for lysosomal proteins? Does finding a motif prove that the protein is glycosylated?**

   Glycosylation can help proteins fold correctly, maintain stability, and move through the cellular secretory pathway toward their proper destinations. However, finding an `N-X-S/T` motif only identifies a potential N-glycosylation site. It does not prove that the site is actually glycosylated in living cells; experimental evidence is needed to confirm this.

5. **What could happen in the cell if your enzyme did not work properly?**

   If AGA is deficient or nonfunctional, glycoprotein-derived degradation products cannot be processed normally and may accumulate in lysosomes. This causes aspartylglycosaminuria, a lysosomal storage disorder associated with progressive cellular dysfunction and neurological problems.

## References

- [NCBI Gene: AGA (Gene ID: 175)](https://www.ncbi.nlm.nih.gov/gene/175)
- [NCBI Protein: NP_000018.2](https://www.ncbi.nlm.nih.gov/protein/NP_000018.2)
- [NCBI Nucleotide: NM_000027.4](https://www.ncbi.nlm.nih.gov/nuccore/NM_000027.4)
- [UniProt: P20933](https://www.uniprot.org/uniprotkb/P20933)

