# Creacion de tablas

En esta sección, veremos cómo crear tablas en SQL, cómo definir sus atributos y restricciones. Más adelante, nos centraremos en la modificación y eliminación de tablas según sea necesario. Además, se presentarán buenas prácticas para la creación de tablas y se discutirán algunos errores comunes que se deben evitar al trabajar con ellas.

En primer lugar, incidir en que solo se hablará de la creación de tablas y no del contenido de las mismas, veremos más adelante las sentencias DML (Data Manipulation Language) que nos permitirán insertar, actualizar y eliminar datos de las tablas creadas.

## Estructura de una tabla

Es importante mencionar que una tabla en una base de datos relacional está compuesta por filas y columnas. Cada fila representa un registro único, mientras que cada columna representa un atributo o campo de ese registro. La estructura de una tabla se define mediante la especificación de sus columnas, tipos de datos y restricciones.

La definición de una tabla en SQL se realiza mediante la sentencia `CREATE TABLE`, donde se especifican los nombres de las columnas, sus tipos de datos y las restricciones que se aplicarán a cada una de ellas.

### Create Table

Una sentencia básica para crear una tabla en SQL tiene la siguiente estructura:

```sql
CREATE TABLE [IF [NOT] EXISTS] esquema.nombre_tabla (
    columna1 tipo_dato [restricciones],
    columna2 tipo_dato [restricciones],
    ...
    columnaN tipo_dato [restricciones]
);
```

Donde:

* `IF [NOT] EXISTS` es una cláusula opcional que permite crear la tabla solo si no existe previamente en la base de datos.
* `esquema` es el nombre del esquema al que pertenece la tabla. Si no se especifica, se utilizará el esquema predeterminado.
* `nombre_tabla` es el nombre que se le asignará a la tabla.
* `columna1`, `columna2`, ..., `columnaN` son los nombres de las columnas que se definirán en la tabla.
* `tipo_dato` es el tipo de dato que se asignará a cada columna, como `INT`, `VARCHAR`, `DATE`, entre otros.
* `restricciones` son las reglas que se aplicarán a cada columna, como `PRIMARY KEY`, `NOT NULL`, `UNIQUE`, entre otras.

Podemos diferenciar que hay que indicar el nombre de la tabla y sus atributos, así como el tipo de dato de cada atributo y las restricciones que se aplicarán a cada uno de ellos.

!!! info
    En MySQl, los nombres de las tablas deben ser únicos en un mismo esquema (BD); además de que deben empezar por una letra y pueden contener letras, números y guiones bajos. No se permiten espacios ni caracteres especiales en los nombres de las tablas.

En el caso de los nombres de las columnas, también deben ser únicos dentro de una misma tabla y seguir las mismas reglas que los nombres de las tablas.

### Atributos

Habrás podido ver que cada atributo tiene un tipo de dato específico, que define el tipo de información que se puede almacenar en esa columna. Algunos de los tipos de datos más comunes en SQL son:

* `INT`: para almacenar números enteros.
* `VARCHAR(n)`: para almacenar cadenas de texto de longitud variable, donde `n` es el número máximo de caracteres permitidos.
* `DATE`: para almacenar fechas en formato `YYYY-MM-DD`.
* `DECIMAL(p, s)`: para almacenar números decimales, donde `p` es la precisión total y `s` es la escala (número de dígitos a la derecha del punto decimal).
* `BOOLEAN`: para almacenar valores booleanos (verdadero o falso).
* `TEXT`: para almacenar cadenas de texto de longitud variable, sin un límite específico.
* `TIMESTAMP`: para almacenar marcas de tiempo que incluyen fecha y hora.
* `BLOB`: para almacenar datos binarios, como imágenes o archivos.

!!! info
    Existe también el tipo de dato `VARCHAR2` en algunas bases de datos, como Oracle, que es similar a `VARCHAR`, pero con algunas diferencias en cuanto a la gestión del almacenamiento y la longitud máxima permitida.

Existen otros tipos de datos específicos para cada sistema de gestión de bases de datos (SGBD), por lo que es importante consultar la documentación del SGBD que se esté utilizando para conocer los tipos de datos disponibles y sus características.

Es importante elegir el tipo de dato adecuado para cada atributo, ya que esto afectará el rendimiento y la eficiencia del almacenamiento de datos en la base de datos. Además, algunos tipos de datos pueden tener restricciones adicionales, como el tamaño máximo permitido o la necesidad de especificar una precisión y escala para los números decimales.

A la hora de seleccionar el tipo de dato para un atributo, es recomendable tener en cuenta el tipo de información que se almacenará en esa columna y las operaciones que se realizarán sobre ella. Por ejemplo, si se espera almacenar solo números enteros positivos, se puede utilizar el tipo de dato `INT UNSIGNED`, mientras que si se espera almacenar texto de longitud variable, se puede utilizar `VARCHAR(n)`.


### Restricciones

Las restricciones son reglas que se aplican a los atributos de una tabla para garantizar la integridad de los datos y evitar inconsistencias. Algunas de las restricciones más comunes en SQL son:

* `CLAVES`: Indican que un atributo es una clave primaria o foránea, lo que garantiza la unicidad y la integridad referencial de los datos.
* `NOT NULL`: Indica que un atributo no puede contener valores nulos, lo que garantiza que siempre se proporcionará un valor para esa columna.
* `DEFAULT`: Permite establecer un valor predeterminado para un atributo en caso de que no se proporcione un valor al insertar un registro.
* `CHECK`: Permite definir una condición que debe cumplirse para que un valor sea válido en un atributo.
* `UNIQUE`: Garantiza que los valores de un atributo sean únicos en toda la tabla, evitando duplicados. Es una clave candidata que no es clave primaria.
* `AUTO_INCREMENT`: Permite que un atributo numérico se incremente automáticamente con cada nuevo registro insertado, lo que es útil para generar identificadores únicos.

Vamos a ver en detalle cada una de estas restricciones y cómo se aplican en la creación de tablas en SQL.

#### Claves

Una clave es un atributo o conjunto de atributos que se utilizan para identificar de manera única un registro en una tabla. Existen dos tipos principales de claves: la clave primaria y la clave foránea.

**PRIMARY KEY**: Es un atributo o conjunto de atributos que identifica de manera única cada registro en una tabla. Una tabla solo puede tener una clave primaria, y los valores de esta clave no pueden ser nulos ni duplicados. La clave primaria se define al crear la tabla mediante la sentencia `CREATE TABLE`, utilizando la cláusula `PRIMARY KEY`.

!!! info
    En MYSQL, solo se puede definir una clave primaria por tabla, pero se pueden definir claves candidatas que no sean clave primaria, utilizando la restricción `UNIQUE`. Estas claves candidatas pueden ser utilizadas para identificar registros de manera única, pero no tienen la misma prioridad que la clave primaria.

**FOREIGN KEY**: Es un atributo o conjunto de atributos que establece una relación entre dos tablas. Una clave foránea en una tabla hace referencia a la clave primaria de otra tabla, lo que permite mantener la integridad referencial entre ambas tablas. La clave foránea se define al crear la tabla mediante la sentencia `CREATE TABLE`, utilizando la cláusula `FOREIGN KEY`. Veamos la sintaxis:

```sql
FOREIGN KEY (columna_foranea) REFERENCES tabla_referenciada(columna_referenciada)
``` 

Vemos como se hare referencia a la tabla y columna que se está referenciando, de manera que se pueda mantener la integridad referencial entre ambas tablas. Además, se pueden definir acciones adicionales para la clave foránea, como `ON DELETE` y `ON UPDATE`, que especifican qué hacer cuando se elimina o actualiza un registro en la tabla referenciada. Veamos con más detalle estas acciones:

* `ON DELETE CASCADE`: Si se elimina un registro en la tabla referenciada, se eliminarán automáticamente todos los registros relacionados en la tabla que contiene la clave foránea.
* `ON DELETE SET NULL`: Si se elimina un registro en la tabla referenciada, los valores de la clave foránea en la tabla que contiene la clave foránea se establecerán en nulo.
* `ON DELETE RESTRICT`: Si se intenta eliminar un registro en la tabla referenciada que tiene registros relacionados en la tabla que contiene la clave foránea, se producirá un error y no se permitirá la eliminación.
* `ON UPDATE CASCADE`: Si se actualiza un valor de la clave primaria en la tabla referenciada, se actualizarán automáticamente los valores correspondientes en la tabla que contiene la clave foránea.
* `ON UPDATE SET NULL`: Si se actualiza un valor de la clave primaria en la tabla referenciada, los valores de la clave foránea en la tabla que contiene la clave foránea se establecerán en nulo.
* `ON UPDATE RESTRICT`: Si se intenta actualizar un valor de la clave primaria en la tabla referenciada que tiene registros relacionados en la tabla que contiene la clave foránea, se producirá un error y no se permitirá la actualización.

#### Not Null

La restricción `NOT NULL` se utiliza para garantizar que un atributo no pueda contener valores nulos. Esto significa que al insertar un registro en la tabla, se debe proporcionar un valor para ese atributo, y no se permitirá dejarlo vacío. La restricción `NOT NULL` se define al crear la tabla mediante la sentencia `CREATE TABLE`, utilizando la cláusula `NOT NULL`.

En caso de establecer un valor `NOT NULL` para un atributo, se debe tener en cuenta que este valor no puede ser nulo ni vacío, y que se debe proporcionar un valor válido al insertar un registro en la tabla. Si se intenta insertar un registro sin proporcionar un valor para un atributo con la restricción `NOT NULL`, se producirá un error y no se permitirá la inserción del registro.

!!! warning
    En el caso de una clave primaria, se establece automáticamente como `NOT NULL`.

#### Default

La restricción `DEFAULT` se utiliza para establecer un valor predeterminado para un atributo en caso de que no se proporcione un valor al insertar un registro. Esto significa que si no se especifica un valor para ese atributo, se utilizará el valor predeterminado definido en la tabla.

Esta restricción se puede utilizar junto a la restricción `NOT NULL`, de manera que si no se proporciona un valor para ese atributo, se utilizará el valor predeterminado en lugar de permitir un valor nulo.

#### Check

La restricción `CHECK` se utiliza para definir una condición que debe cumplirse para que un valor sea válido en un atributo. Esto significa que al insertar o actualizar un registro en la tabla, se verificará si el valor proporcionado cumple con la condición definida en la restricción `CHECK`. Si el valor no cumple con la condición, se producirá un error y no se permitirá la inserción o actualización del registro.

En caso de no cumplir con la condición definida en la restricción `CHECK`, se producirá un error y no se permitirá la inserción o actualización del registro. Esto garantiza que los valores almacenados en la tabla cumplan con ciertas reglas o criterios específicos, lo que ayuda a mantener la integridad de los datos.

Veamos un ejemplo:

```sql
CREATE TABLE empleados (
    id INT PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL,
    salario DECIMAL(10, 2) CHECK (salario >= 0)
);
```

En este ejemplo vemos como el salario de un empleado no puede ser negativo, ya que se ha definido una restricción `CHECK` que verifica que el valor del salario sea mayor o igual a cero. Si se intenta insertar un registro con un salario negativo, se producirá un error y no se permitirá la inserción del registro.

#### Unique

La restricción `UNIQUE` se utiliza para garantizar que los valores de un atributo sean únicos en toda la tabla, evitando duplicados. Esto significa que al insertar o actualizar un registro en la tabla, se verificará si el valor proporcionado ya existe en esa columna. Si el valor ya existe, se producirá un error y no se permitirá la inserción o actualización del registro.

Tiene un comportamiento similar a la clave primaria, pero a diferencia de esta, una tabla puede tener múltiples restricciones `UNIQUE` en diferentes columnas. Además, los valores de una columna con la restricción `UNIQUE` pueden ser nulos, mientras que los valores de una columna con la restricción `PRIMARY KEY` no pueden ser nulos.

Es importante tener en cuenta que la restricción `UNIQUE` no garantiza la integridad referencial entre tablas, ya que no establece una relación entre ellas. Para garantizar la integridad referencial, se debe utilizar la restricción `FOREIGN KEY`.

### Auto Increment

La restricción `AUTO_INCREMENT` se utiliza para permitir que un atributo numérico se incremente automáticamente con cada nuevo registro insertado. Esto es útil para generar identificadores únicos de manera automática, sin necesidad de especificar un valor para ese atributo al insertar un registro.

Auto Increment se utiliza comúnmente en columnas que actúan como claves primarias, ya que garantiza que cada registro tenga un identificador único. Al insertar un nuevo registro en la tabla, el valor de la columna con la restricción `AUTO_INCREMENT` se incrementará automáticamente en uno, generando un nuevo valor único para ese registro.

Es importante mencionar que la restricción `AUTO_INCREMENT` solo se puede aplicar a columnas de tipo numérico, como `INT` o `BIGINT`. Además, solo se puede aplicar a una columna por tabla, y esta columna debe ser la clave primaria o tener una restricción `UNIQUE`.


### Restricciones de varias columnas

Por último, es importante mencionar que algunas restricciones pueden aplicarse a varias columnas de una tabla. Por ejemplo, se puede definir una clave primaria compuesta por varias columnas, lo que garantiza que la combinación de valores en esas columnas sea única en toda la tabla.

Por ejemplo si queremos establecer una clave primaria compuesta por las columnas `columna1` y `columna2`, podemos hacerlo de la siguiente manera:

```sql
CREATE TABLE ejemplo (
    columna1 INT,
    columna2 INT,
    columna3 VARCHAR(50),
    PRIMARY KEY (columna1, columna2)
);
```

Como vemos en este ejemplo, la combinación de valores en las columnas `columna1` y `columna2` debe ser única en toda la tabla, lo que garantiza que no se puedan insertar registros con los mismos valores en esas columnas.

### Nombrar restricciones

En SQL, es posible nombrar las restricciones al momento de crearlas, lo que facilita su identificación y gestión en la base de datos. Al nombrar una restricción, se le asigna un nombre único que se puede utilizar para referirse a ella en futuras operaciones, como la modificación o eliminación de la restricción.

Una nomenclatura clara, permite identificar fácilmente la restricción y su propósito, lo que facilita la comprensión del diseño de la base de datos y la gestión de las restricciones en el futuro.

Veamos un ejemplo de nombrar una restricción al crear una tabla:

```sql
CREATE TABLE empleados (
    id INT PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL,
    salario DECIMAL(10, 2) CONSTRAINT chk_salario CHECK (salario >= 0)
);
```

Como vemos se utilliza la palabra reservada `CONSTRAINT` seguida del nombre de la restricción, en este caso `chk_salario`, y luego se define la restricción `CHECK` que verifica que el salario sea mayor o igual a cero.

Esta restricción se puede utilizar tanto en la utilización de un check como de clave foránea y/o clave primaria, de manera que se puede nombrar cualquier restricción que se defina en la tabla.

!!! info
    Es importante mencionar que el nombre de la restricción debe ser único dentro de la base de datos, y no se pueden utilizar nombres duplicados para diferentes restricciones. Además, algunos sistemas de gestión de bases de datos (SGBD) pueden tener restricciones adicionales sobre los nombres de las restricciones, como la longitud máxima permitida o los caracteres válidos.