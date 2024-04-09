# Integrated Financial Dashboard (IFD)

| Data Owner                      | Amat Kebbeh ([amat.o.kebbeh@undp.org](mailto:amat.o.kebbeh@undp.org)), BMS OFRM |
| ------------------------------- | ------------------------------------------------------------------------------- |
| Availability in Data Warehouse  | Not Available                                                                   |
| Data Refresh Rate               | Quarterly                                                                       |
| Accountability Weighted Scoring | 40%                                                                             |

UNDP introduced the IFD in July 2020 to provide an integrated view of financial management performance for Country Offices. It replaces previous separate dashboards for finance, IPSAS, assets, etc.

The goal is to help Country Offices effectively manage financial risks and deliver programs, without needing to monitor multiple dashboards.

There are currently 3 pillars. Each has specific metrics with defined criteria for scoring points.

1. **Program Financial Performance (25 points)**
   1. Program Utilization: Measures performance against milestones
   2. Non-Core Resources Mobilization: Measures mobilization against milestones
   3. Project Closure: Tracks operationally closed projects
2. **Institutional Budget Efficiency (15 points)**
   1. IB Resources Collection: Measures collection against milestones
   2. Delivery Efficiency Ratio: Compares IB and program utilization
3. **Audit (10 points)**
   1. CO/GFATM/DIM/HACT Audit Ratings: Looks at audit ratings
   2. Outstanding Recommendations: Tracks unimplemented recommendations.

Countries are scored out of 50 points. Points are totalled for a Country Office and mapped:

* Acclaim: >= 40 points
* Satisfactory: 39-35 points
* Concern: 34-28 points
* Critical: <= 27 points

Audit ratings can override the calculated rating if unsatisfactory audits and unimplemented recommendations exist. Emerging risks not captured in the dashboard can also override the rating.

The IFD was updated after the Quantum implementation in 2023 to reflect more robust risk management and retire some legacy indicators. New indicators will be added going forward.

## Calculation of Scoring

Historically, the indicator was scored out of 100 before 2023 and 50 from 2023, but we have normalised all years to 100 to keep everything comparable.

Countries are scored out of 50 points. Points are totalled for a Country Office and mapped:

* Acclaim: >= 80 points
* Satisfactory: 79-70 points
* Concern: 69-56 points
* Critical: <= 56 points

Each CO is scored per the IFD methodology, and the overall indicator score is a global average of all countries for the year.

The traffic light indicator methodology for this indicator is:

* Green = 70+
* Yellow = 56+
* Red = <56

### Pillar Calculation

Here's how you can score each individual pillar based on the percentage used for the overall score, adapted to the points allocated to each pillar:

1. **Program Financial Performance (25 points)**
   * Acclaim: >= 20 points (80% of 25)
   * Satisfactory: 19-17 points (76%-68% of 25)
   * Concern: 16-14 points (64%-56% of 25)
   * Critical: <= 13 points (52% of 25 or less)
2. **Institutional Budget Efficiency (15 points)**
   * Acclaim: >= 12 points (80% of 15)
   * Satisfactory: 11-10 points (73%-67% of 15)
   * Concern: 9-8 points (60%-53% of 15)
   * Critical: <= 7 points (47% of 15 or less)
3. **Audit (10 points)**
   * Acclaim: >= 8 points (80% of 10)
   * Satisfactory: 7 points (70% of 10)
   * Concern: 6-5 points (60%-50% of 10)
   * Critical: <= 4 points (40% of 10 or less)

{% hint style="info" %}
Note that we have rounded the percentages and points to the nearest whole number for simplicity.&#x20;
{% endhint %}
