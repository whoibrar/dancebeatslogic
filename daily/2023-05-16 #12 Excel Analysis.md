---
date : "2023-05-16"
title : "#12 Excel Analysis"
slug : "12-analysis"
time : "2h-00m"
summary : "Learning basic excel functions"
---

Starting a new course “Data Analysis in Spreadsheets”. Today, learned about a few basic functions in excel and how to use them.

---

Data Analysis : process of extracting meaningful insights from data

- Formulate Problem
- Collect and store data
- Explore data
- Clean data
- Analyze data
- Present findings

---

`ROUND(value, places)` rounds up a value to given decimal places 

- second argument defaults to zero and is optional

---

Summary statistics allow us to describe the dataset a macroscopic level. There are three main groups 

- Measure of frequency : How often does a value occur ?
- Measure of center : What typical value looks like ?
- Measure of spread : How do values vary across dataset ?

---

Measures of frequency functions 

- `COUNT()` counts the cells containing numerical data, doesn’t count any dates and currencies
    - A range can be passed like `COUNT(A1:A5)` where the range to count starts from `A1` and ends at `A5`
- `COUNTA()` counts any data type except for empty strings `""` and errors `#DIV/0!`
- `COUNTBLANK()` counts only empty cells and empty strings.

---

Measures of center 

- Mean or average is sum of values divided by no of values
- Median is useful when outliers are present in data
- `SUM()` takes two arguments and returns the sum of the values in that range
- `AVERAGE()` can be directly used on a given range
- `MEDIAN()` needs the list to be sorted in some order.

---

Identifying data quality issues can be done by working with `missing data` and `erroneous data`

- Missing data
    - `COUNTBLANK()`
    - `COUNT()`
    - `COUNTA()`
- Erroneous data
    - `MIN()` & `MAX()`

---

`A2:A` will give the range that starts with the second row of A and continue until the final row of A.

- Auto updates whenever new rows are added

---

Categorical data is where there are only finite number of values 

- `UNIQUE()` gives the count of no of unique values present in the given data
- `FILTER(range,cond1,[cond2, ...)` where range and first condition is required and additional optional conditions can be passed
- `SORT(range,sort_column,is_ascending)` sorts based on the second argument and order is determined by passing TRUE or FALSE on third

---
