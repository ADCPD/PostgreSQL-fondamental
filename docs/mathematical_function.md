#### MAX 

La fonction d’agrégation `MAX()` permet de retourner la valeur maximale d’une colonne dans un set d’enregistrement. 
```sql
select MAX(sales) from sales
```

#### MIN

La fonction d’agrégation `MIN()` permet de retourner la valeur minimal d’une colonne dans un set d’enregistrement. 

```sql
select MIN(sales) from sales
```
#### FLOOR

La fonction `FLOOR()` renvoie le nombre entier le plus grand, inférieur ou égal à l'expression numérique donnée.

```sql
select sales , FLOOR(sales) from sales

-- Exemple resultat : 261.96 > 	261
```

#### CIEL

La fonction `CIEL()` est utilisée pour obtenir le plus petit entier supérieur ou égal à l'expression numérique spécifiée.

```sql
select sales, CIEL(sales) from sales

-- Exemple resultat : : 261.96 > 	262
```

#### RANDOM

La fonction `RANDOM()` permet de sélectionner un nombre aléatoire à virgule, compris entre 0 et 1. Le résultat de cette fonction sera différent à chaque fois que la fonction est exécutée dans une requête SQL.


```sql
select RANDOM()  -- 5.561448415083099

```

#### SETSEED

La fonction `SETSEED()` retourne une valeur en 1.0 et -1.0

```sql
 select SETSEED(0.5); -- En attend des resultats à partir de 0.5
 select random();
 select random(); -- Exemple : 0.520017612227381
 ```
 
#### ROUND

La fonction `ROUND()` permet d’arrondir un résultat numérique.
Cette fonction permet soit d’arrondir sans utiliser de décimal pour retourner un nombre entier (c’est-à-dire : aucun chiffre après la virgule), ou de choisir le nombre de chiffre après la virgule.

```sql
select sales,  ROUND(sales) from sales.  -- Exemple : 261.96	> 262
```

#### POWER

La fonction `POWER()` renvoie la valeur d'un nombre élevé à la puissance d'un autre nombre.

```sql
select POWER(3, 2) -- Exemple : 9

select sales,  POWER(sales, 2) from sales.  -- Exemple : 8.56	> 73.2736
```
