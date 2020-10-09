##### ORDER BY Statement 

```sql
-- Affichage en order croissant 
select * from customer ORDER BY customer_id ASC

-- Affichage en order decroissant  
select * from customer ORDER BY customer_id DESC
```

##### LIMIT Statement 
Afficher un nombre limité des resultats

```sql
select * from customer order by customer_id DESC 
LIMIT 5
```
