# SESP

<table data-header-hidden><thead><tr><th width="288"></th><th></th></tr></thead><tbody><tr><td>Data Owner</td><td>David Maier (<a href="mailto:david.maier@undp.org">david.maier@undp.org</a>) BPPS Effectiveness</td></tr><tr><td>Availability in Data Warehouse</td><td>Available</td></tr><tr><td>Data Refresh Rate</td><td>Daily</td></tr><tr><td>Accountability Weighted Scoring</td><td>40%</td></tr></tbody></table>

## Introduction

Screening and categorization of projects are key requirements of the [Social and Environmental Standards (SES)](https://www.undp.org/content/undp/en/home/librarypage/operations1/undp-social-and-environmental-standards).

In this regard, the objectives of UNDP's Social and Environmental Screening Procedure (SESP) are to:

* Integrate the SES Programming Principles in order to maximize social and environmental opportunities and benefits and strengthen social and environmental sustainability;
* Identify potential social and environmental risks and their significance;
* Determine the project's risk category (Low, Moderate, Substantial, High); and,
* Determine the level of social and environmental assessment and management required to address potential risks and impacts.\


#### Key Elements of the UNDP's Social and Environmental Standards include:

_Part A: Programming Principles:_

* Leave No One Behind
* Human Rights
* Gender Equality and Women's Empowerment
* Sustainability and Resilience
* Accountability

_Part B: Project-Level Standards:_

* Standard 1: Biodiversity Conservation and Sustainable Natural Resource Management
* Standard 2: Climate Change and Disaster Risks
* Standard 3: Community Health, Safety and Security
* Standard 4: Cultural Heritage
* Standard 5: Displacement and Resettlement
* Standard 6: Indigenous Peoples
* Standard 7: Labour and Working Conditions
* Standard 8: Pollution Prevention and Resource Efficiency

_Part C: Social and Environmental Management System Requirements:_

* Quality Assurance and Risk Management
* Screening and Categorization
* Assessment and Management
* Stakeholder Engagement and Response Mechanism
* Access to Information
* Monitoring, Reporting and Compliance

## Organisational Objective

100% of eligible projects have SESP done in the same year the project started.

## Data

For historical reasons, the SESP and PQA Data are stored together. Downloading the data from the UNDP Data Warehouse provides a CSV file with the following columns:

* **OperatingUnit**: Identifies the operational unit associated with the project, indicating the specific geographic or organizational division.
* **Bureau**: Specifies the bureau within the organization that oversees the project, representing a higher-level administrative grouping.
* **isActive**: A binary indicator (1 for active, 0 for inactive) showing whether the project is currently active. _It is not clear how this particular data item is gathered, and this should be not trusted compared to the official Master Project List._
* **Year**: The year associated with the project's data entry, indicating when the project was either initiated or recorded in the system.
* **isQA\_Eligible**: A binary flag (1 for yes, 0 for no) denoting whether the project is eligible for Quality Assurance (QA) processes.
* **isQA\_Required**: Another binary flag (1 for yes, 0 for no) indicating whether the project requires QA based on specific criteria or standards.
* **QA\_Status**: Describes the QA status of the project, such as "Exempted" or "Completed," detailing the outcome of the QA process.
* **isSESP\_Required**: A binary indicator (1 for yes, 0 for no) showing whether the project requires Social and Environmental Standards Screening Procedures (SESP).
* **SESP\_Status**: Reflects the current status of the SESP process for the project, with possible values like "Not Monitored," "Pending," or "Completed."
* **ProjectNum\_Unified**: A unique identifier for each project, allowing for consistent tracking and referencing across different records or databases.
* **ApprovedDate**: The date and time when the project received approval, formatted as a timestamp, indicating when the project was officially sanctioned.

This data is then used to enrich the [Master Project List](../master-project-list.md) with the isSESP\_Required and SESP\_Status information, and we use the ProjectNum\_Unified to match the projects from this SESP dataset and the Master Project List.

{% hint style="info" %}
Because in the SESP dataset a project appears as a row in each year it is active, if *any* year contains the SESP\_Status "completed" we count the project has having done SESP.
{% endhint %}

### Project Types

Some project types are exempt from SESP. Here is the full list of project types in the Data Warehouse and whether they are eligible or exempt from SESP. 

| Project Type | Eligible / Exempt |
| ------------ | ----------------- |
| DEVEF        | Exempt            |
| DEVT         | Exempt            |
| ENGMT        | Eligible          |
| FCORE        | Exempt            |
| FNONC        | Exempt            |
| FPART        | Exempt            |
| GLO          | Eligible          |
| INT          | Exempt            |
| MGMT         | Exempt            |
| MSA          | Exempt            |
| PROJM        | Exempt            |
| RAF          | Eligible          |
| RAP          | Eligible          |
| RAS          | Eligible          |
| REC          | Eligible          |
| RLA          | Eligible          |
| RMCOR        | Exempt            |
| RMFLC        | Exempt            |
| RMPLC        | Exempt            |
| SSC          | Eligible          |
| UNC          | Exempt            |
| UNV          | Exempt            |
| CNT          | Eligible          |

### Project Statuses

The project statuses are defined in the [Master Project List.](../master-project-list.md)

The statuses are:

* Financially Closed
* On Going
* Operationally Closed
* Submit for Operational Close 
* Submitted for Financial close

The only project status that we consider is `On Going` for the purpouses of calculating the % of SESP completion for UNDP as a whole or any business unit within UNDP. 

### SESP Statuses

* **Completed:** These projects have fully met the SESP requirements, indicating successful adherence to and implementation of necessary social and environmental standards.
* **Exempted:** Projects that are not required to do SESP. This can be based on the project type.
* **Not Monitored:** Projects that by their nature do not require SESP and so are not monitored.
* **Not Required:** This SESP status indicates the project is exempt from the SESP process, based on project type or other criteria.
* **Pending:** These projects are either in the process of undergoing SESP evaluation or have not started.

##

## Data Export

{% hint style="danger" %}
This has not yet been defined.
{% endhint %}

### Raw Cleaned Data

### Scoring data

-- **Business Unit**: The name of the country office or business unit
- **3 letter ISO Code**: The ISO code of the country, if applicable.
- **Bureau**: The Bureau of the Country Office, if applicable.
- **Ongoing Projects**: The number of ongoing projects within the business unit
- **Projects requiring SESP**: The number of ongoing projects that require SESP. This includes both the ones that have completed and are yet to complete SESP. 
- **Projects that have completed SESP**:  The number of ongoing projects that have completed SESP 
- **Projects that have not completed SESP**: The number of ongoing projects that have not completed SESP
- **% Completion Rate**: The completion rate, calcuated by the number of ongoing projects that have completed SESP divided by the total number of ongoing projects, multiplied by 100. 
- **Traffic Light Score**: Green/yellow/red: 

## Calculation of Scoring

The filtering below is done on the Master Project List, which has already identified unique projects.

1. **Filter out by project type:** As listed in the table above.
2. **Filter out by project status:** Only "ongoing" projects should be kept.
3. **Deduplicate the SESP data:** As the SESP data contains one row per project year, this leads to multiple SESP statuses for any given project**.** The way to handle this is that if a project contains the SESP Status `Completed` for any given year, we count the entire project as having completed SESP.  In any other case, we count the project as _not_ having done SESP.
4. **Merge Master Project List with SESP Data:** Using the ProjectNum\_Unified in SESP Data with ATLAS\_AWARD\_NUMBER in Master Project List to enrich the [Master Project List](../master-project-list.md) with the following two columns: SESP\_Status and isSESP\_Required
5. **Further Filtering for SESP Required:** Filter by projects that are marked as requiring SESP (`isSESP_Required` == 1), indicating _they must undergo SESP processes based on predefined standards or conditions._
6. **Excluding Projects Based on SESP Status**: From the filtered set, we further exclude projects with an SESP status of `Not Required`,`Exempted`, `Not Monitored`

**Calculation:**

Once we have done this, we can calculate the completion rate using the following formula:

Number of Projects with Completed SESP / Number of Total Projects with Completed + Pending SESP **= Completion Rate.**

{% hint style="info" %}
This calculation counnts the `Pending` status as "incomplete'.
{% endhint %}

The Completion Rate (i.e. 75%) is then the score for this indicator. 

## Traffic Light System

| Traffic Light | Score |
| ------------- | ----- |
| Green         | 100   |
| Yellow        | 90+   |
| Red           | <90   |

## Resources

* [UNDP Social and Environmental Standards](https://www.undp.org/publications/undp-social-and-environmental-standards)
* [UNDP Social and Environmental Screening Procedure (SESP)](https://www.undp.org/publications/undps-social-and-environmental-screening-procedure-sesp)

