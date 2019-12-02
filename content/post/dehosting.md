+++
title = "Removing host sequences in microbiome datasets"
date = 2017-03-03
tags= ['bowtie2', 'metagenomics']
math = false
highlight = true
summary= "Analyzing metagenomic or metatranscriptomic sequencing datasets can cause a lot of trouble when excesive depth is utilized. This is true for microbiome studies that include the host background in the dataset. De-hosting by mapping the total dataset to the host genome could help with the assembly of this type of datasets."
+++


Removing host sequences to alleviate the time consuming assembly tasks is helpful when the host genome is available. There are a few steps that need to be followed to achieve the "dehosting" process.


## 1. Bowtie2 mapping to the host
Mapping all reads to the host genome allows to know which are the reads that need to be eliminated.
##### a.  Create bowtie2 index database (host_DB) from host reference genome
```bash=1
bowtie2-build host_genome.fna host_DB
```
##### b. bowtie2 mapping against host sequence database, keep both mapped and unmapped reads (paired-end reads)
```bash=1
bowtie2 -x host_DB -1 SAMPLE_r1.fastq -2 SAMPLE_r2.fastq -S SAMPLE_mapped_and_unmapped.sam
```

##### c.  Convert file `.sam` to `.bam`

```bash=1
samtools view -bS SAMPLE_mapped_and_unmapped.sam > SAMPLE_mapped_and_unmapped.bam
```

## 2. filter required unmapped reads

##### a. SAMtools SAM-flag filter: get unmapped pairs (both ends unmapped)
```bash
samtools view -b -f 12 -F 256 SAMPLE_mapped_and_unmapped.bam > SAMPLE_bothEndsUnmapped.bam
```
-f 12     Extract only (-f) alignments with both reads unmapped: <read unmapped><mate unmapped>
-F 256   Do not(-F) extract alignments which are: <not primary alignment>


## 3. split paired-end reads into separated fastq files .._r1 .._r2

##### a.  Sort bam file by read name (-n) to have paired reads next to each other as required by bedtools
```bash
samtools sort -n SAMPLE_bothEndsUnmapped.bam SAMPLE_bothEndsUnmapped_sorted
```
##### b. Convert bam to fastq
```bash
bedtools bamtofastq -i SAMPLE_bothEndsUnmapped_sorted.bam -fq SAMPLE_host_removed_r1.fastq -fq2 SAMPLE_host_removed_r2.fastq
```
