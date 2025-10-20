This cheatsheet provides an overview of essential R commands used for data manipulation, exploration, and statistical testing, useful for data analysis and modeling.

## Libraries

### Loading Libraries
```r
# Load the tidymodels library
library(tidymodels)
```

## Data Handling

### Loading Data
```r
# Load dataset from tidymodels package
data("credit_data")
```

### Viewing Data Structure
```r
# Display first rows of the data
head(credit_data)

# List variable names in the dataset
names(credit_data)
colnames(credit_data)

# Display structure of the data (types and summary)
str(credit_data)
summary(credit_data)
```

### Selecting Columns
```r
# Select specific columns from the data
credit_data <- select(credit_data, Status, Home, Age, Marital, Job, Expenses, Income, Assets, Seniority, Records, Debt)
```

## Statistical Testing

### T-Tests
#### Method 1: Formula Notation
```r
# Conduct t-test on Income based on Status
t.test(Income ~ Status, data = credit_data)

# Conduct t-test on Debt based on Status
t.test(Debt ~ Status, data = credit_data)
```

#### Method 2: Manual Data Subsetting
```r
# Filter data for "good" status and perform t-test
cd_good <- filter(credit_data, Status == "good")
cd_bad <- filter(credit_data, Status == "bad")
t.test(cd_good$Income, cd_bad$Income)
```

## Data Transformation

### Filtering Data
```r
# Filter rows where Age is greater than 30
credit_data_over30 <- filter(credit_data, Age > 30)
```

## Miscellaneous

### Random Sampling
```r
# Sample 100 observations from the data
sampled_data <- sample_n(credit_data, 100)
```

### Grouped Summary
```r
# Summarize data by groups (e.g., average Income by Status)
summary_data <- credit_data %>%
  group_by(Status) %>%
  summarize(avg_income = mean(Income, na.rm = TRUE), avg_debt = mean(Debt, na.rm = TRUE))
```

## Logistic Regression

**Goal:** Model a binary outcome (e.g., credit status) with predictors.

### Steps

1. **Data Setup**
   ```r
   # Load data
   library(tidymodels)
   data("credit_data", package = "modeldata")
   
   # Select relevant columns and remove missing values
   credit_data <- credit_data %>%
     dplyr::select(Status, Home, Age, Marital, Job, Expenses, Income, Assets) %>%
     na.omit()
   ```

2. **Fit Logistic Regression Model**
   ```r
   log.fit <- glm(Status ~ Income + Age + Job, data = credit_data, family = binomial(link = "logit"))
   summary(log.fit)
   ```

3. **Inspect Model with `broom`**
   ```r
   library(broom)
   tidy(log.fit)   # Coefficients and stats
   glance(log.fit) # Diagnostics like AIC
   ```

4. **Predictions**
   ```r
   fitted_data <- augment(log.fit)
   head(fitted_data) # .fitted are predicted probabilities
   ```

   For new data predictions:
   ```r
   # new_data <- data.frame(...) # Some new data
   # predict_data <- augment(log.fit, new_data)
   ```

---

## Clustering (K-means)

**Goal:** Identify hidden patterns or groups in unlabeled data.

### Steps

1. **Prepare the Data**
   ```r
   # Example data frame with two numeric variables
   income_spending <- data.frame(
     Annual_Income = c(...),
     Spending_Score = c(...)
   )
   ```

2. **Run K-means Clustering**
   ```r
   set.seed(3) # For reproducibility
   kclust.fit <- kmeans(income_spending, centers = 3)
   ```

3. **Add Cluster Labels**
   ```r
   income_spending_c <- augment(kclust.fit, income_spending)
   head(income_spending_c)
   ```

4. **Visualize Clusters**
   ```r
   library(ggplot2)
   ggplot(income_spending_c, aes(x = Annual_Income, y = Spending_Score, color = .cluster)) +
     geom_point(size = 3)
   ```

5. **Determine Optimal Number of Clusters**
   ```r
   library(factoextra)
   library(NbClust)

   df <- scale(income_spending)
   fviz_nbclust(df, kmeans, method = "wss")       # Elbow method
   fviz_nbclust(df, kmeans, method = "silhouette") # Silhouette method
   ```

6. **Summarize Clusters**
   ```r
   income_spending_c %>%
     dplyr::group_by(.cluster) %>%
     dplyr::summarize(
       Avg_Income = mean(Annual_Income),
       Avg_Spending = mean(Spending_Score)
     )
   ```

## Logistic Regression (Classification)

```r
library(tidymodels)

# Split data
splits <- initial_split(training_data, strata = TargetVariable)
train_data <- training(splits)
test_data  <- testing(splits)

# Define and fit logistic regression
logistic_model <- logistic_reg() %>%
  set_engine("glm") %>%
  set_mode("classification")

recipe_lr <- recipe(TargetVariable ~ ., data = train_data) %>%
  step_rm(Date) %>% # Potentially remove non-integer or double variables
  step_dummy(all_nominal_predictors()) %>%
  step_normalize(all_predictors())

workflow_lr <- workflow() %>%
  add_model(logistic_model) %>%
  add_recipe(recipe_lr)

lr_fit <- workflow_lr %>% fit(data = train_data)

# Predict on new data
predictions_lr <- predict(lr_fit, new_data)
```

---

## Linear Regression (Regression)

```r
library(tidymodels)

# Split data
splits <- initial_split(training_data)
train_data <- training(splits)
test_data  <- testing(splits)

# Define and fit linear regression
lin_model <- linear_reg() %>%
  set_engine("lm") %>%
  set_mode("regression")

recipe_lin <- recipe(TargetVariable ~ ., data = train_data) %>%
  step_dummy(all_nominal_predictors()) %>%
  step_normalize(all_predictors())

workflow_lin <- workflow() %>%
  add_model(lin_model) %>%
  add_recipe(recipe_lin)

lin_fit <- workflow_lin %>% fit(data = train_data)

# Predict on new data
predictions_lin <- predict(lin_fit, new_data)
```

---

## K-Means Clustering (Unsupervised)

```r
set.seed(123)
km <- kmeans(select(training_data, -IDvariable), centers = 3) 
km$cluster
```

---

## Decision Tree (Classification or Regression)

```r
library(tidymodels)

# For classification or regression, just change set_mode()

tree_model <- decision_tree() %>%
  set_engine("rpart") %>%
  set_mode("classification") # or "regression"

workflow_tree <- workflow() %>%
  add_model(tree_model) %>%
  add_formula(TargetVariable ~ .)

tree_fit <- workflow_tree %>% fit(data = train_data)

predictions_tree <- predict(tree_fit, new_data)
```

---

## Random Forest (Classification or Regression)

```r
library(tidymodels)

rf_model <- rand_forest(mtry = 4, min_n = 10, trees = 500) %>%
  set_engine("ranger") %>%
  set_mode("classification") # or "regression"

workflow_rf <- workflow() %>%
  add_model(rf_model) %>%
  add_formula(TargetVariable ~ .)

rf_fit <- workflow_rf %>% fit(data = train_data)

predictions_rf <- predict(rf_fit, new_data)
```