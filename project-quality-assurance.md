# Project Quality Assurance

For historical reasons, the SESP and PQA Data are stored together.

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

## PQA Statuses

1. **Exempted**
2. **Completed**
3. **Not Required**
4. **Pending**
5. **Ongoing**



## Calculation Methodology&#x20;

1. **Filtering out Outputs:**  The initial step involves removing duplicate project records to adhere to the "Quantum" data management approach, transitioning from the "Atlas" method's one-row-per-project standard. This deduplication ensures each project is uniquely represented by eliminating redundancies based on specific attributes. These attributes include the project's operating unit, overseeing bureau, activity status, year of data entry, quality assurance eligibility and requirements, QA status, SESP requirements, SESP status, project identification number, and approval date. The aim is to maintain a dataset where each row uniquely represents a distinct project, setting the stage for precise analysis.
2. **Filtering by Bureau**: Initially, we select projects that are part of specific bureaus, namely "RBA," "RBAP," "RBAS," "RBLAC," "CB," "BPPS," and "RBEC."&#x20;
3. **Further Filtering for QA Required and Active Projects**: Among the projects filtered by bureau, we apply additional criteria to focus on those that:
   * Are marked as requiring QA (`isQA_Required` == 1), indicating that they must undergo Quality Assurance processes based on predefined standards or conditions.
   * Are marked as eligible for QA (`isQA_Eligible` == 1), indicating that they must undergo Quality Assurance processes based on predefined standards or conditions.
   * Are currently active (`isActive` == 1), meaning the project is ongoing or has not been concluded or cancelled.
4. **Excluding Projects Based on QA Status**: From the filtered set, we further exclude projects with an QA status of  `Exepted`,  `Not Required` . This exclusion ensures we focus on projects genuinely engaged with the QA process beyond mere administrative categorization, emphasizing those under evaluation or awaiting completion.
5. **Identifying Unique Projects**: After applying these filters, we count the number of unique projects by their `ProjectNum_Unified` identifier. This final step provides the total count of distinct projects meeting all the specified criteria.
6. **Define Complete and Incomplete:**
   1. Complete: We considered a PQA as "Complete" if the QA Status is  `Complete`and ApprovedDate within the last two years.
   2. Incomplete:  The sum of `Pending` and `Ongoing` QA statuses as "Incomplete'.
7. **Calculating QA Completion Rate:** To calculate the completion rate, we need to determine the total number of projects and the proportion of completed projects. The completion rate is usually expressed as a percentage and can be calculated using the following formula: Completion Rate (%) = (Number of Complete Projects / Total Number of Projects) \* 100



