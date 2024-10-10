# Comprehensive R Cheatsheet

## Important Concepts

### R Basics
- **Assignment Operator**: `<-` is used to assign values to variables.
- **Vectors**: Created using `c()`, e.g., `c(1, 2, 3)`.
- **Data Types**: Numeric, character, logical, etc.

### Variables and Arithmetic

```r
# Assigning values to variables
x <- 3
y <- 2

# Basic arithmetic operations
sum <- x + y  # Addition
difference <- x - y  # Subtraction
product <- x * y  # Multiplication
quotient <- x / y  # Division
```

### Logical Operations

```r
# Logical operations
a <- TRUE
b <- FALSE

# Logical AND
a & b  # FALSE

# Logical OR
a | b  # TRUE

# Logical NOT
!a  # FALSE
```

### Data Structures

#### Vectors

```r
# Creating a vector
numbers <- c(1, 2, 3, 4, 5)

# Accessing elements
first_number <- numbers[1]
```

#### Data Frames

```r
# Creating a data frame
df <- data.frame(
  Name = c("Alice", "Bob", "Charlie"),
  Age = c(25, 30, 35)
)

# Accessing data frame columns
df$Name
```

### Functions

```r
# Define a function
add <- function(a, b) {
  return(a + b)
}

# Call the function
result <- add(5, 3)
```

## Data Ethics
- **Key Principles**: Fairness, accountability, transparency.
- **Ethical Challenges**: Privacy, data misuse, bias.

## Data Visualization with ggplot2

`ggplot2` is a powerful R package for creating complex and customizable plots.

### Basic Plot Structure

```r
library(ggplot2)

# Basic scatter plot
ggplot(data = mpg, aes(x = displ, y = hwy)) +
  geom_point()
```

### Single-variable Plots

#### Boxplot

```r
ggplot(data = mpg) + 
  geom_boxplot(aes(x = cty))
```

#### Histogram

```r
ggplot(data = mpg) + 
  geom_histogram(aes(x = cty), color = "black", fill = "white", binwidth = 5)
```

### Two-variable Plots

#### Scatterplot

```r
ggplot(data = mpg) + 
  geom_point(aes(x = displ, y = hwy))
```

#### Line Graph

```r
ggplot(data = economics) + 
  geom_line(aes(x = date, y = psavert))
```

### Adding More Variables

#### Color

```r
ggplot(data = mpg) + 
  geom_point(aes(x = displ, y = hwy, color = drv))
```

#### Facets

```r
ggplot(data = mpg) + 
  geom_point(aes(x = displ, y = hwy)) + 
  facet_wrap(~ class)
```

### Themes and Customization

```r
# Black and white theme
ggplot(data = mpg) + 
  geom_point(aes(cty, hwy)) + 
  theme_bw()
```

## Data Transformation with dplyr

`dplyr` is a grammar of data manipulation, providing a consistent set of verbs to help you solve the most common data manipulation challenges.

### Filter Rows

```r
library(dplyr)

# Filter rows where dep_delay > 60
lateflights <- filter(flights, dep_delay > 60)
```

### Select Columns

```r
# Select specific columns
selected_flights <- select(flights, year, month, day, dep_delay)
```

### Arrange Rows

```r
# Arrange rows by a column
arranged_data <- arrange(mtcars, desc(mpg))
```

### Mutate Columns

```r
# Create new columns
flights <- mutate(flights, gain = dep_delay - arr_delay)
```

### Summarize Data

```r
# Summarize data
summarize(flights, avg_dep_delay = mean(dep_delay, na.rm = TRUE))
```

### Group By

```r
# Group by and summarize
flights %>% 
  group_by(origin) %>% 
  summarize(avg_dep_delay = mean(dep_delay, na.rm = TRUE))
```

## Data Import

Importing data is a crucial step in data analysis. R provides several functions to import data from various sources.

### Importing CSV Files

```r
library(readr)

# Import CSV from a URL
data <- read_csv("https://example.com/data.csv")

# Import CSV from a local file
data <- read_csv("data.csv")
```

### Read Excel

```r
library(readxl)

# Read an Excel file
data <- read_excel("data.xlsx")
```

## Parsing

Parsing is the process of converting data from one format to another.

### Parsing Numbers

```r
# Parse numbers
parse_number("123,456.78")
```

### Parsing Dates

```r
# Parse dates
parse_date("2024-09-25", "%Y-%m-%d")
```

## Strings

String manipulation is a common task in data analysis.

### Basic String Functions

```r
library(stringr)

# String length
str_length("Hello")

# Concatenate strings
str_c("Hello", "World", sep = " ")

# Change case
str_to_upper("hello")
str_to_lower("HELLO")
```

### Substring

```r
# Extract a substring
substr <- str_sub("Hello, World!", 1, 5)
```

### Replace Substring

```r
# Replace substring
str_replace("hello world", "world", "R")  # Outputs: "hello R"
```

## Tidy Data and Pivoting

Tidy data is a standard way of mapping the meaning of a dataset to its structure.

### Pivoting Data

#### Pivot Wider

```r
# Pivot wider
table2 %>% 
  pivot_wider(names_from = type, values_from = count)
```

#### Pivot Longer

```r
# Pivot longer
table4a %>% 
  pivot_longer(c(`1999`, `2000`), names_to = "year", values_to = "cases")
```

### Separate

```r
# Separate a column into multiple columns
flights %>% 
  separate(col = time_hour, into = c("date", "time"), sep = " ")
```

### Unite

```r
# Unite multiple columns into one
united_data <- unite(data, col = "date", c("year", "month", "day"), sep = "-")
```

### Complete

```r
# Complete missing combinations
complete_data <- complete(data, nesting(var1, var2))
```

### Fill

```r
# Fill missing values
filled_data <- fill(data, var1)
```

## Example Functions

### Sum Function
```r
sum_values <- function(a, b) {
  # This function takes two arguments, a and b, and returns their sum.
  return(a + b)
}
```

### Difference Function
```r
difference <- function(a = 0, b = 1, neg = FALSE) {
  # This function calculates the difference between two numbers, a and b.
  # If neg is TRUE, it returns the negative of the difference.
  s <- a - b
  if (neg) return(-s)
  return(s)
}
```

## Example Questions

1. **True/False**: The `geom_point` function is used to make a scatterplot.  
   **Answer**: True

2. **Short Answer**: What does `sum(c(5,7,NA))` return?  
   **Answer**: NA

3. **Open-ended**: Given a tibble `t`, how would you pick out only those rows where the `stopping_time` is at least 5?  
   **Answer**: `filter(t, stopping_time >= 5)`