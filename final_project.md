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

1. Analyzes changes over time (numerical variable 'year') in media source preference (categorical) across different age groups (numerical) and party affiliations (categorical).
2. Explores the overlap between media consumption patterns (categorical) and political identification (categorical), requiring cross-tabulation and percentage calculations.
3. Investigates correlations between issue priorities (could be numerical if using rating scales) and political leanings (categorical or numerical if using an ideology scale), as well as media source preferences (categorical).


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

- November 20 - November 23: Data Import and Initial Exploration
  - Import the cumulative CCES data set and the relevant yearly data sets into R.
  - Begin initial data exploration to understand the variables, data structure, and any discrepancies between data sets.
  - Start drafting the Data Source section by researching how the data was collected and documenting any relevant URLs and citations.

- November 24 - November 27: Data Cleaning and Tidying
  - Perform data cleaning steps, including:
    - Handling missing values and discussing NA values.
    - Standardizing variable names and formats across different years.
  - Use joins to merge the cumulative data set with yearly data sets.
  - Document each step in the Data Cleaning and Tidying section, providing explanations for code chunks.
  - Reflect on whether any data removal could impact conclusions, in the Data Cleaning and Tidying section.

- November 28 - December 1: Data Exploration and Analysis
  - Question 1:
    - Use data transformation techniques to aggregate media source preferences by year and demographic groups.
    - Create visualizations to illustrate changes over time.
    - Perform any necessary modeling to support findings.
    - Document findings with code explanations in the Data Exploration section.
  - Question 2:
    - Conduct cross-tabulations between media consumption and political identification.
    - Calculate overlap percentages and consider visualizations like diagrams.
    - Explain the analysis process and interpret results.
  - Question 3:
    - Perform correlation analysis between issue priorities, political leanings, and media sources.
    - Build regression models to compare the strength of relationships.
    - Discuss statistical significance and potential limitations.
    - Provide explanations of any techniques used.

- December 2 - December 4: Ethics Reflection and Writing
  - Write the Ethics Reflection section, discussing:
    - Ethical considerations related to survey data and privacy.
    - Potential biases in self-reported data.
    - Ethical implications if the data were used differently.
  - Begin drafting the Introduction and Conclusion sections.
    - Introduction: Present the topic, research questions, and a summary of findings.
    - Conclusion: Summarize insights, discuss limitations, and suggest next steps.

- December 5 - December 6: Review and Revise
  - Review the entire project for coherence, completeness.
  - Check that every code chunk and figure includes an explanation.
  - Ensure all warnings are explained and any NA values are discussed.
  - Verify that any advanced functions or techniques are explained.
  - Cross-reference the project checklist to confirm all requirements are met.

- December 7 - December 8: Presentation Preparation
  - Create slides for the five-minute presentation, focusing on:
    - Data Used: Source, collection method, and any pertinent details.
    - Research Questions: Clearly state the questions explored.
    - Findings: Highlight key results with visual aids.
    - Conclusion: Summarize insights and their implications.
  - Practice the presentation to ensure it fits within the time limit and is engaging.

- December 9: Final Touches
  - Perform a proofreading of the written project.

- December 10: Presentation Day
  - Submit the final project on Gradescope.