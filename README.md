# Call Center Performance Analysis | Power BI

## Project Overview

This project analyzes call center operational performance for **January
2026**, focusing on service level, call demand, staffing capacity,
schedule adherence, and interval-level workforce gaps.

The goal was to transform raw operational data into an interactive
**five-page Power BI report** that helps stakeholders monitor
performance, identify service-level deterioration, investigate staffing
gaps, and prioritize operational interventions.

## Business Problem

Call center demand changes throughout the day, meaning staffing levels
that appear adequate at an aggregate level may still leave specific
intervals or queues understaffed.

The analysis was designed to answer:

* How is the call center performing overall?
* When does service-level performance deteriorate?
* Are scheduled staffing levels aligned with demand?
* Which queues experience the greatest SLA pressure?
* Which intervals have the largest staffing gaps?
* What operational conditions coincide with poor SLA performance?
* What actions should workforce and operations teams prioritize?

## Dataset

The dataset contains interval-level call center records for January
2026.

Key fields include:

\-----------------------------------------------------------------------------

Field                               Description

\-----------------------------------------------------------------------------

Date                                Date of the operational record

Day                                 Day of the week

Interval                            Operating time interval

Queue                               Service queue

Calls Offered                       Calls presented to the queue

Calls Answered                      Calls answered

Calls Abandoned                     Calls abandoned

Service Level %                     Percentage of calls meeting the SLA
definition

AHT Seconds                         Average Handle Time

Required Staff                      Calculated staffing requirement

Scheduled Staff                     Agents scheduled

Adherence %                         Schedule adherence

Effective Staff                     Effective staffing measure
available in the dataset
---

## Data Preparation \& Validation

Data preparation was performed using **Power Query**.

* Converted the Date field from Date/Time to Date.
* Reviewed and validated column data types.
* Created a duplicate-check query.
* Confirmed a record count of **1 for every row**, indicating no
duplicate operational records were identified.
* Created a call-volume validation check and found no mismatches.
* Reviewed Service Level % against the **85% SLA target**.
* Investigated positive and negative staffing-gap values.
* Reviewed adherence values, which ranged from approximately **72% to
99%**.
* Created supporting Date, Queue, and Interval dimension tables.

## Data Model

The report uses a dimensional model consisting of:

**Fact table:** Call Center Data

**Dimension tables:** Dim Date, Dim Queue, Dim Interval

The model supports consistent filtering, aggregation, and analysis
across dates, queues, and operating intervals.

## Key KPIs

KPI                                    Result

\---

Total Calls Offered                **96,506**
Average Service Level               **87.4%**
SLA Target                            **85%**
Abandon Rate                         **2.5%**
Average AHT                 **426.9 seconds**
Cumulative Staffing Gap               **311**
SLA Breach Intervals                **1,437**
Minimum Interval SLA                  **55%**
Average Adherence                   **\~90%**

Although overall SLA was above target, the operation experienced
substantial interval-level variation. This demonstrates why aggregate
KPIs should be complemented by intraday and queue-level analysis.

## DAX \& Analytical Measures

The report includes measures for:

* Total Calls Offered
* Average Service Level %
* Abandon Rate %
* Average AHT
* Cumulative Staffing Gap
* Minimum Interval SLA %
* SLA Breach Intervals
* Total Required Staff
* Total Scheduled Staff
* Average Adherence %

## Dashboard Structure

### Page 1 --- Executive Overview

**Visuals:** KPI cards; Average Service Level % by Date; Average Service
Level % by Queue; SLA Breach Intervals by Queue; SLA Breach Intervals by
Date.

**Purpose:** Provide a high-level view of overall service and
operational performance.

### Page 2 --- Workforce \& Staffing Analysis

**Visuals:** Cumulative Staffing Gap by Date; Cumulative Staffing Gap vs
Average Service Level; Required vs Scheduled Staff by Date; Cumulative
Staffing Gap by Queue.

**Purpose:** Identify staffing imbalances and understand how workforce
coverage varies across the month.

### Page 3 --- Interval \& Root-Cause Analysis

**Visuals:** Average Service Level % by Interval; Required vs Scheduled
Staff by Interval; Staffing Gap by Interval; Total Calls Offered by
Interval.

**Purpose:** Identify intraday demand peaks, staffing shortfalls, and
periods of service deterioration.

### Page 4 --- Adherence \& Worst Performance Observations

**Visuals:** Average Adherence % by Interval; Worst SLA Observations
table; Worst Staffing Observations table.

**Purpose:** Enable targeted investigation of individual operational
observations requiring attention.

### Page 5 --- Business Insights \& Recommended Actions

**Sections:** Key Findings; Recommendations; Analyst Key Takeaway.

**Purpose:** Translate analytical findings into practical workforce and
operational actions.

## Key Findings

1. Overall Service Level was **87.4%**, above the **85% target**.
2. **1,437 intervals** fell below the SLA target.
3. Technical Support recorded the highest number of SLA breach
intervals among the analyzed queues.
4. Several poor-performing observations occurred when scheduled
staffing was below calculated staffing requirements.
5. **2:30 PM** emerged as an important SLA hotspot, with repeated
low-SLA observations, including observations as low as **55%**.
6. Average adherence remained around **90%**, indicating that adherence
alone does not explain SLA deterioration.

## Recommendations

### Rebalance intraday staffing

Review recurring intervals where staffing requirements exceed scheduled
capacity and adjust workforce coverage accordingly.

### Investigate Technical Support

Conduct a queue-level review of Technical Support, considering staffing
capacity, call volume, AHT, call complexity, and scheduling patterns.

### Strengthen intraday monitoring

Monitor staffing requirements and SLA throughout the day instead of
relying solely on daily or monthly averages.

### Review staffing by queue

Evaluate workforce requirements at queue level because aggregate
staffing figures can conceal queue-specific shortages.

### Investigate recurring SLA hotspots

Use the Worst SLA Observations table to investigate recurring dates,
intervals, and queues associated with poor service performance.

### Continue monitoring adherence

Keep adherence as a workforce-management indicator, but evaluate it
alongside demand, staffing requirements, AHT, and SLA.

## Analyst Takeaway

> \*\*Overall staffing levels do not tell the full story. A positive net
> staffing position can coexist with interval-level understaffing and
> SLA breaches. Workforce decisions should therefore focus on when and
> where staffing gaps occur, rather than relying solely on aggregate
> staffing figures.\*\*

## Data Limitation

The available dataset does not contain a dedicated shrinkage or
available-staff measure.

Therefore, the staffing-gap analysis evaluates **scheduled staffing
against calculated staffing requirements** and does not explicitly model
losses in workforce availability caused by shrinkage.

A future workforce-management project could incorporate shrinkage,
planned and unplanned absence, breaks, training, meetings, available
staff, and effective staff.

## Skills Demonstrated

**Power BI · Power Query · DAX · Data Modelling · Data Cleaning · Data
Validation · KPI Development · Data Visualization · Workforce Analytics
· Root-Cause Analysis · Business Intelligence · Business Communication**

## Repository Structure

```text
call-center-performance-analysis/
├── README.md
├── PowerBI/
│   └── Call_Center_Performance_Dashboard.pbix
├── Screenshots/
│   ├── 01_Executive_Overview.png
│   ├── 02_Workforce_Staffing_Analysis.png
│   ├── 03_Interval_Root_Cause_Analysis.png
│   ├── 04_Adherence_Worst_Observations.png
│   └── 05_Business_Insights_Recommendations.png
└── Documentation/
    └── Project_Case_Study.pdf
```

## Project Status

Completed --- January 2026 Call Center Performance Analysis

