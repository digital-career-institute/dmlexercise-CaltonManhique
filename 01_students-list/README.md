# Student List

## Create a new database
Create a new database for this exercise.
```
CREATE DATABASE exercise_student_list
use exercise_student_list
``

## Create the student table
Create a table named **students** with the following columns:  
```
id (integer, primary key)  
name (varchar, maximum length 50)  
age (integer)  
grade (float)  
```

> ANSWER
CREATE DATABASE exercise_student_list;
use exercise_student_list;
Create table student(id integer primary key, name varchar(50), age integer, grade float);
describe student;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| id    | int         | NO   | PRI | NULL    |       |
| name  | varchar(50) | YES  |     | NULL    |       |
| age   | int         | YES  |     | NULL    |       |
| grade | float       | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+

## Insert and Modify Data
### 1. Insert Data
Insert these records into the students table with the following data:
```
(1, 'John Doe', 20, 85.5, '123 Main St')
(2, 'Jane Smith', 22, 92.0, '456 Oak Ave')
(3, 'Bob Johnson', 21, 78.5, '789 Pine Rd')
(4, 'Tina Turner', 25, 71.0, '45 Columbia St')
```

> ANSWER  
alter table student add address varchar(100);
describe student;
+---------+--------------+------+-----+---------+-------+
| Field   | Type         | Null | Key | Default | Extra |
+---------+--------------+------+-----+---------+-------+
| id      | int          | NO   | PRI | NULL    |       |
| name    | varchar(50)  | YES  |     | NULL    |       |
| age     | int          | YES  |     | NULL    |       |
| grade   | float        | YES  |     | NULL    |       |
| address | varchar(100) | YES  |     | NULL    |       |
+---------+--------------+------+-----+---------+-------+

insert into student (id, name, age, grade, address) values(1, 'John Doe', 20, 85.5, '123 Main St'), (2, 'Jane Smith', 22, 92.0, '456 Oak Ave'),(3, 'Bob Johnson', 21, 78.5, '789 Pine Rd'),(4, 'Tina Turner', 25, 71.0, '45 Columbia St');
select * from student;
+----+-------------+------+-------+----------------+
| id | name        | age  | grade | address        |
+----+-------------+------+-------+----------------+
|  1 | John Doe    |   20 |  85.5 | 123 Main St    |
|  2 | Jane Smith  |   22 |    92 | 456 Oak Ave    |
|  3 | Bob Johnson |   21 |  78.5 | 789 Pine Rd    |
|  4 | Tina Turner |   25 |    71 | 45 Columbia St |
+----+-------------+------+-------+----------------+

### Update Data
Update the grade of 'Jane Smith' to 95.0.

> ANSWER  
update student set grade = 95.5 where id = 2;
+----+-------------+------+-------+----------------+
| id | name        | age  | grade | address        |
+----+-------------+------+-------+----------------+
|  1 | John Doe    |   20 |  85.5 | 123 Main St    |
|  2 | Jane Smith  |   22 |  95.5 | 456 Oak Ave    |
|  3 | Bob Johnson |   21 |  78.5 | 789 Pine Rd    |
|  4 | Tina Turner |   25 |    71 | 45 Columbia St |
+----+-------------+------+-------+----------------+

### Delete Data
Delete the record of the student with id 3 from the students table.

> ANSWER  
delete from student where id = 3;
+----+-------------+------+-------+----------------+
| id | name        | age  | grade | address        |
+----+-------------+------+-------+----------------+
|  1 | John Doe    |   20 |  85.5 | 123 Main St    |
|  2 | Jane Smith  |   22 |  95.5 | 456 Oak Ave    |
|  4 | Tina Turner |   25 |    71 | 45 Columbia St |
+----+-------------+------+-------+----------------+

### Select Data
Write a query to retrieve the names and ages of all students.  

> ANSWER  
select name, age from student;
+-------------+------+
| name        | age  |
+-------------+------+
| John Doe    |   20 |
| Jane Smith  |   22 |
| Tina Turner |   25 |
+-------------+------+


### Bonus: Select the best students
Write a query to retrieve the names and grade of all students with a grade higher than 80.

> ANSWER  
select name, grade from student where grade > 80;
+------------+-------+
| name       | grade |
+------------+-------+
| John Doe   |  85.5 |
| Jane Smith |  95.5 |
+------------+-------+
