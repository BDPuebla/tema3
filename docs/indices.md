# Índices

Vamos a hablar de los índices, que son estructuras de datos que mejoran la velocidad de las operaciones de búsqueda en una tabla. Los índices permiten a la base de datos localizar rápidamente los registros que cumplen con ciertos criterios, lo que puede mejorar significativamente el rendimiento de las consultas.

Cuando se crea una base de datos, es importante considerar qué columnas deben ser indexadas y cómo se utilizarán los índices en las consultas. La creación de índices puede tener un impacto positivo en el rendimiento de las consultas, pero también puede afectar negativamente el rendimiento de las operaciones de inserción, actualización y eliminación, ya que cada vez que se realiza una de estas operaciones, el índice debe actualizarse.

En muchas ocasiones, los índices se crean automáticamente en las columnas que son claves primarias o claves únicas. Sin embargo, también es posible crear índices adicionales en otras columnas que se utilizan con frecuencia en las consultas.

Es importante conocer los diferentes tipos de índices que se pueden crear, como los índices de árbol B, los índices hash y los índices compuestos. Cada tipo de índice tiene sus propias ventajas y desventajas, y es importante elegir el tipo de índice adecuado para cada situación.

!!! note
    Aunque en este tema no vamos a profundizar en los diferentes tipos de índices, es importante tener en cuenta que la elección del tipo de índice puede afectar significativamente el rendimiento de las consultas y las operaciones de inserción, actualización y eliminación. Por lo tanto, es recomendable investigar y comprender los diferentes tipos de índices antes de crear uno.

Cuando creamos un índice estamos creando una estructura de datos adicional que se almacena en la base de datos y que se utiliza para mejorar el rendimiento de las consultas. Los índices pueden ser creados en una o varias columnas de una tabla, y pueden ser únicos o no únicos.

Veamos como crear un índice en una tabla:

```sql
CREATE INDEX nombre_indice ON nombre_tabla (columna1, columna2, ...);
```

En este caso podemos ver que se crea un índice llamado `nombre_indice` en la tabla `nombre_tabla`, utilizando las columnas `columna1`, `columna2`, etc. como criterios de búsqueda.

Esto hará que las consultas que utilicen estas columnas como criterios de búsqueda sean más rápidas, ya que la base de datos podrá localizar rápidamente los registros que cumplen con estos criterios.

Para borrar un índice, se utiliza la siguiente sintaxis:

```sql
DROP INDEX nombre_indice;
```

Es importante saber que el añadir los índices puede ser perjudicial para inserciones, actualizaciones y eliminaciones, ya que cada vez que se realiza una de estas operaciones, el índice debe actualizarse. Por lo tanto, es importante evaluar cuidadosamente qué columnas deben ser indexadas y cómo se utilizarán los índices en las consultas.

Algunas de las columnas que suelen ser indexadas son:

- Claves primarias y claves únicas: Estas columnas son utilizadas para identificar de manera única cada registro en una tabla, por lo que es importante que estén indexadas para mejorar el rendimiento de las consultas.

* Columnas utilizadas en consultas frecuentes: Si una columna se utiliza con frecuencia en las consultas, es recomendable crear un índice en esa columna para mejorar el rendimiento de las consultas.

* Columnas utilizadas en operaciones de ordenamiento: Si una columna se utiliza para ordenar los resultados de una consulta, es recomendable crear un índice en esa columna para mejorar el rendimiento de las consultas.

* Columnas utilizadas en operaciones de agrupamiento: Si una columna se utiliza para agrupar los resultados de una consulta, es recomendable crear un índice en esa columna para mejorar el rendimiento de las consultas.

* Columnas utilizadas en operaciones de unión: Si una columna se utiliza para unir dos tablas, es recomendable crear un índice en esa columna para mejorar el rendimiento de las consultas.

Veremos más adelante el uso de cada índice cuando veamos el uso de las consultas y cómo se pueden optimizar para mejorar el rendimiento de las mismas.