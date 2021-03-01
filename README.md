# DNAMAPP_Pipeline
 
 **A simple pipeline as a strategy to use raw data, in order to evaluate the distribution of satcNA PcP190 in the anuran genomes available in public data access platforms and, thus, provide evidence about the existence of these repetitive sequences in the genomes**.
 
 
 ***
  ## Requirements for using the Pipeline
### Install the programs on the Linux system:
- [ ] BWA 0.7.17 (Burrows-Wheeler Aligner)
- [ ] Samtools 1.9 (Sequence Aligment/Map) 



***
### How do I get the species'genomes and their numbers?

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
Follow the code file (in this repository) commands step by step
```

***
 # Pipeline workflow
 ![Figure 1 para git](https://user-images.githubusercontent.com/78439023/109512259-abb47680-7a82-11eb-9693-b0d35867820f.png)

 ***
 
 __Through the construction of the pipeline, we describe a protocol that allows the search and identification of the satDNA PcP190. This protocol made it possible to recognize this family of satDNA in five new species. The variation found in the number of reads between closely related species could be explained by the hypothesis of repetitive DNA library__.
 
__The data generated in this work show that the pipeline was able to map readings of satellite DNA, providing a model to verify the presence / absence of different sequences in the genomes and represent an initial screening strategy for future research in the presence / absence analysis of families of Satellite DNA in the available genomes__.




 
 
