- What is a database? #card
	- A database or some times called a schema is a namespace to hold objects such as Table , stored procedures etc. An object name must be unique within a namespace
	- Different databases use different terminologies - some call it database and some call it schema
- # Creating a database
- Login into the MSQL console that is installed using the root.
- ## Exercise 1 : List databases in the instance
	- To check the database already available use. The SQL should be terminated using a semicolon
	- ```SQL
	  SHOW DATABASES; 
	  
	  
	  mysql> show databases;
	  +--------------------+
	  | Database           |
	  +--------------------+
	  | information_schema |
	  | mysql              |
	  | performance_schema |
	  | sakila             |
	  | sys                |
	  | world              |
	  +--------------------+
	  6 rows in set (0.04 sec)
	  ```
	- These databases are preinstalled and should not be deleted
- ## Exercise 2 : Create Database
	- ```sql
	  mysql> CREATE DATABASE todoapp;
	  Query OK, 1 row affected (0.04 sec)
	  
	  mysql> SHOW DATABASES;
	  +--------------------+
	  | Database           |
	  +--------------------+
	  | information_schema |
	  | mysql              |
	  | performance_schema |
	  | sakila             |
	  | sys                |
	  | todoapp            |
	  | world              |
	  +--------------------+
	  7 rows in set (0.00 sec)
	  ```
- ## Exercise 3:
	- Now we want to store some todo items in the todoapp DB. First step before creating is the write down what we want to store
	- As a user of the TodoApp i want to store the below information for each of my todo item. Write down on a sheet of paper what do you want to store
- ## Exercise 4:
	- Now for the items that you want to store, you need to specify the data types. Just like programming languages have datatypes, information in DB has types
	- Add the types to the information you want to store
	-