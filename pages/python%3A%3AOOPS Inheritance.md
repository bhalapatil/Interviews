- What is inheritance ? #card
  id:: 6a87c573-3d34-4052-a10a-45b7b6f457d1
	- Obtaining or acquiring the properties of another class is known as Inheritance. It deals with the ability of a class to inherit members of another class as part of its own definition.
- What is a super class and a subclass? #card
  id:: 6a87c6cb-3cd2-4598-8bba-a68e9aa8be9d
	- The inheriting class is called a subclass (also “derived class” or “child class”), and the class inherited from is called the superclass (also “base class” or “parent class”). Super classes may themselves inherit from other classes, resulting in a hierarchy of classes
- What are the benefits of using inheritance ? #card
  id:: 6a87c732-c1a3-40bd-aca1-85a955a4f994
	- It represents real-world relationships between the types.
	- It provides the reusability of a code. Also, it allows to add more features to a class
	  without modifying it.
	- It offers a simple, understandable model structure.
	- It is transitive in nature, which means that if class B inherits from another class A, then all the subclasses of B would automatically inherit from class A.
	- Less development and maintenance expenses
- What are the possible relationship possible between classes? #card
  id:: 6a87c7a6-6644-45a0-8666-881e4a2f8006
	- Is-a relationship: Ex: Cat is an Animal. We can have a class for Animal and class for Cat . A Bus is a vehicle similary
	- Has-a relationship: this is also called composition. A Car has an engine , tyres etc. Engine can be a class with attributes such as the capacity, fuel type used etc. Car class will have manufactured year, color etc. The car class has a instance of the Engine class associated with it
	- The inheritance is applicable for **is-a** relationship
- What are the different types of inheritances possible for the is-a relationship? #card
  id:: 6a87c9bd-1205-4475-a46d-328aa72aee17
	- 1. Single level inheritance
	  2. Multi-level inheritance
	  3. Multiple inheritance
	  4. Hierarchical inheritance
	  5. Hybrid inheritance
- What does the Single-level inheritance mean? Give an example? #card
  id:: 6a87ca67-229f-46de-b69b-eb80e252f4d0
	- A single level inheritance means that there is only one parent and child levels
- How you specify the inheritance relationship in python? #card
  id:: 6a87cc3b-f45f-4061-be25-983894cfc642
	- In the child class the base class is specified in parenthesis after the class name
	- ```python
	  class BaseClass:
	    #code
	  
	  class DerivedClass(BaseClass):
	    #code
	  ```
	- ```python
	  class Animal:
	      def make_sound(self):
	          print("No sound")
	   
	  class Cat(Animal):
	      def make_sound(self):
	          print("Meow")
	  
	          
	  c = Cat()
	  c.make_sound()
	  Meow
	  
	  ```
- What is the super()  method? When is it needed/used? #card
  id:: 6a87fa5f-d990-4a43-82bc-090878a41eb4
	- A built-in function super() provides a way to access methods and properties from a parent or superclass within a subclass. It is commonly used in inheritance to call methods or access attributes from the parent class. A subclass can override methods or attributes from its superclass. However, there might be situations where you want to use the overridden method as well as the functionality of the parent method within the overridden
	  method of the subclass. That's where super() becomes helpful.
- Give an example of using the super() method? #card
  id:: 6a87fad3-7899-4fc7-94aa-17b992886703
	- ```python
	  class A:
	      def disp(self):
	          print("in disp A")
	  class B(A):
	      def disp(self):
	          super().disp()
	          print("in disp B")
	  
	  a1=A()
	  a1.disp()
	  b1=B()
	  b1.disp()
	  ```
- Program to demonstrate parent constructors #card
  id:: 6a8805e3-b395-4ada-a40d-8fe861cce9f2
	- ```python
	  class Person:
	      def __init__(self, name, idnumber):
	          self.name = name
	          self.idnumber = idnumber
	          
	      def display(self):
	          print(self.name)
	          print(self.idnumber)
	  
	  class Employee(Person):
	      def __init__(self, name, idnumber, salary, desgn):
	          self.salary = salary
	          self.desgn = desgn
	          Person.__init__(self, name, idnumber)
	  
	  
	  emp = Employee('Riya', 802, 50000, "Admin")
	  emp.display()
	  
	  ```
- What is multi-level inheritance? Give an example? #card
  id:: 6a880604-3d26-4b9a-bf22-0bce2a511400
	- ```python
	  class Shape:
	      def __init__(self, name):
	          self.name = name
	  def info(self):
	      return self.name
	  
	  
	  class Polygon(Shape):
	      def __init__(self, name, sides):
	          super().__init__(name)
	          self.sides = sides
	  
	      def info(self):
	          return f"A {self.name} is a polygon with {self.sides} sides."
	  
	  class Triangle(Polygon):
	      def __init__(self, name):
	          super().__init__(name, 3)
	  
	  class Quadrilateral(Polygon):
	      def __init__(self, name):
	          super().__init__(name, 4)
	  
	  
	  triangle = Triangle("Triangle")
	  print(triangle.info())
	  quadrilateral = Quadrilateral("Quadrilateral")
	  print(quadrilateral.info())
	  
	  ```
- What is multiple inheritance?
	- A class can have more than one super class and inherit the features from all parents.
	- C++ and Python support multiple inheritance. Java did not include this feature as it was a major source of bugs and confusion.
	- Similar functionality can be supported using interfaces in Java
	- Note: Additional notes to be included based on the need and the progress
-
- What is Hierarchial inheritance? #card
  id:: 6a880863-313f-4bb6-b2a6-4787b1fb1579
	- A super class can have multiple base classes. This is the typical need for having inheritance.
	- Ex : Animal super class can be inherited by `Cat` , `Dog and the `Duck`
	- This is nothing but single inheritance at the end of it
	-
- What is hybrid inheritance? #card
  id:: 6a8808fc-0f12-480c-aa2d-1ac990742749
	- A mix of two or more types of inheritance. Also known as *Diamond shaped inheritance*
- How to get the info on the parent class from which the class is inheriting? #card
  id:: 6a880968-5662-4e09-a1ce-eccc46da8e0d
	- To get the immediate parent use the `__bases__` property on the class
	- ```python
	  print(Person.__bases__)
	  print(Student.__bases__)
	  print(UGStudent.__bases__)
	  print(PGStudent.__bases__)
	  ```
- How get all the parents of a given type? #card
  id:: 6a880a0e-b417-42c8-a0e7-b4c0dbadb830
	- use the `__mro__` property in 3.10 olr the mro() from the inspect module in other versions
- Which type is the parent of all the types? #card
  id:: 6a880a4c-bfbb-4052-8229-d5b9754d004b
	- object type
- How to check if an object instance is an instance of a particular type? #card
  id:: 6a880a7f-5253-4577-862b-5d3adec29672
	- use `isinstance(instance,type) ->bool`
	- ```python
	  isinstance(5, int)
	  True
	  ```
- How to determine if a subclass is a subclass of a class? #card
  id:: 6a880af0-21fb-40dc-9a12-17847ca16947
	- use `issubclass(sub,super) -> bool`
	- ``` print(issubclass(Student, Person))```
- How to provide a custom string that is displayed when the print method is passed an object of a class? #card
  id:: 6a880b2b-e4ba-444c-bffc-07054f264464
	- Override the `__str__()` method
	- ```python
	  class Student:
	    def __init__(self, first_name, last_name):
	      self.first_name = first_name
	      self.last_name = last_name
	     
	    def __str__(self):
	      return self.first_name + "  " + self.last_name
	  ```
-