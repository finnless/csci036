# CSCI 36, Fall 2024: Final Project 

Instructor: Dr. Sarah Cannon

## 1 Overview

Final Project Description: Students will work with a publicly-available data set of their choosing and demonstrate what they've learned during the semester by obtaining, cleaning, transforming, modeling, visualizing, and communicating their data. Students will also give a five minute presentation to their classmates about their data set and findings.

## 2 Requirements

## Data Set Requirements:

- In order to effectively demonstrate what you've learned, you cannot work with a single clean and tidy data set for your project. You must either use multiple data sets and combine them, or use a data set that is not clean/tidy. Either way, there must be significant data cleaning/transforming involved. In particular, you must use at least one join or one pivot.
- The data set you choose cannot be a data set you have worked with before in any capacity. This is to make sure all students are on even footing going into the final project.
- Your data set should contain at least 10,000 rows of data, though more is preferable.
- Your data set should be publicly available; exceptions can be discussed with Prof. Cannon.
- You data set(s) should involve both numerical and categorical variables, so that you can demonstrate your proficiency with both types of data.

If you want to work with a data set that doesn't meet all these requirements, talk to Prof. Cannon about what extra things you might add to your project to make up for this.

Question Guidelines: You should ask at least three questions about your data set(s). At least one should involve the relationship between multiple variables. There should be a categorical variable involved in at least one question and there should be a numerical variable involved in at least one question. Your project must include some modeling. Your answer to each question should demonstrate a different data skill. We will have an in-class discussion about what makes a good question.

## 3 Project Proposal, Due November 19th

## 4 Written Project (90 points)

Your final project should be written in RMarkdown, and knitted as either a PDF or a .html file. It will be submitted on Gradescope as a PDF.

Intended Audience and Explanations: Your final project should be written using complete sentences and clear explanations. As a guideline, the level of professionalism should be equivalent to that of a report you might submit to your boss at a future job.

The level of explanation should be sufficient that one of your classmates could read your project and understand what you're doing. For example, you don't need to explain what a join is, but you should explain what particular join you are using and why you chose that join. Additionally, you should be sure to define/explain any terms you use that are specific to your topic; you should assume whoever is reading your project is completely unfamiliar with your topic.

Throughout the project, every code chunk and figure should be accompanied by an explanation. For the code chunk, explain what the code is doing and why you are doing this. For figures, explain what they are showing and what they tell you about your data set(s). Any warnings that appear must be explained. If you remove any rows from your data set, you should carefully consider/explain whether what you're removing could have an impact on your final conclusions. For any NA values that appear in your data, you must discuss them. If you use any skills, concepts, or functions beyond what we have learned in class this semester, you must explain how they work and why you chose to use them.

Outline: You should include the following sections, in this order:

1. Introduction: What is your topic, what questions were you asking, and what answers did you find? This should be 1-2 paragraphs.
2. Data Source: Where does the data you are using come from? How did the person who created the data set gather the information? Do you think the documentation for this data is sufficient, and if not, what else should have been included? Including the URLs for the data sets you used (if you are using publicly available data) should be part of this, but you should provide even more information. This should be 1-2 paragraphs.
3. Ethics Reflection: Are there any ethical issues to consider related to your data? Are there any ethical issues that might arise from your analysis? Are there any ethical issues that might result if someone else used this data in a different way? The length of this will vary widely depending on your data, but should be at least one paragraph.
4. Data Import: Import your data set(s)
5. Data Cleaning and Tidying: clean and tidy your data set(s) so that they are ready to be analyzed.
6. Data Exploration: This section should include data transformation, data visualization, and data modeling. First, you should look individually at any variables you're going to be examining to understand their spread, the values they can take on, etc. Then, the main goal of this section is to answer at least three interesting questions about your data. You can organize it in whatever way makes the most sense for your particular data and questions, and you should feel free to switch back and forth between the three different steps of transformation, visualization, and modeling. You may find it helpful to break this section up into subsections.
7. Conclusion: Summarize what you found, reflect on what limitations there are on your analysis/how broadly applicable your findings are, and discuss what some next steps might be. This should be at least two paragraphs.
For example, maybe you found a relationship between two particular variables, but because your data is only from the United States, you don't know if this relationship will hold in other countries. A next step might be to find out if similar trends exist in other places.
Or, perhaps you have an interesting finding, but your data is from self-reporting via surveys, and there might be some bias in who responds to these surveys. This could affect how much confidence you have in your conclusions.

## 6 Project Checklist

This checklist is not intended to be a substitute for reading the all of the project details above, but is meant to be a helpful reference as you're working on your final project.
$\square$ Am I working with a data set I have never worked with before?
$\square$ Does my data have at least 10,000 rows? If not, have I discussed with Prof. Cannon what I can add to my project to make up for this?
$\square$ Does my project include at least one pivot or join, as part of either the data tidying or data transformation?
$\square$ Have I answered at least three questions about my data?
$\square$ Does at least one of my questions (though ideally more than one) look at the relationship between multiple variables?Does at least one of my questions involve a categorical variable?Does at least one of my questions involve a numerical variable?Do each of my questions demonstrate a different data skill?
$\square$ Have I addressed all parts of the data science pipeline: Collecting, Importing, Tidying, Transforming, Visualizing, Modeling, and Communicating data?Does your project include definitions/explanations of any concepts or terms related to your topic that a classmate or Prof. Cannon may not know?
$\square$ Does every code chunk and figure include an accompanying explanation?
$\square$ Are any warnings explained?
$\square$ Are any NA values, and the potential effect they might have on any conclusions, discussed?
$\square$ If I removed any rows from my data set, did I carefully consider/explain whether what was removed could have an impact on the final conclusions?
$\square$ If I used any skills, concepts, or functions beyond what we have learned in this class, did I explain how they work and why I chose them?
$\square$ Is my project written and presented professionally, at the level of a report I might submit to a future boss?Have I included all the sections listed in the Outline section above?
$\square$ Have I written the code myself, using tools and techniques learned this semester? (See academic dishonesty policy below)

## 7 Rubric

Introduction (5 points): Does the student demonstrate a high-level understanding of the data they are working with, the questions they are asking, and the conclusions they have reached? Have they provided enough explanation so that someone who is not an expert in their particular topic can understand what their project is about and what conclusions they've made?

Data Source (5 points): Does the student demonstrate an understanding of how their data was gathered, beyond just providing the URL at which it can be found?

Data Ethics ( 5 points): Has the student provided a thoughtful consideration of the various ethical issues surrounding their data, and what ethical benefits or harms might or might not apply to their situation? An answer of "There are no ethical harms or benefits related to my data" will not receive credit.

Data Import, Cleaning and Tidying, and Exploration (48 points): By default, these section will be assigned the following point values:

- Data Import (2 points): Can the student successfully import their data set(s) into RStudio?
- Data Cleaning/Tidying (10 points): Does the student understand what it means for data to be clean and tidy, and do they demonstrate that they are able to achieve this? Does the student use at least one join or pivot?
- Data Transformation/Visualization/Modeling (36 points): Does the student state and then answer three questions related to their data? Are the question they've chosen good questions (as discussed in class on 3/19)? Does at least one of these questions look at the relationship between multiple variables? Are their chosen questions ones that can be answered by looking at their data set? Are the methods they chose to use appropriate for the questions they are trying to answer? Do they look at each variable individually before looking at the relationship between multiple variables? Are the answers/conclusions they reached supported by the data? Do they demonstrate a different data skill in answering each question? Do they demonstrate proficiency in all three of data transformation, data visualization, and modeling?

Overall, does the student demonstrate that they've learned how to work with data this semester?

However, these point values within this section may be adjusted for each individual student. For example, for a student with very clean/tidy data, we might discuss doing extra visualization/modeling to make up for this, and this would be reflected in the point values for these parts. As another example, if a student's data import involves more than just simple read_csv() commands, that part will receive more weight.

Conclusion ( 7 points): Does the student demonstrate a high-level understanding of the conclusions they have reached? Does the student understand the limitations on their analysis and how broadly applicable their findings are? Does the student give some appropriate next steps for potential future work with this data?

Report Mechanics (20 points): Is the report professionally written, at the level of a report you might submit to your boss at a future job? Is the level of explanation sufficient so that a classmate could read and understand the project? Are all terms or concepts that are specific to your topic defined/explained? Is every code chunk and figure accompanied by a clear, detailed explanation? Does the data have at least 10,000 rows, or if not, has the student discussed this with Prof. Cannon and added appropriate extra steps to the project?