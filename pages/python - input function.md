- function name - `input([prompt] =None, /)`. The prompt parameter is optional
- Can also be used to display the message to the user using the prompt field and then displays the cursor to the user to take some input from the user.
- Type conversion functions must be used if required. – int(), float(), bool(), complex(), etc
- If multiple values are in the input, use the delimiter while splitting using split()
- By default the datatype of the return of the input will be string
- Examples:
	- ```python
	  >>> length = input("Enter the length in cm: ")
	  Enter the length in cm: 10 #10 is entered by the user
	  >>> type(length)
	  <class 'str'>
	  >>> length=int(length)
	  >>> type(length)
	  <class 'int'>
	  ```
	- using the split on the input
	- ```python
	  >>> marks = input("Enter maths and science marks: ")
	  Enter maths and science marks: 95 99
	  >>> type(marks)
	  <class 'str'>
	  >>> marks = marks.split()
	  >>> type(marks)
	  <class 'list'>
	  >>> marks
	  ['95', '99']
	  ```