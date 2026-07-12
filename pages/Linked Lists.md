# The `Runner` Technique
	- The `runner` (or second pointer) technique is used in many linked list problems.
-
- # Questions
	- Remove dups: Write code to remove duplicates from an unsorted linked list ?
		- In python removing duplicates is simple - converting into a set
		- Write code for using the class  based approach
	- Return Kth to Last:  Implement an algorithm to find the kth to the last element of a singly linked list
	  Hint : Can you use the runner method to run through the linked list ?
	  If you know the size of the list will it be simplified?
	  #card
	-
	-
		- ```python
		  # Return kth last element
		  
		  import unittest
		  
		  
		  class Node:
		      def __init__(self, value):
		          self.value = value
		          self.next = None
		  
		  
		  class LinkedList:
		      def __init__(self):
		          self.head: Node = None  # set the default value
		          self.count: int = 0
		  
		      def addElement(self, value):
		          curr: Node = self.head
		  
		          if not curr:
		              self.head = Node(value)
		  
		          else:
		              while curr.next:
		                  curr = curr.next
		              curr.next = Node(value)
		  
		          self.count += 1
		  
		      def print(self):
		          print("called print")
		          curr = self.head
		          i: int = 0
		          while curr:
		              i += 1
		              print(f" {i} : {curr.value}")
		              curr = curr.next
		  
		      def get_count(self) -> int:
		          return self.count
		  
		      def get_kth_last_element(self, k):
		          # the logic is to have two runners. faster and slower. The slower will
		          # start when the faster has traversed k elements.  By the time the faster reaches the last
		          # element the slower would have reached kth element from the last
		  
		          faster: int = 0
		          slower: int = -k
		          kth_node = None
		  
		          curr = self.head
		          while curr:
		              # print(f" k-curr : {curr.value}")
		              # If there is a next element then increment the faster and slower pointers. When i have moved k elements then set
		              # the kth_node to curr and afer that keep moving the kth_node pointer to the next nodes
		              if curr.next:
		                  faster += 1
		                  slower += 1
		                  if slower == 0:
		                      kth_node = curr
		                  elif slower >= 0:
		                      kth_node = kth_node.next
		  
		              curr = curr.next
		  
		          if slower >= 0:
		              return kth_node.value
		          else:
		              print("The list has less than k node")
		              return None
		  
		  
		  class Check_linkedList(unittest.TestCase):
		      def test_create_linked_list(self):
		          linked_list = LinkedList()
		          linked_list.addElement(1)
		          linked_list.addElement(2)
		          linked_list.addElement(3)
		  
		          # linked_list.print()
		          self.assertEqual(linked_list.get_count(), 3)
		  
		      def test_kth_node1(self):
		          linked_list = LinkedList()
		          linked_list.addElement(1)
		          linked_list.addElement(2)
		          linked_list.addElement(3)
		  
		          # linked_list.print()
		          self.assertEqual(linked_list.get_kth_last_element(1), 2)
		  
		      def test_kth_node2(self):
		          linked_list = LinkedList()
		          linked_list.addElement(1)
		          linked_list.addElement(2)
		          linked_list.addElement(3)
		  
		          # linked_list.print()
		          self.assertIsNone(linked_list.get_kth_last_element(4), 2)
		  
		  
		  if __name__ == "__main__":
		      unittest.main()
		  ```
	- Delete middle node? Implement an algorithm to delete a node in the middle (i.e  any node but the first and last node; not ncessarily the exact middle) of a singly linked list, given only access to that node
	  #card
		-
	- Partition: Write code toe partition a linked list around a value x, such that all the values less than x are to the left of the value. If x is contained within the list , the values of x only need to be after the elements less than x. The partition element x can appear anywhere in the "right partition" . It does not need to appear between the left and right partiion
	  Ex:
	  Input 3 -> 5 -> 8 ->5 ->10 ->2 (partition = 5)
	  Output 3 ->1 -> 2 -> 10 -> 5 -> 5 ->8
	  #card
	- Loop Detection: Given a circular linked list, implement an algorithm that returns the node at the beginning of the loop
	  Defn : Circular linked list : A (corrupt) linked list in which a node's next pointer points to an earlier node, so as to make a loop in the linked list
	  Input : A -> B -< C -> D -> E -> C ( the same C as earlier)
	  Outut - C
		- Traverse the linked list and store the elements already encountered in a hash table.
		- ```python
		  import unittest
		  
		  
		  class Node:
		      def __init__(self, value):
		          self.value = value
		          self.next = None
		  
		  
		  class LinkedList:
		      def __init__(self):
		          self.head: Node = None  # set the default value
		          self.count: int = 0
		  
		      def addElement(self, value):
		          curr: Node = self.head
		  
		          if not curr:
		              self.head = Node(value)
		  
		          else:
		              while curr.next:
		                  curr = curr.next
		              curr.next = Node(value)
		  
		          self.count += 1
		  
		      def print(self) -> str:
		          print("called print")
		          s = ""
		          curr = self.head
		          i: int = 0
		          while curr:
		              i += 1
		              s = s + str(curr.value) + ':'
		              print(f" {i} : {curr.value}")
		              curr = curr.next
		          return s
		  
		      def get_count(self) -> int:
		          return self.count
		  
		  
		  def detect_loop(ll: LinkedList) -> int | None:
		      d = {}
		      curr = ll.head
		      while (curr):
		          if curr.value in d:
		              return curr.value
		          else:
		              d[curr.value] = 1
		              curr = curr.next
		      return None
		  
		  
		  class check_loops(unittest.TestCase):
		      def test_input1(self):
		          ll = LinkedList()
		          ll.addElement(10)
		          ll.addElement(3)
		          ll.addElement(6)
		          ll.addElement(4)
		          ll.addElement(3)
		          result = detect_loop(ll)
		          self.assertEqual(result, 3)
		  
		  
		  if __name__ == "__main__":
		      unittest.main()
		  
		  ```