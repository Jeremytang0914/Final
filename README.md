# Checkpoint3
Database: forbes_global_2010_2014

The Forbes Global 2000 is an annual ranking of the top 2,000 public companies in the world by Forbes magazine. The ranking is based on a mix of four metrics: sales, profit, assets and market value. The list has been published since 2003. Our dataset is consist of 2000 rows and 10 columns. The columns are rank, company, country, continent, sector, industry, market value, sales, profits and assets. Our purpose of studying this dataset is to figure out what kind of industries are currently the most profitable and popular and what the top countries currently having these companies.





## Question 1
--Which country has the most companies from the dataset?

In our first question, we want to know in this Forbes’ world largest companies top 2000, which country have most companies on this ranking, we believe, the more companies on this rank, the better the country’s economy is.


```sql
SELECT 
country,
count(company)
FROM datasets.forbes_global_2010_2014
group by country
order by count (company) DESC 
```
![Final](Visualization/final1.png)

## Question 2
--Which is the most popular sector from the list?

we are interested in finding out which sector nowadays are the most popular, which probably indicates the most profitable.
And the result is Financial sector, which is as we expected to be.

```sql
SELECT sector,
count(*) 
FROM datasets.forbes_global_2010_2014
group by sector
order by count DESC
```
![Final](Visualization/final2.png)

## Question 3
--What industries does most companies in?

This question is asking which industries are currently the most popular and profitable in the Forbes 2000 companies. The top 5 industries are Regional banks, oil and gas operations, electric utilities, investment service, and real estate are the top 5 industries in the Forbes 2000. 

```sql
SELECT 
industry,
count(company)
FROM datasets.forbes_global_2010_2014
group by industry
order by count (company) DESC 
```
![Final](Visualization/final3.png)

## Question 4
--What is the average profit of major banking industry?

The previous slide shows that regional bank industry has most companies in the Forbes Global 2000 list. However, the regional bank industry is usually controlled by the government. So we wonder how much exactly is the average profit of major banking industry since it is industry that people could actually invest on. The result is $4.57 billion dollar annually which is huge profitable number. 

```sql
SELECT avg(profits)
FROM datasets.forbes_global_2010_2014
where industry = 'Major Banks' 

```
Answer: 4.5754

## Question 5
--Which industry has the highest market value in Asia?

The Asian market is currently one of most attractive emerging market for investors and everyone is willing to enter the Asian market. So we want to know which industry has the highest market value in Asia. The top 5 industries in Asia are Regional Banks, Oil & Gas Operations, Telecommunications services, Major Banks and Auto & Truck Manufacturers.

```sql
SELECT 
industry,
sum(marketvalue) as total_marketvalue
FROM datasets.forbes_global_2010_2014 
where continent = 'Asia'
Group by industry
Order by total_marketvalue DESC
```
![Final](Visualization/final5.png)

## Question 6
--What is the total market value of financial sector?

As we discussed earlier, financial sector is recently the most popular sector in Forbes top 2000 businesses. And we are hoping to know the total market value of it, since it is a big thing going on internationally. And the total MV is $44 hundred billion, which we stack up together will be as tall as 4 burj khalifas. 


```sql
SELECT 
sum(marketvalue) as total_marketvalue
FROM datasets.forbes_global_2010_2014 
```
Answer: 44410.3

## Question 7
-- How many American companies on the list?

For this question, we look for the total number of american companies. We used COUNT function for the number of companies and limited the range by using where country= 'United States'

```sql
SELECT
count(company)
from datasets.forbes_globa_2010_2014
where country= 'United States'
```


## Question 8
--What are the top 3 sectors in the United States?

For this question, we just want to know what sectors in the U.S. made most profits. We select all the sectors in the U.S. and order it by rank ASC. And then we got our most profitbale sectors.

```sql
SELECT 
sector
FROM datasets.forbes_global_2010_2014
where country= 'United States'
order by rank ASC
```
![Final](Visualization/final8.png)

## Question 9
--What is the total assets of the energy sector?

For this question, we are looking for the total assets in the energy sector. We have the number of assets for every sector in the database, so we just sum up the asset column under the energy sector. And we got the answer of 6564.7.

```sql
SELECT 
sum(assets)
FROM datasets.forbes_global_2010_2014
where sector= 'Energy'
```
Answer: 6564.7

## Question 10
--Which continent has most companies?

For this question,we want to find out which continent has most companies listed on the forbes global. The database provides all the company names and continent. We select the column "Continent" and the count the number of companies. Then use order by DESC which will rank the highest number first.

```sql
SELECT 
continent,
count(company)
FROM datasets.forbes_global_2010_2014
group by continent
order by count (company) DESC
```
![Final](Visualization/final10.png)



