# Methodology
Research cutoff: 10 November 2026. Annual M&M trend covers FY21–FY26, consolidated, ₹ crore. Revenue means income from operations; PAT is after non-controlling interests. Q2 FY27 quarter ended 30 September 2026.

PAT margin = PAT / income from operations × 100. Revenue CAGR = (FY26 revenue / FY21 revenue)^(1/5) - 1. Share-price returns are split/bonus adjusted through 5 Nov 2026 and exclude dividends. Indicative trailing P/E = market cap dated 9 Nov 2026 divided by FY26 PAT + H1 FY27 PAT - H1 FY26 PAT. This historical multiple is not adjusted for exceptional items or forecasts.

Maruti figures are FY26 company results converted from ₹ million to ₹ crore; SMG amalgamation is noted. Bajaj PAT is after NCI. Tata PV includes JLR and demerger accounting; TMCV is a separate successor. Peer rows are context, not perfect like-for-like ratios.

Financial Services funding affects M&M group borrowings and operating cash flow. They are not industrial-only debt/cash flow measures. Nifty Auto is a price index, and its return window differs by a few days. This is educational material, not investment advice.

**FY21 comparability note:** The FY21 PAT point is continuing-operations PAT after exceptional items as reported in the FY21 results release; FY22 onward uses reported consolidated PAT after non-controlling interests. The chart therefore has a disclosed basis break at FY21.

## Data model and course workflow
`data/financial-data.csv` is a tidy, long-form observation table. Each row records one metric for one entity and period. Fields are `dataset`, `period`, `entity`, `metric`, `value`, `unit`, `scope`, `source_id`, and `notes`. A blank value represents an unavailable numeric value and is not zero. Source IDs link to `research/sources.md`.

The workflow is: collect public disclosures and market snapshots → map each value to a consistent unit and period → retain consolidation/reporting scope → apply validation and comparability notes → derive PAT margin and rebased benchmark values → visualize in the site. See `course-project.md` for quality rules and an optional scalable batch-processing design. The deployed site remains static; no database or distributed processing engine is claimed as implemented.

## Investor chart controls and benchmark
The annual financial chart lets readers select a fiscal-year range, switch among revenue, PAT and PAT margin, change between column and line views, and download the selected series as CSV. The price comparison rebases M&M adjusted calendar-year closes and Nifty Auto month-end closes to 100 at the selected start year. This is a price-only comparison: dividends are excluded, and the 2026 observations are dated 5 November for M&M and 9 November for Nifty Auto. Historical values are selected snapshots, not live market data. Nifty Auto month-end closes are from [Patearn's historical series](https://patearn.in/markets/index?den=Nifty+50&idx=Nifty+Auto&r=1260&tf=m&ty=line).

Tata PV peer revenue is sourced from the FY26 management discussion (source ID 11 in the website register). Its reported loss is preserved as a note; a numeric PAT is not included in the course CSV comparison.
