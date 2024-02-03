# Topics

## How-to's
- [Select the right type of literature review](https://rightreview.knowledgetranslation.net/site/methods)

<details>
<Summary>Publish GitHub pages</Summary>

- Note: this is possible only when repository is public   
- ```Settings``` > ```Pages``` > Click on ```Deploy```

</details>

<hr>
<details>
<summary>Getting started on software</summary>

## Bash <a id='gitbash'></a>
<details>

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
</details>

## Conda
<details>

### Create virtual environment with latest R and Git on your Windows  

Warning: Local R version vs. version on server

1. Program > Anaconda Powershell
2. Create virtual environment (VE) named ```R4.3.1``` 
   ```
   conda create --name R4.3.1 R=4.3.1
   ```
3. Activate this VE:
   ```
   conda activate R4.3.1
   ```
5. Install Git via "anaconda" channel (```-c``` switch; c stands for channel):
   ```
   conda install -c anaconda git
   ```

   
### Other Conda commands

[List under construction]

- To get a list of VEs available on your station, issue:
  ```
  conda info --envs
  ```

- To see what was installed in your VE, issue:
  ```
  conda list
  ```

- [See Conda cheatsheet](https://conda.io/projects/conda/en/latest/_downloads/843d9e0198f2a193a3484886fa28163c/conda-cheatsheet.pdf)
</details>


 
## Python
<details>
 

### Create virtual environment with Python and Git on your Windows 

<a id="py_packages"></a>
1. Program > Anaconda Powershell
2. Create virtual environment (VE) named ```py3.12```
   ```
   conda create --name py3.12 python=3.12
   ```
3. Activate this VE:
   ```
   conda activate py3.12
   ```   
4. Interactive Python:
   ```
   pip install ipython
   ```  
5. Other Python packages
   ```
   pip install plotly streamlit polars
   ```

6. To Create/ Update Jupyter kernel for use in Jupyter notebook:
```ipython kernel install --user --name=r3.6-py3.11-streamlit```
  where ```r3.6-py3.11-streamlit``` is the name of the kernel that you may select from the menu once you launched Jupyter notebook (top-right corner)

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

</details>

### Git

See [notes](git.md)

<hr>

<details>
<Summary>Best practices</Summary>

## Organization

### Naming files and folders

1. Use Universal Naming Convention (UNC) instead of dos path

      - An example in R:
      ```
      sys.setenv(RENV_PATHS_CACHE = "\\phsabc.ebcnet.ca\BCCDC\Groups\Analytics_Resources\Coding\R\global_renv\cache")
      ```
      
      - Below will work in Windows' ```File Explorer```
      ```//phsabc/root/BCCDC/Groups/Analytics_Resources/```

2. Folder namng: replace white space with underscore 
      e.g. UNC path   
      ```
      /o/BCCDC/Groups/Analytics/Data_Analysts
      ```
      When spaces are used in a folder name, the UNC of such folder would require additional escape characters (e.g. back slash), e.g.:  
      ```
      /o/BCCDC/Groups/Analytics/Data\ Science\ and\ Innovation/
      ```

## Processes
- inter-team communication
- intra-team communication
  
## Documentation 

## Coding practices (not specific to programming language)
1. List packages at the top

2. Ideally, use nouns when naming variables and verbs when naming functions:
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

## Dashboard best practices
[Under construnction](training/dashboards.md)
 
</details>

