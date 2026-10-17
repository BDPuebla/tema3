# Introducción al diseño de bases de datos relacionales

Como hemos aprendido en temas anteriores, el diseño de bases de datos relacionales es un proceso fundamental para garantizar la eficiencia, integridad y consistencia de los datos almacenados. En este tema, nos centraremos en los aspectos clave del diseño de bases de datos relacionales, incluyendo la definición de tablas, relaciones y restricciones de integridad.

Hemos aprendido a modelar datos utilizando diagramas Entidad-Relación (E/R) y a convertir estos diagramas en un esquema relacional. Ahora, nos enfocaremos en cómo implementar este esquema en un sistema de gestión de bases de datos (SGBD) utilizando el lenguaje SQL.

Si recordamos los niveles del modelado de datos:

* Nivel conceptual: Representa la estructura de la base de datos utilizando diagramas E/R, donde se identifican las entidades, atributos y relaciones.

* Nivel lógico: Se traduce el modelo conceptual a un esquema relacional, definiendo las tablas, columnas y relaciones entre ellas.

* Nivel físico: Se implementa el esquema relacional en un SGBD, utilizando SQL para crear las tablas, definir relaciones y aplicar restricciones de integridad.

En este tema nos centraremos en los 2 últimos niveles. Por un lado, el nivel lógico, donde se define el esquema relacional a partir del modelo conceptual, y por otro lado, el nivel físico, donde se implementa el esquema en un SGBD utilizando SQL.

## Nivel Lógico

El nivel lógico del diseño de bases de datos relacionales se centra en la definición del esquema relacional a partir del modelo conceptual. En esta etapa, se identifican las tablas, columnas y relaciones entre ellas, asegurando que la estructura de la base de datos sea eficiente y cumpla con las reglas de integridad.

Hasta ahora, hemos aprendido a mostrar la estructura de la base de datos y sus relaciones mediante diagramas E/R. Sin embargo, para implementar la base de datos en un SGBD, es necesario convertir estos diagramas a diagramas conceptuales como también hemos aprendido.

Sin embargo, no solo con el diagrama conceptual como hemos aprendido solo se mostraban las tablas y las relaciones entre ellas, mostrando las diferentes claves.

Por otro lado, es necesario definir el dominio de los atributos y las restricciones de integridad que se aplicarán a la base de datos. Esto se puede hacer mediante diagramas relacionales completos, que no solo muestran la estructura de la base de datos y sus relaciones, sino que también muestran el dominio de los atributos y las restricciones de integridad.

## Nivel Físico

Una vez definido el esquema relacional, es necesario implementarlo en un SGBD utilizando el lenguaje SQL. SQL es un lenguaje estándar que permite definir, manipular y consultar datos en bases de datos relacionales.

Es por ello, que se utilizan los diferentes lenguajes como el DDL (Data Definition Language) para definir la estructura de la base de datos, incluyendo la creación de tablas, definición de relaciones y aplicación de restricciones de integridad.

En este tema, nos centraremos en la definición de datos utilizando SQL, explorando cómo crear y modificar tablas, definir relaciones entre ellas y aplicar restricciones de integridad para garantizar la consistencia de los datos.