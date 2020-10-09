##### COUNT Function 

Retourner le nombre des Consumers assuciée à la table `customer`

```sql
select COUNT(segment) as customer_number from customer where segment = 'Consumer'
```

##### SUM Function 

Afficher la somme des elements vendu qui ont une remise à 0%

```sql

select SUM(sales) from sales where discount = 0

```

##### AVERAGE Function 

Afficher la moyenne age des customers

```sql
select AVG(age) as "Average Customer age" from customer 

```

##### MIN / MAX Function 

```sql
-- Age max Customer
select MAX(age) from customer 

-- Age min Customer
select MIN(age) from customer 
```
