# Country Office Performance Audits

* Data owner: Narayanan Chettiar ([narayanan.chettiar@undp.org](mailto:narayanan.chettiar@undp.org))&#x20;
* Availability in Data Warehouse: Available&#x20;
* Data Refresh Rate: Daily&#x20;
* Contribution to Accountability Overall Score: 30%

## Introduction

Country Office Audits are audits performed by [OAI (Office of Audit and Investigations)](https://www.undp.org/accountability/audit-and-investigations). They measure compliance with corporate rules and regulations. The Performance App takes data from 2018 onwards for all the Country Office audits published on the [Audit Public Disclosure website. ](https://audit-public-disclosure.undp.org/)We showcase the rating from the latest country office audit, as some country offices may have had multiple audits during that period.&#x20;

There are four main possible audit ratings:

* Fully Satisfactory
* Minor Improvements
* Major Improvements
* Unsatisfactory

The underlying data has more categories, but we have mapped it as follows:\


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



An audit will require a set of management responses that are then tracked in a system called [CARDS](https://cards.undp.org/), managed by OAI. The Country Office needs to implement these responses within specific timeframes and flag them according to the traffic light methodology.&#x20;

* 0-12 months — Great (Green)
* 12-18 months — Acceptable (Yellow)
* 18+ months — Unacceptable (Red)\


## Organisational Objective



The organisational objective is the best audit performance possible, with no unsatisfactory audits and maximising entirely satisfactory audits.&#x20;

## Calculation of Scoring

We score only using each country's latest CO audit reports. Previous historical audit ratings are shown in the indicator drill down, but are not considered in the scoring methodology.&#x20;

\
For each audit result, we assign the following scores:

* Fully Satisfactory = 100
* Satisfactory / Some Improvement Needed = 80
* Partially Satisfactory / Major Improvement Needed = 60
* Unsatisfactory = 0

Unsatisfactory is rated as zero. We want to significantly reduce the aggregate scores if even a small number of country offices in a region have Unsatisfactory audit ratings because these are so important to the organisation.&#x20;

For Regional Bureau aggregation, we simply take an average of all the scoring, and the global average is calculated as an average of all country scores, not as an average of the Regional Bureau aggregation. This is to avoid skewed results, as different Regional Bureaus have different numbers of country offices. No weight is attached to country population size, amount of programming, or office size/budget.

The traffic light indicator methodology for this indicator is:

* Green = 85+
* Yellow = 70+
* Red = <70&#x20;

## Drill-down Information&#x20;

As with most other indicators, the drill-down functionality for Country Office Audits is designed to enable management to review pockets of low performance instead of just seeing aggregate data that may hide essential information.&#x20;

It also helps units to assess their performance at addressing and clearing commitments made in audit management responses, from OAI’s CO audits, thematic audits, as well as UNBOA audits.

The drill-down includes the number of positive audit ratings (Satisfactory & minor Improvements) per Regional Bureau, highlighting significant differences in Regional Bureau performance.&#x20;



## Open Management Issues

* We ignore audits that were issued before the last 3 years (audit\_issue\_date)
* Audit IDs are not correct at the moment

## Useful Links

* [Public Audit Disclosure Website](https://audit-public-disclosure.undp.org/)

## Limitations & Future Improvements &#x20;

* Not incorporating country size, budget, programming amount, and other key details into weightings could fail to account for larger country offices' naturally higher complexity and risk exposure. Weightings may better reflect performance. An office with many projects and budgets receiving an Unsatisfactory audit rating is far more important to the organization than a smaller office receiving an Unsatisfactory audit rating — but this is currently not reflected in the methodology.&#x20;
* Looking only at the latest audit per country loses historical context. Incorporating a rolling 3-5-year average could smooth out anomalies and show improvement/regression over time.
* No qualitative context is provided on why audits scored the way they did or what actions are being taken. Incorporating audit insights could make the data more meaningful.
* We do not take into account the management responses in the scoring methodology, but we do show it in the drill-down
