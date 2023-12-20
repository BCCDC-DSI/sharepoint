# Sharepoint

## Conventions
Template for "statistical snacks"

|  |  |
| :-- | :-- |
| Readers will learn to... | |
| Language(s) involved | R, STATA |

# R/ Python conventions
- packages at the top
  
# Notation

| Notation | Definition |
|:-- | :-- |
| $n$ | Number of samples |
| $K$ | Number of independent (observable) variables |
| $i=1 ... n$ | $i$-th sample  |
| $j=1 ... K$ | $j$-th variable |
| $X_{ij} = 1$ | $j$-th independent variable of sample $i$ |
| $Y$ | Dependent variable |
| $Z$ | |

# Binary outcomes
  - Risk ratio
  - Odds ratio
  - ...
  
  ```
  poisson outcome exposure confounder [fweight = freq], irr r
  ```
  
  ```
  library("sandwich")
  library("lmtest")
  model <- glm(outcome~exposure+confounder, family=poissson(link=log), data=dataset)
  coeftest(model, vcov = sandwich)
  ```

# Modeling binary outcomes
- ...
