# Greening Moonshot

<table data-header-hidden><thead><tr><th width="289"></th><th></th></tr></thead><tbody><tr><td>Data Owner</td><td>Anne FernqVist (<a href="mailto:anne.fernqvist@undp.org">anne.fernqvist@undp.org</a>)</td></tr><tr><td>Availability in Data Warehouse</td><td>Available</td></tr><tr><td>Data Refresh Rate</td><td>Yearly</td></tr><tr><td>Accountability Weighted Scoring</td><td>30%</td></tr></tbody></table>

## Introduction

[The UNDP Environmental Management Tool (EMT)](https://app.powerbi.com/groups/me/reports/a7ff2749-e24a-4bb8-bb7a-e0147fd7f8df/ReportSection?ctid=b3e5db5e-2944-4837-99f5-7488ace54319\&experience=power-bi) methodology follows international standards like the GHG (GreenHoues Gas) Protocol to measure UNDP's carbon footprint across facilities, vehicles, and travel. The assessment scope includes emissions from activities paid for and controlled by UNDP like office utilities, vehicle fuels, staff travel, etc. It excludes project activities by external entities.UNDP facilities data covers main offices, and other offices are extrapolated based on the number of personnel. Shared offices are prorated based on UNDP's share.

The main categories of emissions are:

* Air travel
* Electricity
* Vehicle fuel use
* Refrigerants
* Heating
* Public transport

You can read the full methodology for EMT here:

{% file src="../../.gitbook/assets/EMT methodology.pdf" %}

## Organisational Objective

The Greening Moonshot aims to reduce UNDP’s total carbon emissions by 50% by 2030 compared to 2018. This requires reducing the three main categories of Facility Electricity, Vehicle Fuels, and Air Travel by 55%.

## Data

The data export contains the following columns:

1. **Report\_Title\_Office**: This column contains the title of the report and the name of the office for which the data is being reported.
2. **year**: This column indicates the year in which the data was reported.
3. **bureau**: This column specifies the bureau within UNDP that the office belongs to. .
4. **category**: This column denotes the category of emissions or activity being reported such as air travel, electricity, heating, public transport, refrigerants, and vehicle fuel use.
5. **amt**: This column represents the amount of emissions or activity measured in terms of CO2 equivalent (tCO2e) for emissions.
6. **office\_facility\_id**: This column provides a unique identifier for the office facility.
7. **office\_name**: This column contains the name of the office.
8. **office\_unit**: This column lists the unit or division within the office.
9. **property\_address**: This column provides the address of the office facility.
10. **parent\_category**: This column specifies the broader category under which the specific category of emissions or activity falls, such as Travel GHG Emissions, Facility GHG Emissions, or Vehicle GHG Emissions.
11. **indicator**: This column indicates whether the data is reported or prorated.

While the data is available in the UNDP Data Warehouse, the data is taken from the EMT Dashboard (i.e. PowerBI) because there are custom business rules applied on top of the raw data, and we do not want to have to update the Performance App each time the business rules change. Therefore, the EMT Dashboard hold the master business rules for the Greening Moonshot reporting.

## Data Export

{% hint style="danger" %}
This has not yet been defined.
{% endhint %}

## Calculation of Scoring

To track annual progress towards the 2030 target, a linear reduction trendline is plotted from the 2018 baseline to the 2030 goal of 50% reduction:

<figure><img src="../../.gitbook/assets/UNDP Greening Moonshot Trendline.png" alt=""><figcaption><p>50% linear reduction trendline from 2018 baseline to 2030. </p></figcaption></figure>

Each year, the maximum allowed carbon footprint level will be identified based on this linear reduction trendline. If the total carbon footprint is below this trendline-based maximum level in any given year, then the full score of 100 points will be awarded.

However, for every 1% that the actual annual total carbon emissions exceeds the maximum level allotted for that year as per the linear reduction trendline, 2 points will be deducted from the total possible score of 100.

We can provide an example for 2022:

* To stay within the trendline for the 2030 target, the 2022 target was a maximum of 52,184 tCO2e.
* The actual 2022 carbon footprint was 52,535 tCO2e
* So the actual emissions were 52,535 - 52,184 = 351 tCO2e higher than the trendline maximum
* 351 tCO2e is 0.67% higher than the trendline maximum (351/52,184 = 0.0067 i.e. 0.67%)
* As per the methodology, for every 1% above the maximum, 2 points are deducted
* Therefore, the score would be:
  * 100 points (max)
  * 0.67% above the maximum
  * 0.67 rounded up is 1%
  * 2 points deducted for being 1% above the maximum
  * So the total score is 100 - 2 = 98 points



## Traffic Light System

| Traffic Light | Score |
| ------------- | ----- |
| Green         | 100+  |
| Yellow        | 90+   |
| Red           | <90   |



