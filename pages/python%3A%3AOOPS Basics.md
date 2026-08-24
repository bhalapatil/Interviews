- https://github.com/fbaptiste/python-deepdive
- What is a class? #card
  id:: 6a8707a8-689c-4a92-bfa0-084de08ce5c6
	- A class is a methodology to create an entity part of reality, reflecting properties and activities found in the real world
	- A class specifies the set of instance variables and methods (same as functions but inside a type) that are "bundled together" for defined a user defined type
- What is an object? #class
	- An object is an instance of a type/class. Each object has the following
		- A name that uniquely identifies it
		- A set of individual properties which makes it original or unique or outstanding
		- A set of abilities, called method,. to perform specific activities, able to change the state of the object and influence the state of other objects
- How to declare a class? #card
  id:: 6a870ec0-fefa-4497-874d-71a20f6ee2db
	- The class definition has the below structure
	- ```python
	  class class_name:
	    # attributes that capture the information or state of the object
	    # methods or functions associate with this class
	  ```
- In the code below what will be printed and why?
  id:: 6a870fa7-1d26-4ef3-affd-5bc5f0f006ec
  ```python
  class Student:
    name = "Shreyas"
    phone = 888889999
    
  s1 = Student() #create an object of the class
  s2 = Student()
  s3 = Student()
  print(s1.name )
  print(s2.name)
  print(s3.name)
  ```
  #card
	- Each of the print statements will print "Shreyas". This is because each instance of the class will share the same variables. So these are shared variables
- What is the `__init__()` method in a class definition? #card
  id:: 6a871076-25e7-4a5e-8254-fe90c54bb5a3
	- The `__init__` method is the constructor for the class. This method is called when an object of that class is created.
	- Python by default includes this method with a default implementation if this is not provided by the developer
- What is the basic signature for the `__init__` method? Explain the parameters of the same?  Give an example of a class with the method #card
  id:: 6a871107-56fb-4ad6-91c9-fb45b553e4e1
	- The basic definition of the `__init__` method is `def __init__(self):` . In this the self is a reference to the current object that is being created.
	- ```python
	  class Student:
	    def __init__(self):
	      print("constructor called self :", self)
	  ```
- In the code sample below will each of the print statements print the same value for self? Explain ?
  id:: 6a8711ed-562b-4ccb-9ee4-635f720cafb1
  ```python
  class Student:
    def __init__(self):
      print("constructor called self :", self)
      
  s1 = Student()
  s2 = Student()
  s3 = Student()
  ```
   #card
	- Each of the print statements will print different values for the self as the self will print the memory location of the current object being created. See the output below
	- ```
	  s1 = Student()
	  Constructor called  self: <__main__.Student object at 0x000002428AFE4250>
	  s2 = Student()
	  Constructor called  self: <__main__.Student object at 0x000002428B0882D0>
	  s3 = Student()
	  Constructor called  self: <__main__.Student object at 0x000002428AFE1ED0>
	  ```
- What are instance level variables? #card
  id:: 6a87130d-d939-4796-bf47-1d3340c58a1c
	- Instance level variables are used to store unique values for each of the object being created. The variables are created when assigned a value like the normal variables.
	- The typical place to create a the variables is in the `__init__` method although they can be created in any function technically
- I want to create a Student class and assign a student name to each object. How can i do it? #card
  id:: 6a871390-50fa-48f5-b9c9-7454fc331fa6
	- Student name is an instance variable. The ideal method to do this is to define a parameterized contructor or the `__init__` method that takes the name as a parameter and stores it in the object
	- ```python
	  class Student:
	    def __init__(self , name):
	      self.name = name
	      print("constructor called self :", self ," name" , self.name)
	      
	  s1 = Student("Shreyas")
	  s2 = Student("Sourabh")
	  s3 = Student("Joe")
	  ```
	- Note that the name in the function parameter is used to create a instance variable. The instance variable name can also be different or same parameter name
- How do object gets destroyed and the memory reclaimed in python? #card
  id:: 6a871475-bc58-452b-a267-dca2acacb796
	- For every object created in memory Python maintains a count of the references. When a reference is created the count is incremented and when it goes out of scope the count is decremented.
	- When the count of the references goes to zero, a component of the python interpreter called the garbage collector destroys the objects and reclaims the memory allocated to it
- Is there a destructor available in python ? #card
  id:: 6a871553-5234-49cd-bbbd-d332e1d124cb
	- Yes, a destructor method `__del__(self)` is available. If needed this method can be called or the del operator can be used
- What is data encapsulation? #card
  id:: 6a87159d-045c-4354-8de2-b1cfc6d48820
	- Data encapsulation is a principle in which the data of an object is hidden and is not directly exposed to modification. The data for the object is written using set methods and the data is read using the get methods.
	- Many programming languages have explicit support for the data encapsulation using modifiers such as private/public. The modifier are added as part of the instance variable declarations
	- Python does not have explicit support for data encapsulation
- How to declare a variable as a private variable in the class definition? #card
  id:: 6a872b8d-1f1c-4569-941b-086104638720
	- If the variable name starts with two underscores it is treated as private variable
- What is a getter and setter methods? Give an example #card
  id:: 6a872bc4-dfff-4df4-bbcc-bbaf3cfdf8ab
	- A function of the class that returns a value of an instance variable
	- ```python
	  class Student:
	    def __init__(self , name):
	      self.name = name
	      self.__address = None
	      print("constructor called self :", self ," name" , self.name)
	      
	    def set_address(self, address:str):
	      self.__address = address
	      
	    def get_address(self) -> str:
	      return self.__address
	      
	  ```
- What are class level variables? How to reference such variables? #card
  id:: 6a872c65-2a9e-4411-92e9-e6dd929286f3
	- A variable declared in a class without the `self` is a class level variables. The variables are referred using the `<class name>.<variable name>` syntax. Ex
	- ```python
	  class Student:
	    count = 0
	    def __init__(self , name):
	      self.name = name
	      Student.count += 1  #class level variable is referenced
	  ```
- Can the class level variables be accessed using the object instances of that class? #card
  id:: 6a872d67-4367-44a8-9f49-56cf4c192fad
	- Yes. they can be accessed using both the ClassName and the object instances of that class
	- ```python
	  class Student:
	    count = 0
	    def __init__(self , name):
	      self.name = name
	      Student.count += 1  #class level variable is referenced
	  
	  s1 = Student()
	  
	  ```
- Why does the below code fail and how to fix it?
  id:: 6a873a31-86ac-4718-a3d4-ae3b21b4cae0
  ```python
  class Student:
      count = 0
      def display_count():
          print(Student.count)
  
          
  s1= Student()
  s1.display_count()
  Traceback (most recent call last):
    File "<pyshell#22>", line 1, in <module>
      s1.display_count()
  TypeError: Student.display_count() takes 0 positional arguments but 1 was given
  ```
  #card
	- the error is because the display_count function being the class level function needs atleast one parameter self. The self is the reference to the current object
	- to fix this the definition of the display_count needs to be modified as `def display_count(self)`.
	- However, note that the display function is only using class level variables and none of the instance level variables
- What is the `@staticmethod` decorator?
	- The `@staticmethod` decorator means that a function is a static method and only accesses the class level variables and does not use any instance level variables.
	- It also allows us to specify the method without having the `self` as the parameter
	- ```python
	  class Student:
	      count = 0
	      @staticmethod
	      def display_count():
	          print(Student.count)
	  
	  
	  s5 = Student()
	  s5.display_count()
	  0
	      
	  ```