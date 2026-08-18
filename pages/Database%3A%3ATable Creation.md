- What is the basic information to be specified for creating the table #card
  id:: 6a7db0d9-65c2-4fed-b5f4-57432ab40717
	- Database name , table name , columns and their datatypes
	- ```sql
	  CREATE TABLE <database name>.<table name> (
	  	col1 datatype,
	  	col2 datatype.
	    	col3 datatype...
	    	coln datatype
	  );
	  
	  CREATE TABLE todoapp.task_list(
	    task_id INT,
	    topic VARCHAR(100),
	    due_date DATE,
	    status VARCHAR(30),
	    user_name VARCHAR(50)
	  );
	  ```
-
- How can you prevent a column from having NULL values in a table? #card
  id:: 6a7db17d-ec71-46ac-94a2-46d12e10cfd3
	- By specifying the `NOT NULL` constraint on the column while creating the table
	- ```sql
	  CREATE TABLE todoapp.task_list(
	    task_id INT,
	    topic VARCHAR(100) NOT NULL,
	    due_date DATE NOT NULL,
	    status VARCHAR(30) NOT NULL,
	    user_name VARCHAR(50)
	  );
	  ```
- How do you insert records into a table? #card
  id:: 6a7db1f5-d732-496d-a2ef-38b70c809418
	- ```sql
	  insert into <database name>.<table name>(col1 , col2 , col3)
	  values(1, "string" ,"2026/12/31");
	  
	  insert into todoapp.task_list(task_id, topic, due_date,status,user_name
	  values(1, "string" ,"2026/12/31" ,"In progress" , NULL);
	  
	  ```
- Do you have to specify all the columns in the table in the insert statement? #card
  id:: 6a7db293-6fcf-4973-8cb4-2ed17b62abd1
	- No. Partial set of columns can be specified. If the column that is not specified has a not null constraint then the insert will fail; Else a NULL value is inserted into that column
- Is a blank string ("") same as the NULL value? #card
  id:: 6a7db2ec-3dc3-4bf3-805f-72dd9deaa5fe
	- No; a blank string is a string with zero len. A NULL a special key word and a value that need be handled separately.
- What is a primary key? #card
  id:: 6a7db334-0003-4b69-a8ce-867b33f5304f
	- A primary key uniquely identifies a row in a table.
- Why are integers preferred for defining primary keys? #card
  id:: 6a7db39b-e0b1-4140-a900-553201e6af27
	- The primary key is used in various sort of operations such as updating rows (using the primary key) , merging of rows across tables. Identifying relationships etc.
	- While strings can be used as primary key, the operations tend to slow down due to high level of computation needed to handle strings. Integers on the other hand is basic and also helps in reducing the space consumption
	-