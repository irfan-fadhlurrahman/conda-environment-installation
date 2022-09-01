# Conda Environment Installation
This repository is to store a installation guide of conda environment by using yaml file. The drawbacks are it takes time to install a complete environment and prone to error. So only install library that really need dependencies and install other library with pip.

## 0. Activate conda on your terminal
```
 source ~/miniconda3/etc/profile.d/conda.sh
```

## 1. Create enviroment.yml files
```
nano enviroment.yml
```

## 2. Write your own environment setup
* name: your environment name
* do not forget to specify python version, in the example using **python 3.8**
* to ensure reproducibility, please specify **library version** i.e.
  ```
  - scikit-learn=1.1.1
  - pyarrow==8.0.0 
  ```
```
name: personal_env_py38  
channels:
  - conda-forge
dependencies:
  - python=3.8
  - jupyterlab
  - ipywidgets
  - findspark
  - pip
  - pip:
     - scikit-learn==1.1.1
     - pyarrow==8.0.0 
```

## 3. Install environment.yml
```
conda env create --file environment.yml
```

## 4. Check the installed environment
```
conda activate personal_env_py38
conda info --envs
```
