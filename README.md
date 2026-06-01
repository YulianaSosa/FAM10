# Family 10 Variant Filtering Analysis
*Author: Yuliana Denisse Sosa Gómez*
## Overview

This project contains the variant filtering workflow performed to identify rare candidate variants potentially responsible for the disease phenotype observed in **Family 10**.

The analysis was conducted using whole-exome sequencing variant data and a pedigree-based filtering strategy to prioritize potentially pathogenic variants.

## Software Requirements

* **R version:** 4.4.1
* **dplyr version:** 1.2.1

## Dataset Description

The input dataset contains annotated genetic variants for the proband and available family members. A detailed description of all dataset columns is provided within the script.

## Filtering Strategy

The filtering pipeline was designed to progressively reduce the number of candidate variants by applying quality, population frequency, functional, and pedigree-based criteria.

### 1. Genomic Coverage Filtering

Variants were required to have a minimum sequencing depth of: **Coverage ≥ 10X**

### 2. Alternate Allele Ratio Filtering

Variants were required to have sufficient support from alternate allele reads: **Alternate allele ratio (VR/TR) ≥ 0.20**

### 3. Genotype Quality Filtering

Variants were required to meet the following genotype confidence threshold: **Genotype Quality (GQ) ≥ 30**

### 4. Minor Allele Frequency (MAF) Filtering

Common variants were excluded using population databases:

* **1000 Genomes Project (TGP_FREQ)**
* **NHLBI Exome Sequencing Project (ESP_FREQ)**
* **Exome Variant Server (EVE_ALT_FREQ)**

Filtering threshold: **MAF < 1% (0.01)**

### 5. Functional Consequence Filtering

Synonymous variants were removed to prioritize variants with potential functional impact.

### 6. Family-Based Filtering

Variants homozygous in unaffected family members were excluded, as these variants would be unlikely to explain the disease phenotype.

### 7. Pedigree-Based Inheritance Models

Three inheritance models were evaluated:
* Autosomal Recessive
* De Novo Mutations
* Compound Heterozygosity

## Results

After applying all filtering steps and evaluating the inheritance models, the strongest candidate gene identified was: **ST3GAL5**

Variants in **ST3GAL5** have been associated with **Salt and Pepper syndrome**, a rare neurodevelopmental disorder characterized by developmental delay, movement abnormalities, and characteristic skin pigmentation findings.

## Conclusion

The filtering strategy successfully reduced the initial variant set to a small number of biologically plausible candidates. Based on variant rarity, inheritance pattern, functional annotation, and known disease associations, **ST3GAL5** emerged as the most likely disease-causing gene in Family 10.
