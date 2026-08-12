- A set is an unordered collection of Unique elements with zero or more elements present with the following attributes
- In Python sets are written with curly braces. Constructor set() is used to create an empty set
- ```python
  Empty_set=set() # Use the constructor set().
  • fruitset = { “apple”, “orange”, “kiwi”, “banana”, “cherry”}
  • set1 = {(1, 'a', 'hi'), 2, 'hello', 5.56, 3+5j, True}
  ```
- Mutable: Modifiable
- Unordered – Order of elements in a set need not be same as the order in which we add
  or delete elements to/from the set.
  • Iterable – A container object capable of returning its members one at a time. Set is
  eager and not lazy.
  • Not indexable - Cannot access items in a set by referring to an index, since sets are
  unordered in nature.
  • Check for membership using the in operator is faster in case of a set compared to a list,
  a tuple or a string.
- Set is mutable - in the sense that the elements can be added or remove, but the elements within the set must be immutable or hashable
-
- Sets are used to :
  o Remove the duplicate elements, inturn allowing us to find the unique elements.
  o Compare two iterables for common elements or difference.
-
- # Characteristics of sets
- Elements are unique – does not support repeated elements.
  • Elements should be hashable.
  • Hashing is a mechanism to convert the given element into an integer.
  • An object is hashable if it has a hash value which never changes during its
  lifetime (it needs a __hash__() method).
  Examples of hashable objects:
  • int, float, complex, bool, string, tuple, range, frozenset, bytes, decimal.
  Examples of Unhashable objects:
  • list, dict, set, bytearray
- ```python
  #set1={ [ 1, 'a', 'hi' ], 2, 'hello', {3, 4.5, 'how r u' } }
  #TypeError: unhashable type: 'list’
  #set2={ ( 1, 'a', 'hi' ), 2, 'hello', {1:'hi', 2:'hello', 3:'how r u'} }
  #TypeError: unhashable type: 'dict’
  Examples
  set3={ ( 1, 'a', 'hi' ), 2, 'hello', 5.56, 3+5j, True }
  print(set3)
  #{True, (1, 'a', 'hi'), 2, 5.56, (3+5j), 'hello’}
  my_dict = {'name': 'John', tuple([1,2,3]):'values’}
  print(my_dict)
  #{'name': 'John', (1, 2, 3): 'values'}
  ```
- # common methods of sets
	- There are number of functions built into Python that takes set as the
	  arguments.
	  • len()
	  • sum()
	  • sorted()
	  • max()
	  • min()
	  Note: Check reversed()
- The dir() function returns all properties and methods of the specified object.
	- ```python
	  >>> dir(set)
	  o ['__and__', '__class__', '__class_getitem__', '__contains__', '__delattr__',
	  '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__',
	  '__getstate__', '__gt__', '__hash__', '__iand__', '__init__',
	  '__init_subclass__', '__ior__', '__isub__', '__iter__', '__ixor__', '__le__',
	  Specific methods of Set
	  PYTHON FOR COMPUTATIONAL PROBLEM SOLVING
	  '__len__', '__lt__', '__ne__', '__new__', '__or__', '__rand__', '__reduce__',
	  '__reduce_ex__', '__repr__', '__ror__', '__rsub__', '__rxor__', '__setattr__',
	  '__sizeof__', '__str__', '__sub__', '__subclasshook__', '__xor__', 'add',
	  'clear', 'copy', 'difference', 'difference_update', 'discard', 'intersection',
	  'intersection_update', 'isdisjoint', 'issubset', 'issuperset', 'pop', 'remove',
	  'symmetric_difference', 'symmetric_difference_update', 'union', 'update']
	  ```
- # Methods in detail
	- ![image.png](../assets/image_1786519437686_0.png)
	- ![image.png](../assets/image_1786519459031_0.png)
	-
	- Concatenation (|=) operator can be used to combine two sets together, results
	  in a set that contains items of the two sets.
	- ```python
	  >>> s1={1,2.34,(34,22),"python"} >>> s2={10,3.22,"programming"}
	  >>> s1|=s2
	  >>> s1
	  {1, 2.34, 'python', (34, 22), 3.22, 'programming', 10}
	  ```
	- Repetition operator(*) – Throws an error as set has unique elements.
	- ```python
	  >>> s1={1,2,3,4,5,6}
	  >>> print(s1*3)
	  Traceback (most recent call last):
	  File "<stdin>", line 1, in <module>
	  TypeError: unsupported operand type(s) for *: 'set' and 'int’
	  ```
- # Membership operator
	- Membership operator(in) – returns True if a sequence with the specified value is present in the set otherwise False.
	- ```python
	  >>> s1={1,2,3,4,5,6}
	  >>> print(1 in s1)
	  True
	  >>> print('a' in s1)
	  False
	  ```
- # union
- union()- Return the union of sets as a new set. (i.e. all elements that are in either set.) .
- ```python
  >>> s1={1,2,3,4,5,6}
  >>> s2={6,5,7,8,9,10}
  >>> print(s1.union(s2)) 
  {1, 2, 3, 4, 5, 6, 7, 8, 9, 10} 
  >>> print(s1|s2)
  {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
  ```
- # Intersection
- intersection()- Return the intersection of sets as a new set. (i.e. all elements that are in both sets.) .
- ```python
  >>> s1={1,2,3,4,5,6}
  >>> s2={6,5,7,8,9,10}
  >>> print(s1.intersection(s2))
  {5, 6}
  
  or
  >>> print(s1&s2)
  {5, 6}
  
  ```
- # difference
- difference()- Return the difference of two or more sets as a new set.
- ```python
  >>> s1={1,2,3,4,5,6}
  >>> s2={6,5,7,8,9,10}
  >>> print(s1.difference(s2))
  {1, 2, 3, 4}
  >>> print(s1-s2)
   {1, 2, 3, 4}
  ```
- # add
- adds an element in a container set.
-
- ```python
  s1 = {1,2,3,4}
  s1.add(7)
  
  ```
- # symmetric difference
- Return a set with the symmetric differences of two sets.
- ```python
  s1= {1,2,3,4,5 ,6}
  s2 = { 6,5,7,8,9}
  prin(s1.symmetric_difference(s2))
  ```
- # remove
- Removes the specified item in a set. If the item to remove does not exist, remove() will raise an error.
-
- # discard
- Removes the specified item in a set. If the item to remove does not exist, discard() will NOT raise an error.
- ```python
  s1.discard(7)
  ```
- # pop
- Removes an item in a set. Sets are unordered, so when using the pop() method, doesn’t know which item that gets removed.
- ```python
  s1.pop()
  ```
- # update
- update()- updates the current set, by adding items from another set (or any other iterable). If the element is present in both the sets, only one appearance of element present in updated set
- ```python
  >>> s1={120,12,23}
  >>> s1.update([22,15,67,"pes"])
  >>> s1
  
  
  {67, 12, 15, 22, 23, 120, 'pes’}
  ```
- # intersection update
- intersection_update()- Removes the items that is not present in both sets.
- ```pyhon
  >>> set1={"apple", "banana", "cherry"}
  >>> set2={"google", "microsoft", "apple"}
  >>> set1.intersection_update(set2)
  >>> set1
  {'apple'}
  ```
- # difference_update
- Updates the original set by removing items that are present in both sets, and inserting the other items.
- ```python
  >>> set1={"apple", "banana", "cherry"}
  >>> set2={"google", "microsoft", "apple"}
  >>> set1.symmetric_difference_update(set2)
  >>> set1
  {'microsoft', 'google', 'banana', 'cherry'}
  ```
- # issubset
- Returns True if all items in set ‘x’ are present in set ‘y’.
- ```python
  >>> x = {"a", "b", "c"}
  >>> y = {"f", "e", "d", "c", "b", "a"}
  >>> x.issubset(y)
  True
  >>> y.issubset(x)
  False
  ```
- # issuperset
- Returns True if all items in set ‘y’ are present in set ‘x’.
- ```python
  >>> x = {"f", "e", "d", "c", "b", "a"}
  >>> y = {"a", "b", "c"}
  >>> x.issuperset(y)
  True
  >>> y.issuperset(x)
  False
  ```
- # isdisjoint
- ```python
  >>> s1={1,2,5}
  >>> s2={11,22,55}
  >>> s1.isdisjoint(s2)
  True
  ```
- # clear
- clear()- Removes all the elements in a set.
- ```python
  >>> x = {"f", "e", "d", "c", "b", "a"}
  >>> x.clear()
  >>> x
  set()
  ```
- # Example
- Program to check whether a set is emprty or not
	- option 1: check if the len(s1) == 0 where s1i is a set
	- option2: since empty data structure is False; below can be writte
	- ```python
	  s1 = set()
	  if(s1):
	    print("Set is empty")
	  else:
	    print("not empty")
	    
	  ```