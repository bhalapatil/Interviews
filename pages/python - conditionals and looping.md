- Create a function that takes two integer argument and returns the maximum value ? #card
  id:: 6a2830ab-84dd-4214-a0cb-82b608c7229c
	- ```python
	  def max_value(x , y):
	    if x >= y:
	      return x
	    else:
	      return y
	  ```
- Create a function that takes a list of integers and returns the maximum value? #card
  id:: 6a28310b-866b-4512-b541-735aa09edb3c
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