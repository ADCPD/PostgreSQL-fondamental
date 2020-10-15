### USER ACCESS CONTROL FUNCTIONS

#### LISTING DATA BASE USER
```sql
select * from pg_user
```
#### CREATE USER
`CREATE USER` permet de créer un compte de base de données qui vous permet de vous connecter à la base de données.

```sql
CREATE USER johnDoe with password 'jd2020!'
```

#### GRANT & REVOKE
Les privilèges sur les tables peuvent être contrôlés à l'aide de `GRANT` & `PROVOKE`. 
Ces autorisations peuvent être n'importe quelle combinaison de `SELECT`, `INSERT`, `UPDATE`, `DELETE`, `INDEX`, `ALTER`, `DROP`, `GRANT` OPTION ou `ALL`.

**Syntax :**

```sql
GRANT privileges ON object TO user;

REVOKE privileges ON object FROM user;
```

**List des privileges et leurs descriptions :**
- `SELECT` : possibilité d'exécuter l'instruction SELECT sur la table
- `INSERT` : possibilité d'exécuter l'instruction INSERT sur la table
- `UPDATE` : possibilité d'exécuter l'instruction UPDATE sur la table
- `DELETE` : possibilité d'exécuter l'instruction DELETE sur la table
- `TRUNCATE` : possibilité d'exécuter l'instruction TRUNCATE sur la table
- `REFERENCES` : possibilité de créer des clés étrangères (privilèges requis sur les tables parent et enfant)
- `TRIGGER` : possibilité de créer un TRIGGER dans la table
- `CREATE` : possibilité d'exécuter l'instruction CREATE sur la table
- `ALL` : possibilité d'avoir tous les privilèges

**Syntax :**
```sql
GRANT SELECT, INSERT, UPDATE, DELETE ON product TO  johndoe;

GRANt ALL ON product to johndoe;

GRANT SELECT ON product to PUBLIC; -- donner le doit du listing à tout le monde

-- Retirer tout les droits de johndoe sur la table product
REVOKE ALL ON product FROM johndoe;
```
#### DROP USER

`DROP USER` est utilisé pour effacer un utilisateur quelconque de la base de données.

**Syntax :**
```sql
DROP USER johndoe;
```
#### ALTER USER

`DROP USER` est utilisé pour changer le nom d'un utilisateur de la base de données.

**Syntax :**
```sql
ALTER USER johndoe RENAME TO jdoe;
```

#### USER Fonctionnalités :

`pg_stat_activity` permet de retourner les informations relative à la connexion des utilisateurs à la base de données.

```sql
SELECT DISTINCT * FROM pg_stat_activity; 
```


