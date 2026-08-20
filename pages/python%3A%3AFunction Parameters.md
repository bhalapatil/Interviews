- What is the difference between argument and a parameter? #card
  id:: 6a858d2e-3adb-4447-861a-cea0024dc809
	- this is mostly semantic. In the below example the a , b are called the parameter of the function and the x and y are called the arguments of the function
	- parameters are used during the function definition and the arguments are used while calling the functions
	- ```python
	  def my_func(a, b): #parameters of the function
	    # code here
	    
	  x = 20
	  y = 'str'
	  my_func( x, y)
	  ```
- What are positional and keyword arguments in function? #card
  id:: 6a858e4d-6a82-412e-9aad-d5713cdcf4bf
	- Most common way of assigning arguments to parameters is using the position or the order. Such parameters are called the positional arguments
	-
- How to specify a default value for a parameter? #card
  id:: 6a858f22-d660-4452-b0c8-c3bf62e003aa
	- The default value is specified by providing the value while defining the function.
	- Once a default value is defined it becomes an optional parameter. In other words you can pass a value other than the default value if needed. Else the default value is used
	- ```python
	  def my_func(a , b = 100):
	    # code
	    
	  #calls
	  my_func(20,250)
	  my_func(10) #a = 10 and b = 100 (default value)
	  ```
- Is this valid code? If not how to fix it? What is the rule?
  id:: 6a858fcc-98e6-45d4-aa1d-0f367e999fca
  ```python
  def my_func(a, b = 10,c):
  ```
  #card
	- the function will not compile. The rule is that is positional argument is given a default value, every positional argument coming after that must be provided a default value
	  ```python
	  def my_func(a , b = 10 , c = "abc"):
	    #code
	  
	   
	  ```
	- If needed the default value can be none. Alternatively, the parameter c can be placed after a and before b
- With the function definition below, how can you pass a = 125 and c ="PES"
  id:: 6a859148-afdb-4032-bf04-c0df2cc400c1
  ```python
  def my_func(a , b = 10 , c = "abc"):
    #code
  ```
  #card
	- This can be done by using the keyword arguments, also called named arguments
	- ```python
	  my_func(a=125, c ="PES") #b will be assigned a default value
	  or 
	  my_func(125,c ="PES") # a combination or position ond keyword arguments
	  ```
	- Once you use a named argument, all arguments thereafter must be named too
	- You can start with positional arguments and then specify the named arguments
	-