# Municipal Service Delivery Analytics — Capstone Proposal

**Prepared by:** Onyemachi Joshua Ndubuisi  
**Program:** Data Analyst Capstone  
**Prepared for:** City Administration (hypothetical client)  
**Date:** 20 November 2026  
**Submission:** Revised Week 1 proposal responding to supervisor feedback

## Background and business problem
Municipal administrators need to understand what residents request, how quickly departments close requests, whether urgent requests receive timely handling, and which districts experience demand. The capstone program provided a dataset of 2,000 request records with service categories, departments, priority, status, opening and closing dates, district and coordinates. The source municipality and license are unspecified; the data must not be represented as official results for any named city.

The City Manager, operations director and department managers lack a consistent view of service demand and resolution speed. This can lead to poorly targeted reviews, avoidable backlogs, and unverified claims about service performance. No actual monetary cost can be quantified from these data because staffing hours, budgets and cost fields are absent. The data also lack first-response timestamps and official SLA targets; these gaps constrain rather than invalidate the client's questions.

## Stakeholders and decisions
| Stakeholder | Decision supported | Questions |
|---|---|---|
| City Manager | Prioritize reviews of departments with slower resolution and potential resource reallocation; staffing decisions require further evidence. | Q2, Q6 |
| Service Operations Director | Decide which categories need process review or triage changes. | Q1, Q6 |
| Department Managers | Examine backlog and priority-based resolution times before scheduling crews. | Q2, Q3, Q6 |
| Geographic Planning Lead | Prioritize investigation of higher-volume districts; avoid per-capita claims without population data. | Q4, Q5 |
| Data Governance Lead | Commission reconciliation of status/date contradictions and improve field validation. | Q2, Q3, Q6 |

## Six client questions and measurable objectives
| # | Client question | Measurable objective | Available fields |
|---|---|---|---|
| Q1 | Which service categories have the highest volume? | Count requests by category; rank all nine and report the top three and their shares. | `Request_Type, Service_Request_ID` |
| Q2 | What are the average response and resolution times by department? | Calculate mean, median and 90th-percentile resolution days for valid closed requests by department; flag median >20% above overall median. Report response time as not measurable. | `Department, Date_Opened, Date_Closed, Status` |
| Q3 | Are urgent requests handled within acceptable timeframes? | Compare High/Critical resolution durations with illustrative thresholds (Critical 2 days; High 5 days); test sensitivity at ±50%. Never label these official SLAs. | `Priority_Level, Status, Date_Opened, Date_Closed` |
| Q4 | Which geographic districts have the highest demand? | Count requests per district; compare each district share with the equal-share reference of 20%, flag >25%. | `Ward_District, Service_Request_ID` |
| Q5 | Are there seasonal or time-based patterns in service requests? | Count requests by calendar month and year; flag months >20% above the monthly average, noting only two years of data. | `Date_Opened` |
| Q6 | Where do delays or bottlenecks occur in the request lifecycle? | Compare backlog and valid resolution times by department/category; quantify status/closure-date conflicts and flag >10% mismatch. Lifecycle stages beyond open/close cannot be isolated. | `Status, Date_Opened, Date_Closed, Department, Request_Type` |


## Draft KPIs (to refine in Week 5)
| Draft KPI | Definition | Decision relevance | Illustrative threshold / caveat |
|---|---|---|---|
| Closure status rate | Count(Status = Closed) / total requests | Snapshot of workload state | Monitor; not equivalent to verified completion |
| Verified resolution median | Median(Date_Closed - Date_Opened) for Status = Closed AND valid dates | Typical duration by department | Flag department >120% of overall median |
| 90th-percentile resolution | P90 of same eligible duration subset | Detect slow tail | Compare across departments; no official target |
| Priority timeliness (scenario) | Eligible Critical/High cases within hypothetical threshold / eligible Critical/High cases | Test urgent handling | Critical ≤2 days; High ≤5 days; ±50% sensitivity; not SLA compliance |
| Unresolved status share | Count(Status in Open, In Progress) / total | Backlog proxy | Flag >40% for review; snapshot, not aged backlog |
| Status/date conflict rate | Count(Closed without close date OR non-Closed with close date) / total | Trustworthiness of performance data | Flag >10%; data stewardship priority |
| Request volume by district | Count(requests in district) / total | Geographic workload distribution | Flag >25% share as a screening heuristic, not capacity proof |


## Expected insights and deliverables
The work will quantify demand mix, departmental resolution differences, a scenario-based view of urgent timeliness, district and monthly volumes, and conflicts between closure dates and status. The deliverables are a reproducible notebook, raw and processed datasets, data dictionary, an interactive dashboard, a final report and presentation. Interpretations will be descriptive and diagnostic, not causal; no staffing shortage or service-level breach can be established from the available fields.

## Assumptions, data risks and controls
The unit of analysis is one service request ID. A recorded closed status with no closure timestamp, or a non-closed status with a timestamp, will be flagged without silent correction. Duration KPIs use only status-closed records with valid chronological timestamps; excluded records and denominators will be disclosed. Department/category relationships and district/coordinate consistency will be audited. Proposed priority thresholds are **illustrative scenarios, not official city commitments**. Their sensitivity will be tested before recommendations are made. Geographic volumes are not adjusted for population.

## Methods, tools and schedule
Use Python, pandas, NumPy, Jupyter, Matplotlib and Seaborn for profiling and analysis. Week 1: scope and repository; Week 2: exploration, data dictionary and cross-field audits; Week 3: reproducible cleaning and flags; Week 4: exploratory visualizations; Week 5: KPI validation; Week 6: diagnostic comparisons; Week 7: dashboard; Week 8: report and slides. Commit changes throughout the work and tag weekly milestones.

## AI assistance and verification
OpenAI ChatGPT assisted with drafting, Python notebook construction, analysis packaging and revision against supervisor feedback. Numerical observations were checked by executing code against the provided CSV; all conclusions remain subject to student review and supervisor discussion. Earlier `SUBMISSION_INSTRUCTIONS.md` and `WEEK_2_SUBMISSION_GUIDE.md` were also AI-assisted guidance files. They are not independent evidence of student work and should be retained for provenance until discussed with the supervisor.
