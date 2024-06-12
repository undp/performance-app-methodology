# Pipeline

<table data-header-hidden><thead><tr><th width="289"></th><th></th></tr></thead><tbody><tr><td>Data Owner</td><td>John Cambiotis (<a href="mailto:john.cambiotis@undp.org">john.cambiotis@undp.org</a>), BERA</td></tr><tr><td>Availability in Data Warehouse</td><td>Available</td></tr><tr><td>Data Refresh Rate</td><td>Daily</td></tr><tr><td>Accountability Weighted Scoring</td><td>TBD</td></tr></tbody></table>

{% hint style="info" %}
This is a draft proposal for a new indicator.&#x20;
{% endhint %}

## Introduction

The pipeline indicator measures the health of the number and value of all the signed agreements and potential agreements. This is perhaps the most critical indicator for financial sustainability at UNDP because it dictates the future resources available for mobilization in projects, programmes, and portfolios for years to come. 

The data for this comes from Unity which is part of Quantum+ (i.e. Salesforce).

When an opportunity is created, it typically goes through various different pipeline stages. 

1. **Pipeline C (Ideas):** This 
2. **Pipeline B (Soft Pipeline):**
3. **Pipeline A (Hard Pipeline):**
4. **Signed Agreement:** 

Each pipeline stage has a discount as shown in this table:

| Pipeline Stage  | Discount |
| --------------- | ----- |
| C           | 70%   |
| B          | 40%   |
| A          | 10%   |
| Signed             | 0%   |


This discount applies to the total value of the agreement and the tranches (i.e. payments that will be made from donors to UNDP) when calculating the potential future cash flows arising from the opportunity. Because the discounts are based on historical close rates of opportunities across UNDP, this provides a realistic picture of the likely amount of resources available to UNDP based on the current snapshot of the health of the pipeline.


## Organisational Objective

The organizational objective is to, at a minimum, replenish delivery in future years, accounting for inflation. The ideal scenario is the total value of the pipeline is growing month on month to support the growth in contributions and delivery.


## Data

The columns from the Data Warehouse are the following:

* **Department**: The organizational unit or office within the company or agency.
* **Opportunity Record Type**: The type of opportunity, such as funding, partnership, etc.
* **Opportunity Name**: The name or title of the opportunity.
* **Organisation Name**: The name of the organization offering or involved in the opportunity.
* **Opportunity Owner**: The person responsible for managing or overseeing the opportunity.
* **Initial Stage**: The initial stage or status of the opportunity when it was first recorded.
* **Stage**: The current stage or status of the opportunity.
* **Close Date**: The projected or actual closing date of the opportunity.
* **Description**: A brief description of the opportunity.
* **Funding Stream**: The source of funding or type of financial support for the opportunity.
* **Opportunity Currency**: The currency in which the opportunity's financials are denoted.
* **Total Target Funding (OR)**: The total target funding amount for the opportunity.
* **Implementation Period**: The timeframe over which the opportunity is to be implemented.
* **YR2022** to **YR2027**: Yearly breakdown of expected tranche payments
* **Status**: The current status of the opportunity, such as active, closed, etc.
* **Details/Status**: Additional details or updates on the current status of the opportunity.
* **Next Step**: The next steps or actions required for the opportunity.
* **Last Note/Status**: The most recent note or update on the opportunity's status.
* **Thematic Team**: The team or thematic area associated with the opportunity.
* **Topic List\_255**: A list of topics or areas of focus related to the opportunity.
* **External Partner Contacts**: Contacts at external partner organizations involved in the opportunity.
* **Implementing Partners**: The organizations responsible for implementing the opportunity.
* **Responsible Parties**: The parties or individuals responsible for various aspects of the opportunity.
* **Target Countries**: The countries targeted by the opportunity.
* **Created Date**: The date when the opportunity record was created.
* **Created By**: The individual who created the opportunity record.
* **Last Modified Date**: The date when the opportunity record was last modified.
* **Last Modified By**: The individual who last modified the opportunity record.


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
| Green         | 85+   |
| Yellow        | 70+   |
| Red           | <70   |

