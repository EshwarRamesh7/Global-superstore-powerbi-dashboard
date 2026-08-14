# 🛍️ Global Superstore Performance Dashboard

## 📌 Overview
An interactive Power BI dashboard analyzing **51,290 orders across 147 countries** for a global retail superstore, covering sales performance, profitability, and regional trends — built with custom DAX time-intelligence measures and a fully custom visual theme.

## 🎯 Business Objective
- Track sales and profit performance across markets, regions, and product categories
- Surface year-over-year growth and decline using time-intelligence comparisons
- Identify underperforming categories/regions dragging down profitability
- Give decision-makers a drillable view from global performance down to individual order priority

## 🗂️ Dataset
**Source:** [Global Superstore Dataset]
**Size:** 51,290 orders | 2011–2014 | 147 countries across 7 markets (Africa, APAC, EU, EMEA, LATAM, US, Canada)

**Key fields:** order/ship dates, ship mode, customer segment, market/region, product category & sub-category, sales, quantity, discount, profit, shipping cost, order priority

## ⚙️ Tools & Technologies
`Power BI` · `DAX` · `Python (PIL)` for custom visual assets

## 🛠️ Build Highlights
- **Custom DAX time-intelligence** — used `SAMEPERIODLASTYEAR` and related functions to build true year-over-year comparisons, not just static filters
- **Custom gradient background** — generated programmatically in Python (PIL) rather than using a default Power BI theme, for a distinct visual identity
- **Three-page dashboard** — structured for a top-down analysis flow:
  1. **Executive Overview** — KPI cards, high-level sales/profit trends
  2. **Regional & Category Deep-Dive** — heatmaps and category-level breakdowns
  3. **Decomposition & Drivers** — decomposition tree for root-cause analysis of profit/sales swings, with conditional formatting to flag under/over-performance

## 🖼️ Dashboard Preview
![Executive Overview]
![Regional Deep-Dive]
![Decomposition Tree]
## 💡 Key Insights
*(Pull 3-4 real figures from your dashboard here — e.g. top market by profit margin, category with highest discount-driven losses, YoY growth %. Send me the numbers and I'll slot them in properly.)*

## 📁 Repo Structure

├── data/

│ └── global_superstore_orders.csv

├── dashboard/

│ └── global_superstore.pbix

├── scripts/

│ └── background_generator.py

├── images/

│ ├── executive_overview.png

│ ├── regional_deepdive.png

│ └── decomposition_tree.png

└── README.md

## 🚀 How to Run
Open `dashboard/global_superstore.pbix` in **Power BI Desktop** (free download from Microsoft). Data source path may need to be repointed to `data/global_superstore_orders.csv` if reopening on a different machine.

## 👨‍💻 Author
**Eshwar Ramesh**
Aspiring Data Analyst | Power BI Developer
📧 eshwarramesh1985@gmail.com
🌐 [github.com/EshwarRamesh7](https://github.com/EshwarRamesh7) · [Portfolio](https://eshwarrameshportfolio.netlify.app)
