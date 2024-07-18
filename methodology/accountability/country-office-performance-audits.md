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

This is the draft for the new audit indicator that considers not only Country Office Performance Audits, but also project audits and open management recommendations:

### Part 1: Country Office Performance Audit (50% by default)

* Last CO Performance Audit \


How do we determine the overall weight of Part 1?

* 0-2 years: 50% weight
* 2+ years: 40% weight
* 3+ years: 30% weight
* 4+ years: 20% weight

{% hint style="info" %}
Note that the years are based on the issue date of the audit and is recalculated daily
{% endhint %}

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

### Part 2: Project Audits  (70% of \[Indicator minus Part 1])

Let's start with some definitions:

* **DIM/DEX —** Direct Implementation Modality, this is where UNDP is the implementor.
* **NIM —** National Implementation Modality, this is where the Government is the implementor.&#x20;
* **NGO/Other —** Non-Governmental Organization, IFIs (International Financial Institutions) or another UN Agency.&#x20;

These can be further broken down as

* DIM/DEX
* NIM (non-HACT)
* NIM (HACT & Not Using National Auditors)
* NGO/Other (non-HACT)
* NGO/Other (HACT)

{% hint style="info" %}
**What is Harmonized Approach to Cash Transfers (HACT)?**

The Harmonized Approach to Cash Transfers (HACT) is a framework designed to streamline and enhance the management of cash transfers within development programs. It emphasizes the assessment of the technical, managerial, administrative, and financial capacities of implementing partners before engagement. These capacity assessments are crucial as they determine the overall risk level associated with each partner and help identify the most suitable cash transfer modality for them.

HACT offers three distinct cash transfer modalities.&#x20;



1. The first is Direct Cash Transfers, where the United Nations Development Programme (UNDP) advances cash funds to the implementing partner (IP), who then reports back on their expenses.&#x20;
2. The second modality is Direct Payments, in which UNDP makes payments directly to vendors on behalf of the IP.&#x20;
3. The third option is Reimbursement, where UNDP reimburses the IP after they have made their disbursements. Each modality is chosen based on the results of the capacity assessment, ensuring that the method aligns with the partner’s ability to manage funds effectively.

In addition to capacity assessments, HACT requires various assurance activities tailored to the partner's risk level. These activities include micro-assessments to evaluate the financial management capacity of the partner, spot checks to verify the accuracy of their financial records, and audits to review their financial records and internal controls. These assurance activities are integral to maintaining transparency and accountability in the management of cash transfers, ensuring that funds are used appropriately and effectively.
{% endhint %}

#### Qualified vs Unqualified Audit Opinions

All project audits will have one to three Qualified/Unqualified audit opinions:

1. **CDR (Combined Delivery Report):** All project audits will have this. Auditors do not review 100% of financial statements, and they look for financial misstatements.&#x20;
2. **Assets:** Evaluates the value and condition of physical assets.
3. **Cash on hand:** Assesses the actual cash available with the implementing partner at the time of the audit.

In the Performance App, we only consider point 1, the financial statement from the CDR (Combined Delivery Report , due to the potential duplication across the three categories. &#x20;

Some project audits will _also_ have a audit rating as well, this is displayed in the Performance App but does not affect the scoring of this indicator.&#x20;

{% hint style="info" %}
**On Audit Opinions**

**Unqualified (Favorable) Audit Opinion**

An unqualified or "clean" audit opinion means that the auditor concludes that the financial statements give a true and fair view or are presented fairly, in all material respects, in accordance with the applicable financial reporting framework (e.g. UNDP requirements).

**Key points about unqualified opinions:**

* Indicates the financial statements are free of material misstatements.
* The auditor has obtained sufficient appropriate audit evidence to support this conclusion.
* This is considered a favorable or "clean" audit opinion.

**Qualified (Unfavorable) Audit Opinion**

A qualified opinion should be expressed when the auditor concludes that an unqualified opinion cannot be expressed, but the effect of any disagreement with management or limitation on scope is not so material and pervasive as to require an adverse opinion or a disclaimer of opinion.

**Key points about qualified opinions:**

* The auditor found some issues or limitations that prevent them from giving a fully clean opinion.
* The issues are not severe enough to warrant an adverse or disclaimer of opinion.
* The audit report must describe the nature and amount of the possible effects on the financial statements (the "Net Financial Impact").

Other types of opinions that can be issued, but are less common, are:

* Adverse opinion: The auditor concludes that the financial statements are materially misstated and do not give a true and fair view.
* Disclaimer of opinion: The auditor is unable to obtain sufficient appropriate audit evidence to provide a basis for an audit opinion.
{% endhint %}

#### Calculation of Scoring

{% hint style="info" %}
We get this from the "Reports" tab in Cards: OAIHACT Audits - R3000-Net Financial Misstatement for HACT Audits, and then the Non-HACT project audits will be from the export of the regular audit section in CARDS.&#x20;
{% endhint %}

{% hint style="danger" %}
For HACT Audits, we will use the previous FY (Financial Year) reports for this only. This data set is updated once per year, around June. For Non-HACT Audits, these are closer to real time as the audit are published.&#x20;
{% endhint %}

Sum of all $ amount of Qualified Reports = "**Total Financial Misstatement |Absolute Value|"** in the above report

Confirmed that **Audited Expenditure** is the _Total_ audited expenditure for that project, inclusive of financial misstatement.&#x20;

$TotalReports = **"Audited Expenditure"** in the above report

{% hint style="info" %}
We need to confirm with OAI if Audited Expenditure is indeed the Total Amount, or we had to add Audited Expenditure + Total Financial Misstatement
{% endhint %}

The OAI Datasets includes a % calculation called **"% NFM CY to Audited"**

So for this part of the indicator, we get the weighted average.&#x20;

So it **SUM of Total Financial Misstatement / Sum of Audited Expenditure**

We take the "**% NFM CY to Audited"** and multiply 20 to get the Indicator Adjustment Score.

100 - Indicator Adjustment Score = Indicator Score

### Part 3: Long Outstanding Audit Recommendations ≥18 months (30% of Indicator minus Part 1)

This is calculated from the Audit Issue date fro any Outstanding Audit Recommendations that are "open"

| Aged ≥18 Months | Points |
| --------------- | ------ |
| 0               | 100    |
| 1               | 60     |
| 1+              | 30     |

We take the Audit Issue date and then calculate as of today. We count anything with "Yes" in the below table as Open, and then calculate the age etc..&#x20;

The field is **reco\_oai\_status**: Status of the recommendation (e.g., Implemented, In Progress, Not Implemented, Withdrawn).

{% hint style="danger" %}
Where are the UNOBA Country Audits? They are not uploaded in CARDS, only ten years ago. Can they go into CARDS?
{% endhint %}

| OAI Recommendation Status | Definition                                                                                    | Count as Open? |
| ------------------------- | --------------------------------------------------------------------------------------------- | -------------- |
| Implemented               | This is done to a satisfactory level                                                          | No             |
| In Progress               | Country Office is working on the recommendation actions.                                      | **Yes**        |
| Not Implemented           | This is the default status. So the Country Office has not updated the status as "In Progress" | **Yes**        |
| Withdrawn                 | OAI has decided to withdraw this, because the recommendation is no longer applicable          | No             |
| N/A                       | Not Applicable.                                                                               | No             |
