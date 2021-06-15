# vNvS - Viral dN/dS

Calculation of dN/dS from viral Next Generation Sequencing (NGS) / High Throughput Sequencing (HTS) data. This program is based on the initial work of Marco Morelli and Dan Haydon for foot-and-mouth disease virus:

**Evolution of foot-and-mouth disease virus intra-sample sequence diversity during serial transmission in bovine hosts**
Morelli et al
[https://veterinaryresearch.biomedcentral.com/articles/10.1186/1297-9716-44-12](https://veterinaryresearch.biomedcentral.com/articles/10.1186/1297-9716-44-12)

**A blog of the methodology is presented here:**

[https://bioinformatics.cvr.ac.uk/calculating-dnds-for-ngs-datasets/](https://bioinformatics.cvr.ac.uk/calculating-dnds-for-ngs-datasets/)

The program is written in Java and currently requires a SAM file as input (currently updating the code to work with a BAM file), the reference file used in the alignment, and ORF file, and a window size:

```
java -jar DNDS.jar ref.fasta sample.sam orfs.txt 50
```

ref.fasta - is the reference file in fasta format
sampple.sam - is the SAM file of the sample to be analysed
orf.txt - is a simple one line text file giving the start and end co-ordinates of the ORF to analyse (currently only one ORF at a time - update in progress)
50 - is a sliding window size to calculate stats across a sliding window of the ORF

A new version will be release soon that:

1) Works on SAM as well as BAM files
2) Can work on multiple ORFs a the same time (instead of running separately)
3) Includes additional/alternative dN/dS statistics and measures
