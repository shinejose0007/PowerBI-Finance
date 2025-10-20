Power BI Sample Project -  Data Analyst
======================================================

Files included
- financial_sample_data.csv : synthetic transactional dataset (monthly granularity)
- measures.md : suggested DAX measures to implement in Power BI
- dashboard_preview.png : a static preview image showing suggested visuals
- README.md : this file

Purpose
-------
This small sample project is designed to demonstrate a Finance-focused Power BI report. Use the CSV to build a data model, create measures, and make visuals as suggested below. After building a report in Power BI Desktop, export the .pbix to this repository for portfolio presentation.

Suggested Power BI steps
1. Import 'financial_sample_data.csv' into Power BI Desktop (Get Data -> Text/CSV).
2. Convert 'Date' to Date type; create a proper Calendar table (Date dimension) with Year, Month, MonthName, Quarter and relate Date -> Date in the fact table.
3. Build measures from 'measures.md' (Revenue, Cost, Profit, Gross Margin, YoY Growth, Rolling 3M).
4. Create visuals:
   - Line chart: Revenue trend (by Month)
   - Clustered bar: Revenue by Product
   - Card visuals: Total Revenue, Total Profit, Average Margin
   - Table: Top 10 Customers by Revenue
   - Slicer: Region, Product, Year
5. Configure data refresh schedule / gateway when moving to Service (optional).
6. Optionally implement Row-Level Security (RLS) for regions or business units.
7. Save your report as .pbix and add it to this repo.

Notes on reproducibility
- Data is synthetic and intended to showcase modeling and DAX.
- Replace sample CSV with real exports from ERP/CRM when customizing for a real company.

