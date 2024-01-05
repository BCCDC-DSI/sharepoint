# How-to

## Git Bash
<a id='gitbash'></a>

> Git Bash is an application for Microsoft Windows environments which provides an emulation layer for a Git command line experience. Bash is an acronym for Bourne Again Shell. A shell is a terminal application used to interface with an operating system through written commands.

You may need to install ```Anaconda 3``` first.

On Windows: ```START > Anaconda3 > Git Bash```

To change into a directory (i.e. folder location), use ```cd```, e.g.:
```
cd /o/BCCDC/Groups/Analytics/Data Science and Innovation/GitRepositories
```

To make a new directory, use ```mkdir```
```
mkdir /o/BCCDC/Groups/new_group
```


## Conda

<details>

### Create virtual environment with latest R and Git on your desktop station 

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

### Adding other environments in the same VE
<a id="py_packages"></a>

1. Python:
   ```
   conda install python ipython
   ```
   
2. Other Python packages
   ```
   conda install plotly streamlit
   ```
   
### Other Conda commands

[List under construction]

To see what was installed in your VE, issue:
  ```
  conda list
  ```

</details>


## Coding practices

<details>
Ideally, use nouns when naming variables and verbs when naming functions:

```
# Good
example_text <- example_function(
  first_argument = "Some text",
  second_argument = "More text"
)
```

```
# Bad
some.really.long.dot.separated.name <- MyCoolFunction(FirstArgument = 'Some text', second.argument = 'More text')
```
</details>
 
## Python
<details>

- To install Python and Python packages, [see](#py_packages)  
- To Create/ Update Jupyter kernel for use in Jupyter notebook:
```ipython kernel install --user --name=r3.6-py3.11-streamlit```
  where ```r3.6-py3.11-streamlit``` is the name of the kernel that you may select from on the menu

</details>

## R 
<details>

### Working in R Studio

Summary below adapted from [R Working Group Cookbook](file:///O:/BCCDC/Groups/Analytics/Data%20Science%20and%20Innovation/Research_Development_Training/Training%20and%20Education/Educational%20Development/Sharepoint%20Analytic%20Training/presentation_1.html)

Tools -> Global Options -> **Basic Settings**

1. Workspace: 
- Uncheck “Restore .RData into workspace at startup”
- Change “Save workspace to .RData on exit:” to “Never”

2. History:
- Uncheck “Always save history (even when not saving .RData)”

Tools -> Global Options -> **Code**

3. Editing tab: 
- Check “Insert spaces for tab” and set “Tab width” to 2

4. Display tab: 
- Check “Show margin” and set “Margin column” to 80

5. Saving Tab: 
- Check “Ensure that source files end with newline”
- Check “Strip trailing horizontal whitespace when saving”

6. Diagnostics: 
- Check all boxes

### Environment variables
1. ```U:\R``` points to ```R_USER``` 

2. Add below to your ```.Renviron``` file on a new line:
```R_LIBS_USER=${R_USER}/Library/%v```

### Coding practices & Do's and Don'ts 
- Comments should explain what & why you are doing, not how
- remove outdated comments
- Simple code preferred over complex (likewise its implications on comments)
- Generally 3 types of scripts:
   ```load_```
   ```clean_```
   ```func_```

### Template of a typical R script

```
# Project Information -----------------------------------------------------
# Example Project Name...
#                                               
# Purpose: ...
#                                               
# Author: ...
# Created: YYYY/MM/DD...
# Last Modified By: ...

# Package management ------------------------------------------------------
renv::init()

# Load libraries ----------------------------------------------------------

library("dplyr")
library("ggplot2")
library("purrr")

# Set Directories ---------------------------------------------------------

profile_folder <- paste0(getwd(), "/")

script_folder <- paste0(profile_folder, "script/")
function_folder <- paste0(script_folder, "function/")
data_folder <- paste0(profile_folder, "data/")
document_folder <- paste0(profile_folder, "document/")
output_folder <- paste0(profile_folder, "output/")

# Set Global Variables ----------------------------------------------------

# Example p-value threshold for surveillance
p_val <- 0.05

# User Written Functions --------------------------------------------------

source(paste0(function_folder, "fn_custom_func_1.R"))
source(paste0(function_folder, "fn_custom_func_2.R"))
source(paste0(function_folder, "fn_custom_func_3.R"))

# Run Scripts -------------------------------------------------------------

# Load data
source(paste0(script_folder, "load.R"))

# Clean data
source(paste0(script_folder, "clean.R"))

# Perform analysis
source(paste0(script_folder, "do_analysis.R"))
```

</details>

## Git
<details>
 
Acknowledgement: below notes adapted from EHS (\\root\BCCDC\Groups\EHS\Research%20and%20Surveillance\Projects\GitRepositories\Git_Instructions.pdf).

| Terms | Meaning |
| :-- | :-- |
| ```master``` | local copy, typically refers to your copy |
| ```origin``` | remote copy |

### Quick summary

You create a new **master** copy that will be stored **locally** on your computer whenever you clone from a remote repository via a command like this:
```git clone https://github.com/BCCDC-DSI/CANUE-ML.git```

Note that the command above creates a folder called ```CANUE-ML``` while the one below creates a folder called ```my_phido_dashboard```:
```git clone O:\BCCDC\Groups\Analytics\Data Science and Innovation\Research_Development_Training\Research and Development\Projects\p06_PHIDO_dashboard\GitHub" my_phido_dashboard```

Each new session/day, it is good practice to compare your local copy with the remote one:
```git remote show origin```


If the output mentions:
- ***fast-fowardable***, you can push your changes to remote
- ***local out of date***, your local copy is behind the remote copy

To update your local copy, issue:
```git pull origin master```

To update the remote copy, i.e. "publish" your changes for every interested user of the remote repository, **replace ```pull``` from above with ```push```**; i.e. you **push** the local changes **up** to the remote.


### Typical workflow

A cycle of:
1. Work on your local branch.
2. ```Stage``` and ```Commit``` files that you want to archive/ publish
3. ```Push``` changes to the remote repository when ready.


### Staging 

[To be expanded]


### Making changes and commiting to the ```origin```
```
git add --all
git commit -am "<commit message>"
git push
```
Or run in 1 line:

```
git add-commit -m 'My commit message
```

**After** having created command alias called ```add-commit``` with this:
```
git config --global alias.add-commit '!git add -A && git commit'
```


### Starting a bare repository from scratch

In [Git Bash](#gitbash), issue commands like this:
```
cd /o/BCCDC/Groups/Analytics/Data\ Science\ and\ Innovation/

mkdir Collaborations
cd Collaborations

mkdir NLP-Overdose
cd NLP-Overdose

git init --bare
```

**Note: The ```bare``` means that the folder will NOT be a ```working``` directory**.

The output will look like:
```
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint:   git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint:   git branch -m <name>
Initialized empty Git repository in //phsabc.ehcnet.ca/root/BCCDC/Groups/Analytics/Data Science and Innovation/Collaborations/NLP-Overdose/
```

Suppose further that you started a folder in your own folder ```U:\myprojects\NLP```, then issue:
```
git remote add origin "U:\myprojects\NLP"
git push origin master
```


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

### Additional resources
- [Summary list created by Rochelle A. on May 28, 2023](https://rochellea.medium.com/your-git-cheat-sheet-commands-to-remember-1381db3f8efd)

</details>


## Tips & Best Coding Practices

### Use Universal Naming Convention (UNC) instead of dos path

- An example in R:
```
sys.setenv(RENV_PATHS_CACHE = "\\phsabc.ebcnet.ca\BCCDC\Groups\Analytics_Resources\Coding\R\global_renv\cache")
```

- Below will work in Windows' ```File Explorer```
```//phsabc/root/BCCDC/Groups/Analytics_Resources/```

### Folder namng: replace white space with underscore 

e.g. UNC path   
```
/o/BCCDC/Groups/Analytics/Data_Analysts
```

```
/o/BCCDC/Groups/Analytics/GIS_restricted
```
