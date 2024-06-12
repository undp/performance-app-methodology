# Gender Parity

<table data-header-hidden><thead><tr><th width="289"></th><th></th></tr></thead><tbody><tr><td>Data Owner</td><td>Siddharth Pawar (<a href="mailto:siddharth.pawar@undp.org">siddharth.pawar@undp.org</a>), OHR</td></tr><tr><td>Availability in Data Warehouse</td><td>Available</td></tr><tr><td>Data Refresh Rate</td><td>Daily</td></tr><tr><td>Accountability Weighted Scoring</td><td></td></tr></tbody></table>

## Introduction

The gender parity indicator focuses on the split between men and women across the different roles available at UNDP, with a specific focus on leadership positions. This is in alignment with SDG 5 "Gender Equality" 

## Organisational Objective

To achieve gender parity  (approximately equal number of women and men) at all organisational levels, especially at the leadership level.&#x20;

## Data

* Mention that while this data is available in the data warehouse, becuase there are lots of custom business rules applied to the raw data, this is actually pulled from the OHR PowerBI directly. 

## Data Export

The data export for this indicator should contain both the scoring information as well as the raw data that may be useful to collegues as they do their own data analysis. 

The data export contains the following columns for the raw data

- **Country Office**: The name of the country office.
- **3 letter ISO Code**: The ISO code of the country.
- **Bureau**: The Bureau of the Country Office.
- **Positions**: The type of position.
- **% of men**: The percentage of men holding this position.
- **Number of men**: The actual number of men holding this position.
- **% of women**: The percentage of women holding this position.
- **Number of women**: The actual number of women holding this position.
- **Total number of people**: The total number of people holding this position in the business unit.

Then, we should also include the scoring information:

- - **Country Office**: The name of the country office.
- **3 letter ISO Code**: The ISO code of the country.
- **Bureau**: The Bureau of the Country Office.
- **% women in the UNDP workforce overall**: The percentage of women in the overall UNDP workforce.
- **% women in the UNDP workforce overall (score)**: The score derived from the percentage of women in the overall UNDP workforce.
- **% of women in leadership**: The percentage of women in leadership positions.
- **% of women in leadership (score)**: The score derived from the percentage of women in leadership positions.
- **Indicator score**: The combined total score from both metrics, out of 100. 
- **Traffic Light Score**: Green, yellow, or red. 


## Calculation of Scoring

This indicator is scored according to two metrics

1. % women in the UNDP workforce overall
2. % of women in leadership makes up the other half (USG + ASG + D2 + D1 + P5 + NOE + NOD)&#x20;

For % of women in UNDP’s workforce, 50% = 100; every percentage point above/below reduces the score by 1.5 pts. So, if UNDP has 45% women in the workforce, it would contribute 42.5 points to the final score.  This is only for Women, not the other way around.  \


The same method can be used for the percentage of women in leadership. So, if UNDP has 35% women in leadership, it would contribute 22.5 points to the total score (making the total score 70 in this example). If the final score has a decimal, it is rounded up. This requires the actual number of people, not the aggregate percentage because there are different numbers of people in each role. &#x20;

Each one is worth 50 points, and then sum both to get a score out of 100 points.

## Traffic Light System

| Traffic Light | Score |
| ------------- | ----- |
| Green         | 85+   |
| Yellow        | 70+   |
| Red           | <70   |

## Limitations and Future Improvements&#x20;



## Resources
