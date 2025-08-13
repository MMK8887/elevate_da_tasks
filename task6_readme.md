# Task 6: Sales Trend Analysis Using Aggregations

## Objective
Analyze monthly revenue and order volume from the `orders` table.

## Dataset
Table: **orders**
```
order_id INT,
order_date DATE,
amount DECIMAL(10,2),
product_id INT
```

## Steps Performed
1. Extract month from `order_date`.
2. Extract both year and month.
3. Group by year/month.
4. Use `SUM(amount)` to calculate monthly revenue.
5. Use `COUNT(DISTINCT order_id)` to calculate monthly order volume.
6. Combine revenue and order volume, filtering for specific years.

## Deliverables
- **SQL Queries**: Provided for each sub-task (a–f).
- **Sample Outputs**: Mock data results for clarity.
- **PDF**: `sales_trend_analysis_task6.pdf` contains all queries and outputs.

