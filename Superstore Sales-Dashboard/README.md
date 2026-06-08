# Superstore Sales Performance Dashboard (Excel)

## 📌 1. Project Background & Business Case
A mid-sized regional retail supplier was struggling to track its performance due to disconnected datasets spread across multiple regional invoices, product tables, and sales team sheets. Because management lacked a unified view, they could not easily see which product categories were driving growth, which regions were missing monthly sales quotas, or where shipping costs were hurting profitability.

The objective of this project was to ingest, clean, and combine these disconnected datasets into a single, automated spreadsheet model, and build a clean dashboard to support weekly executive business reviews.

---

## 🛠️ 2. Core Excel Techniques Deployed
* **Data Extraction & Transformation:** Power Query Editor (ETL automation, column splitting, data type standardizing, custom unpivoting).
* **Data Engine & Modeling:** Power Pivot (Establishing 1-to-Many relationships, building Date Dimension lookup tables).
* **Advanced Expressions:** Power Pivot DAX Measures and complex native formulas:
  * `Sales_Growth_YOY := DIVIDE([Total_Sales] - [Prior_Year_Sales], [Prior_Year_Sales], 0)`
  * Advanced lookups and array grouping via `XLOOKUP` and `SUMPRODUCT`.
* **Interface Controls:** Multi-Pivot cache linking, custom-themed interactive Slicers, and dynamic KPI trend conditional formatting rules.

---

## 🚀 3. Step-by-Step Analytical Lifecycle

### Step 1: Automated Data Engineering (ETL)
The initial invoicing entries arrived unformatted with missing values, varying date structures, and regional text variations.
1. Connected **Power Query** to the source directory to load all regional CSV files automatically.
2. Filtered out null rows, split address strings into structured `City` and `State` columns, and forced dates into a standard `YYYY-MM-DD` data type.
3. Transformed wide-format seasonal promo columns into clean, long-format vertical rows using the **Unpivot Columns** tool.

### Step 2: Relational Data Modeling
Instead of using massive, slow sheets filled with `VLOOKUP` formulas that slow down Excel, the data was loaded into the **Power Pivot Data Model** using a clean Star Schema:
* **Fact Table:** `Fact_Sales_Transactions`
* **Dimension Tables:** `Dim_Products`, `Dim_Customers`, `Dim_Geography`, and a custom-built `Dim_Calendar` table for reliable time-series tracking.

### Step 3: Executive Interface Engineering
* Designed a clean layout with dark blue headers and light grey backgrounds, avoiding distracting bright neon colors.
* Placed high-level aggregate KPI cards along the top row (Total Revenue, Gross Profit Margin, Target Variance %).
* Grouped trend data into a clean clustered column-line combo chart to compare monthly target trends clearly.

---

## 📊 4. UI Dashboard Preview
*Below is the final interactive visual workspace developed for regional sales management:*

![Corporate Sales Dashboard Preview](./images/sales_dashboard_screenshot.png)

---

## 💡 5. Business Discoveries & Actionable Insights

By slicing and analyzing the combined data model, I uncovered three key insights for the executive team:

* **Margin Attrition:** The "Home Electronics" product line generated the highest top-line revenue ($450K) but carried the lowest net profit margin (**3.2%**) due to unoptimized regional shipping rules.
* **Regional Disparities:** While the Western region exceeded its sales goals by **14%**, the Midwest missed its target for three consecutive quarters due to supply chain delays with a primary logistics vendor.
* **Product Mix Opportunity:** Customers who purchased "Office Hardware" had a **72% correlation** with buying high-margin maintenance contracts, but less than **15%** of the sales team actively pitched these additions.

### Executive Recommendations
1. **Shipping Optimization:** Renegotiate fixed-rate freight terms for Home Electronics to protect profit margins.
2. **Bundle Strategy:** Adjust the sales incentive structure to reward sales reps who bundle high-margin service contracts with Office Hardware purchases.

---

## 📂 6. How to Review and Run the Tool
1. Navigate to the `/dashboard/` folder within this project directory.
2. Download the source file: `Corporate_Sales_Performance_v1.xlsx`.
3. Open the file in desktop Microsoft Excel. 
4. Click **Data > Refresh All** to run the automated Power Query pipelines against the bundled datasets. Use the interactive slicers on the homepage to filter by region and product line.

---
🔗 **Return to Main Portfolio:** [@Ravikumar196](https://github.com/Ravikumar196) | Connect via **[LinkedIn] (https://www.linkedin.com/in/ravi-kumar-13b322236/)**
