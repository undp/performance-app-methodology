# Pipeline

<table data-header-hidden><thead><tr><th width="289"></th><th></th></tr></thead><tbody><tr><td>Data Owner</td><td>John Cambiotis (<a href="mailto:john.cambiotis@undp.org">john.cambiotis@undp.org</a>), BERA</td></tr><tr><td>Availability in Data Warehouse</td><td>Available</td></tr><tr><td>Data Refresh Rate</td><td>Daily</td></tr><tr><td>Accountability Weighted Scoring</td><td>TBD</td></tr></tbody></table>

{% hint style="info" %}
This is a draft proposal for a new indicator.
{% endhint %}

## Introduction

The pipeline indicator measures the health of the number and value of all the potential agreements. This is perhaps the most critical indicator for financial sustainability at UNDP because it dictates the future resources available for mobilization in projects, programmes, and portfolios for years to come. 

The data for this comes from Unity which is part of Quantum+ (i.e. Salesforce). All Country Offices (COs) and Central Bureaus (CBs) use Unity to log new opportunities and update the pipeline stage as opportunities progress. 

When an opportunity is created, it typically goes through various different pipeline stages. 

1. **Pipeline C (Ideas):** This is a speculative opportunity that is not yet ready to be considered for funding. Typically will not result in a project within the next 12 months. 
2. **Pipeline B (Soft Pipeline):** This is an opportunity that is ready to be considered for funding, but the funding is not yet guaranteed. Should be closing in the next 12 months. 
3. **Pipeline A (Hard Pipeline):** This is an opportunity that is under active negotiation and is likely to be signed soon. Should be closed in the next 6 months. 
4. **Signed Agreement:** This is an opportunity that has been signed and is now an actual agreement.

Each pipeline stage has a discount as shown in this table:

| Pipeline Stage | Policy Discount | Actual Discounts |
| -------------- | --------------- | ----------------- |
| C              | 70%             | 80%               |
| B              | 40%             | 60%               |
| A              | 10%             | 35%               |
| Signed         | 0%              | 0%              |



This discount applies to the total value of the agreement and the tranches (i.e. payments that will be made from donors to UNDP each year if the agreement is signed) when calculating the potential future cash flows arising from the opportunity. Based on a historical analysis of close rates, we also have "actual" discounts for each pipeline stage that offer a more realistic picture of the likely amount of resources available to UNDP based on the current snapshot of the health of the pipeline. In the future, the policy discounts should be updated to the actual discounts as they become more accurate over time.

**The Performance App will use the actual discounts to calculate the pipeline indicator.**

The actuals will be updated at the start of each year in conjunction with the Unity team. 


## Organisational Objective

The organizational objective is, at a minimum, to replenish delivery in future years, accounting for inflation. The ideal scenario is the total value of the pipeline is growing month on month to support the growth in contributions and delivery in future years. 


## Data

Table names in UNDP Data Warehouse:

- [Insert here later]

The columns from the Data Warehouse are the following:

* **Department**: The organizational unit or office within UNDP.
* **Opportunity Record Type**: The type of opportunity, such as funding, non-funding, exploratory. 
* **Opportunity Name**: The name or title of the opportunity.
* **Organisation Name**: The name of the organization offering or involved in the opportunity.
* **Opportunity Owner**: The person responsible for managing or overseeing the opportunity.
* **Initial Stage**: The initial stage (A/B/C) of the opportunity when it was first recorded.
* **Stage**: The current stage (A/B/C/Signed) of the opportunity.
* **Close Date**: The projected or actual signature date of the financial agreement.
* **Description**: A brief description of the opportunity.
* **Funding Stream**: The source of funding or type of financial support for the opportunity.
* **Opportunity Currency**: The currency in which the opportunity's financials are denoted.
* **Total Target Funding (OR)**: The total target funding amount for the opportunity. This is non-discounted and non-core (i.e. no TRAC funds are included here)
* **Implementation Period**: The timeframe over which the opportunity is to be implemented. Note, this is based on the tranche payments, the actual project end date could be different. 
* **YR2022** to **YR2030**: Yearly breakdown of expected tranche payments. Each year, we add another future year. 
* **Status**: The current status of the opportunity, such as Prodoc being developed, no clear donor prospect, etc. These are more detailed than the pipeline stage, but do not affect the calculation of the pipeline. 
* **Details/Status**: Additional details or updates on the current status of the opportunity.
* **Next Step**: The next steps or actions required for the opportunity.
* **Last Note/Status**: The most recent note or update on the opportunity's status.
* **Thematic Team**: The team, cluster, or thematic area associated with the opportunity.
* **Topic List**: A list of topics or areas of focus related to the opportunity.
* **External Partner Contacts**: Contacts at external partner organizations involved in the opportunity.
* **Implementing Partners**: The organizations responsible for implementing the opportunity.
* **Responsible Parties**: The parties or individuals responsible for various aspects of the opportunity.
* **Target Countries**: The countries targeted by the opportunity.
* **Created Date**: The date when the opportunity record was created.
* **Created By**: The individual who created the opportunity record.
* **Last Modified Date**: The date when the opportunity record was last modified.
* **Last Modified By**: The individual who last modified the opportunity record.

## Data Export

## Methodology

The pipeline indicator is scored based on two main categories, each contributing to the final score:

1. **Pipeline Sizing**: Ensures the pipeline is adequately sized to meet future programme delivery and office financial sustainability goals.
2. **Pipeline Health**: Assesses the accuracy and active management of the pipeline within Unity. 

This approach provides a comprehensive view of both the pipeline's capacity to meet replenishment goals and its realistic representation of available opportunities.

### Part 1: Pipeline Sizing (70%)

Pipeline Sizing is calculated as the average of three components:

#### A) Active Pipeline Size (45%)
- Measures the total discounted value of all pipeline opportunities against average annual delivery.
- Target: 200% of annual delivery.

#### B) Total value of resources mobilized (45%)
- Calculates the total value of resources mobilized from signed opportunities YTD
- resources mobilized / delivery from previous year
- THis will have to be looked against the delivery trendline from previous year or target from this year. 
- Rate  = subindicator score 


#### C) Average Project Size (10%) 
- Compares the current average size of pipeline opportunities to the previous year's average
- Baseline is to grow the average (Houle: should be median) project size each year by 5% 
- idea: could not be 5%, but just positive score if its growing, negative score if its lower than last year average. 


### Part 2: Pipeline Health (30%)

Pipeline Health is assessed through three components:

#### A) Opportunity Age (40%)
- Measures the average age of opportunities in the pipeline.
- Older is worse. 

#### B) Opportunity Activity (40%)
- Calculates the percentage of opportunities updated within a specified recent period.
- % of opportunities updated in the last 3 months - % score of B

#### C) Early Stage Capture Rate (20%)
- Measures the percentage of signed opportunities that were initially created in Pipeline C.
- This could also be gamed by moving it to Pipeline C and then quickly moving it to Pipeline B, then pipeline A, then signed. How do we prevent this gaming? 
- Encourages early capture of opportunities to improve forecasting and cross-country collaboration.

 

### **Overall Calculation**

* **Part 1: Pipeline Sizing (70%)**
  * **A:** Active Pipeline Size (45%)
  * **B:** Total Value of Resources Mobilized (45%)
  * **C:** Average Project Size (10%)

* **Part 2: Pipeline Health (30%)**
  * **A:** Opportunity Age (40%)
  * **B:** Opportunity Activity (40%)
  * **C:** Early Stage Capture Rate (20%)

* **Final Score Calculation:** The final score combines these parts, weighted accordingly:
  * Part 1 contributes 70%.
  * Part 2 contributes 30%.

Each part's score is calculated by averaging its subcomponents (A, B, C) based on their individual weights. The final score is then determined by combining Part 1 (70%) and Part 2 (30%).



## Traffic Light System


| Traffic Light | Score |
| ------------- | ----- |
| Green         | 90+   |
| Yellow        | 75+   |
| Red           | <75   |



## Limitations 

- The system does not count Central Bureau opportunities correctly if the funds are allocated to multiple departments (i.e. typically country offices or HQ departments). Unity team is working on a feature to fix this by introducing a parent-subsidiary relationship for opportunities. 



## Resources

- Unity Platform
- [Pipeline Policy Guide](https://view.officeapps.live.com/op/embed.aspx?src=https://popp.undp.org/sites/g/files/zskgke421/files/2023-09/FRM_Pipeline%20Management_Guidelines.docx)


## Todo

### General
- Add table names in UNDP Data Warehouse
- Double check the data model with John
- Ask John when an agreement is signed, where do we get the total from? Target Funding (OR)	| Target Funding (RR) |	Expected Funding (OR)


### Part 1A
Confirm that 200% of annual delivery is a good target for active pipeline Size. The way we should do this is to take the 2023 Delivery data and the current pipeline discounted total for each Country Office and add another column for ratio. 

## Part 1B

- For each country, generate a linear trendline from 0 to the value of the 2023 delivery.
- If the delivery was $120M for 2023, you will make a linear trendline that grows by $10m each month. 
- Then we compare current signed agreement YTD for today, against the linear delivery trendline.
- If the RM is above the delivery trendline, the score 100/100 for this subindicator.
- If the RM is below the delivery trendline, the ratio is the score. 
  - Example: If the RM is $80M and the trendline is $100M, then the score is 80/100. 
- Another Example: It's April 1st 2024, so the delivery would show $30M (as 3 months have passed) but the RM is only $20M, then the score is ~67/100. 
- We recognize the entire project value at this point NOT the tranches. 

## Part 1C

- We calculate median opportunity size for previous calendar year
- We calculate median opportunity size for current calendar year (YTD)
- We use the non-discounted values from the pipeline.
- If this year is above last year, we score this 100/100
- If this year is below last year, the score is teh ratio between this year and last year. 
- So if last year was $1m median opportunity size, and this year it is $700,00 median opportunity size, then the score is 70/100 

### Part 2A

- We calculate the average age of opportunities in the pipeline using "Created Date" compared to today.

| Average Age (Months) | Score   |
|----------------------|---------|
| Below 6              | 100/100 |
| Below 12             | 75/100  |
| Below 18             | 50/100  |
| Above 18             | 25/100  |
| Above 24             | 0/100   |

### Part 2B

- % of opportunities updated in the last 30 days
- This equals the score of the subindicator. 

### Part 2C

- Percentage of opportunities created in Pipeline C that are signed YTD, which determines the score for this subindicator.
- Opportunities signed from Pipeline C within 14 days of creation are excluded from this percentage calculation.
- Example: If there are 10 opportunities created in Pipeline C that are signed YTD, and 10 from Pipelines A and B, the initial score would be 50%.
- However, if 5 of the 10 opportunities in Pipeline C were signed within 14 days, they are considered not properly added to Pipeline C.
- Therefore, we adjust the count to 5 opportunities in Pipeline C and 15 in Pipelines A, B, and Exempt, resulting in a revised score of 25%.


