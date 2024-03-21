# Master Project List

Available Data&#x20;

Downloading the datasets from the UNDP Data Warehouse, provides 3 CSV files:&#x20;

* I**ATI\_FINANCIALS data:** IATI Project List (list of projects that we use for external reporting&#x20;
* **UNDP\_CPD\_SP data:** CPD Project list (list of projects where country offices have matched to CPD outcomes)&#x20;
* **UNDP\_PROJECTS data:** List of budgets for each project/CPD outcome&#x20;

&#x20;

{% hint style="info" %}
UNDP\_PROJECTS has all the projects (master list) and UNDP\_CPD\_SP and IATI\_FINANCIALS missing some projects that are already in UNDP\_PROJECTS. &#x20;
{% endhint %}

&#x20;&#x20;

### Columns in IATI\_FINANCIALS data:  &#x20;

* hq\_co: Headquarters (HQ), Country Office (CO) or RC.&#x20;
* bureau: The name of specialized unit or division responsible.&#x20;
* rollup\_ou: The organizational unit's code&#x20;
* rollup\_ou\_description: The organizational unit's name&#x20;
* PROJECT\_ID: Project identifier&#x20;
* PROJECT\_NUMBER: Project number&#x20;
* TASK\_ID: Task identifier&#x20;
* TASK\_NUMBER: Task number&#x20;
* FUND\_CODE: Code of funding&#x20;
* FUND\_CATEGORY: Category of funding&#x20;
* DONOR: Donor code.&#x20;
* DONOR\_DESCR: Donor name.&#x20;
* DONOR\_DESCSHORT:  Donor short description &#x20;
* donor\_type\_lvl1: whether Non-Government, Program city, non-program city or others. &#x20;
* donor\_type\_lvl1\_descr: Description of donor type. &#x20;
* donor\_type\_lvl2: Level 2 name of donor&#x20;
* donor\_type\_lvl2\_descr: Description of level 2 donor type. &#x20;
* donor\_type\_lvl3: Level 3 name of donor&#x20;
* donor\_type\_lvl3\_descr: Description of level 3 donor type.&#x20;
* fiscal\_year: 2023 to 2031&#x20;
* Budget: amount in USD&#x20;
* Expenditure: total amount of money spent (includes –ve number)&#x20;
* Load\_Timestamp: datetime&#x20;

### Columns in UNDP\_CPD\_SP data:  &#x20;

* hq\_co: Headquarters (HQ), Country Office (CO), or RC.&#x20;
* bureau: The name of the specialized unit or division responsible.&#x20;
* rollup\_ou: Organizational unit's code.&#x20;
* rollup\_ou\_description: Organizational unit's name.&#x20;
* BUSINESS\_UNIT: Business unit identifier.&#x20;
* PROJECT\_ID: Project identifier.&#x20;
* PROJECT\_NUMBER: Project number.&#x20;
* TASK\_ID: Task identifier.&#x20;
* TASK\_NUMBER: Task number.&#x20;
* TASK\_NAME: Name of the task.&#x20;
* CPD\_OUTPUT: CPD output code.&#x20;
* CPD\_OUTPUT\_DESCRIPTION: CPD output description.&#x20;
* CPD\_OUTCOME: CPD outcome code.&#x20;
* CPD\_OUTCOME\_DESCRIPTION: CPD outcome description.&#x20;
* sp\_outcome: SP outcome code.&#x20;
* sp\_outcome\_id: SP outcome ID.&#x20;
* sp\_outcome\_description: SP outcome description.&#x20;
* sp\_output: SP output code.&#x20;
* sp\_output\_description: SP output description.&#x20;
* SP\_PRIMARY\_RESULT\_LINKAGE: Linkage to the primary result for SP projects.&#x20;
* SIGNATURE\_SOLUTION: Signature solution code.&#x20;
* SIGNATURE\_SOLUTION\_DESCRIPTION: Signature solution description.&#x20;
* BUDGET\_IDENTIFIER: Budget identifier code.&#x20;
* BUDGET\_IDENTIFIER\_DESCRIPTION: Budget identifier description.&#x20;
* CPD\_CYCLE\_NAME: CPD cycle name.&#x20;
* CPD\_CYCLE: CPD cycle code.&#x20;
* BEGIN\_YEAR: Start year.&#x20;
* END\_YEAR: End year.&#x20;

### Columns in UNDP\_PROJECTS data&#x20;

* hq\_co: Headquarters (HQ), Country Office (CO), or RC.&#x20;
* bureau: The name of the specialized unit or division responsible.&#x20;
* rollup\_ou: Organizational unit's code.&#x20;
* rollup\_ou\_description: Organizational unit's name.&#x20;
* PROJECT\_ID: Project identifier.&#x20;
* PROJECT\_NUMBER: Project number.&#x20;
* PROJECT\_NAME: Name of the project.&#x20;
* PROJECT\_DESCRIPTION: Description of the project.&#x20;
* ATLAS\_AWARD\_NUMBER: Atlas award number.&#x20;
* ATLAS\_AWARD\_DESCIPTION: Description of the Atlas award.&#x20;
* BUSINESS\_UNIT: Business unit identifier.&#x20;
* ORGANIZATION: Organization involved in the project.&#x20;
* DEPARTMENT: Department associated with the project.&#x20;
* START\_DATE: Start date of the project.&#x20;
* COMPLETION\_DATE: Completion date of the project.&#x20;
* CLOSED\_DATE: Date when the project was closed.&#x20;
* PROJECT\_TYPE: Type of project.&#x20;
* PROJECT\_TYPE\_DESCRIPTION: Description of the project type.&#x20;
* PROJECT\_STATUS: Status of the project.&#x20;
* PROJECT\_MANAGER: Project manager's name.&#x20;
* PROJECT\_MANAGER\_EMAIL: Email address of the project manager.&#x20;
* IMPLEMENTING\_PARTNER: Implementing partner code.&#x20;
* IMPLEMENTING\_PARTNER\_DESCRIPTION: Description of the implementing partner.&#x20;
* IMPLEMENTATION\_MODALITY: Implementation modality code.&#x20;
* IMPLEMENTATION\_MODALITY\_DESCRIPTION: Description of the implementation modality.&#x20;
* PROJECT\_ORIG\_TEMPLATE: Original template of the project.&#x20;
* PROGRAMME\_FUNDING\_FLAG: Flag indicating program funding.&#x20;
* GEF\_GCF\_PROJECT\_FLAG: Flag indicating GEF/GCF project.&#x20;
* Other\_References\_Value: Other references value.&#x20;

&#x20;&#x20;

Calculation: To get a list of projects with budgets for each project and by CPD outcome&#x20;

&#x20;

1.Comparison of Project IDs in 3 datasets: &#x20;

Extract unique project IDs in 3 datasets - The aim is to find total number of unique projects in each dataset and which dataset has more unique projects (Mater project list).&#x20;

Later, identify projects in UNDP\_CPD\_SP that are not present in UNDP\_PROJECTS. Then, identify projects in IATI\_FINANCIALS that are not present in UNDP\_PROJECTS – The aim is to verify all the projects in either UNDP\_CPD\_SP or IATI\_FINANCIALS are in UNDP\_PROJECTS.&#x20;

&#x20;

2\. Retrieve unique combinations of 'PROJECT\_ID', 'CPD\_OUTCOME', and 'TASK\_ID':&#x20;

In UNDP\_CPD\_SP, select the columns 'PROJECT\_ID', 'CPD\_OUTCOME', and 'TASK\_ID' for analysis. Then, drop duplicate rows based on unique combinations of 'PROJECT\_ID', 'CPD\_OUTCOME', and 'TASK\_ID' and retain the first occurrence of each unique combination. Analyze the count of unique combinations of 'PROJECT\_ID', 'CPD\_OUTCOME', and 'TASK\_ID' - The aim is to verify the dataset UNDP\_CPD\_SP contains only unique combinations of PROJECT\_ID and CPD\_OUTCOME and TASK\_ID. Also, to verify the count of such unique combinations equal to number of rows of UNDP\_CPD\_SP dataset.&#x20;

&#x20;

3\. Checking missing values: Check in all 3 datasets whether there is any row with missing values for the columns 'PROJECT\_ID', 'PROJECT\_NUMBER', 'hq\_co', 'bureau', 'rollup\_ou', 'rollup\_ou\_description'.&#x20;

&#x20;

4\. Display number of task ids with a budget value in IATI\_FINANCIALS data.&#x20;

&#x20;

5\. Merge Datasets: Utilize the common columns \['hq\_co', 'bureau', 'rollup\_ou', 'rollup\_ou\_description', 'PROJECT\_ID', 'PROJECT\_NUMBER'] to merge UNDP\_PROJECTS with UNDP\_CPD\_SP. Perform a left join to retain all records from UNDP\_PROJECTS while incorporating matching records from UNDP\_CPD\_SP.&#x20;

Later, utilize the same common columns to merge the previously merged dataframe with IATI\_FINANCIALS. Again, perform a left join to retain all records from the previously merged dataframe while incorporating matching records from IATI\_FINANCIALS.&#x20;

&#x20;

6\. Specify columns to retain only the desired columns: Define a list of columns to be retained in the final dataframe based on project-related information and identifiers. After this, extract the selected columns from the merged dataframe to create the final Dataframe. Use the selected column list to filter the merged dataframe and retain only the desired columns.&#x20;

&#x20;

7\. Checking all the rows with budget captured in merged data: Count the number of unique 'TASK\_ID' values corresponding to rows with budget information. This is performed to provide insight into the completeness of budget data captured within the merged Dataframe. Also, we can verify previously displayed value regarding the number of task ids with a budget value in IATI\_FINANCIALS data is same.&#x20;

&#x20;

8\. Count and display the number of unique combinations of 'PROJECT\_ID' and 'CPD\_OUTCOME' in the merged dataframe.&#x20;

&#x20;

9\. Aggregation of Budget Data: A single project ID can have multiple CPD outcomes. Initially, the code defines an aggregation function to calculate the sum of the 'budget' column for each group defined by 'PROJECT\_ID' and 'CPD\_OUTCOME'. This step aggregates budget data across different outcomes for each project.&#x20;

To ensure that all unique 'PROJECT\_ID' values are retained, a dataframe is created containing all unique 'PROJECT\_ID's from the original dataset. The aggregated budget data is merged with the dataframe containing all unique 'PROJECT\_ID' values. This step is important to ensure that even projects with no budgetary allocations or outcomes are included in the final analysis.&#x20;

&#x20;

11\. Project status: Print the counts of unique project IDs for each project status to show the distribution of projects across different statuses.&#x20;

The statuses are:&#x20;

* Financially Closed&#x20;
* On Going&#x20;
* Operationally Closed&#x20;
* Submit for Operational Close &#x20;
* Submitted for Financial close&#x20;

&#x20;

12\. Filter data by specified project statuses: Select rows from the dataframe where the 'PROJECT\_STATUS' column matches the specified status values: 'On Going', 'Operationally Closed', and 'Submit for Operational Close'.&#x20;

&#x20;
