###   STRING FUNCTIONS

##### LENGTH
Retourne la longeure d'une chaine de caractaires
```sql
select customer_id, LENGTH(customer_id) from customer
```

##### UPPER & LOWER

```sql
-- UPPER : returne une chaine de caractaire totalement majuscule 
select customer_name, UPPER(customer_name) from customer

-- LOWER : returne une chaine de caractaire totalement minuscule  
select customer_name, LOWER(customer_name) from customer
```

##### REPLACE

```sql
-- A chaque fois qu'on trouve "United States". On va essaye de la remplacer par  "USA"

select country , REPLACE(country, 'United States', 'USA' ) as country_code from customer
```
##### TRIM ,LTRIM & RTRIM

```sql
-- Effacer les espaces en debut de la chaine de caractères
select TRIM(LEADING ' ' FROM '  Darrin Van Huff')

-- Effacer les espaces à la fin d'une chaine de caractères
select TRIM(TRAILING ' ' FROM '  Darrin Van Huff ')

-- Effacer les espaces au debut & à la fin d'une chaine de caractères
select TRIM(BOTH ' ' FROM '  Darrin Van Huff ')
```

##### CONCATINATION
`||` permet de faire la concaténation 

```sql
select customer_name, city || ' , ' || state || ' , ' || country as address from customer

-- La requete retourne le nom du customer plus son address. Exemple : "Claire Gute"	"Henderson , Kentucky , United States"
```

##### SUBSTRING
Retouner les customers qui ont le customer_id commancant par "AB"

```sql
select 
	customer_id, customer_name,
	SUBSTRING(customer_id for 2) as cust_group
from customer
where SUBSTRING(customer_id for 2) = 'AB'

-- Exemple de resultat : "AB-10060" -	"Adam Bellavance"	 - "AB"
```

#####  LIST AGGREGATION
`STRING_AGG()` : Concatène les valeurs d'entrée d'une chaîne de caractères et les séparée par un délimiteur.

Afficher la liste des product_id associées aux orders

```sql
SELECT 
	order_id,
	STRING_AGG(product_id,',')
FROM sales
	GROUP BY order_id
  
-- Exemple de resultat : "CA-2014-100090"	- "OFF-BI-10001597,FUR-TA-10003715"
```
