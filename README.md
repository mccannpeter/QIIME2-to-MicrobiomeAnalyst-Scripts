QIIME2-to-MicrobiomeAnalyst-Scripts

This script automates the process of:

Copying and renaming raw FASTQ files using a SampleSheet.csv.
Running QIIME 2 analyses (import, DADA2 denoising, taxonomic classification, and barplot generation).
Formatting metadata to be compatible with MicrobiomeAnalyst.
Preparing count and taxonomy tables for use in R-based decontamination (via the decontam package) and other downstream analyses.
The pipeline first copies .fastq.gz files from a specified directory into the current folder. It then parses SampleSheet.csv to create a mapping from sample IDs to user-friendly descriptions, renaming the FASTQ files accordingly. Next, the script runs QIIME 2 commands (such as DADA2 and taxonomic classification) and produces outputs like demux-paired-end.qza, table-dada2.qza, and taxonomic barplots.

Finally, it outlines R steps to read QIIME 2 outputs into phyloseq, remove contaminants using decontam, and export cleaned data. This helps ensure that only high-quality sequences remain for downstream analyses in MicrobiomeAnalyst or other platforms. If you plan to run the R portions, you’ll need to install phyloseq, decontam, ggplot2, and biomformat.