# Municipal Service Delivery Analytics — Eight-Week Capstone

**Student:** Onyemachi Joshua Ndubuisi  
**Program:** Data Analyst Capstone  
**Client:** City Administration (hypothetical; no named municipality verified)  
**Current milestone:** Weeks 1–2 revised; Week 3 follows after feedback is resolved.

## Business problem
Municipal leadership needs defensible information about service volume, resolution times, urgent handling, geographic demand and process bottlenecks. Poor visibility can lead to misdirected process reviews and resource-planning decisions. Monetary costs and staffing effects cannot be estimated because the supplied data contain no budgets, labour hours or staffing levels.

## Client's six business questions and measurable objectives
| # | Client question | Measurable objective | Available fields |
|---|---|---|---|
| Q1 | Which service categories have the highest volume? | Count requests by category; rank all nine and report the top three and their shares. | `Request_Type, Service_Request_ID` |
| Q2 | What are the average response and resolution times by department? | Calculate mean, median and 90th-percentile resolution days for valid closed requests by department; flag median >20% above overall median. Report response time as not measurable. | `Department, Date_Opened, Date_Closed, Status` |
| Q3 | Are urgent requests handled within acceptable timeframes? | Compare High/Critical resolution durations with illustrative thresholds (Critical 2 days; High 5 days); test sensitivity at ±50%. Never label these official SLAs. | `Priority_Level, Status, Date_Opened, Date_Closed` |
| Q4 | Which geographic districts have the highest demand? | Count requests per district; compare each district share with the equal-share reference of 20%, flag >25%. | `Ward_District, Service_Request_ID` |
| Q5 | Are there seasonal or time-based patterns in service requests? | Count requests by calendar month and year; flag months >20% above the monthly average, noting only two years of data. | `Date_Opened` |
| Q6 | Where do delays or bottlenecks occur in the request lifecycle? | Compare backlog and valid resolution times by department/category; quantify status/closure-date conflicts and flag >10% mismatch. Lifecycle stages beyond open/close cannot be isolated. | `Status, Date_Opened, Date_Closed, Department, Request_Type` |


## Stakeholders and decisions
| Stakeholder | Decision supported | Questions |
|---|---|---|
| City Manager | Prioritize reviews of departments with slower resolution and potential resource reallocation; staffing decisions require further evidence. | Q2, Q6 |
| Service Operations Director | Decide which categories need process review or triage changes. | Q1, Q6 |
| Department Managers | Examine backlog and priority-based resolution times before scheduling crews. | Q2, Q3, Q6 |
| Geographic Planning Lead | Prioritize investigation of higher-volume districts; avoid per-capita claims without population data. | Q4, Q5 |
| Data Governance Lead | Commission reconciliation of status/date contradictions and improve field validation. | Q2, Q3, Q6 |


## Draft KPI plan
| Draft KPI | Definition | Decision relevance | Illustrative threshold / caveat |
|---|---|---|---|
| Closure status rate | Count(Status = Closed) / total requests | Snapshot of workload state | Monitor; not equivalent to verified completion |
| Verified resolution median | Median(Date_Closed - Date_Opened) for Status = Closed AND valid dates | Typical duration by department | Flag department >120% of overall median |
| 90th-percentile resolution | P90 of same eligible duration subset | Detect slow tail | Compare across departments; no official target |
| Priority timeliness (scenario) | Eligible Critical/High cases within hypothetical threshold / eligible Critical/High cases | Test urgent handling | Critical ≤2 days; High ≤5 days; ±50% sensitivity; not SLA compliance |
| Unresolved status share | Count(Status in Open, In Progress) / total | Backlog proxy | Flag >40% for review; snapshot, not aged backlog |
| Status/date conflict rate | Count(Closed without close date OR non-Closed with close date) / total | Trustworthiness of performance data | Flag >10%; data stewardship priority |
| Request volume by district | Count(requests in district) / total | Geographic workload distribution | Flag >25% share as a screening heuristic, not capacity proof |


## Dataset and limitations
The capstone program provided `data/raw/Municipal_Service_Data.csv`: 2,000 records and 11 columns. Each row is one service request. The original city, license and provenance are unspecified. First-response timestamps, official SLA thresholds, intermediate workflow events and staffing data are absent. Therefore **response times, official SLA compliance, causes of delay, and staffing shortfalls cannot be measured**. Hypothetical priority thresholds are for sensitivity analysis only.

## Reproduce the work
1. Clone this repository and open its root folder.
2. Install Python 3.10+ and run `python -m pip install -r requirements.txt`.
3. Run `jupyter notebook` and open `notebooks/capstone.ipynb`.
4. Run cells top to bottom from the repository root. The notebook reads `data/raw/Municipal_Service_Data.csv` without modifying it.
5. Read `docs/Data_Dictionary.md` and the written observations beside the outputs.

## Project timeline
Week 1: definition; Week 2: exploration; Week 3: cleaning; Week 4: EDA; Week 5: KPIs; Week 6: diagnostic analysis; Week 7: dashboard; Week 8: report and presentation. Update the **same root notebook** each week, rather than creating a nested weekly project.

## Repository layout
```text
README.md
requirements.txt
docs/Week_1_Project_Proposal.md
docs/Data_Dictionary.md
data/raw/Municipal_Service_Data.csv
data/processed/.gitkeep
notebooks/capstone.ipynb
dashboard/dashboard_link.txt
report/.gitkeep
presentation/.gitkeep
assets/.gitkeep
```

## AI and generated-content disclosure
OpenAI ChatGPT helped draft and revise the README and proposal, generate notebook code and explanatory observations, and package submission files. The numerical claims in this revision were cross-checked by running Python against the provided CSV; the student must review, understand, and be able to explain every cell and decision. Earlier `SUBMISSION_INSTRUCTIONS.md` and `WEEK_2_SUBMISSION_GUIDE.md` were generated with AI assistance and should remain disclosed; they are administrative guides, not independently authored analysis. AI assistance is not a substitute for source verification or academic authorship.

## Current feedback status
The Week 1 and Week 2 supervisor feedback requires a repository transfer, repository screenshot, weekly tags and student review. Those **cannot be completed by a downloadable ZIP**; see `docs/RESUBMISSION_STEPS.md`.
