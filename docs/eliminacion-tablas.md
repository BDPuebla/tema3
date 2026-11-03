# Eliminación de tablas

Para eliminar una tabla existente en una base de datos, utilizamos el comando SQL `DROP TABLE`. Este comando elimina la tabla y todos sus datos, así como también las restricciones y los índices asociados a ella.

Veamos un ejemplo de cómo eliminar una tabla llamada `mi_tabla`:

```sql
DROP TABLE IF EXISTS mi_tabla;
```

Vemos que se utiliza la cláusula `IF EXISTS` para evitar errores en caso de que la tabla no exista. Si la tabla existe, se eliminará; si no existe, no se producirá ningún error y la sentencia se ejecutará sin problemas.

Es importante tener en cuenta que al eliminar una tabla, se perderán todos los datos almacenados en ella de forma permanente. Por lo tanto, es recomendable realizar una copia de seguridad de los datos antes de eliminar una tabla, especialmente si contiene información importante.

También es importante considerar las dependencias que puedan existir en la tabla que se desea eliminar, como claves foráneas en otras tablas. Si existen dependencias, es posible que sea necesario eliminar o modificar esas dependencias antes de poder eliminar la tabla.