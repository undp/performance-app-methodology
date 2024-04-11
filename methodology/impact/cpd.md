# CPD

{% hint style="info" %}
This is a draft proposal for a new indicator.
{% endhint %}

<table data-header-hidden><thead><tr><th width="277"></th><th></th></tr></thead><tbody><tr><td>Data Owner</td><td>Jessica Murray &#x3C;jessica.murray@undp.org>, CPU</td></tr><tr><td>Availability in Data Warehouse</td><td>Available</td></tr><tr><td>Data Refresh Rate</td><td>Daily</td></tr><tr><td>Impact Weighted Scoring </td><td>Not Yet Defined</td></tr></tbody></table>

## Introduction

Every CO (Country Office) has a CPD (Country Programming Document), which is the official agreement between the UNDP and the host country.&#x20;

CPDs are typically four to five years in length. They are broken down into Outcomes, typically three to four Outcomes per CPD. Each Outcome will have indicators called Outcome Indicators. Each Outcome is then further broken down into Output Indicators, which can sometimes be disaggregated further (i.e. to track separately the number of men and women reached with a particular programme).&#x20;

Outcome and Output Indicators serve different purposes within a Country Programming Document (CPD). Outcome Indicators measure high-level, long-term development results influenced by various factors, including the CO's programmes and external factors such as government policies, economic conditions, and social trends. Examples of Outcome Indicators include total GDP growth and unemployment rate. While the CO's work contributes to these indicators, they are not directly controllable by the CO alone.

In contrast, Output Indicators are more specific and directly linked to the CO's programmes and interventions in the host country. These indicators measure the tangible results and deliverables the CO is responsible for achieving through its projects and initiatives. Output Indicators are within the CO's control and can be directly influenced by the CO's actions. Examples of Output Indicators might include the number of people trained, the number of businesses supported, or the number of policy documents drafted directly from the CO's work.

Each Output Indicator has a baseline and a target for the entire CPD, which then has yearly milestone targets that need to be reached. Some indicators can be cumulative, while others are non-cumulative.

Cumulative indicators measure the total progress made from the beginning of the CPD until the current reporting period. The value reported for each year is the total value achieved since the start of the CPD. For example, if the indicator is "Number of people trained," and 100 people were trained in Year 1, 150 in Year 2, and 200 in Year 3, the reported values would be 100 for Year 1, 250 for Year 2 (100 from Year 1 + 150 from Year 2), and 450 for Year 3 (250 from Year 1 and 2 + 200 from Year 3).

On the other hand, non-cumulative indicators measure progress made within a specific reporting period, typically a year. The value reported for each year is the value achieved within that year only. For instance, if the indicator is "Number of policy documents drafted," and 3 policy documents were drafted in Year 1, 5 in Year 2, and 4 in Year 3, the reported values would be 3 for Year 1, 5 for Year 2, and 4 for Year 3.&#x20;

## Organisational Objective

The organisational objective is to meet all milestones at every Country Office for each CPD Outcome, thereby achieving the commitments with the national partners.&#x20;

## Data&#x20;

<details>

<summary>List of Data Column in CPD Dataset</summary>

* **Country**: The Country Office to which the data belongs.
* **CPD Name**: The name of the Country Programme Document.
* **Framework Name**: Identifies the specific framework or plan for measuring the indicator.
* **Reporting Period Name**: The year or specific period during which the reported data was collected.
* **Indicator Definition**: A detailed description of what is being measured, representing a specific outcome or output.
* **Data Type**: Specifies the type of data (e.g., number, percentage, currency, or milestone) for the indicator's values.
* **Type**: This refers to whether the indicator is an IRRF indicator or a local (i.e. country-specific) indicator
* **Result(s)**: A general column that could contain the actual results or outcomes related to the indicator.
* **Indicator Definition Translated**: Provides a translation or alternative expression of the indicator definition, possibly for clarity or localization.
* **Indicator Description**: Offers additional details or context about the indicator, further explaining what is measured.
* **Target Value**: The predetermined value or goal the indicator is expected to achieve within the reporting period.
* **Result Value**: The actual value measured or achieved for the indicator during the reporting period.
* **Indicator Component Group**: It is not clear what this column represents.&#x20;
* **CPD Start Year**: The starting year of the Country Programme Document's period of implementation.
* **CPD End Year**: The ending year of the Country Programme Document's period of implementation.

Note: CPD Start Year and CPD End Year are added after the extracted data was reviewed via an automated process using the CPD Name as the process.

</details>

### Extraction of CPD Dates

As there are no CPD Start Date or End Date columns, we manually created these using the CPD Name column that typically has this format:

* Afghanistan CPD 2024 - 2025
* Albania CPD - 2022 - 2026
* Bangladesh CPD 2022 - 2026
* Central African Republic CPD - 2023 - 2027
* Colombia CPD 2021 - 2024

```python
# Extracing the CPD Start Year and End Year from cpd_name column 
start_years = df['cpd_name'].str.extract('(\d{4}) -')[0]  # Adjusted for start year, ensuring space before dash
end_years = df['cpd_name'].str.extract('- (\d{4})')[0]    # Adjusted for end year, ensuring space after dash

# Adding the new columns to the dataframe
df.insert(loc=df.columns.get_loc('cpd_name') + 1, column='CPD Start Year', value=start_years)
df.insert(loc=df.columns.get_loc('cpd_name') + 2, column='CPD End Year', value=end_years)
```

### Managing MCP (Multi Country Programmes)

There are three MCPs in the data:

1. This is for Barbados MCP 2022 - 2026&#x20;
2. Trinidad and Tobago MCP 2022 - 2026&#x20;
3. &#x20;Jamaica MCP 2022 - 2026

{% hint style="warning" %}
**Significant Issue with MCP Data**\
Unfortunately, there is no indication in the data as to which country within the MCP each indicator belongs to which country. So, for now, we are simply labelling the "Country" field for these as the name of the MCP. For example, the Barbados MCP 2022 - 2026 will have "Barbados" as the Country field for all indicators.&#x20;
{% endhint %}

### CPD Names to Ignore

For now, the following CPD Names are ignored for this indicator as we are focused purely on country-level programming:

* Bur Policy & Prog Supp. Global - 2022 - 2025
* Crisis Bur Global - 2022 - 2025
* Dakar Regional Service Centre RPD - 2022 - 2025
* Istanbul Regional Hub RPD - 2022 - 2025
* Panama Regional Center RPD - 2022 - 2025
* Reg Bureau for Asia & Pacific RPD - 2022 - 2025
* Reg Bur for Arab States RPD - 2022 - 2025
* Reg Bur for Europe & CIS RPD - 2022 - 2025
* Reg Bur Latin Amer & Carib RPD 2022 - 2025
* Regional Bureau for Africa RPD 2022 - 2025
* Regional Center - Addis Ababa RPD - 2022 - 2025
* Regional Center In Amman RPD - 2022 - 2025
* UNDP Strategic Plan 2022-2025
* United Nations Office for South-South Cooperation 2022 - 2025
* United Nations Volunteers Global - 2022 - 2025

## Calculation of Scoring

{% hint style="info" %}
One exception to how we score the IRRF is that we ignore rows with blank values. Country offices are not responsible for all IRRF results, but they are responsible for all CPD results so that we will count blank rows. Part of the indicator may be compliance with how many of the CPD results have values.&#x20;
{% endhint %}

1. **Split out Outcome vs Output Indicators:** Because Country Offices do not control Outcomes fully (i.e. GDP Growth), we will only measure them on Output indicators. Due to the structure of the data, we will filter using the "Result(s)" column for any row that contains Outcome but not Output.&#x20;
2. **Group by Country:** Group the dataset by country using the "Country" column.
3. **Exclude Future Rows:** Remove rows where the `Reporting Period Name` column is a future year.
4. Pivot Data for Yearly Targets and Results:
5.



{% hint style="info" %}
Note below are the current IRRF Calculations to be edited:
{% endhint %}

1. **Exclusion Criteria:** Determine rows to be excluded based on conditions across several columns (baseline, A2023, M2022, M2023, M2024, M2025). The conditions are such that if all of these columns in a row are zero or missing, the row is flagged for exclusion.
2. **Calculate Percentage Change:** For remaining data rows, calculate a percentage change based on the values in the A2023, M2023, and baseline columns.  Special conditions are checked:&#x20;
   1. If any of the involved columns (A2023, M2023, baseline) is missing or all the columns are zero, the percentage change is not calculated for that row.&#x20;
   2. Percentage change is not calculated if (M2023 - baseline) equals to zero.&#x20;
   3. If the calculated percentage is greater than 100, it's capped at 100%.&#x20;
   4. If the calculated percentage is negative, it's set to 0%.
3. **Apply Calculated Percentage:** Assign the calculated percentage change to a new column in the dataset for rows that meet the criteria.
4. **Remove Rows with Missing Percentage Values:** Exclude rows where the percentage change could not be calculated or was set to None.
5. **Exclude Rows from 'Global' Region:** Remove rows where the region is listed as "Global".
6. **Group Data by Country and Calculate Mean Percentage:** Aggregate the refined dataset by country and calculate the average of the calculated percentage changes for each country.
7. **Group Data by Region and Calculate Mean Percentage:** Aggregate the project-level data by bureau/region and calculate the average of the calculated percentage changes for each bureau/region using the underlying project-level data.
8. **Calculate a Global Average Percentage:** Compute the overall average of the calculated percentage changes across all project-level data rows, providing a single metric to represent the overall trend or change captured in the dataset. To avoid the [aggregation trap](cpd.md#introduction), this global average is calculated directly from the project-level data, not from aggregated data.

{% hint style="warning" %}
**If a Country Office submits no data for either Target or Result, that particular CPD Indicator will be scored as zero as there is no evidence that they have achieved the target. The % of indicators that don't have full data will be displayed on the card, to assist Country Offices in updating their CPD reporting data.** &#x20;
{% endhint %}

## Traffic Light System&#x20;

The traffic light score for this indicator is the average progress of all Outcome Indicators Country Office.&#x20;

| Traffic Light | Score |
| ------------- | ----- |
| Green         | >80   |
| Yellow        | >=60  |
| Red           | <60   |

## Limitations and Future Improvements

* Multi-Country Programmes need to be disaggregated by individual country for reporting. &#x20;

## Useful Links

* [Executive Board Annual Session Documents](https://www.undp.org/executive-board/documents-for-sessions) — All final CPD Documents are stored here.
