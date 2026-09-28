# sql-select-fundamentals
Ejercicios de fundamentos de SQL y consultas SELECT._Modulo 4
Aunque SELECT * puede ser útil cuando estamos explorando una tabla y queremos conocer todas sus columnas, no es recomendable utilizarlo habitualmente en ambientes de producción.

Algunas razones son:

Rendimiento: si una tabla tiene muchas columnas, SELECT * recupera información que posiblemente no necesitamos. Esto puede aumentar la cantidad de datos que debe procesar y transferir el sistema.
Mantenibilidad: si posteriormente se agregan nuevas columnas a la tabla, una consulta con SELECT * comenzará a devolverlas automáticamente, lo que puede modificar inesperadamente el resultado de procesos o aplicaciones existentes.
Seguridad: seleccionar todas las columnas puede exponer información que no es necesaria para el usuario o proceso que realiza la consulta.
Por ejemplo, si solamente necesitamos conocer el cliente, el producto y el monto de una venta, es preferible especificar las columnas:

SELECT customer_id, product_id, total_amount
FROM sales;

en lugar de:

SELECT *
FROM sales;

Los alias permiten cambiar temporalmente el nombre de una columna en el resultado de una consulta para hacerla más fácil de interpretar.

Por ejemplo, total_amount puede ser un nombre claro para una persona que trabaja directamente con bases de datos, pero para un stakeholder del área de finanzas puede ser más comprensible como monto_total.

Podemos utilizar un alias de esta manera:

SELECT
    total_amount AS monto_total
FROM sales;

De esta forma, el resultado mostrará la columna como monto_total, facilitando su interpretación para una persona del área de finanzas que no necesariamente conoce los nombres técnicos utilizados en la base de datos.

Los alias permiten, por tanto, adaptar la presentación de los datos al público que los utiliza sin modificar el nombre original de la columna en la base de datos.
