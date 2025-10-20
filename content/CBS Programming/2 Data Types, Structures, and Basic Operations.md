
This cheatsheet provides an overview of R commands and functions to handle data types, structures, and basic operations. Organized by key areas, it is designed to be a quick reference for commonly used commands in R.

## Data Types

### Creating Vectors
- **Numeric Vector**: `v1 <- c(1, 2, 3)`
- **Logical Vector**: `v2 <- c(TRUE, FALSE, TRUE)`
- **Integer Vector**: `v3 <- c(10L, 20L, 30L)`
- **Character Vector**: `v4 <- c("hello", "hi", "bye")`
- **Double Vector**: `v5 <- c(1.3, 2.4, 3.5)`

### Checking Data Types
- **Class of Object**: `class(v1)` (e.g., numeric, character)
- **Type of Object**: `typeof(v3)` (e.g., double, integer)

## Working with Vectors

### Sequence and Length
- **Generate Sequence**: `sorted_vector <- seq(from = 1.5, to = 5, by = 0.5)`
- **Length of Vector**: `length(sorted_vector)`

### Accessing and Modifying Elements
- **Access First Element**: `sorted_vector[1]`
- **Replace Element**: `sorted_vector[2] <- 100`
- **Add Element**: `sorted_vector <- append(sorted_vector, 6, after = 0)`

## Vector Arithmetic

- **Addition**: `result <- v1 + v3`
- **Multiplication**: `result <- v1 * v3`

## Conditional Statements

### Basic Conditional
- **If Statement**:
  ```r
  if (temp[1] > 18) {
    print("It's warm!")
  }
  ```

- **If-Else Statement**:
  ```r
  if (temp[1] > 18) {
    print("It's warm!")
  } else {
    print("It's cold!")
  }
  ```

### Vectorized Conditions
- **Logical Comparison on Vectors**: `temp[temp > 18]`

## Looping

### For Loop
- **Basic For Loop**:
  ```r
  for (i in 1:5) {
    print(i)
  }
  ```

### While Loop
- **Basic While Loop**:
  ```r
  i <- 1
  while (i <= 5) {
    print(i)
    i <- i + 1
  }
  ```

## Functions

- **Define Function**:
  ```r
  add <- function(x, y) {
    return(x + y)
  }
  ```

- **Using Function**: `result <- add(3, 5)`

## Miscellaneous

### Sorting and Summarizing
- **Sort Vector**: `sorted_vector <- sort(v1)`
- **Sum of Elements**: `total <- sum(v1)`

### NA Handling
- **Remove NA Values**: `clean_vector <- na.omit(temp)`