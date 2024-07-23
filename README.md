# UofT SCS Data Analytics Bootcamp's - Data Analytics Boot Camp - Assignment 4 (Pandas) 

# pandas-challenge
This is a challenge submission for UWA Data Analytics Bootcamp, Module 4 Pandas

#### Background

You are the new Chief Data Scientist for your local government area. In this capacity, you'll be helping the school board and mayor make strategic decisions regarding future school budgets and priorities.

As a first task, you've been asked to analyse the area-wide standardised test results. You'll be given access to every student's maths and reading scores, as well as various information on the schools they attend. Your task is to aggregate the data to showcase obvious trends in school performance.

#### Before You Begin

Create a new repository for this project called pandas-challenge. Do not add this assignment to an existing repository.

Clone the new repository to your computer.

Inside your local Git repository, create a folder for this assignment and name it PyCitySchools.

Add your Jupyter notebook to this folder. This will be the main script to run for analysis.

#### Instructions

Using Pandas and Jupyter Notebook, create a report that includes the following data. Your report must include a written description of at least two observable trends based on the data.

Hint: Check out the sample solution called PyCitySchools_starter.ipynb located in the .zip file to review the desired format for this assignment.

## Local Government Area (LGA) Summary
Perform the necessary calculations and then create a high-level snapshot of the local government area's key metrics in a DataFrame.

Include the following:

Total number of unique schools

Total students

Total budget

Average maths score

Average reading score

% passing maths (the percentage of students who passed maths)

% passing reading (the percentage of students who passed reading)

% overall passing (the percentage of students who passed maths AND reading)

Note: A passing grade is 50 or higher.

## School Summary
Perform the necessary calculations and then create a DataFrame that summarises key metrics about each school.

Include the following:

School name

School type

Total students

Total school budget

Per student budget

Average maths score

Average reading score

% passing maths (the percentage of students who passed maths)

% passing reading (the percentage of students who passed reading)

% overall passing (the percentage of students who passed maths AND reading)

## Highest-Performing Schools (by % Overall Passing)
Sort the schools by % Overall Passing in descending order and display the top 5 rows.

Save the results in a DataFrame called "top_schools".

## Lowest-Performing Schools (by % Overall Passing)
Sort the schools by % Overall Passing in ascending order and display the top 5 rows.

Save the results in a DataFrame called "bottom_schools".

## Maths Scores by Year
Perform the necessary calculations to create a DataFrame that lists the average maths score for students of each year level (9, 10, 11, 12) at each school.

## Reading Scores by Year
Create a DataFrame that lists the average reading score for students of each year level (9, 10, 11, 12) at each school.

## Scores by School Spending
Create a table that breaks down school performance based on average spending ranges (per student).

Use the code provided below to create four bins with reasonable cutoff values to group school spending.

spending_bins = [0, 585, 630, 645, 680]
labels = ["<$585", "$585-630", "$630-645", "$645-680"]
Use pd.cut to categorise spending based on the bins.

Use the following code to then calculate mean scores per spending range.

spending_maths_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"]).mean()["Average Maths Score"]
spending_reading_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"]).mean()["Average Reading Score"]
spending_passing_maths = school_spending_df.groupby(["Spending Ranges (Per Student)"]).mean()["% Passing Maths"]
spending_passing_reading = school_spending_df.groupby(["Spending Ranges (Per Student)"]).mean()["% Passing Reading"]
overall_passing_spending = school_spending_df.groupby(["Spending Ranges (Per Student)"]).mean()["% Overall Passing"]
Use the scores above to create a DataFrame called spending_summary.

Include the following metrics in the table:

Average maths score

Average reading score

% passing maths (the percentage of students who passed maths)

% passing reading (the percentage of students who passed reading)

% overall passing (the percentage of students who passed maths AND reading)

## Scores by School Size
Use the following code to bin the per_school_summary.

size_bins = [0, 1000, 2000, 5000]
labels = ["Small (<1000)", "Medium (1000-2000)", "Large (2000-5000)"]
Use pd.cut on the "Total Students" column of the per_school_summary DataFrame.

Create a DataFrame called size_summary that breaks down school performance based on school size (small, medium, or large).

## Scores by School Type
Use the per_school_summary DataFrame from the previous step to create a new DataFrame called type_summary.

This new DataFrame should show school performance based on the "School Type".

------- 

## Analysis

### Conclusions

1. Independent Schools are Better Placed to Achieve Higher Passing Grades on Average</br>
</br>
type_summary</br>
Average Maths Scores	Average Reading Scores	% Passing Maths	% Passing Reading	% Overall Passing</br>
School Type				</br>	
Government	69.83%	69.68%	84.46%	83.59%	70.70%</br>
Independent	71.37%	70.72%	89.20%	86.25%	76.97%</br>
</br>
2. Smaller Schools With A Lower Number Of Students Perform Better Than Larger Schools With More Students</br>
</br>
size_summary</br>
Average Maths Scores	Average Reading Scores	% Passing Maths	% Passing Reading	% Overall Passing</br>
Total Students Range					</br>
Small (<1000)	72.34%	71.64%	90.81%	87.56%	79.07%</br>
Medium (1000-2000)	71.42%	70.72%	89.85%	86.71%	78.04%</br>
Large (2000-5000)	69.75%	69.58%	84.25%	83.30%	70.29%</br>

