# Municipal Service Delivery Analytics — Eight-Week Capstone

**Consulting objective:** Identify service demand, resolution performance, geographic and time patterns, and data-quality bottlenecks in municipal service requests.

**Dataset:** User-supplied `Municipal_Service_Data.csv` (2,000 records, 11 original columns). Original municipality, provenance and license not specified; avoid attributing results to a named city.

**Business questions:** Which service categories are most requested? Which departments have higher turnaround times? How do urgent requests compare? Which districts have most requests? What monthly patterns exist? Where do workflow and data-quality bottlenecks occur?

**Workflow:** Week 1 charter; Week 2 exploration; Week 3 preparation; Week 4 EDA; Week 5 KPIs; Week 6 diagnostics; Week 7 dashboard; Week 8 report and slides. Weekly ZIP submissions are in `weekly_submissions/`.

**Run:** `pip install -r requirements.txt`; open `notebooks/capstone.ipynb` from repository root; `streamlit run dashboard/app.py`.

**Findings:** 2,000 requests; 1,198 Closed statuses; 1,100 valid completed durations; mean 7.33 days; 813 status/closure-timestamp mismatches. Top category: Noise Complaint (245); top district: South (422).

**Important limitations:** First response timestamps and SLA thresholds are absent; no response-time/SLA claim is supported. The dataset cannot establish causes of staffing shortages. Date/status conflicts are flagged, not silently fixed.

**GitHub:** Create a repository and push this directory. Commit weekly changes as you work; a prepared archive is not proof of an eight-week commit history. Capture your own GitHub structure screenshot. Publish dashboard separately to obtain a public URL.
