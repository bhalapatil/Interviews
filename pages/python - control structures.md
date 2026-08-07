# Indentation in python
	- One fairly unique aspect of Python is that the amount of indentation of each program line is significant.
	- In most programming languages, indentation has no affect on program logic—it is simply used to align program lines to aid readability.
	- In Python, however, indentation is used to associate and group statements.
- # If-elif-else
	- ```python
	  age = 20
	  if age > 0 and age < 18:
	    print("Student")
	  elif age > 18 and age < 60:
	    print("Working professional")
	  else:
	    print("Retired")
	  ```
- # for and while
	- Used for iterative control
	- For a looping for a set of numbers range(start, end , increment) is used
	- ```python
	  for i in range(0,10,2):
	    print(i)
	  ```
	- ```python
	  i = 0
	  while i < 10:
	    print(i)
	    i += 1
	  ```
	- Infinite loop
	- ```python
	  while True:
	    //do something
	  ```
- # range function
	- range( start , stop , step )
	- It returns a range object that produces a sequence of integers from start(inclusive) to stop(exclusive) by step.
	- For example, range(0,4) produces 0,1,2,3
	- range(i, j) produces i, i+1, i+2, ..., j-1.
	- When step is given, it specifies the increment (or decrement).
	- It is a Lazy function - The values come into existence only when we explicitly ask for it.
- # for loop over collections
	- Iterative control- for loop:
		- Python has a statement that works exclusively on collections.
		- examines each element and performs any action set by the programmer until there are no more elements left in the collection.
		- for statement is a looping structure
		- The number of times we execute the body or the suite is normally determinable
		  Semantics of for :
		  1. Start the iteration(walking through) of the iterable.
		  2. Get the element to the variable.
		  3. Execute the suite or the body.
		  4. Repeat steps 2 and 3 until the iterable signals that it has no more elements.
		  5. Move to the next statement and exit the for loop.
-