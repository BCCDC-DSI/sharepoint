 

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
| ```master``` | local copy, typically refers to your copy |
| ```origin``` | remote copy |

### Abstract

Below adapted from [EHS](\\root\BCCDC\Groups\EHS\Research%20and%20Surveillance\Projects\GitRepositories\Git_Instructions.pdf)

You create a new **master** copy that will be stored **locally** on your computer whenever you clone from a remote repository via a command like this:
```git clone \\root\BCCDC\Groups\Analytics\Data Science and Innovation\Research_Development_Training\Research and Development\Projects\p06_PHIDO_dashboard\GitHub" my_phido_dashboard```

The above creates a folder called ```my_phido_dashboard```.

Each new session/day, it is good practice to compare your local copy with the remote one:
```git remote show origin```


If the output mentions:
- ***fast-fowardable***, you can push your changes to remote
- ***local out of date***, your local copy is behind the remote copy

To update your local copy, issue:
```git pull origin master```

To update the remote copy, i.e. "publish" your changes for every interested user of the remote repository, **replace ```pull``` from above with ```push```**; i.e. you **push** the local changes **up** to the remote.


### Branch

A branch is a new version, usually for experimentation of a "small" change. 

1. To create new branch named ```beta_version```:
```git branch beta_version```

2. To work in this experimental version, make sure you **switch** to this newly created branch like this:
```git checkout beta_version```

You can also run steps 1-2 in one command:
```git checkout -b beta_version```

To integrate your experimental version with your own **master branch (version)**, you first switch back into your **master**:
```
git checkout master
git merge beta_version
```

If you no longer need the experimental version and wish to delete it, issue:
```
git branch -d beta_version
```

### Staging 


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
