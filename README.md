# End-to-End Sales Data Warehouse & Business Intelligence Analytics (Power BI)

Design and implementation of an analytical **Data Warehouse** using a **Star Schema** architecture in **Power BI Desktop** to analyze sales performance, profitability, customer behavior, and organizational efficiency.

The goal of this project is to transform raw operational data into a clean, high-performance decision-support model capable of delivering actionable executive insights.

---

## Key Technologies & Competencies

| Category | Tools & Competencies |
| :--- | :--- |
| **BI Platform** | Power BI Desktop |
| **ETL & Data Preparation** | Power Query (M Language), Data Cleaning, Query Merging, Custom Columns |
| **Data Modeling** | Dimensional Modeling (Star Schema), Fact & Dimension Tables, 1-to-Many (`1:*`) Relationships |
| **Analytics & KPIs** | DAX (Data Analysis Expressions), Time Intelligence, Calculated Measures |

---

## Data Warehouse Architecture (Star Schema)

The data model is built around a central **Fact Table** connected to five **Dimension Tables** via clean one-to-many (`1:*`) relationships to optimize query performance and filter propagation.

### 1. Fact Table
- **`Order_Fact` (Sales Transactions):** Centralizes transactional records and quantitative business metrics such as order quantities, sales revenue, unit prices, costs, and profit margins.

### 2. Dimension Tables (`DIM`)

| Dimension Table | Description | Key Modeling & ETL Skills |
| :--- | :--- | :--- |
| **`Customer_DIM`** | Customer profiles and demographic attributes. | Data cleansing, deduplication, surrogate key management. |
| **`Time_DIM`** | Calendar table and temporal hierarchies (Year, Quarter, Month, Day). | Date table generation and time-intelligence readiness. |
| **`Product_DIM`** | Product catalog and hierarchy (Category, Sub-Category, Product). | Attribute consolidation and standardization. |
| **`Geography_DIM`** | Sales locations (City, Region, Country). | Geographic standardization for map visualizations. |
| **`Organization_DIM`** | Internal company structure. | **Hierarchical Modeling:** Multi-level hierarchy (*Company > Department > Section*). |

---

## ETL Pipeline (Power Query / M Language)

Power Query (M) was used to build an automated, reproducible ETL pipeline prior to loading data into the analytical model:

- **Data Cleansing:** Handling missing/null values, fixing formatting inconsistencies, trimming text fields, and enforcing strict data types.
- **Dimension Extraction:** Using `Merge Queries` and grouping operations to separate descriptive attributes from transactional tables and build normalized dimensions.
- **Business Logic Implementation:** Creating custom conditional columns in M (such as deriving organizational hierarchy levels and standardizing geographic labels).

---

## Key Analytical Insights & Dashboard Views

The Power BI report (`powerBi.pbix`) provides interactive dashboards designed for business decision-makers[cite: 5]:

1. **Executive Sales Overview:** High-level KPIs tracking total revenue, sales volume, profit margins, and year-over-year (YoY) growth trends.
2. **Product & Category Performance:** Breakdown of top-performing product categories and sub-categories by revenue and profitability.
3. **Geographic Sales Distribution:** Interactive regional and country-level analysis identifying high-growth markets.
4. **Organizational Efficiency:** Drill-down analysis across company departments and sections to evaluate internal commercial performance.

---

## Repository Structure

```text
├── powerBi.pbix          # Complete Power BI Desktop file (Data Model, ETL queries, DAX & Reports)[cite: 5]
├── images/               # Dashboard & Star Schema screenshots (optional)
└── README.md             # Project documentation
