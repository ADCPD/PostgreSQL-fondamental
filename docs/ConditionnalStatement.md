#### CASE WHEN 

##### SYNTAXE : 

```
CASE WHEN condition THEN result
  [WHEN ...]
  [ELSE result]
END

CASE expression 
  WHEN value THEN result
  [WHEN ...]
  [ELSE result]
END
```

##### EXEMPLE : 

En retour, on aura une case supplimentaire `age_category` avec les informations ['YOUNG', 'Senior Citizen', 'Middle aged']

```sql
select *,
CASE WHEN age < 30 THEN 'YOUNG'
	 WHEN age > 60 THEN 'Senior Citizen'
	 ELSE 'Middle aged'
	 END AS age_category
from customer;
```
