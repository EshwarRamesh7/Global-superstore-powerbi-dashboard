# Global Retail Performance Dashboard
## Project explanation and interview preparation

### Project summary

This project is a three-page Power BI dashboard built around the Global Superstore dataset for 2011–2014. It helps a retail decision-maker understand sales performance, profitability, changes over time and geographic differences. It combines KPI monitoring, DAX time-intelligence measures, category analysis and geographic drill-down.

**60-second interview pitch**

“I built a Power BI dashboard for a global retail dataset with more than 51,000 transaction rows. I organised the report into an executive overview, a profitability and trend analysis page, and a geographic deep dive. The report uses DAX measures and time-intelligence logic to compare performance over time. I also used discount-versus-profit analysis and a decomposition tree to investigate categories where sales do not translate into healthy profit. The main lesson is to review revenue and profitability together rather than treating sales growth as the only measure of success.”

### Business problem

A retailer can increase revenue while its margin deteriorates. The dashboard addresses four questions:

1. How are sales, profit and margin trending?
2. Which categories and sub-categories contribute to or erode profit?
3. How do discount levels relate to profitability?
4. Which markets and regions need closer investigation?

### Data and scope

The repository includes a transaction-level CSV, a Power BI report and screenshots. The project records 51,290 rows, 147 countries, seven market groupings and a 2011–2014 period. Fields include order and shipping dates, customer and product attributes, geography, sales, quantity, discount, profit and shipping cost.

A row is an order line, not necessarily a unique order. Use a distinct order identifier when counting orders.

### Approach

- Build a model that supports filtering across time, geography and product.
- Create DAX measures for sales, profit and profit margin.
- Use a date table for time-intelligence calculations.
- Compare trends across years and product categories.
- Use a decomposition tree and discount/profit analysis to investigate weak profitability.
- Validate KPI totals at grand-total and segment levels.

A typical margin measure is `DIVIDE([Total Profit], [Total Sales])`. Year-over-year measures require a valid date table and date relationship.

### Findings and interpretation

The existing project summary reports approximately $12.64M sales, $1.47M profit and an 11.6% overall profit margin. It identifies Tables as a loss-making sub-category and notes that heavily discounted Furniture orders can produce negative profit.

These patterns are descriptive. Discounting may be associated with low profit, but product mix, region, customer type, order size and shipping cost can also influence the result. The earlier country-level values are not repeated because they did not reconcile with the stated global totals.

### Interview questions and suggested answers

**1. What is the difference between sales and profit?**  
Sales measure the value of goods sold. Profit is what remains after the costs included in the model's profit definition. A company can increase sales through discounts while weakening profit, so both should be monitored.

**2. What is a DAX measure?**  
A measure is evaluated when a visual requests it and responds to the current filter context. It is appropriate for dynamic KPIs such as total sales and profit margin.

**3. How does a measure differ from a calculated column?**  
A calculated column is computed row by row and stored in the model. A measure is evaluated at query time and changes with filters and slicers.

**4. What is filter context?**  
It is the set of filters active when a DAX expression is evaluated. Selecting a year, category or region changes the context and therefore the result of a measure.

**5. Why use a date table?**  
A continuous date table provides a consistent calendar for year, quarter and month calculations. It is important for reliable time-intelligence functions.

**6. What does year-over-year analysis show?**  
It compares a metric with the equivalent period in the previous year. A prior-year comparison requires correct date relationships and a clearly defined calendar.

**7. Why analyse margin as well as absolute profit?**  
Absolute profit is influenced by market size. Margin expresses profit relative to sales and allows a more comparable view of efficiency across markets.

**8. Does a negative relationship between discount and profit prove discounts cause losses?**  
No. It indicates association in the observed data. Other factors may affect both discount and profit; segmentation or a suitable causal design would be needed for a causal conclusion.

**9. What is a decomposition tree used for?**  
It allows an analyst to break a measure down by different dimensions, such as region, category or sub-category, to explore possible drivers of a result.

**10. How would you validate the dashboard?**  
Check source row counts, duplicates, missing values and data types; reconcile sales and profit to a trusted baseline; and compare totals across market, category and time. I would also verify that order counts use distinct order IDs.

**11. What is the difference between order lines and orders?**  
An order can contain several line items. Counting rows counts lines; counting distinct order IDs counts orders.

**12. What would you improve?**  
I would document every measure, maintain a star-schema model, add data-quality checks and a refresh process, reconcile all geography-level totals, and add order-level drill-through.

### Limitations to be ready to discuss

- The source notebook appears to contain a separate Smart Logistics analysis, so the PBIX and CSV are the primary dashboard artefacts.
- The row count must not be confused with unique orders.
- Country-level metrics need reconciliation.
- Discount/profit relationships should not be presented as causal without additional analysis.

### Resume bullet

Built a three-page Power BI dashboard for global retail performance using DAX time-intelligence measures and drill-down analysis to monitor sales, profitability, discount sensitivity and geographic trends across a 2011–2014 transaction dataset.

### Files

- [Power BI report](../Superstore%20Analysis%20Dashboard.pbix)
- [Source CSV](../data/SuperStoreOrders.csv)
- [Dashboard images](../images/)
