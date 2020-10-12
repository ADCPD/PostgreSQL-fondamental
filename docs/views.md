##### VIEWS

Une vue est une table virtuelle basée sur l'ensemble de résultats d'une instruction SQL.

Une vue contient des lignes et des colonnes, tout comme une vraie table. Les champs d'une vue sont des champs d'une ou plusieurs tables réelles de la base de données.

Vous pouvez ajouter des fonctions SQL, des instructions WHERE et JOIN à une vue et présenter les données comme si les données provenaient d'une seule table.

```SQL
CREATE VIEW logistique as 
	select s.order_line,
	s.order_id, c.customer_name, c.city, c.state, c.country
	from sales as s
	left join customer as c ON s.customer_id = c.customer_id
	order by s.order_line
	
select * from logistique
```
> Ce model est intressant si vous avez un systeme d'export de données ou generation des data pour un traitement specifique.
