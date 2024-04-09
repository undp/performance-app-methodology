# CPD

{% hint style="info" %}
This is a draft proposal for a new indicator.
{% endhint %}

* **Data owner:** Jessica Murray \<jessica.murray@undp.org>
* **Availability in Data Warehouse:** Available
* **Data Refresh Rate:** Daily
* **Weighted scoring:** (Not defined yet)

## Introduction

This Indicator is for the Country Office View only.&#x20;

## Organisational Objective

The organisational objective is to meet all milestones at every Country Office for each CPD Outcome, thereby achieving the commitments with the national partners.&#x20;

## Data&#x20;

<details>

<summary>List of Data Column in CPD Dataset</summary>

* **Country**: The geographic location or territory to which the data pertains.
* **CPD Name**: The name of the Country Programme Document, outlining the planned programs and initiatives.
* **Framework Name**: Identifies the specific framework or plan within which the indicator is being measured.
* **Reporting Period Name**: The year or specific period during which the reported data was collected.
* **Indicator Definition**: A detailed description of what is being measured, representing a specific outcome or output.
* **Data Type**: Specifies the type of data (e.g., number, percentage, currency) for the indicator's values.
* **Type**: May refer to the classification of the indicator or data, such as whether it is outcome-based, output-based, or another category.
* **Result(s)**: A general column that could contain the actual results or outcomes related to the indicator.
* **Indicator Definition Translated**: Provides a translation or alternative expression of the indicator definition, possibly for clarity or localization.
* **Indicator Description**: Offers additional details or context about the indicator, further explaining what is measured.
* **Target Value**: The predetermined value or goal that the indicator is expected to achieve within the reporting period.
* **Result Value**: The actual value measured or achieved for the indicator during the reporting period.
* **Indicator Component Group**: Could group indicators together based on certain criteria, themes, or components for analytical purposes.
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

## Calculation of Scoring



{% hint style="info" %}
One exception to how we score the IRRF is that we ignore rows with blank values. Country offices are not responsible for all IRRF results, but they are responsible for all CPD results so that we will count blank rows. Part of the indicator may be compliance with how many of the CPD results have values.&#x20;
{% endhint %}

1. **Split out Outcome vs Output Indicators:** Because Country Offices do not control Outcomes fully (i.e. GDP Growth) we will only measure on Output indicators. Due to the structure of the data, we will filter using the "Result(s)" column for any row that contains Outcome but not Output.&#x20;
2. **Group by Country:** Group the dataset by country using the "Country" column.
3. Arrange data for yearly milestones and target.&#x20;



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

