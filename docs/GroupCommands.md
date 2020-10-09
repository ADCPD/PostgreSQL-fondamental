#### GROUP BY Statement

Affichier le nombre de customer par ville

```sql
select 
city, count(city) as customer_count
from customer
GROUP BY city,age
```

#### HAVING Statement
`HAVING` est utilisées en combinaison avec la clause `GROUP BY` pour restreindre les lignes retournées à celles dont la condition est `TRUE`

```sql
select 
region, count(customer_id) as customer_count
from customer
GROUP BY region
HAVING count(customer_id)>200
```
