
#  DNA photolithography sequencing methods and results



# Overview of bioinformatic methods

## Sequence panel design

Sequences were designed to maximise the kmer content diversity while avoiding long internal homopolymers and oligonucleotides with a high secondary structure probability. To do so we started by generating 1 million random candidate sequences of 50 bases long, flanked by an 11 base "A" homopolymer in 3' and an 6 bases "C" homopolymer in 5'. These terminal homopolymers were added for library preparation and data processing reasons. No internal homopolymer longer that 5 bases was allowed during sequence generation. We ran RNAFold (ViennaRNA_2.4.3) to calculate the minimum free energy (MFE) of each sequences, and filtered out any sequence with an MFE lower than -17.6. We obtained a pool of 948,364 valid sequences covering all possible 16356 7-mers, not counting kmers containing homopolymers which were excluded. We then randomly sampled 20,000 sequences from the pool 500,000 times and selected the set of sequencing optimizing the 7-mers content.

The entire analysis is available in the following jupyter notebook: 
The sequence panel reference used for synthesis is available at the following address: 

## Library preparation and Illumina sequencing

Samples were all prepared using the Accel-NGS 1S Plus DNA Library Kit from Swift Biosciences. 
We used 5 ng of each sample as input into the library preparation protocol following manufacturer's instructions.
In order to multiplex the samples for sequencing we used the following barcoded :
O1 (index 2) = Normal DNA synthesis parameters
O2 (index 4) = Cap protecting step between each iteration
O3 (index 5) = Increase space between synthesis clusters
Final libraries were sequenced using a MiSeq Instrument and v2 Nano cartridge following the manufacture instructions. 

## Sequencng data analysis

