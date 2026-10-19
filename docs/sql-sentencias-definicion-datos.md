# Sentencias de definición de datos (DDL)

Las sentencias de definición de datos (DDL) son un conjunto de comandos SQL que se utilizan para definir y modificar la estructura de la base de datos. Estas sentencias permiten crear, alterar y eliminar objetos en la base de datos, como tablas, índices y vistas.

Es importante destacar que las sentencias DDL no manipulan los datos almacenados en la base de datos, sino que se centran en la definición de la estructura de los objetos de la base de datos.

Estas sentencias se centran en el modelo físico de la base de datos, es decir, en cómo se almacenan los datos en el sistema de gestión de bases de datos (SGBD). A través de las sentencias DDL, los usuarios pueden definir la estructura de las tablas, establecer relaciones entre ellas y garantizar la integridad de los datos.

La creación de tablas es una de las operaciones más comunes realizadas mediante sentencias DDL. Al crear una tabla, se definen los nombres de las columnas, los tipos de datos que pueden almacenar y las restricciones que se aplican a los datos.

## Sentencias DDL más comunes

Vamos a ver algunas de las sentencias DDL más comunes y su uso:

* `CREATE`: Se utiliza para crear nuevos objetos en la base de datos, como tablas, índices y vistas. Por ejemplo, para crear una tabla llamada "empleados", se puede utilizar la siguiente sentencia:

```sql
CREATE TABLE empleados (
    id INT PRIMARY KEY,
    nombre VARCHAR2(50),
    puesto VARCHAR2(50),
    salario DECIMAL(10, 2)
);
```

Esta sentencia tiene en cuenta las restricciones de integridad, como la clave primaria (PRIMARY KEY) que garantiza que cada registro en la tabla tenga un identificador único.

Es importante tener en cuenta los diferentes tipos de datos que se pueden utilizar al crear una tabla, como enteros (INT), cadenas de texto (VARCHAR2) y números decimales (DECIMAL). Además, se pueden establecer restricciones adicionales, como la longitud máxima de una cadena de texto o el rango permitido para un número.

Más adelante veremos en detalle como crear cada tabla con la sintaxis completa.

* `ALTER`: Se utiliza para modificar la estructura de los objetos existentes en la base de datos, como agregar o eliminar columnas en una tabla. Por ejemplo, para agregar una columna "fecha_ingreso" a la tabla "empleados", se puede utilizar la siguiente sentencia:

```sql
ALTER TABLE empleados ADD fecha_ingreso DATE;
```

Esta sentencia permite modificar la estructura de la tabla sin perder los datos existentes. También se pueden realizar otras modificaciones, como cambiar el tipo de datos de una columna o establecer nuevas restricciones.

Es importante tener en cuenta que al realizar modificaciones en la estructura de una tabla, se deben considerar las dependencias y relaciones con otras tablas, así como el impacto que estas modificaciones pueden tener en los datos existentes.

* `DROP`: Se utiliza para eliminar objetos de la base de datos, como tablas, índices y vistas. Por ejemplo, para eliminar la tabla "empleados", se puede utilizar la siguiente sentencia:

```sql
DROP TABLE empleados;
```

Esta sentencia elimina la tabla y todos los datos almacenados en ella de forma permanente. Es importante tener precaución al utilizar esta sentencia, ya que no se puede deshacer y se perderán todos los datos asociados a la tabla.

* `TRUNCATE`: Se utiliza para eliminar todos los registros de una tabla, pero mantiene la estructura de la tabla intacta. Por ejemplo, para eliminar todos los registros de la tabla "empleados", se puede utilizar la siguiente sentencia:

```sql
TRUNCATE TABLE empleados;
```

Esta sentencia es útil cuando se desea vaciar una tabla sin eliminarla por completo. A diferencia de la sentencia `DELETE`, que elimina los registros uno por uno y puede generar un registro de transacciones, la sentencia `TRUNCATE` es más eficiente y rápida, ya que elimina todos los registros de manera inmediata.

!!! warning
    Es importante tener en cuenta que las sentencias DDL pueden tener un impacto significativo en la estructura y los datos de la base de datos. Se recomienda realizar copias de seguridad antes de ejecutar estas sentencias y utilizarlas con precaución, especialmente en entornos de producción.