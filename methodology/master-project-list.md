# Master Project List

{% hint style="warning" %}
**This section is under active development**
{% endhint %}

Having an accurate and up-to-date master project list to serve as the one source of truth is crucial at UNDP for both performance monitoring and compliance.&#x20;

## Available Data&#x20;

There are multiple tables in UNDP Data Warehouse that are related to projects:

* **IATI\_FINANCIALS data:** So this is the IATI Project List, which is a list of projects that we use for external reporting on the [Transparency Portal.](https://open.undp.org)
* **UNDP\_CPD\_SP data:** This is the CPD (Country Programming Document) Project list, which lists the projects for which the COs have matched them to the CPD outcomes.&#x20;
* **UNDP\_PROJECTS data:** This is the master dataset of all projects across UNDP and also includes budget data for each project, broken down by CPD outcome.&#x20;

{% hint style="info" %}
Note that UNDP\_CPD\_SP and IATI\_FINANCIALS do not have all the projects, but they can enrich the data within UNDP\_PROJECTS.&#x20;
{% endhint %}

&#x20; The IATI data can be taken from the UNDP Data Warehouse with the following query:

```plsql
select
    a.hq_co,
    a.bureau,
    -- a.rollup_ou,
    rollup_ou = case when a.BUSINESS_UNIT <> 'HQ' then a.BUSINESS_UNIT else a.rollup_ou end,
    -- a.PROJECT_ID,
    a.PROJECT_NUMBER,
    a.PROJECT_NAME,
    iati_compatibility_project = case
        -- converted projects include double zeroes upfront
        when a.PROJECT_NUMBER like '00%' then isNull(a.ATLAS_AWARD_NUMBER, '' /* a.PROJECT_NUMBER */)
        else a.PROJECT_NUMBER
    end
from UNDP_IATI.UNDP_PROJECTS a
join UNDP_IATI.IATI_FINANCIALS c on a.PROJECT_ID = c.PROJECT_ID
    and c.FUND_CATEGORY = 'PROGRAMME'
group by a.hq_co,
    a.bureau,
    -- a.rollup_ou,
    case when a.BUSINESS_UNIT <> 'HQ' then a.BUSINESS_UNIT else a.rollup_ou end,
    -- a.PROJECT_ID,
    a.PROJECT_NUMBER,
    a.PROJECT_NAME,
    case
        -- converted projects include double zeroes upfront
        when a.PROJECT_NUMBER like '00%' then isNull(a.ATLAS_AWARD_NUMBER, '' /* a.PROJECT_NUMBER */)
        else a.PROJECT_NUMBER
    end
```

&#x20;

<details>

<summary>Columns in IATI_FINANCIALS data</summary>

* **hq\_co:** Location type (Headquarters (HQ), Country Office (CO), or Regional Center (RC)).
* **bureau:** Name of the specialized unit or division responsible.
* **rollup\_ou:** Code for the organizational unit.
* **rollup\_ou\_description:** Name of the organizational unit.
* **PROJECT\_ID:** Identifier for the project.
* **PROJECT\_NUMBER:** Number assigned to the project.
* **TASK\_ID:** Identifier for the task.
* **TASK\_NUMBER:** Number assigned to the task.
* **FUND\_CODE:** Code representing the funding source.
* **FUND\_CATEGORY:** Category that the funding falls into.
* **DONOR:** Code representing the donor.
* **DONOR\_DESCR:** Full name of the donor.
* **DONOR\_DESCSHORT:** Abbreviated description of the donor.
* **donor\_type\_lvl1:** Classification of donor (Non-Government, Program city, Non-program city, or Other).
* **donor\_type\_lvl1\_descr:** Detailed description of the donor classification.
* **donor\_type\_lvl2:** Secondary level name of donor.
* **donor\_type\_lvl2\_descr:** Description for the second level of donor classification.
* **donor\_type\_lvl3:** Tertiary level name of donor.
* **donor\_type\_lvl3\_descr:** Description for the third level of donor classification.
* **fiscal\_year:** Fiscal year range (2023 to 2031).
* **Budget:** Project budget amount in USD.
* **Expenditure:** Total amount of money expended (includes negative numbers).
* **Load\_Timestamp:** Date and time of data entry.

</details>

<details>

<summary>Columns in UNDP_CPD_SP data</summary>

* **hq\_co:** Type of location (Headquarters (HQ), Country Office (CO), or Regional Center (RC)).
* **bureau:** Name of the specialized unit or division responsible.
* **rollup\_ou:** Code of the organizational unit.
* **rollup\_ou\_description:** Name of the organizational unit.
* **BUSINESS\_UNIT:** Identifier for the business unit.
* **PROJECT\_ID:** Identifier for the project.
* **PROJECT\_NUMBER:** Number assigned to the project.
* **TASK\_ID:** Identifier for the task.
* **TASK\_NUMBER:** Number assigned to the task.
* **TASK\_NAME:** Name of the task.
* **CPD\_OUTPUT:** Code for CPD output.
* **CPD\_OUTPUT\_DESCRIPTION:** Description of CPD output.
* **CPD\_OUTCOME:** Code for CPD outcome.
* **CPD\_OUTCOME\_DESCRIPTION:** Description of CPD outcome.
* **sp\_outcome:** SP outcome code.
* **sp\_outcome\_id:** Identifier for SP outcome.
* **sp\_outcome\_description:** Description of SP outcome.
* **sp\_output:** SP output code.
* **sp\_output\_description:** Description of SP output.
* **SP\_PRIMARY\_RESULT\_LINKAGE:** Linkage to the primary result for SP projects.
* **SIGNATURE\_SOLUTION:** Code for signature solution.
* **SIGNATURE\_SOLUTION\_DESCRIPTION:** Description of signature solution.
* **BUDGET\_IDENTIFIER:** Code for budget identifier.
* **BUDGET\_IDENTIFIER\_DESCRIPTION:** Description of budget identifier.
* **CPD\_CYCLE\_NAME:** Name of the CPD cycle.
* **CPD\_CYCLE:** Code for CPD cycle.
* **BEGIN\_YEAR:** Start year of the cycle.
* **END\_YEAR:** End year of the cycle.

</details>

<details>

<summary>Columns in UNDP_PROJECTS data </summary>



* **hq\_co:** Type of location (Headquarters (HQ), Country Office (CO), or Regional Center (RC)).
* **bureau:** Name of the specialized unit or division responsible.
* **rollup\_ou:** Code of the organizational unit.
* **rollup\_ou\_description:** Name of the organizational unit.
* **PROJECT\_ID:** Identifier for the project.
* **PROJECT\_NUMBER:** Number assigned to the project.
* **PROJECT\_NAME:** Name of the project.
* **PROJECT\_DESCRIPTION:** Description of the project.
* **ATLAS\_AWARD\_NUMBER:** Atlas award number.
* **ATLAS\_AWARD\_DESCIPTION:** Description of the Atlas award.
* **BUSINESS\_UNIT:** Identifier for the business unit.
* **ORGANIZATION:** Organization involved in the project.
* **DEPARTMENT:** Department associated with the project.
* **START\_DATE:** Start date of the project.
* **COMPLETION\_DATE:** Completion date of the project.
* **CLOSED\_DATE:** Date when the project was closed.
* **PROJECT\_TYPE:** Type of project.
* **PROJECT\_TYPE\_DESCRIPTION:** Description of the project type.
* **PROJECT\_STATUS:** Status of the project.
* **PROJECT\_MANAGER:** Project manager's name.
* **PROJECT\_MANAGER\_EMAIL:** Email address of the project manager.
* **IMPLEMENTING\_PARTNER:** Implementing partner code.
* **IMPLEMENTING\_PARTNER\_DESCRIPTION:** Description of the implementing partner.
* **IMPLEMENTATION\_MODALITY:** Implementation modality code.
* **IMPLEMENTATION\_MODALITY\_DESCRIPTION:** Description of the implementation modality.
* **PROJECT\_ORIG\_TEMPLATE:** Original template of the project.
* **PROGRAMME\_FUNDING\_FLAG:** Flag indicating program funding.
* **GEF\_GCF\_PROJECT\_FLAG:** Flag indicating GEF/GCF project.
* **Other\_References\_Value:** Other references value.

</details>

&#x20;&#x20;

## Calculation

To get a list of projects with budgets for each project and by CPD outcome.

1. **Comparison of Project IDs in 3 datasets:**  Extract unique project IDs in 3 datasets. The aim is to find the total number of unique projects in each dataset and ensure that all projects within UNDP\_CPD\_SP and IATI\_FINANCIALS can be found within UNDP\_PROJECTS
2. **Checking UNDP\_CPD\_SP Dataset:** Retrieve unique combinations of 'PROJECT\_ID', 'CPD\_OUTCOME', and 'TASK\_ID': In UNDP\_CPD\_SP, select the columns 'PROJECT\_ID', 'CPD\_OUTCOME', and 'TASK\_ID' for analysis. Then, drop duplicate rows based on unique combinations of 'PROJECT\_ID', 'CPD\_OUTCOME', and 'TASK\_ID' and retain the first occurrence of each unique combination. Analyze the count of unique combinations of 'PROJECT\_ID', 'CPD\_OUTCOME', and 'TASK\_ID' . The aim is to verify the dataset UNDP\_CPD\_SP contains only unique combinations of PROJECT\_ID and CPD\_OUTCOME and TASK\_ID. Also, to verify the count of such unique combinations equal to number of rows of UNDP\_CPD\_SP dataset.&#x20;
3. **Check Missing Values:** Check in all 3 datasets whether there is any row with missing values for the columns 'PROJECT\_ID', 'PROJECT\_NUMBER', 'hq\_co', 'bureau', 'rollup\_ou', 'rollup\_ou\_description'.
4. Display number of task ids with a budget value in IATI\_FINANCIALS data.&#x20;
5. **Merge Datasets:** Utilize the common columns \['hq\_co', 'bureau', 'rollup\_ou', 'rollup\_ou\_description', 'PROJECT\_ID', 'PROJECT\_NUMBER'] to merge UNDP\_PROJECTS with UNDP\_CPD\_SP. Perform a left join to retain all records from UNDP\_PROJECTS while incorporating matching records from UNDP\_CPD\_SP. Later, utilize the same common columns to merge the previously merged dataframe with IATI\_FINANCIALS. Again, perform a left join to retain all records from the previously merged dataframe while incorporating matching records from IATI\_FINANCIALS.
6. **Specify columns to retain only the desired columns:**  Define a list of columns to be retained in the final dataframe based on project-related information and identifiers. After this, extract the selected columns from the merged dataframe to create the final Dataframe. Use the selected column list to filter the merged dataframe and retain only the desired columns.&#x20;
7. **Checking all the rows with budget captured in merged data:** Count the number of unique 'TASK\_ID' values corresponding to rows with budget information. This is performed to provide insight into the completeness of budget data captured within the merged Dataframe. Also, we can verify previously displayed value regarding the number of task ids with a budget value in IATI\_FINANCIALS data is same.&#x20;
8. Count and display the number of unique combinations of 'PROJECT\_ID' and 'CPD\_OUTCOME' in the merged dataframe.&#x20;

&#x20;

### 9. Aggregation of Budget Data&#x20;

A single project ID can have multiple CPD outcomes. Initially, the code defines an aggregation function to calculate the sum of the 'budget' column for each group defined by 'PROJECT\_ID' and 'CPD\_OUTCOME'. This step aggregates budget data across different outcomes for each project.&#x20;

To ensure that all unique 'PROJECT\_ID' values are retained, a dataframe is created containing all unique 'PROJECT\_ID's from the original dataset. The aggregated budget data is merged with the dataframe containing all unique 'PROJECT\_ID' values. This step is important to ensure that even projects with no budgetary allocations or outcomes are included in the final analysis.&#x20;

&#x20;

## 9. Project status&#x20;

Print the counts of unique project IDs for each project status to show the distribution of projects across different statuses.&#x20;

The statuses are:&#x20;

* Financially Closed&#x20;
* On Going&#x20;
* Operationally Closed&#x20;
* Submit for Operational Close &#x20;
* Submitted for Financial close&#x20;

&#x20;

## 10. Filter data by specified project statuses:&#x20;

Select rows from the dataframe where the 'PROJECT\_STATUS' column matches the specified status values: 'On Going', 'Operationally Closed', and 'Submit for Operational Close'.&#x20;



{% hint style="info" %}
The items below were taken from previous SESP Methodology and must be included here
{% endhint %}



**Filtering out Outputs:** The initial step involves removing duplicate project records to adhere to the "Quantum" data management approach, transitioning from the "Atlas" method's one-row-per-project standard. This deduplication ensures each project is uniquely represented by eliminating redundancies based on specific attributes. These attributes include the project's operating unit, overseeing bureau, activity status, year of data entry, quality assurance eligibility and requirements, QA status, SESP requirements, SESP status, project identification number, and approval date. The aim is to maintain a dataset where each row uniquely represents a distinct project, setting the stage for precise analysis.

**Identifying Unique Projects**: After applying these filters, we count the number of unique projects by their `ProjectNum_Unified` identifier. This final step provides the total count of distinct projects meeting all the specified criteria.

&#x20;
