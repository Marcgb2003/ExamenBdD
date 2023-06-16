#Examen BdD

1. Escribe una sentencia SQL que muestre el valor de todos los atributos de todos los regisrtos de la tabla Costumers
![image](https://github.com/Marcgb2003/ExamenBdD/assets/122601138/bd34dc15-bd99-4620-97a1-914697a8ee80)
~~~
Select * from Customers
~~~
\
2. Escribe una sentencia SQL que muestre el valor máximo de todos los atributos de todos los registros de la tabla Customers
![image](https://github.com/Marcgb2003/ExamenBdD/assets/122601138/e482c66a-8000-4813-b5e6-e7e0749ae6fb)
~~~
Select max(CustomerID), max(CustomerName), max(ContactName), max(Address), max(City), max(PostalCode), max(Country) from Customers
~~~
\
3. Escribe una sentencia SLQ que muestre solo los valores de los atributos CustomerName y City de todos los registros de la tabla costumers
![image](https://github.com/Marcgb2003/ExamenBdD/assets/122601138/64ac0d68-1124-4da7-afd7-26c00cb02027)
~~~
Select CustomerName, City from Customers
~~~
\
4.Escribe una sentencia SQL para la tabla Customers que muestre todos los valores diferentes del atributo Country, sin mostrar duplicados.
![image](https://github.com/Marcgb2003/ExamenBdD/assets/122601138/bc9dbf9a-eeed-4f64-8d55-3e502108151b)
~~~
Select Distinct Country from Customers
~~~
\
5. Escribe una sentencia SQL que muestre los valores de todos los atributos de la tabla Customers, pero solo de los registros donde el atributo Country valga exactamente Mexico.
![image](https://github.com/Marcgb2003/ExamenBdD/assets/122601138/0fe65496-a97b-437a-99bb-c301baf6d7d7)
~~~
Select * from Customers where country like 'Mexico'
~~~
\
6. Escribe una sentencia SQL que muestre los valores de todos los atributos de la tabla Customers, pero solo de los registros donde el atributo Country valga Germany y simultáneamente el atributo City valga Berlin.3
![image](https://github.com/Marcgb2003/ExamenBdD/assets/122601138/4c3e79f5-8010-4d20-a868-43708811ee31)
~~~
Select * from Customers where country like 'Germany' and city like 'Berlin'
~~~
\
7. Escribe una sentencia SQL que muestre el nombre de todos los productos (ProductName) y el nombre de la categoría (CategorieName) a la que pertenece cada uno de los productos. Las categorías se encuentran en la tabla Categories y los productos en la tabla Products.
![image](https://github.com/Marcgb2003/ExamenBdD/assets/122601138/7601b65e-0b0a-40fc-afee-d36e0df7b237)
~~~
Select p.ProductName,c.CategoryName from Products p inner join Categories c on p.CategoryID=c.CategoryID
~~~
\
8. Escribe una sentencia SQL que muestre el nombre de todos los productos (ProductName) y el nombre de las categorías (CategorieName) a las que pertenecen cada uno de los productos así como también el nombre del proveedor (Suppliers). Las categorías se encuentran a la tabla Categories, los productos a la tabla Products y los proveedores a la tabla Suppliers.
![image](https://github.com/Marcgb2003/ExamenBdD/assets/122601138/c1b5129c-e7e0-4626-8852-a605a5fef300)
~~~
Select p.ProductName,c.CategoryName, s.SupplierName from Categories c inner join (Products p inner join Suppliers s on p.SupplierID=s.SupplierID )on p.CategoryID=c.CategoryID
~~~
\
9.Escribe una sentencia SQL que cuente el número de productos (Products) por categorías (Categories). Se tienen que mostrar dos columnas, CategorieName y el contador. Solo tienen que aparecer las categorías con productos. Las categorías se encuentran a la tabla Categories, los productos en la tabla Products.
![image](https://github.com/Marcgb2003/ExamenBdD/assets/122601138/8738cccc-ceea-4cf7-bb98-69557aa69ef0)
~~~
Select c.CategoryName, count(p.ProductID) from Categories c inner join Products p on c.CategoryID=p.CategoryID group by c.CategoryName
~~~
\
10.Escribe una sentencia SQL que cuente el número de productos (Productos) por categorías (Categorías). Solamente nos interesa contar el productos que su nombre empieza por P. Tienen que aparecer las categorías que no tienen productos. Las categorías se encuentran en la tabla Categorías, los productos en la tabla Products.
![image](https://github.com/Marcgb2003/ExamenBdD/assets/122601138/b27f7f62-2a86-450a-be16-168f808e504b)
~~~
Select c.CategoryName, count(p.ProductID) from Categories c left join Products p on c.CategoryID=p.CategoryID where p.ProductName like 'P%' group by c.CategoryName
~~~
En esta, como puedes ver, hay una equivocación que hace que no salgan los que no tienen ninguno, así que está mal
