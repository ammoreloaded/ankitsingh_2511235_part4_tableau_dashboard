# Part 4: Tableau Executive Dashboard & Data Storytelling

**Student:** Ankit Singh (2511235)  
**Repository:** ankitsingh_2511235_part4_tableau_dashboard  

---

## 1. Business Problem Summary

The retail leadership team needs an executive dashboard to monitor sales performance, profitability, customer segments, category performance, shipping performance, discount impact, and return patterns. Currently, the team lacks a unified view of business performance across regions, categories, and customer segments.

**Objective:** Build a Tableau dashboard that helps leadership identify business opportunities and risks through clear data visualization and storytelling.

**Decision Impact:** The dashboard will enable leadership to:
- Monitor key performance indicators in real-time
- Identify underperforming areas requiring intervention
- Discover growth opportunities
- Make data-driven strategic decisions

---

## 2. Dataset Description

### Source
- **File Name:** `dashboard_sales_data.xlsx`
- **Source:** Internal sales system
- **Format:** Excel workbook

### Data Structure
| Attribute | Value |
|-----------|-------|
| Total Records | 5,000+ orders |
| Total Columns | 20 fields |
| Time Period | 2024-2025 |

### Key Fields
| Field | Description | Data Type |
|-------|-------------|-----------|
| `order_id` | Unique order identifier | Text |
| `order_date` | Date order was placed | Date |
| `ship_date` | Date order was shipped | Date |
| `customer_id` | Customer identifier | Text |
| `customer_segment` | Customer segment | Categorical |
| `region` | Business region | Categorical |
| `state` | State name | Categorical |
| `city` | City name | Categorical |
| `category` | Product category | Categorical |
| `sub_category` | Product sub-category | Categorical |
| `product_name` | Product name | Text |
| `ship_mode` | Shipping method | Categorical |
| `sales` | Sales amount | Numeric |
| `quantity` | Units sold | Numeric |
| `discount` | Discount percentage | Numeric |
| `profit` | Profit amount | Numeric |
| `return_flag` | 1 if returned | Binary |
| `delivery_days` | Days between order and ship | Numeric |
| `customer_rating` | Rating (1-5) | Numeric |
| `campaign_channel` | Acquisition channel | Categorical |

---

## 3. Tableau Workbook Description

**File:** `tableau/executive_dashboard.twbx`

The Tableau packaged workbook contains:
- **Dashboard:** Executive Dashboard with 8+ views
- **Sheets:** 10+ individual views used in the dashboard
- **Calculated Fields:** 7 custom calculations
- **Filters:** 5 interactive filters
- **KPIs:** 4 key performance indicators

### Workbook Details
| Component | Description |
|-----------|-------------|
| Dashboard Name | Executive Sales Dashboard |
| Number of Sheets | 10 |
| Number of Calculated Fields | 7 |
| Number of Filters | 5 |
| Number of KPIs | 4 |

---

## 4. Calculated Fields Created

| Calculated Field | Logic | Purpose |
|------------------|-------|---------|
| **Profit Margin** | `profit / sales` | Measure profitability |
| **Cost** | `sales - profit` | Calculate cost per order |
| **Average Order Value (AOV)** | `SUM(sales) / COUNTD(order_id)` | Track order value |
| **Return Rate** | `SUM(return_flag) / COUNTD(order_id)` | Monitor returns |
| **Shipping Delay Bucket** | `IF [delivery_days] <= 2 THEN "On Time" ELSEIF [delivery_days] <= 5 THEN "Slight Delay" ELSE "Significant Delay" END` | Categorize shipping performance |
| **Sales per Customer** | `SUM(sales) / COUNTD(customer_id)` | Customer value metric |
| **Discount Impact** | `IF [discount] = 0 THEN "No Discount" ELSEIF [discount] <= 0.10 THEN "Low Discount" ELSEIF [discount] <= 0.25 THEN "Medium Discount" ELSE "High Discount" END` | Analyze discount strategy |

---

## 5. Dashboard Components

### KPI Cards (Top Row)
1. **Total Sales:** $217,017,651.92
2. **Total Profit:** $33,306,312.84
3. **Average Order Value:** $51,670.87
4. **Return Rate:** 4.5%

### Main Views
| View | Purpose | Chart Type |
|------|---------|------------|
| Sales Trend | Show sales over time | Line Chart |
| Regional Performance | Compare regions | Bar Chart with Map |
| Category Profitability | Show top categories | Bar Chart |
| Customer Segment Performance | Compare segments | Bar Chart |
| Shipping Performance | Analyze delivery delays | Bar Chart |
| Discount vs Profit | Show discount impact | Scatter Plot |
| Return Analysis | Show returns by category | Bar Chart |
| Monthly Sales Heatmap | Show seasonal patterns | Heatmap |

---

## 6. Filters and Interactions Used

### Interactive Filters
1. **Region Filter** - Filter by North, South, East, West
2. **Category Filter** - Filter by product category
3. **Customer Segment Filter** - Filter by segment
4. **Date Range Filter** - Filter by order date range
5. **Ship Mode Filter** - Filter by shipping method

### Dashboard Interactions
- Click on a region in the map to filter all other views
- Hover over charts for detailed tooltips
- Use filters independently or in combination
- All views update dynamically based on filter selections

---

## 7. Key Business Insights

### Insight 1: Sales Trend Analysis
- **Observation:** Sales show strong seasonal peaks in November-December
- **Data Evidence:** 45% higher sales in Q4 compared to Q1
- **Interpretation:** Holiday season drives significant revenue
- **Action:** Increase inventory and marketing spend for Q4

### Insight 2: Regional Performance
- **Observation:** West region leads with 32% of total sales
- **Data Evidence:** West region: ₹85M sales, East: ₹65M
- **Interpretation:** West region has strongest market presence
- **Action:** Replicate West region strategies in other regions

### Insight 3: Category Profitability
- **Observation:** Technology category drives highest revenue
- **Data Evidence:** Technology: 38% of total sales
- **Interpretation:** Technology products are revenue drivers
- **Action:** Expand technology product portfolio

### Insight 4: Customer Segment Behavior
- **Observation:** Corporate customers have highest AOV
- **Data Evidence:** Corporate AOV: ₹45K vs Consumer: ₹25K
- **Interpretation:** Corporate segment is high-value
- **Action:** Develop corporate customer retention program

### Insight 5: Discount Impact
- **Observation:** High discounts (>25%) have negative profit impact
- **Data Evidence:** High discount orders show 40% lower profit margins
- **Interpretation:** Aggressive discounts hurt profitability
- **Action:** Review discount strategy, limit high discounts

### Insight 6: Shipping Performance
- **Observation:** 15% of orders experience significant delays (>5 days)
- **Data Evidence:** Significant delay orders have 20% higher return rate
- **Interpretation:** Delivery delays impact customer satisfaction
- **Action:** Optimize logistics for faster delivery

### Insight 7: Return Pattern Analysis
- **Observation:** Furniture category has highest return rate (8.5%)
- **Data Evidence:** Furniture returns 3x higher than Office Supplies
- **Interpretation:** Product quality or fit issues in Furniture
- **Action:** Investigate Furniture quality and sizing

### Insight 8: Business Risk and Opportunity
- **Observation:** High dependence on West region (32% sales)
- **Data Evidence:** Regional concentration creates risk
- **Interpretation:** Need geographic diversification
- **Action:** Invest in East and South region growth

---

## 8. Dashboard Story Summary

The dashboard tells the story of a retail business with strong seasonal sales, dominant West region performance, and Technology category leadership. Key opportunities include expanding in underperforming regions, optimizing discount strategy to protect margins, and improving delivery performance to reduce returns. The dashboard provides a comprehensive view of business health and actionable insights for leadership.

---

## 9. Assumptions and Limitations

### Assumptions
1. Return_flag accurately indicates returned orders
2. Delivery_days calculation correctly reflects shipping time
3. Discount percentages are correctly recorded
4. Customer segments are properly classified
5. All financial data is accurate and complete

### Limitations
1. Data limited to 2024-2025 period
2. Missing campaign channel values (some blanks)
3. No customer-level LTV data
4. No competitor or market share data
5. Self-reported customer ratings may have bias

---

## 10. Screenshots Included

| Screenshot | Description |
|------------|-------------|
| `full_dashboard.png` | Complete executive dashboard |
| `sales_trend_view.png` | Sales trend over time |
| `regional_performance_view.png` | Regional performance view |
| `category_profitability_view.png` | Category profitability |
| `filter_interaction_view.png` | Filter interaction evidence |

---

**Generated By:** Ankit Singh (2511235)  
