## Setting up *micromamba* env. 

```{sh}
curl micro.mamba.pm/install.sh | bash
bash
micromamba config prepend channels bioconda
micromamba config prepend channels conda-forge
micromamba create -n HiC \
   'python>=3.7.12' \
   'hicstuff>=3.1.5' 'chromosight>=1.6.3' \
   'cooler>=0.9.1' 'cooltools>=0.5.1' \
   'samtools>=1.7' 'bowtie2>=2.4.5' 'bedtools>=2.30.0' 'deeptools>=3.5.1' \
   'matplotlib>=3.5.3' 'tree>=2.0.0'  
micromamba activate HiC
```
