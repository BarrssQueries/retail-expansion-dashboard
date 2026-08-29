# Retail Expansion Readiness Dashboard
An interactive Excel dashboard and business case analyzing four years of retail sales data to recommend where a company should prioritize a new subsidiary or branch expansion.

<img width="632" height="376" alt="dashboard-preview" src="https://github.com/user-attachments/assets/49b39343-c879-47b2-b70b-01f046c2ef5c" />


## Business Brief

**Scenario:** A retail superstore is planning a rebrand and the launch of a new subsidiary. Before committing resources, leadership asked for a clean, interactive one-page executive summary to evaluate historical sales patterns and identify the company's strongest markets, segments, and product lines.

**Questions the dashboard answers:**
- What key metrics define overall business performance, including total revenue, profit, order volume, quantity sold, and average discount rate, and how do these compare on a year-over-year basis?
- How have monthly sales trended against the prior year?
- Which customer segments (Consumer, Corporate, Home Office) drive the most revenue and volume?
- Which product categories (Technology, Furniture, Office Supplies) are the top revenue contributors?
- Which states and regions are the biggest revenue strongholds, and how is customer segment mix distributed geographically?
- Where should the company prioritize resources for its new subsidiary?

## Data Source

This project uses the Sample – Superstore dataset (9,994 order-line records, 2011–2014), originally distributed with Tableau Desktop as a demo/training dataset and widely mirrored on Kaggle and the Tableau Community. It is synthetic data, used here to demonstrate an end-to-end analysis workflow rather than to represent a real company.

Four columns were engineered on top of the original fields for this analysis: Discounted Unit Price, Profit Margin, Lead Time, and Delivery Status.

## What's in the Workbook

| Sheet | Purpose |
|---|---|
| Dataset | Raw order-level data (9,994 rows, 24 columns), loaded as an Excel Table and connected to the Data Model. |
| Analysis | Staging layer — PivotTable outputs (monthly trend, segment, category, state, and segment-by-region breakdowns) that feed the dashboard's charts and KPI cards. |
| Dashboard | The final one-page executive summary — see below. |

**Data model:** Built on Power Pivot, with a dedicated Calendar date table related to the Dataset table, and DAX measures for time-intelligence calculations (e.g. Year-over-Year revenue and a prior-year comparison measure using HASONEVALUE / SELECTEDVALUE patterns).

**Dashboard components:**
- 4 KPI cards: Sales & Profit (combined), Total Quantity, Total Orders, and Average Discount, custom-formatted to display in thousands/millions (e.g. $2.3M, $286.4K) via a dynamic number format.
- Monthly Trend chart: Current-year revenue plotted against the prior year to surface seasonality and YoY momentum.
- Segment breakdown: revenue by Consumer / Corporate / Home Office.
- Category breakdown: revenue by Technology / Furniture / Office Supplies.
- Top 5 states by revenue: geographic revenue leaders.
- Filled map visual: revenue by state, for at-a-glance geographic distribution.
- Segment × Region matrix: how customer segment mix varies (or doesn't) across regions.
- Slicers: Year, Sub-Category, Ship Mode, and Delivery Status, so any visual can be filtered interactively.

## Key Insights

- Growth is outrunning profit. Revenue grew ~20.6% year-over-year while profit grew only ~14.4%, as average discounts ticked up and margin slipped, a reminder that top-line growth alone doesn't confirm financial health.
- Furniture is a profitability trap. It drives roughly a third of all revenue but returns a razor-thin margin, dragged down specifically by Tables and Bookcases, which carry the highest average discounts in the catalog and are net loss-making.
- Discounting is the mechanism, not demand. Discount rate and profit margin are strongly negatively correlated; margin turns negative once a line item's discount passes roughly 20%.
- Revenue size is misleading without profitability. California and New York are both high-revenue and high-margin, the strongest expansion signal in the data. Texas, Ohio, Pennsylvania, and Illinois generate comparable revenue but are net loss-making, driven by much heavier average discounting.
- Segment mix doesn't vary by geography. The Consumer/Corporate/Home Office split is nearly identical in every region, so segment mix isn't a useful screen for site selection; regional and state-level profitability is.

**Recommendation:** Prioritize the new subsidiary in markets with a California/New York profile — proven revenue and margin strength — rather than markets chosen on revenue size alone, and address discount governance (especially on Tables and Bookcases) before scaling the current product mix into a new location. See Expansion_Recommendation_Memo.docx in this repo for the full one-page write-up.

## Skills Demonstrated

Excel Data Model / Power Pivot · DAX measures & time intelligence (YoY, prior-year comparisons) · Power Query · PivotTables & PivotCharts · slicers for interactive filtering · custom number formatting · dashboard design and one-page executive storytelling · translating data findings into a business recommendation.

## Repository Contents
Sales_Performance_Analysis.xlsx # Full workbook: raw data, data model, analysis, dashboard
Expansion_Recommendation.docx # One-page business recommendation
assets/dashboard-preview.png # Screenshot of the Dashboard tab
README.md


## Data Source Acknowledgement

Sample – Superstore dataset, originally distributed with Tableau (Tableau Software / Salesforce); publicly available via the Tableau Community and Kaggle. Used here for independent portfolio analysis; all figures in this README and the accompanying memo were calculated directly from the raw order-level data.

## Author

Mubarakatu Adebayo - Masters of Management, Business Data Analytics
