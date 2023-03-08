## Setting up the conda env. (does not require anything installed)

If you do not have `conda` already installed, run the following chunk: 

```
wget https://repo.anaconda.com/miniconda/Miniconda3-py310_23.1.0-1-Linux-x86_64.sh
bash Miniconda3-py310_23.1.0-1-Linux-x86_64.sh
bash
```

For everybody, run: 

```
conda env create --file https://raw.githubusercontent.com/js2264/training_HiC/main/requirements.yml
```
