- #+BEGIN_IMPORTANT
  Being able to implement trees and graphs from basics is essential
  #+END_IMPORTANT
- # Types of Trees
	- A tree can be understood recursively
		- Each tree has a root node
		- The root node has zero or mode child nodtes
		- Each child node has zero or more child nodes and so on
		- The tree cannot contain cycle. The nodes may or may not be in a particular order. They could have any datatype as values and they may or may not have links back to their parent nodes
- # Defn of a node
	- Create a tree as below and print
		- {{renderer :drawio, 1783878878314.svg}}
		- ```python
		  from __future__ import annotations
		  import unittest
		  
		  
		  class Node:
		      def __init__(self, value: int):
		          self.value: int = value
		          self.children: List[Node] = []
		  
		      def addChild(self, value: int) -> Node:
		          child = Node(value)
		          self.children.append(child)
		          return child
		  
		      # a depth first search printing the current node and then
		      # calling the print on the children recursively
		  
		      def print(self):
		          print(f"value:{self.value}")
		          for child in self.children:
		              child.print()
		  
		  
		  class check_tree_creation(unittest.TestCase):
		      def test_addingchildre(self):
		          root = Node(8)
		          child1 = root.addChild(4)
		          child2 = root.addChild(6)
		          child3 = root.addChild(10)
		  
		          child4 = child1.addChild(2)
		          child5 = child1.addChild(1)
		          root.print()
		  
		  
		  if __name__ == "__main__":
		      unittest.main()
		  
		  ```
		-
- What is the difference between trees and binary tree? #card
	- A binary tree is a tree In which each node has up to two children. A tree could have More than three children I
- What is the difference between a binary tree vs binary search tree? #card
	- A binary search tree is a binary tree in which each node hits a specific ordering condition. All left descendants are lesser than or equal to n And all right descendants are greater than n. This must be true for each node n
	- The definition of a binary search tree Can vary slightly with respect to equality. Under some definitions The tree cannot have duplicate values. In others the duplicate values will be on the right or can be on either side. All are valid definitions But you should clarify this with you were interviewers
	- #+BEGIN_IMPORTANT
	  When given a tree question Many candidates assume the interviewer means a binary search tree. Be sure to ask. A binary search tree imposes the condition that 4 each node Its left descendant are less than or equal to the current node, which is less than the right descendants
	  #+END_IMPORTANT
- # Note on balanced trees
	- #+BEGIN_NOTE
	  While many trees are balanced not all are. Ask for clarification. Note that balancing a tree does not mean the left and right subtrees are exactly the same size gir. One way to think about it is that a balanced tree really means something more like not terribly imbalance. It's balanced enough to ensure O(log n) times for insert and find. But its not necessarily balanced as it could be.
	  #+END_NOTE
	- #+BEGIN_NOTE
	  Two common types of trees are Red-black trees and AVL Trees
	  #+END_NOTE
- # complete vs imcomplete binary tree
	- What is a complete binary tree? Draw some examples of a complete and incomplete binary tree #card
		- Show complete binary tree is a binary tree in which every level of the tree is filled, except for perhaps the last level. To the extent that the last level is filled It is filled from left to right
	- What is a Full binary tree? #card
		- A full binary Is a binary tree in which every known has either zero or two children. .i.e that is no nodes have only one child
	- What is a perfect binary tree? #card
		- a perfect binary iii is one that is both full and complete. All leaf notes will be at the same level and this level has the maximum number of nodes.
		-
- # Binary tree traversal
	- In-Order : visit - left branch , then current node then right branch
	- Pre-Order: visit -Current node, left branch and then right branch
	- Post-Order : visit - left branch , right branch and then current node
	-
	- Create a Binary tree as below #card
		- {{renderer :drawio, 1783990867348.svg}}
		- ```python
		  from __future__ import annotations
		  import unittest
		  
		  
		  class Node:
		      # constructor
		      def __init__(self, value: int) -> Node:
		          self.value: int = value
		          self.left: Node = None
		          self.right: Node = None
		  
		      def add_left_child(self, value: int) -> Node:
		          left: Node = Node(value)
		          self.left = left
		          return left
		  
		      def add_right_child(self, value: int) -> Node:
		          right: Node = Node(value)
		          self.right = right
		          return right
		  
		  
		  class check_tree_repr(unittest.TestCase):
		  
		      def test_tree1(self):
		          root = Node(10)
		          five = root.add_left_child(5)
		          twenty = root.add_right_child(20)
		  
		          nine = five.add_left_child(9)
		          eigtheen = five.add_right_child((18))
		  
		          three = twenty.add_left_child(3)
		          seven = twenty.add_right_child(7)
		  
		          self.assertEqual(root.left.value, 5)
		          self.assertEqual(root.left.right.value, 18)
		  
		  
		  if __name__ == "__main__":
		      unittest.main()
		  
		  ```
		- Write a function for performing the InOrder Traversal of a binary tree? #card
			- ```python
			  from __future__ import annotations
			  import unittest
			  
			  
			  class Node:
			      # constructor
			      def __init__(self, value: int) -> Node:
			          self.value: int = value
			          self.left: Node = None
			          self.right: Node = None
			  
			      def add_left_child(self, value: int) -> Node:
			          left: Node = Node(value)
			          self.left = left
			          return left
			  
			      def add_right_child(self, value: int) -> Node:
			          right: Node = Node(value)
			          self.right = right
			          return right
			  
			  def in_order_traversal(root: Node) -> str:
			      result = ""
			      if root.left:
			          left_value = in_order_traversal(root.left)
			          result = result + str(left_value)
			      result = result + str(root.value) + ":"
			      if root.right:
			          right_value = in_order_traversal(root.right)
			          result = result + str(right_value)
			      return result
			  
			  
			  class check_tree_repr(unittest.TestCase):
			  
			  # TODO : Notice how the values have been rolled up for testing
			  # The rolling up will be needed in many different problems
			  
			      def test_in_order_traversal(self):
			          root = Node(10)
			          five = root.add_left_child(5)
			          twenty = root.add_right_child(20)
			  
			          nine = five.add_left_child(9)
			          eigtheen = five.add_right_child((18))
			  
			          three = twenty.add_left_child(3)
			          seven = twenty.add_right_child(7)
			  
			          result = in_order_traversal(root)
			  
			          self.assertEqual(result, "9:5:18:10:3:20:7:")
			  ```
		- Write a function to perform the preorder traversal of binary tree? #card
			-
		- Write a function to perform the post-order traversal of a binary tree #card
- # Binary Heaps (Min-heaps and Max- Heaps)
	- What is a min-heap (min-binary heap)? #card
		- A min-heap is a complete binary tree(that is, totally filled other than the rightmost elements on the last level), where each node is smaller than its children. The root, therefore, is the minimum element in the tree
		- There are two key operations on a min-heap: insert and extract_min
	- What a max-heap (max-binary-heap) ? #card
		- A max-heap is a complete binary tree(that is, totally filled other than the rightmost elements on the last level), where each node is greater than its children. The root, therefore, is the maximum element in the tree
	- What is the algorithm for inserting into a min-heap? #card
		- The new element is always inserted at the bottom. The insert is done at the rightmost spot so as to maintain the complete tree property. Then the tree is fixed by swapping the new element with its parent, until an appropriate sport is found. Essentially the element is bubbled up the minimum element
		- This takes O(log n) times
	- How is the minimum element extracted and then the property of the tree is maintained? #card
		- The minimum element is always at the top in a min-heap. First, we remove the minimum element and sway it with the last element in the heap (i.e the bottom-most and the right-most). This is done to maintain the property of the tree (my guess). Then the element is bubbled down so that the min-heap property is restored.
		- While swapping the element with the child, either the right or the left element can be chosen depending on the values. There is no inherent ordering between the left and the right element, but you will have to pick the smaller one in order to maintain the min-heap orderning
		- This algorithm takes O(log n) time
- # Tries (prefix trees)
	- A trie is a variant of an n-ary tree in which characters are stored at each node. Each path down the tree may represent a word.
	- Below is an example of Tries
		- {{renderer :drawio, 1784079493662.svg}}
		- The * nodes (somtimes called "null nodes") are often used to indicate complete words. For example,  the fact that there is a * node under many indicates that MANY is a complete word. The existance of MA path indicates there are words that start with MA
		- The actual implementation of these * nodes can be a special type such as TerminatingTrieNode which inherits from TrieNode. Or we could just use a boolean flag terminates within the parent node
		- A node in a trie could have anywhere from 1 through ALPHABET_SIZE+1 children ( or 0 through ALPHABET_SIZE if boolean flag is used for termination).
	-
		- What is the runtime of the Trie for searching a word compared to hash? #card
			- Both actually take O(K) where K is the length of the string. Incase of Hashes, the string must be read fully to convert into a hash value.
		- #+BEGIN_IMPORTANT
		  Many problems involving list of valid words leverage a trie as an optimization. In situations where we search through the tree on related prefixes repeately (e.g looking up M, then MA, htne MAN, then MANY) we migh pass around a reference to the current node in the tree. This will allow us to just check if Y is a child of MAN, rather than starting from root each time
		  #+END_IMPORTANT
		-