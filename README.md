# Assignment 7 - FCB 2020
### Deadline: 20/11/2020 - 23:59

## Submission procedure

This assignment has to be submitted using GitHub Classroom. This
means that you should have cloned the GitHub repo of this assignment from
the organization account for FCB in the academic year 2020-21 at
[https://github.com/funcompbio2020](https://github.com/funcompbio2020)
using the submission link provided at the FCB Moodle site.

Once you have cloned the GitHub repo which has `assignment-7` and your
GitHub username as repo name, then you can work on it in your local disk
and _push_ your changes whenever you like, but make sure that you have pushed
the last version of your assignment before the deadline. There is no
_submit_ button or any other specific submission procedure or action than
just pushing your changes to you GitHub assignment repo. When correcting the
assignment, the version available at the deadline will be retrieved. If the
first version available is posterior to the deadline, then the mark of the
assignment will have a penalty.

## Description

The goal of this assignment is to **calculate a ranking of Catalan counties
based on the mean accumulated incidence of COVID19 infections by 100,000 inhabitants
for the month of October derived from the general population**. To achieve this goal
you should follow these 2 steps:

  1. Create an R script called `analysis.R` with the R commands that
  read the CSV file `comarques_setmanal.csv` **provided in the repo
  of the assignment** and make the necesssary transformations and
  calculations to obtain a `data.frame` object of the ranking whose
  first lines look like this (round numerical results to one decimal
  point using the function `round()`):

  ```
             COUNTY IA14Oct 
  1           OSONA   974.7
  2         SEGARRA   868.4
  3 PLA DE L'ESTANY   849.2
  4       GARRIGUES   848.4
  5         GIRONES   767.1
  6       BAIX CAMP   731.4
  ```

  2. Let the `data.frame` object of the ranking be called `rnk`,
  the last line of your script should write to disk that ranking
  into a CSV file called `rnkIA14Oct20byCounty.csv` with the
  following R command:

  ```
  write.csv(dtf, "rnkIA14Oct20byCounty.csv", row.names=FALSE)
  ```

Your assignment repo should have the following files:

  1. This `README.md` file.
  2. The COVID19 data file `comarques_setmanal.csv`.
  3. The R script file `analysis.R`.
  4. The ranking file `rnkIA14Oct20byCounty.csv`.

The file `rnkIA14Oct20byCounty.csv` should have the following
characteristics:

  1. It should be a CSV file using the comma (`,`) as column separator.
  2. It should have the following line as first (column header) line:
     ```
     "COUNTY","IA14Oct"
     ```
  3. The second and following lines should contain the names of counties
     and the value of their mean accumulated incidence per 100,000 inhabitants
     for the month of October 2020 separated by a comma (`,`) and
     derived from the general population, that is, **excluding the data
     from geriatric residences**. For instance, one such lines could look
     like this one:
     ```
     "SEGRIA",442.8
     ```
  4. The second and following lines should be stored in descending order
     of the second column, corresponding to the mean accumulated incidence
     per 100,000 inhabitants for the month of October 2020 derived from the
     general population, i.e., the largest value should be at the top of the
     file, and the lowest at the bottom.

This assignment incorporates [GitHub Classroom Autograding](https://mspoweruser.com/github-classroom-autograding-feature),
which will help you to automatically test whether your R script is
correctly working after every _push_. More concretely, the autograding
will check whether the R script generates the CSV file `rnkIA14Oct20byCounty.csv`
and that this CSV file contains the expected result.

## Evaluation rubric

The rubric to evaluate this assignment consists of the following items:

  * Does the assignment contain the required files?
  * Does the file `rnkIA14Oct20byCounty.csv` contain the two required columns?
  * Is the file `rnkIA14Oct20byCounty.csv` ordered by descending mean accumulated
    incidence per 100,000 inhabitants for the month of October 2020 derived from
    the general population?
  * Does the R code runs without errors and produces the expected result?
