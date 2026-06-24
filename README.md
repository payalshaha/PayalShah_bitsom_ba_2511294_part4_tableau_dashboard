# Task 1: Data Connection and Inspection

## Data Source

The dataset `dashboard_sales_data.xlsx` was connected to Tableau using the Microsoft Excel connector. The dataset contains retail transaction records covering sales, profitability, customer segments, product categories, shipping performance, discounts, and returns.

## Field Classification and Data Types

### Date Fields

| Field Name | Tableau Data Type | Purpose              |
| ---------- | ----------------- | -------------------- |
| order_date | Date              | Order placement date |
| ship_date  | Date              | Shipment date        |

### Geographic Fields

| Field Name | Tableau Data Type | Geographic Role |
| ---------- | ----------------- | --------------- |
| region     | String            | Region          |
| state      | String            | State/Province  |
| city       | String            | City            |

### Categorical Fields

| Field Name       |
| ---------------- |
| order_id         |
| customer_id      |
| customer_segment |
| category         |
| sub_category     |
| product_name     |
| ship_mode        |
| campaign_channel |

These fields were used for grouping, filtering, segmentation, and comparison analysis.

### Numerical Measures

| Field Name      | Data Type        |
| --------------- | ---------------- |
| sales           | Number (Decimal) |
| profit          | Number (Decimal) |
| discount        | Number (Decimal) |
| delivery_days   | Number (Whole)   |
| customer_rating | Number (Decimal) |

These fields were used for KPI calculations, trend analysis, profitability analysis, and operational performance evaluation.

### Binary / Flag Fields

| Field Name  | Description                                                              |
| ----------- | ------------------------------------------------------------------------ |
| return_flag | Indicates whether an order was returned (1 = Returned, 0 = Not Returned) |

This field was used to calculate return rates and perform return pattern analysis.

## Data Quality Checks Performed

* Verified that date fields were recognized as Date data types.
* Confirmed sales, profit, discount, and delivery_days were imported as numeric measures.
* Checked categorical fields for consistent naming and grouping.
* Verified return_flag contains binary values suitable for return analysis.
* Reviewed geographic fields for mapping and regional analysis.

## Assumptions

1. Each record represents a single retail transaction.
2. `order_id` uniquely identifies an order.
3. `return_flag = 1` indicates a returned order and `0` indicates a non-returned order.
4. `delivery_days` represents the actual number of days between order and delivery.
5. Sales and profit values are recorded in the same currency throughout the dataset.
6. Discount values are expressed as proportions (e.g., 0.10 = 10% discount).
7. Customer ratings are recorded on a consistent rating scale across all transactions.
8. No external data sources were required for dashboard creation.

## Conclusion

The dataset was successfully loaded into Tableau, field types were validated, and the data was determined to be suitable for executive dashboard development, KPI tracking, profitability analysis, return analysis, shipping performance evaluation, and business storytelling.


# Tableau Executive Dashboard & Data Storytelling

## Business Problem Summary

The retail leadership team requires an executive dashboard to monitor overall business performance across sales, profitability, customer segments, product categories, shipping operations, discount effectiveness, and return patterns. The objective is to identify business opportunities, operational risks, and areas requiring management attention through a single interactive Tableau dashboard.

---

# Dataset Description

The dataset contains retail sales transaction data and includes information related to:

* Orders and sales transactions
* Product categories and sub-categories
* Customer segments
* Geographic regions
* Shipping modes
* Discounts and profits
* Order and shipping dates
* Return indicators

The dataset was imported into Tableau and reviewed to verify field types and data quality before dashboard development.

### Data Types Reviewed

#### Date Fields

* Order Date
* Ship Date

#### Geographic Fields

* Region
* State

#### Categorical Fields

* Category
* Sub-Category
* Customer Segment
* Ship Mode
* Campaign Channel

#### Numerical Measures

* Sales
* Profit
* Discount
* Quantity
* Delivery Days

#### Binary / Flag Fields

* Return Flag

---

# Tableau Workbook Description

The Tableau workbook (`executive_dashboard.twbx`) contains:

* Calculated fields
* Individual analysis worksheets
* KPI cards
* Interactive filters
* Dashboard actions
* Executive dashboard layout

The dashboard was designed to support leadership decision-making through interactive business performance monitoring.

---

# Calculated Fields Created

## 1. Profit Margin

```tableau
SUM([Profit]) / SUM([Sales])
```

Purpose:
Measures profitability as a percentage of sales.

---

## 2. Cost

```tableau
SUM([Sales]) - SUM([Profit])
```

Purpose:
Estimates the cost associated with generating sales.

---

## 3. Average Order Value

```tableau
SUM([Sales]) / COUNTD([Order ID])
```

Purpose:
Measures average revenue generated per order.

---

## 4. Return Rate

```tableau
SUM([Return Flag]) / COUNT([Order ID])
```

Purpose:
Measures the percentage of orders that were returned.

---

## 5. Shipping Delay Bucket

```tableau
IF [Delivery Days] <= 3 THEN "Fast"
ELSEIF [Delivery Days] <= 7 THEN "Moderate"
ELSEIF [Delivery Days] <= 14 THEN "Slow"
ELSE "Very Slow"
END
```

Purpose:
Categorizes delivery performance into business-friendly groups.

---

# Dashboard Components

The dashboard includes the following visualizations:

### KPI Cards

* Total Sales
* Total Profit
* Profit Margin
* Return Rate

### Analysis Views

1. Sales Trend View
2. Regional Performance View
3. Category Profitability View
4. Customer Segment View
5. Shipping Performance View
6. Discount vs Profit View
7. Return Analysis View

These views collectively provide a comprehensive picture of business performance.

---

# Filters and Interactions Used

## Dashboard Filters

* Region
* Category
* Customer Segment
* Ship Mode
* Order Date
* Campaign Channel

## Dashboard Actions

A filter action was created where selecting a region in the Regional Performance View automatically filters related charts across the dashboard.

This interaction allows users to perform deeper regional analysis without navigating to separate dashboards.

---

# Key Business Insights

Key findings from the dashboard include:

1. Sales performance demonstrates identifiable growth and seasonal patterns.
2. Certain regions consistently outperform others in both sales and profitability.
3. Some product categories contribute significantly more profit than others.
4. Customer segments differ substantially in sales contribution.
5. Higher discount levels are frequently associated with lower profitability.
6. Standard shipping experiences longer delivery times compared with premium shipping methods.
7. Certain categories or regions exhibit higher return rates.
8. Profitability improvement opportunities exist through optimized discounting and operational efficiency improvements.

---

# Dashboard Story Summary

The dashboard reveals a business that generates strong sales across multiple markets while facing profitability challenges linked to discounting practices, shipping delays, and return behavior.

High-performing regions and categories provide growth opportunities, while underperforming areas highlight the need for targeted operational improvements. The analysis demonstrates that revenue growth alone is insufficient and should be balanced with profitability, customer satisfaction, and operational efficiency.

The dashboard supports leadership decision-making by connecting sales performance, profitability, customer behavior, logistics, and returns into a unified business narrative.

---

# Assumptions and Limitations

## Assumptions

* Date fields were correctly interpreted by Tableau.
* Return Flag values accurately represent returned orders.
* Delivery Days accurately reflect shipping performance.
* Missing values were handled appropriately during data preparation.

## Limitations

* The dashboard is based on historical data and does not predict future performance.
* External market factors are not included.
* Customer satisfaction data is unavailable.
* Return analysis identifies patterns but not root causes.
* Results depend on the accuracy and completeness of source data.

---

# Screenshots Included

The repository includes the following screenshots:

* full_dashboard.png
* sales_trend_view.png
* regional_performance_view.png
* category_profitability_view.png
* filter_interaction_view.png

These screenshots provide evidence of dashboard construction, visualizations, and interactive functionality.

---

# Repository Structure

```text
part4_tableau_dashboard/
├── data/
│   └── dashboard_sales_data.xlsx
├── tableau/
│   └── executive_dashboard.twbx
├── outputs/
│   ├── dashboard_story.md
│   ├── business_insights.md
│   └── chart_selection_justification.md
├── screenshots/
│   ├── full_dashboard.png
│   ├── sales_trend_view.png
│   ├── regional_performance_view.png
│   ├── category_profitability_view.png
│   └── filter_interaction_view.png
└── README.md
```
