# Country Office Performance Audits

<table data-header-hidden><thead><tr><th width="292"></th><th></th></tr></thead><tbody><tr><td>Data Owner</td><td>Narayanan Chettiar (<a href="mailto:narayanan.chettiar@undp.org">narayanan.chettiar@undp.org</a>), OAI</td></tr><tr><td>Availability in Data Warehouse</td><td>Available</td></tr><tr><td>Data Refresh Rate</td><td>Daily</td></tr><tr><td>Accountability Weighted Scoring</td><td>30%</td></tr></tbody></table>

## Introduction

Country Office Audits are audits performed by [OAI (Office of Audit and Investigations)](https://www.undp.org/accountability/audit-and-investigations). They measure compliance with corporate rules and regulations. The Performance App takes data from 2018 onwards for all the Country Office audits captured in [CARDS](https://cards.undp.org/) and published on the [Audit Public Disclosure website. ](https://audit-public-disclosure.undp.org/)We showcase the rating from the latest country office audit, as some country offices may have had multiple audits during that period.

There are four main possible audit ratings:

* Fully Satisfactory
* Minor Improvements
* Major Improvements
* Unsatisfactory

The underlying data has more categories, but we have mapped it as follows:

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

An audit will result in a set of recommendations that are tracked in a system called CARDS, managed by OAI. The Country Office is responsible for implementing these recommendations and providing status updates via CARDS within specific timeframes. Once the updates are provided, OAI evaluates them to confirm whether the recommendations have been implemented.

The recommendations are flagged according to the following traffic-light methodology based on OAI's assessment of the implementation status:&#x20;

| Time Frame   | Status       | Indicator Color |
| ------------ | ------------ | --------------- |
| 0-12 months  | Great        | Green           |
| 12-18 months | Acceptable   | Yellow          |
| 18+ months   | Unacceptable | Red             |

## Organisational Objective

The organisational objective is the best audit performance possible, with no unsatisfactory audits and maximising entirely satisfactory audits. Additionally, the fastest and comprehensive implementation of the audit recommendations.&#x20;

## Data

{% hint style="warning" %}
Check that we are not missing the field here for the actual main result of the audit
{% endhint %}

| Field                       | Description                                                                                |
| --------------------------- | ------------------------------------------------------------------------------------------ |
| as\_of\_date                | Date of data extraction or last update.                                                    |
| audit\_categ                | Category or type of audit (e.g., OAI - Office of Audit and Investigations).                |
| audited\_bureau             | Bureau or regional office audited (e.g., RBAS - Regional Bureau for Arab States).          |
| audited\_org\_id\_c         | Unique identifier for the audited organization.                                            |
| audited\_cty\_code          | ISO 3166-1 alpha-3 country code (e.g., MAR - Morocco).                                     |
| audited\_unit\_desc         | Description of the audited unit.                                                           |
| action\_bureau              | Bureau responsible for audit action.                                                       |
| action\_org\_id\_c          | Identifier for the action organization.                                                    |
| action\_cty\_code           | Country code for the action location.                                                      |
| action\_unit\_desc          | Description of the action unit.                                                            |
| action\_responsible\_person | Name or title of the responsible person.                                                   |
| audit\_id                   | Unique audit identifier.                                                                   |
| audit\_title                | Title of the audit.                                                                        |
| audit\_period\_start        | Start date of the audit period.                                                            |
| audit\_period\_end          | End date of the audit period.                                                              |
| audit\_issue\_date          | Date when the audit report was issued.                                                     |
| audit\_type                 | Type of audit conducted (e.g., COA - Country Office Audit).                                |
| reco\_no                    | Number of the recommendation.                                                              |
| recom\_id                   | Unique recommendation identifier.                                                          |
| reco\_title                 | Title or summary of the recommendation.                                                    |
| reco\_descr                 | Detailed recommendation description.                                                       |
| reco\_planned\_imnpl\_d     | Planned implementation date for the recommendation.                                        |
| reco\_priority              | Priority level (e.g., High, Medium, Low).                                                  |
| reco\_oai\_status           | Status of the recommendation (e.g., Implemented, In Progress, Not Implemented, Withdrawn). |
| reco\_open                  | Binary indicator of recommendation status (0 = closed, 1 = open).                          |
| sub\_domain                 | Specific organizational domain (e.g., SRF - Strategic Results Framework).                  |

## Data Export

{% hint style="danger" %}
Requires definition
{% endhint %}

## Calculation of Scoring

We score only using each country's latest CO audit reports. Previous historical audit ratings are shown in the indicator drill down but are not considered in the scoring methodology.

For each audit result, we assign the following scores:

| Audit Result                                      | Score |
| ------------------------------------------------- | ----- |
| Fully Satisfactory                                | 100   |
| Satisfactory / Some Improvement Needed            | 80    |
| Partially Satisfactory / Major Improvement Needed | 60    |
| Unsatisfactory                                    | 0     |

Unsatisfactory is rated as zero. We want to significantly reduce the aggregate scores if even a small number of country offices in a region have Unsatisfactory audit ratings because these are so important to the organisation.

For Regional Bureau aggregation, we take an average of all the scoring, and the global average is calculated as an average of all country scores, not as an average of the Regional Bureau aggregation. This is to avoid skewed results, as different Regional Bureaus have different numbers of country offices. No weight is attached to country population size, amount of programming, or office size/budget.

## Traffic Light System

| Traffic Light | Score |
| ------------- | ----- |
| Green         | 80+   |
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
