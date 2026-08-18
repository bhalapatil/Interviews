- #+BEGIN_IMPORTANT
  You need to be comfortable with the ins and outs of the data structure. Questions can be quite tricky. 
  Some problems might be slight modifications on the original data structure. Others have more complex challenges
  #+END_IMPORTANT
- # Implement a stack
	- A stack data structure has LIFO. The following are the operations
		- `pop()` removes the top item from the stack
		- `push(item)` Add an item on the top of the stack
		- `peek()` Return to the top of the stack
		- `isEmpty()`: Return true if and only if the stack is empty
		-
	- Implement a stack to store integers using D ? #card
	  id:: 6a525490-3ffa-42f1-8634-806763d30a32
		-
	- How can you create a stack that can store anything? Such as Struct of Student or Struct of BankAccounts etc? #card
	  id:: 6a5254af-2bbe-4db8-bcea-3fb3158a5951
		- Use the implementation that uses `ints` and try to make it generic using `C Macros`
	- What features does compilers of modern programming languages like C++ or Java have for building DS that are generic? #card
	  id:: 6a525502-8b4e-4c53-9390-87a7c390555d
		- The features is called by different names in C++ they are called templates and in Java they are called Generics
	- Provide a Java implementation of a stack that is generic ? #card
	  id:: 6a52554f-4b63-47f7-87ff-98aef9aec5f6
		-
	- ## Some uses of stack
		- #+BEGIN_IMPORTANT
		  One case Where stacks are often useful Is in recursive algorithms. Sometimes You need to push temporary data onto a stack As you recurse, But then remove them as you backtrack If a recursive check failed. A stack offers an intuitive way of doing this.
		  #+END_IMPORTANT
		- #+BEGIN_IMPORTANT
		  Her stack can also be used to implement a recursive algorithm iteratively. Can you name some Methods that you used in your course where-in the recursive algorithm was converted into a iterative algorithm using stack
		  #+END_IMPORTANT
		-
- # Queues
	- A Queue Implements FIFO. The operations available on the Q are:
		- `add(item)` : Add an item
		- `remove()`: Remove the first item from the list
		- `peek()`: peek to the top of the queue
		- `isempty()` returning true if and only if the queue is empty
	- A Q can be implemented using the Linked List - just that the elements are added and removed from the same side
	-
	- Implement a Q that stores `ints` using Linked List in C? #card
	  id:: 6a52572a-c3f3-4787-a9b9-f83f2b3e724e
	- How can you convert the Q that stores only `ints` into a more generic DS ? #card
	  id:: 6a525738-a481-4d26-9413-2a2fc78f81b8
	- Provide a Java implementation of a Generic Queue ? #card
	  id:: 6a525796-ca6c-4ec7-bd4b-47d3cfee9a78
	- ## Uses of Q
		- Used in Breadth-First search or implementing a cache
		- In BFS Q was used to store the list of the nodes that needed to be processed. Each time a node was processed, the adjacent nodes were added to the back of the queue. This allows us to process nodes in the order in which they were viewed
	-
- # Questions
	- *Three in one* : Describe how you could a single array to implement three stack? #card
	  id:: 6a525833-2a5f-461c-ad7a-ec6e17a7e77f
	- *Stack Min* : How would you design a stack which, in addition to push an pop, has a function min which returns the minimum element? Push, pop and min should all operate in O(1) time #card
	  id:: 6a525856-32f9-40b1-bda9-681ac1f013f7
		- Hints : Build a logical diagram of the stack and observe how the min value changes as the elements are pushed and poped from the stack
		- ```python
		  # How would you design a stack which,
		  # in addition to push an pop,
		  # has a function min which returns the minimum element?
		  # Push, pop and min should all operate in O(1) time
		  
		  from typing import List, Tuple
		  import unittest
		  
		  # The stack will be implement using an array.
		  # Each element in the array will be a Tuple[Int , Int] consisting of the
		  # item to be placed on the stack and the minimum element until then
		  
		  
		  class StackMin:
		      def __init__(self):
		          self.arr: List[int] = []
		  
		      def push(self, item: int):
		          if len(self.arr) == 0:
		              elem = (item, item)
		              print(type(elem))
		              self.arr.append(elem)
		          else:
		              # Get the last inserted element in the arr
		              prev_elem: Tuple[int, int] = self.arr[len(self.arr) - 1]
		              # TODO practise writing if/else statements in a single line
		              # for simple cases
		              min_item = item if item < prev_elem[1] else prev_elem[1]
		              self.arr.append((item, min_item))
		  
		      def pop(self) -> Tuple[int, int]:
		          # Default is to remove the last element.
		          last_item = self.arr.pop()
		          return last_item
		  
		  
		  class check_min_stack(unittest.TestCase):
		      def test_input1(self):
		          stack = StackMin()
		          stack.push(1)
		          result = stack.pop()
		          self.assertTupleEqual(result, (1, 1))
		  
		      def test_input2(self):
		          stack = StackMin()
		          stack.push(10)
		          stack.push(3)
		          stack.push(25)
		          result = stack.pop()
		          self.assertTupleEqual(result, (25, 3))
		  
		  
		  if __name__ == "__main__":
		      unittest.main()
		  
		  ```
	- **Queue via stack** : Implement a MyQueue which implements a queue using stack #card
	  id:: 6a525471-4acf-46f3-9c4b-44f77a21e2e8
		- Logically how do you used two stack to implement a queue
		- ```python
		  import unittest
		  
		  # In creating a queue with a stack, two stacks are used
		  # When a dequeue is done on the queue, the elements from the first stack
		  # are pushed on the 2nd stack. The last element is returned and then
		  # the elements from the 2nd stack and pushed back on the first stack
		  
		  # The stack itself is created using the list and the append and the pop methods
		  # of the list
		  
		  
		  class MyQueue:
		      def __init__(self):
		          self.first_stack: List[int] = []
		          self.second_stack: List[int] = []
		  
		      def enqueu(self, item: int):
		          self.first_stack.append(item)
		  
		      def dequeue(self) -> int:
		          # keep removing the elements from the first stack using pop
		          # and add to the second stack.
		          while (len(self.first_stack) > 1):
		              elem = self.first_stack.pop()
		              self.second_stack.append(elem)
		          last_elem = self.first_stack.pop()
		          if len(self.first_stack) != 0:
		              print("Something wrong in pop!!")
		          # move the elements from the second stack to the first one
		          while (len(self.second_stack) > 0):
		              self.first_stack.append(self.second_stack.pop())
		          return last_elem
		  
		  
		  class check_myqueue(unittest.TestCase):
		      def test_single_deque(self):
		          Q = MyQueue()
		          Q.enqueu(1)
		          Q.enqueu(2)
		          Q.enqueu(3)
		  
		          result = Q.dequeue()
		          self.assertEqual(result, 1)
		  
		      def test_multiple_deque(self):
		          Q = MyQueue()
		          Q.enqueu(1)
		          Q.enqueu(2)
		          Q.enqueu(3)
		  
		          result = Q.dequeue()
		          result = Q.dequeue()
		          result = Q.dequeue()
		          self.assertEqual(result, 3)
		  
		  
		  if __name__ == "__main__":
		      unittest.main()
		  
		  ```
	- **Sort Stack** : Write a program to sort a stack such that the smallest items are on the top. You can use an additional temporary stack, but you may not copy the elements into any other data structure (such as an array). the stack support the following operations: push , pop , peek and isEmpty
	-
-