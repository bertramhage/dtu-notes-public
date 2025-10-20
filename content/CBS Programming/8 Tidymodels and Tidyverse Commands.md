## Setup and Library Loading
**Set Knitr Options**
  ```r
  knitr::opts_chunk$set(echo = TRUE)
  ```

**Load Libraries**
  ```r
  library(tidyverse)
  library(modelr)
  ```

## Data Preparation
**Filtering Data with dplyr**
  ```r
  wages <- heights %>% filter(income > 0)
  ```

## Model Creation
**Building a Linear Model**
  ```r
  lm.fit1 <- lm(log(income) ~ education + height, data = wages)
  ```

## Model Analysis with Tidymodels
**Extracting Model Coefficients and Statistics**
  ```r
  tidy(lm.fit1)
  ```

**Getting Model Diagnostics**
  ```r
  glance(lm.fit1)
  ```

**Selecting Specific Diagnostics**
  ```r
  select(glance(lm.fit1), adj.r.squared, p.value)
  ```

**Model Predictions and Residuals**
  ```r
  augment(lm.fit1)
  ```

## Data Manipulation and Summarization
**Calculating Summary Statistics**
  ```r
  wages %>% summarize(mean_income = mean(income))
  ```

## Plotting with ggplot2
**Creating Basic Plots**
  ```r
  ggplot(data = wages, aes(x = education, y = income)) +
    geom_point() +
    geom_smooth(method = "lm")
  ```

**Customizing Plot Aesthetics**
  ```r
  ggplot(data = wages, aes(x = height, y = income)) +
    geom_point() +
    labs(title = "Income by Height", x = "Height", y = "Income")
  ```