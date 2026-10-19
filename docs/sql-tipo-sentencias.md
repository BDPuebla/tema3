# Tipos de sentencias SQL

En SQL, existen varios tipos de sentencias que se utilizan para realizar diferentes operaciones en la base de datos. Estos tipos de sentencias se pueden clasificar en las siguientes categorías:

* Sentencias de definición de datos (DDL, Data Definition Language): Estas sentencias se utilizan para definir y modificar la estructura de la base de datos, como la creación, modificación y eliminación de tablas, índices y otros objetos.

* Sentencias de manipulación de datos (DML, Data Manipulation Language): Estas sentencias se utilizan para manipular los datos almacenados en la base de datos, como la inserción, actualización y eliminación de registros.

* Sentencias de control de transacciones (TCL, Transaction Control Language): Estas sentencias se utilizan para controlar las transacciones en la base de datos, como la confirmación (commit) y la reversión (rollback) de cambios.

* Sentencias de control de datos (DCL, Data Control Language): Estas sentencias se utilizan para controlar el acceso a los datos en la base de datos, como la concesión y revocación de permisos a los usuarios.

Vamos a ver cada uno de estos tipos de sentencias con más detalle y ejemplos prácticos.

## Sentencias de definición de datos (DDL)

Una sentencia DDL se utiliza para definir y modificar la estructura de la base de datos. Algunas de las sentencias DDL más comunes son:

* `CREATE`: Se utiliza para crear nuevos objetos en la base de datos, como tablas, índices y vistas.
* `ALTER`: Se utiliza para modificar la estructura de los objetos existentes en la base de datos, como agregar o eliminar columnas en una tabla.
* `DROP`: Se utiliza para eliminar objetos de la base de datos, como tablas, índices y vistas.
* `TRUNCATE`: Se utiliza para eliminar todos los registros de una tabla, pero mantiene la estructura de la tabla intacta.

## Sentencias de manipulación de datos (DML)

Una sentencia DML se utiliza para manipular los datos almacenados en la base de datos. Algunas de las sentencias DML más comunes son:

* `SELECT`: Se utiliza para consultar y recuperar datos de la base de datos.
* `INSERT`: Se utiliza para insertar nuevos registros en una tabla.
* `UPDATE`: Se utiliza para actualizar los registros existentes en una tabla.
* `DELETE`: Se utiliza para eliminar registros de una tabla.

## Sentencias de control de transacciones (TCL)

Una sentencia TCL se utiliza para controlar las transacciones en la base de datos. Algunas de las sentencias TCL más comunes son:

* `COMMIT`: Se utiliza para confirmar los cambios realizados en la base de datos durante una transacción.
* `ROLLBACK`: Se utiliza para deshacer los cambios realizados en la base de datos durante una transacción.
* `SAVEPOINT`: Se utiliza para establecer un punto de guardado dentro de una transacción, lo que permite deshacer los cambios hasta ese punto específico.

## Sentencias de control de datos (DCL)

Una sentencia DCL se utiliza para controlar el acceso a los datos en la base de datos. Algunas de las sentencias DCL más comunes son:

* `GRANT`: Se utiliza para conceder permisos a los usuarios para realizar ciertas operaciones en la base de datos.
* `REVOKE`: Se utiliza para revocar los permisos concedidos a los usuarios en la base de datos.
