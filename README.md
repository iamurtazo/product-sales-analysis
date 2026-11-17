# Product Sales Analysis

Data analysis of a 6-week sales trial for **Pens and Printers**, comparing three customer outreach methods — **Email**, **Call**, and **Email + Call** — to determine which approach drives the most revenue for the least team effort.

**Analyst:** Murtazo · **Date:** October 25, 2025

## Business Question

Which sales method should the team use going forward, considering both revenue generated and the time it costs to reach each customer?

## Data

- **Source:** [`product_sales.csv`](product_sales.csv) — 15,000 customer records, 8 columns (`week`, `sales_method`, `customer_id`, `nb_sold`, `revenue`, `years_as_customer`, `nb_site_visits`, `state`)
- **Known issue:** ~7% of `revenue` values were missing and were cleaned/handled in the analysis

## Analysis

The full workflow lives in [`notebook_copy.ipynb`](notebook_copy.ipynb):

1. **Data loading & exploration** — initial look at structure and data types
2. **Data validation & cleaning** — missing value handling and column-by-column checks
3. **Exploratory analysis** — customer counts per method, revenue distribution (overall and by method), revenue trends over the 6-week period
4. **Business metric** — defines and calculates **Revenue per Customer Effort (RPCE)**, i.e. revenue generated relative to the time the sales team spends per customer
5. **Recommendation** — final method comparison and recommendation

Supporting charts are saved in [`visuals/`](visuals).

## Key Finding

**Email** is the recommended primary method: it delivers the highest revenue efficiency (RPCE) with minimal team effort (~2 minutes per customer vs. 12–30 minutes for the other methods) and scales easily to a larger customer base.

- **Primary — Email:** most efficient, lowest effort, use as the default
- **Secondary — Email + Call:** good middle ground, reserve for high-value prospects
- **Not recommended — Call only:** lowest efficiency, highest effort, not scalable

## Reports

- [`Practical_DAP_Product_Sales.pdf`](Practical_DAP_Product_Sales.pdf) — full written report
- [`Comprehensive_Presentation_On_Findings.pdf`](Comprehensive_Presentation_On_Findings.pdf) — presentation summary of findings

## Running the Notebook

```bash
pip install pandas matplotlib seaborn
jupyter notebook notebook_copy.ipynb
```
