#### INDEX : 
Les `index` sont des ressources très utiles qui permettent d’accéder plus rapidement aux données. 

Un `index`, dans une base de données se base sur le même principe qu’un `index` dans un livre. 
Avec un `index` placé sur une ou plusieurs colonnes le système d’une base de données peut rechercher les données d’abord sur l’`index` et s’il trouve ce qu’il cherche il saura plus rapidement où se trouve les enregistrements concernés.

Généralement un index pourra être utilisé dans les requêtes utilisant les clauses `WHERE`, `GROUP BY` ou `ORDER BY`. 
Lorsqu’une base de données possède un grand nombre d’enregistrements (exemple: plusieurs milliers ou plusieurs millions de lignes) 
Un `index` permet de gagner un temps précieux pour la lecture de données.

> Ces petites ressources ont toutefois leurs inconvénients car cela occupe de l’espace supplémentaire dans la base de données. 
> Par ailleurs, l’insertion de données est plus long car les index sont mis à jour à chaque fois que des données sont insérées.

```SQL
create INDEX mon_idx on month_values(MM); 

drop INDEX mon_idx;
```

##### Bonne pratiques : 

1. Construire un index sur des colonnes de type entier
2. Gardez l'index aussi restreint que possible
3. L'ordre des colonnes est important
4. Assurez-vous que la colonne pour laquelle vous créez un index est déclarée NON NULL
5. Créez un index uniquement lorsque cela est nécessaire
