# Introduction
- function name `print()`
- This function takes any argument and as a part of the processing, displays the value of the argument to the output screen.
- #+BEGIN_IMPORTANT
  1. Can display/print anything in the world.
  2. Has the capability to evaluate the expression.
  3. Can take any type of arguments and any number of arguments.
  4. Formatting is possible to some extent using the keyword separators – sep & end
  #+END_IMPORTANT
- The print function definition
- ```python
  print(...)
  print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
  Prints the values to a stream, or to sys.stdout by default.
  Optional keyword arguments:
  • file: a file-like object (stream); defaults to the current sys.stdout.
  • sep: string inserted between values, default a space.
  • end: string appended after the last value, default a newline.
  • flush: whether to forcibly flush the stream
  ```
- # Exercises
	- print three numbers. What is the separator ? #card
	- print three numbers. Specify the separator to be : in this case #card
	- Why is the below code printing on two separate line? How can you print in the same line with a space between them?
		- Hint: what should you change for the end parameter
		- ```python
		  print("first");print("second")
		  ```
	-