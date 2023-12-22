 

# Create virtual environment with latest R and Git on your desktop station 

Warning: Local R version vs. version on server

1. Anaconda Powershell
2. Create virtual environment (VE) named ```R```
   ```
   conda create --name R R
   ```
3. Activate this VE:
   ```
   conda activate R
   ```
5. Install Git via "anaconda" channel (```-c``` switch; c stands for channel):
   ```
   conda install -c anaconda git
   ```

# Adding other environments in the same VE

1. Python:
   ```
   conda install python ipython
   ```
   
2. Other Python packages
   ```
   conda install plotly streamlit
   ```
   
## Other Conda commands

To see what was installed in your VE, issue:
  ```
  conda list
  ```

## Git

[Summary list created by Rochelle A. on May 28, 2023](https://rochellea.medium.com/your-git-cheat-sheet-commands-to-remember-1381db3f8efd)


# Tips & Best Practices

## Use Universal Naming Convention (UNC) instead of dos path 

  R example
  ```
  sys.setenv(RENV_PATHS_CACHE = "\\phsabc\BCCDC\Groups\Analytics_Resources\Coding\R\global_renv\cache") 
  ```
