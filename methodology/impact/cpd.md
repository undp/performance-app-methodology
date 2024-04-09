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

