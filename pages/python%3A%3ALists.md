# List characteristics
	- Should the elements in the always be homogenous? #card
	  id:: 6a7eb149-05de-432b-8456-e50c8b126901
		- Elements in the list can be heterogeneous (different datatypes) or homogeneous
	- How to access elements in a list? #card
	  id:: 6a7eb172-c8f4-441c-84b2-49018dc41f65
		- Elements are accessed using indexing operation (also called subscript notation).
	- Are list mutable or unmutable? #card
	  id:: 6a7eb18a-f637-4291-863a-f042b2dc90d9
		- Lists are mutable, as it can grow and shrink
	-
	- Assignment of one list to another causes both to refer to the same list.
	- List can be sliced. This creates a new (sub)list.
	- ```python
	  >>> numbers=[55,88,45,12]
	  >>> numbers[0]=10 # index operation is used.
	  >>> numbers
	  [10, 88, 45, 12]
	  ```
- How to iterate over list? Give example using for loop and while loop? #card
  id:: 6a7da7a6-538e-4b48-9758-f21b0fce4850
	- Ex: (i) 
	  ```python
	  numbers=[55,88,45,12]
	  for i in numbers:
	  print(i, end =' ')
	  ```
	- ```python
	  number=[10,20,30,40,50]
	  i=0
	  while(i<len(number)):
	  	print(number[i],end=' ')
	      i=i+1
	  ```
- Give an example of nested lists? Is it possible? #card
  id:: 6a7eb1b2-6180-422b-b9a2-42808fb8809d
	- List can be nested. We can have list of lists.
	  ```python
	   numbers=[55,20,[63,72,33]]
	  for i in numbers:
	  print(i, end =' ')
	  ```
- ![image.png](../assets/image_1786347116728_0.png)
- What are list slices? How to create list slices? Give examples? #card
  id:: 6a7da7a6-258a-41a4-aec2-df4c8317f6c2
	- ```python
	  lst = [10,20,30,40,50]
	  # l[start:end] # the end is not included
	  lst[1:3]
	  # just using the : gives the enntire list
	  lst[:]
	  # skipping the start means from beginning
	  lst[:3]
	  # skipping the end means include till the end
	  lst[2:]
	  
	  ```
- # Creation of list
	- How to declare an empty list? #card
	  id:: 6a7eb271-c368-4e7a-94dd-089194b83961
		- List items are surrounded by square brackets and the elements in the list are separated by commas
		- A list can be empty.
			- ```python
			  lst = []
			  lst = list()
			  ```
- # Builtin functions
	- How to get the number of elements in a list? #card
	  id:: 6a7eb2b2-7e46-4ef5-99f9-b170c1d7ee06
		- using the `len(lst)` function
	- How to get the max of the elements in a list? #card
	  id:: 6a7eb2c8-7aff-4ecc-a6ae-1ccf1ea002f4
		- using the `max(lst)` function
	- How to get the minimum of the elements in a list? #card
	  id:: 6a7eb2e8-3c31-4114-8da7-0541519d71fa
		- using the `min(lst)` function
	- How to get the sum of all the elements in a list? #card
	  id:: 6a7eb305-8032-488e-b596-5d2999631e16
		- using the sum(lst) function
	- How to concatenate two lists and create a new list? #card
	  id:: 6a7eb31f-109e-44c6-9bcf-aa9f8cef3a1b
		- using the concatenate operator. The concatenate is the `+`
		- ```python
		  lst = ls1 + lst2
		  ```
	- How to multiply a list n times and create a new list? #card
	  id:: 6a7eb380-83ad-462a-a3ee-93cd169ca0a2
		- using the * operator.
		- ```python
		  lst = [ 1 ,2 ,3]
		  lst_new = lst * 4 # 
		  ```
	- How to sort elements in a list? #card
	  id:: 6a7eb3ba-7475-4d7b-b993-39cb877183f5
		- using the `lst.sort()` function. Note that this function is defined on the list object
	- How to append elements to the end of the list? #card
	  id:: 6a7eb3e4-4904-4135-874a-47c53948cfce
		- Using the append operator `lst.append(elem)`
	- How to insert an element at a specific position in the list? #card
	  id:: 6a7eb40e-e789-4975-b94e-8d1d3b35036d
		- using the lst.insert(pos,value) function on the list object
	- What does the `lst.extend(iterable)` function do? #card
	  id:: 6a7eb459-ed92-461b-a967-238d2e38fa9c
		- This function takes an object that can be iterated and inserts all the elements from that object to the end of the list object; lst in this case
	- What to return an element at a specific position in the list and also remove it? #card
	  id:: 6a7eb499-9710-4ec8-aaa9-cf53a7c94786
		- using the `lst.pop(index)` will remove the element at the position index and return it
	- How to return an element at the end of the list and also remove it? #card
	  id:: 6a7eb503-9fff-49e4-8f0f-30f65af42bf6
		- using the pop function. When the pop function is called without any index, it returns the last object in the list and also remove it from the list
	- How to get the number of occurances of a value in a list? #card
	  id:: 6a7eb539-b402-4a4b-9baf-7aca95485d44
		- using the `lst.count(value)` method
	- How to get the index of the first value in a list? #card
	  id:: 6a7eb57d-b4a9-4685-a70a-39085c6aa230
		- using the `lst.index(value)` function.
	- |function| when to use it| example|
	  |len(list_name)|to get the number of elements in the list| len(lst)
	  |max(list_name)|to get the max of them elements in the list|max(lst)|
	  |min(list_name)|to get the minimum of elements in the list|min(lst)|
	  |sum(list_name)|to get the sum of elements in the list| sum(lst)|
	  | + (concatenation operator)| We can create a new list by adding two existing lists together.|lstnew = l1 + l2|
	  | * (repetition operator) | Allows for the multiplying of the list n times and create a new list| lstnew = lst*2|
	  |lst.sort| to sort the elements in the list | lst.sort()|
	  |lst.append()| Append elements to the end of the list||
	  |lst.insert(pos,val)| insert val at a specific postion||
	  |lst.extend()|adds the specified list elements (or any iterable) to theend of the current list. | lst.extend([20,25,30]|
	  |lst.pop(index) | remove and return at the value at the index. If no index is specified last element is returned and removed|
	  |lst.count(val)| Returns the number of occurances of value in a list||
	  |lst.index(val)| Returns first index of a value. Raises ValueError is the value is not present||
- # membership
	- How to check if an element is part of the list? #card
	  id:: 6a7eb5f1-d222-41bb-a1ad-817b030818ce
		- using the membership operators. (in and not in)
		- in and not in : in returns true if an item exists in the list. Otherwise false
		- not in is the opposite
		- ```python
		  if elem in lst:
		    print("Element is in the list")
		  else:
		    print("Element is not part of the list")
		  ```
- # Comparison
	- How does the comparison operator work on a list? #card
	  id:: 6a7eb667-1581-4a90-b604-29fe78231b5b
		- It returns true if all the elements in the list1 is in the second element and the length of both the lists is the same
		- We may at times need to compare data items in the two lists to perform certain operations by using == operator.
		- ```python
		  >>> list1 = [10,2.2,(22,33,43]
		  >>> list2=[2,3,4]
		  >>> list1==list2
		  False
		  >>>list1!=list2
		  True
		  ```
- # List using the for loop
	- The for loop in Python is used to iterate over a sequence (list, tuple, string) or other iterable objects.
	- Iterating over a sequence is called traversal.
	- Loop continues until we reach the last item in the sequence
	- The body of for loop is separated from the rest of the code using indentation.
	- ```python
	  for val in lst:
	    print(val)
	  ```
-
- How to use the list as a stack? Which methods are use for doing this? #card
  id:: 6a7da7a6-5fbd-4417-ab58-6036f79e5f41
	- The end of the list can be used as the top of the stack
	- lst.append() method for adding a value to the end of the list. In this case the top of the stack
	- lst.pop() - without the index will pop at the end of the list. In this case the top of the stack
	-
	-