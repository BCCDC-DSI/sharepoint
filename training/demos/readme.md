

## Installation 

[under construction]


## Starting and creating a new virtual environment 

```
conda create name_of_vir_enviorn
```

## Returning to your session

1. Reactivate virtual environment that is named ```python3.11```:
    ```
    conda activate python3.11  
    conda install streamlit   # akin to R Shiny
    conda install -c conda-forge polars  # queries for large database 
    ```
    
1. If you wish to use Juypter notebook, create a kernel specs using ```ipykernel-py3.11```:
    ```
    python -m ipykernel install --user --display-name "r3.6-py3.11-streamlit"
    ```
  
    The specs will be saved under: 
    ```
    C:\Users\your_username\AppData\Roaming\jupyter\kernels\ipykernel-py3.11
    ```

1. Mount netowrkdrive and launch jupyter notebook on your default browser
    ```
    jupyter notebook --notebook-dir=\\phsabc.ehcnet.ca\root\
    ```
