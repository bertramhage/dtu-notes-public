
This cheatsheet covers essential R commands for working with regular expressions, string manipulation, and package loading. It is organized into sections to provide a quick reference for each task.

## Setup and Package Management

### Installing Packages
To install packages required for string manipulation and visualization:
```r
# Install tidyverse for data manipulation
install.packages("tidyverse")

# Install packages for viewing regex matches
install.packages("htmlwidgets")
install.packages("htmltools")
```

### Loading Libraries
To use functions from the tidyverse and stringr:
```r
library(tidyverse)
library(stringr)
library(htmlwidgets)
library(htmltools)
```

## String Manipulation with `stringr`

### Basic Matching with Regex Patterns
Use `str_detect` and `str_view` to identify patterns in strings.

- **Detect presence of a pattern**:
```r
emails <- c("my_email1234@gmail.com", "invalid_email.com")
str_detect(emails, "\\@")
```

- **View matches in strings**:
```r
str_view(emails, "\\@")
```

### Extracting and Replacing Patterns

- **Extract substrings matching a pattern**:
```r
str_extract(emails, "\\@.*")
```

- **Replace patterns in a string**:
```r
str_replace(emails, "@.*", "@example.com")
```

## Advanced Matching and Grouping

### Using Capture Groups
To extract parts of a string using capture groups, parentheses `()` are used within the regex pattern.

- **Match and capture part of an email domain**:
```r
domains <- str_extract(emails, "@(.*)\\.")
```

### Applying Multiple Patterns
Combine patterns with `|` for "or" conditions or `&` for multiple conditions in regex.

- **Match emails ending in `.com` or `.org`**:
```r
str_detect(emails, "\\.com$|\\.org$")
```

## Pattern Anchoring and Boundaries

### Anchoring Patterns
Use `^` to anchor the pattern to the start and `$` to anchor to the end of the string.

- **Match emails ending in `.com`**:
```r
str_detect(emails, "\\.com$")
```

- **Match emails starting with `my_email`**:
```r
str_detect(emails, "^my_email")
```

### Word Boundaries
Use `\\b` to mark word boundaries in patterns.

- **Match the whole word "email"**:
```r
str_detect(emails, "\\bemail\\b")
```

## Useful Tips and Debugging

### Printing Regex Matches
Use `str_view_all` to highlight all occurrences of a pattern in each string, useful for complex patterns.

```r
str_view_all(emails, "\\@")
```

### Additional Resources
Refer to the [stringr package documentation](https://stringr.tidyverse.org/) for further details on functions and examples.