-- Calendar (Datumstabelle) - als berechnete Tabelle in Power BI einfügen
Calendar =
VAR MinD = MINX(ALL(financial_sample_data), financial_sample_data[Date])
VAR MaxD = MAXX(ALL(financial_sample_data), financial_sample_data[Date])
RETURN
ADDCOLUMNS(
    CALENDAR(MinD, MaxD),
    "Year", YEAR([Date]),
    "MonthNumber", MONTH([Date]),
    "MonthName", FORMAT([Date],"MMMM"),
    "MonthYear", FORMAT([Date],"MMM YYYY"),
    "Quarter", "Q" & FORMAT([Date],"Q"),
    "IsMonthStart", DAY([Date]) = 1
)
