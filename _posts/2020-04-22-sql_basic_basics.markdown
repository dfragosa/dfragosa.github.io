---
layout: post
title:      "SQL Basic Basics"
date:       2020-04-22 23:50:53 +0000
permalink:  sql_basic_basics
---


Salutations, my name is of no importance.  Going to be quick, simple (hopefully) and to the point.  
Welcome to the world of SQL which stands for Standard Query Language.  It kind of uses English
speak.  Henceforth coming due to my lackadaisical writing English speak = SQL commands structure 
just the way that the English language does (English speak).  It's used to operate on a DBMS (Database
Management System)

If you can CRUD you are halfway there.  This acronym is the four basic operations at working with data. 

* Create- this creates a table that's going to hold our data
* Read- this is in order to query or read data in the table
* Update- changes the data that's already in the table
* Delete- removes the data from a table

Let's put it practice now using Creating data:
In abstract terms it's:
 CREATE TABLE table_name (column_name1  data_type, column_name2 data_type)
 
 In real life it's:

CREATE TABLE student (id INTEGER PRIMARY KEY,  name TEXT, age INTEGER,  grade INTEGER);

To put values into the table we would type the following

INSERT INTO student (name, age, grade) 
VALUES ("Sam", 12, 9);


If you type in your terminal or command line  at the  sqlite> prompt 
** .header on
 .mode column**

this will make the format the data to make it easy to read as such if you had info in it already.

**id    name    age    grade**
1         Sam         12          9
2         Sasha       18         12
3        Seleaha    7             5

Let's put into practice  Readiing data:
We use filters to read and sort data.
* SELECT - tells computer you want values returned to you and what those values are
* FROM -  you telling the computer From this table_name or that table_name
* WHERE will list the conditions that need to be met for a specific value we are looking for.  
     Example WHERE value is > 40,  or WHERE name = "Steve".  WHERE is optional.

In abstract terms it's:

SELECT column_name1, column_name2 FROM table_name;

or you can use the * to select all the columns in a table

SELECT * FROM table_name;

or use all three combos above as such
SELECT column_name1, column_name3
FROM table_name
WHERE column_name operator value

Operator values you can use are
= equal to
> greater than
< less than
>= greater than or equal to
<= less than or equal to
<> not equal to
% this is placed before or after characters to search for character match
BETWEEN - between two values
LIKE - used to search for a patter

SELECT name  FROM  student WHERE grade > 9;

should return to you 
**id    name   **
1         Sam         
2         Sasha       

Lets put into practice using Update
In abstract terms it's
 
 UPDATE table_name 
 SET column_name = new value 
 WHERE column_name operator value;  
 
 Sam's name should be Sammy let's change that:
 
 UPDATE student SET name = "Sammy"
 WHERE name = "Sam";
 
 This should do the trick for the basic usage.  
 




      




 
