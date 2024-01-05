# Live contents

## Binary outcomes
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

## Modeling binary outcomes
- ...
- 


## Possible topics

### On setup

[STATS 545](https://stat545.stat.ubc.ca/course/)
