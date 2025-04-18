# Investigating Colistin Resistance in Bacteria

## Project Overview

This project aims to identify the gene(s) responsible for **colistin resistance** in bacteria by analyzing a plasmid DNA sequence. Colistin, a last-resort antibiotic, has seen rising resistance, posing serious public health threats. Using bioinformatics tools like **ORF Finder**, **BLAST**, and **Jalview**, the project investigates gene prediction, functional annotation, and evolutionary conservation of resistance genes across bacterial strains.

---

## Problem Statement

Scientists discovered a bacterial isolate resistant to **colistin** in an animal farm. Plasmid DNA from the isolate was sequenced, and the challenge was to identify any gene conferring colistin resistance, specifically through analysis of open reading frames (ORFs) and their protein products.

---

## Tools & Methodology

### ORF Finder
- Tool used: NCBI ORF Finder
- Parameters:
  - Genetic Code 11 (Bacterial)
  - Min ORF length: 150 nt
  - Excluded nested ORFs
- Output: 30 ORFs identified (only those with ≥95 amino acids were analyzed further)

### BLASTp
- Compared ORF-predicted protein sequences against **UniProtKB/Swiss-Prot** database
- Parameters:
  - E-value: 0.01
  - Max target sequences: 100
  - Word size: 6
  - Matrix: BLOSUM90
- Purpose: Confirm protein-coding potential and annotate protein function

### Functional Annotation
- Matched accession numbers to **UniProt** entries
- Focused on identifying **polymyxin resistance proteins** (e.g., EptA, PmrC)

### BLASTn & MSA
- Used BLASTn with the PmrC gene sequence to identify similar resistance genes in other bacterial genomes
- Performed multiple sequence alignment (MSA) using **Jalview**
- Analyzed nucleotide and amino acid variations across bacterial strains

---

## Key Findings

- Identified **Phosphoethanolamine transferase EptA / Polymyxin resistance protein PmrC** as the likely gene responsible for colistin resistance.
- Protein modifies lipid A in the bacterial membrane, reducing its negative charge to confer resistance.
- BLASTn analysis revealed similar genes in *E. coli* and *Klebsiella pneumoniae* strains.
- MSA revealed significant nucleotide and amino acid variations, notably at:
  - **Position 937** (Isoleucine → Valine)
  - **Position 993** (A → T; transversion mutation)

---

## Biological Significance

Understanding resistance mechanisms like that of **PmrC** provides insight into:
- Antibiotic resistance evolution
- Potential molecular targets for future therapeutics
- Surveillance of resistance gene spread via plasmids

---

## File Contents

- `Plasmid_sequence.txt` – Input DNA sequence
- `ORF_results.txt` – Output from ORF Finder
- `BLAST_results.csv` – BLASTp analysis summary
- `PmrC_variants.aln` – MSA alignment file
- `README.md` – This file

---

## References

1. [DrugBank - Colistin](https://go.drugbank.com/drugs/DB00803)  
2. [NCBI PMC - Colistin resistance mechanisms](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8406936/)  
3. [NCBI Guide to BLAST](https://chanzuckerberg.zendesk.com/hc/en-us/articles/360050963352-A-guide-to-BLAST)  
4. [UniProtKB - PmrC](https://www.uniprot.org/uniprotkb/P36555/entry#function)

---  
