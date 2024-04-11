# Transparency

<table data-header-hidden><thead><tr><th width="288"></th><th></th></tr></thead><tbody><tr><td>Data Owner</td><td>Addul Riza (<a href="mailto:abdul.riza@undp.org">abdul.riza@undp.org</a>), BPPS Effectiveness</td></tr><tr><td>Availability in Data Warehouse</td><td>Not Available</td></tr><tr><td>Data Refresh Rate</td><td>Yearly</td></tr><tr><td>Accountability Weighted Scoring</td><td>30%</td></tr></tbody></table>

## Transparency Index

This is the global indicator.&#x20;

### Introduction to Indicator

{% embed url="https://www.publishwhatyoufund.org/the-index/2022/united-nations-development-program-undp/" %}

### Calculation of Scoring.

Publish What You Fund Score = Indicator Score

The traffic light indicator methodology for this indicator is:

* Green = 80+
* Yellow = 60+
* Red = <60

{% hint style="info" %}
This is aligned with the Very Good / Good / Fair scoring at Publish What You Fund
{% endhint %}



## Transparency Dashboard Performance.

{% hint style="info" %}
This is a draft and under testing
{% endhint %}

This is the indicator for Country & Bureau levels.&#x20;

### Available Data&#x20;

Downloading the dataset from the UNDP Data Warehouse:&#x20;

&#x20;

* UNDP\_PROJECTS data - List of all unique projects in UNDP&#x20;

&#x20;

Columns in UNDP\_PROJECTS data&#x20;

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

&#x20;

&#x20;

### Calculation: &#x20;

1\. Define the rollup\_ou\_description to filter: &#x20;

Filters the DataFrame df\_UNDP\_PROJECTS by selecting only the rows where the value in the 'rollup\_ou' column matches the value stored in the variable target\_rollup\_ou (note: which is 'ALB' in this case as an example).&#x20;

&#x20;

2\. Calculates the count of projects for each unique project status in the dataframe if count>0.&#x20;

The statuses are:&#x20;

* Financially Closed&#x20;
* On Going&#x20;
* Operationally Closed&#x20;
* Submit for Operational Close &#x20;
* Submitted for Financial close&#x20;

3\. Visualization - Grouping projects by project status and counting the number of projects in each status.&#x20;

&#x20;

4\. Filter data by specified project statuses: Select rows from the dataframe where the 'PROJECT\_STATUS' column matches the specified status values: 'On Going', 'Operationally Closed', and 'Submit for Operational Close'.&#x20;

&#x20;

Then remaining visualizations are done using this filtered dataframe.&#x20;

&#x20;

5\. Visualization: creates a horizontal bar chart showing the number of projects by project type, with the bars colored in sky blue except for the bars representing projects with null Project\_Type, which are colored in red.&#x20;

Grouping projects by project type and counting the number of projects in each type - First, count the occurrences of each unique project type in the 'PROJECT\_TYPE' column. Then resets the index and renames the columns to 'Project\_Type' and 'Count' respectively to prepare the data for visualization. &#x20;

Then, filters the dataframe to select rows where the 'PROJECT\_TYPE' column is null and counting projects with null Project\_Type. After that, adding the count of projects with null Project\_Type to the dataframe. Then created a bar chart including the rest of the project types.&#x20;

&#x20;

6\. Visualization: Counting the number of projects with and without descriptions - counts the number of non-null values in the 'PROJECT\_DESCRIPTION' column and then calculates the number of projects without descriptions by subtracting the count of projects with descriptions from the total number of projects. Then created a bar chart and annotated each bar with its respective count.&#x20;

&#x20;

7\. Visualization: Counting the number of projects with and without PROJECT\_TYPE - calculates the number of non-null values in the 'PROJECT\_TYPE' column and then calculates the number of projects without a 'PROJECT\_TYPE' by subtracting the count of projects with 'PROJECT\_TYPE' from the total number of projects. Then created a bar chart and annotated each bar with its respective count.&#x20;

&#x20;

8\. Visualization: creates a horizontal bar chart, annotates each bar with its respective count - Computes various statistics about projects on such as:&#x20;

* Total number of projects&#x20;
* Projects with less than 10 characters in project name&#x20;
* Projects without description&#x20;
* Projects without implementing partner&#x20;
* Projects with description less than 80 characters&#x20;

&#x20;

Transparency Scoring for CO - Methodology:&#x20;

Step 1: Make sure having a filtered dataframe (rollup\_ou = \[mention CO], also, PROJECT\_STATUS'].isin(\['On Going', 'Operationally Closed', 'Submit for Operational Close').&#x20;

Step 2: Penalty Factors for More Severe Penalization (1 to 5): Define penalty factors for each indicator to adjust the severity of penalization - &#x20;

* Penalty factor for projects with names shorter than 10 characters = 1&#x20;
* Penalty factor for projects without a description = 2&#x20;
* Penalty factor for projects without an implementing partner = 4&#x20;
* Penalty factor for projects with descriptions shorter than 80 characters = 3&#x20;
* Penalty factor for projects without a project type = 5&#x20;

Step 3: Count of All Projects : Calculate the total number of projects for normalization purposes.&#x20;

Step 4: count the occurrences of projects in each noncompliance case:&#x20;

* projects with names shorter than 10 characters.&#x20;
* projects without a description.&#x20;
* projects without an implementing partner.&#x20;
* projects with descriptions shorter than 80 characters.&#x20;
* projects without a project type&#x20;

Step 5: Determine total number of projects for each indicator.&#x20;

Step 6: Scores Calculation:&#x20;

Calculation of Percentages: Calculate the percentage of non-compliant projects relative to the total number of projects for each indicator.&#x20;

Penalty Factor Application: Apply the penalty factors to the percentages of non-compliant projects instead of raw counts. This adjustment ensures that the severity of penalization is proportionate to the extent of non-compliance relative to the total project count.&#x20;

Scoring Calculation: Calculate the scores based on the adjusted percentages of non-compliant projects multiplied by 20. This scaling operation ensures that the scores fall within a range of 0 to 20.&#x20;

Finally, individual scores for each indicator, along with the total score out of 100 for the CO, are displayed. Note: With each indicator having a maximum of 20 points and 5 indicators, the maximum possible total score would be 100 points.&#x20;
