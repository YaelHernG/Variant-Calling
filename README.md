# Variant Calling in Evolved Yeast Strains
By: Yael Daniel Hernandez Gonzalez

This project performs a comprehensive variant calling analysis on Saccharomyces cerevisiae strains, including a parental strain and two independently evolved strains (IMW004 and IMW005). The aim is to identify candidate mutations associated with adaptive phenotypes (e.g. growth on lactate) and to annotate their biological consequences.

## Analysis Overview
1. Preprocessing & Variant Calling
   
   BAM files aligned to the S288C reference genome.

   Variants called using bcftools mpileup and call.

   Multi-sample VCF files generated and filtered.

3. Variant Filtering

   Applied quality filters: QUAL >= 30, DP > 30, and AD[*:1] >= 50.

   Excluded indels and poorly supported sites.

   Transition/transversion (Ts/Tv) ratio calculated before and after filtering.

5. Comparative Genomics

   Variants unique to evolved strains (IMW004, IMW005) identified by comparing with the parental strain.

   Intersection and difference operations performed using bcftools isec.

7. Variant Annotation with VEP

   Variants annotated using Ensembl VEP (vep --cache) with the Saccharomyces cerevisiae reference.

   Consequences parsed to identify impactful variants: missense, stop gained, frameshift, splice variants.

9. Candidate Gene Prioritization

   Genes mutated in both IMW004 and IMW005 strains were identified as candidates.

   The gene ADY2 was confirmed to be mutated in both strains, consistent with published findings.

11. Ensembl REST API Integration

   Used Ensembl REST API to retrieve detailed annotations for all candidate genes.
   
   Extracted: Ensembl ID, gene name, genomic location, biotype, description, and canonical transcript.

## Outputs
Filtered VCFs for each strain

Lists of strain-specific and shared variants

TSV tables with functional annotation per gene

Annotated gene summary from Ensembl

R and Perl scripts for filtering, annotation, and gene comparison

## Technologies Used

bcftools

vep (Ensembl Variant Effect Predictor)

Ensembl REST API

R (for parsing, analysis, and visualization)

Perl (for parsing annotated VCFs)

bash (SGE job scripts)

[Report]()

Kok et al. (2012): Laboratory evolution of new lactate transporter genes in a jen1D mutant of Saccharomyces cerevisiae and their identification as ADY2 alleles by whole-genome resequencing and transcriptome analysis. FEMS Yeast Res, 12:359-74.


