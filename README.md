# Mrs. DIY Sales & Logistics Dashboard (Power BI)

> Portfolio project using a **sample/training dataset** (not real company
> data). Currency: Malaysian Ringgit (RM). Period: May-June.

## Business Questions
**Sales Manager**
- Which products generate the highest revenue?
- What is the total sales revenue over time?
- Which payment methods are most commonly used?

**Operations Manager**
- Which shipping method performs best and worst?
- What are the busiest shipping days or peak delivery periods?
- Which locations have the best on-time performance?

## Tools
Power BI, Power Query, DAX, Excel

## Data Model
Star schema with **Orders** as the central table, linked one-to-many to
**Customers**, **Product** and **Shipping** using shared keys.

![Data Model](images/01-data-model.jpg)

## Data Transformation (Power Query)
- Split "City, State and Postal Code" into separate columns
- Removed duplicates on primary keys (Customer ID, Product Category ID,
  Shipping ID)
- Merged Ship Code + Ship Reference Number to create a Shipping ID that
  matches the Orders table

![Transformation](images/02-data-transformation.jpg)

## DAX
- `Total Sales = SUM('Orders'[Sales])`
- `Total Profit = SUM('Orders'[Profit])`
- `Profit Margin = DIVIDE([Total Profit], [Total Sales], 0)`
- Calculated column `Delivery Timing New`: Early (<=10 days),
  On Time (11-20 days), Late (>20 days). Thresholds are my own assumption.

![DAX](images/03-dax-measures.jpg)

## Key Findings
| Question | Answer |
|---|---|
| Top products | Machines, Chairs and Tables lead sales |
| Total sales | RM344.24K at a 7.38% profit margin |
| Payment methods | Visa and Mastercard make up 91.38% of orders |
| Shipping performance | Standard Class has the most late deliveries (381) |
| Peak delivery days | End of month, about 53 deliveries per day |
| Delivery by location | Kota Kinabalu performs best; Johor Bahru is worst (36.21% late) |

## Recommendations
1. Review Standard Class courier performance, since it has the most late
   deliveries.
2. Investigate causes of delays in Johor Bahru.
3. Plan extra delivery capacity for the end of each month.
4. [Add your own, such as encouraging e-wallet payments.]

## Dashboard
![Summary](images/04-dashboard-summary.jpg)
![Overview](images/05-dashboard-overview.jpg)
![Product](images/06-dashboard-product.jpg)
![Logistics](images/07-dashboard-logistics.jpg)

## What I Learned
[One or two sentences, e.g. data cleaning, key relationships, DAX.]

## Contact
[Danial Bin Azmy] | [www.linkedin.com/in/danial-azmy] | [Danial3034@gmail.com]
