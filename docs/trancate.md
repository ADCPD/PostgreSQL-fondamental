#### TRANCATE

L'instruction de table `TRUNCATE` est utilisée pour supprimer tous les enregistrements d'une table ou d'un ensemble de tables dans PostgreSQL.
Elle remplit la même fonction qu'une instruction `DELETE` sans clause WHERE.

```SQL
TRUNCATE TABLE customer;

-- SAME AS 

DELETE FROM customer;
```
