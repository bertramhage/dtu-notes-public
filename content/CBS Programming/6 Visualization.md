This cheatsheet covers commands related to data visualization and manipulation in R, specifically for creating basic and polished plots. It includes functions from various packages and examples of reading data, setting up plots, and customizing aesthetics.

## Setup and Libraries

### Loading Required Libraries
```r
# Load core libraries
library(tidyverse)  # Data manipulation and visualization
library(readxl)     # Read Excel files
library(cowplot)    # Advanced plot customization
```

### Setting Knitr Options
```r
# Configure knitr options to control code chunk display
knitr::opts_chunk$set(echo = TRUE)
```

## Data Import

### Reading Different Data Formats
```r
# Read data from various file formats
BOFF <- read_delim("BOFF.txt", delim="\t")        # Read tab-delimited text file
Geo_dim <- read_excel("Geo_dim.xlsx")             # Read Excel file
who_disease <- read.csv("who_disease.csv")        # Read CSV file
```

## Basic Plotting

### Histogram
Histograms help visualize the distribution of a single variable.
```r
# Simple histogram
hist(BOFF$ppk)

# Advanced histogram using ggplot
ggplot(BOFF, aes(x=ppk)) +
  geom_histogram(bins=60)  # Customize number of bins
```

### Density Plot
Density plots offer a smooth curve representing variable distribution.
```r
# Basic density plot with facets
ggplot(BOFF, aes(ppk, col=foodLabel)) +
  geom_density() +
  facet_wrap(vars(fruit))

# Polished density plot with color and labels
ggplot(BOFF, aes(ppk, col=foodLabel)) +
  geom_density() +
  scale_color_brewer(palette='Set1', name='Food Label') +
  labs(title="Price of Fruits", x="$ per kilo", y="Frequency", caption="Price of organic and conventional apples and oranges")
```

## Additional Customizations

### Facet Wrapping
Faceting splits data visualization based on categorical variables.
```r
# Facet wrap example
ggplot(BOFF, aes(ppk, col=foodLabel)) +
  geom_density() +
  facet_wrap(vars(fruit))
```

### Aesthetic Adjustments
Customize plots using `labs` for labels and `scale_color_brewer` for color palettes.
```r
# Adding titles, axis labels, and captions
ggplot(BOFF, aes(ppk, col=foodLabel)) +
  geom_density() +
  labs(title="Price of Fruits", x="Price per kilo", y="Density") +
  scale_color_brewer(palette="Set1")
```