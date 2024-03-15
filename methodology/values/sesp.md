# SESP

* Data owner: David Maier <[david.maier@undp.org](mailto:david.maier@undp.org)>, BPPS Effectiveness
* Availability in Data Warehouse: Available&#x20;
* Data Refresh Rate: Ad Hoc&#x20;
* Contribution to Values Overall Score: 0%

## Introduction to the Indicator



For historical reasons, the SESP and PQA Data are stored together.

### Available Data

Downloading the data from the UNDP Data Warehouse, provides a CSV file with the following columns:

* **OperatingUnit**: Identifies the operational unit associated with the project, indicating the specific geographic or organizational division.
* **Bureau**: Specifies the bureau within the organization that oversees the project, representing a higher-level administrative grouping.
* **isActive**: A binary indicator (1 for active, 0 for inactive) showing whether the project is currently active.
* **Year**: The year associated with the project's data entry, indicating when the project was either initiated or recorded in the system.
* **isQA\_Eligible**: A binary flag (1 for yes, 0 for no) denoting whether the project is eligible for Quality Assurance (QA) processes.
* **isQA\_Required**: Another binary flag (1 for yes, 0 for no) indicating whether the project requires QA based on specific criteria or standards.
* **QA\_Status**: Describes the QA status of the project, such as "Exempted" or "Completed," detailing the outcome of the QA process.
* **isSESP\_Required**: A binary indicator (1 for yes, 0 for no) showing whether the project requires Social and Environmental Standards Screening Procedures (SESP).
* **SESP\_Status**: Reflects the current status of the SESP process for the project, with possible values like "Not Monitored," "Pending," or "Completed."
* **ProjectNum\_Unified**: A unique identifier for each project, allowing for consistent tracking and referencing across different records or databases.
* **ApprovedDate**: The date and time when the project received approval, formatted as a timestamp, indicating when the project was officially sanctioned.

### SESP Statuses

* **Completed:** These are projects that have fully met the SESP requirements, indicating successful adherence to and implementation of necessary social and environmental standards.
* Exempted:&#x20;
* Not Monitored:&#x20;
* Not Required:&#x20;
* **Pending:** These projects are either in process of undergoing SESP evaluation or have not started.&#x20;

## Organisational Objective

100% of eligible projects have SESP done in the same year the project started.

## Calculation of Scoring&#x20;

1. **Filtering out Outputs:**  The initial step involves removing duplicate project records to adhere to the "Quantum" data management approach, transitioning from the "Atlas" method's one-row-per-project standard. This deduplication ensures each project is uniquely represented by eliminating redundancies based on specific attributes. These attributes include the project's operating unit, overseeing bureau, activity status, year of data entry, quality assurance eligibility and requirements, QA status, SESP requirements, SESP status, project identification number, and approval date. The aim is to maintain a dataset where each row uniquely represents a distinct project, setting the stage for precise analysis.
2. **Filtering by Bureau**: Initially, we select projects that are part of specific bureaus, namely "RBA," "RBAP," "RBAS," "RBLAC," "CB," "BPPS," and "RBEC."&#x20;
3. **Further Filtering for SESP Required and Active Projects**: Among the projects filtered by bureau, we apply additional criteria to focus on those that:
   * Are marked as requiring SESP (`isSESP_Required` == 1), indicating that they must undergo Quality Assurance processes based on predefined standards or conditions.
   * Are currently active (`isActive` == 1), meaning the project is ongoing or has not been concluded or cancelled.
4. **Excluding Projects Based on SESP Status**: From the filtered set, we further exclude projects with an SESP status of  `Exepted`, `Not Monitored`, `Not Required` . This exclusion ensures we focus on projects genuinely engaged with the SESP process beyond mere administrative categorization, emphasizing those under evaluation or awaiting completion.
5. **Identifying Unique Projects**: After applying these filters, we count the number of unique projects by their `ProjectNum_Unified` identifier. This final step provides the total count of distinct projects meeting all the specified criteria.

Once we have done this, we can calculate the completion rate using the following formula: This counts the `Pending` status as "incomplete'.

The % of eligible projects =  the points of the indicator.&#x20;

* Green = 100
* Yellow = <90
* Red = >90

\










