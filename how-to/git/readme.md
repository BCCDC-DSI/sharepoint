 

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

## Create/ Update Jupyter kernel

To create a kernel of the VE for use in Jupyter notebook, e.g.:

```ipython kernel install --user --name=r3.6-py3.11-streamlit```



## Git

[Summary list created by Rochelle A. on May 28, 2023](https://rochellea.medium.com/your-git-cheat-sheet-commands-to-remember-1381db3f8efd)


| Terms | Meaning |
| :-- | :-- |
| ```master``` | local branch, typically refers to your copy |
| ```origin``` | remote branch |

### Abstract

Below adapted from [EHS group](\\root\BCCDC\Groups\EHS\Research and Surveillance\Projects\GitRepositories\Git_Instructions.pdf).

You create a new **master** copy that will be stored **locally** on your computer whenever you clone from a remote repository via a command like this:
```git clone "\\root\BCCDC\Groups\EHS\Research and Surveillance\Projects\GitRepositories\XXX"```

Each new session/day, it is good practice to compare your local branch with the remote one:
```git remote show origin```


If the output mentions:
- ***fast-fowardable***, you can push your changes to remote
- ***local out of date***, your local copy is behind the remote branch

To update your local copy, issue:
```git pull origin master```

To update the remote, **replace ```pull``` from above with ```push```**.

i.e. you **push** local changes to remote/master branch.

Staging 
### Typical workflow

1. Work on your branch.
2. Stage files that you want to commit.
3. Commit the changes.
4. Repeat steps 2-4 for other tasks as needed.
5. Push changes to the remote repository when ready.



# Tips & Best Practices

## Use Universal Naming Convention (UNC) instead of dos path 

  R example
  ```
  sys.setenv(RENV_PATHS_CACHE = "\\phsabc\BCCDC\Groups\Analytics_Resources\Coding\R\global_renv\cache") 
  ```
