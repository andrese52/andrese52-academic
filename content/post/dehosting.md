+++
title = "Removing Host sequences in microbiome datasets"
date = 2017-03-03
tags= ['bowtie2', 'metagenomics']
math = false
highlight = true
summary= "Analyzing metagenomic or metatranscriptomic sequencing datasets can cause a lot of trouble when excesive depth is utilized. This is true for microbiome studies that include the host background in the dataset. De-hosting by mapping the total dataset to the host genome could help with the assembly of this type of datasets."
+++

Removing host sequences to alleviate the time consuming assembly tasks is helpful when the host genome is available. There are a few steps that need to be followed to achieve the "dehosting" process. 

1. Bowtie2 mapping to the host
2. Samtools to extract mapped reads
3. Bedtools to split paired ends.



{{< youtube id="6oTzYnQY17Q" autoplay="false" >}}