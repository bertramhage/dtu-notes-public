This cheatsheet covers essential commands and functions for string handling, looping, and functions in R.

## String Manipulation

### Finding Patterns in Strings
- `grep("pattern", vector)`: Finds indices of elements containing "pattern".
- `grep("pattern", vector, value = TRUE)`: Returns elements containing "pattern" instead of indices.
- `grepl("pattern", vector)`: Returns a logical vector indicating presence of "pattern".

### Replacing Patterns in Strings
- `str_replace(vector, "pattern", "replacement")`: Replaces the first occurrence of "pattern" with "replacement" in each string.
- `str_replace_all(vector, "pattern", "replacement")`: Replaces all occurrences of "pattern" with "replacement".

### Concatenating Strings
- `str_c(string1, string2, sep = "/")`: Concatenates `string1` and `string2` with `/` as separator.

## Looping

### Basic For Loop
- `for (element in vector) { print(element) }`: Iterates over `vector` and prints each `element`.

## Functions

### Defining a Simple Function
```r
  my_function <- function(arg1, arg2) {
    # function body
    return(result)
  }
```

This syntax defines a custom function with two arguments, `arg1` and `arg2`, and returns a result.