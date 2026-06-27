# Hash tables
	- How are hash tables implemented using the hash functions and linked list ? #card
		- The hash function is used to calculate an int or long using the key as input from the hash function. Then the hash index is used as an index into an array at which the key and the value is stored
	- How are collisions handled in the Hash table? #card
		- A linked list is maintained at each index and collisions are handled
	- What the different names used in  Hash tables? #card
		-
		- A hash table is a data structure used to store key-value pairs for highly efficient retrieval. Depending on the programming language, context, or theoretical computer science perspective, it goes by several other names. [[1](https://datastructures.maximal.io/hash-tables/)]
		- The most common alternative names include:
			- **Hash Map:** A term commonly used in Java and C++.
			- **Dictionary:** The standard term used in Python, C#, and Swift.
			- **Associative Array:** The formal mathematical or computer science term used for a collection of unique keys mapped to values.
			- **Map:** A shorter, common alias used broadly across many modern programming languages.
			- **Symbol Table:** Often used in compiler design and theoretical computer science to refer to a data structure that tracks information like variable names. [[1](https://medium.com/@poojadas053/hash-table-beea12d978b4), [2](https://study.com/academy/lesson/hash-tables-definition-use-functions.html), [3](https://www.cs.cornell.edu/courses/cs3110/2017fa/l/15-hashtable/notes.html), [4](https://ethans.co.in/blogs/hashmap-vs-hash-table-understanding-the-differences/), [5](https://datastructures.maximal.io/hash-tables/)]
		- Depending on specific implementation variations, you may also encounter terms like **Hash Set** (which stores only keys without accompanying values) or **Distributed Hash Table** (a decentralized variant used in distributed computing networks)
	- Ch1 : Q1 : Write a implementation of the hash table with arrays and linked list in c ? #card #cprogramming
		-
- # ArrayList and Resizeable Arrays
	- In some languages, arrays (often called lists ) are automatically resizeable. The array list or list will grow as you append items. In other languages the arrays are fixed length. the size is defined when you create the array
	- #+BEGIN_IMPORTANT
	  This is an important data structure for the interviews
	  #+END_IMPORTANT
	- How is any arraylist of the List in python implemented? Can you implement in C to store int values? #card #cprogramming
	- How do you extend the arraylist data structure to store values of any type ? #card #cprogramming
		- Hint : using macros
	- What will be the amortized runtime of the insertion into an list ? #card
		- O(1) . Suppose you have a list of size N, We can work backwards to compute how many elements are copied as the size increases. When we increase the array to K elements, the array was K/2 previously. Therefore we need to copy k/2 elements
		- ```
		  final capacity increase : n/2 elements to copy
		  previous capacity increase : n/4 elements to copy
		  previous capacity increase :: n/8 elements to copy
		  ....
		  second capacity increase : 2 elements to copy
		  first capacity increase : 1 element to copy
		  ```
		- The addition of this series is N/2 + N/ 4 + N/8 ...2 + 1. This is approximately N
- # Exercises
	- Is Unique : Part 1 :  Implement an algorithm to determine if a string has all unique characters? What will be the Space and time complexity ? #card
		-
	-
	- Is Unique : Part 2 : What if you cannot use any other additional data structures? What will be the space and time complexity ? #card #cprogramming
		-
	- Check Permutation: Given two strings, write a method to decide if one is a permutation of the other? #card
		- Hint: How do you decide that on string is a permutation of the other?
		- Two strings are a permutation of each other if the char counts are the same. To implement this we can use a dictionary and then compare the dictionaries
		- Important : You should not assume that the permutation is case insensitive. "God" is different from "dog". Also, you can check if the spaces are significant. i.e. if "God" is different from "God     ". If spaces are not significant then you should trim the string
		- ```python
		  import unittest
		  
		  
		  def isPermutation(s1: str, s2: str) -> bool:
		      d1 = {}
		      d2 = {}
		      for s in s1:
		          if s in d1:
		              d1[s] = d1[s] + 1
		          else:
		              d1[s] = 1
		  
		      for s in s2:
		          if s in d2:
		              d2[s] = d2[s] + 1
		          else:
		              d2[s] = 1
		      return d1 == d2
		  
		  
		  # step1 : Create a test class inheriting from the unittest.TestCase
		  
		  class check_permutations(unittest.TestCase):
		  
		      # Step2 : Create method that start with test
		      def test_input1(self):
		          result = isPermutation("god", "dog")
		          self.assertEqual(result, True)
		  
		      def test_input2(self):
		          result = isPermutation("god ", "dog")
		          self.assertEqual(result, False)
		  
		      def test_input3(self):
		          result = isPermutation("God ", "dog")
		          self.assertEqual(result, True)
		  
		  
		  if __name__ == "__main__":
		      unittest.main()
		  ```
	- URLify: Write a method to replace all the spaces in a string with "%20". #card
		- Hint: Count the number of characters in the string and how much is needed later
	- Palindrome permutation: Given a string, write a function to check if it is a permutation of a palindrome.
	  id:: 6a3ab47b-e5a8-46da-8e64-3c5d8924e194
		- What is a palindrome? What are the possible cases (even , odd) and what is are the features
		-