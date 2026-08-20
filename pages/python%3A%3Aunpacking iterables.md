- What are packed value? #card
	- Packed values refers to values that are bundled together in some way
	- Example are Tuples and Lists. Even string is considered as packed values
	- Sets and dictionary is considered a packed value
	- Any iterable is considered a packed value. So when we are unpacking a packed value we are unpacking an iterable
- What does it mean to unpack a packed value? #card
	- Unpacking is the act of splitting packed values into individual variables contained in a list or tuple
	- The unpacking into variables happens by the position
	- Ex  `a,b,c= [1,2,3]` unpacks a = 1 , b -= 2 and c=3 based on the position
	- similarly for the tuples and strings `a,b,c ='XYZ` means a = X and so on
- How to swap two variables in python without using a temporary variable? #card
	- This can be done using the unpacking ` a , b = b, a `
	- In python the RHS is evaluated completely first before the assignment. With that can you explain how this is working internally ?
- Can you unpack dictionaries? What will this code return? 
  ```python
  d = { 'key1' : 1 , 'key2' : 2 , 'key3' : 3}
  a , b ,c = d
  ```
	- the unpacking is similar to using the for loops. ` for e in d` . This will have e iterate through the keys of the dict and not the key value pairs. So the a, b and c will get the keys. However, since the dictionary are unordered there is no guarantee to say that a will be key1 or key2 or key3. It could be any of them
	- Given the limitation above dictionaries are rarely unpacked using this methodology
	- Similarly with the sets
- What is the * operator in the extended unpacking of the iterables? #card
	- While unpacking the iterabls the * operator can be used to collect the remaining items that are unmapped into a list. For Ex
	- `a , *b = [ 1,2,3,4,5]  ` this means that a will be 1 and the rest will be unpacked into a list `b=[2.3.4.5]`
	- `a ,*b ,c = [ 1,2,3,4,5]` means a = 1 c = 5 and the rest are collected as a list b = [ 2,3,4]
	- this works with any iterable
	- Note that the * operator can only be used on on the LHS
- Can the * operator be used on the RHS of the assignment? #card
	- Yes. It helps in unpacking the elements. In the example below the two lists L1 and L2 are unpacked and a new list is created
	- ```python
	  l1 = [ 1,2,3]
	  l2 = [ 3, 4, 5]
	  l = [*l1 , *l2] # l= [1,2,3,4,5]
	  ```
	- this works with any iterable
- What do you get if you use the * operator to unpack over a dictionary? #card
	- When the * operator is used over the dictionary it returns the keys. The ordering is not guarenteed
	- ```python
	  d = {'one': 1 , 'two':2 , 'three':3}
	  x , y , z = *d
	  # x could be one or two or three as the ordering is not guarenteed
	  ```
- How to unpack the key-value pairs from a dictionary? #card
	- By using the ** operator
	- ```python
	  d1 = {'one': 1 , 'two':2 , 'three':3}
	  d2 = {'four': 4 , 'five':5}
	  d = { **d1, **d2}
	  
	  ```
	- This creates a new dictionary with the key value pairs from both the dictionary. If the keys are repeating then the second value in the order is taken
	- The ** operator can only be used in the RHS. It cannot be used in the LHS
- How to use the ** operator to build a dictionary literal? #card
	- You can place the ** operator anywhere while building a string literal
	- ```python
	  d = { 'a' : 10. 'b' : 20 , **d1}
	  ```
	- This will unpack the d1 into the dictionary d. Order is not guaranteed
	-
- What is nested unpacking and show how to use it using some examples? #card
	- ```python
	  l = [ 1,2,[3,4]]
	  a,b,(c,d) = l #a = 1, b = 2 , c= 3 and d = 4
	  ```
- What are the *args used in the function arguments? #card
	- the *args is used specify a unknown number of positional arguments.  Ex in the code below a = 10 , b = -1 and c will be tuple (25,35)
	- ```python
	  def fun1(a , b , *c):
	  	#code
	  If this is called with the below parameters
	  fun1(10,-1,25,35) then you will get a = 10 , b = -1 and c is a tuple (25,35)
	  
	  ```
	- Note that you can pass as many arguments as needed for the call to the fun1. Such a concept is called variadic arugment.
	- See the definition of the print function. It uses the variadic arguments concept
- You have a function that takes three paameters. How can pass a list with three values as an argument? #card
	- You can unpack the list (iterable unpacking) and then pass the arguments
	- ```python
	  def fun1(a, b, c):
	    #code
	   l = [ 1,2,3]
	  fun1(*l) #This will unpack the l first and then assign the values to a , b and c
	  ```
- In the function definition below, how can you specify the value for d as the *args will consume all the positional arugments?
  ```python
  def func(a , b, *args, d):
    #code
  ```
  #card
	- By using the keyword arugments
	  ```python
	  func(10,20,40,50,d="str")
	  ```
- What is the use of the **kwargs ?
	- This is used to collect a variable number of keyword arguments and is stored as a dictionary. The parameter name is arbitrary but it is customary to call it kwargs
	- The **kwargs can be specified even if the positional arguments have not been exhausted
	- Note that no parameters can be specified after the **kwargs is specified
	- ```python
	  def func(a , *args , c , **kwargs):
	    #code
	    
	  func(10,30,50,c=100 , d= 40 , e = 50)
	  # the kwargs = { 'd':40,'e':50} . The remaining keyword arguments are collected
	  
	  ```
-