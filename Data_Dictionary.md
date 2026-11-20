# Data Dictionary — Municipal Service Requests

One row represents one recorded municipal service request, identified by `Service_Request_ID`. Raw text timestamps are parsed to datetimes in analysis; the raw CSV is unchanged.

| Column | Type (raw → analysis) | Meaning | Example | Missing | Distinct non-null values | Quality notes |
|---|---|---|---|---:|---:|---|
| `Service_Request_ID` | text → category/text | Unique identifier for a service request | SR00001 | 0 | 2,000 | No missing values; verify business meaning with client. |
| `Request_Type` | text → category/text | Category of municipal issue | Garbage Collection | 0 | 9 | Nine types; counts range 206–245, relatively even. |
| `Description` | text → category/text | Free-text issue description | Service request related to municipal operations. | 0 | 1 | Mostly generic text; limited diagnostic value. |
| `Department` | text → category/text | Department assigned to the request | Public Works | 0 | 5 | Every request type occurs across all five departments; assignments require validation against actual business rules. |
| `Priority_Level` | text → category/text | Recorded urgency label | High | 0 | 4 | No missing values; verify business meaning with client. |
| `Status` | text → category/text | Current recorded workflow status | Closed | 0 | 3 | Do not infer closure from Date_Closed; 813 conflicts with date presence. |
| `Date_Opened` | text → datetime | Timestamp request was opened | 2022-04-13 19:00:00 | 0 | 1,901 | 1,901 distinct timestamps among 2,000 rows; 99 repeated timestamp entries, not necessarily duplicate requests. |
| `Date_Closed` | text → datetime | Recorded closure timestamp (may contradict status) | 2022-04-28 08:00:00 | 185 | 1,732 | 185 missing; 98 Closed requests lack a date; 715 non-Closed have a date. |
| `Ward_District` | text → category/text | Recorded geographic district | South | 0 | 5 | District coordinate ranges overlap strongly; boundaries not provided. |
| `Latitude` | float → numeric | Recorded latitude coordinate | 49.233907 | 0 | 1,993 | No missing values; verify business meaning with client. |
| `Longitude` | float → numeric | Recorded longitude coordinate | -123.020945 | 0 | 1,989 | No missing values; verify business meaning with client. |
