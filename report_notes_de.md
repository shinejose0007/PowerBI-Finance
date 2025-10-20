Report Notes (Deutsch) - Zweck, Implementierung & Business Value
===============================================================

Zweck des Berichts
Der Beispiel-Report demonstriert ein Finance-orientiertes Power BI-Dashboard, das Management-Reporting, Produkt- und Kundenanalysen sowie Trend- und Zeitreihenkennzahlen abbildet. Ziel ist es, Entscheidungsgrundlagen zu schaffen (Umsatz, Profit, Marge, Wachstum) und typische Controlling-Fragen schnell zu beantworten.

Datenmodell & Beziehungen
- Fact-Tabelle: financial_sample_data (transaktionale Ebene: Date, Product, Region, Customer, Revenue, Cost, Units).
- Dimension: Calendar (als berechnete Tabelle) mit Year, MonthNumber, MonthName, Quarter.
- Beziehung: financial_sample_data[Date] -> Calendar[Date] (Many-to-One, Cross filter = Single direction empfohlen für einfache Modelle).

Wesentliche Measures (Kurzbeschreibung)
- Total Revenue, Total Cost, Total Profit: Basiskennzahlen für Umsatz- und Ergebnisanalyse.
- Gross Margin %: Profitabilitätskennzahl (Profit / Revenue).
- Revenue YoY / MoM / Rolling 3M: Zeitintelligenz zur Trendanalyse und Saisonalitätserkennung.
- Top Customers: Identifikation kundenbasierter Hebel für Umsatzsteigerung oder Risikominimierung.

Empfohlene Visuals & Interaktion
- Line Chart: Revenue Trend (monatl.) mit Slicer für Year/Region/Product.
- Clustered Bar: Revenue by Product (letzte 12 Monate) für Produkt-Performance-Vergleich.
- Cards: Total Revenue, Total Profit, Average Gross Margin (Schnellüberblick für Management).
- Table / Matrix: Top 10 Customers mit Revenue, Profit, Margin.
- Slicers: Region, Product, Year — optional Drillthrough für Kunden-Detail-Report.

Hinweise zu Governance & Produktion
- Datenaktualisierung: Beim Produktionsbetrieb Power BI Gateway und Refresh-Pläne (z. B. tägliche/monatliche Aktualisierung) konfigurieren.
- Row-Level Security (RLS): Bei Bedarf RLS nach Region implementieren (z. B. Rollen "Region_North", "Region_South").
- Dokumentation: README + measures.md in Repo für Reproduzierbarkeit; Report-Notes (dieses Dokument) für Business-Kontext.
- Performance: Bei großen Datensätzen Aggregationstables (z. B. Monats- oder Quartals-Aggregate) in Power Query oder im Datenlager voraggregieren.

Wie man die PBIX für das Portfolio vorbereitet
1. Erstelle das PBIX in Power BI Desktop und implementiere die Measures wie oben.
2. Füge 2-3 Screenshots (Homepage, Product Breakdown, Top Customers) in den Repo-Ordner /screenshots/ ein.
3. Schreibe in das Repo eine kurze `report_notes.md` (dieses Dokument) mit Business-Zielen und verwendeten Metriken.
4. Optional: Exportiere ein Power BI Template (.pbit) statt .pbix, wenn du sensible Daten nicht mitliefern willst.

Kontakt & Weiteres
Wenn du möchtest, passe ich die Measures an konkrete Unternehmenskennzahlen (Budget vs Ist, Forecast vs Actual) an oder erstelle eine Version mit RLS-Beispiel und Anleitung zur Gateway-Konfiguration.
