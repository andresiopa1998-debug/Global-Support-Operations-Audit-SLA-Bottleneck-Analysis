# Global Support Operations Audit: SLA & Bottleneck Analysis

## Project Overview
This project audits over 200,000 international customer service tickets to identify routing bottlenecks and assess Service Level Agreement (SLA) compliance. The analysis uncovered a systemic, global operational failure resulting in a uniform ~50% SLA breach rate and an average resolution time of ~120 hours (5 days) across all queues and priority levels.

## Tools & Workflow
* **Python (Pandas):** Data cleaning, missing value handling, and datetime conversions.
* **Google BigQuery (SQL):** Exploratory data analysis and metric engineering.
* **Tableau:** Interactive dashboard design and executive storytelling.
* **AI Assistance (Gemini):** Utilized as a technical sounding board for SQL syntax troubleshooting, Python debugging, and optimizing analytical workflow efficiency.

## Business Objectives
1. Identify which ticket categories or support channels are missing SLAs most frequently.
2. Determine the average resolution time across different operational dimensions (Category, Priority, Channel).
3. Provide actionable intelligence on routing efficiency to senior leadership.

## Methodology
1. **Data Cleaning:** Ingested raw data into Python. Verified data integrity by checking for duplicate `Ticket ID`s. Transformed raw `object` string dates into `datetime` objects to enable time-series viability. Exported the clean data to a CSV.
2. **SQL Aggregations:** Imported the clean CSV into BigQuery. Utilized conditional counting (`COUNTIF`) to calculate true SLA breach percentages without filtering out total volume baseline data. Leveraged `AVG()` functions on pre-calculated resolution metrics to bypass timestamp anomalies.
3. **Dashboard Development:** Engineered calculated fields in Tableau to handle string-to-boolean conversions ("Yes"/"No"). Built a 100% Stacked Bar Chart and a Reference Line bar chart to visually communicate the deviation from standard 24-hour operational goals.

## Key Findings & Strategic Recommendations
* **Global Capacity Crisis:** The data indicates the organization is not suffering from localized routing errors (e.g., a specific department failing). Instead, the uniform 120-hour resolution time across even the highest priority queues indicates a critical, system-wide capacity shortage. 
* **Action Plan:** Immediate action is required to scale global headcount and overhaul the tier-based priority routing logic, which currently fails to expedite high-priority international requests.

## Dashboard
* (https://public.tableau.com/app/profile/andre.siopa/viz/GlobalSupportOperationsSLAResolutionBottleneckAudit/Dashboard1)
