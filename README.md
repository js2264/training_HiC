## Installing `micromamba` 

If you do not have `micromamba` already installed, run the following lines once:  

```sh
apt update && apt install curl -y 
"${SHELL}" <(curl -L micro.mamba.pm/install.sh)
## Here, press ENTER to each question

source ~/.bashrc
```

## Setting up a dedicated `micromamba` environment

This has to be ran just once. 
It can be ran on a local workstation or on a HPC (e.g. `maestro`).

```sh
## Set up a `hicstuff` environment
micromamba create -n hicstuff && micromamba activate hicstuff

## Install relevant softwares
micromamba install -c bioconda -c conda-forge "python>=3.10" numpy pysam cython
micromamba install -c bioconda -c conda-forge pairtools samtools bowtie2
micromamba install -c bioconda -c conda-forge hicstuff chromosight cooltools
hicstuff --version
```

## Process a Hi-C library (Yeast)

```sh
cpu=12
sample="testHiC"
genome="R64-1-1"
outdir="results"
## Command (does not need to activate the environment)
micromamba run -n hicstuff hicstuff pipeline \
    --threads "${cpu}" \
    --enzyme DpnII,HinfI \
    --filter \
    --duplicates \
    --prefix "${sample}" \
    --binning 1000 \
    --plot \
    --distance-law \
    --outdir "${outdir}" \
    --genome tests/"${genome}"/"${genome}".fa \
    tests/"${sample}"_R1.fq.gz tests/"${sample}"_R2.fq.gz
```
