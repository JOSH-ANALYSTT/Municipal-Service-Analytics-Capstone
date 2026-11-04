# Week 1 — Project Proposal / Charter

## Project title
Improving Municipal Service Delivery Through Data Analytics

## Organizational context and problem
A hypothetical municipal administration needs a consistent evidence base to understand citizen requests, department turnaround, district demand, priority handling, and records quality. The source dataset is user-provided and not identified as an official extract from any particular city.

## Objectives and stakeholder questions
1. Rank service request categories by demand.
2. Compare valid resolution duration across departments.
3. Compare high-priority requests with other priorities.
4. Identify districts with highest recorded request volume.
5. Describe monthly demand patterns.
6. Identify closure status/date inconsistencies that undermine reporting.

## Data source and feasibility
`Municipal_Service_Data.csv`: 2,000 rows and 11 fields, including request ID, service type, department, priority, status, opened/closed dates, district and coordinates. The dataset has no first-response timestamp, service standard or staffing data; response time, SLA compliance and staffing causality cannot be measured.

## Methodology
Python/Pandas for profiling and preparation, descriptive grouping and charts for exploration, well-defined KPIs and cross-tab diagnostics, Streamlit for dashboard, PDF and PowerPoint for final communications.

## Expected decision support
Identify workload concentrations, valid turnaround comparisons, data-entry control issues, and candidates for capacity reviews. Recommendations will be framed as tests and management actions, not causal findings.

## Delivery
Eight GitHub milestones: project charter; exploration; preparation; EDA; KPIs; diagnostics; dashboard; final report and slides.
