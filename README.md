
#  DNA photolithography sequencing methods and results

## Overview of sequencing and bioinformatic methods

### Sequence panel design

Sequences were designed to maximise the kmer content diversity while avoiding long internal homopolymers and oligonucleotides with a probability of having a strong secondary structure. To do so we started by generating 1 million random candidate sequences of 50 bases long, flanked by an 11 base "A" homopolymer in 3' and an 6 bases "C" homopolymer in 5'. These terminal homopolymers were added for library preparation and data processing reasons. No internal homopolymer longer that 5 bases was allowed during sequence generation. We ran RNAFold (ViennaRNA_2.4.3) to calculate the minimum free energy (MFE) of each sequences, and filtered out any sequence with an MFE lower than -17.6. We obtained a pool of 948,364 valid sequences covering all possible 16356 7-mers, not counting kmers containing homopolymers which were excluded. We then randomly sampled 20,000 sequences from the pool 500,000 times and selected the set of sequencing optimizing the 7-mers content.

* Full analysis notebook: [Jupyter notebook](https://a-slide.github.io/DNA_photolitography_seq/notebooks/Sequence_panel_design.html)
* Reference sequence panel generated: [FASTA](https://github.com/a-slide/DNA_photolitography_seq/raw/main/results/reference/DNA_test_sequence_panel_selection.fa.gz)

### Library preparation and Illumina sequencing

Samples were all prepared using the Accel-NGS 1S Plus DNA Library Kit from Swift Biosciences. We used 5 ng of each sample as input into the library preparation protocol following manufacturer's instructions.

In order to multiplex the samples for sequencing we used the following barcoded :
* O1 (index 2) = Normal DNA synthesis parameters
* O2 (index 4) = Cap protecting step between each iteration
* O3 (index 5) = Increase space between synthesis clusters

Final libraries were sequenced using a MiSeq Instrument and v2 Nano cartridge following the manufacture instructions in paired-end mode (2x150bp)

### Sequencing data analysis

Fastq files were obtained and demultiplexed with Illumina Casava bcl2fastq2 Conversion Software v2.20 and adapters were trimmed off using Cutadapt (v1.1.18) to a minimal read length of 20 bases.
Reads were subsequently aligned to the sequence panel reference previously generated using Bowtie2 (v2.3.4.3), then sorted and indexed with samtools (v1.9). Finally, we performed the error rate analysis overlayed on the flowcell layout or as a function the reference base position using python programming language via a Jupyter Notebook.

* Full analysis notebook: [Jupyter notebook](https://a-slide.github.io/DNA_photolitography_seq/notebooks/Illumina_error_rate_analysis.html)
* Plots generated during the analysis: [Flowcell layout error rate](https://github.com/a-slide/DNA_photolitography_seq/tree/main/results/flowcell_layout_error_rate/) and [Reference position error rate](https://github.com/a-slide/DNA_photolitography_seq/tree/main/results/ref_position_error_rate)
* Raw illumina datasets: [ENA_PRJEB43002](https://www.ebi.ac.uk/ena/browser/view/PRJEB43002)

## Citation

* Publication: When published

* Repository: Zenodo repo when public 

## Licence

MIT

Copyright © 2020 Adrien Leger

## Authors

Adrien Leger / aleg@ebi.ac.uk / https://adrienleger.com
