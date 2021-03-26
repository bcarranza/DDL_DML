# DATA TYPES
| Datatype | Descripcion    |
| :------- | :------:       |
|CHAR(size)|	A FIXED length string (can contain letters, numbers, and special characters). The size parameter specifies the column length in characters - can be from 0 to 255. Default is 1|
|VARCHAR(size)|	A VARIABLE length string (can contain letters, numbers, and special characters). The size parameter specifies the maximum column length in characters - can be from 0 to 65535|
|BINARY(size)|	Equal to CHAR(), but stores binary byte strings. The size parameter specifies the column length in bytes. Default is 1|
|VARBINARY(size)|	Equal to VARCHAR(), but stores binary byte strings. The size parameter specifies the maximum column length in bytes.|
|TINYBLOB|	For BLOBs (Binary Large OBjects). Max length: 255 bytes|
|TINYTEXT|	Holds a string with a maximum length of 255 characters|
|TEXT(size)|	Holds a string with a maximum length of 65,535 bytes|
|BLOB(size)|	For BLOBs (Binary Large OBjects). Holds up to 65,535 bytes of data|
|MEDIUMTEXT|	Holds a string with a maximum length of 16,777,215 characters|
|MEDIUMBLOB|	For BLOBs (Binary Large OBjects). Holds up to 16,777,215 bytes of data|
|LONGTEXT|	Holds a string with a maximum length of 4,294,967,295 characters|
|LONGBLOB|	For BLOBs (Binary Large OBjects). Holds up to 4,294,967,295 bytes of data|
|ENUM(val1, val2, val3, ...)|	A string object that can have only one value, chosen from a list of possible |values. You can list up to 65535 values in an ENUM list. If a value is inserted that is not in the list, a blank value will be inserted. The values are sorted in the order you enter them|
|SET(val1, val2, val3, ...)|	A string object that can have 0 or more values, chosen from a list of possible values. You can list up to 64 values in a SET list|


# DDL (Data Definition Lenguage)-(Relacionado con Estructura)
### Definición: 
Sentencias DDL son aquellas utilizadas para la creación de una base de datos y todos sus componentes: tablas, índices, relaciones, disparadores (triggers), procedimientos almacenados, etc

- CREATE
- ALTER
- DROP

### CREATE: 
Es un elemento básico de creación de nuevos componentes en nuestra base de datos; entre los más comunes tenemos:

- CREATE DATABASE
- CREATE TABLE
- CREATE INDEX

Crear una base de datos nueva.
~~~
CREATE DATABASE db_umg_introsis;
~~~
Borrar una base de datos existente
~~~
DROP DATABASE db_umg_introsis;
~~~
Listar bases de datos disponibles
~~~
show databases;
~~~
Utilizar una bd existente
~~~
use db_umg_introsis;
~~~


Tablas:
Crear una nueva tabla.



# DML (Data Manipulation Language)-(Releacionado con interacción con datos)
### Definición:  
DML son aquellas sentencias utilizadas para insertar, borrar, modificar y consultar los datos de una base de datos

- SELECT
- INSERT
- UPDATE 
- DELETE




