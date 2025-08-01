# SRA data analysis workflow for detection of satDNA PcP190 in anurans
 
 **A simple pipeline as a strategy to use raw data, in order to evaluate the distribution of satcNA PcP190 in the anuran genomes available in public data access platforms and, thus, provide evidence about the existence of these repetitive sequences in the genomes**.
 
 
 
 ***
  ## Requirements for using the Pipeline
### Install the programs on the Linux system:
## Prerequisites

Install required development packages before building the tools:

```bash
sudo apt update
sudo apt install build-essential zlib1g-dev libbz2-dev liblzma-dev \
libncurses5-dev libcurl4-openssl-dev autoconf



- BWA

            1. wget https://sourceforge.net/projects/bio-bwa/files/bwa-0.7.17.tar.bz2
            2. tar -xjf bwa-0.7.17.tar.bz2
            3. cd bwa
            4. make

            # (Optional) Move the executable to a system-wide location
              - sudo cp bwa /usr/local/bin/

            # Check BWA
              bwa
            # Output should show the BWA command options

- Samtools 

            1. wget https://github.com/samtools/samtools/releases/download/1.20/samtools-1.20.tar.bz2
            2. tar -xjf samtools-1.20.tar.bz2
            3. cd samtools/
            4. ./configure
            5. make
            6. sudo make install

            # Check Samtools version
              samtools --version
              # Output should be: samtools 1.20
         
            


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

```

### 🛠️ Mapping Workflow (using BWA)
- Sequences of the satDNA PcP190 isolated from different species of anurans, used in this mapping experiment (Table 2) and and the SRAS of each species in this study.

     **Index the reference sequences** (PcP190 consensus or species-specific repeats):

            1. bwa sequences_index.fasta
            2. bwa mem seqs_index.fasta  SRA_1.fastq SRA_2.fastq > Anuran_especies_mapping.sam 
            
 - 🛠️ Conversion, manipulation and data extraction, through Samtools.
          ## Processing SAM to Sorted and Indexed BAM with Samtools

        Once the mapping is complete, the `.sam` file can be converted and filtered as follows:

            1. samtools view -bS Anuran_especies_mapping.sam> Anuran_especies_mapping.bam
            2. samtools sort Anuran_especies_mapping.bam > Anuran_especies_sorted.bam
            3. samtools view -b -F 4 Anuran_especies_sorted.bam > Anuran_especies_sorted_mapped.bam
            4. samtools index Anuran_especies_sorted_mapped.bam > Anuran_especies_sorted_mapped.bam.bai


          ##  Check how many reads are in the BAM file
            1. samtools view -c Anuran_especies_sorted_mapped.bam
                   
            
            
```
Using visualization software—specifically Tablet (version 1.21.02 )—the user compares the last two generated files with each other.
```


***
 # Pipeline workflow
 ![Figure 1 para git](https://user-images.githubusercontent.com/78439023/109512259-abb47680-7a82-11eb-9693-b0d35867820f.png)

 ***
 
 
 __Through the construction of the pipeline, we describe a protocol that allows the search and identification of the satDNA PcP190. This protocol made it possible to recognize this family of satDNA in five new species. The variation found in the number of reads between closely related species could be explained by the hypothesis of repetitive DNA library__.
 
__The data generated in this work show that the pipeline was able to map readings of satellite DNA, providing a model to verify the presence / absence of different sequences in the genomes and represent an initial screening strategy for future research in analysis of families of Satellite DNA in the available genomes__.




 
 
