##### IN STATEMENT 

Cette requette affichera que les customers qui ont 20 et 30 ans

```sql
SELECT * FROM customer WHERE age in (20,30)
```

##### BETWEEN STATEMENT 

Cette requette affichera tous les customers que leurs ages est entre 20 et 30 ans

```sql
SELECT * FROM customer WHERE age BETWEEN 20 AND 30
```

##### LIKE STATEMENT

Cette requette affichera tous customers ayant le prenom 'Claire' dans sans nom : 

- "%ma_chaine" : % au debut veut dire le mot 'Claire' ne sera pas au debut du nom
- "ma_chaine%" : % a la fin veut dire le mot 'Claire' peut etre à la fin du nom
- "%ma_chaine%" : % au debut et a la fin veut dire le mot 'Claire' n'importe ou dans le nom


```sql
SELECT * FROM customer WHERE customer_name LIKE '%Claire%'
```
