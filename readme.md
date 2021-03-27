# DATA TYPES
### String Data Types
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


### Numeric Data Types
| Datatype | Descripcion    |
| :------- | :------:       |
|BIT(size)|	A bit-value type. The number of bits per value is specified in size. The size parameter can hold a value from 1 to 64. The default value for size is 1.|
|TINYINT(size)|	A very small integer. Signed range is from -128 to 127. Unsigned range is from 0 to 255. The size parameter specifies the maximum display width (which is 255)|
|BOOL|	Zero is considered as false, nonzero values are considered as true.|
|BOOLEAN|	Equal to BOOL|
|SMALLINT(size)|	A small integer. Signed range is from -32768 to 32767. Unsigned range is from 0 to 65535. The size parameter specifies the maximum display width (which is 255)|
|MEDIUMINT(size)|	A medium integer. Signed range is from -8388608 to 8388607. Unsigned range is from 0 to 16777215. The size parameter specifies the maximum display width (which is 255)|
|INT(size)|	A medium integer. Signed range is from -2147483648 to 2147483647. Unsigned range is from 0 to 4294967295. The size parameter specifies the maximum display width (which is 255)|
|INTEGER(size)|	Equal to INT(size)|
|BIGINT(size)|	A large integer. Signed range is from -9223372036854775808 to 9223372036854775807. Unsigned range is from 0 to 18446744073709551615. The size parameter specifies the maximum display width (which is 255)|
|FLOAT(size, d)|	A floating point number. The total number of digits is specified in size. The number of digits after the decimal point is specified in the d parameter. This syntax is deprecated in MySQL 8.0.17, and it will be removed in future MySQL versions|
|FLOAT(p)|	A floating point number. MySQL uses the p value to determine whether to use FLOAT or DOUBLE for the resulting data type. If p is from 0 to 24, the data type becomes FLOAT(). If p is from 25 to 53, the data type becomes DOUBLE()|
|DOUBLE(size, d)|	A normal-size floating point number. The total number of digits is specified in size. The number of digits after the decimal point is specified in the d parameter|
|DOUBLE PRECISION(size, d)|	 
|DECIMAL(size, d)|	An exact fixed-point number. The total number of digits is specified in size. The number of digits after the decimal point is specified in the d parameter. The maximum number for size is 65. The maximum number for d is 30. The default value for size is 10. The default value for d is 0.|
|DEC(size, d)|	Equal to DECIMAL(size,d)|



### Date and Time Data Types
| Datatype | Descripcion    |
| :------- | :------:       |
|DATE|	A date. Format: YYYY-MM-DD. The supported range is from '1000-01-01' to '9999-12-31'|
|DATETIME(fsp)|	A date and time combination. Format: YYYY-MM-DD hh:mm:ss. The supported range is from '1000-01-01 00:00:00' to '9999-12-31 23:59:59'. Adding DEFAULT and ON UPDATE in the column definition to get automatic initialization and updating to the current date and time|
|TIMESTAMP(fsp)|	A timestamp. TIMESTAMP values are stored as the number of seconds since the Unix epoch ('1970-01-01 00:00:00' UTC). Format: YYYY-MM-DD hh:mm:ss. The supported range is from '1970-01-01 00:00:01' UTC to '2038-01-09 03:14:07' UTC. Automatic initialization and updating to the current date and time can be specified using DEFAULT |CURRENT_TIMESTAMP and ON UPDATE CURRENT_TIMESTAMP in the column definition|
|TIME(fsp)|	A time. Format: hh:mm:ss. The supported range is from '-838:59:59' to '838:59:59'|
|YEAR|	A year in four-digit format. Values allowed in four-digit format: 1901 to 2155, and 0000. MySQL 8.0 does not support year in two-digit format.|

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


###Interacción con Tablas:
Crear una nueva tabla.
~~~
CREATE TABLE CITY
(
ID INT,
NAME VARCHAR(50),
COUNTRYCODE VARCHAR(3),
DISTRICT VARCHAR(20),
POPULATION INT,
PRIMARY KEY (ID)
)
~~~
Eliminar dos columanas para posteriormente normalizar.
~~~
ALTER TABLE CITY
DROP COLUMN COUNTRYCODE

ALTER TABLE CITY
DROP COLUMN DISTRICT
~~~
Crear dos tablas nuevas: Pais y Distrito
~~~
CREATE TABLE COUNTRY
(
ID INT,
NAME VARCHAR(50),
COUNTRYCODE VARCHAR(3),
PRIMARY KEY (ID)
);
CREATE TABLE DISTRICT
(
ID INT,
NAME VARCHAR(50),
ID_COUNTRY INT,
PRIMARY KEY (ID)
);
~~~
Crear una nueva columna a ciudad 
~~~
ALTER TABLE CITY
ADD COLUMN ID_DISTRICT INT
~~~

Creación de relaciones. 
Se deben de crear primero los indices.
~~~
CREATE INDEX IX_Relationship1 ON CITY (ID_DISTRICT);

CREATE INDEX IX_Relationship2 ON DISTRICT (ID_COUNTRY);
~~~

Creación de constraints
~~~ 
ALTER TABLE CITY
ADD CONSTRAINT Relationship1 FOREIGN KEY (ID_DISTRICT) REFERENCES DISTRICT (ID) ON DELETE RESTRICT ON UPDATE RESTRICT

ALTER TABLE DISTRICT
ADD CONSTRAINT Relationship2 FOREIGN KEY (ID_COUNTRY) REFERENCES COUNTRY (ID) ON DELETE RESTRICT ON UPDATE RESTRICT
~~~ 


Borrar tablas creadas
~~~
DROP TABLE CITY; 
DROP TABLE DISTRICT;
DROP TABLE COUNTRY;
~~~

# DML (Data Manipulation Language)-(Releacionado con interacción con datos)
### Definición:  
DML son aquellas sentencias utilizadas para insertar, borrar, modificar y consultar los datos de una base de datos

- SELECT
- INSERT
- UPDATE 
- DELETE

### Ingreso de datos (INSERT)
Ingreso de Paises
~~~
INSERT INTO COUNTRY(ID,NAME,COUNTRYCODE) VALUES(1,'Guatemala','GTM');
INSERT INTO COUNTRY(ID,NAME,COUNTRYCODE) VALUES(2,'El Salvador','ESV');
INSERT INTO COUNTRY(ID,NAME,COUNTRYCODE) VALUES(3,'Honduras','HND');
~~~
Ingreso de Distritos
~~~
INSERT INTO DISTRICT(ID,NAME,ID_PAIS) VALUES(1,'Guatemala','1');
INSERT INTO DISTRICT(ID,NAME,ID_PAIS) VALUES(2,'Jalapa','1');
INSERT INTO DISTRICT(ID,NAME,ID_PAIS) VALUES(3,'El Progreso','1');
INSERT INTO DISTRICT(ID,NAME,ID_PAIS) VALUES(4,'Sonsonate','2');
INSERT INTO DISTRICT(ID,NAME,ID_PAIS) VALUES(5,'Santa Ana','2');
INSERT INTO DISTRICT(ID,NAME,ID_PAIS) VALUES(6,'San Salvador','2');
INSERT INTO DISTRICT(ID,NAME,ID_PAIS) VALUES(7,'Olancho','3');
INSERT INTO DISTRICT(ID,NAME,ID_PAIS) VALUES(8,'Tegucigalpa','3');
INSERT INTO DISTRICT(ID,NAME,ID_PAIS) VALUES(9,'San Pedro Sula','3');
~~~
Ingreso de ciudades
~~~
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (1,'Ciudad de Guatemala',995393,1);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (2,'Villa Nueva',618397,1);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (3,'Mixco',465773,1);

INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (4,'Jalapa',355566,2);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (5,'Chaparron',7000,2);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (6,'Mataquescuintla',41848,2);

INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (7,'Sansare',11486,3);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (8,'Sanarate',33000,3);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (9,'Guastatoya',24831,3);

INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (10,'Acajutla',29701,4);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (11,'Santa Isabel',10241,4);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (12,'Santa Catarina',10076,4);

INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (13,'Metapan',59004,5);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (14,'El Porvenir',7819,5);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (15,'Chalchupa',84510,5);

INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (16,'Soyapango',283223,6);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (17,'Guazapa',22906,6);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (18,'Ciudad San Salvador',84510,6);

INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (19,'Catacamas',117493,7);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (20,'Juticalpa',124828,7);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (21,'Gualaco',22975 ,7);

INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (22,'Talanga',38095,8);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (23,'Vallecillos',8533,8);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (24,'Ciudad de Tegucigalpa',1690661 ,8);

INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (25,'Choloma',222828,9);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (26,'Ciudad San Pedro Sula',719064,9);
INSERT INTO CITY(ID,NAME,POPULATION, ID_DISTRICT) VALUES (27,'Omoa',53771 ,9);
~~~


### Actualización de datos (UPDATE)
~~~
UPDATE CITY SET POPULATION=53772 WHERE ID=27
~~~
### Eliminación  de datos (DELETE)
~~~
DELETE CITY WHERE ID=27
~~~

### Selección de datos (SELECT)

Listado completo de ciudades ordenadas por su población de mayor a menor.
~~~
SELECT NAME,POPULATION FROM CITY ORDER BY POPULATION DESC
~~~

Listado completo de ciudades ordenadas por su población de mayor a menor pero solamente las de Distrito Ciudad Guatemala
~~~
SELECT NAME,POPULATION FROM CITY WHERE ID_DISTRICT=1 ORDER BY POPULATION DESC;
~~~


### JOINS
Su contenido es similar a las reglas de conjuntos. 
- INNER JOIN 
- LEFT JOIN
- RIGHT JOIN
- FULL O CROSS JOIN


Listado completo de ciudades ordenadas por su población, solamente del País Guatemala.
~~~
SELECT C.NAME,D.NAME,POPULATION 
FROM CITY C 
INNER JOIN DISTRICT D ON C.ID_DISTRICT = D.ID
INNER JOIN COUNTRY CT ON D.ID_PAIS=CT.ID
WHERE CT.ID =1
ORDER BY POPULATION DESC
~~~


### AGGREGATE FUNCTIONS
- SUM
- COUNT
- AVG
- DISTINCT

### OTRAS FUNCIONES
- SUBSTRING
- LEN


