# IRRF

<table data-header-hidden><thead><tr><th width="280"></th><th></th></tr></thead><tbody><tr><td>Data Owner</td><td>Xiaodong Cai &#x3C;xiaodong.cai@undp.org></td></tr><tr><td>Availability in Data Warehouse</td><td>Not Available</td></tr><tr><td>Data Refresh Rate</td><td>Once Per Year</td></tr><tr><td>Impact Weighted Scoring</td><td>90%</td></tr></tbody></table>

## Introduction

The UNDP Integrated Results and Resources Framework (IRRF) sets out the development results, indicators, and targets that UNDP aims to contribute to from 2022 to 2025 in alignment with the new Strategic Plan. In other words, the IRRF measures our organisation's results.

Grounded in a rigorous consultative process, the IRRF spans three tiers, cascading from development impact to institutional outcomes, outputs, and organisational effectiveness.

1. **Tier 1 (Impact):** This tier captures long-term development changes in people's lives and the planet that UNDP contributes to. It is monitored through global indicators like poverty, inequality, and gender norms.
2. **Tier 2:**
   1. **Outcomes:** Medium-term institutional and behavioural changes in 3 areas that UNDP contributes to through work with partners. These are monitored through the SDGs and global indicators.
   2. **Outputs:** Short-term results from UNDP projects and activities across 6 signature solutions and three enablers. Direct UNDP accountability through 21 output indicators.

The Performance App only measures the performance of Tier 2b because these are the indicators that speak directly to UNDP’s contribution and achievement of development results. \\

Tier 2b includes 22 Results (i.e. Outputs) across UNDP's signature solutions and enablers, directly reflecting UNDP's work. Assessing results against IRRF targets provides a crucial means for UNDP to account for its contributions toward [Agenda 2030.](https://www.undp.org/sustainable-development-goals)

The output indicators span UNDP's six signature solutions:

1. Poverty and Inequality (4 indicators)
2. Governance (4 indicators)
3. Resilience (4 indicators)
4. Environment (2 indicators)
5. Energy (2 indicators)
6. Gender Equality (3 indicators).

There are also 3 Enablers, with one output each:

1. **Digital Capabilities:** People and institutions equipped with strengthened digital capabilities and opportunities to contribute to and benefit from inclusive digital societies (1 indicator)
2. **Innovation:** Innovation capabilities built, and approaches adopted to expand policy options at global, regional, national and sub-national levels
3. **Financing for the SDGs:** Public and private financing for the achievement of the SDGs expanded at global, regional, and national levels

Within these outputs, 57 indicators measure results from a specific baseline.

The indicators reflect a range of development areas that UNDP supports, such as policy and institutional strengthening, service delivery, climate resilience, women's empowerment, governance, crisis prevention and recovery, natural resource management, clean energy access, digital skills, and sustainable financing.

Each indicator measures direct UNDP contribution through tracking metrics such as the number of countries supported, the number of people benefiting from services, the number of policies strengthened, the number of solutions adopted, and the amount of financing mobilised. Based on their programmes and focus areas, any specific Country Office may contribute to a subset of these indicators.

## Organisational Objective

The organisational objective is that all milestones at every country office are met, and through this, we have the achievement of the global level milestones

## Data

The data is manually imported from Quantum+ into the Performance App, as this is only updated once per year there is no need to have the data available in the Data Warehouse. &#x20;

## **Data Export**

{% hint style="danger" %}
Data export requirements to be defined.
{% endhint %}

## Calculation of Scoring

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
8. **Calculate a Global Average Percentage:** Compute the overall average of the calculated percentage changes across all project-level data rows, providing a single metric to represent the overall trend or change captured in the dataset. To avoid the [aggregation trap](irrf.md#introduction), this global average is calculated directly from the project-level data, not from aggregated data.

## **Traffic Light System**

| Traffic Light | Score |
| ------------- | ----- |
| Green         | 80+   |
| Yellow        | 60+   |
| Red           | <60   |

## Resources

* [Annex 2 (Framework, Baseline Data, Methodology)](https://www.undp.org/sites/g/files/zskgke326/files/dp2021-28\_Annex%202\_1.docx)
