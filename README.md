# Consultas_1_SQL
introduccion a las consultas a una BD usando el lenguaje SQL

## Base de datos: Ventas
## Tabla: Cliente

![Tabla Cliente](Consultas_Clientes.png 'Tabla Cliente')

## Instruccion SELECT
- permite seleccionar datos de una tabla.
- su formato es: 'SELECT CAMPOS_tabla FROM nombre tabla``

## Consulta N°  1
1.Para visualizar toda la información que contiene la tabla Cliente se puede incluir con la introducción SELECT el caracter **\*** o cada uno de los campos de la tabla.

- `SELECT * FROM Cliente'
![Consulta1](Consulta1.png " Consulta 1 - 1")
- `SELECT identificacion. nombre, apellidos, direccion. telefono,ciudad nac, fecha nac FROM Cliente´
![Consulta2](Consulta2.png " Consulta 1 - 2")

### Consulta No. 2

2. Para visualizar solamente la identificacion del cliente: - `SELECT identificacion. FROM Cliente`
![Consulta2](ConsultaNumber2.png " consulta 2")

### Consulta No. 3

3. si desea obtener los registros cuya identificacion sea mayor o igual a 150, se debe utilizar la clausula `WHERE` que especifi las condiciones que deben reunir los registros que se van a seleccionar: `SELECT * FROM Cliente WHERE identificacion>=150'
![Consulta3](Consulta3.png " consulta 3")

### Consulta No.4

4. se desea obtener los registros cuyos apellidos sean Vanegas o Celina, se debe utilizar el operador `IN` Que especifica los registros de una tabla. 

`SELECT apellidos FROM cliente WHERE apellidos IN('vanegas', 'celina')`

![Consulta4](Consulta4.png " consulta 4")

O se puede utilizar el operador `OR`

`SELECT apellidos FROM cliente WHERE apellidos ='vanegas'OR apellidos = 'celina'`

![Consulta4 1](Consulta4_1.png " consulta 4 1")

### Consulta No. 5

5. Se desea obtener los registros cuya ciudad identificacion sea menor de 110 y la ciudad sea Cali, se debe utilizar el operador `AND`


`SELECT * FROM CLiente WHERE identificacion<=110 AND ciudad_nac  = 'Cali'`

![Consulta5 1](Consulta5.png " consulta 5 1")

### Consulta No. 6

6. Si se desea obtener los registros cuyos nombres empiecen con la letra 'A', se debe utilizar el operador `LIKE` que utiliza los patrones `%` (todos) y caracter `_` (caracter).

`SELECT * FROM Cliente WHERE nombre LIKE 'A%'`

![Consulta6 1](Consulta6.png " consulta 6 1")


### Consulta No. 7

7. Se desea obtener los registros cuyos nombres contengan la letra 'a'

`SELECT * FROM Cliente WHERE nombre LIKE '%a%'`

![Consulta7 1](Consulta7.png " consulta 7 1")

### Consulta No. 8

8. Se desea obtener los registros donde la cuarta letra del nombre del cliente sea la letra 'a'

`SELECT * FROM Cliente WHERE nombre LIKE '___a'`

![Consulta8 1](Consulta8.png " consulta 8 1")

### Consulta No. 9

9. Si se desea obtener los registros cuya identificacion este entre el intervalo 110 y 150; se debe utilizar la clausula `BETWEEN`, Que sirve para especificar un intervalo de valores

`SELECT * FROM Cliente WHERE identificion BETWEEN 110 AND 150`

![Consulta9 1](Consulta9.png " consulta 9 1")

## Intrusccion DELETE
- Permite seleccionar datos de una tabla.
-Su formato es: `DELETE FROM nombre_tabla`

### Eliminacion No. 1

1. Eliminar los registros cuya identificacion sea mayor de 170

`DELETE FROM Cliente WHERE Identificacion = 170`

![Eliminacion 1](Eliminacion1.png "Eliminacion 1")

![Eliminacion 2](Eliminacion2.png "Eliminacion 2")

2. Eliminar los registros cuya id sea igual a 116

## Instruccion UPDATE
- Actualizar un campo de la tabla
- El formato es: `UPDATE nombre_tabla SET nombre_campo = valor`

### Actualizacion No. 1

1. Para actualizar la ciu_nacu de Cristian Vanegas, cuya id es 114

`UPDATE Cliente SET ciudad_nac = 'Pereira' WHERE identificacion = 114`

## Creacion tabla Pedido
### diccionario de datos
Campo  Tipo de Dato  Longitud

No_pedido Varchar 15
iden_cliente varchar 15
Fecha_compra varchar 20
Fecha_vencimiento varchar 25
Observacion varchar 30

![Relacion](Relacion.png "Relacion")

### Tabla pedido

![Tabla nueva](Tablapedido.png "New table")

### modelo entidad relacion

![Modelo](Modelo.png "Modelo")

## Operador Inner Join
- permite obtener datos de dos o mas tablas.
- Cuando sea realiza la concatenacion de las tablas, no necesariamente se deben mostrar todos los datos de las tablas.
- Su formato es:
`SELECT tabla1.campo, tabla2.campo; ... FROM tabla principal INNER JOIN tabla_secundaria ON campo_comun_tabla1 = campo_comun_tabla2`

1. Para visualizar los campos identificacion, nombre, apellidos de la tabla CLiente y No_pedido, fecha_compra, fecha_vencimiento y observacion de la tabla Pedido, se debe realizar la siguiente instruccion:

`SELECT Cliente.identificacion, Cliente.nombre, Cliente.apellidos, Pedido.no_pedido, Pedido.fecha_compra, Pedido.fecha_vencimiento, pedido.observacion FROM Cliente INNER JOIN Pedido ON Cliente.identificacion= Pedido.iden_cliente`

![INNER](inner.png "JOIN")

2. Para visualizar todos los campos de las tablas Cliente y Pedido donde identificacion sea mayor que 100, se debe utilizar la 1ra funcion 
`SELECT Cliente.*, Pedido.* FROM Cliente INNER JOIN Pedido ON Cliente.identificacion = Pedido.iden_cliente WHERE Cliente.identificacion
100` 
![INNER2](inner2.png "JOIN2")

