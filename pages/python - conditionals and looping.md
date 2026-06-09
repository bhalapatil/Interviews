- Create a function that takes two integer argument and returns the maximum value ? #card
	- ```python
	  def max_value(x , y):
	    if x >= y:
	      return x
	    else:
	      return y
	  ```
- Create a function that takes a list of integers and returns the maximum value? #card
	- ```python
	  l = [10,8,20,33]
	  def get_max(int_list):
	    m = None
	    for item in int_list:
	      if not m:
	        m = item
	      elif m < item:
	        m = item
	    return m
	  
	      	
	  ```