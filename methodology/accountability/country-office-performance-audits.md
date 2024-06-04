# Country Office Performance Audits

<table data-header-hidden><thead><tr><th width="292"></th><th></th></tr></thead><tbody><tr><td>Data Owner</td><td>Narayanan Chettiar (<a href="mailto:narayanan.chettiar@undp.org">narayanan.chettiar@undp.org</a>), OAI</td></tr><tr><td>Availability in Data Warehouse</td><td>Available</td></tr><tr><td>Data Refresh Rate</td><td>Daily</td></tr><tr><td>Accountability Weighted Scoring</td><td>30%</td></tr></tbody></table>

## Introduction

Country Office Audits are audits performed by [OAI (Office of Audit and Investigations)](https://www.undp.org/accountability/audit-and-investigations). They measure compliance with corporate rules and regulations. The Performance App takes data from 2018 onwards for all the Country Office audits published on the [Audit Public Disclosure website. ](https://audit-public-disclosure.undp.org/)We showcase the rating from the latest country office audit, as some country offices may have had multiple audits during that period.

There are four main possible audit ratings:

* Fully Satisfactory
* Minor Improvements
* Major Improvements
* Unsatisfactory

The underlying data has more categories, but we have mapped it as follows:\\

| Old Categories                                  | New Categories                                  |
| ----------------------------------------------- | ----------------------------------------------- |
| Fully Satisfactory                              | Fully Satisfactory                              |
| Good                                            | Fully Satisfactory                              |
| Satisfactory                                    | Fully Satisfactory                              |
| Partially Satisfactory/SI                       | Satisfactory/Some Improvement Needed            |
| Partially Satisfactory                          | Satisfactory/Some Improvement Needed            |
| Satisfactory/Some Improvement Needed            | Satisfactory/Some Improvement Needed            |
| Marginally Deficient                            | Partially Satisfactory/Major Improvement Needed |
| Partially Satisfactory/Major Improvement Needed | Partially Satisfactory/Major Improvement Needed |
| Partially Satisfactory/MI                       | Partially Satisfactory/Major Improvement Needed |
| Seriously Deficient                             | Unsatisfactory                                  |
| Unsatisfactory                                  | Unsatisfactory                                  |
| Deficient                                       | Unsatisfactory                                  |

An audit will require a set of management responses that are then tracked in a system called [CARDS](https://cards.undp.org/), managed by OAI. The Country Office needs to implement these responses within specific timeframes and flag them according to the traffic light methodology.

* 0-12 months — Great (Green)
* 12-18 months — Acceptable (Yellow)
* 18+ months — Unacceptable (Red)

## Organisational Objective

The organisational objective is the best audit performance possible, with no unsatisfactory audits and maximising entirely satisfactory audits.

## Data

* **as\_of\_date**: The date when the data was extracted or last updated.
* **audit\_categ**: The category or type of audit conducted, e.g., OAI (Office of Audit and Investigations).
* **audited\_bureau**: The bureau or regional office that was audited, e.g., RBAS (Regional Bureau for Arab States), RBA (Regional Bureau for Africa), RBEC (Regional Bureau for Europe and the CIS).
* **audited\_org\_id\_c**: The unique identifier for the audited organization.
* **audited\_cty\_code**: The ISO 3166-1 alpha-3 country code for the audited country, e.g., MAR (Morocco), ZWE (Zimbabwe), ROU (Romania).
* **audited\_unit\_desc**: A brief description of the audited unit or entity.
* **action\_bureau**: The bureau or regional office responsible for taking action on the audit recommendations.
* **action\_org\_id\_c**: The unique identifier for the organization responsible for taking action on the audit recommendations.
* **action\_cty\_code**: The ISO 3166-1 alpha-3 country code for the country where the action is to be taken.
* **action\_unit\_desc**: A brief description of the unit or entity responsible for taking action on the audit recommendations.
* **action\_responsible\_person**: The name or title of the person responsible for taking action on the audit recommendations.
* **audit\_id**: A unique identifier for the audit.
* **audit\_title**: The title or name of the audit.
* **audit\_period\_start**: The start date of the period covered by the audit.
* **audit\_period\_end**: The end date of the period covered by the audit.
* **audit\_issue\_date**: The date when the audit report was issued.
* **audit\_type**: The type of audit conducted, e.g., COA (Country Office Audit), DEX (Direct Execution Audit).
* **reco\_no**: The number of the recommendation within the audit report.
* **recom\_id**: A unique identifier for the recommendation.
* **reco\_title**: A brief title or summary of the recommendation.
* **reco\_descr**: A detailed description of the recommendation.
* **reco\_planned\_imnpl\_d**: The planned implementation date for the recommendation.
* **reco\_priority**: The priority level assigned to the recommendation, e.g., High, Medium, Low.
* **reco\_oai\_status**: The status of the recommendation as determined by OAI, e.g., Implemented, Open.
* **reco\_open**: A binary indicator (0 or 1) showing whether the recommendation is still open or has been closed. This is a calculated field.
* **sub\_domain**: The specific area or domain within the organization that the recommendation pertains to, e.g., SRF (Strategic Results Framework), IT and communications.

## Data Export

{% hint style="danger" %}
Requires definition
{% endhint %}

## Calculation of Scoring

We score only using each country's latest CO audit reports. Previous historical audit ratings are shown in the indicator drill down but are not considered in the scoring methodology.

\
For each audit result, we assign the following scores:

* Fully Satisfactory = 100
* Satisfactory / Some Improvement Needed = 80
* Partially Satisfactory / Major Improvement Needed = 60
* Unsatisfactory = 0

Unsatisfactory is rated as zero. We want to significantly reduce the aggregate scores if even a small number of country offices in a region have Unsatisfactory audit ratings because these are so important to the organisation.

For Regional Bureau aggregation, we take an average of all the scoring, and the global average is calculated as an average of all country scores, not as an average of the Regional Bureau aggregation. This is to avoid skewed results, as different Regional Bureaus have different numbers of country offices. No weight is attached to country population size, amount of programming, or office size/budget.

## Traffic Light System

| Traffic Light | Score |
| ------------- | ----- |
| Green         | 85+   |
| Yellow        | 70+   |
| Red           | <70   |

## Limitations & Future Improvements

* Not incorporating country size, budget, programming amount, and other key details into weightings could fail to account for larger country offices' naturally higher complexity and risk exposure. Weightings may better reflect performance. An office with many projects and budgets receiving an Unsatisfactory audit rating is far more important to the organization than a smaller office receiving an Unsatisfactory audit rating — but this is currently not reflected in the methodology.
* Looking only at the latest audit per country loses historical context. Incorporating a rolling 3-5-year average could smooth out anomalies and show improvement/regression over time.
* No qualitative context is provided on why audits scored the way they did or what actions are being taken. Incorporating audit insights could make the data more meaningful.
* We do not take into account the management responses in the scoring methodology, but we do show it in the drill-down

## Resources

* [Public Audit Disclosure Website](https://audit-public-disclosure.undp.org/)
* [CARDS](https://cards.undp.org/) (Requires invitation from OAI)

## Draft New Audit Indicator

This is the draft for the new audit indicator that considers not only Country Officer Performance Audits, but also project audits and open management recommendations:

### Part 1: Country Office Performance (50% by default)

* Last CO Performance Audit (80% of Part 1 or 100% if B is not applicable)&#x20;
* B) DIM & Other Project Audits done by OAI, if applicable (20% of Part 1)&#x20;
* &#x20;How do we determine the overall weight of Part 1?&#x20;
  * 0-2 years: 50% weight&#x20;
  * 2+ years: 40% weight&#x20;
  * 3+ years: 30% weight&#x20;
  * 4+ years: 20% weight&#x20;

{% hint style="info" %}
Note that the years are based on the issue date of the audit and is recalculated daily
{% endhint %}

### Part 2: NIM/NGO Project Audit (70% of \[Indicator minus Part 1])

#### IF CO USES NATIONAL AUDIT SYSTEMS (HACT):

* Note, we use the actual amounts for the year that it was audited to calculate the below.
* Sum of all $ amount of Unqualified Reports
* Numerator is the total of audited expenses where all Are Unmodified:
* Audit Opinion (CDR)
* Cash Position Opinion
* Asset and Equipment Opinion
* Divided by Total $ Sum of All Reports -> Total sum of audited expenses column is denominator

§  ($UnqualifiedReports)/$TotalReports

§  A higher number is better,  as this means a higher amount of money going through implementing partners (IPs) with clean audits

§  % of money going through IPs with a clean audit opinion = point score

#### IF CO CANNOT USE NATIONAL AUDIT SYSTEMS (NON\_HACT)

* Use Audit Letter Overall Score for the following:
  * Materiality of NFM (A) (50%)
    * Satisfactory = 100
    * Partially Satisfactory = 80
    * Unsatisfactory = 60
  * Severity of Audit Observations (B) (50%)
    * Satisfactory = 100
    * Partially Satisfactory = 80
    * Unsatisfactory = 60
* Average Score of: Materiality of NFM (A) + Severity of Audit Observations (B)
* This is the score out of 100 for Part 2

### Part 3: Long Outstanding Audit Recommendations ≥18 months (30% of Indicator minus Part 1)

* 0 aged ≥18 Months: 100  points
* &#x20;1  aged ≥18 Months: 60 points
* 1+ aged ≥18 Months: 30 points
