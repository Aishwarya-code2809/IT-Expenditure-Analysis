# IT Expenditure Analysis Dashboard

An interactive Power BI report for reviewing IT expenditure across business areas, regions, IT areas, and cost groups. It compares actual spend with forecast and plan to help finance and IT leaders identify budget variances and decide where to investigate further.

## Project objective

This project addresses the question: **How can an organization monitor IT expenditure and spot budget variances early enough to act?**

The dashboard is designed to support:

- Budget monitoring across Actual, Forecast, and Plan
- Comparison of spending by region, business area, IT area, and cost element
- Identification of areas that are above or below plan
- Interactive review of cost patterns using slicers and visual cross-filtering

## Dashboard pages

### Overview

- KPI cards for total Actual and Plan
- Monthly trend comparing Actual, Forecast, and Plan
- Region and month slicers
- Actual spend by Cost Element Group treemap
- Actual versus Plan variance by Business Area

### Cost Drivers

- Business Area variance chart
- IT Area variance chart
- Business Area slicer
- Cost Element Sub Group table with Actual, Plan, and Actual vs Plan

Select a slicer value or a chart element to filter related visuals on the page. Clear the selection to return to the full view.

## Key findings

The dataset’s amounts are shown in the source units; no currency was specified.

- Total Forecast is approximately **890.54 million**, compared with a Plan of **900.40 million**. Forecast is about **9.86 million (1.1%) below Plan** overall.
- **December** has the largest monthly Actual-over-Plan variance at approximately **21.52 million**. This is a signal to investigate the underlying cost groups and business areas; the dataset does not establish the cause.
- **Europe** is approximately **7.07 million above Plan**, while the **USA** is approximately **38.54 million below Plan**. These differences merit review with budget owners to understand timing, scope, and operating context.
- At the cost subgroup level, Telecomm and Software are among the positive variances; Depreciation and Internal Labor are below Plan.
- Africa & Asia has Actual spend but no corresponding Plan value. Treat this as a plan coverage gap or unplanned spend, not as a zero variance.

## Data preparation

The source workbook contains two tabs: `Data` and `Future Data`. The report model aggregates data across the shared dimensions:

- Month (`Date`)
- Business Area
- Region and Country
- IT Area and IT Sub Area
- Cost Element Group and Cost Element Sub Group
- Cost element name

Actual, Forecast, and Plan are summed at this dimensional grain. Later-month Actual values from `Future Data` are matched to the corresponding dimensional records in `Data`. Forecast and Plan remain sourced from `Data`.

The included CSV has one row per dimensional combination and includes month number and variance fields for analysis in Power BI.

## Files

```text
IT_Expenditure_Analysis_GitHub/
├── README.md
├── IT_Expenditure_Analysis.pbix
├── IT_Expenditure_Model.csv
└── IT_Expenditure_Dashboard.html
```

- **`IT_Expenditure_Analysis.pbix`** — Power BI report. Open with Power BI Desktop.
- **`IT_Expenditure_Model.csv`** — prepared data model used by the report.
- **`IT_Expenditure_Dashboard.html`** — browser-based interactive preview.

## Open the report

1. Download or clone this folder.
2. Open `IT_Expenditure_Analysis.pbix` in Power BI Desktop.
3. Use the page tabs to switch between **Overview** and **Cost Drivers**.
4. Use the Region, Month, and Business Area slicers or select chart elements to explore the data.

If you need to reconnect or refresh the data, import `IT_Expenditure_Model.csv` in Power BI Desktop using **Home → Get data → Text/CSV**.

## Tools

- Microsoft Power BI Desktop
- CSV / Excel source data
- Power BI slicers, KPI cards, line and bar charts, treemap, and table visuals

## Data limitations

- The source date field contains month names only; it does not include a year. The report therefore does not make year-over-year comparisons.
- The source does not specify a currency. Amounts are reported in the source units without a currency symbol.
- Some records have no matching Plan value. Blank variance means Plan is unavailable, not that the variance equals zero.
- Variances identify areas for follow-up; they do not explain why a cost changed.

## Source

[Open the source Google Sheets workbook](https://docs.google.com/spreadsheets/d/1PUEkX0vyDYfHwzzGVoyNluiaPbofYC01/edit?gid=1542984324#gid=1542984324)
