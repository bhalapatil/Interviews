# Tuples and its operations
	- What does a tuple mean in computer science ? In which domains is it used ? #card
	  id:: 6a82e63c-d1c6-40dc-9372-3e6de231e52c
		- Unlike a set, the **order of elements matters**, and **duplicate values are allowed**. Tuples are typically **immutable**, meaning once they are created, their values and size cannot be changed. They are used to group related pieces of data together as a single compound object
		- Key Characteristics of Tuples
			- **Ordered:** The position of each item is fixed (indexed).
			- **Immutable:** Cannot be modified, appended, or resized after creation.
			- **Heterogeneous:** Can store different data types (e.g., a string, an integer, and a float together).
			- **Fixed Length:** Represents a structure with a specific, predetermined number of fields.
		- ---
		- Core Domains Where Tuples Are Used
		- Tuples are fundamental structures across several major technology domains:
		- 1. Relational Databases (SQL)
		- In database theory, a **tuple represents a single row (or record)** in a table. Each attribute in the row corresponds to a specific column field.
			- **Example:** In a `Users` table, the tuple `(1042, "Alice Smith", "alice@email.com")` represents a distinct user entity.
		- 2. Functional and General Programming
		- Languages like Python, Rust, TypeScript, and Haskell use tuples for lightweight data grouping without the overhead of creating a formal class.
			- **Multi-value returns:** Allowing a function to return multiple distinct pieces of data at once.
			- **Dictionary keys:** Because they are immutable and hashable, tuples can be used as keys in Python dictionaries (unlike lists).
		- 3. Mathematics and Coordinate Systems
		- Graphics engines, physics simulations, and mapping software rely on tuples to represent fixed mathematical structures. [[1](https://www.h2kinfosys.com/blog/top-python-data-structures-explained-with-real-world-examples/)]
			- **2D/3D Coordinates:** Representing pixels or spatial positions as `(x, y)` or `(x, y, z)`.
			- **Color Models:** Storing color data like RGB `(255, 128, 0)` or RGBA `(255, 128, 0, 0.5)`.
		- 4. Data Science and Machine Learning
		- Tuples handle data shapes and structure metadata that must remain constant during model training.
			- **Tensor Shapes:** Describing image dimensions in deep learning (e.g., a shape tuple of `(batch_size, channels, height, width)`).
			- **Data Splitting:** Returning train/test splits as `(X_train, X_test, y_train, y_test)`.
		- 5. Network Routing and Systems
		- Operating systems and network stacks pack fixed network configurations into tuples.
			- **Socket Pairs:** A network connection is uniquely defined by a 4-tuple: `(Source IP, Source Port, Destination IP, Destination Port)`.
		- ---
	- ## Creation
		- How to create tuples in python? #card
		  id:: 6a82e5db-c41a-459c-beba-928e797b4e47
			- using constructor tuple() or just `()`
			- t = ( 1,2) or t=(1,) for a single element. Having a comma is important
		- What exactly defines a tuple in python? #card
		  id:: 6a85e4ce-ffc0-4e08-bf14-1524e6b6a786
			- Although the tuple is defined as `(1,2)` it not the parenthesis that makes it a tuple. It is the comma. So just having `1,2` still makes it a tuple
			- if you define `t = (1)` as a single element tuple; it will not work. It will return an integer in this case. `1,` will make a single element tuple
			- However, for an empty tuple `()` can be used. Better is to use the tuple() constructor
	- ## Indexing
		- Can tuples in python be indexed? How to index tuples in python? #card
		  id:: 6a82e6bb-8d30-4ff9-ac27-a8e90749f3a0
			- The elements in the tuple can be accessed using the subscripting form the indexing starts from zero like a list
			- ```python
			  >>> t1=(11,22,33,44,55)
			  >>> t1[1]
			  22
			  >>> t1[-1]
			  55
			  ```
	- ## Immutability
		- Ae tuples mutable ? #card
		  id:: 6a82e6fc-da0e-4bc5-9012-d401f9787e71
			- Tuples are immutable. Once created, we cannot change the number of elements
			  – no append, no insert, no remove, no delete.
			  ```python
			  >>> z = (5, 4, 3)
			  >>> z[2] = 0
			  ```
			- Traceback:'tuple' object does not support item Assignment
		- What are some benefits of usage of Tuples: #card
		  id:: 6a58ad2d-139d-4fd6-a7be-c2d5776b5ed5
			- Tuples are faster than lists.
			- If the user wants to protect the data from accidental changes, tuple can be used since they are immutable
			- Tuples can be used as keys in dictionaries, while lists can't.
	- ## Other properties of Tuples
		- Can elements repeat in tuple? #card
		  id:: 6a82e7e6-5ab6-4026-96e2-44ca99be1b49
			- yes. Elements in the tuple can repeat .
			  `>>> t1=(11,22,33,44,22,11,55)`
			- Tuple is a sequence . Tuple is also iterable - is eager and not lazy.
			  ```python 
			  t2=(5,10,15,20)
			  for i in t2:
			  print(i, end=' ‘)
			  ```
		-
		-
		- Give an example of nested tuples? #card
		  id:: 6a58ad2d-60fa-4411-84b4-5891b68b1084
			- Tuples can be nested. We can have tuple of tuples.
			  ```python
			  t=(1,2,3,4,(6,7,8))
			  for i in t:
			  print(i)
			  ```
		- What does assignment of one tuple to another cause? #card
		  id:: 6a82e83b-b056-4041-9101-d5c27f6f243e
			- Assignment of one tuple to another causes both to refer to the same tuple.
			- ```python
			  >>> t1 = (11, 22, 33, 44, 22, 11, 55)
			  >>> t2=t1
			  >>> print(id(t1))
			  2397027797408
			  >>> print(id(t2))
			  2397027797408
			  ```
		- Can tuples can be sliced. What does it return? #card
		  id:: 6a58ad2d-c157-4798-afb6-a828b95ec7a1
			- Yes, they can be sliced. This creates a new tuple.
			- ```python
			  t1 = (11, 22, 33, 44, 22, 11, 55)
			  >>> t1[2:5]
			  (33, 44, 22)
			  >>> t1[::-1]
			  (55, 11, 22, 44, 33, 22, 11)
			  ```
	- ## Tuple Builtin functions
		- Explain how to use the len, min ,max and sorted methods on tuples with examples? #card
		  id:: 6a82e897-c0e4-4c77-9d43-8de04ee17dd6
			- len(tup) - Gives the total length of the tuple.
			- sorted() - Takes elements in the tuple and returns a new sorted list. It should benoted that, sorted () does not make any changes to the original tuple
			- min() - min element in the tuple. Similarly the max
			- sum - the sum of the elements in the tuple
		- How to convert a sequence object into a tuple? Give examples of some sequence types in python? #card
		  id:: 6a82e8ba-5524-4219-809a-59f829b7e564
			- tuple(seq) - Convert sequence into tuple
		- How to count the number an item repeats in a tuple? #card
		  id:: 6a82e8e2-ace9-4e32-9ddd-96012b109f38
			- count() - Returns the count of the items.
				- ```python
				  >>> tuple1 =
				  (10,20,30,10,40,10,50)
				  >>> tuple1.count(10)
				  3
				  >>> tuple1.count(90)
				  0
				  ```
		- How to get the index of first occurance of an element in a set? #card
		  id:: 6a58ad2d-096b-40be-9d9f-e1cd43da6f49
			- index() - Returns the index of the item specified
			- ```python
			  >>> tuple1 = (10,20,30,40,50)
			  >>> tuple1.index(30)
			  2
			  >>> tuple1.index(90)
			  ValueError: tuple.index(x): x not
			  in tuple.
			  ```
	-