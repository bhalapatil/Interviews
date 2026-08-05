# Introduction
	- A tree is actually a type of graph, but not all graphs are trees. A tree is a connected graph without cycles
	- #+BEGIN_IMPORTANT
	  Graphs can be ither directed or undirected, While directed edges are like one-way street, undirected edges are like two-way street
	  A graph might consist of multiple isolated subgraphs. If there is a path between every pair of vertices, it is called a "connected graph"
	  The graph can also have cycles (or not). An ``acyclic graph` is one without cycles
	  #+END_IMPORTANT
- # graph representation
	- ## Adjacency list
		- Every vertex(or node) stores a list of adjacent vertices. It an undirected graph an edge like (a, b) would be stored twice: once in a's adjacent vertices and once in b's adjacent vertices
		- A simple definition for a graph node could look essentially the same as tree node
		- Represent the graph below as an adjacency list:
		- {{renderer :drawio, 1784476012979.svg}}
		- Represent the above graph in python? #card
			- ```python
			  from __future__ import annotations
			  import unittest
			  
			  
			  # Represents one node in the graph. The connections are maintained
			  # using the list
			  
			  class Node:
			      def __init__(self, name: str):
			          self.name: str = name,
			          self.edges: List[Node] = []
			  
			      def add_edge(self, child: Node):
			          self.edges.append(child)
			  
			  
			  class Graph:
			      def __init__(self):
			          self.nodes: List[Node] = []
			  
			      def add_node(self, node: Node):
			          self.nodes.append(node)
			  
			  
			  class check_graph_representation(unittest.TestCase):
			      def test_input1(self):
			          g: Graph = Graph()
			          one = Node('1')
			          g.add_node(one)
			          two = Node('2')
			          g.add_node(two)
			          self.assertTrue(True)
			  
			  
			  if __name__ == "__main__":
			      unittest.main()
			  
			  ```
- #+BEGIN_IMPORTANT
  You do not necessarily need classes to represent graphs. They can also be represented using simple builtin data structures such as an Array or a hash table etc
  #+END_IMPORTANT
	- Represent the above graph using simple data structures. #card
		- A simple dictionary can be used to represent a graph. The key of the graphs are individual nodes. The value is a list of nodes with each entry in the list represent an edge
		- For example the same graph can be represented as
			- ```
			  0: 1
			  1: 2
			  2: 0, 3
			  3: 2
			  4: 6
			  5: 4
			  6: 5
			  ```
		- #+BEGIN_NOTE
		  Although this is little bit more compact, it is not clean and intuitive. The preference is to use classes. However, some problems might use representations other than classes
		  #+END_NOTE
	- ## Adjacency Matrices
		- An adjacency matrix is an NxN boolean matrix (where N is the number of Nodes). Where a true value at matrix[i][j] indicates an edge from node i to node j (You can also use an integer matrix with 0s and 1s)
		- In an undirected graph, an adjacency matrix will be symmetric. In a directed graph, it will not (necessarily) be.
		- ||0|1|2|3|
		  |--|--|--|--|--|
		  |0|0|1|0|0|
		  |1|0|0|1|0|
		  |2|1|0|0|0|
		  |3|0|0|1|0|
	- #+BEGIN_IMPORTANT
	  
	  The same graph algorithms that are used on adjacency lists (breadth-first search etc) can be performed with adjacency matrices, but they may be somewhat less efficient. In the adjacency list represented, you can easily iterate through the neighbours of a node. In the adjacency matrix representation, you will need to iterate through all the nodes to identify a node's neighbours
	  
	  #+END_IMPORTANT
- # Graph Search
	- ## Depth First search
		- Start at the root (or another abitrary seleced node) and explore each branch completely before moving on to the next brach. That is, we go deep first (hence the name depth-first search) before we go wide
		- ```python
		  def search(root: Node):
		    if not root:
		      return None
		    visit(root)
		    root.visited = True
		    for n in root.adjacent:
		      if not n.visited:
		        search(n)
		  ```
	- ## Breadth First search
		- Breadth-first search and depth-first search tend to be used in different scenarios. DFS is often preferred if we want to visit every node in the graph. Both will work just fine, but depth-first search is a bit simpler.
		- However, if we want to find the shortest path (or just any path) between two nodes, BFS is generally better.
		- The BFS uses a queue and is not recursive
		- ```python
		  def search(root: Node):
		    q = queue()
		    root.marked = true
		    queue.enqueue(root) #add to th end of the queue
		    
		    while not queue.isEmpty():
		      r = queue.dequeue()
		      visit(r)
		      for each n in r.adjacent():
		        if not n.marked:
		          n.marked = True
		          queue.enqueue(n)
		  ```
		- #+BEGIN_IMPORTANT
		  Key thing to remember is that BFS uses a queue. The rest of the algorithm flows from this fact
		  #+END_IMPORTANT
	- ## Bidirectional search
		- Bidirectional search is used to find the shortest path between a source and destination node. It operates by essentially running two simultaneous breadth-first searches, one from each node. When their searches collide, we have found a path
		- #+BEGIN_PINNED
		  How to implement the bidrectional search? Is it done using different theards to ensure parallel execution ??
		  #+END_PINNED
- # Exercies
	- **Build Order** :  You are given a list of projects and a list of dependencies (which is a lit of pairs of projects, where  the second project is dependent on the first project). All of a project's dependencies must be built before the project is built. Find a build order that will allow the projects to be built. If there is no valid build order, return an error.
		- input
			- projects: a, b, c, d, e, f
			- dependencies (a , b) , (f ,b) , (b ,d) (f , a) (d ,c)
			- Output: f, e, a, b ,d ,c
		- Hints:
		- 26 47 60 85 125 133
	- Design an algorithm and write code to find the first common ancestor of two nodes in a binary tree. Avoid storing additional nodes in a data structure
		- 10 16 28 36 46 70 80 96
	- BST Sequences: A binary search tree was created by traversing through an array from left to right and inserting each element. Given a binary search tree with distinct elements print all possible arrays that could have let to this trree
	- {{renderer :drawio, 1784603573808.svg}}
	- Output: { 2 , 1, 3}, {2 , 3 , 1}
	- Hint: 39: What is the very first value that must be in the array - root
	- Hint:  48: The root is the very first value. What can you say about the order
	- Hint: 66 : T
	- Hint: 82: Break this down into subproblems. Use recursion, if you had all possible sequences for the left subtree and the right subtree, how could you create all possible sequences for the entire tree
	- ~~~~
	-