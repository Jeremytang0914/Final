# Final
## Question 1
--Which country has the most companies from the dataset?

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

```sql
SELECT avg(profits)
FROM datasets.forbes_global_2010_2014
where industry = 'Major Banks' 

```
Answer: 4.5754

## Question 5
--Which industry has the highest market value in Asia?

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

```sql
SELECT 
sum(marketvalue) as total_marketvalue
FROM datasets.forbes_global_2010_2014 
```
Answer: 44410.3

## Question 7
-- How many countries on the list?

```sql
count(country)
FROM datasets.forbes_global_2010_2014 
```
Answer: 2000

## Question 8
--What are the top 3 sectors in the United States?

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

```sql
SELECT 
sum(assets)
FROM datasets.forbes_global_2010_2014
where sector= 'Energy'
```
Answer: 6564.7

## Question 10
--Which continent has most companies?

```sql
SELECT 
continent,
count(company)
FROM datasets.forbes_global_2010_2014
group by continent
order by count (company) DESC
```
![Final](Visualization/final10.png)



