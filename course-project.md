# Course Project: Big Data Management & Data Visualization

## Project
**Mahindra & Mahindra: Financial Data Management and Interactive Equity Analysis**

This project uses company and market disclosures to show how financial data can be collected, standardized, checked, interpreted, and communicated through interactive visualizations. The published website remains a static GitHub Pages application, so there is no database or paid service dependency.

## Course concepts demonstrated

- **Data acquisition:** Source register connects each observation to its public disclosure or market-data reference.
- **Data modeling:** `data/financial-data.csv` uses a tidy, long-form schema: one observation per row, with dataset, period, entity, metric, value, unit, reporting scope, source ID, and notes.
- **Data quality and governance:** Units and consolidation scope are explicit; missing numeric values remain blank; methodological breaks, peer-perimeter differences, and observation dates are documented rather than hidden.
- **Data transformation:** PAT margin is derived as PAT / income from operations × 100. Benchmark series are rebased to 100 at the selected start year. Financial-year and calendar-year data remain identified separately.
- **Data visualization:** The site includes annual revenue/PAT/margin views, segment mix, cash flows, H1 comparisons, balance-sheet scale, indexed M&M versus Nifty Auto performance, and peer revenue. Readers can change the annual range and metric, change chart style, toggle the benchmark, and download selected chart data.
- **Communication:** The article explains what each chart can and cannot establish, with an evidence-linked conclusion and limitations.

## Data flow

`Public reports and market snapshots → source register → normalized observation table → quality and scope checks → derived measures → interactive Chart.js views → CSV export`

The published site uses a small, curated sample of historical observations. It is a **data-management and visualization prototype for the course**, not a production big-data platform and not evidence that Hadoop or Spark was run. This is deliberate: the assignment brief prioritizes a free, static site and discourages unnecessary backend infrastructure.

## Data-quality rules

1. Keep values in ₹ crore unless the row explicitly gives another unit.
2. Preserve source reporting scope (consolidated, standalone, segment, or company).
3. Do not coerce non-numeric reported losses or unavailable values into invented numbers.
4. Keep reported and derived measures distinguishable through the `scope` and `notes` fields.
5. Note dates for market observations and do not imply prices are live.
6. Explain comparability breaks, including FY21 PAT basis, Financial Services borrowings, peer reporting perimeters, corporate actions, and dividend exclusion.
7. Reconcile each source ID against `research/sources.md`.

## Scalable extension

If expanded to daily exchange prices, multiple companies, and more years of filings, the same tidy records could be ingested in scheduled batches into object storage, validated with schema and range checks, transformed with a distributed engine such as Apache Spark, and served to the dashboard from partitioned Parquet or an analytics store. That is a possible next phase, not part of this delivered static implementation.

## Run and submit

Open `index.html` or publish the repository with GitHub Pages. Internet access is needed for Chart.js and Google Fonts. Use `data/financial-data.csv`, `methodology.md`, and `research/sources.md` as the course evidence for the data model, definitions, provenance, and limitations.
