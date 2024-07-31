# Operating Unit Mapping

{% hint style="info" %}
These files require updating.
{% endhint %}

The two files below help to map OUs (Operating Units), such as Country Offices and other offices, to countries and Bureaus. This ensures that the Performance App uses the correct terminologies for each Operating Unit.

{% file src="../.gitbook/assets/country_lookup.xlsx" %}
Provide ISO standards for countries
{% endfile %}

{% file src="../.gitbook/assets/Office to Country Mapper.csv" %}
Mapping Offices to Countries
{% endfile %}

### New Methodology for Operating Unit Mapping

So we want to have the following information as columns:

* **Unofficial List**: Found across various systems, used for matching.
* **Office/Unit**: Official Office Name. Taken from "Operating Unit" from UNDP Data Warehouse table.
* **CODE**: UNDP Official Codes.
* **Country/Unit**: Official Names.
* **Alpha-2 code (ISO)**: ISO Country Codes (2-letter).
* **Alpha-3 code (ISO)**: ISO Country Codes (3-letter).
* **Bureau**: Bureau responsible for the unit.
* **Office Type**: Type of Office (CO, Regional Hub, Regional HQ, Operations, Partnership, Project, Policy, etc)
* **Crisis**: L1/L2/L3 crisis classification.
  * **L1 Emergency Response:** Managed by the Country Office with minimal additional support from headquarters, suitable for situations that can be handled locally with some backstopping.
  * **L2 Emergency Response:** Requires significant organizational support, with the Country Office managing the response but receiving expanded assistance from headquarters and regional offices, directed by a Crisis Board.&#x20;
  * &#x20;**L3 Emergency Response:** Represents a "corporate emergency" demanding organization-wide mobilization, typically activated for crises that overwhelm local and national capacities, requiring exceptional corporate support and the appointment of a Global Emergency Coordinator.
* **World Bank Income Group**: Classification of the country by the World Bank Income Group.
* **United Nations LDC Classification**: Least Developed Country (LDC) classification by the United Nations.
* **Fragility Classification**: Fragility classification according to OECD States of Fragility 2022.
* **SIDS**: Small Island Developing States (True/False).
* **NCC**: Net Contributor Country. &#x20;
* **Country Office Size**: Size of the Country Office (Small/Medium/Large). (more on this below)
* **MCO**: Multi-Country Office (True/False).
* **Main Implementation Modality**: Main method of implementing programs (e.g., National Implementation Modality (NIM), Direct Implementation Modality (DIM), or Mixed). (more on this below)
* **Main Funding Source**: Primary source of funding (e.g., Government, Voluntary Funding (VF), OECD Country).

#### Country Office Size Methodology

* **Small**: Workforce total < 40
* **Medium**: Workforce total between 40 and 150
* **Large**: Workforce total > 150

This includes all workforce types, not just staff.&#x20;

Regardless of the workforce amount

* More than $30M in delivery, they are automatically a **medium** CO regardless of workforce size.&#x20;
* More than $100M in delivery, they are automatically a **large** CO regardless of workforce size. (i.e. Argentina, 75 people with $367M delivery)

#### Main Implementation Modality Methodology

We consider a country office primarily NIM or DIM based on a particular methodology. This is currently under discussion, but there are various considerations:&#x20;

* % of **development** project (i.e. CNT)
* Project size ($)

Steps to approval:

1. Calculate all fields for all units
2. Write one page OPG brief for review.
3. Get comments and update
4. Sign Off
5. **Generate new view in the UNDP Data Warehouse**&#x20;





