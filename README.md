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
{73-134} secondary data cleaning, creating of a new columns for resarch(top 20,top 15, top 25) , graphs for proposal

{180-692} tree models section

{180-186}  creating primary chronological data split
{195-298} tree models with 12 parameters chronologically timed spilt

{195-210} training tree model with 12 parameters for top 15
{214-228} testing tree model with 12 parameters for top 15
{234-246} training tree model with 12 parameters for top 20
{250-263} testing tree model with 12 parameters for top 20
{269-281} training tree model with 12 parameters for top 25
{285-298} testing tree model with 12 parameters for top 25

{303-310} creating secondary random data split
{317-422} tree models with 12 parameters random spilt

{317-332} training tree model with 12 parameters for top 15
{336-351} testing tree model with 12 parameters for top 15
{356-369} training tree model with 12 parameters for top 20
{373-386} testing tree model with 12 parameters for top 20
{392-405} training tree model with 12 parameters for top 25
{409-422} testing tree model with 12 parameters for top 25

{424-429} calcaulating average factor importance chronological data vector
{432-437} calcaulating average factor importance random data vector
{440-444} calcaulating average  factor importance vector of chronological and random data and finding the top 7 parameters

{453-557} tree models with 7 parameters chronologically timed spilt

{453-468} training tree model with 7 parameters for top 15
{472-487} testing tree model with 7 parameters for top 15
{493-505} training tree model with 7 parameters for top 20
{509-522} testing tree model with 7 parameters for top 20
{528-540} training tree model with 7 parameters for top 25
{544-557} testing tree model with 7 parameters for top 25


{565-668} tree models with 7 parameters random spilt

{565-578} training tree model with 7 parameters for top 15
{582-597} testing tree model with 7 parameters for top 15
{602-615} training tree model with 7 parameters for top 20
{619-632} testing tree model with 7 parameters for top 20
{638-651} training tree model with 7 parameters for top 25
{655-668} testing tree model with 7 parameters for top 25

{671-676} calcaulating average factor importance chronological data vector
{679-684} calcaulating average factor importance random data vector
{687-692} calcaulating average factor importance vector of chronological and random data

{700-} logistical regression models

{700-787} logistical regression models with random data split 
{700-743} logistical regression model with 12 parameters for top 20 with random data
{745-787} logistical regression model with top 7 parameters for top 20 with random data

{791-864} logistical regression models with chronological data split 
{791-826} logistical regression model with 12 parameters for top 20 with random data
{829-864} logistical regression model with top 7 parameters for top 20 with random data and find shared factors.

{867-880} calcaulating average factor importance vector of chronological and random data 

{881-929} create top 20 and bottom 20 datasets,histogram of top and bottom 20 by continent

{932-1051} each of these 4 graphs each have a random of 13 countries from the top and the bottom 20 and it has time in the x axis and the selected variable in the y column, top 20 countries are in blue and bottom 20 are in red.

{932-961} progression of log_gdp chart blue countries in comparison to red countries
{962-991}progression of social_support chart blue countries in comparison to red countries
{992-1021}progression of pos_emotions chart blue countries in comparison to red countries
{1022-1051}progression of life_expectancy chart blue countries in comparison to red countries

{} appendix












Data section:
This Markdown file describes the data structure and organization for the project.
we will also elaborate about the pre project data cleaning
this data is a addition of WHR(world happiness reports) from 2011 to 2024.
the data cleaning included fixing the country names(where the standard of naming was changed in between the reports),erasing countries that dont exist and deleting duplicates.we also changed the column names(not all of the column names were identical in all the reports.)


Data Columns: 
1.YEAR: the year in which the survey was conducted(the data is from 2011-2024)
2.Rank- the country's Rank in the according year(from 1 to 158) not all countries were ranked .
3.Country name- the abbrivieated name of the relevant country.
4.Ladder score -the WHR provides a number of the final happiness score of the current country (from 1.3 to 7.9 )
5.upperwhisker- the upper boundry of the whisker score (from 1.43 to 7.91)
6.lowerwhisker- the lower boundry of the whisker score (from 1.3 to 7.78)
7.Log GDP per capita - a normalized version of the country's GDP index in comparison to the rest of the world(normalized in range from 0 to 2.2) 
8.Social support-a normalized version of the country's social support index in comparison to the rest of the world(normalized in range from 0 to 1.8)
9.Healthy life expectancy-a normalized version of the country's Healthy life expectancy index in comparison to the rest of the world(normalized in range from 0 to 1.13)
10.Freedom to make life choices-a normalized version of the country's Freedom to make life choices index in comparison to the rest of the world(normalized in range from 0 to 1.018)
11.Generosity-a normalized version of the country's Generosity index in comparison to the rest of the world(normalized in range from 0 to 0.57)
12.Perceptions of corruption-a normalized version of the country's Perceptions of corruption index in comparison to the rest of the world(normalized in range from 0 to 0.587)
13.Dystopia + residual-a normalized version of the country's Dystopia + residual index in comparison to the rest of the world(normalized in range from -0.11 to 3.482)
14.Top 20-  a binary variable of whether the country is in the top 20 in this perticular year(the outcome variable)

Rows: 1,969
Columns: 14
$ Year                                      <dbl> 2024, 2023, 2022, 2021, 2020, 20…
$ Rank                                      <dbl> 1, 143, 137, 146, 150, 153, 154,…
$ Country_name                              <chr> "Finland", "Afghanistan", "Afgha…
$ Ladder_score                              <dbl> 7.7360, 1.7210, 1.8590, 2.4040, …
$ upperwhisker                              <dbl> 7.810000, 1.775000, 1.923000, 2.…
$ lowerwhisker                              <dbl> 7.662000, 1.667000, 1.795000, 2.…
$ Log_GDP                                   <dbl> 1.7490000, 0.6280000, 0.6450000,…
$ Social_support                            <dbl> 1.7830000, 0.0000000, 0.0000000,…
$ Life_expectancy                           <dbl> 0.8240000, 0.2420000, 0.0870000,…
$ Freedom_of_choices                        <dbl> 0.9860000, 0.0000000, 0.0000000,…
$ Generosity                                <dbl> 0.1100000, 0.0910000, 0.0930000,…
$ `Explained by: Perceptions of corruption` <dbl> 0.502000000, 0.088000000, 0.0590…
$ Dystopia_and_residual                     <dbl> 1.782000, 0.672000, 0.976000, 1.…
$ Top_20                                    <lgl> TRUE, FALSE, FALSE, FALSE, FALSE…