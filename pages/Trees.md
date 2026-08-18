title:: Trees
#+BEGIN_IMPORTANT
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
  id:: 6a58ad2d-9164-4a79-94aa-6fc422bec248
	- A binary tree is a tree In which each node has up to two children. A tree could have More than three children I
- What is the difference between a binary tree vs binary search tree? #card
  id:: 6a58ad2d-2ecb-4df6-b2f7-320eed5a5f50
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
	  id:: 6a58ad2d-9b39-4224-aa7d-ba5ef8a55823
		- Show complete binary tree is a binary tree in which every level of the tree is filled, except for perhaps the last level. To the extent that the last level is filled It is filled from left to right
	- What is a Full binary tree? #card
	  id:: 6a58ad2d-7474-481a-be1a-fa5a534c68f3
		- A full binary Is a binary tree in which every known has either zero or two children. .i.e that is no nodes have only one child
	- What is a perfect binary tree? #card
	  id:: 6a58ad2d-4652-4c0c-9de3-5babf0fe7d30
		- a perfect binary iii is one that is both full and complete. All leaf notes will be at the same level and this level has the maximum number of nodes.
		-
- # Binary tree traversal
	- In-Order : visit - left branch , then current node then right branch
	- Pre-Order: visit -Current node, left branch and then right branch
	- Post-Order : visit - left branch , right branch and then current node
	-
	- Create a Binary tree as below #card
	  id:: 6a58ad2d-d9d7-4196-9301-364e8b36af1f
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
		  id:: 6a58ad2d-4e3f-4bad-bb87-2419d6426790
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
		  id:: 6a58ad2d-0f6f-43d7-96fd-bd46ebb1ddf3
			-
		- Write a function to perform the post-order traversal of a binary tree #card
		  id:: 6a58ad2d-f937-4be2-a231-1b1cb9e8995d
- # Binary Heaps (Min-heaps and Max- Heaps)
	- What is a min-heap (min-binary heap)? #card
	  id:: 6a58ad2d-0175-4da1-8a04-1e5516d20b0c
		- A min-heap is a complete binary tree(that is, totally filled other than the rightmost elements on the last level), where each node is smaller than its children. The root, therefore, is the minimum element in the tree
		- There are two key operations on a min-heap: insert and extract_min
	- What a max-heap (max-binary-heap) ? #card
	  id:: 6a58ad2d-0d46-495c-b554-db5ff2b35475
		- A max-heap is a complete binary tree(that is, totally filled other than the rightmost elements on the last level), where each node is greater than its children. The root, therefore, is the maximum element in the tree
	- What is the algorithm for inserting into a min-heap? #card
	  id:: 6a58ad2d-229c-4d30-b044-1326d90bca87
		- The new element is always inserted at the bottom. The insert is done at the rightmost spot so as to maintain the complete tree property. Then the tree is fixed by swapping the new element with its parent, until an appropriate sport is found. Essentially the element is bubbled up the minimum element
		- This takes O(log n) times
	- How is the minimum element extracted and then the property of the tree is maintained? #card
	  id:: 6a58ad2d-83a8-44e8-bf7c-28834b7a388f
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
		  id:: 6a58ad2d-0f4f-4d40-b792-d48d013deb2c
			- Both actually take O(K) where K is the length of the string. Incase of Hashes, the string must be read fully to convert into a hash value.
		- #+BEGIN_IMPORTANT
		  Many problems involving list of valid words leverage a trie as an optimization. In situations where we search through the tree on related prefixes repeately (e.g looking up M, then MA, htne MAN, then MANY) we migh pass around a reference to the current node in the tree. This will allow us to just check if Y is a child of MAN, rather than starting from root each time
		  #+END_IMPORTANT
- # Exercises
	- **MInimal Tree** : Given a sorted (increasing order) array with unique integer elements, write an algo to create a binary search tree with minimal height #card
	  id:: 6a58ad2d-168c-43ed-8fd7-81c234e94a03
		- hints
		- A minimal binary tree will have about the same number of nodes on the left and right od each node. Let's focus on the root and how would you ensure that the same number of nodes are on the left and right of the root
		- Can this problem be solved by recursion? Try to break this problem into subproblems
		- ```python
		  import unittest
		  from typing import List
		  
		  # since the array is sorted, we can utilize this fact to create a tree.
		  # The smallest tree will be from 3 nodes with the middle node
		  # being the root and the first node being the left and the node
		  # after middle being the right
		  
		  
		  class TreeNode:
		      def __init__(self, value: int):
		          self.value = value
		          self.left = None
		          self.right = None
		  
		  
		  def create_minimal_bst(arr: List[int], start: int | None, end: int | None) -> TreeNode:
		      # print(f"start:{start} end:{end}")
		      if end < start:
		          return None
		  
		      mid = (start + end)//2
		      print(f"creating the node for {mid}")
		      node = TreeNode(arr[mid])
		      node.left = create_minimal_bst(arr, start, mid - 1)
		      node.right = create_minimal_bst(arr, mid+1, end)
		      return node
		  
		  
		  class check_minimal_bst(unittest.TestCase):
		  
		      def test_input1(self):
		          arr = [1, 2, 3]
		          n = create_minimal_bst(arr, 0, len(arr) - 1)
		          self.assertEqual(n.value, 2)
		          self.assertEqual(n.left.value, 1)
		          self.assertEqual(n.right.value, 3)
		  
		      def test_zero_elements(self):
		          arr = []
		          n = create_minimal_bst(arr, 0, len(arr) - 1)
		          self.assertIsNone(n)
		  
		  
		  if __name__ == "__main__":
		      unittest.main()
		  
		  ```
		- TODO Leetcode 108 is the same question: Using the solution solve it on Leetcode and submit it. You can search it using 108 in the search 
		  https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/description/
		- ```python
		  # Definition for a binary tree node.
		  # class TreeNode:
		  #     def __init__(self, val=0, left=None, right=None):
		  #         self.val = val
		  #         self.left = left
		  #         self.right = right
		  class Solution:
		      def create_minimal_bst(self, arr: List[int], start , end):
		      # print(f"start:{start} end:{end}")
		          if end < start:
		              return None
		  
		          mid = (start + end)//2
		          print(f"creating the node for {mid}")
		          node = TreeNode(arr[mid])
		          node.left = self.create_minimal_bst(arr, start, mid - 1)
		          node.right = self.create_minimal_bst(arr, mid+1, end)
		          return node
		  
		      def sortedArrayToBST(self, nums: List[int]) -> Optional[TreeNode]:
		          result = self.create_minimal_bst(nums, 0 , len(nums) -1)
		          return result
		          
		  ```
		- TODO Solve Leetcode 109: Same question but using linkedlist https://leetcode.com/problems/convert-sorted-list-to-binary-search-tree/description/
		-
	- **List of Depths**: Given a binary tree, design an algorithm which creates a linked list of all the nodes at each depth(e.g if you have a tree with depth D, you'll have D linked lists)
		- What are the different ways of traversing a tree? Isn't tree a graph ?
		- ```python
		  import unittest
		  from typing import List, Optional
		  
		  
		  # **List of Depths**: Given a binary tree, design an algorithm which creates
		  # a linked list of all the nodes at each depth
		  # (e.g if you have a tree with depth D, you'll have D linked lists)
		  
		  # In this case instead of SLL we will create an python list.
		  # It can be easily extended to LinkedList.
		  # hints 107: Try modifying a graph search algo to track the depth of the tree
		  # hint 123: a hast table or an array that maps from level number to the nodes
		  # at that level might be useful
		  # hint 135: You could come up with an algorithm that combines BFS and DFS
		  
		  # Definition for a binary tree node.
		  class TreeNode:
		      def __init__(self, val=0, left=None, right=None):
		          self.val = val
		          self.left = left
		          self.right = right
		  
		  
		  class Solution:
		      def levelOrder(self, root: Optional[TreeNode]) -> List[List[int]]:
		          result_list = []
		          queue: List[TreeNode] = []  # A queue needed for BFS
		          level = 0  # track the level of the node being traversed
		          queue.append((root, 0))  # add the first element to the queue
		          while (len(queue) > 0):  # process until there are elements
		              curr_node, level = queue.pop(0)
		              try:
		                  level_list = result_list[level]
		                  level_list.append(curr_node.val)
		              except IndexError:
		                  result_list.insert(level, [curr_node.val])
		              if curr_node.left:
		                  queue.append((curr_node.left, level + 1))
		              if curr_node.right:
		                  queue.append((curr_node.right, level + 1))
		          return result_list
		  
		  
		  class check_list_of_depths(unittest.TestCase):
		      def test_input1(self):
		          t1 = TreeNode(1)
		          t1.left = TreeNode(2)
		          t1.right = TreeNode(3)
		          result = Solution().levelOrder(t1)
		          print(result)
		          self.assertEqual(result, [[1], [2, 3]])
		  
		      def test_input2(self):
		          t1 = TreeNode(1)
		          t1.left = TreeNode(2)
		          t1.right = TreeNode(3)
		  
		          t2 = t1.right
		          t2.right = TreeNode(6)
		          result = Solution().levelOrder(t1)
		          print(result)
		          self.assertEqual(result, [[1], [2, 3], [6]])
		  
		  
		  if __name__ == "__main__":
		      unittest.main()
		  
		  
		  
		  
		  
		  
		  ```
- **Check Balanced** Implement a function to check if a binary tree is balanced. For the purposes of this question, a balanced tree is defined to be a tree such that the heights of the two subtrees of any node never differ by more than one #card
  id:: 6a590f62-f25c-42d0-a0d6-715bd9b7c38a
	- Leetcode question 110: https://leetcode.com/problems/balanced-binary-tree/description/
	- ```python
	  import unittest
	  from typing import Optional
	  
	  # Definition for a binary tree node.
	  
	  
	  class TreeNode:
	      def __init__(self, val=0, left=None, right=None):
	          self.val = val
	          self.left = left
	          self.right = right
	  
	  
	  class Solution:
	      def isBalanced(self, root: Optional[TreeNode]) -> bool:
	          if not root:  # root is none
	              return True
	          else:
	              result = self.traverse_tree(root)
	              if result == -2:
	                  return False
	              return True
	  
	      def traverse_tree(self, root: Optional[TreeNode]) -> int:
	          if not root:
	              return -1
	          else:
	  
	              left_height = self.traverse_tree(root.left)
	              right_height = self.traverse_tree(root.right)
	              if left_height == -2 or right_height == -2:
	                  return -2
	  
	              # Question: Why is the below code needed
	              print(f"value:{root.val} left_height:{left_height} right_height:{right_height} diff: {abs(left_height - right_height)}")
	              if abs(left_height - right_height) > 1:
	                  print("Tree imbalanced: {root.val}")
	                  return -2  # Tree is not balanced
	              else:
	                  return max(left_height, right_height) + 1
	  
	  
	  class check_balanced(unittest.TestCase):
	  
	      # def test_input1(self):
	      #     root = TreeNode(0)
	      #     root.left = TreeNode(1)
	      #     root.right = TreeNode(2)
	      #     result = Solution().isBalanced(root)
	      #     self.assertTrue(result)
	  
	      # def test_input2(self):
	      #     root = TreeNode(0)
	      #     root.left = TreeNode(1)
	      #     root.left.left = TreeNode(2)
	      #     result = Solution().isBalanced(root)
	      #     self.assertFalse(result)
	  
	      # # Test case added as per Leetcode
	      # def test_input3(self):
	      #     root = None
	      #     result = Solution().isBalanced(root)
	      #     self.assertTrue(result)
	  
	      def test_input4(self):
	          root = TreeNode(1)
	          two1 = TreeNode(2)
	          root.left = two1
	          three1 = TreeNode(3)
	          two1.left = three1
	          four1 = TreeNode(4)
	          three1.left = four1
	  
	          two2 = TreeNode(2)
	          root.right = two2
	          three2 = TreeNode(3)
	          two2.right = three2
	          four2 = TreeNode(4)
	          three2.right = four2
	  
	          result = Solution().isBalanced(root)
	  
	          self.assertFalse(result)
	  
	  if __name__ == "__main__":
	      unittest.main()
	  
	  ```
- **Validate BST** : Implement a function to check if  a binary tree is binary search tree? #card
  id:: 6a5996cf-17b6-4524-826f-522eb983031c
	- What conditions need to satisfied to say a tree is balanced?
	- leetcode 98: https://leetcode.com/problems/validate-binary-search-tree/description/
	-
	- 1. Left Subtree Condition
		- All node values in the **left subtree** must be strictly **less than** the parent node's value. [[1](https://levelup.gitconnected.com/mastering-binary-search-tree-bst-e860c1e3ac39), [2](https://unstop.com/blog/difference-between-binary-tree-and-binary-search-tree)]
	- 2. Right Subtree Condition
		- All node values in the **right subtree** must be strictly **greater than** the parent node's value. [[1](https://levelup.gitconnected.com/mastering-binary-search-tree-bst-e860c1e3ac39)]
	- 3. Recursive Validity
		- Both the left and right subtrees must also be valid Binary Search Trees. [[1](https://algo.monster/liteproblems/1373)]
	- An Important Traps to Watch Out For
	- #+BEGIN_IMPORTANT
	  It is a common mistake to only check if a node is greater than its immediate left child and less than its immediate right child. **That is not enough.** Every single node in the entire left branch must be smaller than the root. [[1](https://neetcode.io/solutions/validate-binary-search-tree), [2](https://algomaster.io/learn/dsa/validate-binary-search-tree), [3](https://www.guvi.in/blog/binary-tree-vs-binary-search-tree/)]
	  #+END_IMPORTANT
		- **Example of a FAILED BST:**
			- text
			- ```
			            5
			           / \
			          3   7
			             /
			            4   <-- Invalid! 4 is less than 5, but it is in the right subtree of 5.
			  ```
		- ```python
		  import unittest
		  from typing import Optional
		  # Definition for a binary tree node.
		  
		  
		  class TreeNode:
		      def __init__(self, val=0, left=None, right=None):
		          self.val = val
		          self.left = left
		          self.right = right
		  
		  
		  class Solution:
		      def traverse_bst(self, root: Optional[TreeNode], start: int | float, end: int | float) -> bool:
		          if not root:
		              return True
		          # if  root.val < start or root.val > end:
		              # return False
		          if not (start < root.val < end):
		              return False
		          else:
		  
		              left = self.traverse_bst(root.left, start, root.val)
		  
		              right = self.traverse_bst(root.right, root.val, end)
		  
		              return left and right
		  
		      def isValidBST(self, root: Optional[TreeNode]) -> bool:
		          return self.traverse_bst(root, float('-inf'), float('+inf'))
		  
		  
		  class test_bst(unittest.TestCase):
		  
		      def test_input1(self):
		          root = TreeNode(5)
		          root.left = TreeNode(1)
		          root.right = TreeNode(25)
		          result = Solution().isValidBST(root)
		          self.assertTrue(result)
		  
		      def test_input2(self):
		          root = TreeNode(2)
		          root.left = TreeNode(1)
		          root.right = TreeNode(3)
		          result = Solution().isValidBST(root)
		          self.assertTrue(result)
		  
		  
		  
		  if __name__ == "__main__":
		      unittest.main()
		  
		  ```
	- **Successor** : Write an algorithm to find the "next" node (i.e in-order successor) of a given node in a binary search tree. You may assume that each node has a link to its parent #card
	  id:: 6a599714-02ea-4943-9df1-ecbfacdb5c67
		- How do you define the next node of a node ?
			- It is the leftmost node of the right subtree of the node. In the case of in-order traversal the depth of the tree is traversed completely
			- If there is no right subtree then you need to traverse the tree up using the parent node links and then look for the parent in which the child is the left subtree of the parent ? Why is it the left subtree?
			- ```python
			  import unittest
			  from typing import Optional
			  
			  
			  class TreeNode:
			      def __init__(self, val=0, parent=None, left=None, right=None):
			          self.val = val
			          self.parent = parent
			          self.left = left
			          self.right = right
			  
			  
			  class Solution:
			      def successor(self, node: TreeNode) -> Optional[TreeNode]:
			          if not node:
			              return None
			  
			          # if the right subtree exists then check the leftmost child of the right subtree
			          if node.right:
			              curr = node.right
			              while curr:
			                  if curr.left:
			                      curr = curr.left
			              return curr
			          elif node.parent:
			              curr = node
			              parent = node.parent
			              while (parent):
			                  if parent.left == curr:
			                      return parent
			                  else:
			                      curr = parent
			                      parent = parent.parent
			  
			          print("No successor found")
			          return None
			  
			  
			  class check_successor(unittest.TestCase):
			  
			      #       0
			      #     1    2
			      #   3    4
			      #  find next node of 4. Answer : 0
			      def test_input1(self):
			          root = TreeNode(0)
			          one = TreeNode(1, root)
			          root.left = one
			          two = TreeNode(2, root)
			          root.right = two
			          three = TreeNode(3, one)
			          one.left = three
			          four = TreeNode(4, one)
			          one.right = four
			  
			          result = Solution().successor(four)
			          self.assertEqual(result.val, 0)
			  
			      def test_input2(self):
			          root = TreeNode(0)
			          one = TreeNode(1, root)
			          root.left = one
			          two = TreeNode(2, root)
			          root.right = two
			          three = TreeNode(3, one)
			          one.left = three
			          four = TreeNode(4, one)
			          one.right = four
			  
			          result = Solution().successor(two)
			          self.assertIsNone(result)
			  
			  
			  if __name__ == "__main__":
			      unittest.main()
			  
			  ```
			-