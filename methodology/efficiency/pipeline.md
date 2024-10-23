# Pipeline

<table data-header-hidden><thead><tr><th width="289"></th><th></th></tr></thead><tbody><tr><td>Data Owner</td><td>John Cambiotis (<a href="mailto:john.cambiotis@undp.org">john.cambiotis@undp.org</a>), BERA</td></tr><tr><td>Availability in Data Warehouse</td><td>Available</td></tr><tr><td>Data Refresh Rate</td><td>Daily</td></tr><tr><td>Accountability Weighted Scoring</td><td>25%</td></tr></tbody></table>

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

There are actually more stages in the pipeline data, but we do not consider them all:

| Stage                                   | Used in Methodology? |
|-----------------------------------------|-----------------------|
| Agreement Signed (100%)                 | Yes                   |
| Withdrawn/Discontinued                  | No                    |
| C- Ideas (30%)                          | Yes                   |
| B-Soft Pipe Line (50-70%)              | Yes                   |
| A-Hard Pipeline (90%)                   | Yes                   |
| Exploratory Opportunity                  | No                    |
| Withdrawn                                | No                    |
| Agreement Signed / Engagement Achieved   | Yes                   |
| Initial Meetings                         | No                    |
| Negotiations / Contracting               | No                    |
| Formulation, Planning & Coordination     | No                    |
| Engagement Not Achieved                  | No                    |
| Proposal Development                     | No                    |

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

Table names in UNDP Data Warehouse: [SF_UNITY].[Opportunity]

The columns from the Data Warehouse are the following:

[This is to be cleaned up and then confirmed with John]

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
* **Id**
* **IsDeleted**
* **AccountId**
* **RecordTypeId**
* **IsPrivate**
* **Name**
* **StageName**
* **Amount**
* **Probability**
* **ExpectedRevenue**
* **TotalOpportunityQuantity**
* **Type**
* **LeadSource**
* **IsClosed**
* **IsWon**
* **ForecastCategory**
* **ForecastCategoryName**
* **CampaignId**
* **HasOpportunityLineItem**
* **Pricebook2Id**
* **OwnerId**
* **CreatedById**
* **LastModifiedById**
* **SystemModstamp**
* **LastActivityDate**
* **FiscalQuarter**
* **FiscalYear**
* **Fiscal**
* **ContactId**
* **LastViewedDate**
* **LastReferencedDate**
* **ContractId**
* **HasOpenActivity**
* **HasOverdueTask**
* **Account_Implementing_Partner__c**
* **Account_Responsible_Party__c**
* **CPD_Outcome_Primary__c**
* **CPD_Output_Primary__c**
* **Change_Opportunity_Type__c**
* **Closed_Reason_NonFunding__c**
* **Closed_Reason__c**
* **Create_a_New_Opportunity__c**
* **I_am_in_the_Owners_Initiative_Region__c**
* **I_am_in_the_Owners_Region__c**
* **Include_on_Funding_Pipeline__c**
* **Managing_Department__c**
* **Next_Opportunity_Review_Date__c**
* **Opp_Name_Text__c**
* **Opportunity_ID__c**
* **Opportunity_Lead_Name__c**
* **Partnership_Strategy__c**
* **Project_ID__c**
* **Project_Type__c**
* **Targeted_Countries__c**
* **Thematic_Area_Programmatic_Area__c**
* **Thematic_TeamV2__c**
* **UNDP_Signature_Solution__c**
* **Opportunity_Development_Total_Cost__c**
* **Target_Fund_Next_Year__c**
* **Target_Funding_Future_Years__c**
* **Total_Funding_This_Year__c**
* **Total_Target_Funding__c**
* **CPD_YR1__c**
* **CPD_YR2__c**
* **CPD_YR3__c**
* **CPD_YR4__c**
* **CPD_YR5__c**
* **Contact_List_Rollup__c**
* **Stage_Modified_Date__c**
* **Expected_Agreement_Duration__c**
* **Expected_Agreement_Start__c**
* **Organization_Subtype__c**
* **Exploratory_Type_Change_Date__c**
* **Day_of_the_Month__c**
* **Department_Name__c**
* **Opportunity_Name__c**
* **Ultimate_Parent_Organization__c**
* **Ultimate_Parent_ID__c**
* **Organisation_Subtype__c**
* **Opp_Team_List__c**
* **Target_Countries_List_255__c**
* **Cloned_record__c**
* **Add_Supporting_Thematic_Teams__c**
* **Organisation_Source__c**
* **W_INSERT_DT**
* **W_CREATED_BY**
* **W_UPDATE_DT**
* **W_UPDATED_BY**

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
- Target: 300% of annual delivery.

#### B) Total value of resources mobilized (45%)
- Calculates the total value of resources mobilized from signed opportunities YTD
- resources mobilized / delivery from previous year
- THis will have to be looked against the delivery trendline from previous year. 
- Rate  = subindicator score 


#### C) Average Project Size (10%) 
- Compares the current average size of pipeline opportunities to the previous year's average
- Baseline is to grow the median project size each year 
- 100% positive score if its growing, negative score if its lower than last year average based on the ratio of this year to last year. 


### Part 2: Pipeline Health (30%)

Pipeline Health is assessed through three components:

#### A) Opportunity Age (40%)
- Measures the average age of opportunities in the pipeline.
- Older is worse. 


| Months       | Score   |
|--------------|---------|
| Below 12     | 100/100 |
| 12 to 18    | 75/100  |
| 18 to 24    | 50/100  |
| Above 24     | 25/100  |

If there are no opportunities in the pipeline, the score is 0/100. 


#### B) Opportunity Activity (40%)
- Calculates the percentage of opportunities updated within a specified recent period.
- % of opportunities updated in the last 3 months - % score of B

#### C) Early Stage Capture Rate (20%)
- Measures the percentage of signed opportunities that were initially created in Pipeline C + Initial: Exploratory Opportunity (this is merged to be called Pipeline C)
- This could also be gamed by moving it to Pipeline C and then quickly moving it to Pipeline B, then pipeline A, then signed. 14 days is the threshold for this. 
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




## Traffic Light System


| Traffic Light | Score |
| ------------- | ----- |
| Green         | 80+   |
| Yellow        | 60+   |
| Red           | <60   |



## Limitations 

- The system does not count Central Bureau opportunities correctly if the funds are allocated to multiple departments (i.e. typically country offices or HQ departments). Unity team is working on a feature to fix this by introducing a parent-subsidiary relationship for opportunities. 


## Resources

- Unity Platform
- [Pipeline Policy Guide](https://view.officeapps.live.com/op/embed.aspx?src=https://popp.undp.org/sites/g/files/zskgke421/files/2023-09/FRM_Pipeline%20Management_Guidelines.docx)


