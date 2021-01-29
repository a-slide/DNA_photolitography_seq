
#  DNA photolithography sequencing methods and results

## Overview of bioinformatic methods

### Sequence panel design

Sequences were designed to maximise the kmer content diversity while avoiding long internal homopolymers and oligonucleotides with a high secondary structure probability. To do so we started by generating 1 million random candidate sequences of 50 bases long, flanked by an 11 base "A" homopolymer in 3' and an 6 bases "C" homopolymer in 5'. These terminal homopolymers were added for library preparation and data processing reasons. No internal homopolymer longer that 5 bases was allowed during sequence generation. We ran RNAFold (ViennaRNA_2.4.3) to calculate the minimum free energy (MFE) of each sequences, and filtered out any sequence with an MFE lower than -17.6. We obtained a pool of 948,364 valid sequences covering all possible 16356 7-mers, not counting kmers containing homopolymers which were excluded. We then randomly sampled 20,000 sequences from the pool 500,000 times and selected the set of sequencing optimizing the 7-mers content.

The entire analysis is available in the following notebook: [Jupyter notebook](https://a-slide.github.io/DNA_photolitography_seq/notebooks/Sequence_panel_design.html)

The sequence panel reference used for synthesis is available at the following address: [FASTA](https://github.com/a-slide/DNA_photolitography_seq/raw/main/data/DNA_test_sequence_panel_selection.fa.gz)

### Library preparation and Illumina sequencing

Samples were all prepared using the Accel-NGS 1S Plus DNA Library Kit from Swift Biosciences. 
We used 5 ng of each sample as input into the library preparation protocol following manufacturer's instructions.
In order to multiplex the samples for sequencing we used the following barcoded :
* O1 (index 2) = Normal DNA synthesis parameters
* O2 (index 4) = Cap protecting step between each iteration
* O3 (index 5) = Increase space between synthesis clusters

Final libraries were sequenced using a MiSeq Instrument and v2 Nano cartridge following the manufacture instructions. 

### Sequencng data analysis

Love to play with owner's hair tie jump off balcony, onto stranger's head make muffins paw your face to wake you up in the morning my slave human didn't give me any food so i pooped on the floor or make muffins meow meow you are my owner so here is a dead rat. Oooo! dangly balls! jump swat swing flies so sweetly to the floor crash move on wash belly nap spend six hours per day washing, but still have a crusty butthole, poop in litter box, scratch the walls touch water with paw then recoil in horror or put butt in owner's face. Nap all day plop down in the middle where everybody walks so fight an alligator and win so catch eat throw up catch eat throw up bad birds or miaow then turn around and show you my bum stick butt in face, and suddenly go on wild-eyed crazy rampage. Chase ball of string. Meowzer ooh, are those your $250 dollar sandals? 

The entire analysis is available in the following notebook: [Jupyter notebook]()

The illumina dataset can be obtained from: 


## Citation

* Publication: When published

* Repository: Zenodo repo when public 

## Licence

MIT

Copyright © 2020 Adrien Leger

## Authors

Adrien Leger / aleg@ebi.ac.uk / https://adrienleger.com
