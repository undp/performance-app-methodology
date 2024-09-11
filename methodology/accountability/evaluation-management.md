# Evaluation Management

| Data Owner                      | Anish Pradhan   |
| ------------------------------- | --------------- |
| Availability in Data Warehouse  | Partial         |
| Data Refresh Rate               | Daily           |
| Accountability Weighted Scoring | Not Yet Defined |

## Introduction&#x20;

This indicator takes information from the ERC (Evaluation Resource Center) to measure the performance in managing evaluation, including the timely conduct of evaluations, the completion and implementation of management responses, and the quality of decentralised evaluations.&#x20;

This is both a Global, Regional, and Country Office level indicator.&#x20;

## Organisational Objective

The organisational objective can be broken down into three parts:

1. 100% of  planned evaluations were completed on time.
2. 100% of completed evaluations have management responses with no overdue key actions.&#x20;
3. 100% of evaluations are of acceptable quality.&#x20;

## Notes



* We exclude UNV, UNCDF, UNOSSC
*



## Calculation of Scoring

The Evaluation Management Indicator is comprehensively divided into three distinct components, each aligned with a specific organizational objective. These components are as follows:

1. **Evaluation Planning:** This part assesses the efficiency and timeliness of the evaluation scheduling process, ensuring that evaluations are completed as planned.
2. **Evaluation Management Responses:** This section measures the promptness and effectiveness of management in responding to the evaluations conducted, emphasizing the importance of timely action on feedback and recommendations.
3. **Evaluation Quality:** The final component evaluates the overall quality of the evaluations themselves, focusing on the depth, accuracy, and usefulness of the findings and conclusions drawn.

These components provide a holistic view of an organization's evaluation management capabilities, reflecting its commitment to continuous improvement and accountability.

### **Part 1: Evaluation Planning (30% weight)**

This focuses on the punctuality and scheduling discipline of the evaluation process, specifically measuring the percentage of evaluations completed within their designated timeframes. This assesses the effectiveness of evaluation planning and execution at the Country Office level.

* Non-Overdue Evaluations / Total Evaluations = **% of On-Time Evaluations**

{% hint style="info" %}
Speak with Evaluation team on this, as what is "Completed" precisely?&#x20;
{% endhint %}

**Example below:**

So this is a snapshot of Global, so in this case, it would be 2113/2176

The reason it is 2113, is because there are 2176 total evaluation, and 63 overdue, so that gives us 2113 non-overdue planned evaluation, which is \~97%&#x20;

<figure><img src="../../.gitbook/assets/CleanShot 2024-07-10 at 13.42.58@2x.png" alt=""><figcaption></figcaption></figure>

#### Statuses

* **Planned:** Not started yet
* **Initiated ToR:** The ToR is now being written
* **Team Onboard:** Consultants have been hired
* **Completed:** Evaluation has been completed

An evaluation can only have one status at a time.&#x20;

Potential change to % overdue calculation

We have to make it clear that we are counting overdue % of ACTIVE evaluatuations which is overdue+planned+iniatedTOR+Team Onboard



### **Part 2: Evaluation Management Responses (30% weight)**

#### A) % Evaluations without a management response 6+ weeks after evaluation (50% of Part 2)

This component evaluates the proportion of evaluations lacking a management response more than six weeks after completion. It is a key indicator of the efficiency and timeliness with which management acts on evaluation findings.

The formula used is:

* 1 - (Number of Evaluations Overdue by More Than 6 Weeks / Total Completed Evaluations in the Programme Period) = **Percentage of Evaluations with a Management Response**

{% hint style="info" %}
**Clarification note:** This part of the scoring methodology is intended to highlight evaluations with overdue management response so that corrective action can be taken. Once a management response is submitted, even if overdue, it is no longer counted as overdue.&#x20;
{% endhint %}

Example from ERC Dashboard:

There are a total of 1924 Reports, with 89 being overdue for more than 6 weeks.

Total completed evaluation in the programme period = All Reports - Waiting for Management Response.

So the calculation:

**1-(89/(1924-122)) = 95.06%**

<figure><img src="../../.gitbook/assets/CleanShot 2024-07-10 at 13.44.23@2x.png" alt=""><figcaption></figcaption></figure>

#### B) Key actions timings (50% of Part 2)

Within Part 2B, the following two metrics each contribute 50% by averaging their scores:

* Non-Overdue Key Actions / Total Actions = **Percentage of Actions Not Overdue**
* Not Long-Overdue Key Action / Total Actions = **Percentage of Actions Not Long Overdue**

{% hint style="danger" %}
**Important Note 1:** Long Overdue Key Actions are intentionally double-counted in this section to underscore their significance in the evaluation process. This approach highlights the critical importance of addressing long overdue actions promptly, reflecting their heightened impact on overall performance assessment.
{% endhint %}

{% hint style="danger" %}
**Important Note 2:** "Total Actions" include ALL key actions, including overdue, completed, and not yet due.&#x20;
{% endhint %}

**Example for part 1 of 2B:**

<figure><img src="../../.gitbook/assets/CleanShot 2024-07-10 at 13.47.55@2x.png" alt=""><figcaption></figcaption></figure>

**Total =** Total in the screenshot above from ERC

**Percentage of Actions Not Overdue =** 100-Overdue % in Screenshot Above &#x20;

{% hint style="danger" %}
Further discussions are required here about cut-off dates, and including and not including "No Longer Applicable" — this can be ignored.

Same consideration as Part 1, we can not include Completed.\
\
One other consideration: ignoring "Completed" and "No Longer Applicable" because this will keep growing the denominator.\
\
Instead, on the above is should be:

Overdue / (Overdue+Not Initiated + Initiated) = % Overdue

\
This needs to be confirmed with IEO.
{% endhint %}

**Example for part 2 of 2B:**

<figure><img src="../../.gitbook/assets/CleanShot 2024-07-10 at 13.59.58@2x.png" alt=""><figcaption></figcaption></figure>

In this case, Long Overdue % would be 1 divided by Open Actions (Overdue+Not Initiated + Initiated)&#x20;

note: It may also be interesting to note how many recommendations have no key actions.&#x20;

### **Part 3: Evaluation Quality (40% Weight)**&#x20;

This section determines the overall quality of evaluations based on a comprehensive scoring system. Evaluation quality is critical, reflecting the evaluation's depth, accuracy, and usefulness.&#x20;

{% hint style="info" %}
The quality rating is _**not**_ the quality of the project, it is the quality of _**how**_ the evaluation was conducted.&#x20;
{% endhint %}

Six distinct scores are possible, each reflecting a specific level of evaluation quality. These scores are predetermined and assigned based on established criteria that evaluate various aspects of the evaluation process and its outcomes.

{% hint style="info" %}
There are several different categories that make up the quality level.
{% endhint %}

| Quality Level             | Scores |
| ------------------------- | ------ |
| High Satisfactory         | 100    |
| Satisfactory              | 90     |
| Moderately Satisfactory   | 80     |
| Moderately Unsatisfactory | 70     |
| Unsatisfactory            | 60     |
| Highly Unsatisfactory     | 50     |

This is where it is shown in the ERC Dashboard:

<figure><img src="../../.gitbook/assets/CleanShot 2024-07-10 at 14.03.27@2x.png" alt=""><figcaption></figcaption></figure>

The final quality score is derived by calculating the assigned scores' straight average across all programme period evaluations in the 2022, 2023, and 2024. For each new calendar, we drop the previous calendar year. This average score provides a clear, quantitative measure of the overall quality of evaluations.

### **Overall Calculation**

* **Part 1:** This section's score is derived directly from the Evaluation Planning performance.
* **Part 2:** The score for this section is calculated as the average of two components:
  * **A:** The percentage of evaluations that have received a management response.
  * **B:** The average of two metrics: the percentage of actions not overdue and the percentage of actions not long overdue.
* **Part 3:** This score comes from the Evaluation Quality assessment.
* **Final Score Calculation:** The final score combines these parts, weighted accordingly:
  * Part 1 contributes 30%.
  * Part 2 contributes 30%.
  * Part 3 contributes 40%.

The formula for the final score calculation is:&#x20;

* **Final Score = (Part 1 × 0.3) + (Part 2 × 0.3) + (Part 3 × 0.4)**.

This calculation method ensures that each aspect of the evaluation process—planning, management response, and quality—is appropriately considered in the overall performance score.

The traffic light indicator methodology for this indicator is:

* Green = 90+
* Yellow = 80+
* Red = <80



## Useful Links

* [ERC Dashboard](https://erc.undp.org/login?redirectUrl=https://erc.undp.org/oversight/dashboard)
* [IEO Method Center](https://erc.undp.org/methods-center/guidelines/undp-evaluation-guidelines/evaluation-assessment)
