# Online Shop 

## Create a new database
Create a new database for this exercise.
```
CREATE DATABASE exercise_online_shop
use exercise_online_shop
``

## Create the product table
Create a table named **products** with the following columns:  
```
product_id (integer, primary key)
product_name (varchar, maximum length 100)
price (decimal, 2 decimal places)
stock_quantity (integer)
```

> ANSWER  
create table products(product_id integer primary key, product_name varchar(100), price decimal(3,2), stock_quantity integer);
describe products;
+----------------+---------------+------+-----+---------+-------+
| Field          | Type          | Null | Key | Default | Extra |
+----------------+---------------+------+-----+---------+-------+
| product_id     | int           | NO   | PRI | NULL    |       |
| product_name   | varchar(100)  | YES  |     | NULL    |       |
| price          | decimal(10,2) | YES  |     | NULL    |       |
| stock_quantity | int           | YES  |     | NULL    |       |
+----------------+---------------+------+-----+---------+-------+

## Insert and select Data
### 1. Insert Data
Insert these records into the products table with the following data:
```
(1, 'Laptop', 999.99, 20)
(2, 'Smartphone', 499.50, 30)
(3, 'Headphones', 79.99, 50)
(4, 'Tablet', 299.75, 15)
(5, 'Bluetooth Speaker', 39.95, 40)
(6, 'Keyboard', 29.95, 10)
```

> ANSWER  
INSERT INTO products (product_id, product_name, price, stock_quantity) VALUES(1, 'Laptop', 999.99, 20),
(2, 'Smartphone', 499.50, 30),
(3, 'Headphones', 79.99, 50),
(4, 'Tablet', 299.75, 15),
(5, 'Bluetooth Speaker', 39.95, 40),
(6, 'Keyboard', 29.95, 10);

SELECT* FROM products ;
+------------+-------------------+--------+----------------+
| product_id | product_name      | price  | stock_quantity |
+------------+-------------------+--------+----------------+
|          1 | Laptop            | 999.99 |             20 |
|          2 | Smartphone        | 499.50 |             30 |
|          3 | Headphones        |  79.99 |             50 |
|          4 | Tablet            | 299.75 |             15 |
|          5 | Bluetooth Speaker |  39.95 |             40 |
|          6 | Keyboard          |  29.95 |             10 |
+------------+-------------------+--------+----------------+


### Select Products 
Write a query to retrieve the **names and prices** of all products.

> ANSWER  
SELECT product_name, price  FROM products;
+-------------------+--------+
| product_name      | price  |
+-------------------+--------+
| Laptop            | 999.99 |
| Smartphone        | 499.50 |
| Headphones        |  79.99 |
| Tablet            | 299.75 |
| Bluetooth Speaker |  39.95 |
| Keyboard          |  29.95 |
+-------------------+--------+

### Search expensive products
Write a query to select products with a price greater than $100.

> ANSWER  
SELECT product_name, price  FROM products where price > 100;
+--------------+--------+
| product_name | price  |
+--------------+--------+
| Laptop       | 999.99 |
| Smartphone   | 499.50 |
| Tablet       | 299.75 |
+--------------+--------+

### Search low stock
Write a query to retrieve the **names an prices** of all products with a stock less than 30.

> ANSWER  
SELECT product_name, price  FROM products where stock_quantity < 30;
+--------------+--------+
| product_name | price  |
+--------------+--------+
| Laptop       | 999.99 |
| Tablet       | 299.75 |
| Keyboard     |  29.95 |
+--------------+--------+

### Bonus: Select expensive out of stock products
Write a query to retrieve the **names and prices** of all products with a price greater than $100 and a stock less than 30.

> ANSWER  
SELECT product_name, price  FROM products WHERE price > 100 AND stock_quantity < 30;
+--------------+--------+
| product_name | price  |
+--------------+--------+
| Laptop       | 999.99 |
| Tablet       | 299.75 |
+--------------+--------+
