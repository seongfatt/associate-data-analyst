# Project Summary: Singapore HDB Resale Flats Data Analysis
Project Purpose
The primary objective of this project was to perform a comprehensive data analysis of the HDB resale flats dataset. The goal was to clean, transform, and analyze the data to uncover valuable insights into the Singapore HDB resale market. This includes understanding price trends, identifying key factors influencing prices, and creating a robust foundation for interactive dashboards.

Methodology & Process
The project followed a structured data analysis workflow, from raw data to actionable insights.

1. Data Cleaning & Preprocessing
The initial raw data presented several challenges that required meticulous cleaning. The following steps were taken:

Data Loading: The hdb_resale_flats.csv file was loaded into a data environment (e.g., Power Query or Python with Pandas).

Handling Data Anomalies: Specific issues were addressed, including:

Date Conversion: The month column (e.g., "Monday, October 1, 2018") was converted to a proper Date data type.

Erroneous Dates: The lease_commence_date column, which contained Whole Number values and problematic entries like 1905, was handled to ensure accurate calculations. These entries were identified and treated as missing or invalid data.

String Parsing: The remaining_lease (e.g., "57 years 11 months") and storey_range (e.g., "10 TO 12") columns were parsed to extract usable numerical data.

Outlier & Missing Value Treatment: Extreme values in resale_price and floor_area_sqm were identified using statistical methods (like Box Plots) and addressed. Missing values were handled appropriately (e.g., by imputation or removal).

2. Feature Engineering
New columns were created from the existing data to provide deeper analytical context. This was primarily done using DAX (Data Analysis Expressions) in Power BI or through Python scripting. Key engineered features include:

**Price_Per_SQM_Col**: The price per square meter, calculated by dividing resale_price by floor_area_sqm. This helps normalize prices for comparison regardless of flat size.

**Flat_Age_At_Sale_Col**: The age of the flat at the time of its sale, calculated from the difference between the month of sale and the lease_commence_date. This is a crucial indicator of property depreciation.

**Lease_Remaining_Years_Col**: The number of years remaining on the flat's 99-year lease at the time of sale.

3. Data Modeling & Analysis
A robust data model was established to facilitate dynamic analysis and time-series calculations.

Date Table: A dedicated Calendar table was created and related to the month column in the main data table. This is essential for time intelligence functions like SAMEPERIODLASTYEAR.

Key Measures: Several DAX measures were created to perform aggregations and calculations based on filtered data:

**Avg_Resale_Price**: The average resale price.

**Total_Transactions**: The total number of transactions.

**YoY_Price_Growth**: The Year-over-Year price growth, a key indicator of market performance.

4. Visualization & Insights
Visualizations were created to present the data in an intuitive manner, revealing key insights.

Box & Whisker Plots: These plots were generated to visualize the distribution, median, and potential outliers of resale_price and Price_Per_SQM_Col across different towns and flat types. This provided a clear understanding of price variability.

Time-Series Charts: Line charts and bar charts were used to visualize trends over time, such as average resale prices and transaction volumes by month, quarter, and year.

Geographical Analysis: The latitude and longitude data was used to create map visuals, showing the geographical distribution of resale prices across Singapore.

Key Technologies Used
Power BI: For data modeling, DAX calculations, and dashboard creation.

Python: For advanced data cleaning and visualization using libraries such as pandas, matplotlib, and seaborn.

Conclusion
Through this project, the raw HDB resale data was transformed into a clean and structured format, ready for deep analysis. The process successfully handled common data quality issues and generated valuable insights into the key drivers of the Singapore HDB resale market. The resulting visualizations provide a powerful tool for stakeholders to explore market trends and make informed decisions.
