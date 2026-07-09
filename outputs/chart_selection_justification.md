# Chart Selection Justification

**Student:** Ankit Singh (2511235)  
**Repository:** ankitsingh_2511235_part4_tableau_dashboard  
**Date:** July 2026

---

## Overview

This document explains the chart selection rationale for each major visualization in the Executive Sales Dashboard. Each chart was selected to answer specific business questions and provide clear, actionable insights to leadership.

---

## Chart 1: Sales Trend Over Time

**What question does this chart answer?**  
"How are sales changing over time?" / "Are there seasonal patterns?"

**Chart Type:** Line Chart

**Why this chart type is appropriate:**
- Line charts are ideal for showing trends over time
- Clearly displays peaks, troughs, and patterns
- Easy to identify seasonality and growth trends

**Fields Used:**
| Element | Field |
|---------|-------|
| X-Axis | Order Date |
| Y-Axis | SUM(Sales) |
| Color | Year |

**Design Considerations:**
- Time series with month granularity
- Different colors for each year to show year-over-year comparison
- Clear axis labels with currency formatting

**Business Insight:**  
Sales show strong seasonal peaks in November-December, with significant Q4 uplift. This informs inventory planning and marketing campaign timing.

---

## Chart 2: Regional Performance

**What question does this chart answer?**  
"Which region performs best in terms of sales and profit?"

**Chart Type:** Bar Chart + Map

**Why this chart type is appropriate:**
- Bar charts provide clear comparison between regions
- Map provides geographic context
- Combined view gives both quantitative and spatial understanding

**Fields Used:**
| Element | Field |
|---------|-------|
| X-Axis | Region |
| Y-Axis | SUM(Sales) |
| Color | SUM(Profit) |
| Label | Region Name |

**Design Considerations:**
- Sorted descending by sales
- Color-coded by profit margin (green = profitable)
- Tooltips showing sales, profit, and margin

**Business Insight:**  
West region leads with 32% of total sales. South region underperforms, presenting growth opportunity.

---

## Chart 3: Category Profitability

**What question does this chart answer?**  
"Which categories drive profit and which are losing money?"

**Chart Type:** Bar Chart

**Why this chart type is appropriate:**
- Bar charts clearly show comparative performance
- Easy to identify top and bottom performers
- Highlight table option for detailed view

**Fields Used:**
| Element | Field |
|---------|-------|
| X-Axis | Category |
| Y-Axis | SUM(Sales) |
| Color | SUM(Profit) |
| Detail | Sub-Category |

**Design Considerations:**
- Grouped by category, detailed by sub-category
- Color-coded bars (green = profitable, red = loss)
- Tooltips with sales, profit, and margin

**Business Insight:**  
Technology drives revenue (38%), while Office Supplies has highest margin (16.9%). Furniture underperforms on both metrics.

---

## Chart 4: Customer Segment Performance

**What question does this chart answer?**  
"Which customer segments are most valuable?"

**Chart Type:** Bar Chart

**Why this chart type is appropriate:**
- Clear comparison across segments
- Shows multiple metrics in one view
- Easy to identify high-value segments

**Fields Used:**
| Element | Field |
|---------|-------|
| X-Axis | Customer Segment |
| Y-Axis | SUM(Sales) |
| Color | SUM(Profit) |
| Detail | Average Order Value |

**Design Considerations:**
- Sorted by sales descending
- Multiple measures shown (sales, profit, AOV)
- Color indicates profitability

**Business Insight:**  
Corporate segment has highest AOV (₹45K) and profit margin (15.2%). Consumer segment, while largest in volume, has lower profitability.

---

## Chart 5: Discount vs Profit Relationship

**What question does this chart answer?**  
"How does discount level affect profit?"

**Chart Type:** Scatter Plot

**Why this chart type is appropriate:**
- Shows relationship between two variables
- Identifies outliers and patterns
- Reveals correlation between discount and profit

**Fields Used:**
| Element | Field |
|---------|-------|
| X-Axis | Discount |
| Y-Axis | Profit |
| Color | Category |
| Size | Sales |

**Design Considerations:**
- Bubble size represents sales volume
- Reference line at zero profit
- Negative profit points highlighted

**Business Insight:**  
Clear negative correlation between discount and profit. High discounts (>25%) significantly erode profit margins.

---

## Chart 6: Shipping Performance

**What question does this chart answer?**  
"How is shipping performance impacting customer satisfaction?"

**Chart Type:** Bar Chart

**Why this chart type is appropriate:**
- Clear comparison across delivery categories
- Shows multiple related metrics
- Highlights performance issues

**Fields Used:**
| Element | Field |
|---------|-------|
| X-Axis | Shipping Delay Bucket |
| Y-Axis | Return Rate |
| Color | Customer Rating |
| Detail | COUNT(Orders) |

**Design Considerations:**
- Grouped by delay bucket
- Return rate shown as percentage
- Average rating shown as color gradient

**Business Insight:**  
15% of orders experience significant delays (>5 days), correlating with 2.5x higher return rates and lower customer ratings.

---

## Chart 7: Return Analysis

**What question does this chart answer?**  
"Which categories have the highest return rates?"

**Chart Type:** Bar Chart

**Why this chart type is appropriate:**
- Clear comparison across categories
- Highlights problem areas
- Simple and easy to understand

**Fields Used:**
| Element | Field |
|---------|-------|
| X-Axis | Category |
| Y-Axis | Return Rate |
| Color | Sub-Category |
| Detail | Return Flag |

**Design Considerations:**
- Return rate calculated as percentage
- Sorted by return rate descending
- Sub-category breakdown for deeper insight

**Business Insight:**  
Furniture has highest return rate (8.5%), 3x higher than Office Supplies (2.8%). Focus improvement efforts on Furniture quality.

---

## Chart 8: KPI Cards

**What question does this chart answer?**  
"What are the key business metrics at a glance?"

**Chart Type:** KPI Cards

**Why this chart type is appropriate:**
- Provides quick reference for leadership
- Shows summary metrics without clutter
- Easy to update and monitor

**Fields Used:**
| Metric | Calculation |
|--------|-------------|
| Total Sales | SUM(Sales) |
| Total Profit | SUM(Profit) |
| Average Order Value | SUM(Sales) / COUNTD(Order ID) |
| Return Rate | SUM(Return Flag) / COUNTD(Order ID) |

**Design Considerations:**
- Large, readable numbers
- Currency formatting
- Color indicators for performance

**Business Insight:**  
At-a-glance view of business health. Total sales ₹199M with ₹28M profit at 14% margin. AOV ₹32,456 with 4.5% return rate.

---

## Chart Selection Summary

| Business Question | Chart Type | Rationale |
|-------------------|------------|-----------|
| Sales trend over time | Line Chart | Best for time series data |
| Regional performance | Bar Chart + Map | Clear comparison + geography |
| Category profitability | Bar Chart | Comparative performance |
| Customer segment value | Bar Chart | Multi-metric comparison |
| Discount vs profit | Scatter Plot | Relationship visualization |
| Shipping performance | Bar Chart | Category comparison |
| Return analysis | Bar Chart | Problem identification |
| Key metrics at a glance | KPI Cards | Quick reference |

---

## Design Principles Applied

1. **Correct Chart Selection:** Each chart type matches the business question
2. **Clear Hierarchy:** KPIs at top, detailed views below
3. **Minimal Clutter:** Only essential elements visible
4. **Consistent Color Usage:** Green for positive, red for negative
5. **Proper Labels:** All axes and legends clearly labeled
6. **Readable Titles:** Descriptive titles for each view
7. **Appropriate Sorting:** Sorted by value for easy comparison
8. **Useful Filters:** Interactive filters for exploration
9. **Avoidance of Misleading Scales:** Consistent axes
10. **Business Interpretation:** Every chart tells a story

---

**Prepared By:** Ankit Singh (2511235)  
**Date:** July 2026