### Realice la insercion de lo siguientes datos

   

(1.0) 

INSERT INTO fabricante (codigo, nombre)

VALUES

(1, 'ASUS'), 

(2, 'Lenovo'), 

(3, 'Hewlett-Packard'), 

(4, 'Samsung'), 

(5, 'Seagate'), 

(6, 'Crucial'),

(7, 'Gigabyte'),

(8, 'Huawei'),

(9, 'Xiaomi'); 

SELECT codigo, nombre

FROM fabricante;





(2.0) 

INSERT INTO producto (codigo, nombre, precio)

VALUES 

(1, 'Disco duro SATA3 1TB' 86.99, 5), 

(2, 'Memoria RAM DDR4 8GB', 120, 6), 

(3, 'Disco SSD 1 TB' 150,99, 4), 

(4, 'GeForce GTX 1050Ti', 150.99, 4), 

(5, 'GeForce GTX 1080 Xtreme' 755, 6), 

(6, 'Monitor 24 LED Full HD' 202, 1),

(7, 'Monitor 27 LED Full HD' 245.99, 1),

(8, 'Portatil Yoga 520' 559, 2),

(9, 'Portatil Ideapad' 444, 2), 

(10, 'Impresora HP Deskjet 3720', 59.99, 3), 

(11, 'Impresora HP Laserjet Pro M26nw', 180, 3);


SELECT codigo, nombre, precio

FROM producto





### REALICE LAS SIGUIENTES CONSULTAS

#### Consultas sobre una tabla



1. Lista el nombre de todos los productos que hay en la tabla producto.
   
   

​	SELECT p.codigo, p.nombre 
​	FROM producto as p;





2. Lista los nombres y los precios de todos los productos de la tabla producto.

​	SELECT p.nombre, p.precio
​	FROM producto as p;





3. Lista todas las columnas de la tabla producto.

​	SELECT p.codigo, p.nombre, p.precio, p.codigo_fabricante
​	FROM producto as p;



4. Lista el nombre de los productos, el precio en euros y el precio en dólares
   estadounidenses (USD). 







5. Lista el nombre de los productos, el precio en euros y el precio en dólares
   estadounidenses (USD). Utiliza los siguientes alias para las columnas: nombre 
   de producto, euros, dólares.







6. Lista los nombres y los precios de todos los productos de la tabla producto,
   convirtiendo los nombres a mayúscula. 

​	SELECT UPPER(nombre), precio
​	FROM producto;



7. Lista los nombres y los precios de todos los productos de la tabla producto,
   convirtiendo los nombres a minúscula.

​	SELECT LOWER(nombre), precio 
​	FROM producto;





8. Lista el nombre de todos los fabricantes en una columna, y en otra  columna obtenga en mayúsculas los dos primeros caracteres del nombre del fabricante.

   

​	SELECT nombre, UPPER(LEFT(nombre, 2)) AS Mayus

​	FROM fabricante

​	



9. Lista los nombres y los precios de todos los productos de la tabla producto,
   redondeando el valor del precio.



​	SELECT nombre, ROUND(precio, 2);

​	FROM producto



10. Lista los nombres y los precios de todos los productos de la tabla producto,
    truncando el valor del precio para mostrarlo sin ninguna cifra decimal.
    
    

​	SELECT nombre, TRUNCATE(precio, 0)

​	FROM producto



11. Lista el identificador de los fabricantes que tienen productos en la tabla producto.

    

​	SELECT f.codigo

​	FROM fabricante AS f,  producto AS p

​	WHERE f.codigo = p.codigo_fabricante;



12. Lista el identificador de los fabricantes que tienen productos en la tabla producto, eliminando los identificadores que aparecen repetidos.

    

​	SELECT DISTINCT codigo_fabricante

​	FROM producto AS p, fabricante AS f

​	WHERE f.codigo = p.codigo_fabricante;



13. Lista los nombres de los fabricantes ordenados de forma ascendente.

    

​	SELECT nombre

​	FROM fabricante

​	ORDER BY nombre ASC;



14. Lista los nombres de los fabricantes ordenados de forma descendente.

    

​	SELECT nombre

​	FROM fabricante

​	ORDER BY nombre DESC;



15. Lista los nombres de los productos ordenados en primer lugar por el
    nombre de forma ascendente y en segundo lugar por el precio de forma
    descendente.

    

​	SELECT nombre, precio

​	FROM producto

​	ORDER BY nombre ASC, precio DESC;



16. Devuelve una lista con las 5 primeras filas de la tabla fabricante.

    

    SELECT codigo, nombre

    FROM fabricante

    LIMIT 5;

    

17. Devuelve una lista con 2 filas a partir de la cuarta fila de la tabla fabricante.
    La cuarta fila también se debe incluir en la respuesta.

    

​	SELECT codigo, nombre

​	FROM fabricante

​	LIMIT 2 

​	OFFSET 3;



18. Lista el nombre y el precio del producto más barato. (Utilice solamente las
    cláusulas ORDER BY y LIMIT)
    
    

​	SELECT nombre, precio

​	FROM producto

​	ORDER BY precio ASC

​	LIMIT 1;



19. Lista el nombre y el precio del producto más caro. (Utilice solamente las
    cláusulas ORDER BY y LIMIT)

    

    SELECT nombre, precio

    FROM producto

    ORDER BY precio DESC

    LIMIT 1;

    

20. Lista el nombre de todos los productos del fabricante cuyo identificador de
    fabricante es igual a 2.

    

​	SELECT p.nombre

​	FROM producto AS p, fabricante AS f

​	WHERE f.codigo = p.codigo_fabricante AND f.codigo = 2;





21. Lista el nombre de los productos que tienen un precio menor o igual a 120€.

    

    SELECT nombre, precio 

    FROM producto 

    WHERE precio <= 120;

    

22. Lista el nombre de los productos que tienen un precio menor o igual a 400€.

    

    SELECT nombre, precio

    FROM producto

    WHERE precio <= 400;

    

23. Lista el nombre de los productos que no tienen un precio mayor o igual a
    400€.

    

    SELECT nombre, precio

    FROM producto

    WHERE precio < 400;

    

    

24. Lista todos los productos que tengan un precio entre 80€ y 300€. Sin utilizar
    el operador BETWEEN.

    

    SELECT nombre, precio

    FROM producto

    WHERE precio >= 80 AND <= 300

    

    

25. Lista todos los productos que tengan un precio entre 60€ y 200€. Utilizando
    el operador BETWEEN.

    

    SELECT nombre, precio

    FROM producto

    WHERE precio BETWEEN 60 AND 200;

    

    

26. Lista todos los productos que tengan un precio mayor que 200€ y que el
    identificador de fabricante sea igual a 6.

    

    SELECT p.nombre, p.precio, p.codigo_fabricante

    FROM producto AS p

    WHERE p.precio > 200 AND p.codigo_fabricante = 6;

    

