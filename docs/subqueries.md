##### Subqueries 

Le principe, c'est d'utilisé une requete à partir d'une autre

```sql
select * from sales where customer_ID in (SELECT DISTINCT customer_id FROM customer WHERE age > 60)
```
