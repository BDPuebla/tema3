# Ejemplo de modificación de tablas

Vamos a ver un ejemplo de cómo modificar una tabla existente en una base de datos utilizando el comando SQL `ALTER TABLE`. Supongamos que tenemos una tabla llamada `empleados` con las siguientes columnas:

```sql
CREATE TABLE empleados (
    id INT PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL,
    apellido VARCHAR(50) NOT NULL,
    salario DECIMAL(10, 2) NOT NULL
);
```

Ahora, supongamos que queremos modificar la tabla `empleados` para agregar una nueva columna llamada `departamento` de tipo `VARCHAR(50)` y no nula. Para hacer esto, utilizamos el comando `ALTER TABLE`:

```sql
ALTER TABLE empleados
ADD COLUMN departamento VARCHAR(50) NOT NULL;
```

En este caso, hemos agregado una nueva columna llamada `departamento` a la tabla `empleados`. Ahora, la estructura de la tabla `empleados` se verá así:

```sql
CREATE TABLE empleados (
    id INT PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL,
    apellido VARCHAR(50) NOT NULL,
    salario DECIMAL(10, 2) NOT NULL,
    departamento VARCHAR(50) NOT NULL
);
```

!!! note
    Este último fragmento es para conocer la estructura actual de la tabla después de la modificación. En este caso, hemos agregado una nueva columna llamada `departamento` a la tabla `empleados`.

Como vemos, la modificación de tablas es un proceso importante en la gestión de bases de datos, ya que permite adaptar la estructura de las tablas a los cambios en los requisitos del negocio o para corregir errores en el diseño original. Es importante realizar estas modificaciones con cuidado y probar adecuadamente para asegurarse de que no se introduzcan errores o inconsistencias en la base de datos.

Veamos otro ejemplo de cómo modificar una tabla existente en una base de datos. Supongamos que queremos cambiar el tipo de datos de la columna `salario` de la tabla `empleados` a `FLOAT`. Para hacer esto, utilizamos el comando `ALTER TABLE`:

```sql
ALTER TABLE empleados
MODIFY COLUMN salario FLOAT;
```

Por otro lado, como podemos hacer una modificación de borrar una columna, supongamos que queremos eliminar la columna `apellido` de la tabla `empleados`. Para hacer esto, utilizamos el comando `ALTER TABLE`:

```sql
ALTER TABLE empleados
DROP COLUMN apellido;
```