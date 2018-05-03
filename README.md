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
