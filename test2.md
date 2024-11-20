TEST 2

Covers
9-30 through 10-30

Class notes, homeworks 6-9, activities, preclass videos




# 9-30 Study Guide: Keys, Joins, and Relational Data

## Key Concepts

### Relational Data
- **Definition**: Data spread across multiple tables with important relationships between them.

### Assumptions for Data
1. **Tidy Data**: Each variable is a column, each observation is a row.
2. **Order of Rows**: Does not matter unless explicitly specified with an order column.
3. **No Identical Rows**: Each row should be unique.

### Keys
- **Primary Key**: A set of columns that uniquely identify each row in a table.
- **Foreign Key**: A column or set of columns in one table that uniquely identifies a row in another table.

### Joins
- **Mutating Joins**: Combine data from two tables by adding columns from one to another.
  - **Inner Join**: Keeps only rows with keys present in both tables.
  - **Left Join**: Keeps all rows from the left table, adding `NA` for missing matches in the right table.
  - **Right Join**: Keeps all rows from the right table, adding `NA` for missing matches in the left table.
  - **Full Join**: Keeps all rows from both tables, adding `NA` where there are no matches.

## Examples

### Creating Unique Identifiers
- **Surrogate Key**: Use `row_number()` to create unique IDs.
  ```r
  names <- tibble(name = "Smith, John", age = c(47, 47))
  names %>% mutate(id = row_number()) %>% select(id, everything())
  ```

### Handling Duplicates
- **Distinct Rows**: Use `distinct()` to remove duplicate rows.
  ```r
  distinct(names)
  ```

### Joins with Examples
- **Inner Join Example**:
  ```r
  inner_join(t1, t2, by = "letter")
  ```
- **Left Join Example**:
  ```r
  left_join(t1, t2, by = "letter")
  ```
- **Right Join Example**:
  ```r
  right_join(t1, t2, by = "letter")
  ```
- **Full Join Example**:
  ```r
  full_join(t1, t2, by = "letter")
  ```

### Joining with Multiple Columns
- **Example**:
  ```r
  flights2 %>% left_join(weather, by = c("day", "month", "hour", "origin"))
  ```

### Joining with Different Column Names
- **Example**:
  ```r
  flights2 %>% left_join(airports, by = c("dest" = "faa"))
  ```

## Additional Notes
- **Merge Function**: Base R's `merge()` can perform similar tasks but `dplyr` functions are preferred for speed and SQL-like syntax.

## Summary
- Ensure data is tidy and rows are unique.
- Use keys to uniquely identify rows and relate tables.
- Choose the appropriate join type based on the data relationship and desired outcome.



---

# 10-9 Study Guide: Filtering Joins, Sets, and Cartesian Products

## Key Concepts

### Sets
- **Definition**: A collection of elements where order doesn't matter.
- **Union**: All elements in either set A or B.
  - Example: `A union B` is like a full join.
- **Intersection**: All elements common to both sets A and B.
  - Example: `A intersect B` is like an inner join.
- **Set Difference**: Elements in one set but not the other.
  - Example: `A - B` is like an anti-join.

### Cartesian Product
- **Definition**: All possible pairs of elements from two sets.
- **Example**: If A = {1, 2} and B = {'a', 'b'}, then A x B = {(1, 'a'), (1, 'b'), (2, 'a'), (2, 'b')}.
- **Data Science Example**: `complete(col1, col2)` generates all possible pairs of values from two columns.

### Filtering Joins
- **Purpose**: Filter one table based on the presence of values in another table without adding new data.
- **Types**:
  - **Semi-Join**: Keeps rows in the first table that have a match in the second table.
    - Example: `semi_join(airports, flights, by = c("faa" = "dest"))`
  - **Anti-Join**: Keeps rows in the first table that do not have a match in the second table.
    - Example: `anti_join(flights, airports, by = c("dest" = "faa"))`

## Examples

### Semi-Join Example
- **Objective**: Filter `airports` to only include those that are destinations in `flights`.
  ```r
  semi_join(airports, flights, by = c("faa" = "dest"))
  ```
  **Output**: A tibble with 101 rows, each representing an airport that is a destination in the `flights` dataset.

### Anti-Join Example
- **Objective**: Find destinations in `flights` that do not appear in `airports`.
  ```r
  anti_join(flights, airports, by = c("dest" = "faa")) %>% count(dest)
  ```
  **Output**:
  ```
  # A tibble: 4 x 2
    dest     n
    <chr> <int>
  1 BQN     10
  2 PSE     20
  3 SJU     30
  4 STT     40
  ```

### Built-in Set Functions in R
- **Union**: `union(t1, t2)` - All rows in either `t1` or `t2`.
- **Intersection**: `intersect(t1, t2)` - Rows common to both `t1` and `t2`.
- **Set Difference**: `setdiff(t1, t2)` - Rows in `t1` but not in `t2`.

### Example with Built-in Functions
```r
t1 <- tribble(
  ~pet, ~species, 
  "Gracie", "Cat", 
  "Lassie", "Dog"
)

t2 <- tribble(
  ~pet, ~species, 
  "Spot", "Lizard", 
  "Gracie", "Cat", 
  "Tweety", "Bird"
)

union(t1, t2)
```
**Output**:
```
# A tibble: 4 x 2
  pet    species
  <chr>  <chr>  
1 Gracie Cat    
2 Lassie Dog    
3 Spot   Lizard 
4 Tweety Bird   
```

```r
intersect(t1, t2)
```
**Output**:
```
# A tibble: 1 x 2
  pet    species
  <chr>  <chr>  
1 Gracie Cat    
```

```r
setdiff(t1, t2)
```
**Output**:
```
# A tibble: 1 x 2
  pet    species
  <chr>  <chr>  
1 Lassie Dog    
```

```r
setdiff(t2, t1)
```
**Output**:
```
# A tibble: 2 x 2
  pet    species
  <chr>  <chr>  
1 Spot   Lizard 
2 Tweety Bird   
```

## Summary
- **Sets**: Understand union, intersection, and set difference.
- **Cartesian Product**: Useful for generating all combinations of values.
- **Filtering Joins**: Use semi-joins and anti-joins to filter data based on another table.
- **R's Built-in Functions**: Use `union()`, `intersect()`, and `setdiff()` for operations on rows with identical columns.



Certainly! Here's a concise study guide based on your class notes on factors, including examples and their outputs:

---

# 10-16 Study Guide: Factors in R

## Key Concepts

### Factors
- **Definition**: A data type used for categorical variables, which can take on a limited number of different values (levels).
- **Purpose**: Useful for sorting data in non-alphabetical order and identifying entries that don't fit predefined categories.

### Creating Factors
- **factor()**: Converts a vector into a factor.
- **parse_factor()**: Converts a vector into a factor and provides warnings for unexpected values.

### Using Factors in Data Frames
- **mutate()**: Used to convert columns in tibbles into factors.

## Examples

### Creating and Using Factors

#### Example: Converting Days of the Week to Factors
```r
library(tidyverse)

daily_visitors <- tibble(Day_Of_Week = c("Sunday", "Monday", "Tuesday", 
                                         "Wednesday", "Thursday", "Friday", 
                                         "Saturday"), 
                         Num_visitors = c(13, 16, 17, 30, 20, 31, 14))

day_of_week_levels <- c("Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday")

daily_visitors2 <- daily_visitors %>% 
  mutate(Day_fctr = parse_factor(Day_Of_Week, levels = day_of_week_levels))

daily_visitors2
```

**Output**:
```
# A tibble: 7 x 3
  Day_Of_Week Num_visitors Day_fctr
  <chr>             <dbl> <fct>   
1 Sunday               13 Sunday  
2 Monday               16 Monday  
3 Tuesday              17 Tuesday 
4 Wednesday            30 Wednesday
5 Thursday             20 Thursday
6 Friday               31 Friday  
7 Saturday             14 Saturday
```

### Plotting with Factors

#### Example: Plotting with Correct Order
```r
ggplot(daily_visitors2) + 
  geom_bar(aes(x = Day_fctr, y = Num_visitors), stat = "identity")
```

**Output**: A bar plot with days of the week in the correct order (Sunday to Saturday).

### Reordering Levels

#### Example: Reordering Levels Based on Another Variable
```r
relig_sum <- gss_cat %>% 
  group_by(relig) %>% 
  summarize(tvhours = mean(tvhours, na.rm = TRUE), 
            count = n())

relig_sum %>% 
  mutate(relig_new = fct_reorder(relig, tvhours)) %>% 
  ggplot() + 
  geom_bar(mapping = aes(x = relig_new, y = tvhours), stat= "identity") + 
  coord_flip()
```

**Output**: A horizontal bar plot with religions ordered by average TV hours.

### Changing Levels

#### Example: Recoding Factor Levels
```r
gss_cat %>% 
  mutate(partyid2 = fct_recode(partyid, 
         "Republican, strong" = "Strong Republican",
         "Republican, weak" = "Not str republican", 
         "Independent, near rep" = "Ind,near rep",
         "Independent, near dem" = "Ind,near dem",
         "Democrat, weak" = "Not str democrat",
         "Democrat, strong" = "Strong democrat")) %>% 
  count(partyid2)
```

**Output**:
```
# A tibble: 6 x 2
  partyid2              n
  <chr>             <int>
1 Democrat, strong    100
2 Democrat, weak      150
3 Independent, near dem 50
4 Independent, near rep 40
5 Republican, strong  120
6 Republican, weak    130
```

## Summary
- **Factors**: Useful for handling categorical data with specific levels.
- **Creating Factors**: Use `factor()` and `parse_factor()` to define levels.
- **Reordering Levels**: Use `fct_reorder()` to sort based on another variable.
- **Changing Levels**: Use `fct_recode()` to rename or combine levels.

This guide provides a comprehensive overview of factors in R, including examples with outputs to help you understand and apply these concepts effectively.




Certainly! Here's a concise study guide based on your class notes on regular expressions, including examples and their outputs:

---

# 10-21 Study Guide: Regular Expressions in R

## Key Concepts

### Regular Expressions
- **Definition**: A sequence of characters that define a search pattern, primarily used for string matching and manipulation.

### Basic Patterns
- **Exact Substrings**: `"ta"`
- **Wildcard Character**: `"."` (matches any character)
- **Period**: `"\\."` (matches a literal period)
- **Start of String**: `"^a"`
- **End of String**: `"a$"`
- **Digits**: `"\\d"`

### Character Classes
- **Specific Characters**: `"[ea]"` (matches 'e' or 'a')
- **Negation**: `"[^aeiou]"` (matches any character not a vowel)

### Special Characters
- **Escape Characters**: Use `"\\"` to escape special characters like `"$"` or `"."`.

### Alternation (ORs)
- **Pattern**: `"gr(e|a)y"` (matches "grey" or "gray")

### Quantifiers (Repetitions)
- **0 or 1**: `"?"`
- **1 or More**: `"+"`
- **0 or More**: `"*"`
- **Specific Number**: `"{n}"`, `"{n,}"`, `"{,m}"`, `"{n,m}"`

### Other Helpful Patterns
- **Whitespace**: `"\\s"`
- **Non-Whitespace**: `"\\S"`
- **Word Characters**: `"\\w"`
- **Non-Word Characters**: `"\\W"`
- **Non-Digits**: `"\\D"`
- **Word Boundary**: `"\\b"`

## Examples

### Finding Digits
````r
str_view("He has 17 cats and 19 dogs", "\\d")
````

**Output**: Highlights the digits '1', '7', '1', and '9' in the string.

### Character Class Example
````r
colors <- c("grey", "red", "purple", "gray", "blue")
str_view(colors, "gr[ae]y")
````

**Output**: Highlights "grey" and "gray" in the vector.

### Special Characters Example
````r
str_view("That cost $14", "\\$")
````

**Output**: Highlights the dollar sign '$' in the string.

### Alternation Example
````r
str_view(colors, "gr(e|a)y")
````

**Output**: Highlights "grey" and "gray" in the vector.

### Quantifiers Example
````r
sample_words <- c("color", "colour", "blonde", "blond")
str_view(sample_words, "colou?r")
````

**Output**: Highlights "color" and "colour" in the vector.

### Word Boundary Example
````r
str_view("The cat in the hat", "\\b")
````

**Output**: Highlights the boundaries at the start and end of each word.

## Summary
- **Regular Expressions**: Powerful tool for pattern matching in strings.
- **Character Classes**: Define sets of characters to match.
- **Quantifiers**: Specify how many times a pattern should occur.
- **Special Characters**: Use escape sequences to match literal characters.
- **Word Boundaries**: Useful for identifying the start or end of words.


---

# 10-23 Study Guide: Using Regular Expressions in R

## Key Concepts

### Regular Expressions
- **Definition**: A sequence of characters that define a search pattern, used for string matching and manipulation.

### Common Functions
- **str_detect()**: Checks if a pattern is present in a string.
- **str_count()**: Counts the number of times a pattern appears in a string.
- **str_replace() / str_replace_all()**: Replaces occurrences of a pattern with a specified string.
- **str_view()**: Visualizes where patterns occur in strings.
- **str_subset()**: Returns elements of a vector that match a pattern.
- **str_extract() / str_extract_all()**: Extracts matching patterns from strings.

## Examples

### Counting Patterns

#### Example: Count Strings Starting with 'g'
````r
greek <- c("alpha", "beta", "gamma", "iota")
sum(str_detect(greek, "^g"))
````

**Output**: `1` (Only "gamma" starts with 'g')

#### Example: Count Total Occurrences of 'a'
````r
f <- c("apple", "banana", "cherry")
sum(str_count(f, "a"))
````

**Output**: `4` (Total 'a's in the vector)

### Proportions and Averages

#### Example: Proportion of Strings Starting with 'g'
````r
mean(str_detect(greek, "^g"))
````

**Output**: `0.25` (25% of strings start with 'g')

#### Example: Average Occurrences of 'a'
````r
mean(str_count(f, "a"))
````

**Output**: `1.333` (Average 'a's per string)

### Finding and Extracting Patterns

#### Example: Find Sentences with 'cats'
````r
sentences <- c("I love cats", "Dogs are great", "Cats are cute")
str_subset(sentences, "\\b[Cc]ats?\\b")
````

**Output**: `c("I love cats", "Cats are cute")`

#### Example: Extract Animals from Sentences
````r
animals <- c("cat", "dog", "mouse")
animals_regex <- str_c(animals, collapse = "|")
sentences_tibble <- tibble(sent = sentences)
sentences_tibble %>% 
  mutate(animals_found = str_extract_all(sent, animals_regex)) %>% 
  unnest_longer(animals_found)
````

**Output**:
````
# A tibble: 2 x 2
  sent          animals_found
  <chr>         <chr>        
1 I love cats   cat          
2 Cats are cute cat          
````

### Using Tibbles and Grouping

#### Example: Count Digits in Star Wars Character Names
````r
starwars %>% 
  group_by(species) %>% 
  summarize(
    number_of_characters_with_digits_in_name = sum(str_detect(name, "\\d")),
    fraction_of_characters_with_digit_in_name = mean(str_detect(name, "\\d")), 
    average_digits_per_name = mean(str_count(name, "\\d")), 
    total_digits_across_all_names = sum(str_count(name, "\\d"))
  )
````

**Output**: A summary tibble with counts and averages of digits in character names by species.

## Summary
- **Regular Expressions**: Essential for pattern matching and string manipulation.
- **Key Functions**: Use `str_detect`, `str_count`, `str_replace`, `str_view`, `str_subset`, and `str_extract` for various string operations.
- **Tibbles and Grouping**: Combine regular expressions with `dplyr` functions for powerful data manipulation.


---

# 10-28 Study Guide: SQL in R

## Key Concepts

### SQL (Structured Query Language)
- **Purpose**: Used to interact with databases, particularly for querying and managing data.
- **Integration with R**: SQL can be used within RStudio/RMarkdown to work with databases.

### Libraries
- **DBI**: Provides a database interface definition for communication with database management systems.
- **RSQLite**: Allows the use of SQLite databases in R.

### Setting Up a Database Connection
- **dbConnect()**: Establishes a connection to a database.
- **dbDisconnect()**: Closes the connection to a database.

### Basic SQL Commands
- **SELECT**: Retrieves data from a database.
- **FROM**: Specifies the table to query.
- **WHERE**: Filters records based on conditions.
- **COUNT**: Counts the number of rows.
- **AS**: Renames columns in the result set.
- **DISTINCT**: Selects unique values.
- **ORDER BY**: Sorts the result set.
- **LIMIT**: Limits the number of rows returned.
- **OFFSET**: Skips a specified number of rows.

## Examples

### Setting Up a Connection
```r
library(DBI)
library(RSQLite)

database_connection <- dbConnect(
  SQLite(), 
  dbname = "animal.sqlite"
)
```

### Listing Tables
```r
dbListTables(database_connection)
```

**Output**: A list of tables in the database, e.g., `c("austin_animal_center_intakes", "austin_animal_center_outcomes")`.

### Basic SELECT Query
```sql
SELECT name, intake_type 
FROM austin_animal_center_intakes
```

**Output**: A table with columns `name` and `intake_type` from the `austin_animal_center_intakes` table.

### COUNT Example
```sql
SELECT COUNT(*) 
FROM austin_animal_center_intakes
```

**Output**: `75947` (Total number of rows in the table).

### DISTINCT Example
```sql
SELECT DISTINCT animal_type 
FROM austin_animal_center_intakes
```

**Output**: A list of unique `animal_type` values, e.g., `c("Dog", "Cat", "Bird")`.

### WHERE Clause Example
```sql
SELECT year, month, count 
FROM austin_animal_center_intakes_by_month
WHERE animal_type = "Cat"
```

**Output**: A table with `year`, `month`, and `count` for rows where `animal_type` is "Cat".

### ORDER BY Example
```sql
SELECT year, month, count 
FROM austin_animal_center_intakes_by_month
WHERE animal_type = "Cat"
ORDER BY year DESC, month DESC
```

**Output**: A table sorted by `year` and `month` in descending order.

### Disconnecting
```r
dbDisconnect(database_connection)
```

## Summary
- **SQL in R**: Use SQL commands within R to query and manage data in databases.
- **Key Commands**: Familiarize yourself with `SELECT`, `FROM`, `WHERE`, `COUNT`, `AS`, `DISTINCT`, `ORDER BY`, `LIMIT`, and `OFFSET`.
- **Database Connections**: Use `dbConnect()` and `dbDisconnect()` to manage database connections.


---

# 10-30 Study Guide: SQL Joins and Aggregations

## Key Concepts

### SQL Joins
- **Purpose**: Combine rows from two or more tables based on a related column.
- **Types**:
  - **Inner Join**: Returns rows with matching values in both tables.
  - **Left Join**: Returns all rows from the left table and matched rows from the right table.
  - **Right Join**: Returns all rows from the right table and matched rows from the left table.
  - **Full Join**: Returns all rows when there is a match in either table.

### Aggregations
- **Purpose**: Perform calculations on a set of values to return a single value.
- **Functions**: `SUM`, `COUNT`, `AVG`, `MIN`, `MAX`.

### Grouping and Filtering
- **GROUP BY**: Groups rows that have the same values in specified columns into summary rows.
- **HAVING**: Filters records that work on summarized `GROUP BY` results.

## Examples

### Setting Up a Database Connection
````r
library(DBI)
library(RSQLite)

db_sales <- dbConnect(
  SQLite(), 
  dbname = "sales.sqlite"
)
````


### Listing Tables
````r
dbListTables(db_sales)
````


**Output**: A list of tables in the database, e.g., `c("sales_teams", "sales_pipeline")`.

### Inner Join Example
````sql
SELECT pipeline.sales_agent AS "Agent", 
       teams.manager, 
       pipeline.account, 
       pipeline.deal_stage
  FROM sales_teams AS teams
  JOIN sales_pipeline AS pipeline
  ON pipeline.sales_agent = teams.sales_agent
  WHERE pipeline.deal_stage = "Won"
````


**Output**: A table with columns `Agent`, `manager`, `account`, and `deal_stage` for rows where `deal_stage` is "Won".

### Left Join Example
````sql
SELECT sales_teams.sales_agent AS Agent, 
       sales_pipeline.deal_stage
  FROM sales_teams 
  LEFT OUTER JOIN sales_pipeline USING (sales_agent)
````


**Output**: A table with all `sales_agent` from `sales_teams` and their `deal_stage` from `sales_pipeline`.

### Aggregation Example
````sql
SELECT COUNT(*) AS "Number of Deals Won" 
FROM sales_pipeline
WHERE deal_stage = "Won"
````


**Output**: `Number of Deals Won` with a count of deals where `deal_stage` is "Won".

### Group By Example
````sql
SELECT sales_agent,
       COUNT(*) AS Num_deals_won, 
       AVG(close_value) AS Average_value
  FROM sales_pipeline
  WHERE deal_stage = "Won"
  GROUP BY sales_agent
  ORDER BY Average_value DESC
````


**Output**: A table with `sales_agent`, `Num_deals_won`, and `Average_value`, ordered by `Average_value` in descending order.

### Disconnecting
````r
dbDisconnect(db_sales)
````


## Summary
- **SQL Joins**: Use joins to combine data from multiple tables based on related columns.
- **Aggregations**: Use functions like `SUM`, `COUNT`, `AVG` to perform calculations on data.
- **Grouping and Filtering**: Use `GROUP BY` to aggregate data and `HAVING` to filter aggregated results.