# SuperStore Sales Dashboard

![Dashboard Overview](images/overview.jpg)

## Overview

An interactive 3-page Power BI dashboard that analyzes sales, profit, and customer performance for a US retail store, and shows whether growth is profitable.

- Period: 2019 – 2020
- Size: 1.57M in sales, 175K in profit (11.2% margin), 3,003 orders and 773 customers
- Dataset: SuperStore sample data (5,901 rows), cleaned in Power Query and modeled with DAX

## Dashboard

### 1. Overview
Headline KPIs, sales by category, ship mode, and a ranked view of sub-categories.

![Overview](images/overview.jpg)

### 2. Time & Profit
Sales and profit by month, and sales by payment mode, to spot seasonality and margin changes.

![Time & Profit](images/time_profit.jpg)

### 3. Customers & Geography
Sales by region, customer segment, and state.

![Customers & Geography](images/customers_geography.jpg)

The same KPI cards and year filter (All, 2019, 2020) appear on all three pages.

## Data Cleaning (Power Query)

Main problems fixed:

- Two completely empty columns and one corrupted header
- Extra spaces and unclean text in text columns
- `Returns` text converted into a numeric `Is Returned` flag
- Day-first dates parsed correctly using the en-GB locale
- Added Order Year, Month Number, and Month Name

The full cleaning log is in `SuperStore_Cleaning_Log.xlsx`.

## Key Metrics

- Total Sales: 1.57M
- Total Profit: 175K
- Profit Margin: 11.2%
- Orders: 3,003
- Customers: 773

## Key Findings

1. **Growth came with lower margins.** Sales grew about 77% from 2019 to 2020 (564.7K to 1.00M), but profit grew only about 14% (81.8K to 93.4K). Profit margin fell from about 14.5% to 9.3%.
2. **Technology is the profit engine.** It earns a margin of about 19%, while Furniture sells 451K but earns only about 2%.
3. **Tables lose money.** The Tables sub-category has a net loss of about 11.1K on 119K of sales, and Supplies is also negative.
4. **California leads.** It generates about 21% of total sales (335K), followed by New York and Texas.
5. **West is the strongest region** (522K sales, 13% margin), while Central has the weakest margin (8%).
6. **Sales peak at the end of the year.** December, November, and September are the top three months by sales.

## Limitations

- The file is a sample (5,901 rows), so results reflect this sample only.
- `Row ID` is not unique, and 28 Product IDs map to more than one product name, so the analysis uses Order ID and Product Name.
- `Returns` is filled only for 2020, so return rates for 2019 are not reliable.
- 14 rows have Profit greater than Sales. They were kept as in the source and flagged in the cleaning log.

## Tools

Power Query, DAX, Power BI (data model, bookmarks, navigation), Deneb (Vega-Lite)

## How to Use

1. Download `SuperStore_SalesDashboard.pbix` from this repository.
2. Open it in Power BI Desktop.
3. If Power BI asks for the data source, point it to `SuperStore_Sales_Dataset.csv` (Transform data, then Data source settings).

## Contact

LinkedIn: https://www.linkedin.com/in/hamza-yosry
