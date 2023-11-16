# DNAMAPP_Pipeline
 
 **A simple pipeline as a strategy to use raw data, in order to evaluate the distribution of satcNA PcP190 in the anuran genomes available in public data access platforms and, thus, provide evidence about the existence of these repetitive sequences in the genomes**.
 
 
 
 ***
  ## Requirements for using the Pipeline
### Install the programs on the Linux system:
**1. BWA 0.7.17 (Burrows-Wheeler Aligner)
**2. Samtools 1.9 (Sequence Aligment/Map) 


- BWA

            1. wget https://sourceforge.net/projects/bio-bwa/files/bwa-0.7.17.tar.bz2
            2. tar -xjvf bwa-0.7.17.tar.bz2
            3. cd bwa
            4. make 

- Samtools 

            1. wget https://github.com/samtools/samtools/releases/download/1.4.1/samtools-1.4.1.tar.bz2 -O samtools.tar.bz2
            2. tar -xjvf samtools.tar.bz2 
            3. cd samtools-1.4.1/
            4. ./configure
            5. make
            6. make install



***
## How do I get the species' genomes and their numbers?

* All SRAs (Sequence Read Archive) are selected, using the data available at the National Center for Biotechnology Information (NCBI), on the platform (https://www.ncbi.nlm.nih.gov/sra). 
  * Each species will have an SRA (ID number). It is with it that the user will work.
  
* The SRAs will be downloaded through the SRA EXPLORER online platform, free of charge (https://sra-explorer.info/#), in the *fastq.gz* format.
  * In this study, table 1, lists the name of the anuran species and their SRAs.
 


**ex:**
Species name | Respective SRAs of the species
---|---
Anuran species 1 | SRA number
Anuran species 2 | SRA number
Anuran species 3 | SRA number



 ***
 
 

### Using the programs

```
If you prefer, follow the complete file commands step by step, the file is present in this repository, go to the folder> supplementary material> supplementary files> supplementary file 2. 
```



- Construction of the index (sequences / genomes of interest for the search) in the       format.fasta.

            1. bwa sequences_index.fasta
            2. bwa mem seqs_index.fasta  SRA_1.fastq SRA_2.fastq > Anuran_especies_mapping.sam 
            
 - Conversion, manipulation and data extraction, through Samtools 1.9

            1. samtools view -bS Anuran_especies_mapping.sam> Anuran_especies_mapping.bam
            2. samtools sort Anuran_especies_mapping.bam > Anuran_especies_mapping_sorted.bam
            3. samtools view -b -F 4 Anuran_especies_mapping_sorted.bam > Anuran_especies _mapping_sorted_mapped.bam
            4. samtools index Anuran_especies_mapping_sorted_mapped.bam > Anuran_especies _mapping_sorted_mapped.bam.bai
            
            
            
```
Using visualization software, in this case the Tablet (1.19.09.03), the user compares the last two generated files, with each other. (To see generated images, in this work, go to Supplementary material> supplementary figures).
```


***
 # Pipeline workflow
 ![Figure 1 para git](https://user-images.githubusercontent.com/78439023/109512259-abb47680-7a82-11eb-9693-b0d35867820f.png)

 ***
 
 
 __Through the construction of the pipeline, we describe a protocol that allows the search and identification of the satDNA PcP190. This protocol made it possible to recognize this family of satDNA in five new species. The variation found in the number of reads between closely related species could be explained by the hypothesis of repetitive DNA library__.
 
__The data generated in this work show that the pipeline was able to map readings of satellite DNA, providing a model to verify the presence / absence of different sequences in the genomes and represent an initial screening strategy for future research in analysis of families of Satellite DNA in the available genomes__.




 
 
