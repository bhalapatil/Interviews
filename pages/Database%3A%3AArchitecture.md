- What is a database or a schema? #card
  id:: 6a7daac5-7379-4c64-8743-222117ee44f8
	- The description of a database is called the database schema, which is specified during database design and is not expected to change frequently
	- It also provides a namespace to contain the objects within the physical database. An object name is unique within the namesapce
- How to create a database in MySQL? #card
  id:: 6a7dab84-e86e-4013-88fa-e45c0cb4a7de
	- ```SQL
	  CREATE DATABASE <database name>;
	  
	  CREATE DATABASE todoapp;
	  ```
- How to list the available databases in an instance of MySQL? #card
  id:: 6a7daac6-3438-49b2-aecd-435bd5e23125
	- ```sql
	  SHOW DATABASES;
	  ```
- What does metadata mean in database technology? #card
  id:: 6a7dac17-2021-460b-9e7f-bae8e706f71b
	- Metadata means data about data. In the context of Database, the database software maintains information about user create objects such as the tables, procedures, View etc in an inbuilt database. Such data about the data is called metadata
- How does the database manage the metadata? #card
  id:: 6a7dac06-0cd1-43b5-a7e8-b1d330aa5562
	- Typically most databases have some prebuild databases that are created when the software is installed and the instance is started. In MySQL this kind of database is called the `information schem`. List the databases available in the instance to see this
	-
-