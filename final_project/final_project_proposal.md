# Final Project

Review begining of 10/28 class for overview of project proposal guidelines.

Project proposal due 11/18.


**1. What data set(s) are you using? If you are using publicly available data, give URLs; if you are using other data, describe where it is coming from.**

I will be using the Cumulative Cooperative Election Study (CCES) data set, covering years 2006 to 2023. This data set is publicly available and can be accessed through Harvard Dataverse at [https://doi.org/10.7910/DVN/II2DB6](https://doi.org/10.7910/DVN/II2DB6). Additionally, I will join this cumulative data with specific yearly CCES data sets to include variables not present in the cumulative file.


**2. In 1-2 sentences describe what data is in the data set(s).**

The CCES is an annual survey that collects extensive data on U.S. voters, including their demographic information, political attitudes, media consumption habits, and voting behavior. The cumulative data set aggregates common variables across years, providing a comprehensive longitudinal data source for analyzing trends over time.


**3. Do the data set(s) have both categorical and numerical variables?**

Yes, the CCES data sets contain both categorical variables (party affiliation, media source preference, race) and numerical variables (age, income, year of birth).


**4. Have you worked with the data set(s) before in any capacity?**

No, I have not worked directly with the CCES data sets before this project.


**5. How many rows/columns are in the data set(s)?**

The cumulative CCES data set includes approximately 641,955 rows, representing individual survey responses collected from 2006 to 2023. The number of columns varies by year but generally includes hundreds of variables; after joining with yearly data sets, the combined data will have a lot of columns encompassing variables of interest.


**6. Describe in 1-3 sentences how the data set(s) are going to allow you to demonstrate your data cleaning/tidying/transformation skills. How will pivots and/or joins be useful?**

The cumulative data set lacks certain variables specific to media consumption and issue questions that are present only in the yearly data sets. I will demonstrate data cleaning and transformation skills by importing multiple yearly data sets and performing joins to integrate these variables into the cumulative data. This process will involve handling inconsistencies, resolving missing values, and standardizing variable formats across different years. I may use pivots to restructure data for time-series analyses.


**7. What questions will you be using your data set(s) to answer? List at least three questions.**

1. How has media source preference changed over time, especially among specific demographic groups such as political party affiliation and age cohorts?
2. What is the degree of overlap between individuals who consume left-leaning media sources and those who identify as liberal? Similarly, what is the overlap for conservative media consumers and conservative identifiers?
3. What is the correlation between respondents' top issue priorities and their political leanings? Additionally, how does this correlation compare to the relationship between their media source preferences and political leanings?


**8. Does at least one question involve the relationship between multiple variables? Is a numerical variable involved in at least one question, and is a categorical variable involved in at least one question? Does each question allow you to demonstrate different data skills?**

Yes, all questions involve relationships between multiple variables.

[Had to change first question which was asking about change over time because the media source question wasn't asked for earlier years.]
# TODO. These aren't questions, edit questions above.

1. Analyzes respondant age (numerical variable 'age') vs media source preference (categorical).
2. Explores the overlap between media consumption patterns (categorical) and political identification (categorical), requiring cross-tabulation and percentage calculations.
3. Investigates correlations between issue priorities (could be numerical if using rating scales) and political leanings (categorical or numerical if using an ideology scale), as well as media source preferences (categorical)

# NOTE: For Q2, could check topline ideological composition of network news viewers vs overall ideological composition of CCES respondents.


**9. What is your plan for how to work with these data set(s)? Include necessary importing/cleaning/tidying steps (with details specific to your data), as well as how you plan to answer your questions, including what data skills you'll demonstrate in answering each question.**

- Data Importing and Cleaning:
  - Import the cumulative CCES data set and relevant yearly data sets containing media source and issue variables.
  - Use joins to merge yearly data with the cumulative data based on respondent identifiers and survey years.
  - Clean the data by handling missing values, standardizing variable names, and recoding categorical variables for consistency across years.

- Analysis for Question 1:
  - Data Skills: Time-series analysis, data visualization.
  - Aggregate media source preferences by year and demographic groups using grouping and summarizing techniques.
  - Visualize trends over time with line graphs or area charts to illustrate changes in media consumption.

- Analysis for Question 2:
  - Data Skills: Cross-tabulation.
  - Create cross-tabulations of media source preferences and political identification.
  - Calculate overlap percentages and use diagrams to represent the degree of overlap.

- Analysis for Question 3:
  - Data Skills: Correlation analysis, regression modeling.
  - Quantify issue priorities and political leanings to perform correlation analyses.
  - Use statistical models to compare the strength of associations between issue priorities and political leanings versus media source preferences.


**10. When do you plan to complete the various parts of the project? Make a timeline, working backwards from the due date and keeping in mind other commitments and demands on your time you may have.**

- Nov 20-23: Data Import and Exploration
  - Import CCES data sets into R.
  - Explore variables and data structure.
  - Draft Data Source section with URLs.

- Nov 24-27: Data Cleaning and Tidying
  - Handle missing values and standardize names.
  - Merge data sets with joins.
  - Document cleaning steps and impacts.

- Nov 28-Dec 1: Data Exploration and Analysis
  - Q1: Aggregate and visualize media preferences.
  - Q2: Cross-tabulate media and political ID, calculate overlaps.
  - Q3: Correlate issue priorities with political leanings and media sources.

- Dec 2-4: Ethics Reflection and Writing
  - Discuss survey data privacy and biases.
  - Draft Introduction and Conclusion.

- Dec 5-6: Review and Revise
  - Ensure project coherence and completeness.
  - Explain code chunks and address warnings.

- Dec 7-8: Presentation Preparation
  - Create slides on data, questions, findings, and conclusions.
  - Practice presentation.

- Dec 9: Final Touches
  - Proofread project.

- Dec 10: Presentation Day
  - Submit project on Gradescope.