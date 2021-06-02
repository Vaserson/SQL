<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="utf-8">
  <title></title>
  <link href="style.css" rel="stylesheet" />
</head>
<body>




<button type="button" class="collapsible">1. SELECT, DISTINCT, LIKE</button>

<div class="content">
	<button type="button" class="collapsible">1.1 Вывести таблицу customers</button>
	<code class="content">
		<pre>
SELECT * FROM customers;</pre>
	</code>
	<button type="button" class="collapsible">1.2 Вывести только города и страны</button>
	<code class="content">
		<pre>
SELECT City, Country FROM customers;</pre>
	</code>
	<button type="button" class="collapsible">1.3 Вывести только города начинающиеся на 'b'</button>
	<code class="content">
		<pre>
SELECT City FROM customers
WHERE City LIKE 'b%';</pre>
	</code>
	<button type="button" class="collapsible">1.4 Вывести города HE начинающиеся на 'b'</button>
	<code class="content">
		<pre>
SELECT City FROM customers
WHERE City NOT LIKE 'b%';</pre>
	</code>
	<button type="button" class="collapsible">1.5 Вывести города, которые начинаются на 'M' и заканчиваются на 'e'</button>
	<code class="content">
		<pre>
SELECT City FROM customers
WHERE City LIKE 'M%e';</pre>
	</code>
	<button type="button" class="collapsible">1.6 Только заканчиваются на 'e'</button>
	<code class="content">
		<pre>
SELECT City FROM customers
WHERE City LIKE '%e';</pre>
	</code>
	<button type="button" class="collapsible">1.7 Все города с пробелом в названии</button>
	<code class="content">
		<pre>
SELECT City FROM customers
WHERE City LIKE '% %';</pre>
	</code>
	<button type="button" class="collapsible">1.8 Вывести количество строк в столбце 'City'</button>
	<code class="content">
		<pre>
SELECT COUNT(City) FROM customers;</pre>
	</code>
	<button type="button" class="collapsible">1.9 Вывести два столбца: Город, и число его повторений в столбце 'City'</button>
	<code class="content">
		<pre>
SELECT City, COUNT(City) FROM customers
GROUP BY City;</pre>
	</code>
	<button type="button" class="collapsible">1.10 Количество уникальных городов</button>
	<code class="content">
		<pre>
SELECT COUNT(DISTINCT City) FROM customers;
<i>-- или</i>
SELECT COUNT(DISTINCT (City)) FROM customers;</pre>
	</code>
</div>





<button type="button" class="collapsible">2. AND, OR</button>

<div class="content">
	<button type="button" class="collapsible">2.1 Вывести customers у которых город 'Madrid' и страна 'Spain'</button>
	<code class="content">
		<pre>
SELECT * FROM customers
WHERE City = 'Madrid' AND Country = 'Spain';</pre>
	</code>
	<button type="button" class="collapsible">2.2 Вывести customers у которых город 'London' ИЛИ страна 'France'</button>
	<code class="content">
		<pre>
SELECT * FROM customers
WHERE City = 'London' OR Country = 'France';</pre>
	</code>
	<button type="button" class="collapsible">2.3 Вывести customers у которых город 'London' ИЛИ страна 'France'</button>
	<code class="content">
		<pre>
SELECT * FROM customers
WHERE City = 'London' OR Country = 'France';</pre>
	</code>
	<button type="button" class="collapsible">2.4 Вывести customers у которых CustomerName имеет в названии букву на 'z' И город 'London' ИЛИ страна 'Spain'</button>
	<code class="content">
		<pre>
SELECT * FROM customers
WHERE CustomerName LIKE '%a%'
	AND (City = 'London' OR Country = 'Spain');</pre>
	</code>
</div>




<button type="button" class="collapsible">3. ORDER BY, UPDATE</button>

<div class="content">
	<button type="button" class="collapsible">3.1 Сделать страну пустой у supplier с SupplierID = 26</button>
	<code class="content">
		<pre>
UPDATE suppliers
SET Country = NULL
WHERE SupplierID = 26;</pre>
	</code>
	<button type="button" class="collapsible">3.2 Найти записи, где Country = NULL</button>
	<code class="content">
		<pre>
SELECT * FROM suppliers
WHERE Country IS NULL;</pre>
	</code>
	<button type="button" class="collapsible">3.3 Найти записи, где Country не NULL</button>
	<code class="content">
		<pre>
SELECT * FROM suppliers
WHERE Country IS NOT NULL;</pre>
	</code>
	<button type="button" class="collapsible">3.4 Вернуть страну на место</button>
	<code class="content">
		<pre>
UPDATE suppliers
SET Country = 'Italy'
WHERE SupplierID = 26;</pre>
	</code>
	<button type="button" class="collapsible">3.5 Вывести всех suppliers с сортировкой по ContactName</button>
	<code class="content">
		<pre>
SELECT * FROM suppliers
ORDER BY ContactName;</pre>
	</code>
	<button type="button" class="collapsible">3.6 Вывести всех suppliers с обратной сортировкой по ContactName</button>
	<code class="content">
		<pre>
SELECT * FROM suppliers
ORDER BY ContactName DESC;</pre>
	</code>
</div>




<button type="button" class="collapsible">4. Агрегатные функции и операторы сравнения</button>

<div class="content">
	<button type="button" class="collapsible">4.1 Вывести минимальное, максимальное, среднее значение и сумму для Quantity в order_details</button>
	<code class="content">
		<pre>
SELECT MIN(Quantity), MAX(Quantity), AVG(Quantity), SUM(Quantity) from order_details;</pre>
	</code>
	<button type="button" class="collapsible">4.2 Вывести все order_details у которых Quantity от 80 до 100</button>
	<code class="content">
		<pre>
SELECT * from order_details
WHERE Quantity BETWEEN 80 AND 100;</pre>
	</code>
	<button type="button" class="collapsible">4.3 Вывести все order_details у которых Quantity больше или равняется 80</button>
	<code class="content">
		<pre>
SELECT * from order_details
WHERE Quantity &gt;= 80;</pre>
	</code>
	<button type="button" class="collapsible">4.4 Вывести все order_details у которых Quantity меньше или равняется 3</button>
	<code class="content">
		<pre>
SELECT * from order_details
WHERE Quantity &lt;= 3;</pre>
	</code>
	<button type="button" class="collapsible">4.5 Вывести все order_details у которых Quantity равняется 120</button>
	<code class="content">
		<pre>
SELECT * from order_details
WHERE Quantity = 120;</pre>
	</code>
	<button type="button" class="collapsible">4.6 Вывести все order_details у которых Quantity НЕ равняется 120</button>
	<code class="content">
		<pre>
SELECT * from order_details
WHERE Quantity &lt;&gt; 120;
<i>-- или</i>
SELECT * from order_details
WHERE Quantity != 120;</pre>
	</code>
</div>




<button type="button" class="collapsible">5. GROUP BY</button>

<div class="content">
	<button type="button" class="collapsible">5.1 Сгруппировать order_details по OrderID</button>
	<code class="content">
		<pre>
SELECT * from order_details
GROUP BY OrderID;
);</pre>
	</code>
	<button type="button" class="collapsible">5.2 Вывести колонку OrderID и колонку с количеством сгруппированных OrderID в order_details</button>
	<code class="content">
		<pre>
SELECT OrderID, COUNT(OrderID) from order_details
GROUP BY OrderID;</pre>
	</code>
	<button type="button" class="collapsible">5.3*** Вывести одно число максимального количества сгруппированных OrderID в order_details</button>
	<code class="content">
		<pre>
SELECT COUNT(OrderID) from order_details
GROUP BY OrderID
ORDER BY COUNT(OrderID) DESC
LIMIT 1;</pre>
	</code>
	<button type="button" class="collapsible">5.4 Вывести OrderID сгруппированные из более чем 4-ёх OrderID в order_details</button>
	<code class="content">
		<pre>
SELECT OrderID from order_details
GROUP BY OrderID
HAVING COUNT(OrderID) &gt; 4;</pre>
	</code>
</div>




<button type="button" class="collapsible">6. Вложенный запрос и EXISTS</button>

<div class="content">
	<button type="button" class="collapsible">6.1 Вывести customers, которых нету в CustomerID в orders при помощи вложенного запроса</button>
	<code class="content">
		<pre>
SELECT * FROM customers
WHERE customers.CustomerID NOT IN (
	SELECT orders.CustomerID 
	FROM orders
);</pre>
	</code>
	<button type="button" class="collapsible">6.2 Вывести customers, которых нету в CustomerID в orders при помощи ключевого слова EXISTS</button>
	<code class="content">
		<pre>
SELECT * FROM customers AS c
WHERE NOT EXISTS (
	SELECT * FROM orders AS o
	WHERE c.CustomerID = o.CustomerID
);</pre>
	</code>
</div>






<button type="button" class="collapsible">7. Объединение таблиц</button>
<div class="content">
	<button type="button" class="collapsible">7.1 Вывести две колонки: ProductName из таблицы products и соответствующие им SupplierName из таблицы suppliers</button>
	<code class="content">
		<pre>
	SELECT p.ProductName, s.SupplierName
	FROM products AS p
	JOIN suppliers AS s
	ON p.SupplierID = s.SupplierID;</pre>
	</code>
	<button type="button" class="collapsible">7.2 Вывести две колонки: ProductName из таблицы products и соответствующие им CategoryName из таблицы categories. Сортировать по ProductName</button>
	<code class="content">
		<pre>
	SELECT p.ProductName, c.CategoryName
	FROM products AS p
	JOIN categories AS c
	ON p.CategoryID = c.CategoryID
	ORDER BY p.ProductName;</pre>
	</code>
	<button type="button" class="collapsible">7.3 Вывести информацию о shippers у которых больше 60-ти orders используя JOIN</button>
	<code class="content">
		<pre>
	SELECT s.*
	FROM shippers AS s
	JOIN orders AS o
	ON s.ShipperID = o.ShipperID
	GROUP BY o.ShipperID
	HAVING COUNT(o.ShipperID) &gt; 60;</pre>
	</code>
	<button type="button" class="collapsible">7.4 Вывести информацию о shippers у которых больше 60-ти orders используя вложенный запрос</button>
	<code class="content">
		<pre>
	SELECT s.*
	FROM shippers AS s
	WHERE ShipperID IN(
		SELECT o.ShipperID
		FROM orders AS o
		GROUP BY o.ShipperID
		HAVING COUNT(o.ShipperID) &gt; 60);</pre>
	</code>
	<button type="button" class="collapsible">7.5 Вывести все поля customers которых нет в orders используя LEFT JOIN</button>
	<code class="content">
		<pre>
	SELECT c.*
	FROM customers AS c
	LEFT JOIN orders AS o
	ON c.CustomerID = o.CustomerID
	WHERE o.CustomerID IS NULL;</pre>
	</code>
	<button type="button" class="collapsible">7.6  Вывести все поля customers которых нет в orders используя вложенный запрос</button>
	<code class="content">
		<pre>SELECT c.*
	FROM customers AS c
	WHERE c.CustomerID NOT IN(
		SELECT o.CustomerID
		FROM orders AS o);</pre>
	</code>
</div>
<script>
var coll = document.getElementsByClassName("collapsible");
var i;

for (i = 0; i < coll.length; i++) {
  coll[i].addEventListener("click", function() {
    this.classList.toggle("active");
    var content = this.nextElementSibling;
    if (content.style.display === "block") {
      content.style.display = "none";
    } else {
      content.style.display = "block";
    }
  });
}
</script>

</body>
</html>