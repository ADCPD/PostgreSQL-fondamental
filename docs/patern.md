##### PATERN Matching : 
1. LIKE statement 
2. SIMILAR TO statement
3. REGULAR Expressions

#### LIKE
Retourner tous les produits ayant un code commancant par 'FUR-'

```SQL
select product_id from sales where  product_id LIKE 'FUR-%'
```

Retourner tous les produits hors ceux qui ont le code commancant par 'FUR-'

```SQL
select product_id from sales where product_id NOT LIKE 'FUR-%'
```

#### SIMILAR

Retourner tous les produits ayant un code commancant par 'FUR-'

```SQL
select product_id from sales where  product_id SIMILAR TO 'FUR-%'
```

Retourner tous les produits hors ceux qui ont le code commancant par 'FUR-'

```SQL
select product_id from sales where product_id NOT SIMILAR TO 'FUR-%'
```

#### REGULAR Expressions (La [documentation](https://www.postgresql.org/docs/9.3/functions-matching.html) pour plus de details)

```SQL

```
