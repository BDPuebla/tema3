# Modificación de tablas

Para modificar la estructura de una tabla existente en una base de datos, se utiliza el comando SQL `ALTER TABLE`. Este comando permite realizar cambios en la tabla sin perder los datos existentes. A continuación, se presentan algunos ejemplos de cómo modificar tablas utilizando el comando `ALTER TABLE`.

```sql
ALTER TABLE nombre_tabla
ADD nombre_columna tipo_dato;
```

Por ejemplo en el ejemplo anterior, se añade una nueva columna llamada `nombre_columna` de tipo `tipo_dato` a la tabla `nombre_tabla`.

No existe una única forma de modificar una tabla, ya que depende de los cambios que se deseen realizar. Se puede realizar:

* Agregar una nueva columna a la tabla.
* Cambiar el tipo de datos de una columna existente.
* Eliminar una columna de la tabla.
* Cambiar el nombre de una columna existente.
* Cambiar el nombre de la tabla.
* Cambiar las restricciones de la tabla, como agregar o eliminar claves primarias o foráneas.

Vamos a ver cada uno de estos casos.

## Agregar una nueva columna a la tabla

Agregar una nueva columna a una tabla existente se puede hacer utilizando el comando `ALTER TABLE` seguido de `ADD`. Por ejemplo, para agregar una columna llamada `nueva_columna` de tipo `VARCHAR(50)` a la tabla `mi_tabla`, se puede utilizar la siguiente sentencia SQL:

```sql
ALTER TABLE mi_tabla
ADD COLUMN nueva_columna VARCHAR(50) NOT NULL;
```

Por ejemplo en este caso se añade una nueva columna llamada `nueva_columna` de tipo `VARCHAR(50)` a la tabla `mi_tabla`. Es importante tener en cuenta que al agregar una nueva columna, se pueden establecer valores predeterminados o permitir valores nulos según sea necesario.

Vemos como en este caso se añade el tipo de dato y las correspondientes restricciones a la nueva columna. En este caso, se establece que la columna no puede contener valores nulos (`NOT NULL`).

## Cambiar el tipo de datos de una columna existente

Para cambiar el tipo de datos de una columna existente, se puede utilizar el comando `ALTER TABLE` seguido de `MODIFY` o `ALTER COLUMN`, dependiendo del sistema de gestión de bases de datos que se esté utilizando. Por ejemplo, para cambiar el tipo de datos de la columna `mi_columna` a `INT` en la tabla `mi_tabla`, se puede utilizar la siguiente sentencia SQL:

```sql
ALTER TABLE mi_tabla
MODIFY mi_columna INT;
```

En este caso se cambia el tipo de datos de la columna `mi_columna` a `INT` en la tabla `mi_tabla`. Es importante tener en cuenta que al cambiar el tipo de datos de una columna, se deben considerar los posibles efectos en los datos existentes y en las aplicaciones que dependen de esa columna.

También es importante saber que se pueden añadir algunas restricciones a la columna, como `NOT NULL`, `UNIQUE`, `PRIMARY KEY`, entre otras, según sea necesario. Por ejemplo, para cambiar el tipo de datos de la columna `mi_columna` a `INT` y establecerla como clave primaria, se puede utilizar la siguiente sentencia SQL:

```sql
ALTER TABLE mi_tabla
MODIFY mi_columna INT PRIMARY KEY;
```


## Eliminar una columna de la tabla

Para eliminar una columna de una tabla existente, se puede utilizar el comando `ALTER TABLE` seguido de `DROP COLUMN`. Por ejemplo, para eliminar la columna `mi_columna` de la tabla `mi_tabla`, se puede utilizar la siguiente sentencia SQL:

```sql
ALTER TABLE mi_tabla
DROP COLUMN mi_columna;
```

Donde `mi_columna` es el nombre de la columna que se desea eliminar y `mi_tabla` es el nombre de la tabla de la cual se desea eliminar la columna. Es importante tener en cuenta que al eliminar una columna, se perderán todos los datos almacenados en esa columna, por lo que se debe tener precaución al realizar esta operación.

Es importante tener en cuenta las correspondientes restricciones y dependencias que puedan existir en la columna que se desea eliminar, como claves foráneas o índices, ya que estas restricciones pueden impedir la eliminación de la columna. En caso de que existan dependencias, se deben eliminar o modificar antes de eliminar la columna.

## Cambiar el nombre de una columna existente

Para cambiar el nombre de una columna existente, se puede utilizar el comando `ALTER TABLE` seguido de `RENAME COLUMN`. Por ejemplo, para cambiar el nombre de la columna `mi_columna` a `nueva_columna` en la tabla `mi_tabla`, se puede utilizar la siguiente sentencia SQL:

```sql
ALTER TABLE mi_tabla
RENAME COLUMN mi_columna TO nueva_columna;
```

Es importante tener en cuenta que al cambiar el nombre de una columna, se deben actualizar todas las referencias a esa columna en las consultas y aplicaciones que dependan de ella. Además, es recomendable realizar pruebas para asegurarse de que el cambio de nombre no afecte la funcionalidad de la base de datos y las aplicaciones que la utilizan.

## Cambiar el nombre de la tabla

Para cambiar el nombre de una tabla existente, se puede utilizar el comando `ALTER TABLE` seguido de `RENAME TO`. Por ejemplo, para cambiar el nombre de la tabla `mi_tabla` a `nueva_tabla`, se puede utilizar la siguiente sentencia SQL:

```sql
ALTER TABLE mi_tabla
RENAME TO nueva_tabla;
```

Hay que tener en cuenta que al cambiar el nombre de una tabla, se deben actualizar todas las referencias a esa tabla en las consultas y aplicaciones que dependan de ella. 

## Cambiar las restricciones de la tabla

Por último, para cambiar las restricciones de una tabla, se puede utilizar el comando `ALTER TABLE` seguido de la acción correspondiente. Por ejemplo, para agregar una clave primaria a la columna `mi_columna` en la tabla `mi_tabla`, se puede utilizar la siguiente sentencia SQL:

```sql
ALTER TABLE mi_tabla
ADD PRIMARY KEY (mi_columna);
```

También se pueden eliminar restricciones existentes utilizando el comando `ALTER TABLE` seguido de `DROP CONSTRAINT`. Por ejemplo, para eliminar una clave primaria existente en la tabla `mi_tabla`, se puede utilizar la siguiente sentencia SQL:

```sql
ALTER TABLE mi_tabla
DROP CONSTRAINT nombre_restriccion;
```

En el caso de añadir una clave foránea a una columna existente, se puede utilizar la siguiente sentencia SQL:

```sql
ALTER TABLE mi_tabla
ADD CONSTRAINT nombre_restriccion FOREIGN KEY (mi_columna) REFERENCES otra_tabla(otra_columna);
```