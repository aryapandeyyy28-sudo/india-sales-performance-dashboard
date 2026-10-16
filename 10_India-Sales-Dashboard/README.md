# India Sales Performance & Executive Analytics Dashboard

[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](#)
[![DAX](https://img.shields.io/badge/DAX-Data_Analysis_Expressions-blue?style=for-the-badge)](#)
[![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)](#)

**Author:** [Arya Pandey](https://github.com/aryapandeyyy28-sudo)  
**Role:** Data & Business Analyst  
**Contact:** [aryapandeyyy28@gmail.com](mailto:aryapandeyyy28@gmail.com)

---

## Business Overview
This project delivers a multi-page interactive executive sales analytics dashboard built in **Microsoft Power BI**. It analyzes sales volume, regional profitability, manager quota tracking, and category performance across major Indian territories.

---

## Dashboard Visuals & Reports

### 1. Sales Performance Overview
> *Tracking gross sales, target progress, regional sales distribution, and order volume.*

![Sales Performance Overview](10_India-Sales-Dashboard/Screenshots/I4.png)

---

### 2. Profit Performance Overview
> *Detailed analysis of net margins, monthly profit trends, and high-margin product zones.*

![Profit Performance Overview](10_India-Sales-Dashboard/Screenshots/I2.png)

---

### 3. Manager Performance Overview
> *Executive scorecard measuring individual manager achievement against targets and quotas.*

![Manager Performance Overview](10_India-Sales-Dashboard/Screenshots/I1.png)

---

### 4. Manager Detailed Drill-Down Table
> *Granular transaction matrix tracking manager-level metrics, customer accounts, and variances.*

![Manager Details](10_India-Sales-Dashboard/Screenshots/I3.png)

---

### 5. Category Breakdown & Insights
> *Pareto distribution and visual breakdown across sub-categories and product lines.*

![Category Insights](10_India-Sales-Dashboard/Screenshots/I5.png)

---

## Data Architecture & Modeling

### Data Pipeline:
1. **Extraction & Ingestion:** Ingested transaction tables, manager targets, customer logs, and regional metadata.
2. **Power Query ETL:** Applied data type casting, handled missing values, created date dimension hierarchies, and cleaned territory tags.
3. **Star Schema Data Model:** Established relationships between dimensional tables (Managers, Products, Customers, Date) and the central Sales Fact table.

---

## Core DAX Formulations

| Metric | Business Purpose | DAX Expression |
| :--- | :--- | :--- |
| **Total Sales** | Gross revenue generated | `Total Sales = SUM(Sales[Sales_Amount])` |
| **Total Profit** | Net operational gain | `Total Profit = SUM(Sales[Profit])` |
| **Profit Margin %** | Measure margin efficiency | `Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)` |
| **Target Variance** | Identify quota deficit or surplus | `Target Variance = [Total Sales] - SUM(Targets[Target_Amount])` |
| **Average Order Value** | Track basket size | `AOV = DIVIDE([Total Sales], DISTINCTCOUNT(Sales[Order_ID]), 0)` |

---

## Repository Structure

```text
├── 10_India-Sales-Dashboard/
│   ├── Screenshots/
│   │   ├── I1.png
│   │   ├── I2.png
│   │   ├── I3.png
│   │   ├── I4.png
│   │   └── I5.png
│   └── (Dashboard reports & dataset files)
└── README.md
