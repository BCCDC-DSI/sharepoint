# Topics

### How-to's
- [Select the right type of literature review](https://rightreview.knowledgetranslation.net/site/methods)
<details>
<Summary>Publish GitHub pages</Summary>

Note: this is possible only when repository is public   

```Settings``` > ```Pages``` > ```Deploy```

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

### Git
<details>
See [notes](git.md)
</details>
</details>
      
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

## Dash boarding best practices
[Under construnction](training/dashboards.md)
 
</details>

