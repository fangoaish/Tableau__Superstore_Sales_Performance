# Superstore Sales Performance

## Project Overview
The [Sales Performance Dashboard](https://public.tableau.com/app/profile/fang.wen.hsiao/viz/SupersotreSales_17111190533460/SuperstoreSalesPerformance) aims to provide actionable insights into our company's sales performance, focusing on key metrics such as Total Profit, Total Sales, Total Quantity, Profit by Subcategory, Sales by Segment, Order Distribution by Shipping Mode, and Order Distribution by Category. By leveraging these metrics, we aim to enhance our understanding of sales trends, identify areas of improvement, and drive strategic decision-making to optimize revenue and profitability.
![Superstore Sales Performance](https://github.com/fangoaish/Tableau__Superstore_Sales_Performance/assets/51399519/824c6010-480a-4933-8a10-2e67e523c235)


## Dashboard Metrics
1. **Total Profit with % Difference from Previous Year**
- What do I want to know:
  - I want to understand the overall profitability of our sales operations.
- Why do I want to know:
  - To check the financial health of our business and track changes in profitability over time.
- So what?
  - Analyze factors contributing to changes in profit.
  - Identify areas for cost reduction or revenue enhancement.

2. **Total Sales with % Difference from Previous Year**
- What do I want to know:
  - I want to assess the overall sales performance.
- Why do I want to know:
  - To track revenue growth or decline and evaluate the effectiveness of sales strategies.
- So what?
  - Investigate reasons behind fluctuations in sales.
  - Develop strategies to boost sales in underperforming areas.
 
3. **Total Quantity with % Difference from Previous Year**
- What do I want to know:
  - I want to understand the volume of products sold.
- Why do I want to know:
  - To evaluate demand trends and inventory management efficiency.
- So what? 
  - Adjust inventory levels based on demand fluctuations.
  - Explore opportunities for bundling or cross-selling products.

4. **Profit by Subcategory**
- What do I want to know:
  - I want to analyze profitability across different product categories.
- Why do I want to know:
  - To identify high-performing product categories and prioritize resource allocation.
- So what?
  - Allocate marketing resources to high-profit subcategories.
  - Consider expanding product lines in profitable categories.

5. **Sales by Segment**
- What do I want to know:
  - I want to understand sales performance across different customer segments.
- Why do I want to know:
  - To tailor marketing strategies and services to specific customer segments.
- So what?
  - Customize marketing campaigns to target specific segments.
  - Enhance customer experience based on segment preferences.

6. **Order Distribution by Shipping Mode**
- What do I want to know:
  - I want to analyze the distribution of orders by shipping method.
- Why do I want to know:
  - To optimize shipping logistics and improve delivery efficiency.
- So what?
  - Evaluate shipping costs and delivery times for each method.
  - Optimize shipping routes and carrier partnerships.

7. **Order Distribution by Category**
- What do I want to know:
  - I want to understand the distribution of orders across different product categories.
- Why do I want to know:
  - To identify popular product categories and adjust inventory management strategies.
- So what?
  - Ensure adequate inventory levels for high-demand categories.
  - Monitor sales trends to anticipate shifts in category popularity.

## Business Objectives
- Improve overall profitability by optimizing sales strategies and resource allocation.
- Increase revenue through targeted marketing efforts and product innovation.
- Enhance customer satisfaction by tailoring services to specific segments and improving delivery experiences.
- Optimize inventory management to meet demand and minimize stockouts.
- Drive growth by capitalizing on opportunities in high-profit product categories and customer segments.

## Data Source
The Sample Data is from [Tableau Superstore Sales](https://public.tableau.com/app/learn/sample-data): Contains information about products, sales, and profits that you can use to identify key areas of improvement within this fictitious company.

## Data Exploration
Prior to developing visualizations for these distinct aspects, it was essential to generate several calculated fields to filter the sales data from four years down to only two years, encompassing the current year and the preceding year.
To do this, I first created Calculated Fields for the following main KPIs: Total Profit, Total Sales, and Total Quantity Sold:
- Sales Current Year: IF YEAR ( [Order Date] ) = {MAX ( YEAR ( [Order Date] ))} THEN [Sales] END
- Sales Previous Year: IF YEAR ( [Order Date] ) = {MAX ( YEAR ( [Order Date] ))} - 1 THEN [Sales] END
- Sales % Differences: ( SUM ( [Sales Current Year] ) - SUM ( [Sales Previous Year] )) / SUM ( [Sales Previous Year] )
- Sales YoY%(+): IF [Sales % Differences] >= 0 then [Sales % Differences] END
- Sales YoY%(-): IF [Sales % Differences] < 0 then [Sales % Differences] END

![Sales Current Year](https://github.com/fangoaish/Tableau__Superstore_Sales_Performance/assets/51399519/9940ab14-d836-42f4-8b27-5c374a7071fa)

![Sales Previouse Year](https://github.com/fangoaish/Tableau__Superstore_Sales_Performance/assets/51399519/7ec2f5ee-4cd4-450a-8f09-d5b9f264c23a)

![Sales % Difference](https://github.com/fangoaish/Tableau__Superstore_Sales_Performance/assets/51399519/94289f72-75c5-4ad2-a8e7-d9ac58e99438)

![Sales YoY% (+)](https://github.com/fangoaish/Tableau__Superstore_Sales_Performance/assets/51399519/286b8982-b40c-4c86-82b3-4d8b6d13f4b2)

![Sales YoY% (-)](https://github.com/fangoaish/Tableau__Superstore_Sales_Performance/assets/51399519/39745e2a-5cce-4ecf-81b4-de857ce030c1)


Which allowed me to create this visual:

<img width="684" alt="Total Profit" src="https://github.com/fangoaish/Tableau__Superstore_Sales_Performance/assets/51399519/78769c4b-6628-4fc9-9d14-58637558c41b">

I then duplicated those calculated fields to create the same for Profits and Quantity:
<img width="676" alt="Total Sales" src="https://github.com/fangoaish/Tableau__Superstore_Sales_Performance/assets/51399519/8a0def18-371c-430a-9f2a-6c1c1b9c317c">
<img width="696" alt="Total Quantity" src="https://github.com/fangoaish/Tableau__Superstore_Sales_Performance/assets/51399519/8ae1cb26-db9e-4f41-89a2-658cab1dcfef">

This provides a quick and easy snapshot to see how sales, profit, and quantity sold are doing compared to the previous year.
