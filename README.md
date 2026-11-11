# Mahindra & Mahindra — Financial Data Management and Visualization

**Course project:** Big Data Management & Data Visualization  
**Live research site:** https://Revanth015.github.io/mnm-equity-analysis/  
**Research cutoff:** 10 November 2026

An interactive, source-linked financial research project using public M&M and peer disclosures. It demonstrates a tidy financial data model, data provenance and scope notes, derived metrics, and interactive visual analysis in a responsive static website.

## Project files

- `index.html` — investor-style research article and interactive Chart.js visualizations.
- `data/financial-data.csv` — tidy long-form observations used as a documented course dataset.
- `course-project.md` — course concepts, data workflow, quality rules, and scalable extension.
- `methodology.md` — metric definitions, transformations, and comparison limitations.
- `research/sources.md` — source register and provenance.
- `.github/workflows/deploy.yml` — GitHub Pages deployment workflow.

## Data and visualization features

Readers can select fiscal-year ranges and revenue, PAT, or PAT margin; switch annual chart style; download the selected data; and compare indexed M&M share-price observations with Nifty Auto. Additional views cover segment mix, cash flow, H1 growth, balance-sheet scale, and peers.

The current dataset is a small curated financial history for course demonstration, not a production-scale big-data system. The static implementation follows the project brief’s zero-cost and no-backend requirements. See `course-project.md` for design and scaling context.

Open `index.html` locally or publish through GitHub Pages. Internet access is required for Chart.js and Google Fonts. Historical market values are snapshots, not live prices. Research is educational and not investment advice.
