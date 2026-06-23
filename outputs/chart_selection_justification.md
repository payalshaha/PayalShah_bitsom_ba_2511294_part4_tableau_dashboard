# Chart Selection Justification

## Dashboard Design Principles Applied

The executive dashboard was designed to support leadership decision-making by focusing on clarity, business relevance, and ease of interpretation.

### Visualization Principles Applied

* Correct chart selection based on business questions
* Clear visual hierarchy with KPI cards at the top
* Minimal clutter by removing unnecessary gridlines and labels
* Consistent color usage across charts
* Readable titles and labels
* Appropriate sorting for easier comparison
* Interactive filters for user exploration
* Avoidance of misleading scales and unnecessary 3D effects
* Focus on business interpretation rather than decoration

---

# 1. Sales Trend View

### Business Question

How are sales changing over time?

### Chart Type

Line Chart

### Why This Chart Was Selected

A line chart is the most effective way to display trends over time and identify growth patterns, seasonality, and changes in sales performance.

### Fields Used

* Columns: Order Date (Month)
* Rows: Sales
* Color: Year (optional)
* Filters: Region, Category, Customer Segment, Date

### Design Principle Applied

The chart emphasizes trend analysis and avoids unnecessary visual elements that may distract from the sales pattern.

### Mistake Avoided

A bar chart was not used because it is less effective for showing continuous time-based trends.

---

# 2. Regional Performance View

### Business Question

Which region performs best in terms of sales and profit?

### Chart Type

Horizontal Bar Chart

### Why This Chart Was Selected

Bar charts allow clear comparison of performance across regions and make it easy to rank regions by sales or profit.

### Fields Used

* Rows: Region
* Columns: Sales
* Color: Profit

### Design Principle Applied

Regions are sorted from highest to lowest sales to improve readability and support quick comparisons.

### Mistake Avoided

Pie charts were avoided because comparing multiple regional values is difficult with pie slices.

---

# 3. Category Profitability View

### Business Question

Which categories and sub-categories generate the most profit?

### Chart Type

Horizontal Bar Chart

### Why This Chart Was Selected

Bar charts provide a straightforward comparison of profitability across categories and sub-categories.

### Fields Used

* Rows: Category, Sub-Category
* Columns: Profit
* Color: Category

### Design Principle Applied

Profitability is displayed using consistent category colors and sorted order.

### Mistake Avoided

Treemaps were avoided because exact profit comparisons are easier with bars.

---

# 4. Customer Segment View

### Business Question

How do customer segments compare in performance?

### Chart Type

Bar Chart

### Why This Chart Was Selected

Bar charts effectively compare sales performance across customer segments.

### Fields Used

* Columns: Customer Segment
* Rows: Sales
* Label: Profit

### Design Principle Applied

Simple comparison with clear labels and limited color usage.

### Mistake Avoided

3D charts were avoided because they distort comparisons.

---

# 5. Shipping Performance View

### Business Question

Which shipping modes are associated with delivery delays?

### Chart Type

Bar Chart

### Why This Chart Was Selected

Bar charts allow quick comparison of average delivery times between shipping modes.

### Fields Used

* Rows: Ship Mode
* Columns: Average Delivery Days
* Color: Shipping Delay Bucket

### Design Principle Applied

Delay categories are color-coded to highlight operational issues.

### Mistake Avoided

Tables alone were avoided because visual comparisons are easier with bars.

---

# 6. Discount vs Profit View

### Business Question

What is the relationship between discounts and profitability?

### Chart Type

Scatter Plot

### Why This Chart Was Selected

Scatter plots are the most appropriate visualization for showing relationships between two numerical variables.

### Fields Used

* Columns: Discount
* Rows: Profit
* Color: Category
* Detail: Order ID

### Design Principle Applied

Each mark represents an individual transaction, allowing patterns and outliers to be identified.

### Mistake Avoided

Line charts were avoided because discount values are not sequential time-series data.

---

# 7. Return Analysis View

### Business Question

Which categories have the highest return rates?

### Chart Type

Bar Chart

### Why This Chart Was Selected

Bar charts provide a clear comparison of return rates across categories.

### Fields Used

* Rows: Category
* Columns: Return Rate
* Color: Return Rate

### Design Principle Applied

Return rates are formatted as percentages and highlighted using a consistent color scale.

### Mistake Avoided

Pie charts were avoided because small differences in return rates are difficult to compare visually.

---

# Dashboard-Level Design Decisions

## Clear Hierarchy

The dashboard places KPI cards at the top, followed by trend analysis and operational views, ensuring leadership sees key metrics first.

## Consistent Color Usage

* Sales metrics use blue tones.
* Profitability metrics use green for positive performance and red for losses.
* Return-related metrics use orange tones.
* Category colors remain consistent across charts.

## Interactive Filtering

Dashboard-wide filters include:

* Region
* Category
* Customer Segment
* Ship Mode
* Order Date
* Campaign Channel

These filters allow users to explore data without creating additional dashboards.

## Action Filter Interaction

Selecting a region in the Regional Performance View filters all related charts, enabling deeper analysis of regional performance.

## Business Interpretation Focus

The dashboard prioritizes business insights and decision-making rather than decorative visual effects. Every chart directly answers a business question relevant to leadership.



## Proper Labels

All charts include clear axis labels, category names, and data labels where appropriate. Labels were used only when they improved interpretation and were removed when they created unnecessary clutter. KPI cards include descriptive titles to ensure users immediately understand the metric being displayed.

## Readable Titles

Each worksheet and dashboard component uses a business-friendly title that clearly communicates the purpose of the visualization. Examples include:

* Monthly Sales Trend
* Regional Performance Analysis
* Category Profitability Analysis
* Customer Segment Performance
* Shipping Performance Analysis
* Discount vs Profit Relationship
* Return Rate Analysis

Titles were written from a business perspective rather than using technical field names.

## Appropriate Sorting

Charts were sorted to improve readability and highlight key insights:

* Regions sorted by total sales in descending order.
* Categories and sub-categories sorted by profit in descending order.
* Return analysis sorted by highest return rate.
* Customer segments sorted by sales contribution.

Sorting helps leadership quickly identify top-performing and underperforming areas without manually interpreting the data.

## Useful Filters

Interactive filters were included to allow users to explore the dashboard from different perspectives.

Filters implemented:

* Region
* Category
* Customer Segment
* Ship Mode
* Order Date
* Campaign Channel

All filters were applied across the dashboard using "Apply to Worksheets → All Using This Data Source" to provide a consistent user experience.

## Avoidance of Misleading Scales

The dashboard avoids visual practices that may distort interpretation:

* No 3D charts were used.
* No truncated axes were used for bar charts.
* Percentage metrics such as Return Rate and Profit Margin were clearly formatted as percentages.
* Consistent scales were maintained within related visualizations.
* Color intensity was used carefully to support interpretation rather than exaggerate differences.

These choices ensure accurate representation of business performance.

## Focus on Business Interpretation

The dashboard was designed to answer leadership questions rather than simply display data.

Key business decisions supported include:

* Identifying high-performing and low-performing regions.
* Evaluating category profitability.
* Understanding customer segment behavior.
* Measuring the impact of discounts on profit.
* Monitoring shipping efficiency and delivery delays.
* Detecting categories with elevated return risk.

Each visualization was selected to support actionable decision-making and help leadership identify opportunities, risks, and areas requiring further investigation.
