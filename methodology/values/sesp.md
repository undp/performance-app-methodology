# SESP

* Data owner: David Maier <[david.maier@undp.org](mailto:david.maier@undp.org)>, BPPS Effectiveness
* Availability in Data Warehouse: Available
* Data Refresh Rate: Ad Hoc
* Contribution to Values Overall Score: 0%

## Introduction to the Indicator

For historical reasons, the SESP and PQA Data are stored together.

### Available Data

Downloading the data from the UNDP Data Warehouse provides a CSV file with the following columns:

* **OperatingUnit**: Identifies the operational unit associated with the project, indicating the specific geographic or organizational division.
* **Bureau**: Specifies the bureau within the organization that oversees the project, representing a higher-level administrative grouping.
* **isActive**: A binary indicator (1 for active, 0 for inactive) showing whether the project is currently active. _It is not clear how this particular data item is gathered, and this should be not trusted compared to the official Master Project List._&#x20;
* **Year**: The year associated with the project's data entry, indicating when the project was either initiated or recorded in the system.
* **isQA\_Eligible**: A binary flag (1 for yes, 0 for no) denoting whether the project is eligible for Quality Assurance (QA) processes.
* **isQA\_Required**: Another binary flag (1 for yes, 0 for no) indicating whether the project requires QA based on specific criteria or standards.
* **QA\_Status**: Describes the QA status of the project, such as "Exempted" or "Completed," detailing the outcome of the QA process.
* **isSESP\_Required**: A binary indicator (1 for yes, 0 for no) showing whether the project requires Social and Environmental Standards Screening Procedures (SESP).
* **SESP\_Status**: Reflects the current status of the SESP process for the project, with possible values like "Not Monitored," "Pending," or "Completed."
* **ProjectNum\_Unified**: A unique identifier for each project, allowing for consistent tracking and referencing across different records or databases.
* **ApprovedDate**: The date and time when the project received approval, formatted as a timestamp, indicating when the project was officially sanctioned.

This data is then used to enrich the [Master Project List](../master-project-list.md) with the isSESP\_Required and SESP\_Status information, and we use the ProjectNum\_Unified to match the projects from this SESP dataset and the Master Project List.&#x20;

{% hint style="info" %}
Because in the SESP dataset a project appears as a row in each year it is active, if any year contains the SESP\_Status "completed" we count the project has having done SESP.&#x20;
{% endhint %}

### Project Types

Some project types are exempt from SESP. Here is the full list of project types in the Data Warehouse

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

The only project status that we consider is "On Going".

### SESP Statuses

* **Completed:** These projects have fully met the SESP requirements, indicating successful adherence to and implementation of necessary social and environmental standards.
* **Exempted:** Projects that are not required to do SESP. This can be based on the project type.&#x20;
* **Not Monitored:** Projects that by their nature do not require SESP and so are not monitored.&#x20;
* **Pending:** These projects are either in the process of undergoing SESP evaluation or have not started.

## Organisational Objective

100% of eligible projects have SESP done in the same year the project started.

## Calculation of Scoring

The filtering below is done on the Master Project List unless otherwise noted, which has already identified unique projects.&#x20;

1. **Filter out by project type:** As listed in the table above.
2. **Filter out by project status:** Only "ongoing" projects should be kept.&#x20;
3. **Deduplicate the SESP data:** As the SESP data contains one row per project-year, this lead to multiple SESP statuses for any given project. The way to handle this is that if a project contains the SESP Status `Completed` for any given year, we count the entire project as having completed SESP.  In any other case, we count the project as _not_ having done SESP.&#x20;
4. **Merge Master Project List with SESP Data:** Using the ProjectNum\_Unified in SESP Data with ATLAS\_AWARD\_NUMBER in Master Project List to enrich the Master Project List with the following two columns: SESP\_Status and isSESP\_Required
5. **Further Filtering for SESP Required:** Filter by projects that are marked as requiring SESP (`isSESP_Required` == 1), indicating they must undergo SESP processes based on predefined standards or conditions.
6. **Excluding Projects Based on SESP Status**: From the filtered set, we further exclude projects with an SESP status of `Exempted`, `Not Monitored`

**Calculation:**

Once we have done this, we can calculate the completion rate using the following formula: This counts the `Pending` status as "incomplete'.

Number of project with Completed SESP / Number of Total Projects with Completed + Pending SESP **= Completion Rate.**&#x20;

Completion Rate = the points of the indicator.

Traffic Light Scoring for this indicator is:&#x20;

* Green = 100
* Yellow = <90
* Red = >90

