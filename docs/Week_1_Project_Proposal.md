# WEEK 1 — PROJECT PROPOSAL / CHARTER

## Project Title

**Improving Municipal Service Delivery Through Data Analytics**

**Project:** Municipal Service Analytics Capstone  
**Student:** Onyemachi Joshua Ndubuisi  
**Project Duration:** 8 Weeks  
**Tools:** Python, Pandas, Jupyter Notebook, Matplotlib, Seaborn, Streamlit, GitHub

---

## 1. Executive Summary

Municipal governments receive service requests relating to infrastructure, sanitation, maintenance, public facilities, and other community needs. Effectively managing these requests requires an understanding of service demand, departmental performance, geographic distribution, and data quality.

This project will analyze a dataset containing 2,000 municipal service requests to identify operational patterns and opportunities for improving service delivery.

The analysis will focus on request volumes, resolution times, priority levels, geographic distribution, monthly trends, and data inconsistencies.

Python will be used for data preparation, exploratory analysis, and performance measurement. The findings will support the development of an interactive dashboard and a final report containing evidence-based recommendations.

The dataset is user-provided and is not identified as an official extract from any particular municipality.

---

## 2. Business Problem

Municipal service delivery teams require accurate information to understand where demand is highest, which departments experience longer resolution times, and whether urgent requests receive appropriate attention.

Without consistent analysis, municipal administrators may struggle to:

- Identify high-volume service categories.
- Compare operational performance across departments.
- Understand the handling of high-priority requests.
- Identify geographic concentrations of service demand.
- Monitor changes in request volumes over time.
- Detect inaccurate or inconsistent service records.

These challenges can affect operational planning, resource allocation, and management reporting.

This project addresses these challenges through descriptive data analysis and clearly defined performance indicators.

---

## 3. Project Aim

The primary aim of this project is to use municipal service request data to evaluate service demand, operational performance, geographic patterns, and data quality.

The analysis will provide actionable information to support municipal management decisions.

---

## 4. Business Questions

The project will answer the following six questions:

**Question 1: Service Demand**

Which municipal service request categories have the highest recorded volumes?

**Question 2: Departmental Performance**

How do valid service request resolution times compare across municipal departments?

**Question 3: Priority Handling**

How do high-priority requests compare with medium- and low-priority requests in terms of recorded resolution duration and completion status?

**Question 4: Geographic Distribution**

Which municipal districts generate the highest volumes of recorded service requests?

**Question 5: Demand Trends**

How does municipal service request volume change across months?

**Question 6: Data Quality**

What inconsistencies exist between service request status and closure dates, and how might these affect performance reporting?

---

## 5. SMART Objectives and Success Measures

The following objectives will guide the analysis.

### Objective 1: Analyze Service Demand

By the end of Week 4, calculate the total number and percentage distribution of service requests across all recorded service categories.

**Success Measure:** Produce a ranked category summary and at least one visualization showing service demand.

### Objective 2: Evaluate Departmental Resolution Performance

By the end of Week 5, calculate and compare valid resolution durations for each department.

**Success Measure:** Produce a departmental comparison showing the number of valid completed requests and average and median resolution duration.

### Objective 3: Assess Priority Handling

By the end of Week 5, compare resolution duration and recorded completion status across priority groups.

**Success Measure:** Produce a priority-level summary table and supporting visualization.

### Objective 4: Identify Geographic Demand Patterns

By the end of Week 4, calculate request volumes by district and examine their relationship with recorded geographic coordinates.

**Success Measure:** Produce a district-level ranking and identify any geographic data inconsistencies requiring further investigation.

### Objective 5: Examine Monthly Request Trends

By the end of Week 4, aggregate service requests by opening month.

**Success Measure:** Produce a monthly trend chart showing changes in recorded service demand.

### Objective 6: Evaluate Data Quality

By the end of Week 3, identify missing values, duplicate request identifiers, invalid dates, and inconsistencies between request status and closure dates.

**Success Measure:** Produce a documented data quality assessment containing issue counts, percentages, and proposed handling rules.

### Objective 7: Communicate Findings

By the end of Week 8, develop a dashboard, final report, and presentation summarizing the findings.

**Success Measure:** Deliver the completed analysis, documented methodology, interactive dashboard, and management recommendations through the project repository.

---

## 6. Stakeholder Identification and Decision Support

| Stakeholder | Information Required | Decisions Supported |
|---|---|---|
| Municipal Administration | Overall demand, service performance, and trends | Identify operational priorities and areas requiring management attention |
| Department Managers | Departmental workloads and resolution durations | Review workflow efficiency and investigate performance differences |
| Service Delivery Coordinators | Request categories, priorities, and completion status | Improve request monitoring and escalation processes |
| Operations Planning Team | Geographic demand and monthly trends | Identify locations and periods requiring further capacity assessment |
| Data Governance and IT Teams | Missing values, inconsistent statuses, and date errors | Improve data validation, reporting accuracy, and record management |
| Community Service Leadership | High-level service indicators and geographic patterns | Communicate service delivery challenges and improvement priorities |

The analysis will support operational decision-making but will not establish that staffing levels or specific management practices caused observed performance differences.

---

## 7. Dataset Description

The project will use the file:

**`Municipal_Service_Data.csv`**

The dataset contains:

- **2,000 service request records**
- **11 original data fields**

The fields describe service request identifiers, service categories, responsible departments, priority levels, request statuses, opening and closing timestamps, districts, and geographic coordinates.

Each row represents one recorded municipal service request.

A separate data dictionary will document all 11 original columns, including their descriptions, data types, and quality considerations.

### Data Source

The dataset was provided for the capstone project. Its provenance, licensing, and relationship to an actual municipal government have not been independently established.

Therefore, findings will be presented as analysis of the supplied dataset rather than verified performance statistics for a named city.

---

## 8. Planned Key Performance Indicators

Seven KPIs will be developed during the project.

| KPI | Definition | Calculation |
|---|---|---|
| 1. Total Service Requests | Total number of recorded requests | Count of request records |
| 2. Request Volume by Category | Number and proportion of requests within each category | Category count ÷ total requests × 100 |
| 3. Average Resolution Duration | Average elapsed time between opening and closing for valid completed requests | Mean of valid closure date minus opening date |
| 4. Median Resolution Duration | Typical elapsed resolution duration, less affected by extreme values | Median of valid completed request durations |
| 5. Recorded Completion Rate | Percentage of requests recorded as closed | Requests with status Closed ÷ total requests × 100 |
| 6. High-Priority Resolution Duration | Resolution duration for valid completed high-priority requests | Mean and median duration for valid high-priority completed requests |
| 7. Status–Closure Date Inconsistency Rate | Percentage of records with contradictory status and closure-date information | Inconsistent records ÷ total requests × 100 |

Additional supporting analysis will include request volumes by district, department, priority, and month.

### KPI Interpretation

Resolution durations will only be calculated for records with valid opening and closing timestamps that meet the documented completion rules.

The recorded completion rate will be clearly distinguished from the proportion of requests with valid closure timestamps.

Any inconsistencies will be reported rather than silently excluded from the analysis.

---

## 9. Analytical Methodology

The project will follow six analytical stages.

### Stage 1: Data Understanding

- Import the dataset into Python.
- Examine dataset dimensions and column names.
- Review data types and sample records.
- Identify missing values and duplicate identifiers.
- Document the meaning of each field.

### Stage 2: Data Cleaning

- Standardize column names where necessary.
- Convert date fields into appropriate datetime formats.
- Investigate missing and invalid timestamps.
- Identify inconsistent status and closure-date combinations.
- Document all cleaning decisions.
- Preserve the original dataset.

### Stage 3: Exploratory Data Analysis

- Analyze request categories and frequencies.
- Compare departmental workloads.
- Examine priority distributions.
- Investigate geographic demand patterns.
- Analyze monthly request trends.
- Produce charts and summary tables.

### Stage 4: KPI Development

- Calculate the seven planned KPIs.
- Apply consistent calculation rules.
- Compare performance across relevant groups.
- Validate KPI outputs against source records.

### Stage 5: Dashboard Development

- Develop an interactive dashboard using Streamlit.
- Display major KPIs and operational charts.
- Include filters where supported by the data.
- Present clear labels and methodological limitations.

### Stage 6: Reporting and Recommendations

- Summarize the most important findings.
- Identify operational areas requiring further investigation.
- Develop evidence-based management recommendations.
- Prepare the final report and presentation.

---

## 10. Tools and Technologies

| Tool | Purpose |
|---|---|
| Python | Data analysis and automation |
| Pandas | Data cleaning, transformation, and aggregation |
| NumPy | Numerical calculations |
| Matplotlib | Data visualization |
| Seaborn | Statistical and comparative charts |
| Jupyter Notebook | Executable analysis and documentation |
| Streamlit | Interactive dashboard development |
| GitHub | Version control and weekly submissions |
| Markdown | Project documentation |

---

## 11. Project Scope

### In Scope

The project will examine:

- Municipal service request volumes.
- Request category distributions.
- Departmental resolution performance.
- Priority-level comparisons.
- Geographic request distribution.
- Monthly demand trends.
- Missing data and record inconsistencies.
- Operational KPIs and dashboard reporting.

### Out of Scope

The project will not directly measure:

- First-response time.
- Compliance with official service-level agreements.
- Employee productivity.
- Staffing adequacy.
- Financial cost per service request.
- Citizen satisfaction.
- Causal effects of operational policies.

These measures require information that is not available in the supplied dataset.

---

## 12. Data Limitations and Risks

**Missing Closure Dates:** Some requests may not contain valid closure timestamps. These records cannot be used to calculate completed resolution duration.

**Status Inconsistencies:** Some records may contain contradictory status and closure-date information. These issues must be investigated and documented.

**Unknown Data Provenance:** The dataset is not verified as an official municipal extract.

**Limited Operational Variables:** The dataset does not contain staffing, first-response timestamps, financial costs, or official service standards.

**Geographic Accuracy:** District assignments and coordinates may contain inconsistencies requiring validation.

**Interpretation Risk:** Differences between departments or districts should not automatically be interpreted as evidence of poor performance or inadequate staffing.

### Risk Mitigation

The project will preserve the original dataset, document data cleaning rules, validate calculated metrics, and communicate analytical limitations alongside the findings.

---

## 13. Eight-Week Project Delivery Plan

| Week | Milestone | Expected Deliverable |
|---|---|---|
| Week 1 | Project Definition | Project proposal, objectives, stakeholder analysis, KPI plan, and GitHub setup |
| Week 2 | Data Understanding | Data dictionary, dataset profiling, and preliminary quality checks |
| Week 3 | Data Preparation | Cleaned dataset, documented cleaning decisions, and validation checks |
| Week 4 | Exploratory Data Analysis | Category, department, priority, geographic, and monthly trend analysis |
| Week 5 | KPI Development | KPI calculations, definitions, and comparative performance analysis |
| Week 6 | Operational Diagnostics | Investigation of performance differences and data quality implications |
| Week 7 | Dashboard Development | Interactive Streamlit dashboard |
| Week 8 | Final Reporting | Final analytical report, presentation, and completed GitHub repository |

---

## 14. Expected Outcomes

At the end of the project, the expected outputs are:

1. A structured and documented municipal service request dataset.
2. A reproducible Python analysis notebook.
3. A data dictionary covering all original fields.
4. Seven clearly defined operational KPIs.
5. Visualizations of request demand and resolution performance.
6. An interactive dashboard.
7. A final report containing findings, limitations, and recommendations.
8. A GitHub repository documenting the eight-week project.

The findings are expected to help municipal managers identify workload concentrations, investigate service delivery differences, improve data quality controls, and prioritize further operational reviews.

---

## 15. AI-Assisted Work Disclosure

AI-assisted tools were used to support the organization, drafting, and refinement of project documentation and to assist with analytical planning.

AI-generated suggestions and analytical code must be reviewed, tested, and validated against the supplied dataset before being presented as project findings.

The student remains responsible for understanding the methodology, verifying calculations, interpreting results, and ensuring the accuracy of submitted work.

---

## 16. Conclusion

This project will apply data analytics to evaluate municipal service demand, departmental resolution performance, priority handling, geographic patterns, and data quality.

Through systematic data preparation, exploratory analysis, KPI development, and dashboard reporting, the project will provide a structured evidence base for municipal service delivery decisions.

The completed capstone will demonstrate practical skills in Python, data quality assessment, performance analytics, visualization, and communicating findings to operational stakeholders.
