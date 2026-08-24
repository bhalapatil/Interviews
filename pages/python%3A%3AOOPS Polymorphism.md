- What is polymorphism? #card
  id:: 6a880d47-0264-41af-ae9d-e5a513325e3d
	- Polymorphism refers to having multiple forms.
	- refers to the use of the same function name, but with different signatures
	- allows objects of different classes to be treated as objects of a common superclass.
	- This concept enables a single interface to be used for entities of different types.
- What is runtime polymorphism? #card
  id:: 6a8816e2-c023-4f79-a00a-9cbdecf88f73
	- Python supports runtime polymorphism by using techniques like method overloading and method overriding
	- Runtime polymorphism is the ability of an object to behave differently based  on its actual type during program execution
	- It is also known as dynamic polymorphism
	- It enables the same method name to behave differently based on the specific class instance at runtime.
- What are key aspects of Runtime polymorphism? #card
  id:: 6a88173c-d2e6-4ef7-a10f-92ccd2fc3b42
	- Inheritance:
		- Runtime polymorphism is closely associated with inheritance.
		- Subclasses inherit methods from their superclass, and they can provide their own implementation for these methods.
	- Method Overriding:
		- Subclasses override methods from their superclass to provide their own specialized implementation
		- The method signature remains the same in both the superclass and subclass.
	- Dynamic Binding:
		- During runtime, the appropriate method to execute is dynamically determined
		- It is based on the actual type of the object invoking the method
	- Common Interface
		- Different subclasses sharing a common superclass interface
		- Exhibits different behaviors based on their specific implementations
-