## Sales Insights Data Analysis Project

#Dashboard
[![Dashboard](https://raw.githubusercontent.com/minlin-ml/sales-insight-tableau/main/Dashboard.png)](https://prod-ca-a.online.tableau.com/t/minlin/views/SalesInsightsPhase1/Dashboard1/53d03169-d868-4182-aa10-a9347f8ea4ad/ff7550e3-ab51-4843-8351-a12d77d1a840?:display_count=n&:showVizHome=n&:origin=viz_share_link)

[Source](https://www.youtube.com/watch?v=CCNd2fUfFkk&list=PLeo1K3hjS3usDI9XeUgjNZs6VnE0meBrL&index=1)

1. SQL database dump is in db_dump.sql file above. Download `db_dump.sql` file to your local computer and import it as per instructions given in the tutorial video

### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`




