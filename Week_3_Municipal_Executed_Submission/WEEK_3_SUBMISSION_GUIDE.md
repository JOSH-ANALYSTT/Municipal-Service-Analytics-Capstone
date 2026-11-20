# Week 3 — Data Preparation and Cleaning

## Submission contents
- `notebooks/capstone.ipynb` — **executed** Week 1–3 notebook, including Week 3 cleaning steps and outputs.
- `data/raw/Municipal_Service_Data.csv` — unchanged source data (2,000 rows).
- `data/cleaned/Municipal_Service_Cleaned.csv` — generated cleaned dataset (2,000 rows).

## What was done
- Converted opening/closing date fields to datetime with invalid values coerced to missing.
- Trimmed whitespace from categorical fields while preserving missing values.
- Derived `Resolution_Days` from closing minus opening timestamps.
- Flagged valid completed resolutions only when status is Closed and duration is nonnegative.
- Flagged records where Closed status and closing timestamp disagree; **813** such records were found.
- Added opening month, weekday, and hour fields for later analysis.
- Preserved the original CSV without filling unknown closure dates or silently correcting conflicting statuses.

## Verified results
- Source rows: 2,000; cleaned rows: 2,000.
- Valid resolution records: 1,100.
- Closure-status mismatches: 813.
- Notebook executed without errors.

## GitHub upload instructions
**Preferred repository structure:** place `data/` and `notebooks/` in the **repository root**, next to `README.md` and `docs/`. This keeps Week 3 ready for subsequent weeks. Do not upload the outer `Week_3_Municipal_Data_Preparation_Ready` folder as another nested folder.

1. Extract this ZIP.
2. Open the root of your GitHub repository.
3. Upload the **contents** of this package: `data/raw/Municipal_Service_Data.csv`, `data/cleaned/Municipal_Service_Cleaned.csv`, `notebooks/capstone.ipynb` and this guide.
4. Commit with `Week 3: Clean municipal service data and document preparation`.
5. Open `notebooks/capstone.ipynb` and confirm the outputs are visible.
6. Submit the repository link and point your supervisor to the notebook and cleaned CSV.

**Note:** Earlier Week 2 folders can remain in the repository for historical reference. Avoid deleting or rewriting prior commits. This Week 3 notebook is the current version.
