#### CURRENT DATE & TIME

```sql
select CURRENT_DATE;  -- Returne date du jour en format YYYY-MM-DD

select CURRENT_TIME;  -- Retourne l'heure du moment d'execution. Exemple : "13:17:55.913558+02:00"

select CURRENT_TIME(1); -- Retourne l'heure du moment d'execution. Exemple : "13:19:36.900000+02:00"

select CURRENT_TIMESTAMP; -- Retourne la date complete. Exemple : "2020-10-13 13:20:35.783549+02"
```

#### AGE

La fonction `AGE()` retourne le nombre des années entre deux DATE

```sql
select AGE('2020/06/24', '1988/06/24'); -- Resultat : "32 years"

select order_line, order_date, ship_date,
	AGE(ship_date,order_date) as time_taken
	from sales 
order by time_taken DESC

--  Exemple resultat : 5351 >	"2017-12-09"	> "2017-12-16"	> "7 days"
```

#### EXTRACT 

La fonction `EXTRACT()` permet d'extraire une unité à partir d'une DATE 

```SQL

select CURRENT_TIMESTAMP;

select EXTRACT(day from CURRENT_TIMESTAMP); -- 13

select EXTRACT(month from CURRENT_TIMESTAMP); -- 10

select EXTRACT(year from CURRENT_TIMESTAMP); -- 2020

select EXTRACT(hour from CURRENT_TIMESTAMP); -- 13H

select EXTRACT(minute from CURRENT_TIMESTAMP); -- 23 minutes

select EXTRACT(second from CURRENT_TIMESTAMP); -- 1.878123 seconds

select EXTRACT(epoch from CURRENT_TIMESTAMP); -- Afficher nombres second depuis 1970-01-01 à partir de la date courrante

```

[ Voir plus ... ](https://www.postgresql.org/docs/9.1/functions-datetime.html)
