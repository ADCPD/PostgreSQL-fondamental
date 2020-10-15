#### TABLESPACES

Les `tablespaces` permettent aux administrateurs de tables de données de définir des emplacements dans le système de fichiers 
où les fichiers représentant des objets de base de données peuvent être stockés.

*Exemple : *

```SQL
CREATE TABLESPACE newspace LOCATION 'c:/Program Files/PostgreSQl/10/data/Storage';

CREATE TABLE customer_test(test_column int) TABLESPACE newSpace;

SET default_tablespace = newSpace;
CREATE TABLE soldes_test(test_column int);

SELECT newSpace FROM pg_tableSpace;
```
