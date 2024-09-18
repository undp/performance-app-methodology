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
| Signed         | 0%              | 100%              |



This discount applies to the total value of the agreement and the tranches (i.e. payments that will be made from donors to UNDP each year if the agreement is signed) when calculating the potential future cash flows arising from the opportunity. Based on a historical analysis of close rates, we also have "actual" discounts for each pipeline stage that offer a more realistic picture of the likely amount of resources available to UNDP based on the current snapshot of the health of the pipeline. In the future, the policy discounts should be updated to the actual discounts as they become more accurate over time.

The actuals will be updated at the start of each year in conjunction with the Unity team. 


## Organisational Objective

The organizational objective is, at a minimum, to replenish delivery in future years, accounting for inflation. The ideal scenario is the total value of the pipeline is growing month on month to support the growth in contributions and delivery in future years. 


## Data

The columns from the Data Warehouse are the following:

* **Department**: The organizational unit or office within the company or agency.
* **Opportunity Record Type**: The type of opportunity, such as funding, non-funding, exploratory. 
* **Opportunity Name**: The name or title of the opportunity.
* **Organisation Name**: The name of the organization offering or involved in the opportunity.
* **Opportunity Owner**: The person responsible for managing or overseeing the opportunity.
* **Initial Stage**: The initial stage or status of the opportunity when it was first recorded.
* **Stage**: The current stage or status of the opportunity.
* **Close Date**: The projected or actual signature date of the financial agreement.
* **Description**: A brief description of the opportunity.
* **Funding Stream**: The source of funding or type of financial support for the opportunity.
* **Opportunity Currency**: The currency in which the opportunity's financials are denoted.
* **Total Target Funding (OR)**: The total target funding amount for the opportunity. This is non-discounted and non-core (i.e. no TRAC funds are included here)
* **Implementation Period**: The timeframe over which the opportunity is to be implemented. Note, this is based on the tranche payments, the actual project end date could be different. 
* **YR2022** to **YR2030**: Yearly breakdown of expected tranche payments. Each year, we add another future year. 
* **Status**: The current status of the opportunity, such as prodoc being developed, no clear donor prospect, etc. These are more detailed than the pipeline stage, but do not effect the calculation of the pipeline. 
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


## Methodology

The organizational objective is, at a minimum, to replenish delivery in future years, accounting for inflation. The ideal scenario is the total value of the pipeline is growing month on month to support the growth in contributions and delivery in future years. 


- Active pipeline size compared to delivery/contributions (average of 3-5 years) to ensure that we "right size" the pipeline. 
- We want to incentivize capturing opportuniesi at an early stage becuase helps with forecasting resource mobilization and transparency and partner intelligence. If the organization knows at an early stage, thsi can help cross-country collaboration with donors, whcih plays into the strength UNDP that we have a strong country presence everywhere! We want to reward Cos that report opporunities at an early stage. So this means something around a % of opporunities closed that were created in Pipeline C. 
- Something around growing the average project size? Something like the average opportunity in the last 3 years, and then compare the snapshot of today vs that and there is score if its above or below. 
- Something around outdated opportunities. If the close date is in the past, then that is an outdated opportunity. One consideration here is that we exlcude these from the pipeline, COs may consider that there is a bug. 
- Something about not having captured any opportunities in the last 3 months. This could be a proxy for not having a pipeline. Need to discuss how many shoudl trigger an alert and how many months. So right now with 179 business units collect their pipelines, and we hav a steady 400-500 opporunities per month. So there are around ~3 opportunities per business unit per month. So if we say if there are less than 2 opportunities per business unit per 2 months, then we should trigger an alert and perhaps score the indicator as 0 (this may be too harsh but worth discussing!)

We should also consider if the future close date is too far off. If pipeline A has a closed date that is above 12 months, we should consider that this is really not a pipeline A and should be a pipeline B. Likewise with pipeline B having a closed date above 18 months, we should consider that this is really not a pipeline B and should be a pipeline C. We should not consider Pipeline C have a close date in 1 month. 


## Data Export

## Calculation of Scoring


1. For Opportunity Record Type, filter to show only "Funding"
2. For Stage, filter to show only the following:
   * C- Ideas (30%)
   * B-Soft Pipe Line (50-70%)
   * A-Hard Pipeline (90%)
   * Agreement Signed (100%)



## Traffic Light System

This is yet to be defined for this indicator, below is just a placeholder. 

| Traffic Light | Score |
| ------------- | ----- |
| Green         | 90+   |
| Yellow        | 75+   |
| Red           | <75   |


## Limitations 

- The system does not count central bureau opportunities correctly if the funds are allocated to multiple departments (i.e. typically country offices or HQ departments). Unity team is working on a feature to fix this by introducing a parent-subsidiary relationships for opportunities. 



## Resources

- Unity Platform
- [Pipeline Policy Guide](https://view.officeapps.live.com/op/embed.aspx?src=https://popp.undp.org/sites/g/files/zskgke421/files/2023-09/FRM_Pipeline%20Management_Guidelines.docx)
