# E-Commerce-Case-Study
This project was analyzed an visualized with Power BI
# An overview of the project phases 
## Data importing: 
First, I checked my data type it’s a csv format I imported the data to the power Bi,
Data Transforming:
• Started with checking the data and cleaning it with power query I removed some rows 
and columns as I won’t need them.
• Filtered the rows to remove the blank and null values.
• Change the data category for the continent, country, region and address and also for all 
the dated columns.
• Delete all unnecessary rows and columns in the tables like the different languages 
describing the products 
## Data Modeling: 
Checked the auto linked relationships between the tables and then I added the relations
between the keys manually
## Data Analysis and visualization: 
• First, I created new columns for Profit, Year, Month and Profit Margin Ratio calculated 
with the below DAXs
- Profit = InternetSale[SalesAmount]-InternetSale[TotalProductCost]
- Year = YEAR('Date'[FullDateAlternateKey])
- Month = FORMAT('Date'[FullDateAlternateKey],"MMMM")
- Profit Margin Ratio= DIVIDE('Product'[profit],'Product'[ListPrice])
• Then I made a new table contains the new measures
- Bikes
Sales=CALCULATE(SUM(InternetSale[SalesAmount]),ProductSubcategory[ProductCategor
yName]= "Bike" )
- previous year orders = 
CALCULATE(DISTINCTCOUNT(InternetSale[SalesOrderNumber]),DATEADD(InternetSale[O
rderDate].[date],-1,YEAR))
- Year Over Year = DIVIDE(DISTINCTCOUNT(InternetSale[SalesOrderNumber])-[previous 
year orders],[previous year orders])
- SalesMTD = TOTALMTD(SUM(InternetSale[UnitPrice]),InternetSale[OrderDate])
- Number of sales = DISTINCTCOUNT(InternetSale[SalesOrderNumber]) 
Then made the visualization as shown in the attached dashboard.
## Business Questions and Insights: 
### 1. Analyze Profit and how much the company gain from the sales. 
Sum of Profit = $12.08 M
AVG of Profit Margin Ratio= 53.35%
This Ratio represents that the company net profit 0.53$ from each dollar of sales granted.
### 2. We want to identify trends in quantity sold by time and Top performing products and 
countries. 
• According to the sales order records, the orders are placed at their highest point in the 
second quarter and at their lowest point in the fourth quarter.
• About the products performance the Bikes are the driving force behind the sales then 
comes the Accessories this helps in promoting and expending these categories for further 
growth in contrast, the data shows no sales orders for the component category despite 
the high-cost amount, so I recommend that this product be promoted more aggressively.
• The Top performing countries are Australia, German, Canada, Northwest this information 
helps in targeting market efforts and optimizing delivery logistics in these countries, and 
also helps to recognize the geographical hotspot for the business.
### 3. Year over Year change in orders QTY. 
The year over year change is increasing significantly and it shows the business growth.
