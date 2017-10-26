# fastq-from-ITSx
These scripts allow ITSx to be used with fastq files, with minimal overhead.

These two R scripts can be used with ITSx in order to get fastq files as an output. This is useful if you are running a program like DADA2 or Unoise3 to cluster your extracted sequence data, since those programs use quality scores of sequences. You'd run these scripts as follows:

./fastq_to_fasta.r -i my_raw_seqs.fastq -o my_raw_seqs.fasta
ITSx -i my_raw_seqs.fasta -o my_extracted_seqs -t --cpu 8 --graphical F --preserve T --save_regions ITS1
./itsx_fastq_extractor.r -f my_extracted_seqs.ITS1.fasta -q my_raw_seqs.fastq --threads 8 -o my_extracted_seqs.ITS1.fastq

Note: This won't work on interleaved files. Not sure if interleaved fastq is a thing, even. I hope not. 
