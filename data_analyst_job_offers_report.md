
# The Data Analyst Jobs Report

This is a report of data analyst jobs offer. The data are collected from
Glassdoor.com (some value show that they are from Employer Est.) and
provided by picklesueat. This analysis is for private project exercise.

  - The data report can be found bellow  
  - The analysis was conducted with R  
  - The code can be found here  
  - [The data sets can be found
    here](https://github.com/picklesueat/data_jobs_data)

This report is inspired by [Brian
Dean](https://backlinko.com/seo-jobs-report)

# Introduction

The Data Analyst Job Offers data sets are for job offers from United
States. The data provider has cleaned the data so it will be ready to
use for analysis. This data sets contain 5631 observation of 18
variables. The data contain information such as `Salary Estimate`, `Job
description`, or `Location` that are interesting to be analyzed.

The data needed some wrangling to be able to use because there is some
error in data writing. For example, `Salary Estimate` variable is
character type of column when we expect it should be numeric type. Or,
the use of “-1” value to what we expected to be `NA` value or `FALSE`
value.

# Job Title

## Common Words

**What words are the most used in the job title?**

We wanted to know what words the most used in data analyst job offers in
this data. It also gives us insight what the most offered role at US. In
this data, we applied simple text mining on `Job Title` variable. Using
function by `tidytext` package, we tokenize the job title into single
word and drop the stop words and certain words such as `data` and
`analyst` (because they are the job we are discuss about). Then, we
visualize the words frequency that more than 60 occurrences.

![](data_analyst_job_offers_report_files/figure-gfm/job%20title-1.png)<!-- -->

From the plot we could see that the most common words use in the job
title are “Senior”, “Business”, and “Junior”. Two of them , “Senior” and
“Junior”, represent the seniority level of the jobs. There are also
another words on the plot that represent the seniority level such as
“II”, “III”, and “Lead”. The other words represent function or
sector of offered jobs.

# Job Description

## Education Requirement

**What degree are the most required in the job offers?**

Job offers usually describe minimum education as requirement for
applying it. In this data sets we could find education requirement in
`Job Description` variable. To finding the education we just simply
convert the value of column into lower case alphabet and look for the
words related to the degree itself.

From the plot we could see that minimum degree most required is
Bachelor’s Degree. In total we get 5369 positions require Bachelors,
18 require Master’s, 5 require Doctorate, and 221 not mentioning the
degree. We have looked manually to the data and got some information
that the positions that not mentioning bachelor’s degree, required the
work experience instead.

![](data_analyst_job_offers_report_files/figure-gfm/minimum%20degree%20required-1.png)<!-- -->

**Actual degree required**

If we looked on the plot above, we would say that not so many positions
for data analyst jobs require Master’s or Doctorate degree. But if we
looked at the data manually, we’ll find that actually many of them
prefer to require Master’s degree. On the plot bellow, we could see that
more than 1000 positions require Master’s Degree. Afterwards, we can say
that the positions also open the opportunity to the lower degree but
prefer to choose the higher one.

![](data_analyst_job_offers_report_files/figure-gfm/all%20degree%20required-1.png)<!-- -->

## Experience Requirement

Still using `Job Description` variable, we would like to look for the
experience years require for data analyst jobs. We simply extracted the
variable by looking for phrase that similar to “years experience” or
another like that.

When we looked at the data manually, we got some information that there
is position that require more than 20 years experience, but we didn’t
include it to the plot. From the plot, we can say that most of job
offers require 2-5 years of experience. It also relates to most common
words used in the job title such as senior, lead, II, or III that inform
us the jobs are for higher level.

![](data_analyst_job_offers_report_files/figure-gfm/plot%20experience-1.png)<!-- -->

## Tools Requirement

Apart from education and years experience, job positions require some
tools the candidates should have. They are database, BI, or programming
tools. We analyzed this aspect by tokenize the `Job Description`
variable into words and then filter them with some written tools by
writer.

We collect the tools that more than 20 occurrences and visualize them on
the plot bellow. From the plot we could say that the most required for
database tools are SQL and Access, for analysis and visualization tools
are Excel and Tableau, for programming tools are Python and R.

![](data_analyst_job_offers_report_files/figure-gfm/tools%20required-1.png)<!-- -->

# Salaries

## Salary Estimate

**What are the salary estimate for the data analyst jobs in USA?**

Before, I have mentioned that `Salary Estimate` column is character type
of column where we expected to be numeric type of column. So, we
extracted it and got the salary range. For the analysis we use an
addition column, called `Average Salary`. The range value of the salary
estimate can be seen on the plot bellow. We could see that the average
of salary estimate for data analyst jobs is around $72K. But we could
also say that the average of salary estimate is the median value because
we have outlier at the large value of the data (or the data has positive
skew distribution).

![](data_analyst_job_offers_report_files/figure-gfm/plot%20average%20salary-1.png)<!-- -->

## Salaries by City

**Which location has the highest salary estimate?**

![](data_analyst_job_offers_report_files/figure-gfm/salaries%20by%20city-1.png)<!-- -->

## Salaries by State

**Which state has the highest average salary estimate?**

![](data_analyst_job_offers_report_files/figure-gfm/salaries%20by%20state-1.png)<!-- -->

Data Source : Github - picklesueat  
\- (<https://github.com/picklesueat/data_jobs_data>)  
Inspired by SEO Job Report - Brian Dean  
\- (<https://backlinko.com/seo-jobs-report>)  
\- Reference
(<https://www.kaggle.com/erickdcohen/is-there-a-correlation-between-rating-and-salary>)
