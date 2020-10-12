[VISULAISER LES JOINS MODELS, ICI](http://cartman34.fr/wp-content/uploads/2017/01/sql_joins.jpg)

##### INNER JOIN 

La commande `INNER JOIN`, aussi appelée `EQUIJOIN`, est un type de jointures très communes pour lier plusieurs tables entre-elles. 
**Cette commande retourne les enregistrements lorsqu’il y a au moins une ligne dans chaque colonne qui correspond à la condition.**

```sql
 	select 
	s.order_line,
	s.customer_id,
	s.sales,
	c.customer_name
	from sales as s
	INNER JOIN customer c ON c.customer_id = s.customer_id
```

##### LEFT JOIN 

La commande `LEFT JOIN` (aussi appelée `LEFT OUTER JOIN`) est un type de jointure entre 2 tables. 
**Cela permet de lister tous les résultats de la table de gauche (left = gauche) même s’il n’y a pas de correspondance dans la deuxième tables.**

```sql
  	select 
	s.order_line,
	s.customer_id,
	s.sales,
	c.customer_name
	from sales as s
	LEFT JOIN customer c ON c.customer_id = s.customer_id
```

##### RIGHT JOIN 

La commande `RIGHT JOIN` (ou `RIGHT OUTER JOIN`) est un type de jointure entre 2 tables qui permet de retourner tous les enregistrements de la table de droite (right = droite) même s’il n’y a pas de correspondance avec la table de gauche. 
S’il y a un enregistrement de la table de droite qui ne trouve pas de correspondance dans la table de gauche, alors les colonnes de la table de gauche auront NULL pour valeur.

```sql
 	select 
	s.order_line,
	s.customer_id,
	s.sales,
	c.customer_name
	from sales as s
	RIGHT JOIN customer c ON c.customer_id = s.customer_id
```

##### FULL OUTER JOIN 

 La commande `FULL JOIN` (ou `FULL OUTER JOIN`) permet de faire une jointure entre 2 tables. 
 **L’utilisation de cette commande permet de combiner les résultats des 2 tables, les associer entre eux grâce à une condition et remplir avec des valeurs NULL si la condition n’est pas respectée.**
 
```sql
 select 
	s.order_line,
	s.customer_id,
	s.sales,
	c.customer_name
	from sales as s
	FULL OUTER JOIN customer c ON c.customer_id = s.customer_id
```

##### CROSS JOIN 

La commande `CROSS JOIN` est un type de jointure sur 2 tables SQL qui permet de retourner le produit cartésien. 
Autrement dit, cela permet de retourner chaque ligne d’une table avec chaque ligne d’une autre table

```sql
create  table month_values (MM integer);
create table year_values (YYYY integer);

insert into month_values values (1), (2), (3), (4), (5), (6), (7), (8), (9), (10), (11), (12);
insert into year_values values (2011), (2012), (2013), (2014), (2015), (2016), (2017);

select * from month_values;
select * from  year_values;

-- CROSS JOIN 

select yv.YYYY , mv.MM
from year_values as yv, month_values as mv
order by  yv.YYYY , mv.MM;

-- En resultat, on aura pour chaque année ces  12 mois affectés. [2011 => 1 , .., 2011 => 12, 2012 => 1, ... ]
```

##### EXCEPT 

la commande EXCEPT s’utilise entre 2 instructions pour récupérer les enregistrements de la première instruction sans inclure les résultats de la seconde requête. 
Si un même enregistrement devait être présent dans les résultats des 2 syntaxes, ils ne seront pas présent dans le résultat final.

```sql
select customer_id from sales
EXCEPT 
select customer_id from customer
order by customer_id
```
> Cette requete retourne les `customer_id` qui sont ajouté dans `sales` et qui ne sont pas dans la table `customer`
Dans notre cas, la requete devrait retourner null

##### UNION 

La commande UNION de SQL permet de mettre bout-à-bout les résultats de plusieurs requêtes utilisant elles-même la commande SELECT. 
C’est donc une commande qui permet de concaténer les résultats de 2 requêtes ou plus. 
Pour l’utiliser, il est nécessaire que chacune des requêtes à concaténer retournes le même nombre de colonnes, avec les mêmes types de données et dans le même ordre.

```sql
select customer_id from sales
UNION 
select customer_id from customer
order by customer_id
```
> Cette requete retourne les `customer_id` qui sont present dans la table `sales` & `customer`
