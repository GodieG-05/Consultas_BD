![image-20240412063607704](/home/camper/.config/Typora/typora-user-images/image-20240412063607704.png)

I)	Inserición de datos

 1. ​	INSERT INTO fabricante (codigo, nombre)

    ​	VALUES (1, 'Asus'), (2, 'Lenovo'), (3, 'Hewlett-Packard'), (4, 'Samsung'), (5, 'Seagate'), (6, 'Crucial'), (7, 'Gigabyte'),

    ​		       (8, 'Huawei'), (9, 'Xiaomi');

    

 2. ​	INSERT INTO producto (codigo, nombre, precio, codigo_fabricante)

    ​	VALUES (1, 'Disco duro SATA3 1TB', 86.99, 5),

    ​		       (2, 'Memoria RAM DDR4 8GB', 120, 6),

    ​		       (3, 'Disco SSD 1 TB', 150.99, 4),

    ​		       (4, 'GeForce GTX 1050Ti', 185, 7),

    ​		       (5, 'GeForce GTX 1080 Xtreme', 755, 6),

    ​		       (6, 'Monitor 24 LED Full HD', 202, 1),

    ​		       (7, 'Monitor 27 LED Full HD', 245.99, 1),

    ​		       (8, 'Portátil Yoga 520', 559, 2),

    ​		       (9, 'Portátil Ideapd 320', 444, 2),

    ​		       (10, 'Impresora HP Deskjet 3720', 59.99, 3),

    ​		       (11, 'Impresora HP Laserjet Pro M26nw', 180, 3),

    

II)	Consultas sobre una Tabla



1. ​	SELECT p.nombre

   ​	FROM producto as p;

   

2. ​	SELECT p.nombre, p.precio

   ​	FROM producto as p;

   

3. ​	SELECT p.codigo, p.nombre, p.precio, p.codigo_fabricante

   ​	FROM producto as p;



4. ​	SELECT p.nombre, p.precio,

   ​	 	     p.precio * 1.07

   ​	FROM producto as p;

   

5. ​	SELECT p.nombre as 'nombre de producto',

   ​		      p.precio as 'euros',

   ​		      p.precio * 1.07 as 'dólares'

   ​	FROM producto as p;

   

6. ​	SELECT UPPER( p.nombre ) as 'nombre de producto',

   ​		      p.precio as 'precio',

   ​	FROM producto as p;

   

7. ​	SELECT LOWER ( p.nombre ) as 'nombre de producto',

   ​		      p.precio as 'precio',

   ​	FROM producto as p;

   

8. ​	SELECT f.nombre as 'nombre de fabricante',

   ​		      UPPER ( LEFT(f.nombre, 2) ) as 'caracteres en mayusculas'

   ​	FROM fabricante as f;

   

9. ​	SELECT p.nombre as 'nombre de producto',

   ​		      ROUND ( p.precio ) as 'precio redondeado',

   ​	FROM producto as p;

   

10. ​	SELECT p.nombre as 'nombre de producto',

    ​		      TRUNCATE (p.precio, 0) as 'precio truncado',

    ​	FROM producto as p;

11. ​	SELECT f.codigo as 'codigo de fabricante',

    ​	FROM fabricante as f, producto as p;

    ​	WHERE f.codigo = p.codigo_fabricante;

    

12. ​	SELECT DISTINCT f.codigo as 'codigo de fabricante',

    ​	FROM fabricante as f, producto as p;

    ​	WHERE f.codigo = p.codigo_fabricante;

    

13. ​	SELECT f.nombre as 'nombre de fabricante',

    ​	FROM fabricante as f

    ​	ORDER BY f.nombre ASC;

    

14. ​	SELECT f.nombre as 'nombre de fabricante',

    ​	FROM fabricante as f

    ​	ORDER BY f.nombre DESC;

    

15. ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio'

    ​	FROM producto as p

    ​	ORDER BY p.nombre ASC; 

    ​	*** Tabla producto ordenada alfabéticamente de forma ascendente

    ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio'

    ​	FROM producto as p

    ​	ORDER BY p.precio DESC;

    ​	*** Tabla producto ordenada de manera descendente según su precio

    

16. ​	SELECT f.codigo as 'código de fabricante', f.nombre as 'nombre de fabricante',

    ​	FROM fabricante as f

    ​	LIMIT 5;

    

17. ​	SELECT f.codigo as 'código de fabricante', f.nombre as 'nombre de fabricante',

    ​	FROM fabricante as f

    ​	LIMIT 2 OFFSET 3;

    

18. ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio'

    ​	FROM producto as p

    ​	ORDER BY p.precio ASC 

    ​	LIMIT 1;

    

19. ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio'

    ​	FROM producto as p

    ​	ORDER BY p.precio DESC

    ​	LIMIT 1;

    

20. ​	SELECT p.nombre as 'nombre de producto', p.codigo_fabricante as 'código de fabricante'

    ​	FROM producto as p

    ​	WHERE p.codigo_fabricante = 2;

    

21. ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio'

    ​	FROM producto as p

    ​	WHERE p.precio <= 120;

    

22. ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio'

    ​	FROM producto as p

    ​	WHERE p.precio >= 400;

    

23. ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio'

    ​	FROM producto as p

    ​	WHERE NOT p.precio >= 400;

    

24. ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio'

    ​	FROM producto as p

    ​	WHERE p.precio >= 80 AND p.precio <= 300

    

25. ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio'

    ​	FROM producto as p

    ​	WHERE p.precio BETWEEN 60 AND 200

    

26. ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio', p.codigo_fabricante as 'código de fabricante'

    ​	FROM producto as p

    ​	WHERE p.precio > 200 AND p.codigo_fabricante = 6;

    

27. ​	SELECT p.nombre as 'nombre de producto', p.codigo_fabricante as 'código de fabricante'

    ​	FROM producto as p

    ​	WHERE p.codigo_fabricante = 1 OR p.codigo_fabricante = 3 OR p.codigo_fabricante = 5;

    

28. ​	SELECT p.nombre as 'nombre de producto', p.codigo_fabricante as 'código de fabricante'

    ​	FROM producto as p

    ​	WHERE p.codigo_fabricante IN (1, 3, 5);

    

29. ​	SELECT p.nombre as 'nombre de producto', p.precio * 100 as 'céntimos'

    ​	FROM producto as p

    

30. ​	SELECT f.nombre as 'nombre de fabricantes que empiezan por s'

    ​	FROM fabricante as f

    ​	WHERE LOWER ( LEFT (f.nombre, 1) ) = 's';

    

31. ​	SELECT f.nombre as 'nombre de fabricantes que terminan en e'

    ​	FROM fabricante as f

    ​	WHERE LOWER ( RIGHT (f.nombre, 1) ) = 'e';

    

32. ​	SELECT f.nombre as 'nombre de fabricantes que contienen w'

    ​	FROM fabricante as f

    ​	WHERE LOWER ( f.nombre ) LIKE = '%w%';

    ​	*** %, busca cualquier nombre que contenga el carácter "w" en cualquier posición dentro del nombre.

    

33. ​	SELECT f.nombre as 'nombre de fabricantes de 4 caracteres'

    ​	FROM fabricante as f

    ​	WHERE LENGTH ( f.nombre ) = 4;

    

34. ​	SELECT p.nombre as 'productos con 'Portátil' en su nombre'

    ​	FROM producto as p

    ​	WHERE f.nombre LIKE '%Portátil%';

    

35. ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio'

    ​	FROM producto as p

    ​	WHERE f.nombre LIKE '%Monitor%' AND p.precio < 215;

    

36. ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio'

    ​	FROM producto as p

    ​	WHERE p.precio >= 180

    ​	ORDER BY p.precio DESC;
    
    ​	*** Tabla producto ordenada de forma descendente según su precio y cuyo valor es mayor a 180 euros
    
    ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio'
    
    ​	FROM producto as p
    
    ​	WHERE p.precio >= 180
    
    ​	ORDER BY p.nombre ASC;
    
    ​	*** Tabla producto ordenada alfabéticamente de forma ascendente y cuyo valor es mayor a 180 euros



III)	Consultas Multitabla (Composición Interna)



1. ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio', f.nombre as 'nombre de fabricante'

   ​	FROM producto as p, fabricante as f

   ​	WHERE p.codigo_fabricante = f.codigo;

   

2. ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio', f.nombre as 'nombre de fabricante'

   ​	FROM producto as p, fabricante as f

   ​	WHERE p.codigo_fabricante = f.codigo;

   ​	ORDER BY f.nombre ASC;

   

3. ​	SELECT p.codigo as 'ID producto', p.nombre as 'nombre de producto', f.codigo as 'ID fabricante', f.nombre as 'nombre de fabricante'

   ​	FROM producto as p, fabricante as f

   ​	WHERE p.codigo_fabricante = f.codigo;

   

4. ​	SELECT p.nombre as 'nombre de producto', p.precio as 'precio', f.nombre as 'nombre de fabricante'

   ​	FROM producto as p, fabricante as f

   ​	WHERE p.codigo_fabricante = f.codigo

   ​	ORDER BY p.precio ASC

   ​	LIMIT 1;

   

5. ​        SELECT p.nombre as 'nombre de producto', p.precio as 'precio', f.nombre as 'nombre de fabricante'

   ​	FROM producto as p, fabricante as f

   ​	WHERE p.codigo_fabricante = f.codigo

   ​	ORDER BY p.precio DESC

   ​	LIMIT 1;

   

6. ​        SELECT p.codigo as 'ID producto', p.nombre as 'nombre de producto', p.precio as 'precio', f.nombre as 'nombre de fabricante'

   ​	FROM producto as p, fabricante as f

   ​	WHERE p.codigo_fabricante = f.codigo 

   ​        AND f.nombre = 'Lenovo';

   

7. ​        SELECT p.codigo as 'ID producto', p.nombre as 'nombre de producto', p.precio as 'precio', f.nombre as 'nombre de fabricante'

   ​	FROM producto as p, fabricante as f

   ​	WHERE p.codigo_fabricante = f.codigo 

   ​        AND f.nombre = 'Crucial' AND p.precio > 200;

   

8. ​        SELECT p.codigo as 'ID producto', p.nombre as 'nombre de producto', p.precio as 'precio', f.nombre as 'nombre de fabricante'

   ​	FROM producto as p, fabricante as f

   ​	WHERE p.codigo_fabricante = f.codigo 

   ​	AND ( f.nombre = 'Asus' OR f.nombre = 'Hewlett-Packard' OR f.nombre = 'Seagate' );

   

9. ​        SELECT p.codigo as 'ID producto', p.nombre as 'nombre de producto', p.precio as 'precio', f.nombre as 'nombre de fabricante'

   ​	FROM producto as p, fabricante as f

   ​	WHERE p.codigo_fabricante = f.codigo 

   ​	AND f.nombre IN ('Asus', 'Hewlett-Packard', 'Seagate');

   

10. ​        SELECT p.nombre as 'nombre de producto', p.precio as 'precio', f.nombre as 'nombre de fabricante'

    ​	FROM producto as p, fabricante as f

    ​	WHERE p.codigo_fabricante = f.codigo 

    ​	AND LOWER( RIGHT ( f.nombre, 1) ) = 'e';

    ​	*** Devuelve una lista con los nombres de fabricantes que terminan en 'e'

    

11. ​        SELECT p.nombre as 'nombre de producto', p.precio as 'precio', f.nombre as 'nombre de fabricante'

    ​	FROM producto as p, fabricante as f

    ​	WHERE p.codigo_fabricante = f.codigo 

    ​	AND LOWER ( f.nombre ) LIKE %'w'%;

    ​	*** Devuelve una lista de los fabricantes que contienen 'w' en su nombre

    

12. ​        SELECT p.nombre as 'nombre de producto', p.precio as 'precio', f.nombre as 'nombre de fabricante'

    ​	FROM producto as p, fabricante as f

    ​	WHERE p.codigo_fabricante = f.codigo 

    ​	AND p.precio >= 180

    ​	ORDER BY p.precio DESC;

    ​	*** Resultados ordenados según su precio de forma descendente y cuyo valor es mayor o igual a 180

    ​        SELECT p.nombre as 'nombre de producto', p.precio as 'precio', f.nombre as 'nombre de fabricante'

    ​	FROM producto as p, fabricante as f

    ​	WHERE p.codigo_fabricante = f.codigo 

    ​	AND p.precio >= 180

    ​	ORDER BY p.nombre ASC;

    *** Resultados ordenados según alfabéticamente de forma ascendente y cuyo valor es mayor o igual a 180

    

13. ​        SELECT f.codigo as 'ID fabricante', f.nombre as 'nombre de fabricante'

    ​	FROM producto as p, fabricante as f

    ​	WHERE p.codigo_fabricante = f.codigo 









​		

























