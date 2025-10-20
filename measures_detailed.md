-- Detaillierte DAX-Measures (benutze die 'Calendar' Tabelle für Zeitintelligenz)

Total Revenue = 
SUM(financial_sample_data[Revenue])

Total Cost =
SUM(financial_sample_data[Cost])

Total Profit =
[Total Revenue] - [Total Cost]

Gross Margin % =
DIVIDE([Total Profit], [Total Revenue], 0)

Revenue MoM Growth % =
VAR Current = [Total Revenue]
VAR Prev = CALCULATE([Total Revenue], DATEADD('Calendar'[Date], -1, MONTH))
RETURN DIVIDE(Current - Prev, Prev, 0)

Revenue YoY Growth % =
VAR Current = [Total Revenue]
VAR Prev = CALCULATE([Total Revenue], SAMEPERIODLASTYEAR('Calendar'[Date]))
RETURN DIVIDE(Current - Prev, Prev, 0)

Revenue Rolling 3M =
CALCULATE([Total Revenue], DATESINPERIOD('Calendar'[Date], LASTDATE('Calendar'[Date]), -3, MONTH))

Top 10 Customers by Revenue =
TOPN(10, SUMMARIZE(financial_sample_data, financial_sample_data[Customer], "Rev", [Total Revenue]), [Rev], DESC)
