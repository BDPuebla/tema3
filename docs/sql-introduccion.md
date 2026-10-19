# El lenguaje de consulta estructurado (SQL)

SQL (Structured Query Language) es un lenguaje de programación diseñado para gestionar y manipular bases de datos relacionales. Este lenguaje permite a los usuarios realizar diversas operaciones, como la creación, modificación y consulta de datos almacenados en una base de datos.

SQL fue creado en la década de 1970 por IBM y se ha convertido en el estándar de facto para interactuar con bases de datos relacionales. A lo largo de los años, SQL ha evolucionado y se ha adaptado a diferentes sistemas de gestión de bases de datos (DBMS), como MySQL, PostgreSQL, Oracle y Microsoft SQL Server.

SQL no solo se utiliza para consultar datos, sino también para definir la estructura de la base de datos, controlar el acceso a los datos y garantizar la integridad de la información. Su sintaxis es relativamente sencilla y se basa en comandos declarativos que permiten a los usuarios expresar lo que desean hacer con los datos sin necesidad de especificar cómo hacerlo.

Normalmente su uso esta pensado para bases de datos de tipo relacional, aunque existen extensiones y variantes de SQL que permiten trabajar con bases de datos no relacionales o con características específicas.

Veamos algunos ejemplos de sentencias SQL:

```sql
-- Crear una tabla llamada "empleados"
CREATE TABLE empleados (
    id INT PRIMARY KEY,
    nombre VARCHAR(50),
    puesto VARCHAR(50),
    salario DECIMAL(10, 2)
);

-- Insertar datos en la tabla "empleados"
INSERT INTO empleados (id, nombre, puesto, salario) VALUES
(1, 'Juan Pérez', 'Gerente', 50000.00),
(2, 'María López', 'Analista', 40000.00),
(3, 'Carlos García', 'Desarrollador', 45000.00);

-- Consultar todos los empleados
SELECT * FROM empleados;

-- Actualizar el salario de un empleado
UPDATE empleados SET salario = 55000.00 WHERE id = 1;

-- Eliminar un empleado
DELETE FROM empleados WHERE id = 2;
```

En este tema, nos centraremos en los conceptos básicos de SQL, centrándonos en las sentencias de definición de datos (DDL). Aprenderemos cómo crear y modificar tablas.

!!! info
    Durante este curso, nos centraremos en el uso de SQL en el contexto del SGBD MySQL, aunque los conceptos y sentencias que aprenderemos son aplicables a otros sistemas de gestión de bases de datos relacionales, pueden haber pequeñas diferencias en la sintaxis y características específicas de cada SGBD.