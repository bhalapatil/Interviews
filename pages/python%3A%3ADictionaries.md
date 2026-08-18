# Dictionary
- What is a dictionary? #card
  id:: 6a7eb900-4812-4f4e-bf93-1932a70b227a
	- Dictionary is a data structure that organizes data into key and value pairs
	- Every value has a certain unique key mapped to it
	-
- Are dictionaries mutable? #card
  id:: 6a7eb917-9a90-4a45-833b-5b0ce18ae2b2
	- It is mutable (values can be changed after creation)
-
- # Dictionary creation
- Give examples of how to create an empty dictionary and dictionary with entries? #card
  id:: 6a7eb948-00fd-417a-b45a-8058d2c2d0ac
	- ```python
	  >>> phonebook={} # Creation of empty dictionary
	  >>> phonebook={"Johan":938477565} # Dictionary with one key-value pair
	  >>> phonebook={"Johan":938477565,"Jill":938547565} # Dictionary with two key-value pair
	  ```
	- To access values in the dictionary, we use the key
	- ```python
	  phonebook={"Johan":938477565,"Jill":938547565} # Dictionary with two key-value pair
	  phonebook['Jill'] # his will give the phone number of Jill
	  ```
- The key in the dictionary can be of any immutable type? Explain why? #card
  id:: 6a7eb988-cd3a-45b8-81ec-d699bce65077
	- Each key is of any immutable type associated with a single value. The keys are hashed and the hash value is used to store the corresponding values
	- If the keys are allowed to be mutable, then the association between the key and the value  can be easily broken leading to unpredictable behavior
	- ```python
	  >>> d={1:"one",2:"two",3:"three",4:"four"}
	  >>> d1={[1,2]:"hello"}
	  Traceback (most recent call last): File "<stdin>", line 1, in
	  <module> TypeError: unhashable type: 'list'
	  ```
- Can you have a list as a key in python dictionary? #card
  id:: 6a7eba11-a743-4604-85aa-45844ae767da
	- No, since the list is a mutable type
- Can you have a tuple as a key in python dictionary? #card
  id:: 6a7eba23-a0ec-4266-8307-7ca09763411b
	- Yes, since the tuples are immutable
- Are there any restriction on dictionary values in a python dictionary? #card
  id:: 6a7eba5e-ba3d-4d9b-859e-6a29c00735d7
	- No restrictions. The values can be of any type.
	- ```python
	  >>> d={1:"one", 2:[23,33] , 3:"three", 4:"four"}
	  ```
- Can you overwrite a value for a key in python dictionary? #card
  id:: 6a7eba9e-109f-485a-a06c-03e615354ad0
	- Yes the value for a key can be overwritten.
	- If you assign a value to a key, then later in the same dictionary have the same key assigned to a new value, the previous value will be overwritten.
	- ```python
	  >>> d={1:"one",2:"two",3:"three"}
	  >>> d={1:"one",2:"two",3:"three",1:"five"}
	  >>> d
	  {1: 'five', 2: 'two', 3: 'three'}
	  ```
- Are the key-value pairs in python dictionary ordered? #card
  id:: 6a7ebaee-11e0-4026-a560-3325e20415d3
	- The items (key-value pair) in dictionary are unordered, which means that the order isn’t decided by the programmer but rather the interpreter. The ordering is based on a concept called “hashing” .
	- ```python
	  >>> d={'w':11,'a':33,'e':44}
	  >>> f= {'e':44,'w':11,'a':33}
	  >>> print(d==f)
	  True
	  ```
- # Common operations on dictionaries
	- What are some of the common operators on the dictionary? #card
	  id:: 6a7ebb60-2e67-4833-81b4-69800051961c
		- len() , min() , max()
		  Note: Dictionaries do not support ‘+’ and ‘*’ operations
	- How to get the number of elements in a dictionary? #card
	  id:: 6a7ebb75-56c4-48dd-bd45-38200b205c0f
		- using the len(dict) function
	- What does the min on a python dictionary return? #card
	  id:: 6a7ebb8d-c347-4d90-8bc5-ad736a2f2626
		- To be completed
	- What does the max on a python dictionary return? #card
	  id:: 6a7ebba9-8d3e-4aa1-a8c5-862e6fe998bc
		- To be completed
	- What does the get function on the python dictionary return? #card
	  id:: 6a7ebbc5-0497-4bab-818f-e98705315f3f
		- get(): returns the value for a given key, if present. Else returns None
		- ```python
		  >>> print(phonebook.get('Jill’))
		  938547565
		  ```
	- How to get a value for a key in python dictionary if present else get a default value? #card
	  id:: 6a7ebbef-8247-4221-bce8-94267ab73ffd
		- using the get function. `dict.get(key,default_value)` . If the default value is not specified None is returned.
	- What does the items function on the python dictionary return? #card
	  id:: 6a7ebc7a-3949-4463-bc5d-0134bbc0b890
		- A list containing tuples with each tuple containing the key and the value
		  D.items() -> a set-like object providing a view on D’s items.
		- ```python
		  >>> phonebook.items()
		  dict_items([('Johan', 938477565), ('Jill', 938547565)])
		  ```
	- How to get the set of keys in python dictionary? #card
	  id:: 6a7ebcb4-b4bd-46a8-a58e-c6e31e6c7791
		- Using the keys function
		- ```python
		  >>> phonebook.keys()
		  dict_keys(['Johan', 'Jill’])
		  ```
	- How to remove an element from python dictionary? #card
	  id:: 6a7ebce9-056e-4985-bb38-33e9dfa3023d
		- using the pop(...) fucntion. D.pop(key) -> v, remove specified key and return the corresponding value. If key is not found, otherwise KeyError is raised.
		  ```python
		  >>> phonebook.pop(‘Jill’)
		  938547565
		  ```
	- How to remove an item from the python dictionary? #card
	  id:: 6a7ebd20-2dc2-4020-8508-6cf0a074d7b8
		- using the popitem function
		- popitem(...) D.popitem() -> (k, v); remove and return some (key, value) pair as a 2-tuple, but raise KeyError if D is empty.
		- ```python
		  >>> person = {'name': 'Phill', 'age': 22, 'salary': 3500.0}
		  >>> result = person.popitem()
		  >>> print('Return Value = ', result)
		  Return Value = ('salary', 3500.0)
		  >>> print('person = ', person)
		  person = {'name': 'Phill', 'age': 22}
		  ```
	- What does the setdefault function do on the python dictionary? #card
	  id:: 6a7ebd4f-0f69-47fd-b3af-e4026de1ea06
		- setdefault(...) D.setdefault(key,value) -> if the key is in the dictionary, returns its value. If the key is not present, insert the key with a specified value and returns that same value.
		- ```python
		  >>> person = {'name': 'Phil', 'age': 22}
		  >>> phone = person.setdefault(‘phone’, 90909090)
		  >>> print('person = ',person)
		  >>> print(‘phone = ‘,phone)
		  ```
		- Output:
		  person = {‘name’: ‘Phil’, ‘age’: 22, ‘phone’: 90909090}
		  phone = 90909090
	- What does the update function do on the python dictionary? #card
	  id:: 6a7da7a6-30a1-4d6e-9b30-1768c285886a
		- update(...) D.update() -> updates content of D with key-value pairs from a dictionary/iterable that it is given
		- ```python
		  >>> marks = {'Physics':67, 'Maths':87}
		  >>> internal_marks = {'Practical':48}
		  >>> marks.update( [(‘Chemistry’, 90), (‘Python’, 100)] )
		  >>> marks.update(internal_marks)
		  >>> print(marks)
		  {'Physics': 67, 'Maths': 87, ‘Chemistry’: 90, ‘Python’: 100, 'Practical': 48}
		  ```
	- How to get the list of values in a python dictionary? #card
	  id:: 6a7ebda7-5fa1-44d2-a683-280def23210a
		- values(...) D.values() -> returns a view object that displays a list of all the values in the dictionary.
		- ```python
		  >>> marks = {'Physics':67, 'Maths':87}
		  >>> print(marks.values())
		  dict_values([67, 87])
		  ```
- ## Use of for and while loops for dictionary
	- Give examples of using iterators over python dictionary ? #card
	  id:: 6a7ebb27-3433-4fbc-a97e-670b4668b6b8
		- ```python
		  dict = {'a': 'pencil', 'b': ‘eraser', 'c': 'sharpner’}
		  for key, value in dict.items():
		  	print(key, value)
		      
		  dict = {'a': 'juice', 'b': 'grill', 'c': 'corn’}
		  for key in dict:
		  	print(key, dict[key])
		  ```
		- while loop
			- ```python
			  books={"learning python": "Mark Lutz", "think python": "Allen B. Downey", "Fluent Python": "Luciano Ramalho"}
			  key=list(books) #converts keys into a list
			  i=0
			  while i<len(key):
			  	print(key[i],":",books[key[i]])
			  	i+=1
			  ```