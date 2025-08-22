# CRM Sales Opportunities: A Data-Driven Analysis

## Project Overview

This project is a capstone data analysis initiative focused on transforming raw CRM sales pipeline data into actionable business intelligence. By leveraging Power BI, we've created a comprehensive analytical solution that provides key stakeholders with critical insights into sales performance, product effectiveness, and customer value.

## Business Problem & Goal

The primary business challenge was the lack of a consolidated, real-time view of sales performance. Raw transactional data was difficult to interpret and did not provide answers to key business questions.

The project's goal was to build a robust, dynamic analytical solution to:
* Identify top-performing sales agents, teams, and products.
* Analyze quarter-over-quarter growth and identify trends.
* Determine key drivers of win rates and revenue.
* Uncover insights into customer value and market segments.

## Data Sources

The analysis was built upon four interconnected datasets, representing a typical sales data model:
* **`sales_pipeline`**: The central fact table containing every sales opportunity, including deal value, stage, dates, and associated agents, products, and accounts.
* **`accounts`**: A dimension table with master data on customer accounts, including sector, revenue, and number of employees.
* **`products`**: A dimension table providing details on the products being sold.
* **`sales_teams`**: A dimension table outlining the sales organizational hierarchy, linking agents to their managers and regional offices.

## Methodology

Our approach followed a structured data analysis workflow, from data ingestion to final visualization.

### 1. Data Preparation & Cleaning (Power Query)
The raw data was ingested into Power Query for a series of cleaning and transformation steps. This phase focused on ensuring data quality and usability, including:
* **Data Type Validation:** Ensuring all columns (`close_value`, dates, etc.) were in the correct format.
* **Error & Null Handling:** Identifying and managing missing values, particularly the interpretation of a `null` `close_date` as an "Open" deal.
* **Duplicate Removal:** Verifying the data for any duplicate records.

### 2. Data Modeling & Relationships
A star schema data model was designed and implemented to facilitate efficient and accurate analysis.
* **Fact Table:** `sales_pipeline` served as the central fact table.
* **Dimension Tables:** `accounts`, `products`, and `sales_teams` were connected to the fact table with One-to-Many relationships.
* **Date Dimension:** A dedicated Date table was created and connected to `sales_pipeline[close_date]` to enable advanced time-intelligence calculations.

### 3. Key Performance Indicators (KPIs) with DAX
A suite of powerful DAX measures was developed to define core KPIs, including:
* `Total Revenue` & `Won Deals Count`
* `Win Rate`
* `Average Account Revenue (Won Deals)`
* `Growth % (QoQ)`

### 4. Visualization & Dashboarding
Five comprehensive, interactive dashboards were designed in Power BI to address the project's key questions:
1.  **Sales Performance Overview:** High-level KPIs and pipeline distribution.
2.  **Sales Team Performance:** Metrics by sales agent, manager, and regional office.
3.  **Quarterly & Annual Trends:** Time-based analysis for growth and seasonality.
4.  **Product Performance Analysis:** Insights into product-specific win rates and revenue contributions.
5.  **Account Insights:** Analysis by account sector and customer value.

Advanced visualizations were explored using **R scripts** within Power BI to create custom, interactive charts that went beyond standard visuals.

## Key Findings & Recommendations

The analysis led to several actionable insights, which were summarized into key recommendations:
* Identified top-performing teams and agents for potential mentorship programs.
* Pinpointed high-performing product series with above-average win rates.
* Uncovered clear quarterly trends and growth opportunities.
* Recommended the integration of sales target data for future performance tracking against goals.

## Tools & Technologies
* **Data Transformation:** Power BI (Power Query)
* **Data Modeling & Analysis:** Power BI (DAX)
* **Visualization:** Power BI, R (ggplot2, plotly)
* **Documentation:** PowerPoint, Markdown (`README.md`)

## Project Outcome

The final deliverable is a functional and insightful Power BI report that transforms raw data into a strategic business asset. It serves as a single source of truth for sales performance, enabling data-driven decision-making and showcasing a comprehensive data analysis skillset.
