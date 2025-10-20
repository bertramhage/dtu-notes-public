This cheat sheet covers essential R commands for data wrangling, transformation, and analysis, as seen in a sample solution file. 

## Importing and Inspecting Data

### Load Libraries
```r
library(dplyr)
library(tidyr)
library(readr)
library(ggplot2)
library(lubridate)
```

### Import Data
```r
data <- read_csv("file_path.csv")
```

### Data Overview
```r
head(data)      # Show the first few rows
str(data)       # View structure and data types
summary(data)   # Summary statistics for each column
```

## Data Transformation and Cleaning

### Selecting and Renaming Columns
```r
data <- data %>%
  select(column1, column2, column3)        # Select specific columns
  rename(new_name = old_name)              # Rename columns
```

### Filtering Rows
```r
data <- data %>%
  filter(condition)                        # Filter rows based on a condition
```

### Mutate and Calculate New Columns
```r
data <- data %>%
  mutate(new_column = existing_column * 2) # Add or modify a column
```

### Handling Missing Data
```r
data <- data %>%
  drop_na(column_name)                     # Drop rows with NA in a column
  fill(column_name, .direction = "updown") # Fill NA values with the closest value
  replace_na(list(column_name = 0))        # Replace NA with a specified value
```

## Data Aggregation and Summarization

### Group By and Summarize
```r
data_summary <- data %>%
  group_by(group_column) %>%
  summarize(mean_value = mean(target_column, na.rm = TRUE),
            sum_value = sum(target_column, na.rm = TRUE))
```

### Arranging and Sorting
```r
data <- data %>%
  arrange(column_name)                     # Sort by a column in ascending order
  arrange(desc(column_name))               # Sort by a column in descending order
```

## Data Reshaping

### Pivoting Data (Wide to Long)
```r
data_long <- data %>%
  pivot_longer(cols = starts_with("prefix"), 
               names_to = "new_column_name", 
               values_to = "value_column")
```

### Pivoting Data (Long to Wide)
```r
data_wide <- data %>%
  pivot_wider(names_from = key_column, 
              values_from = value_column)
```

## Date and Time Manipulation

### Parsing Dates
```r
data <- data %>%
  mutate(date_column = ymd(date_column))  # Convert to Date type
```

### Extracting Date Components
```r
data <- data %>%
  mutate(year = year(date_column),
         month = month(date_column),
         day = day(date_column))
```

## Visualization

### Basic Plotting with ggplot2
```r
ggplot(data, aes(x = x_column, y = y_column)) +
  geom_point() +
  labs(title = "Plot Title", x = "X-Axis Label", y = "Y-Axis Label")
```

### Histogram
```r
ggplot(data, aes(x = numeric_column)) +
  geom_histogram(bins = 30) +
  labs(title = "Histogram", x = "X-Axis Label", y = "Frequency")
```

### Line Plot
```r
ggplot(data, aes(x = date_column, y = y_column)) +
  geom_line() +
  labs(title = "Line Plot", x = "Date", y = "Y-Axis Label")
```

## Saving Data

### Write CSV
```r
write_csv(data, "output_file.csv")
```

### Save Plot
```r
ggsave("plot_name.png", plot = last_plot(), width = 8, height = 6)
```