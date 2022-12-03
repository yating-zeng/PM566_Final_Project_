PM566 Final Project
================
**Yating Zeng**
2022-12-02

This is my PM566 Final Project website.
<https://yating-zeng.github.io/PM566_Lab12/Final_Project.html>

And Supplementary website.
<https://yating-zeng.github.io/PM566_Lab12/Final_Project_Supplementary.html>

<br>

# Introduction

COVID-19 has been here for around 3 years, with vaccine widely used. It
would be likely that some of the people tend to not take the vaccine
than the others. Thus, in this project, the question of my interest is:
What is the association between age and the vaccination status (at least
one dose & completed a primary series) in California state? For this
project, I’ll use the dataset on Covid-19 vaccination from the Centers
for Disease Control and Prevention (CDC) website, which provided data
for select demographic characteristics (age, sex, and age by sex) of
people receiving COVID-19 vaccinations in the United States at the
national and jurisdictional levels, fitting my analysis interest well.
All the data were cumulative data, which were counted since the date it
started observing.

<br>

# Methods

## 1.Dataset

In this project, the dataset used was a public resource from CDC
website, named “COVID-19 Vaccination Age and Sex Trends in the United
States, National and Jurisdictional”. The link of the dataset is shown
below:
<https://data.cdc.gov/Vaccinations/COVID-19-Vaccination-Age-and-Sex-Trends-in-the-Uni/5i5k-6cmh>.
The CSV file of the data was then downloaded and read into R studio for
further analysis in this project.

<br>

## 2.Data cleaning, wrangling and EDA

After checking the summary of the content of the dataset, the dimensions
and the original properties for each variable were known. I filtered the
data to create a new dataset to keep only the information of California.
For simplifying the typing in analysis, 7 columns were renamed to be
shorter. Then the proportion of missing values of each column and column
“Demographic_Category” were checked. Considering that age and
vaccination status of primary dose series were the main factors towards
this analysis, the information about “Booster”, “Age_unknown” and all
the “Age\>65” levels of the “Demographic_Category” column, and and the
missing values of “dose1”(count of people take at least one dose) and
“census” (census statistics used for calculating the percentage of
vaccination) were removed.

Because the information this dataset was about the information strongly
rely on time series, and all the statistics were cumulative data, a new
variable “date” was created for further reorder the data by the time
recorded. Based on the category from “Demographic_Category” variable
(now named “cat”), the original dataset was split into 4 subset for
better analysis, which are 1. objects from both sex categorized only by
age level; 2. objects were all females categorized by age level; 3.
objects were all males categorized by age level; and 4. objects from
both sex categorized only by sex level.

Totally 25 tables and figures were created, with 1 table and 4 figures
would shown below and the others to be the supplementary. All the tables
and figure were planed to create by 2 vaccination status (“at least one
dose” and “completed a primary series”) and 4 categorical groups (“age”;
“female_age”; “male_age”; and “sex”). The summary tables and figures
would show the minimum, 1st quantile, median, 3nd quantile, maximum, and
the number of recorded objects of “the percentage of people” with the 2
kinds of vaccination status grouped by age, sex or age groups stratified
by sex. The reason to use data stratified by sex was to remove the
possible confounding effect from sex on the association between
vaccination status and age level. The association between the age and
vaccination status would be shown with scatterplots.

<br>

# Results

Considering that all the results for people who completed a series dose
(Supplementary table 4-7, 11-15,17-20) were consistent with the results
for people with at least one dose, thus, in this report, we would focus
on the showing the results of analysis for people with at least one
dose, which contained more information.

## 1. Summary tables

From the summary table of the percent of people with at least one dose
grouped by age (Table 1), we could notice that excepting a little part
of the data, most part the data were showing a trend that the statistics
(the minimum, 1st quantile, median, 3nd quantile, maximum) of Percent of
people with at least one dose would be larger when the age level was
higher. And for the major part of observed objects, who were aged from
12-17 years old to 75+ years old, the final vaccination rate will went
up to around 90%, while for the low age-level(\<5 years) objects, the
vaccination rate were all under or around 10%, and for 5-11 years
objects the vaccination rate stayed in the middle, which is around 50%.
This trend were consistent with the results form all the other 2 summary
tables of Percent of people with at least one dose grouped by age
stratified by sex (Supplementary table 1 & 2).

<br>

**Table 1.Summary of Percent of people with at least one dose grouped by
age** ![](Final_Project_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

<br>

## 2. Summary figures

The summary figures (Figure 1) showed the similar trend mentioned above
relatively. Excepting those information, we still could notice that for
the object age level from 5-11 years old to 65-74 years old, with the
age level went up, the major part of the statistics would with higher
values, which means it might take shorter time to have a relatively high
vaccination rate for those people with higher age level.

![](Final_Project_files/figure-gfm/summary%20graphs%20for%20dose1-1.png)<!-- -->
<br> From the line plot (figures 2) suggests that there would be
difference of the percent of having at least one dose between female and
male, making it to be more appropriate to use the stratified data for
analyzing the association between age and vaccination rate.

![](Final_Project_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

<br>

## 3. Visualization of the association

These 2 figures (Figure 3-4) all verified the trend that after adjusting
by sex, the vaccination rate would be higher with the age level being
higher for the same time point, and the objects with higher age might
take shorter time to have a relatively high vaccination rate. Which
needs to be mentioned is that, this trend was also observed in the low
age-level group(\<5 years), but with obviously lower vaccination rate
than the major part of the sample objects.

![](Final_Project_files/figure-gfm/visualization%20for%20first%20dose-1.png)<!-- -->![](Final_Project_files/figure-gfm/visualization%20for%20first%20dose-2.png)<!-- -->

<br>

# Conclusion

We could believe that there could be an association between age and the
two vaccination status (at least one dose & completed a primary series)
in California state.For both 2 kinds of vaccination status(take at least
one dose & with completed series) and both sex, the vaccination rate
would be higher with the age level being higher for the same time point,
and the objects with higher age might also take shorter time to have a
relatively high vaccination rate. And the final vaccination rate would
be higher with the age level being higher, but the rate for people with
age less than 5 years old would keep in a low level, even though they
follow the same trend mentioned above.

<br>
