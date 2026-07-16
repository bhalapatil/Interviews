# Tuples and its operations
	- ## Creation
		- using constructor tuple() or just `()`
		- t = ( 1,2) or t=(1,) for a single element. Having a comma is important
	- ## Indexing
		- The elements in the tuple can be accessed using the subscripting form
		- the indexing starts from zero like a list
		- ```python
		  >>> t1=(11,22,33,44,55)
		  >>> t1[1]
		  22
		  >>> t1[-1]
		  55
		  ```
	- ## Immutability
		- Tuples are immutable. Once created, we cannot change the number of elements
		  – no append, no insert, no remove, no delete.
		  ```python
		  >>> z = (5, 4, 3)
		  >>> z[2] = 0
		  ```
		- Traceback:'tuple' object does not support item
		  Assignment
	- Benefits of usage of type - Tuple:
	  • Tuples are faster than lists.
	  • If the user wants to protect the data from accidental changes, tuple can be used.
	  • Tuples can be used as keys in dictionaries, while lists can't.
	- ## Other properties of Tuples
		- • Elements in the tuple can repeat .
		  `>>> t1=(11,22,33,44,22,11,55)`
		- • Tuple is a sequence .
		  • Tuple is also iterable - is eager and not lazy.
		  ```python 
		  t2=(5,10,15,20)
		  for i in t2:
		  print(i, end=' ‘)
		  ```
		-
		-
		- • Tuples can be nested. We can have tuple of tuples.
		  ```python
		  t=(1,2,3,4,(6,7,8))
		  for i in t:
		  print(i)
		  ```
		- • Assignment of one tuple to another causes both to refer to the same tuple.
		- ```python
		  >>> t1 = (11, 22, 33, 44, 22, 11, 55)
		  >>> t2=t1
		  >>> print(id(t1))
		  2397027797408
		  >>> print(id(t2))
		  2397027797408
		  ```
		- tuples can be sliced. This creates a new tuple.
		- ```python
		  t1 = (11, 22, 33, 44, 22, 11, 55)
		  >>> t1[2:5]
		  (33, 44, 22)
		  >>> t1[::-1]
		  (55, 11, 22, 44, 33, 22, 11)
		  ```
	- ## Tuple Builtin functions
		- len(tup) - Gives the total length of the tuple.
		- sorted() - Takes elements in the tuple and returns a new sorted list. It should benoted that, sorted () does not make any changes to the original tuple
		- min() - min element in the tuple. Similarly the max
		- sum - the sum of the elements in the tuple
		- tuple(seq) - Convert sequence into tuple
		- count() - Returns the count of the items.
			- ```python
			  >>> tuple1 =
			  (10,20,30,10,40,10,50)
			  >>> tuple1.count(10)
			  3
			  >>> tuple1.count(90)
			  0
			  ```
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