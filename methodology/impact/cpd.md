# CPD

<table data-header-hidden><thead><tr><th width="277"></th><th></th></tr></thead><tbody><tr><td>Data Owner</td><td>Jessica Murray &#x3C;jessica.murray@undp.org>, CPU</td></tr><tr><td>Availability in Data Warehouse</td><td>Available</td></tr><tr><td>Data Refresh Rate</td><td>Daily</td></tr><tr><td>Impact Weighted Scoring</td><td>Not Yet Defined</td></tr></tbody></table>

## Introduction

Every CO (Country Office) has a CPD (Country Programming Document), the official agreement between the UNDP and the host country.

CPDs are typically four to five years in length. They are broken down into Outcomes, typically three to four Outcomes per CPD. Each Outcome will have indicators called Outcome Indicators. Each Outcome is then further broken down into Output Indicators, which can sometimes be disaggregated further (i.e. to track separately the number of men and women reached with a particular programme).

Outcome and Output Indicators serve different purposes within a Country Programming Document (CPD). Outcome Indicators measure high-level, long-term development results influenced by various factors, including the CO's programmes and external factors such as government policies, economic conditions, and social trends. Examples of Outcome Indicators include total GDP growth and unemployment rate. While the CO's work contributes to these indicators, they are not directly controllable by the CO alone.

In contrast, Output Indicators are more specific and directly linked to the CO's programmes and interventions in the host country. These indicators measure the tangible results and deliverables the CO is responsible for achieving through its projects and initiatives. Output Indicators are within the CO's control and can be directly influenced by the CO's actions. Examples of Output Indicators might include the number of people trained, the number of businesses supported, or the number of policy documents drafted directly from the CO's work.

Each Output Indicator has a baseline and a target for the entire CPD, which then has yearly milestone targets that need to be reached. Some indicators can be cumulative, while others are non-cumulative.

Cumulative indicators measure the total progress made from the beginning of the CPD until the current reporting period. The value reported for each year is the total value achieved since the start of the CPD. For example, if the indicator is "Number of people trained," and 100 people were trained in Year 1, 150 in Year 2, and 200 in Year 3, the reported values would be 100 for Year 1, 250 for Year 2 (100 from Year 1 + 150 from Year 2), and 450 for Year 3 (250 from Year 1 and 2 + 200 from Year 3).

On the other hand, non-cumulative indicators measure progress made within a specific reporting period, typically a year. The value reported for each year is the value achieved within that year only. For instance, if the indicator is "Number of policy documents drafted," and 3 policy documents were drafted in Year 1, 5 in Year 2, and 4 in Year 3, the reported values would be 3 for Year 1, 5 for Year 2, and 4 for Year 3.

## Organisational Objective

The organisational objective is to meet all milestones at every Country Office for each CPD Outcome, thereby achieving the commitments with the national partners.

## Data

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
* **Indicator Component Group**: It is not clear what this column represents.
* **CPD Start Year**: The starting year of the Country Programme Document's period of implementation.
* **CPD End Year**: The ending year of the Country Programme Document's period of implementation.

Note: CPD Start Year and CPD End Year are added after the extracted data was reviewed via an automated process using the CPD Name as the process.

</details>

### Outcome Names

This is being taken from the [Master Project List](../master-project-list.md), specifically:

* The table " UNDP\_CPD\_SP data"
* The column CPD\_OUTCOME\_DESCRIPTION

### Donor Type Names

We take from donor\_type\_lvl2\_descr in AITI Financials.

These are the options available:

| Name in AITI Financials                             | Performance App Display Name                                                      |
| --------------------------------------------------- | --------------------------------------------------------------------------------- |
| Academic, Training and Research                     | Academic, Training and Research                                                   |
| Foundations                                         | Foundations                                                                       |
| Multi-Partner Trust Funds and Joint Programmes      | Multi-Partner Trust Funds and Joint Programmes                                    |
| Multilateral - European Union                       | European Union                                                                    |
| Multilateral - International Financial Institutions | IFIs                                                                              |
| Multilateral funds and agencies                     | Multilateral funds and agencies                                                   |
| Non-DAC and non-programme countries                 | Non-DAC Donor                                                                     |
| Non-governmental and Non-Profit organizations       | NGO                                                                               |
| OECD-DAC countries                                  | OECD-DAC Donor                                                                    |
| OTHERS\_UNIDENTIFIED                                | Other                                                                             |
| Private Sector                                      | Private Sector                                                                    |
| Programme countries                                 | Programme Country                                                                 |
| United Nations System                               | United Nations System                                                             |
| Vertical funds                                      | {Individual Name of Vertical Fund}\* if available, if not "Vertical Fund — Other" |

\*This can be taken from "donor\_type\_lvl3", and we show the actual name:

| Name in AITI Financials | Performance App Display Name |
| ----------------------- | ---------------------------- |
| Vertical fund - Forest  | REDD+                        |
| Vertical fund - GEF     | GEF                          |
| Vertical fund - Global  | Global Fund                  |
| Vertical fund - Green   | GCF                          |

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

### **Outcome vs Output Indicators**

Because Country Offices do not fully control outcomes (e.g., GDP Growth), we will only measure them using Output indicators. Due to the data's structure, we will filter using the "Result(s)" column for any row that contains the word "Outcome" but not "Output".

### Managing MCP (Multi Country Programmes)

There are three MCPs in the data:

1. This is for Barbados MCP 2022 - 2026
2. Trinidad and Tobago MCP 2022 - 2026
3. Jamaica MCP 2022 - 2026

{% hint style="warning" %}
**Significant Issue with MCP Data**\
Unfortunately, there is no indication in the data as to which country within the MCP each indicator belongs to which country. So, for now, we are simply labelling the "Country" field for these as the name of the MCP. For example, the Barbados MCP 2022 - 2026 will have "Barbados" as the Country field for all indicators.
{% endhint %}

### Kosovo Missing Country Name

The Kosovo Programme Document 2021 - 2025 has no value under "Country", so this has been added manually. Eventually, this will have to be resolved at the source data level in the UNDP Data Warehouse.

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

### Output Indicators Missing Disagreegation Details

A significant number of Output Indicators are missing disaggregation details. Many duplicate Output Indicators in the CPD dataset have different target and results values, which hints that there are disaggregations present that are not stated in the dataset.

For instance, for _"3.3.2 Number of people benefitting from improved infrastructure for recovery in crisis or post-crisis settings"_ for Afghanistan, we get the two identical rows in the Result(s) column with the value AFG\_Output 1.3. For 2023, there are two target values of 135000 and 315000. This is likely the number of men and women tracked separately.

{% hint style="warning" %}
**Handling Missing Output Indicators Disagreegation Details**\
The process to handle these cases is to sum them together, but the disaggregation details should be provided in the future.
{% endhint %}

### Handling Baselines

In the input system for CPD targets and results, there is no way to record baselines for indicators. Many COs have added additional rows for years _before_ the CPD Start Date to indicate baselines, but this is not a widespread practice. For now, we are not using any baselines, but these are available in all CPDs and will have to be manually extracted to be used.

### Restructuring Data

To simplify the analysis, we pivot the data to align with the Integrated Results and Resources Framework (IRRF) structure. This approach facilitates progress calculation akin to IRRF methodologies but tailored to the nuances of Country Programming Document (CPD) indicators.

We undertook a data transformation process to accommodate the reporting of yearly milestones associated with each Output Indicator within the CPDs. Recognizing the need for separate analyses of target and result values by year, we pivoted the dataset to generate distinct columns for each combination of year and metric type—target and result.

This transformation was executed in several steps:

1. **Separate Pivots for Target and Result Values**: Our initial action involved creating two distinct pivot tables from the original dataset—one focusing on "Target Value" and the other on "Result Value." This separation allowed us to aggregate the values for each year, thus clearly distinguishing between the set targets and the achieved results.
2. **Column Renaming**: Following the pivot, we proceeded to rename the columns within both tables to bolster clarity and maintain consistency. The adopted naming convention explicitly denotes the metric type (target or result) alongside the year (e.g., "Target (2020)", "Results (2020)"), thereby facilitating immediate comprehension.
3. **Merging Pivot Tables**: A pivotal step in our process was merging the target and result pivot tables based on their shared identifiers. This crucial action enabled the congruent pairing of target and result values for each year, thus allowing for a direct comparison. The index columns used in this merging process were as follows:
   * Country
   * cpd\_name
   * Framework Name
   * CPD Start Year
   * CPD End Year
   * Indicator Definition
   * Data Type
   * Type
   * Result(s)
4. **Data Cleaning and Final Adjustments**: The concluding phase of our transformation entailed thoroughly reviewing the dataset for any inconsistencies or gaps, adjusting data types as needed, and addressing missing values. This phase included assigning "Not Required" to any target/result year columns falling in the future of CPD End Year range, thereby ensuring the dataset's completeness and readiness for substantive analysis.

## Calculation of Scoring

{% hint style="warning" %}
**Important Note on CPD Baselines**

The Performance App assumes that the baseline is zero as there is no reliable system data on the baselines. A manual effort is underway to extract baselines and then to adjust the system accordingly.
{% endhint %}

### Outcome % Calculation

For Outcome % calculations, we use average % results achievement of all the of the Output Indicators under that specific Outcome. One indicator = one vote, we do not agreegate or sum the results or targets.

### Output % Calculation

For Output % calculations, we use average % results achievement of all the of the Output Indicators under that specific Output. One indicator = one vote, we do not agreegate or sum the results or targets.

### Indicator Scoring

The indicator score is the average % of all output indicators combined. Each output indicator has one vote.

We calculate the progress against the target (i.e. milestone) for the most recent year, and take the reported Result for that year.

So, if the Target (2023) is 1,000,000 and the Result (2023) is 400,000, the % achievement of that specific indicator will be 40%

**Yearly Progress (%)** = ( Results for Year / Target for Year ​ )×100

{% hint style="warning" %}
**Important Note on Missing Data**\
If a Country Office submits no data for either Target or Result, that particular CPD Indicator will be scored as zero as there is no evidence that they have achieved the target. The % of indicators that don't have full data will be displayed on the card, to assist Country Offices in updating their CPD reporting data.
{% endhint %}

## Traffic Light System

The traffic light score for this indicator is the average progress of all Outcome Indicators Country Office.

| Traffic Light | Score |
| ------------- | ----- |
| Green         | >80   |
| Yellow        | >=60  |
| Red           | <60   |

## Limitations and Future Improvements

* Multi-Country Programmes need to be disaggregated by individual country for reporting.

## Useful Links

* [Executive Board Annual Session Documents](https://www.undp.org/executive-board/documents-for-sessions) — All final CPD Documents are stored here.

## New Methodology based on Quantum+ Data



So while the data _is_ in the UNDP Data Warehouse the structure is quite complex, so for now we are pulling the data from Quantum+ manually, as it is easier to deal with.

There are two extracted excel files from Quantum+:

1. **CPD Indicator and Data  —** This contains the bulk of the CPD indicator data
2. **CPD Indicator Linkage —** This tell us whether each indicator (via an ID) is an Outcome or an Output

#### Data structure for CPD Indicator & Data

* **Programme Name**: Name of the programme.
* **Geographical Area**: The specific geographical area or country related to the data.
* **Indicator Definition**: Detailed description of the indicator being measured.
* **Indicator Component: Indicator Component Name**: Name of the specific component of the indicator.
* **Result Value**: The actual value/result recorded for the indicator.
* **Target Value**: The target value set for the indicator.
* **Reporting Period: Reporting Period Name**: Name or description of the reporting period.
* **Type**: The type/category of the data (e.g., Local, National).
* **Programme Indicator ID**: Unique identifier for the programme indicator.
* **Last Modified Date**: The date when the data was last modified.

#### Columns in  CPD Indicator Linkage:&#x20;

* **Programme Indicator ID —** The ID of the indicator
* **Level —** This can be "Outcome" or "Output"
* **Result Name —** This is the result name, typically "Outcome 1.1", "Output 3.2", etc.

**Issues we are facing:**

**First, we need to clean up the data by extracting the CPD Start and End dates, and only considering Active CPDs**

1. ✅ No consecutive order numbers to the outcomes, we took in order (1, 2, 3, 4) — So for instance, I-00604 has "OutCome 10", should we consider this as "Outcome 1", or do it in order?&#x20;
   1. Outcome 4/7/10/15
   2. Outcome 1: (which is actually 4): naming UNSDCF Outcome 4: {Outcome Description/Statement}
   3. Outcome 2: (which is actually 7): naming UNSDCF Outcome 7: {Outcome Description/Statement}
   4. Outcome 3: (which is actually 10): naming UNSDCF Outcome 10: {Outcome Description/Statement}
   5. Outcome 4: (which is actually 15): naming UNSDCF Outcome 15: {Outcome Description/Statement
   6. Is it outcome description or outcome statement?
2. ✅ More than 4 outcomes — This is fine, we can show 5 Outcomes.&#x20;
3. Multiple numbers, 1.1.1 considered 1.1 — _how to handle this?_
4. Outputs number is not matching with existing outcomes 24.1 Output, Considered 2.1 — How to handle this?&#x20;
5. ✅ Negative Results Values — Solved,&#x20;
6. ✅ For outcomes had some values like 1.1 so we consider only the integer part(1) — Does this mean Indicator 1 of Outcome 1? For instance, I-13237 ID has this issue. Yes, we consider this just as "1"
7. Some output numbers like 1.24, 1.35 we consider them as (1.2, 1.3) — Need to confirm that this is the case — We consider something like 1.2.1 as Output 1 of Outcome 1.2. So the last number is the number of output, the first two numbers are what we use to match to the outcome.&#x20;

