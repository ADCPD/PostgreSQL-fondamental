### PERFOMRANCE TUNING TIPS

#### EXPLAIN : 
Affiche le plan d'exécution d'une instruction de requête sans exécuter la requête

**Syntax :**

```TEXT
EXPLAIN [VERBOSE] query;

VERBOSE : affiche le plan de requête complet au lieu d'un simple résumé

query: l'instruction de requête pour expliquer
```

**Exemple :**
```SQL
EXPLAIN SELECT * FROM customer;

-- Result : "Seq Scan on customer  (cost=0.00..19.93 rows=793 width=81)"
```

```SQL
EXPLAIN SELECT DISTINCT * FROM customer;

-- Result : 
-- "HashAggregate  (cost=37.77..45.70 rows=793 width=81)"
-- "  Group Key: customer_id, customer_name, segment, age, country, city, state, postal_code, region"
-- "  ->  Seq Scan on customer  (cost=0.00..19.93 rows=793 width=81)"
```

#### SOFT DELETE Vs HARD DELETE

`SOFT DELETE` : (suppression réversible) signifie que vous ne supprimez pas réellement l'enregistrement au lieu de ca vous les marquez comme supprimé

`HARD DELETE` : (suppression forcée) signifie que les données sont physiquement supprimées définitivement de la table de base de données.

#### UPDATE Vs CASE

`UPDATE` : 

**Syntax :**
```SQL
 UPDATE customer SET customer_name = (trim(upper(customer_name))) WHERE (trim(upper(customer_name)) <> customer_name
```
Chaque ligne de mise à jour est en fait une `SOFT suppression` et une insertion. Ainsi, la mise à jour de chaque ligne augmentera la taille de stockage de la table

`CASE STATEMENT` : Vous pouvez utiliser l'instruction `CASE` lors de la création d'une table


#### VACCUM

**Syntax :**
```SQL
VACCUM [table]
```
- récupérer l'espace disque occupé par les lignes marquées pour suppression par les opérations UPDATE et DELETE précédentes
- compacte la table pour libérer de l'espace consommé
- utilisez-le sur les tableaux que vous mettez à jour et vous les supprimez régulièrement

> `VACCUM` permet d'optimisée les espaces consommer par les tables de base données suite multiple insertion ou suppression de données

#### TRUNCATE Vs DELETE

- L'instruction `TRUNCATE` est généralement beaucoup plus efficace que l'utilisation de l'instruction `DELETE` sans clause `WHERE` pour vider la table.
- `TRUNCATE` nécessite moins de ressources et moins de frais de journalisation
- Au lieu de créer une table à chaque fois, essayez d'utiliser `TRUNCATE` car cela gardera la structure et les propriétés de la table intactes
- `TRUNCATE`libère de l'espace et impossible de revenir en arrière

#### STRING FUNCTION

**Pattern Matching :**
- Dans la mesure du possible, utilisez l'instruction LIKE à la place de l'expression REGEX.
- N'utilisez pas d'instructions 'Similaire à', utilisez plutôt LIKE et REGEX.
- Evitez les opérations de chaîne inutiles telles que REPLACE, UPPER, LOWER, etc.

**String Operations :**
- Utilisez `TRIM` au lieu de remplacer autant que possible.
- Evitez les colonnes String inutiles. Pour par exemple : Utilisez des formats de date au lieu d'une chaîne pour les dates

#### JOIN

**Syntax :**
```SQL
 SELECT 
    s.order_line, 
    s.product_id, 
    c.customer_name, 
    c.age 
 FROM sales as s
  LEFT JOIN customer c ON s.customer_id = c.customer_id
 ORDER BY customer_id;
```
- Utilisez des `subqueries` pour sélectionner uniquement les champs obligatoires dans les tables
- Eviter d'utiliser une ou plusieurs jointures en mentionnant la clause Group by sur les champs correspondants

#### SCHEMAS

1. Pour permettre à de nombreux utilisateurs d'utiliser une base de données sans interférer les uns avec les autres
2. Pour organiser les objets de la base de données en groupes logiques pour les rendre plus faciles à gérer
3. Les applications tierces peuvent être placées dans des schémas distincts afin de ne pas entrer en collision avec les noms d'autres objets
4. Vous pouvez avoir un ou plusieur schemas dans la meme base de données.

**Syntax :**

```SQL
CREATE SCHEMA testschema;

CREATE TABLE testschema.customer AS SELECT * FROM customer; -- creer une copie de la table customer dans le schema testschema
```
