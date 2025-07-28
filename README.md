# GateDiffST: Installation Guide  
This document provides the environment setup and installation steps for GateDiffST.  


## 1. Environment Preparation  
Create a dedicated Conda environment for GateDiffST:  
```bash
# Create and activate the environment
conda create -n GateDiffST
source activate GateDiffST  # For Linux/macOS; use "conda activate GateDiffST" for Windows

# Install Python
conda install python=3.8
```


## 2. Dependencies Installation  
Install required packages via Conda and pip:  

### Conda Packages  
```bash
# Install system-level dependencies
conda install conda-forge::gmp
conda install conda-forge::pot

# Install PyTorch with CUDA support (CUDA 11.8)
conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
```

### Pip Packages  
```bash
pip install scanpy
pip install anndata==0.8.0
pip install pandas==1.4.2
pip install rpy2==3.5.1  # For R package integration
pip install scikit-learn==1.1.1
pip install scipy==1.8.1
pip install tqdm==4.64.0
pip install einops
```


## 3. R Package Installation  
Install the required R package `mclust` via `rpy2`:  
```python
import rpy2.robjects as robjects

robjects.r('''
    install.packages('mclust')
''')
```

