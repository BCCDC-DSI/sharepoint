 

# Installing R and Git on your desktop station 

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

## Other Conda commands

To see what was installed in your VE, issue:
  ```
  conda list
  ```



# Tips & Best Practices

## Use Universal Naming Convention (UNC) instead of dos path 

  R example
  ```
  sys.setenv(RENV_PATHS_CACHE = "O:/BCCDC/Groups/Analytics_Resources/Coding/R/global_renv/cache") 
  ```
