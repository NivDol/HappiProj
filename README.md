# HappiProj
 a git file for the project





here is a detailed read me for the code

Structure
---------
- modeling_summary.txt: Contains all R code and descriptive summaries for:
  - Decision tree models (chronological and random splits)
  - Logistic regression models (12 and 7 variables)
  - Factor importance aggregation
  - Country-level analysis (average rank, top/bottom countries by continent)
  - Progression plots of key factors over time (e.g., Log_GDP, Social_support)

Models Used
-----------

Decision Tree Models
- Built using `rpart` and evaluated via confusion matrices.
- Compared across different splits (time vs random).
- Variable importance visualized via pie charts.

Logistic Regression Models
- Built using `glm` with `binomial` family.
- Compared using both full and reduced (7-feature) models.
- Variable importance extracted via `caret::varImp`.

Key Findings
------------
- Chronological models showed moderate accuracy (82–95%), indicating reasonable generalization.
- Random split models were overly accurate (up to 98%), suggesting data leakage and overfitting.
- Logistic models (random and time-split) also showed high accuracy (>95%), indicating potential unreliability for future prediction.
- Top 4 shared features across all models:
  - Log_GDP
  - Social_support
  - Life_expectancy
  - Pos_emotions
  

Visualizations
--------------
Includes:
- pie charts for each model factor importance
- tree Visualizations for each  individual tree model
- Bar charts of continent distribution (Top vs Bottom 20 countries).
- Line plots showing time progression of:
  - Log_GDP
  - Social_support
  - Pos_emotions
  - Life_expectancy
 





here are names and titles for each code segment
{1-13} authors
{15-29} importing libaries
{53-70} preliminary data cleaning
{73-149} secondary data cleaning, creating of a new columns for resarch(top 20,top 15, top 25) , graphs for proposal

{180-706} tree models section

{195-201}  creating primary chronological data split
{210-314} tree models with 12 parameters chronologically timed spilt

{210-225} training tree model with 12 parameters for top 15
{229-244} testing tree model with 12 parameters for top 15
{249-261} training tree model with 12 parameters for top 20
{266-279} testing tree model with 12 parameters for top 20
{281-297} training tree model with 12 parameters for top 25
{301-314} testing tree model with 12 parameters for top 25

{317-322}  calcaulating average factor importance chronological data vector
{326-333} creating secondary random data split
{340-706} tree models with 12 parameters random spilt

{340-355} training tree model with 12 parameters for top 15
{359-374} testing tree model with 12 parameters for top 15
{379-392} training tree model with 12 parameters for top 20
{396-409} testing tree model with 12 parameters for top 20
{415-428} training tree model with 12 parameters for top 25
{433-446} testing tree model with 12 parameters for top 25

{448-453} calcaulating average factor importance random data vector
{456-460} calcaulating average  factor importance vector of chronological and random data and finding the top 7 parameters

{461-573} tree models with 7 parameters chronologically timed spilt

{469-484} training tree model with 7 parameters for top 15
{488-503} testing tree model with 7 parameters for top 15
{509-520} training tree model with 7 parameters for top 20
{525-538} testing tree model with 7 parameters for top 20
{544-556} training tree model with 7 parameters for top 25
{560-573} testing tree model with 7 parameters for top 25

{576-581} calcaulating average factor importance chronological data vector

{582-706} tree models with 7 parameters random spilt

{588-601} training tree model with 7 parameters for top 15
{605-620} testing tree model with 7 parameters for top 15
{625-638} training tree model with 7 parameters for top 20
{642-655} testing tree model with 7 parameters for top 20
{661-674} training tree model with 7 parameters for top 25
{674-691} testing tree model with 7 parameters for top 25


{693-698} calcaulating average factor importance random data vector
{701-706} calcaulating average factor importance vector of chronological and random data

{708-} logistical regression models

{713-} logistical regression models with random data split 
{713-787} logistical regression model with 12 parameters for top 20 with random data
{791-832} logistical regression model with top 7 parameters for top 20 with random data

{837-872} logistical regression models with chronological data split 
{837-872} logistical regression model with 7 parameters for top 20 with random data


{876-883} calcaulating average factor importance vector of chronological and random data 

{889-935} create top 20 and bottom 20 datasets,histogram of top and bottom 20 by continent

{937-1051} each of these 4 graphs each have a random of 13 countries from the top and the bottom 20 and it has time in the x axis and the selected variable in the y column, top 20 countries are in blue and bottom 20 are in red.

{937-966} progression of log_gdp chart blue countries in comparison to red countries
{968-997}progression of social_support chart blue countries in comparison to red countries
{999-1028}progression of pos_emotions chart blue countries in comparison to red countries
{1030-1060}progression of life_expectancy chart blue countries in comparison to red countries
{1063-1091}progression of Inequality chart blue countries in comparison to red countries
{1093-1122}progression of Inequality chart blue countries in comparison to red countries

{1124-1178}Appendix
Appendix:



Data section:
This Markdown file describes the data structure and organization for the project.
we will also elaborate about the pre project data cleaning
this data is a addition of WHR(world happiness reports) from 2011 to 2024.
the data cleaning included fixing the country names(where the standard of naming was changed in between the reports),erasing countries that dont exist and deleting duplicates.we also changed the column names(not all of the column names were identical in all the reports.)
in addition the scraping was directly from the WHR report website



Data Columns: 
1. YEAR: the year in which the survey was conducted (the data is from 2011–2024)\newline  
2. Rank – the country's Rank in the according year (from 1 to 158); not all countries were ranked plus the rank is by 3 year average.\newline  
3. Country name – the abbreviated name of the relevant country.\newline  
4. Ladder score – the WHR provides a number of the final happiness score of the current country (from 1.3 to 7.9).\newline 
5. Rank – the Country's rank in this year.\newline  
6. Inequality – level of inequality in the country from(0.9 to 4.1).\newline 
7.Social support – a normalized version of the country's social support index in comparison to the rest of the world (normalized in range from 0 to 1.8).\newline  
8.GDP –  the country's GDP .\newline  
9. Healthy life expectancy – a normalized version of the country's healthy life expectancy index in comparison to the rest of the world (normalized in range from 0 to 1.13).\newline  
10. Freedom to make life choices – a normalized version of the country's freedom to make life choices index in comparison to the rest of the world (normalized in range from 0 to 1.018).\newline  
11. Generosity – a normalized version of the country's generosity index in comparison to the rest of the world (normalized in range from 0 to 0.57).\newline  
12. Perceptions of corruption – a normalized version of the country's perceptions of corruption index in comparison to the rest of the world (normalized in range from 0 to 0.587).\newline  
13.Pos_emotions- a normalized version of the Pos_emotions of the responders from the country(from 0.18 to 0.9)\newline
14.Neg_emotions- a normalized version of the Neg_emotions of the responders from the country(from 0.1 to 0.7)\newline
15.Donated - a normalized version of how many people donated from said country(from 0.003 to 0.92)\newline
16.Volunteered- a normalized version of how many people donated from said country(from 0.02 to 0.65)\newline
17.Helped_stranger- a normalized version of how many people helped a stranger from said country(from 0.115 to 0.88)\newline
18.Top 20 – a binary variable indicating whether the country is in the top 20 in that particular year (an outcome variable).\newline
19.Top_15- a binary variable indicating whether the country is in the top 15 in that particular year (an outcome variable).\newline
20.Top_25- a binary variable indicating whether the country is in the top 25 in that particular year (the outcome variable).\newline
21.Top20_Last- a numbered variable indicating whether the country was in the top 20 in that previous year (an outcome variable).\newline
22.Log_GDP -the country's GDP in log base 10\newline


Rows: Rows: 2,283
Columns: 21 
$ Country_name    <chr> "Peru", "Tunisia", "Burkina Faso", "Australia", "Malta", "Israel", "Iraq", "Georgia", "Russian Federation", "DR Congo", "Philippines", "Indones…\
$ Year            <int> 2009, 2014, 2007, 2014, 2014, 2022, 2013, 2015, 2019, 2016, 2015, 2024, 2006, 2022, 2018, 2019, 2019, 2014, 2011, 2014, 2016, 2014, 2014, 2008,…\
$ Ladder_score    <dbl> 5.519, 4.764, 4.017, 7.289, 6.452, 7.662, 4.725, 4.122, 5.441, 4.522, 5.547, 5.573, 5.832, 5.870, 5.340, 5.674, 5.952, 6.037, 4.260, 4.240, 6.8…\
$ Rank            <int> 47, 98, 96, 9, 32, 2, 93, 122, 80, 105, 66, 84, 26, 67, 74, 69, 60, 44, 125, 119, 20, 114, 65, 74, 27, 42, 131, 97, 28, 143, 102, 67, 44, 126, …\
$ Inequality      <dbl> 2.2, 2.1, 1.3, 1.8, 1.9, 1.4, 3.0, 2.0, 2.3, 1.6, 2.7, 2.5, 2.4, 3.0, 2.5, 2.3, 2.0, 2.0, 1.9, 2.1, 2.0, 1.4, 2.4, 1.6, 1.5, 2.2, 1.7, 2.1, 2.1…\
$ Social_support  <dbl> 0.799, 0.680, 0.771, 0.924, 0.941, 0.954, 0.728, 0.517, 0.910, 0.864, 0.854, 0.814, 0.887, 0.868, 0.809, 0.784, 0.891, 0.932, 0.705, 0.778, 0.8…\
$ GDP             <dbl> 11206, 12753, 1732, 55253, 42958, 48196, 13713, 14937, 37699, 1253, 7692, 14474, 33613, 10072, 12262, 9985, 33473, 36218, 10990, 4588, 21572, 3…\
$ Life_expectancy <dbl> 68.10000, 66.10000, 49.50000, 70.10000, 70.70000, 70.62500, 61.00000, 64.10000, 63.70000, 52.30000, 61.30000, 61.91250, 62.70000, 63.93750, 63.…\
$ Freedom         <dbl> 0.6380000, 0.5890000, 0.5820000, 0.9230000, 0.9040000, 0.7750000, 0.5476667, 0.6400000, 0.7150000, 0.6370000, 0.9120000, 0.9070000, 0.8400000, …\
$ Generosity      <dbl> 0.202, 0.057, 0.095, 0.716, 0.781, 0.391, 0.241, 0.097, 0.241, 0.101, 0.212, 0.895, 0.499, 0.200, 0.807, 0.190, 0.076, 0.090, 0.058, 0.137, 0.1…\
$ Corruption      <dbl> 0.8800000, 0.7830000, 0.8330000, 0.4420000, 0.6700000, 0.6550000, 0.7100000, 0.5020000, 0.8480000, 0.8750000, 0.7550000, 0.8830000, 0.9170000, …\
$ Pos_emotions    <dbl> 0.7580000, 0.4240000, 0.6090000, 0.7400000, 0.6060000, 0.5830000, 0.5214667, 0.4480000, 0.6320000, 0.6100000, 0.7960000, 0.8420000, 0.7500000, …\
$ Neg_emotions    <dbl> 0.320, 0.321, 0.281, 0.245, 0.352, 0.183, 0.554, 0.233, 0.200, 0.222, 0.351, 0.285, 0.229, 0.269, 0.296, 0.419, 0.236, 0.151, 0.459, 0.216, 0.2…\
$ Donated         <dbl> 0.202, 0.057, 0.095, 0.716, 0.781, 0.391, 0.241, 0.097, 0.241, 0.101, 0.212, 0.895, 0.499, 0.200, 0.807, 0.190, 0.076, 0.090, 0.058, 0.137, 0.1…\
$ Volunteered     <dbl> 0.188, 0.057, 0.122, 0.396, 0.263, 0.196, 0.178, 0.184, 0.103, 0.104, 0.422, 0.654, 0.263, 0.397, 0.548, 0.201, 0.071, 0.194, 0.090, 0.125, 0.1…\
$ Helped_stranger <dbl> 0.423, 0.410, 0.375, 0.662, 0.501, 0.532, 0.745, 0.404, 0.449, 0.362, 0.552, 0.643, 0.626, 0.827, 0.552, 0.493, 0.417, 0.322, 0.427, 0.590, 0.4…\
$ Top_20          <lgl> FALSE, FALSE, FALSE, TRUE, FALSE, TRUE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, TRUE,…\
$ Top_15          <lgl> FALSE, FALSE, FALSE, TRUE, FALSE, TRUE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE…\
$ Top_25          <lgl> FALSE, FALSE, FALSE, TRUE, FALSE, TRUE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, TRUE,…\
$ Top20_Last      <dbl> 0, 0, 0, 1, 0, 1, 0, 0, 0, 0, 0, 0, 2, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 1, 0, 1, 1, 0, 0, 0, 0, 2, 0, 0, 1, 0, 1,…\
$ Log_GDP         <dbl> 9.324205, 9.453522, 7.457032, 10.919678, 10.667978, 10.783031, 9.526100, 9.611597, 10.537389, 7.133296, 8.947936, 9.580109, 10.422668, 9.217515…\