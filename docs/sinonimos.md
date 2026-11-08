# Sinónimos

Los sinónimos son alias que se pueden crear para objetos de base de datos, como tablas, vistas o procedimientos almacenados. Los sinónimos permiten a los desarrolladores y usuarios referirse a estos objetos utilizando nombres más cortos o más significativos, lo que puede mejorar la legibilidad del código y facilitar el mantenimiento de la base de datos.

El utilizar sinónimos puede ser especialmente útil en entornos donde se utilizan nombres de objetos largos o complejos, o cuando se desea cambiar el nombre de un objeto sin afectar a las aplicaciones que lo utilizan. Al crear un sinónimo, se puede mantener la compatibilidad con el código existente mientras se mejora la claridad y la comprensión del mismo.

Para crear un sinónimo, se utiliza la siguiente sintaxis:

```sql
CREATE SYNONYM nombre_sinonimo FOR nombre_objeto;
```

Donde `nombre_sinonimo` es el nombre que se desea asignar al sinónimo y `nombre_objeto` es el nombre del objeto de base de datos al que se hace referencia.

Tras la creación del sinónimo, se puede utilizar el nombre del sinónimo en lugar del nombre del objeto original en las consultas y operaciones de la base de datos. Esto puede simplificar el código y mejorar la legibilidad, especialmente cuando se trabaja con objetos de base de datos que tienen nombres largos o complejos.

El borrar un sinónimo no implica borrar el objeto original al que hace referencia. Para eliminar un sinónimo, se utiliza la siguiente sintaxis:

```sql
DROP SYNONYM nombre_sinonimo;
```

Más adelante, veremos cómo utilizar los sinónimos en conjunto con los índices para optimizar el rendimiento de las consultas y mejorar la legibilidad del código.